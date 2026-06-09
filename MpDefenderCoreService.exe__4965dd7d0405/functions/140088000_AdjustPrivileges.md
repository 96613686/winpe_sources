# AdjustPrivileges

- ea: `0x140088000`
- end: `0x1400885c0`
- name: `AdjustPrivileges`
- size: `1472`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140089890`

## callees

- `0x14000d738`
- `0x14000dde4`
- `0x1400107ac`
- `0x140010fb4`
- `0x140011038`
- `0x140012100`
- `0x1400125a8`
- `0x1400125f8`
- `0x14001263c`
- `0x140012840`
- `0x140015574`
- `0x140017738`
- `0x14003a130`
- `0x14003a5c0`
- `0x14007d210`
- `0x140085d38`
- `0x140085d94`
- `0x140085eb4`
- `0x140088000`
- `0x140166d30`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x14008826b`
- `KERNEL32!GetCurrentProcess` at `0x14008826b`
- `KERNEL32!CloseHandle` at `0x14008827d`
- `KERNEL32!CloseHandle` at `0x1400882ce`
- `KERNEL32!CloseHandle` at `0x1400884e0`
- `KERNEL32!CloseHandle` at `0x140088519`
- `KERNEL32!CloseHandle` at `0x14008858e`
- `KERNEL32!CloseHandle` at `0x14008827d`
- `KERNEL32!CloseHandle` at `0x1400882ce`
- `KERNEL32!CloseHandle` at `0x1400884e0`
- `KERNEL32!CloseHandle` at `0x140088519`
- `KERNEL32!CloseHandle` at `0x14008858e`
- `ADVAPI32!AdjustTokenPrivileges` at `0x140088440`
- `ADVAPI32!AdjustTokenPrivileges` at `0x140088440`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1400883b6`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1400883b6`
- `ADVAPI32!RegCloseKey` at `0x1400880ef`
- `ADVAPI32!RegCloseKey` at `0x140088237`
- `ADVAPI32!RegCloseKey` at `0x1400880ef`
- `ADVAPI32!RegCloseKey` at `0x140088237`

## string_xrefs

- `0x14008802d`: `SeBackupPrivilege`
- `0x14008816f`: `SeBackupPrivilege`
- `0x140088379`: `SeBackupPrivilege`

## pseudocode

```c
__int64 __fastcall AdjustPrivileges(__int64 a1, const wchar_t *a2)
{
  CommonUtil *v2; // rdi
  const wchar_t *v3; // r8
  unsigned int v4; // r14d
  int v5; // eax
  int v6; // ebx
  int ValueMultiString; // eax
  const struct std::nothrow_t *v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rdx
  void **CurrentProcess; // rbx
  unsigned int v15; // r9d
  int v16; // eax
  enum _TOKEN_INFORMATION_CLASS v17; // r9d
  int TokenInformationImpl; // eax
  unsigned __int64 v19; // r8
  void *v20; // rcx
  void **v21; // rdx
  struct _LUID *v22; // rbx
  __int64 v23; // rdi
  const WCHAR *v24; // rax
  struct _TOKEN_PRIVILEGES *v25; // r8
  unsigned int v26; // edi
  int v27; // esi
  __int64 i; // r9
  __int64 v29; // r10
  unsigned int v30; // eax
  unsigned int v31; // edi
  unsigned int LastFailure; // eax
  unsigned int PreviousState; // [rsp+20h] [rbp-50h]
  wchar_t **PreviousStatea; // [rsp+20h] [rbp-50h]
  PDWORD ReturnLength; // [rsp+28h] [rbp-48h]
  HANDLE hObject; // [rsp+30h] [rbp-40h] BYREF
  PTOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-38h] BYREF
  void *Buf1; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  wchar_t v40[4]; // [rsp+50h] [rbp-20h] BYREF
  __int128 v41; // [rsp+58h] [rbp-18h] BYREF

  v2 = (CommonUtil *)CommonUtil::UtilRegMultiStringLen((CommonUtil *)L"SeBackupPrivilege", a2);
  v4 = CommonUtil::UtilRegMultiStringCount(v2, (unsigned __int64)L"SeBackupPrivilege", v3);
  if ( !(unsigned int)MpIsWindowsRedstoneOrGreater() )
    goto LABEL_38;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_S(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      36,
      &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
      &stru_140194C20);
  hKey = 0;
  v5 = CommonUtil::UtilRegOpenKey(
         (CommonUtil *)&hKey,
         (HKEY *)0xFFFFFFFF80000002LL,
         (HKEY)&stru_140194C20,
         (const wchar_t *)0x2001F,
         PreviousState);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Sd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        37,
        (unsigned int)&WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
        (unsigned int)&stru_140194C20,
        v5);
LABEL_9:
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v6;
  }
  Buf1 = 0;
  *(_QWORD *)v40 = 0;
  ValueMultiString = CommonUtil::UtilRegGetValueMultiString(
                       (CommonUtil *)hKey,
                       (HKEY)&stru_1401950E8,
                       v40,
                       (unsigned __int64 *)&Buf1,
                       PreviousStatea);
  v6 = 0;
  if ( ValueMultiString != -2147024894 )
    v6 = ValueMultiString;
  if ( v6 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v11 = 38;
LABEL_18:
      WPP_SF_d(*(_QWORD *)(v10 + 16), v11, &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids, (unsigned int)v6);
      goto LABEL_19;
    }
    goto LABEL_19;
  }
  if ( *(CommonUtil **)v40 == v2 && !memcmp(Buf1, L"SeBackupPrivilege", 2LL * *(_QWORD *)v40) )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      v13 = 39;
LABEL_33:
      WPP_SF_S(*(_QWORD *)(v12 + 16), v13, &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids, &stru_140194C20);
      v12 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v6 = CommonUtil::UtilRegSetValue(
           (CommonUtil *)hKey,
           (HKEY)&stru_1401950E8,
           (const wchar_t *)7,
           2 * (int)v2,
           (unsigned __int64)L"SeBackupPrivilege",
           ReturnLength);
    if ( v6 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v11 = 40;
        goto LABEL_18;
      }
LABEL_19:
      if ( Buf1 )
        operator delete(Buf1, v9);
      goto LABEL_9;
    }
    v12 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      v13 = 41;
      goto LABEL_33;
    }
  }
  if ( Buf1 )
  {
    operator delete(Buf1, v9);
    v12 = WPP_GLOBAL_Control;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
LABEL_38:
    v12 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v12 != &WPP_GLOBAL_Control && (*(_BYTE *)(v12 + 28) & 4) != 0 )
    WPP_SF_d(*(_QWORD *)(v12 + 16), 42, &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids, v4);
  hObject = 0;
  CurrentProcess = (void **)GetCurrentProcess();
  v16 = CommonUtil::UtilOpenProcessToken((CommonUtil *)&hObject, CurrentProcess, (void *)0x28, v15);
  v6 = v16;
  if ( v16 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        43,
        &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
        (unsigned int)v16);
LABEL_46:
    if ( hObject )
      CloseHandle(hObject);
    return (unsigned int)v6;
  }
  NewState = 0;
  TokenInformationImpl = CommonUtil::UtilGetTokenInformationImpl(
                           (CommonUtil *)&NewState,
                           (void **)hObject,
                           (void *)3,
                           v17);
  v6 = TokenInformationImpl;
  if ( TokenInformationImpl < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        44,
        &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
        (unsigned int)TokenInformationImpl);
LABEL_52:
    if ( NewState )
      operator delete(NewState, (const struct std::nothrow_t *)0x10);
    goto LABEL_46;
  }
  v20 = 0;
  v21 = (void **)(8LL * v4);
  Buf1 = 0;
  if ( (unsigned __int64)v21 < 8 )
  {
    v6 = -2147024809;
    goto LABEL_58;
  }
  _mm_lfence();
  v6 = CommonUtil::MpNewAlloc((CommonUtil *)&Buf1, v21, v19);
  if ( v6 < 0 )
  {
    v20 = Buf1;
LABEL_58:
    if ( v20 )
      operator delete(v20, (const struct std::nothrow_t *)8);
    goto LABEL_52;
  }
  v41 = 0;
  CommonUtil::CMultiStringIterator::CMultiStringIterator(
    (CommonUtil::CMultiStringIterator *)&v41,
    (unsigned __int64)v2,
    L"SeBackupPrivilege");
  v22 = (struct _LUID *)Buf1;
  v23 = 0;
  if ( v4 )
  {
    while ( 1 )
    {
      v24 = CommonUtil::CMultiStringIterator::EnumString((CommonUtil::CMultiStringIterator *)&v41);
      if ( !v24 )
      {
        if ( v22 )
          operator delete(v22, (const struct std::nothrow_t *)8);
        if ( NewState )
          operator delete(NewState, (const struct std::nothrow_t *)0x10);
        if ( hObject )
          CloseHandle(hObject);
        return 2147500037LL;
      }
      if ( !LookupPrivilegeValueW(0, v24, &v22[v23]) && (unsigned int)HrGetLastFailure() != -2147023583 )
        break;
      v23 = (unsigned int)(v23 + 1);
      if ( (unsigned int)v23 >= v4 )
        goto LABEL_65;
    }
    LastFailure = HrGetLastFailure();
    v31 = LastFailure;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        45,
        &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
        LastFailure);
    if ( !v22 )
      goto LABEL_82;
LABEL_81:
    operator delete(v22, (const struct std::nothrow_t *)8);
LABEL_82:
    if ( NewState )
      operator delete(NewState, (const struct std::nothrow_t *)0x10);
    if ( hObject )
      CloseHandle(hObject);
    return v31;
  }
LABEL_65:
  v25 = NewState;
  v26 = 0;
  v27 = 0;
  for ( i = 0; (unsigned int)i < NewState->PrivilegeCount; i = (unsigned int)(i + 1) )
  {
    v29 = 0;
    if ( v4 )
    {
      while ( *(_QWORD *)&v25->Privileges[i].Luid != *(_QWORD *)&v22[v29] )
      {
        v29 = (unsigned int)(v29 + 1);
        if ( (unsigned int)v29 >= v4 )
          goto LABEL_69;
      }
      v25->Privileges[i].Attributes = 2;
      ++v26;
    }
    else
    {
LABEL_69:
      ++v27;
      v25->Privileges[i].Attributes = 4;
    }
    v25 = NewState;
  }
  if ( !AdjustTokenPrivileges(hObject, 0, v25, 0, 0, 0) )
  {
    v30 = HrGetLastFailure();
    v31 = v30;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 46, &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids, v30);
    if ( !v22 )
      goto LABEL_82;
    goto LABEL_81;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_Dd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 47, &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids, v26, v27);
  if ( v22 )
    operator delete(v22, (const struct std::nothrow_t *)8);
  if ( NewState )
    operator delete(NewState, (const struct std::nothrow_t *)0x10);
  if ( hObject )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x140088000  mov     rax, rsp
0x140088003  mov     [rax+8], rbx
0x140088007  mov     [rax+10h], rsi
0x14008800b  mov     [rax+18h], rdi
0x14008800f  mov     [rax+20h], r12
0x140088013  push    rbp
0x140088014  push    r13
0x140088016  push    r14
0x140088018  mov     rbp, rsp
0x14008801b  sub     rsp, 70h
0x14008801f  mov     rax, cs:__security_cookie
0x140088026  xor     rax, rsp
0x140088029  mov     [rbp+var_8], rax
0x14008802d  lea     rbx, aSebackupprivil; "SeBackupPrivilege"
0x140088034  mov     rcx, rbx; this
0x140088037  call    ?UtilRegMultiStringLen@CommonUtil@@YA_KPEB_W@Z; CommonUtil::UtilRegMultiStringLen(wchar_t const *)
0x14008803c  mov     rdx, rbx; unsigned __int64
0x14008803f  mov     rcx, rax; this
0x140088042  mov     rdi, rax
0x140088045  call    ?UtilRegMultiStringCount@CommonUtil@@YA_K_KPEB_W@Z; CommonUtil::UtilRegMultiStringCount(unsigned __int64,wchar_t const *)
0x14008804a  mov     r14, rax
0x14008804d  call    MpIsWindowsRedstoneOrGreater
0x140088052  lea     r12, WPP_GLOBAL_Control
0x140088059  lea     r13, WPP_015d1d1aad8334bf574fd190c463be63_Traceguids
0x140088060  test    eax, eax
0x140088062  jz      loc_14008823D
0x140088068  mov     rcx, cs:WPP_GLOBAL_Control
0x14008806f  lea     rsi, stru_140194C20
0x140088076  cmp     rcx, r12
0x140088079  jz      short loc_140088095
0x14008807b  test    byte ptr [rcx+1Ch], 4
0x14008807f  jz      short loc_140088095
0x140088081  mov     rcx, [rcx+10h]
0x140088085  mov     edx, 24h ; '$'
0x14008808a  mov     r9, rsi
0x14008808d  mov     r8, r13
0x140088090  call    WPP_SF_S
0x140088095  mov     r9d, 2001Fh; wchar_t *
0x14008809b  mov     [rbp+hKey], 0
0x1400880a3  mov     r8, rsi; HKEY
0x1400880a6  lea     rcx, [rbp+hKey]; this
0x1400880aa  mov     rdx, 0FFFFFFFF80000002h; HKEY *
0x1400880b1  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)
0x1400880b6  mov     ebx, eax
0x1400880b8  test    eax, eax
0x1400880ba  jns     short loc_1400880FC
0x1400880bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400880c3  cmp     rcx, r12
0x1400880c6  jz      short loc_1400880E6
0x1400880c8  test    byte ptr [rcx+1Ch], 1
0x1400880cc  jz      short loc_1400880E6
0x1400880ce  mov     rcx, [rcx+10h]
0x1400880d2  mov     edx, 25h ; '%'
0x1400880d7  mov     r9, rsi
0x1400880da  mov     dword ptr [rsp+70h+PreviousState], eax
0x1400880de  mov     r8, r13
0x1400880e1  call    WPP_SF_Sd
0x1400880e6  mov     rcx, [rbp+hKey]; hKey
0x1400880ea  test    rcx, rcx
0x1400880ed  jz      short loc_1400880F5
0x1400880ef  call    cs:__imp_RegCloseKey
0x1400880f5  mov     eax, ebx
0x1400880f7  jmp     loc_140088596
0x1400880fc  mov     rcx, [rbp+hKey]; this
0x140088100  lea     r9, [rbp+Buf1]; unsigned __int64 *
0x140088104  lea     r8, [rbp+var_20]; wchar_t *
0x140088108  mov     [rbp+Buf1], 0
0x140088110  lea     rdx, stru_1401950E8; HKEY
0x140088117  mov     qword ptr [rbp+var_20], 0
0x14008811f  call    ?UtilRegGetValueMultiString@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEA_KPEAPEA_W@Z; CommonUtil::UtilRegGetValueMultiString(HKEY__ *,wchar_t const *,unsigned __int64 *,wchar_t * *)
0x140088124  xor     ebx, ebx
0x140088126  cmp     eax, 80070002h
0x14008812b  cmovnz  ebx, eax
0x14008812e  test    ebx, ebx
0x140088130  jns     short loc_14008816B
0x140088132  mov     rcx, cs:WPP_GLOBAL_Control
0x140088139  cmp     rcx, r12
0x14008813c  jz      short loc_140088158
0x14008813e  test    byte ptr [rcx+1Ch], 1
0x140088142  jz      short loc_140088158
0x140088144  mov     edx, 26h ; '&'
0x140088149  mov     rcx, [rcx+10h]
0x14008814d  mov     r9d, ebx
0x140088150  mov     r8, r13
0x140088153  call    WPP_SF_d
0x140088158  mov     rcx, [rbp+Buf1]; void *
0x14008815c  test    rcx, rcx
0x14008815f  jz      short loc_1400880E6
0x140088161  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140088166  jmp     loc_1400880E6
0x14008816b  mov     r8, qword ptr [rbp+var_20]
0x14008816f  lea     rbx, aSebackupprivil; "SeBackupPrivilege"
0x140088176  cmp     r8, rdi
0x140088179  jnz     short loc_1400881A7
0x14008817b  mov     rcx, [rbp+Buf1]; Buf1
0x14008817f  add     r8, r8; Size
0x140088182  mov     rdx, rbx; Buf2
0x140088185  call    memcmp
0x14008818a  test    eax, eax
0x14008818c  jnz     short loc_1400881A7
0x14008818e  mov     rax, cs:WPP_GLOBAL_Control
0x140088195  cmp     rax, r12
0x140088198  jz      short loc_140088219
0x14008819a  test    byte ptr [rax+1Ch], 4
0x14008819e  jz      short loc_140088219
0x1400881a0  mov     edx, 27h ; '''
0x1400881a5  jmp     short loc_140088203
0x1400881a7  mov     rcx, [rbp+hKey]; this
0x1400881ab  lea     r9, [rdi+rdi]; unsigned int
0x1400881af  mov     r8d, 7; wchar_t *
0x1400881b5  mov     [rsp+70h+PreviousState], rbx; unsigned __int64
0x1400881ba  lea     rdx, stru_1401950E8; HKEY
0x1400881c1  call    ?UtilRegSetValue@CommonUtil@@YAJPEAUHKEY__@@PEB_WK_KPEBX@Z; CommonUtil::UtilRegSetValue(HKEY__ *,wchar_t const *,ulong,unsigned __int64,void const *)
0x1400881c6  mov     ebx, eax
0x1400881c8  test    eax, eax
0x1400881ca  jns     short loc_1400881EC
0x1400881cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400881d3  cmp     rcx, r12
0x1400881d6  jz      short loc_140088158
0x1400881d8  test    byte ptr [rcx+1Ch], 1
0x1400881dc  jz      loc_140088158
0x1400881e2  mov     edx, 28h ; '('
0x1400881e7  jmp     loc_140088149
0x1400881ec  mov     rax, cs:WPP_GLOBAL_Control
0x1400881f3  cmp     rax, r12
0x1400881f6  jz      short loc_140088219
0x1400881f8  test    byte ptr [rax+1Ch], 4
0x1400881fc  jz      short loc_140088219
0x1400881fe  mov     edx, 29h ; ')'
0x140088203  mov     rcx, [rax+10h]
0x140088207  mov     r9, rsi
0x14008820a  mov     r8, r13
0x14008820d  call    WPP_SF_S
0x140088212  mov     rax, cs:WPP_GLOBAL_Control
0x140088219  mov     rcx, [rbp+Buf1]; void *
0x14008821d  test    rcx, rcx
0x140088220  jz      short loc_14008822E
0x140088222  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140088227  mov     rax, cs:WPP_GLOBAL_Control
0x14008822e  mov     rcx, [rbp+hKey]; hKey
0x140088232  test    rcx, rcx
0x140088235  jz      short loc_140088244
0x140088237  call    cs:__imp_RegCloseKey
0x14008823d  mov     rax, cs:WPP_GLOBAL_Control
0x140088244  cmp     rax, r12
0x140088247  jz      short loc_140088263
0x140088249  test    byte ptr [rax+1Ch], 4
0x14008824d  jz      short loc_140088263
0x14008824f  mov     rcx, [rax+10h]
0x140088253  mov     edx, 2Ah ; '*'
0x140088258  mov     r9d, r14d
0x14008825b  mov     r8, r13
0x14008825e  call    WPP_SF_d
0x140088263  mov     [rbp+hObject], 0
0x14008826b  call    cs:__imp_GetCurrentProcess
0x140088271  mov     rcx, [rbp+hObject]; hObject
0x140088275  mov     rbx, rax
0x140088278  test    rcx, rcx
0x14008827b  jz      short loc_140088283
0x14008827d  call    cs:__imp_CloseHandle
0x140088283  mov     r8d, 28h ; '('; void *
0x140088289  lea     rcx, [rbp+hObject]; this
0x14008828d  mov     rdx, rbx; void **
0x140088290  call    ?UtilOpenProcessToken@CommonUtil@@YAJPEAPEAXPEAXK@Z; CommonUtil::UtilOpenProcessToken(void * *,void *,ulong)
0x140088295  mov     ebx, eax
0x140088297  test    eax, eax
0x140088299  jns     short loc_1400882D9
0x14008829b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400882a2  cmp     rcx, r12
0x1400882a5  jz      short loc_1400882C1
0x1400882a7  test    byte ptr [rcx+1Ch], 1
0x1400882ab  jz      short loc_1400882C1
0x1400882ad  mov     rcx, [rcx+10h]
0x1400882b1  mov     edx, 2Bh ; '+'
0x1400882b6  mov     r9d, eax
0x1400882b9  mov     r8, r13
0x1400882bc  call    WPP_SF_d
0x1400882c1  mov     rcx, [rbp+hObject]; hObject
0x1400882c5  test    rcx, rcx
0x1400882c8  jz      loc_1400880F5
0x1400882ce  call    cs:__imp_CloseHandle
0x1400882d4  jmp     loc_1400880F5
0x1400882d9  mov     rdx, [rbp+hObject]; void **
0x1400882dd  lea     rcx, [rbp+NewState]; this
0x1400882e1  mov     r8d, 3; void *
0x1400882e7  mov     [rbp+NewState], 0
0x1400882ef  call    ?UtilGetTokenInformationImpl@CommonUtil@@YAJPEAPEAXPEAXW4_TOKEN_INFORMATION_CLASS@@@Z; CommonUtil::UtilGetTokenInformationImpl(void * *,void *,_TOKEN_INFORMATION_CLASS)
0x1400882f4  mov     ebx, eax
0x1400882f6  test    eax, eax
0x1400882f8  jns     short loc_140088335
0x1400882fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140088301  cmp     rcx, r12
0x140088304  jz      short loc_140088320
0x140088306  test    byte ptr [rcx+1Ch], 1
0x14008830a  jz      short loc_140088320
0x14008830c  mov     rcx, [rcx+10h]
0x140088310  mov     edx, 2Ch ; ','
0x140088315  mov     r9d, eax
0x140088318  mov     r8, r13
0x14008831b  call    WPP_SF_d
0x140088320  mov     rcx, [rbp+NewState]; void *
0x140088324  test    rcx, rcx
0x140088327  jz      short loc_1400882C1
0x140088329  mov     edx, 10h; struct std::nothrow_t *
0x14008832e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140088333  jmp     short loc_1400882C1
0x140088335  xor     ecx, ecx
0x140088337  mov     edx, r14d
0x14008833a  shl     rdx, 3; void **
0x14008833e  mov     [rbp+Buf1], rcx
0x140088342  lea     esi, [rcx+8]
0x140088345  cmp     rdx, rsi
0x140088348  jnb     short loc_140088351
0x14008834a  mov     ebx, 80070057h
0x14008834f  jmp     short loc_140088367
0x140088351  lfence
0x140088354  lea     rcx, [rbp+Buf1]; this
0x140088358  call    ?MpNewAlloc@CommonUtil@@YAJPEAPEAX_K@Z; CommonUtil::MpNewAlloc(void * *,unsigned __int64)
0x14008835d  mov     ebx, eax
0x14008835f  test    eax, eax
0x140088361  jns     short loc_140088376
0x140088363  mov     rcx, [rbp+Buf1]; void *
0x140088367  test    rcx, rcx
0x14008836a  jz      short loc_140088320
0x14008836c  mov     rdx, rsi; struct std::nothrow_t *
0x14008836f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140088374  jmp     short loc_140088320
0x140088376  xorps   xmm0, xmm0
0x140088379  lea     r8, aSebackupprivil; "SeBackupPrivilege"
0x140088380  mov     rdx, rdi; unsigned __int64
0x140088383  lea     rcx, [rbp+var_18]; this
0x140088387  movups  [rbp+var_18], xmm0
0x14008838b  call    ??0CMultiStringIterator@CommonUtil@@QEAA@_KPEB_W@Z; CommonUtil::CMultiStringIterator::CMultiStringIterator(unsigned __int64,wchar_t const *)
0x140088390  mov     rbx, [rbp+Buf1]
0x140088394  xor     edi, edi
0x140088396  test    r14d, r14d
0x140088399  jz      short loc_1400883D7
0x14008839b  lea     rcx, [rbp+var_18]; this
0x14008839f  call    ?EnumString@CMultiStringIterator@CommonUtil@@QEAAPEB_WXZ; CommonUtil::CMultiStringIterator::EnumString(void)
0x1400883a4  test    rax, rax
0x1400883a7  jz      loc_1400884ED
0x1400883ad  lea     r8, [rbx+rdi*8]; lpLuid
0x1400883b1  mov     rdx, rax; lpName
0x1400883b4  xor     ecx, ecx; lpSystemName
0x1400883b6  call    cs:__imp_LookupPrivilegeValueW
0x1400883bc  test    eax, eax
0x1400883be  jnz     short loc_1400883D0
0x1400883c0  call    HrGetLastFailure
0x1400883c5  cmp     eax, 80070521h
0x1400883ca  jnz     loc_140088487
0x1400883d0  inc     edi
0x1400883d2  cmp     edi, r14d
0x1400883d5  jb      short loc_14008839B
0x1400883d7  mov     r8, [rbp+NewState]
0x1400883db  xor     edi, edi
0x1400883dd  xor     esi, esi
0x1400883df  xor     r9d, r9d
0x1400883e2  cmp     [r8], esi
0x1400883e5  jbe     short loc_140088425
0x1400883e7  xor     r10d, r10d
0x1400883ea  test    r14d, r14d
0x1400883ed  jz      short loc_14008840A
0x1400883ef  lea     r11, [r9+r9*2]
0x1400883f3  mov     rax, [r8+r11*4+4]
0x1400883f8  cmp     rax, [rbx+r10*8]
0x1400883fc  jz      loc_140088526
0x140088402  inc     r10d
0x140088405  cmp     r10d, r14d
0x140088408  jb      short loc_1400883F3
0x14008840a  lea     rax, [r9+r9*2]
0x14008840e  inc     esi
0x140088410  mov     dword ptr [r8+rax*4+0Ch], 4
0x140088419  mov     r8, [rbp+NewState]; NewState
0x14008841d  inc     r9d
0x140088420  cmp     r9d, [r8]
0x140088423  jb      short loc_1400883E7
0x140088425  mov     rcx, [rbp+hObject]; TokenHandle
0x140088429  xor     r9d, r9d; BufferLength
0x14008842c  mov     [rsp+70h+ReturnLength], 0; ReturnLength
0x140088435  xor     edx, edx; DisableAllPrivileges
0x140088437  mov     [rsp+70h+PreviousState], 0; PreviousState
0x140088440  call    cs:__imp_AdjustTokenPrivileges
0x140088446  test    eax, eax
0x140088448  jnz     loc_140088536
0x14008844e  call    HrGetLastFailure
0x140088453  mov     edi, eax
0x140088455  mov     rcx, cs:WPP_GLOBAL_Control
0x14008845c  cmp     rcx, r12
0x14008845f  jz      short loc_14008847B
0x140088461  test    byte ptr [rcx+1Ch], 1
0x140088465  jz      short loc_14008847B
0x140088467  mov     rcx, [rcx+10h]
0x14008846b  mov     edx, 2Eh ; '.'
0x140088470  mov     r9d, eax
0x140088473  mov     r8, r13
0x140088476  call    WPP_SF_d
0x14008847b  test    rbx, rbx
0x14008847e  jz      short loc_1400884C4
0x140088480  mov     edx, 8
0x140088485  jmp     short loc_1400884BC
  ... truncated ...
```
