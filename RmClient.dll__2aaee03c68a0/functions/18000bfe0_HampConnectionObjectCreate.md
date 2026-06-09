# HampConnectionObjectCreate

- ea: `0x18000bfe0`
- end: `0x18000c05d`
- name: `HampConnectionObjectCreate`
- size: `125`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000bed0`
- `0x180019620`

## callees

- `0x18000bfe0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000c00d`
- `ntdll!RtlAllocateHeap` at `0x18000c00d`

## pseudocode

```c
__int64 __fastcall HampConnectionObjectCreate(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *Heap; // rax

  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x40u);
  if ( !Heap )
    return 3221225495LL;
  *Heap = 0;
  Heap[1] = 0;
  Heap[2] = 0;
  Heap[3] = 0;
  Heap[4] = 0;
  Heap[5] = a2 + 24;
  Heap[7] = a1;
  Heap[6] = -1;
  *a3 = Heap;
  return 0;
}

```

## disassembly

```asm
0x18000bfe0  mov     [rsp+arg_0], rbx
0x18000bfe5  mov     [rsp+arg_8], rsi
0x18000bfea  push    rdi
0x18000bfeb  sub     rsp, 20h
0x18000bfef  mov     rsi, rcx
0x18000bff2  mov     rbx, r8
0x18000bff5  mov     rcx, gs:60h
0x18000bffe  mov     rdi, rdx
0x18000c001  xor     edx, edx; Flags
0x18000c003  mov     r8d, 40h ; '@'; Size
0x18000c009  mov     rcx, [rcx+30h]; HeapHandle
0x18000c00d  call    cs:__imp_RtlAllocateHeap
0x18000c013  test    rax, rax
0x18000c016  jz      short loc_18000C056
0x18000c018  xor     edx, edx
0x18000c01a  lea     rcx, [rdi+18h]
0x18000c01e  mov     [rax], rdx
0x18000c021  mov     [rax+8], rdx
0x18000c025  mov     [rax+10h], rdx
0x18000c029  mov     [rax+18h], rdx
0x18000c02d  mov     [rax+20h], rdx
0x18000c031  mov     [rax+28h], rcx
0x18000c035  mov     [rax+38h], rsi
0x18000c039  mov     qword ptr [rax+30h], 0FFFFFFFFFFFFFFFFh
0x18000c041  mov     [rbx], rax
0x18000c044  mov     eax, edx
0x18000c046  mov     rbx, [rsp+28h+arg_0]
0x18000c04b  mov     rsi, [rsp+28h+arg_8]
0x18000c050  add     rsp, 20h
0x18000c054  pop     rdi
0x18000c055  retn
0x18000c056  mov     eax, 0C0000017h
0x18000c05b  jmp     short loc_18000C046
```
