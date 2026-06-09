# VfsCowCopyFile

- ea: `0x140002b4c`
- end: `0x140002e88`
- name: `VfsCowCopyFile`
- size: `828`
- prototype: `__int64 __fastcall(__int64, __int64, struct _FLT_INSTANCE *, struct _UNICODE_STRING *, PFLT_INSTANCE Instance, __int64, __int64, PVOID Buffer, char, char)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1400049b4`
- `0x14000502c`

## callees

- `0x1400022b4`
- `0x140002b4c`
- `0x140002e90`
- `0x1400037ac`
- `0x140009298`
- `0x140009368`
- `0x14000d868`
- `0x14000fd38`
- `0x140012acc`

## import_xrefs

- `FLTMGR!FltGetInstanceContext` at `0x140002ba0`
- `FLTMGR!FltGetInstanceContext` at `0x140002be0`
- `FLTMGR!FltGetInstanceContext` at `0x140002ba0`
- `FLTMGR!FltGetInstanceContext` at `0x140002be0`
- `FLTMGR!FltClose` at `0x140002e2f`
- `FLTMGR!FltClose` at `0x1400146c6`
- `FLTMGR!FltClose` at `0x140002e2f`
- `FLTMGR!FltClose` at `0x1400146c6`
- `FLTMGR!FltReleaseContext` at `0x140002e52`
- `FLTMGR!FltReleaseContext` at `0x140002e68`
- `FLTMGR!FltReleaseContext` at `0x1400146ee`
- `FLTMGR!FltReleaseContext` at `0x140014704`
- `FLTMGR!FltReleaseContext` at `0x140002e52`
- `FLTMGR!FltReleaseContext` at `0x140002e68`
- `FLTMGR!FltReleaseContext` at `0x1400146ee`
- `FLTMGR!FltReleaseContext` at `0x140014704`

## string_xrefs

- `0x140002bbe`: `VfsCowCopyFile() - Failed to get instance context for instance: %p\n Status: 0x%08X`
- `0x140002caa`: `VfsCowCopyFile() - Failed to get COW mapping to copy %wZ into the COW\n Status: 0x%08X`
- `0x140002cf1`: `VfsCowCopyFile() - Failed to create parent directories for %wZ\n Status: 0x%08X`
- `0x140002db2`: `VfsCowCopyFile() - Failed to copy file: %wZ\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsCowCopyFile(
        __int64 a1,
        __int64 a2,
        struct _FLT_INSTANCE *a3,
        struct _UNICODE_STRING *a4,
        PFLT_INSTANCE Instance,
        __int64 a6,
        __int64 a7,
        PVOID Buffer,
        char a9,
        char a10)
{
  void *v13; // rsi
  int InstanceContext; // eax
  int v15; // ebx
  __int64 v16; // r9
  const WCHAR *v17; // r8
  __int64 v18; // rdx
  unsigned __int16 Length; // cx
  __int64 v20; // rdx
  __int64 v22; // [rsp+20h] [rbp-C8h]
  __int64 v23; // [rsp+20h] [rbp-C8h]
  int v24; // [rsp+38h] [rbp-B0h]
  int v25; // [rsp+40h] [rbp-A8h]
  PFLT_CONTEXT Context; // [rsp+68h] [rbp-80h] BYREF
  PFLT_CONTEXT v27; // [rsp+70h] [rbp-78h] BYREF
  HANDLE FileHandle; // [rsp+78h] [rbp-70h] BYREF
  void *v29; // [rsp+80h] [rbp-68h]
  __int64 v30[2]; // [rsp+90h] [rbp-58h] BYREF
  __int128 v31; // [rsp+A0h] [rbp-48h] BYREF
  PVOID Entry; // [rsp+F0h] [rbp+8h] BYREF

  FileHandle = 0;
  v27 = 0;
  Context = 0;
  v13 = 0;
  v29 = 0;
  Entry = 0;
  if ( a9 )
  {
    InstanceContext = FltGetInstanceContext(Instance, &v27);
    v15 = InstanceContext;
    if ( InstanceContext < 0 )
    {
      v16 = (__int64)Instance;
LABEL_4:
      v17 = L"VfsCowCopyFile() - Failed to get instance context for instance: %p\n Status: 0x%08X";
LABEL_5:
      LODWORD(v22) = InstanceContext;
      LogWrite(1, 0, v17, v16, v22);
      goto LABEL_23;
    }
    InstanceContext = FltGetInstanceContext(a3, &Context);
    v15 = InstanceContext;
    if ( InstanceContext < 0 )
    {
      v16 = (__int64)a3;
      goto LABEL_4;
    }
    v18 = *((unsigned __int16 *)Context + 4);
    *(_OWORD *)v30 = 0;
    Length = a4->Length;
    if ( (unsigned __int16)v18 < a4->Length )
    {
      v30[1] = (__int64)a4->Buffer + v18;
      LOWORD(v30[0]) = Length - v18;
      WORD1(v30[0]) = Length - v18;
    }
    else
    {
      v30[1] = 0;
      LODWORD(v30[0]) = 0;
    }
    v31 = *(_OWORD *)v30;
    v13 = (void *)VfsLookupMappingForUserAndPackage(Buffer, a7, (int)Context + 8, (int)&v31, (__int64)v30);
    v29 = v13;
    if ( !v13 )
    {
      v15 = -1073741595;
      LODWORD(v23) = -1073741595;
      LogWrite(1, 0, L"VfsCowCopyFile() - Failed to get COW mapping to copy %wZ into the COW\n Status: 0x%08X", a4, v23);
      goto LABEL_23;
    }
    InstanceContext = VfsCreateParentDirectories(a3, Instance, (__int64)v13, (__int16 *)a6, *((_WORD *)v27 + 4));
    v15 = InstanceContext;
    if ( InstanceContext < 0 )
    {
      v16 = a6;
      v17 = L"VfsCowCopyFile() - Failed to create parent directories for %wZ\n Status: 0x%08X";
      goto LABEL_5;
    }
  }
  v15 = VfsOpenScb(a3, a7, (__int64)Buffer, (__int64)&Entry, (__int64)&FileHandle, 0);
  if ( v15 < 0 )
    goto LABEL_23;
  if ( Entry )
  {
    v15 = VfsCowCopyFileForScb((__int64)Entry, a2 & ((unsigned __int128)-(__int128)(unsigned __int64)Entry >> 64), a3);
    goto LABEL_23;
  }
  InstanceContext = VfsCopyFile(a3, v20, a4, Instance, 0, (struct _UNICODE_STRING *)a6, a10, v24, v25, 1, 0);
  v15 = InstanceContext;
  if ( InstanceContext == -1073741771 )
  {
    v15 = 0;
    goto LABEL_23;
  }
  if ( InstanceContext < 0 )
  {
    v16 = (__int64)a4;
    v17 = L"VfsCowCopyFile() - Failed to copy file: %wZ\n Status: 0x%08X";
    goto LABEL_5;
  }
LABEL_23:
  if ( Entry )
    VfsScbClose(Entry);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v13 )
    VfsReleaseMappingEntry(v13);
  if ( Context )
    FltReleaseContext(Context);
  if ( v27 )
    FltReleaseContext(v27);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140002b4c  mov     rax, rsp
0x140002b4f  mov     [rax+8], rcx
0x140002b53  push    rbx
0x140002b54  push    rsi
0x140002b55  push    rdi
0x140002b56  push    r12
0x140002b58  push    r14
0x140002b5a  push    r15
0x140002b5c  sub     rsp, 0B8h
0x140002b63  mov     rdi, r9
0x140002b66  mov     r14, r8
0x140002b69  mov     r15, rdx
0x140002b6c  xor     r12d, r12d
0x140002b6f  mov     [rax-70h], r12
0x140002b73  mov     [rax-78h], r12
0x140002b77  mov     [rax-80h], r12
0x140002b7b  mov     esi, r12d
0x140002b7e  mov     [rax-68h], r12
0x140002b82  mov     [rax+8], r12
0x140002b86  cmp     [rsp+0E8h+arg_40], r12b
0x140002b8e  jz      loc_140002CFD
0x140002b94  lea     rdx, [rax-78h]; Context
0x140002b98  mov     rcx, [rsp+0E8h+Instance]; Instance
0x140002ba0  call    cs:__imp_FltGetInstanceContext
0x140002ba7  nop     dword ptr [rax+rax+00h]
0x140002bac  mov     ebx, eax
0x140002bae  mov     [rsp+0E8h+var_88], eax
0x140002bb2  test    eax, eax
0x140002bb4  jns     short loc_140002BD8
0x140002bb6  mov     r9, [rsp+0E8h+Instance]
0x140002bbe  lea     r8, aVfscowcopyfile_2; "VfsCowCopyFile() - Failed to get instan"...
0x140002bc5  mov     dword ptr [rsp+0E8h+var_C8], eax
0x140002bc9  xor     edx, edx
0x140002bcb  lea     ecx, [rdx+1]
0x140002bce  call    LogWrite
0x140002bd3  jmp     loc_140002E13
0x140002bd8  lea     rdx, [rsp+0E8h+Context]; Context
0x140002bdd  mov     rcx, r14; Instance
0x140002be0  call    cs:__imp_FltGetInstanceContext
0x140002be7  nop     dword ptr [rax+rax+00h]
0x140002bec  mov     ebx, eax
0x140002bee  mov     [rsp+0E8h+var_88], eax
0x140002bf2  test    eax, eax
0x140002bf4  jns     short loc_140002BFB
0x140002bf6  mov     r9, r14
0x140002bf9  jmp     short loc_140002BBE
0x140002bfb  mov     r8, [rsp+0E8h+Context]
0x140002c00  add     r8, 8
0x140002c04  movzx   edx, word ptr [r8]
0x140002c08  xorps   xmm0, xmm0
0x140002c0b  movups  xmmword ptr [rsp+0E8h+var_58], xmm0
0x140002c13  movzx   ecx, word ptr [rdi]
0x140002c16  cmp     dx, cx
0x140002c19  jb      short loc_140002C2D
0x140002c1b  mov     [rsp+0E8h+var_58+8], r12
0x140002c23  mov     dword ptr [rsp+0E8h+var_58], r12d
0x140002c2b  jmp     short loc_140002C4F
0x140002c2d  mov     rax, rdx
0x140002c30  add     rax, [rdi+8]
0x140002c34  mov     [rsp+0E8h+var_58+8], rax
0x140002c3c  sub     cx, dx
0x140002c3f  mov     word ptr [rsp+0E8h+var_58], cx
0x140002c47  mov     word ptr [rsp+0E8h+var_58+2], cx
0x140002c4f  movaps  xmm0, xmmword ptr [rsp+0E8h+var_58]
0x140002c57  movdqa  [rsp+0E8h+var_48], xmm0
0x140002c60  lea     rax, [rsp+0E8h+var_58]
0x140002c68  mov     [rsp+0E8h+var_C8], rax; __int64
0x140002c6d  lea     r9, [rsp+0E8h+var_48]
0x140002c75  mov     rdx, [rsp+0E8h+arg_30]
0x140002c7d  mov     rcx, [rsp+0E8h+Buffer]; Buffer
0x140002c85  call    VfsLookupMappingForUserAndPackage
0x140002c8a  mov     rsi, rax
0x140002c8d  mov     [rsp+0E8h+var_68], rax
0x140002c95  test    rax, rax
0x140002c98  jnz     short loc_140002CB6
0x140002c9a  mov     ebx, 0C00000E5h
0x140002c9f  mov     [rsp+0E8h+var_88], ebx
0x140002ca3  mov     dword ptr [rsp+0E8h+var_C8], ebx
0x140002ca7  mov     r9, rdi
0x140002caa  lea     r8, aVfscowcopyfile_3; "VfsCowCopyFile() - Failed to get COW ma"...
0x140002cb1  jmp     loc_140002BC9
0x140002cb6  mov     rax, [rsp+0E8h+var_78]
0x140002cbb  movzx   ecx, word ptr [rax+8]
0x140002cbf  mov     word ptr [rsp+0E8h+var_C8], cx
0x140002cc4  mov     r9, [rsp+0E8h+arg_28]
0x140002ccc  mov     r8, rsi
0x140002ccf  mov     rdx, [rsp+0E8h+Instance]
0x140002cd7  mov     rcx, r14
0x140002cda  call    VfsCreateParentDirectories
0x140002cdf  mov     ebx, eax
0x140002ce1  mov     [rsp+0E8h+var_88], eax
0x140002ce5  test    eax, eax
0x140002ce7  jns     short loc_140002CFD
0x140002ce9  mov     r9, [rsp+0E8h+arg_28]
0x140002cf1  lea     r8, aVfscowcopyfile_4; "VfsCowCopyFile() - Failed to create par"...
0x140002cf8  jmp     loc_140002BC5
0x140002cfd  mov     [rsp+0E8h+var_A8], r12; int
0x140002d02  lea     rax, [rsp+0E8h+FileHandle]
0x140002d07  mov     [rsp+0E8h+var_B0], rax; int
0x140002d0c  lea     rax, [rsp+0E8h+Entry]
0x140002d14  mov     qword ptr [rsp+0E8h+var_B8], rax; __int64
0x140002d19  mov     rax, [rsp+0E8h+Buffer]
0x140002d21  mov     [rsp+0E8h+var_C0], rax; __int64
0x140002d26  mov     rax, [rsp+0E8h+arg_30]
0x140002d2e  mov     [rsp+0E8h+var_C8], rax; __int64
0x140002d33  xor     r9d, r9d
0x140002d36  mov     r8, rdi
0x140002d39  xor     edx, edx
0x140002d3b  mov     rcx, r14; Instance
0x140002d3e  call    VfsOpenScb
0x140002d43  mov     ebx, eax
0x140002d45  mov     [rsp+0E8h+var_88], eax
0x140002d49  test    eax, eax
0x140002d4b  js      loc_140002E13
0x140002d51  cmp     [rsp+0E8h+Entry], r12
0x140002d59  jnz     short loc_140002DBE
0x140002d5b  mov     [rsp+0E8h+var_98], r12b; char
0x140002d60  mov     [rsp+0E8h+var_A0], 1; char
0x140002d65  mov     al, [rsp+0E8h+arg_48]
0x140002d6c  mov     [rsp+0E8h+var_B8], al; char
0x140002d70  mov     rax, [rsp+0E8h+arg_28]
0x140002d78  mov     [rsp+0E8h+var_C0], rax; __int64
0x140002d7d  mov     [rsp+0E8h+var_C8], r12; __int64
0x140002d82  mov     r9, [rsp+0E8h+Instance]
0x140002d8a  mov     r8, rdi
0x140002d8d  mov     rcx, r14; Instance
0x140002d90  call    VfsCopyFile
0x140002d95  mov     ebx, eax
0x140002d97  mov     [rsp+0E8h+var_88], eax
0x140002d9b  cmp     eax, 0C0000035h
0x140002da0  jnz     short loc_140002DAB
0x140002da2  mov     ebx, r12d
0x140002da5  mov     [rsp+0E8h+var_88], ebx
0x140002da9  jmp     short loc_140002E13
0x140002dab  test    eax, eax
0x140002dad  jns     short loc_140002E13
0x140002daf  mov     r9, rdi
0x140002db2  lea     r8, aVfscowcopyfile_0; "VfsCowCopyFile() - Failed to copy file:"...
0x140002db9  jmp     loc_140002BC5
0x140002dbe  mov     rcx, [rsp+0E8h+Entry]
0x140002dc6  mov     rax, rcx
0x140002dc9  neg     rax
0x140002dcc  sbb     rdx, rdx
0x140002dcf  and     rdx, r15
0x140002dd2  mov     qword ptr [rsp+0E8h+var_98], r12
0x140002dd7  mov     [rsp+0E8h+var_A0], r12b
0x140002ddc  mov     byte ptr [rsp+0E8h+var_A8], 1
0x140002de1  mov     rax, [rsp+0E8h+arg_28]
0x140002de9  mov     [rsp+0E8h+var_B0], rax
0x140002dee  mov     qword ptr [rsp+0E8h+var_B8], r12
0x140002df3  mov     rax, [rsp+0E8h+Instance]
0x140002dfb  mov     [rsp+0E8h+var_C0], rax
0x140002e00  mov     [rsp+0E8h+var_C8], rdi
0x140002e05  mov     r8, r14
0x140002e08  call    VfsCowCopyFileForScb
0x140002e0d  mov     ebx, eax
0x140002e0f  mov     [rsp+0E8h+var_88], eax
0x140002e13  mov     rcx, [rsp+0E8h+Entry]; Entry
0x140002e1b  test    rcx, rcx
0x140002e1e  jz      short loc_140002E25
0x140002e20  call    VfsScbClose
0x140002e25  mov     rcx, [rsp+0E8h+FileHandle]; FileHandle
0x140002e2a  test    rcx, rcx
0x140002e2d  jz      short loc_140002E3B
0x140002e2f  call    cs:__imp_FltClose
0x140002e36  nop     dword ptr [rax+rax+00h]
0x140002e3b  test    rsi, rsi
0x140002e3e  jz      short loc_140002E48
0x140002e40  mov     rcx, rsi; P
0x140002e43  call    VfsReleaseMappingEntry
0x140002e48  mov     rcx, [rsp+0E8h+Context]; Context
0x140002e4d  test    rcx, rcx
0x140002e50  jz      short loc_140002E5E
0x140002e52  call    cs:__imp_FltReleaseContext
0x140002e59  nop     dword ptr [rax+rax+00h]
0x140002e5e  mov     rcx, [rsp+0E8h+var_78]; Context
0x140002e63  test    rcx, rcx
0x140002e66  jz      short loc_140002E74
0x140002e68  call    cs:__imp_FltReleaseContext
0x140002e6f  nop     dword ptr [rax+rax+00h]
0x140002e74  mov     eax, ebx
0x140002e76  add     rsp, 0B8h
0x140002e7d  pop     r15
0x140002e7f  pop     r14
0x140002e81  pop     r12
0x140002e83  pop     rdi
0x140002e84  pop     rsi
0x140002e85  pop     rbx
0x140002e86  retn
0x1400146a2  push    rbp
0x1400146a4  sub     rsp, 60h
0x1400146a8  mov     rbp, rdx
0x1400146ab  mov     rcx, [rbp+0F0h]; Entry
0x1400146b2  test    rcx, rcx
0x1400146b5  jz      short loc_1400146BD
0x1400146b7  call    VfsScbClose
0x1400146bc  nop
0x1400146bd  mov     rcx, [rbp+78h]; FileHandle
0x1400146c1  test    rcx, rcx
0x1400146c4  jz      short loc_1400146D3
0x1400146c6  call    cs:__imp_FltClose
0x1400146cd  nop     dword ptr [rax+rax+00h]
0x1400146d2  nop
0x1400146d3  mov     rcx, [rbp+80h]; P
0x1400146da  test    rcx, rcx
0x1400146dd  jz      short loc_1400146E5
0x1400146df  call    VfsReleaseMappingEntry
0x1400146e4  nop
0x1400146e5  mov     rcx, [rbp+68h]; Context
0x1400146e9  test    rcx, rcx
0x1400146ec  jz      short loc_1400146FB
0x1400146ee  call    cs:__imp_FltReleaseContext
0x1400146f5  nop     dword ptr [rax+rax+00h]
0x1400146fa  nop
0x1400146fb  mov     rcx, [rbp+70h]; Context
0x1400146ff  test    rcx, rcx
0x140014702  jz      short loc_140014711
0x140014704  call    cs:__imp_FltReleaseContext
0x14001470b  nop     dword ptr [rax+rax+00h]
0x140014710  nop
0x140014711  add     rsp, 60h
0x140014715  pop     rbp
0x140014716  retn
```
