# UsageAndQualityInsights::Utilities::GetUTCSideloadDirectoryPath(void)

- ea: `0x180022910`
- end: `0x180022aee`
- name: `?GetUTCSideloadDirectoryPath@Utilities@UsageAndQualityInsights@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `478`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800e55e8`

## callees

- `0x1800033d0`
- `0x180003850`
- `0x180003fac`
- `0x180004f6c`
- `0x180004fd4`
- `0x18000a874`
- `0x18000eee0`
- `0x180012dd4`
- `0x180016628`
- `0x180016d2c`
- `0x180019794`
- `0x1800215a4`
- `0x180022910`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180022a63`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180022a63`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002297b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002297b`

## string_xrefs

- `0x1800229e7`: `%PROGRAMDATA%\Microsoft\Diagnosis\MetricSettings`
- `0x1800229c6`: `%PROGRAMDATA%\Microsoft\Diagnosis\Sideload`
- `0x180022aa7`: `onecore\base\usageandqualityinsights\service\lib\utilities\utilities.cpp`

## pseudocode

```c
__int64 __fastcall UsageAndQualityInsights::Utilities::GetUTCSideloadDirectoryPath(__int64 a1)
{
  unsigned __int64 v2; // rbx
  const char *v3; // r9
  int LastError; // eax
  _QWORD *v5; // rax
  __int64 v6; // r8
  void **v7; // rdi
  size_t v8; // rbx
  WINBOOL fPending[4]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v11[32]; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *(_QWORD *)fPending = a1;
  v2 = -1;
  if ( dword_18015A3F0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18015A3F0);
    if ( dword_18015A3F0 == -1 )
    {
      atexit(UsageAndQualityInsights::Utilities::GetUTCSideloadDirectoryPath_::_2_::_dynamic_atexit_destructor_for__s_utcSideloadDirectoryPath__);
      Init_thread_footer(&dword_18015A3F0);
    }
  }
  fPending[0] = 0;
  if ( __std_init_once_begin_initialize(&stru_18015A3F8, 0, fPending, 0) )
  {
    if ( fPending[0] )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::GetImpl'::`2'::impl) )
      {
        v5 = (_QWORD *)wil::ExpandEnvironmentStringsW<std::wstring,256>(
                         v11,
                         L"%PROGRAMDATA%\\Microsoft\\Diagnosis\\MetricSettings");
        if ( v5[3] > 7u )
          v5 = (_QWORD *)*v5;
        do
          ++v2;
        while ( *((_WORD *)v5 + v2) );
      }
      else
      {
        v5 = (_QWORD *)wil::ExpandEnvironmentStringsW<std::wstring,256>(
                         v11,
                         L"%PROGRAMDATA%\\Microsoft\\Diagnosis\\Sideload");
        if ( v5[3] > 7u )
          v5 = (_QWORD *)*v5;
        do
          ++v2;
        while ( *((_WORD *)v5 + v2) );
      }
      if ( v2 > qword_180159288 )
      {
        ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
          &qword_180159270,
          v2,
          v6,
          v5);
      }
      else
      {
        v7 = &qword_180159270;
        if ( (unsigned __int64)qword_180159288 > 7 )
          v7 = (void **)qword_180159270;
        qword_180159280 = v2;
        v8 = 2 * v2;
        memmove_0(v7, v5, v8);
        *(_WORD *)((char *)v7 + v8) = 0;
      }
      std::wstring::~wstring(v11);
      InitOnceComplete(&stru_18015A3F8, 0, 0);
    }
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v3);
  }
  if ( LastError < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\utilities\\utilities.cpp",
      (const char *)(unsigned int)LastError,
      fPending[0]);
  std::wstring::wstring(a1, &qword_180159270);
  return a1;
}

```

## disassembly

```asm
0x180022910  mov     [rsp+arg_8], rbx
0x180022915  mov     [rsp+arg_10], rbp
0x18002291a  push    rsi
0x18002291b  push    rdi
0x18002291c  push    r14
0x18002291e  sub     rsp, 60h
0x180022922  mov     rax, cs:__security_cookie
0x180022929  xor     rax, rsp
0x18002292c  mov     [rsp+78h+var_28], rax
0x180022931  mov     rsi, rcx
0x180022934  mov     qword ptr [rsp+78h+fPending], rcx
0x180022939  xor     ebp, ebp
0x18002293b  mov     ecx, cs:_tls_index
0x180022941  mov     rax, gs:58h
0x18002294a  mov     edx, 4
0x18002294f  mov     rax, [rax+rcx*8]
0x180022953  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180022957  mov     eax, [rdx+rax]
0x18002295a  cmp     cs:dword_18015A3F0, eax
0x180022960  jg      loc_180022AB9
0x180022966  mov     [rsp+78h+fPending], ebp; int
0x18002296a  xor     r9d, r9d; lpContext
0x18002296d  lea     r8, [rsp+78h+fPending]; fPending
0x180022972  xor     edx, edx; dwFlags
0x180022974  lea     rcx, stru_18015A3F8; lpInitOnce
0x18002297b  call    cs:__imp___std_init_once_begin_initialize
0x180022981  lea     r14, qword_180159270
0x180022988  test    eax, eax
0x18002298a  jnz     short loc_1800229A7
0x18002298c  mov     rcx, [rsp+78h]; this
0x180022991  lea     r8, aWil; "wil"
0x180022998  mov     edx, 37Ah; void *
0x18002299d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800229a2  jmp     loc_180022A6B
0x1800229a7  cmp     [rsp+78h+fPending], ebp
0x1800229ab  jz      loc_180022A69
0x1800229b1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UtcExtendedMetricsSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UtcExtendedMetricsSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport> `wil::Feature<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::GetImpl(void)'::`2'::impl
0x1800229b8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UtcExtendedMetricsSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::__private_IsEnabled(void)
0x1800229bd  lea     rcx, [rsp+78h+var_48]
0x1800229c2  test    al, al
0x1800229c4  jnz     short loc_1800229E7
0x1800229c6  lea     rdx, aProgramdataMic; "%PROGRAMDATA%\\Microsoft\\Diagnosis\\Si"...
0x1800229cd  call    ??$ExpandEnvironmentStringsW@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0BAA@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; wil::ExpandEnvironmentStringsW<std::wstring,256>(wchar_t const *)
0x1800229d2  cmp     qword ptr [rax+18h], 7
0x1800229d7  jbe     short loc_1800229DC
0x1800229d9  mov     rax, [rax]
0x1800229dc  inc     rbx
0x1800229df  cmp     [rax+rbx*2], bp
0x1800229e3  jnz     short loc_1800229DC
0x1800229e5  jmp     short loc_180022A06
0x1800229e7  lea     rdx, aProgramdataMic_0; "%PROGRAMDATA%\\Microsoft\\Diagnosis\\Me"...
0x1800229ee  call    ??$ExpandEnvironmentStringsW@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0BAA@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; wil::ExpandEnvironmentStringsW<std::wstring,256>(wchar_t const *)
0x1800229f3  cmp     qword ptr [rax+18h], 7
0x1800229f8  jbe     short loc_1800229FD
0x1800229fa  mov     rax, [rax]
0x1800229fd  inc     rbx
0x180022a00  cmp     [rax+rbx*2], bp
0x180022a04  jnz     short loc_1800229FD
0x180022a06  mov     rcx, cs:qword_180159288
0x180022a0d  cmp     rbx, rcx
0x180022a10  ja      short loc_180022A3F
0x180022a12  mov     rdi, r14
0x180022a15  cmp     rcx, 7
0x180022a19  cmova   rdi, cs:qword_180159270
0x180022a21  mov     cs:qword_180159280, rbx
0x180022a28  add     rbx, rbx
0x180022a2b  mov     r8, rbx; Size
0x180022a2e  mov     rdx, rax; Src
0x180022a31  mov     rcx, rdi; void *
0x180022a34  call    memmove_0
0x180022a39  mov     [rbx+rdi], bp
0x180022a3d  jmp     short loc_180022A4D
0x180022a3f  mov     r9, rax
0x180022a42  mov     rdx, rbx
0x180022a45  mov     rcx, r14
0x180022a48  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x180022a4d  lea     rcx, [rsp+78h+var_48]; void *
0x180022a52  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022a57  xor     r8d, r8d; lpContext
0x180022a5a  xor     edx, edx; dwFlags
0x180022a5c  lea     rcx, stru_18015A3F8; lpInitOnce
0x180022a63  call    cs:__imp_InitOnceComplete
0x180022a69  mov     eax, ebp
0x180022a6b  test    eax, eax
0x180022a6d  js      short loc_180022A9F
0x180022a6f  mov     rdx, r14
0x180022a72  mov     rcx, rsi
0x180022a75  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180022a7a  mov     rax, rsi
0x180022a7d  mov     rcx, [rsp+78h+var_28]
0x180022a82  xor     rcx, rsp; StackCookie
0x180022a85  call    __security_check_cookie
0x180022a8a  lea     r11, [rsp+78h+var_18]
0x180022a8f  mov     rbx, [r11+28h]
0x180022a93  mov     rbp, [r11+30h]
0x180022a97  mov     rsp, r11
0x180022a9a  pop     r14
0x180022a9c  pop     rdi
0x180022a9d  pop     rsi
0x180022a9e  retn
0x180022a9f  mov     rcx, [rsp+78h]; this
0x180022aa4  mov     r9d, eax; char *
0x180022aa7  lea     r8, aOnecoreBaseUsa_8; "onecore\\base\\usageandqualityinsights"...
0x180022aae  mov     edx, 32h ; '2'; void *
0x180022ab3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022ab9  lea     rcx, dword_18015A3F0
0x180022ac0  call    _Init_thread_header
0x180022ac5  cmp     cs:dword_18015A3F0, ebx
0x180022acb  jnz     loc_180022966
0x180022ad1  lea     rcx, _UsageAndQualityInsights__Utilities__GetUTCSideloadDirectoryPath____2____dynamic_atexit_destructor_for__s_utcSideloadDirectoryPath__; void (__cdecl *)()
0x180022ad8  call    atexit
0x180022add  lea     rcx, dword_18015A3F0
0x180022ae4  call    _Init_thread_footer
0x180022ae9  jmp     loc_180022966
```
