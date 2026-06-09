# udk::CopilotPlusDetection::_GetPhysicalDiskSize(ushort const *,_ULARGE_INTEGER *)

- ea: `0x18009c5d8`
- end: `0x18009c8fe`
- name: `?_GetPhysicalDiskSize@CopilotPlusDetection@udk@@YAJPEBGPEAT_ULARGE_INTEGER@@@Z`
- size: `806`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName, const unsigned __int16 *, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x18009a568`

## callees

- `0x180063a68`
- `0x18006d210`
- `0x180071dc0`
- `0x180072370`
- `0x180072cf4`
- `0x180095f74`
- `0x18009c3bc`
- `0x18009c5d8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c877`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c8bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c877`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c8bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009c7ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009c7ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009c7d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009c869`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009c8b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009c7d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009c869`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009c8b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c6a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c7b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c6a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c7b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18009c699`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18009c699`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18009c650`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18009c6cf`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18009c650`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18009c6cf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009c797`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009c797`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18009c845`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18009c845`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18009c6ef`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18009c6ef`

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
               (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
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
               (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
               v5);
    }
  }
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    v6 = 426;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
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
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
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
    goto LABEL_26;
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
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      (const char *)0x8007000ELL,
      dwCreationDispositiona);
LABEL_26:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
    return v9;
  }
  if ( !DeviceIoControl(FileW, 0x70050u, 0, 0, v14, 0x48C0u, BytesReturned, 0) )
  {
    v9 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x1C4,
           (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
           v15);
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v14);
    goto LABEL_26;
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
0x18009c5d8  mov     [rsp-8+arg_10], rbx
0x18009c5dd  mov     [rsp-8+arg_18], rsi
0x18009c5e2  push    rbp
0x18009c5e3  push    rdi
0x18009c5e4  push    r15
0x18009c5e6  lea     rbp, [rsp-5A0h]
0x18009c5ee  sub     rsp, 6A0h
0x18009c5f5  mov     rax, cs:__security_cookie
0x18009c5fc  xor     rax, rsp
0x18009c5ff  mov     [rbp+5B0h+var_20], rax
0x18009c606  mov     rsi, rdx
0x18009c609  mov     qword ptr [rdx], 0
0x18009c610  mov     rdi, rcx
0x18009c613  mov     r15d, 208h
0x18009c619  mov     r8d, r15d; Size
0x18009c61c  lea     rcx, [rsp+6B0h+szVolumeName]; void *
0x18009c621  xor     edx, edx; Val
0x18009c623  call    memset_0
0x18009c628  mov     r8d, r15d; Size
0x18009c62b  lea     rcx, [rbp+5B0h+szVolumePathName]; void *
0x18009c632  xor     edx, edx; Val
0x18009c634  call    memset_0
0x18009c639  test    rdi, rdi
0x18009c63c  jz      short loc_18009C67A
0x18009c63e  mov     ebx, 104h
0x18009c643  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x18009c64a  mov     r8d, ebx; cchBufferLength
0x18009c64d  mov     rcx, rdi; lpszFileName
0x18009c650  call    cs:__imp_GetVolumePathNameW
0x18009c656  test    eax, eax
0x18009c658  jnz     loc_18009C6E0
0x18009c65e  lea     edx, [r15-6Bh]; void *
0x18009c662  mov     rcx, [rbp+5B8h]; this
0x18009c669  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18009c670  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009c675  jmp     loc_18009C8D1
0x18009c67a  mov     r8, r15; Size
0x18009c67d  lea     rcx, [rbp+5B0h+Buffer]; void *
0x18009c684  xor     edx, edx; Val
0x18009c686  call    memset_0
0x18009c68b  mov     ebx, 104h
0x18009c690  lea     rcx, [rbp+5B0h+Buffer]; lpBuffer
0x18009c697  mov     edx, ebx; uSize
0x18009c699  call    cs:__imp_GetSystemDirectoryW
0x18009c69f  test    eax, eax
0x18009c6a1  jnz     short loc_18009C6BE
0x18009c6a3  call    cs:__imp_GetLastError
0x18009c6a9  test    eax, eax
0x18009c6ab  jle     loc_18009C8D1
0x18009c6b1  movzx   eax, ax
0x18009c6b4  or      eax, 80070000h
0x18009c6b9  jmp     loc_18009C8D1
0x18009c6be  mov     r8d, ebx; cchBufferLength
0x18009c6c1  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x18009c6c8  lea     rcx, [rbp+5B0h+Buffer]; lpszFileName
0x18009c6cf  call    cs:__imp_GetVolumePathNameW
0x18009c6d5  test    eax, eax
0x18009c6d7  jnz     short loc_18009C6E0
0x18009c6d9  mov     edx, 1A7h
0x18009c6de  jmp     short loc_18009C662
0x18009c6e0  mov     r8d, ebx; cchBufferLength
0x18009c6e3  lea     rdx, [rsp+6B0h+szVolumeName]; lpszVolumeName
0x18009c6e8  lea     rcx, [rbp+5B0h+szVolumePathName]; lpszVolumeMountPoint
0x18009c6ef  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18009c6f5  test    eax, eax
0x18009c6f7  jnz     short loc_18009C703
0x18009c6f9  mov     edx, 1AAh
0x18009c6fe  jmp     loc_18009C662
0x18009c703  lea     r8, [rsp+6B0h+var_670]; unsigned __int64 *
0x18009c708  mov     [rsp+6B0h+var_670], 0
0x18009c711  mov     rdx, rbx; unsigned __int64
0x18009c714  lea     rcx, [rsp+6B0h+szVolumeName]; unsigned __int16 *
0x18009c719  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009c71e  mov     ebx, eax
0x18009c720  test    eax, eax
0x18009c722  jns     short loc_18009C746
0x18009c724  mov     rcx, [rbp+5B8h]; this
0x18009c72b  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18009c732  mov     r9d, eax; char *
0x18009c735  mov     edx, 1AEh; void *
0x18009c73a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009c73f  mov     eax, ebx
0x18009c741  jmp     loc_18009C8D1
0x18009c746  mov     rax, [rsp+6B0h+var_670]
0x18009c74b  test    rax, rax
0x18009c74e  jz      short loc_18009C770
0x18009c750  cmp     [rsp+rax*2+6B0h+var_652], 5Ch ; '\'
0x18009c756  jnz     short loc_18009C770
0x18009c758  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18009c760  cmp     rcx, r15
0x18009c763  jnb     loc_18009C8F8
0x18009c769  xor     eax, eax
0x18009c76b  mov     [rsp+rcx+6B0h+szVolumeName], ax
0x18009c770  xor     r9d, r9d; lpSecurityAttributes
0x18009c773  mov     [rsp+6B0h+hTemplateFile], 0; hTemplateFile
0x18009c77c  mov     [rsp+6B0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18009c784  lea     rcx, [rsp+6B0h+szVolumeName]; lpFileName
0x18009c789  xor     edx, edx; dwDesiredAccess
0x18009c78b  mov     [rsp+6B0h+dwCreationDisposition], 3; int
0x18009c793  lea     r8d, [r9+1]; dwShareMode
0x18009c797  call    cs:__imp_CreateFileW
0x18009c79d  mov     rbx, rax
0x18009c7a0  mov     [rsp+6B0h+var_670], rax
0x18009c7a5  inc     rax
0x18009c7a8  test    rax, 0FFFFFFFFFFFFFFFEh
0x18009c7ae  jnz     short loc_18009C7CE
0x18009c7b0  call    cs:__imp_GetLastError
0x18009c7b6  mov     ebx, eax
0x18009c7b8  test    eax, eax
0x18009c7ba  jle     loc_18009C87D
0x18009c7c0  movzx   ebx, ax
0x18009c7c3  or      ebx, 80070000h
0x18009c7c9  jmp     loc_18009C87D
0x18009c7ce  mov     [rsp+6B0h+BytesReturned], 0
0x18009c7d6  call    cs:__imp_GetProcessHeap
0x18009c7dc  mov     r15d, 48C0h
0x18009c7e2  xor     edx, edx; dwFlags
0x18009c7e4  mov     rcx, rax; hHeap
0x18009c7e7  mov     r8d, r15d; dwBytes
0x18009c7ea  call    cs:__imp_HeapAlloc
0x18009c7f0  mov     rdi, rax
0x18009c7f3  test    rax, rax
0x18009c7f6  jnz     short loc_18009C81A
0x18009c7f8  mov     rcx, [rbp+5B8h]; this
0x18009c7ff  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18009c806  mov     ebx, 8007000Eh
0x18009c80b  mov     edx, 1BEh; void *
0x18009c810  mov     r9d, ebx; char *
0x18009c813  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009c818  jmp     short loc_18009C87D
0x18009c81a  mov     [rsp+6B0h+lpOverlapped], 0; lpOverlapped
0x18009c823  lea     rax, [rsp+6B0h+BytesReturned]
0x18009c828  mov     [rsp+6B0h+hTemplateFile], rax; lpBytesReturned
0x18009c82d  xor     r9d, r9d; nInBufferSize
0x18009c830  mov     [rsp+6B0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x18009c835  xor     r8d, r8d; lpInBuffer
0x18009c838  mov     edx, 70050h; dwIoControlCode
0x18009c83d  mov     qword ptr [rsp+6B0h+dwCreationDisposition], rdi; lpOutBuffer
0x18009c842  mov     rcx, rbx; hDevice
0x18009c845  call    cs:__imp_DeviceIoControl
0x18009c84b  test    eax, eax
0x18009c84d  jnz     short loc_18009C88C
0x18009c84f  mov     rcx, [rbp+5B8h]; this
0x18009c856  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18009c85d  mov     edx, 1C4h; void *
0x18009c862  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009c867  mov     ebx, eax
0x18009c869  call    cs:__imp_GetProcessHeap
0x18009c86f  mov     r8, rdi; lpMem
0x18009c872  xor     edx, edx; dwFlags
0x18009c874  mov     rcx, rax; hHeap
0x18009c877  call    cs:__imp_HeapFree
0x18009c87d  lea     rcx, [rsp+6B0h+var_670]
0x18009c882  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009c887  jmp     loc_18009C73F
0x18009c88c  xor     ecx, ecx
0x18009c88e  cmp     [rdi+4], ecx
0x18009c891  jbe     short loc_18009C8B1
0x18009c893  mov     rdx, [rsi]
0x18009c896  lea     rax, [rcx+rcx*8]
0x18009c89a  inc     rcx
0x18009c89d  shl     rax, 4
0x18009c8a1  add     rdx, [rax+rdi+40h]
0x18009c8a6  mov     [rsi], rdx
0x18009c8a9  mov     eax, [rdi+4]
0x18009c8ac  cmp     rcx, rax
0x18009c8af  jb      short loc_18009C896
0x18009c8b1  call    cs:__imp_GetProcessHeap
0x18009c8b7  mov     r8, rdi; lpMem
0x18009c8ba  xor     edx, edx; dwFlags
0x18009c8bc  mov     rcx, rax; hHeap
0x18009c8bf  call    cs:__imp_HeapFree
0x18009c8c5  lea     rcx, [rsp+6B0h+var_670]
0x18009c8ca  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009c8cf  xor     eax, eax
0x18009c8d1  mov     rcx, [rbp+5B0h+var_20]
0x18009c8d8  xor     rcx, rsp; StackCookie
0x18009c8db  call    __security_check_cookie
0x18009c8e0  lea     r11, [rsp+6B0h+var_10]
0x18009c8e8  mov     rbx, [r11+30h]
0x18009c8ec  mov     rsi, [r11+38h]
0x18009c8f0  mov     rsp, r11
0x18009c8f3  pop     r15
0x18009c8f5  pop     rdi
0x18009c8f6  pop     rbp
0x18009c8f7  retn
0x18009c8f8  call    __report_rangecheckfailure
```
