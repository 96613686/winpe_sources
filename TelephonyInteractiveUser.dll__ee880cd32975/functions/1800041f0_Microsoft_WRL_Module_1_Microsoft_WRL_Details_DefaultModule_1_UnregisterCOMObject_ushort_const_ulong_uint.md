# Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x1800041f0`
- end: `0x18000420b`
- name: `?UnregisterCOMObject@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `27`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000ba80`
- `0x18000baa0`
- `0x18000bab0`
- `0x18000bac0`
- `0x18000bad0`
- `0x18000baf0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800041fb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800041fb`

## pseudocode

```c
__int64 Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::UnregisterCOMObject()
{
  RoOriginateError(2147500033LL);
  return 2147500033LL;
}

```

## disassembly

```asm
0x1800041f0  sub     rsp, 28h
0x1800041f4  xor     edx, edx
0x1800041f6  mov     ecx, 80004001h
0x1800041fb  call    cs:__imp_RoOriginateError
0x180004201  mov     eax, 80004001h
0x180004206  add     rsp, 28h
0x18000420a  retn
```
