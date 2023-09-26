Inserting Documents in a MongoDB Collection
Review the following code, which demonstrates how to insert a single document and multiple documents into a collection.


Insert a Single Document
Use insertOne() to insert a document into a collection. Within the parentheses of insertOne(), include an object that contains the document data. Here's an example:

db.grades.insertOne({
  student_id: 654321,
  products: [
    {
      type: "exam",
      score: 90,
    },
    {
      type: "homework",
      score: 59,
    },
    {
      type: "quiz",
      score: 75,
    },
    {
      type: "homework",
      score: 88,
    },
  ],
  class_id: 550,
})

Insert Multiple Documents
Use insertMany() to insert multiple documents at once. Within insertMany(), include the documents within an array. Each document should be separated by a comma. Here's an example:

db.grades.insertMany([
  {
    student_id: 546789,
    products: [
      {
        type: "quiz",
        score: 50,
      },
      {
        type: "homework",
        score: 70,
      },
      {
        type: "quiz",
        score: 66,
      },
      {
        type: "exam",
        score: 70,
      },
    ],
    class_id: 551,
  },
  {
    student_id: 777777,
    products: [
      {
        type: "exam",
        score: 83,
      },
      {
        type: "quiz",
        score: 59,
      },
      {
        type: "quiz",
        score: 72,
      },
      {
        type: "quiz",
        score: 67,
      },
    ],
    class_id: 550,
  },
  {
    student_id: 223344,
    products: [
      {
        type: "exam",
        score: 45,
      },
      {
        type: "homework",
        score: 39,
      },
      {
        type: "quiz",
        score: 40,
      },
      {
        type: "homework",
        score: 88,
      },
    ],
    class_id: 551,
  },
])


Finding Documents in a MongoDB Collection
Review the following code, which demonstrates how to query documents in MongoDB.

Find a Document with Equality
When given equality with an _id field, the find() command will return the specified document that matches the _id. Here's an example:

db.zips.find({ _id: ObjectId("5c8eccc1caa187d17ca6ed16") })
Find a Document by Using the $in Operator
Use the $in operator to select documents where the value of a field equals any value in the specified array. Here's an example:

db.zips.find({ city: { $in: ["PHOENIX", "CHICAGO"] } })