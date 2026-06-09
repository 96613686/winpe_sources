# Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x180009710`
- end: `0x18000972b`
- name: `?UnregisterCOMObject@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000971b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000971b`

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
0x180009710  sub     rsp, 28h
0x180009714  xor     edx, edx
0x180009716  mov     ecx, 80004001h
0x18000971b  call    cs:__imp_RoOriginateError
0x180009721  mov     eax, 80004001h
0x180009726  add     rsp, 28h
0x18000972a  retn
```
