# AddBSMRequest

- ea: `0x180002010`
- end: `0x18000216b`
- name: `AddBSMRequest`
- size: `347`
- prototype: `__int64 __fastcall(int, char, struct _LUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001010`

## callees

- `0x180002010`
- `0x180002180`
- `0x1800077b0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800020a3`
- `ntdll!RtlAllocateHeap` at `0x1800020a3`
- `ntdll!RtlEnterCriticalSection` at `0x1800020fb`
- `ntdll!RtlEnterCriticalSection` at `0x1800020fb`
- `ntdll!RtlCopyLuid` at `0x1800020e5`
- `ntdll!RtlCopyLuid` at `0x1800020e5`
- `ntdll!RtlLeaveCriticalSection` at `0x180002136`
- `ntdll!RtlLeaveCriticalSection` at `0x18000214e`
- `ntdll!RtlLeaveCriticalSection` at `0x180002136`
- `ntdll!RtlLeaveCriticalSection` at `0x18000214e`

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
0x180002010  mov     [rsp+arg_18], rbp
0x180002015  push    rsi
0x180002016  push    r14
0x180002018  push    r15
0x18000201a  sub     rsp, 20h
0x18000201e  xor     r15d, r15d
0x180002021  mov     rsi, r8
0x180002024  mov     qword ptr [rsp+38h+DestinationLuid.LowPart], r15
0x180002029  movzx   ebp, dl
0x18000202c  mov     r14d, ecx
0x18000202f  test    r8, r8
0x180002032  jnz     short loc_180002049
0x180002034  mov     eax, 0C000000Dh
0x180002039  mov     rbp, [rsp+38h+arg_18]
0x18000203e  add     rsp, 20h
0x180002042  pop     r15
0x180002044  pop     r14
0x180002046  pop     rsi
0x180002047  retn
0x180002049  mov     rax, cs:BaseSrvpStaticServerData
0x180002050  mov     [rsp+38h+arg_8], rdi
0x180002055  cmp     [rax+9CCh], r15b
0x18000205c  jz      loc_180002161
0x180002062  lea     rcx, [rsp+38h+DestinationLuid]; DestinationLuid
0x180002067  call    GetCallerLuid
0x18000206c  mov     edi, eax
0x18000206e  test    eax, eax
0x180002070  js      short loc_1800020C1
0x180002072  cmp     [rsp+38h+DestinationLuid.LowPart], 3E7h
0x18000207a  jnz     loc_180002161
0x180002080  cmp     [rsp+38h+DestinationLuid.HighPart], r15d
0x180002085  jnz     loc_180002161
0x18000208b  mov     edx, cs:BaseSrvTag; Flags
0x180002091  mov     r8d, 18h; Size
0x180002097  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x18000209e  mov     [rsp+38h+arg_0], rbx
0x1800020a3  call    cs:__imp_RtlAllocateHeap
0x1800020aa  nop     dword ptr [rax+rax+00h]
0x1800020af  mov     rbx, rax
0x1800020b2  test    rax, rax
0x1800020b5  jnz     short loc_1800020D6
0x1800020b7  mov     eax, 0C0000017h
0x1800020bc  mov     rbx, [rsp+38h+arg_0]
0x1800020c1  mov     rdi, [rsp+38h+arg_8]
0x1800020c6  mov     rbp, [rsp+38h+arg_18]
0x1800020cb  add     rsp, 20h
0x1800020cf  pop     r15
0x1800020d1  pop     r14
0x1800020d3  pop     rsi
0x1800020d4  retn
0x1800020d6  lea     rcx, [rax+8]; DestinationLuid
0x1800020da  mov     [rax+10h], r14d
0x1800020de  mov     rdx, rsi; SourceLuid
0x1800020e1  mov     [rax+14h], bpl
0x1800020e5  call    cs:__imp_RtlCopyLuid
0x1800020ec  nop     dword ptr [rax+rax+00h]
0x1800020f1  lea     rcx, BaseSrvDDDBSMCritSec; CriticalSection
0x1800020f8  mov     [rbx], r15
0x1800020fb  call    cs:__imp_RtlEnterCriticalSection
0x180002102  nop     dword ptr [rax+rax+00h]
0x180002107  mov     rax, cs:BSM_Request_Queue_End
0x18000210e  test    rax, rax
0x180002111  jz      short loc_180002118
0x180002113  mov     [rax], rbx
0x180002116  jmp     short loc_18000211F
0x180002118  mov     cs:BSM_Request_Queue, rbx
0x18000211f  cmp     cs:BaseSrvpBSMThreadCount, 1
0x180002126  lea     rcx, BaseSrvDDDBSMCritSec; CriticalSection
0x18000212d  mov     cs:BSM_Request_Queue_End, rbx
0x180002134  jge     short loc_18000214E
0x180002136  call    cs:__imp_RtlLeaveCriticalSection
0x18000213d  nop     dword ptr [rax+rax+00h]
0x180002142  call    CreateBSMThread
0x180002147  mov     edi, eax
0x180002149  jmp     loc_1800020BC
0x18000214e  call    cs:__imp_RtlLeaveCriticalSection
0x180002155  nop     dword ptr [rax+rax+00h]
0x18000215a  mov     eax, edi
0x18000215c  jmp     loc_1800020BC
0x180002161  mov     eax, 0C0000022h
0x180002166  jmp     loc_1800020C1
```
