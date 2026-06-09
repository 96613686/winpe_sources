# BaseSrvAllocateDOSRecord

- ea: `0x1800084bc`
- end: `0x18000850d`
- name: `BaseSrvAllocateDOSRecord`
- size: `81`
- prototype: `PVOID()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000806c`
- `0x180008644`

## callees

- `0x1800084bc`
- `0x18000d713`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800084e1`
- `ntdll!RtlAllocateHeap` at `0x1800084e1`

## pseudocode

```c
PVOID BaseSrvAllocateDOSRecord()
{
  PVOID result; // rax
  PVOID v1; // rbx

  result = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, BaseSrvTag + 0x40000, 0x50u);
  v1 = result;
  if ( result )
  {
    memset_0(result, 0, 0x50u);
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x1800084bc  push    rbx
0x1800084be  sub     rsp, 20h
0x1800084c2  mov     rcx, gs:60h
0x1800084cb  mov     r8d, 50h ; 'P'; Size
0x1800084d1  mov     edx, cs:BaseSrvTag
0x1800084d7  add     edx, 40000h; Flags
0x1800084dd  mov     rcx, [rcx+30h]; HeapHandle
0x1800084e1  call    cs:__imp_RtlAllocateHeap
0x1800084e8  nop     dword ptr [rax+rax+00h]
0x1800084ed  mov     rbx, rax
0x1800084f0  test    rax, rax
0x1800084f3  jz      short loc_180008506
0x1800084f5  xor     edx, edx; Val
0x1800084f7  mov     rcx, rbx; void *
0x1800084fa  lea     r8d, [rdx+50h]; Size
0x1800084fe  call    memset_0
0x180008503  mov     rax, rbx
0x180008506  add     rsp, 20h
0x18000850a  pop     rbx
0x18000850b  retn
```
