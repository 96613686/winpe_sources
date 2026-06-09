# FAX_SetConfigWizardUsed

- ea: `0x14001f870`
- end: `0x14001fa54`
- name: `FAX_SetConfigWizardUsed`
- size: `484`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x14001f870`
- `0x140047d20`
- `0x140075070`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14001fa07`
- `ADVAPI32!RegCloseKey` at `0x14001fa07`
- `ADVAPI32!RegOpenKeyExW` at `0x14001f970`
- `ADVAPI32!RegOpenKeyExW` at `0x14001f970`
- `KERNEL32!GetLastError` at `0x14001f9c8`
- `KERNEL32!GetLastError` at `0x14001f9c8`

## pseudocode

```c
__int64 __fastcall FAX_SetConfigWizardUsed(__int64 a1, unsigned int a2)
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
0x14001f870  mov     [rsp+arg_0], rbx
0x14001f875  push    rbp
0x14001f876  push    rdi
0x14001f877  push    r15
0x14001f879  sub     rsp, 30h
0x14001f87d  mov     edi, edx
0x14001f87f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f886  lea     rbp, WPP_GLOBAL_Control
0x14001f88d  lea     r15, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001f894  cmp     rcx, rbp
0x14001f897  jz      short loc_14001F8B6
0x14001f899  test    byte ptr [rcx+1Ch], 4
0x14001f89d  jz      short loc_14001F8B6
0x14001f89f  cmp     byte ptr [rcx+19h], 5
0x14001f8a3  jb      short loc_14001F8B6
0x14001f8a5  mov     rcx, [rcx+10h]
0x14001f8a9  mov     edx, 243h
0x14001f8ae  mov     r8, r15
0x14001f8b1  call    WPP_SF_
0x14001f8b6  mov     r9d, 1; int
0x14001f8bc  mov     [rsp+48h+hKey], 0
0x14001f8c5  xor     r8d, r8d; unsigned int *
0x14001f8c8  mov     [rsp+48h+arg_10], 0
0x14001f8d0  lea     rdx, [rsp+48h+arg_10]; int *
0x14001f8d5  lea     ecx, [r9+3Fh]; unsigned int
0x14001f8d9  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14001f8de  mov     ebx, eax
0x14001f8e0  test    eax, eax
0x14001f8e2  jz      short loc_14001F915
0x14001f8e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f8eb  cmp     rcx, rbp
0x14001f8ee  jz      loc_14001FA43
0x14001f8f4  test    byte ptr [rcx+1Ch], 4
0x14001f8f8  jz      loc_14001FA43
0x14001f8fe  cmp     byte ptr [rcx+19h], 2
0x14001f902  jb      loc_14001FA43
0x14001f908  mov     edx, 244h
0x14001f90d  mov     r9d, ebx
0x14001f910  jmp     loc_14001FA37
0x14001f915  cmp     [rsp+48h+arg_10], 0
0x14001f91a  jnz     short loc_14001F94F
0x14001f91c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f923  cmp     rcx, rbp
0x14001f926  jz      short loc_14001F945
0x14001f928  test    byte ptr [rcx+1Ch], 4
0x14001f92c  jz      short loc_14001F945
0x14001f92e  cmp     byte ptr [rcx+19h], 2
0x14001f932  jb      short loc_14001F945
0x14001f934  mov     rcx, [rcx+10h]
0x14001f938  mov     edx, 245h
0x14001f93d  mov     r8, r15
0x14001f940  call    WPP_SF_
0x14001f945  mov     eax, 5
0x14001f94a  jmp     loc_14001FA45
0x14001f94f  lea     rax, [rsp+48h+hKey]
0x14001f954  mov     r9d, 20006h; samDesired
0x14001f95a  xor     r8d, r8d; ulOptions
0x14001f95d  mov     [rsp+48h+phkResult], rax; phkResult
0x14001f962  lea     rdx, SubKey; "Software\\Microsoft\\Fax\\Client"
0x14001f969  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001f970  call    cs:__imp_RegOpenKeyExW
0x14001f977  nop     dword ptr [rax+rax+00h]
0x14001f97c  mov     ebx, eax
0x14001f97e  test    eax, eax
0x14001f980  jz      short loc_14001F9B0
0x14001f982  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f989  cmp     rcx, rbp
0x14001f98c  jz      loc_14001FA43
0x14001f992  test    byte ptr [rcx+1Ch], 4
0x14001f996  jz      loc_14001FA43
0x14001f99c  cmp     byte ptr [rcx+19h], 2
0x14001f9a0  jb      loc_14001FA43
0x14001f9a6  mov     edx, 246h
0x14001f9ab  jmp     loc_14001F90D
0x14001f9b0  mov     rcx, [rsp+48h+hKey]
0x14001f9b5  lea     rdx, aCfgwzdrdevice; "CfgWzdrDevice"
0x14001f9bc  mov     r8d, edi
0x14001f9bf  call    SetRegistryDword
0x14001f9c4  test    eax, eax
0x14001f9c6  jnz     short loc_14001FA02
0x14001f9c8  call    cs:__imp_GetLastError
0x14001f9cf  nop     dword ptr [rax+rax+00h]
0x14001f9d4  mov     ebx, eax
0x14001f9d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f9dd  cmp     rcx, rbp
0x14001f9e0  jz      short loc_14001FA02
0x14001f9e2  test    byte ptr [rcx+1Ch], 4
0x14001f9e6  jz      short loc_14001FA02
0x14001f9e8  cmp     byte ptr [rcx+19h], 2
0x14001f9ec  jb      short loc_14001FA02
0x14001f9ee  mov     rcx, [rcx+10h]
0x14001f9f2  mov     edx, 247h
0x14001f9f7  mov     r9d, eax
0x14001f9fa  mov     r8, r15
0x14001f9fd  call    WPP_SF_d
0x14001fa02  mov     rcx, [rsp+48h+hKey]; hKey
0x14001fa07  call    cs:__imp_RegCloseKey
0x14001fa0e  nop     dword ptr [rax+rax+00h]
0x14001fa13  test    eax, eax
0x14001fa15  jz      short loc_14001FA43
0x14001fa17  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fa1e  cmp     rcx, rbp
0x14001fa21  jz      short loc_14001FA43
0x14001fa23  test    byte ptr [rcx+1Ch], 4
0x14001fa27  jz      short loc_14001FA43
0x14001fa29  cmp     byte ptr [rcx+19h], 2
0x14001fa2d  jb      short loc_14001FA43
0x14001fa2f  mov     edx, 248h
0x14001fa34  mov     r9d, eax
0x14001fa37  mov     rcx, [rcx+10h]
0x14001fa3b  mov     r8, r15
0x14001fa3e  call    WPP_SF_d
0x14001fa43  mov     eax, ebx
0x14001fa45  mov     rbx, [rsp+48h+arg_0]
0x14001fa4a  add     rsp, 30h
0x14001fa4e  pop     r15
0x14001fa50  pop     rdi
0x14001fa51  pop     rbp
0x14001fa52  retn
```
