# wil::details::make_threadpool_timer_context(std::function<void (void)> &&,_TP_CALLBACK_ENVIRON_V3 *,wil::details::threadpool_timer_context * *)

- ea: `0x18004545c`
- end: `0x180045573`
- name: `?make_threadpool_timer_context@details@wil@@YAJ$$QEAV?$function@$$A6AXXZ@std@@PEAU_TP_CALLBACK_ENVIRON_V3@@PEAPEAUthreadpool_timer_context@12@@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18004557c`

## callees

- `0x180002250`
- `0x180003ce8`
- `0x180004398`
- `0x1800074fc`
- `0x18000751c`
- `0x18000ae5c`
- `0x18003eefc`
- `0x18003f238`
- `0x18003f9fc`
- `0x18004545c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800454fa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800454fa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180045519`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180045519`

## string_xrefs

- `0x1800454d9`: `onecore\private\drivers\inc\bluetooth\foundation\ThreadpoolCoordinator.h`
- `0x180045537`: `onecore\private\drivers\inc\bluetooth\foundation\ThreadpoolCoordinator.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::make_threadpool_timer_context(
        __int64 a1,
        struct _TP_CALLBACK_ENVIRON_V3 *a2,
        wil::details::threadpool_object_context **a3)
{
  wil::details::threadpool_object_context *v6; // rax
  wil::details::threadpool_object_context *v7; // rbx
  unsigned int LastError; // ebx
  void (__stdcall *v9)(PTP_CALLBACK_INSTANCE, PVOID, PTP_TIMER); // rax
  PTP_TIMER ThreadpoolTimer; // rdi
  const char *v11; // r9
  struct _TP_TIMER *v12; // rbp
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  wil::details::threadpool_object_context *v16; // [rsp+50h] [rbp+18h] BYREF
  char v17; // [rsp+58h] [rbp+20h] BYREF

  *a3 = 0;
  v6 = (wil::details::threadpool_object_context *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  v16 = v6;
  if ( v6 )
  {
    wil::details::threadpool_object_context::threadpool_object_context(v6);
    std::function<void (void)>::function<void (void)>((char *)v7 + 16, a1);
    *((_QWORD *)v7 + 10) = 0;
    *((_QWORD *)v7 + 11) = 0;
    *((_DWORD *)v7 + 24) = 0;
    *((_BYTE *)v7 + 100) = 0;
  }
  else
  {
    v7 = 0;
  }
  v16 = v7;
  if ( v7 )
  {
    v9 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_TIMER))_lambda_90aa8c6107d6f80cbf2b6bcb4b215f71_::operator void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)();
    ThreadpoolTimer = CreateThreadpoolTimer(v9, v7, a2);
    v12 = (struct _TP_TIMER *)*((_QWORD *)v7 + 10);
    if ( v12 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v17);
      CloseThreadpoolTimer(v12);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v17);
    }
    *((_QWORD *)v7 + 10) = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      v16 = 0;
      *a3 = v7;
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x182,
                    (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\ThreadpoolCoordinator.h",
                    v11);
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
      v14);
  }
  std::unique_ptr<wil::details::threadpool_timer_context>::~unique_ptr<wil::details::threadpool_timer_context>(&v16);
  return LastError;
}

```

## disassembly

```asm
0x18004545c  mov     [rsp+arg_0], rbx
0x180045461  push    rbp
0x180045462  push    rsi
0x180045463  push    rdi; int
0x180045464  sub     rsp, 20h
0x180045468  mov     rsi, r8
0x18004546b  mov     rbp, rdx
0x18004546e  mov     rdi, rcx
0x180045471  mov     qword ptr [r8], 0
0x180045478  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004547f  mov     ecx, 68h ; 'h'; unsigned __int64
0x180045484  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180045489  mov     rbx, rax
0x18004548c  mov     [rsp+38h+arg_10], rax
0x180045491  test    rax, rax
0x180045494  jz      short loc_1800454C0
0x180045496  mov     rcx, rax; this
0x180045499  call    ??0threadpool_object_context@details@wil@@QEAA@XZ; wil::details::threadpool_object_context::threadpool_object_context(void)
0x18004549e  lea     rcx, [rbx+10h]
0x1800454a2  mov     rdx, rdi
0x1800454a5  call    ??0?$function@$$A6AXXZ@std@@QEAA@$$QEAV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> &&)
0x1800454aa  mov     qword ptr [rbx+50h], 0
0x1800454b2  xor     eax, eax
0x1800454b4  mov     [rbx+58h], rax
0x1800454b8  mov     [rbx+60h], eax
0x1800454bb  mov     [rbx+64h], al
0x1800454be  jmp     short loc_1800454C2
0x1800454c0  xor     ebx, ebx
0x1800454c2  mov     [rsp+38h+arg_10], rbx
0x1800454c7  test    rbx, rbx
0x1800454ca  jnz     short loc_1800454EC
0x1800454cc  mov     rcx, [rsp+38h]; this
0x1800454d1  mov     ebx, 8007000Eh
0x1800454d6  mov     r9d, ebx; char *
0x1800454d9  lea     r8, aOnecorePrivate_4; "onecore\\private\\drivers\\inc\\bluetoo"...
0x1800454e0  mov     edx, 177h; void *
0x1800454e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800454ea  jmp     short loc_18004555A
0x1800454ec  call    ??B_lambda_90aa8c6107d6f80cbf2b6bcb4b215f71_@@QEBAP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@ZXZ; _lambda_90aa8c6107d6f80cbf2b6bcb4b215f71_::operator void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)(void)
0x1800454f1  mov     rcx, rax; pfnti
0x1800454f4  mov     r8, rbp; pcbe
0x1800454f7  mov     rdx, rbx; pv
0x1800454fa  call    cs:__imp_CreateThreadpoolTimer
0x180045500  mov     rdi, rax
0x180045503  mov     rbp, [rbx+50h]
0x180045507  test    rbp, rbp
0x18004550a  jz      short loc_180045529
0x18004550c  lea     rcx, [rsp+38h+arg_18]; this
0x180045511  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180045516  mov     rcx, rbp; pti
0x180045519  call    cs:__imp_CloseThreadpoolTimer
0x18004551f  lea     rcx, [rsp+38h+arg_18]; this
0x180045524  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180045529  mov     [rbx+50h], rdi
0x18004552d  test    rdi, rdi
0x180045530  jnz     short loc_18004554C
0x180045532  mov     rcx, [rsp+38h]; this
0x180045537  lea     r8, aOnecorePrivate_4; "onecore\\private\\drivers\\inc\\bluetoo"...
0x18004553e  mov     edx, 182h; void *
0x180045543  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180045548  mov     ebx, eax
0x18004554a  jmp     short loc_18004555A
0x18004554c  mov     [rsp+38h+arg_10], 0
0x180045555  mov     [rsi], rbx
0x180045558  xor     ebx, ebx
0x18004555a  lea     rcx, [rsp+38h+arg_10]
0x18004555f  call    ??1?$unique_ptr@Uthreadpool_timer_context@details@wil@@U?$default_delete@Uthreadpool_timer_context@details@wil@@@std@@@std@@QEAA@XZ; std::unique_ptr<wil::details::threadpool_timer_context>::~unique_ptr<wil::details::threadpool_timer_context>(void)
0x180045564  mov     eax, ebx
0x180045566  mov     rbx, [rsp+38h+arg_0]
0x18004556b  add     rsp, 20h
0x18004556f  pop     rdi
0x180045570  pop     rsi
0x180045571  pop     rbp
0x180045572  retn
```
