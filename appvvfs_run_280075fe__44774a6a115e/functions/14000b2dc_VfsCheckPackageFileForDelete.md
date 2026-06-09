# VfsCheckPackageFileForDelete

- ea: `0x14000b2dc`
- end: `0x14000b4e3`
- name: `VfsCheckPackageFileForDelete`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000bbf4`

## callees

- `0x1400037ac`
- `0x14000b2dc`
- `0x14000d868`

## import_xrefs

- `ntoskrnl!SeReleaseSubjectContext` at `0x14000b47b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000b47b`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000b40c`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000b40c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000b41c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000b41c`
- `ntoskrnl!SeAccessCheck` at `0x14000b468`
- `ntoskrnl!SeAccessCheck` at `0x14000b468`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b4a9`
- `ntoskrnl!ObfDereferenceObject` at `0x140014ff4`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b4a9`
- `ntoskrnl!ObfDereferenceObject` at `0x140014ff4`
- `FLTMGR!FltIsDirectory` at `0x14000b3b0`
- `FLTMGR!FltIsDirectory` at `0x14000b3b0`
- `FLTMGR!FltClose` at `0x14000b4bf`
- `FLTMGR!FltClose` at `0x14001500a`
- `FLTMGR!FltClose` at `0x14000b4bf`
- `FLTMGR!FltClose` at `0x14001500a`

## pseudocode

```c
__int64 __fastcall VfsCheckPackageFileForDelete(
        __int64 a1,
        struct _FLT_INSTANCE *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  NTSTATUS v8; // edi
  PVOID v9; // rsi
  bool v10; // zf
  __int64 v11; // rbx
  void *v12; // rbx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  int AccessStatus; // [rsp+54h] [rbp-54h] BYREF
  DWORD GrantedAccess; // [rsp+58h] [rbp-50h] BYREF
  PVOID Entry; // [rsp+60h] [rbp-48h] BYREF
  PFILE_OBJECT FileObject; // [rsp+68h] [rbp-40h] BYREF
  HANDLE FileHandle; // [rsp+70h] [rbp-38h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+78h] [rbp-30h] BYREF
  __int64 IsDirectory; // [rsp+B0h] [rbp+8h] BYREF

  IsDirectory = a1;
  Entry = 0;
  FileHandle = 0;
  FileObject = 0;
  v8 = VfsOpenScb(a2, a5, a6, (__int64)&Entry, (__int64)&FileHandle, (__int64)&FileObject);
  v9 = Entry;
  if ( v8 >= 0 )
  {
    if ( Entry )
    {
      if ( *((_DWORD *)Entry + 70) )
      {
LABEL_4:
        v8 = -1073741790;
        goto LABEL_13;
      }
      v10 = (*((_DWORD *)Entry + 68) & 2) == 0;
    }
    else
    {
      LOBYTE(IsDirectory) = 0;
      v8 = FltIsDirectory(FileObject, a2, (PBOOLEAN)&IsDirectory);
      if ( v8 < 0 )
        goto LABEL_13;
      v10 = (_BYTE)IsDirectory == 0;
    }
    if ( !v10 )
      goto LABEL_4;
    v11 = a7;
    if ( *(_QWORD *)(a7 + 80) )
    {
      memset(&SubjectContext, 0, sizeof(SubjectContext));
      AccessStatus = 0;
      GrantedAccess = 0;
      SeCaptureSubjectContext(&SubjectContext);
      v12 = *(void **)(v11 + 80);
      GenericMapping = IoGetFileObjectGenericMapping();
      LOBYTE(v12) = SeAccessCheck(
                      v12,
                      &SubjectContext,
                      0,
                      0x10000u,
                      0,
                      0,
                      GenericMapping,
                      1,
                      &GrantedAccess,
                      &AccessStatus);
      SeReleaseSubjectContext(&SubjectContext);
      if ( !(_BYTE)v12 )
        v8 = AccessStatus;
    }
  }
LABEL_13:
  if ( v9 )
    VfsScbClose(v9);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000b2dc  mov     rax, rsp
0x14000b2df  mov     [rax+10h], rbx
0x14000b2e3  mov     [rax+18h], rsi
0x14000b2e7  mov     [rax+8], rcx
0x14000b2eb  push    rdi
0x14000b2ec  sub     rsp, 0A0h
0x14000b2f3  mov     r10, r9
0x14000b2f6  mov     r11, r8
0x14000b2f9  mov     rbx, rdx
0x14000b2fc  mov     qword ptr [rax-48h], 0
0x14000b304  mov     qword ptr [rax-38h], 0
0x14000b30c  mov     qword ptr [rax-40h], 0
0x14000b314  lea     rax, [rax-40h]
0x14000b318  mov     [rsp+0A8h+GrantedAccess], rax; __int64
0x14000b31d  lea     rax, [rsp+0A8h+FileHandle]
0x14000b322  mov     qword ptr [rsp+0A8h+AccessMode], rax; __int64
0x14000b327  lea     rax, [rsp+0A8h+Entry]
0x14000b32c  mov     [rsp+0A8h+GenericMapping], rax; __int64
0x14000b331  mov     rax, [rsp+0A8h+arg_28]
0x14000b339  mov     [rsp+0A8h+Privileges], rax; __int64
0x14000b33e  mov     rax, [rsp+0A8h+arg_20]
0x14000b346  mov     qword ptr [rsp+0A8h+PreviouslyGrantedAccess], rax; __int64
0x14000b34b  mov     r9b, 1
0x14000b34e  mov     r8, r10
0x14000b351  mov     rdx, r11
0x14000b354  mov     rcx, rbx; Instance
0x14000b357  call    VfsOpenScb
0x14000b35c  mov     edi, eax
0x14000b35e  mov     [rsp+0A8h+var_58], eax
0x14000b362  mov     rsi, [rsp+0A8h+Entry]
0x14000b367  test    eax, eax
0x14000b369  js      loc_14000B492
0x14000b36f  test    rsi, rsi
0x14000b372  jz      short loc_14000B398
0x14000b374  cmp     dword ptr [rsi+118h], 0
0x14000b37b  jz      short loc_14000B387
0x14000b37d  mov     edi, 0C0000022h
0x14000b382  jmp     loc_14000B48E
0x14000b387  test    rsi, rsi
0x14000b38a  jz      short loc_14000B398
0x14000b38c  mov     eax, [rsi+110h]
0x14000b392  test    al, 2
0x14000b394  jz      short loc_14000B3D4
0x14000b396  jmp     short loc_14000B37D
0x14000b398  mov     byte ptr [rsp+0A8h+IsDirectory], 0
0x14000b3a0  lea     r8, [rsp+0A8h+IsDirectory]; IsDirectory
0x14000b3a8  mov     rdx, rbx; Instance
0x14000b3ab  mov     rcx, [rsp+0A8h+FileObject]; FileObject
0x14000b3b0  call    cs:__imp_FltIsDirectory
0x14000b3b7  nop     dword ptr [rax+rax+00h]
0x14000b3bc  mov     edi, eax
0x14000b3be  mov     [rsp+0A8h+var_58], eax
0x14000b3c2  test    eax, eax
0x14000b3c4  js      loc_14000B492
0x14000b3ca  cmp     byte ptr [rsp+0A8h+IsDirectory], 0
0x14000b3d2  jmp     short loc_14000B394
0x14000b3d4  mov     rbx, [rsp+0A8h+arg_30]
0x14000b3dc  cmp     qword ptr [rbx+50h], 0
0x14000b3e1  jz      loc_14000B492
0x14000b3e7  xorps   xmm0, xmm0
0x14000b3ea  movups  xmmword ptr [rsp+0A8h+SubjectContext.ClientToken], xmm0
0x14000b3ef  movups  xmmword ptr [rsp+0A8h+SubjectContext.PrimaryToken], xmm0
0x14000b3f7  mov     [rsp+0A8h+var_54], 0
0x14000b3ff  mov     [rsp+0A8h+var_50], 0
0x14000b407  lea     rcx, [rsp+0A8h+SubjectContext]; SubjectContext
0x14000b40c  call    cs:__imp_SeCaptureSubjectContext
0x14000b413  nop     dword ptr [rax+rax+00h]
0x14000b418  mov     rbx, [rbx+50h]
0x14000b41c  call    cs:__imp_IoGetFileObjectGenericMapping
0x14000b423  nop     dword ptr [rax+rax+00h]
0x14000b428  lea     rcx, [rsp+0A8h+var_54]
0x14000b42d  mov     [rsp+0A8h+AccessStatus], rcx; AccessStatus
0x14000b432  lea     rcx, [rsp+0A8h+var_50]
0x14000b437  mov     [rsp+0A8h+GrantedAccess], rcx; GrantedAccess
0x14000b43c  mov     [rsp+0A8h+AccessMode], 1; AccessMode
0x14000b441  mov     [rsp+0A8h+GenericMapping], rax; GenericMapping
0x14000b446  mov     [rsp+0A8h+Privileges], 0; Privileges
0x14000b44f  mov     [rsp+0A8h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14000b457  mov     r9d, 10000h; DesiredAccess
0x14000b45d  xor     r8d, r8d; SubjectContextLocked
0x14000b460  lea     rdx, [rsp+0A8h+SubjectContext]; SubjectSecurityContext
0x14000b465  mov     rcx, rbx; SecurityDescriptor
0x14000b468  call    cs:__imp_SeAccessCheck
0x14000b46f  nop     dword ptr [rax+rax+00h]
0x14000b474  mov     bl, al
0x14000b476  lea     rcx, [rsp+0A8h+SubjectContext]; SubjectContext
0x14000b47b  call    cs:__imp_SeReleaseSubjectContext
0x14000b482  nop     dword ptr [rax+rax+00h]
0x14000b487  test    bl, bl
0x14000b489  cmovz   edi, [rsp+0A8h+var_54]
0x14000b48e  mov     [rsp+0A8h+var_58], edi
0x14000b492  test    rsi, rsi
0x14000b495  jz      short loc_14000B49F
0x14000b497  mov     rcx, rsi; Entry
0x14000b49a  call    VfsScbClose
0x14000b49f  mov     rcx, [rsp+0A8h+FileObject]; Object
0x14000b4a4  test    rcx, rcx
0x14000b4a7  jz      short loc_14000B4B5
0x14000b4a9  call    cs:__imp_ObfDereferenceObject
0x14000b4b0  nop     dword ptr [rax+rax+00h]
0x14000b4b5  mov     rcx, [rsp+0A8h+FileHandle]; FileHandle
0x14000b4ba  test    rcx, rcx
0x14000b4bd  jz      short loc_14000B4CB
0x14000b4bf  call    cs:__imp_FltClose
0x14000b4c6  nop     dword ptr [rax+rax+00h]
0x14000b4cb  mov     eax, edi
0x14000b4cd  lea     r11, [rsp+0A8h+var_8]
0x14000b4d5  mov     rbx, [r11+18h]
0x14000b4d9  mov     rsi, [r11+20h]
0x14000b4dd  mov     rsp, r11
0x14000b4e0  pop     rdi
0x14000b4e1  retn
0x140014fd3  push    rbp
0x140014fd5  sub     rsp, 50h
0x140014fd9  mov     rbp, rdx
0x140014fdc  mov     rcx, [rbp+60h]; Entry
0x140014fe0  test    rcx, rcx
0x140014fe3  jz      short loc_140014FEB
0x140014fe5  call    VfsScbClose
0x140014fea  nop
0x140014feb  mov     rcx, [rbp+68h]; Object
0x140014fef  test    rcx, rcx
0x140014ff2  jz      short loc_140015001
0x140014ff4  call    cs:__imp_ObfDereferenceObject
0x140014ffb  nop     dword ptr [rax+rax+00h]
0x140015000  nop
0x140015001  mov     rcx, [rbp+70h]; FileHandle
0x140015005  test    rcx, rcx
0x140015008  jz      short loc_140015017
0x14001500a  call    cs:__imp_FltClose
0x140015011  nop     dword ptr [rax+rax+00h]
0x140015016  nop
0x140015017  add     rsp, 50h
0x14001501b  pop     rbp
0x14001501c  retn
```
