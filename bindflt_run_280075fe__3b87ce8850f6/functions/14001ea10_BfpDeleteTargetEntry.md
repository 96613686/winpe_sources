# BfpDeleteTargetEntry

- ea: `0x14001ea10`
- end: `0x14001ea6d`
- name: `BfpDeleteTargetEntry`
- size: `93`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140019c44`
- `0x14001caf8`
- `0x14001e998`

## callees

- `0x1400172f0`
- `0x14001ea10`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001ea5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ea5a`
- `FLTMGR!FltReleaseContext` at `0x14001ea3d`
- `FLTMGR!FltReleaseContext` at `0x14001ea3d`
- `FLTMGR!FltObjectDereference` at `0x14001ea2d`
- `FLTMGR!FltObjectDereference` at `0x14001ea2d`

## pseudocode

```c
void __fastcall BfpDeleteTargetEntry(char *P)
{
  __int64 v1; // rax

  v1 = *((_QWORD *)P + 2);
  if ( v1 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v1 + 36));
    FltObjectDereference(**((PVOID **)P + 2));
    FltReleaseContext(*((PFLT_CONTEXT *)P + 2));
  }
  BfFreeUnicodeString(P + 24);
  ExFreePoolWithTag(P, 0x706D4642u);
}

```

## disassembly

```asm
0x14001ea10  push    rbx
0x14001ea12  sub     rsp, 20h
0x14001ea16  mov     rax, [rcx+10h]
0x14001ea1a  mov     rbx, rcx
0x14001ea1d  test    rax, rax
0x14001ea20  jz      short loc_14001EA49
0x14001ea22  lock dec dword ptr [rax+24h]
0x14001ea26  mov     rcx, [rcx+10h]
0x14001ea2a  mov     rcx, [rcx]; FltObject
0x14001ea2d  call    cs:__imp_FltObjectDereference
0x14001ea34  nop     dword ptr [rax+rax+00h]
0x14001ea39  mov     rcx, [rbx+10h]; Context
0x14001ea3d  call    cs:__imp_FltReleaseContext
0x14001ea44  nop     dword ptr [rax+rax+00h]
0x14001ea49  lea     rcx, [rbx+18h]
0x14001ea4d  call    BfFreeUnicodeString
0x14001ea52  mov     edx, 706D4642h; Tag
0x14001ea57  mov     rcx, rbx; P
0x14001ea5a  call    cs:__imp_ExFreePoolWithTag
0x14001ea61  nop     dword ptr [rax+rax+00h]
0x14001ea66  add     rsp, 20h
0x14001ea6a  pop     rbx
0x14001ea6b  retn
```
