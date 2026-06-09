# BaseSrvFreeAppNameMapping

- ea: `0x18000ce84`
- end: `0x18000cecd`
- name: `BaseSrvFreeAppNameMapping`
- size: `73`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ce84`
- `0x18000ced4`

## callees

- `0x180007770`
- `0x18000ce84`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000ceba`
- `ntdll!RtlFreeHeap` at `0x18000ceba`

## pseudocode

```c
BOOLEAN __fastcall BaseSrvFreeAppNameMapping(PVOID *P)
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
0x18000ce84  test    rcx, rcx
0x18000ce87  jz      short locret_18000CECB
0x18000ce89  push    rbx
0x18000ce8a  sub     rsp, 20h
0x18000ce8e  mov     rbx, rcx
0x18000ce91  mov     rcx, [rcx+18h]; P
0x18000ce95  call    BaseSrvFreeVarNameMapping
0x18000ce9a  mov     rcx, [rbx+20h]; P
0x18000ce9e  call    BaseSrvFreeVarNameMapping
0x18000cea3  mov     rcx, [rbx]; P
0x18000cea6  call    BaseSrvFreeAppNameMapping
0x18000ceab  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x18000ceb2  mov     r8, rbx; P
0x18000ceb5  mov     edx, 1; Flags
0x18000ceba  call    cs:__imp_RtlFreeHeap
0x18000cec1  nop     dword ptr [rax+rax+00h]
0x18000cec6  add     rsp, 20h
0x18000ceca  pop     rbx
0x18000cecb  retn
```
