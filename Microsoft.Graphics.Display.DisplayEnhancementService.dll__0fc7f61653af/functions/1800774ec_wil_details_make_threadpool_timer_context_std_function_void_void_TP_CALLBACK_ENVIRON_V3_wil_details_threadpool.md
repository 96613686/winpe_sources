# wil::details::make_threadpool_timer_context(std::function<void (void)> &&,_TP_CALLBACK_ENVIRON_V3 *,wil::details::threadpool_timer_context * *)

- ea: `0x1800774ec`
- end: `0x18007761e`
- name: `?make_threadpool_timer_context@details@wil@@YAJ$$QEAV?$function@$$A6AXXZ@std@@PEAU_TP_CALLBACK_ENVIRON_V3@@PEAPEAUthreadpool_timer_context@12@@Z`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180077624`

## callees

- `0x18000740c`
- `0x180009094`
- `0x180009534`
- `0x180009eb0`
- `0x18000c118`
- `0x18000dc74`
- `0x18000deac`
- `0x18000decc`
- `0x180075b9c`
- `0x1800774ec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800775be`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800775be`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007759f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007759f`

## string_xrefs

- `0x18007757f`: `onecore\private\drivers\inc\bluetooth\foundation\ThreadpoolCoordinator.h`
- `0x1800775dc`: `onecore\private\drivers\inc\bluetooth\foundation\ThreadpoolCoordinator.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::make_threadpool_timer_context(
        __int64 a1,
        struct _TP_CALLBACK_ENVIRON_V3 *a2,
        _QWORD *a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  __int64 v8; // rbx
  void *v9; // rdx
  unsigned int LastError; // ebx
  PTP_TIMER ThreadpoolTimer; // rbx
  const char *v12; // r9
  struct _TP_TIMER *v13; // rsi
  int v15; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  _QWORD *v17; // [rsp+50h] [rbp+18h] BYREF
  char v18; // [rsp+58h] [rbp+20h] BYREF

  *a3 = 0;
  v6 = operator new(0x68u, (const struct std::nothrow_t *)std::nothrow);
  v7 = v6;
  v17 = v6;
  if ( v6 )
  {
    Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::Instance(v6);
    v8 = *v7;
    wil::details::ResetEvent(*(wil::details **)(*v7 + 16LL), v9);
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
    std::function<void (void)>::function<void (void)>(v7 + 2, a1);
    v7[10] = 0;
    v7[11] = 0;
    *((_DWORD *)v7 + 24) = 0;
    *((_BYTE *)v7 + 100) = 0;
  }
  else
  {
    v7 = 0;
  }
  v17 = v7;
  if ( v7 )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(_lambda_90aa8c6107d6f80cbf2b6bcb4b215f71_::_lambda_invoker_cdecl_, v7, a2);
    v13 = (struct _TP_TIMER *)v7[10];
    if ( v13 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v18);
      CloseThreadpoolTimer(v13);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v18);
    }
    v7[10] = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      v17 = 0;
      *a3 = v7;
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x182,
                    (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\ThreadpoolCoordinator.h",
                    v12);
    }
  }
  else
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\ThreadpoolCoordinator.h",
      (const char *)0x8007000ELL,
      v15);
  }
  std::unique_ptr<wil::details::threadpool_timer_context>::~unique_ptr<wil::details::threadpool_timer_context>(&v17);
  return LastError;
}

```

## disassembly

```asm
0x1800774ec  mov     [rsp+arg_0], rbx
0x1800774f1  mov     [rsp+arg_8], rbp
0x1800774f6  push    rsi
0x1800774f7  push    rdi
0x1800774f8  push    r14; int
0x1800774fa  sub     rsp, 20h
0x1800774fe  mov     r14, r8
0x180077501  mov     rsi, rdx
0x180077504  mov     rbp, rcx
0x180077507  mov     qword ptr [r8], 0
0x18007750e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180077515  mov     ecx, 68h ; 'h'; unsigned __int64
0x18007751a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18007751f  mov     rdi, rax
0x180077522  mov     [rsp+38h+arg_10], rax
0x180077527  test    rax, rax
0x18007752a  jz      short loc_180077566
0x18007752c  mov     rcx, rax
0x18007752f  call    ?Instance@?$SingletonWithFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@345@@Foundation@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@std@@XZ; Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::Instance(void)
0x180077534  mov     rbx, [rdi]
0x180077537  mov     rcx, [rbx+10h]; this
0x18007753b  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x180077540  lock inc dword ptr [rbx+8]
0x180077544  lea     rcx, [rdi+10h]
0x180077548  mov     rdx, rbp
0x18007754b  call    ??0?$function@$$A6AXXZ@std@@QEAA@$$QEAV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> &&)
0x180077550  mov     qword ptr [rdi+50h], 0
0x180077558  xor     eax, eax
0x18007755a  mov     [rdi+58h], rax
0x18007755e  mov     [rdi+60h], eax
0x180077561  mov     [rdi+64h], al
0x180077564  jmp     short loc_180077568
0x180077566  xor     edi, edi
0x180077568  mov     [rsp+38h+arg_10], rdi
0x18007756d  test    rdi, rdi
0x180077570  jnz     short loc_180077592
0x180077572  mov     rcx, [rsp+38h]; this
0x180077577  mov     ebx, 8007000Eh
0x18007757c  mov     r9d, ebx; char *
0x18007757f  lea     r8, aOnecorePrivate_4; "onecore\\private\\drivers\\inc\\bluetoo"...
0x180077586  mov     edx, 177h; void *
0x18007758b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077590  jmp     short loc_1800775FF
0x180077592  mov     r8, rsi; pcbe
0x180077595  mov     rdx, rdi; pv
0x180077598  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_90aa8c6107d6f80cbf2b6bcb4b215f71_@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18007759f  call    cs:__imp_CreateThreadpoolTimer
0x1800775a5  mov     rbx, rax
0x1800775a8  mov     rsi, [rdi+50h]
0x1800775ac  test    rsi, rsi
0x1800775af  jz      short loc_1800775CE
0x1800775b1  lea     rcx, [rsp+38h+arg_18]; this
0x1800775b6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800775bb  mov     rcx, rsi; pti
0x1800775be  call    cs:__imp_CloseThreadpoolTimer
0x1800775c4  lea     rcx, [rsp+38h+arg_18]; this
0x1800775c9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800775ce  mov     [rdi+50h], rbx
0x1800775d2  test    rbx, rbx
0x1800775d5  jnz     short loc_1800775F1
0x1800775d7  mov     rcx, [rsp+38h]; this
0x1800775dc  lea     r8, aOnecorePrivate_4; "onecore\\private\\drivers\\inc\\bluetoo"...
0x1800775e3  mov     edx, 182h; void *
0x1800775e8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800775ed  mov     ebx, eax
0x1800775ef  jmp     short loc_1800775FF
0x1800775f1  mov     [rsp+38h+arg_10], 0
0x1800775fa  mov     [r14], rdi
0x1800775fd  xor     ebx, ebx
0x1800775ff  lea     rcx, [rsp+38h+arg_10]
0x180077604  call    ??1?$unique_ptr@Uthreadpool_timer_context@details@wil@@U?$default_delete@Uthreadpool_timer_context@details@wil@@@std@@@std@@QEAA@XZ; std::unique_ptr<wil::details::threadpool_timer_context>::~unique_ptr<wil::details::threadpool_timer_context>(void)
0x180077609  mov     eax, ebx
0x18007760b  mov     rbx, [rsp+38h+arg_0]
0x180077610  mov     rbp, [rsp+38h+arg_8]
0x180077615  add     rsp, 20h
0x180077619  pop     r14
0x18007761b  pop     rdi
0x18007761c  pop     rsi
0x18007761d  retn
```
