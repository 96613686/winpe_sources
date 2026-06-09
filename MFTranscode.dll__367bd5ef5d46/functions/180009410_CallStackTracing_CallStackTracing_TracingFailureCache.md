# CallStackTracing::CallStackTracing(TracingFailureCache *)

- ea: `0x180009410`
- end: `0x18000952e`
- name: `??0CallStackTracing@@QEAA@PEAVTracingFailureCache@@@Z`
- size: `286`
- prototype: `CallStackTracing *__fastcall(CallStackTracing *__hidden this, struct TracingFailureCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001680`

## callees

- `0x180009410`
- `0x180017e20`
- `0x18004f044`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000950b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000950b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009447`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009454`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009480`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009447`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009454`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009480`

## pseudocode

```c
CallStackTracing *__fastcall CallStackTracing::CallStackTracing(CallStackTracing *this, struct TracingFailureCache *a2)
{
  CallStackInfo *v2; // rbx
  __int64 v3; // rdi
  CallStackTracing *result; // rax

  dword_180069A9C = -1;
  qword_180069A90 = (__int64)&CallStackTracing::`vftable';
  byte_180069A98 = 0;
  InitializeCriticalSection(&CriticalSection);
  InitializeCriticalSection(&stru_180069AC8);
  byte_180069AF0 = 0;
  qword_180069AF8 = (__int64)&CFreeList<CallStackContextNode,16>::`vftable';
  dword_180069B00 = 16;
  InitializeCriticalSection(&stru_180069B08);
  qword_180069B30 = 0;
  xmmword_180069B40 = 0;
  v2 = (CallStackInfo *)qword_180069B60;
  qword_180069B38 = 0;
  v3 = 124;
  qword_180069B50 = 0;
  byte_180069B58 = 0;
  do
  {
    CallStackInfo::CallStackInfo(v2);
    v2 = (CallStackInfo *)((char *)v2 + 16);
    --v3;
  }
  while ( v3 );
  dword_18006A328 = 0;
  memset_0(qword_180069B60, 0, 0x7C0u);
  dword_18006A324 = 0;
  qword_18006A340 = 0;
  xmmword_18006A330 = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  dword_18006A32C = 0;
  dword_18006A348 = 0;
  GetCurrentThreadId();
  result = (CallStackTracing *)&qword_180069A90;
  dword_18006A320 = 0;
  return result;
}

```

## disassembly

```asm
0x180009410  mov     [rsp+arg_0], rbx
0x180009415  mov     [rsp+arg_8], rsi
0x18000941a  push    rdi
0x18000941b  sub     rsp, 20h
0x18000941f  lea     rax, ??_7CallStackTracing@@6B@; const CallStackTracing::`vftable'
0x180009426  mov     cs:dword_180069A9C, 0FFFFFFFFh
0x180009430  xor     esi, esi
0x180009432  mov     cs:qword_180069A90, rax
0x180009439  lea     rcx, CriticalSection; lpCriticalSection
0x180009440  mov     cs:byte_180069A98, sil
0x180009447  call    cs:__imp_InitializeCriticalSection
0x18000944d  lea     rcx, stru_180069AC8; lpCriticalSection
0x180009454  call    cs:__imp_InitializeCriticalSection
0x18000945a  lea     rax, ??_7?$CFreeList@VCallStackContextNode@@$0BA@@@6B@; const CFreeList<CallStackContextNode,16>::`vftable'
0x180009461  mov     cs:byte_180069AF0, sil
0x180009468  lea     rcx, stru_180069B08; lpCriticalSection
0x18000946f  mov     cs:qword_180069AF8, rax
0x180009476  mov     cs:dword_180069B00, 10h
0x180009480  call    cs:__imp_InitializeCriticalSection
0x180009486  xorps   xmm0, xmm0
0x180009489  mov     cs:qword_180069B30, rsi
0x180009490  movdqa  cs:xmmword_180069B40, xmm0
0x180009498  lea     rbx, qword_180069B60
0x18000949f  mov     cs:qword_180069B38, rsi
0x1800094a6  lea     edi, [rsi+7Ch]
0x1800094a9  mov     cs:qword_180069B50, rsi
0x1800094b0  mov     cs:byte_180069B58, sil
0x1800094b7  mov     rcx, rbx; this
0x1800094ba  call    ??0CallStackInfo@@QEAA@XZ; CallStackInfo::CallStackInfo(void)
0x1800094bf  add     rbx, 10h
0x1800094c3  sub     rdi, 1
0x1800094c7  jnz     short loc_1800094B7
0x1800094c9  xor     edx, edx; Val
0x1800094cb  mov     cs:dword_18006A328, esi
0x1800094d1  mov     r8d, 7C0h; Size
0x1800094d7  lea     rcx, qword_180069B60; void *
0x1800094de  call    memset_0
0x1800094e3  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800094ea  mov     cs:dword_18006A324, esi
0x1800094f0  mov     cs:qword_18006A340, rsi
0x1800094f7  movdqu  cs:xmmword_18006A330, xmm0
0x1800094ff  mov     cs:dword_18006A32C, esi
0x180009505  mov     cs:dword_18006A348, esi
0x18000950b  call    cs:__imp_GetCurrentThreadId
0x180009511  mov     rbx, [rsp+28h+arg_0]
0x180009516  lea     rax, qword_180069A90
0x18000951d  mov     cs:dword_18006A320, esi
0x180009523  mov     rsi, [rsp+28h+arg_8]
0x180009528  add     rsp, 20h
0x18000952c  pop     rdi
0x18000952d  retn
```
