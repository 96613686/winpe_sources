# Windows::UO::UOProvider::GetUpdateProvider(void)

- ea: `0x1403151e8`
- end: `0x14031566f`
- name: `?GetUpdateProvider@UOProvider@UO@Windows@@AEBA?AV?$com_ptr_t@UIUpdateOrchestratorUpdateProvider@@Uerr_exception_policy@wil@@@wil@@XZ`
- size: `1159`
- prototype: ``
- caller_count: `5`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140316700`
- `0x1403167a0`
- `0x14031690c`
- `0x140316d10`
- `0x140316d60`

## callees

- `0x14003c578`
- `0x1400413a8`
- `0x140043284`
- `0x140043814`
- `0x140044b18`
- `0x140045404`
- `0x1400c75e4`
- `0x14012d7d8`
- `0x140315058`
- `0x1403151e8`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1403154d4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1403155a3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1403154d4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1403155a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140315553`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1403155c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140315553`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1403155c5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1403155b1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1403155b1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14031555c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14031555c`

## string_xrefs

- `0x14031562a`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOProvider.cpp`
- `0x140315645`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOProvider.cpp`
- `0x14031565d`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
LPVOID *__fastcall Windows::UO::UOProvider::GetUpdateProvider(__int64 a1, LPVOID *a2)
{
  _QWORD *v4; // rsi
  __int64 System; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // r10
  void (__fastcall *v9)(__int64, _QWORD *, __int128 *, _QWORD *, HANDLE *); // r11
  __int64 v10; // rax
  __int128 *p_Src; // rax
  __int64 v12; // rax
  volatile signed __int32 *v13; // rbx
  volatile signed __int32 *v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rcx
  void (__fastcall *v17)(__int64, _QWORD *, __int128 *); // r9
  _QWORD *v18; // rdx
  volatile signed __int32 *v19; // rbx
  LPVOID v20; // rcx
  HRESULT Instance; // eax
  __int64 v22; // rax
  void **AppContainerUserToken; // rax
  char *v24; // rbx
  const char *v25; // r9
  LPVOID v26; // rcx
  HRESULT v27; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  __int128 v31; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v33; // [rsp+60h] [rbp-A0h]
  __int128 v34; // [rsp+70h] [rbp-90h] BYREF
  LPVOID *v35; // [rsp+80h] [rbp-80h]
  _BYTE v36[8]; // [rsp+88h] [rbp-78h] BYREF
  volatile signed __int32 *v37; // [rsp+90h] [rbp-70h]
  _QWORD v38[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 Src; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v40; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v41; // [rsp+C8h] [rbp-38h]
  _QWORD v42[4]; // [rsp+D0h] [rbp-30h] BYREF
  char v43; // [rsp+F0h] [rbp-10h]
  char v44; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v35 = a2;
  v33 = 0;
  Src = 0;
  v40 = 0;
  v41 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&Src, L"\\UScheduler");
  std::wstring::append(&Src);
  v4 = (_QWORD *)(a1 + 136);
  std::wstring::append(&Src);
  System = SystemInterface::Providers::GetSystem(&v34);
  v6 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
  v7 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v6 + 32LL))(v6, v36);
  v8 = *(_QWORD *)v7;
  v9 = *(void (__fastcall **)(__int64, _QWORD *, __int128 *, _QWORD *, HANDLE *))(**(_QWORD **)v7 + 56LL);
  v10 = -1;
  do
    ++v10;
  while ( aUpdatersid[v10] );
  hObject[0] = L"updaterSid";
  hObject[1] = (HANDLE)v10;
  p_Src = &Src;
  if ( v41 > 7 )
    p_Src = (__int128 *)Src;
  v38[0] = p_Src;
  v38[1] = v40;
  *(_QWORD *)&v31 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
  v12 = -1;
  do
    ++v12;
  while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v12] );
  *((_QWORD *)&v31 + 1) = v12;
  v9(v8, v42, &v31, v38, hObject);
  v13 = v37;
  if ( v37 )
  {
    if ( _InterlockedExchangeAdd(v37 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  v14 = (volatile signed __int32 *)*((_QWORD *)&v34 + 1);
  if ( *((_QWORD *)&v34 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v34 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  *a2 = 0;
  v33 = 1;
  v38[0] = 0;
  if ( v44 )
  {
    v15 = SystemInterface::Providers::GetSystem(hObject);
    v16 = *(_QWORD *)v15 + *(int *)(*(_QWORD *)(*(_QWORD *)v15 + 8LL) + 4LL) + 8LL;
    v17 = *(void (__fastcall **)(__int64, _QWORD *, __int128 *))(*(_QWORD *)v16 + 136LL);
    if ( !v44 )
      std::_Throw_bad_optional_access();
    if ( v43 != 2 )
      std::_Throw_bad_variant_access();
    v18 = v42;
    if ( v42[3] > 7u )
      v18 = (_QWORD *)v42[0];
    *(_QWORD *)&v31 = v18;
    *((_QWORD *)&v31 + 1) = v42[2];
    v34 = v31;
    v17(v16, v38, &v34);
    v19 = (volatile signed __int32 *)hObject[1];
    if ( hObject[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)hObject[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    v20 = *a2;
    *a2 = 0;
    if ( v20 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    Instance = CoCreateInstance(
                 (const IID *const)(a1 + 8),
                 0,
                 0x110004u,
                 &GUID_e7b7429d_80c8_4459_98cc_fd065cd778dd,
                 a2);
    if ( Instance < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\UOProvider.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
    if ( v38[0] )
      (**(void (__fastcall ***)(_QWORD, __int64))v38[0])(v38[0], 1);
  }
  else
  {
    v22 = *(_QWORD *)(a1 + 152);
    if ( *(_QWORD *)(a1 + 160) > 7u )
      v4 = (_QWORD *)*v4;
    *(_QWORD *)&v31 = v4;
    *((_QWORD *)&v31 + 1) = v22;
    v34 = v31;
    AppContainerUserToken = (void **)Windows::UO::GetAppContainerUserToken(hObject, &v34);
    v24 = (char *)*AppContainerUserToken;
    *AppContainerUserToken = 0;
    v38[0] = v24;
    if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject[0]);
    if ( !ImpersonateLoggedOnUser(v24) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x58,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\UOProvider.cpp",
        v25);
    v26 = *a2;
    *a2 = 0;
    if ( v26 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
    v27 = CoCreateInstance((const IID *const)(a1 + 8), 0, 0x10004u, &GUID_e7b7429d_80c8_4459_98cc_fd065cd778dd, a2);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\UOProvider.cpp",
        (const char *)(unsigned int)v27,
        ppva);
    RevertToSelf();
    if ( (unsigned __int64)(v24 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v24);
  }
  if ( v44 && v43 != -1 && v43 && v43 != 1 )
    std::wstring::~wstring(v42);
  std::wstring::~wstring(&Src);
  return a2;
}

```

## disassembly

```asm
0x1403151e8  mov     [rsp-8+arg_10], rbx
0x1403151ed  mov     [rsp-8+arg_18], rsi
0x1403151f2  push    rbp
0x1403151f3  push    rdi
0x1403151f4  push    r12
0x1403151f6  push    r14
0x1403151f8  push    r15
0x1403151fa  lea     rbp, [rsp-10h]
0x1403151ff  sub     rsp, 110h
0x140315206  mov     rax, cs:__security_cookie
0x14031520d  xor     rax, rsp
0x140315210  mov     [rbp+30h+var_30], rax
0x140315214  mov     rdi, rdx
0x140315217  mov     r14, rcx
0x14031521a  mov     [rbp+30h+var_B0], rdx
0x14031521e  xor     r15d, r15d
0x140315221  mov     [rsp+130h+var_D0], r15d
0x140315226  xorps   xmm0, xmm0
0x140315229  movups  [rbp+30h+Src], xmm0
0x14031522d  mov     [rbp+30h+var_70], r15
0x140315231  mov     [rbp+30h+var_68], r15
0x140315235  lea     r8d, [r15+0Bh]
0x140315239  lea     rdx, aUscheduler; "\\UScheduler"
0x140315240  lea     rcx, [rbp+30h+Src]
0x140315244  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140315249  nop
0x14031524a  lea     r8d, [r15+1]
0x14031524e  lea     rdx, asc_14041A8E0; "\\"
0x140315255  lea     rcx, [rbp+30h+Src]; Src
0x140315259  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x14031525e  lea     rsi, [r14+88h]
0x140315265  mov     rdx, rsi
0x140315268  cmp     qword ptr [rsi+18h], 7
0x14031526d  jbe     short loc_140315272
0x14031526f  mov     rdx, [rsi]
0x140315272  mov     r8, [rsi+10h]
0x140315276  lea     rcx, [rbp+30h+Src]; Src
0x14031527a  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x14031527f  lea     rcx, [rsp+130h+var_C0]
0x140315284  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x140315289  nop
0x14031528a  mov     rdx, [rax]
0x14031528d  mov     rax, [rdx+8]
0x140315291  movsxd  rcx, dword ptr [rax+4]
0x140315295  add     rdx, 8
0x140315299  add     rcx, rdx
0x14031529c  mov     rax, [rcx]
0x14031529f  lea     rdx, [rbp+30h+var_A8]
0x1403152a3  mov     rax, [rax+20h]
0x1403152a7  call    _guard_dispatch_icall
0x1403152ac  nop
0x1403152ad  mov     r10, [rax]
0x1403152b0  mov     rax, [r10]
0x1403152b3  mov     r11, [rax+38h]
0x1403152b7  mov     rcx, cs:off_14047EA80; "updaterSid"
0x1403152be  or      r12, 0FFFFFFFFFFFFFFFFh
0x1403152c2  mov     rax, r12
0x1403152c5  inc     rax
0x1403152c8  cmp     [rcx+rax*2], r15w
0x1403152cd  jnz     short loc_1403152C5
0x1403152cf  mov     [rsp+130h+hObject], rcx
0x1403152d4  mov     [rsp+130h+hObject+8], rax
0x1403152d9  lea     rax, [rbp+30h+Src]
0x1403152dd  cmp     [rbp+30h+var_68], 7
0x1403152e2  cmova   rax, qword ptr [rbp+30h+Src]
0x1403152e7  mov     qword ptr [rbp+30h+var_90], rax
0x1403152eb  mov     rax, [rbp+30h+var_70]
0x1403152ef  mov     qword ptr [rbp+30h+var_90+8], rax
0x1403152f3  mov     rcx, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x1403152fa  mov     qword ptr [rsp+130h+var_F0], rcx
0x1403152ff  mov     rax, r12
0x140315302  inc     rax
0x140315305  cmp     [rcx+rax*2], r15w
0x14031530a  jnz     short loc_140315302
0x14031530c  mov     qword ptr [rsp+130h+var_F0+8], rax
0x140315311  movups  xmm0, xmmword ptr [rsp+130h+hObject]
0x140315316  movdqu  xmmword ptr [rsp+130h+hObject], xmm0
0x14031531c  movups  xmm1, [rbp+30h+var_90]
0x140315320  movdqu  [rbp+30h+var_90], xmm1
0x140315325  movaps  xmm0, [rsp+130h+var_F0]
0x14031532a  movdqa  [rsp+130h+var_F0], xmm0
0x140315330  lea     rax, [rsp+130h+hObject]
0x140315335  mov     qword ptr [rsp+130h+ppv], rax
0x14031533a  lea     r9, [rbp+30h+var_90]
0x14031533e  lea     r8, [rsp+130h+var_F0]
0x140315343  lea     rdx, [rbp+30h+var_60]
0x140315347  mov     rcx, r10
0x14031534a  mov     rax, r11
0x14031534d  call    _guard_dispatch_icall
0x140315352  nop
0x140315353  mov     rbx, [rbp+30h+var_A0]
0x140315357  test    rbx, rbx
0x14031535a  jz      short loc_140315394
0x14031535c  mov     eax, r12d
0x14031535f  lock xadd [rbx+8], eax
0x140315364  add     eax, r12d
0x140315367  jnz     short loc_140315394
0x140315369  mov     rax, [rbx]
0x14031536c  mov     rcx, rbx
0x14031536f  mov     rax, [rax]
0x140315372  call    _guard_dispatch_icall
0x140315377  mov     eax, r12d
0x14031537a  lock xadd [rbx+0Ch], eax
0x14031537f  add     eax, r12d
0x140315382  jnz     short loc_140315394
0x140315384  mov     rax, [rbx]
0x140315387  mov     rcx, rbx
0x14031538a  mov     rax, [rax+8]
0x14031538e  call    _guard_dispatch_icall
0x140315393  nop
0x140315394  mov     rbx, qword ptr [rsp+130h+var_C0+8]
0x140315399  test    rbx, rbx
0x14031539c  jz      short loc_1403153D5
0x14031539e  mov     eax, r12d
0x1403153a1  lock xadd [rbx+8], eax
0x1403153a6  add     eax, r12d
0x1403153a9  jnz     short loc_1403153D5
0x1403153ab  mov     rax, [rbx]
0x1403153ae  mov     rcx, rbx
0x1403153b1  mov     rax, [rax]
0x1403153b4  call    _guard_dispatch_icall
0x1403153b9  mov     eax, r12d
0x1403153bc  lock xadd [rbx+0Ch], eax
0x1403153c1  add     eax, r12d
0x1403153c4  jnz     short loc_1403153D5
0x1403153c6  mov     rax, [rbx]
0x1403153c9  mov     rcx, rbx
0x1403153cc  mov     rax, [rax+8]
0x1403153d0  call    _guard_dispatch_icall
0x1403153d5  mov     [rdi], r15
0x1403153d8  mov     [rsp+130h+var_D0], 1
0x1403153e0  mov     qword ptr [rbp+30h+var_90], r15
0x1403153e4  cmp     [rbp+30h+var_38], r15b
0x1403153e8  jz      loc_140315508
0x1403153ee  lea     rcx, [rsp+130h+hObject]
0x1403153f3  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x1403153f8  nop
0x1403153f9  mov     rdx, [rax]
0x1403153fc  mov     rax, [rdx+8]
0x140315400  movsxd  rcx, dword ptr [rax+4]
0x140315404  add     rcx, 8
0x140315408  add     rcx, rdx
0x14031540b  mov     rax, [rcx]
0x14031540e  mov     r9, [rax+88h]
0x140315415  cmp     [rbp+30h+var_38], r15b
0x140315419  jz      loc_14031563C
0x14031541f  cmp     [rbp+30h+var_40], 2
0x140315423  jnz     loc_140315657
0x140315429  lea     rdx, [rbp+30h+var_60]
0x14031542d  cmp     [rbp+30h+var_48], 7
0x140315432  cmova   rdx, [rbp+30h+var_60]
0x140315437  mov     qword ptr [rsp+130h+var_F0], rdx
0x14031543c  mov     rax, [rbp+30h+var_50]
0x140315440  mov     qword ptr [rsp+130h+var_F0+8], rax
0x140315445  movaps  xmm0, [rsp+130h+var_F0]
0x14031544a  movdqa  [rsp+130h+var_C0], xmm0
0x140315450  lea     r8, [rsp+130h+var_C0]
0x140315455  lea     rdx, [rbp+30h+var_90]
0x140315459  mov     rax, r9
0x14031545c  call    _guard_dispatch_icall
0x140315461  nop
0x140315462  mov     rbx, [rsp+130h+hObject+8]
0x140315467  test    rbx, rbx
0x14031546a  jz      short loc_1403154A4
0x14031546c  mov     eax, r12d
0x14031546f  lock xadd [rbx+8], eax
0x140315474  add     eax, r12d
0x140315477  jnz     short loc_1403154A4
0x140315479  mov     rax, [rbx]
0x14031547c  mov     rcx, rbx
0x14031547f  mov     rax, [rax]
0x140315482  call    _guard_dispatch_icall
0x140315487  mov     eax, r12d
0x14031548a  lock xadd [rbx+0Ch], eax
0x14031548f  add     eax, r12d
0x140315492  jnz     short loc_1403154A4
0x140315494  mov     rax, [rbx]
0x140315497  mov     rcx, rbx
0x14031549a  mov     rax, [rax+8]
0x14031549e  call    _guard_dispatch_icall
0x1403154a3  nop
0x1403154a4  mov     rcx, [rdi]
0x1403154a7  mov     [rdi], r15
0x1403154aa  test    rcx, rcx
0x1403154ad  jz      short loc_1403154BC
0x1403154af  mov     rax, [rcx]
0x1403154b2  mov     rax, [rax+10h]
0x1403154b6  call    _guard_dispatch_icall
0x1403154bb  nop
0x1403154bc  lea     rcx, [r14+8]; rclsid
0x1403154c0  mov     qword ptr [rsp+130h+ppv], rdi; int
0x1403154c5  lea     r9, _GUID_e7b7429d_80c8_4459_98cc_fd065cd778dd; riid
0x1403154cc  xor     edx, edx; pUnkOuter
0x1403154ce  mov     r8d, 110004h; dwClsContext
0x1403154d4  call    cs:__imp_CoCreateInstance
0x1403154da  mov     rcx, [rbp+38h]; this
0x1403154de  test    eax, eax
0x1403154e0  js      loc_140315642
0x1403154e6  mov     rcx, qword ptr [rbp+30h+var_90]
0x1403154ea  test    rcx, rcx
0x1403154ed  jz      loc_1403155CC
0x1403154f3  mov     rax, [rcx]
0x1403154f6  mov     edx, 1
0x1403154fb  mov     rax, [rax]
0x1403154fe  call    _guard_dispatch_icall
0x140315503  jmp     loc_1403155CC
0x140315508  mov     rax, [rsi+10h]
0x14031550c  cmp     qword ptr [rsi+18h], 7
0x140315511  jbe     short loc_140315516
0x140315513  mov     rsi, [rsi]
0x140315516  mov     qword ptr [rsp+130h+var_F0], rsi
0x14031551b  mov     qword ptr [rsp+130h+var_F0+8], rax
0x140315520  movaps  xmm0, [rsp+130h+var_F0]
0x140315525  movdqa  [rsp+130h+var_C0], xmm0
0x14031552b  lea     rdx, [rsp+130h+var_C0]
0x140315530  lea     rcx, [rsp+130h+hObject]
0x140315535  call    ?GetAppContainerUserToken@UO@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@_W@4@@Z; Windows::UO::GetAppContainerUserToken(wil::basic_zstring_view<wchar_t>)
0x14031553a  mov     rbx, [rax]
0x14031553d  mov     [rax], r15
0x140315540  mov     qword ptr [rbp+30h+var_90], rbx
0x140315544  mov     rcx, [rsp+130h+hObject]; hObject
0x140315549  lea     rax, [rcx-1]
0x14031554d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140315551  ja      short loc_140315559
0x140315553  call    cs:__imp_CloseHandle
0x140315559  mov     rcx, rbx; hToken
0x14031555c  call    cs:__imp_ImpersonateLoggedOnUser
0x140315562  mov     rcx, [rbp+38h]; this
0x140315566  test    eax, eax
0x140315568  jz      loc_14031565D
0x14031556e  mov     [rsp+130h+var_100], 1
0x140315573  mov     rcx, [rdi]
0x140315576  mov     [rdi], r15
0x140315579  test    rcx, rcx
0x14031557c  jz      short loc_14031558B
0x14031557e  mov     rax, [rcx]
0x140315581  mov     rax, [rax+10h]
0x140315585  call    _guard_dispatch_icall
0x14031558a  nop
0x14031558b  lea     rcx, [r14+8]; rclsid
0x14031558f  mov     qword ptr [rsp+130h+ppv], rdi; int
0x140315594  lea     r9, _GUID_e7b7429d_80c8_4459_98cc_fd065cd778dd; riid
0x14031559b  xor     edx, edx; pUnkOuter
0x14031559d  mov     r8d, 10004h; dwClsContext
0x1403155a3  call    cs:__imp_CoCreateInstance
0x1403155a9  mov     rcx, [rbp+38h]; this
0x1403155ad  test    eax, eax
0x1403155af  js      short loc_140315627
0x1403155b1  call    cs:__imp_RevertToSelf
0x1403155b7  nop
0x1403155b8  lea     rax, [rbx-1]
0x1403155bc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1403155c0  ja      short loc_1403155CC
0x1403155c2  mov     rcx, rbx; hObject
0x1403155c5  call    cs:__imp_CloseHandle
0x1403155cb  nop
0x1403155cc  cmp     [rbp+30h+var_38], r15b
0x1403155d0  jz      short loc_1403155F3
0x1403155d2  movsx   rax, [rbp+30h+var_40]
0x1403155d7  add     rax, 1
0x1403155db  jz      short loc_1403155F3
0x1403155dd  sub     rax, 1
0x1403155e1  jz      short loc_1403155F3
0x1403155e3  cmp     rax, 1
0x1403155e7  jz      short loc_1403155F3
0x1403155e9  lea     rcx, [rbp+30h+var_60]
0x1403155ed  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403155f2  nop
0x1403155f3  lea     rcx, [rbp+30h+Src]
0x1403155f7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403155fc  mov     rax, rdi
0x1403155ff  mov     rcx, [rbp+30h+var_30]
0x140315603  xor     rcx, rsp; StackCookie
0x140315606  call    __security_check_cookie
0x14031560b  lea     r11, [rsp+130h+var_20]
0x140315613  mov     rbx, [r11+40h]
0x140315617  mov     rsi, [r11+48h]
0x14031561b  mov     rsp, r11
0x14031561e  pop     r15
0x140315620  pop     r14
0x140315622  pop     r12
0x140315624  pop     rdi
0x140315625  pop     rbp
0x140315626  retn
0x140315627  mov     r9d, eax; char *
0x14031562a  lea     r8, aCW1SSrcOrchest_84; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140315631  mov     edx, 5Fh ; '_'; void *
0x140315636  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14031563c  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x140315642  mov     r9d, eax; char *
0x140315645  lea     r8, aCW1SSrcOrchest_84; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14031564c  mov     edx, 51h ; 'Q'; void *
0x140315651  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140315657  call    ?_Throw_bad_variant_access@std@@YAXXZ; std::_Throw_bad_variant_access(void)
0x14031565d  lea     r8, aCW1SSrcOrchest_84; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140315664  mov     edx, 58h ; 'X'; void *
0x140315669  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
