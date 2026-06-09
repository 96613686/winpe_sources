# StoredIdentitySnapshot::CaptureIdentity(std::shared_ptr<Nexus>)

- ea: `0x180012984`
- end: `0x180012db1`
- name: `?CaptureIdentity@StoredIdentitySnapshot@@IEAAXV?$shared_ptr@VNexus@@@std@@@Z`
- size: `1069`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012e10`
- `0x180068d10`

## callees

- `0x18000737c`
- `0x18000a98c`
- `0x18000b750`
- `0x18000f07c`
- `0x180011960`
- `0x180012984`
- `0x180013b50`
- `0x1800171b0`
- `0x180017200`
- `0x180038c0c`
- `0x180038f8c`
- `0x1800408c0`
- `0x180075e60`
- `0x18008251f`
- `0x18008a400`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b1d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012b3b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012b3b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180012b76`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180012b76`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180012a16`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180012a16`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012c51`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012c51`

## string_xrefs

- `0x180012d4a`: `CaptureIdentity failed for SID %s (0x%08x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall StoredIdentitySnapshot::CaptureIdentity(__int64 a1, __int64 a2)
{
  __int64 v2; // r12
  __int64 v4; // rcx
  __int64 v5; // rax
  _WORD *v6; // r15
  unsigned __int64 v7; // rbx
  size_t v8; // rbx
  size_t v9; // rbx
  __int64 *v10; // rbx
  int LastError; // eax
  __int64 v12; // rax
  const char *v13; // r9
  __int64 v14; // r15
  PVOID v15; // r15
  __int64 v16; // r15
  wil *v17; // rcx
  __int64 v18; // r15
  PVOID v19; // r15
  __int64 v20; // r15
  _DWORD *v21; // rsi
  std::_Ref_count_base *v22; // rcx
  const char *v23; // r9
  char *v24; // [rsp+40h] [rbp-98h]
  __int64 v26; // [rsp+50h] [rbp-88h]
  __int128 v28; // [rsp+60h] [rbp-78h] BYREF
  __m128i si128; // [rsp+70h] [rbp-68h]
  _QWORD v30[5]; // [rsp+80h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v2 = a2;
  v4 = *(_QWORD *)(a1 + 208);
  try
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 32LL))(v4);
    v6 = *(_WORD **)(GetTokenSID((__int64)v30, v5) + 8);
    v28 = 0;
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    if ( v7 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    if ( v7 > 7 )
    {
      v26 = std::wstring::_Calculate_growth(v7, 7);
      v24 = (char *)std::allocator<unsigned short>::allocate(&v28, v26 + 1);
      *(_QWORD *)&v28 = v24;
      si128.m128i_i64[0] = v7;
      si128.m128i_i64[1] = v26;
      v9 = 2 * v7;
      memcpy_0(v24, v6, v9);
      *(_WORD *)&v24[v9] = 0;
    }
    else
    {
      si128.m128i_i64[0] = v7;
      si128.m128i_i64[1] = 7;
      v8 = 2 * v7;
      memcpy_0(&v28, v6, v8);
      *(_WORD *)((char *)&v28 + v8) = 0;
    }
    v10 = (__int64 *)(a1 + 48);
    if ( (__int128 *)(a1 + 48) != &v28 )
    {
      std::wstring::_Tidy_deallocate(a1 + 48);
      *(_OWORD *)v10 = v28;
      *(__m128i *)(a1 + 64) = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v28) = 0;
    }
    std::wstring::_Tidy_deallocate(&v28);
    v30[0] = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
    if ( v30[1] && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(v30) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RaiseException(LastError, 1u, 0, 0);
      __debugbreak();
    }
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 208) + 40LL))(*(_QWORD *)(a1 + 208)) )
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 208) + 32LL))(*(_QWORD *)(a1 + 208));
      if ( !SetThreadToken(0, *(HANDLE *)(v12 + 8)) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x221,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
          v13);
      v14 = CaptureLanguage(v30);
      if ( a1 + 16 != v14 )
      {
        std::wstring::_Tidy_deallocate(a1 + 16);
        *(_OWORD *)(a1 + 16) = *(_OWORD *)v14;
        *(_OWORD *)(a1 + 32) = *(_OWORD *)(v14 + 16);
        *(_QWORD *)(v14 + 16) = 0;
        *(_QWORD *)(v14 + 24) = 7;
        *(_WORD *)v14 = 0;
      }
      std::wstring::_Tidy_deallocate(v30);
      v15 = *(PVOID *)v2;
      Nexus::InitializeIfNecessary(*(PVOID *)v2);
      ProxySettings::Capture(a1 + 80, (__int64)v15 + 24);
      v16 = CaptureMarket(v30);
      if ( a1 + 176 != v16 )
      {
        std::wstring::_Tidy_deallocate(a1 + 176);
        *(_OWORD *)(a1 + 176) = *(_OWORD *)v16;
        *(_OWORD *)(a1 + 192) = *(_OWORD *)(v16 + 16);
        *(_QWORD *)(v16 + 16) = 0;
        *(_QWORD *)(v16 + 24) = 7;
        *(_WORD *)v16 = 0;
      }
      std::wstring::_Tidy_deallocate(v30);
      RevertToSelf();
    }
    else
    {
      v18 = CaptureLanguage(v30);
      if ( a1 + 16 != v18 )
      {
        std::wstring::_Tidy_deallocate(a1 + 16);
        *(_OWORD *)(a1 + 16) = *(_OWORD *)v18;
        *(_OWORD *)(a1 + 32) = *(_OWORD *)(v18 + 16);
        *(_QWORD *)(v18 + 16) = 0;
        *(_QWORD *)(v18 + 24) = 7;
        *(_WORD *)v18 = 0;
      }
      std::wstring::_Tidy_deallocate(v30);
      v19 = *(PVOID *)v2;
      Nexus::InitializeIfNecessary(*(PVOID *)v2);
      ProxySettings::Capture(a1 + 80, (__int64)v19 + 24);
      v20 = CaptureMarket(v30);
      if ( a1 + 176 != v20 )
      {
        std::wstring::_Tidy_deallocate(a1 + 176);
        *(_OWORD *)(a1 + 176) = *(_OWORD *)v20;
        *(_OWORD *)(a1 + 192) = *(_OWORD *)(v20 + 16);
        *(_QWORD *)(v20 + 16) = 0;
        *(_QWORD *)(v20 + 24) = 7;
        *(_WORD *)v20 = 0;
      }
      std::wstring::_Tidy_deallocate(v30);
    }
    v21 = (_DWORD *)(a1 + 8);
    *v21 = 0;
  }
  catch ( ... )
  {
    *(_DWORD *)(a1 + 8) = wil::ResultFromCaughtException(v17);
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\identity.cpp",
      v23);
    v21 = (_DWORD *)(a1 + 8);
    v10 = (__int64 *)(a1 + 48);
    v2 = a2;
  }
  if ( (int)*v21 < 0 )
  {
    if ( (unsigned __int64)v10[3] > 7 )
      v10 = (__int64 *)*v10;
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\identity.cpp",
      0x8Fu,
      "StoredIdentitySnapshot::CaptureIdentity",
      (wchar_t *)L"CaptureIdentity failed for SID %s (0x%08x)",
      v10,
      *v21);
  }
  v22 = *(std::_Ref_count_base **)(v2 + 8);
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
}

```

## disassembly

```asm
0x180012984  mov     [rsp+arg_10], rbx
0x180012989  mov     [rsp+arg_18], rsi
0x18001298e  push    rdi
0x18001298f  push    r12
0x180012991  push    r13
0x180012993  push    r14
0x180012995  push    r15
0x180012997  sub     rsp, 0B0h
0x18001299e  mov     rax, cs:__security_cookie
0x1800129a5  xor     rax, rsp
0x1800129a8  mov     [rsp+0D8h+var_30], rax
0x1800129b0  mov     r12, rdx
0x1800129b3  mov     rsi, rcx
0x1800129b6  mov     [rsp+0D8h+var_90], rcx
0x1800129bb  mov     [rsp+0D8h+var_80], rdx
0x1800129c0  xor     edi, edi
0x1800129c2  mov     rcx, [rcx+0D0h]
0x1800129c9  mov     rax, [rcx]
0x1800129cc  mov     rax, [rax+20h]
0x1800129d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129d5  mov     rdx, rax
0x1800129d8  lea     rcx, [rsp+0D8h+var_58]
0x1800129e0  call    ?GetTokenSID@@YA?AV?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@234@@Z; GetTokenSID(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x1800129e5  nop
0x1800129e6  mov     r15, [rax+8]
0x1800129ea  xorps   xmm0, xmm0
0x1800129ed  movups  [rsp+0D8h+var_78], xmm0
0x1800129f2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800129f6  inc     rbx
0x1800129f9  cmp     [r15+rbx*2], di
0x1800129fe  jnz     short loc_1800129F6
0x180012a00  mov     r8, 7FFFFFFFFFFFFFFEh
0x180012a0a  cmp     rbx, r8
0x180012a0d  jbe     short loc_180012A1C
0x180012a0f  lea     rcx, aStringTooLong; "string too long"
0x180012a16  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180012a1c  mov     r14d, 7
0x180012a22  cmp     rbx, r14
0x180012a25  ja      short loc_180012A4B
0x180012a27  mov     qword ptr [rsp+0D8h+var_68], rbx
0x180012a2c  mov     qword ptr [rsp+0D8h+var_68+8], r14
0x180012a31  add     rbx, rbx
0x180012a34  mov     r8, rbx; Size
0x180012a37  mov     rdx, r15; Src
0x180012a3a  lea     rcx, [rsp+0D8h+var_78]; void *
0x180012a3f  call    memcpy_0
0x180012a44  mov     word ptr [rsp+rbx+0D8h+var_78], di
0x180012a49  jmp     short loc_180012AAE
0x180012a4b  mov     rdx, r14
0x180012a4e  mov     rcx, rbx
0x180012a51  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x180012a56  mov     [rsp+0D8h+var_88], rax
0x180012a5b  lea     rdx, [rax+1]
0x180012a5f  lea     rcx, [rsp+0D8h+var_78]
0x180012a64  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x180012a69  mov     r13, rax
0x180012a6c  mov     [rsp+0D8h+var_98], rax
0x180012a71  mov     word ptr [rsp+0D8h+var_78], r13w
0x180012a77  mov     ecx, dword ptr [rsp+0D8h+var_98+2]
0x180012a7b  mov     dword ptr [rsp+0D8h+var_78+2], ecx
0x180012a7f  movzx   ecx, word ptr [rsp+0D8h+var_98+6]
0x180012a84  mov     word ptr [rsp+0D8h+var_78+6], cx
0x180012a89  mov     qword ptr [rsp+0D8h+var_68], rbx
0x180012a8e  mov     rax, [rsp+0D8h+var_88]
0x180012a93  mov     qword ptr [rsp+0D8h+var_68+8], rax
0x180012a98  add     rbx, rbx
0x180012a9b  mov     r8, rbx; Size
0x180012a9e  mov     rdx, r15; Src
0x180012aa1  mov     rcx, r13; void *
0x180012aa4  call    memcpy_0
0x180012aa9  mov     [rbx+r13], di
0x180012aae  lea     rbx, [rsi+30h]
0x180012ab2  lea     rax, [rsp+0D8h+var_78]
0x180012ab7  cmp     rbx, rax
0x180012aba  jz      short loc_180012AE8
0x180012abc  mov     rcx, rbx
0x180012abf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012ac4  movups  xmm0, [rsp+0D8h+var_78]
0x180012ac9  movups  xmmword ptr [rbx], xmm0
0x180012acc  movups  xmm1, [rsp+0D8h+var_68]
0x180012ad1  movups  xmmword ptr [rbx+10h], xmm1
0x180012ad5  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180012add  movdqu  [rsp+0D8h+var_68], xmm0
0x180012ae3  mov     word ptr [rsp+0D8h+var_78], di
0x180012ae8  lea     rcx, [rsp+0D8h+var_78]
0x180012aed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012af2  nop
0x180012af3  lea     rax, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x180012afa  mov     [rsp+0D8h+var_58], rax
0x180012b02  cmp     [rsp+0D8h+var_50], rdi
0x180012b0a  jz      short loc_180012B42
0x180012b0c  lea     rcx, [rsp+0D8h+var_58]
0x180012b14  call    ?InternalClose@?$HandleT@ULocalAllocMemBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(void)
0x180012b19  test    al, al
0x180012b1b  jnz     short loc_180012B42
0x180012b1d  call    cs:__imp_GetLastError
0x180012b23  test    eax, eax
0x180012b25  jle     short loc_180012B2F
0x180012b27  movzx   eax, ax
0x180012b2a  or      eax, 80070000h
0x180012b2f  xor     r9d, r9d; lpArguments
0x180012b32  xor     r8d, r8d; nNumberOfArguments
0x180012b35  lea     edx, [r9+1]; dwExceptionFlags
0x180012b39  mov     ecx, eax; dwExceptionCode
0x180012b3b  call    cs:__imp_RaiseException
0x180012b41  int     3; Trap to Debugger
0x180012b42  mov     rcx, [rsi+0D0h]
0x180012b49  mov     rax, [rcx]
0x180012b4c  mov     rax, [rax+28h]
0x180012b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b55  test    al, al
0x180012b57  jz      loc_180012C5C
0x180012b5d  mov     rcx, [rsi+0D0h]
0x180012b64  mov     rax, [rcx]
0x180012b67  mov     rax, [rax+20h]
0x180012b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b70  mov     rdx, [rax+8]; Token
0x180012b74  xor     ecx, ecx; Thread
0x180012b76  call    cs:__imp_SetThreadToken
0x180012b7c  mov     rcx, [rsp+0D8h]; this
0x180012b84  test    eax, eax
0x180012b86  jnz     short loc_180012B9A
0x180012b88  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\licensem"...
0x180012b8f  mov     edx, 221h; void *
0x180012b94  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180012b9a  lea     rcx, [rsp+0D8h+var_58]
0x180012ba2  call    ?CaptureLanguage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CaptureLanguage(void)
0x180012ba7  mov     r15, rax
0x180012baa  lea     r13, [rsi+10h]
0x180012bae  cmp     r13, rax
0x180012bb1  jz      short loc_180012BDA
0x180012bb3  mov     rcx, r13
0x180012bb6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012bbb  movups  xmm0, xmmword ptr [r15]
0x180012bbf  movups  xmmword ptr [r13+0], xmm0
0x180012bc4  movups  xmm1, xmmword ptr [r15+10h]
0x180012bc9  movups  xmmword ptr [r13+10h], xmm1
0x180012bce  mov     [r15+10h], rdi
0x180012bd2  mov     [r15+18h], r14
0x180012bd6  mov     [r15], di
0x180012bda  lea     rcx, [rsp+0D8h+var_58]
0x180012be2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012be7  mov     r15, [r12]
0x180012beb  mov     rcx, r15; Parameter
0x180012bee  call    ?InitializeIfNecessary@Nexus@@QEBAXXZ; Nexus::InitializeIfNecessary(void)
0x180012bf3  lea     rdx, [r15+18h]
0x180012bf7  lea     rcx, [rsi+50h]
0x180012bfb  call    ?Capture@ProxySettings@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ProxySettings::Capture(std::wstring const &)
0x180012c00  lea     rcx, [rsp+0D8h+var_58]; void *
0x180012c08  call    ?CaptureMarket@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CaptureMarket(void)
0x180012c0d  mov     r15, rax
0x180012c10  lea     r13, [rsi+0B0h]
0x180012c17  cmp     r13, rax
0x180012c1a  jz      short loc_180012C43
0x180012c1c  mov     rcx, r13
0x180012c1f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012c24  movups  xmm0, xmmword ptr [r15]
0x180012c28  movups  xmmword ptr [r13+0], xmm0
0x180012c2d  movups  xmm1, xmmword ptr [r15+10h]
0x180012c32  movups  xmmword ptr [r13+10h], xmm1
0x180012c37  mov     [r15+10h], rdi
0x180012c3b  mov     [r15+18h], r14
0x180012c3f  mov     [r15], di
0x180012c43  lea     rcx, [rsp+0D8h+var_58]
0x180012c4b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012c50  nop
0x180012c51  call    cs:__imp_RevertToSelf
0x180012c57  jmp     loc_180012D12
0x180012c5c  lea     rcx, [rsp+0D8h+var_58]
0x180012c64  call    ?CaptureLanguage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CaptureLanguage(void)
0x180012c69  mov     r15, rax
0x180012c6c  lea     r13, [rsi+10h]
0x180012c70  cmp     r13, rax
0x180012c73  jz      short loc_180012C9C
0x180012c75  mov     rcx, r13
0x180012c78  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012c7d  movups  xmm0, xmmword ptr [r15]
0x180012c81  movups  xmmword ptr [r13+0], xmm0
0x180012c86  movups  xmm1, xmmword ptr [r15+10h]
0x180012c8b  movups  xmmword ptr [r13+10h], xmm1
0x180012c90  mov     [r15+10h], rdi
0x180012c94  mov     [r15+18h], r14
0x180012c98  mov     [r15], di
0x180012c9c  lea     rcx, [rsp+0D8h+var_58]
0x180012ca4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012ca9  mov     r15, [r12]
0x180012cad  mov     rcx, r15; Parameter
0x180012cb0  call    ?InitializeIfNecessary@Nexus@@QEBAXXZ; Nexus::InitializeIfNecessary(void)
0x180012cb5  lea     rdx, [r15+18h]
0x180012cb9  lea     rcx, [rsi+50h]
0x180012cbd  call    ?Capture@ProxySettings@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ProxySettings::Capture(std::wstring const &)
0x180012cc2  lea     rcx, [rsp+0D8h+var_58]; void *
0x180012cca  call    ?CaptureMarket@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CaptureMarket(void)
0x180012ccf  mov     r15, rax
0x180012cd2  lea     r13, [rsi+0B0h]
0x180012cd9  cmp     r13, rax
0x180012cdc  jz      short loc_180012D05
0x180012cde  mov     rcx, r13
0x180012ce1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012ce6  movups  xmm0, xmmword ptr [r15]
0x180012cea  movups  xmmword ptr [r13+0], xmm0
0x180012cef  movups  xmm1, xmmword ptr [r15+10h]
0x180012cf4  movups  xmmword ptr [r13+10h], xmm1
0x180012cf9  mov     [r15+10h], rdi
0x180012cfd  mov     [r15+18h], r14
0x180012d01  mov     [r15], di
0x180012d05  lea     rcx, [rsp+0D8h+var_58]
0x180012d0d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012d12  add     rsi, 8
0x180012d16  mov     [rsi], edi
0x180012d18  jmp     short loc_180012D32
0x180012d1a  mov     rax, [rsp+0D8h+var_90]
0x180012d1f  lea     rsi, [rax+8]
0x180012d23  lea     rbx, [rax+30h]
0x180012d27  mov     r14d, 7
0x180012d2d  mov     r12, [rsp+0D8h+var_80]
0x180012d32  mov     eax, [rsi]
0x180012d34  test    eax, eax
0x180012d36  jns     short loc_180012D75
0x180012d38  cmp     [rbx+18h], r14
0x180012d3c  jbe     short loc_180012D41
0x180012d3e  mov     rbx, [rbx]
0x180012d41  mov     [rsp+0D8h+var_A8], eax
0x180012d45  mov     [rsp+0D8h+var_B0], rbx
0x180012d4a  lea     rax, aCaptureidentit; "CaptureIdentity failed for SID %s (0x%0"...
0x180012d51  mov     [rsp+0D8h+Format], rax; Format
0x180012d56  lea     r9, aStoredidentity; "StoredIdentitySnapshot::CaptureIdentity"
0x180012d5d  mov     r8d, 8Fh; unsigned int
0x180012d63  lea     rdx, aOnecoreuapEndu_34; "onecoreuap\\enduser\\winstore\\licensem"...
0x180012d6a  mov     ecx, 1; unsigned int
0x180012d6f  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180012d74  nop
0x180012d75  mov     rcx, [r12+8]; this
0x180012d7a  test    rcx, rcx
0x180012d7d  jz      short loc_180012D84
0x180012d7f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012d84  mov     rcx, [rsp+0D8h+var_30]
0x180012d8c  xor     rcx, rsp; StackCookie
0x180012d8f  call    __security_check_cookie
0x180012d94  lea     r11, [rsp+0D8h+var_28]
0x180012d9c  mov     rbx, [r11+40h]
0x180012da0  mov     rsi, [r11+48h]
0x180012da4  mov     rsp, r11
0x180012da7  pop     r15
0x180012da9  pop     r14
0x180012dab  pop     r13
0x180012dad  pop     r12
0x180012daf  pop     rdi
0x180012db0  retn
```
