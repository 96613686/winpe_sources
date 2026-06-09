# pplx::details::windows_scheduler::schedule(void (*)(void *),void *)

- ea: `0x18001b6c0`
- end: `0x18001b765`
- name: `?schedule@windows_scheduler@details@pplx@@UEAAXP6AXPEAX@Z0@Z`
- size: `165`
- prototype: `void __fastcall(pplx::details::windows_scheduler *__hidden this, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x18000bd9c`
- `0x18000bddc`
- `0x18000c510`
- `0x18001b5d0`
- `0x18001b6c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b741`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b741`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001b704`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001b704`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001b715`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001b715`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001b72d`

## pseudocode

```c
void __fastcall pplx::details::windows_scheduler::schedule(
        pplx::details::windows_scheduler *this,
        void (*a2)(void *),
        void *a3)
{
  _QWORD *v5; // rax
  void *v6; // rbx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v8; // rdi
  DWORD LastError; // eax
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-38h] BYREF

  v5 = operator new(0x10u);
  v6 = v5;
  if ( v5 )
  {
    *v5 = a2;
    v5[1] = a3;
  }
  else
  {
    v6 = 0;
  }
  ThreadpoolWork = CreateThreadpoolWork(pplx::details::_Scheduler_Param::DefaultWorkCallback, v6, 0);
  v8 = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    operator delete(v6, (const struct std::nothrow_t *)0x10);
    LastError = GetLastError();
    utility::details::create_system_error(pExceptionObject, LastError);
    throw (std::system_error *)pExceptionObject;
  }
  SubmitThreadpoolWork(ThreadpoolWork);
  CloseThreadpoolWork(v8);
}

```

## disassembly

```asm
0x18001b6c0  mov     [rsp+arg_0], rbx
0x18001b6c5  mov     [rsp+arg_8], rsi
0x18001b6ca  push    rdi
0x18001b6cb  sub     rsp, 50h
0x18001b6cf  mov     ecx, 10h; Size
0x18001b6d4  mov     rdi, r8
0x18001b6d7  mov     rsi, rdx
0x18001b6da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b6df  mov     [rsp+58h+arg_18], rax
0x18001b6e4  mov     rbx, rax
0x18001b6e7  test    rax, rax
0x18001b6ea  jz      short loc_18001B6F5
0x18001b6ec  mov     [rax], rsi
0x18001b6ef  mov     [rax+8], rdi
0x18001b6f3  jmp     short loc_18001B6F7
0x18001b6f5  xor     ebx, ebx
0x18001b6f7  xor     r8d, r8d; pcbe
0x18001b6fa  lea     rcx, ?DefaultWorkCallback@_Scheduler_Param@details@pplx@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001b701  mov     rdx, rbx; pv
0x18001b704  call    cs:__imp_CreateThreadpoolWork
0x18001b70a  mov     rdi, rax
0x18001b70d  test    rax, rax
0x18001b710  jz      short loc_18001B734
0x18001b712  mov     rcx, rax; pwk
0x18001b715  call    cs:__imp_SubmitThreadpoolWork
0x18001b71b  mov     rcx, rdi
0x18001b71e  mov     rbx, [rsp+58h+arg_0]
0x18001b723  mov     rsi, [rsp+58h+arg_8]
0x18001b728  add     rsp, 50h
0x18001b72c  pop     rdi
0x18001b72d  jmp     cs:__imp_CloseThreadpoolWork
0x18001b734  mov     edx, 10h; struct std::nothrow_t *
0x18001b739  mov     rcx, rbx; void *
0x18001b73c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b741  call    cs:__imp_GetLastError
0x18001b747  mov     edx, eax
0x18001b749  lea     rcx, [rsp+58h+pExceptionObject]
0x18001b74e  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18001b753  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18001b75a  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001b75f  call    _CxxThrowException_0
```
