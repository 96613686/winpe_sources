# AsyncWorkQueue::~AsyncWorkQueue(void)

- ea: `0x18000547c`
- end: `0x1800054f5`
- name: `??1AsyncWorkQueue@@MEAA@XZ`
- size: `121`
- prototype: `void __fastcall(AsyncWorkQueue *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005500`

## callees

- `0x18000547c`
- `0x180005bd4`
- `0x18000a8e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800054da`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800054da`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800054c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800054c8`

## pseudocode

```c
void __fastcall AsyncWorkQueue::~AsyncWorkQueue(AsyncWorkQueue *this)
{
  bool v1; // zf
  struct _TP_WORK *v3; // rcx

  v1 = *((_DWORD *)this + 23) == 0;
  *(_QWORD *)this = &AsyncWorkQueue::`vftable';
  if ( v1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((AsyncWorkQueue **)this + 7) != (AsyncWorkQueue *)((char *)this + 56) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_DWORD *)this + 22) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v3 = (struct _TP_WORK *)*((_QWORD *)this + 12);
  if ( v3 )
    CloseThreadpoolWork(v3);
  utl::list<AsyncWorkQueue::AsyncWorkItem,utl::allocator<AsyncWorkQueue::AsyncWorkItem>>::clear((char *)this + 56);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *(_QWORD *)this = &IAsyncWorkQueue::`vftable';
}

```

## disassembly

```asm
0x18000547c  mov     [rsp+arg_0], rbx
0x180005481  push    rdi
0x180005482  sub     rsp, 20h
0x180005486  cmp     dword ptr [rcx+5Ch], 0
0x18000548a  lea     rax, ??_7AsyncWorkQueue@@6B@; const AsyncWorkQueue::`vftable'
0x180005491  mov     [rcx], rax
0x180005494  mov     rbx, rcx
0x180005497  jnz     short loc_18000549E
0x180005499  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000549e  lea     rdi, [rbx+38h]
0x1800054a2  cmp     [rdi], rdi
0x1800054a5  jz      short loc_1800054AC
0x1800054a7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800054ac  mov     eax, [rbx+58h]
0x1800054af  test    eax, eax
0x1800054b1  jz      short loc_1800054BF
0x1800054b3  mov     eax, [rbx+58h]
0x1800054b6  test    eax, eax
0x1800054b8  jz      short loc_1800054BF
0x1800054ba  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800054bf  mov     rcx, [rbx+60h]; pwk
0x1800054c3  test    rcx, rcx
0x1800054c6  jz      short loc_1800054CE
0x1800054c8  call    cs:__imp_CloseThreadpoolWork
0x1800054ce  mov     rcx, rdi
0x1800054d1  call    ?clear@?$list@UAsyncWorkItem@AsyncWorkQueue@@V?$allocator@UAsyncWorkItem@AsyncWorkQueue@@@utl@@@utl@@QEAAXXZ; utl::list<AsyncWorkQueue::AsyncWorkItem,utl::allocator<AsyncWorkQueue::AsyncWorkItem>>::clear(void)
0x1800054d6  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800054da  call    cs:__imp_DeleteCriticalSection
0x1800054e0  lea     rax, ??_7IAsyncWorkQueue@@6B@; const IAsyncWorkQueue::`vftable'
0x1800054e7  mov     [rbx], rax
0x1800054ea  mov     rbx, [rsp+28h+arg_0]
0x1800054ef  add     rsp, 20h
0x1800054f3  pop     rdi
0x1800054f4  retn
```
