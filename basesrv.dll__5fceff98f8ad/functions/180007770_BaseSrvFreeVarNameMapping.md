# BaseSrvFreeVarNameMapping

- ea: `0x180007770`
- end: `0x1800077a7`
- name: `BaseSrvFreeVarNameMapping`
- size: `55`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007770`
- `0x18000ce84`

## callees

- `0x180007770`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180007794`
- `ntdll!RtlFreeHeap` at `0x180007794`

## pseudocode

```c
BOOLEAN __fastcall BaseSrvFreeVarNameMapping(PVOID *P)
{
  BOOLEAN result; // al

  if ( P )
  {
    BaseSrvFreeVarNameMapping(*P);
    return RtlFreeHeap(BaseSrvSharedHeap, 1u, P);
  }
  return result;
}

```

## disassembly

```asm
0x180007770  test    rcx, rcx
0x180007773  jz      short locret_1800077A5
0x180007775  push    rbx
0x180007776  sub     rsp, 20h
0x18000777a  mov     rbx, rcx
0x18000777d  mov     rcx, [rcx]; P
0x180007780  call    BaseSrvFreeVarNameMapping
0x180007785  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x18000778c  mov     r8, rbx; P
0x18000778f  mov     edx, 1; Flags
0x180007794  call    cs:__imp_RtlFreeHeap
0x18000779b  nop     dword ptr [rax+rax+00h]
0x1800077a0  add     rsp, 20h
0x1800077a4  pop     rbx
0x1800077a5  retn
```
