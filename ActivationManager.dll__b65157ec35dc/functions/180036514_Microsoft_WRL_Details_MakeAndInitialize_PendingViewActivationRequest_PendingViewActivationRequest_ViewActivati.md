# Microsoft::WRL::Details::MakeAndInitialize<PendingViewActivationRequest,PendingViewActivationRequest,ViewActivationRequest const &,Execution::IHamHacksForViewActivation *,ulong &,ulong &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<PendingViewActivationRequest>>,ViewActivationRequest const &,Execution::IHamHacksForViewActivation * &&,ulong &,ulong &)

- ea: `0x180036514`
- end: `0x18003678a`
- name: `??$MakeAndInitialize@VPendingViewActivationRequest@@V1@AEBUViewActivationRequest@@PEAUIHamHacksForViewActivation@Execution@@AEAKAEAK@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VPendingViewActivationRequest@@@WRL@Microsoft@@@012@AEBUViewActivationRequest@@$$QEAPEAUIHamHacksForViewActivation@Execution@@AEAK3@Z`
- size: `630`
- prototype: `__int64 __fastcall(PendingViewActivationRequest **, __int64, __int64 *, int *, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180082cf0`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x18001bdc0`
- `0x180036014`
- `0x180036514`
- `0x180044408`
- `0x180047048`
- `0x180047068`
- `0x18005b37c`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800366b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800366b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800366ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003670f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800366ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003670f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036651`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036651`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180036662`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180036662`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003657c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003657c`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<PendingViewActivationRequest,PendingViewActivationRequest,ViewActivationRequest const &,Execution::IHamHacksForViewActivation *,unsigned long &,unsigned long &>(
        PendingViewActivationRequest **a1,
        __int64 a2,
        __int64 *a3,
        int *a4,
        int *a5)
{
  PendingViewActivationRequest *v9; // rax
  int LastError; // esi
  PendingViewActivationRequest *v11; // rdi
  int v12; // r15d
  int v13; // r12d
  __int64 v14; // rsi
  __int64 v15; // r14
  __int64 v16; // rcx
  __int64 v17; // rcx
  HSTRING *v18; // r14
  const WCHAR *v19; // rbp
  unsigned __int64 v20; // rsi
  HRESULT String; // eax
  __int64 v22; // rax
  char *EventW; // rbp
  const char *v24; // r9
  void **v25; // rsi
  void *v26; // r14
  int v28; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a1);
  *a1 = 0;
  v9 = (PendingViewActivationRequest *)operator new(0x120u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v9 )
  {
    v11 = PendingViewActivationRequest::PendingViewActivationRequest(v9);
    v12 = *a5;
    v13 = *a4;
    v14 = *a3;
    QueryPerformanceCounter((LARGE_INTEGER *)v11 + 4);
    *((_DWORD *)v11 + 62) = -2147483638;
    *((_DWORD *)v11 + 45) = -1;
    *((_QWORD *)v11 + 5) = *(_QWORD *)a2;
    *((_QWORD *)v11 + 6) = *(_QWORD *)(a2 + 40);
    *((_DWORD *)v11 + 16) = *(_DWORD *)(a2 + 64);
    *((_DWORD *)v11 + 17) = *(_DWORD *)(a2 + 68);
    v15 = *(_QWORD *)(a2 + 88);
    if ( *((_QWORD *)v11 + 10) != v15 )
    {
      if ( v15 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v15 + 8LL))(*(_QWORD *)(a2 + 88));
      v16 = *((_QWORD *)v11 + 10);
      *((_QWORD *)v11 + 10) = v15;
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    if ( *((_QWORD *)v11 + 11) != v14 )
    {
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      v17 = *((_QWORD *)v11 + 11);
      *((_QWORD *)v11 + 11) = v14;
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    *((_DWORD *)v11 + 14) = v13;
    *((_DWORD *)v11 + 15) = v12;
    v18 = (HSTRING *)((char *)v11 + 72);
    v19 = *(const WCHAR **)(a2 + 24);
    if ( v19 )
    {
      v20 = -1;
      do
        ++v20;
      while ( v19[v20] );
      if ( v20 > 0xFFFFFFFF )
      {
        LastError = -2147024362;
        goto LABEL_21;
      }
      WindowsDeleteString(*v18);
      *v18 = 0;
      String = WindowsCreateString(v19, v20, (HSTRING *)v11 + 9);
    }
    else
    {
      String = Microsoft::WRL::Wrappers::HString::Set((PendingViewActivationRequest *)((char *)v11 + 72), &Src, 0);
    }
    LastError = String;
LABEL_21:
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewrequest.cpp",
        (const char *)(unsigned int)LastError,
        v28);
      v22 = *(_QWORD *)v11;
LABEL_31:
      (*(void (__fastcall **)(PendingViewActivationRequest *))(v22 + 16))(v11);
      return (unsigned int)LastError;
    }
    EventW = (char *)CreateEventW(0, 1, 0, 0);
    v25 = (void **)((char *)v11 + 104);
    if ( (int *)((char *)v11 + 104) == &v28 )
    {
      if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(EventW);
    }
    else
    {
      v26 = *v25;
      if ( (char *)*v25 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&a5);
        CloseHandle(v26);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&a5);
      }
      *v25 = EventW;
    }
    if ( (((unsigned __int64)*v25 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      v22 = *(_QWORD *)v11;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x56,
                    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewrequest.cpp",
                    v24);
      v22 = *(_QWORD *)v11;
      if ( LastError < 0 )
        goto LABEL_31;
    }
    (*(void (__fastcall **)(PendingViewActivationRequest *))(v22 + 8))(v11);
    *a1 = v11;
    (*(void (__fastcall **)(PendingViewActivationRequest *))(*(_QWORD *)v11 + 16LL))(v11);
    return 0;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x180036514  push    rbx
0x180036516  push    rbp
0x180036517  push    rsi
0x180036518  push    rdi
0x180036519  push    r12
0x18003651b  push    r13
0x18003651d  push    r14
0x18003651f  push    r15
0x180036521  sub     rsp, 38h
0x180036525  mov     rsi, r9
0x180036528  mov     r14, r8
0x18003652b  mov     rbp, rdx
0x18003652e  mov     rbx, rcx
0x180036531  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180036536  xor     r13d, r13d
0x180036539  mov     [rbx], r13
0x18003653c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180036543  mov     ecx, 120h; unsigned __int64
0x180036548  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003654d  test    rax, rax
0x180036550  jnz     short loc_18003655C
0x180036552  mov     esi, 8007000Eh
0x180036557  jmp     loc_180036777
0x18003655c  mov     rcx, rax; this
0x18003655f  call    ??0PendingViewActivationRequest@@QEAA@XZ; PendingViewActivationRequest::PendingViewActivationRequest(void)
0x180036564  mov     rdi, rax
0x180036567  mov     rcx, [rsp+78h+arg_20]
0x18003656f  mov     r15d, [rcx]
0x180036572  mov     r12d, [rsi]
0x180036575  mov     rsi, [r14]
0x180036578  lea     rcx, [rax+20h]; lpPerformanceCount
0x18003657c  call    cs:__imp_QueryPerformanceCounter
0x180036582  mov     dword ptr [rdi+0F8h], 8000000Ah
0x18003658c  mov     dword ptr [rdi+0B4h], 0FFFFFFFFh
0x180036596  mov     rcx, [rbp+0]
0x18003659a  mov     [rdi+28h], rcx
0x18003659e  mov     rax, [rbp+28h]
0x1800365a2  mov     [rdi+30h], rax
0x1800365a6  mov     eax, [rbp+40h]
0x1800365a9  mov     [rdi+40h], eax
0x1800365ac  mov     eax, [rbp+44h]
0x1800365af  mov     [rdi+44h], eax
0x1800365b2  mov     r14, [rbp+58h]
0x1800365b6  cmp     [rdi+50h], r14
0x1800365ba  jz      short loc_1800365EB
0x1800365bc  test    r14, r14
0x1800365bf  jz      short loc_1800365D1
0x1800365c1  mov     rax, [r14]
0x1800365c4  mov     rcx, r14
0x1800365c7  mov     rax, [rax+8]
0x1800365cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365d0  nop
0x1800365d1  mov     rcx, [rdi+50h]
0x1800365d5  mov     [rdi+50h], r14
0x1800365d9  test    rcx, rcx
0x1800365dc  jz      short loc_1800365EB
0x1800365de  mov     rax, [rcx]
0x1800365e1  mov     rax, [rax+10h]
0x1800365e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365ea  nop
0x1800365eb  cmp     [rdi+58h], rsi
0x1800365ef  jz      short loc_180036620
0x1800365f1  test    rsi, rsi
0x1800365f4  jz      short loc_180036606
0x1800365f6  mov     rax, [rsi]
0x1800365f9  mov     rcx, rsi
0x1800365fc  mov     rax, [rax+8]
0x180036600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036605  nop
0x180036606  mov     rcx, [rdi+58h]
0x18003660a  mov     [rdi+58h], rsi
0x18003660e  test    rcx, rcx
0x180036611  jz      short loc_180036620
0x180036613  mov     rax, [rcx]
0x180036616  mov     rax, [rax+10h]
0x18003661a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003661f  nop
0x180036620  mov     [rdi+38h], r12d
0x180036624  mov     [rdi+3Ch], r15d
0x180036628  lea     r14, [rdi+48h]
0x18003662c  mov     rbp, [rbp+18h]
0x180036630  test    rbp, rbp
0x180036633  jz      short loc_180036671
0x180036635  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180036639  inc     rsi
0x18003663c  cmp     [rbp+rsi*2+0], r13w
0x180036642  jnz     short loc_180036639
0x180036644  mov     eax, 0FFFFFFFFh
0x180036649  cmp     rsi, rax
0x18003664c  ja      short loc_18003666A
0x18003664e  mov     rcx, [r14]; string
0x180036651  call    cs:__imp_WindowsDeleteString
0x180036657  mov     [r14], r13
0x18003665a  mov     edx, esi; length
0x18003665c  mov     r8, r14; string
0x18003665f  mov     rcx, rbp; sourceString
0x180036662  call    cs:__imp_WindowsCreateString
0x180036668  jmp     short loc_180036683
0x18003666a  mov     esi, 80070216h
0x18003666f  jmp     short loc_180036685
0x180036671  xor     r8d, r8d; unsigned int
0x180036674  lea     rdx, Src; unsigned __int16 *
0x18003667b  mov     rcx, r14; this
0x18003667e  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180036683  mov     esi, eax
0x180036685  test    esi, esi
0x180036687  jns     short loc_1800366AA
0x180036689  mov     rcx, [rsp+78h]; this
0x18003668e  mov     r9d, esi; char *
0x180036691  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180036698  mov     edx, 53h ; 'S'; void *
0x18003669d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800366a2  mov     rax, [rdi]
0x1800366a5  jmp     loc_180036742
0x1800366aa  xor     r9d, r9d; lpName
0x1800366ad  xor     r8d, r8d; bInitialState
0x1800366b0  lea     edx, [r9+1]; bManualReset
0x1800366b4  xor     ecx, ecx; lpEventAttributes
0x1800366b6  call    cs:__imp_CreateEventW
0x1800366bc  mov     rbp, rax
0x1800366bf  lea     rsi, [rdi+68h]
0x1800366c3  lea     rax, [rsp+78h+var_58]
0x1800366c8  cmp     rsi, rax
0x1800366cb  jz      short loc_180036702
0x1800366cd  mov     r14, [rsi]
0x1800366d0  lea     rdx, [r14-1]
0x1800366d4  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800366d8  ja      short loc_1800366FD
0x1800366da  lea     rcx, [rsp+78h+arg_20]; this
0x1800366e2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800366e7  mov     rcx, r14; hObject
0x1800366ea  call    cs:__imp_CloseHandle
0x1800366f0  lea     rcx, [rsp+78h+arg_20]; this
0x1800366f8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800366fd  mov     [rsi], rbp
0x180036700  jmp     short loc_180036715
0x180036702  lea     rax, [rbp-1]
0x180036706  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003670a  ja      short loc_180036715
0x18003670c  mov     rcx, rbp; hObject
0x18003670f  call    cs:__imp_CloseHandle
0x180036715  mov     rax, [rsi]
0x180036718  inc     rax
0x18003671b  test    rax, 0FFFFFFFFFFFFFFFEh
0x180036721  jnz     short loc_180036751
0x180036723  mov     rcx, [rsp+78h]; this
0x180036728  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18003672f  mov     edx, 56h ; 'V'; void *
0x180036734  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036739  mov     esi, eax
0x18003673b  mov     rax, [rdi]
0x18003673e  test    esi, esi
0x180036740  jns     short loc_180036754
0x180036742  mov     rcx, rdi
0x180036745  mov     rax, [rax+10h]
0x180036749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003674e  nop
0x18003674f  jmp     short loc_180036777
0x180036751  mov     rax, [rdi]
0x180036754  mov     rcx, rdi
0x180036757  mov     rax, [rax+8]
0x18003675b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036760  nop
0x180036761  mov     [rbx], rdi
0x180036764  mov     rax, [rdi]
0x180036767  mov     rcx, rdi
0x18003676a  mov     rax, [rax+10h]
0x18003676e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036773  nop
0x180036774  mov     esi, r13d
0x180036777  mov     eax, esi
0x180036779  add     rsp, 38h
0x18003677d  pop     r15
0x18003677f  pop     r14
0x180036781  pop     r13
0x180036783  pop     r12
0x180036785  pop     rdi
0x180036786  pop     rsi
0x180036787  pop     rbp
0x180036788  pop     rbx
0x180036789  retn
```
