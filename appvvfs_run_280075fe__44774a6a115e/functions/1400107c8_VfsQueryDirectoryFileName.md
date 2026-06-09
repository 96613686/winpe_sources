# VfsQueryDirectoryFileName

- ea: `0x1400107c8`
- end: `0x1400108b2`
- name: `VfsQueryDirectoryFileName`
- size: `234`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, ULONG Length)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a22c`
- `0x14000a5a0`
- `0x140010cb4`

## callees

- `0x14001070c`
- `0x1400107c8`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140010887`
- `ntoskrnl!ObfDereferenceObject` at `0x140010887`
- `FLTMGR!FltClose` at `0x140010898`
- `FLTMGR!FltClose` at `0x140010898`
- `FLTMGR!FltQueryDirectoryFile` at `0x140010874`
- `FLTMGR!FltQueryDirectoryFile` at `0x140010874`

## string_xrefs

- `0x140010830`: `VfsQueryDirectoryFileName() - Failed to open file: %wZ\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsQueryDirectoryFileName(
        PFLT_INSTANCE Instance,
        __int64 a2,
        struct _UNICODE_STRING *a3,
        void *a4,
        ULONG Length)
{
  int v9; // eax
  unsigned int DirectoryFile; // ebx
  __int64 FileInformationClass; // [rsp+20h] [rbp-68h]
  PFILE_OBJECT FileObject; // [rsp+50h] [rbp-38h] BYREF
  HANDLE FileHandle; // [rsp+58h] [rbp-30h] BYREF

  FileObject = 0;
  FileHandle = 0;
  v9 = VfsOpenFile(Instance, 1u, 0x4021u, &FileHandle, &FileObject);
  DirectoryFile = v9;
  if ( v9 >= 0 )
  {
    DirectoryFile = FltQueryDirectoryFile(Instance, FileObject, a4, Length, FileNamesInformation, 1u, a3, 1u, 0);
    ObfDereferenceObject(FileObject);
    FltClose(FileHandle);
  }
  else
  {
    LODWORD(FileInformationClass) = v9;
    LogWrite(1, 0, L"VfsQueryDirectoryFileName() - Failed to open file: %wZ\n Status: 0x%08X", a2, FileInformationClass);
  }
  return DirectoryFile;
}

```

## disassembly

```asm
0x1400107c8  mov     r11, rsp
0x1400107cb  push    rbx
0x1400107cc  push    rbp
0x1400107cd  push    rsi
0x1400107ce  push    rdi
0x1400107cf  push    r14
0x1400107d1  sub     rsp, 60h
0x1400107d5  lea     rax, [r11-38h]
0x1400107d9  mov     qword ptr [r11-38h], 0
0x1400107e1  mov     [r11-50h], rax
0x1400107e5  mov     r14, r8
0x1400107e8  lea     rax, [r11-30h]
0x1400107ec  mov     qword ptr [r11-30h], 0
0x1400107f4  mov     [r11-58h], rax
0x1400107f8  mov     rbp, r9
0x1400107fb  mov     rdi, rdx
0x1400107fe  mov     dword ptr [rsp+88h+ReturnSingleEntry], 4021h; ULONG
0x140010806  mov     r8, rdx
0x140010809  mov     dword ptr [rsp+88h+FileInformationClass], 1; ULONG
0x140010811  mov     r9d, 100001h
0x140010817  xor     edx, edx
0x140010819  mov     rsi, rcx
0x14001081c  call    VfsOpenFile
0x140010821  mov     ebx, eax
0x140010823  test    eax, eax
0x140010825  jns     short loc_140010841
0x140010827  xor     edx, edx
0x140010829  mov     dword ptr [rsp+88h+FileInformationClass], eax
0x14001082d  mov     r9, rdi
0x140010830  lea     r8, aVfsquerydirect_0; "VfsQueryDirectoryFileName() - Failed to"...
0x140010837  lea     ecx, [rdx+1]
0x14001083a  call    LogWrite
0x14001083f  jmp     short loc_1400108A4
0x140010841  mov     r9d, [rsp+88h+Length]; Length
0x140010849  mov     r8, rbp; FileInformation
0x14001084c  mov     rdx, [rsp+88h+FileObject]; FileObject
0x140010851  mov     rcx, rsi; Instance
0x140010854  mov     [rsp+88h+LengthReturned], 0; LengthReturned
0x14001085d  mov     [rsp+88h+RestartScan], 1; RestartScan
0x140010862  mov     [rsp+88h+FileName], r14; FileName
0x140010867  mov     [rsp+88h+ReturnSingleEntry], 1; ReturnSingleEntry
0x14001086c  mov     dword ptr [rsp+88h+FileInformationClass], 0Ch; FileInformationClass
0x140010874  call    cs:__imp_FltQueryDirectoryFile
0x14001087b  nop     dword ptr [rax+rax+00h]
0x140010880  mov     rcx, [rsp+88h+FileObject]; Object
0x140010885  mov     ebx, eax
0x140010887  call    cs:__imp_ObfDereferenceObject
0x14001088e  nop     dword ptr [rax+rax+00h]
0x140010893  mov     rcx, [rsp+88h+FileHandle]; FileHandle
0x140010898  call    cs:__imp_FltClose
0x14001089f  nop     dword ptr [rax+rax+00h]
0x1400108a4  mov     eax, ebx
0x1400108a6  add     rsp, 60h
0x1400108aa  pop     r14
0x1400108ac  pop     rdi
0x1400108ad  pop     rsi
0x1400108ae  pop     rbp
0x1400108af  pop     rbx
0x1400108b0  retn
```
