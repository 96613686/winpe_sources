# CLocationManager::get_DefaultLocation(GEOLOCATION_INFO * *)

- ea: `0x1800c22c0`
- end: `0x1800c262c`
- name: `?get_DefaultLocation@CLocationManager@@UEAAJPEAPEAUGEOLOCATION_INFO@@@Z`
- size: `876`
- prototype: `__int64 __fastcall(CLocationManager *__hidden this, struct GEOLOCATION_INFO **)`
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003228`
- `0x18000c974`
- `0x18001be08`
- `0x18001eb88`
- `0x18001ecbc`
- `0x18001efe0`
- `0x18001f334`
- `0x180020994`
- `0x180020c64`
- `0x180021450`
- `0x180022568`
- `0x1800277ec`
- `0x180028434`
- `0x18003b92c`
- `0x1800498bc`
- `0x1800536d8`
- `0x18005bb84`
- `0x18006807c`
- `0x180087f08`
- `0x18008b56c`
- `0x18009c310`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x1800c157c`
- `0x1800c22c0`
- `0x18015e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800c24c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c24c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c23d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c23d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c23eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c244d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c25f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c23eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c244d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c25f9`

## string_xrefs

- `0x1800c2415`: `LocationCallerInfoHelper::ImpersonateAndGetUserSid(sidUser)`
- `0x1800c247b`: `!(wil::verify_bool(sidUser.IsValid()))`

## pseudocode

```c
__int64 __fastcall CLocationManager::get_DefaultLocation(CLocationManager *this, std::_Ref_count_base ***a2)
{
  __int64 v4; // rax
  std::_Ref_count_base *v5; // r15
  void *v6; // r14
  int UserSid; // ebx
  const char *v8; // rax
  __int64 v9; // rdx
  void *v10; // rbx
  unsigned int (__fastcall *v11)(std::_Ref_count_base *, _QWORD, void *); // rdi
  const unsigned __int16 *v12; // rax
  _QWORD *v13; // rax
  int CallerAppDisplayName; // eax
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rdx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  std::_Ref_count_base **v21; // rcx
  wil::details *v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+30h] [rbp-D0h]
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v25[2]; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v26[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v28; // [rsp+70h] [rbp-90h]
  _OWORD v29[2]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v30[128]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+168h] [rbp+68h]

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  bstrString = 0;
  *(_OWORD *)v26 = 0;
  *(_OWORD *)v25 = 0;
  wil::EnterCriticalSection(&bstrString, &stru_1801E4420);
  if ( !dword_1801E4448 )
    CLocationObjectManager::Start();
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&bstrString);
  CLocationObjectManager::GetLocationSavedPositions(&CLocationObjectManager::s_instance, v25);
  v4 = std::weak_ptr<ILocationUIHandler>::lock(v25, &v27);
  std::shared_ptr<ILocationSignalManager>::operator=(v26, v4);
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
  v5 = v26[0];
  if ( !v26[0] )
  {
    if ( v25[1] )
      std::_Ref_count_base::_Decwref(v25[1]);
    if ( v26[1] )
      std::_Ref_count_base::_Decref(v26[1]);
    return 2147500036LL;
  }
  if ( v25[1] )
    std::_Ref_count_base::_Decwref(v25[1]);
  memset_0(v30, 0, 0x78u);
  ATL::CSid::CSid((ATL::CSid *)v30);
  v6 = CoTaskMemAlloc(0x58u);
  if ( !v6 )
  {
    ATL::CSid::~CSid((ATL::CSid *)v30);
    CoTaskMemFree(0);
    if ( v26[1] )
      std::_Ref_count_base::_Decref(v26[1]);
    return 2147942414LL;
  }
  UserSid = LocationCallerInfoHelper::ImpersonateAndGetUserSid((struct ATL::CSid *)v30);
  if ( UserSid < 0 )
  {
    v8 = "LocationCallerInfoHelper::ImpersonateAndGetUserSid(sidUser)";
    v9 = 258;
LABEL_21:
    LODWORD(v22) = UserSid;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationmanager.cpp",
      "CLocationManager::get_DefaultLocation",
      v8,
      v22,
      v23);
    ATL::CSid::~CSid((ATL::CSid *)v30);
    CoTaskMemFree(v6);
    if ( v26[1] )
      std::_Ref_count_base::_Decref(v26[1]);
    return (unsigned int)UserSid;
  }
  if ( !ATL::CSid::IsValid((ATL::CSid *)v30) )
  {
    UserSid = -2147023559;
    v8 = "!(wil::verify_bool(sidUser.IsValid()))";
    v9 = 259;
    goto LABEL_21;
  }
  v10 = v6;
  v11 = *(unsigned int (__fastcall **)(std::_Ref_count_base *, _QWORD, void *))(*(_QWORD *)v5 + 24LL);
  v12 = ATL::CSid::Sid((ATL::CSid *)v30);
  v13 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v12);
  LODWORD(v11) = v11(v5, *v13, v6) >> 31;
  SysFreeString(bstrString);
  if ( (unsigned __int8)v11 != 1 )
  {
    v10 = 0;
    *a2 = (std::_Ref_count_base **)v6;
  }
  v29[0] = 0;
  LOWORD(v29[0]) = 0;
  v29[1] = _mm_load_si128((const __m128i *)&_xmm);
  CallerAppDisplayName = LocationCallerInfoHelper::GetCallerAppDisplayName(v29);
  if ( CallerAppDisplayName < 0 )
  {
    LODWORD(v22) = CallerAppDisplayName;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x10D,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationmanager.cpp",
      "CLocationManager::get_DefaultLocation",
      "LocationCallerInfoHelper::GetCallerAppDisplayName(appDisplayName)",
      (const char *)v22,
      v23);
  }
  if ( (unsigned int)dword_1801DDF30 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801DDF30, 0x200000000000LL) )
  {
    v27 = 0x1000000;
    v25[0] = (std::_Ref_count_base *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29, v17);
    LODWORD(bstrString) = *a2 == 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v18,
      (unsigned int)&dword_1801AE444,
      v19,
      v20,
      (__int64)&bstrString,
      (__int64)v25,
      (__int64)&v27);
  }
  if ( *a2 && (unsigned int)dword_1801DDEF8 > 4 )
  {
    v21 = *a2;
    v25[0] = (*a2)[1];
    v27 = (__int64)*v21;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (_DWORD)v21,
      (unsigned int)word_1801AE172,
      v15,
      v16,
      (__int64)&v27,
      (__int64)v25);
  }
  std::wstring::_Tidy_deallocate(v29);
  ATL::CSid::~CSid((ATL::CSid *)v30);
  CoTaskMemFree(v10);
  if ( v26[1] )
    std::_Ref_count_base::_Decref(v26[1]);
  return 0;
}

```

## disassembly

```asm
0x1800c22c0  push    rbp
0x1800c22c2  push    rbx
0x1800c22c3  push    rsi
0x1800c22c4  push    rdi
0x1800c22c5  push    r14
0x1800c22c7  push    r15
0x1800c22c9  lea     rbp, [rsp-38h]
0x1800c22ce  sub     rsp, 138h
0x1800c22d5  mov     rax, cs:__security_cookie
0x1800c22dc  xor     rax, rsp
0x1800c22df  mov     [rbp+60h+var_40], rax
0x1800c22e3  mov     rsi, rdx
0x1800c22e6  test    rdx, rdx
0x1800c22e9  jnz     short loc_1800C22F5
0x1800c22eb  mov     eax, 80004003h
0x1800c22f0  jmp     loc_1800C2610
0x1800c22f5  xorps   xmm0, xmm0
0x1800c22f8  mov     qword ptr [rdx], 0
0x1800c22ff  lea     rdx, stru_1801E4420
0x1800c2306  mov     [rsp+160h+bstrString], 0
0x1800c230f  lea     rcx, [rsp+160h+bstrString]
0x1800c2314  movdqu  xmmword ptr [rsp+160h+var_108], xmm0
0x1800c231a  movups  xmmword ptr [rsp+160h+var_118], xmm0
0x1800c231f  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800c2324  cmp     cs:dword_1801E4448, 0
0x1800c232b  jnz     short loc_1800C2332
0x1800c232d  call    ?Start@CLocationObjectManager@@KAJXZ; CLocationObjectManager::Start(void)
0x1800c2332  lea     rcx, [rsp+160h+bstrString]
0x1800c2337  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1800c233c  lea     rdx, [rsp+160h+var_118]
0x1800c2341  lea     rcx, ?s_instance@CLocationObjectManager@@1V1@A; CLocationObjectManager CLocationObjectManager::s_instance
0x1800c2348  call    ?GetLocationSavedPositions@CLocationObjectManager@@QEBA?AV?$weak_ptr@VILocationSavedPositions@@@std@@XZ; CLocationObjectManager::GetLocationSavedPositions(void)
0x1800c234d  lea     rdx, [rsp+160h+var_F8]
0x1800c2352  lea     rcx, [rsp+160h+var_118]
0x1800c2357  call    ?lock@?$weak_ptr@VILocationUIHandler@@@std@@QEBA?AV?$shared_ptr@VILocationUIHandler@@@2@XZ; std::weak_ptr<ILocationUIHandler>::lock(void)
0x1800c235c  mov     rdx, rax
0x1800c235f  lea     rcx, [rsp+160h+var_108]
0x1800c2364  call    ??4?$shared_ptr@VILocationSignalManager@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ILocationSignalManager>::operator=(std::shared_ptr<ILocationSignalManager> &&)
0x1800c2369  mov     rcx, [rsp+160h+var_F0]; this
0x1800c236e  test    rcx, rcx
0x1800c2371  jz      short loc_1800C2378
0x1800c2373  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c2378  mov     r15, [rsp+160h+var_108]
0x1800c237d  mov     rcx, [rsp+160h+var_118+8]; this
0x1800c2382  test    r15, r15
0x1800c2385  jnz     short loc_1800C23AA
0x1800c2387  test    rcx, rcx
0x1800c238a  jz      short loc_1800C2391
0x1800c238c  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800c2391  mov     rcx, [rsp+160h+var_108+8]; this
0x1800c2396  test    rcx, rcx
0x1800c2399  jz      short loc_1800C23A0
0x1800c239b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c23a0  mov     eax, 80004004h
0x1800c23a5  jmp     loc_1800C2610
0x1800c23aa  test    rcx, rcx
0x1800c23ad  jz      short loc_1800C23B4
0x1800c23af  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800c23b4  xor     edx, edx; Val
0x1800c23b6  lea     rcx, [rbp+60h+var_C0]; void *
0x1800c23ba  lea     r8d, [rdx+78h]; Size
0x1800c23be  call    memset_0
0x1800c23c3  lea     rcx, [rbp+60h+var_C0]; this
0x1800c23c7  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x1800c23cc  mov     ecx, 58h ; 'X'; cb
0x1800c23d1  call    cs:__imp_CoTaskMemAlloc
0x1800c23d7  lea     rcx, [rbp+60h+var_C0]; struct ATL::CSid *
0x1800c23db  mov     r14, rax
0x1800c23de  test    rax, rax
0x1800c23e1  jnz     short loc_1800C240A
0x1800c23e3  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1800c23e8  mov     rcx, r14; pv
0x1800c23eb  call    cs:__imp_CoTaskMemFree
0x1800c23f1  mov     rcx, [rsp+160h+var_108+8]; this
0x1800c23f6  test    rcx, rcx
0x1800c23f9  jz      short loc_1800C2400
0x1800c23fb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c2400  mov     eax, 8007000Eh
0x1800c2405  jmp     loc_1800C2610
0x1800c240a  call    ?ImpersonateAndGetUserSid@LocationCallerInfoHelper@@SAJAEAVCSid@ATL@@@Z; LocationCallerInfoHelper::ImpersonateAndGetUserSid(ATL::CSid &)
0x1800c240f  mov     ebx, eax
0x1800c2411  test    eax, eax
0x1800c2413  jns     short loc_1800C2469
0x1800c2415  lea     rax, aLocationcaller_6; "LocationCallerInfoHelper::ImpersonateAn"...
0x1800c241c  mov     edx, 102h; void *
0x1800c2421  mov     rcx, [rbp+68h]; this
0x1800c2425  lea     r8, aOnecoreuapDriv_45; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800c242c  mov     dword ptr [rsp+160h+var_138], ebx; wil::details *
0x1800c2430  lea     r9, aClocationmanag_1; "CLocationManager::get_DefaultLocation"
0x1800c2437  mov     [rsp+160h+var_140], rax; char *
0x1800c243c  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800c2441  lea     rcx, [rbp+60h+var_C0]; this
0x1800c2445  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1800c244a  mov     rcx, r14; pv
0x1800c244d  call    cs:__imp_CoTaskMemFree
0x1800c2453  mov     rcx, [rsp+160h+var_108+8]; this
0x1800c2458  test    rcx, rcx
0x1800c245b  jz      short loc_1800C2462
0x1800c245d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c2462  mov     eax, ebx
0x1800c2464  jmp     loc_1800C2610
0x1800c2469  lea     rcx, [rbp+60h+var_C0]; this
0x1800c246d  call    ?IsValid@CSid@ATL@@QEBA_NXZ; ATL::CSid::IsValid(void)
0x1800c2472  test    al, al
0x1800c2474  jnz     short loc_1800C2489
0x1800c2476  mov     ebx, 80070539h
0x1800c247b  lea     rax, aWilVerifyBoolS_0; "!(wil::verify_bool(sidUser.IsValid()))"
0x1800c2482  mov     edx, 103h
0x1800c2487  jmp     short loc_1800C2421
0x1800c2489  mov     rax, [r15]
0x1800c248c  lea     rcx, [rbp+60h+var_C0]; this
0x1800c2490  mov     rbx, r14
0x1800c2493  mov     rdi, [rax+18h]
0x1800c2497  call    ?Sid@CSid@ATL@@QEBAPEBGXZ; ATL::CSid::Sid(void)
0x1800c249c  mov     rdx, rax; unsigned __int16 *
0x1800c249f  lea     rcx, [rsp+160h+bstrString]; this
0x1800c24a4  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800c24a9  mov     r8, r14
0x1800c24ac  mov     rcx, r15
0x1800c24af  mov     rdx, [rax]
0x1800c24b2  mov     rax, rdi
0x1800c24b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c24ba  mov     rcx, [rsp+160h+bstrString]; bstrString
0x1800c24bf  mov     edi, eax
0x1800c24c1  shr     edi, 1Fh
0x1800c24c4  call    cs:__imp_SysFreeString
0x1800c24ca  xor     dil, 1
0x1800c24ce  jz      short loc_1800C24D5
0x1800c24d0  xor     ebx, ebx
0x1800c24d2  mov     [rsi], r14
0x1800c24d5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800c24dd  lea     rcx, [rsp+160h+var_E8]
0x1800c24e2  xorps   xmm0, xmm0
0x1800c24e5  xor     eax, eax
0x1800c24e7  movups  [rsp+160h+var_E8], xmm0
0x1800c24ec  mov     word ptr [rsp+160h+var_E8], ax
0x1800c24f1  movdqu  [rbp+60h+var_D8], xmm1
0x1800c24f6  call    ?GetCallerAppDisplayName@LocationCallerInfoHelper@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LocationCallerInfoHelper::GetCallerAppDisplayName(std::wstring &)
0x1800c24fb  test    eax, eax
0x1800c24fd  jns     short loc_1800C252B
0x1800c24ff  mov     rcx, [rbp+68h]; this
0x1800c2503  lea     r9, aClocationmanag_1; "CLocationManager::get_DefaultLocation"
0x1800c250a  mov     dword ptr [rsp+160h+var_138], eax; char *
0x1800c250e  lea     r8, aOnecoreuapDriv_45; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800c2515  lea     rax, aLocationcaller_1; "LocationCallerInfoHelper::GetCallerAppD"...
0x1800c251c  mov     edx, 10Dh; void *
0x1800c2521  mov     [rsp+160h+var_140], rax; char *
0x1800c2526  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800c252b  mov     eax, cs:dword_1801DDF30
0x1800c2531  cmp     eax, 4
0x1800c2534  jbe     short loc_1800C259E
0x1800c2536  mov     rdx, 200000000000h
0x1800c2540  lea     rcx, dword_1801DDF30
0x1800c2547  call    _tlgKeywordOn
0x1800c254c  test    al, al
0x1800c254e  jz      short loc_1800C259E
0x1800c2550  lea     rcx, [rsp+160h+var_E8]
0x1800c2555  mov     [rsp+160h+var_F8], 1000000h
0x1800c255e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c2563  mov     [rsp+160h+var_118], rax
0x1800c2568  lea     rdx, dword_1801AE444
0x1800c256f  xor     eax, eax
0x1800c2571  cmp     [rsi], rax
0x1800c2574  setz    al
0x1800c2577  mov     dword ptr [rsp+160h+bstrString], eax
0x1800c257b  lea     rax, [rsp+160h+var_F8]
0x1800c2580  mov     qword ptr [rsp+160h+var_130], rax
0x1800c2585  lea     rax, [rsp+160h+var_118]
0x1800c258a  mov     [rsp+160h+var_138], rax
0x1800c258f  lea     rax, [rsp+160h+bstrString]
0x1800c2594  mov     [rsp+160h+var_140], rax
0x1800c2599  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800c259e  cmp     qword ptr [rsi], 0
0x1800c25a2  jz      short loc_1800C25E3
0x1800c25a4  mov     eax, cs:dword_1801DDEF8
0x1800c25aa  cmp     eax, 4
0x1800c25ad  jbe     short loc_1800C25E3
0x1800c25af  mov     rcx, [rsi]
0x1800c25b2  lea     rdx, word_1801AE172
0x1800c25b9  mov     rax, [rcx+8]
0x1800c25bd  mov     [rsp+160h+var_118], rax
0x1800c25c2  mov     rax, [rcx]
0x1800c25c5  mov     [rsp+160h+var_F8], rax
0x1800c25ca  lea     rax, [rsp+160h+var_118]
0x1800c25cf  mov     [rsp+160h+var_138], rax
0x1800c25d4  lea     rax, [rsp+160h+var_F8]
0x1800c25d9  mov     [rsp+160h+var_140], rax
0x1800c25de  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800c25e3  lea     rcx, [rsp+160h+var_E8]
0x1800c25e8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c25ed  lea     rcx, [rbp+60h+var_C0]; this
0x1800c25f1  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1800c25f6  mov     rcx, rbx; pv
0x1800c25f9  call    cs:__imp_CoTaskMemFree
0x1800c25ff  mov     rcx, [rsp+160h+var_108+8]; this
0x1800c2604  test    rcx, rcx
0x1800c2607  jz      short loc_1800C260E
0x1800c2609  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c260e  xor     eax, eax
0x1800c2610  mov     rcx, [rbp+60h+var_40]
0x1800c2614  xor     rcx, rsp; StackCookie
0x1800c2617  call    __security_check_cookie
0x1800c261c  add     rsp, 138h
0x1800c2623  pop     r15
0x1800c2625  pop     r14
0x1800c2627  pop     rdi
0x1800c2628  pop     rsi
0x1800c2629  pop     rbx
0x1800c262a  pop     rbp
0x1800c262b  retn
```
