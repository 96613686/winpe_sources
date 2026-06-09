# EffectiveWebAccountContext::CreateForCDPActivityStoreInfo(EffectiveUserContext const &,std::shared_ptr<ICDPActivityStoreInfo> const &,ushort const *)

- ea: `0x18001527c`
- end: `0x1800156e6`
- name: `?CreateForCDPActivityStoreInfo@EffectiveWebAccountContext@@SA?AV1@AEBVEffectiveUserContext@@AEBV?$shared_ptr@VICDPActivityStoreInfo@@@std@@PEBG@Z`
- size: `1130`
- prototype: `__int64 __fastcall(EffectiveWebAccountContext *this)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014b7c`

## callees

- `0x18000e84c`
- `0x18000e904`
- `0x18000f8dc`
- `0x1800151d4`
- `0x18001527c`
- `0x180015d58`
- `0x180015dbc`
- `0x180016cf4`
- `0x180019720`
- `0x1800219e0`
- `0x1800233f0`
- `0x1800238d0`
- `0x180023fd4`
- `0x180024e90`
- `0x18002e010`
- `0x18002ec7c`
- `0x180054c90`
- `0x180063ba0`
- `0x1800b3b58`
- `0x1801201a0`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001555b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800156df`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001555b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800156df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015545`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015545`

## string_xrefs

- `0x1800153da`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x18001558e`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
EffectiveWebAccountContext *__fastcall EffectiveWebAccountContext::CreateForCDPActivityStoreInfo(
        EffectiveWebAccountContext *this,
        __int64 a2,
        _QWORD *a3,
        const WCHAR *a4)
{
  const char *v8; // rax
  __int64 v9; // rax
  void **v10; // r8
  __int64 ObjectFactory; // rax
  __int64 v12; // rdi
  void (__fastcall *v13)(__int64, __int64 **, __int64, __int64); // rbx
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64); // rbx
  __int64 v20; // r14
  unsigned __int8 *v21; // rax
  __int64 v22; // r14
  int v23; // edx
  int v24; // ecx
  __int64 (__fastcall ***v25)(__int64, HSTRING, const WCHAR *, __int64 *); // r14
  const char *v26; // rax
  __int64 v27; // rax
  const WCHAR *v28; // rdi
  unsigned __int64 v29; // rbx
  unsigned int v30; // eax
  UINT32 v31; // edx
  HRESULT v32; // eax
  int v33; // eax
  void **v34; // r9
  int v36; // [rsp+20h] [rbp-E0h]
  __int64 v37; // [rsp+38h] [rbp-C8h] BYREF
  const WCHAR *Reserved1; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall **v40)(__int64, HSTRING, const WCHAR *, __int64 *); // [rsp+58h] [rbp-A8h]
  __int64 (__fastcall ***v41)(__int64, HSTRING, const WCHAR *, __int64 *); // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v42; // [rsp+70h] [rbp-90h] BYREF
  std::_Ref_count_base *v43; // [rsp+78h] [rbp-88h]
  __int64 *v44; // [rsp+80h] [rbp-80h] BYREF
  __int64 v45; // [rsp+88h] [rbp-78h] BYREF
  __m128i si128; // [rsp+90h] [rbp-70h]
  void *v47[3]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v48; // [rsp+B8h] [rbp-48h]
  void *v49[2]; // [rsp+C0h] [rbp-40h] BYREF
  __m128i v50; // [rsp+D0h] [rbp-30h]
  HSTRING_HEADER hstringHeader; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING string; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v53[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v54[32]; // [rsp+120h] [rbp+20h] BYREF
  PSRWLOCK SRWLock; // [rsp+140h] [rbp+40h]
  std::_Ref_count_base *v56; // [rsp+148h] [rbp+48h]
  _BYTE v57[32]; // [rsp+150h] [rbp+50h] BYREF
  HSTRING_HEADER v58; // [rsp+170h] [rbp+70h] BYREF
  __int64 v59; // [rsp+188h] [rbp+88h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  Reserved1 = a4;
  v8 = (const char *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 24LL))(*a3);
  std::string::string(v49, v8);
  v9 = Utf8StringToWideString(&v44);
  WideStringToLowerCase(v47, v9);
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v44, (const struct std::nothrow_t *)(2 * si128.m128i_i64[1] + 2));
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v44) = 0;
  std::string::_Tidy_deallocate(v49);
  v10 = v47;
  if ( v48 > 7 )
    v10 = (void **)v47[0];
  EffectiveWebAccountContext::CreateForStoreDefaultAccount(v53, a2, v10, a4);
  ObjectFactory = EffectiveUserContext::GetObjectFactory(a2);
  v12 = *(_QWORD *)ObjectFactory;
  v13 = *(void (__fastcall **)(__int64, __int64 **, __int64, __int64))(**(_QWORD **)ObjectFactory + 8LL);
  v40 = (__int64 (__fastcall **)(__int64, HSTRING, const WCHAR *, __int64 *))v53;
  v14 = EnsureMemberWithReturnType_std::shared_ptr_Windows::Internal::Storage::Cloud::Core::CloudStoreAccount__const___std::shared_ptr_Windows::Internal::Storage::Cloud::Core::CloudStoreAccount___lambda_023b433145e571973f82c66908a08866___(SRWLock);
  v13(v12, &v42, v14, 30000);
  v37 = 0;
  v15 = *v42;
  v44 = &v37;
  v45 = 0;
  si128.m128i_i8[0] = 1;
  v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v15 + 272))(v42, &v45);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x94,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
      (const char *)(unsigned int)v16,
      v36);
  if ( si128.m128i_i8[0] )
  {
    v17 = *v44;
    *v44 = v45;
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v18 = *a3;
  v19 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)*a3 + 24LL);
  v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 24LL))(v37);
  v21 = (unsigned __int8 *)v19(v18);
  v22 = v20 - (_QWORD)v21;
  do
  {
    v23 = v21[v22];
    v24 = *v21 - v23;
    if ( v24 )
      break;
    ++v21;
  }
  while ( v23 );
  if ( v24 )
  {
    EffectiveUserContext::ActivateInstance<Windows::Internal::Storage::Cloud::Broker::ICloudStoreBroker>(
      a2,
      (__int64)&v41);
    v39 = 0;
    v25 = v41;
    v40 = *v41;
    v44 = &v39;
    v45 = 0;
    si128.m128i_i8[0] = 1;
    Reserved1 = (const WCHAR *)Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v58, &Reserved1)[1].Reserved.Reserved1;
    v26 = (const char *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 24LL))(*a3);
    std::string::string(v57, v26);
    v27 = Utf8StringToWideString(v49);
    v28 = (const WCHAR *)v27;
    if ( *(_QWORD *)(v27 + 24) > 7u )
      v28 = *(const WCHAR **)v27;
    string = 0;
    v29 = -1;
    do
      ++v29;
    while ( v28[v29] );
    if ( v29 > 0xFFFFFFFF )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      JUMPOUT(0x1800156E5LL);
    }
    v30 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v29);
    v31 = v30 - 1;
    if ( (unsigned int)v29 < v30 )
      v31 = v29;
    v32 = WindowsCreateStringReference(v28, v31, &hstringHeader, &string);
    if ( v32 < 0 )
      RaiseException(v32, 1u, 0, 0);
    v33 = v40[7]((__int64)v25, string, Reserved1, &v45);
    if ( v33 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
        (const char *)(unsigned int)v33,
        v36);
    string = 0;
    if ( v50.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v49[0], (const struct std::nothrow_t *)(2 * v50.m128i_i64[1] + 2));
    v50 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v49[0]) = 0;
    std::string::_Tidy_deallocate(v57);
    v59 = 0;
    if ( si128.m128i_i8[0] )
      wil::com_ptr_t<Windows::Internal::Storage::Cloud::State::ICloudStoreStateManager,wil::err_exception_policy>::attach(
        v44,
        v45);
    v34 = v47;
    if ( v48 > 7 )
      v34 = (void **)v47[0];
    EffectiveWebAccountContext::CreateForStoreWebAccount(this, a2, v39, v34, a4);
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    if ( v41 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, HSTRING, const WCHAR *, __int64 *)))(*v41)[2])(v41);
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  else
  {
    EffectiveWebAccountContext::EffectiveWebAccountContext(this, (const struct EffectiveWebAccountContext *)v53);
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  if ( v43 )
    std::_Ref_count_base::_Decref(v43);
  if ( v56 )
    std::_Ref_count_base::_Decref(v56);
  std::wstring::~wstring(v54);
  EffectiveUserContext::~EffectiveUserContext((EffectiveUserContext *)v53);
  if ( v48 > 7 )
    std::_Deallocate<16>(v47[0], (const struct std::nothrow_t *)(2 * v48 + 2));
  return this;
}

```

## disassembly

```asm
0x18001527c  push    rbp
0x18001527e  push    rbx
0x18001527f  push    rsi
0x180015280  push    rdi
0x180015281  push    r12
0x180015283  push    r13
0x180015285  push    r14
0x180015287  push    r15
0x180015289  lea     rbp, [rsp-0A8h]
0x180015291  sub     rsp, 1A8h
0x180015298  mov     rax, cs:__security_cookie
0x18001529f  xor     rax, rsp
0x1800152a2  mov     [rbp+0E0h+var_50], rax
0x1800152a9  mov     r13, r9
0x1800152ac  mov     r15, r8
0x1800152af  mov     r12, rdx
0x1800152b2  mov     rsi, rcx
0x1800152b5  mov     [rsp+1E0h+var_1A0], rcx
0x1800152ba  mov     [rsp+1E0h+var_1A0], r9
0x1800152bf  xor     r14d, r14d
0x1800152c2  mov     rcx, [r8]
0x1800152c5  mov     rax, [rcx]
0x1800152c8  mov     rax, [rax+18h]
0x1800152cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152d1  mov     rdx, rax
0x1800152d4  lea     rcx, [rbp+0E0h+var_120]
0x1800152d8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800152dd  nop
0x1800152de  lea     rdx, [rbp+0E0h+var_120]
0x1800152e2  lea     rcx, [rbp+0E0h+var_160]
0x1800152e6  call    ?Utf8StringToWideString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; Utf8StringToWideString(std::string const &)
0x1800152eb  nop
0x1800152ec  mov     rdx, rax
0x1800152ef  lea     rcx, [rbp+0E0h+var_140]
0x1800152f3  call    ?WideStringToLowerCase@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; WideStringToLowerCase(std::wstring const &)
0x1800152f8  nop
0x1800152f9  mov     rdx, [rbp+0E0h+var_148]
0x1800152fd  cmp     rdx, 7
0x180015301  jbe     short loc_180015314
0x180015303  lea     rdx, ds:2[rdx*2]
0x18001530b  mov     rcx, [rbp+0E0h+var_160]
0x18001530f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015314  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001531c  movdqu  xmmword ptr [rbp-70h], xmm0
0x180015321  mov     word ptr [rbp+0E0h+var_160], r14w
0x180015326  lea     rcx, [rbp+0E0h+var_120]; void *
0x18001532a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001532f  lea     r8, [rbp+0E0h+var_140]
0x180015333  cmp     [rbp+0E0h+var_128], 7
0x180015338  cmova   r8, [rbp+0E0h+var_140]
0x18001533d  mov     r9, r13
0x180015340  mov     rdx, r12
0x180015343  lea     rcx, [rbp+0E0h+var_E0]
0x180015347  call    ?CreateForStoreDefaultAccount@EffectiveWebAccountContext@@CA?AV1@AEBVEffectiveUserContext@@PEBG1@Z; EffectiveWebAccountContext::CreateForStoreDefaultAccount(EffectiveUserContext const &,ushort const *,ushort const *)
0x18001534c  nop
0x18001534d  mov     rcx, r12
0x180015350  call    ?GetObjectFactory@EffectiveUserContext@@QEBAAEBV?$shared_ptr@VUserObjectFactory@Core@Cloud@Storage@Internal@Windows@@@std@@XZ; EffectiveUserContext::GetObjectFactory(void)
0x180015355  mov     rdi, [rax]
0x180015358  mov     rax, [rdi]
0x18001535b  mov     rbx, [rax+8]
0x18001535f  lea     rax, [rbp+0E0h+var_E0]
0x180015363  mov     [rsp+1E0h+var_188], rax
0x180015368  mov     rcx, [rbp+0E0h+SRWLock]; SRWLock
0x18001536c  mov     [rsp+1E0h+var_1B0], r14b
0x180015371  lea     rdx, [rcx+10h]
0x180015375  lea     r9, [rsp+1E0h+var_188]
0x18001537a  lea     r8, [rsp+1E0h+var_1B0]
0x18001537f  call    EnsureMemberWithReturnType_std__shared_ptr_Windows__Internal__Storage__Cloud__Core__CloudStoreAccount__const___std__shared_ptr_Windows__Internal__Storage__Cloud__Core__CloudStoreAccount___lambda_023b433145e571973f82c66908a08866___
0x180015384  mov     r9d, 7530h
0x18001538a  mov     r8, rax
0x18001538d  lea     rdx, [rsp+1E0h+var_170]
0x180015392  mov     rcx, rdi
0x180015395  mov     rax, rbx
0x180015398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001539d  nop
0x18001539e  mov     [rsp+1E0h+var_1A8], r14
0x1800153a3  mov     rcx, [rsp+1E0h+var_170]
0x1800153a8  mov     rax, [rcx]
0x1800153ab  lea     rdx, [rsp+1E0h+var_1A8]
0x1800153b0  mov     [rbp+0E0h+var_160], rdx
0x1800153b4  mov     [rbp+0E0h+var_158], r14
0x1800153b8  mov     [rbp+0E0h+var_150], 1
0x1800153bc  lea     rdx, [rbp+0E0h+var_158]
0x1800153c0  mov     rax, [rax+110h]
0x1800153c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153cc  mov     rcx, [rbp+0E8h]; this
0x1800153d3  test    eax, eax
0x1800153d5  jns     short loc_1800153EC
0x1800153d7  mov     r9d, eax; char *
0x1800153da  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800153e1  mov     edx, 94h; void *
0x1800153e6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800153ec  cmp     [rbp+0E0h+var_150], r14b
0x1800153f0  jz      short loc_180015412
0x1800153f2  mov     rdx, [rbp+0E0h+var_158]
0x1800153f6  mov     rax, [rbp+0E0h+var_160]
0x1800153fa  mov     rcx, [rax]
0x1800153fd  mov     [rax], rdx
0x180015400  test    rcx, rcx
0x180015403  jz      short loc_180015412
0x180015405  mov     rax, [rcx]
0x180015408  mov     rax, [rax+10h]
0x18001540c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015411  nop
0x180015412  mov     rcx, [rsp+1E0h+var_1A8]
0x180015417  mov     rdi, [r15]
0x18001541a  mov     rax, [rcx]
0x18001541d  mov     rdx, [rax+18h]
0x180015421  mov     rax, [rdi]
0x180015424  mov     rbx, [rax+18h]
0x180015428  mov     rax, rdx
0x18001542b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015430  mov     r14, rax
0x180015433  mov     rcx, rdi
0x180015436  mov     rax, rbx
0x180015439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001543e  sub     r14, rax
0x180015441  movzx   ecx, byte ptr [rax]
0x180015444  movzx   edx, byte ptr [rax+r14]
0x180015449  sub     ecx, edx
0x18001544b  jnz     short loc_180015454
0x18001544d  inc     rax
0x180015450  test    edx, edx
0x180015452  jnz     short loc_180015441
0x180015454  test    ecx, ecx
0x180015456  jnz     short loc_180015481
0x180015458  lea     rdx, [rbp+0E0h+var_E0]; struct EffectiveWebAccountContext *
0x18001545c  mov     rcx, rsi; this
0x18001545f  call    ??0EffectiveWebAccountContext@@QEAA@AEBV0@@Z; EffectiveWebAccountContext::EffectiveWebAccountContext(EffectiveWebAccountContext const &)
0x180015464  nop
0x180015465  mov     rcx, [rsp+1E0h+var_1A8]
0x18001546a  test    rcx, rcx
0x18001546d  jz      short loc_18001547C
0x18001546f  mov     rax, [rcx]
0x180015472  mov     rax, [rax+10h]
0x180015476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001547b  nop
0x18001547c  jmp     loc_18001565E
0x180015481  lea     rdx, [rsp+1E0h+var_180]
0x180015486  mov     rcx, r12
0x180015489  call    ??$ActivateInstance@UICloudStoreBroker@Broker@Cloud@Storage@Internal@Windows@@@EffectiveUserContext@@QEBA?AV?$com_ptr_t@UICloudStoreBroker@Broker@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@PEBG@Z; EffectiveUserContext::ActivateInstance<Windows::Internal::Storage::Cloud::Broker::ICloudStoreBroker>(ushort const *)
0x18001548e  nop
0x18001548f  mov     [rsp+1E0h+var_190], 0
0x180015498  mov     r14, [rsp+1E0h+var_180]
0x18001549d  mov     rax, [r14]
0x1800154a0  mov     [rsp+1E0h+var_188], rax
0x1800154a5  lea     rcx, [rsp+1E0h+var_190]
0x1800154aa  mov     [rbp+0E0h+var_160], rcx
0x1800154ae  mov     [rbp+0E0h+var_158], 0
0x1800154b6  mov     [rbp+0E0h+var_150], 1
0x1800154ba  lea     rdx, [rsp+1E0h+var_1A0]
0x1800154bf  lea     rcx, [rbp+0E0h+var_70]
0x1800154c3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800154c8  nop
0x1800154c9  mov     rax, [rax+18h]
0x1800154cd  mov     [rsp+1E0h+var_1A0], rax
0x1800154d2  mov     rcx, [r15]
0x1800154d5  mov     rax, [rcx]
0x1800154d8  mov     rax, [rax+18h]
0x1800154dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154e1  mov     rdx, rax
0x1800154e4  lea     rcx, [rbp+0E0h+var_90]
0x1800154e8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800154ed  nop
0x1800154ee  lea     rdx, [rbp+0E0h+var_90]
0x1800154f2  lea     rcx, [rbp+0E0h+var_120]
0x1800154f6  call    ?Utf8StringToWideString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; Utf8StringToWideString(std::string const &)
0x1800154fb  mov     rdi, rax
0x1800154fe  cmp     qword ptr [rax+18h], 7
0x180015503  jbe     short loc_180015508
0x180015505  mov     rdi, [rax]
0x180015508  xor     r15d, r15d
0x18001550b  mov     [rbp+0E0h+string], r15
0x18001550f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015513  inc     rbx
0x180015516  cmp     [rdi+rbx*2], r15w
0x18001551b  jnz     short loc_180015513
0x18001551d  mov     eax, 0FFFFFFFFh
0x180015522  cmp     rbx, rax
0x180015525  ja      loc_1800156D0
0x18001552b  mov     ecx, ebx; unsigned int
0x18001552d  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180015532  lea     edx, [rax-1]
0x180015535  cmp     ebx, eax
0x180015537  cmovb   edx, ebx; length
0x18001553a  lea     r9, [rbp+0E0h+string]; string
0x18001553e  lea     r8, [rbp+0E0h+hstringHeader]; hstringHeader
0x180015542  mov     rcx, rdi; sourceString
0x180015545  call    cs:__imp_WindowsCreateStringReference
0x18001554b  test    eax, eax
0x18001554d  jns     short loc_180015562
0x18001554f  xor     r9d, r9d; lpArguments
0x180015552  xor     r8d, r8d; nNumberOfArguments
0x180015555  lea     edx, [r9+1]; dwExceptionFlags
0x180015559  mov     ecx, eax; dwExceptionCode
0x18001555b  call    cs:__imp_RaiseException
0x180015561  nop
0x180015562  lea     r9, [rbp+0E0h+var_158]
0x180015566  mov     r8, [rsp+1E0h+var_1A0]
0x18001556b  mov     rdx, [rbp+0E0h+string]
0x18001556f  mov     rcx, r14
0x180015572  mov     rax, [rsp+1E0h+var_188]
0x180015577  mov     rax, [rax+38h]
0x18001557b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015580  mov     rcx, [rbp+0E8h]; this
0x180015587  test    eax, eax
0x180015589  jns     short loc_1800155A0
0x18001558b  mov     r9d, eax; char *
0x18001558e  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180015595  mov     edx, 9Fh; void *
0x18001559a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800155a0  mov     [rbp+0E0h+string], r15
0x1800155a4  mov     rdx, [rbp+0E0h+var_108]
0x1800155a8  cmp     rdx, 7
0x1800155ac  jbe     short loc_1800155BF
0x1800155ae  lea     rdx, ds:2[rdx*2]
0x1800155b6  mov     rcx, [rbp+0E0h+var_120]
0x1800155ba  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800155bf  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800155c7  movdqu  xmmword ptr [rbp-30h], xmm0
0x1800155cc  mov     word ptr [rbp+0E0h+var_120], r15w
0x1800155d1  lea     rcx, [rbp+0E0h+var_90]; void *
0x1800155d5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800155da  nop
0x1800155db  mov     [rbp+0E0h+var_58], r15
0x1800155e2  cmp     [rbp+0E0h+var_150], r15b
0x1800155e6  jz      short loc_1800155F5
0x1800155e8  mov     rdx, [rbp+0E0h+var_158]
0x1800155ec  mov     rcx, [rbp+0E0h+var_160]
0x1800155f0  call    ?attach@?$com_ptr_t@VICloudStoreStateManager@State@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXPEAVICloudStoreStateManager@State@Cloud@Storage@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::Storage::Cloud::State::ICloudStoreStateManager,wil::err_exception_policy>::attach(Windows::Internal::Storage::Cloud::State::ICloudStoreStateManager *)
0x1800155f5  lea     r9, [rbp+0E0h+var_140]
0x1800155f9  cmp     [rbp+0E0h+var_128], 7
0x1800155fe  cmova   r9, [rbp+0E0h+var_140]
0x180015603  mov     qword ptr [rsp+1E0h+var_1C0], r13
0x180015608  mov     r8, [rsp+1E0h+var_190]
0x18001560d  mov     rdx, r12
0x180015610  mov     rcx, rsi
0x180015613  call    ?CreateForStoreWebAccount@EffectiveWebAccountContext@@CA?AV1@AEBVEffectiveUserContext@@PEAUIWebAccount@Credentials@Security@Windows@@PEBG2@Z; EffectiveWebAccountContext::CreateForStoreWebAccount(EffectiveUserContext const &,Windows::Security::Credentials::IWebAccount *,ushort const *,ushort const *)
0x180015618  nop
0x180015619  mov     rcx, [rsp+1E0h+var_190]
0x18001561e  test    rcx, rcx
0x180015621  jz      short loc_180015630
0x180015623  mov     rax, [rcx]
0x180015626  mov     rax, [rax+10h]
0x18001562a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001562f  nop
0x180015630  mov     rcx, [rsp+1E0h+var_180]
0x180015635  test    rcx, rcx
0x180015638  jz      short loc_180015647
0x18001563a  mov     rax, [rcx]
0x18001563d  mov     rax, [rax+10h]
0x180015641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015646  nop
0x180015647  mov     rcx, [rsp+1E0h+var_1A8]
0x18001564c  test    rcx, rcx
0x18001564f  jz      short loc_18001565E
0x180015651  mov     rax, [rcx]
0x180015654  mov     rax, [rax+10h]
0x180015658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001565d  nop
0x18001565e  mov     rcx, [rsp+1E0h+var_168]; this
0x180015663  test    rcx, rcx
0x180015666  jz      short loc_18001566E
0x180015668  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001566d  nop
0x18001566e  mov     rcx, [rbp+0E0h+var_98]; this
0x180015672  test    rcx, rcx
0x180015675  jz      short loc_18001567C
0x180015677  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001567c  lea     rcx, [rbp+0E0h+var_C0]
0x180015680  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015685  lea     rcx, [rbp+0E0h+var_E0]; this
0x180015689  call    ??1EffectiveUserContext@@QEAA@XZ; EffectiveUserContext::~EffectiveUserContext(void)
0x18001568e  nop
0x18001568f  mov     rdx, [rbp+0E0h+var_128]
0x180015693  cmp     rdx, 7
0x180015697  jbe     short loc_1800156AA
0x180015699  lea     rdx, ds:2[rdx*2]
0x1800156a1  mov     rcx, [rbp+0E0h+var_140]
0x1800156a5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800156aa  mov     rax, rsi
0x1800156ad  mov     rcx, [rbp+0E0h+var_50]
0x1800156b4  xor     rcx, rsp; StackCookie
0x1800156b7  call    __security_check_cookie
0x1800156bc  add     rsp, 1A8h
0x1800156c3  pop     r15
0x1800156c5  pop     r14
0x1800156c7  pop     r13
0x1800156c9  pop     r12
0x1800156cb  pop     rdi
0x1800156cc  pop     rsi
0x1800156cd  pop     rbx
0x1800156ce  pop     rbp
0x1800156cf  retn
0x1800156d0  xor     r9d, r9d; lpArguments
0x1800156d3  xor     r8d, r8d; nNumberOfArguments
0x1800156d6  lea     edx, [r9+1]; dwExceptionFlags
0x1800156da  mov     ecx, 80070216h; dwExceptionCode
0x1800156df  call    cs:__imp_RaiseException
```
