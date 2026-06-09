# BfDeleteEnumerationContext

- ea: `0x140020c70`
- end: `0x140020ce4`
- name: `BfDeleteEnumerationContext`
- size: `116`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400149a8`
- `0x140020a98`
- `0x140020ae0`

## callees

- `0x140020c70`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140020c8f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140020ca5`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140020c8f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140020ca5`
- `ntoskrnl!ObfDereferenceObject` at `0x140020cd6`
- `ntoskrnl!ObfDereferenceObject` at `0x140020cd6`
- `FLTMGR!FltClose` at `0x140020cc1`
- `FLTMGR!FltClose` at `0x140020cc1`

## pseudocode

```c
void __fastcall BfDeleteEnumerationContext(_QWORD *Entry)
{
  void *v2; // rdx
  void *v3; // rcx
  void *v4; // rcx

  if ( *((_BYTE *)Entry + 16) )
  {
    v3 = (void *)Entry[3];
    if ( v3 )
    {
      FltClose(v3);
      v4 = (void *)Entry[4];
      if ( v4 )
        ObfDereferenceObject(v4);
    }
  }
  v2 = (void *)Entry[8];
  if ( v2 )
    ExFreeToPagedLookasideList(&stru_14000B480, v2);
  ExFreeToPagedLookasideList(&Lookaside, Entry);
}

```

## disassembly

```asm
0x140020c70  push    rbx
0x140020c72  sub     rsp, 20h
0x140020c76  cmp     byte ptr [rcx+10h], 0
0x140020c7a  mov     rbx, rcx
0x140020c7d  jnz     short loc_140020CB8
0x140020c7f  mov     rdx, [rbx+40h]; Entry
0x140020c83  test    rdx, rdx
0x140020c86  jz      short loc_140020C9B
0x140020c88  lea     rcx, stru_14000B480; Lookaside
0x140020c8f  call    cs:__imp_ExFreeToPagedLookasideList
0x140020c96  nop     dword ptr [rax+rax+00h]
0x140020c9b  mov     rdx, rbx; Entry
0x140020c9e  lea     rcx, Lookaside; Lookaside
0x140020ca5  call    cs:__imp_ExFreeToPagedLookasideList
0x140020cac  nop     dword ptr [rax+rax+00h]
0x140020cb1  add     rsp, 20h
0x140020cb5  pop     rbx
0x140020cb6  retn
0x140020cb8  mov     rcx, [rcx+18h]; FileHandle
0x140020cbc  test    rcx, rcx
0x140020cbf  jz      short loc_140020C7F
0x140020cc1  call    cs:__imp_FltClose
0x140020cc8  nop     dword ptr [rax+rax+00h]
0x140020ccd  mov     rcx, [rbx+20h]; Object
0x140020cd1  test    rcx, rcx
0x140020cd4  jz      short loc_140020C7F
0x140020cd6  call    cs:__imp_ObfDereferenceObject
0x140020cdd  nop     dword ptr [rax+rax+00h]
0x140020ce2  jmp     short loc_140020C7F
```
