# wil::details::make_threadpool_wait_context(std::function<void (void)> &&,_TP_CALLBACK_ENVIRON_V3 *,wil::details::threadpool_wait_context * *)

- ea: `0x180055980`
- end: `0x180055a98`
- name: `?make_threadpool_wait_context@details@wil@@YAJ$$QEAV?$function@$$A6AXXZ@std@@PEAU_TP_CALLBACK_ENVIRON_V3@@PEAPEAUthreadpool_wait_context@12@@Z`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180055aa0`

## callees

- `0x180002250`
- `0x180003ce8`
- `0x180004398`
- `0x1800074fc`
- `0x18000751c`
- `0x18000ae5c`
- `0x18003eefc`
- `0x180052828`
- `0x180055980`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180055a3d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180055a3d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180055a1e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180055a1e`

## string_xrefs

- `0x1800559fe`: `onecore\drivers\bluetooth\foundation\lib\ThreadpoolCoordinator.h`
- `0x180055a5b`: `onecore\drivers\bluetooth\foundation\lib\ThreadpoolCoordinator.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::make_threadpool_wait_context(
        __int64 a1,
        struct _TP_CALLBACK_ENVIRON_V3 *a2,
        wil::details::threadpool_object_context **a3)
{
  wil::details::threadpool_object_context *v6; // rax
  wil::details::threadpool_object_context *v7; // rbx
  unsigned int LastError; // ebx
  PTP_WAIT ThreadpoolWait; // rdi
  const char *v10; // r9
  struct _TP_WAIT *v11; // rsi
  int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  wil::details::threadpool_object_context *v15; // [rsp+50h] [rbp+18h] BYREF
  char v16; // [rsp+58h] [rbp+20h] BYREF

  *a3 = 0;
  v6 = (wil::details::threadpool_object_context *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  v15 = v6;
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
  v15 = v7;
  if ( v7 )
  {
    ThreadpoolWait = CreateThreadpoolWait(_lambda_e9f9d7a9aa50b62f01ee7fcec6355d9f_::_lambda_invoker_cdecl_, v7, a2);
    v11 = (struct _TP_WAIT *)*((_QWORD *)v7 + 10);
    if ( v11 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v16);
      CloseThreadpoolWait(v11);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v16);
    }
    *((_QWORD *)v7 + 10) = ThreadpoolWait;
    if ( ThreadpoolWait )
    {
      v15 = 0;
      *a3 = v7;
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x199,
                    (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ThreadpoolCoordinator.h",
                    v10);
    }
  }
  else
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18E,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ThreadpoolCoordinator.h",
      (const char *)0x8007000ELL,
      v13);
  }
  std::unique_ptr<wil::details::threadpool_wait_context>::~unique_ptr<wil::details::threadpool_wait_context>(&v15);
  return LastError;
}

```

## disassembly

```asm
0x180055980  mov     [rsp+arg_0], rbx
0x180055985  push    rsi
0x180055986  push    rdi
0x180055987  push    r14; int
0x180055989  sub     rsp, 20h
0x18005598d  mov     r14, r8
0x180055990  mov     rsi, rdx
0x180055993  mov     rdi, rcx
0x180055996  mov     qword ptr [r8], 0
0x18005599d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800559a4  mov     ecx, 68h ; 'h'; unsigned __int64
0x1800559a9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800559ae  mov     rbx, rax
0x1800559b1  mov     [rsp+38h+arg_10], rax
0x1800559b6  test    rax, rax
0x1800559b9  jz      short loc_1800559E5
0x1800559bb  mov     rcx, rax; this
0x1800559be  call    ??0threadpool_object_context@details@wil@@QEAA@XZ; wil::details::threadpool_object_context::threadpool_object_context(void)
0x1800559c3  lea     rcx, [rbx+10h]
0x1800559c7  mov     rdx, rdi
0x1800559ca  call    ??0?$function@$$A6AXXZ@std@@QEAA@$$QEAV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> &&)
0x1800559cf  mov     qword ptr [rbx+50h], 0
0x1800559d7  xor     eax, eax
0x1800559d9  mov     [rbx+58h], rax
0x1800559dd  mov     [rbx+60h], eax
0x1800559e0  mov     [rbx+64h], al
0x1800559e3  jmp     short loc_1800559E7
0x1800559e5  xor     ebx, ebx
0x1800559e7  mov     [rsp+38h+arg_10], rbx
0x1800559ec  test    rbx, rbx
0x1800559ef  jnz     short loc_180055A11
0x1800559f1  mov     rcx, [rsp+38h]; this
0x1800559f6  mov     ebx, 8007000Eh
0x1800559fb  mov     r9d, ebx; char *
0x1800559fe  lea     r8, aOnecoreDrivers_37; "onecore\\drivers\\bluetooth\\foundation"...
0x180055a05  mov     edx, 18Eh; void *
0x180055a0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055a0f  jmp     short loc_180055A7E
0x180055a11  mov     r8, rsi; pcbe
0x180055a14  mov     rdx, rbx; pv
0x180055a17  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_e9f9d7a9aa50b62f01ee7fcec6355d9f_@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180055a1e  call    cs:__imp_CreateThreadpoolWait
0x180055a24  mov     rdi, rax
0x180055a27  mov     rsi, [rbx+50h]
0x180055a2b  test    rsi, rsi
0x180055a2e  jz      short loc_180055A4D
0x180055a30  lea     rcx, [rsp+38h+arg_18]; this
0x180055a35  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180055a3a  mov     rcx, rsi; pwa
0x180055a3d  call    cs:__imp_CloseThreadpoolWait
0x180055a43  lea     rcx, [rsp+38h+arg_18]; this
0x180055a48  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180055a4d  mov     [rbx+50h], rdi
0x180055a51  test    rdi, rdi
0x180055a54  jnz     short loc_180055A70
0x180055a56  mov     rcx, [rsp+38h]; this
0x180055a5b  lea     r8, aOnecoreDrivers_37; "onecore\\drivers\\bluetooth\\foundation"...
0x180055a62  mov     edx, 199h; void *
0x180055a67  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180055a6c  mov     ebx, eax
0x180055a6e  jmp     short loc_180055A7E
0x180055a70  mov     [rsp+38h+arg_10], 0
0x180055a79  mov     [r14], rbx
0x180055a7c  xor     ebx, ebx
0x180055a7e  lea     rcx, [rsp+38h+arg_10]
0x180055a83  call    ??1?$unique_ptr@Uthreadpool_wait_context@details@wil@@U?$default_delete@Uthreadpool_wait_context@details@wil@@@std@@@std@@QEAA@XZ; std::unique_ptr<wil::details::threadpool_wait_context>::~unique_ptr<wil::details::threadpool_wait_context>(void)
0x180055a88  mov     eax, ebx
0x180055a8a  mov     rbx, [rsp+38h+arg_0]
0x180055a8f  add     rsp, 20h
0x180055a93  pop     r14
0x180055a95  pop     rdi
0x180055a96  pop     rsi
0x180055a97  retn
```
