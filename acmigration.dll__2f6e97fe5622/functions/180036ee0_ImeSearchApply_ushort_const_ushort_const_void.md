# ImeSearchApply(ushort const *,ushort const *,void *)

- ea: `0x180036ee0`
- end: `0x180037263`
- name: `?ImeSearchApply@@YAJPEBG0PEAX@Z`
- size: `899`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001cf0`
- `0x180036ee0`
- `0x180037298`
- `0x180037328`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18003701a`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18003701a`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18003703f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18003703f`
- `KERNEL32!LocalFree` at `0x180037132`
- `KERNEL32!LocalFree` at `0x1800371bf`
- `KERNEL32!LocalFree` at `0x180037132`
- `KERNEL32!LocalFree` at `0x1800371bf`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180037059`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180037059`
- `ntdll!RtlNtStatusToDosError` at `0x180037159`
- `ntdll!RtlNtStatusToDosError` at `0x1800371e5`
- `ntdll!RtlNtStatusToDosError` at `0x180037219`
- `ntdll!RtlNtStatusToDosError` at `0x180037159`
- `ntdll!RtlNtStatusToDosError` at `0x1800371e5`
- `ntdll!RtlNtStatusToDosError` at `0x180037219`
- `ntdll!RtlAdjustPrivilege` at `0x18003714d`
- `ntdll!RtlAdjustPrivilege` at `0x1800371d9`
- `ntdll!RtlAdjustPrivilege` at `0x18003720d`
- `ntdll!RtlAdjustPrivilege` at `0x18003714d`
- `ntdll!RtlAdjustPrivilege` at `0x1800371d9`
- `ntdll!RtlAdjustPrivilege` at `0x18003720d`
- `ADVAPI32!RegQueryValueExW` at `0x180036fdf`
- `ADVAPI32!RegQueryValueExW` at `0x180036fdf`
- `ADVAPI32!RegCloseKey` at `0x1800370bb`
- `ADVAPI32!RegCloseKey` at `0x1800370bb`
- `ADVAPI32!RegSetValueExW` at `0x1800370a6`
- `ADVAPI32!RegSetValueExW` at `0x1800370a6`
- `ADVAPI32!RegOpenKeyExW` at `0x180036fa2`
- `ADVAPI32!RegOpenKeyExW` at `0x180036fa2`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180037112`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18003719f`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180037112`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18003719f`

## string_xrefs

- `0x180037034`: `\SYSTEM32\`
- `0x18003711e`: `SetNamedSecurityInfo DACL_SECURITY_INFORMATION Restore Err`
- `0x18003715f`: `RtlAdjustPrivilege SE_RESTORE_PRIVILEGE Err`
- `0x1800371ab`: `SetNamedSecurityInfo Restore  OWNER_SECURITY_INFORMATION Err`
- `0x1800371eb`: `RtlAdjustPrivilege Restore SE_RESTORE_PRIVILEGE  Err\n`
- `0x180037221`: `RtlAdjustPrivilege Restore Err`

## pseudocode

```c
__int64 __fastcall ImeSearchApply(const unsigned __int16 *a1, const unsigned __int16 *a2, void *a3)
{
  __int64 v3; // r13
  __int64 v4; // r14
  WCHAR *v5; // rcx
  DWORD i; // edi
  __int64 v7; // rbx
  wint_t v8; // ax
  __int64 v9; // rax
  HLOCAL v10; // rdi
  PSID v11; // rsi
  WCHAR *v12; // r15
  HLOCAL v13; // rbx
  DWORD v14; // eax
  NTSTATUS v15; // eax
  ULONG v16; // eax
  char *v17; // rcx
  ULONG v18; // edx
  char *v19; // rcx
  DWORD v20; // eax
  NTSTATUS v21; // eax
  NTSTATUS v22; // eax
  unsigned __int8 OldValue; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v25[7]; // [rsp+41h] [rbp-BFh] BYREF
  unsigned __int8 v26[8]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL ppSecurityDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  PSID psidOwner; // [rsp+68h] [rbp-98h] BYREF
  PACL pDacl; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Data[264]; // [rsp+80h] [rbp-80h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  Type = 0;
  cbData = 0;
  LogMsg("*Apply*", 0);
  v3 = 0;
  v4 = 0;
  do
  {
    v5 = *(WCHAR **)((char *)&ImeRegData + v4);
    v25[0] = 0;
    psidOwner = 0;
    pDacl = 0;
    ppSecurityDescriptor = 0;
    hMem = 0;
    MakeRegistryWritable(v5, &pDacl, &psidOwner, v25, &ppSecurityDescriptor, &hMem);
    if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, *(LPCWSTR *)((char *)&ImeRegData + v4 + 8), 0, 0x2001Bu, &hKey) )
    {
      cbData = 518;
      if ( !RegQueryValueExW(hKey, &psz, 0, &Type, (LPBYTE)Data, &cbData) && cbData < 0x104 && Type - 1 <= 1 )
      {
        for ( i = 0; i < cbData; Data[v7] = v8 )
        {
          v7 = i;
          v8 = towupper(Data[i++]);
        }
        if ( !wcsstr(Data, L"\\SYSTEM32\\") )
        {
          if ( ExpandEnvironmentStringsW(*(LPCWSTR *)((char *)&ImeRegData + v4 + 16), Data, 0x104u) - 1 > 0x102 )
          {
            v18 = 111;
            v19 = "ExpandEnvironmentStrings Failed";
LABEL_35:
            LogMsg(v19, v18);
            goto LABEL_36;
          }
          v9 = -1;
          do
            ++v9;
          while ( Data[v9] );
          RegSetValueExW(hKey, &psz, 0, Type, (const BYTE *)Data, 2 * v9 + 2);
        }
      }
    }
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKey);
      hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    }
    v10 = ppSecurityDescriptor;
    v11 = psidOwner;
    v12 = *(WCHAR **)((char *)&ImeRegData + v4);
    v26[0] = v25[0];
    OldValue = 0;
    if ( pDacl )
    {
      v13 = hMem;
      v14 = SetNamedSecurityInfoW(v12, SE_REGISTRY_KEY, 4u, 0, 0, pDacl, 0);
      if ( v14 )
        LogMsg("SetNamedSecurityInfo DACL_SECURITY_INFORMATION Restore Err", v14);
      if ( v13 )
        LocalFree(v13);
    }
    v15 = RtlAdjustPrivilege(0x12u, 1u, 0, &OldValue);
    if ( v15 )
    {
      v16 = RtlNtStatusToDosError(v15);
      v17 = "RtlAdjustPrivilege SE_RESTORE_PRIVILEGE Err";
LABEL_31:
      LogMsg(v17, v16);
      goto LABEL_32;
    }
    if ( v11 )
    {
      v20 = SetNamedSecurityInfoW(v12, SE_REGISTRY_KEY, 1u, v11, 0, 0, 0);
      if ( v20 )
        LogMsg("SetNamedSecurityInfo Restore  OWNER_SECURITY_INFORMATION Err", v20);
      if ( v10 )
        LocalFree(v10);
    }
    if ( !OldValue )
    {
      v21 = RtlAdjustPrivilege(0x12u, 0, 0, &OldValue);
      if ( v21 )
      {
        v16 = RtlNtStatusToDosError(v21);
        v17 = "RtlAdjustPrivilege Restore SE_RESTORE_PRIVILEGE  Err\n";
        goto LABEL_31;
      }
    }
LABEL_32:
    if ( !v26[0] )
    {
      v22 = RtlAdjustPrivilege(9u, 0, 0, v26);
      if ( v22 )
      {
        v18 = RtlNtStatusToDosError(v22);
        v19 = "RtlAdjustPrivilege Restore Err";
        goto LABEL_35;
      }
    }
LABEL_36:
    ++v3;
    v4 += 24;
  }
  while ( v3 != 2 );
  return 0;
}

```

## disassembly

```asm
0x180036ee0  push    rbp
0x180036ee2  push    rbx
0x180036ee3  push    rsi
0x180036ee4  push    rdi
0x180036ee5  push    r12
0x180036ee7  push    r13
0x180036ee9  push    r14
0x180036eeb  push    r15
0x180036eed  lea     rbp, [rsp-1A8h]
0x180036ef5  sub     rsp, 2A8h
0x180036efc  mov     rax, cs:__security_cookie
0x180036f03  xor     rax, rsp
0x180036f06  mov     [rbp+1E0h+var_50], rax
0x180036f0d  xor     r12d, r12d
0x180036f10  mov     [rsp+2E0h+hKey], 0FFFFFFFFFFFFFFFFh
0x180036f19  xor     edx, edx; unsigned int
0x180036f1b  mov     [rsp+2E0h+Type], r12d
0x180036f20  lea     rcx, aApply; "*Apply*"
0x180036f27  mov     [rsp+2E0h+cbData], r12d
0x180036f2c  call    ?LogMsg@@YAXPEADK@Z; LogMsg(char *,ulong)
0x180036f31  mov     r13d, r12d
0x180036f34  lea     rbx, ?ImeRegData@@3PAU_IMEREG@@A; _IMEREG near * ImeRegData
0x180036f3b  mov     r14d, r12d
0x180036f3e  mov     rcx, [r14+rbx]; pObjectName
0x180036f42  lea     rax, [rsp+2E0h+hMem]
0x180036f47  mov     [rsp+2E0h+lpcbData], rax; void **
0x180036f4c  lea     r9, [rsp+2E0h+var_29F]; unsigned __int8 *
0x180036f51  lea     rax, [rsp+2E0h+ppSecurityDescriptor]
0x180036f56  mov     [rsp+2E0h+var_29F], r12b
0x180036f5b  lea     r8, [rsp+2E0h+psidOwner]; ppsidOwner
0x180036f60  mov     [rsp+2E0h+phkResult], rax; ppSecurityDescriptor
0x180036f65  lea     rdx, [rsp+2E0h+pDacl]; ppDacl
0x180036f6a  mov     [rsp+2E0h+psidOwner], r12
0x180036f6f  mov     [rsp+2E0h+pDacl], r12
0x180036f74  mov     [rsp+2E0h+ppSecurityDescriptor], r12
0x180036f79  mov     [rsp+2E0h+hMem], r12
0x180036f7e  call    ?MakeRegistryWritable@@YAKPEAGPEAPEAU_ACL@@PEAPEAXPEAE22@Z; MakeRegistryWritable(ushort *,_ACL * *,void * *,uchar *,void * *,void * *)
0x180036f83  mov     rdx, [r14+rbx+8]; lpSubKey
0x180036f88  lea     rax, [rsp+2E0h+hKey]
0x180036f8d  mov     r9d, 2001Bh; samDesired
0x180036f93  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180036f98  xor     r8d, r8d; ulOptions
0x180036f9b  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180036fa2  call    cs:__imp_RegOpenKeyExW
0x180036fa8  test    eax, eax
0x180036faa  jnz     loc_1800370AC
0x180036fb0  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180036fb5  lea     rax, [rsp+2E0h+cbData]
0x180036fba  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x180036fbf  lea     r9, [rsp+2E0h+Type]; lpType
0x180036fc4  lea     rax, [rbp+1E0h+Data]
0x180036fc8  mov     [rsp+2E0h+cbData], 206h
0x180036fd0  xor     r8d, r8d; lpReserved
0x180036fd3  mov     [rsp+2E0h+phkResult], rax; lpData
0x180036fd8  lea     rdx, psz; lpValueName
0x180036fdf  call    cs:__imp_RegQueryValueExW
0x180036fe5  test    eax, eax
0x180036fe7  jnz     loc_1800370AC
0x180036fed  mov     ecx, [rsp+2E0h+cbData]
0x180036ff1  cmp     ecx, 104h
0x180036ff7  jnb     loc_1800370AC
0x180036ffd  mov     eax, [rsp+2E0h+Type]
0x180037001  dec     eax
0x180037003  cmp     eax, 1
0x180037006  ja      loc_1800370AC
0x18003700c  mov     edi, r12d
0x18003700f  test    ecx, ecx
0x180037011  jz      short loc_180037034
0x180037013  mov     ebx, edi
0x180037015  movzx   ecx, [rbp+rbx*2+1E0h+Data]; C
0x18003701a  call    cs:__imp_towupper
0x180037020  inc     edi
0x180037022  mov     [rbp+rbx*2+1E0h+Data], ax
0x180037027  cmp     edi, [rsp+2E0h+cbData]
0x18003702b  jb      short loc_180037013
0x18003702d  lea     rbx, ?ImeRegData@@3PAU_IMEREG@@A; _IMEREG near * ImeRegData
0x180037034  lea     rdx, aSystem32; "\\SYSTEM32\\"
0x18003703b  lea     rcx, [rbp+1E0h+Data]; Str
0x18003703f  call    cs:__imp_wcsstr
0x180037045  test    rax, rax
0x180037048  jnz     short loc_1800370AC
0x18003704a  mov     rcx, [r14+rbx+10h]; lpSrc
0x18003704f  lea     rdx, [rbp+1E0h+Data]; lpDst
0x180037053  mov     r8d, 104h; nSize
0x180037059  call    cs:__imp_ExpandEnvironmentStringsW
0x18003705f  dec     eax
0x180037061  cmp     eax, 102h
0x180037066  ja      loc_18003716B
0x18003706c  lea     rcx, [rbp+1E0h+Data]
0x180037070  or      rax, 0FFFFFFFFFFFFFFFFh
0x180037074  inc     rax
0x180037077  cmp     [rcx+rax*2], r12w
0x18003707c  jnz     short loc_180037074
0x18003707e  mov     r9d, [rsp+2E0h+Type]; dwType
0x180037083  lea     eax, ds:2[rax*2]
0x18003708a  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18003708f  lea     rdx, psz; lpValueName
0x180037096  mov     dword ptr [rsp+2E0h+lpcbData], eax; cbData
0x18003709a  xor     r8d, r8d; Reserved
0x18003709d  lea     rax, [rbp+1E0h+Data]
0x1800370a1  mov     [rsp+2E0h+phkResult], rax; lpData
0x1800370a6  call    cs:__imp_RegSetValueExW
0x1800370ac  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800370b1  lea     rax, [rcx-1]
0x1800370b5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800370b9  ja      short loc_1800370CA
0x1800370bb  call    cs:__imp_RegCloseKey
0x1800370c1  mov     [rsp+2E0h+hKey], 0FFFFFFFFFFFFFFFFh
0x1800370ca  mov     al, [rsp+2E0h+var_29F]
0x1800370ce  mov     rdi, [rsp+2E0h+ppSecurityDescriptor]
0x1800370d3  mov     rsi, [rsp+2E0h+psidOwner]
0x1800370d8  mov     r15, [r14+rbx]
0x1800370dc  mov     [rsp+2E0h+var_298], al
0x1800370e0  mov     rax, [rsp+2E0h+pDacl]
0x1800370e5  mov     [rsp+2E0h+OldValue], r12b
0x1800370ea  test    rax, rax
0x1800370ed  jz      short loc_18003713F
0x1800370ef  mov     rbx, [rsp+2E0h+hMem]
0x1800370f4  xor     r9d, r9d; psidOwner
0x1800370f7  mov     [rsp+2E0h+pSacl], r12; pSacl
0x1800370fc  mov     rcx, r15; pObjectName
0x1800370ff  mov     [rsp+2E0h+lpcbData], rax; pDacl
0x180037104  mov     [rsp+2E0h+phkResult], r12; psidGroup
0x180037109  lea     eax, [r9+4]
0x18003710d  mov     r8d, eax; SecurityInfo
0x180037110  mov     edx, eax; ObjectType
0x180037112  call    cs:__imp_SetNamedSecurityInfoW
0x180037118  test    eax, eax
0x18003711a  jz      short loc_18003712A
0x18003711c  mov     edx, eax; unsigned int
0x18003711e  lea     rcx, aSetnamedsecuri; "SetNamedSecurityInfo DACL_SECURITY_INFO"...
0x180037125  call    ?LogMsg@@YAXPEADK@Z; LogMsg(char *,ulong)
0x18003712a  test    rbx, rbx
0x18003712d  jz      short loc_180037138
0x18003712f  mov     rcx, rbx; hMem
0x180037132  call    cs:__imp_LocalFree
0x180037138  lea     rbx, ?ImeRegData@@3PAU_IMEREG@@A; _IMEREG near * ImeRegData
0x18003713f  xor     r8d, r8d; ForThread
0x180037142  lea     r9, [rsp+2E0h+OldValue]; OldValue
0x180037147  mov     dl, 1; NewValue
0x180037149  lea     ecx, [r8+12h]; Privilege
0x18003714d  call    cs:__imp_RtlAdjustPrivilege
0x180037153  test    eax, eax
0x180037155  jz      short loc_18003717C
0x180037157  mov     ecx, eax; Status
0x180037159  call    cs:__imp_RtlNtStatusToDosError
0x18003715f  lea     rcx, aRtladjustprivi_0; "RtlAdjustPrivilege SE_RESTORE_PRIVILEGE"...
0x180037166  jmp     loc_1800371F2
0x18003716b  mov     edx, 6Fh ; 'o'
0x180037170  lea     rcx, aExpandenvironm_0; "ExpandEnvironmentStrings Failed"
0x180037177  jmp     loc_180037228
0x18003717c  test    rsi, rsi
0x18003717f  jz      short loc_1800371C5
0x180037181  mov     edx, 4; ObjectType
0x180037186  mov     [rsp+2E0h+pSacl], r12; pSacl
0x18003718b  mov     [rsp+2E0h+lpcbData], r12; pDacl
0x180037190  mov     r9, rsi; psidOwner
0x180037193  mov     rcx, r15; pObjectName
0x180037196  mov     [rsp+2E0h+phkResult], r12; psidGroup
0x18003719b  lea     r8d, [rdx-3]; SecurityInfo
0x18003719f  call    cs:__imp_SetNamedSecurityInfoW
0x1800371a5  test    eax, eax
0x1800371a7  jz      short loc_1800371B7
0x1800371a9  mov     edx, eax; unsigned int
0x1800371ab  lea     rcx, aSetnamedsecuri_1; "SetNamedSecurityInfo Restore  OWNER_SEC"...
0x1800371b2  call    ?LogMsg@@YAXPEADK@Z; LogMsg(char *,ulong)
0x1800371b7  test    rdi, rdi
0x1800371ba  jz      short loc_1800371C5
0x1800371bc  mov     rcx, rdi; hMem
0x1800371bf  call    cs:__imp_LocalFree
0x1800371c5  cmp     [rsp+2E0h+OldValue], r12b
0x1800371ca  jnz     short loc_1800371F9
0x1800371cc  xor     edx, edx; NewValue
0x1800371ce  lea     r9, [rsp+2E0h+OldValue]; OldValue
0x1800371d3  xor     r8d, r8d; ForThread
0x1800371d6  lea     ecx, [rdx+12h]; Privilege
0x1800371d9  call    cs:__imp_RtlAdjustPrivilege
0x1800371df  test    eax, eax
0x1800371e1  jz      short loc_1800371F9
0x1800371e3  mov     ecx, eax; Status
0x1800371e5  call    cs:__imp_RtlNtStatusToDosError
0x1800371eb  lea     rcx, aRtladjustprivi_2; "RtlAdjustPrivilege Restore SE_RESTORE_P"...
0x1800371f2  mov     edx, eax; unsigned int
0x1800371f4  call    ?LogMsg@@YAXPEADK@Z; LogMsg(char *,ulong)
0x1800371f9  cmp     [rsp+2E0h+var_298], r12b
0x1800371fe  jnz     short loc_18003722D
0x180037200  xor     edx, edx; NewValue
0x180037202  lea     r9, [rsp+2E0h+var_298]; OldValue
0x180037207  xor     r8d, r8d; ForThread
0x18003720a  lea     ecx, [rdx+9]; Privilege
0x18003720d  call    cs:__imp_RtlAdjustPrivilege
0x180037213  test    eax, eax
0x180037215  jz      short loc_18003722D
0x180037217  mov     ecx, eax; Status
0x180037219  call    cs:__imp_RtlNtStatusToDosError
0x18003721f  mov     edx, eax; unsigned int
0x180037221  lea     rcx, aRtladjustprivi; "RtlAdjustPrivilege Restore Err"
0x180037228  call    ?LogMsg@@YAXPEADK@Z; LogMsg(char *,ulong)
0x18003722d  inc     r13
0x180037230  add     r14, 18h
0x180037234  cmp     r13, 2
0x180037238  jnz     loc_180036F3E
0x18003723e  xor     eax, eax
0x180037240  mov     rcx, [rbp+1E0h+var_50]
0x180037247  xor     rcx, rsp; StackCookie
0x18003724a  call    __security_check_cookie
0x18003724f  add     rsp, 2A8h
0x180037256  pop     r15
0x180037258  pop     r14
0x18003725a  pop     r13
0x18003725c  pop     r12
0x18003725e  pop     rdi
0x18003725f  pop     rsi
0x180037260  pop     rbx
0x180037261  pop     rbp
0x180037262  retn
```
