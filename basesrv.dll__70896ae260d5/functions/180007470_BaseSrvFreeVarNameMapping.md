# BaseSrvFreeVarNameMapping

- ea: `0x180007470`
- end: `0x1800074a7`
- name: `BaseSrvFreeVarNameMapping`
- size: `55`
- prototype: `BOOLEAN __fastcall(PVOID *P)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007470`
- `0x18000caa0`

## callees

- `0x180007470`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180007494`
- `ntdll!RtlFreeHeap` at `0x180007494`

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
0x180007470  test    rcx, rcx
0x180007473  jz      short locret_1800074A5
0x180007475  push    rbx
0x180007476  sub     rsp, 20h
0x18000747a  mov     rbx, rcx
0x18000747d  mov     rcx, [rcx]; P
0x180007480  call    BaseSrvFreeVarNameMapping
0x180007485  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x18000748c  mov     r8, rbx; P
0x18000748f  mov     edx, 1; Flags
0x180007494  call    cs:__imp_RtlFreeHeap
0x18000749b  nop     dword ptr [rax+rax+00h]
0x1800074a0  add     rsp, 20h
0x1800074a4  pop     rbx
0x1800074a5  retn
```
