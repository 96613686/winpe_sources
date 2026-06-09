# pplx::details::windows_scheduler::schedule(void (*)(void *),void *)

- ea: `0x18001b6a0`
- end: `0x18001b745`
- name: `?schedule@windows_scheduler@details@pplx@@UEAAXP6AXPEAX@Z0@Z`
- size: `165`
- prototype: `void __fastcall(pplx::details::windows_scheduler *__hidden this, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x18000bccc`
- `0x18000bd0c`
- `0x18000c420`
- `0x18001b5b0`
- `0x18001b6a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b721`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b721`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001b6e4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001b6e4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001b6f5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001b6f5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001b70d`

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
0x18001b6a0  mov     [rsp+arg_0], rbx
0x18001b6a5  mov     [rsp+arg_8], rsi
0x18001b6aa  push    rdi
0x18001b6ab  sub     rsp, 50h
0x18001b6af  mov     ecx, 10h; Size
0x18001b6b4  mov     rdi, r8
0x18001b6b7  mov     rsi, rdx
0x18001b6ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b6bf  mov     [rsp+58h+arg_18], rax
0x18001b6c4  mov     rbx, rax
0x18001b6c7  test    rax, rax
0x18001b6ca  jz      short loc_18001B6D5
0x18001b6cc  mov     [rax], rsi
0x18001b6cf  mov     [rax+8], rdi
0x18001b6d3  jmp     short loc_18001B6D7
0x18001b6d5  xor     ebx, ebx
0x18001b6d7  xor     r8d, r8d; pcbe
0x18001b6da  lea     rcx, ?DefaultWorkCallback@_Scheduler_Param@details@pplx@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001b6e1  mov     rdx, rbx; pv
0x18001b6e4  call    cs:__imp_CreateThreadpoolWork
0x18001b6ea  mov     rdi, rax
0x18001b6ed  test    rax, rax
0x18001b6f0  jz      short loc_18001B714
0x18001b6f2  mov     rcx, rax; pwk
0x18001b6f5  call    cs:__imp_SubmitThreadpoolWork
0x18001b6fb  mov     rcx, rdi
0x18001b6fe  mov     rbx, [rsp+58h+arg_0]
0x18001b703  mov     rsi, [rsp+58h+arg_8]
0x18001b708  add     rsp, 50h
0x18001b70c  pop     rdi
0x18001b70d  jmp     cs:__imp_CloseThreadpoolWork
0x18001b714  mov     edx, 10h; struct std::nothrow_t *
0x18001b719  mov     rcx, rbx; void *
0x18001b71c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b721  call    cs:__imp_GetLastError
0x18001b727  mov     edx, eax
0x18001b729  lea     rcx, [rsp+58h+pExceptionObject]
0x18001b72e  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18001b733  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18001b73a  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001b73f  call    _CxxThrowException_0
```
