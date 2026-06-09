# BaseSrvAllocateWOWRecord

- ea: `0x1800085bc`
- end: `0x18000863d`
- name: `BaseSrvAllocateWOWRecord`
- size: `129`
- prototype: `_DWORD *()`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18000821c`
- `0x180008d80`

## callees

- `0x1800085bc`
- `0x18000b4a4`
- `0x18000d713`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800085e1`
- `ntdll!RtlAllocateHeap` at `0x1800085e1`
- `ntdll!RtlFreeHeap` at `0x180008625`
- `ntdll!RtlFreeHeap` at `0x180008625`

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
0x1800085bc  push    rbx
0x1800085be  sub     rsp, 20h
0x1800085c2  mov     rcx, gs:60h
0x1800085cb  mov     r8d, 48h ; 'H'; Size
0x1800085d1  mov     edx, cs:BaseSrvTag
0x1800085d7  add     edx, 40000h; Flags
0x1800085dd  mov     rcx, [rcx+30h]; HeapHandle
0x1800085e1  call    cs:__imp_RtlAllocateHeap
0x1800085e8  nop     dword ptr [rax+rax+00h]
0x1800085ed  mov     rbx, rax
0x1800085f0  test    rax, rax
0x1800085f3  jnz     short loc_1800085F9
0x1800085f5  xor     eax, eax
0x1800085f7  jmp     short loc_180008636
0x1800085f9  xor     edx, edx; Val
0x1800085fb  mov     rcx, rbx; void *
0x1800085fe  lea     r8d, [rdx+48h]; Size
0x180008602  call    memset_0
0x180008607  call    BaseSrvGetWOWTaskId
0x18000860c  mov     [rbx], eax
0x18000860e  cmp     eax, 0FFFFFFFEh
0x180008611  jnz     short loc_180008633
0x180008613  mov     rcx, gs:60h
0x18000861c  mov     r8, rbx; P
0x18000861f  xor     edx, edx; Flags
0x180008621  mov     rcx, [rcx+30h]; HeapHandle
0x180008625  call    cs:__imp_RtlFreeHeap
0x18000862c  nop     dword ptr [rax+rax+00h]
0x180008631  jmp     short loc_1800085F5
0x180008633  mov     rax, rbx
0x180008636  add     rsp, 20h
0x18000863a  pop     rbx
0x18000863b  retn
```
