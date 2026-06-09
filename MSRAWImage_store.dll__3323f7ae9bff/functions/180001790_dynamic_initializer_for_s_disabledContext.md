# _dynamic_initializer_for__s_disabledContext__

- ea: `0x180001790`
- end: `0x1800018ac`
- name: `_dynamic_initializer_for__s_disabledContext__`
- size: `284`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001790`
- `0x180002df8`
- `0x1800a3128`
- `0x1800b0b00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800017a6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800017b9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800017eb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800017a6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800017b9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800017eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000187f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000187f`

## pseudocode

```c
int dynamic_initializer_for__s_disabledContext__()
{
  CallStackInfo *v0; // rdi
  __int64 v1; // rbx

  InitializeCriticalSection(&CriticalSection);
  InitializeCriticalSection(&stru_1800E51C8);
  byte_1800E51F0 = 0;
  qword_1800E51F8 = (__int64)&CFreeList<CallStackContextNode,16>::`vftable';
  dword_1800E5200 = 16;
  InitializeCriticalSection(&stru_1800E5208);
  v0 = (CallStackInfo *)qword_1800E5260;
  qword_1800E5230 = 0;
  qword_1800E5238 = 0;
  v1 = 124;
  xmmword_1800E5240 = 0;
  qword_1800E5250 = 0;
  byte_1800E5258 = 0;
  do
  {
    CallStackInfo::CallStackInfo(v0);
    v0 = (CallStackInfo *)((char *)v0 + 16);
    --v1;
  }
  while ( v1 );
  dword_1800E5A28 = 0;
  memset(qword_1800E5260, 0, sizeof(qword_1800E5260));
  dword_1800E5A24 = 0;
  qword_1800E5A40 = 0;
  xmmword_1800E5A30 = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  dword_1800E5A2C = 0;
  dword_1800E5A48 = 0;
  GetCurrentThreadId();
  dword_1800E5A20 = 0;
  return atexit(dynamic_atexit_destructor_for__s_disabledContext__);
}

```

## disassembly

```asm
0x180001790  mov     [rsp+arg_0], rbx
0x180001795  mov     [rsp+arg_8], rsi
0x18000179a  push    rdi
0x18000179b  sub     rsp, 20h
0x18000179f  lea     rcx, CriticalSection; lpCriticalSection
0x1800017a6  call    cs:__imp_InitializeCriticalSection
0x1800017ad  nop     dword ptr [rax+rax+00h]
0x1800017b2  lea     rcx, stru_1800E51C8; lpCriticalSection
0x1800017b9  call    cs:__imp_InitializeCriticalSection
0x1800017c0  nop     dword ptr [rax+rax+00h]
0x1800017c5  lea     rax, ??_7?$CFreeList@VCallStackContextNode@@$0BA@@@6B@; const CFreeList<CallStackContextNode,16>::`vftable'
0x1800017cc  mov     cs:byte_1800E51F0, 0
0x1800017d3  lea     rcx, stru_1800E5208; lpCriticalSection
0x1800017da  mov     cs:qword_1800E51F8, rax
0x1800017e1  mov     cs:dword_1800E5200, 10h
0x1800017eb  call    cs:__imp_InitializeCriticalSection
0x1800017f2  nop     dword ptr [rax+rax+00h]
0x1800017f7  xor     esi, esi
0x1800017f9  lea     rdi, qword_1800E5260
0x180001800  xorps   xmm0, xmm0
0x180001803  mov     cs:qword_1800E5230, rsi
0x18000180a  mov     cs:qword_1800E5238, rsi
0x180001811  mov     ebx, 7Ch ; '|'
0x180001816  movdqa  cs:xmmword_1800E5240, xmm0
0x18000181e  mov     cs:qword_1800E5250, rsi
0x180001825  mov     cs:byte_1800E5258, sil
0x18000182c  mov     rcx, rdi; this
0x18000182f  call    ??0CallStackInfo@@QEAA@XZ; CallStackInfo::CallStackInfo(void)
0x180001834  add     rdi, 10h
0x180001838  sub     rbx, 1
0x18000183c  jnz     short loc_18000182C
0x18000183e  xor     edx, edx; Val
0x180001840  mov     cs:dword_1800E5A28, esi
0x180001846  mov     r8d, 7C0h; Size
0x18000184c  lea     rcx, qword_1800E5260; void *
0x180001853  call    memset
0x180001858  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18000185f  mov     cs:dword_1800E5A24, esi
0x180001865  mov     cs:qword_1800E5A40, rsi
0x18000186c  movaps  cs:xmmword_1800E5A30, xmm0
0x180001873  mov     cs:dword_1800E5A2C, esi
0x180001879  mov     cs:dword_1800E5A48, esi
0x18000187f  call    cs:__imp_GetCurrentThreadId
0x180001886  nop     dword ptr [rax+rax+00h]
0x18000188b  lea     rcx, _dynamic_atexit_destructor_for__s_disabledContext__
0x180001892  mov     cs:dword_1800E5A20, esi
0x180001898  mov     rbx, [rsp+28h+arg_0]
0x18000189d  mov     rsi, [rsp+28h+arg_8]
0x1800018a2  add     rsp, 20h
0x1800018a6  pop     rdi
0x1800018a7  jmp     atexit
```
