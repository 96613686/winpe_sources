# VfsRenameVirtualFileToVirtualTarget

- ea: `0x14000cfd8`
- end: `0x14000d250`
- name: `VfsRenameVirtualFileToVirtualTarget`
- size: `632`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x14000c1b4`

## callees

- `0x140009368`
- `0x14000b2a4`
- `0x14000bdcc`
- `0x14000be3c`
- `0x14000c40c`
- `0x14000c6fc`
- `0x14000c8c4`
- `0x14000cfd8`
- `0x14000d9cc`
- `0x140012acc`

## import_xrefs

- `FLTMGR!FltObjectDereference` at `0x14000d218`
- `FLTMGR!FltObjectDereference` at `0x1400152fd`
- `FLTMGR!FltObjectDereference` at `0x14000d218`
- `FLTMGR!FltObjectDereference` at `0x1400152fd`
- `FLTMGR!FltClose` at `0x14000d22e`
- `FLTMGR!FltClose` at `0x140015313`
- `FLTMGR!FltClose` at `0x14000d22e`
- `FLTMGR!FltClose` at `0x140015313`

## string_xrefs

- `0x14000d08b`: `VfsRenameVirtualFileToVirtualTarget() - Package directory rename is not supported`

## pseudocode

```c
__int64 __fastcall VfsRenameVirtualFileToVirtualTarget(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  int v5; // edi
  char *v8; // rbx
  void *Mapping; // r13
  __int64 v11; // rcx
  int CanReplace; // edi
  char v13; // al
  __int16 v14; // bx
  struct _FLT_INSTANCE *v15; // r12
  HANDLE v16; // rcx
  __int64 v17; // r15
  int v18; // ecx
  char v19; // al
  char v20; // [rsp+50h] [rbp-68h]
  PVOID FltObject; // [rsp+58h] [rbp-60h] BYREF
  HANDLE FileHandle; // [rsp+60h] [rbp-58h] BYREF
  __int64 v23; // [rsp+68h] [rbp-50h]
  void *v24; // [rsp+70h] [rbp-48h]
  char v25; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v26; // [rsp+C8h] [rbp+10h]
  __int64 v27; // [rsp+D0h] [rbp+18h]
  HANDLE v28; // [rsp+D8h] [rbp+20h] BYREF

  v27 = a3;
  v26 = a2;
  v5 = a3;
  v8 = *(char **)(*(_QWORD *)(a1 + 16) + 56LL);
  FltObject = 0;
  FileHandle = 0;
  LODWORD(v28) = 0;
  v25 = 0;
  Mapping = (void *)VfsScbGetMapping(a4[3], a2);
  v24 = Mapping;
  if ( !Mapping )
    return 3221225659LL;
  CanReplace = VfsCheckVirtualTargetForRename(a1, v5, (_DWORD)a4, (_DWORD)Mapping, (__int64)&v28);
  if ( CanReplace >= 0 )
  {
    CanReplace = VfsCheckPackageDirectoryForRename(v11, a2);
    if ( CanReplace >= 0 )
    {
      if ( *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL) == 10 )
        v13 = *v8;
      else
        v13 = *(_DWORD *)v8 & 1;
      v20 = v13;
      v14 = (__int16)v28;
      if ( ((unsigned __int8)v28 & 0x10) != 0 )
      {
        v15 = (struct _FLT_INSTANCE *)a4[8];
        v16 = (HANDLE)a4[10];
      }
      else
      {
        CanReplace = VfsCreateStoreForRename(
                       a1,
                       (__int64)a4,
                       (__int64)Mapping,
                       (struct _FLT_INSTANCE **)&FltObject,
                       &FileHandle);
        if ( CanReplace < 0 )
          goto LABEL_26;
        v15 = (struct _FLT_INSTANCE *)FltObject;
        v16 = FileHandle;
      }
      v28 = v16;
      v17 = v26;
      if ( (*(_DWORD *)(v26 + 4) & 4) != 0 )
      {
        if ( (v14 & 0x80u) != 0 && (v14 & 0x200) == 0 )
        {
          CanReplace = VfsRenameCanReplace(v15);
          if ( CanReplace < 0 )
            goto LABEL_26;
        }
        v23 = v27 + 88;
        CanReplace = VfsRenamePackageFile(
                       a1,
                       v17,
                       (_DWORD)v15,
                       (_DWORD)v28,
                       v27 + 88,
                       (__int64)Mapping,
                       1,
                       (v14 & 0x40) != 0,
                       (__int64)&v25);
        if ( CanReplace < 0 || v25 )
          goto LABEL_26;
        v18 = v23;
      }
      else
      {
        v18 = v27 + 88;
      }
      if ( *(struct _FLT_INSTANCE **)(v17 + 64) == v15 )
      {
        v19 = v20;
        if ( (v14 & 0x200) != 0 )
          v19 = 1;
        CanReplace = VfsRenameStoreFile(a1, v17, (_DWORD)v28, v18, (__int64)Mapping, 1, (v14 & 0x40) != 0, v19);
      }
      else
      {
        CanReplace = -1073741822;
      }
      goto LABEL_26;
    }
    LogWrite(1, 0, L"VfsRenameVirtualFileToVirtualTarget() - Package directory rename is not supported");
  }
LABEL_26:
  VfsReleaseMappingEntry(Mapping);
  if ( FltObject )
    FltObjectDereference(FltObject);
  if ( FileHandle )
    FltClose(FileHandle);
  *(_DWORD *)(a1 + 24) = CanReplace;
  *(_QWORD *)(a1 + 32) = 0;
  return 4;
}

```

## disassembly

```asm
0x14000cfd8  mov     r11, rsp
0x14000cfdb  mov     [r11+18h], r8
0x14000cfdf  mov     [r11+10h], rdx
0x14000cfe3  push    rbx
0x14000cfe4  push    rsi
0x14000cfe5  push    rdi
0x14000cfe6  push    r12
0x14000cfe8  push    r13
0x14000cfea  push    r14
0x14000cfec  push    r15
0x14000cfee  sub     rsp, 80h
0x14000cff5  mov     r15, r9
0x14000cff8  mov     rdi, r8
0x14000cffb  mov     rsi, rdx
0x14000cffe  mov     r14, rcx
0x14000d001  mov     rax, [rcx+10h]
0x14000d005  mov     rbx, [rax+38h]
0x14000d009  mov     qword ptr [r11-60h], 0
0x14000d011  mov     qword ptr [r11-58h], 0
0x14000d019  mov     dword ptr [r11+20h], 0
0x14000d021  mov     byte ptr [r11+8], 0
0x14000d026  mov     rcx, [r9+18h]
0x14000d02a  call    VfsScbGetMapping
0x14000d02f  mov     r13, rax
0x14000d032  mov     [rsp+0B8h+var_48], rax
0x14000d037  test    rax, rax
0x14000d03a  jnz     short loc_14000D055
0x14000d03c  mov     eax, 0C00000BBh
0x14000d041  add     rsp, 80h
0x14000d048  pop     r15
0x14000d04a  pop     r14
0x14000d04c  pop     r13
0x14000d04e  pop     r12
0x14000d050  pop     rdi
0x14000d051  pop     rsi
0x14000d052  pop     rbx
0x14000d053  retn
0x14000d055  lea     rax, [rsp+0B8h+arg_18]
0x14000d05d  mov     [rsp+0B8h+var_98], rax
0x14000d062  mov     r9, r13
0x14000d065  mov     r8, r15
0x14000d068  mov     rdx, rdi
0x14000d06b  mov     rcx, r14
0x14000d06e  call    VfsCheckVirtualTargetForRename
0x14000d073  mov     edi, eax
0x14000d075  test    eax, eax
0x14000d077  js      loc_14000D206
0x14000d07d  mov     rdx, rsi
0x14000d080  call    VfsCheckPackageDirectoryForRename
0x14000d085  mov     edi, eax
0x14000d087  test    eax, eax
0x14000d089  jns     short loc_14000D0A1
0x14000d08b  lea     r8, aVfsrenamevirtu_0; "VfsRenameVirtualFileToVirtualTarget() -"...
0x14000d092  xor     edx, edx
0x14000d094  lea     ecx, [rdx+1]
0x14000d097  call    LogWrite
0x14000d09c  jmp     loc_14000D206
0x14000d0a1  mov     rax, [r14+10h]
0x14000d0a5  mov     esi, 1
0x14000d0aa  cmp     dword ptr [rax+20h], 0Ah
0x14000d0ae  jnz     short loc_14000D0B4
0x14000d0b0  mov     al, [rbx]
0x14000d0b2  jmp     short loc_14000D0B9
0x14000d0b4  mov     eax, [rbx]
0x14000d0b6  and     al, sil
0x14000d0b9  mov     dword ptr [rsp+0B8h+var_68], eax
0x14000d0bd  mov     ebx, dword ptr [rsp+0B8h+arg_18]
0x14000d0c4  test    bl, 10h
0x14000d0c7  jnz     short loc_14000D0FC
0x14000d0c9  lea     rax, [rsp+0B8h+FileHandle]
0x14000d0ce  mov     [rsp+0B8h+var_98], rax; FileHandle
0x14000d0d3  lea     r9, [rsp+0B8h+FltObject]; int
0x14000d0d8  mov     r8, r13; int
0x14000d0db  mov     rdx, r15; int
0x14000d0de  mov     rcx, r14; int
0x14000d0e1  call    VfsCreateStoreForRename
0x14000d0e6  mov     edi, eax
0x14000d0e8  test    eax, eax
0x14000d0ea  js      loc_14000D206
0x14000d0f0  mov     r12, [rsp+0B8h+FltObject]
0x14000d0f5  mov     rcx, [rsp+0B8h+FileHandle]
0x14000d0fa  jmp     short loc_14000D104
0x14000d0fc  mov     r12, [r15+40h]
0x14000d100  mov     rcx, [r15+50h]
0x14000d104  mov     [rsp+0B8h+arg_18], rcx
0x14000d10c  mov     r15, [rsp+0B8h+arg_8]
0x14000d114  mov     eax, [r15+4]
0x14000d118  test    al, 4
0x14000d11a  jz      loc_14000D1B1
0x14000d120  test    bl, bl
0x14000d122  jns     short loc_14000D14B
0x14000d124  bt      ebx, 9
0x14000d128  jb      short loc_14000D14B
0x14000d12a  mov     r8, [rsp+0B8h+arg_10]
0x14000d132  add     r8, 58h ; 'X'
0x14000d136  mov     rdx, rcx
0x14000d139  mov     rcx, r12; Instance
0x14000d13c  call    VfsRenameCanReplace
0x14000d141  mov     edi, eax
0x14000d143  test    eax, eax
0x14000d145  js      loc_14000D206
0x14000d14b  mov     rcx, [rsp+0B8h+arg_10]
0x14000d153  add     rcx, 58h ; 'X'
0x14000d157  mov     [rsp+0B8h+var_50], rcx
0x14000d15c  mov     eax, ebx
0x14000d15e  shr     eax, 6
0x14000d161  and     al, sil
0x14000d164  lea     rdx, [rsp+0B8h+arg_0]
0x14000d16c  mov     [rsp+0B8h+var_78], rdx
0x14000d171  mov     [rsp+0B8h+var_80], al
0x14000d175  mov     [rsp+0B8h+var_88], sil
0x14000d17a  mov     [rsp+0B8h+var_90], r13
0x14000d17f  mov     [rsp+0B8h+var_98], rcx
0x14000d184  mov     r9, [rsp+0B8h+arg_18]
0x14000d18c  mov     r8, r12
0x14000d18f  mov     rdx, r15
0x14000d192  mov     rcx, r14
0x14000d195  call    VfsRenamePackageFile
0x14000d19a  mov     edi, eax
0x14000d19c  test    eax, eax
0x14000d19e  js      short loc_14000D206
0x14000d1a0  cmp     [rsp+0B8h+arg_0], 0
0x14000d1a8  jnz     short loc_14000D206
0x14000d1aa  mov     rcx, [rsp+0B8h+var_50]
0x14000d1af  jmp     short loc_14000D1BD
0x14000d1b1  mov     rax, [rsp+0B8h+arg_10]
0x14000d1b9  lea     rcx, [rax+58h]
0x14000d1bd  cmp     [r15+40h], r12
0x14000d1c1  jnz     short loc_14000D201
0x14000d1c3  bt      ebx, 9
0x14000d1c7  movzx   eax, [rsp+0B8h+var_68]
0x14000d1cc  cmovb   eax, esi
0x14000d1cf  shr     ebx, 6
0x14000d1d2  and     bl, sil
0x14000d1d5  mov     [rsp+0B8h+var_80], al
0x14000d1d9  mov     [rsp+0B8h+var_88], bl
0x14000d1dd  mov     byte ptr [rsp+0B8h+var_90], sil
0x14000d1e2  mov     [rsp+0B8h+var_98], r13
0x14000d1e7  mov     r9, rcx
0x14000d1ea  mov     r8, [rsp+0B8h+arg_18]
0x14000d1f2  mov     rdx, r15
0x14000d1f5  mov     rcx, r14
0x14000d1f8  call    VfsRenameStoreFile
0x14000d1fd  mov     edi, eax
0x14000d1ff  jmp     short loc_14000D206
0x14000d201  mov     edi, 0C0000002h
0x14000d206  mov     rcx, r13; P
0x14000d209  call    VfsReleaseMappingEntry
0x14000d20e  mov     rcx, [rsp+0B8h+FltObject]; FltObject
0x14000d213  test    rcx, rcx
0x14000d216  jz      short loc_14000D224
0x14000d218  call    cs:__imp_FltObjectDereference
0x14000d21f  nop     dword ptr [rax+rax+00h]
0x14000d224  mov     rcx, [rsp+0B8h+FileHandle]; FileHandle
0x14000d229  test    rcx, rcx
0x14000d22c  jz      short loc_14000D23A
0x14000d22e  call    cs:__imp_FltClose
0x14000d235  nop     dword ptr [rax+rax+00h]
0x14000d23a  mov     [r14+18h], edi
0x14000d23e  mov     qword ptr [r14+20h], 0
0x14000d246  mov     eax, 4
0x14000d24b  jmp     loc_14000D041
0x1400152e2  push    rbp
0x1400152e4  sub     rsp, 50h
0x1400152e8  mov     rbp, rdx
0x1400152eb  mov     rcx, [rbp+70h]; P
0x1400152ef  call    VfsReleaseMappingEntry
0x1400152f4  mov     rcx, [rbp+58h]; FltObject
0x1400152f8  test    rcx, rcx
0x1400152fb  jz      short loc_14001530A
0x1400152fd  call    cs:__imp_FltObjectDereference
0x140015304  nop     dword ptr [rax+rax+00h]
0x140015309  nop
0x14001530a  mov     rcx, [rbp+60h]; FileHandle
0x14001530e  test    rcx, rcx
0x140015311  jz      short loc_140015320
0x140015313  call    cs:__imp_FltClose
0x14001531a  nop     dword ptr [rax+rax+00h]
0x14001531f  nop
0x140015320  add     rsp, 50h
0x140015324  pop     rbp
0x140015325  retn
```
