# ShieldProvider::InitializeSecurity

- ea: `0x140004174`
- end: `0x140004581`
- name: `ShieldProvider::InitializeSecurity`
- size: `1037`
- prototype: `__int64 __fastcall(__int64, void **, const struct _GUID *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140005110`

## callees

- `0x1400015d0`
- `0x140002370`
- `0x140003640`
- `0x140004174`
- `0x140011174`
- `0x140012180`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140004388`
- `KERNEL32!GetLastError` at `0x140004472`
- `KERNEL32!GetLastError` at `0x140004388`
- `KERNEL32!GetLastError` at `0x140004472`
- `KERNEL32!LocalFree` at `0x1400043d5`
- `KERNEL32!LocalFree` at `0x14000452a`
- `KERNEL32!LocalFree` at `0x14000453f`
- `KERNEL32!LocalFree` at `0x1400043d5`
- `KERNEL32!LocalFree` at `0x14000452a`
- `KERNEL32!LocalFree` at `0x14000453f`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140004468`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140004468`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140004310`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140004310`
- `ole32!CoInitializeSecurity` at `0x1400044e6`
- `ole32!CoInitializeSecurity` at `0x1400044e6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14000437e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14000437e`
- `ext-ms-win32-subsystem-query-l1-1-0!QueryWin32SubsystemHost` at `0x14000432d`
- `ext-ms-win32-subsystem-query-l1-1-0!QueryWin32SubsystemHost` at `0x140004340`
- `ext-ms-win32-subsystem-query-l1-1-0!QueryWin32SubsystemHost` at `0x140004354`
- `ext-ms-win32-subsystem-query-l1-1-0!QueryWin32SubsystemHost` at `0x14000432d`
- `ext-ms-win32-subsystem-query-l1-1-0!QueryWin32SubsystemHost` at `0x140004340`
- `ext-ms-win32-subsystem-query-l1-1-0!QueryWin32SubsystemHost` at `0x140004354`

## pseudocode

```c
__int64 __fastcall ShieldProvider::InitializeSecurity(
        __int64 a1,
        void **a2,
        const struct _GUID *a3,
        const struct _GUID *a4)
{
  signed int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  void (*v7)(void); // rax
  int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  const WCHAR *v12; // rcx
  signed int LastError; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  signed int v16; // eax
  HRESULT v17; // eax
  unsigned int lpdwDaclSize; // [rsp+20h] [rbp-E0h]
  struct IUnknown *pSacl; // [rsp+28h] [rbp-D8h]
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  int v21; // [rsp+68h] [rbp-98h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp-90h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+78h] [rbp-88h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD dwOwnerSize; // [rsp+80h] [rbp-80h] BYREF
  DWORD dwSaclSize; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD dwDaclSize; // [rsp+88h] [rbp-78h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+8Ch] [rbp-74h] BYREF
  __int64 v29; // [rsp+90h] [rbp-70h] BYREF
  _BYTE pAbsoluteSecurityDescriptor[2048]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pPrimaryGroup[2048]; // [rsp+8A0h] [rbp+7A0h] BYREF
  _BYTE pOwner[2048]; // [rsp+10A0h] [rbp+FA0h] BYREF
  struct _ACL pDacl; // [rsp+18A0h] [rbp+17A0h] BYREF

  ppv = 0;
  v4 = CommonUtil::UtilCoCreateInstanceImpl(&ppv, a2, a3, a4, lpdwDaclSize, pSacl);
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v6 = 37;
LABEL_5:
    WPP_SF_d(v5[2], v6, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids, (unsigned int)v4);
LABEL_6:
    if ( !ppv )
      return (unsigned int)v4;
    v7 = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
LABEL_8:
    v7();
    return (unsigned int)v4;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v6 = 38;
    goto LABEL_5;
  }
  v29 = 0;
  v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, 4, &v29);
  if ( v9 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_23;
    v11 = 40;
  }
  else
  {
    v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 4, v29 | 8);
    if ( v9 >= 0 )
      goto LABEL_23;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_23;
    v11 = 39;
  }
  WPP_SF_d(v10[2], v11, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids, (unsigned int)v9);
LABEL_23:
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  if ( ShieldProvider::g_fDevMode )
  {
    v12 = L"O:BAG:BAD:(A;;0x3;;;SY)(A;;0x3;;;BA)(A;;0x23;;;IU)(A;;0x3;;;LS)(A;;0x23;;;AC)(A;;0x23;;;AN)";
  }
  else
  {
    v21 = 0;
    RtlGetDeviceFamilyInfoEnum(0, &v21, 0);
    if ( (v21 == 16 || v21 == 6)
      && (!(unsigned __int8)IsQueryWin32SubsystemHostPresent() || !(unsigned int)QueryWin32SubsystemHost())
      || (unsigned __int8)IsQueryWin32SubsystemHostPresent() && (unsigned int)QueryWin32SubsystemHost() == 1
      || (unsigned __int8)IsQueryWin32SubsystemHostPresent() && (unsigned int)QueryWin32SubsystemHost() == 2 )
    {
      v12 = L"O:BAG:BAD:(A;;0x3;;;SY)(A;;0x3;;;BA)(A;;0x23;;;IU)(A;;0x23;;;AC)(A;;0x3;;;LS)(A;;0x3;;;S-1-15-2-2743877165-1"
             "931364543-2468930561-3765762410-1162139025-1178895811-1086226821)";
    }
    else
    {
      v12 = L"O:BAG:BAD:(A;;0x3;;;SY)(A;;0x3;;;BA)(A;;0x3;;;IU)(A;;0x3;;;LS)(A;;0x3;;;S-1-15-2-2743877165-1931364543-24689"
             "30561-3765762410-1162139025-1178895811-1086226821)";
    }
  }
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v12, 1u, &SecurityDescriptor, &SecurityDescriptorSize) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_43;
      v15 = 41;
LABEL_42:
      WPP_SF_d(v14[2], v15, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids, (unsigned int)v4);
LABEL_43:
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
      if ( !ppv )
        return (unsigned int)v4;
      v7 = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
      goto LABEL_8;
    }
  }
  dwSaclSize = 0;
  dwAbsoluteSecurityDescriptorSize = 2048;
  dwDaclSize = 2048;
  dwOwnerSize = 2048;
  dwPrimaryGroupSize = 2048;
  if ( !MakeAbsoluteSD(
          SecurityDescriptor,
          pAbsoluteSecurityDescriptor,
          &dwAbsoluteSecurityDescriptorSize,
          &pDacl,
          &dwDaclSize,
          0,
          &dwSaclSize,
          pOwner,
          &dwOwnerSize,
          pPrimaryGroup,
          &dwPrimaryGroupSize) )
  {
    v16 = GetLastError();
    v4 = v16;
    if ( v16 > 0 )
      v4 = (unsigned __int16)v16 | 0x80070000;
    if ( v4 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_43;
      v15 = 42;
      goto LABEL_42;
    }
  }
  v17 = CoInitializeSecurity(pAbsoluteSecurityDescriptor, -1, 0, 0, 2u, 2u, 0, 0, 0);
  v4 = v17;
  if ( v17 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids,
        (unsigned int)v17);
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    goto LABEL_6;
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 0;
}

```

## disassembly

```asm
0x140004174  mov     [rsp-8+arg_0], rbx
0x140004179  mov     [rsp-8+arg_8], rdi
0x14000417e  push    rbp
0x14000417f  lea     rbp, [rsp-1FB0h]
0x140004187  mov     eax, 20B0h
0x14000418c  call    _alloca_probe
0x140004191  sub     rsp, rax
0x140004194  mov     rax, cs:__security_cookie
0x14000419b  xor     rax, rsp
0x14000419e  mov     [rbp+1FB0h+var_10], rax
0x1400041a5  lea     rcx, [rsp+20B0h+ppv]; ppv
0x1400041aa  mov     [rsp+20B0h+ppv], 0
0x1400041b3  call    ?UtilCoCreateInstanceImpl@CommonUtil@@YAJPEAPEAXAEBU_GUID@@1KPEAUIUnknown@@@Z; CommonUtil::UtilCoCreateInstanceImpl(void * *,_GUID const &,_GUID const &,ulong,IUnknown *)
0x1400041b8  mov     ebx, eax
0x1400041ba  test    eax, eax
0x1400041bc  jns     short loc_14000420C
0x1400041be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400041c5  lea     rdi, WPP_GLOBAL_Control
0x1400041cc  cmp     rcx, rdi
0x1400041cf  jz      short loc_1400041EF
0x1400041d1  test    byte ptr [rcx+1Ch], 1
0x1400041d5  jz      short loc_1400041EF
0x1400041d7  mov     edx, 25h ; '%'
0x1400041dc  mov     rcx, [rcx+10h]
0x1400041e0  lea     r8, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids
0x1400041e7  mov     r9d, ebx
0x1400041ea  call    WPP_SF_d
0x1400041ef  mov     rcx, [rsp+20B0h+ppv]
0x1400041f4  test    rcx, rcx
0x1400041f7  jz      short loc_140004205
0x1400041f9  mov     rax, [rcx]
0x1400041fc  mov     rax, [rax+10h]
0x140004200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004205  mov     eax, ebx
0x140004207  jmp     loc_14000455D
0x14000420c  mov     rcx, [rsp+20B0h+ppv]
0x140004211  mov     edx, 5
0x140004216  mov     rax, [rcx]
0x140004219  lea     r8d, [rdx-4]
0x14000421d  mov     rax, [rax+18h]
0x140004221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004226  mov     ebx, eax
0x140004228  test    eax, eax
0x14000422a  jns     short loc_14000424C
0x14000422c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004233  lea     rdi, WPP_GLOBAL_Control
0x14000423a  cmp     rcx, rdi
0x14000423d  jz      short loc_1400041EF
0x14000423f  test    byte ptr [rcx+1Ch], 1
0x140004243  jz      short loc_1400041EF
0x140004245  mov     edx, 26h ; '&'
0x14000424a  jmp     short loc_1400041DC
0x14000424c  mov     rcx, [rsp+20B0h+ppv]
0x140004251  lea     r8, [rbp+1FB0h+var_2020]
0x140004255  mov     [rbp+1FB0h+var_2020], 0
0x14000425d  mov     ebx, 4
0x140004262  mov     edx, ebx
0x140004264  mov     rax, [rcx]
0x140004267  mov     rax, [rax+20h]
0x14000426b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004270  lea     rdi, WPP_GLOBAL_Control
0x140004277  test    eax, eax
0x140004279  js      short loc_1400042B1
0x14000427b  mov     rcx, [rsp+20B0h+ppv]
0x140004280  mov     edx, ebx
0x140004282  mov     r8, [rbp+1FB0h+var_2020]
0x140004286  or      r8, 8
0x14000428a  mov     rax, [rcx]
0x14000428d  mov     rax, [rax+18h]
0x140004291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004296  test    eax, eax
0x140004298  jns     short loc_1400042DB
0x14000429a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400042a1  cmp     rcx, rdi
0x1400042a4  jz      short loc_1400042DB
0x1400042a6  test    byte ptr [rcx+1Ch], 1
0x1400042aa  jz      short loc_1400042DB
0x1400042ac  lea     edx, [rbx+23h]
0x1400042af  jmp     short loc_1400042C8
0x1400042b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400042b8  cmp     rcx, rdi
0x1400042bb  jz      short loc_1400042DB
0x1400042bd  test    byte ptr [rcx+1Ch], 1
0x1400042c1  jz      short loc_1400042DB
0x1400042c3  mov     edx, 28h ; '('
0x1400042c8  mov     rcx, [rcx+10h]
0x1400042cc  lea     r8, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids
0x1400042d3  mov     r9d, eax
0x1400042d6  call    WPP_SF_d
0x1400042db  cmp     cs:?g_fDevMode@ShieldProvider@@3_NA, 0; bool ShieldProvider::g_fDevMode
0x1400042e2  mov     [rsp+20B0h+SecurityDescriptor], 0
0x1400042eb  mov     [rsp+20B0h+SecurityDescriptorSize], 0
0x1400042f3  jz      short loc_1400042FE
0x1400042f5  lea     rcx, aOBagBadA0x3SyA_1; "O:BAG:BAD:(A;;0x3;;;SY)(A;;0x3;;;BA)(A;"...
0x1400042fc  jmp     short loc_14000436F
0x1400042fe  xor     r8d, r8d
0x140004301  mov     [rsp+20B0h+var_2048], 0
0x140004309  lea     rdx, [rsp+20B0h+var_2048]
0x14000430e  xor     ecx, ecx
0x140004310  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x140004316  cmp     [rsp+20B0h+var_2048], 10h
0x14000431b  jz      short loc_140004324
0x14000431d  cmp     [rsp+20B0h+var_2048], 6
0x140004322  jnz     short loc_140004337
0x140004324  call    IsQueryWin32SubsystemHostPresent
0x140004329  test    al, al
0x14000432b  jz      short loc_140004368
0x14000432d  call    cs:__imp_QueryWin32SubsystemHost
0x140004333  test    eax, eax
0x140004335  jz      short loc_140004368
0x140004337  call    IsQueryWin32SubsystemHostPresent
0x14000433c  test    al, al
0x14000433e  jz      short loc_14000434B
0x140004340  call    cs:__imp_QueryWin32SubsystemHost
0x140004346  cmp     eax, 1
0x140004349  jz      short loc_140004368
0x14000434b  call    IsQueryWin32SubsystemHostPresent
0x140004350  test    al, al
0x140004352  jz      short loc_14000435F
0x140004354  call    cs:__imp_QueryWin32SubsystemHost
0x14000435a  cmp     eax, 2
0x14000435d  jz      short loc_140004368
0x14000435f  lea     rcx, aOBagBadA0x3SyA; "O:BAG:BAD:(A;;0x3;;;SY)(A;;0x3;;;BA)(A;"...
0x140004366  jmp     short loc_14000436F
0x140004368  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;;0x3;;;SY)(A;;0x3;;;BA)(A;"...
0x14000436f  lea     r9, [rsp+20B0h+SecurityDescriptorSize]; SecurityDescriptorSize
0x140004374  mov     edx, 1; StringSDRevision
0x140004379  lea     r8, [rsp+20B0h+SecurityDescriptor]; SecurityDescriptor
0x14000437e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140004384  test    eax, eax
0x140004386  jnz     short loc_1400043F5
0x140004388  call    cs:__imp_GetLastError
0x14000438e  mov     ebx, eax
0x140004390  test    eax, eax
0x140004392  jle     short loc_14000439D
0x140004394  movzx   ebx, ax
0x140004397  or      ebx, 80070000h
0x14000439d  test    ebx, ebx
0x14000439f  jns     short loc_1400043F5
0x1400043a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400043a8  cmp     rcx, rdi
0x1400043ab  jz      short loc_1400043CB
0x1400043ad  test    byte ptr [rcx+1Ch], 1
0x1400043b1  jz      short loc_1400043CB
0x1400043b3  mov     edx, 29h ; ')'
0x1400043b8  mov     rcx, [rcx+10h]
0x1400043bc  lea     r8, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids
0x1400043c3  mov     r9d, ebx
0x1400043c6  call    WPP_SF_d
0x1400043cb  mov     rcx, [rsp+20B0h+SecurityDescriptor]; hMem
0x1400043d0  test    rcx, rcx
0x1400043d3  jz      short loc_1400043DB
0x1400043d5  call    cs:__imp_LocalFree
0x1400043db  mov     rcx, [rsp+20B0h+ppv]
0x1400043e0  test    rcx, rcx
0x1400043e3  jz      loc_140004205
0x1400043e9  mov     rdx, [rcx]
0x1400043ec  mov     rax, [rdx+10h]
0x1400043f0  jmp     loc_140004200
0x1400043f5  mov     rcx, [rsp+20B0h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x1400043fa  lea     r9, [rbp+1FB0h+pDacl]; pDacl
0x140004401  mov     eax, 800h
0x140004406  mov     [rbp+1FB0h+dwSaclSize], 0
0x14000440d  mov     [rbp+1FB0h+dwAbsoluteSecurityDescriptorSize], eax
0x140004410  lea     r8, [rbp+1FB0h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140004414  mov     [rbp+1FB0h+dwDaclSize], eax
0x140004417  lea     rdx, [rbp+1FB0h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x14000441b  mov     [rbp+1FB0h+dwOwnerSize], eax
0x14000441e  mov     [rsp+20B0h+dwPrimaryGroupSize], eax
0x140004422  lea     rax, [rsp+20B0h+dwPrimaryGroupSize]
0x140004427  mov     [rsp+20B0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x14000442c  lea     rax, [rbp+1FB0h+var_1810]
0x140004433  mov     [rsp+20B0h+pPrimaryGroup], rax; pPrimaryGroup
0x140004438  lea     rax, [rbp+1FB0h+dwOwnerSize]
0x14000443c  mov     [rsp+20B0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140004441  lea     rax, [rbp+1FB0h+var_1010]
0x140004448  mov     [rsp+20B0h+pOwner], rax; pOwner
0x14000444d  lea     rax, [rbp+1FB0h+dwSaclSize]
0x140004451  mov     [rsp+20B0h+lpdwSaclSize], rax; lpdwSaclSize
0x140004456  lea     rax, [rbp+1FB0h+dwDaclSize]
0x14000445a  mov     [rsp+20B0h+pSacl], 0; pSacl
0x140004463  mov     [rsp+20B0h+lpdwDaclSize], rax; lpdwDaclSize
0x140004468  call    cs:__imp_MakeAbsoluteSD
0x14000446e  test    eax, eax
0x140004470  jnz     short loc_1400044AF
0x140004472  call    cs:__imp_GetLastError
0x140004478  mov     ebx, eax
0x14000447a  test    eax, eax
0x14000447c  jle     short loc_140004487
0x14000447e  movzx   ebx, ax
0x140004481  or      ebx, 80070000h
0x140004487  test    ebx, ebx
0x140004489  jns     short loc_1400044AF
0x14000448b  mov     rcx, cs:WPP_GLOBAL_Control
0x140004492  cmp     rcx, rdi
0x140004495  jz      loc_1400043CB
0x14000449b  test    byte ptr [rcx+1Ch], 1
0x14000449f  jz      loc_1400043CB
0x1400044a5  mov     edx, 2Ah ; '*'
0x1400044aa  jmp     loc_1400043B8
0x1400044af  mov     [rsp+20B0h+lpdwOwnerSize], 0; pReserved3
0x1400044b8  lea     rcx, [rbp+1FB0h+pAbsoluteSecurityDescriptor]; pSecDesc
0x1400044bc  mov     dword ptr [rsp+20B0h+pOwner], 0; dwCapabilities
0x1400044c4  xor     r9d, r9d; pReserved1
0x1400044c7  mov     [rsp+20B0h+lpdwSaclSize], 0; pAuthList
0x1400044d0  xor     r8d, r8d; asAuthSvc
0x1400044d3  mov     dword ptr [rsp+20B0h+pSacl], 2; dwImpLevel
0x1400044db  or      edx, 0FFFFFFFFh; cAuthSvc
0x1400044de  mov     dword ptr [rsp+20B0h+lpdwDaclSize], 2; dwAuthnLevel
0x1400044e6  call    cs:__imp_CoInitializeSecurity
0x1400044ec  mov     ebx, eax
0x1400044ee  test    eax, eax
0x1400044f0  jns     short loc_140004535
0x1400044f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400044f9  cmp     rcx, rdi
0x1400044fc  jz      short loc_14000451C
0x1400044fe  test    byte ptr [rcx+1Ch], 1
0x140004502  jz      short loc_14000451C
0x140004504  mov     rcx, [rcx+10h]
0x140004508  lea     r8, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids
0x14000450f  mov     edx, 2Bh ; '+'
0x140004514  mov     r9d, eax
0x140004517  call    WPP_SF_d
0x14000451c  mov     rcx, [rsp+20B0h+SecurityDescriptor]; hMem
0x140004521  test    rcx, rcx
0x140004524  jz      loc_1400041EF
0x14000452a  call    cs:__imp_LocalFree
0x140004530  jmp     loc_1400041EF
0x140004535  mov     rcx, [rsp+20B0h+SecurityDescriptor]; hMem
0x14000453a  test    rcx, rcx
0x14000453d  jz      short loc_140004545
0x14000453f  call    cs:__imp_LocalFree
0x140004545  mov     rcx, [rsp+20B0h+ppv]
0x14000454a  test    rcx, rcx
0x14000454d  jz      short loc_14000455B
0x14000454f  mov     rax, [rcx]
0x140004552  mov     rax, [rax+10h]
0x140004556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000455b  xor     eax, eax
0x14000455d  mov     rcx, [rbp+1FB0h+var_10]
0x140004564  xor     rcx, rsp; StackCookie
0x140004567  call    __security_check_cookie
0x14000456c  lea     r11, [rsp+20B0h+var_s0]
0x140004574  mov     rbx, [r11+10h]
0x140004578  mov     rdi, [r11+18h]
0x14000457c  mov     rsp, r11
0x14000457f  pop     rbp
0x140004580  retn
```
