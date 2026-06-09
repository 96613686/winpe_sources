# Microsoft::WRL::Module<1,MultipleUseOutOfProcModule>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x1400083f0`
- end: `0x14000840b`
- name: `?UnregisterCOMObject@?$Module@$00VMultipleUseOutOfProcModule@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `27`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1400083fb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1400083fb`

## pseudocode

```c
__int64 Microsoft::WRL::Module<1,MultipleUseOutOfProcModule>::UnregisterCOMObject()
{
  RoOriginateError(2147500033LL, 0);
  return 2147500033LL;
}

```

## disassembly

```asm
0x1400083f0  sub     rsp, 28h
0x1400083f4  xor     edx, edx
0x1400083f6  mov     ecx, 80004001h
0x1400083fb  call    cs:__imp_RoOriginateError
0x140008401  mov     eax, 80004001h
0x140008406  add     rsp, 28h
0x14000840a  retn
```
