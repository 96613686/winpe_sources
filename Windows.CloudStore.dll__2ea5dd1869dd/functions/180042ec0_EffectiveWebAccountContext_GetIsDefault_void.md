# EffectiveWebAccountContext::GetIsDefault(void)

- ea: `0x180042ec0`
- end: `0x1800431d6`
- name: `?GetIsDefault@EffectiveWebAccountContext@@QEBA_NXZ`
- size: `790`
- prototype: `bool __fastcall(EffectiveWebAccountContext *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800111a0`
- `0x180042eb0`
- `0x18005facc`
- `0x1801c1d84`

## callees

- `0x180016cf4`
- `0x180042ec0`
- `0x1800431dc`
- `0x1800433b0`
- `0x180063ba0`
- `0x1801201a0`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180043174`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004318a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800431bc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800431cf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180043174`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004318a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800431bc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800431cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180042ef1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180042ef1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042fa3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042fa3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180042f0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180042f65`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180043020`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180042f0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180042f65`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180043020`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180042fc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180042fc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800430a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043103`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800430a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043103`

## string_xrefs

- `0x18004319e`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall EffectiveWebAccountContext::GetIsDefault(EffectiveWebAccountContext *this)
{
  RTL_SRWLOCK *v2; // rbx
  __int64 v3; // r14
  __int64 v5; // r14
  __int64 v6; // rbx
  int v7; // esi
  RTL_SRWLOCK *v8; // r12
  __int64 v9; // rax
  bool v10; // si
  const WCHAR *v11; // rsi
  const WCHAR *v12; // rax
  unsigned __int64 v13; // r12
  unsigned __int64 v14; // r13
  unsigned int v15; // eax
  UINT32 v16; // edx
  HRESULT v17; // eax
  int v18; // r13d
  unsigned int v19; // eax
  UINT32 v20; // edx
  HRESULT v21; // eax
  int v22; // eax
  const WCHAR *sourceString; // [rsp+48h] [rbp-61h]
  PCWSTR sourceStringa; // [rsp+48h] [rbp-61h]
  __int64 *v25; // [rsp+50h] [rbp-59h] BYREF
  __int64 v26; // [rsp+58h] [rbp-51h] BYREF
  __int64 *v27; // [rsp+60h] [rbp-49h]
  __int64 v28; // [rsp+68h] [rbp-41h]
  __int64 v29; // [rsp+70h] [rbp-39h]
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-31h] BYREF
  HSTRING string; // [rsp+90h] [rbp-19h] BYREF
  HSTRING_HEADER v32; // [rsp+98h] [rbp-11h] BYREF
  HSTRING v33; // [rsp+B0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v2 = (RTL_SRWLOCK *)*((_QWORD *)this + 8);
  AcquireSRWLockShared(v2);
  v3 = *((_QWORD *)this + 8);
  if ( *(_DWORD *)(v3 + 52) == 1 )
  {
    if ( v2 )
      ReleaseSRWLockShared(v2);
    return 1;
  }
  if ( *(_DWORD *)(v3 + 52) != 2 )
  {
    v5 = *(_QWORD *)(v3 + 8);
    v29 = v5;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    if ( v2 )
      ReleaseSRWLockShared(v2);
    EffectiveWebAccountContext::GetTokenBrokerInternalStatics(&v25);
    EffectiveWebAccountContext::GetDefaultAccount(&v26, v25);
    v6 = v26;
    if ( !v26 )
    {
      v7 = (v5 != 0) + 1;
LABEL_12:
      v8 = (RTL_SRWLOCK *)*((_QWORD *)this + 8);
      AcquireSRWLockExclusive(v8);
      v9 = *((_QWORD *)this + 8);
      if ( !*(_DWORD *)(v9 + 52) )
        *(_DWORD *)(v9 + 52) = v7;
      v10 = *(_DWORD *)(*((_QWORD *)this + 8) + 52LL) == 1;
      if ( v8 )
        ReleaseSRWLockExclusive(v8);
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      if ( v25 )
        (*(void (__fastcall **)(__int64 *))(*v25 + 16))(v25);
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      return v10;
    }
    if ( !v5 )
    {
      v7 = 2;
      goto LABEL_12;
    }
    v27 = v25;
    v28 = *v25;
    v11 = (const WCHAR *)((char *)this + 32);
    if ( *((_QWORD *)this + 7) <= 7u )
      v12 = (const WCHAR *)((char *)this + 32);
    else
      v12 = *(const WCHAR **)v11;
    sourceString = v12;
    string = 0;
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( v12[v14] );
    if ( v14 <= 0xFFFFFFFF )
    {
      v15 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v14);
      v16 = v15 - 1;
      if ( (unsigned int)v14 < v15 )
        v16 = v14;
      v17 = WindowsCreateStringReference(sourceString, v16, &hstringHeader, &string);
      if ( v17 < 0 )
      {
        RaiseException(v17, 1u, 0, 0);
        goto LABEL_51;
      }
      sourceStringa = *(PCWSTR *)(*((_QWORD *)this + 8) + 8LL);
      if ( *((_QWORD *)this + 7) > 7u )
        v11 = *(const WCHAR **)v11;
      v33 = 0;
      do
        ++v13;
      while ( v11[v13] );
      if ( v13 <= 0xFFFFFFFF )
      {
        v18 = (int)string;
        v19 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v13);
        v20 = v19 - 1;
        if ( (unsigned int)v13 < v19 )
          v20 = v13;
        v21 = WindowsCreateStringReference(v11, v20, &v32, &v33);
        if ( v21 >= 0 )
        {
          v22 = (*(__int64 (__fastcall **)(__int64 *, __int64, HSTRING, PCWSTR))(v28 + 352))(
                  v27,
                  v6,
                  v33,
                  sourceStringa);
          if ( v22 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xFB,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
              (const char *)(unsigned int)v22,
              v18);
          v7 = 2;
          goto LABEL_12;
        }
LABEL_51:
        RaiseException(v21, 1u, 0, 0);
        JUMPOUT(0x1800431D5LL);
      }
      RaiseException(0x80070216, 1u, 0, 0);
    }
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  if ( v2 )
    ReleaseSRWLockShared(v2);
  return 0;
}

```

## disassembly

```asm
0x180042ec0  push    rbp
0x180042ec2  push    rbx
0x180042ec3  push    rsi
0x180042ec4  push    rdi
0x180042ec5  push    r12
0x180042ec7  push    r13
0x180042ec9  push    r14
0x180042ecb  push    r15
0x180042ecd  lea     rbp, [rsp-1Fh]
0x180042ed2  sub     rsp, 0C8h
0x180042ed9  mov     rax, cs:__security_cookie
0x180042ee0  xor     rax, rsp
0x180042ee3  mov     [rbp+57h+var_48], rax
0x180042ee7  mov     r15, rcx
0x180042eea  mov     rbx, [rcx+40h]
0x180042eee  mov     rcx, rbx; SRWLock
0x180042ef1  call    cs:__imp_AcquireSRWLockShared
0x180042ef7  mov     r14, [r15+40h]
0x180042efb  cmp     dword ptr [r14+34h], 1
0x180042f00  jnz     short loc_180042F33
0x180042f02  test    rbx, rbx
0x180042f05  jz      short loc_180042F11
0x180042f07  mov     rcx, rbx; SRWLock
0x180042f0a  call    cs:__imp_ReleaseSRWLockShared
0x180042f10  nop
0x180042f11  mov     al, 1
0x180042f13  mov     rcx, [rbp+57h+var_48]
0x180042f17  xor     rcx, rsp; StackCookie
0x180042f1a  call    __security_check_cookie
0x180042f1f  add     rsp, 0C8h
0x180042f26  pop     r15
0x180042f28  pop     r14
0x180042f2a  pop     r13
0x180042f2c  pop     r12
0x180042f2e  pop     rdi
0x180042f2f  pop     rsi
0x180042f30  pop     rbx
0x180042f31  pop     rbp
0x180042f32  retn
0x180042f33  cmp     dword ptr [r14+34h], 2
0x180042f38  jz      loc_180043018
0x180042f3e  mov     r14, [r14+8]
0x180042f42  mov     [rbp+57h+var_90], r14
0x180042f46  xor     edi, edi
0x180042f48  test    r14, r14
0x180042f4b  jz      short loc_180042F5D
0x180042f4d  mov     rax, [r14]
0x180042f50  mov     rcx, r14
0x180042f53  mov     rax, [rax+8]
0x180042f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f5c  nop
0x180042f5d  test    rbx, rbx
0x180042f60  jz      short loc_180042F6B
0x180042f62  mov     rcx, rbx; SRWLock
0x180042f65  call    cs:__imp_ReleaseSRWLockShared
0x180042f6b  lea     rcx, [rbp+57h+var_B0]
0x180042f6f  call    ?GetTokenBrokerInternalStatics@EffectiveWebAccountContext@@SA?AV?$com_ptr_t@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@XZ; EffectiveWebAccountContext::GetTokenBrokerInternalStatics(void)
0x180042f74  nop
0x180042f75  mov     rdx, [rbp+57h+var_B0]
0x180042f79  lea     rcx, [rbp+57h+var_A8]
0x180042f7d  call    ?GetDefaultAccount@EffectiveWebAccountContext@@SA?AV?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@PEAUITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@Z; EffectiveWebAccountContext::GetDefaultAccount(Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics *)
0x180042f82  nop
0x180042f83  mov     rbx, [rbp+57h+var_A8]
0x180042f87  test    rbx, rbx
0x180042f8a  jnz     loc_18004302E
0x180042f90  mov     rax, r14
0x180042f93  neg     rax
0x180042f96  sbb     esi, esi
0x180042f98  neg     esi
0x180042f9a  inc     esi
0x180042f9c  mov     r12, [r15+40h]
0x180042fa0  mov     rcx, r12; SRWLock
0x180042fa3  call    cs:__imp_AcquireSRWLockExclusive
0x180042fa9  mov     rax, [r15+40h]
0x180042fad  cmp     [rax+34h], edi
0x180042fb0  jnz     short loc_180042FB5
0x180042fb2  mov     [rax+34h], esi
0x180042fb5  mov     rax, [r15+40h]
0x180042fb9  cmp     dword ptr [rax+34h], 1
0x180042fbd  setz    sil
0x180042fc1  test    r12, r12
0x180042fc4  jz      short loc_180042FD0
0x180042fc6  mov     rcx, r12; SRWLock
0x180042fc9  call    cs:__imp_ReleaseSRWLockExclusive
0x180042fcf  nop
0x180042fd0  test    rbx, rbx
0x180042fd3  jz      short loc_180042FE5
0x180042fd5  mov     rax, [rbx]
0x180042fd8  mov     rcx, rbx
0x180042fdb  mov     rax, [rax+10h]
0x180042fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042fe4  nop
0x180042fe5  mov     rcx, [rbp+57h+var_B0]
0x180042fe9  test    rcx, rcx
0x180042fec  jz      short loc_180042FFB
0x180042fee  mov     rax, [rcx]
0x180042ff1  mov     rax, [rax+10h]
0x180042ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ffa  nop
0x180042ffb  test    r14, r14
0x180042ffe  jz      short loc_180043010
0x180043000  mov     rdx, [r14]
0x180043003  mov     rcx, r14
0x180043006  mov     rax, [rdx+10h]
0x18004300a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004300f  nop
0x180043010  mov     al, sil
0x180043013  jmp     loc_180042F13
0x180043018  test    rbx, rbx
0x18004301b  jz      short loc_180043027
0x18004301d  mov     rcx, rbx; SRWLock
0x180043020  call    cs:__imp_ReleaseSRWLockShared
0x180043026  nop
0x180043027  xor     al, al
0x180043029  jmp     loc_180042F13
0x18004302e  test    r14, r14
0x180043031  jz      loc_180043191
0x180043037  mov     [rbp+57h+var_C0], dil
0x18004303b  mov     rax, [rbp+57h+var_B0]
0x18004303f  mov     [rbp+57h+var_A0], rax
0x180043043  mov     rax, [rax]
0x180043046  mov     [rbp+57h+var_98], rax
0x18004304a  lea     rsi, [r15+20h]
0x18004304e  cmp     qword ptr [rsi+18h], 7
0x180043053  jbe     loc_180043155
0x180043059  mov     rax, [rsi]
0x18004305c  mov     [rbp+57h+sourceString], rax
0x180043060  mov     [rbp+57h+string], rdi
0x180043064  or      r12, 0FFFFFFFFFFFFFFFFh
0x180043068  mov     r13, r12
0x18004306b  inc     r13
0x18004306e  cmp     [rax+r13*2], di
0x180043073  jnz     short loc_18004306B
0x180043075  mov     eax, 0FFFFFFFFh
0x18004307a  cmp     r13, rax
0x18004307d  ja      loc_18004317B
0x180043083  mov     ecx, r13d; unsigned int
0x180043086  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18004308b  lea     edx, [rax-1]
0x18004308e  cmp     r13d, eax
0x180043091  cmovb   edx, r13d; length
0x180043095  lea     r9, [rbp+57h+string]; string
0x180043099  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004309d  mov     rcx, [rbp+57h+sourceString]; sourceString
0x1800430a1  call    cs:__imp_WindowsCreateStringReference
0x1800430a7  test    eax, eax
0x1800430a9  js      loc_1800431B0
0x1800430af  mov     rax, [r15+40h]
0x1800430b3  mov     rax, [rax+8]
0x1800430b7  mov     [rbp+57h+sourceString], rax
0x1800430bb  cmp     qword ptr [rsi+18h], 7
0x1800430c0  ja      loc_18004315D
0x1800430c6  mov     [rbp+57h+var_50], rdi
0x1800430ca  inc     r12
0x1800430cd  cmp     [rsi+r12*2], di
0x1800430d2  jnz     short loc_1800430CA
0x1800430d4  mov     eax, 0FFFFFFFFh
0x1800430d9  cmp     r12, rax
0x1800430dc  ja      loc_180043165
0x1800430e2  mov     r13, [rbp+57h+string]
0x1800430e6  mov     ecx, r12d; unsigned int
0x1800430e9  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800430ee  lea     edx, [rax-1]
0x1800430f1  cmp     r12d, eax
0x1800430f4  cmovb   edx, r12d; length
0x1800430f8  lea     r9, [rbp+57h+var_50]; string
0x1800430fc  lea     r8, [rbp+57h+var_68]; hstringHeader
0x180043100  mov     rcx, rsi; sourceString
0x180043103  call    cs:__imp_WindowsCreateStringReference
0x180043109  test    eax, eax
0x18004310b  js      loc_1800431C3
0x180043111  lea     rax, [rbp+57h+var_C0]
0x180043115  mov     [rsp+100h+var_D8], rax
0x18004311a  mov     qword ptr [rsp+100h+var_E0], r13; int
0x18004311f  mov     r9, [rbp+57h+sourceString]
0x180043123  mov     r8, [rbp+57h+var_50]
0x180043127  mov     rdx, rbx
0x18004312a  mov     rcx, [rbp+57h+var_A0]
0x18004312e  mov     rax, [rbp+57h+var_98]
0x180043132  mov     rax, [rax+160h]
0x180043139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004313e  mov     rcx, [rbp+5Fh]; this
0x180043142  test    eax, eax
0x180043144  js      short loc_18004319B
0x180043146  mov     al, [rbp+57h+var_C0]
0x180043149  neg     al
0x18004314b  sbb     esi, esi
0x18004314d  add     esi, 2
0x180043150  jmp     loc_180042F9C
0x180043155  mov     rax, rsi
0x180043158  jmp     loc_18004305C
0x18004315d  mov     rsi, [rsi]
0x180043160  jmp     loc_1800430C6
0x180043165  xor     r9d, r9d; lpArguments
0x180043168  xor     r8d, r8d; nNumberOfArguments
0x18004316b  lea     edx, [r9+1]; dwExceptionFlags
0x18004316f  mov     ecx, 80070216h; dwExceptionCode
0x180043174  call    cs:__imp_RaiseException
0x18004317a  nop
0x18004317b  xor     r9d, r9d; lpArguments
0x18004317e  xor     r8d, r8d; nNumberOfArguments
0x180043181  lea     edx, [r9+1]; dwExceptionFlags
0x180043185  mov     ecx, 80070216h; dwExceptionCode
0x18004318a  call    cs:__imp_RaiseException
0x180043190  int     3; Trap to Debugger
0x180043191  mov     esi, 2
0x180043196  jmp     loc_180042F9C
0x18004319b  mov     r9d, eax; char *
0x18004319e  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800431a5  mov     edx, 0FBh; void *
0x1800431aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800431b0  xor     r9d, r9d; lpArguments
0x1800431b3  xor     r8d, r8d; nNumberOfArguments
0x1800431b6  lea     edx, [r9+1]; dwExceptionFlags
0x1800431ba  mov     ecx, eax; dwExceptionCode
0x1800431bc  call    cs:__imp_RaiseException
0x1800431c2  nop
0x1800431c3  xor     r9d, r9d; lpArguments
0x1800431c6  xor     r8d, r8d; nNumberOfArguments
0x1800431c9  lea     edx, [r9+1]; dwExceptionFlags
0x1800431cd  mov     ecx, eax; dwExceptionCode
0x1800431cf  call    cs:__imp_RaiseException
```
