# wil::details::make_threadpool_work_context(std::function<void (void)> &&,_TP_CALLBACK_ENVIRON_V3 *,wil::details::threadpool_work_context * *)

- ea: `0x180055b00`
- end: `0x180055c19`
- name: `?make_threadpool_work_context@details@wil@@YAJ$$QEAV?$function@$$A6AXXZ@std@@PEAU_TP_CALLBACK_ENVIRON_V3@@PEAPEAUthreadpool_work_context@12@@Z`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180055c20`

## callees

- `0x180002250`
- `0x180003ce8`
- `0x180004398`
- `0x1800074fc`
- `0x18000751c`
- `0x18000ae5c`
- `0x18003eefc`
- `0x180052844`
- `0x180055b00`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180055b9f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180055b9f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180055bbe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180055bbe`

## string_xrefs

- `0x180055b7f`: `onecore\drivers\bluetooth\foundation\lib\ThreadpoolCoordinator.h`
- `0x180055bdc`: `onecore\drivers\bluetooth\foundation\lib\ThreadpoolCoordinator.h`

## pseudocode

```c
__int64 __fastcall wil::details::make_threadpool_work_context(
        __int64 a1,
        struct _TP_CALLBACK_ENVIRON_V3 *a2,
        wil::details::threadpool_object_context **a3)
{
  wil::details::threadpool_object_context *v6; // rax
  wil::details::threadpool_object_context *v7; // rbx
  unsigned int LastError; // ebx
  PTP_WORK ThreadpoolWork; // rdi
  const char *v10; // r9
  struct _TP_WORK *v11; // rsi
  int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  wil::details::threadpool_object_context *v15; // [rsp+50h] [rbp+18h] BYREF
  char v16; // [rsp+58h] [rbp+20h] BYREF

  *a3 = 0;
  v6 = (wil::details::threadpool_object_context *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  v15 = v6;
  if ( v6 )
  {
    wil::details::threadpool_object_context::threadpool_object_context(v6);
    std::function<void (void)>::function<void (void)>((char *)v7 + 16, a1);
    *((_QWORD *)v7 + 10) = 0;
    *((_QWORD *)v7 + 11) = 0;
    *((_QWORD *)v7 + 12) = 0;
    *((_BYTE *)v7 + 104) = 0;
  }
  else
  {
    v7 = 0;
  }
  v15 = v7;
  if ( v7 )
  {
    ThreadpoolWork = CreateThreadpoolWork(_lambda_6375b06740b0ef4eab4bb6f72956849c_::_lambda_invoker_cdecl_, v7, a2);
    v11 = (struct _TP_WORK *)*((_QWORD *)v7 + 10);
    if ( v11 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v16);
      CloseThreadpoolWork(v11);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v16);
    }
    *((_QWORD *)v7 + 10) = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      v15 = 0;
      *a3 = v7;
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x16B,
                    (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ThreadpoolCoordinator.h",
                    v10);
    }
  }
  else
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x160,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ThreadpoolCoordinator.h",
      (const char *)0x8007000ELL,
      v13);
  }
  std::unique_ptr<wil::details::threadpool_work_context>::~unique_ptr<wil::details::threadpool_work_context>(&v15);
  return LastError;
}

```

## disassembly

```asm
0x180055b00  mov     [rsp+arg_0], rbx
0x180055b05  push    rsi
0x180055b06  push    rdi
0x180055b07  push    r14; int
0x180055b09  sub     rsp, 20h
0x180055b0d  mov     r14, r8
0x180055b10  mov     rsi, rdx
0x180055b13  mov     rdi, rcx
0x180055b16  mov     qword ptr [r8], 0
0x180055b1d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180055b24  mov     ecx, 70h ; 'p'; unsigned __int64
0x180055b29  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180055b2e  mov     rbx, rax
0x180055b31  mov     [rsp+38h+arg_10], rax
0x180055b36  test    rax, rax
0x180055b39  jz      short loc_180055B66
0x180055b3b  mov     rcx, rax; this
0x180055b3e  call    ??0threadpool_object_context@details@wil@@QEAA@XZ; wil::details::threadpool_object_context::threadpool_object_context(void)
0x180055b43  lea     rcx, [rbx+10h]
0x180055b47  mov     rdx, rdi
0x180055b4a  call    ??0?$function@$$A6AXXZ@std@@QEAA@$$QEAV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> &&)
0x180055b4f  mov     qword ptr [rbx+50h], 0
0x180055b57  xor     eax, eax
0x180055b59  mov     [rbx+58h], rax
0x180055b5d  mov     [rbx+60h], rax
0x180055b61  mov     [rbx+68h], al
0x180055b64  jmp     short loc_180055B68
0x180055b66  xor     ebx, ebx
0x180055b68  mov     [rsp+38h+arg_10], rbx
0x180055b6d  test    rbx, rbx
0x180055b70  jnz     short loc_180055B92
0x180055b72  mov     rcx, [rsp+38h]; this
0x180055b77  mov     ebx, 8007000Eh
0x180055b7c  mov     r9d, ebx; char *
0x180055b7f  lea     r8, aOnecoreDrivers_37; "onecore\\drivers\\bluetooth\\foundation"...
0x180055b86  mov     edx, 160h; void *
0x180055b8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055b90  jmp     short loc_180055BFF
0x180055b92  mov     r8, rsi; pcbe
0x180055b95  mov     rdx, rbx; pv
0x180055b98  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_6375b06740b0ef4eab4bb6f72956849c_@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180055b9f  call    cs:__imp_CreateThreadpoolWork
0x180055ba5  mov     rdi, rax
0x180055ba8  mov     rsi, [rbx+50h]
0x180055bac  test    rsi, rsi
0x180055baf  jz      short loc_180055BCE
0x180055bb1  lea     rcx, [rsp+38h+arg_18]; this
0x180055bb6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180055bbb  mov     rcx, rsi; pwk
0x180055bbe  call    cs:__imp_CloseThreadpoolWork
0x180055bc4  lea     rcx, [rsp+38h+arg_18]; this
0x180055bc9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180055bce  mov     [rbx+50h], rdi
0x180055bd2  test    rdi, rdi
0x180055bd5  jnz     short loc_180055BF1
0x180055bd7  mov     rcx, [rsp+38h]; this
0x180055bdc  lea     r8, aOnecoreDrivers_37; "onecore\\drivers\\bluetooth\\foundation"...
0x180055be3  mov     edx, 16Bh; void *
0x180055be8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180055bed  mov     ebx, eax
0x180055bef  jmp     short loc_180055BFF
0x180055bf1  mov     [rsp+38h+arg_10], 0
0x180055bfa  mov     [r14], rbx
0x180055bfd  xor     ebx, ebx
0x180055bff  lea     rcx, [rsp+38h+arg_10]
0x180055c04  call    ??1?$unique_ptr@Uthreadpool_work_context@details@wil@@U?$default_delete@Uthreadpool_work_context@details@wil@@@std@@@std@@QEAA@XZ; std::unique_ptr<wil::details::threadpool_work_context>::~unique_ptr<wil::details::threadpool_work_context>(void)
0x180055c09  mov     eax, ebx
0x180055c0b  mov     rbx, [rsp+38h+arg_0]
0x180055c10  add     rsp, 20h
0x180055c14  pop     r14
0x180055c16  pop     rdi
0x180055c17  pop     rsi
0x180055c18  retn
```
