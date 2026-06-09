# CfpRecurseDirectory

- ea: `0x180010c9c`
- end: `0x180011016`
- name: `CfpRecurseDirectory`
- size: `890`
- prototype: `__int64 __fastcall(int, int, int, int, int, HANDLE FileHandle)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800079c0`
- `0x180010c9c`

## callees

- `0x18000b080`
- `0x18000e610`
- `0x180010c9c`

## import_xrefs

- `ntdll!NtCreateFile` at `0x180010ed0`
- `ntdll!NtCreateFile` at `0x180010ed0`
- `ntdll!RtlIsPartialPlaceholder` at `0x180010d17`
- `ntdll!RtlIsPartialPlaceholder` at `0x180010d17`
- `ntdll!RtlEqualUnicodeString` at `0x180010e3d`
- `ntdll!RtlEqualUnicodeString` at `0x180010e56`
- `ntdll!RtlEqualUnicodeString` at `0x180010e3d`
- `ntdll!RtlEqualUnicodeString` at `0x180010e56`
- `ntdll!RtlNtStatusToDosError` at `0x180010ddc`
- `ntdll!RtlNtStatusToDosError` at `0x180010eea`
- `ntdll!RtlNtStatusToDosError` at `0x180010f49`
- `ntdll!RtlNtStatusToDosError` at `0x180010ddc`
- `ntdll!RtlNtStatusToDosError` at `0x180010eea`
- `ntdll!RtlNtStatusToDosError` at `0x180010f49`
- `ntdll!NtClose` at `0x180010f7c`
- `ntdll!NtClose` at `0x180010ffc`
- `ntdll!NtClose` at `0x180010f7c`
- `ntdll!NtClose` at `0x180010ffc`
- `ntdll!NtQueryDirectoryFile` at `0x180010dc6`
- `ntdll!NtQueryDirectoryFile` at `0x180010dc6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010d59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010fde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010d59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010fde`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010d6a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010d6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010fec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010fec`

## pseudocode

```c
__int64 __fastcall CfpRecurseDirectory(
        void *a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        __int64 FileHandle)
{
  void *v6; // r15
  signed int v7; // ebx
  unsigned int *FileInformation; // rdi
  BOOLEAN v9; // r14
  HANDLE ProcessHeap; // rax
  NTSTATUS v11; // eax
  signed int v12; // eax
  unsigned int *v13; // rsi
  NTSTATUS v14; // r15d
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  HANDLE v18; // rax
  UNICODE_STRING String1; // [rsp+68h] [rbp-61h] BYREF
  UNICODE_STRING String2; // [rsp+78h] [rbp-51h] BYREF
  UNICODE_STRING v22; // [rsp+88h] [rbp-41h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-21h] BYREF

  *(_QWORD *)&String2.Length = 262146;
  *(_QWORD *)&v22.Length = 393220;
  v6 = a1;
  FileHandle = -1;
  String2.Buffer = L".";
  v22.Buffer = L"..";
  v7 = 0;
  FileInformation = 0;
  if ( (a3 & 0x10) == 0 )
    goto LABEL_30;
  v9 = 1;
  if ( (unsigned __int8)RtlIsPartialPlaceholder(a3, a4) )
    CfUpdatePlaceholder((int)v6, 0, 0, 0, 0, 0, 16, 0, 0);
LABEL_4:
  while ( 1 )
  {
    IoStatusBlock = 0;
    if ( !FileInformation )
    {
      ProcessHeap = GetProcessHeap();
      FileInformation = (unsigned int *)HeapAlloc(ProcessHeap, 0, 0x400u);
      v7 = FileInformation == 0 ? 8 : 0;
      if ( !FileInformation )
        v7 |= 0x80070000;
      if ( v7 < 0 )
        break;
    }
    v11 = NtQueryDirectoryFile(
            v6,
            0,
            0,
            0,
            &IoStatusBlock,
            FileInformation,
            0x400u,
            FileFullDirectoryInformation,
            0,
            0,
            v9);
    v9 = 0;
    if ( v11 == -2147483642 )
      break;
    v12 = RtlNtStatusToDosError(v11);
    v7 = v12;
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
    if ( v7 < 0 )
      break;
    v13 = FileInformation;
    if ( FileInformation )
    {
      while ( 1 )
      {
        *(_QWORD *)&String1.Length = 0;
        String1.Buffer = (PWSTR)(v13 + 17);
        memset(&ObjectAttributes, 0, 44);
        String1.Length = *((_WORD *)v13 + 30);
        String1.MaximumLength = *((_WORD *)v13 + 30);
        if ( !RtlEqualUnicodeString(&String1, &String2, 0) && !RtlEqualUnicodeString(&String1, &v22, 0) )
        {
          ObjectAttributes.ObjectName = &String1;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = v6;
          ObjectAttributes.Attributes = 64;
          v14 = NtCreateFile(
                  (PHANDLE)&FileHandle,
                  (v13[14] & 0x10 | 0x1101800) >> 4,
                  &ObjectAttributes,
                  &IoStatusBlock,
                  0,
                  0x80u,
                  7u,
                  1u,
                  0x200020u,
                  0,
                  0);
          v15 = RtlNtStatusToDosError((a5 & 1) != 0 ? v14 : 0);
          v7 = v15;
          if ( v15 > 0 )
            v7 = (unsigned __int16)v15 | 0x80070000;
          if ( v7 < 0 )
          {
            v6 = a1;
            goto LABEL_30;
          }
          if ( v14 < 0 )
          {
            v6 = a1;
          }
          else
          {
            CfpRecurseDirectory(FileHandle, 65920, v13[14], v13[16], a5 & 0xFFFFFFFD, CfpProcessUnregistration);
            v16 = RtlNtStatusToDosError((a5 & 1) != 0 ? v14 : 0);
            v7 = v16;
            if ( v16 > 0 )
              v7 = (unsigned __int16)v16 | 0x80070000;
            v6 = a1;
            if ( v7 < 0 )
              goto LABEL_30;
          }
        }
        if ( FileHandle != -1 )
        {
          NtClose((HANDLE)FileHandle);
          FileHandle = -1;
        }
        if ( *v13 )
        {
          v13 = (unsigned int *)((char *)v13 + *v13);
          if ( v13 )
            continue;
        }
        goto LABEL_4;
      }
    }
  }
LABEL_30:
  if ( (a5 & 2) == 0 && (v7 >= 0 || (a5 & 1) == 0) )
  {
    v17 = CfpProcessUnregistration(v6);
    if ( v7 >= 0 )
      v7 = v17;
  }
  if ( FileInformation )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, FileInformation);
  }
  if ( FileHandle != -1 )
    NtClose((HANDLE)FileHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180010c9c  mov     rax, rsp
0x180010c9f  mov     [rax+20h], r9d
0x180010ca3  mov     [rax+18h], r8d
0x180010ca7  mov     [rax+8], rcx
0x180010cab  push    rbp
0x180010cac  push    rbx
0x180010cad  push    rsi
0x180010cae  push    rdi
0x180010caf  push    r12
0x180010cb1  push    r14
0x180010cb3  push    r15
0x180010cb5  lea     rbp, [rax-47h]
0x180010cb9  sub     rsp, 0D0h
0x180010cc0  xor     r12d, r12d
0x180010cc3  mov     qword ptr [rbp+3Fh+String2.Length], 40002h
0x180010ccb  mov     qword ptr [rbp+3Fh+var_80.Length], 60004h
0x180010cd3  mov     r15, rcx
0x180010cd6  mov     [rbp+3Fh+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180010cde  lea     rcx, asc_180020960; "."
0x180010ce5  mov     [rbp+3Fh+String2.Buffer], rcx
0x180010ce9  lea     rcx, asc_180020958; ".."
0x180010cf0  mov     [rbp+3Fh+var_80.Buffer], rcx
0x180010cf4  mov     r10d, r9d
0x180010cf7  mov     eax, r8d
0x180010cfa  mov     esi, 2
0x180010cff  mov     ebx, r12d
0x180010d02  mov     edi, r12d
0x180010d05  test    r8b, 10h
0x180010d09  jz      loc_180010FB4
0x180010d0f  mov     edx, r9d
0x180010d12  mov     ecx, eax
0x180010d14  mov     r14b, 1
0x180010d17  call    cs:__imp_RtlIsPartialPlaceholder
0x180010d1d  test    al, al
0x180010d1f  jz      short loc_180010D4D
0x180010d21  mov     qword ptr [rsp+100h+ReturnSingleEntry], r12; __int64
0x180010d26  xor     r9d, r9d; int
0x180010d29  mov     qword ptr [rsp+100h+FileInformationClass], r12; __int64
0x180010d2e  xor     r8d, r8d; int
0x180010d31  mov     [rsp+100h+Length], 10h; int
0x180010d39  xor     edx, edx; int
0x180010d3b  mov     dword ptr [rsp+100h+FileInformation], r12d; int
0x180010d40  mov     rcx, r15; int
0x180010d43  mov     [rsp+100h+IoStatusBlock], r12; Src
0x180010d48  call    CfUpdatePlaceholder
0x180010d4d  xorps   xmm0, xmm0
0x180010d50  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x180010d54  test    rdi, rdi
0x180010d57  jnz     short loc_180010D92
0x180010d59  call    cs:__imp_GetProcessHeap
0x180010d5f  xor     edx, edx; dwFlags
0x180010d61  mov     r8d, 400h; dwBytes
0x180010d67  mov     rcx, rax; hHeap
0x180010d6a  call    cs:__imp_HeapAlloc
0x180010d70  mov     rdi, rax
0x180010d73  neg     rax
0x180010d76  sbb     ebx, ebx
0x180010d78  not     ebx
0x180010d7a  and     ebx, 8
0x180010d7d  mov     eax, ebx
0x180010d7f  or      eax, 80070000h
0x180010d84  test    rdi, rdi
0x180010d87  cmovz   ebx, eax
0x180010d8a  test    ebx, ebx
0x180010d8c  js      loc_180010FAD
0x180010d92  mov     [rsp+50h], r14b; RestartScan
0x180010d97  lea     rax, [rbp+3Fh+var_70]
0x180010d9b  mov     [rsp+100h+FileName], r12; FileName
0x180010da0  xor     r9d, r9d; ApcContext
0x180010da3  mov     [rsp+100h+ReturnSingleEntry], r12b; ReturnSingleEntry
0x180010da8  xor     r8d, r8d; ApcRoutine
0x180010dab  mov     [rsp+100h+FileInformationClass], esi; FileInformationClass
0x180010daf  xor     edx, edx; Event
0x180010db1  mov     [rsp+100h+Length], 400h; Length
0x180010db9  mov     rcx, r15; FileHandle
0x180010dbc  mov     [rsp+100h+FileInformation], rdi; FileInformation
0x180010dc1  mov     [rsp+100h+IoStatusBlock], rax; IoStatusBlock
0x180010dc6  call    cs:__imp_NtQueryDirectoryFile
0x180010dcc  mov     r14b, r12b
0x180010dcf  cmp     eax, 80000006h
0x180010dd4  jz      loc_180010FAD
0x180010dda  mov     ecx, eax; Status
0x180010ddc  call    cs:__imp_RtlNtStatusToDosError
0x180010de2  mov     ebx, eax
0x180010de4  test    eax, eax
0x180010de6  jle     short loc_180010DF1
0x180010de8  movzx   ebx, ax
0x180010deb  or      ebx, 80070000h
0x180010df1  test    ebx, ebx
0x180010df3  js      loc_180010FAD
0x180010df9  mov     rsi, rdi
0x180010dfc  test    rdi, rdi
0x180010dff  jz      loc_180010F9A
0x180010e05  mov     qword ptr [rbp+3Fh+String1.Length], r12
0x180010e09  lea     rdx, [rbp+3Fh+String2]; String2
0x180010e0d  xor     eax, eax
0x180010e0f  lea     rcx, [rbp+3Fh+String1]; String1
0x180010e13  xorps   xmm0, xmm0
0x180010e16  lea     rax, [rsi+44h]
0x180010e1a  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x180010e1e  mov     [rbp+3Fh+String1.Buffer], rax
0x180010e22  xor     r8d, r8d; CaseInsensitive
0x180010e25  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x180010e29  movups  xmmword ptr [rbp+3Fh+ObjectAttributes+1Ch], xmm0
0x180010e2d  movzx   eax, word ptr [rsi+3Ch]
0x180010e31  mov     [rbp+3Fh+String1.Length], ax
0x180010e35  movzx   eax, word ptr [rsi+3Ch]
0x180010e39  mov     [rbp+3Fh+String1.MaximumLength], ax
0x180010e3d  call    cs:__imp_RtlEqualUnicodeString
0x180010e43  test    al, al
0x180010e45  jnz     loc_180010F72
0x180010e4b  xor     r8d, r8d; CaseInsensitive
0x180010e4e  lea     rdx, [rbp+3Fh+var_80]; String2
0x180010e52  lea     rcx, [rbp+3Fh+String1]; String1
0x180010e56  call    cs:__imp_RtlEqualUnicodeString
0x180010e5c  test    al, al
0x180010e5e  jnz     loc_180010F72
0x180010e64  mov     [rsp+50h], r12d; EaLength
0x180010e69  lea     rax, [rbp+3Fh+String1]
0x180010e6d  mov     [rsp+100h+FileName], r12; EaBuffer
0x180010e72  lea     r9, [rbp+3Fh+var_70]; IoStatusBlock
0x180010e76  mov     dword ptr [rsp+100h+ReturnSingleEntry], 200020h; CreateOptions
0x180010e7e  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x180010e82  mov     [rsp+100h+FileInformationClass], 1; CreateDisposition
0x180010e8a  lea     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x180010e8e  xorps   xmm0, xmm0
0x180010e91  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x180010e95  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180010e9a  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x180010ea1  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r15
0x180010ea5  mov     [rbp+3Fh+ObjectAttributes.Attributes], 40h ; '@'
0x180010eac  mov     edx, [rsi+38h]
0x180010eaf  and     edx, 10h
0x180010eb2  mov     [rsp+100h+Length], 7; ShareAccess
0x180010eba  or      edx, 1101800h
0x180010ec0  mov     dword ptr [rsp+100h+FileInformation], 80h; FileAttributes
0x180010ec8  shr     edx, 4; DesiredAccess
0x180010ecb  mov     [rsp+100h+IoStatusBlock], r12; AllocationSize
0x180010ed0  call    cs:__imp_NtCreateFile
0x180010ed6  mov     r12d, [rbp+3Fh+arg_20]
0x180010eda  mov     r15d, eax
0x180010edd  and     r12d, 1
0x180010ee1  mov     ecx, r12d
0x180010ee4  neg     ecx
0x180010ee6  sbb     ecx, ecx
0x180010ee8  and     ecx, eax; Status
0x180010eea  call    cs:__imp_RtlNtStatusToDosError
0x180010ef0  mov     ebx, eax
0x180010ef2  test    eax, eax
0x180010ef4  jle     short loc_180010EFF
0x180010ef6  movzx   ebx, ax
0x180010ef9  or      ebx, 80070000h
0x180010eff  test    ebx, ebx
0x180010f01  js      loc_180010FA4
0x180010f07  test    r15d, r15d
0x180010f0a  js      short loc_180010F6B
0x180010f0c  mov     eax, [rbp+3Fh+arg_20]
0x180010f0f  lea     rcx, CfpProcessUnregistration
0x180010f16  mov     r9d, [rsi+40h]; int
0x180010f1a  and     eax, 0FFFFFFFDh
0x180010f1d  mov     r8d, [rsi+38h]; int
0x180010f21  mov     edx, 10180h; int
0x180010f26  mov     qword ptr [rsp+100h+Length], 0
0x180010f2f  mov     [rsp+100h+FileInformation], rcx; FileHandle
0x180010f34  mov     rcx, [rbp+3Fh+FileHandle]; int
0x180010f38  mov     dword ptr [rsp+100h+IoStatusBlock], eax; int
0x180010f3c  call    CfpRecurseDirectory
0x180010f41  neg     r12d
0x180010f44  sbb     ecx, ecx
0x180010f46  and     ecx, r15d; Status
0x180010f49  call    cs:__imp_RtlNtStatusToDosError
0x180010f4f  xor     r12d, r12d
0x180010f52  mov     ebx, eax
0x180010f54  test    eax, eax
0x180010f56  jle     short loc_180010F61
0x180010f58  movzx   ebx, ax
0x180010f5b  or      ebx, 80070000h
0x180010f61  mov     r15, [rbp+3Fh+arg_0]
0x180010f65  test    ebx, ebx
0x180010f67  js      short loc_180010FA8
0x180010f69  jmp     short loc_180010F72
0x180010f6b  mov     r15, [rbp+3Fh+arg_0]
0x180010f6f  xor     r12d, r12d
0x180010f72  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x180010f76  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180010f7a  jz      short loc_180010F8A
0x180010f7c  call    cs:__imp_NtClose
0x180010f82  mov     [rbp+3Fh+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180010f8a  cmp     [rsi], r12d
0x180010f8d  jz      short loc_180010F9A
0x180010f8f  mov     eax, [rsi]
0x180010f91  add     rsi, rax
0x180010f94  jnz     loc_180010E05
0x180010f9a  mov     esi, 2
0x180010f9f  jmp     loc_180010D4D
0x180010fa4  mov     r15, [rbp+3Fh+arg_0]
0x180010fa8  mov     esi, 2
0x180010fad  mov     eax, [rbp+3Fh+arg_10]
0x180010fb0  mov     r10d, [rbp+3Fh+arg_18]
0x180010fb4  test    byte ptr [rbp+3Fh+arg_20], sil
0x180010fb8  jnz     short loc_180010FD9
0x180010fba  test    ebx, ebx
0x180010fbc  jns     short loc_180010FC4
0x180010fbe  test    byte ptr [rbp+3Fh+arg_20], 1
0x180010fc2  jnz     short loc_180010FD9
0x180010fc4  xor     r9d, r9d
0x180010fc7  mov     r8d, r10d
0x180010fca  mov     edx, eax
0x180010fcc  mov     rcx, r15; hFile
0x180010fcf  call    CfpProcessUnregistration
0x180010fd4  test    ebx, ebx
0x180010fd6  cmovns  ebx, eax
0x180010fd9  test    rdi, rdi
0x180010fdc  jz      short loc_180010FF2
0x180010fde  call    cs:__imp_GetProcessHeap
0x180010fe4  mov     r8, rdi; lpMem
0x180010fe7  xor     edx, edx; dwFlags
0x180010fe9  mov     rcx, rax; hHeap
0x180010fec  call    cs:__imp_HeapFree
0x180010ff2  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x180010ff6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180010ffa  jz      short loc_180011002
0x180010ffc  call    cs:__imp_NtClose
0x180011002  mov     eax, ebx
0x180011004  add     rsp, 0D0h
0x18001100b  pop     r15
0x18001100d  pop     r14
0x18001100f  pop     r12
0x180011011  pop     rdi
0x180011012  pop     rsi
0x180011013  pop     rbx
0x180011014  pop     rbp
0x180011015  retn
```
