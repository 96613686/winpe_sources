# Microsoft::WRL::Module<1,MultipleUseOutOfProcModule>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x14000bec0`
- end: `0x14000bedb`
- name: `?UnregisterCOMObject@?$Module@$00VMultipleUseOutOfProcModule@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x14000becb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x14000becb`

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
0x14000bec0  sub     rsp, 28h
0x14000bec4  xor     edx, edx
0x14000bec6  mov     ecx, 80004001h
0x14000becb  call    cs:__imp_RoOriginateError
0x14000bed1  mov     eax, 80004001h
0x14000bed6  add     rsp, 28h
0x14000beda  retn
```
