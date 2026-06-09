# udk::CopilotPlusDetection::_GetPhysicalDiskSize(ushort const *,_ULARGE_INTEGER *)

- ea: `0x18003326c`
- end: `0x1800335e6`
- name: `?_GetPhysicalDiskSize@CopilotPlusDetection@udk@@YAJPEBGPEAT_ULARGE_INTEGER@@@Z`
- size: `890`
- prototype: `signed int __fastcall(LPCWSTR lpszFileName, unsigned __int16 *, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180055230`

## callees

- `0x18000f760`
- `0x18002b1c8`
- `0x18002b610`
- `0x18003326c`
- `0x1800335ec`
- `0x180034070`
- `0x180034500`
- `0x180034d28`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033552`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800335a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033552`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800335a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800334b3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800334b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033499`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003353e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033592`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033499`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003353e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033343`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033343`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033467`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180033333`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180033333`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18003339e`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18003339e`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800332e4`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180033375`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800332e4`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180033375`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033448`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033448`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180033514`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180033514`

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
  unsigned __int64 v23[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned[4]; // [rsp+50h] [rbp-B0h] BYREF
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
  v23[0] = 0;
  v8 = StringCchLengthW(szVolumeName, 0x104u, v23);
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
  if ( v23[0] && *((_WORD *)&BytesReturned[3] + v23[0] + 1) == 92 )
  {
    v10 = 2 * v23[0] - 2;
    if ( v10 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v10) = 0;
  }
  FileW = CreateFileW(szVolumeName, 0, 1u, 0, 3u, 0x2000000u, 0);
  v23[0] = (unsigned __int64)FileW;
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
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v23);
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
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v23);
  return 0;
}

```

## disassembly

```asm
0x18003326c  mov     [rsp-8+arg_10], rbx
0x180033271  mov     [rsp-8+arg_18], rsi
0x180033276  push    rbp
0x180033277  push    rdi
0x180033278  push    r15
0x18003327a  lea     rbp, [rsp-5A0h]
0x180033282  sub     rsp, 6A0h
0x180033289  mov     rax, cs:__security_cookie
0x180033290  xor     rax, rsp
0x180033293  mov     [rbp+5B0h+var_20], rax
0x18003329a  mov     rsi, rdx
0x18003329d  mov     qword ptr [rdx], 0
0x1800332a4  mov     rdi, rcx
0x1800332a7  mov     r15d, 208h
0x1800332ad  mov     r8d, r15d; Size
0x1800332b0  lea     rcx, [rsp+6B0h+szVolumeName]; void *
0x1800332b5  xor     edx, edx; Val
0x1800332b7  call    memset_0
0x1800332bc  mov     r8d, r15d; Size
0x1800332bf  lea     rcx, [rbp+5B0h+szVolumePathName]; void *
0x1800332c6  xor     edx, edx; Val
0x1800332c8  call    memset_0
0x1800332cd  test    rdi, rdi
0x1800332d0  jz      short loc_180033314
0x1800332d2  mov     ebx, 104h
0x1800332d7  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x1800332de  mov     r8d, ebx; cchBufferLength
0x1800332e1  mov     rcx, rdi; lpszFileName
0x1800332e4  call    cs:__imp_GetVolumePathNameW
0x1800332eb  nop     dword ptr [rax+rax+00h]
0x1800332f0  test    eax, eax
0x1800332f2  jnz     loc_18003338F
0x1800332f8  lea     edx, [r15-6Bh]; void *
0x1800332fc  mov     rcx, [rbp+5B8h]; this
0x180033303  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18003330a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003330f  jmp     loc_1800335BE
0x180033314  mov     r8, r15; Size
0x180033317  lea     rcx, [rbp+5B0h+Buffer]; void *
0x18003331e  xor     edx, edx; Val
0x180033320  call    memset_0
0x180033325  mov     ebx, 104h
0x18003332a  lea     rcx, [rbp+5B0h+Buffer]; lpBuffer
0x180033331  mov     edx, ebx; uSize
0x180033333  call    cs:__imp_GetSystemDirectoryW
0x18003333a  nop     dword ptr [rax+rax+00h]
0x18003333f  test    eax, eax
0x180033341  jnz     short loc_180033364
0x180033343  call    cs:__imp_GetLastError
0x18003334a  nop     dword ptr [rax+rax+00h]
0x18003334f  test    eax, eax
0x180033351  jle     loc_1800335BE
0x180033357  movzx   eax, ax
0x18003335a  or      eax, 80070000h
0x18003335f  jmp     loc_1800335BE
0x180033364  mov     r8d, ebx; cchBufferLength
0x180033367  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x18003336e  lea     rcx, [rbp+5B0h+Buffer]; lpszFileName
0x180033375  call    cs:__imp_GetVolumePathNameW
0x18003337c  nop     dword ptr [rax+rax+00h]
0x180033381  test    eax, eax
0x180033383  jnz     short loc_18003338F
0x180033385  mov     edx, 1A7h
0x18003338a  jmp     loc_1800332FC
0x18003338f  mov     r8d, ebx; cchBufferLength
0x180033392  lea     rdx, [rsp+6B0h+szVolumeName]; lpszVolumeName
0x180033397  lea     rcx, [rbp+5B0h+szVolumePathName]; lpszVolumeMountPoint
0x18003339e  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800333a5  nop     dword ptr [rax+rax+00h]
0x1800333aa  test    eax, eax
0x1800333ac  jnz     short loc_1800333B8
0x1800333ae  mov     edx, 1AAh
0x1800333b3  jmp     loc_1800332FC
0x1800333b8  lea     r8, [rsp+6B0h+var_670]; unsigned __int64 *
0x1800333bd  mov     [rsp+6B0h+var_670], 0
0x1800333c6  mov     rdx, rbx; unsigned __int64
0x1800333c9  lea     rcx, [rsp+6B0h+szVolumeName]; unsigned __int16 *
0x1800333ce  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800333d3  mov     ebx, eax
0x1800333d5  test    eax, eax
0x1800333d7  jns     short loc_1800333FB
0x1800333d9  mov     rcx, [rbp+5B8h]; this
0x1800333e0  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1800333e7  mov     r9d, eax; char *
0x1800333ea  mov     edx, 1AEh; void *
0x1800333ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800333f4  mov     eax, ebx
0x1800333f6  jmp     loc_1800335BE
0x1800333fb  mov     rax, [rsp+6B0h+var_670]
0x180033400  test    rax, rax
0x180033403  jz      short loc_180033421
0x180033405  cmp     [rsp+rax*2+6B0h+var_652], 5Ch ; '\'
0x18003340b  jnz     short loc_180033421
0x18003340d  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180033415  cmp     rcx, r15
0x180033418  jnb     short loc_18003348B
0x18003341a  xor     eax, eax
0x18003341c  mov     [rsp+rcx+6B0h+szVolumeName], ax
0x180033421  xor     r9d, r9d; lpSecurityAttributes
0x180033424  mov     [rsp+6B0h+hTemplateFile], 0; hTemplateFile
0x18003342d  mov     [rsp+6B0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180033435  lea     rcx, [rsp+6B0h+szVolumeName]; lpFileName
0x18003343a  xor     edx, edx; dwDesiredAccess
0x18003343c  mov     [rsp+6B0h+dwCreationDisposition], 3; int
0x180033444  lea     r8d, [r9+1]; dwShareMode
0x180033448  call    cs:__imp_CreateFileW
0x18003344f  nop     dword ptr [rax+rax+00h]
0x180033454  mov     rbx, rax
0x180033457  mov     [rsp+6B0h+var_670], rax
0x18003345c  inc     rax
0x18003345f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180033465  jnz     short loc_180033491
0x180033467  call    cs:__imp_GetLastError
0x18003346e  nop     dword ptr [rax+rax+00h]
0x180033473  mov     ebx, eax
0x180033475  test    eax, eax
0x180033477  jle     loc_18003355E
0x18003347d  movzx   ebx, ax
0x180033480  or      ebx, 80070000h
0x180033486  jmp     loc_18003355E
0x18003348b  call    __report_rangecheckfailure
0x180033491  mov     [rsp+6B0h+BytesReturned], 0
0x180033499  call    cs:__imp_GetProcessHeap
0x1800334a0  nop     dword ptr [rax+rax+00h]
0x1800334a5  mov     r15d, 48C0h
0x1800334ab  xor     edx, edx; dwFlags
0x1800334ad  mov     rcx, rax; hHeap
0x1800334b0  mov     r8d, r15d; dwBytes
0x1800334b3  call    cs:__imp_HeapAlloc
0x1800334ba  nop     dword ptr [rax+rax+00h]
0x1800334bf  mov     rdi, rax
0x1800334c2  test    rax, rax
0x1800334c5  jnz     short loc_1800334E9
0x1800334c7  mov     rcx, [rbp+5B8h]; this
0x1800334ce  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1800334d5  mov     ebx, 8007000Eh
0x1800334da  mov     edx, 1BEh; void *
0x1800334df  mov     r9d, ebx; char *
0x1800334e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800334e7  jmp     short loc_18003355E
0x1800334e9  mov     [rsp+6B0h+lpOverlapped], 0; lpOverlapped
0x1800334f2  lea     rax, [rsp+6B0h+BytesReturned]
0x1800334f7  mov     [rsp+6B0h+hTemplateFile], rax; lpBytesReturned
0x1800334fc  xor     r9d, r9d; nInBufferSize
0x1800334ff  mov     [rsp+6B0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x180033504  xor     r8d, r8d; lpInBuffer
0x180033507  mov     edx, 70050h; dwIoControlCode
0x18003350c  mov     qword ptr [rsp+6B0h+dwCreationDisposition], rdi; lpOutBuffer
0x180033511  mov     rcx, rbx; hDevice
0x180033514  call    cs:__imp_DeviceIoControl
0x18003351b  nop     dword ptr [rax+rax+00h]
0x180033520  test    eax, eax
0x180033522  jnz     short loc_18003356D
0x180033524  mov     rcx, [rbp+5B8h]; this
0x18003352b  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x180033532  mov     edx, 1C4h; void *
0x180033537  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003353c  mov     ebx, eax
0x18003353e  call    cs:__imp_GetProcessHeap
0x180033545  nop     dword ptr [rax+rax+00h]
0x18003354a  mov     r8, rdi; lpMem
0x18003354d  xor     edx, edx; dwFlags
0x18003354f  mov     rcx, rax; hHeap
0x180033552  call    cs:__imp_HeapFree
0x180033559  nop     dword ptr [rax+rax+00h]
0x18003355e  lea     rcx, [rsp+6B0h+var_670]
0x180033563  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180033568  jmp     loc_1800333F4
0x18003356d  xor     ecx, ecx
0x18003356f  cmp     [rdi+4], ecx
0x180033572  jbe     short loc_180033592
0x180033574  mov     rdx, [rsi]
0x180033577  lea     rax, [rcx+rcx*8]
0x18003357b  inc     rcx
0x18003357e  shl     rax, 4
0x180033582  add     rdx, [rax+rdi+40h]
0x180033587  mov     [rsi], rdx
0x18003358a  mov     eax, [rdi+4]
0x18003358d  cmp     rcx, rax
0x180033590  jb      short loc_180033577
0x180033592  call    cs:__imp_GetProcessHeap
0x180033599  nop     dword ptr [rax+rax+00h]
0x18003359e  mov     r8, rdi; lpMem
0x1800335a1  xor     edx, edx; dwFlags
0x1800335a3  mov     rcx, rax; hHeap
0x1800335a6  call    cs:__imp_HeapFree
0x1800335ad  nop     dword ptr [rax+rax+00h]
0x1800335b2  lea     rcx, [rsp+6B0h+var_670]
0x1800335b7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800335bc  xor     eax, eax
0x1800335be  mov     rcx, [rbp+5B0h+var_20]
0x1800335c5  xor     rcx, rsp; StackCookie
0x1800335c8  call    __security_check_cookie
0x1800335cd  lea     r11, [rsp+6B0h+var_10]
0x1800335d5  mov     rbx, [r11+30h]
0x1800335d9  mov     rsi, [r11+38h]
0x1800335dd  mov     rsp, r11
0x1800335e0  pop     r15
0x1800335e2  pop     rdi
0x1800335e3  pop     rbp
0x1800335e4  retn
```
