# Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x180009e20`
- end: `0x180009e3b`
- name: `?UnregisterCOMObject@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180009e2b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180009e2b`

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
0x180009e20  sub     rsp, 28h
0x180009e24  xor     edx, edx
0x180009e26  mov     ecx, 80004001h
0x180009e2b  call    cs:__imp_RoOriginateError
0x180009e31  mov     eax, 80004001h
0x180009e36  add     rsp, 28h
0x180009e3a  retn
```
