# VmWbemCore::GetWbemObject(ushort const *,IWbemClassObject * *,IWbemContext *)

- ea: `0x1802313e4`
- end: `0x1802315ca`
- name: `?GetWbemObject@VmWbemCore@@QEBAXPEBGPEAPEAUIWbemClassObject@@PEAUIWbemContext@@@Z`
- size: `486`
- prototype: `void(VmWbemCore *__hidden this, const unsigned __int16 *, struct IWbemClassObject **, struct IWbemContext *)`
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
- `0x1802313e4`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180231487`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180231487`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180231468`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180231468`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18023147d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18023147d`
- `OLEAUT32!__imp_SysAllocString` at `0x180231432`
- `OLEAUT32!__imp_SysAllocString` at `0x180231432`
- `OLEAUT32!__imp_SysFreeString` at `0x1802314f7`
- `OLEAUT32!__imp_SysFreeString` at `0x1802314f7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18023149b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18023149b`

## string_xrefs

- `0x18023159b`: `onecore\vm\common\vml\VmBstr.h`
- `0x180231517`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1802315b8`: `onecore\vm\common\vml\VmSecurity.h`
- `0x18023155c`: `onecore\vm\common\wmimgmt\vmwbemcore.cpp`
- `0x180231574`: `onecore\vm\common\wmimgmt\vmwbemcore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall VmWbemCore::GetWbemObject(
        VmWbemCore *this,
        const unsigned __int16 *a2,
        struct IWbemClassObject **a3,
        struct IWbemContext *a4)
{
  int v5; // r14d
  OLECHAR *v8; // rbx
  void *v9; // rbp
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  const char *v12; // r9
  int v13; // esi
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // [rsp+20h] [rbp-88h]
  void *TokenHandle[2]; // [rsp+50h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v5 = (int)a3;
  if ( !*((_QWORD *)this + 10) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x386,
      (unsigned int)"onecore\\vm\\common\\wmimgmt\\vmwbemcore.cpp",
      (const char *)0x80004003LL,
      v16);
  v8 = 0;
  if ( a2 )
  {
    v8 = SysAllocString(a2);
    if ( !v8 )
    {
      v15 = wil::verify_hresult<long>(2147942414LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x254,
        (unsigned int)"onecore\\vm\\common\\vml\\VmBstr.h",
        (const char *)v15,
        v16);
    }
  }
  *(_OWORD *)TokenHandle = 0;
  v9 = (void *)*((_QWORD *)this + 12);
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
        v16);
  }
  if ( !ImpersonateLoggedOnUser(v9) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1D52,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v12);
  LOBYTE(TokenHandle[1]) = 1;
  v13 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, struct IWbemContext *))(**((_QWORD **)this + 10) + 48LL))(
          *((_QWORD *)this + 10),
          v8,
          0,
          a4);
  if ( v13 < 0 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16391) )
      VmlDebugTrace(16391, L"Failed to get object or class '%ls'", a2);
    v14 = wil::verify_hresult<long>((unsigned int)v13);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x393,
      (unsigned int)"onecore\\vm\\common\\wmimgmt\\vmwbemcore.cpp",
      (const char *)v14,
      v5);
  }
  LOBYTE(TokenHandle[1]) = 0;
  Vml::VmImpersonator::~VmImpersonator((Vml::VmImpersonator *)TokenHandle);
  if ( v8 )
    SysFreeString(v8);
}

```

## disassembly

```asm
0x1802313e4  push    rbx
0x1802313e6  push    rbp
0x1802313e7  push    rsi
0x1802313e8  push    rdi
0x1802313e9  push    r14
0x1802313eb  push    r15
0x1802313ed  sub     rsp, 78h
0x1802313f1  mov     rax, cs:__security_cookie
0x1802313f8  xor     rax, rsp
0x1802313fb  mov     [rsp+0A8h+var_48], rax
0x180231400  mov     r15, r9
0x180231403  mov     r14, r8
0x180231406  mov     rdi, rdx
0x180231409  mov     rsi, rcx
0x18023140c  mov     [rsp+0A8h+var_68], 0
0x180231415  mov     rcx, [rsp+0A8h]; this
0x18023141d  cmp     qword ptr [rsi+50h], 0
0x180231422  jz      loc_18023156E
0x180231428  xor     ebx, ebx
0x18023142a  test    rdx, rdx
0x18023142d  jz      short loc_180231444
0x18023142f  mov     rcx, rdx; psz
0x180231432  call    cs:__imp_SysAllocString
0x180231438  mov     rbx, rax
0x18023143b  test    rax, rax
0x18023143e  jz      loc_180231586
0x180231444  mov     [rsp+0A8h+var_68], rbx
0x180231449  xorps   xmm0, xmm0
0x18023144c  movups  xmmword ptr [rsp+0A8h+TokenHandle], xmm0
0x180231451  mov     rbp, [rsi+60h]
0x180231455  lea     rax, [rsp+0A8h+TokenHandle]
0x18023145a  mov     [rsp+0A8h+var_60], rax
0x18023145f  mov     [rsp+0A8h+TokenHandle], 0
0x180231468  call    cs:__imp_GetCurrentThread
0x18023146e  lea     r9, [rsp+0A8h+TokenHandle]; TokenHandle
0x180231473  xor     r8d, r8d; OpenAsSelf
0x180231476  lea     edx, [r8+0Ch]; DesiredAccess
0x18023147a  mov     rcx, rax; ThreadHandle
0x18023147d  call    cs:__imp_OpenThreadToken
0x180231483  test    eax, eax
0x180231485  jnz     short loc_180231498
0x180231487  call    cs:__imp_GetLastError
0x18023148d  cmp     eax, 3F0h
0x180231492  jnz     loc_1802315AD
0x180231498  mov     rcx, rbp; hToken
0x18023149b  call    cs:__imp_ImpersonateLoggedOnUser
0x1802314a1  mov     rcx, [rsp+0A8h]; this
0x1802314a9  test    eax, eax
0x1802314ab  jz      short loc_180231517
0x1802314ad  mov     byte ptr [rsp+0A8h+TokenHandle+8], 1
0x1802314b2  mov     rcx, [rsi+50h]
0x1802314b6  mov     rax, [rcx]
0x1802314b9  mov     [rsp+0A8h+var_80], 0
0x1802314c2  mov     qword ptr [rsp+0A8h+var_88], r14; int
0x1802314c7  mov     r9, r15
0x1802314ca  xor     r8d, r8d
0x1802314cd  mov     rdx, rbx
0x1802314d0  mov     rax, [rax+30h]
0x1802314d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802314d9  mov     esi, eax
0x1802314db  test    eax, eax
0x1802314dd  js      short loc_180231529
0x1802314df  mov     byte ptr [rsp+0A8h+TokenHandle+8], 0
0x1802314e4  lea     rcx, [rsp+0A8h+TokenHandle]; this
0x1802314e9  call    ??1VmImpersonator@Vml@@QEAA@XZ; Vml::VmImpersonator::~VmImpersonator(void)
0x1802314ee  nop
0x1802314ef  test    rbx, rbx
0x1802314f2  jz      short loc_1802314FD
0x1802314f4  mov     rcx, rbx; bstrString
0x1802314f7  call    cs:__imp_SysFreeString
0x1802314fd  mov     rcx, [rsp+0A8h+var_48]
0x180231502  xor     rcx, rsp; StackCookie
0x180231505  call    __security_check_cookie
0x18023150a  add     rsp, 78h
0x18023150e  pop     r15
0x180231510  pop     r14
0x180231512  pop     rdi
0x180231513  pop     rsi
0x180231514  pop     rbp
0x180231515  pop     rbx
0x180231516  retn
0x180231517  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x18023151e  mov     edx, 1D52h; void *
0x180231523  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180231529  mov     ebx, 4007h
0x18023152e  mov     ecx, ebx
0x180231530  call    VmlIsDebugTraceEnabled
0x180231535  test    eax, eax
0x180231537  jz      short loc_18023154A
0x180231539  mov     r8, rdi
0x18023153c  lea     rdx, aFailedToGetObj; "Failed to get object or class '%ls'"
0x180231543  mov     ecx, ebx
0x180231545  call    VmlDebugTrace
0x18023154a  mov     ecx, esi
0x18023154c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180231551  mov     r9d, eax; char *
0x180231554  mov     rcx, [rsp+0A8h]; this
0x18023155c  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\wmimgmt\\vmwbemcor"...
0x180231563  mov     edx, 393h; void *
0x180231568  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18023156e  mov     r9d, 80004003h; char *
0x180231574  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\wmimgmt\\vmwbemcor"...
0x18023157b  mov     edx, 386h; void *
0x180231580  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180231586  mov     ecx, 8007000Eh
0x18023158b  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180231590  mov     r9d, eax; char *
0x180231593  mov     rcx, [rsp+0A8h]; this
0x18023159b  lea     r8, aOnecoreVmCommo_4; "onecore\\vm\\common\\vml\\VmBstr.h"
0x1802315a2  mov     edx, 254h; void *
0x1802315a7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802315ad  mov     rcx, [rsp+0A8h]; this
0x1802315b5  mov     r9d, eax; char *
0x1802315b8  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1802315bf  mov     edx, 1CC3h; void *
0x1802315c4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
