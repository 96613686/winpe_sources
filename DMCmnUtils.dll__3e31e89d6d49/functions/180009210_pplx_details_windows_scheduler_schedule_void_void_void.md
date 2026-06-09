# pplx::details::windows_scheduler::schedule(void (*)(void *),void *)

- ea: `0x180009210`
- end: `0x1800092b5`
- name: `?schedule@windows_scheduler@details@pplx@@UEAAXP6AXPEAX@Z0@Z`
- size: `165`
- prototype: `void __fastcall(pplx::details::windows_scheduler *__hidden this, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180007640`
- `0x180009120`
- `0x180009210`
- `0x180051d48`
- `0x1800522a2`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009291`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000927d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180009265`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180009265`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180009254`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180009254`

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
0x180009210  mov     [rsp+arg_0], rbx
0x180009215  mov     [rsp+arg_8], rsi
0x18000921a  push    rdi
0x18000921b  sub     rsp, 50h
0x18000921f  mov     ecx, 10h; Size
0x180009224  mov     rdi, r8
0x180009227  mov     rsi, rdx
0x18000922a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000922f  mov     [rsp+58h+arg_18], rax
0x180009234  mov     rbx, rax
0x180009237  test    rax, rax
0x18000923a  jz      short loc_180009245
0x18000923c  mov     [rax], rsi
0x18000923f  mov     [rax+8], rdi
0x180009243  jmp     short loc_180009247
0x180009245  xor     ebx, ebx
0x180009247  xor     r8d, r8d; pcbe
0x18000924a  lea     rcx, ?DefaultWorkCallback@_Scheduler_Param@details@pplx@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180009251  mov     rdx, rbx; pv
0x180009254  call    cs:__imp_CreateThreadpoolWork
0x18000925a  mov     rdi, rax
0x18000925d  test    rax, rax
0x180009260  jz      short loc_180009284
0x180009262  mov     rcx, rax; pwk
0x180009265  call    cs:__imp_SubmitThreadpoolWork
0x18000926b  mov     rcx, rdi
0x18000926e  mov     rbx, [rsp+58h+arg_0]
0x180009273  mov     rsi, [rsp+58h+arg_8]
0x180009278  add     rsp, 50h
0x18000927c  pop     rdi
0x18000927d  jmp     cs:__imp_CloseThreadpoolWork
0x180009284  mov     edx, 10h; struct std::nothrow_t *
0x180009289  mov     rcx, rbx; void *
0x18000928c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009291  call    cs:__imp_GetLastError
0x180009297  mov     edx, eax
0x180009299  lea     rcx, [rsp+58h+pExceptionObject]
0x18000929e  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x1800092a3  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x1800092aa  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800092af  call    _CxxThrowException_0
```
