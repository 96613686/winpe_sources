# VfsRenameNativeFileToVirtualTarget

- ea: `0x14000c574`
- end: `0x14000c6f4`
- name: `VfsRenameNativeFileToVirtualTarget`
- size: `384`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000c1b4`

## callees

- `0x140009368`
- `0x14000bdcc`
- `0x14000be3c`
- `0x14000c574`
- `0x14000d9cc`
- `0x140011134`

## import_xrefs

- `FLTMGR!FltObjectDereference` at `0x14000c6ba`
- `FLTMGR!FltObjectDereference` at `0x14001519a`
- `FLTMGR!FltObjectDereference` at `0x14000c6ba`
- `FLTMGR!FltObjectDereference` at `0x14001519a`
- `FLTMGR!FltClose` at `0x14000c6d3`
- `FLTMGR!FltClose` at `0x1400151b3`
- `FLTMGR!FltClose` at `0x14000c6d3`
- `FLTMGR!FltClose` at `0x1400151b3`

## pseudocode

```c
__int64 __fastcall VfsRenameNativeFileToVirtualTarget(__int64 a1, __int64 a2, _QWORD *a3)
{
  char *v6; // r14
  void *Mapping; // r15
  int v9; // edi
  char v10; // r14
  struct _FLT_INSTANCE *v11; // rax
  HANDLE v12; // r8
  __int64 v13; // rdx
  struct _FLT_INSTANCE *v14; // rcx
  char v15; // al
  unsigned int v16; // [rsp+80h] [rbp+8h] BYREF
  PVOID FltObject; // [rsp+90h] [rbp+18h] BYREF
  HANDLE FileHandle; // [rsp+98h] [rbp+20h] BYREF

  v6 = *(char **)(*(_QWORD *)(a1 + 16) + 56LL);
  FltObject = 0;
  FileHandle = 0;
  v16 = 0;
  Mapping = (void *)VfsScbGetMapping(a3[3]);
  if ( !Mapping )
    return 3221225659LL;
  v9 = VfsCheckVirtualTargetForRename(a1, a2, (__int64)a3, (__int64)Mapping, &v16);
  if ( v9 >= 0 )
  {
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL) == 10 )
      v10 = *v6;
    else
      v10 = *(_DWORD *)v6 & 1;
    if ( (v16 & 0x10) != 0 )
    {
      v11 = (struct _FLT_INSTANCE *)a3[8];
      v12 = (HANDLE)a3[10];
LABEL_11:
      v13 = *(_QWORD *)(a1 + 16);
      v14 = *(struct _FLT_INSTANCE **)(v13 + 16);
      if ( v11 == v14 )
      {
        v15 = v10;
        if ( (v16 & 0x200) != 0 )
          v15 = 1;
        v9 = VfsRenameFile(v14, *(PFILE_OBJECT *)(v13 + 8), (__int64)v12, (const void **)(a2 + 88), v15);
      }
      else
      {
        v9 = -1073741822;
      }
      goto LABEL_16;
    }
    v9 = VfsCreateStoreForRename(a1, (__int64)a3, (__int64)Mapping, (struct _FLT_INSTANCE **)&FltObject, &FileHandle);
    if ( v9 >= 0 )
    {
      v11 = (struct _FLT_INSTANCE *)FltObject;
      v12 = FileHandle;
      goto LABEL_11;
    }
  }
LABEL_16:
  VfsReleaseMappingEntry(Mapping);
  if ( FltObject )
    FltObjectDereference(FltObject);
  if ( FileHandle )
    FltClose(FileHandle);
  *(_DWORD *)(a1 + 24) = v9;
  *(_QWORD *)(a1 + 32) = 0;
  return 4;
}

```

## disassembly

```asm
0x14000c574  mov     r11, rsp
0x14000c577  push    rbx
0x14000c578  push    rsi
0x14000c579  push    rdi
0x14000c57a  push    r12
0x14000c57c  push    r13
0x14000c57e  push    r14
0x14000c580  push    r15
0x14000c582  sub     rsp, 40h
0x14000c586  mov     rsi, r8
0x14000c589  mov     r13, rdx
0x14000c58c  mov     rbx, rcx
0x14000c58f  mov     rax, [rcx+10h]
0x14000c593  mov     r14, [rax+38h]
0x14000c597  mov     qword ptr [r11+18h], 0
0x14000c59f  mov     qword ptr [r11+20h], 0
0x14000c5a7  mov     dword ptr [r11+8], 0
0x14000c5af  mov     rcx, [r8+18h]
0x14000c5b3  call    VfsScbGetMapping
0x14000c5b8  mov     r15, rax
0x14000c5bb  mov     [rsp+78h+var_48], rax
0x14000c5c0  test    rax, rax
0x14000c5c3  jnz     short loc_14000C5DB
0x14000c5c5  mov     eax, 0C00000BBh
0x14000c5ca  add     rsp, 40h
0x14000c5ce  pop     r15
0x14000c5d0  pop     r14
0x14000c5d2  pop     r13
0x14000c5d4  pop     r12
0x14000c5d6  pop     rdi
0x14000c5d7  pop     rsi
0x14000c5d8  pop     rbx
0x14000c5d9  retn
0x14000c5db  lea     rax, [rsp+78h+arg_0]
0x14000c5e3  mov     [rsp+78h+var_58], rax
0x14000c5e8  mov     r9, r15
0x14000c5eb  mov     r8, rsi
0x14000c5ee  mov     rdx, r13
0x14000c5f1  mov     rcx, rbx
0x14000c5f4  call    VfsCheckVirtualTargetForRename
0x14000c5f9  mov     edi, eax
0x14000c5fb  test    eax, eax
0x14000c5fd  js      loc_14000C6A5
0x14000c603  mov     rax, [rbx+10h]
0x14000c607  mov     r12d, 1
0x14000c60d  cmp     dword ptr [rax+20h], 0Ah
0x14000c611  jnz     short loc_14000C618
0x14000c613  mov     r14b, [r14]
0x14000c616  jmp     short loc_14000C61E
0x14000c618  mov     r14d, [r14]
0x14000c61b  and     r14b, r12b
0x14000c61e  test    byte ptr [rsp+78h+arg_0], 10h
0x14000c626  jnz     short loc_14000C663
0x14000c628  lea     rax, [rsp+78h+FileHandle]
0x14000c630  mov     [rsp+78h+var_58], rax; FileHandle
0x14000c635  lea     r9, [rsp+78h+FltObject]; int
0x14000c63d  mov     r8, r15; int
0x14000c640  mov     rdx, rsi; int
0x14000c643  mov     rcx, rbx; int
0x14000c646  call    VfsCreateStoreForRename
0x14000c64b  mov     edi, eax
0x14000c64d  test    eax, eax
0x14000c64f  js      short loc_14000C6A5
0x14000c651  mov     rax, [rsp+78h+FltObject]
0x14000c659  mov     r8, [rsp+78h+FileHandle]
0x14000c661  jmp     short loc_14000C66B
0x14000c663  mov     rax, [rsi+40h]
0x14000c667  mov     r8, [rsi+50h]
0x14000c66b  mov     rdx, [rbx+10h]
0x14000c66f  mov     rcx, [rdx+10h]; Instance
0x14000c673  cmp     rax, rcx
0x14000c676  jnz     short loc_14000C6A0
0x14000c678  test    [rsp+78h+arg_0], 200h
0x14000c683  movzx   eax, r14b
0x14000c687  cmovnz  eax, r12d
0x14000c68b  lea     r9, [r13+58h]
0x14000c68f  mov     byte ptr [rsp+78h+var_58], al; char
0x14000c693  mov     rdx, [rdx+8]; FileObject
0x14000c697  call    VfsRenameFile
0x14000c69c  mov     edi, eax
0x14000c69e  jmp     short loc_14000C6A5
0x14000c6a0  mov     edi, 0C0000002h
0x14000c6a5  mov     rcx, r15; P
0x14000c6a8  call    VfsReleaseMappingEntry
0x14000c6ad  mov     rcx, [rsp+78h+FltObject]; FltObject
0x14000c6b5  test    rcx, rcx
0x14000c6b8  jz      short loc_14000C6C6
0x14000c6ba  call    cs:__imp_FltObjectDereference
0x14000c6c1  nop     dword ptr [rax+rax+00h]
0x14000c6c6  mov     rcx, [rsp+78h+FileHandle]; FileHandle
0x14000c6ce  test    rcx, rcx
0x14000c6d1  jz      short loc_14000C6DF
0x14000c6d3  call    cs:__imp_FltClose
0x14000c6da  nop     dword ptr [rax+rax+00h]
0x14000c6df  mov     [rbx+18h], edi
0x14000c6e2  mov     qword ptr [rbx+20h], 0
0x14000c6ea  mov     eax, 4
0x14000c6ef  jmp     loc_14000C5CA
0x14001517c  push    rbp
0x14001517e  sub     rsp, 30h
0x140015182  mov     rbp, rdx
0x140015185  mov     rcx, [rbp+30h]; P
0x140015189  call    VfsReleaseMappingEntry
0x14001518e  mov     rcx, [rbp+90h]; FltObject
0x140015195  test    rcx, rcx
0x140015198  jz      short loc_1400151A7
0x14001519a  call    cs:__imp_FltObjectDereference
0x1400151a1  nop     dword ptr [rax+rax+00h]
0x1400151a6  nop
0x1400151a7  mov     rcx, [rbp+98h]; FileHandle
0x1400151ae  test    rcx, rcx
0x1400151b1  jz      short loc_1400151C0
0x1400151b3  call    cs:__imp_FltClose
0x1400151ba  nop     dword ptr [rax+rax+00h]
0x1400151bf  nop
0x1400151c0  add     rsp, 30h
0x1400151c4  pop     rbp
0x1400151c5  retn
```
