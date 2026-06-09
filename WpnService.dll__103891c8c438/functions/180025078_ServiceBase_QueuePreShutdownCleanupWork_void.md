# ServiceBase::QueuePreShutdownCleanupWork(void)

- ea: `0x180025078`
- end: `0x180025100`
- name: `?QueuePreShutdownCleanupWork@ServiceBase@@QEAAXXZ`
- size: `136`
- prototype: `void __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180013a60`

## callees

- `0x180025078`
- `0x180025108`
- `0x180025160`
- `0x1800251ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800250ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800250ba`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800250b2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800250b2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180025099`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180025099`

## pseudocode

```c
void __fastcall ServiceBase::QueuePreShutdownCleanupWork(char *Context)
{
  PTP_WORK *v2; // rbx
  PTP_WORK ThreadpoolWork; // rax
  signed int LastError; // eax
  __int64 v5; // rdx
  int v6; // [rsp+30h] [rbp+8h] BYREF
  char *v7; // [rsp+38h] [rbp+10h] BYREF

  v2 = (PTP_WORK *)(Context + 184);
  ThreadpoolWork = CreateThreadpoolWork((PTP_WORK_CALLBACK)ServiceBase::_PreShutdownCleanupWorker, Context, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
    v2,
    ThreadpoolWork);
  if ( *v2 )
  {
    SubmitThreadpoolWork(*v2);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = LastError;
    v7 = Context + 8;
    ServiceHostTelemetry::ServiceBaseError<unsigned short const *,unsigned short const (&)[36],long>(&v7, v5, &v6);
    ServiceBase::_PreShutdownCleanupWorker(0, (wil::details **)Context, 0);
  }
}

```

## disassembly

```asm
0x180025078  mov     [rsp+arg_10], rbx
0x18002507d  push    rdi
0x18002507e  sub     rsp, 20h
0x180025082  mov     rdi, rcx
0x180025085  lea     rbx, [rcx+0B8h]
0x18002508c  mov     rdx, rcx; pv
0x18002508f  xor     r8d, r8d; pcbe
0x180025092  lea     rcx, ?_PreShutdownCleanupWorker@ServiceBase@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180025099  call    cs:__imp_CreateThreadpoolWork
0x18002509f  mov     rdx, rax
0x1800250a2  mov     rcx, rbx
0x1800250a5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x1800250aa  mov     rcx, [rbx]; pwk
0x1800250ad  test    rcx, rcx
0x1800250b0  jz      short loc_1800250BA
0x1800250b2  call    cs:__imp_SubmitThreadpoolWork
0x1800250b8  jmp     short loc_1800250F5
0x1800250ba  call    cs:__imp_GetLastError
0x1800250c0  test    eax, eax
0x1800250c2  jle     short loc_1800250CC
0x1800250c4  movzx   eax, ax
0x1800250c7  or      eax, 80070000h
0x1800250cc  mov     [rsp+28h+arg_0], eax
0x1800250d0  lea     r8, [rsp+28h+arg_0]
0x1800250d5  lea     rax, [rdi+8]
0x1800250d9  lea     rcx, [rsp+28h+arg_8]
0x1800250de  mov     [rsp+28h+arg_8], rax
0x1800250e3  call    ??$ServiceBaseError@PEBGAEAY0CE@$$CBGJ@ServiceHostTelemetry@@SAX$$QEAPEBGAEAY0CE@$$CBG$$QEAJ@Z; ServiceHostTelemetry::ServiceBaseError<ushort const *,ushort const (&)[36],long>(ushort const * &&,ushort const (&)[36],long &&)
0x1800250e8  xor     r8d, r8d; Work
0x1800250eb  mov     rdx, rdi; Context
0x1800250ee  xor     ecx, ecx; Instance
0x1800250f0  call    ?_PreShutdownCleanupWorker@ServiceBase@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; ServiceBase::_PreShutdownCleanupWorker(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x1800250f5  mov     rbx, [rsp+28h+arg_10]
0x1800250fa  add     rsp, 20h
0x1800250fe  pop     rdi
0x1800250ff  retn
```
