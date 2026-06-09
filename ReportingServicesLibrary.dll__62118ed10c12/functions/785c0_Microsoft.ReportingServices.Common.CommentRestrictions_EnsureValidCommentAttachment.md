# Microsoft.ReportingServices.Common.CommentRestrictions::EnsureValidCommentAttachment

- ea: `0x785c0`
- end: `0x785fe`
- name: `Microsoft.ReportingServices.Common.CommentRestrictions::EnsureValidCommentAttachment`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3b980`
- `0x3be00`

## callees

- `0x785a0`
- `0x785c0`

## string_xrefs

- `0x785df`: `Invalid File format for comment attachment`
- `0x785f2`: `Invalid Mime Type for comment attachment`

## pseudocode

```c

```

## disassembly

```asm
0x785c0  ldarg.1
0x785c1  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x785c6  stloc.0
0x785c7  ldsfld   class [mscorlib]System.Collections.Generic.IReadOnlyCollection`1<string> Microsoft.ReportingServices.Common.CommentRestrictions::ValidFileFormats
0x785cc  ldloc.0
0x785cd  brtrue.s loc_785D2
0x785cf  ldnull
0x785d0  br.s     loc_785D8
0x785d2  ldloc.0
0x785d3  call     instance string [mscorlib]System.String::ToLowerInvariant()
0x785d8  call     T0x2B00004A
0x785dd  brtrue.s loc_785EA
0x785df  ldstr    aInvalidFileFor// "Invalid File format for comment attachm"...
0x785e4  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ResourceFileFormatNotAllowedException::.ctor(string)
0x785e9  throw
0x785ea  ldarg.0
0x785eb  call     bool Microsoft.ReportingServices.Common.CommentRestrictions::IsValidCommentAttachmentMimeType(string mimeType)
0x785f0  brtrue.s loc_785FD
0x785f2  ldstr    aInvalidMimeTyp// "Invalid Mime Type for comment attachmen"...
0x785f7  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ResourceMimeTypeNotAllowedException::.ctor(string)
0x785fc  throw
0x785fd  ret
```
