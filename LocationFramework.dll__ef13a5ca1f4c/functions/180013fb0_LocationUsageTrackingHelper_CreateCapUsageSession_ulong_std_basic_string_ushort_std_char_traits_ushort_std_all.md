# LocationUsageTrackingHelper::CreateCapUsageSession(ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageSession> &)

- ea: `0x180013fb0`
- end: `0x1800142bd`
- name: `?CreateCapUsageSession@LocationUsageTrackingHelper@@SAJKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UICapabilityUsageSession@Management@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Z`
- size: `781`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006902c`
- `0x18006fe10`
- `0x180088c20`
- `0x1800a2370`
- `0x18011a104`

## callees

- `0x180012310`
- `0x180013fb0`
- `0x1800142c4`
- `0x18001438c`
- `0x1800143c4`
- `0x180020994`
- `0x180020c64`
- `0x18009c310`
- `0x1800a98c0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800141c4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800142a3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800142b6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800141c4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800142a3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800142b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014000`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014145`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014000`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014145`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180014029`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180014029`

## string_xrefs

- `0x180013ff9`: `Windows.Internal.CapabilityAccess.Management.CapabilityUsage`
- `0x180014050`: `onecoreuap\drivers\MobilePC\Location\Product\Common\inc\LocationUsageTrackingHelper.h`
- `0x1800141e6`: `onecoreuap\drivers\MobilePC\Location\Product\Common\inc\LocationUsageTrackingHelper.h`
- `0x18001424c`: `onecoreuap\drivers\MobilePC\Location\Product\Common\inc\LocationUsageTrackingHelper.h`
- `0x180014049`: `LocationUsageTrackingHelper::CreateCapUsageSession`
- `0x1800141df`: `LocationUsageTrackingHelper::CreateCapUsageSession`
- `0x180014245`: `LocationUsageTrackingHelper::CreateCapUsageSession`
- `0x18001403d`: `GetActivationFactory( HStringReference(RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityUsage).Get(), &usageStatics)`
- `0x1800141d3`: `usage->CreateSession(CallerProcessId, HStringReference(UserSidString.c_str()).Get(), &CamUsageSession)`
- `0x180014239`: `usageStatics->Create(HStringReference(c_szCapabilityLocation).Get(), &usage)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall LocationUsageTrackingHelper::CreateCapUsageSession(unsigned int a1, HSTRING a2, __int64 a3)
{
  HRESULT v6; // eax
  HSTRING v7; // rbx
  int ActivationFactory; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, _QWORD **); // rbx
  __int64 v14; // rax
  int v15; // eax
  _QWORD *v16; // rdi
  __int64 v17; // r13
  __int64 v18; // rdx
  const WCHAR *v19; // r14
  unsigned __int64 v20; // rbx
  unsigned int v21; // eax
  UINT32 v22; // edx
  HRESULT v23; // eax
  int v24; // eax
  _QWORD *v25; // rcx
  __int64 v26; // rcx
  _QWORD *v27; // rcx
  __int64 v28; // rcx
  _QWORD *v29; // rcx
  __int64 v30; // rcx
  wil::details *v31; // [rsp+28h] [rbp-48h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v34; // [rsp+58h] [rbp-18h] BYREF
  _QWORD *v35; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+A8h] [rbp+38h]

  string[1] = a2;
  v34 = 0;
  string[0] = 0;
  v6 = WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.Management.CapabilityUsage",
         0x3Cu,
         &hstringHeader,
         string);
  if ( v6 < 0 )
  {
    RaiseException(v6, 1u, 0, 0);
    goto LABEL_31;
  }
  v7 = string[0];
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  ActivationFactory = RoGetActivationFactory(v7, &GUID_42947746_4ea0_48c2_9274_062ed61f8daa, &v34);
  v9 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    LODWORD(v31) = ActivationFactory;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Common\\inc\\LocationUsageTrackingHelper.h",
      "LocationUsageTrackingHelper::CreateCapUsageSession",
      "GetActivationFactory( HStringReference(RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityUsage)."
      "Get(), &usageStatics)",
      v31,
      (int)hstringHeader.Reserved.Reserved1);
    v10 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
LABEL_5:
    std::wstring::_Tidy_deallocate(a2);
    return v9;
  }
  v35 = 0;
  v12 = v34;
  v13 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)v34 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &c_szCapabilityLocation);
  v15 = v13(v12, *(_QWORD *)(v14 + 24), &v35);
  v9 = v15;
  if ( v15 < 0 )
  {
    LODWORD(v31) = v15;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Common\\inc\\LocationUsageTrackingHelper.h",
      "LocationUsageTrackingHelper::CreateCapUsageSession",
      "usageStatics->Create(HStringReference(c_szCapabilityLocation).Get(), &usage)",
      v31,
      (int)hstringHeader.Reserved.Reserved1);
    v29 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
    }
    v30 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    goto LABEL_5;
  }
  v16 = v35;
  v17 = *v35;
  Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageSession>::InternalRelease(a3);
  v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v18);
  string[0] = 0;
  v20 = -1;
  do
    ++v20;
  while ( v19[v20] );
  if ( v20 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v21 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v20);
  v22 = v21 - 1;
  if ( (unsigned int)v20 < v21 )
    v22 = v20;
  v23 = WindowsCreateStringReference(v19, v22, &hstringHeader, string);
  if ( v23 < 0 )
  {
LABEL_31:
    RaiseException(v23, 1u, 0, 0);
    JUMPOUT(0x1800142BCLL);
  }
  v24 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, HSTRING, __int64))(v17 + 48))(v16, a1, string[0], a3);
  v9 = v24;
  if ( v24 < 0 )
  {
    LODWORD(v31) = v24;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Common\\inc\\LocationUsageTrackingHelper.h",
      "LocationUsageTrackingHelper::CreateCapUsageSession",
      "usage->CreateSession(CallerProcessId, HStringReference(UserSidString.c_str()).Get(), &CamUsageSession)",
      v31,
      (int)hstringHeader.Reserved.Reserved1);
    v27 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v27 + 16LL))(v27);
    }
    v28 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    goto LABEL_5;
  }
  v25 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v25 + 16LL))(v25);
  }
  v26 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  std::wstring::_Tidy_deallocate(a2);
  return 0;
}

```

## disassembly

```asm
0x180013fb0  mov     [rsp-38h+arg_18], rbx
0x180013fb5  push    rbp
0x180013fb6  push    rsi
0x180013fb7  push    rdi
0x180013fb8  push    r12
0x180013fba  push    r13
0x180013fbc  push    r14
0x180013fbe  push    r15
0x180013fc0  mov     rbp, rsp
0x180013fc3  sub     rsp, 70h
0x180013fc7  mov     rax, cs:__security_cookie
0x180013fce  xor     rax, rsp
0x180013fd1  mov     [rbp+var_8], rax
0x180013fd5  mov     r15, r8
0x180013fd8  mov     rsi, rdx
0x180013fdb  mov     r12d, ecx
0x180013fde  mov     [rbp+var_20], rdx
0x180013fe2  xor     r14d, r14d
0x180013fe5  mov     [rbp+var_18], r14
0x180013fe9  mov     [rbp+string], r14
0x180013fed  lea     r9, [rbp+string]; string
0x180013ff1  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180013ff5  lea     edx, [r14+3Ch]; length
0x180013ff9  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityUsage@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x180014000  call    cs:__imp_WindowsCreateStringReference
0x180014006  test    eax, eax
0x180014008  js      loc_180014297
0x18001400e  mov     rbx, [rbp+string]
0x180014012  lea     rcx, [rbp+var_18]
0x180014016  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001401b  lea     r8, [rbp+var_18]
0x18001401f  lea     rdx, _GUID_42947746_4ea0_48c2_9274_062ed61f8daa
0x180014026  mov     rcx, rbx
0x180014029  call    cs:__imp_RoGetActivationFactory
0x18001402f  mov     ebx, eax
0x180014031  test    eax, eax
0x180014033  jns     short loc_1800140A9
0x180014035  mov     rcx, [rbp+38h]; this
0x180014039  mov     dword ptr [rsp+70h+var_48], eax; wil::details *
0x18001403d  lea     rax, aGetactivationf_2; "GetActivationFactory( HStringReference("...
0x180014044  mov     [rsp+70h+var_50], rax; char *
0x180014049  lea     r9, aLocationusaget; "LocationUsageTrackingHelper::CreateCapU"...
0x180014050  lea     r8, aOnecoreuapDriv_84; "onecoreuap\\drivers\\MobilePC\\Location"...
0x180014057  lea     edx, [r14+22h]; void *
0x18001405b  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180014060  nop
0x180014061  mov     rcx, [rbp+var_18]
0x180014065  test    rcx, rcx
0x180014068  jz      short loc_18001407B
0x18001406a  mov     [rbp+var_18], r14
0x18001406e  mov     rax, [rcx]
0x180014071  mov     rax, [rax+10h]
0x180014075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001407a  nop
0x18001407b  mov     rcx, rsi
0x18001407e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014083  mov     eax, ebx
0x180014085  mov     rcx, [rbp+var_8]
0x180014089  xor     rcx, rsp; StackCookie
0x18001408c  call    __security_check_cookie
0x180014091  mov     rbx, [rsp+70h+arg_18]
0x180014099  add     rsp, 70h
0x18001409d  pop     r15
0x18001409f  pop     r14
0x1800140a1  pop     r13
0x1800140a3  pop     r12
0x1800140a5  pop     rdi
0x1800140a6  pop     rsi
0x1800140a7  pop     rbp
0x1800140a8  retn
0x1800140a9  mov     [rbp+var_10], r14
0x1800140ad  mov     rdi, [rbp+var_18]
0x1800140b1  mov     rax, [rdi]
0x1800140b4  mov     rbx, [rax+30h]
0x1800140b8  lea     rcx, [rbp+var_10]
0x1800140bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800140c1  lea     rdx, ?c_szCapabilityLocation@@3QEBGEB; ushort const * const c_szCapabilityLocation
0x1800140c8  lea     rcx, [rbp+hstringHeader]
0x1800140cc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800140d1  nop
0x1800140d2  lea     r8, [rbp+var_10]
0x1800140d6  mov     rdx, [rax+18h]
0x1800140da  mov     rcx, rdi
0x1800140dd  mov     rax, rbx
0x1800140e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140e5  mov     ebx, eax
0x1800140e7  test    eax, eax
0x1800140e9  js      loc_180014231
0x1800140ef  mov     rdi, [rbp+var_10]
0x1800140f3  mov     r13, [rdi]
0x1800140f6  mov     rcx, r15
0x1800140f9  call    ?InternalRelease@?$ComPtr@UICapabilityUsageSession@Management@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageSession>::InternalRelease(void)
0x1800140fe  mov     rcx, rsi
0x180014101  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180014106  mov     r14, rax
0x180014109  xor     eax, eax
0x18001410b  mov     [rbp+string], rax
0x18001410f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180014113  inc     rbx
0x180014116  cmp     [r14+rbx*2], ax
0x18001411b  jnz     short loc_180014113
0x18001411d  mov     eax, 0FFFFFFFFh
0x180014122  cmp     rbx, rax
0x180014125  ja      loc_1800141B5
0x18001412b  mov     ecx, ebx; unsigned int
0x18001412d  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180014132  lea     edx, [rax-1]
0x180014135  cmp     ebx, eax
0x180014137  cmovb   edx, ebx; length
0x18001413a  lea     r9, [rbp+string]; string
0x18001413e  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180014142  mov     rcx, r14; sourceString
0x180014145  call    cs:__imp_WindowsCreateStringReference
0x18001414b  xor     r14d, r14d
0x18001414e  test    eax, eax
0x180014150  js      loc_1800142AA
0x180014156  mov     r9, r15
0x180014159  mov     r8, [rbp+string]
0x18001415d  mov     edx, r12d
0x180014160  mov     rcx, rdi
0x180014163  mov     rax, [r13+30h]
0x180014167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001416c  mov     ebx, eax
0x18001416e  test    eax, eax
0x180014170  js      short loc_1800141CB
0x180014172  mov     rcx, [rbp+var_10]
0x180014176  test    rcx, rcx
0x180014179  jz      short loc_18001418C
0x18001417b  mov     [rbp+var_10], r14
0x18001417f  mov     rax, [rcx]
0x180014182  mov     rax, [rax+10h]
0x180014186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001418b  nop
0x18001418c  mov     rcx, [rbp+var_18]
0x180014190  test    rcx, rcx
0x180014193  jz      short loc_1800141A6
0x180014195  mov     [rbp+var_18], r14
0x180014199  mov     rax, [rcx]
0x18001419c  mov     rax, [rax+10h]
0x1800141a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141a5  nop
0x1800141a6  mov     rcx, rsi
0x1800141a9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800141ae  xor     eax, eax
0x1800141b0  jmp     loc_180014085
0x1800141b5  xor     r9d, r9d; lpArguments
0x1800141b8  xor     r8d, r8d; nNumberOfArguments
0x1800141bb  lea     edx, [r9+1]; dwExceptionFlags
0x1800141bf  mov     ecx, 80070216h; dwExceptionCode
0x1800141c4  call    cs:__imp_RaiseException
0x1800141ca  int     3; Trap to Debugger
0x1800141cb  mov     rcx, [rbp+38h]; this
0x1800141cf  mov     dword ptr [rsp+70h+var_48], eax; wil::details *
0x1800141d3  lea     rax, aUsageCreateses; "usage->CreateSession(CallerProcessId, H"...
0x1800141da  mov     [rsp+70h+var_50], rax; char *
0x1800141df  lea     r9, aLocationusaget; "LocationUsageTrackingHelper::CreateCapU"...
0x1800141e6  lea     r8, aOnecoreuapDriv_84; "onecoreuap\\drivers\\MobilePC\\Location"...
0x1800141ed  mov     edx, 27h ; '''; void *
0x1800141f2  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800141f7  nop
0x1800141f8  mov     rcx, [rbp+var_10]
0x1800141fc  test    rcx, rcx
0x1800141ff  jz      short loc_180014212
0x180014201  mov     [rbp+var_10], r14
0x180014205  mov     rax, [rcx]
0x180014208  mov     rax, [rax+10h]
0x18001420c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014211  nop
0x180014212  mov     rcx, [rbp+var_18]
0x180014216  test    rcx, rcx
0x180014219  jz      short loc_18001422C
0x18001421b  mov     [rbp+var_18], r14
0x18001421f  mov     rax, [rcx]
0x180014222  mov     rax, [rax+10h]
0x180014226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001422b  nop
0x18001422c  jmp     loc_18001407B
0x180014231  mov     rcx, [rbp+38h]; this
0x180014235  mov     dword ptr [rsp+70h+var_48], eax; wil::details *
0x180014239  lea     rax, aUsagestaticsCr; "usageStatics->Create(HStringReference(c"...
0x180014240  mov     [rsp+70h+var_50], rax; char *
0x180014245  lea     r9, aLocationusaget; "LocationUsageTrackingHelper::CreateCapU"...
0x18001424c  lea     r8, aOnecoreuapDriv_84; "onecoreuap\\drivers\\MobilePC\\Location"...
0x180014253  mov     edx, 25h ; '%'; void *
0x180014258  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18001425d  nop
0x18001425e  mov     rcx, [rbp+var_10]
0x180014262  test    rcx, rcx
0x180014265  jz      short loc_180014278
0x180014267  mov     [rbp+var_10], r14
0x18001426b  mov     rax, [rcx]
0x18001426e  mov     rax, [rax+10h]
0x180014272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014277  nop
0x180014278  mov     rcx, [rbp+var_18]
0x18001427c  test    rcx, rcx
0x18001427f  jz      short loc_180014292
0x180014281  mov     [rbp+var_18], r14
0x180014285  mov     rax, [rcx]
0x180014288  mov     rax, [rax+10h]
0x18001428c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014291  nop
0x180014292  jmp     loc_18001407B
0x180014297  xor     r9d, r9d; lpArguments
0x18001429a  xor     r8d, r8d; nNumberOfArguments
0x18001429d  lea     edx, [r9+1]; dwExceptionFlags
0x1800142a1  mov     ecx, eax; dwExceptionCode
0x1800142a3  call    cs:__imp_RaiseException
0x1800142a9  nop
0x1800142aa  xor     r9d, r9d; lpArguments
0x1800142ad  xor     r8d, r8d; nNumberOfArguments
0x1800142b0  lea     edx, [r9+1]; dwExceptionFlags
0x1800142b4  mov     ecx, eax; dwExceptionCode
0x1800142b6  call    cs:__imp_RaiseException
```
