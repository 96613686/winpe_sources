# VfsDeleteCcb

- ea: `0x14000d618`
- end: `0x14000d726`
- name: `VfsDeleteCcb`
- size: `270`
- prototype: `void __fastcall(_QWORD *Entry)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140001b8c`
- `0x14000f188`

## callees

- `0x140007a14`
- `0x14000d618`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000d664`
- `ntoskrnl!ZwClose` at `0x14000d664`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d6a5`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d6df`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d6a5`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d6df`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000d713`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000d713`
- `FLTMGR!FltObjectDereference` at `0x14000d62a`
- `FLTMGR!FltObjectDereference` at `0x14000d647`
- `FLTMGR!FltObjectDereference` at `0x14000d62a`
- `FLTMGR!FltObjectDereference` at `0x14000d647`
- `FLTMGR!FltClose` at `0x14000d688`
- `FLTMGR!FltClose` at `0x14000d6c2`
- `FLTMGR!FltClose` at `0x14000d688`
- `FLTMGR!FltClose` at `0x14000d6c2`

## pseudocode

```c
void __fastcall VfsDeleteCcb(_QWORD *Entry)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx

  v2 = (void *)Entry[5];
  if ( v2 )
  {
    FltObjectDereference(v2);
    Entry[5] = 0;
  }
  v3 = (void *)Entry[8];
  if ( v3 )
  {
    FltObjectDereference(v3);
    Entry[8] = 0;
  }
  v4 = (void *)Entry[11];
  if ( v4 )
  {
    ZwClose(v4);
    Entry[11] = 0;
  }
  if ( (*((_DWORD *)Entry + 1) & 2) != 0 )
  {
    v5 = (void *)Entry[7];
    if ( v5 )
    {
      FltClose(v5);
      Entry[7] = 0;
    }
    v6 = (void *)Entry[6];
    if ( v6 )
    {
      ObfDereferenceObject(v6);
      Entry[6] = 0;
    }
    v7 = (void *)Entry[10];
    if ( v7 )
    {
      FltClose(v7);
      Entry[10] = 0;
    }
    v8 = (void *)Entry[9];
    if ( v8 )
    {
      ObfDereferenceObject(v8);
      Entry[9] = 0;
    }
  }
  v9 = (void *)Entry[15];
  if ( v9 )
  {
    VfsDeleteDirQueryContext(v9);
    Entry[15] = 0;
  }
  ExFreeToPagedLookasideList(&stru_14001F780, Entry);
}

```

## disassembly

```asm
0x14000d618  push    rbx
0x14000d61a  sub     rsp, 20h
0x14000d61e  mov     rbx, rcx
0x14000d621  mov     rcx, [rcx+28h]; FltObject
0x14000d625  test    rcx, rcx
0x14000d628  jz      short loc_14000D63E
0x14000d62a  call    cs:__imp_FltObjectDereference
0x14000d631  nop     dword ptr [rax+rax+00h]
0x14000d636  mov     qword ptr [rbx+28h], 0
0x14000d63e  mov     rcx, [rbx+40h]; FltObject
0x14000d642  test    rcx, rcx
0x14000d645  jz      short loc_14000D65B
0x14000d647  call    cs:__imp_FltObjectDereference
0x14000d64e  nop     dword ptr [rax+rax+00h]
0x14000d653  mov     qword ptr [rbx+40h], 0
0x14000d65b  mov     rcx, [rbx+58h]; Handle
0x14000d65f  test    rcx, rcx
0x14000d662  jz      short loc_14000D678
0x14000d664  call    cs:__imp_ZwClose
0x14000d66b  nop     dword ptr [rax+rax+00h]
0x14000d670  mov     qword ptr [rbx+58h], 0
0x14000d678  mov     eax, [rbx+4]
0x14000d67b  test    al, 2
0x14000d67d  jz      short loc_14000D6F3
0x14000d67f  mov     rcx, [rbx+38h]; FileHandle
0x14000d683  test    rcx, rcx
0x14000d686  jz      short loc_14000D69C
0x14000d688  call    cs:__imp_FltClose
0x14000d68f  nop     dword ptr [rax+rax+00h]
0x14000d694  mov     qword ptr [rbx+38h], 0
0x14000d69c  mov     rcx, [rbx+30h]; Object
0x14000d6a0  test    rcx, rcx
0x14000d6a3  jz      short loc_14000D6B9
0x14000d6a5  call    cs:__imp_ObfDereferenceObject
0x14000d6ac  nop     dword ptr [rax+rax+00h]
0x14000d6b1  mov     qword ptr [rbx+30h], 0
0x14000d6b9  mov     rcx, [rbx+50h]; FileHandle
0x14000d6bd  test    rcx, rcx
0x14000d6c0  jz      short loc_14000D6D6
0x14000d6c2  call    cs:__imp_FltClose
0x14000d6c9  nop     dword ptr [rax+rax+00h]
0x14000d6ce  mov     qword ptr [rbx+50h], 0
0x14000d6d6  mov     rcx, [rbx+48h]; Object
0x14000d6da  test    rcx, rcx
0x14000d6dd  jz      short loc_14000D6F3
0x14000d6df  call    cs:__imp_ObfDereferenceObject
0x14000d6e6  nop     dword ptr [rax+rax+00h]
0x14000d6eb  mov     qword ptr [rbx+48h], 0
0x14000d6f3  mov     rcx, [rbx+78h]; Entry
0x14000d6f7  test    rcx, rcx
0x14000d6fa  jz      short loc_14000D709
0x14000d6fc  call    VfsDeleteDirQueryContext
0x14000d701  mov     qword ptr [rbx+78h], 0
0x14000d709  mov     rdx, rbx; Entry
0x14000d70c  lea     rcx, stru_14001F780; Lookaside
0x14000d713  call    cs:__imp_ExFreeToPagedLookasideList
0x14000d71a  nop     dword ptr [rax+rax+00h]
0x14000d71f  add     rsp, 20h
0x14000d723  pop     rbx
0x14000d724  retn
```
