# CTimer::_OnTimerTick(void)

- ea: `0x18006a35c`
- end: `0x18006a3a7`
- name: `?_OnTimerTick@CTimer@@AEAAXXZ`
- size: `75`
- prototype: `void __fastcall(CTimer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006a320`

## callees

- `0x18006a35c`
- `0x18006a3b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a375`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a375`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a396`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a396`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006a37c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006a37c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTimer::_OnTimerTick(CTimer *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 18) = GetCurrentThreadId();
  CTimer::_OnTimerCallback(this);
  if ( v2 )
    LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x18006a35c  mov     [rsp+arg_8], rbx
0x18006a361  push    rdi
0x18006a362  sub     rsp, 20h
0x18006a366  mov     rbx, rcx
0x18006a369  lea     rdi, [rcx+10h]
0x18006a36d  mov     [rsp+28h+arg_0], rdi
0x18006a372  mov     rcx, rdi; lpCriticalSection
0x18006a375  call    cs:__imp_EnterCriticalSection
0x18006a37b  nop
0x18006a37c  call    cs:__imp_GetCurrentThreadId
0x18006a382  mov     [rbx+48h], eax
0x18006a385  mov     rcx, rbx; this
0x18006a388  call    ?_OnTimerCallback@CTimer@@AEAAXXZ; CTimer::_OnTimerCallback(void)
0x18006a38d  nop
0x18006a38e  test    rdi, rdi
0x18006a391  jz      short loc_18006A39C
0x18006a393  mov     rcx, rdi; lpCriticalSection
0x18006a396  call    cs:__imp_LeaveCriticalSection
0x18006a39c  mov     rbx, [rsp+28h+arg_8]
0x18006a3a1  add     rsp, 20h
0x18006a3a5  pop     rdi
0x18006a3a6  retn
```
