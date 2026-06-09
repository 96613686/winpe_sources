# VfsGenerateFileName

- ea: `0x14000a3c0`
- end: `0x14000a58e`
- name: `VfsGenerateFileName`
- size: `462`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, PFLT_CALLBACK_DATA CallbackData, int, _BYTE *, PFLT_NAME_CONTROL NameCtrl)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140009368`
- `0x14000a3c0`
- `0x14000a7d0`
- `0x14000d9cc`
- `0x14000f124`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a571`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014eae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a571`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014eae`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000a537`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000a537`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x14000a516`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x14000a516`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14000a46f`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14000a46f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000a559`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140014e96`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000a559`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140014e96`
- `FLTMGR!FltGetFileNameInformation` at `0x14000a41c`
- `FLTMGR!FltGetFileNameInformation` at `0x14000a453`
- `FLTMGR!FltGetFileNameInformation` at `0x14000a41c`
- `FLTMGR!FltGetFileNameInformation` at `0x14000a453`

## pseudocode

```c
__int64 __fastcall VfsGenerateFileName(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        PFLT_CALLBACK_DATA CallbackData,
        int a4,
        _BYTE *a5,
        PFLT_NAME_CONTROL NameCtrl)
{
  FLT_FILE_NAME_OPTIONS v9; // esi
  NTSTATUS v10; // ebx
  bool v11; // sf
  NTSTATUS FileNameInformationUnsafe; // eax
  UNICODE_STRING *p_Name; // rdi
  __int64 v14; // rdi
  void *Mapping; // r14
  struct _FILE_OBJECT *v16; // rdx
  struct _FLT_INSTANCE *v17; // rcx
  char v18; // al
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+38h] [rbp-60h] BYREF
  __int64 v21; // [rsp+40h] [rbp-58h] BYREF
  __int64 v22; // [rsp+48h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-48h] BYREF

  v22 = 0;
  v21 = 0;
  FileNameInformation = 0;
  DestinationString = 0;
  *a5 = 0;
  v9 = a4 & 0xFEFFFFFF;
  if ( !FileObject->FsContext )
  {
    v10 = FltGetFileNameInformation(CallbackData, v9, &FileNameInformation);
    v11 = v10 < 0;
LABEL_8:
    if ( v11 )
      goto LABEL_21;
    p_Name = &FileNameInformation->Name;
    goto LABEL_18;
  }
  if ( !VfsDecodeFileObject((__int64)FileObject, &v22, &v21) )
  {
    if ( CallbackData )
      FileNameInformationUnsafe = FltGetFileNameInformation(CallbackData, v9, &FileNameInformation);
    else
      FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(FileObject, Instance, v9, &FileNameInformation);
    v10 = FileNameInformationUnsafe;
    v11 = FileNameInformationUnsafe < 0;
    goto LABEL_8;
  }
  v14 = v21;
  if ( (*(_DWORD *)(v21 + 4) & 4) != 0 )
  {
    Mapping = 0;
    v17 = *(struct _FLT_INSTANCE **)(v21 + 40);
    v18 = 1;
    v16 = *(struct _FILE_OBJECT **)(v21 + 48);
  }
  else
  {
    v10 = *(_DWORD *)(v21 + 32);
    if ( v10 < 0 )
      goto LABEL_21;
    Mapping = (void *)VfsScbGetMapping(v22);
    v16 = *(struct _FILE_OBJECT **)(v14 + 72);
    v17 = *(struct _FLT_INSTANCE **)(v14 + 64);
    v18 = 0;
  }
  v10 = VfsUnMapFileName(v17, v16, (int)Mapping, v9, v18, &DestinationString);
  if ( Mapping )
    VfsReleaseMappingEntry(Mapping);
  if ( v10 >= 0 )
  {
    p_Name = &DestinationString;
LABEL_18:
    v10 = FltCheckAndGrowNameControl(NameCtrl, p_Name->Length);
    if ( v10 >= 0 )
    {
      RtlCopyUnicodeString(&NameCtrl->Name, p_Name);
      if ( FileObject->FsContext )
        *a5 = 1;
    }
  }
LABEL_21:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000a3c0  mov     rax, rsp
0x14000a3c3  push    rbx
0x14000a3c4  push    rsi
0x14000a3c5  push    rdi
0x14000a3c6  push    r12
0x14000a3c8  push    r14
0x14000a3ca  push    r15
0x14000a3cc  sub     rsp, 68h
0x14000a3d0  mov     esi, r9d
0x14000a3d3  mov     rbx, r8
0x14000a3d6  mov     r15, rdx
0x14000a3d9  mov     rdi, rcx
0x14000a3dc  mov     qword ptr [rax-50h], 0
0x14000a3e4  mov     qword ptr [rax-58h], 0
0x14000a3ec  mov     qword ptr [rax-60h], 0
0x14000a3f4  xorps   xmm0, xmm0
0x14000a3f7  movups  xmmword ptr [rax-48h], xmm0
0x14000a3fb  mov     r12, [rsp+98h+arg_20]
0x14000a403  mov     byte ptr [r12], 0
0x14000a408  btr     esi, 18h
0x14000a40c  cmp     qword ptr [rdx+18h], 0
0x14000a411  jnz     short loc_14000A42E
0x14000a413  lea     r8, [rax-60h]; FileNameInformation
0x14000a417  mov     edx, esi; NameOptions
0x14000a419  mov     rcx, rbx; CallbackData
0x14000a41c  call    cs:__imp_FltGetFileNameInformation
0x14000a423  nop     dword ptr [rax+rax+00h]
0x14000a428  mov     ebx, eax
0x14000a42a  test    eax, eax
0x14000a42c  jmp     short loc_14000A47F
0x14000a42e  lea     r8, [rsp+98h+var_58]
0x14000a433  lea     rdx, [rsp+98h+var_50]
0x14000a438  mov     rcx, r15
0x14000a43b  call    VfsDecodeFileObject
0x14000a440  test    al, al
0x14000a442  jnz     short loc_14000A494
0x14000a444  test    rbx, rbx
0x14000a447  jz      short loc_14000A461
0x14000a449  lea     r8, [rsp+98h+FileNameInformation]; FileNameInformation
0x14000a44e  mov     edx, esi; NameOptions
0x14000a450  mov     rcx, rbx; CallbackData
0x14000a453  call    cs:__imp_FltGetFileNameInformation
0x14000a45a  nop     dword ptr [rax+rax+00h]
0x14000a45f  jmp     short loc_14000A47B
0x14000a461  lea     r9, [rsp+98h+FileNameInformation]; FileNameInformation
0x14000a466  mov     r8d, esi; NameOptions
0x14000a469  mov     rdx, rdi; Instance
0x14000a46c  mov     rcx, r15; FileObject
0x14000a46f  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14000a476  nop     dword ptr [rax+rax+00h]
0x14000a47b  mov     ebx, eax
0x14000a47d  test    eax, eax
0x14000a47f  mov     [rsp+98h+var_68], eax
0x14000a483  js      loc_14000A54F
0x14000a489  mov     rdi, [rsp+98h+FileNameInformation]
0x14000a48e  add     rdi, 8
0x14000a492  jmp     short loc_14000A50B
0x14000a494  mov     rdi, [rsp+98h+var_58]
0x14000a499  mov     eax, [rdi+4]
0x14000a49c  test    al, 4
0x14000a49e  jnz     short loc_14000A4C9
0x14000a4a0  mov     ebx, [rdi+20h]
0x14000a4a3  test    ebx, ebx
0x14000a4a5  jns     short loc_14000A4B0
0x14000a4a7  mov     [rsp+98h+var_68], ebx
0x14000a4ab  jmp     loc_14000A54F
0x14000a4b0  mov     rcx, [rsp+98h+var_50]
0x14000a4b5  call    VfsScbGetMapping
0x14000a4ba  mov     r14, rax
0x14000a4bd  mov     rdx, [rdi+48h]
0x14000a4c1  mov     rcx, [rdi+40h]
0x14000a4c5  xor     al, al
0x14000a4c7  jmp     short loc_14000A4D6
0x14000a4c9  xor     r14d, r14d
0x14000a4cc  mov     rcx, [rdi+28h]; Instance
0x14000a4d0  mov     al, 1
0x14000a4d2  mov     rdx, [rdi+30h]; FileObject
0x14000a4d6  lea     r8, [rsp+98h+var_48]
0x14000a4db  mov     [rsp+98h+DestinationString], r8; DestinationString
0x14000a4e0  mov     [rsp+98h+var_78], al; char
0x14000a4e4  mov     r9d, esi; NameOptions
0x14000a4e7  mov     r8, r14; int
0x14000a4ea  call    VfsUnMapFileName
0x14000a4ef  mov     ebx, eax
0x14000a4f1  mov     [rsp+98h+var_68], eax
0x14000a4f5  test    r14, r14
0x14000a4f8  jz      short loc_14000A502
0x14000a4fa  mov     rcx, r14; P
0x14000a4fd  call    VfsReleaseMappingEntry
0x14000a502  test    ebx, ebx
0x14000a504  js      short loc_14000A54F
0x14000a506  lea     rdi, [rsp+98h+var_48]
0x14000a50b  movzx   edx, word ptr [rdi]; NewSize
0x14000a50e  mov     rcx, [rsp+98h+NameCtrl]; NameCtrl
0x14000a516  call    cs:__imp_FltCheckAndGrowNameControl
0x14000a51d  nop     dword ptr [rax+rax+00h]
0x14000a522  mov     ebx, eax
0x14000a524  mov     [rsp+98h+var_68], eax
0x14000a528  test    eax, eax
0x14000a52a  js      short loc_14000A54F
0x14000a52c  mov     rdx, rdi; SourceString
0x14000a52f  mov     rcx, [rsp+98h+NameCtrl]; DestinationString
0x14000a537  call    cs:__imp_RtlCopyUnicodeString
0x14000a53e  nop     dword ptr [rax+rax+00h]
0x14000a543  cmp     qword ptr [r15+18h], 0
0x14000a548  jz      short loc_14000A54F
0x14000a54a  mov     byte ptr [r12], 1
0x14000a54f  mov     rcx, [rsp+98h+FileNameInformation]; FileNameInformation
0x14000a554  test    rcx, rcx
0x14000a557  jz      short loc_14000A565
0x14000a559  call    cs:__imp_FltReleaseFileNameInformation
0x14000a560  nop     dword ptr [rax+rax+00h]
0x14000a565  mov     rcx, [rsp+98h+var_48.Buffer]; P
0x14000a56a  test    rcx, rcx
0x14000a56d  jz      short loc_14000A57D
0x14000a56f  xor     edx, edx; Tag
0x14000a571  call    cs:__imp_ExFreePoolWithTag
0x14000a578  nop     dword ptr [rax+rax+00h]
0x14000a57d  mov     eax, ebx
0x14000a57f  add     rsp, 68h
0x14000a583  pop     r15
0x14000a585  pop     r14
0x14000a587  pop     r12
0x14000a589  pop     rdi
0x14000a58a  pop     rsi
0x14000a58b  pop     rbx
0x14000a58c  retn
0x140014e84  push    rbp
0x140014e86  sub     rsp, 30h
0x140014e8a  mov     rbp, rdx
0x140014e8d  mov     rcx, [rbp+38h]; FileNameInformation
0x140014e91  test    rcx, rcx
0x140014e94  jz      short loc_140014EA3
0x140014e96  call    cs:__imp_FltReleaseFileNameInformation
0x140014e9d  nop     dword ptr [rax+rax+00h]
0x140014ea2  nop
0x140014ea3  mov     rcx, [rbp+58h]; P
0x140014ea7  test    rcx, rcx
0x140014eaa  jz      short loc_140014EBB
0x140014eac  xor     edx, edx; Tag
0x140014eae  call    cs:__imp_ExFreePoolWithTag
0x140014eb5  nop     dword ptr [rax+rax+00h]
0x140014eba  nop
0x140014ebb  add     rsp, 30h
0x140014ebf  pop     rbp
0x140014ec0  retn
```
