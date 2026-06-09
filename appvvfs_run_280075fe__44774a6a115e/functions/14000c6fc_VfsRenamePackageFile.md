# VfsRenamePackageFile

- ea: `0x14000c6fc`
- end: `0x14000c8bd`
- name: `VfsRenamePackageFile`
- size: `449`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x14000ca28`
- `0x14000cd04`
- `0x14000cfd8`

## callees

- `0x140002e90`
- `0x140005b48`
- `0x140009368`
- `0x14000c6fc`
- `0x14000d9cc`
- `0x14000e110`
- `0x140010aa8`
- `0x140012acc`

## import_xrefs

- `FLTMGR!FltReleaseFileNameInformation` at `0x14000c891`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400151ee`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000c891`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400151ee`

## string_xrefs

- `0x14000c79a`: `VfsRenamePackageFile() - Failed to get filename info for fileobject: %p\n IRP: %d\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsRenamePackageFile(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        char a7,
        char a8,
        _BYTE *a9)
{
  int v11; // ebx
  struct _FLT_FILE_NAME_INFORMATION *v12; // rsi
  void *Mapping; // r14
  int FileNameInfoForFileObject; // eax
  __int64 p_Name; // r15
  __int64 v16; // rax
  __int64 v18; // [rsp+20h] [rbp-88h]
  struct _FLT_FILE_NAME_INFORMATION *v19; // [rsp+68h] [rbp-40h] BYREF
  void *v20; // [rsp+70h] [rbp-38h]

  v11 = 0;
  v12 = 0;
  v19 = 0;
  v20 = 0;
  *a9 = 0;
  Mapping = (void *)VfsScbGetMapping(*(_QWORD *)(a2 + 24), a2);
  v20 = Mapping;
  if ( Mapping )
  {
    FileNameInfoForFileObject = VfsGetFileNameInfoForFileObject(
                                  a1,
                                  *(_QWORD *)(a2 + 48),
                                  *(_QWORD *)(a2 + 40),
                                  257,
                                  &v19);
    v11 = FileNameInfoForFileObject;
    if ( FileNameInfoForFileObject >= 0 )
    {
      v12 = v19;
      p_Name = (__int64)&v19->Name;
      v11 = VfsCowCopyFileForScb(*(_QWORD *)(a2 + 24), 0, *(struct _FLT_INSTANCE **)(a2 + 40));
      if ( v11 >= 0 )
      {
        v11 = *(_DWORD *)(a2 + 32);
        if ( v11 >= 0 )
        {
          if ( a7 )
            VfsScbUpdateMapping(*(_QWORD *)(a2 + 24), a6);
          v16 = *(_QWORD *)(a2 + 24);
          if ( a8 )
            _InterlockedOr((volatile signed __int32 *)(v16 + 272), 4u);
          else
            _InterlockedAnd((volatile signed __int32 *)(v16 + 272), 0xFFFFFFFB);
          v11 = VfsMarkPackageFileDeleted(*(void **)(a2 + 40), p_Name, (__int64)Mapping);
          if ( v11 >= 0 )
            *a9 = 1;
        }
      }
    }
    else
    {
      LODWORD(v18) = *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL);
      LogWrite(
        1,
        0,
        L"VfsRenamePackageFile() - Failed to get filename info for fileobject: %p\n IRP: %d\n Status: 0x%08X",
        *(_QWORD *)(a2 + 48),
        v18,
        FileNameInfoForFileObject);
      v12 = v19;
    }
  }
  if ( Mapping )
    VfsReleaseMappingEntry(Mapping);
  if ( v12 )
    FltReleaseFileNameInformation(v12);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000c6fc  mov     r11, rsp
0x14000c6ff  mov     [r11+8], rbx
0x14000c703  mov     [r11+10h], rsi
0x14000c707  mov     [r11+18h], r8
0x14000c70b  push    rdi
0x14000c70c  push    r12
0x14000c70e  push    r13
0x14000c710  push    r14
0x14000c712  push    r15
0x14000c714  sub     rsp, 80h
0x14000c71b  mov     r13, r9
0x14000c71e  mov     rdi, rdx
0x14000c721  mov     r15, rcx
0x14000c724  xor     eax, eax
0x14000c726  mov     ebx, eax
0x14000c728  mov     esi, eax
0x14000c72a  mov     [r11-40h], rax
0x14000c72e  mov     [r11-38h], rax
0x14000c732  mov     [rsp+0A8h+var_48], al
0x14000c736  mov     r12, [rsp+0A8h+arg_40]
0x14000c73e  mov     [r12], al
0x14000c742  mov     rcx, [rdx+18h]
0x14000c746  call    VfsScbGetMapping
0x14000c74b  mov     r14, rax
0x14000c74e  mov     [rsp+0A8h+var_38], rax
0x14000c753  test    rax, rax
0x14000c756  jz      loc_14000C87C
0x14000c75c  lea     rax, [rsp+0A8h+var_40]
0x14000c761  mov     [rsp+0A8h+var_88], rax
0x14000c766  mov     r9d, 101h
0x14000c76c  mov     r8, [rdi+28h]
0x14000c770  mov     rdx, [rdi+30h]
0x14000c774  mov     rcx, r15
0x14000c777  call    VfsGetFileNameInfoForFileObject
0x14000c77c  mov     ebx, eax
0x14000c77e  mov     [rsp+0A8h+var_44], eax
0x14000c782  test    eax, eax
0x14000c784  jns     short loc_14000C7B5
0x14000c786  mov     rcx, [r15+10h]
0x14000c78a  movzx   edx, byte ptr [rcx+4]
0x14000c78e  mov     dword ptr [rsp+0A8h+var_80], eax
0x14000c792  mov     dword ptr [rsp+0A8h+var_88], edx
0x14000c796  mov     r9, [rdi+30h]
0x14000c79a  lea     r8, aVfsrenamepacka; "VfsRenamePackageFile() - Failed to get "...
0x14000c7a1  xor     edx, edx
0x14000c7a3  lea     ecx, [rsi+1]
0x14000c7a6  call    LogWrite
0x14000c7ab  mov     rsi, [rsp+0A8h+var_40]
0x14000c7b0  jmp     loc_14000C87C
0x14000c7b5  mov     rsi, [rsp+0A8h+var_40]
0x14000c7ba  lea     r15, [rsi+8]
0x14000c7be  lea     rax, [rsp+0A8h+var_48]
0x14000c7c3  mov     [rsp+0A8h+var_58], rax
0x14000c7c8  mov     [rsp+0A8h+var_60], 1
0x14000c7cd  mov     [rsp+0A8h+var_68], 0
0x14000c7d2  mov     rax, [rsp+0A8h+arg_20]
0x14000c7da  mov     [rsp+0A8h+var_70], rax
0x14000c7df  mov     [rsp+0A8h+var_78], r13
0x14000c7e4  mov     rax, [rsp+0A8h+arg_10]
0x14000c7ec  mov     [rsp+0A8h+var_80], rax
0x14000c7f1  mov     [rsp+0A8h+var_88], r15
0x14000c7f6  mov     r8, [rdi+28h]
0x14000c7fa  xor     edx, edx
0x14000c7fc  mov     rcx, [rdi+18h]
0x14000c800  call    VfsCowCopyFileForScb
0x14000c805  mov     ebx, eax
0x14000c807  mov     [rsp+0A8h+var_44], eax
0x14000c80b  test    eax, eax
0x14000c80d  js      short loc_14000C87C
0x14000c80f  cmp     [rsp+0A8h+var_48], 0
0x14000c814  jnz     short loc_14000C87C
0x14000c816  mov     ebx, [rdi+20h]
0x14000c819  test    ebx, ebx
0x14000c81b  jns     short loc_14000C823
0x14000c81d  mov     [rsp+0A8h+var_44], ebx
0x14000c821  jmp     short loc_14000C87C
0x14000c823  cmp     [rsp+0A8h+arg_30], 0
0x14000c82b  jz      short loc_14000C83E
0x14000c82d  mov     rdx, [rsp+0A8h+arg_28]
0x14000c835  mov     rcx, [rdi+18h]
0x14000c839  call    VfsScbUpdateMapping
0x14000c83e  mov     rax, [rdi+18h]
0x14000c842  cmp     [rsp+0A8h+arg_38], 0
0x14000c84a  jz      short loc_14000C856
0x14000c84c  lock or dword ptr [rax+110h], 4
0x14000c854  jmp     short loc_14000C85E
0x14000c856  lock and dword ptr [rax+110h], 0FFFFFFFBh
0x14000c85e  mov     r8, r14
0x14000c861  mov     rdx, r15
0x14000c864  mov     rcx, [rdi+28h]
0x14000c868  call    VfsMarkPackageFileDeleted
0x14000c86d  mov     ebx, eax
0x14000c86f  mov     [rsp+0A8h+var_44], eax
0x14000c873  test    eax, eax
0x14000c875  js      short loc_14000C87C
0x14000c877  mov     byte ptr [r12], 1
0x14000c87c  test    r14, r14
0x14000c87f  jz      short loc_14000C889
0x14000c881  mov     rcx, r14; P
0x14000c884  call    VfsReleaseMappingEntry
0x14000c889  test    rsi, rsi
0x14000c88c  jz      short loc_14000C89D
0x14000c88e  mov     rcx, rsi; FileNameInformation
0x14000c891  call    cs:__imp_FltReleaseFileNameInformation
0x14000c898  nop     dword ptr [rax+rax+00h]
0x14000c89d  mov     eax, ebx
0x14000c89f  lea     r11, [rsp+0A8h+var_28]
0x14000c8a7  mov     rbx, [r11+30h]
0x14000c8ab  mov     rsi, [r11+38h]
0x14000c8af  mov     rsp, r11
0x14000c8b2  pop     r15
0x14000c8b4  pop     r14
0x14000c8b6  pop     r13
0x14000c8b8  pop     r12
0x14000c8ba  pop     rdi
0x14000c8bb  retn
0x1400151cd  push    rbp
0x1400151cf  sub     rsp, 60h
0x1400151d3  mov     rbp, rdx
0x1400151d6  mov     rcx, [rbp+70h]; P
0x1400151da  test    rcx, rcx
0x1400151dd  jz      short loc_1400151E5
0x1400151df  call    VfsReleaseMappingEntry
0x1400151e4  nop
0x1400151e5  mov     rcx, [rbp+68h]; FileNameInformation
0x1400151e9  test    rcx, rcx
0x1400151ec  jz      short loc_1400151FB
0x1400151ee  call    cs:__imp_FltReleaseFileNameInformation
0x1400151f5  nop     dword ptr [rax+rax+00h]
0x1400151fa  nop
0x1400151fb  add     rsp, 60h
0x1400151ff  pop     rbp
0x140015200  retn
```
