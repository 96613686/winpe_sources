# FltpCleanupFrame

- ea: `0x18004c4d0`
- end: `0x18004c561`
- name: `FltpCleanupFrame`
- size: `145`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18004c008`
- `0x18004dea0`

## callees

- `0x18004c570`
- `0x180077c90`
- `0x180077f00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18004c53a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004c54e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004c53a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004c54e`
- `ntoskrnl!ExDeleteFastResource` at `0x18004c4e5`
- `ntoskrnl!ExDeleteFastResource` at `0x18004c4f5`
- `ntoskrnl!ExDeleteFastResource` at `0x18004c508`
- `ntoskrnl!ExDeleteFastResource` at `0x18004c4e5`
- `ntoskrnl!ExDeleteFastResource` at `0x18004c4f5`
- `ntoskrnl!ExDeleteFastResource` at `0x18004c508`

## pseudocode

```c
void __fastcall FltpCleanupFrame(PVOID *P)
{
  FltpCleanupBackPocketIrpCtrls();
  ExDeleteFastResource(P + 65);
  ExDeleteFastResource(P + 9);
  ExDeleteFastResource(P + 25);
  FltpFreeUnicodeString(P + 4);
  FltpFreeUnicodeString(P + 6);
  FltpFreeFrameLookasideLists((__int64)P);
  ExFreePoolWithTag(P[86], 0x72704D46u);
  ExFreePoolWithTag(P, 0x72664D46u);
}

```

## disassembly

```asm
0x18004c4d0  push    rbx
0x18004c4d2  sub     rsp, 20h
0x18004c4d6  mov     rbx, rcx
0x18004c4d9  call    FltpCleanupBackPocketIrpCtrls
0x18004c4de  lea     rcx, [rbx+208h]
0x18004c4e5  call    cs:__imp_ExDeleteFastResource
0x18004c4ec  nop     dword ptr [rax+rax+00h]
0x18004c4f1  lea     rcx, [rbx+48h]
0x18004c4f5  call    cs:__imp_ExDeleteFastResource
0x18004c4fc  nop     dword ptr [rax+rax+00h]
0x18004c501  lea     rcx, [rbx+0C8h]
0x18004c508  call    cs:__imp_ExDeleteFastResource
0x18004c50f  nop     dword ptr [rax+rax+00h]
0x18004c514  lea     rcx, [rbx+20h]
0x18004c518  call    FltpFreeUnicodeString
0x18004c51d  lea     rcx, [rbx+30h]
0x18004c521  call    FltpFreeUnicodeString
0x18004c526  mov     rcx, rbx
0x18004c529  call    FltpFreeFrameLookasideLists
0x18004c52e  mov     rcx, [rbx+2B0h]; P
0x18004c535  mov     edx, 72704D46h; Tag
0x18004c53a  call    cs:__imp_ExFreePoolWithTag
0x18004c541  nop     dword ptr [rax+rax+00h]
0x18004c546  mov     edx, 72664D46h; Tag
0x18004c54b  mov     rcx, rbx; P
0x18004c54e  call    cs:__imp_ExFreePoolWithTag
0x18004c555  nop     dword ptr [rax+rax+00h]
0x18004c55a  add     rsp, 20h
0x18004c55e  pop     rbx
0x18004c55f  retn
```
