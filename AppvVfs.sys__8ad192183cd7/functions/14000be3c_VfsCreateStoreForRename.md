# VfsCreateStoreForRename

- ea: `0x14000be3c`
- end: `0x14000c0fa`
- name: `VfsCreateStoreForRename`
- size: `702`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, struct _FLT_INSTANCE **, void **FileHandle)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14000c574`
- `0x14000cfd8`

## callees

- `0x140008c04`
- `0x14000be3c`
- `0x14000fd38`
- `0x14001070c`
- `0x140010aa8`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001510b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001510b`
- `FLTMGR!FltObjectDereference` at `0x14000c0d1`
- `FLTMGR!FltObjectDereference` at `0x14001512b`
- `FLTMGR!FltObjectDereference` at `0x14000c0d1`
- `FLTMGR!FltObjectDereference` at `0x14001512b`
- `FLTMGR!FltClose` at `0x14000c005`
- `FLTMGR!FltClose` at `0x14000c005`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000c09c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400150f3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000c09c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400150f3`

## string_xrefs

- `0x14000bec0`: `VfsCreateStoreForRename() - Failed to get filename info for fileobject: %p\n IRP: %d\n Status: 0x%08X`
- `0x14000bf25`: `VfsCreateStoreForRename() - Failed to map filename: %wZ\n for mapping: %wZ\n Status: 0x%08X`
- `0x14000bf75`: `VfsCreateStoreForRename() - Failed to create parent directories for %wZ\n Status: 0x%08X`
- `0x14000c021`: `VfsCreateStoreForRename() - Failed to create directory for %wZ\n Status: 0x%08X`
- `0x14000c06a`: `VfsCreateStoreForRename() - Failed to open file: %wZ\n Status: 0x%08X`
- `0x14000bfea`: `VfsCreateDirectory() - Failed to open file: %wZ\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsCreateStoreForRename(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct _FLT_INSTANCE **a4,
        void **FileHandle)
{
  struct _FLT_INSTANCE *v9; // rdi
  void **v10; // r13
  int FileNameInfoForFileObject; // eax
  int v12; // ebx
  struct _FLT_FILE_NAME_INFORMATION *v13; // r14
  int MappedTarget; // eax
  int ParentDirectories; // eax
  const WCHAR *v16; // r8
  int v17; // eax
  ULONG v19[2]; // [rsp+20h] [rbp-78h]
  ULONG v20[2]; // [rsp+20h] [rbp-78h]
  ULONG v21[2]; // [rsp+20h] [rbp-78h]
  int v22; // [rsp+28h] [rbp-70h]
  ULONG v23[2]; // [rsp+28h] [rbp-70h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+48h] [rbp-50h] BYREF
  void *v25; // [rsp+50h] [rbp-48h] BYREF
  PVOID P[2]; // [rsp+58h] [rbp-40h] BYREF
  PFLT_INSTANCE Instance; // [rsp+B8h] [rbp+20h] BYREF

  FileNameInformation = 0;
  v9 = 0;
  Instance = 0;
  v25 = 0;
  *(_OWORD *)P = 0;
  *a4 = 0;
  v10 = FileHandle;
  *FileHandle = 0;
  FileNameInfoForFileObject = VfsGetFileNameInfoForFileObject(
                                a1,
                                *(_QWORD *)(a2 + 48),
                                *(_QWORD *)(a2 + 40),
                                257,
                                &FileNameInformation);
  v12 = FileNameInfoForFileObject;
  if ( FileNameInfoForFileObject < 0 )
  {
    v22 = FileNameInfoForFileObject;
    v19[0] = *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL);
    LogWrite(
      1,
      0,
      L"VfsCreateStoreForRename() - Failed to get filename info for fileobject: %p\n IRP: %d\n Status: 0x%08X",
      *(_QWORD *)(a2 + 48),
      *(_QWORD *)v19,
      v22);
    v13 = FileNameInformation;
    goto LABEL_17;
  }
  v13 = FileNameInformation;
  MappedTarget = VfsGetMappedTarget(
                   *(PVOID *)(a2 + 40),
                   &FileNameInformation->Name.Length,
                   0,
                   a3,
                   (__int64)P,
                   &Instance);
  v12 = MappedTarget;
  if ( MappedTarget < 0 )
  {
    v23[0] = MappedTarget;
    LogWrite(
      1,
      0,
      L"VfsCreateStoreForRename() - Failed to map filename: %wZ\n for mapping: %wZ\n Status: 0x%08X",
      &v13->Name,
      *(_QWORD *)(a3 + 40),
      *(_QWORD *)v23);
    v9 = Instance;
    goto LABEL_17;
  }
  v9 = Instance;
  ParentDirectories = VfsCreateParentDirectories(
                        *(struct _FLT_INSTANCE **)(a2 + 40),
                        Instance,
                        a3,
                        (__int16 *)P,
                        *(_WORD *)(a3 + 8));
  v12 = ParentDirectories;
  if ( ParentDirectories >= 0 )
  {
    FileHandle = 0;
    v17 = VfsOpenFile(v9, 2u, 0x4021u, (PHANDLE)&FileHandle, 0);
    v12 = v17;
    if ( v17 >= 0 )
    {
      FltClose(FileHandle);
      v12 = 0;
    }
    else
    {
      v21[0] = v17;
      LogWrite(1, 0, L"VfsCreateDirectory() - Failed to open file: %wZ\n Status: 0x%08X", P, *(_QWORD *)v21);
    }
    if ( v12 < 0 )
    {
      v21[0] = v12;
      LogWrite(
        1,
        0,
        L"VfsCreateStoreForRename() - Failed to create directory for %wZ\n Status: 0x%08X",
        P,
        *(_QWORD *)v21);
      goto LABEL_17;
    }
    ParentDirectories = VfsOpenFile(v9, 1u, 0x4020u, &v25, 0);
    v12 = ParentDirectories;
    if ( ParentDirectories >= 0 )
    {
      *a4 = v9;
      *v10 = v25;
      v9 = 0;
      Instance = 0;
      v25 = 0;
      goto LABEL_17;
    }
    v16 = L"VfsCreateStoreForRename() - Failed to open file: %wZ\n Status: 0x%08X";
  }
  else
  {
    v16 = L"VfsCreateStoreForRename() - Failed to create parent directories for %wZ\n Status: 0x%08X";
  }
  v20[0] = ParentDirectories;
  LogWrite(1, 0, v16, P, *(_QWORD *)v20);
LABEL_17:
  if ( v13 )
    FltReleaseFileNameInformation(v13);
  if ( P[1] )
  {
    ExFreePoolWithTag(P[1], 0);
    P[1] = 0;
  }
  if ( v9 )
    FltObjectDereference(v9);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000be3c  mov     r11, rsp
0x14000be3f  mov     [r11+8], rbx
0x14000be43  mov     [r11+10h], rsi
0x14000be47  push    rdi
0x14000be48  push    r12
0x14000be4a  push    r13
0x14000be4c  push    r14
0x14000be4e  push    r15
0x14000be50  sub     rsp, 70h
0x14000be54  mov     r12, r9
0x14000be57  mov     r15, r8
0x14000be5a  mov     rsi, rdx
0x14000be5d  mov     r14, rcx
0x14000be60  xor     eax, eax
0x14000be62  mov     [r11-50h], rax
0x14000be66  mov     edi, eax
0x14000be68  mov     [r11+20h], rax
0x14000be6c  mov     [r11-48h], rax
0x14000be70  xorps   xmm0, xmm0
0x14000be73  movups  xmmword ptr [rsp+98h+P], xmm0
0x14000be78  mov     [r9], rax
0x14000be7b  mov     r13, [rsp+98h+FileHandle]
0x14000be83  mov     [r13+0], rax
0x14000be87  lea     rax, [r11-50h]
0x14000be8b  mov     [r11-78h], rax
0x14000be8f  mov     r9d, 101h
0x14000be95  mov     r8, [rdx+28h]
0x14000be99  mov     rdx, [rdx+30h]
0x14000be9d  call    VfsGetFileNameInfoForFileObject
0x14000bea2  mov     ebx, eax
0x14000bea4  mov     [rsp+98h+var_58], eax
0x14000bea8  test    eax, eax
0x14000beaa  jns     short loc_14000BEDB
0x14000beac  mov     rcx, [r14+10h]
0x14000beb0  movzx   edx, byte ptr [rcx+4]
0x14000beb4  mov     [rsp+98h+var_70], eax
0x14000beb8  mov     [rsp+98h+var_78], edx
0x14000bebc  mov     r9, [rsi+30h]
0x14000bec0  lea     r8, aVfscreatestore_2; "VfsCreateStoreForRename() - Failed to g"...
0x14000bec7  xor     edx, edx
0x14000bec9  lea     ecx, [rdi+1]
0x14000becc  call    LogWrite
0x14000bed1  mov     r14, [rsp+98h+FileNameInformation]
0x14000bed6  jmp     loc_14000C094
0x14000bedb  mov     r14, [rsp+98h+FileNameInformation]
0x14000bee0  lea     rax, [rsp+98h+Instance]
0x14000bee8  mov     qword ptr [rsp+98h+var_70], rax; __int64
0x14000beed  lea     rax, [rsp+98h+P]
0x14000bef2  mov     qword ptr [rsp+98h+var_78], rax; __int64
0x14000bef7  mov     r9, r15
0x14000befa  xor     r8d, r8d
0x14000befd  lea     rdx, [r14+8]
0x14000bf01  mov     rcx, [rsi+28h]; FltObject
0x14000bf05  call    VfsGetMappedTarget
0x14000bf0a  mov     ebx, eax
0x14000bf0c  mov     [rsp+98h+var_58], eax
0x14000bf10  test    eax, eax
0x14000bf12  jns     short loc_14000BF43
0x14000bf14  mov     [rsp+98h+var_70], eax
0x14000bf18  mov     rax, [r15+28h]
0x14000bf1c  mov     qword ptr [rsp+98h+var_78], rax
0x14000bf21  lea     r9, [r14+8]
0x14000bf25  lea     r8, aVfscreatestore_3; "VfsCreateStoreForRename() - Failed to m"...
0x14000bf2c  xor     edx, edx
0x14000bf2e  lea     ecx, [rdx+1]
0x14000bf31  call    LogWrite
0x14000bf36  mov     rdi, [rsp+98h+Instance]
0x14000bf3e  jmp     loc_14000C094
0x14000bf43  movzx   eax, word ptr [r15+8]
0x14000bf48  mov     word ptr [rsp+98h+var_78], ax
0x14000bf4d  lea     r9, [rsp+98h+P]
0x14000bf52  mov     r8, r15
0x14000bf55  mov     rdi, [rsp+98h+Instance]
0x14000bf5d  mov     rdx, rdi
0x14000bf60  mov     rcx, [rsi+28h]
0x14000bf64  call    VfsCreateParentDirectories
0x14000bf69  mov     ebx, eax
0x14000bf6b  mov     [rsp+98h+var_58], eax
0x14000bf6f  xor     edx, edx
0x14000bf71  test    eax, eax
0x14000bf73  jns     short loc_14000BF94
0x14000bf75  lea     r8, aVfscreatestore_1; "VfsCreateStoreForRename() - Failed to c"...
0x14000bf7c  mov     [rsp+98h+var_78], eax
0x14000bf80  lea     r9, [rsp+98h+P]
0x14000bf85  mov     ecx, 1
0x14000bf8a  call    LogWrite
0x14000bf8f  jmp     loc_14000C094
0x14000bf94  mov     [rsp+98h+FileHandle], 0
0x14000bfa0  mov     [rsp+98h+FileObject], 0; FileObject
0x14000bfa9  lea     rax, [rsp+98h+FileHandle]
0x14000bfb1  mov     [rsp+98h+var_68], rax; FileHandle
0x14000bfb6  mov     [rsp+98h+var_70], 4021h; ULONG
0x14000bfbe  mov     [rsp+98h+var_78], 2; ULONG
0x14000bfc6  mov     esi, 100000h
0x14000bfcb  mov     r9d, esi
0x14000bfce  lea     r8, [rsp+98h+P]
0x14000bfd3  mov     rcx, rdi; Instance
0x14000bfd6  call    VfsOpenFile
0x14000bfdb  mov     ebx, eax
0x14000bfdd  test    eax, eax
0x14000bfdf  jns     short loc_14000BFFD
0x14000bfe1  mov     [rsp+98h+var_78], eax
0x14000bfe5  lea     r9, [rsp+98h+P]
0x14000bfea  lea     r8, aVfscreatedirec; "VfsCreateDirectory() - Failed to open f"...
0x14000bff1  xor     edx, edx
0x14000bff3  lea     ecx, [rdx+1]
0x14000bff6  call    LogWrite
0x14000bffb  jmp     short loc_14000C013
0x14000bffd  mov     rcx, [rsp+98h+FileHandle]; FileHandle
0x14000c005  call    cs:__imp_FltClose
0x14000c00c  nop     dword ptr [rax+rax+00h]
0x14000c011  xor     ebx, ebx
0x14000c013  mov     [rsp+98h+var_58], ebx
0x14000c017  xor     edx, edx
0x14000c019  test    ebx, ebx
0x14000c01b  jns     short loc_14000C02D
0x14000c01d  mov     [rsp+98h+var_78], ebx
0x14000c021  lea     r8, aVfscreatestore_0; "VfsCreateStoreForRename() - Failed to c"...
0x14000c028  jmp     loc_14000BF80
0x14000c02d  mov     [rsp+98h+FileObject], 0; FileObject
0x14000c036  lea     rax, [rsp+98h+var_48]
0x14000c03b  mov     [rsp+98h+var_68], rax; FileHandle
0x14000c040  mov     [rsp+98h+var_70], 4020h; ULONG
0x14000c048  mov     [rsp+98h+var_78], 1; ULONG
0x14000c050  mov     r9d, esi
0x14000c053  lea     r8, [rsp+98h+P]
0x14000c058  mov     rcx, rdi; Instance
0x14000c05b  call    VfsOpenFile
0x14000c060  mov     ebx, eax
0x14000c062  mov     [rsp+98h+var_58], eax
0x14000c066  test    eax, eax
0x14000c068  jns     short loc_14000C078
0x14000c06a  lea     r8, aVfscreatestore; "VfsCreateStoreForRename() - Failed to o"...
0x14000c071  xor     edx, edx
0x14000c073  jmp     loc_14000BF7C
0x14000c078  mov     [r12], rdi
0x14000c07c  mov     rax, [rsp+98h+var_48]
0x14000c081  mov     [r13+0], rax
0x14000c085  xor     edi, edi
0x14000c087  mov     [rsp+98h+Instance], rdi
0x14000c08f  mov     [rsp+98h+var_48], rdi
0x14000c094  test    r14, r14
0x14000c097  jz      short loc_14000C0A8
0x14000c099  mov     rcx, r14; FileNameInformation
0x14000c09c  call    cs:__imp_FltReleaseFileNameInformation
0x14000c0a3  nop     dword ptr [rax+rax+00h]
0x14000c0a8  mov     rcx, [rsp+98h+P+8]; P
0x14000c0ad  test    rcx, rcx
0x14000c0b0  jz      short loc_14000C0C9
0x14000c0b2  xor     edx, edx; Tag
0x14000c0b4  call    cs:__imp_ExFreePoolWithTag
0x14000c0bb  nop     dword ptr [rax+rax+00h]
0x14000c0c0  mov     [rsp+98h+P+8], 0
0x14000c0c9  test    rdi, rdi
0x14000c0cc  jz      short loc_14000C0DD
0x14000c0ce  mov     rcx, rdi; FltObject
0x14000c0d1  call    cs:__imp_FltObjectDereference
0x14000c0d8  nop     dword ptr [rax+rax+00h]
0x14000c0dd  mov     eax, ebx
0x14000c0df  lea     r11, [rsp+98h+var_28]
0x14000c0e4  mov     rbx, [r11+30h]
0x14000c0e8  mov     rsi, [r11+38h]
0x14000c0ec  mov     rsp, r11
0x14000c0ef  pop     r15
0x14000c0f1  pop     r14
0x14000c0f3  pop     r13
0x14000c0f5  pop     r12
0x14000c0f7  pop     rdi
0x14000c0f8  retn
0x1400150e1  push    rbp
0x1400150e3  sub     rsp, 40h
0x1400150e7  mov     rbp, rdx
0x1400150ea  mov     rcx, [rbp+48h]; FileNameInformation
0x1400150ee  test    rcx, rcx
0x1400150f1  jz      short loc_140015100
0x1400150f3  call    cs:__imp_FltReleaseFileNameInformation
0x1400150fa  nop     dword ptr [rax+rax+00h]
0x1400150ff  nop
0x140015100  mov     rcx, [rbp+60h]; P
0x140015104  test    rcx, rcx
0x140015107  jz      short loc_14001511F
0x140015109  xor     edx, edx; Tag
0x14001510b  call    cs:__imp_ExFreePoolWithTag
0x140015112  nop     dword ptr [rax+rax+00h]
0x140015117  mov     qword ptr [rbp+60h], 0
0x14001511f  mov     rcx, [rbp+0B8h]; FltObject
0x140015126  test    rcx, rcx
0x140015129  jz      short loc_140015138
0x14001512b  call    cs:__imp_FltObjectDereference
0x140015132  nop     dword ptr [rax+rax+00h]
0x140015137  nop
0x140015138  add     rsp, 40h
0x14001513c  pop     rbp
0x14001513d  retn
```
