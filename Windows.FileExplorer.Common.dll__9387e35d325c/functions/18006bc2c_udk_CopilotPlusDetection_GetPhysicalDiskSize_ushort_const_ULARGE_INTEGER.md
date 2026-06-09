# udk::CopilotPlusDetection::_GetPhysicalDiskSize(ushort const *,_ULARGE_INTEGER *)

- ea: `0x18006bc2c`
- end: `0x18006bf52`
- name: `?_GetPhysicalDiskSize@CopilotPlusDetection@udk@@YAJPEBGPEAT_ULARGE_INTEGER@@@Z`
- size: `806`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName, const unsigned __int16 *, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180067040`

## callees

- `0x1800077c8`
- `0x18003169c`
- `0x180037780`
- `0x180037d10`
- `0x180038708`
- `0x18003d3e8`
- `0x18006b790`
- `0x18006bc2c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006becb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bf13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006becb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bf13`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006be3e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006be3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006be2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006bebd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006bf05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006be2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006bebd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006bf05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bcf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006be04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bcf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006be04`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18006bced`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18006bced`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006bdeb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006bdeb`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18006bca4`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18006bd23`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18006bca4`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18006bd23`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006be99`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006be99`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18006bd43`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18006bd43`

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
  HRESULT v8; // eax
  unsigned int v9; // ebx
  size_t v10; // rcx
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
  size_t pcchLength; // [rsp+40h] [rbp-C0h] BYREF
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
  pcchLength = 0;
  v8 = StringLengthWorkerW(szVolumeName, 0x104u, &pcchLength);
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
  if ( pcchLength && *((_WORD *)&BytesReturned[5] + pcchLength + 1) == 92 )
  {
    v10 = 2 * pcchLength - 2;
    if ( v10 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v10) = 0;
  }
  FileW = CreateFileW(szVolumeName, 0, 1u, 0, 3u, 0x2000000u, 0);
  pcchLength = (size_t)FileW;
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
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&pcchLength);
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
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&pcchLength);
  return 0;
}

```

## disassembly

```asm
0x18006bc2c  mov     [rsp-8+arg_10], rbx
0x18006bc31  mov     [rsp-8+arg_18], rsi
0x18006bc36  push    rbp
0x18006bc37  push    rdi
0x18006bc38  push    r15
0x18006bc3a  lea     rbp, [rsp-5A0h]
0x18006bc42  sub     rsp, 6A0h
0x18006bc49  mov     rax, cs:__security_cookie
0x18006bc50  xor     rax, rsp
0x18006bc53  mov     [rbp+5B0h+var_20], rax
0x18006bc5a  mov     rsi, rdx
0x18006bc5d  mov     qword ptr [rdx], 0
0x18006bc64  mov     rdi, rcx
0x18006bc67  mov     r15d, 208h
0x18006bc6d  mov     r8d, r15d; Size
0x18006bc70  lea     rcx, [rsp+6B0h+szVolumeName]; void *
0x18006bc75  xor     edx, edx; Val
0x18006bc77  call    memset_0
0x18006bc7c  mov     r8d, r15d; Size
0x18006bc7f  lea     rcx, [rbp+5B0h+szVolumePathName]; void *
0x18006bc86  xor     edx, edx; Val
0x18006bc88  call    memset_0
0x18006bc8d  test    rdi, rdi
0x18006bc90  jz      short loc_18006BCCE
0x18006bc92  mov     ebx, 104h
0x18006bc97  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x18006bc9e  mov     r8d, ebx; cchBufferLength
0x18006bca1  mov     rcx, rdi; lpszFileName
0x18006bca4  call    cs:__imp_GetVolumePathNameW
0x18006bcaa  test    eax, eax
0x18006bcac  jnz     loc_18006BD34
0x18006bcb2  lea     edx, [r15-6Bh]; void *
0x18006bcb6  mov     rcx, [rbp+5B8h]; this
0x18006bcbd  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18006bcc4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006bcc9  jmp     loc_18006BF25
0x18006bcce  mov     r8, r15; Size
0x18006bcd1  lea     rcx, [rbp+5B0h+Buffer]; void *
0x18006bcd8  xor     edx, edx; Val
0x18006bcda  call    memset_0
0x18006bcdf  mov     ebx, 104h
0x18006bce4  lea     rcx, [rbp+5B0h+Buffer]; lpBuffer
0x18006bceb  mov     edx, ebx; uSize
0x18006bced  call    cs:__imp_GetSystemDirectoryW
0x18006bcf3  test    eax, eax
0x18006bcf5  jnz     short loc_18006BD12
0x18006bcf7  call    cs:__imp_GetLastError
0x18006bcfd  test    eax, eax
0x18006bcff  jle     loc_18006BF25
0x18006bd05  movzx   eax, ax
0x18006bd08  or      eax, 80070000h
0x18006bd0d  jmp     loc_18006BF25
0x18006bd12  mov     r8d, ebx; cchBufferLength
0x18006bd15  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x18006bd1c  lea     rcx, [rbp+5B0h+Buffer]; lpszFileName
0x18006bd23  call    cs:__imp_GetVolumePathNameW
0x18006bd29  test    eax, eax
0x18006bd2b  jnz     short loc_18006BD34
0x18006bd2d  mov     edx, 1A7h
0x18006bd32  jmp     short loc_18006BCB6
0x18006bd34  mov     r8d, ebx; cchBufferLength
0x18006bd37  lea     rdx, [rsp+6B0h+szVolumeName]; lpszVolumeName
0x18006bd3c  lea     rcx, [rbp+5B0h+szVolumePathName]; lpszVolumeMountPoint
0x18006bd43  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18006bd49  test    eax, eax
0x18006bd4b  jnz     short loc_18006BD57
0x18006bd4d  mov     edx, 1AAh
0x18006bd52  jmp     loc_18006BCB6
0x18006bd57  lea     r8, [rsp+6B0h+pcchLength]; pcchLength
0x18006bd5c  mov     [rsp+6B0h+pcchLength], 0
0x18006bd65  mov     rdx, rbx; cchMax
0x18006bd68  lea     rcx, [rsp+6B0h+szVolumeName]; psz
0x18006bd6d  call    StringLengthWorkerW
0x18006bd72  mov     ebx, eax
0x18006bd74  test    eax, eax
0x18006bd76  jns     short loc_18006BD9A
0x18006bd78  mov     rcx, [rbp+5B8h]; this
0x18006bd7f  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18006bd86  mov     r9d, eax; char *
0x18006bd89  mov     edx, 1AEh; void *
0x18006bd8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bd93  mov     eax, ebx
0x18006bd95  jmp     loc_18006BF25
0x18006bd9a  mov     rax, [rsp+6B0h+pcchLength]
0x18006bd9f  test    rax, rax
0x18006bda2  jz      short loc_18006BDC4
0x18006bda4  cmp     [rsp+rax*2+6B0h+var_652], 5Ch ; '\'
0x18006bdaa  jnz     short loc_18006BDC4
0x18006bdac  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18006bdb4  cmp     rcx, r15
0x18006bdb7  jnb     loc_18006BF4C
0x18006bdbd  xor     eax, eax
0x18006bdbf  mov     [rsp+rcx+6B0h+szVolumeName], ax
0x18006bdc4  xor     r9d, r9d; lpSecurityAttributes
0x18006bdc7  mov     [rsp+6B0h+hTemplateFile], 0; hTemplateFile
0x18006bdd0  mov     [rsp+6B0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18006bdd8  lea     rcx, [rsp+6B0h+szVolumeName]; lpFileName
0x18006bddd  xor     edx, edx; dwDesiredAccess
0x18006bddf  mov     [rsp+6B0h+dwCreationDisposition], 3; int
0x18006bde7  lea     r8d, [r9+1]; dwShareMode
0x18006bdeb  call    cs:__imp_CreateFileW
0x18006bdf1  mov     rbx, rax
0x18006bdf4  mov     [rsp+6B0h+pcchLength], rax
0x18006bdf9  inc     rax
0x18006bdfc  test    rax, 0FFFFFFFFFFFFFFFEh
0x18006be02  jnz     short loc_18006BE22
0x18006be04  call    cs:__imp_GetLastError
0x18006be0a  mov     ebx, eax
0x18006be0c  test    eax, eax
0x18006be0e  jle     loc_18006BED1
0x18006be14  movzx   ebx, ax
0x18006be17  or      ebx, 80070000h
0x18006be1d  jmp     loc_18006BED1
0x18006be22  mov     [rsp+6B0h+BytesReturned], 0
0x18006be2a  call    cs:__imp_GetProcessHeap
0x18006be30  mov     r15d, 48C0h
0x18006be36  xor     edx, edx; dwFlags
0x18006be38  mov     rcx, rax; hHeap
0x18006be3b  mov     r8d, r15d; dwBytes
0x18006be3e  call    cs:__imp_HeapAlloc
0x18006be44  mov     rdi, rax
0x18006be47  test    rax, rax
0x18006be4a  jnz     short loc_18006BE6E
0x18006be4c  mov     rcx, [rbp+5B8h]; this
0x18006be53  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18006be5a  mov     ebx, 8007000Eh
0x18006be5f  mov     edx, 1BEh; void *
0x18006be64  mov     r9d, ebx; char *
0x18006be67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006be6c  jmp     short loc_18006BED1
0x18006be6e  mov     [rsp+6B0h+lpOverlapped], 0; lpOverlapped
0x18006be77  lea     rax, [rsp+6B0h+BytesReturned]
0x18006be7c  mov     [rsp+6B0h+hTemplateFile], rax; lpBytesReturned
0x18006be81  xor     r9d, r9d; nInBufferSize
0x18006be84  mov     [rsp+6B0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x18006be89  xor     r8d, r8d; lpInBuffer
0x18006be8c  mov     edx, 70050h; dwIoControlCode
0x18006be91  mov     qword ptr [rsp+6B0h+dwCreationDisposition], rdi; lpOutBuffer
0x18006be96  mov     rcx, rbx; hDevice
0x18006be99  call    cs:__imp_DeviceIoControl
0x18006be9f  test    eax, eax
0x18006bea1  jnz     short loc_18006BEE0
0x18006bea3  mov     rcx, [rbp+5B8h]; this
0x18006beaa  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18006beb1  mov     edx, 1C4h; void *
0x18006beb6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006bebb  mov     ebx, eax
0x18006bebd  call    cs:__imp_GetProcessHeap
0x18006bec3  mov     r8, rdi; lpMem
0x18006bec6  xor     edx, edx; dwFlags
0x18006bec8  mov     rcx, rax; hHeap
0x18006becb  call    cs:__imp_HeapFree
0x18006bed1  lea     rcx, [rsp+6B0h+pcchLength]
0x18006bed6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006bedb  jmp     loc_18006BD93
0x18006bee0  xor     ecx, ecx
0x18006bee2  cmp     [rdi+4], ecx
0x18006bee5  jbe     short loc_18006BF05
0x18006bee7  mov     rdx, [rsi]
0x18006beea  lea     rax, [rcx+rcx*8]
0x18006beee  inc     rcx
0x18006bef1  shl     rax, 4
0x18006bef5  add     rdx, [rax+rdi+40h]
0x18006befa  mov     [rsi], rdx
0x18006befd  mov     eax, [rdi+4]
0x18006bf00  cmp     rcx, rax
0x18006bf03  jb      short loc_18006BEEA
0x18006bf05  call    cs:__imp_GetProcessHeap
0x18006bf0b  mov     r8, rdi; lpMem
0x18006bf0e  xor     edx, edx; dwFlags
0x18006bf10  mov     rcx, rax; hHeap
0x18006bf13  call    cs:__imp_HeapFree
0x18006bf19  lea     rcx, [rsp+6B0h+pcchLength]
0x18006bf1e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006bf23  xor     eax, eax
0x18006bf25  mov     rcx, [rbp+5B0h+var_20]
0x18006bf2c  xor     rcx, rsp; StackCookie
0x18006bf2f  call    __security_check_cookie
0x18006bf34  lea     r11, [rsp+6B0h+var_10]
0x18006bf3c  mov     rbx, [r11+30h]
0x18006bf40  mov     rsi, [r11+38h]
0x18006bf44  mov     rsp, r11
0x18006bf47  pop     r15
0x18006bf49  pop     rdi
0x18006bf4a  pop     rbp
0x18006bf4b  retn
0x18006bf4c  call    __report_rangecheckfailure
```
