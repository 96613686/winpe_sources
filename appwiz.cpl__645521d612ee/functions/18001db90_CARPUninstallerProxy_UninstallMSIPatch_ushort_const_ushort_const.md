# CARPUninstallerProxy::UninstallMSIPatch(ushort const *,ushort const *)

- ea: `0x18001db90`
- end: `0x18001dbf0`
- name: `?UninstallMSIPatch@CARPUninstallerProxy@@UEAAJPEBG0@Z`
- size: `96`
- prototype: `__int64 __fastcall(CARPUninstallerProxy *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18001db90`

## import_xrefs

- `msi!__imp_MsiSetInternalUI` at `0x18001dbaa`
- `msi!__imp_MsiSetInternalUI` at `0x18001dbcb`
- `msi!__imp_MsiSetInternalUI` at `0x18001dbaa`
- `msi!__imp_MsiSetInternalUI` at `0x18001dbcb`
- `msi!__imp_MsiRemovePatchesW` at `0x18001dbbf`
- `msi!__imp_MsiRemovePatchesW` at `0x18001dbbf`

## pseudocode

```c
__int64 __fastcall CARPUninstallerProxy::UninstallMSIPatch(
        CARPUninstallerProxy *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  INSTALLUILEVEL v5; // ebx
  signed int v6; // edi

  v5 = MsiSetInternalUI(INSTALLUILEVEL_NONE, 0);
  v6 = MsiRemovePatchesW(a2, a3, INSTALLTYPE_SINGLE_INSTANCE, 0);
  MsiSetInternalUI(v5, 0);
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001db90  mov     [rsp+arg_0], rbx
0x18001db95  mov     [rsp+arg_8], rsi
0x18001db9a  push    rdi
0x18001db9b  sub     rsp, 20h
0x18001db9f  mov     rsi, rdx
0x18001dba2  mov     rdi, r8
0x18001dba5  xor     edx, edx; phWnd
0x18001dba7  lea     ecx, [rdx+2]; dwUILevel
0x18001dbaa  call    cs:__imp_MsiSetInternalUI
0x18001dbb0  xor     r9d, r9d; szPropertyList
0x18001dbb3  mov     rdx, rdi; szProductCode
0x18001dbb6  mov     rcx, rsi; szPatchList
0x18001dbb9  mov     ebx, eax
0x18001dbbb  lea     r8d, [r9+2]; eUninstallType
0x18001dbbf  call    cs:__imp_MsiRemovePatchesW
0x18001dbc5  xor     edx, edx; phWnd
0x18001dbc7  mov     ecx, ebx; dwUILevel
0x18001dbc9  mov     edi, eax
0x18001dbcb  call    cs:__imp_MsiSetInternalUI
0x18001dbd1  test    edi, edi
0x18001dbd3  jle     short loc_18001DBDE
0x18001dbd5  movzx   edi, di
0x18001dbd8  or      edi, 80070000h
0x18001dbde  mov     rbx, [rsp+28h+arg_0]
0x18001dbe3  mov     eax, edi
0x18001dbe5  mov     rsi, [rsp+28h+arg_8]
0x18001dbea  add     rsp, 20h
0x18001dbee  pop     rdi
0x18001dbef  retn
```
