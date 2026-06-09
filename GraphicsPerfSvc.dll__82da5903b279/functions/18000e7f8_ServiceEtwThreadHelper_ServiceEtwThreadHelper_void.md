# ServiceEtwThreadHelper::~ServiceEtwThreadHelper(void)

- ea: `0x18000e7f8`
- end: `0x18000e84c`
- name: `??1ServiceEtwThreadHelper@@QEAA@XZ`
- size: `84`
- prototype: `void __fastcall(ServiceEtwThreadHelper *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000e9f0`

## callees

- `0x180005c6c`
- `0x18000e760`
- `0x18000e7f8`
- `0x1800106cc`
- `0x1800112d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e80f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e80f`

## pseudocode

```c
void __fastcall ServiceEtwThreadHelper::~ServiceEtwThreadHelper(ServiceEtwThreadHelper *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // [rsp+30h] [rbp+8h] BYREF

  EnterCriticalSection(&g::ShutdownCritsect);
  v2 = &g::ShutdownCritsect;
  ServiceEtwThreadHelper::WaitForJoinAndResetTraceConsumer(this);
  if ( *(_DWORD *)(*(_QWORD *)this + 8LL) )
    std::thread::detach(*(std::thread **)this);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v2);
  std::unique_ptr<std::thread>::~unique_ptr<std::thread>(this);
}

```

## disassembly

```asm
0x18000e7f8  mov     [rsp+arg_8], rbx
0x18000e7fd  push    rdi
0x18000e7fe  sub     rsp, 20h
0x18000e802  mov     rbx, rcx
0x18000e805  lea     rdi, ?ShutdownCritsect@g@@3Vcritical_section@wil@@A; wil::critical_section g::ShutdownCritsect
0x18000e80c  mov     rcx, rdi; lpCriticalSection
0x18000e80f  call    cs:__imp_EnterCriticalSection
0x18000e815  mov     [rsp+28h+arg_0], rdi
0x18000e81a  mov     rcx, rbx; this
0x18000e81d  call    ?WaitForJoinAndResetTraceConsumer@ServiceEtwThreadHelper@@QEAAXXZ; ServiceEtwThreadHelper::WaitForJoinAndResetTraceConsumer(void)
0x18000e822  mov     rcx, [rbx]; this
0x18000e825  cmp     dword ptr [rcx+8], 0
0x18000e829  jz      short loc_18000E830
0x18000e82b  call    ?detach@thread@std@@QEAAXXZ; std::thread::detach(void)
0x18000e830  lea     rcx, [rsp+28h+arg_0]
0x18000e835  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000e83a  mov     rcx, rbx
0x18000e83d  mov     rbx, [rsp+28h+arg_8]
0x18000e842  add     rsp, 20h
0x18000e846  pop     rdi
0x18000e847  jmp     ??1?$unique_ptr@Vthread@std@@U?$default_delete@Vthread@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::thread>::~unique_ptr<std::thread>(void)
```
