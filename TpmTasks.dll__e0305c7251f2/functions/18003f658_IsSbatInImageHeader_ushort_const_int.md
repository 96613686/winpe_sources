# IsSbatInImageHeader(ushort const *,int *)

- ea: `0x18003f658`
- end: `0x18003f852`
- name: `?IsSbatInImageHeader@@YAJPEBGPEAH@Z`
- size: `506`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18003f984`

## callees

- `0x18002b4c0`
- `0x18003c0b8`
- `0x18003f658`
- `0x18003f858`
- `0x18003f960`

## import_xrefs

- `ntdll!RtlImageNtHeaderEx` at `0x18003f7ec`
- `ntdll!RtlImageNtHeaderEx` at `0x18003f7ec`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003f78b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003f78b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f6b4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f6b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f6cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f6d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f74d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f755`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f79f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f7a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f6cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f6d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f74d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f755`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f79f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f7a7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18003f731`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18003f731`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18003f7d3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18003f830`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18003f7d3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18003f830`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18003f704`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18003f704`

## string_xrefs

- `0x18003f680`: `Checking IsSbatInImageHeader for efiFullPath %s\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IsSbatInImageHeader(LPCWSTR lpFileName, int *a2)
{
  HANDLE FileW; // rbx
  unsigned int v5; // ebx
  HANDLE FileMappingW; // rax
  void *v7; // rdi
  unsigned int LastError; // eax
  DWORD v9; // eax
  DWORD LowPart; // ebx
  NTSTATUS v11; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-40h]
  PIMAGE_NT_HEADERS NtHeader; // [rsp+40h] [rbp-20h] BYREF
  HANDLE v15; // [rsp+48h] [rbp-18h] BYREF
  void *v16; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  HANDLE v18; // [rsp+90h] [rbp+30h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+98h] [rbp+38h] BYREF

  v15 = 0;
  v16 = 0;
  SBServicingLogMessage((wchar_t *)L"Checking IsSbatInImageHeader for efiFullPath %s\n", lpFileName);
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v18 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
    v15 = FileMappingW;
    if ( (((unsigned __int64)FileMappingW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0
      || (v7 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0), (v16 = v7) == 0) )
    {
      if ( (int)GetLastError() > 0 )
      {
        LastError = (unsigned __int16)GetLastError() | 0xC0070000;
        goto LABEL_9;
      }
LABEL_7:
      LastError = GetLastError();
LABEL_9:
      v5 = LastError;
      goto LABEL_10;
    }
    NtHeader = 0;
    FileSize.QuadPart = 0;
    if ( GetFileSizeEx(FileW, &FileSize) )
    {
      LowPart = FileSize.LowPart;
      if ( FileSize.QuadPart > 0xFFFFFFFFLL )
      {
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
        UnmapViewOfFile(v7);
        v5 = -1073739516;
        goto LABEL_22;
      }
      v11 = RtlImageNtHeaderEx(0, v7, FileSize.LowPart, &NtHeader);
      if ( v11 >= 0 )
        v9 = IsSbatInImageHeaderHelper(NtHeader, LowPart, (unsigned __int64)v7, a2);
      else
        v9 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x9A,
               (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\bootorder.cpp",
               (const char *)(unsigned int)v11,
               dwCreationDisposition);
    }
    else
    {
      if ( (int)GetLastError() > 0 )
      {
        v5 = (unsigned __int16)GetLastError() | 0xC0070000;
LABEL_21:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
        UnmapViewOfFile(v7);
        goto LABEL_22;
      }
      v9 = GetLastError();
    }
    v5 = v9;
    goto LABEL_21;
  }
  if ( (int)GetLastError() <= 0 )
    goto LABEL_7;
  v5 = (unsigned __int16)GetLastError() | 0xC0070000;
LABEL_10:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
LABEL_22:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v15);
  return v5;
}

```

## disassembly

```asm
0x18003f658  mov     [rsp-18h+arg_0], rbx
0x18003f65d  push    rbp
0x18003f65e  push    rsi
0x18003f65f  push    rdi
0x18003f660  mov     rbp, rsp
0x18003f663  sub     rsp, 60h
0x18003f667  mov     rsi, rdx
0x18003f66a  mov     rbx, rcx
0x18003f66d  mov     [rbp+var_18], 0
0x18003f675  mov     [rbp+var_10], 0
0x18003f67d  mov     rdx, rcx
0x18003f680  lea     rcx, aCheckingIssbat; "Checking IsSbatInImageHeader for efiFul"...
0x18003f687  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003f68c  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x18003f695  mov     [rsp+60h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003f69d  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x18003f6a5  xor     r9d, r9d; lpSecurityAttributes
0x18003f6a8  mov     edx, 80000000h; dwDesiredAccess
0x18003f6ad  lea     r8d, [r9+1]; dwShareMode
0x18003f6b1  mov     rcx, rbx; lpFileName
0x18003f6b4  call    cs:__imp_CreateFileW
0x18003f6ba  mov     rbx, rax
0x18003f6bd  mov     [rbp+arg_10], rax
0x18003f6c1  inc     rax
0x18003f6c4  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003f6ca  jnz     short loc_18003F6E7
0x18003f6cc  call    cs:__imp_GetLastError
0x18003f6d2  test    eax, eax
0x18003f6d4  jle     short loc_18003F74D
0x18003f6d6  call    cs:__imp_GetLastError
0x18003f6dc  movzx   ebx, ax
0x18003f6df  or      ebx, 0C0070000h
0x18003f6e5  jmp     short loc_18003F765
0x18003f6e7  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], 0; lpName
0x18003f6f0  mov     [rsp+60h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18003f6f8  xor     r9d, r9d; dwMaximumSizeHigh
0x18003f6fb  xor     edx, edx; lpFileMappingAttributes
0x18003f6fd  lea     r8d, [r9+2]; flProtect
0x18003f701  mov     rcx, rbx; hFile
0x18003f704  call    cs:__imp_CreateFileMappingW
0x18003f70a  mov     [rbp+var_18], rax
0x18003f70e  lea     rcx, [rax+1]
0x18003f712  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18003f719  jz      short loc_18003F743
0x18003f71b  mov     qword ptr [rsp+60h+dwCreationDisposition], 0; int
0x18003f724  xor     r9d, r9d; dwFileOffsetLow
0x18003f727  xor     r8d, r8d; dwFileOffsetHigh
0x18003f72a  lea     edx, [r9+4]; dwDesiredAccess
0x18003f72e  mov     rcx, rax; hFileMappingObject
0x18003f731  call    cs:__imp_MapViewOfFile
0x18003f737  mov     rdi, rax
0x18003f73a  mov     [rbp+var_10], rax
0x18003f73e  test    rax, rax
0x18003f741  jnz     short loc_18003F774
0x18003f743  call    cs:__imp_GetLastError
0x18003f749  test    eax, eax
0x18003f74b  jg      short loc_18003F755
0x18003f74d  call    cs:__imp_GetLastError
0x18003f753  jmp     short loc_18003F763
0x18003f755  call    cs:__imp_GetLastError
0x18003f75b  movzx   eax, ax
0x18003f75e  or      eax, 0C0070000h
0x18003f763  mov     ebx, eax
0x18003f765  lea     rcx, [rbp+arg_10]
0x18003f769  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003f76e  nop
0x18003f76f  jmp     loc_18003F837
0x18003f774  mov     [rbp+NtHeader], 0
0x18003f77c  mov     qword ptr [rbp+FileSize], 0
0x18003f784  lea     rdx, [rbp+FileSize]; lpFileSize
0x18003f788  mov     rcx, rbx; hFile
0x18003f78b  call    cs:__imp_GetFileSizeEx
0x18003f791  test    eax, eax
0x18003f793  jnz     short loc_18003F7B8
0x18003f795  call    cs:__imp_GetLastError
0x18003f79b  test    eax, eax
0x18003f79d  jg      short loc_18003F7A7
0x18003f79f  call    cs:__imp_GetLastError
0x18003f7a5  jmp     short loc_18003F821
0x18003f7a7  call    cs:__imp_GetLastError
0x18003f7ad  movzx   ebx, ax
0x18003f7b0  or      ebx, 0C0070000h
0x18003f7b6  jmp     short loc_18003F823
0x18003f7b8  mov     eax, 0FFFFFFFFh
0x18003f7bd  mov     rbx, qword ptr [rbp+FileSize]
0x18003f7c1  cmp     rbx, rax
0x18003f7c4  jle     short loc_18003F7E0
0x18003f7c6  lea     rcx, [rbp+arg_10]
0x18003f7ca  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003f7cf  nop
0x18003f7d0  mov     rcx, rdi; lpBaseAddress
0x18003f7d3  call    cs:__imp_UnmapViewOfFile
0x18003f7d9  mov     ebx, 0C0000904h
0x18003f7de  jmp     short loc_18003F837
0x18003f7e0  mov     r8d, ebx; Size
0x18003f7e3  lea     r9, [rbp+NtHeader]; NtHeader
0x18003f7e7  mov     rdx, rdi; BaseAddress
0x18003f7ea  xor     ecx, ecx; Flags
0x18003f7ec  call    cs:__imp_RtlImageNtHeaderEx
0x18003f7f2  test    eax, eax
0x18003f7f4  jns     short loc_18003F810
0x18003f7f6  mov     rcx, [rbp+18h]; this
0x18003f7fa  mov     r9d, eax; char *
0x18003f7fd  lea     r8, aOnecoreBaseSec_4; "onecore\\base\\secureboot\\servicing\\l"...
0x18003f804  mov     edx, 9Ah; void *
0x18003f809  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18003f80e  jmp     short loc_18003F821
0x18003f810  mov     r9, rsi; int *
0x18003f813  mov     r8, rdi; unsigned __int64
0x18003f816  mov     edx, ebx; unsigned int
0x18003f818  mov     rcx, [rbp+NtHeader]; struct _IMAGE_NT_HEADERS64 *
0x18003f81c  call    ?IsSbatInImageHeaderHelper@@YAJPEAU_IMAGE_NT_HEADERS64@@K_KPEAH@Z; IsSbatInImageHeaderHelper(_IMAGE_NT_HEADERS64 *,ulong,unsigned __int64,int *)
0x18003f821  mov     ebx, eax
0x18003f823  lea     rcx, [rbp+arg_10]
0x18003f827  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003f82c  nop
0x18003f82d  mov     rcx, rdi; lpBaseAddress
0x18003f830  call    cs:__imp_UnmapViewOfFile
0x18003f836  nop
0x18003f837  lea     rcx, [rbp+var_18]
0x18003f83b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003f840  mov     eax, ebx
0x18003f842  mov     rbx, [rsp+60h+arg_0]
0x18003f84a  add     rsp, 60h
0x18003f84e  pop     rdi
0x18003f84f  pop     rsi
0x18003f850  pop     rbp
0x18003f851  retn
```
