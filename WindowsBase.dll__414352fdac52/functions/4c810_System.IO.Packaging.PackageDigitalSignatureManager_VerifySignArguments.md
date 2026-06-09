# System.IO.Packaging.PackageDigitalSignatureManager::VerifySignArguments

- ea: `0x4c810`
- end: `0x4c92d`
- name: `System.IO.Packaging.PackageDigitalSignatureManager::VerifySignArguments`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x4c170`

## callees

- `0x25f90`
- `0x2c100`
- `0x2c130`
- `0x4c810`
- `0x4c930`
- `0x5b950`

## string_xrefs

- `0x4c90b`: `NotAValidXmlIdString`

## pseudocode

```c

```

## disassembly

```asm
0x4c810  ldarg.2
0x4c811  brtrue.s loc_4C81E
0x4c813  ldstr    aCertificate// "certificate"
0x4c818  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4c81d  throw
0x4c81e  ldarg.0
0x4c81f  ldarg.1
0x4c820  call     instance bool System.IO.Packaging.PackageDigitalSignatureManager::EnumeratorEmptyCheck(class [mscorlib]System.Collections.IEnumerable enumerable)
0x4c825  brfalse.s loc_4C854
0x4c827  ldarg.0
0x4c828  ldarg.3
0x4c829  call     instance bool System.IO.Packaging.PackageDigitalSignatureManager::EnumeratorEmptyCheck(class [mscorlib]System.Collections.IEnumerable enumerable)
0x4c82e  brfalse.s loc_4C854
0x4c830  ldarg.0
0x4c831  ldarg.s  5
0x4c833  call     instance bool System.IO.Packaging.PackageDigitalSignatureManager::EnumeratorEmptyCheck(class [mscorlib]System.Collections.IEnumerable enumerable)
0x4c838  brfalse.s loc_4C854
0x4c83a  ldarg.0
0x4c83b  ldarg.s  6
0x4c83d  call     instance bool System.IO.Packaging.PackageDigitalSignatureManager::EnumeratorEmptyCheck(class [mscorlib]System.Collections.IEnumerable enumerable)
0x4c842  brfalse.s loc_4C854
0x4c844  ldstr    aNothingtosign// "NothingToSign"
0x4c849  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4c84e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4c853  throw
0x4c854  ldarg.s  5
0x4c856  brfalse  loc_4C8EE
0x4c85b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x4c860  stloc.0
0x4c861  ldarg.s  5
0x4c863  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Security]System.Security.Cryptography.Xml.DataObject>::GetEnumerator()
0x4c868  stloc.1
0x4c869  br.s     loc_4C8DA
0x4c86b  ldloc.1
0x4c86c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Security]System.Security.Cryptography.Xml.DataObject>::get_Current()
0x4c871  stloc.2
0x4c872  ldloc.2
0x4c873  callvirt instance string [System.Security]System.Security.Cryptography.Xml.DataObject::get_Id()
0x4c878  ldc.i4.s 0x11
0x4c87a  call     string MS.Internal.IO.Packaging.XTable::Get(valuetype ID i)
0x4c87f  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x4c884  brtrue.s loc_4C89B
0x4c886  ldstr    aSignaturepacka// "SignaturePackageObjectTagMustBeUnique"
0x4c88b  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4c890  ldstr    aSignatureobjec_0// "signatureObjects"
0x4c895  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x4c89a  throw
0x4c89b  ldloc.0
0x4c89c  ldloc.2
0x4c89d  callvirt instance string [System.Security]System.Security.Cryptography.Xml.DataObject::get_Id()
0x4c8a2  newobj   instance void StringMatchPredicate::.ctor(string id)
0x4c8a7  ldftn    instance bool StringMatchPredicate::Match(string id)
0x4c8ad  newobj   instance void class [mscorlib]System.Predicate`1<string>::.ctor(object, native int)
0x4c8b2  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Exists(class [mscorlib]System.Predicate`1<var<u1>>)
0x4c8b7  brfalse.s loc_4C8CE
0x4c8b9  ldstr    aSignatureobjec// "SignatureObjectIdMustBeUnique"
0x4c8be  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4c8c3  ldstr    aSignatureobjec_0// "signatureObjects"
0x4c8c8  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x4c8cd  throw
0x4c8ce  ldloc.0
0x4c8cf  ldloc.2
0x4c8d0  callvirt instance string [System.Security]System.Security.Cryptography.Xml.DataObject::get_Id()
0x4c8d5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4c8da  ldloc.1
0x4c8db  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4c8e0  brtrue.s loc_4C86B
0x4c8e2  leave.s  loc_4C8EE
0x4c8e4  ldloc.1
0x4c8e5  brfalse.s loc_4C8ED
0x4c8e7  ldloc.1
0x4c8e8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c8ed  endfinally
0x4c8ee  ldarg.s  4
0x4c8f0  brfalse.s loc_4C92C
0x4c8f2  ldarg.s  4
0x4c8f4  ldsfld   string [mscorlib]System.String::Empty
0x4c8f9  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x4c8fe  brfalse.s loc_4C92C
0x4c900  ldarg.s  4
0x4c902  call     string [System.Xml]System.Xml.XmlConvert::VerifyNCName(string)
0x4c907  pop
0x4c908  leave.s  loc_4C92C
0x4c90a  stloc.3
0x4c90b  ldstr    aNotavalidxmlid// "NotAValidXmlIdString"
0x4c910  ldc.i4.1
0x4c911  newarr   [mscorlib]System.Object
0x4c916  dup
0x4c917  ldc.i4.0
0x4c918  ldarg.s  4
0x4c91a  stelem.ref
0x4c91b  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x4c920  ldstr    aSignatureid// "signatureId"
0x4c925  ldloc.3
0x4c926  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string, class [mscorlib]System.Exception)
0x4c92b  throw
0x4c92c  ret
```
