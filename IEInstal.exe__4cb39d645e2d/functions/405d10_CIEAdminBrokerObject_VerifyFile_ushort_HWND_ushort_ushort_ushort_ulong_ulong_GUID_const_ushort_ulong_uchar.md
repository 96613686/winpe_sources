# CIEAdminBrokerObject::VerifyFile(ushort *,HWND__ *,ushort *,ushort *,ushort *,ulong,ulong,_GUID const &,ushort * *,ulong *,uchar * *)

- ea: `0x405d10`
- end: `0x405d54`
- name: `?VerifyFile@CIEAdminBrokerObject@@UAGJPAGPAUHWND__@@000KKABU_GUID@@PAPAGPAKPAPAE@Z`
- size: `68`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, HWND, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, const struct _GUID *, unsigned __int16 **, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x40373b`
- `0x405d10`

## pseudocode

```c

```

## disassembly

```asm
0x405d10  mov     edi, edi
0x405d12  push    ebp; unsigned int *
0x405d13  mov     ebp, esp
0x405d15  mov     eax, [ebp+this]
0x405d18  mov     ecx, 80004005h
0x405d1d  cmp     dword ptr [eax+8], 0
0x405d21  jz      short loc_405D4E
0x405d23  push    [ebp+arg_2C]; unsigned __int16 **
0x405d26  mov     edx, [ebp+arg_4]
0x405d29  push    [ebp+arg_28]; struct _GUID *
0x405d2c  mov     ecx, [eax+8]
0x405d2f  push    [ebp+arg_24]; unsigned int
0x405d32  push    [ebp+arg_20]; unsigned int
0x405d35  push    [ebp+arg_1C]; unsigned __int16 *
0x405d38  push    [ebp+arg_18]; unsigned __int16 *
0x405d3b  push    [ebp+arg_14]; unsigned __int16 *
0x405d3e  push    [ebp+arg_10]; HWND
0x405d41  push    [ebp+arg_C]; unsigned __int16 *
0x405d44  push    [ebp+arg_8]; this
0x405d47  call    ?VerifyFile@CActiveXInstallBroker@@QAGJPAGPAUHWND__@@000KKABU_GUID@@PAPAGPAKPAPAE@Z; CActiveXInstallBroker::VerifyFile(ushort *,HWND__ *,ushort *,ushort *,ushort *,ulong,ulong,_GUID const &,ushort * *,ulong *,uchar * *)
0x405d4c  mov     ecx, eax
0x405d4e  mov     eax, ecx
0x405d50  pop     ebp
0x405d51  retn    30h ; '0'
```
