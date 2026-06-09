# BaseSrvAllocateDOSRecord

- ea: `0x1800087b0`
- end: `0x180008801`
- name: `BaseSrvAllocateDOSRecord`
- size: `81`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008394`
- `0x180008938`

## callees

- `0x1800087b0`
- `0x18000db1d`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800087d5`
- `ntdll!RtlAllocateHeap` at `0x1800087d5`

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
0x1800087b0  push    rbx
0x1800087b2  sub     rsp, 20h
0x1800087b6  mov     rcx, gs:60h
0x1800087bf  mov     r8d, 50h ; 'P'; Size
0x1800087c5  mov     edx, cs:BaseSrvTag
0x1800087cb  add     edx, 40000h; Flags
0x1800087d1  mov     rcx, [rcx+30h]; HeapHandle
0x1800087d5  call    cs:__imp_RtlAllocateHeap
0x1800087dc  nop     dword ptr [rax+rax+00h]
0x1800087e1  mov     rbx, rax
0x1800087e4  test    rax, rax
0x1800087e7  jz      short loc_1800087FA
0x1800087e9  xor     edx, edx; Val
0x1800087eb  mov     rcx, rbx; void *
0x1800087ee  lea     r8d, [rdx+50h]; Size
0x1800087f2  call    memset_0
0x1800087f7  mov     rax, rbx
0x1800087fa  add     rsp, 20h
0x1800087fe  pop     rbx
0x1800087ff  retn
```
