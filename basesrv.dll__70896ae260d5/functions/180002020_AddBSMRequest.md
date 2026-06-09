# AddBSMRequest

- ea: `0x180002020`
- end: `0x18000217b`
- name: `AddBSMRequest`
- size: `347`
- prototype: `__int64 __fastcall(int, char, struct _LUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001010`

## callees

- `0x180002020`
- `0x180002190`
- `0x1800074b0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800020b3`
- `ntdll!RtlAllocateHeap` at `0x1800020b3`
- `ntdll!RtlEnterCriticalSection` at `0x18000210b`
- `ntdll!RtlEnterCriticalSection` at `0x18000210b`
- `ntdll!RtlCopyLuid` at `0x1800020f5`
- `ntdll!RtlCopyLuid` at `0x1800020f5`
- `ntdll!RtlLeaveCriticalSection` at `0x180002146`
- `ntdll!RtlLeaveCriticalSection` at `0x18000215e`
- `ntdll!RtlLeaveCriticalSection` at `0x180002146`
- `ntdll!RtlLeaveCriticalSection` at `0x18000215e`

## pseudocode

```c
__int64 __fastcall AddBSMRequest(int a1, char a2, struct _LUID *a3)
{
  __int64 result; // rax
  unsigned int v7; // edi
  PVOID Heap; // rax
  _QWORD *v9; // rbx
  struct _LUID DestinationLuid; // [rsp+50h] [rbp+18h] BYREF

  DestinationLuid = 0;
  if ( !a3 )
    return 3221225485LL;
  if ( !*(_BYTE *)(BaseSrvpStaticServerData + 2508) )
    return 3221225506LL;
  result = GetCallerLuid(&DestinationLuid);
  v7 = result;
  if ( (int)result < 0 )
    return result;
  if ( DestinationLuid.LowPart != 999 || DestinationLuid.HighPart )
    return 3221225506LL;
  Heap = RtlAllocateHeap(BaseSrvHeap, BaseSrvTag, 0x18u);
  v9 = Heap;
  if ( !Heap )
    return 3221225495LL;
  *((_DWORD *)Heap + 4) = a1;
  *((_BYTE *)Heap + 20) = a2;
  RtlCopyLuid((PLUID)Heap + 1, a3);
  *v9 = 0;
  RtlEnterCriticalSection(&BaseSrvDDDBSMCritSec);
  if ( BSM_Request_Queue_End )
    *(_QWORD *)BSM_Request_Queue_End = v9;
  else
    BSM_Request_Queue = v9;
  BSM_Request_Queue_End = (__int64)v9;
  if ( BaseSrvpBSMThreadCount >= 1 )
  {
    RtlLeaveCriticalSection(&BaseSrvDDDBSMCritSec);
    return v7;
  }
  else
  {
    RtlLeaveCriticalSection(&BaseSrvDDDBSMCritSec);
    return CreateBSMThread();
  }
}

```

## disassembly

```asm
0x180002020  mov     [rsp+arg_18], rbp
0x180002025  push    rsi
0x180002026  push    r14
0x180002028  push    r15
0x18000202a  sub     rsp, 20h
0x18000202e  xor     r15d, r15d
0x180002031  mov     rsi, r8
0x180002034  mov     qword ptr [rsp+38h+DestinationLuid.LowPart], r15
0x180002039  movzx   ebp, dl
0x18000203c  mov     r14d, ecx
0x18000203f  test    r8, r8
0x180002042  jnz     short loc_180002059
0x180002044  mov     eax, 0C000000Dh
0x180002049  mov     rbp, [rsp+38h+arg_18]
0x18000204e  add     rsp, 20h
0x180002052  pop     r15
0x180002054  pop     r14
0x180002056  pop     rsi
0x180002057  retn
0x180002059  mov     rax, cs:BaseSrvpStaticServerData
0x180002060  mov     [rsp+38h+arg_8], rdi
0x180002065  cmp     [rax+9CCh], r15b
0x18000206c  jz      loc_180002171
0x180002072  lea     rcx, [rsp+38h+DestinationLuid]; DestinationLuid
0x180002077  call    GetCallerLuid
0x18000207c  mov     edi, eax
0x18000207e  test    eax, eax
0x180002080  js      short loc_1800020D1
0x180002082  cmp     [rsp+38h+DestinationLuid.LowPart], 3E7h
0x18000208a  jnz     loc_180002171
0x180002090  cmp     [rsp+38h+DestinationLuid.HighPart], r15d
0x180002095  jnz     loc_180002171
0x18000209b  mov     edx, cs:BaseSrvTag; Flags
0x1800020a1  mov     r8d, 18h; Size
0x1800020a7  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x1800020ae  mov     [rsp+38h+arg_0], rbx
0x1800020b3  call    cs:__imp_RtlAllocateHeap
0x1800020ba  nop     dword ptr [rax+rax+00h]
0x1800020bf  mov     rbx, rax
0x1800020c2  test    rax, rax
0x1800020c5  jnz     short loc_1800020E6
0x1800020c7  mov     eax, 0C0000017h
0x1800020cc  mov     rbx, [rsp+38h+arg_0]
0x1800020d1  mov     rdi, [rsp+38h+arg_8]
0x1800020d6  mov     rbp, [rsp+38h+arg_18]
0x1800020db  add     rsp, 20h
0x1800020df  pop     r15
0x1800020e1  pop     r14
0x1800020e3  pop     rsi
0x1800020e4  retn
0x1800020e6  lea     rcx, [rax+8]; DestinationLuid
0x1800020ea  mov     [rax+10h], r14d
0x1800020ee  mov     rdx, rsi; SourceLuid
0x1800020f1  mov     [rax+14h], bpl
0x1800020f5  call    cs:__imp_RtlCopyLuid
0x1800020fc  nop     dword ptr [rax+rax+00h]
0x180002101  lea     rcx, BaseSrvDDDBSMCritSec; CriticalSection
0x180002108  mov     [rbx], r15
0x18000210b  call    cs:__imp_RtlEnterCriticalSection
0x180002112  nop     dword ptr [rax+rax+00h]
0x180002117  mov     rax, cs:BSM_Request_Queue_End
0x18000211e  test    rax, rax
0x180002121  jz      short loc_180002128
0x180002123  mov     [rax], rbx
0x180002126  jmp     short loc_18000212F
0x180002128  mov     cs:BSM_Request_Queue, rbx
0x18000212f  cmp     cs:BaseSrvpBSMThreadCount, 1
0x180002136  lea     rcx, BaseSrvDDDBSMCritSec; CriticalSection
0x18000213d  mov     cs:BSM_Request_Queue_End, rbx
0x180002144  jge     short loc_18000215E
0x180002146  call    cs:__imp_RtlLeaveCriticalSection
0x18000214d  nop     dword ptr [rax+rax+00h]
0x180002152  call    CreateBSMThread
0x180002157  mov     edi, eax
0x180002159  jmp     loc_1800020CC
0x18000215e  call    cs:__imp_RtlLeaveCriticalSection
0x180002165  nop     dword ptr [rax+rax+00h]
0x18000216a  mov     eax, edi
0x18000216c  jmp     loc_1800020CC
0x180002171  mov     eax, 0C0000022h
0x180002176  jmp     loc_1800020D1
```
