# pplx::details::windows_scheduler::schedule(void (*)(void *),void *)

- ea: `0x180031030`
- end: `0x1800310c7`
- name: `?schedule@windows_scheduler@details@pplx@@UEAAXP6AXPEAX@Z0@Z`
- size: `151`
- prototype: `void __fastcall(pplx::details::windows_scheduler *__hidden this, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x18000529c`
- `0x18000575c`
- `0x180005e9c`
- `0x180030f20`
- `0x180031030`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031081`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800310a8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800310a8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800310c0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003106b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003106b`

## pseudocode

```c
void __fastcall pplx::details::windows_scheduler::schedule(
        pplx::details::windows_scheduler *this,
        void (*a2)(void *),
        void *a3)
{
  _QWORD *v5; // rsi
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v7; // rbx
  DWORD LastError; // eax
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-38h] BYREF

  v5 = operator new(0x10u);
  *v5 = a2;
  v5[1] = a3;
  ThreadpoolWork = CreateThreadpoolWork(pplx::details::_Scheduler_Param::DefaultWorkCallback, v5, 0);
  v7 = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    operator delete(v5);
    LastError = GetLastError();
    utility::details::create_system_error(pExceptionObject, LastError);
    throw (std::system_error *)pExceptionObject;
  }
  SubmitThreadpoolWork(ThreadpoolWork);
  CloseThreadpoolWork(v7);
}

```

## disassembly

```asm
0x180031030  mov     [rsp+arg_0], rbx
0x180031035  mov     [rsp+arg_8], rsi
0x18003103a  push    rdi
0x18003103b  sub     rsp, 50h
0x18003103f  mov     ecx, 10h; Size
0x180031044  mov     rdi, r8
0x180031047  mov     rbx, rdx
0x18003104a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003104f  xor     r8d, r8d; pcbe
0x180031052  mov     [rsp+58h+arg_18], rax
0x180031057  mov     rdx, rax; pv
0x18003105a  lea     rcx, ?DefaultWorkCallback@_Scheduler_Param@details@pplx@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180031061  mov     rsi, rax
0x180031064  mov     [rax], rbx
0x180031067  mov     [rax+8], rdi
0x18003106b  call    cs:__imp_CreateThreadpoolWork
0x180031071  mov     rbx, rax
0x180031074  test    rax, rax
0x180031077  jnz     short loc_1800310A5
0x180031079  mov     rcx, rsi; Block
0x18003107c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031081  call    cs:__imp_GetLastError
0x180031087  mov     edx, eax
0x180031089  lea     rcx, [rsp+58h+pExceptionObject]
0x18003108e  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x180031093  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18003109a  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18003109f  call    _CxxThrowException_0
0x1800310a5  mov     rcx, rbx; pwk
0x1800310a8  call    cs:__imp_SubmitThreadpoolWork
0x1800310ae  mov     rcx, rbx
0x1800310b1  mov     rbx, [rsp+58h+arg_0]
0x1800310b6  mov     rsi, [rsp+58h+arg_8]
0x1800310bb  add     rsp, 50h
0x1800310bf  pop     rdi
0x1800310c0  jmp     cs:__imp_CloseThreadpoolWork
```
