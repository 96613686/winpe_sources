# CIEAdminBrokerObject::RunSetupCommand(ushort *,HWND__ *,ushort *,ushort *,ushort *,ushort *,ulong,ulong *)

- ea: `0x405d60`
- end: `0x405d9b`
- name: `?RunSetupCommand@CIEAdminBrokerObject@@UAGJPAGPAUHWND__@@0000KPAK@Z`
- size: `59`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, HWND, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x403d84`
- `0x405d60`

## pseudocode

```c

```

## disassembly

```asm
0x405d60  mov     edi, edi
0x405d62  push    ebp; unsigned int
0x405d63  mov     ebp, esp
0x405d65  mov     eax, [ebp+this]
0x405d68  mov     ecx, 80004005h
0x405d6d  cmp     dword ptr [eax+8], 0
0x405d71  jz      short loc_405D95
0x405d73  push    [ebp+lpTargetHandle]; lpTargetHandle
0x405d76  mov     edx, [ebp+arg_4]
0x405d79  push    [ebp+arg_1C]; unsigned __int16 *
0x405d7c  mov     ecx, [eax+8]
0x405d7f  push    [ebp+arg_18]; unsigned __int16 *
0x405d82  push    [ebp+arg_14]; unsigned __int16 *
0x405d85  push    [ebp+arg_10]; HWND
0x405d88  push    [ebp+arg_C]; unsigned __int16 *
0x405d8b  push    [ebp+arg_8]; this
0x405d8e  call    ?RunSetupCommand@CActiveXInstallBroker@@QAGJPAGPAUHWND__@@0000KPAPAX@Z; CActiveXInstallBroker::RunSetupCommand(ushort *,HWND__ *,ushort *,ushort *,ushort *,ushort *,ulong,void * *)
0x405d93  mov     ecx, eax
0x405d95  mov     eax, ecx
0x405d97  pop     ebp
0x405d98  retn    24h ; '$'
```
