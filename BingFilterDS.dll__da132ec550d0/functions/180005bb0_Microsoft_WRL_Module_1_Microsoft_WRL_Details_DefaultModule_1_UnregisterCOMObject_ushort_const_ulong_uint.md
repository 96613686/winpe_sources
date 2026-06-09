# Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x180005bb0`
- end: `0x180005bcb`
- name: `?UnregisterCOMObject@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `27`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005bbb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005bbb`

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
0x180005bb0  sub     rsp, 28h
0x180005bb4  xor     edx, edx
0x180005bb6  mov     ecx, 80004001h
0x180005bbb  call    cs:__imp_RoOriginateError
0x180005bc1  mov     eax, 80004001h
0x180005bc6  add     rsp, 28h
0x180005bca  retn
```
