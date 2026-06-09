# PhoneController::_SetPreferredCallUpgradeLine(PhoneLine const *)

- ea: `0x180049284`
- end: `0x18004954d`
- name: `?_SetPreferredCallUpgradeLine@PhoneController@@IEAAJPEBVPhoneLine@@@Z`
- size: `713`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, const struct PhoneLine *)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180031820`
- `0x18003a744`
- `0x180043690`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x1800091a8`
- `0x18000e1a4`
- `0x18002c574`
- `0x18002c580`
- `0x18003084c`
- `0x18003baf0`
- `0x180049284`
- `0x18004f30c`
- `0x18004f420`
- `0x18005354c`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180049325`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180049325`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800492b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800492d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800492b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800492d3`

## string_xrefs

- `0x1800492b6`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_SetPreferredCallUpgradeLine(PhoneController *this, const struct PhoneLine *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  BackTraceCollection *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rdx
  int v10; // eax
  BackTraceCollection *v11; // rcx
  __int64 v13; // rcx
  int AllCalls; // eax
  BackTraceCollection *v15; // rcx
  __int64 v16; // r9
  _QWORD *v17; // rbx
  int v18; // eax
  BackTraceCollection *v19; // rcx
  const struct OLITEMID *v20; // r8
  int v21; // eax
  __int64 v22; // r8
  BackTraceCollection *v23; // rcx
  int v24; // eax
  unsigned int v25; // [rsp+30h] [rbp-69h] BYREF
  void *Block[2]; // [rsp+38h] [rbp-61h] BYREF
  __int16 v27; // [rsp+48h] [rbp-51h] BYREF
  __int64 v28; // [rsp+4Ah] [rbp-4Fh]
  int v29; // [rsp+52h] [rbp-47h]
  __int16 v30; // [rsp+56h] [rbp-43h]
  GUID rguid; // [rsp+58h] [rbp-41h] BYREF
  __int64 v32; // [rsp+68h] [rbp-31h]
  OLECHAR sz[40]; // [rsp+70h] [rbp-29h] BYREF

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v4, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 771);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  Block[0] = &v27;
  Block[1] = &v27;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v27 = 0;
  if ( a2 )
  {
    rguid = *(GUID *)((char *)a2 + 88);
    StringFromGUID2(&rguid, sz, 39);
    v5 = -1;
    do
      ++v5;
    while ( sz[v5] );
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(Block) )
    {
      v7 = -2147024882;
      BackTraceCollection::Capture(v6, -2147024882);
      v8 = 779;
      v9 = 0;
LABEL_11:
      Log_HREvent_7(v7, v9, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v8);
LABEL_12:
      if ( Block[0] != &v27 )
        operator delete(Block[0]);
      return v7;
    }
  }
  v10 = ConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Set(
          *((_QWORD *)this + 61) + 1576LL,
          (__int64)Block);
  v7 = v10;
  if ( v10 < 0 )
  {
    BackTraceCollection::Capture(v11, v10);
    v8 = 782;
    v9 = 1;
    goto LABEL_11;
  }
  v13 = *((_QWORD *)this + 12);
  rguid = (GUID)_mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v32 = -1;
  AllCalls = PhoneCallStorage::GetAllCalls(v13, &rguid, 0);
  v7 = AllCalls;
  if ( AllCalls < 0 )
  {
    BackTraceCollection::Capture(v15, AllCalls);
    v16 = 786;
LABEL_17:
    Log_HREvent_7(v7, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v16);
    utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&rguid);
    goto LABEL_12;
  }
  v17 = *(_QWORD **)&rguid.Data1;
  v18 = 0;
  while ( v17 != *(_QWORD **)rguid.Data4 )
  {
    CallInfo::SetCallUpgradeState(*v17, 0);
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(*v17 + 6792LL) )
    {
      v7 = -2147024882;
      BackTraceCollection::Capture(v19, -2147024882);
      Log_HREvent_9(2147942414LL, 0, v22, 1695);
      BackTraceCollection::Capture(v23, -2147024882);
      v16 = 792;
      goto LABEL_17;
    }
    if ( a2 )
    {
      v20 = (const struct OLITEMID *)(*v17 + 2468LL);
      if ( g_ZeroOlItemId != *(_DWORD *)v20
        || *(&g_ZeroOlItemId + 1) != *(_DWORD *)(*v17 + 2472LL)
        || *(_DWORD *)(*v17 + 2476LL) )
      {
        v25 = *(_DWORD *)(*v17 + 3068LL);
        v21 = PhoneController::_GetCallUpgradeabilityState(this, &v25, v20);
        if ( v21 < 0 )
          Log_HREvent_7((unsigned int)v21, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 795);
      }
    }
    v18 = 1;
    ++v17;
  }
  if ( v18 )
  {
    v24 = (*(__int64 (__fastcall **)(PhoneController *))(*(_QWORD *)this + 872LL))(this);
    if ( v24 < 0 )
      Log_HREvent_7((unsigned int)v24, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 803);
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&rguid);
  if ( Block[0] != &v27 )
    operator delete(Block[0]);
  return 0;
}

```

## disassembly

```asm
0x180049284  mov     [rsp-8+arg_10], rbx
0x180049289  push    rbp
0x18004928a  push    rsi
0x18004928b  push    rdi
0x18004928c  push    r14
0x18004928e  push    r15
0x180049290  lea     rbp, [rsp-37h]
0x180049295  sub     rsp, 0D0h
0x18004929c  mov     rax, cs:__security_cookie
0x1800492a3  xor     rax, rsp
0x1800492a6  mov     [rbp+57h+var_30], rax
0x1800492aa  mov     rsi, rdx
0x1800492ad  mov     rdi, rcx
0x1800492b0  call    cs:__imp_GetCurrentThreadId
0x1800492b6  lea     r15, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800492bd  cmp     [rdi+0F0h], eax
0x1800492c3  jz      short loc_1800492E6
0x1800492c5  mov     r8d, 303h
0x1800492cb  mov     rdx, r15
0x1800492ce  call    Log_AssertionEvent_3
0x1800492d3  call    cs:__imp_GetCurrentThreadId
0x1800492d9  cmp     [rdi+0F0h], eax
0x1800492df  jz      short loc_1800492E6
0x1800492e1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800492e6  xor     r14d, r14d
0x1800492e9  lea     rax, [rbp+57h+var_A8]
0x1800492ed  mov     [rbp+57h+Block], rax
0x1800492f1  lea     rax, [rbp+57h+var_A8]
0x1800492f5  mov     [rbp+57h+var_B0], rax
0x1800492f9  mov     [rbp+57h+var_A6], r14
0x1800492fd  mov     [rbp+57h+var_9E], r14d
0x180049301  mov     [rbp+57h+var_9A], r14w
0x180049306  mov     [rbp+57h+var_A8], r14w
0x18004930b  test    rsi, rsi
0x18004930e  jz      short loc_180049364
0x180049310  movups  xmm0, xmmword ptr [rsi+58h]
0x180049314  lea     r8d, [r14+27h]; cchMax
0x180049318  lea     rdx, [rbp+57h+sz]; lpsz
0x18004931c  lea     rcx, [rbp+57h+rguid]; rguid
0x180049320  movdqu  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x180049325  call    cs:__imp_StringFromGUID2
0x18004932b  lea     rax, [rbp+57h+sz]
0x18004932f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180049333  inc     r8
0x180049336  cmp     [rax+r8*2], r14w
0x18004933b  jnz     short loc_180049333
0x18004933d  lea     rdx, [rbp+57h+sz]
0x180049341  lea     rcx, [rbp+57h+Block]
0x180049345  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18004934a  test    al, al
0x18004934c  jnz     short loc_180049364
0x18004934e  mov     ebx, 8007000Eh
0x180049353  mov     edx, ebx; int
0x180049355  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004935a  mov     r9d, 30Bh
0x180049360  xor     edx, edx
0x180049362  jmp     short loc_180049393
0x180049364  mov     rcx, [rdi+1E8h]
0x18004936b  lea     rdx, [rbp+57h+Block]
0x18004936f  add     rcx, 628h
0x180049376  call    ?Set@?$ConfigValue@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@@QEAAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; ConfigValue<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>::Set(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18004937b  mov     ebx, eax
0x18004937d  test    eax, eax
0x18004937f  jns     short loc_1800493BD
0x180049381  mov     edx, eax; int
0x180049383  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180049388  mov     r9d, 30Eh
0x18004938e  mov     edx, 1
0x180049393  mov     r8, r15
0x180049396  mov     ecx, ebx
0x180049398  call    Log_HREvent_7
0x18004939d  mov     rcx, [rbp+57h+Block]; Block
0x1800493a1  lea     rax, [rbp+57h+var_A8]
0x1800493a5  cmp     rcx, rax
0x1800493a8  jz      short loc_1800493B6
0x1800493aa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800493b1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800493b6  mov     eax, ebx
0x1800493b8  jmp     loc_18004952A
0x1800493bd  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800493c5  lea     rdx, [rbp+57h+rguid]
0x1800493c9  mov     rcx, [rdi+60h]
0x1800493cd  xor     r8d, r8d
0x1800493d0  movdqu  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x1800493d5  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFFh
0x1800493dd  call    ?GetAllCalls@PhoneCallStorage@@QEAAJPEAV?$vector@V?$CComPtr@VCallInfo@@@ATL@@V?$allocator@V?$CComPtr@VCallInfo@@@ATL@@@utl@@@utl@@PEAUISecurityToken@@@Z; PhoneCallStorage::GetAllCalls(utl::vector<ATL::CComPtr<CallInfo>,utl::allocator<ATL::CComPtr<CallInfo>>> *,ISecurityToken *)
0x1800493e2  mov     ebx, eax
0x1800493e4  test    eax, eax
0x1800493e6  jns     short loc_18004940F
0x1800493e8  mov     edx, eax; int
0x1800493ea  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800493ef  mov     r9d, 312h
0x1800493f5  mov     r8, r15
0x1800493f8  mov     edx, 1
0x1800493fd  mov     ecx, ebx
0x1800493ff  call    Log_HREvent_7
0x180049404  lea     rcx, [rbp+57h+rguid]
0x180049408  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18004940d  jmp     short loc_18004939D
0x18004940f  mov     rbx, qword ptr [rbp+57h+rguid.Data1]
0x180049413  mov     eax, r14d
0x180049416  cmp     rbx, qword ptr [rbp+57h+rguid.Data4]
0x18004941a  jz      loc_1800494DA
0x180049420  mov     rcx, [rbx]
0x180049423  xor     edx, edx
0x180049425  call    ?SetCallUpgradeState@CallInfo@@QEAAXW4CallUpgradeState@@@Z; CallInfo::SetCallUpgradeState(CallUpgradeState)
0x18004942a  mov     rcx, [rbx]
0x18004942d  xor     r8d, r8d
0x180049430  add     rcx, 1A88h
0x180049437  xor     edx, edx
0x180049439  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18004943e  test    al, al
0x180049440  jz      short loc_1800494AD
0x180049442  test    rsi, rsi
0x180049445  jz      short loc_18004949F
0x180049447  mov     rcx, [rbx]
0x18004944a  mov     eax, dword ptr cs:?g_ZeroOlItemId@@3UOLITEMID@@B; OLITEMID const g_ZeroOlItemId
0x180049450  lea     r8, [rcx+9A4h]; struct OLITEMID *
0x180049457  cmp     eax, [r8]
0x18004945a  jnz     short loc_180049474
0x18004945c  mov     eax, dword ptr cs:?g_ZeroOlItemId@@3UOLITEMID@@B+4; OLITEMID const g_ZeroOlItemId
0x180049462  cmp     eax, [r8+4]
0x180049466  jnz     short loc_180049474
0x180049468  mov     eax, cs:dword_18009B148
0x18004946e  cmp     eax, [r8+8]
0x180049472  jz      short loc_18004949F
0x180049474  mov     eax, [rcx+0BFCh]
0x18004947a  lea     rdx, [rbp+57h+var_C0]; unsigned int *
0x18004947e  mov     rcx, rdi; this
0x180049481  mov     [rbp+57h+var_C0], eax
0x180049484  call    ?_GetCallUpgradeabilityState@PhoneController@@IEAAJAEBIAEBUOLITEMID@@@Z; PhoneController::_GetCallUpgradeabilityState(uint const &,OLITEMID const &)
0x180049489  test    eax, eax
0x18004948b  jns     short loc_18004949F
0x18004948d  mov     r9d, 31Bh
0x180049493  mov     r8, r15
0x180049496  xor     edx, edx
0x180049498  mov     ecx, eax
0x18004949a  call    Log_HREvent_7
0x18004949f  mov     eax, 1
0x1800494a4  add     rbx, 8
0x1800494a8  jmp     loc_180049416
0x1800494ad  mov     ebx, 8007000Eh
0x1800494b2  mov     edx, ebx; int
0x1800494b4  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800494b9  xor     edx, edx
0x1800494bb  mov     r9d, 69Fh
0x1800494c1  mov     ecx, ebx
0x1800494c3  call    Log_HREvent_9
0x1800494c8  mov     edx, ebx; int
0x1800494ca  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800494cf  mov     r9d, 318h
0x1800494d5  jmp     loc_1800493F5
0x1800494da  test    eax, eax
0x1800494dc  jz      short loc_180049506
0x1800494de  mov     rax, [rdi]
0x1800494e1  mov     rcx, rdi
0x1800494e4  mov     rax, [rax+368h]
0x1800494eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800494f0  test    eax, eax
0x1800494f2  jns     short loc_180049506
0x1800494f4  mov     r9d, 323h
0x1800494fa  mov     r8, r15
0x1800494fd  xor     edx, edx
0x1800494ff  mov     ecx, eax
0x180049501  call    Log_HREvent_7
0x180049506  lea     rcx, [rbp+57h+rguid]
0x18004950a  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18004950f  mov     rcx, [rbp+57h+Block]; Block
0x180049513  lea     rax, [rbp+57h+var_A8]
0x180049517  cmp     rcx, rax
0x18004951a  jz      short loc_180049528
0x18004951c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180049523  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180049528  xor     eax, eax
0x18004952a  mov     rcx, [rbp+57h+var_30]
0x18004952e  xor     rcx, rsp; StackCookie
0x180049531  call    __security_check_cookie
0x180049536  mov     rbx, [rsp+0F0h+arg_10]
0x18004953e  add     rsp, 0D0h
0x180049545  pop     r15
0x180049547  pop     r14
0x180049549  pop     rdi
0x18004954a  pop     rsi
0x18004954b  pop     rbp
0x18004954c  retn
```
