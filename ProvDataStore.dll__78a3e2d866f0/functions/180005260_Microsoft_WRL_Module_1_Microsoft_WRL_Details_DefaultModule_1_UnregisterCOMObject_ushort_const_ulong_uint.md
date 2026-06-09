# Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x180005260`
- end: `0x18000527b`
- name: `?UnregisterCOMObject@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `27`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000526b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000526b`

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
0x180005260  sub     rsp, 28h
0x180005264  xor     edx, edx
0x180005266  mov     ecx, 80004001h
0x18000526b  call    cs:__imp_RoOriginateError
0x180005271  mov     eax, 80004001h
0x180005276  add     rsp, 28h
0x18000527a  retn
```
