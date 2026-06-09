# VmWbemCore::PutObject(IWbemClassObject *,ulong,IWbemContext *,ushort * *)

- ea: `0x1802315d0`
- end: `0x180231799`
- name: `?PutObject@VmWbemCore@@QEAAXPEAUIWbemClassObject@@KPEAUIWbemContext@@PEAPEAG@Z`
- size: `457`
- prototype: `void __fastcall(VmWbemCore *__hidden this, struct IWbemClassObject *, unsigned int, struct IWbemContext *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18022ef7c`

## callees

- `0x18005f0c0`
- `0x180061240`
- `0x1800663fc`
- `0x1800666b4`
- `0x180078200`
- `0x18007845c`
- `0x18007cbc8`
- `0x1802309d0`
- `0x1802315d0`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180231633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180231633`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180231615`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180231615`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180231629`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180231629`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180231647`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180231647`

## string_xrefs

- `0x18023172f`: `onecore\vm\common\vml\VmSecurity.h`
- `0x180231741`: `onecore\vm\common\vml\VmSecurity.h`
- `0x180231701`: `onecore\vm\common\wmimgmt\vmwbemcore.cpp`
- `0x180231716`: `onecore\vm\common\wmimgmt\vmwbemcore.cpp`
- `0x180231787`: `onecore\vm\common\wmimgmt\vmwbemcore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall VmWbemCore::PutObject(
        VmWbemCore *this,
        struct IWbemClassObject *a2,
        unsigned int a3,
        struct IWbemContext *a4)
{
  void *v8; // rdi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  const char *v11; // r9
  int v12; // eax
  int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // [rsp+20h] [rbp-48h]
  int v16; // [rsp+30h] [rbp-38h] BYREF
  int v17[2]; // [rsp+38h] [rbp-30h] BYREF
  void *TokenHandle[2]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  *(_OWORD *)TokenHandle = 0;
  v8 = (void *)*((_QWORD *)this + 12);
  *(_QWORD *)v17 = TokenHandle;
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
  if ( !ImpersonateLoggedOnUser(v8) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1D52,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v11);
  LOBYTE(TokenHandle[1]) = 1;
  *(_QWORD *)v17 = 0;
  v12 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemClassObject *, _QWORD, struct IWbemContext *))(**((_QWORD **)this + 10) + 112LL))(
          *((_QWORD *)this + 10),
          a2,
          a3,
          a4);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9E4,
      (unsigned int)"onecore\\vm\\common\\wmimgmt\\vmwbemcore.cpp",
      (const char *)(unsigned int)v12,
      (int)v17);
  v16 = -2147418113;
  v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(**(_QWORD **)v17 + 48LL))(
          *(_QWORD *)v17,
          0xFFFFFFFFLL,
          &v16);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9EA,
      (unsigned int)"onecore\\vm\\common\\wmimgmt\\vmwbemcore.cpp",
      (const char *)(unsigned int)v13,
      (int)v17);
  if ( v16 < 0 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16391) )
      VmlDebugTrace(16391, L"Failed to put WMI object with flags 0x%04lX! HRESULT = 0x%08lX \n", a3, (unsigned int)v16);
    v14 = wil::verify_hresult<long>((unsigned int)v16);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9F1,
      (unsigned int)"onecore\\vm\\common\\wmimgmt\\vmwbemcore.cpp",
      (const char *)v14,
      (int)v17);
  }
  if ( *(_QWORD *)v17 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v17 + 16LL))(*(_QWORD *)v17);
  LOBYTE(TokenHandle[1]) = 0;
  Vml::VmImpersonator::~VmImpersonator((Vml::VmImpersonator *)TokenHandle);
}

```

## disassembly

```asm
0x1802315d0  push    rbp
0x1802315d2  push    rbx
0x1802315d3  push    rsi
0x1802315d4  push    rdi
0x1802315d5  push    r14
0x1802315d7  push    r15
0x1802315d9  mov     rbp, rsp
0x1802315dc  sub     rsp, 68h
0x1802315e0  mov     rax, cs:__security_cookie
0x1802315e7  xor     rax, rsp
0x1802315ea  mov     [rbp+var_18], rax
0x1802315ee  mov     r15, r9
0x1802315f1  mov     ebx, r8d
0x1802315f4  mov     r14, rdx
0x1802315f7  mov     rsi, rcx
0x1802315fa  xorps   xmm0, xmm0
0x1802315fd  movups  xmmword ptr [rbp+TokenHandle], xmm0
0x180231601  mov     rdi, [rcx+60h]
0x180231605  lea     rax, [rbp+TokenHandle]
0x180231609  mov     qword ptr [rbp+var_30], rax
0x18023160d  mov     [rbp+TokenHandle], 0
0x180231615  call    cs:__imp_GetCurrentThread
0x18023161b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18023161f  xor     r8d, r8d; OpenAsSelf
0x180231622  lea     edx, [r8+0Ch]; DesiredAccess
0x180231626  mov     rcx, rax; ThreadHandle
0x180231629  call    cs:__imp_OpenThreadToken
0x18023162f  test    eax, eax
0x180231631  jnz     short loc_180231644
0x180231633  call    cs:__imp_GetLastError
0x180231639  cmp     eax, 3F0h
0x18023163e  jnz     loc_180231728
0x180231644  mov     rcx, rdi; hToken
0x180231647  call    cs:__imp_ImpersonateLoggedOnUser
0x18023164d  mov     rcx, [rbp+30h]; this
0x180231651  test    eax, eax
0x180231653  jz      loc_180231741
0x180231659  mov     byte ptr [rbp+TokenHandle+8], 1
0x18023165d  mov     qword ptr [rbp+var_30], 0
0x180231665  mov     rcx, [rsi+50h]
0x180231669  mov     rax, [rcx]
0x18023166c  lea     rdx, [rbp+var_30]
0x180231670  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180231675  mov     r9, r15
0x180231678  mov     r8d, ebx
0x18023167b  mov     rdx, r14
0x18023167e  mov     rax, [rax+70h]
0x180231682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180231687  mov     rcx, [rbp+30h]; this
0x18023168b  test    eax, eax
0x18023168d  js      loc_180231713
0x180231693  mov     [rbp+var_38], 8000FFFFh
0x18023169a  mov     rcx, qword ptr [rbp+var_30]
0x18023169e  mov     rax, [rcx]
0x1802316a1  lea     r8, [rbp+var_38]
0x1802316a5  or      edx, 0FFFFFFFFh
0x1802316a8  mov     rax, [rax+30h]
0x1802316ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802316b1  mov     rcx, [rbp+30h]; this
0x1802316b5  test    eax, eax
0x1802316b7  js      short loc_1802316FE
0x1802316b9  cmp     [rbp+var_38], 0
0x1802316bd  jl      loc_180231753
0x1802316c3  mov     rcx, qword ptr [rbp+var_30]
0x1802316c7  test    rcx, rcx
0x1802316ca  jz      short loc_1802316D8
0x1802316cc  mov     rax, [rcx]
0x1802316cf  mov     rax, [rax+10h]
0x1802316d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802316d8  mov     byte ptr [rbp+TokenHandle+8], 0
0x1802316dc  lea     rcx, [rbp+TokenHandle]; this
0x1802316e0  call    ??1VmImpersonator@Vml@@QEAA@XZ; Vml::VmImpersonator::~VmImpersonator(void)
0x1802316e5  mov     rcx, [rbp+var_18]
0x1802316e9  xor     rcx, rsp; StackCookie
0x1802316ec  call    __security_check_cookie
0x1802316f1  add     rsp, 68h
0x1802316f5  pop     r15
0x1802316f7  pop     r14
0x1802316f9  pop     rdi
0x1802316fa  pop     rsi
0x1802316fb  pop     rbx
0x1802316fc  pop     rbp
0x1802316fd  retn
0x1802316fe  mov     r9d, eax; char *
0x180231701  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\wmimgmt\\vmwbemcor"...
0x180231708  mov     edx, 9EAh; void *
0x18023170d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180231713  mov     r9d, eax; char *
0x180231716  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\wmimgmt\\vmwbemcor"...
0x18023171d  mov     edx, 9E4h; void *
0x180231722  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180231728  mov     rcx, [rbp+30h]; this
0x18023172c  mov     r9d, eax; char *
0x18023172f  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x180231736  mov     edx, 1CC3h; void *
0x18023173b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180231741  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x180231748  mov     edx, 1D52h; void *
0x18023174d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180231753  mov     edi, 4007h
0x180231758  mov     ecx, edi
0x18023175a  call    VmlIsDebugTraceEnabled
0x18023175f  test    eax, eax
0x180231761  jz      short loc_180231778
0x180231763  mov     r9d, [rbp+var_38]
0x180231767  mov     r8d, ebx
0x18023176a  lea     rdx, aFailedToPutWmi; "Failed to put WMI object with flags 0x%"...
0x180231771  mov     ecx, edi
0x180231773  call    VmlDebugTrace
0x180231778  mov     ecx, [rbp+var_38]
0x18023177b  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180231780  mov     r9d, eax; char *
0x180231783  mov     rcx, [rbp+30h]; this
0x180231787  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\wmimgmt\\vmwbemcor"...
0x18023178e  mov     edx, 9F1h; void *
0x180231793  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
