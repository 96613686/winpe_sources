# LanguageManager::_QueueLanguageInstallation(std::shared_ptr<InstallationRequest> const &,LanguageOverlayTraceProvider::LanguagePackInstallationRequest &,LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest &)

- ea: `0x180032618`
- end: `0x180032c7a`
- name: `?_QueueLanguageInstallation@LanguageManager@@AEAAJAEBV?$shared_ptr@VInstallationRequest@@@std@@AEAVLanguagePackInstallationRequest@LanguageOverlayTraceProvider@@AEAVLanguageFeatureInstallationRequest@5@@Z`
- size: `1634`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002ee00`
- `0x18002f100`
- `0x18002f410`

## callees

- `0x180003a00`
- `0x180005db4`
- `0x18000e1b8`
- `0x18000eb50`
- `0x180010120`
- `0x1800141e4`
- `0x180014418`
- `0x180014ca0`
- `0x180014e24`
- `0x180014f3c`
- `0x180015a00`
- `0x1800178ac`
- `0x18002c28c`
- `0x18002c948`
- `0x18002d3d0`
- `0x18002d8b8`
- `0x180032618`
- `0x180043a60`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032735`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800327ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032859`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800328f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032735`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800327ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032859`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800328f8`
- `msvcp_win!_Mtx_unlock` at `0x1800326e3`
- `msvcp_win!_Mtx_unlock` at `0x1800326e3`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180032668`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003268c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180032668`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003268c`
- `msvcp_win!_Mtx_lock` at `0x180032659`
- `msvcp_win!_Mtx_lock` at `0x180032659`

## string_xrefs

- `0x1800327f1`: `LanguageFeatureInstallationRequest`
- `0x18003280d`: `LanguageFeatureInstallationRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=17 #try_helpers=1
__int64 __fastcall LanguageManager::_QueueLanguageInstallation(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  _QWORD *v9; // rdx
  __int64 v10; // rax
  bool i; // zf
  signed __int32 v12; // eax
  _QWORD *v13; // rax
  bool j; // zf
  signed __int32 v15; // eax
  bool k; // zf
  signed __int32 v17; // eax
  __int64 v18; // rax
  __int64 v19; // rax
  _BYTE *v20; // rdx
  _QWORD *v21; // rdx
  PSRWLOCK SRWLock; // [rsp+20h] [rbp-BB8h] BYREF
  int v24; // [rsp+28h] [rbp-BB0h] BYREF
  __int128 v25; // [rsp+30h] [rbp-BA8h] BYREF
  __int128 v26; // [rsp+40h] [rbp-B98h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B88h]
  __int64 v28; // [rsp+58h] [rbp-B80h]
  __int64 v29; // [rsp+60h] [rbp-B78h]
  __int64 v30; // [rsp+68h] [rbp-B70h]
  __int64 v31; // [rsp+70h] [rbp-B68h]
  _QWORD v32[7]; // [rsp+80h] [rbp-B58h] BYREF
  _QWORD *v33; // [rsp+B8h] [rbp-B20h]
  _BYTE v34[56]; // [rsp+C0h] [rbp-B18h] BYREF
  _BYTE *v35; // [rsp+F8h] [rbp-AE0h]
  void **v36; // [rsp+100h] [rbp-AD8h] BYREF
  __int64 v37; // [rsp+108h] [rbp-AD0h]
  __int64 v38; // [rsp+110h] [rbp-AC8h]
  void **v39; // [rsp+118h] [rbp-AC0h] BYREF
  void **v40; // [rsp+268h] [rbp-970h] BYREF
  void **v41; // [rsp+3B8h] [rbp-820h] BYREF
  void **v42; // [rsp+508h] [rbp-6D0h] BYREF
  _QWORD v43[42]; // [rsp+660h] [rbp-578h] BYREF
  _QWORD v44[42]; // [rsp+7B0h] [rbp-428h] BYREF
  _QWORD v45[42]; // [rsp+900h] [rbp-2D8h] BYREF
  _QWORD v46[42]; // [rsp+A50h] [rbp-188h] BYREF

  SRWLock = (PSRWLOCK)&LanguageManager::s_installationLock;
  if ( _Mtx_lock((_Mtx_t)&LanguageManager::s_installationLock) )
    std::_Throw_Cpp_error(5);
  if ( dword_180089E7C == 0x7FFFFFFF )
  {
    dword_180089E7C = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v9 = (_QWORD *)qword_18008A3A8;
  if ( qword_18008A3A8 == qword_18008A3B0 )
  {
    std::vector<std::shared_ptr<InstallationRequest>>::_Emplace_reallocate<std::shared_ptr<InstallationRequest> const &>(
      v8,
      (char *)qword_18008A3A8,
      a2);
  }
  else
  {
    *(_QWORD *)qword_18008A3A8 = 0;
    v9[1] = 0;
    v10 = a2[1];
    if ( v10 )
      _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
    *v9 = *a2;
    v9[1] = a2[1];
    qword_18008A3A8 += 16;
  }
  _Mtx_unlock((_Mtx_t)&LanguageManager::s_installationLock);
  v30 = a1;
  for ( i = a1 == 0; !i; i = v12 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 28), v12 + 1, v12) )
  {
    v12 = *(_DWORD *)(a1 + 28);
    if ( v12 == 0x7FFFFFFF )
      break;
  }
  if ( **(_DWORD **)(a3 + 272) == 1 )
  {
    wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a3,
      &SRWLock);
    ++*(_DWORD *)(*(_QWORD *)(a3 + 272) + 248LL);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(
      v44,
      a3);
    v44[0] = &LanguageOverlayTraceProvider::LanguagePackInstallationRequest::`vftable';
  }
  else
  {
    wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(
      v44,
      a3);
    v44[0] = &LanguageOverlayTraceProvider::LanguagePackInstallationRequest::`vftable';
  }
  if ( **(_DWORD **)(a4 + 272) == 1 )
  {
    wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a4,
      &SRWLock);
    ++*(_DWORD *)(*(_QWORD *)(a4 + 272) + 248LL);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
  }
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(
    v43,
    a4);
  v43[0] = &LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::`vftable';
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(
    v46,
    "LanguageFeatureInstallationRequest");
  v46[0] = &LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::`vftable';
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(
    v45,
    "LanguageFeatureInstallationRequest");
  v45[0] = &LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::`vftable';
  if ( **(_DWORD **)(a4 + 272) == 1 )
  {
    wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a4,
      &SRWLock);
    ++*(_DWORD *)(*(_QWORD *)(a4 + 272) + 248LL);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
  }
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(
    &v36,
    a4);
  v36 = &LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::`vftable';
  LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::operator=((__int64)v46, (__int64)&v36);
  v36 = &LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::`vftable';
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v36);
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)&v36);
  if ( **(_DWORD **)(a4 + 272) == 1 )
  {
    wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a4,
      &SRWLock);
    ++*(_DWORD *)(*(_QWORD *)(a4 + 272) + 248LL);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
  }
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(
    &v36,
    a4);
  v36 = &LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::`vftable';
  LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::operator=((__int64)v45, (__int64)&v36);
  v36 = &LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::`vftable';
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v36);
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)&v36);
  v24 = 0;
  v25 = 0;
  v13 = operator new(0x30u);
  *v13 = v13;
  v13[1] = v13;
  *(_QWORD *)&v25 = v13;
  v26 = 0;
  v27 = 0;
  v28 = 7;
  v29 = 8;
  v24 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::weak_ptr<ExecutionGate>>>>>>>::_Assign_grow(
    &v26,
    16,
    v13);
  for ( j = a1 == 0; !j; j = v15 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 28), v15 + 1, v15) )
  {
    v15 = *(_DWORD *)(a1 + 28);
    if ( v15 == 0x7FFFFFFF )
      break;
  }
  v32[0] = off_18006BD80;
  v32[1] = a1;
  v31 = 0;
  v33 = v32;
  v36 = (void **)a1;
  for ( k = a1 == 0; !k; k = v17 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 28), v17 + 1, v17) )
  {
    v17 = *(_DWORD *)(a1 + 28);
    if ( v17 == 0x7FFFFFFF )
      break;
  }
  v37 = 0;
  v38 = 0;
  v18 = a2[1];
  if ( v18 )
    _InterlockedIncrement((volatile signed __int32 *)(v18 + 8));
  v37 = *a2;
  v38 = a2[1];
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(
    &v39,
    v44);
  v39 = &LanguageOverlayTraceProvider::LanguagePackInstallationRequest::`vftable';
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(
    &v40,
    v43);
  v40 = &LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::`vftable';
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(
    &v41,
    v46);
  v41 = &LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::`vftable';
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(
    &v42,
    v45);
  v42 = &LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::`vftable';
  v35 = 0;
  v35 = (_BYTE *)std::_Global_new_std::_Func_impl_no_alloc__lambda_9eedea0c4fc191e31f859f53b9188479__void___lambda_9eedea0c4fc191e31f859f53b9188479___(&v36);
  v19 = CreateManagedWork(&SRWLock, v34, v32);
  QueueWork(v19, &v24, 2);
  if ( v35 )
  {
    v20 = v34;
    LOBYTE(v20) = v35 != v34;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v35 + 32LL))(v35, v20);
  }
  lambda_9eedea0c4fc191e31f859f53b9188479_::__lambda_9eedea0c4fc191e31f859f53b9188479_(&v36);
  if ( v33 )
  {
    v21 = v32;
    LOBYTE(v21) = v33 != v32;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v33 + 32LL))(v33, v21);
    v33 = 0;
  }
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>((char **)&v26);
  std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>((void **)&v25);
  v45[0] = &LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::`vftable';
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v45);
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v45);
  v46[0] = &LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::`vftable';
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v46);
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v46);
  v43[0] = &LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::`vftable';
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v43);
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v43);
  v44[0] = &LanguageOverlayTraceProvider::LanguagePackInstallationRequest::`vftable';
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v44);
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v44);
  if ( a1 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ILanguageManager,ILanguagePackInstaller,IFastRundown>::Release(a1);
  return 0;
}

```

## disassembly

```asm
0x180032618  mov     [rsp+arg_0], rbx
0x18003261d  push    rsi
0x18003261e  push    rdi
0x18003261f  push    r13
0x180032621  push    r14
0x180032623  push    r15
0x180032625  sub     rsp, 0BB0h
0x18003262c  mov     rax, cs:__security_cookie
0x180032633  xor     rax, rsp
0x180032636  mov     [rsp+0BD8h+var_38], rax
0x18003263e  mov     rdi, r9
0x180032641  mov     rsi, r8
0x180032644  mov     r14, rdx
0x180032647  mov     rbx, rcx
0x18003264a  lea     r15, ?s_installationLock@LanguageManager@@0Vrecursive_mutex@std@@A; std::recursive_mutex LanguageManager::s_installationLock
0x180032651  mov     [rsp+0BD8h+SRWLock], r15
0x180032656  mov     rcx, r15; _Mtx_t
0x180032659  call    cs:__imp__Mtx_lock
0x18003265f  test    eax, eax
0x180032661  jz      short loc_18003266E
0x180032663  mov     ecx, 5
0x180032668  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003266e  mov     r13d, 7FFFFFFFh
0x180032674  cmp     cs:dword_180089E7C, r13d
0x18003267b  jnz     short loc_180032693
0x18003267d  mov     cs:dword_180089E7C, 7FFFFFFEh
0x180032687  mov     ecx, 6
0x18003268c  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180032692  nop
0x180032693  mov     rdx, cs:qword_18008A3A8
0x18003269a  cmp     rdx, cs:qword_18008A3B0
0x1800326a1  jz      short loc_1800326D7
0x1800326a3  mov     qword ptr [rdx], 0
0x1800326aa  mov     qword ptr [rdx+8], 0
0x1800326b2  mov     rax, [r14+8]
0x1800326b6  test    rax, rax
0x1800326b9  jz      short loc_1800326BF
0x1800326bb  lock inc dword ptr [rax+8]
0x1800326bf  mov     rax, [r14]
0x1800326c2  mov     [rdx], rax
0x1800326c5  mov     rax, [r14+8]
0x1800326c9  mov     [rdx+8], rax
0x1800326cd  add     cs:qword_18008A3A8, 10h
0x1800326d5  jmp     short loc_1800326E0
0x1800326d7  mov     r8, r14
0x1800326da  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VInstallationRequest@@@std@@@?$vector@V?$shared_ptr@VInstallationRequest@@@std@@V?$allocator@V?$shared_ptr@VInstallationRequest@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VInstallationRequest@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<InstallationRequest>>::_Emplace_reallocate<std::shared_ptr<InstallationRequest> const &>(std::shared_ptr<InstallationRequest> * const,std::shared_ptr<InstallationRequest> const &)
0x1800326df  nop
0x1800326e0  mov     rcx, r15; _Mtx_t
0x1800326e3  call    cs:__imp__Mtx_unlock
0x1800326e9  mov     [rsp+0BD8h+var_B70], rbx
0x1800326ee  test    rbx, rbx
0x1800326f1  jmp     short loc_1800326FB
0x1800326f3  lea     ecx, [rax+1]
0x1800326f6  lock cmpxchg [rbx+1Ch], ecx
0x1800326fb  jz      short loc_180032705
0x1800326fd  mov     eax, [rbx+1Ch]
0x180032700  cmp     eax, r13d
0x180032703  jnz     short loc_1800326F3
0x180032705  mov     rax, [rsi+110h]
0x18003270c  cmp     dword ptr [rax], 1
0x18003270f  jnz     short loc_18003275C
0x180032711  lea     rdx, [rsp+0BD8h+SRWLock]
0x180032716  mov     rcx, rsi
0x180032719  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003271e  mov     rax, [rsi+110h]
0x180032725  inc     dword ptr [rax+0F8h]
0x18003272b  mov     rcx, [rsp+0BD8h+SRWLock]; SRWLock
0x180032730  test    rcx, rcx
0x180032733  jz      short loc_18003273B
0x180032735  call    cs:__imp_ReleaseSRWLockExclusive
0x18003273b  mov     rdx, rsi
0x18003273e  lea     rcx, [rsp+0BD8h+var_428]
0x180032746  call    ??0?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType> const &)
0x18003274b  lea     r15, ??_7LanguagePackInstallationRequest@LanguageOverlayTraceProvider@@6B@; const LanguageOverlayTraceProvider::LanguagePackInstallationRequest::`vftable'
0x180032752  mov     [rsp+0BD8h+var_428], r15
0x18003275a  jmp     short loc_18003277B
0x18003275c  mov     rdx, rsi
0x18003275f  lea     rcx, [rsp+0BD8h+var_428]
0x180032767  call    ??0?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType> const &)
0x18003276c  lea     r15, ??_7LanguagePackInstallationRequest@LanguageOverlayTraceProvider@@6B@; const LanguageOverlayTraceProvider::LanguagePackInstallationRequest::`vftable'
0x180032773  mov     [rsp+0BD8h+var_428], r15
0x18003277b  mov     rax, [rdi+110h]
0x180032782  cmp     dword ptr [rax], 1
0x180032785  jnz     short loc_1800327D2
0x180032787  lea     rdx, [rsp+0BD8h+SRWLock]
0x18003278c  mov     rcx, rdi
0x18003278f  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180032794  mov     rax, [rdi+110h]
0x18003279b  inc     dword ptr [rax+0F8h]
0x1800327a1  mov     rcx, [rsp+0BD8h+SRWLock]; SRWLock
0x1800327a6  test    rcx, rcx
0x1800327a9  jz      short loc_1800327B1
0x1800327ab  call    cs:__imp_ReleaseSRWLockExclusive
0x1800327b1  mov     rdx, rdi
0x1800327b4  lea     rcx, [rsp+0BD8h+var_578]
0x1800327bc  call    ??0?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType> const &)
0x1800327c1  lea     rsi, ??_7LanguageFeatureInstallationRequest@LanguageOverlayTraceProvider@@6B@; const LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::`vftable'
0x1800327c8  mov     [rsp+0BD8h+var_578], rsi
0x1800327d0  jmp     short loc_1800327F1
0x1800327d2  mov     rdx, rdi
0x1800327d5  lea     rcx, [rsp+0BD8h+var_578]
0x1800327dd  call    ??0?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType> const &)
0x1800327e2  lea     rsi, ??_7LanguageFeatureInstallationRequest@LanguageOverlayTraceProvider@@6B@; const LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::`vftable'
0x1800327e9  mov     [rsp+0BD8h+var_578], rsi
0x1800327f1  lea     rdx, aLanguagefeatur_0; "LanguageFeatureInstallationRequest"
0x1800327f8  lea     rcx, [rsp+0BD8h+var_188]
0x180032800  call    ??0?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180032805  mov     [rsp+0BD8h+var_188], rsi
0x18003280d  lea     rdx, aLanguagefeatur_0; "LanguageFeatureInstallationRequest"
0x180032814  lea     rcx, [rsp+0BD8h+var_2D8]
0x18003281c  call    ??0?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180032821  mov     [rsp+0BD8h+var_2D8], rsi
0x180032829  mov     rax, [rdi+110h]
0x180032830  cmp     dword ptr [rax], 1
0x180032833  jnz     short loc_180032879
0x180032835  lea     rdx, [rsp+0BD8h+SRWLock]
0x18003283a  mov     rcx, rdi
0x18003283d  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180032842  mov     rax, [rdi+110h]
0x180032849  inc     dword ptr [rax+0F8h]
0x18003284f  mov     rcx, [rsp+0BD8h+SRWLock]; SRWLock
0x180032854  test    rcx, rcx
0x180032857  jz      short loc_18003285F
0x180032859  call    cs:__imp_ReleaseSRWLockExclusive
0x18003285f  mov     rdx, rdi
0x180032862  lea     rcx, [rsp+0BD8h+var_AD8]
0x18003286a  call    ??0?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType> const &)
0x18003286f  mov     [rsp+0BD8h+var_AD8], rsi
0x180032877  jmp     short loc_180032891
0x180032879  mov     rdx, rdi
0x18003287c  lea     rcx, [rsp+0BD8h+var_AD8]
0x180032884  call    ??0?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType> const &)
0x180032889  mov     [rsp+0BD8h+var_AD8], rsi
0x180032891  lea     rdx, [rsp+0BD8h+var_AD8]
0x180032899  lea     rcx, [rsp+0BD8h+var_188]
0x1800328a1  call    ??4LanguageFeatureInstallationRequest@LanguageOverlayTraceProvider@@QEAAAEAV01@$$QEAV01@@Z; LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::operator=(LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest &&)
0x1800328a6  mov     [rsp+0BD8h+var_AD8], rsi
0x1800328ae  lea     rcx, [rsp+0BD8h+var_AD8]
0x1800328b6  call    ?Destroy@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800328bb  lea     rcx, [rsp+0BD8h+var_AD8]
0x1800328c3  call    ??1?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800328c8  mov     rax, [rdi+110h]
0x1800328cf  cmp     dword ptr [rax], 1
0x1800328d2  jnz     short loc_180032918
0x1800328d4  lea     rdx, [rsp+0BD8h+SRWLock]
0x1800328d9  mov     rcx, rdi
0x1800328dc  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800328e1  mov     rax, [rdi+110h]
0x1800328e8  inc     dword ptr [rax+0F8h]
0x1800328ee  mov     rcx, [rsp+0BD8h+SRWLock]; SRWLock
0x1800328f3  test    rcx, rcx
0x1800328f6  jz      short loc_1800328FE
0x1800328f8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800328fe  mov     rdx, rdi
0x180032901  lea     rcx, [rsp+0BD8h+var_AD8]
0x180032909  call    ??0?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType> const &)
0x18003290e  mov     [rsp+0BD8h+var_AD8], rsi
0x180032916  jmp     short loc_180032930
0x180032918  mov     rdx, rdi
0x18003291b  lea     rcx, [rsp+0BD8h+var_AD8]
0x180032923  call    ??0?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType> const &)
0x180032928  mov     [rsp+0BD8h+var_AD8], rsi
0x180032930  lea     rdx, [rsp+0BD8h+var_AD8]
0x180032938  lea     rcx, [rsp+0BD8h+var_2D8]
0x180032940  call    ??4LanguageFeatureInstallationRequest@LanguageOverlayTraceProvider@@QEAAAEAV01@$$QEAV01@@Z; LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest::operator=(LanguageOverlayTraceProvider::LanguageFeatureInstallationRequest &&)
0x180032945  mov     [rsp+0BD8h+var_AD8], rsi
0x18003294d  lea     rcx, [rsp+0BD8h+var_AD8]
0x180032955  call    ?Destroy@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18003295a  lea     rcx, [rsp+0BD8h+var_AD8]
0x180032962  call    ??1?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180032967  mov     [rsp+0BD8h+var_BB0], 0
0x18003296f  xorps   xmm1, xmm1
0x180032972  movdqu  [rsp+0BD8h+var_BA8], xmm1
0x180032978  mov     ecx, 30h ; '0'; Size
0x18003297d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032982  mov     [rax], rax
0x180032985  mov     [rax+8], rax
0x180032989  mov     qword ptr [rsp+0BD8h+var_BA8], rax
0x18003298e  xorps   xmm0, xmm0
0x180032991  movdqu  [rsp+0BD8h+var_B98], xmm0
0x180032997  mov     [rsp+0BD8h+var_B88], 0
0x1800329a0  mov     [rsp+0BD8h+var_B80], 7
0x1800329a9  mov     [rsp+0BD8h+var_B78], 8
0x1800329b2  mov     [rsp+0BD8h+var_BB0], 3F800000h
0x1800329ba  mov     r8, rax
0x1800329bd  mov     edx, 10h
0x1800329c2  lea     rcx, [rsp+0BD8h+var_B98]
0x1800329c7  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$weak_ptr@VExecutionGate@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$weak_ptr@VExecutionGate@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::weak_ptr<ExecutionGate>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::weak_ptr<ExecutionGate>>>>>)
0x1800329cc  nop
0x1800329cd  test    rbx, rbx
0x1800329d0  jmp     short loc_1800329DA
0x1800329d2  lea     ecx, [rax+1]
0x1800329d5  lock cmpxchg [rbx+1Ch], ecx
0x1800329da  jz      short loc_1800329E4
0x1800329dc  mov     eax, [rbx+1Ch]
0x1800329df  cmp     eax, r13d
0x1800329e2  jnz     short loc_1800329D2
0x1800329e4  lea     rax, off_18006BD80
0x1800329eb  mov     [rsp+0BD8h+var_B58], rax
0x1800329f3  mov     [rsp+0BD8h+var_B50], rbx
0x1800329fb  mov     [rsp+0BD8h+var_B68], 0
0x180032a04  lea     rax, [rsp+0BD8h+var_B58]
0x180032a0c  mov     [rsp+0BD8h+var_B20], rax
0x180032a14  mov     [rsp+0BD8h+var_AD8], rbx
0x180032a1c  test    rbx, rbx
0x180032a1f  jmp     short loc_180032A29
0x180032a21  lea     ecx, [rax+1]
0x180032a24  lock cmpxchg [rbx+1Ch], ecx
0x180032a29  jz      short loc_180032A33
0x180032a2b  mov     eax, [rbx+1Ch]
0x180032a2e  cmp     eax, r13d
0x180032a31  jnz     short loc_180032A21
0x180032a33  mov     [rsp+0BD8h+var_AD0], 0
0x180032a3f  mov     [rsp+0BD8h+var_AC8], 0
0x180032a4b  mov     rax, [r14+8]
0x180032a4f  test    rax, rax
0x180032a52  jz      short loc_180032A58
0x180032a54  lock inc dword ptr [rax+8]
0x180032a58  mov     rax, [r14]
0x180032a5b  mov     [rsp+0BD8h+var_AD0], rax
0x180032a63  mov     rax, [r14+8]
0x180032a67  mov     [rsp+0BD8h+var_AC8], rax
0x180032a6f  lea     rdx, [rsp+0BD8h+var_428]
0x180032a77  lea     rcx, [rsp+0BD8h+var_AC0]
0x180032a7f  call    ??0?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType> const &)
0x180032a84  mov     [rsp+0BD8h+var_AC0], r15
0x180032a8c  lea     rdx, [rsp+0BD8h+var_578]
0x180032a94  lea     rcx, [rsp+0BD8h+var_970]
0x180032a9c  call    ??0?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType> const &)
0x180032aa1  mov     [rsp+0BD8h+var_970], rsi
0x180032aa9  lea     rdx, [rsp+0BD8h+var_188]
0x180032ab1  lea     rcx, [rsp+0BD8h+var_820]
0x180032ab9  call    ??0?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType> const &)
0x180032abe  mov     [rsp+0BD8h+var_820], rsi
0x180032ac6  lea     rdx, [rsp+0BD8h+var_2D8]
0x180032ace  lea     rcx, [rsp+0BD8h+var_6D0]
0x180032ad6  call    ??0?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType> const &)
0x180032adb  mov     [rsp+0BD8h+var_6D0], rsi
0x180032ae3  mov     [rsp+0BD8h+var_AE0], 0
0x180032aef  lea     rcx, [rsp+0BD8h+var_AD8]
0x180032af7  call    std___Global_new_std___Func_impl_no_alloc__lambda_9eedea0c4fc191e31f859f53b9188479__void___lambda_9eedea0c4fc191e31f859f53b9188479___
0x180032afc  mov     [rsp+0BD8h+var_AE0], rax
0x180032b04  lea     r8, [rsp+0BD8h+var_B58]
0x180032b0c  lea     rdx, [rsp+0BD8h+var_B18]
0x180032b14  lea     rcx, [rsp+0BD8h+SRWLock]
0x180032b19  call    ?CreateManagedWork@@YA?AV?$unique_ptr@VIManagedWork@@U?$default_delete@VIManagedWork@@@std@@@std@@$$QEAV?$function@$$A6AXXZ@2@0@Z; CreateManagedWork(std::function<void (void)> &&,std::function<void (void)> &&)
0x180032b1e  mov     r8d, 2
0x180032b24  lea     rdx, [rsp+0BD8h+var_BB0]
0x180032b29  mov     rcx, rax
0x180032b2c  call    ?QueueWork@@YAXV?$unique_ptr@VIManagedWork@@U?$default_delete@VIManagedWork@@@std@@@std@@AEBV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@W4WorkPriority@@@Z; QueueWork(std::unique_ptr<IManagedWork>,std::unordered_set<std::wstring> const &,WorkPriority)
0x180032b31  nop
0x180032b32  mov     rcx, [rsp+0BD8h+var_AE0]
0x180032b3a  test    rcx, rcx
0x180032b3d  jz      short loc_180032B5A
0x180032b3f  mov     rax, [rcx]
0x180032b42  lea     rdx, [rsp+0BD8h+var_B18]
0x180032b4a  cmp     rcx, rdx
0x180032b4d  setnz   dl
0x180032b50  mov     rax, [rax+20h]
0x180032b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b59  nop
0x180032b5a  lea     rcx, [rsp+0BD8h+var_AD8]
0x180032b62  call    _lambda_9eedea0c4fc191e31f859f53b9188479_____lambda_9eedea0c4fc191e31f859f53b9188479_
0x180032b67  nop
0x180032b68  mov     rcx, [rsp+0BD8h+var_B20]
0x180032b70  test    rcx, rcx
0x180032b73  jz      short loc_180032B9B
0x180032b75  mov     rax, [rcx]
0x180032b78  lea     rdx, [rsp+0BD8h+var_B58]
0x180032b80  cmp     rcx, rdx
0x180032b83  setnz   dl
0x180032b86  mov     rax, [rax+20h]
0x180032b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b8f  mov     [rsp+0BD8h+var_B20], 0
0x180032b9b  lea     rcx, [rsp+0BD8h+var_B98]
0x180032ba0  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x180032ba5  lea     rcx, [rsp+0BD8h+var_BA8]
0x180032baa  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x180032baf  nop
0x180032bb0  mov     [rsp+0BD8h+var_2D8], rsi
0x180032bb8  lea     rcx, [rsp+0BD8h+var_2D8]
0x180032bc0  call    ?Destroy@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180032bc5  lea     rcx, [rsp+0BD8h+var_2D8]
0x180032bcd  call    ??1?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180032bd2  nop
0x180032bd3  mov     [rsp+0BD8h+var_188], rsi
0x180032bdb  lea     rcx, [rsp+0BD8h+var_188]
0x180032be3  call    ?Destroy@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180032be8  lea     rcx, [rsp+0BD8h+var_188]
0x180032bf0  call    ??1?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180032bf5  nop
0x180032bf6  mov     [rsp+0BD8h+var_578], rsi
0x180032bfe  lea     rcx, [rsp+0BD8h+var_578]
0x180032c06  call    ?Destroy@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180032c0b  lea     rcx, [rsp+0BD8h+var_578]
0x180032c13  call    ??1?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180032c18  nop
0x180032c19  mov     [rsp+0BD8h+var_428], r15
0x180032c21  lea     rcx, [rsp+0BD8h+var_428]
0x180032c29  call    ?Destroy@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
  ... truncated ...
```
