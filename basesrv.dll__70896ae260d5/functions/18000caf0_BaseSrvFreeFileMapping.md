# BaseSrvFreeFileMapping

- ea: `0x18000caf0`
- end: `0x18000cb31`
- name: `BaseSrvFreeFileMapping`
- size: `65`
- prototype: `BOOLEAN __fastcall(PVOID *P)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004d80`
- `0x180005f10`

## callees

- `0x18000caa0`
- `0x18000caf0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000cb1e`
- `ntdll!RtlFreeHeap` at `0x18000cb1e`

## pseudocode

```c
BOOLEAN __fastcall BaseSrvFreeFileMapping(PVOID *P)
{
  BOOLEAN result; // al

  if ( P )
  {
    BaseSrvFreeAppNameMapping(P[3]);
    BaseSrvFreeAppNameMapping(P[4]);
    return RtlFreeHeap(BaseSrvSharedHeap, 1u, P);
  }
  return result;
}

```

## disassembly

```asm
0x18000caf0  test    rcx, rcx
0x18000caf3  jz      short locret_18000CB2F
0x18000caf5  push    rbx
0x18000caf6  sub     rsp, 20h
0x18000cafa  mov     rbx, rcx
0x18000cafd  mov     rcx, [rcx+18h]; P
0x18000cb01  call    BaseSrvFreeAppNameMapping
0x18000cb06  mov     rcx, [rbx+20h]; P
0x18000cb0a  call    BaseSrvFreeAppNameMapping
0x18000cb0f  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x18000cb16  mov     r8, rbx; P
0x18000cb19  mov     edx, 1; Flags
0x18000cb1e  call    cs:__imp_RtlFreeHeap
0x18000cb25  nop     dword ptr [rax+rax+00h]
0x18000cb2a  add     rsp, 20h
0x18000cb2e  pop     rbx
0x18000cb2f  retn
```
