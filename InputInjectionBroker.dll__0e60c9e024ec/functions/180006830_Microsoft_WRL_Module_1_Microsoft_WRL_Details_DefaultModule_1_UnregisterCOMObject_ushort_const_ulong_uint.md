# Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x180006830`
- end: `0x18000684b`
- name: `?UnregisterCOMObject@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `27`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000aa80`
- `0x18000aa90`
- `0x18000aaa0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000683b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000683b`

## pseudocode

```c
__int64 Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::UnregisterCOMObject()
{
  RoOriginateError(2147500033LL, 0);
  return 2147500033LL;
}

```

## disassembly

```asm
0x180006830  sub     rsp, 28h
0x180006834  xor     edx, edx
0x180006836  mov     ecx, 80004001h
0x18000683b  call    cs:__imp_RoOriginateError
0x180006841  mov     eax, 80004001h
0x180006846  add     rsp, 28h
0x18000684a  retn
```
