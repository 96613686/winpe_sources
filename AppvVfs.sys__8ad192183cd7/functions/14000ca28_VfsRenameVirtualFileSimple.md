# VfsRenameVirtualFileSimple

- ea: `0x14000ca28`
- end: `0x14000ccfc`
- name: `VfsRenameVirtualFileSimple`
- size: `724`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x14000c1b4`

## callees

- `0x140009368`
- `0x14000b2a4`
- `0x14000b4ec`
- `0x14000c40c`
- `0x14000c6fc`
- `0x14000c8c4`
- `0x14000ca28`
- `0x14000d9cc`
- `0x14000fd38`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000cccb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015286`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cccb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015286`
- `FLTMGR!FltObjectDereference` at `0x14000ccb3`
- `FLTMGR!FltObjectDereference` at `0x14001526e`
- `FLTMGR!FltObjectDereference` at `0x14000ccb3`
- `FLTMGR!FltObjectDereference` at `0x14001526e`
- `FLTMGR!FltGetInstanceContext` at `0x14000caec`
- `FLTMGR!FltGetInstanceContext` at `0x14000caec`
- `FLTMGR!FltReleaseContext` at `0x14000cc9f`
- `FLTMGR!FltReleaseContext` at `0x140015258`
- `FLTMGR!FltReleaseContext` at `0x14000cc9f`
- `FLTMGR!FltReleaseContext` at `0x140015258`

## string_xrefs

- `0x14000cabb`: `VfsRenameVirtualFileSimple() - Package directory rename is not supported`
- `0x14000cb05`: `VfsRenameVirtualFileSimple() - Failed to get instance context for instance: %p\n Status: 0x%08X`
- `0x14000cb47`: `VfsRenameVirtualFileSimple() - Failed to get COW mapping for simple rename of %wZ\n Status: 0x%08X`
- `0x14000cb7f`: `VfsRenameVirtualFileSimple() - Failed to create parent directories for %wZ\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsRenameVirtualFileSimple(__int64 a1, __int64 a2)
{
  void *Mapping; // r12
  __int64 v5; // rcx
  int CanReplace; // edi
  struct _FLT_INSTANCE *v7; // r14
  __int16 v8; // bx
  int InstanceContext; // eax
  PVOID *v10; // r9
  const WCHAR *v11; // r8
  char v12; // al
  __int64 v14; // [rsp+20h] [rbp-98h]
  PFLT_INSTANCE Instance; // [rsp+58h] [rbp-60h] BYREF
  char *v16; // [rsp+60h] [rbp-58h]
  void *v17; // [rsp+68h] [rbp-50h]
  PVOID P[2]; // [rsp+70h] [rbp-48h] BYREF
  char v19; // [rsp+C0h] [rbp+8h] BYREF
  int v20; // [rsp+D0h] [rbp+18h] BYREF
  PFLT_CONTEXT Context; // [rsp+D8h] [rbp+20h] BYREF

  v16 = *(char **)(*(_QWORD *)(a1 + 16) + 56LL);
  *(_OWORD *)P = 0;
  Instance = 0;
  Context = 0;
  Mapping = 0;
  v17 = 0;
  v20 = 0;
  v19 = 0;
  CanReplace = VfsCheckSimpleTargetForRename(a1, a2, &Instance, (struct _UNICODE_STRING *)P, &v20);
  v7 = Instance;
  if ( CanReplace >= 0 && Instance )
  {
    CanReplace = VfsCheckPackageDirectoryForRename(v5, a2);
    if ( CanReplace < 0 )
    {
      LogWrite(1, 0, L"VfsRenameVirtualFileSimple() - Package directory rename is not supported");
      goto LABEL_28;
    }
    v8 = v20;
    if ( (v20 & 0x10) == 0 )
    {
      InstanceContext = FltGetInstanceContext(v7, &Context);
      CanReplace = InstanceContext;
      if ( InstanceContext < 0 )
      {
        v10 = (PVOID *)v7;
        v11 = L"VfsRenameVirtualFileSimple() - Failed to get instance context for instance: %p\n Status: 0x%08X";
LABEL_8:
        LODWORD(v14) = InstanceContext;
        LogWrite(1, 0, v11, v10, v14);
        goto LABEL_28;
      }
      Mapping = (void *)VfsScbGetMapping(*(_QWORD *)(a2 + 24));
      v17 = Mapping;
      if ( !Mapping )
      {
        CanReplace = -1073741595;
        LODWORD(v14) = -1073741595;
        LogWrite(
          1,
          0,
          L"VfsRenameVirtualFileSimple() - Failed to get COW mapping for simple rename of %wZ\n Status: 0x%08X",
          P,
          v14);
        goto LABEL_28;
      }
      InstanceContext = VfsCreateParentDirectories(
                          *(struct _FLT_INSTANCE **)(a2 + 40),
                          v7,
                          (__int64)Mapping,
                          (__int16 *)P,
                          *((_WORD *)Context + 4));
      CanReplace = InstanceContext;
      if ( InstanceContext < 0 )
      {
        v10 = P;
        v11 = L"VfsRenameVirtualFileSimple() - Failed to create parent directories for %wZ\n Status: 0x%08X";
        goto LABEL_8;
      }
    }
    if ( (*(_DWORD *)(a2 + 4) & 4) == 0
      || ((v8 & 0x80u) == 0 || (v8 & 0x200) != 0 || (CanReplace = VfsRenameCanReplace(v7, 0), CanReplace >= 0))
      && (CanReplace = VfsRenamePackageFile(a1, a2, (__int64)v7, 0, (__int64)P, 0, 0, (v8 & 0x40) != 0, &v19),
          CanReplace >= 0)
      && !v19 )
    {
      if ( *(struct _FLT_INSTANCE **)(a2 + 64) == v7 )
      {
        if ( *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL) == 10 )
          v12 = *v16;
        else
          v12 = *(_DWORD *)v16 & 1;
        if ( (v8 & 0x200) != 0 )
          v12 = 1;
        CanReplace = VfsRenameStoreFile(a1, a2, 0, (const void **)P, 0, 0, (v8 & 0x40) != 0, v12);
      }
      else
      {
        CanReplace = -1073741822;
      }
    }
  }
LABEL_28:
  if ( Mapping )
    VfsReleaseMappingEntry(Mapping);
  if ( Context )
    FltReleaseContext(Context);
  if ( v7 )
    FltObjectDereference(v7);
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0);
  *(_DWORD *)(a1 + 24) = CanReplace;
  *(_QWORD *)(a1 + 32) = 0;
  return 4;
}

```

## disassembly

```asm
0x14000ca28  mov     r11, rsp
0x14000ca2b  push    rbx
0x14000ca2c  push    rsi
0x14000ca2d  push    rdi
0x14000ca2e  push    r12
0x14000ca30  push    r13
0x14000ca32  push    r14
0x14000ca34  push    r15
0x14000ca36  sub     rsp, 80h
0x14000ca3d  mov     r15, rdx
0x14000ca40  mov     r13, rcx
0x14000ca43  mov     rax, [rcx+10h]
0x14000ca47  mov     rax, [rax+38h]
0x14000ca4b  mov     [rsp+0B8h+var_58], rax
0x14000ca50  xorps   xmm0, xmm0
0x14000ca53  movups  xmmword ptr [rsp+0B8h+P], xmm0
0x14000ca58  mov     qword ptr [r11-60h], 0
0x14000ca60  mov     qword ptr [r11+20h], 0
0x14000ca68  xor     r12d, r12d
0x14000ca6b  mov     [r11-50h], r12
0x14000ca6f  mov     [r11+18h], r12d
0x14000ca73  mov     [r11+8], r12b
0x14000ca77  lea     rax, [r11+18h]
0x14000ca7b  mov     [rsp+0B8h+var_98], rax
0x14000ca80  lea     r9, [r11-48h]
0x14000ca84  lea     r8, [r11-60h]
0x14000ca88  call    VfsCheckSimpleTargetForRename
0x14000ca8d  mov     edi, eax
0x14000ca8f  mov     [rsp+0B8h+var_68], eax
0x14000ca93  mov     r14, [rsp+0B8h+Instance]
0x14000ca98  test    eax, eax
0x14000ca9a  js      loc_14000CC85
0x14000caa0  test    r14, r14
0x14000caa3  jz      loc_14000CC85
0x14000caa9  mov     rdx, r15
0x14000caac  call    VfsCheckPackageDirectoryForRename
0x14000cab1  mov     edi, eax
0x14000cab3  mov     [rsp+0B8h+var_68], eax
0x14000cab7  test    eax, eax
0x14000cab9  jns     short loc_14000CAD1
0x14000cabb  lea     r8, aVfsrenamevirtu_2; "VfsRenameVirtualFileSimple() - Package "...
0x14000cac2  xor     edx, edx
0x14000cac4  lea     ecx, [rdx+1]
0x14000cac7  call    LogWrite
0x14000cacc  jmp     loc_14000CC85
0x14000cad1  mov     ebx, [rsp+0B8h+arg_10]
0x14000cad8  test    bl, 10h
0x14000cadb  jnz     loc_14000CB88
0x14000cae1  lea     rdx, [rsp+0B8h+Context]; Context
0x14000cae9  mov     rcx, r14; Instance
0x14000caec  call    cs:__imp_FltGetInstanceContext
0x14000caf3  nop     dword ptr [rax+rax+00h]
0x14000caf8  mov     edi, eax
0x14000cafa  mov     [rsp+0B8h+var_68], eax
0x14000cafe  test    eax, eax
0x14000cb00  jns     short loc_14000CB1F
0x14000cb02  mov     r9, r14
0x14000cb05  lea     r8, aVfsrenamevirtu_5; "VfsRenameVirtualFileSimple() - Failed t"...
0x14000cb0c  mov     dword ptr [rsp+0B8h+var_98], eax
0x14000cb10  xor     edx, edx
0x14000cb12  lea     ecx, [rdx+1]
0x14000cb15  call    LogWrite
0x14000cb1a  jmp     loc_14000CC85
0x14000cb1f  mov     rcx, [r15+18h]
0x14000cb23  call    VfsScbGetMapping
0x14000cb28  mov     r12, rax
0x14000cb2b  mov     [rsp+0B8h+var_50], rax
0x14000cb30  lea     r9, [rsp+0B8h+P]
0x14000cb35  test    rax, rax
0x14000cb38  jnz     short loc_14000CB50
0x14000cb3a  mov     edi, 0C00000E5h
0x14000cb3f  mov     [rsp+0B8h+var_68], edi
0x14000cb43  mov     dword ptr [rsp+0B8h+var_98], edi
0x14000cb47  lea     r8, aVfsrenamevirtu; "VfsRenameVirtualFileSimple() - Failed t"...
0x14000cb4e  jmp     short loc_14000CB10
0x14000cb50  mov     rax, [rsp+0B8h+Context]
0x14000cb58  movzx   ecx, word ptr [rax+8]
0x14000cb5c  mov     word ptr [rsp+0B8h+var_98], cx
0x14000cb61  mov     r8, r12
0x14000cb64  mov     rdx, r14
0x14000cb67  mov     rcx, [r15+28h]
0x14000cb6b  call    VfsCreateParentDirectories
0x14000cb70  mov     edi, eax
0x14000cb72  mov     [rsp+0B8h+var_68], eax
0x14000cb76  test    eax, eax
0x14000cb78  jns     short loc_14000CB88
0x14000cb7a  lea     r9, [rsp+0B8h+P]
0x14000cb7f  lea     r8, aVfsrenamevirtu_1; "VfsRenameVirtualFileSimple() - Failed t"...
0x14000cb86  jmp     short loc_14000CB0C
0x14000cb88  mov     eax, [r15+4]
0x14000cb8c  test    al, 4
0x14000cb8e  jz      loc_14000CC18
0x14000cb94  test    bl, bl
0x14000cb96  jns     short loc_14000CBBB
0x14000cb98  bt      ebx, 9
0x14000cb9c  jb      short loc_14000CBBB
0x14000cb9e  lea     r8, [rsp+0B8h+P]
0x14000cba3  xor     edx, edx
0x14000cba5  mov     rcx, r14; Instance
0x14000cba8  call    VfsRenameCanReplace
0x14000cbad  mov     edi, eax
0x14000cbaf  mov     [rsp+0B8h+var_68], eax
0x14000cbb3  test    eax, eax
0x14000cbb5  js      loc_14000CC85
0x14000cbbb  mov     eax, ebx
0x14000cbbd  shr     eax, 6
0x14000cbc0  mov     esi, 1
0x14000cbc5  and     al, sil
0x14000cbc8  lea     rcx, [rsp+0B8h+arg_0]
0x14000cbd0  mov     [rsp+0B8h+var_78], rcx
0x14000cbd5  mov     [rsp+0B8h+var_80], al
0x14000cbd9  mov     [rsp+0B8h+var_88], 0
0x14000cbde  mov     [rsp+0B8h+var_90], 0
0x14000cbe7  lea     rax, [rsp+0B8h+P]
0x14000cbec  mov     [rsp+0B8h+var_98], rax
0x14000cbf1  xor     r9d, r9d
0x14000cbf4  mov     r8, r14
0x14000cbf7  mov     rdx, r15
0x14000cbfa  mov     rcx, r13
0x14000cbfd  call    VfsRenamePackageFile
0x14000cc02  mov     edi, eax
0x14000cc04  mov     [rsp+0B8h+var_68], eax
0x14000cc08  test    eax, eax
0x14000cc0a  js      short loc_14000CC85
0x14000cc0c  cmp     [rsp+0B8h+arg_0], 0
0x14000cc14  jnz     short loc_14000CC85
0x14000cc16  jmp     short loc_14000CC1D
0x14000cc18  mov     esi, 1
0x14000cc1d  cmp     [r15+40h], r14
0x14000cc21  jnz     short loc_14000CC7C
0x14000cc23  mov     rax, [r13+10h]
0x14000cc27  cmp     dword ptr [rax+20h], 0Ah
0x14000cc2b  mov     rax, [rsp+0B8h+var_58]
0x14000cc30  jnz     short loc_14000CC36
0x14000cc32  mov     al, [rax]
0x14000cc34  jmp     short loc_14000CC3B
0x14000cc36  mov     eax, [rax]
0x14000cc38  and     al, sil
0x14000cc3b  bt      ebx, 9
0x14000cc3f  movzx   eax, al
0x14000cc42  cmovb   eax, esi
0x14000cc45  shr     ebx, 6
0x14000cc48  and     bl, sil
0x14000cc4b  mov     [rsp+0B8h+var_80], al
0x14000cc4f  mov     [rsp+0B8h+var_88], bl
0x14000cc53  mov     byte ptr [rsp+0B8h+var_90], 0
0x14000cc58  mov     [rsp+0B8h+var_98], 0
0x14000cc61  lea     r9, [rsp+0B8h+P]
0x14000cc66  xor     r8d, r8d
0x14000cc69  mov     rdx, r15
0x14000cc6c  mov     rcx, r13
0x14000cc6f  call    VfsRenameStoreFile
0x14000cc74  mov     edi, eax
0x14000cc76  mov     [rsp+0B8h+var_68], eax
0x14000cc7a  jmp     short loc_14000CC85
0x14000cc7c  mov     edi, 0C0000002h
0x14000cc81  mov     [rsp+0B8h+var_68], edi
0x14000cc85  test    r12, r12
0x14000cc88  jz      short loc_14000CC92
0x14000cc8a  mov     rcx, r12; P
0x14000cc8d  call    VfsReleaseMappingEntry
0x14000cc92  mov     rcx, [rsp+0B8h+Context]; Context
0x14000cc9a  test    rcx, rcx
0x14000cc9d  jz      short loc_14000CCAB
0x14000cc9f  call    cs:__imp_FltReleaseContext
0x14000cca6  nop     dword ptr [rax+rax+00h]
0x14000ccab  test    r14, r14
0x14000ccae  jz      short loc_14000CCBF
0x14000ccb0  mov     rcx, r14; FltObject
0x14000ccb3  call    cs:__imp_FltObjectDereference
0x14000ccba  nop     dword ptr [rax+rax+00h]
0x14000ccbf  mov     rcx, [rsp+0B8h+P+8]; P
0x14000ccc4  test    rcx, rcx
0x14000ccc7  jz      short loc_14000CCD7
0x14000ccc9  xor     edx, edx; Tag
0x14000cccb  call    cs:__imp_ExFreePoolWithTag
0x14000ccd2  nop     dword ptr [rax+rax+00h]
0x14000ccd7  mov     [r13+18h], edi
0x14000ccdb  mov     qword ptr [r13+20h], 0
0x14000cce3  mov     eax, 4
0x14000cce8  add     rsp, 80h
0x14000ccef  pop     r15
0x14000ccf1  pop     r14
0x14000ccf3  pop     r13
0x14000ccf5  pop     r12
0x14000ccf7  pop     rdi
0x14000ccf8  pop     rsi
0x14000ccf9  pop     rbx
0x14000ccfa  retn
0x140015234  push    rbp
0x140015236  sub     rsp, 50h
0x14001523a  mov     rbp, rdx
0x14001523d  mov     rcx, [rbp+68h]; P
0x140015241  test    rcx, rcx
0x140015244  jz      short loc_14001524C
0x140015246  call    VfsReleaseMappingEntry
0x14001524b  nop
0x14001524c  mov     rcx, [rbp+0D8h]; Context
0x140015253  test    rcx, rcx
0x140015256  jz      short loc_140015265
0x140015258  call    cs:__imp_FltReleaseContext
0x14001525f  nop     dword ptr [rax+rax+00h]
0x140015264  nop
0x140015265  mov     rcx, [rbp+58h]; FltObject
0x140015269  test    rcx, rcx
0x14001526c  jz      short loc_14001527B
0x14001526e  call    cs:__imp_FltObjectDereference
0x140015275  nop     dword ptr [rax+rax+00h]
0x14001527a  nop
0x14001527b  mov     rcx, [rbp+78h]; P
0x14001527f  test    rcx, rcx
0x140015282  jz      short loc_140015293
0x140015284  xor     edx, edx; Tag
0x140015286  call    cs:__imp_ExFreePoolWithTag
0x14001528d  nop     dword ptr [rax+rax+00h]
0x140015292  nop
0x140015293  add     rsp, 50h
0x140015297  pop     rbp
0x140015298  retn
```
