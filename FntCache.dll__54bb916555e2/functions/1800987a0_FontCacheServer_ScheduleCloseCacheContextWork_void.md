# FontCacheServer::ScheduleCloseCacheContextWork(void)

- ea: `0x1800987a0`
- end: `0x180098813`
- name: `?ScheduleCloseCacheContextWork@FontCacheServer@@QEAAXXZ`
- size: `115`
- prototype: `void __fastcall(FontCacheServer *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18002a37c`
- `0x1800b1a10`

## callees

- `0x180068e24`
- `0x1800987a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009880c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800987c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800987c1`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800987f3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800987f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FontCacheServer::ScheduleCloseCacheContextWork(FontCacheServer *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( !*((_BYTE *)this + 176) )
  {
    if ( !*((_QWORD *)this + 24) )
      ThreadpoolWork::Initialize(
        (FontCacheServer *)((char *)this + 192),
        (void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *))FontCacheServer::CacheContextCloseCallback,
        this);
    SubmitThreadpoolWork(*((PTP_WORK *)this + 24));
  }
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x1800987a0  mov     [rsp+arg_8], rbx
0x1800987a5  mov     [rsp+arg_10], rsi
0x1800987aa  push    rdi
0x1800987ab  sub     rsp, 20h
0x1800987af  mov     rbx, rcx
0x1800987b2  lea     rsi, [rcx+88h]
0x1800987b9  mov     [rsp+28h+arg_0], rsi
0x1800987be  mov     rcx, rsi; lpCriticalSection
0x1800987c1  call    cs:__imp_EnterCriticalSection
0x1800987c7  nop
0x1800987c8  cmp     byte ptr [rbx+0B0h], 0
0x1800987cf  jnz     short loc_1800987FA
0x1800987d1  lea     rdi, [rbx+0C0h]
0x1800987d8  cmp     qword ptr [rdi], 0
0x1800987dc  jnz     short loc_1800987F0
0x1800987de  mov     r8, rbx; void *
0x1800987e1  lea     rdx, ?CacheContextCloseCallback@FontCacheServer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)
0x1800987e8  mov     rcx, rdi; this
0x1800987eb  call    ?Initialize@ThreadpoolWork@@QEAAXP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1@Z; ThreadpoolWork::Initialize(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)
0x1800987f0  mov     rcx, [rdi]; pwk
0x1800987f3  call    cs:__imp_SubmitThreadpoolWork
0x1800987f9  nop
0x1800987fa  mov     rcx, rsi
0x1800987fd  mov     rbx, [rsp+28h+arg_8]
0x180098802  mov     rsi, [rsp+28h+arg_10]
0x180098807  add     rsp, 20h
0x18009880b  pop     rdi
0x18009880c  jmp     cs:__imp_LeaveCriticalSection
```
