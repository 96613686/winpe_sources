# BaseSrvFreeAppNameMapping

- ea: `0x18000caa0`
- end: `0x18000cae9`
- name: `BaseSrvFreeAppNameMapping`
- size: `73`
- prototype: `BOOLEAN __fastcall(PVOID **P)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000caa0`
- `0x18000caf0`

## callees

- `0x180007470`
- `0x18000caa0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000cad6`
- `ntdll!RtlFreeHeap` at `0x18000cad6`

## pseudocode

```c
BOOLEAN __fastcall BaseSrvFreeAppNameMapping(PVOID **P)
{
  BOOLEAN result; // al

  if ( P )
  {
    BaseSrvFreeVarNameMapping(P[3]);
    BaseSrvFreeVarNameMapping(P[4]);
    BaseSrvFreeAppNameMapping(*P);
    return RtlFreeHeap(BaseSrvSharedHeap, 1u, P);
  }
  return result;
}

```

## disassembly

```asm
0x18000caa0  test    rcx, rcx
0x18000caa3  jz      short locret_18000CAE7
0x18000caa5  push    rbx
0x18000caa6  sub     rsp, 20h
0x18000caaa  mov     rbx, rcx
0x18000caad  mov     rcx, [rcx+18h]; P
0x18000cab1  call    BaseSrvFreeVarNameMapping
0x18000cab6  mov     rcx, [rbx+20h]; P
0x18000caba  call    BaseSrvFreeVarNameMapping
0x18000cabf  mov     rcx, [rbx]; P
0x18000cac2  call    BaseSrvFreeAppNameMapping
0x18000cac7  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x18000cace  mov     r8, rbx; P
0x18000cad1  mov     edx, 1; Flags
0x18000cad6  call    cs:__imp_RtlFreeHeap
0x18000cadd  nop     dword ptr [rax+rax+00h]
0x18000cae2  add     rsp, 20h
0x18000cae6  pop     rbx
0x18000cae7  retn
```
