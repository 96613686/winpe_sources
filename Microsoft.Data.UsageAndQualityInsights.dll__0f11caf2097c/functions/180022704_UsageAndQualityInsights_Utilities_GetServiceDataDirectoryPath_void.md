# UsageAndQualityInsights::Utilities::GetServiceDataDirectoryPath(void)

- ea: `0x180022704`
- end: `0x1800228a7`
- name: `?GetServiceDataDirectoryPath@Utilities@UsageAndQualityInsights@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `419`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004f4ac`
- `0x1800e55e8`
- `0x1800f5308`

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
- `0x180019794`
- `0x1800215a4`
- `0x180022704`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180022821`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180022821`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180022766`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180022766`

## string_xrefs

- `0x180022860`: `onecore\base\usageandqualityinsights\service\lib\utilities\utilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UsageAndQualityInsights::Utilities::GetServiceDataDirectoryPath(__int64 a1)
{
  unsigned __int64 v2; // rbx
  const char *v3; // r9
  int LastError; // eax
  _QWORD *v5; // rax
  __int64 v6; // r8
  void **v7; // rdi
  size_t v8; // rbx
  WINBOOL fPending[4]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v11[32]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *(_QWORD *)fPending = a1;
  v2 = -1;
  if ( dword_18015A3E0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18015A3E0);
    if ( dword_18015A3E0 == -1 )
    {
      atexit(UsageAndQualityInsights::Utilities::GetServiceDataDirectoryPath_::_2_::_dynamic_atexit_destructor_for__s_dataDirectoryPath__);
      Init_thread_footer(&dword_18015A3E0);
    }
  }
  fPending[0] = 0;
  if ( __std_init_once_begin_initialize(&InitOnce, 0, fPending, 0) )
  {
    if ( fPending[0] )
    {
      v5 = (_QWORD *)wil::ExpandEnvironmentStringsW<std::wstring,256>(v11, L"%LOCALAPPDATA%\\UsageAndQualityInsights");
      if ( v5[3] > 7u )
        v5 = (_QWORD *)*v5;
      do
        ++v2;
      while ( *((_WORD *)v5 + v2) );
      if ( v2 > qword_1801592A8 )
      {
        ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
          &qword_180159290,
          v2,
          v6,
          v5);
      }
      else
      {
        v7 = &qword_180159290;
        if ( (unsigned __int64)qword_1801592A8 > 7 )
          v7 = (void **)qword_180159290;
        qword_1801592A0 = v2;
        v8 = 2 * v2;
        memmove_0(v7, v5, v8);
        *(_WORD *)((char *)v7 + v8) = 0;
      }
      std::wstring::~wstring(v11);
      InitOnceComplete(&InitOnce, 0, 0);
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
      (void *)0x1E,
      (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\utilities\\utilities.cpp",
      (const char *)(unsigned int)LastError,
      fPending[0]);
  std::wstring::wstring(a1, &qword_180159290);
  return a1;
}

```

## disassembly

```asm
0x180022704  push    rbx
0x180022706  push    rbp
0x180022707  push    rsi
0x180022708  push    rdi
0x180022709  sub     rsp, 68h
0x18002270d  mov     rax, cs:__security_cookie
0x180022714  xor     rax, rsp
0x180022717  mov     [rsp+88h+var_38], rax
0x18002271c  mov     rsi, rcx
0x18002271f  mov     qword ptr [rsp+88h+fPending], rcx
0x180022724  xor     ebp, ebp
0x180022726  mov     ecx, cs:_tls_index
0x18002272c  mov     rax, gs:58h
0x180022735  mov     edx, 4
0x18002273a  mov     rax, [rax+rcx*8]
0x18002273e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180022742  mov     eax, [rdx+rax]
0x180022745  cmp     cs:dword_18015A3E0, eax
0x18002274b  jg      loc_180022872
0x180022751  mov     [rsp+88h+fPending], ebp; int
0x180022755  xor     r9d, r9d; lpContext
0x180022758  lea     r8, [rsp+88h+fPending]; fPending
0x18002275d  xor     edx, edx; dwFlags
0x18002275f  lea     rcx, InitOnce; lpInitOnce
0x180022766  call    cs:__imp___std_init_once_begin_initialize
0x18002276c  test    eax, eax
0x18002276e  jnz     short loc_18002278E
0x180022770  mov     rcx, [rsp+88h]; this
0x180022778  lea     r8, aWil; "wil"
0x18002277f  mov     edx, 37Ah; void *
0x180022784  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180022789  jmp     loc_180022829
0x18002278e  cmp     [rsp+88h+fPending], ebp
0x180022792  jz      loc_180022827
0x180022798  lea     rdx, aLocalappdataUs; "%LOCALAPPDATA%\\UsageAndQualityInsights"
0x18002279f  lea     rcx, [rsp+88h+var_58]
0x1800227a4  call    ??$ExpandEnvironmentStringsW@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0BAA@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; wil::ExpandEnvironmentStringsW<std::wstring,256>(wchar_t const *)
0x1800227a9  cmp     qword ptr [rax+18h], 7
0x1800227ae  jbe     short loc_1800227B3
0x1800227b0  mov     rax, [rax]
0x1800227b3  inc     rbx
0x1800227b6  cmp     [rax+rbx*2], bp
0x1800227ba  jnz     short loc_1800227B3
0x1800227bc  mov     rcx, cs:qword_1801592A8
0x1800227c3  cmp     rbx, rcx
0x1800227c6  ja      short loc_1800227F9
0x1800227c8  lea     rdi, qword_180159290
0x1800227cf  cmp     rcx, 7
0x1800227d3  cmova   rdi, cs:qword_180159290
0x1800227db  mov     cs:qword_1801592A0, rbx
0x1800227e2  add     rbx, rbx
0x1800227e5  mov     r8, rbx; Size
0x1800227e8  mov     rdx, rax; Src
0x1800227eb  mov     rcx, rdi; void *
0x1800227ee  call    memmove_0
0x1800227f3  mov     [rbx+rdi], bp
0x1800227f7  jmp     short loc_18002280B
0x1800227f9  mov     r9, rax
0x1800227fc  mov     rdx, rbx
0x1800227ff  lea     rcx, qword_180159290
0x180022806  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x18002280b  lea     rcx, [rsp+88h+var_58]; void *
0x180022810  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022815  xor     r8d, r8d; lpContext
0x180022818  xor     edx, edx; dwFlags
0x18002281a  lea     rcx, InitOnce; lpInitOnce
0x180022821  call    cs:__imp_InitOnceComplete
0x180022827  mov     eax, ebp
0x180022829  test    eax, eax
0x18002282b  js      short loc_180022855
0x18002282d  lea     rdx, qword_180159290
0x180022834  mov     rcx, rsi
0x180022837  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002283c  mov     rax, rsi
0x18002283f  mov     rcx, [rsp+88h+var_38]
0x180022844  xor     rcx, rsp; StackCookie
0x180022847  call    __security_check_cookie
0x18002284c  add     rsp, 68h
0x180022850  pop     rdi
0x180022851  pop     rsi
0x180022852  pop     rbp
0x180022853  pop     rbx
0x180022854  retn
0x180022855  mov     rcx, [rsp+88h]; this
0x18002285d  mov     r9d, eax; char *
0x180022860  lea     r8, aOnecoreBaseUsa_8; "onecore\\base\\usageandqualityinsights"...
0x180022867  mov     edx, 1Eh; void *
0x18002286c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022872  lea     rcx, dword_18015A3E0
0x180022879  call    _Init_thread_header
0x18002287e  cmp     cs:dword_18015A3E0, ebx
0x180022884  jnz     loc_180022751
0x18002288a  lea     rcx, _UsageAndQualityInsights__Utilities__GetServiceDataDirectoryPath____2____dynamic_atexit_destructor_for__s_dataDirectoryPath__; void (__cdecl *)()
0x180022891  call    atexit
0x180022896  lea     rcx, dword_18015A3E0
0x18002289d  call    _Init_thread_footer
0x1800228a2  jmp     loc_180022751
```
