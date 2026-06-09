# Windows::AI::IsolationEnvironment::Internal::IsolationEnvironmentInternalStatics::GetCallerUserSid(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800116ac`
- end: `0x180011851`
- name: `?GetCallerUserSid@IsolationEnvironmentInternalStatics@Internal@IsolationEnvironment@AI@Windows@@CAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180012140`

## callees

- `0x180002a54`
- `0x1800050cd`
- `0x18000a444`
- `0x180010148`
- `0x180010240`
- `0x1800116ac`
- `0x180013270`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001173a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001173a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001174d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001174d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180011792`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180011807`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180011792`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180011807`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800116c6`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800116c6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001171b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001171b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011745`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001177d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800117f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011745`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001177d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800117f2`

## string_xrefs

- `0x18001183f`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180011762`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentinternalstatics.cpp`
- `0x18001182a`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::AI::IsolationEnvironment::Internal::IsolationEnvironmentInternalStatics::GetCallerUserSid(
        __int64 a1)
{
  HRESULT v2; // eax
  int token_information; // eax
  void *v4; // rdi
  __int64 v5; // r8
  const char *v6; // r9
  BOOL v7; // r13d
  unsigned int LastError; // ebx
  unsigned __int64 v10; // rdx
  char *v11; // r14
  __int64 v12; // rbx
  int v13; // [rsp+20h] [rbp-20h]
  LPWSTR StringSid; // [rsp+28h] [rbp-18h] BYREF
  char v15; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  LPWSTR hMem; // [rsp+90h] [rbp+50h]
  void *Block; // [rsp+98h] [rbp+58h] BYREF

  v2 = CoImpersonateClient();
  if ( v2 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x14AA,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      (const char *)(unsigned int)v2,
      v13);
  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, -5);
  if ( token_information < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1C9B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)token_information,
      v13);
  hMem = 0;
  StringSid = 0;
  v15 = 1;
  v4 = Block;
  v7 = ConvertSidToStringSidW(*(PSID *)Block, &StringSid);
  if ( v15 )
    hMem = StringSid;
  if ( v7 )
  {
    v10 = -1;
    do
      ++v10;
    while ( hMem[v10] );
    if ( v10 > *(_QWORD *)(a1 + 24) )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
        (char **)a1,
        v10,
        v5,
        hMem);
    }
    else
    {
      if ( *(_QWORD *)(a1 + 24) <= 7u )
        v11 = (char *)a1;
      else
        v11 = *(char **)a1;
      *(_QWORD *)(a1 + 16) = v10;
      v12 = 2 * v10;
      memmove_0(v11, hMem, 2 * v10);
      *(_WORD *)&v11[v12] = 0;
    }
    if ( hMem )
      LocalFree(hMem);
    if ( v4 )
      operator delete(v4);
    CoRevertToSelf();
    return 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x6F,
                  (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentinternalstatics.cpp",
                  v6);
    if ( hMem )
      LocalFree(hMem);
    if ( v4 )
      operator delete(v4);
    CoRevertToSelf();
    return LastError;
  }
}

```

## disassembly

```asm
0x1800116ac  mov     [rsp-38h+arg_0], rbx
0x1800116b1  push    rbp
0x1800116b2  push    rsi
0x1800116b3  push    rdi
0x1800116b4  push    r12
0x1800116b6  push    r13
0x1800116b8  push    r14
0x1800116ba  push    r15
0x1800116bc  mov     rbp, rsp
0x1800116bf  sub     rsp, 40h
0x1800116c3  mov     rsi, rcx
0x1800116c6  call    cs:__imp_CoImpersonateClient
0x1800116cc  mov     rcx, [rbp+38h]; this
0x1800116d0  xor     r15d, r15d
0x1800116d3  test    eax, eax
0x1800116d5  js      loc_18001183C
0x1800116db  mov     [rbp+arg_8], 1
0x1800116df  mov     [rbp+Block], r15
0x1800116e3  lea     rdx, [r15-5]
0x1800116e7  lea     rcx, [rbp+Block]
0x1800116eb  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800116f0  mov     rcx, [rbp+38h]; this
0x1800116f4  test    eax, eax
0x1800116f6  js      loc_180011827
0x1800116fc  mov     [rbp+hMem], r15
0x180011700  lea     rax, [rbp+hMem]
0x180011704  mov     [rbp+var_20], rax
0x180011708  mov     [rbp+StringSid], r15
0x18001170c  mov     [rbp+var_10], 1
0x180011710  lea     rdx, [rbp+StringSid]; StringSid
0x180011714  mov     rdi, [rbp+Block]
0x180011718  mov     rcx, [rdi]; Sid
0x18001171b  call    cs:__imp_ConvertSidToStringSidW
0x180011721  mov     r13d, eax
0x180011724  cmp     [rbp+var_10], r15b
0x180011728  jz      short loc_180011759
0x18001172a  mov     r12, [rbp+StringSid]
0x18001172e  mov     r14, [rbp+var_20]
0x180011732  mov     r15, [r14]
0x180011735  test    r15, r15
0x180011738  jz      short loc_180011753
0x18001173a  call    cs:__imp_GetLastError
0x180011740  mov     ebx, eax
0x180011742  mov     rcx, r15; hMem
0x180011745  call    cs:__imp_LocalFree
0x18001174b  mov     ecx, ebx; dwErrCode
0x18001174d  call    cs:__imp_SetLastError
0x180011753  mov     [r14], r12
0x180011756  xor     r15d, r15d
0x180011759  test    r13d, r13d
0x18001175c  jnz     short loc_18001179C
0x18001175e  mov     rcx, [rbp+38h]; this
0x180011762  lea     r8, aOnecoreuapWind_17; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180011769  lea     edx, [r13+6Fh]; void *
0x18001176d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011772  mov     ebx, eax
0x180011774  mov     rcx, [rbp+hMem]; hMem
0x180011778  test    rcx, rcx
0x18001177b  jz      short loc_180011784
0x18001177d  call    cs:__imp_LocalFree
0x180011783  nop
0x180011784  test    rdi, rdi
0x180011787  jz      short loc_180011792
0x180011789  mov     rcx, rdi; Block
0x18001178c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011791  nop
0x180011792  call    cs:__imp_CoRevertToSelf
0x180011798  mov     eax, ebx
0x18001179a  jmp     short loc_18001180F
0x18001179c  mov     r9, [rbp+hMem]
0x1800117a0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800117a4  inc     rdx
0x1800117a7  cmp     [r9+rdx*2], r15w
0x1800117ac  jnz     short loc_1800117A4
0x1800117ae  cmp     rdx, [rsi+18h]
0x1800117b2  ja      short loc_1800117E0
0x1800117b4  cmp     qword ptr [rsi+18h], 7
0x1800117b9  jbe     short loc_1800117C0
0x1800117bb  mov     r14, [rsi]
0x1800117be  jmp     short loc_1800117C3
0x1800117c0  mov     r14, rsi
0x1800117c3  mov     [rsi+10h], rdx
0x1800117c7  lea     rbx, [rdx+rdx]
0x1800117cb  mov     r8, rbx; Size
0x1800117ce  mov     rdx, r9; Src
0x1800117d1  mov     rcx, r14; void *
0x1800117d4  call    memmove_0
0x1800117d9  mov     [rbx+r14], r15w
0x1800117de  jmp     short loc_1800117E9
0x1800117e0  mov     rcx, rsi
0x1800117e3  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x1800117e8  nop
0x1800117e9  mov     rcx, [rbp+hMem]; hMem
0x1800117ed  test    rcx, rcx
0x1800117f0  jz      short loc_1800117F9
0x1800117f2  call    cs:__imp_LocalFree
0x1800117f8  nop
0x1800117f9  test    rdi, rdi
0x1800117fc  jz      short loc_180011807
0x1800117fe  mov     rcx, rdi; Block
0x180011801  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011806  nop
0x180011807  call    cs:__imp_CoRevertToSelf
0x18001180d  xor     eax, eax
0x18001180f  mov     rbx, [rsp+40h+arg_0]
0x180011817  add     rsp, 40h
0x18001181b  pop     r15
0x18001181d  pop     r14
0x18001181f  pop     r13
0x180011821  pop     r12
0x180011823  pop     rdi
0x180011824  pop     rsi
0x180011825  pop     rbp
0x180011826  retn
0x180011827  mov     r9d, eax; char *
0x18001182a  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011831  mov     edx, 1C9Bh; void *
0x180011836  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001183c  mov     r9d, eax; char *
0x18001183f  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011846  mov     edx, 14AAh; void *
0x18001184b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
