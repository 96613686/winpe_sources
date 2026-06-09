# NativeZLibDLLStub::CreateDelegate

- ea: `0x5c710`
- end: `0x5c750`
- name: `NativeZLibDLLStub::CreateDelegate`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x5bc60`
- `0x5c710`

## string_xrefs

- `0x5c729`: `clrcompression.dll!`

## pseudocode

```c

```

## disassembly

```asm
0x5c710  ldsfld   class SafeLibraryHandle ZLibStreamHandle::zlibLibraryHandle
0x5c715  ldarg.0
0x5c716  call     native int NativeMethods::GetProcAddress(class SafeLibraryHandle moduleHandle, string procName)
0x5c71b  stloc.0
0x5c71c  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5c721  ldloc.0
0x5c722  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x5c727  brfalse.s loc_5C73A
0x5c729  ldstr    aClrcompression_0// "clrcompression.dll!"
0x5c72e  ldarg.0
0x5c72f  call     string [mscorlib]System.String::Concat(string, string)
0x5c734  newobj   instance void [mscorlib]System.EntryPointNotFoundException::.ctor(string)
0x5c739  throw
0x5c73a  ldloc.0
0x5c73b  ldtoken  mvar<u1>
0x5c740  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5c745  call     class [mscorlib]System.Delegate [mscorlib]System.Runtime.InteropServices.Marshal::GetDelegateForFunctionPointer(native int, class [mscorlib]System.Type)
0x5c74a  unbox.any mvar<u1>
0x5c74f  ret
```
