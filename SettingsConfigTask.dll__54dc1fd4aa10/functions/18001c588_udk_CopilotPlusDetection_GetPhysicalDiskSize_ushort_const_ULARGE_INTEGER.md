# udk::CopilotPlusDetection::_GetPhysicalDiskSize(ushort const *,_ULARGE_INTEGER *)

- ea: `0x18001c588`
- end: `0x18001c8aa`
- name: `?_GetPhysicalDiskSize@CopilotPlusDetection@udk@@YAJPEBGPEAT_ULARGE_INTEGER@@@Z`
- size: `802`
- prototype: `signed int __fastcall(LPCWSTR lpszFileName, unsigned __int16 *, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x1800194b4`

## callees

- `0x1800021d0`
- `0x1800027e0`
- `0x180002c18`
- `0x18000970c`
- `0x18000972c`
- `0x1800128fc`
- `0x18001be8c`
- `0x18001c588`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c829`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c871`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c829`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c871`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c79c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c79c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c788`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c81b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c863`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c788`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c81b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c75c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c75c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001c649`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001c649`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18001c600`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18001c67f`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18001c600`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18001c67f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001c743`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001c743`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18001c69f`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18001c69f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001c7f7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001c7f7`

## pseudocode

```c
signed int __fastcall udk::CopilotPlusDetection::_GetPhysicalDiskSize(
        LPCWSTR lpszFileName,
        unsigned __int16 *a2,
        union _ULARGE_INTEGER *a3)
{
  const char *v5; // r9
  __int64 v6; // rdx
  signed int result; // eax
  int v8; // eax
  unsigned int v9; // ebx
  unsigned __int64 v10; // rcx
  HANDLE FileW; // rbx
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  unsigned int *v14; // rdi
  const char *v15; // r9
  HANDLE v16; // rax
  unsigned __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rax
  HANDLE v20; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned[6]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR szVolumeName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR Buffer[264]; // [rsp+480h] [rbp+380h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6B8h] [rbp+5B8h]

  *(_QWORD *)a2 = 0;
  memset_0(szVolumeName, 0, 0x208u);
  memset_0(szVolumePathName, 0, 0x208u);
  if ( lpszFileName )
  {
    if ( !GetVolumePathNameW(lpszFileName, szVolumePathName, 0x104u) )
    {
      v6 = 413;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v6,
               (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
               v5);
    }
  }
  else
  {
    memset_0(Buffer, 0, 0x208u);
    if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    if ( !GetVolumePathNameW(Buffer, szVolumePathName, 0x104u) )
    {
      v6 = 423;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v6,
               (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
               v5);
    }
  }
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    v6 = 426;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
             v5);
  }
  v23 = 0;
  v8 = StringCchLengthW(szVolumeName, 0x104u, &v23);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
      (const char *)(unsigned int)v8,
      dwCreationDisposition);
    return v9;
  }
  if ( v23 && *((_WORD *)&BytesReturned[5] + v23 + 1) == 92 )
  {
    v10 = 2 * v23 - 2;
    if ( v10 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v10) = 0;
  }
  FileW = CreateFileW(szVolumeName, 0, 1u, 0, 3u, 0x2000000u, 0);
  v23 = (unsigned __int64)FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_27;
  }
  BytesReturned[0] = 0;
  ProcessHeap = GetProcessHeap();
  v14 = (unsigned int *)HeapAlloc(ProcessHeap, 0, 0x48C0u);
  if ( !v14 )
  {
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
      (const char *)0x8007000ELL,
      dwCreationDispositiona);
LABEL_27:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
    return v9;
  }
  if ( !DeviceIoControl(FileW, 0x70050u, 0, 0, v14, 0x48C0u, BytesReturned, 0) )
  {
    v9 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x1C4,
           (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
           v15);
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v14);
    goto LABEL_27;
  }
  v17 = 0;
  if ( v14[1] )
  {
    v18 = *(_QWORD *)a2;
    do
    {
      v19 = 9 * v17++;
      v18 += *(_QWORD *)&v14[4 * v19 + 16];
      *(_QWORD *)a2 = v18;
    }
    while ( v17 < v14[1] );
  }
  v20 = GetProcessHeap();
  HeapFree(v20, 0, v14);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
  return 0;
}

```

## disassembly

```asm
0x18001c588  mov     [rsp-8+arg_10], rbx
0x18001c58d  mov     [rsp-8+arg_18], rsi
0x18001c592  push    rbp
0x18001c593  push    rdi
0x18001c594  push    r15
0x18001c596  lea     rbp, [rsp-5A0h]
0x18001c59e  sub     rsp, 6A0h
0x18001c5a5  mov     rax, cs:__security_cookie
0x18001c5ac  xor     rax, rsp
0x18001c5af  mov     [rbp+5B0h+var_20], rax
0x18001c5b6  mov     rsi, rdx
0x18001c5b9  mov     qword ptr [rdx], 0
0x18001c5c0  mov     rdi, rcx
0x18001c5c3  mov     r15d, 208h
0x18001c5c9  mov     r8d, r15d; Size
0x18001c5cc  lea     rcx, [rsp+6B0h+szVolumeName]; void *
0x18001c5d1  xor     edx, edx; Val
0x18001c5d3  call    memset_0
0x18001c5d8  mov     r8d, r15d; Size
0x18001c5db  lea     rcx, [rbp+5B0h+szVolumePathName]; void *
0x18001c5e2  xor     edx, edx; Val
0x18001c5e4  call    memset_0
0x18001c5e9  test    rdi, rdi
0x18001c5ec  jz      short loc_18001C62A
0x18001c5ee  mov     ebx, 104h
0x18001c5f3  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x18001c5fa  mov     r8d, ebx; cchBufferLength
0x18001c5fd  mov     rcx, rdi; lpszFileName
0x18001c600  call    cs:__imp_GetVolumePathNameW
0x18001c606  test    eax, eax
0x18001c608  jnz     loc_18001C690
0x18001c60e  lea     edx, [r15-6Bh]; void *
0x18001c612  mov     rcx, [rbp+5B8h]; this
0x18001c619  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x18001c620  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001c625  jmp     loc_18001C883
0x18001c62a  mov     r8, r15; Size
0x18001c62d  lea     rcx, [rbp+5B0h+Buffer]; void *
0x18001c634  xor     edx, edx; Val
0x18001c636  call    memset_0
0x18001c63b  mov     ebx, 104h
0x18001c640  lea     rcx, [rbp+5B0h+Buffer]; lpBuffer
0x18001c647  mov     edx, ebx; uSize
0x18001c649  call    cs:__imp_GetSystemDirectoryW
0x18001c64f  test    eax, eax
0x18001c651  jnz     short loc_18001C66E
0x18001c653  call    cs:__imp_GetLastError
0x18001c659  test    eax, eax
0x18001c65b  jle     loc_18001C883
0x18001c661  movzx   eax, ax
0x18001c664  or      eax, 80070000h
0x18001c669  jmp     loc_18001C883
0x18001c66e  mov     r8d, ebx; cchBufferLength
0x18001c671  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x18001c678  lea     rcx, [rbp+5B0h+Buffer]; lpszFileName
0x18001c67f  call    cs:__imp_GetVolumePathNameW
0x18001c685  test    eax, eax
0x18001c687  jnz     short loc_18001C690
0x18001c689  mov     edx, 1A7h
0x18001c68e  jmp     short loc_18001C612
0x18001c690  mov     r8d, ebx; cchBufferLength
0x18001c693  lea     rdx, [rsp+6B0h+szVolumeName]; lpszVolumeName
0x18001c698  lea     rcx, [rbp+5B0h+szVolumePathName]; lpszVolumeMountPoint
0x18001c69f  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18001c6a5  test    eax, eax
0x18001c6a7  jnz     short loc_18001C6B3
0x18001c6a9  mov     edx, 1AAh
0x18001c6ae  jmp     loc_18001C612
0x18001c6b3  lea     r8, [rsp+6B0h+var_670]; unsigned __int64 *
0x18001c6b8  mov     [rsp+6B0h+var_670], 0
0x18001c6c1  mov     rdx, rbx; unsigned __int64
0x18001c6c4  lea     rcx, [rsp+6B0h+szVolumeName]; unsigned __int16 *
0x18001c6c9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001c6ce  mov     ebx, eax
0x18001c6d0  test    eax, eax
0x18001c6d2  jns     short loc_18001C6F6
0x18001c6d4  mov     rcx, [rbp+5B8h]; this
0x18001c6db  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x18001c6e2  mov     r9d, eax; char *
0x18001c6e5  mov     edx, 1AEh; void *
0x18001c6ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c6ef  mov     eax, ebx
0x18001c6f1  jmp     loc_18001C883
0x18001c6f6  mov     rax, [rsp+6B0h+var_670]
0x18001c6fb  test    rax, rax
0x18001c6fe  jz      short loc_18001C71C
0x18001c700  cmp     [rsp+rax*2+6B0h+var_652], 5Ch ; '\'
0x18001c706  jnz     short loc_18001C71C
0x18001c708  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18001c710  cmp     rcx, r15
0x18001c713  jnb     short loc_18001C77A
0x18001c715  xor     eax, eax
0x18001c717  mov     [rsp+rcx+6B0h+szVolumeName], ax
0x18001c71c  xor     r9d, r9d; lpSecurityAttributes
0x18001c71f  mov     [rsp+6B0h+hTemplateFile], 0; hTemplateFile
0x18001c728  mov     [rsp+6B0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18001c730  lea     rcx, [rsp+6B0h+szVolumeName]; lpFileName
0x18001c735  xor     edx, edx; dwDesiredAccess
0x18001c737  mov     [rsp+6B0h+dwCreationDisposition], 3; int
0x18001c73f  lea     r8d, [r9+1]; dwShareMode
0x18001c743  call    cs:__imp_CreateFileW
0x18001c749  mov     rbx, rax
0x18001c74c  mov     [rsp+6B0h+var_670], rax
0x18001c751  inc     rax
0x18001c754  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001c75a  jnz     short loc_18001C780
0x18001c75c  call    cs:__imp_GetLastError
0x18001c762  mov     ebx, eax
0x18001c764  test    eax, eax
0x18001c766  jle     loc_18001C82F
0x18001c76c  movzx   ebx, ax
0x18001c76f  or      ebx, 80070000h
0x18001c775  jmp     loc_18001C82F
0x18001c77a  call    __report_rangecheckfailure
0x18001c780  mov     [rsp+6B0h+BytesReturned], 0
0x18001c788  call    cs:__imp_GetProcessHeap
0x18001c78e  mov     r15d, 48C0h
0x18001c794  xor     edx, edx; dwFlags
0x18001c796  mov     rcx, rax; hHeap
0x18001c799  mov     r8d, r15d; dwBytes
0x18001c79c  call    cs:__imp_HeapAlloc
0x18001c7a2  mov     rdi, rax
0x18001c7a5  test    rax, rax
0x18001c7a8  jnz     short loc_18001C7CC
0x18001c7aa  mov     rcx, [rbp+5B8h]; this
0x18001c7b1  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x18001c7b8  mov     ebx, 8007000Eh
0x18001c7bd  mov     edx, 1BEh; void *
0x18001c7c2  mov     r9d, ebx; char *
0x18001c7c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c7ca  jmp     short loc_18001C82F
0x18001c7cc  mov     [rsp+6B0h+lpOverlapped], 0; lpOverlapped
0x18001c7d5  lea     rax, [rsp+6B0h+BytesReturned]
0x18001c7da  mov     [rsp+6B0h+hTemplateFile], rax; lpBytesReturned
0x18001c7df  xor     r9d, r9d; nInBufferSize
0x18001c7e2  mov     [rsp+6B0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x18001c7e7  xor     r8d, r8d; lpInBuffer
0x18001c7ea  mov     edx, 70050h; dwIoControlCode
0x18001c7ef  mov     qword ptr [rsp+6B0h+dwCreationDisposition], rdi; lpOutBuffer
0x18001c7f4  mov     rcx, rbx; hDevice
0x18001c7f7  call    cs:__imp_DeviceIoControl
0x18001c7fd  test    eax, eax
0x18001c7ff  jnz     short loc_18001C83E
0x18001c801  mov     rcx, [rbp+5B8h]; this
0x18001c808  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x18001c80f  mov     edx, 1C4h; void *
0x18001c814  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001c819  mov     ebx, eax
0x18001c81b  call    cs:__imp_GetProcessHeap
0x18001c821  mov     r8, rdi; lpMem
0x18001c824  xor     edx, edx; dwFlags
0x18001c826  mov     rcx, rax; hHeap
0x18001c829  call    cs:__imp_HeapFree
0x18001c82f  lea     rcx, [rsp+6B0h+var_670]
0x18001c834  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001c839  jmp     loc_18001C6EF
0x18001c83e  xor     ecx, ecx
0x18001c840  cmp     [rdi+4], ecx
0x18001c843  jbe     short loc_18001C863
0x18001c845  mov     rdx, [rsi]
0x18001c848  lea     rax, [rcx+rcx*8]
0x18001c84c  inc     rcx
0x18001c84f  shl     rax, 4
0x18001c853  add     rdx, [rax+rdi+40h]
0x18001c858  mov     [rsi], rdx
0x18001c85b  mov     eax, [rdi+4]
0x18001c85e  cmp     rcx, rax
0x18001c861  jb      short loc_18001C848
0x18001c863  call    cs:__imp_GetProcessHeap
0x18001c869  mov     r8, rdi; lpMem
0x18001c86c  xor     edx, edx; dwFlags
0x18001c86e  mov     rcx, rax; hHeap
0x18001c871  call    cs:__imp_HeapFree
0x18001c877  lea     rcx, [rsp+6B0h+var_670]
0x18001c87c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001c881  xor     eax, eax
0x18001c883  mov     rcx, [rbp+5B0h+var_20]
0x18001c88a  xor     rcx, rsp; StackCookie
0x18001c88d  call    __security_check_cookie
0x18001c892  lea     r11, [rsp+6B0h+var_10]
0x18001c89a  mov     rbx, [r11+30h]
0x18001c89e  mov     rsi, [r11+38h]
0x18001c8a2  mov     rsp, r11
0x18001c8a5  pop     r15
0x18001c8a7  pop     rdi
0x18001c8a8  pop     rbp
0x18001c8a9  retn
```
