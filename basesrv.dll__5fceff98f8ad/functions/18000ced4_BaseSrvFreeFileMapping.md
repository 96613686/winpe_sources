# BaseSrvFreeFileMapping

- ea: `0x18000ced4`
- end: `0x18000cf15`
- name: `BaseSrvFreeFileMapping`
- size: `65`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004d70`
- `0x180006170`

## callees

- `0x18000ce84`
- `0x18000ced4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000cf02`
- `ntdll!RtlFreeHeap` at `0x18000cf02`

## pseudocode

```c
BOOLEAN __fastcall BaseSrvFreeFileMapping(PVOID **P)
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
0x18000ced4  test    rcx, rcx
0x18000ced7  jz      short locret_18000CF13
0x18000ced9  push    rbx
0x18000ceda  sub     rsp, 20h
0x18000cede  mov     rbx, rcx
0x18000cee1  mov     rcx, [rcx+18h]; P
0x18000cee5  call    BaseSrvFreeAppNameMapping
0x18000ceea  mov     rcx, [rbx+20h]; P
0x18000ceee  call    BaseSrvFreeAppNameMapping
0x18000cef3  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x18000cefa  mov     r8, rbx; P
0x18000cefd  mov     edx, 1; Flags
0x18000cf02  call    cs:__imp_RtlFreeHeap
0x18000cf09  nop     dword ptr [rax+rax+00h]
0x18000cf0e  add     rsp, 20h
0x18000cf12  pop     rbx
0x18000cf13  retn
```
