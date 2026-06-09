# udk::CopilotPlusDetection::_GetPhysicalDiskSize(wchar_t const *,_ULARGE_INTEGER *)

- ea: `0x180174f0c`
- end: `0x18017522e`
- name: `?_GetPhysicalDiskSize@CopilotPlusDetection@udk@@YAJPEB_WPEAT_ULARGE_INTEGER@@@Z`
- size: `802`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName, const wchar_t *, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180171b70`

## callees

- `0x18000f880`
- `0x18005e788`
- `0x1800828f0`
- `0x1800f8f24`
- `0x1801244c0`
- `0x180124cf0`
- `0x18012540e`
- `0x180174f0c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801751ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801751f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801751ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801751f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180175120`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180175120`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18017510c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18017519f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801751e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18017510c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18017519f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801751e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180174fd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801750e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180174fd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801750e0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801750c7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801750c7`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180174f84`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180175003`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180174f84`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180175003`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180175023`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180175023`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180174fcd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180174fcd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18017517b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18017517b`

## pseudocode

```c
signed int __fastcall udk::CopilotPlusDetection::_GetPhysicalDiskSize(
        LPCWSTR lpszFileName,
        wchar_t *a2,
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
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
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
           (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
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
0x180174f0c  mov     [rsp-8+arg_10], rbx
0x180174f11  mov     [rsp-8+arg_18], rsi
0x180174f16  push    rbp
0x180174f17  push    rdi
0x180174f18  push    r15
0x180174f1a  lea     rbp, [rsp-5A0h]
0x180174f22  sub     rsp, 6A0h
0x180174f29  mov     rax, cs:__security_cookie
0x180174f30  xor     rax, rsp
0x180174f33  mov     [rbp+5B0h+var_20], rax
0x180174f3a  mov     rsi, rdx
0x180174f3d  mov     qword ptr [rdx], 0
0x180174f44  mov     rdi, rcx
0x180174f47  mov     r15d, 208h
0x180174f4d  mov     r8d, r15d; Size
0x180174f50  lea     rcx, [rsp+6B0h+szVolumeName]; void *
0x180174f55  xor     edx, edx; Val
0x180174f57  call    memset_0
0x180174f5c  mov     r8d, r15d; Size
0x180174f5f  lea     rcx, [rbp+5B0h+szVolumePathName]; void *
0x180174f66  xor     edx, edx; Val
0x180174f68  call    memset_0
0x180174f6d  test    rdi, rdi
0x180174f70  jz      short loc_180174FAE
0x180174f72  mov     ebx, 104h
0x180174f77  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x180174f7e  mov     r8d, ebx; cchBufferLength
0x180174f81  mov     rcx, rdi; lpszFileName
0x180174f84  call    cs:__imp_GetVolumePathNameW
0x180174f8a  test    eax, eax
0x180174f8c  jnz     loc_180175014
0x180174f92  lea     edx, [r15-6Bh]; void *
0x180174f96  mov     rcx, [rbp+5B8h]; this
0x180174f9d  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x180174fa4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180174fa9  jmp     loc_180175207
0x180174fae  mov     r8, r15; Size
0x180174fb1  lea     rcx, [rbp+5B0h+Buffer]; void *
0x180174fb8  xor     edx, edx; Val
0x180174fba  call    memset_0
0x180174fbf  mov     ebx, 104h
0x180174fc4  lea     rcx, [rbp+5B0h+Buffer]; lpBuffer
0x180174fcb  mov     edx, ebx; uSize
0x180174fcd  call    cs:__imp_GetSystemDirectoryW
0x180174fd3  test    eax, eax
0x180174fd5  jnz     short loc_180174FF2
0x180174fd7  call    cs:__imp_GetLastError
0x180174fdd  test    eax, eax
0x180174fdf  jle     loc_180175207
0x180174fe5  movzx   eax, ax
0x180174fe8  or      eax, 80070000h
0x180174fed  jmp     loc_180175207
0x180174ff2  mov     r8d, ebx; cchBufferLength
0x180174ff5  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x180174ffc  lea     rcx, [rbp+5B0h+Buffer]; lpszFileName
0x180175003  call    cs:__imp_GetVolumePathNameW
0x180175009  test    eax, eax
0x18017500b  jnz     short loc_180175014
0x18017500d  mov     edx, 1A7h
0x180175012  jmp     short loc_180174F96
0x180175014  mov     r8d, ebx; cchBufferLength
0x180175017  lea     rdx, [rsp+6B0h+szVolumeName]; lpszVolumeName
0x18017501c  lea     rcx, [rbp+5B0h+szVolumePathName]; lpszVolumeMountPoint
0x180175023  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180175029  test    eax, eax
0x18017502b  jnz     short loc_180175037
0x18017502d  mov     edx, 1AAh
0x180175032  jmp     loc_180174F96
0x180175037  lea     r8, [rsp+6B0h+var_670]; unsigned __int64 *
0x18017503c  mov     [rsp+6B0h+var_670], 0
0x180175045  mov     rdx, rbx; unsigned __int64
0x180175048  lea     rcx, [rsp+6B0h+szVolumeName]; wchar_t *
0x18017504d  call    ?StringCchLengthW@@YAJPEB_W_KPEA_K@Z; StringCchLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180175052  mov     ebx, eax
0x180175054  test    eax, eax
0x180175056  jns     short loc_18017507A
0x180175058  mov     rcx, [rbp+5B8h]; this
0x18017505f  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x180175066  mov     r9d, eax; char *
0x180175069  mov     edx, 1AEh; void *
0x18017506e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180175073  mov     eax, ebx
0x180175075  jmp     loc_180175207
0x18017507a  mov     rax, [rsp+6B0h+var_670]
0x18017507f  test    rax, rax
0x180175082  jz      short loc_1801750A0
0x180175084  cmp     [rsp+rax*2+6B0h+var_652], 5Ch ; '\'
0x18017508a  jnz     short loc_1801750A0
0x18017508c  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180175094  cmp     rcx, r15
0x180175097  jnb     short loc_1801750FE
0x180175099  xor     eax, eax
0x18017509b  mov     [rsp+rcx+6B0h+szVolumeName], ax
0x1801750a0  xor     r9d, r9d; lpSecurityAttributes
0x1801750a3  mov     [rsp+6B0h+hTemplateFile], 0; hTemplateFile
0x1801750ac  mov     [rsp+6B0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1801750b4  lea     rcx, [rsp+6B0h+szVolumeName]; lpFileName
0x1801750b9  xor     edx, edx; dwDesiredAccess
0x1801750bb  mov     [rsp+6B0h+dwCreationDisposition], 3; int
0x1801750c3  lea     r8d, [r9+1]; dwShareMode
0x1801750c7  call    cs:__imp_CreateFileW
0x1801750cd  mov     rbx, rax
0x1801750d0  mov     [rsp+6B0h+var_670], rax
0x1801750d5  inc     rax
0x1801750d8  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801750de  jnz     short loc_180175104
0x1801750e0  call    cs:__imp_GetLastError
0x1801750e6  mov     ebx, eax
0x1801750e8  test    eax, eax
0x1801750ea  jle     loc_1801751B3
0x1801750f0  movzx   ebx, ax
0x1801750f3  or      ebx, 80070000h
0x1801750f9  jmp     loc_1801751B3
0x1801750fe  call    __report_rangecheckfailure
0x180175104  mov     [rsp+6B0h+BytesReturned], 0
0x18017510c  call    cs:__imp_GetProcessHeap
0x180175112  mov     r15d, 48C0h
0x180175118  xor     edx, edx; dwFlags
0x18017511a  mov     rcx, rax; hHeap
0x18017511d  mov     r8d, r15d; dwBytes
0x180175120  call    cs:__imp_HeapAlloc
0x180175126  mov     rdi, rax
0x180175129  test    rax, rax
0x18017512c  jnz     short loc_180175150
0x18017512e  mov     rcx, [rbp+5B8h]; this
0x180175135  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18017513c  mov     ebx, 8007000Eh
0x180175141  mov     edx, 1BEh; void *
0x180175146  mov     r9d, ebx; char *
0x180175149  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017514e  jmp     short loc_1801751B3
0x180175150  mov     [rsp+6B0h+lpOverlapped], 0; lpOverlapped
0x180175159  lea     rax, [rsp+6B0h+BytesReturned]
0x18017515e  mov     [rsp+6B0h+hTemplateFile], rax; lpBytesReturned
0x180175163  xor     r9d, r9d; nInBufferSize
0x180175166  mov     [rsp+6B0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x18017516b  xor     r8d, r8d; lpInBuffer
0x18017516e  mov     edx, 70050h; dwIoControlCode
0x180175173  mov     qword ptr [rsp+6B0h+dwCreationDisposition], rdi; lpOutBuffer
0x180175178  mov     rcx, rbx; hDevice
0x18017517b  call    cs:__imp_DeviceIoControl
0x180175181  test    eax, eax
0x180175183  jnz     short loc_1801751C2
0x180175185  mov     rcx, [rbp+5B8h]; this
0x18017518c  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x180175193  mov     edx, 1C4h; void *
0x180175198  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18017519d  mov     ebx, eax
0x18017519f  call    cs:__imp_GetProcessHeap
0x1801751a5  mov     r8, rdi; lpMem
0x1801751a8  xor     edx, edx; dwFlags
0x1801751aa  mov     rcx, rax; hHeap
0x1801751ad  call    cs:__imp_HeapFree
0x1801751b3  lea     rcx, [rsp+6B0h+var_670]
0x1801751b8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801751bd  jmp     loc_180175073
0x1801751c2  xor     ecx, ecx
0x1801751c4  cmp     [rdi+4], ecx
0x1801751c7  jbe     short loc_1801751E7
0x1801751c9  mov     rdx, [rsi]
0x1801751cc  lea     rax, [rcx+rcx*8]
0x1801751d0  inc     rcx
0x1801751d3  shl     rax, 4
0x1801751d7  add     rdx, [rax+rdi+40h]
0x1801751dc  mov     [rsi], rdx
0x1801751df  mov     eax, [rdi+4]
0x1801751e2  cmp     rcx, rax
0x1801751e5  jb      short loc_1801751CC
0x1801751e7  call    cs:__imp_GetProcessHeap
0x1801751ed  mov     r8, rdi; lpMem
0x1801751f0  xor     edx, edx; dwFlags
0x1801751f2  mov     rcx, rax; hHeap
0x1801751f5  call    cs:__imp_HeapFree
0x1801751fb  lea     rcx, [rsp+6B0h+var_670]
0x180175200  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180175205  xor     eax, eax
0x180175207  mov     rcx, [rbp+5B0h+var_20]
0x18017520e  xor     rcx, rsp; StackCookie
0x180175211  call    __security_check_cookie
0x180175216  lea     r11, [rsp+6B0h+var_10]
0x18017521e  mov     rbx, [r11+30h]
0x180175222  mov     rsi, [r11+38h]
0x180175226  mov     rsp, r11
0x180175229  pop     r15
0x18017522b  pop     rdi
0x18017522c  pop     rbp
0x18017522d  retn
```
