# VmWbemCore::ExecuteQuery(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,long,IEnumWbemClassObject * *,IWbemContext *)

- ea: `0x180230e54`
- end: `0x18023100b`
- name: `?ExecuteQuery@VmWbemCore@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JPEAPEAUIEnumWbemClassObject@@PEAUIWbemContext@@@Z`
- size: `439`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1802304a4`
- `0x180230624`

## callees

- `0x18005f0c0`
- `0x180061240`
- `0x1800663fc`
- `0x1800666b4`
- `0x180077910`
- `0x180078200`
- `0x18007845c`
- `0x18007cbc8`
- `0x18022ab78`
- `0x1802309d0`
- `0x180230e54`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180230ee6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180230ee6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180230ec8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180230ec8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180230edc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180230edc`
- `OLEAUT32!__imp_SysFreeString` at `0x180230f56`
- `OLEAUT32!__imp_SysFreeString` at `0x180230f56`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180230efa`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180230efa`

## string_xrefs

- `0x180230f7c`: `onecore\vm\common\vml\VmSecurity.h`
- `0x180230ff9`: `onecore\vm\common\vml\VmSecurity.h`
- `0x180230fc8`: `onecore\vm\common\wmimgmt\vmwbemcore.cpp`
- `0x180230fe0`: `onecore\vm\common\wmimgmt\vmwbemcore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall VmWbemCore::ExecuteQuery(_QWORD *a1, const unsigned __int16 *a2, __int64 a3, __int64 a4, int a5)
{
  const unsigned __int16 *v5; // rdi
  void *v7; // rbx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  const char *v10; // r9
  OLECHAR *v11; // rbx
  int v12; // esi
  __int64 v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // [rsp+20h] [rbp-50h]
  BSTR bstrString[2]; // [rsp+40h] [rbp-30h] BYREF
  void *TokenHandle[2]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v5 = a2;
  bstrString[0] = 0;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const unsigned __int16 **)a2;
  Vml::VmBstr::VmBstr((Vml::VmBstr *)bstrString, a2);
  if ( !a1[10] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x524,
      (unsigned int)"onecore\\vm\\common\\wmimgmt\\vmwbemcore.cpp",
      (const char *)0x80004003LL,
      v15);
  *(_OWORD *)TokenHandle = 0;
  v7 = (void *)a1[12];
  bstrString[1] = (BSTR)TokenHandle;
  TokenHandle[0] = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 0, TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1CC3,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        (const char *)LastError,
        v15);
  }
  if ( !ImpersonateLoggedOnUser(v7) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1D52,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v10);
  LOBYTE(TokenHandle[1]) = 1;
  v11 = bstrString[0];
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, BSTR, __int64))(*(_QWORD *)a1[10] + 160LL))(
          a1[10],
          a1[11],
          bstrString[0],
          288);
  if ( v12 < 0 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16391) )
    {
      v13 = std::wstring::c_str(v5);
      VmlDebugTrace(16391, L"WMI query '%ls' failedHRESULT = 0x%08lX \n", v13, (unsigned int)v12);
    }
    v14 = wil::verify_hresult<long>((unsigned int)v12);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x532,
      (unsigned int)"onecore\\vm\\common\\wmimgmt\\vmwbemcore.cpp",
      (const char *)v14,
      a5);
  }
  LOBYTE(TokenHandle[1]) = 0;
  Vml::VmImpersonator::~VmImpersonator((Vml::VmImpersonator *)TokenHandle);
  if ( v11 )
    SysFreeString(v11);
}

```

## disassembly

```asm
0x180230e54  mov     [rsp-28h+arg_10], rbx
0x180230e59  push    rbp
0x180230e5a  push    rsi
0x180230e5b  push    rdi
0x180230e5c  push    r14
0x180230e5e  push    r15
0x180230e60  mov     rbp, rsp
0x180230e63  sub     rsp, 70h
0x180230e67  mov     rax, cs:__security_cookie
0x180230e6e  xor     rax, rsp
0x180230e71  mov     [rbp+var_10], rax
0x180230e75  mov     r14, r9
0x180230e78  mov     rdi, rdx
0x180230e7b  mov     rsi, rcx
0x180230e7e  mov     r15, qword ptr [rbp+arg_20]
0x180230e82  mov     [rbp+bstrString], 0
0x180230e8a  cmp     qword ptr [rdx+18h], 7
0x180230e8f  jbe     short loc_180230E94
0x180230e91  mov     rdx, [rdx]; unsigned __int16 *
0x180230e94  lea     rcx, [rbp+bstrString]; this
0x180230e98  call    ??0VmBstr@Vml@@QEAA@PEBG@Z; Vml::VmBstr::VmBstr(ushort const *)
0x180230e9d  nop
0x180230e9e  mov     rcx, [rbp+28h]; this
0x180230ea2  cmp     qword ptr [rsi+50h], 0
0x180230ea7  jz      loc_180230FDA
0x180230ead  xorps   xmm0, xmm0
0x180230eb0  movups  xmmword ptr [rbp+TokenHandle], xmm0
0x180230eb4  mov     rbx, [rsi+60h]
0x180230eb8  lea     rax, [rbp+TokenHandle]
0x180230ebc  mov     [rbp+var_28], rax
0x180230ec0  mov     [rbp+TokenHandle], 0
0x180230ec8  call    cs:__imp_GetCurrentThread
0x180230ece  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180230ed2  xor     r8d, r8d; OpenAsSelf
0x180230ed5  lea     edx, [r8+0Ch]; DesiredAccess
0x180230ed9  mov     rcx, rax; ThreadHandle
0x180230edc  call    cs:__imp_OpenThreadToken
0x180230ee2  test    eax, eax
0x180230ee4  jnz     short loc_180230EF7
0x180230ee6  call    cs:__imp_GetLastError
0x180230eec  cmp     eax, 3F0h
0x180230ef1  jnz     loc_180230FF2
0x180230ef7  mov     rcx, rbx; hToken
0x180230efa  call    cs:__imp_ImpersonateLoggedOnUser
0x180230f00  mov     rcx, [rbp+28h]; this
0x180230f04  test    eax, eax
0x180230f06  jz      short loc_180230F7C
0x180230f08  mov     byte ptr [rbp+TokenHandle+8], 1
0x180230f0c  mov     rcx, [rsi+50h]
0x180230f10  mov     rax, [rcx]
0x180230f13  mov     [rsp+70h+var_48], r14
0x180230f18  mov     qword ptr [rsp+70h+var_50], r15; int
0x180230f1d  mov     r9d, 120h
0x180230f23  mov     rbx, [rbp+bstrString]
0x180230f27  mov     r8, rbx
0x180230f2a  mov     rdx, [rsi+58h]
0x180230f2e  mov     rax, [rax+0A0h]
0x180230f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180230f3a  mov     esi, eax
0x180230f3c  test    eax, eax
0x180230f3e  js      short loc_180230F8E
0x180230f40  mov     byte ptr [rbp+TokenHandle+8], 0
0x180230f44  lea     rcx, [rbp+TokenHandle]; this
0x180230f48  call    ??1VmImpersonator@Vml@@QEAA@XZ; Vml::VmImpersonator::~VmImpersonator(void)
0x180230f4d  nop
0x180230f4e  test    rbx, rbx
0x180230f51  jz      short loc_180230F5C
0x180230f53  mov     rcx, rbx; bstrString
0x180230f56  call    cs:__imp_SysFreeString
0x180230f5c  mov     rcx, [rbp+var_10]
0x180230f60  xor     rcx, rsp; StackCookie
0x180230f63  call    __security_check_cookie
0x180230f68  mov     rbx, [rsp+70h+arg_10]
0x180230f70  add     rsp, 70h
0x180230f74  pop     r15
0x180230f76  pop     r14
0x180230f78  pop     rdi
0x180230f79  pop     rsi
0x180230f7a  pop     rbp
0x180230f7b  retn
0x180230f7c  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x180230f83  mov     edx, 1D52h; void *
0x180230f88  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180230f8e  mov     ebx, 4007h
0x180230f93  mov     ecx, ebx
0x180230f95  call    VmlIsDebugTraceEnabled
0x180230f9a  test    eax, eax
0x180230f9c  jz      short loc_180230FBA
0x180230f9e  mov     rcx, rdi
0x180230fa1  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180230fa6  mov     r8, rax
0x180230fa9  mov     r9d, esi
0x180230fac  lea     rdx, aWmiQueryLsFail; "WMI query '%ls' failedHRESULT = 0x%08lX"...
0x180230fb3  mov     ecx, ebx
0x180230fb5  call    VmlDebugTrace
0x180230fba  mov     ecx, esi
0x180230fbc  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180230fc1  mov     r9d, eax; char *
0x180230fc4  mov     rcx, [rbp+28h]; this
0x180230fc8  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\wmimgmt\\vmwbemcor"...
0x180230fcf  mov     edx, 532h; void *
0x180230fd4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180230fda  mov     r9d, 80004003h; char *
0x180230fe0  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\wmimgmt\\vmwbemcor"...
0x180230fe7  mov     edx, 524h; void *
0x180230fec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180230ff2  mov     rcx, [rbp+28h]; this
0x180230ff6  mov     r9d, eax; char *
0x180230ff9  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x180231000  mov     edx, 1CC3h; void *
0x180231005  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
