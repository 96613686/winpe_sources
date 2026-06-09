# AdjustProcessSecurityToAllowPowerUsersToWait(void)

- ea: `0x18000198c`
- end: `0x180001bd7`
- name: `?AdjustProcessSecurityToAllowPowerUsersToWait@@YAJXZ`
- size: `587`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180004a64`

## callees

- `0x18000198c`
- `0x180001be0`
- `0x180001c64`
- `0x180023d86`
- `0x180023dd0`

## import_xrefs

- `ADVAPI32!SetSecurityInfo` at `0x180001b58`
- `ADVAPI32!SetSecurityInfo` at `0x180001b58`
- `ADVAPI32!SetEntriesInAclW` at `0x180001b25`
- `ADVAPI32!SetEntriesInAclW` at `0x180001b25`
- `ADVAPI32!GetSecurityInfo` at `0x180001a7f`
- `ADVAPI32!GetSecurityInfo` at `0x180001a7f`
- `KERNEL32!LocalFree` at `0x180001ba2`
- `KERNEL32!LocalFree` at `0x180001bb7`
- `KERNEL32!LocalFree` at `0x180001ba2`
- `KERNEL32!LocalFree` at `0x180001bb7`
- `KERNEL32!GetCurrentProcess` at `0x1800019d8`
- `KERNEL32!GetCurrentProcess` at `0x1800019d8`
- `iisutil!PuDbgPrintError` at `0x180024a50`
- `iisutil!PuDbgPrintError` at `0x180024a50`

## string_xrefs

- `0x180024904`: `Creating Power User SID failed\n`
- `0x18002492e`: `Creating Power User SID failed\n`
- `0x180024a39`: `AdjustProcessSecurityToAllowPowerUsersToWait`
- `0x180024958`: `Creating System Operators SID failed\n`
- `0x180024982`: `Creating perf log user SID failed\n`
- `0x1800249ac`: `Creating perf mon user SID failed\n`
- `0x1800249d3`: `Could not get security info for the current process \n`
- `0x1800249fa`: `Could not set Acls into security descriptor \n`
- `0x180024a25`: `Could not set process security info \n`

## pseudocode

```c
__int64 AdjustProcessSecurityToAllowPowerUsersToWait(void)
{
  HANDLE CurrentProcess; // rdi
  int v1; // eax
  unsigned int v2; // ebx
  int v3; // eax
  int v4; // eax
  int v5; // eax
  int v6; // eax
  signed int SecurityInfo; // eax
  signed int v8; // eax
  signed int v9; // eax
  const char *v11; // rax
  __int64 v12; // r8
  void *v13; // [rsp+40h] [rbp-C0h] BYREF
  void *v14; // [rsp+48h] [rbp-B8h] BYREF
  void *v15; // [rsp+50h] [rbp-B0h] BYREF
  void *v16; // [rsp+58h] [rbp-A8h] BYREF
  void *v17; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+68h] [rbp-98h] BYREF
  PACL NewAcl; // [rsp+70h] [rbp-90h] BYREF
  PACL OldAcl; // [rsp+78h] [rbp-88h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+80h] [rbp-80h] BYREF
  int v22; // [rsp+B0h] [rbp-50h]
  __int64 v23; // [rsp+B4h] [rbp-4Ch]
  int v24; // [rsp+CCh] [rbp-34h]
  int v25; // [rsp+D0h] [rbp-30h]
  void *v26; // [rsp+D8h] [rbp-28h]
  int v27; // [rsp+E0h] [rbp-20h]
  __int64 v28; // [rsp+E4h] [rbp-1Ch]
  int v29; // [rsp+FCh] [rbp-4h]
  int v30; // [rsp+100h] [rbp+0h]
  void *v31; // [rsp+108h] [rbp+8h]
  int v32; // [rsp+110h] [rbp+10h]
  __int64 v33; // [rsp+114h] [rbp+14h]
  int v34; // [rsp+12Ch] [rbp+2Ch]
  int v35; // [rsp+130h] [rbp+30h]
  void *v36; // [rsp+138h] [rbp+38h]
  int v37; // [rsp+140h] [rbp+40h]
  __int64 v38; // [rsp+144h] [rbp+44h]
  int v39; // [rsp+15Ch] [rbp+5Ch]
  int v40; // [rsp+160h] [rbp+60h]
  void *v41; // [rsp+168h] [rbp+68h]

  v13 = 0;
  v14 = 0;
  v15 = 0;
  v17 = 0;
  v16 = 0;
  NewAcl = 0;
  OldAcl = 0;
  hMem = 0;
  CurrentProcess = GetCurrentProcess();
  v1 = AllocateAndCreateWellKnownSid(WinBuiltinAdministratorsSid, &v15);
  v2 = v1;
  if ( v1 )
  {
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_9;
    v11 = "Creating Power User SID failed\n";
    v12 = 2187;
LABEL_47:
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      v12,
      "AdjustProcessSecurityToAllowPowerUsersToWait",
      v2,
      v11);
    goto LABEL_9;
  }
  v3 = AllocateAndCreateWellKnownSid(WinBuiltinPowerUsersSid, &v13);
  v2 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_9;
    v11 = "Creating Power User SID failed\n";
    v12 = 2206;
    goto LABEL_47;
  }
  v4 = AllocateAndCreateWellKnownSid(WinBuiltinSystemOperatorsSid, &v14);
  v2 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v2 = (unsigned __int16)v4 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_9;
    v11 = "Creating System Operators SID failed\n";
    v12 = 2225;
    goto LABEL_47;
  }
  v5 = AllocateAndCreateWellKnownSid(WinBuiltinPerfLoggingUsersSid, &v16);
  v2 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_9;
    v11 = "Creating perf log user SID failed\n";
    v12 = 2243;
    goto LABEL_47;
  }
  v6 = AllocateAndCreateWellKnownSid(WinBuiltinPerfMonitoringUsersSid, &v17);
  v2 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_9;
    v11 = "Creating perf mon user SID failed\n";
    v12 = 2261;
    goto LABEL_47;
  }
  SecurityInfo = GetSecurityInfo(CurrentProcess, SE_KERNEL_OBJECT, 4u, 0, 0, &OldAcl, 0, &hMem);
  v2 = SecurityInfo;
  if ( SecurityInfo )
  {
    if ( SecurityInfo > 0 )
      v2 = (unsigned __int16)SecurityInfo | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_9;
    v11 = "Could not get security info for the current process \n";
    v12 = 2291;
    goto LABEL_47;
  }
  memset_0(&pListOfExplicitEntries, 0, 0xF0u);
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)v13;
  v26 = v14;
  v31 = v15;
  v36 = v17;
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  pListOfExplicitEntries.grfAccessPermissions = 0x100000;
  v23 = 1;
  v22 = 0x100000;
  v28 = 1;
  v27 = 0x100000;
  v33 = 1;
  v32 = 0x100000;
  v38 = 1;
  v37 = 0x100000;
  v41 = v16;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
  v24 = 0;
  v25 = 5;
  v29 = 0;
  v30 = 5;
  v34 = 0;
  v35 = 5;
  v39 = 0;
  v40 = 5;
  v8 = SetEntriesInAclW(5u, &pListOfExplicitEntries, OldAcl, &NewAcl);
  v2 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v2 = (unsigned __int16)v8 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_9;
    v11 = "Could not set Acls into security descriptor \n";
    v12 = 2339;
    goto LABEL_47;
  }
  v2 = 0;
  v9 = SetSecurityInfo(CurrentProcess, SE_KERNEL_OBJECT, 4u, 0, 0, NewAcl, 0);
  if ( v9 )
  {
    v2 = v9 > 0 ? (unsigned __int16)v9 | 0x80070000 : v9;
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v11 = "Could not set process security info \n";
      v12 = 2362;
      goto LABEL_47;
    }
  }
LABEL_9:
  FreeWellKnownSid(&v13);
  FreeWellKnownSid(&v14);
  FreeWellKnownSid(&v15);
  FreeWellKnownSid(&v16);
  FreeWellKnownSid(&v17);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( NewAcl )
    LocalFree(NewAcl);
  return v2;
}

```

## disassembly

```asm
0x18000198c  push    rbp
0x18000198e  push    rbx
0x18000198f  push    rsi
0x180001990  push    rdi
0x180001991  lea     rbp, [rsp-88h]
0x180001999  sub     rsp, 188h
0x1800019a0  mov     rax, cs:__security_cookie
0x1800019a7  xor     rax, rsp
0x1800019aa  mov     [rbp+0A0h+var_30], rax
0x1800019ae  xor     esi, esi
0x1800019b0  mov     [rsp+1A0h+var_160], rsi
0x1800019b5  mov     [rsp+1A0h+var_158], rsi
0x1800019ba  mov     [rsp+1A0h+var_150], rsi
0x1800019bf  mov     [rsp+1A0h+var_140], rsi
0x1800019c4  mov     [rsp+1A0h+var_148], rsi
0x1800019c9  mov     [rsp+1A0h+NewAcl], rsi
0x1800019ce  mov     [rsp+1A0h+OldAcl], rsi
0x1800019d3  mov     [rsp+1A0h+hMem], rsi
0x1800019d8  call    cs:__imp_GetCurrentProcess
0x1800019de  lea     rdx, [rsp+1A0h+var_150]; void **
0x1800019e3  mov     rdi, rax
0x1800019e6  lea     ecx, [rsi+1Ah]; WellKnownSidType
0x1800019e9  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x1800019ee  mov     ebx, eax
0x1800019f0  test    eax, eax
0x1800019f2  jnz     loc_1800248EC
0x1800019f8  lea     rdx, [rsp+1A0h+var_160]; void **
0x1800019fd  lea     ecx, [rsi+1Dh]; WellKnownSidType
0x180001a00  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180001a05  mov     ebx, eax
0x180001a07  test    eax, eax
0x180001a09  jnz     loc_180024916
0x180001a0f  lea     rdx, [rsp+1A0h+var_158]; void **
0x180001a14  lea     ecx, [rsi+1Fh]; WellKnownSidType
0x180001a17  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180001a1c  mov     ebx, eax
0x180001a1e  test    eax, eax
0x180001a20  jnz     loc_180024940
0x180001a26  lea     rdx, [rsp+1A0h+var_148]; void **
0x180001a2b  lea     ecx, [rsi+3Ah]; WellKnownSidType
0x180001a2e  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180001a33  mov     ebx, eax
0x180001a35  test    eax, eax
0x180001a37  jnz     loc_18002496A
0x180001a3d  lea     rdx, [rsp+1A0h+var_140]; void **
0x180001a42  lea     ecx, [rsi+39h]; WellKnownSidType
0x180001a45  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180001a4a  mov     ebx, eax
0x180001a4c  test    eax, eax
0x180001a4e  jnz     loc_180024994
0x180001a54  lea     rax, [rsp+1A0h+hMem]
0x180001a59  xor     r9d, r9d; ppsidOwner
0x180001a5c  mov     [rsp+1A0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180001a61  lea     edx, [rsi+6]; ObjectType
0x180001a64  lea     rax, [rsp+1A0h+OldAcl]
0x180001a69  mov     [rsp+1A0h+ppSacl], rsi; ppSacl
0x180001a6e  mov     [rsp+1A0h+ppDacl], rax; ppDacl
0x180001a73  lea     r8d, [rsi+4]; SecurityInfo
0x180001a77  mov     rcx, rdi; handle
0x180001a7a  mov     [rsp+1A0h+ppsidGroup], rsi; ppsidGroup
0x180001a7f  call    cs:__imp_GetSecurityInfo
0x180001a85  mov     ebx, eax
0x180001a87  test    eax, eax
0x180001a89  jnz     loc_1800249BB
0x180001a8f  xor     edx, edx; Val
0x180001a91  lea     rcx, [rbp+0A0h+pListOfExplicitEntries]; void *
0x180001a95  mov     r8d, 0F0h; Size
0x180001a9b  call    memset_0
0x180001aa0  mov     rax, [rsp+1A0h+var_160]
0x180001aa5  lea     r8d, [rsi+1]
0x180001aa9  mov     edx, 100000h
0x180001aae  mov     [rbp+0A0h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180001ab2  mov     rax, [rsp+1A0h+var_158]
0x180001ab7  lea     ecx, [rsi+5]; cCountOfExplicitEntries
0x180001aba  mov     [rbp+0A0h+var_C8], rax
0x180001abe  lea     r9, [rsp+1A0h+NewAcl]; NewAcl
0x180001ac3  mov     rax, [rsp+1A0h+var_150]
0x180001ac8  mov     [rbp+0A0h+var_98], rax
0x180001acc  mov     rax, [rsp+1A0h+var_140]
0x180001ad1  mov     [rbp+0A0h+var_68], rax
0x180001ad5  mov     rax, [rsp+1A0h+var_148]
0x180001ada  mov     [rbp+0A0h+pListOfExplicitEntries.grfAccessMode], r8d
0x180001ade  mov     [rbp+0A0h+pListOfExplicitEntries.grfAccessPermissions], edx
0x180001ae1  mov     [rbp+0A0h+var_EC], r8
0x180001ae5  mov     [rbp+0A0h+var_F0], edx
0x180001ae8  mov     [rbp+0A0h+var_BC], r8
0x180001aec  mov     [rbp+0A0h+var_C0], edx
0x180001aef  mov     [rbp+0A0h+var_8C], r8
0x180001af3  mov     [rbp+0A0h+var_90], edx
0x180001af6  mov     [rbp+0A0h+var_5C], r8
0x180001afa  mov     r8, [rsp+1A0h+OldAcl]; OldAcl
0x180001aff  mov     [rbp+0A0h+var_60], edx
0x180001b02  lea     rdx, [rbp+0A0h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180001b06  mov     [rbp+0A0h+var_38], rax
0x180001b0a  mov     [rbp+0A0h+pListOfExplicitEntries.Trustee.TrusteeType], ecx
0x180001b0d  mov     [rbp+0A0h+var_D4], esi
0x180001b10  mov     [rbp+0A0h+var_D0], ecx
0x180001b13  mov     [rbp+0A0h+var_A4], esi
0x180001b16  mov     [rbp+0A0h+var_A0], ecx
0x180001b19  mov     [rbp+0A0h+var_74], esi
0x180001b1c  mov     [rbp+0A0h+var_70], ecx
0x180001b1f  mov     [rbp+0A0h+var_44], esi
0x180001b22  mov     [rbp+0A0h+var_40], ecx
0x180001b25  call    cs:__imp_SetEntriesInAclW
0x180001b2b  mov     ebx, eax
0x180001b2d  test    eax, eax
0x180001b2f  jnz     loc_1800249E2
0x180001b35  mov     rax, [rsp+1A0h+NewAcl]
0x180001b3a  lea     edx, [rsi+6]; ObjectType
0x180001b3d  mov     [rsp+1A0h+ppSacl], rsi; pSacl
0x180001b42  lea     r8d, [rsi+4]; SecurityInfo
0x180001b46  mov     [rsp+1A0h+ppDacl], rax; pDacl
0x180001b4b  xor     r9d, r9d; psidOwner
0x180001b4e  mov     rcx, rdi; handle
0x180001b51  mov     [rsp+1A0h+ppsidGroup], rsi; psidGroup
0x180001b56  mov     ebx, esi
0x180001b58  call    cs:__imp_SetSecurityInfo
0x180001b5e  test    eax, eax
0x180001b60  jnz     loc_180024A09
0x180001b66  lea     rcx, [rsp+1A0h+var_160]; void **
0x180001b6b  call    ?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x180001b70  lea     rcx, [rsp+1A0h+var_158]; void **
0x180001b75  call    ?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x180001b7a  lea     rcx, [rsp+1A0h+var_150]; void **
0x180001b7f  call    ?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x180001b84  lea     rcx, [rsp+1A0h+var_148]; void **
0x180001b89  call    ?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x180001b8e  lea     rcx, [rsp+1A0h+var_140]; void **
0x180001b93  call    ?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x180001b98  mov     rcx, [rsp+1A0h+hMem]; hMem
0x180001b9d  test    rcx, rcx
0x180001ba0  jz      short loc_180001BAD
0x180001ba2  call    cs:__imp_LocalFree
0x180001ba8  mov     [rsp+1A0h+hMem], rsi
0x180001bad  mov     rcx, [rsp+1A0h+NewAcl]; hMem
0x180001bb2  test    rcx, rcx
0x180001bb5  jz      short loc_180001BBD
0x180001bb7  call    cs:__imp_LocalFree
0x180001bbd  mov     eax, ebx
0x180001bbf  mov     rcx, [rbp+0A0h+var_30]
0x180001bc3  xor     rcx, rsp; StackCookie
0x180001bc6  call    __security_check_cookie
0x180001bcb  add     rsp, 188h
0x180001bd2  pop     rdi
0x180001bd3  pop     rsi
0x180001bd4  pop     rbx
0x180001bd5  pop     rbp
0x180001bd6  retn
0x1800248ec  jle     short loc_1800248F7
0x1800248ee  movzx   ebx, ax
0x1800248f1  or      ebx, 80070000h
0x1800248f7  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800248fe  jz      loc_180001B66
0x180024904  lea     rax, aCreatingPowerU; "Creating Power User SID failed\n"
0x18002490b  mov     r8d, 88Bh
0x180024911  jmp     loc_180024A32
0x180024916  jle     short loc_180024921
0x180024918  movzx   ebx, ax
0x18002491b  or      ebx, 80070000h
0x180024921  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024928  jz      loc_180001B66
0x18002492e  lea     rax, aCreatingPowerU; "Creating Power User SID failed\n"
0x180024935  mov     r8d, 89Eh
0x18002493b  jmp     loc_180024A32
0x180024940  jle     short loc_18002494B
0x180024942  movzx   ebx, ax
0x180024945  or      ebx, 80070000h
0x18002494b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024952  jz      loc_180001B66
0x180024958  lea     rax, aCreatingSystem; "Creating System Operators SID failed\n"
0x18002495f  mov     r8d, 8B1h
0x180024965  jmp     loc_180024A32
0x18002496a  jle     short loc_180024975
0x18002496c  movzx   ebx, ax
0x18002496f  or      ebx, 80070000h
0x180024975  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002497c  jz      loc_180001B66
0x180024982  lea     rax, aCreatingPerfLo; "Creating perf log user SID failed\n"
0x180024989  mov     r8d, 8C3h
0x18002498f  jmp     loc_180024A32
0x180024994  jle     short loc_18002499F
0x180024996  movzx   ebx, ax
0x180024999  or      ebx, 80070000h
0x18002499f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800249a6  jz      loc_180001B66
0x1800249ac  lea     rax, aCreatingPerfMo; "Creating perf mon user SID failed\n"
0x1800249b3  mov     r8d, 8D5h
0x1800249b9  jmp     short loc_180024A32
0x1800249bb  jle     short loc_1800249C6
0x1800249bd  movzx   ebx, ax
0x1800249c0  or      ebx, 80070000h
0x1800249c6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800249cd  jz      loc_180001B66
0x1800249d3  lea     rax, aCouldNotGetSec; "Could not get security info for the cur"...
0x1800249da  mov     r8d, 8F3h
0x1800249e0  jmp     short loc_180024A32
0x1800249e2  jle     short loc_1800249ED
0x1800249e4  movzx   ebx, ax
0x1800249e7  or      ebx, 80070000h
0x1800249ed  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800249f4  jz      loc_180001B66
0x1800249fa  lea     rax, aCouldNotSetAcl; "Could not set Acls into security descri"...
0x180024a01  mov     r8d, 923h
0x180024a07  jmp     short loc_180024A32
0x180024a09  jg      short loc_180024A0F
0x180024a0b  mov     ebx, eax
0x180024a0d  jmp     short loc_180024A18
0x180024a0f  movzx   ebx, ax
0x180024a12  or      ebx, 80070000h
0x180024a18  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024a1f  jz      loc_180001B66
0x180024a25  lea     rax, aCouldNotSetPro; "Could not set process security info \n"
0x180024a2c  mov     r8d, 93Ah
0x180024a32  mov     rcx, cs:g_pDebug
0x180024a39  lea     r9, aAdjustprocesss; "AdjustProcessSecurityToAllowPowerUsersT"...
0x180024a40  mov     [rsp+1A0h+ppDacl], rax
0x180024a45  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cp"...
0x180024a4c  mov     dword ptr [rsp+1A0h+ppsidGroup], ebx
0x180024a50  call    cs:__imp_PuDbgPrintError
0x180024a56  nop
0x180024a57  jmp     loc_180001B66
```
