# Windows::Usage::GetUserDisplayState(void)

- ea: `0x180055614`
- end: `0x180055a60`
- name: `?GetUserDisplayState@Usage@Windows@@AEBA?AW4DisplayState@12@XZ`
- size: `1100`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180055580`
- `0x180055c00`
- `0x180055c20`
- `0x180055c40`

## callees

- `0x180007660`
- `0x180013ccc`
- `0x180019e48`
- `0x18001ba70`
- `0x18001ee04`
- `0x18001ee70`
- `0x1800209fc`
- `0x18002183c`
- `0x180023a18`
- `0x180025cd0`
- `0x18002778c`
- `0x18003ef60`
- `0x180045bd4`
- `0x180055614`
- `0x180056f30`
- `0x1800672b4`
- `0x180067360`
- `0x1800677a4`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180055862`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180055862`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180055893`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180055893`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800558d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800558f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055920`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055934`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800558d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800558f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055920`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055934`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180055669`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180055669`
- `ext-ms-win-shell-shell32-l1-2-0!SHQueryUserNotificationState` at `0x180055949`
- `ext-ms-win-shell-shell32-l1-2-0!SHQueryUserNotificationState` at `0x180055949`

## string_xrefs

- `0x1800559c0`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\usage.cpp`
- `0x1800559e3`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\usage.cpp`
- `0x180055a14`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\usage.cpp`
- `0x180055a26`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\usage.cpp`
- `0x180055a38`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\usage.cpp`

## pseudocode

```c
__int64 Windows::Usage::GetUserDisplayState()
{
  char IsSidInToken; // bl
  _QWORD *System; // rax
  __int64 v2; // rax
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, _BYTE *, _OWORD *); // rbx
  _QWORD *v5; // rax
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  volatile signed __int32 *v9; // rbx
  volatile signed __int32 *v10; // rbx
  __int128 *v11; // r9
  __int128 *v12; // rdx
  DWORD v13; // eax
  unsigned int v14; // r8d
  const char *v15; // r9
  const char *v16; // r9
  DWORD v17; // ebx
  const char *v18; // r9
  unsigned int v19; // r8d
  const char *v20; // r9
  unsigned int v21; // r8d
  const char *v22; // r9
  HRESULT v24; // eax
  _QWORD *v25; // rax
  _BYTE *v26; // rcx
  unsigned int v27; // eax
  int v28; // [rsp+20h] [rbp-E0h]
  unsigned int v29; // [rsp+20h] [rbp-E0h]
  DWORD ExitCode[2]; // [rsp+40h] [rbp-C0h] BYREF
  PSID pSid; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hHandle; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-A8h]
  __int128 v34; // [rsp+68h] [rbp-98h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h]
  __int64 v36; // [rsp+80h] [rbp-80h]
  _QWORD *v37; // [rsp+88h] [rbp-78h]
  _BYTE v38[8]; // [rsp+98h] [rbp-68h] BYREF
  volatile signed __int32 *v39; // [rsp+A0h] [rbp-60h]
  _BYTE v40[8]; // [rsp+A8h] [rbp-58h] BYREF
  volatile signed __int32 *v41; // [rsp+B0h] [rbp-50h]
  _QWORD v42[4]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v43; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v44[2]; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v45; // [rsp+F0h] [rbp-10h]
  _OWORD v46[2]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v47[32]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  *(_QWORD *)ExitCode = 0;
  Windows::Trust::CreateSid(&pSid);
  IsSidInToken = Windows::Trust::IsSidInToken(ExitCode, &pSid);
  if ( pSid )
    FreeSid(pSid);
  if ( !IsSidInToken )
  {
    ExitCode[0] = 5;
    v24 = SHQueryUserNotificationState((QUERY_USER_NOTIFICATION_STATE *)ExitCode);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x142,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\usage.cpp",
        (const char *)(unsigned int)v24,
        v28);
    v25 = (_QWORD *)*((_QWORD *)qword_180096BD8 + 1);
    HIDWORD(hObject) = 0;
    v26 = qword_180096BD8;
    while ( !*((_BYTE *)v25 + 25) )
    {
      if ( *((_DWORD *)v25 + 7) >= (int)ExitCode[0] )
        v26 = v25;
      else
        v25 += 2;
      v25 = (_QWORD *)*v25;
    }
    if ( v26[25] || (int)ExitCode[0] < *((_DWORD *)v26 + 7) )
      v26 = qword_180096BD8;
    if ( v26 != qword_180096BD8 )
      return *((unsigned int *)v26 + 8);
    return 0;
  }
  Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(&pSid);
  if ( (char *)pSid - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    return 0;
  System = (_QWORD *)SystemInterface::Service::GetSystem(v40);
  v2 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*System + 8LL))(*System, v38);
  v3 = *(_QWORD *)v2;
  v4 = *(__int64 (__fastcall **)(__int64, _BYTE *, _OWORD *))(**(_QWORD **)v2 + 16LL);
  memset(v46, 0, sizeof(v46));
  std::wstring::_Construct<1,unsigned short const *>(v46, L"DisplayCheck", 12);
  v5 = (_QWORD *)v4(v3, v47, v46);
  if ( v5[3] > 7u )
    v5 = (_QWORD *)*v5;
  v43 = 0;
  *(_QWORD *)v44 = 0;
  v45 = 0;
  v6 = -1;
  do
    ++v6;
  while ( *((_WORD *)v5 + v6) );
  std::wstring::_Construct<1,unsigned short const *>(&v43, v5, v6);
  std::wstring::_Tidy_deallocate(v47);
  std::wstring::_Tidy_deallocate(v46);
  v9 = v39;
  if ( v39 )
  {
    if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  v10 = v41;
  if ( v41 )
  {
    if ( _InterlockedExchangeAdd(v41 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  v37 = v42;
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - *(_QWORD *)v44) < 0x13 )
    std::_Xlen_string();
  v11 = &v43;
  if ( v45 > 7 )
    v11 = (__int128 *)v43;
  v29 = v44[0];
  std::wstring::wstring(v42, v7, v8, v11);
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v12 = &v43;
  if ( v45 > 7 )
    v12 = (__int128 *)v43;
  std::wstring::_Construct<2,unsigned short const *>(&v34, v12, *(_QWORD *)v44);
  Windows::ProcessHelpers::CreateProcessAsUserToken(&hHandle, &pSid, &v34, v42);
  v13 = WaitForSingleObject(hHandle, 0x7530u);
  if ( v13 )
  {
    if ( v13 != 258 )
    {
      if ( v13 == -1 )
        wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x130, v14, v15);
      v27 = wil::verify_hresult<long>(2147549183LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x134,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\usage.cpp",
        (const char *)v27,
        v29);
    }
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x12C,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\usage.cpp",
      (const char *)0x5B4,
      v29);
  }
  ExitCode[0] = 0;
  if ( !GetExitCodeProcess(hHandle, ExitCode) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\usage.cpp",
      v16);
  v17 = ExitCode[0];
  if ( (int)ExitCode[0] > 0 )
    v18 = (const char *)(LOWORD(ExitCode[0]) | 0x80070000);
  else
    v18 = (const char *)ExitCode[0];
  if ( ExitCode[0] > 3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\usage.cpp",
      v18,
      v29);
  if ( hHandle && !CloseHandle(hHandle) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v19, v20);
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  std::wstring::_Tidy_deallocate(&v43);
  if ( (char *)pSid - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(pSid);
  return v17;
}

```

## disassembly

```asm
0x180055614  push    rbp
0x180055616  push    rbx
0x180055617  push    rsi
0x180055618  push    rdi
0x180055619  lea     rbp, [rsp-48h]
0x18005561e  sub     rsp, 148h
0x180055625  mov     rax, cs:__security_cookie
0x18005562c  xor     rax, rsp
0x18005562f  mov     [rbp+60h+var_28], rax
0x180055633  xor     esi, esi
0x180055635  mov     qword ptr [rsp+160h+ExitCode], rsi
0x18005563a  xor     r9d, r9d
0x18005563d  lea     r8d, [rsi+12h]
0x180055641  mov     dl, 1
0x180055643  lea     rcx, [rsp+160h+pSid]; pSid
0x180055648  call    ?CreateSid@Trust@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@EKK@Z; Windows::Trust::CreateSid(uchar,ulong,ulong)
0x18005564d  nop
0x18005564e  lea     rdx, [rsp+160h+pSid]
0x180055653  lea     rcx, [rsp+160h+ExitCode]
0x180055658  call    ?IsSidInToken@Trust@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@4@@Z; Windows::Trust::IsSidInToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> const &)
0x18005565d  mov     bl, al
0x18005565f  mov     rcx, [rsp+160h+pSid]; pSid
0x180055664  test    rcx, rcx
0x180055667  jz      short loc_180055670
0x180055669  call    cs:__imp_FreeSid
0x18005566f  nop
0x180055670  test    bl, bl
0x180055672  jz      loc_18005593C
0x180055678  lea     rcx, [rsp+160h+pSid]
0x18005567d  call    ?GetMostPreferredLoggedOnSessionToken@CallerToken@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(void)
0x180055682  nop
0x180055683  mov     rcx, [rsp+160h+pSid]; hObject
0x180055688  lea     rax, [rcx-1]
0x18005568c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180055690  ja      loc_18005592A
0x180055696  lea     rcx, [rbp+60h+var_B8]
0x18005569a  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18005569f  nop
0x1800556a0  mov     rcx, [rax]
0x1800556a3  mov     rax, [rcx]
0x1800556a6  lea     rdx, [rbp+60h+var_C8]
0x1800556aa  mov     rax, [rax+8]
0x1800556ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800556b3  nop
0x1800556b4  mov     rdi, [rax]
0x1800556b7  mov     rax, [rdi]
0x1800556ba  mov     rbx, [rax+10h]
0x1800556be  xorps   xmm0, xmm0
0x1800556c1  movups  [rbp+60h+var_68], xmm0
0x1800556c5  xorps   xmm1, xmm1
0x1800556c8  movdqu  [rbp+60h+var_58], xmm1
0x1800556cd  mov     r8d, 0Ch
0x1800556d3  lea     rdx, aDisplaycheck; "DisplayCheck"
0x1800556da  lea     rcx, [rbp+60h+var_68]
0x1800556de  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800556e3  nop
0x1800556e4  lea     r8, [rbp+60h+var_68]
0x1800556e8  lea     rdx, [rbp+60h+var_48]
0x1800556ec  mov     rcx, rdi
0x1800556ef  mov     rax, rbx
0x1800556f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800556f7  nop
0x1800556f8  cmp     qword ptr [rax+18h], 7
0x1800556fd  jbe     short loc_180055702
0x1800556ff  mov     rax, [rax]
0x180055702  xorps   xmm0, xmm0
0x180055705  movups  [rbp+60h+var_88], xmm0
0x180055709  mov     qword ptr [rbp+60h+var_78], rsi
0x18005570d  mov     [rbp+60h+var_70], rsi
0x180055711  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180055715  mov     r8, rdi
0x180055718  inc     r8
0x18005571b  cmp     [rax+r8*2], si
0x180055720  jnz     short loc_180055718
0x180055722  mov     rdx, rax
0x180055725  lea     rcx, [rbp+60h+var_88]
0x180055729  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005572e  nop
0x18005572f  lea     rcx, [rbp+60h+var_48]
0x180055733  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180055738  nop
0x180055739  lea     rcx, [rbp+60h+var_68]
0x18005573d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180055742  nop
0x180055743  mov     rbx, [rbp+60h+var_C0]
0x180055747  test    rbx, rbx
0x18005574a  jz      short loc_180055780
0x18005574c  mov     eax, edi
0x18005574e  lock xadd [rbx+8], eax
0x180055753  add     eax, edi
0x180055755  jnz     short loc_180055780
0x180055757  mov     rax, [rbx]
0x18005575a  mov     rcx, rbx
0x18005575d  mov     rax, [rax]
0x180055760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055765  mov     eax, edi
0x180055767  lock xadd [rbx+0Ch], eax
0x18005576c  add     eax, edi
0x18005576e  jnz     short loc_180055780
0x180055770  mov     rax, [rbx]
0x180055773  mov     rcx, rbx
0x180055776  mov     rax, [rax+8]
0x18005577a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005577f  nop
0x180055780  mov     rbx, [rbp+60h+var_B0]
0x180055784  test    rbx, rbx
0x180055787  jz      short loc_1800557BC
0x180055789  mov     eax, edi
0x18005578b  lock xadd [rbx+8], eax
0x180055790  add     eax, edi
0x180055792  jnz     short loc_1800557BC
0x180055794  mov     rax, [rbx]
0x180055797  mov     rcx, rbx
0x18005579a  mov     rax, [rax]
0x18005579d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800557a2  mov     eax, edi
0x1800557a4  lock xadd [rbx+0Ch], eax
0x1800557a9  add     eax, edi
0x1800557ab  jnz     short loc_1800557BC
0x1800557ad  mov     rax, [rbx]
0x1800557b0  mov     rcx, rbx
0x1800557b3  mov     rax, [rax+8]
0x1800557b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800557bc  lea     rax, [rbp+60h+var_A8]
0x1800557c0  mov     [rbp+60h+var_D8], rax
0x1800557c4  mov     rcx, qword ptr [rbp+60h+var_78]
0x1800557c8  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800557d2  sub     rax, rcx
0x1800557d5  cmp     rax, 13h
0x1800557d9  jb      loc_1800559F5
0x1800557df  lea     r9, [rbp+60h+var_88]
0x1800557e3  cmp     [rbp+60h+var_70], 7
0x1800557e8  cmova   r9, qword ptr [rbp+60h+var_88]
0x1800557ed  mov     [rsp+160h+var_130], 13h
0x1800557f6  lea     rax, aNotificationst; " /NotificationState"
0x1800557fd  mov     [rsp+160h+var_138], rax
0x180055802  mov     qword ptr [rsp+160h+var_140], rcx; int
0x180055807  lea     rcx, [rbp+60h+var_A8]
0x18005580b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180055810  nop
0x180055811  xorps   xmm0, xmm0
0x180055814  movups  [rsp+160h+var_F8], xmm0
0x180055819  mov     [rsp+160h+var_E8], rsi
0x18005581e  mov     [rbp+60h+var_E0], rsi
0x180055822  lea     rdx, [rbp+60h+var_88]
0x180055826  cmp     [rbp+60h+var_70], 7
0x18005582b  cmova   rdx, qword ptr [rbp+60h+var_88]
0x180055830  mov     r8, qword ptr [rbp+60h+var_78]
0x180055834  lea     rcx, [rsp+160h+var_F8]
0x180055839  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18005583e  nop
0x18005583f  lea     r9, [rbp+60h+var_A8]
0x180055843  lea     r8, [rsp+160h+var_F8]
0x180055848  lea     rdx, [rsp+160h+pSid]
0x18005584d  lea     rcx, [rsp+160h+hHandle]; lpTargetHandle
0x180055852  call    ?CreateProcessAsUserToken@ProcessHelpers@Windows@@YA?AV?$unique_struct@U_PROCESS_INFORMATION@@P6AXPEAU1@@Z$1?CloseProcessInformation@details@wil@@YAX0@Z$$T$0A@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@4@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::ProcessHelpers::CreateProcessAsUserToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,std::wstring,std::wstring)
0x180055857  nop
0x180055858  mov     edx, 7530h; dwMilliseconds
0x18005585d  mov     rcx, [rsp+160h+hHandle]; hHandle
0x180055862  call    cs:__imp_WaitForSingleObject
0x180055868  test    eax, eax
0x18005586a  jz      short loc_180055885
0x18005586c  cmp     eax, 102h
0x180055871  jz      loc_180055A0A
0x180055877  cmp     eax, 0FFFFFFFFh
0x18005587a  jnz     loc_1800559D2
0x180055880  jmp     loc_1800559FB
0x180055885  mov     [rsp+160h+ExitCode], esi
0x180055889  lea     rdx, [rsp+160h+ExitCode]; lpExitCode
0x18005588e  mov     rcx, [rsp+160h+hHandle]; hProcess
0x180055893  call    cs:__imp_GetExitCodeProcess
0x180055899  mov     rcx, [rbp+68h]; this
0x18005589d  test    eax, eax
0x18005589f  jz      loc_180055A26
0x1800558a5  mov     ebx, [rsp+160h+ExitCode]
0x1800558a9  cmp     ebx, 3
0x1800558ac  setnbe  al
0x1800558af  test    ebx, ebx
0x1800558b1  jg      short loc_1800558B8
0x1800558b3  mov     r9d, ebx
0x1800558b6  jmp     short loc_1800558C3
0x1800558b8  movzx   r9d, bx
0x1800558bc  or      r9d, 80070000h; char *
0x1800558c3  mov     rcx, [rbp+68h]; this
0x1800558c7  test    al, al
0x1800558c9  jnz     loc_180055A38
0x1800558cf  mov     rcx, [rsp+160h+hHandle]; hObject
0x1800558d4  test    rcx, rcx
0x1800558d7  jz      short loc_1800558EB
0x1800558d9  call    cs:__imp_CloseHandle
0x1800558df  mov     rcx, [rbp+68h]; this
0x1800558e3  test    eax, eax
0x1800558e5  jz      loc_180055A4A
0x1800558eb  mov     rcx, [rsp+160h+hObject]; hObject
0x1800558f0  test    rcx, rcx
0x1800558f3  jz      short loc_180055907
0x1800558f5  call    cs:__imp_CloseHandle
0x1800558fb  mov     rcx, [rbp+68h]; this
0x1800558ff  test    eax, eax
0x180055901  jz      loc_180055A55
0x180055907  lea     rcx, [rbp+60h+var_88]
0x18005590b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180055910  nop
0x180055911  mov     rcx, [rsp+160h+pSid]; hObject
0x180055916  lea     rdx, [rcx-1]
0x18005591a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005591e  ja      short loc_180055926
0x180055920  call    cs:__imp_CloseHandle
0x180055926  mov     eax, ebx
0x180055928  jmp     short loc_1800559A1
0x18005592a  lea     rax, [rcx-1]
0x18005592e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180055932  ja      short loc_18005599A
0x180055934  call    cs:__imp_CloseHandle
0x18005593a  jmp     short loc_18005599A
0x18005593c  mov     [rsp+160h+ExitCode], 5
0x180055944  lea     rcx, [rsp+160h+ExitCode]; pquns
0x180055949  call    cs:__imp_SHQueryUserNotificationState
0x18005594f  test    eax, eax
0x180055951  js      short loc_1800559B9
0x180055953  mov     rdx, cs:qword_180096BD8
0x18005595a  mov     rax, [rdx+8]
0x18005595e  xor     ecx, ecx
0x180055960  mov     dword ptr [rsp+160h+hObject+4], ecx
0x180055964  mov     rcx, rdx
0x180055967  mov     r8d, [rsp+160h+ExitCode]
0x18005596c  jmp     short loc_180055980
0x18005596e  cmp     [rax+1Ch], r8d
0x180055972  jge     short loc_18005597A
0x180055974  add     rax, 10h
0x180055978  jmp     short loc_18005597D
0x18005597a  mov     rcx, rax
0x18005597d  mov     rax, [rax]
0x180055980  cmp     [rax+19h], sil
0x180055984  jz      short loc_18005596E
0x180055986  cmp     [rcx+19h], sil
0x18005598a  jnz     short loc_180055992
0x18005598c  cmp     r8d, [rcx+1Ch]
0x180055990  jge     short loc_180055995
0x180055992  mov     rcx, rdx
0x180055995  cmp     rcx, rdx
0x180055998  jnz     short loc_18005599E
0x18005599a  xor     eax, eax
0x18005599c  jmp     short loc_1800559A1
0x18005599e  mov     eax, [rcx+20h]
0x1800559a1  mov     rcx, [rbp+60h+var_28]
0x1800559a5  xor     rcx, rsp; StackCookie
0x1800559a8  call    __security_check_cookie
0x1800559ad  add     rsp, 148h
0x1800559b4  pop     rdi
0x1800559b5  pop     rsi
0x1800559b6  pop     rbx
0x1800559b7  pop     rbp
0x1800559b8  retn
0x1800559b9  mov     rcx, [rbp+68h]; this
0x1800559bd  mov     r9d, eax; char *
0x1800559c0  lea     r8, aOnecoreEnduser_6; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800559c7  mov     edx, 142h; void *
0x1800559cc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800559d2  mov     ecx, 8000FFFFh
0x1800559d7  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800559dc  mov     r9d, eax; char *
0x1800559df  mov     rcx, [rbp+68h]; this
0x1800559e3  lea     r8, aOnecoreEnduser_6; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800559ea  mov     edx, 134h; void *
0x1800559ef  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800559f5  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x1800559fb  mov     rcx, [rbp+68h]; this
0x1800559ff  mov     edx, 130h; void *
0x180055a04  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180055a0a  mov     rcx, [rbp+68h]; this
0x180055a0e  mov     r9d, 5B4h; char *
0x180055a14  lea     r8, aOnecoreEnduser_6; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180055a1b  mov     edx, 12Ch; void *
0x180055a20  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180055a26  lea     r8, aOnecoreEnduser_6; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180055a2d  mov     edx, 139h; void *
0x180055a32  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180055a38  lea     r8, aOnecoreEnduser_6; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180055a3f  mov     edx, 13Bh; void *
0x180055a44  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180055a4a  mov     edx, 0A0Bh; void *
0x180055a4f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180055a55  mov     edx, 0A0Bh; void *
0x180055a5a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
