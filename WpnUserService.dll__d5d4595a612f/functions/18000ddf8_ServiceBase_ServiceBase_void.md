# ServiceBase::~ServiceBase(void)

- ea: `0x18000ddf8`
- end: `0x18000de6d`
- name: `??1ServiceBase@@UEAA@XZ`
- size: `117`
- prototype: `void __fastcall(ServiceBase *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180008654`
- `0x18000e2b0`

## callees

- `0x1800071a8`
- `0x18000ddf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000de39`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000de39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de48`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000de23`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000de23`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000de2c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000de2c`

## pseudocode

```c
void __fastcall ServiceBase::~ServiceBase(ServiceBase *this)
{
  struct _TP_WORK *v2; // rdi
  void *v3; // rcx
  unsigned int v4; // r8d
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &ServiceBase::`vftable';
  v2 = (struct _TP_WORK *)*((_QWORD *)this + 23);
  if ( v2 )
  {
    WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 23), 1);
    CloseThreadpoolWork(v2);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v3 = (void *)*((_QWORD *)this + 10);
  if ( v3 )
  {
    if ( !CloseHandle(v3) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v4, v5);
  }
}

```

## disassembly

```asm
0x18000ddf8  mov     [rsp+arg_0], rbx
0x18000ddfd  push    rdi
0x18000ddfe  sub     rsp, 20h
0x18000de02  lea     rax, ??_7ServiceBase@@6B@; const ServiceBase::`vftable'
0x18000de09  mov     rbx, rcx
0x18000de0c  mov     [rcx], rax
0x18000de0f  mov     rdi, [rcx+0B8h]
0x18000de16  test    rdi, rdi
0x18000de19  jz      short loc_18000DE32
0x18000de1b  mov     edx, 1; fCancelPendingCallbacks
0x18000de20  mov     rcx, rdi; pwk
0x18000de23  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000de29  mov     rcx, rdi; pwk
0x18000de2c  call    cs:__imp_CloseThreadpoolWork
0x18000de32  lea     rcx, [rbx+88h]; lpCriticalSection
0x18000de39  call    cs:__imp_DeleteCriticalSection
0x18000de3f  mov     rcx, [rbx+50h]; hObject
0x18000de43  test    rcx, rcx
0x18000de46  jz      short loc_18000DE52
0x18000de48  call    cs:__imp_CloseHandle
0x18000de4e  test    eax, eax
0x18000de50  jz      short loc_18000DE5D
0x18000de52  mov     rbx, [rsp+28h+arg_0]
0x18000de57  add     rsp, 20h
0x18000de5b  pop     rdi
0x18000de5c  retn
0x18000de5d  mov     rcx, [rsp+28h]; this
0x18000de62  mov     edx, 0A0Bh; void *
0x18000de67  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
