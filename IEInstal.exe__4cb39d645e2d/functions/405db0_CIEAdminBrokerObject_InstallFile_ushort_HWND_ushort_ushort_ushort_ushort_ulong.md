# CIEAdminBrokerObject::InstallFile(ushort *,HWND__ *,ushort *,ushort *,ushort *,ushort *,ulong)

- ea: `0x405db0`
- end: `0x405de6`
- name: `?InstallFile@CIEAdminBrokerObject@@UAGJPAGPAUHWND__@@0000K@Z`
- size: `54`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, HWND, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x403ffd`
- `0x405db0`

## pseudocode

```c

```

## disassembly

```asm
0x405db0  mov     edi, edi
0x405db2  push    ebp; unsigned __int16 *
0x405db3  mov     ebp, esp
0x405db5  mov     eax, [ebp+this]
0x405db8  mov     edx, 80004005h
0x405dbd  mov     ecx, [eax+8]
0x405dc0  test    ecx, ecx
0x405dc2  jz      short loc_405DE0
0x405dc4  push    [ebp+arg_1C]; unsigned __int16 *
0x405dc7  mov     edx, [ebp+arg_4]
0x405dca  push    [ebp+arg_18]; unsigned __int16 *
0x405dcd  push    [ebp+arg_14]; unsigned __int16 *
0x405dd0  push    [ebp+arg_10]; HWND
0x405dd3  push    [ebp+arg_C]; unsigned __int16 *
0x405dd6  push    [ebp+arg_8]; this
0x405dd9  call    ?InstallFile@CActiveXInstallBroker@@QAGJPAGPAUHWND__@@0000K@Z; CActiveXInstallBroker::InstallFile(ushort *,HWND__ *,ushort *,ushort *,ushort *,ushort *,ulong)
0x405dde  mov     edx, eax
0x405de0  mov     eax, edx
0x405de2  pop     ebp
0x405de3  retn    20h ; ' '
```
