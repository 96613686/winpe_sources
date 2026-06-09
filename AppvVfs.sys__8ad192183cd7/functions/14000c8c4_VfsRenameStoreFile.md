# VfsRenameStoreFile

- ea: `0x14000c8c4`
- end: `0x14000ca21`
- name: `VfsRenameStoreFile`
- size: `349`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const void **, __int64, char, char, char)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000ca28`
- `0x14000cd04`
- `0x14000cfd8`

## callees

- `0x14000c8c4`
- `0x14000e110`
- `0x14000f7ac`
- `0x140010aa8`
- `0x140011134`
- `0x140012acc`

## import_xrefs

- `FLTMGR!FltReleaseFileNameInformation` at `0x14000c9f8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001521a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000c9f8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001521a`

## string_xrefs

- `0x14000c93e`: `VfsRenameStoreFile() - Failed to get filename info for fileobject: %p\n IRP: %d\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsRenameStoreFile(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const void **a4,
        __int64 a5,
        char a6,
        char a7,
        char a8)
{
  int v11; // r15d
  PFLT_INSTANCE *v12; // rsi
  NTSTATUS FileNameInfoForFileObject; // eax
  int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v18; // [rsp+20h] [rbp-48h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+78h] [rbp+10h] BYREF
  __int64 v20; // [rsp+80h] [rbp+18h]

  v20 = a3;
  FileNameInformation = 0;
  v11 = *(_DWORD *)(*(_QWORD *)(a2 + 24) + 272LL) & 4;
  v12 = (PFLT_INSTANCE *)(a2 + 64);
  if ( v11
    && (FileNameInfoForFileObject = VfsGetFileNameInfoForFileObject(
                                      a1,
                                      *(struct _FILE_OBJECT **)(a2 + 72),
                                      *v12,
                                      0x101u,
                                      &FileNameInformation),
        v14 = FileNameInfoForFileObject,
        FileNameInfoForFileObject < 0) )
  {
    LODWORD(v18) = *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL);
    LogWrite(
      1,
      0,
      L"VfsRenameStoreFile() - Failed to get filename info for fileobject: %p\n IRP: %d\n Status: 0x%08X",
      *(_QWORD *)(a2 + 48),
      v18,
      FileNameInfoForFileObject,
      FileNameInfoForFileObject);
  }
  else
  {
    v14 = VfsRenameFile(*v12, *(PFILE_OBJECT *)(a2 + 72), v20, a4, a8);
    if ( v14 >= 0 )
    {
      if ( a6 )
        VfsScbUpdateMapping(*(_QWORD *)(a2 + 24), a5);
      v16 = *(_QWORD *)(a2 + 24);
      if ( a7 )
        _InterlockedOr((volatile signed __int32 *)(v16 + 272), 4u);
      else
        _InterlockedAnd((volatile signed __int32 *)(v16 + 272), 0xFFFFFFFB);
      if ( v11 )
        v14 = VfsMarkFileDeleted(
                *v12,
                v15,
                (__int64)&FileNameInformation->Name,
                (*(_DWORD *)(*(_QWORD *)(a2 + 24) + 272LL) & 2) != 0);
    }
  }
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14000c8c4  mov     r11, rsp
0x14000c8c7  mov     [r11+8], rbx
0x14000c8cb  mov     [r11+20h], rsi
0x14000c8cf  mov     [r11+18h], r8
0x14000c8d3  push    rdi
0x14000c8d4  push    r12
0x14000c8d6  push    r13
0x14000c8d8  push    r14
0x14000c8da  push    r15
0x14000c8dc  sub     rsp, 40h
0x14000c8e0  mov     r12, r9
0x14000c8e3  mov     rdi, rdx
0x14000c8e6  mov     r13, rcx
0x14000c8e9  mov     qword ptr [r11+10h], 0
0x14000c8f1  mov     rax, [rdx+18h]
0x14000c8f5  mov     r15d, [rax+110h]
0x14000c8fc  and     r15d, 4
0x14000c900  lea     rsi, [rdx+40h]
0x14000c904  jz      short loc_14000C954
0x14000c906  lea     rax, [r11+10h]
0x14000c90a  mov     [r11-48h], rax
0x14000c90e  mov     r9d, 101h
0x14000c914  mov     r8, [rsi]
0x14000c917  mov     rdx, [rdx+48h]
0x14000c91b  call    VfsGetFileNameInfoForFileObject
0x14000c920  mov     ebx, eax
0x14000c922  mov     [rsp+68h+var_38], eax
0x14000c926  test    eax, eax
0x14000c928  jns     short loc_14000C954
0x14000c92a  mov     rcx, [r13+10h]
0x14000c92e  movzx   edx, byte ptr [rcx+4]
0x14000c932  mov     [rsp+68h+var_40], eax
0x14000c936  mov     dword ptr [rsp+68h+var_48], edx
0x14000c93a  mov     r9, [rdi+30h]
0x14000c93e  lea     r8, aVfsrenamestore; "VfsRenameStoreFile() - Failed to get fi"...
0x14000c945  xor     edx, edx
0x14000c947  lea     ecx, [rdx+1]
0x14000c94a  call    LogWrite
0x14000c94f  jmp     loc_14000C9EE
0x14000c954  mov     al, [rsp+68h+arg_38]
0x14000c95b  mov     [rsp+68h+var_48], al; char
0x14000c95f  mov     r9, r12
0x14000c962  mov     r8, [rsp+68h+arg_10]
0x14000c96a  mov     rdx, [rdi+48h]; FileObject
0x14000c96e  mov     rcx, [rsi]; Instance
0x14000c971  call    VfsRenameFile
0x14000c976  mov     ebx, eax
0x14000c978  mov     [rsp+68h+var_38], eax
0x14000c97c  test    eax, eax
0x14000c97e  js      short loc_14000C9EE
0x14000c980  cmp     [rsp+68h+arg_28], 0
0x14000c988  jz      short loc_14000C99B
0x14000c98a  mov     rdx, [rsp+68h+arg_20]
0x14000c992  mov     rcx, [rdi+18h]
0x14000c996  call    VfsScbUpdateMapping
0x14000c99b  mov     rax, [rdi+18h]
0x14000c99f  cmp     [rsp+68h+arg_30], 0
0x14000c9a7  jz      short loc_14000C9B3
0x14000c9a9  lock or dword ptr [rax+110h], 4
0x14000c9b1  jmp     short loc_14000C9BB
0x14000c9b3  lock and dword ptr [rax+110h], 0FFFFFFFBh
0x14000c9bb  test    r15d, r15d
0x14000c9be  jz      short loc_14000C9EE
0x14000c9c0  mov     rax, [rdi+18h]
0x14000c9c4  mov     r9d, [rax+110h]
0x14000c9cb  shr     r9d, 1
0x14000c9ce  and     r9b, 1
0x14000c9d2  mov     r8, [rsp+68h+FileNameInformation]
0x14000c9d7  add     r8, 8
0x14000c9db  mov     [rsp+68h+var_48], 1; char
0x14000c9e0  mov     rcx, [rsi]; Instance
0x14000c9e3  call    VfsMarkFileDeleted
0x14000c9e8  mov     ebx, eax
0x14000c9ea  mov     [rsp+68h+var_38], eax
0x14000c9ee  mov     rcx, [rsp+68h+FileNameInformation]; FileNameInformation
0x14000c9f3  test    rcx, rcx
0x14000c9f6  jz      short loc_14000CA04
0x14000c9f8  call    cs:__imp_FltReleaseFileNameInformation
0x14000c9ff  nop     dword ptr [rax+rax+00h]
0x14000ca04  mov     eax, ebx
0x14000ca06  lea     r11, [rsp+68h+var_28]
0x14000ca0b  mov     rbx, [r11+30h]
0x14000ca0f  mov     rsi, [r11+48h]
0x14000ca13  mov     rsp, r11
0x14000ca16  pop     r15
0x14000ca18  pop     r14
0x14000ca1a  pop     r13
0x14000ca1c  pop     r12
0x14000ca1e  pop     rdi
0x14000ca1f  retn
0x140015208  push    rbp
0x14001520a  sub     rsp, 30h
0x14001520e  mov     rbp, rdx
0x140015211  mov     rcx, [rbp+78h]; FileNameInformation
0x140015215  test    rcx, rcx
0x140015218  jz      short loc_140015227
0x14001521a  call    cs:__imp_FltReleaseFileNameInformation
0x140015221  nop     dword ptr [rax+rax+00h]
0x140015226  nop
0x140015227  add     rsp, 30h
0x14001522b  pop     rbp
0x14001522c  retn
```
