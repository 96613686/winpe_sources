# VfsUnMapFileName

- ea: `0x14000a7d0`
- end: `0x14000a8be`
- name: `VfsUnMapFileName`
- size: `238`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, int, FLT_FILE_NAME_OPTIONS NameOptions, char, PUNICODE_STRING DestinationString)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a3c0`

## callees

- `0x14000947c`
- `0x14000a7d0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000a85d`
- `ntoskrnl!ExAllocatePool2` at `0x14000a85d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000a88d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000a88d`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14000a802`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14000a802`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000a8a4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140014f4b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000a8a4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140014f4b`

## pseudocode

```c
NTSTATUS __fastcall VfsUnMapFileName(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        __int64 a3,
        FLT_FILE_NAME_OPTIONS NameOptions,
        char a5,
        PUNICODE_STRING DestinationString)
{
  bool v7; // di
  NTSTATUS result; // eax
  __int64 v9; // r8
  int v10; // ebx
  PFLT_FILE_NAME_INFORMATION v11; // rdi
  unsigned __int16 Length; // bx
  wchar_t *Pool2; // rax
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+30h] [rbp-18h] BYREF

  FileNameInformation = 0;
  v7 = (_BYTE)NameOptions == 3;
  result = FltGetFileNameInformationUnsafe(FileObject, Instance, NameOptions, &FileNameInformation);
  if ( result >= 0 )
  {
    if ( a5 || !a3 )
    {
      v11 = FileNameInformation;
      Length = FileNameInformation->Name.Length;
      Pool2 = (wchar_t *)ExAllocatePool2(256, Length, 1951614550);
      DestinationString->Buffer = Pool2;
      if ( Pool2 )
      {
        DestinationString->Length = 0;
        DestinationString->MaximumLength = Length;
        v10 = 0;
        RtlCopyUnicodeString(DestinationString, &v11->Name);
      }
      else
      {
        v10 = -1073741670;
      }
    }
    else
    {
      LOBYTE(v9) = v7;
      v10 = VfsUnMapName(a3, (__int64)&FileNameInformation->Name, v9, 0, DestinationString);
    }
    if ( FileNameInformation )
      FltReleaseFileNameInformation(FileNameInformation);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x14000a7d0  mov     [rsp+arg_0], rbx
0x14000a7d5  push    rdi
0x14000a7d6  sub     rsp, 40h
0x14000a7da  mov     eax, r9d
0x14000a7dd  mov     rbx, r8
0x14000a7e0  mov     r10, rdx
0x14000a7e3  mov     [rsp+48h+FileNameInformation], 0
0x14000a7ec  cmp     r9b, 3
0x14000a7f0  setz    dil
0x14000a7f4  lea     r9, [rsp+48h+FileNameInformation]; FileNameInformation
0x14000a7f9  mov     r8d, eax; NameOptions
0x14000a7fc  mov     rdx, rcx; Instance
0x14000a7ff  mov     rcx, r10; FileObject
0x14000a802  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14000a809  nop     dword ptr [rax+rax+00h]
0x14000a80e  test    eax, eax
0x14000a810  js      loc_14000A8B2
0x14000a816  cmp     [rsp+48h+arg_20], 0
0x14000a81b  jnz     short loc_14000A847
0x14000a81d  test    rbx, rbx
0x14000a820  jz      short loc_14000A847
0x14000a822  mov     rdx, [rsp+48h+FileNameInformation]
0x14000a827  add     rdx, 8; int
0x14000a82b  mov     rax, [rsp+48h+DestinationString]
0x14000a830  mov     [rsp+48h+var_28], rax; DestinationString
0x14000a835  xor     r9d, r9d; int
0x14000a838  mov     r8b, dil; int
0x14000a83b  mov     rcx, rbx; int
0x14000a83e  call    VfsUnMapName
0x14000a843  mov     ebx, eax
0x14000a845  jmp     short loc_14000A89A
0x14000a847  mov     rdi, [rsp+48h+FileNameInformation]
0x14000a84c  movzx   ebx, word ptr [rdi+8]
0x14000a850  mov     edx, ebx
0x14000a852  mov     ecx, 100h
0x14000a857  mov     r8d, 74534656h
0x14000a85d  call    cs:__imp_ExAllocatePool2
0x14000a864  nop     dword ptr [rax+rax+00h]
0x14000a869  mov     rcx, [rsp+48h+DestinationString]; DestinationString
0x14000a86e  mov     [rcx+8], rax
0x14000a872  test    rax, rax
0x14000a875  jnz     short loc_14000A87E
0x14000a877  mov     ebx, 0C000009Ah
0x14000a87c  jmp     short loc_14000A89A
0x14000a87e  xor     eax, eax
0x14000a880  mov     [rcx], ax
0x14000a883  mov     [rcx+2], bx
0x14000a887  xor     ebx, ebx
0x14000a889  lea     rdx, [rdi+8]; SourceString
0x14000a88d  call    cs:__imp_RtlCopyUnicodeString
0x14000a894  nop     dword ptr [rax+rax+00h]
0x14000a899  nop
0x14000a89a  mov     rcx, [rsp+48h+FileNameInformation]; FileNameInformation
0x14000a89f  test    rcx, rcx
0x14000a8a2  jz      short loc_14000A8B0
0x14000a8a4  call    cs:__imp_FltReleaseFileNameInformation
0x14000a8ab  nop     dword ptr [rax+rax+00h]
0x14000a8b0  mov     eax, ebx
0x14000a8b2  mov     rbx, [rsp+48h+arg_0]
0x14000a8b7  add     rsp, 40h
0x14000a8bb  pop     rdi
0x14000a8bc  retn
0x140014f39  push    rbp
0x140014f3b  sub     rsp, 30h
0x140014f3f  mov     rbp, rdx
0x140014f42  mov     rcx, [rbp+30h]; FileNameInformation
0x140014f46  test    rcx, rcx
0x140014f49  jz      short loc_140014F58
0x140014f4b  call    cs:__imp_FltReleaseFileNameInformation
0x140014f52  nop     dword ptr [rax+rax+00h]
0x140014f57  nop
0x140014f58  add     rsp, 30h
0x140014f5c  pop     rbp
0x140014f5d  retn
```
