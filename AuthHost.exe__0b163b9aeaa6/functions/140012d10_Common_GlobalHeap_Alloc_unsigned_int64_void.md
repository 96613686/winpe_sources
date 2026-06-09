# Common::GlobalHeap::Alloc(unsigned __int64,void * *)

- ea: `0x140012d10`
- end: `0x140012d43`
- name: `?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z`
- size: `51`
- prototype: `__int64 __fastcall(unsigned __int64, void **)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003090`
- `0x14000cec0`
- `0x14000d538`
- `0x14000f12c`
- `0x14000f1b4`
- `0x14000f2ec`
- `0x140012cdc`
- `0x1400137a2`

## callees

- `0x140012d10`
- `0x140012d74`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140012d26`
- `ntdll!RtlAllocateHeap` at `0x140012d26`

## pseudocode

```c
__int64 __fastcall Common::GlobalHeap::Alloc(ReservedForLocalUse *a1, void **a2)
{
  void *Heap; // rax
  SIZE_T v4; // r8
  PVOID v5; // rax

  Heap = ReservedForLocalUse::GetHeap(a1);
  v5 = RtlAllocateHeap(Heap, 0, v4);
  if ( !v5 )
    return 2147942414LL;
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x140012d10  push    rbx
0x140012d12  sub     rsp, 20h
0x140012d16  mov     rbx, rdx
0x140012d19  mov     r8, rcx
0x140012d1c  call    ?GetHeap@ReservedForLocalUse@@YAPEAXXZ; ReservedForLocalUse::GetHeap(void)
0x140012d21  mov     rcx, rax; HeapHandle
0x140012d24  xor     edx, edx; Flags
0x140012d26  call    cs:__imp_RtlAllocateHeap
0x140012d2c  test    rax, rax
0x140012d2f  jnz     short loc_140012D38
0x140012d31  mov     eax, 8007000Eh
0x140012d36  jmp     short loc_140012D3D
0x140012d38  mov     [rbx], rax
0x140012d3b  xor     eax, eax
0x140012d3d  add     rsp, 20h
0x140012d41  pop     rbx
0x140012d42  retn
```
