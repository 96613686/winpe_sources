# MS.Internal.Ink.InkSerializedFormat.ExtendedPropertySerializer::DecodeAsISF

- ea: `0x13cde0`
- end: `0x13cf73`
- name: `MS.Internal.Ink.InkSerializedFormat.ExtendedPropertySerializer::DecodeAsISF`
- size: `403`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x13da80`
- `0x13ea40`
- `0x142bf0`

## callees

- `0x13c7e0`
- `0x13cde0`
- `0x13cf80`
- `0x13e5a0`
- `0x13e5f0`
- `0x140f50`
- `0x142780`
- `0x146e40`

## string_xrefs

- `0x13cec9`: `Read different size from stream then expected`
- `0x13cf2c`: `Read different size from stream then expected`

## pseudocode

```c

```

## disassembly

```asm
0x13cde0  ldc.i4.0
0x13cde1  stloc.1
0x13cde2  ldarg.1
0x13cde3  stloc.0
0x13cde4  ldarg.1
0x13cde5  brtrue.s loc_13CDF7
0x13cde7  ldstr    aEmptydatatoloa// "EmptyDataToLoad"
0x13cdec  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x13cdf1  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x13cdf6  throw
0x13cdf7  ldarg.3
0x13cdf8  brtrue.s loc_13CE3A
0x13cdfa  ldarg.0
0x13cdfb  ldloca.s 0xB
0x13cdfd  call     unsigned int32 MS.Internal.Ink.InkSerializedFormat.SerializationHelper::Decode(class [mscorlib]System.IO.Stream strm, [out] unsigned int32& dw)
0x13ce02  stloc.s  4
0x13ce04  ldloc.s  0xB
0x13ce06  starg.s  3
0x13ce08  ldloc.s  4
0x13ce0a  ldloc.0
0x13ce0b  ble.un.s loc_13CE22
0x13ce0d  ldstr    aInvalidsizespe// "InvalidSizeSpecified"
0x13ce12  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x13ce17  ldstr    aCbsize// "cbSize"
0x13ce1c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x13ce21  throw
0x13ce22  ldloc.0
0x13ce23  ldloc.s  4
0x13ce25  sub
0x13ce26  stloc.0
0x13ce27  ldloc.1
0x13ce28  ldloc.s  4
0x13ce2a  add
0x13ce2b  stloc.1
0x13ce2c  ldarg.s  4
0x13ce2e  ldarg.2
0x13ce2f  ldarg.3
0x13ce30  callvirt instance valuetype [mscorlib]System.Guid MS.Internal.Ink.InkSerializedFormat.GuidList::FindGuid(valuetype KnownTagIndex tag)
0x13ce35  stobj    [mscorlib]System.Guid
0x13ce3a  ldarg.s  4
0x13ce3c  ldobj    [mscorlib]System.Guid
0x13ce41  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x13ce46  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x13ce4b  brfalse.s loc_13CE62
0x13ce4d  ldstr    aCustomAttribut// "Custom Attribute tag embedded in ISF st"...
0x13ce52  call     string MS.Internal.Ink.InkSerializedFormat.StrokeCollectionSerializer::ISFDebugMessage(string debugMessage)
0x13ce57  ldstr    aTag// "tag"
0x13ce5c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x13ce61  throw
0x13ce62  ldarg.s  4
0x13ce64  ldobj    [mscorlib]System.Guid
0x13ce69  call     unsigned int32 MS.Internal.Ink.InkSerializedFormat.GuidList::GetDataSizeIfKnownGuid(valuetype [mscorlib]System.Guid guid)
0x13ce6e  stloc.2
0x13ce6f  ldloc.2
0x13ce70  ldloc.0
0x13ce71  ble.un.s loc_13CE88
0x13ce73  ldstr    aInvalidsizespe// "InvalidSizeSpecified"
0x13ce78  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x13ce7d  ldstr    aCbsize// "cbSize"
0x13ce82  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x13ce87  throw
0x13ce88  ldloc.2
0x13ce89  brtrue   loc_13CF13
0x13ce8e  ldarg.0
0x13ce8f  ldloca.s 2
0x13ce91  call     unsigned int32 MS.Internal.Ink.InkSerializedFormat.SerializationHelper::Decode(class [mscorlib]System.IO.Stream strm, [out] unsigned int32& dw)
0x13ce96  stloc.s  4
0x13ce98  ldloc.2
0x13ce99  ldc.i4.1
0x13ce9a  add
0x13ce9b  stloc.3
0x13ce9c  ldloc.1
0x13ce9d  ldloc.s  4
0x13ce9f  add
0x13cea0  stloc.1
0x13cea1  ldloc.0
0x13cea2  ldloc.s  4
0x13cea4  sub
0x13cea5  stloc.0
0x13cea6  ldloc.3
0x13cea7  ldloc.0
0x13cea8  ble.un.s loc_13CEB0
0x13ceaa  newobj   instance void [mscorlib]System.ArgumentException::.ctor()
0x13ceaf  throw
0x13ceb0  ldloc.3
0x13ceb1  newarr   [mscorlib]System.Byte
0x13ceb6  stloc.s  8
0x13ceb8  ldarg.0
0x13ceb9  ldloc.s  8
0x13cebb  ldc.i4.0
0x13cebc  ldloc.3
0x13cebd  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x13cec2  stloc.s  0xA
0x13cec4  ldloc.3
0x13cec5  ldloc.s  0xA
0x13cec7  beq.s    loc_13CEDE
0x13cec9  ldstr    aReadDifferentS// "Read different size from stream then ex"...
0x13cece  call     string MS.Internal.Ink.InkSerializedFormat.StrokeCollectionSerializer::ISFDebugMessage(string debugMessage)
0x13ced3  ldstr    aCbsize// "cbSize"
0x13ced8  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x13cedd  throw
0x13cede  ldloc.1
0x13cedf  ldloc.3
0x13cee0  add
0x13cee1  stloc.1
0x13cee2  ldloc.0
0x13cee3  ldloc.3
0x13cee4  sub
0x13cee5  stloc.0
0x13cee6  ldloc.s  8
0x13cee8  call     unsigned int8[] MS.Internal.Ink.InkSerializedFormat.Compressor::DecompressPropertyData(unsigned int8[] input)
0x13ceed  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x13cef2  stloc.s  6
0x13cef4  ldarg.s  5
0x13cef6  ldarg.s  4
0x13cef8  ldobj    [mscorlib]System.Guid
0x13cefd  ldloc.s  6
0x13ceff  call     object MS.Internal.Ink.InkSerializedFormat.ExtendedPropertySerializer::DecodeAttribute(valuetype [mscorlib]System.Guid guid, class [mscorlib]System.IO.Stream stream)
0x13cf04  stind.ref
0x13cf05  leave.s  loc_13CF71
0x13cf07  ldloc.s  6
0x13cf09  brfalse.s loc_13CF12
0x13cf0b  ldloc.s  6
0x13cf0d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13cf12  endfinally
0x13cf13  ldloc.2
0x13cf14  newarr   [mscorlib]System.Byte
0x13cf19  stloc.s  7
0x13cf1b  ldarg.0
0x13cf1c  ldloc.s  7
0x13cf1e  ldc.i4.0
0x13cf1f  ldloc.2
0x13cf20  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x13cf25  stloc.s  9
0x13cf27  ldloc.2
0x13cf28  ldloc.s  9
0x13cf2a  beq.s    loc_13CF41
0x13cf2c  ldstr    aReadDifferentS// "Read different size from stream then ex"...
0x13cf31  call     string MS.Internal.Ink.InkSerializedFormat.StrokeCollectionSerializer::ISFDebugMessage(string debugMessage)
0x13cf36  ldstr    aCbsize// "cbSize"
0x13cf3b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x13cf40  throw
0x13cf41  ldloc.s  7
0x13cf43  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x13cf48  stloc.s  5
0x13cf4a  ldarg.s  5
0x13cf4c  ldarg.s  4
0x13cf4e  ldobj    [mscorlib]System.Guid
0x13cf53  ldloc.s  5
0x13cf55  call     object MS.Internal.Ink.InkSerializedFormat.ExtendedPropertySerializer::DecodeAttribute(valuetype [mscorlib]System.Guid guid, class [mscorlib]System.IO.Stream stream)
0x13cf5a  stind.ref
0x13cf5b  leave.s  loc_13CF69
0x13cf5d  ldloc.s  5
0x13cf5f  brfalse.s loc_13CF68
0x13cf61  ldloc.s  5
0x13cf63  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13cf68  endfinally
0x13cf69  ldloc.0
0x13cf6a  ldloc.2
0x13cf6b  sub
0x13cf6c  stloc.0
0x13cf6d  ldloc.1
0x13cf6e  ldloc.2
0x13cf6f  add
0x13cf70  stloc.1
0x13cf71  ldloc.1
0x13cf72  ret
```
