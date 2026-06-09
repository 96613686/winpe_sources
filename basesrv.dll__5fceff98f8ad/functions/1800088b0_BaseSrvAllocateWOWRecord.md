# BaseSrvAllocateWOWRecord

- ea: `0x1800088b0`
- end: `0x180008931`
- name: `BaseSrvAllocateWOWRecord`
- size: `129`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180008528`
- `0x18000905c`

## callees

- `0x1800088b0`
- `0x18000b750`
- `0x18000db1d`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800088d5`
- `ntdll!RtlAllocateHeap` at `0x1800088d5`
- `ntdll!RtlFreeHeap` at `0x180008919`
- `ntdll!RtlFreeHeap` at `0x180008919`

## pseudocode

```c
_DWORD *BaseSrvAllocateWOWRecord()
{
  _DWORD *Heap; // rax
  _DWORD *v1; // rbx
  int WOWTaskId; // eax

  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, BaseSrvTag + 0x40000, 0x48u);
  v1 = Heap;
  if ( !Heap )
    return 0;
  memset_0(Heap, 0, 0x48u);
  WOWTaskId = BaseSrvGetWOWTaskId();
  *v1 = WOWTaskId;
  if ( WOWTaskId == -2 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x1800088b0  push    rbx
0x1800088b2  sub     rsp, 20h
0x1800088b6  mov     rcx, gs:60h
0x1800088bf  mov     r8d, 48h ; 'H'; Size
0x1800088c5  mov     edx, cs:BaseSrvTag
0x1800088cb  add     edx, 40000h; Flags
0x1800088d1  mov     rcx, [rcx+30h]; HeapHandle
0x1800088d5  call    cs:__imp_RtlAllocateHeap
0x1800088dc  nop     dword ptr [rax+rax+00h]
0x1800088e1  mov     rbx, rax
0x1800088e4  test    rax, rax
0x1800088e7  jnz     short loc_1800088ED
0x1800088e9  xor     eax, eax
0x1800088eb  jmp     short loc_18000892A
0x1800088ed  xor     edx, edx; Val
0x1800088ef  mov     rcx, rbx; void *
0x1800088f2  lea     r8d, [rdx+48h]; Size
0x1800088f6  call    memset_0
0x1800088fb  call    BaseSrvGetWOWTaskId
0x180008900  mov     [rbx], eax
0x180008902  cmp     eax, 0FFFFFFFEh
0x180008905  jnz     short loc_180008927
0x180008907  mov     rcx, gs:60h
0x180008910  mov     r8, rbx; P
0x180008913  xor     edx, edx; Flags
0x180008915  mov     rcx, [rcx+30h]; HeapHandle
0x180008919  call    cs:__imp_RtlFreeHeap
0x180008920  nop     dword ptr [rax+rax+00h]
0x180008925  jmp     short loc_1800088E9
0x180008927  mov     rax, rbx
0x18000892a  add     rsp, 20h
0x18000892e  pop     rbx
0x18000892f  retn
```
