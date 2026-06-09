# FAX_SetConfigWizardUsed

- ea: `0x14001eb10`
- end: `0x14001ece1`
- name: `FAX_SetConfigWizardUsed`
- size: `465`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x14001eb10`
- `0x1400452ac`
- `0x1400709fc`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14001ec9b`
- `ADVAPI32!RegCloseKey` at `0x14001ec9b`
- `ADVAPI32!RegOpenKeyExW` at `0x14001ec10`
- `ADVAPI32!RegOpenKeyExW` at `0x14001ec10`
- `KERNEL32!GetLastError` at `0x14001ec62`
- `KERNEL32!GetLastError` at `0x14001ec62`

## pseudocode

```c
__int64 __fastcall FAX_SetConfigWizardUsed(__int64 a1, int a2)
{
  unsigned int v3; // ebx
  CMapDeviceId *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  DWORD LastError; // eax
  unsigned int v9; // eax
  int v10; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 579, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  hKey = 0;
  v10 = 0;
  v3 = FaxSvcAccessCheck(0x40u, &v10, 0, 1);
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v3;
    }
    v5 = 580;
    goto LABEL_10;
  }
  if ( v10 )
  {
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Client", 0, 0x20006u, &hKey);
    if ( !v3 )
    {
      if ( !(unsigned int)SetRegistryDword(hKey, L"CfgWzdrDevice", a2) )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            583,
            &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
            LastError);
        }
      }
      v9 = RegCloseKey(hKey);
      if ( !v9 )
        return v3;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v3;
      }
      v5 = 584;
      v6 = v9;
      goto LABEL_32;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v3;
    }
    v5 = 582;
LABEL_10:
    v6 = v3;
LABEL_32:
    WPP_SF_d(*((_QWORD *)v4 + 2), v5, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v6);
    return v3;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 581, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  return 5;
}

```

## disassembly

```asm
0x14001eb10  mov     [rsp+arg_0], rbx
0x14001eb15  push    rbp
0x14001eb16  push    rdi
0x14001eb17  push    r15
0x14001eb19  sub     rsp, 30h
0x14001eb1d  mov     edi, edx
0x14001eb1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eb26  lea     rbp, WPP_GLOBAL_Control
0x14001eb2d  lea     r15, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001eb34  cmp     rcx, rbp
0x14001eb37  jz      short loc_14001EB56
0x14001eb39  test    byte ptr [rcx+1Ch], 4
0x14001eb3d  jz      short loc_14001EB56
0x14001eb3f  cmp     byte ptr [rcx+19h], 5
0x14001eb43  jb      short loc_14001EB56
0x14001eb45  mov     rcx, [rcx+10h]
0x14001eb49  mov     edx, 243h
0x14001eb4e  mov     r8, r15
0x14001eb51  call    WPP_SF_
0x14001eb56  mov     r9d, 1; int
0x14001eb5c  mov     [rsp+48h+hKey], 0
0x14001eb65  xor     r8d, r8d; unsigned int *
0x14001eb68  mov     [rsp+48h+arg_10], 0
0x14001eb70  lea     rdx, [rsp+48h+arg_10]; int *
0x14001eb75  lea     ecx, [r9+3Fh]; unsigned int
0x14001eb79  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14001eb7e  mov     ebx, eax
0x14001eb80  test    eax, eax
0x14001eb82  jz      short loc_14001EBB5
0x14001eb84  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eb8b  cmp     rcx, rbp
0x14001eb8e  jz      loc_14001ECD1
0x14001eb94  test    byte ptr [rcx+1Ch], 4
0x14001eb98  jz      loc_14001ECD1
0x14001eb9e  cmp     byte ptr [rcx+19h], 2
0x14001eba2  jb      loc_14001ECD1
0x14001eba8  mov     edx, 244h
0x14001ebad  mov     r9d, ebx
0x14001ebb0  jmp     loc_14001ECC5
0x14001ebb5  cmp     [rsp+48h+arg_10], 0
0x14001ebba  jnz     short loc_14001EBEF
0x14001ebbc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ebc3  cmp     rcx, rbp
0x14001ebc6  jz      short loc_14001EBE5
0x14001ebc8  test    byte ptr [rcx+1Ch], 4
0x14001ebcc  jz      short loc_14001EBE5
0x14001ebce  cmp     byte ptr [rcx+19h], 2
0x14001ebd2  jb      short loc_14001EBE5
0x14001ebd4  mov     rcx, [rcx+10h]
0x14001ebd8  mov     edx, 245h
0x14001ebdd  mov     r8, r15
0x14001ebe0  call    WPP_SF_
0x14001ebe5  mov     eax, 5
0x14001ebea  jmp     loc_14001ECD3
0x14001ebef  lea     rax, [rsp+48h+hKey]
0x14001ebf4  mov     r9d, 20006h; samDesired
0x14001ebfa  xor     r8d, r8d; ulOptions
0x14001ebfd  mov     [rsp+48h+phkResult], rax; phkResult
0x14001ec02  lea     rdx, SubKey; "Software\\Microsoft\\Fax\\Client"
0x14001ec09  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001ec10  call    cs:__imp_RegOpenKeyExW
0x14001ec16  mov     ebx, eax
0x14001ec18  test    eax, eax
0x14001ec1a  jz      short loc_14001EC4A
0x14001ec1c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ec23  cmp     rcx, rbp
0x14001ec26  jz      loc_14001ECD1
0x14001ec2c  test    byte ptr [rcx+1Ch], 4
0x14001ec30  jz      loc_14001ECD1
0x14001ec36  cmp     byte ptr [rcx+19h], 2
0x14001ec3a  jb      loc_14001ECD1
0x14001ec40  mov     edx, 246h
0x14001ec45  jmp     loc_14001EBAD
0x14001ec4a  mov     rcx, [rsp+48h+hKey]
0x14001ec4f  lea     rdx, aCfgwzdrdevice; "CfgWzdrDevice"
0x14001ec56  mov     r8d, edi
0x14001ec59  call    SetRegistryDword
0x14001ec5e  test    eax, eax
0x14001ec60  jnz     short loc_14001EC96
0x14001ec62  call    cs:__imp_GetLastError
0x14001ec68  mov     ebx, eax
0x14001ec6a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ec71  cmp     rcx, rbp
0x14001ec74  jz      short loc_14001EC96
0x14001ec76  test    byte ptr [rcx+1Ch], 4
0x14001ec7a  jz      short loc_14001EC96
0x14001ec7c  cmp     byte ptr [rcx+19h], 2
0x14001ec80  jb      short loc_14001EC96
0x14001ec82  mov     rcx, [rcx+10h]
0x14001ec86  mov     edx, 247h
0x14001ec8b  mov     r9d, eax
0x14001ec8e  mov     r8, r15
0x14001ec91  call    WPP_SF_d
0x14001ec96  mov     rcx, [rsp+48h+hKey]; hKey
0x14001ec9b  call    cs:__imp_RegCloseKey
0x14001eca1  test    eax, eax
0x14001eca3  jz      short loc_14001ECD1
0x14001eca5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ecac  cmp     rcx, rbp
0x14001ecaf  jz      short loc_14001ECD1
0x14001ecb1  test    byte ptr [rcx+1Ch], 4
0x14001ecb5  jz      short loc_14001ECD1
0x14001ecb7  cmp     byte ptr [rcx+19h], 2
0x14001ecbb  jb      short loc_14001ECD1
0x14001ecbd  mov     edx, 248h
0x14001ecc2  mov     r9d, eax
0x14001ecc5  mov     rcx, [rcx+10h]
0x14001ecc9  mov     r8, r15
0x14001eccc  call    WPP_SF_d
0x14001ecd1  mov     eax, ebx
0x14001ecd3  mov     rbx, [rsp+48h+arg_0]
0x14001ecd8  add     rsp, 30h
0x14001ecdc  pop     r15
0x14001ecde  pop     rdi
0x14001ecdf  pop     rbp
0x14001ece0  retn
```
