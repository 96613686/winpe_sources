# udk::CopilotPlusDetection::_GetPhysicalDiskSize(wchar_t const *,_ULARGE_INTEGER *)

- ea: `0x140033184`
- end: `0x1400334a7`
- name: `?_GetPhysicalDiskSize@CopilotPlusDetection@udk@@YAJPEB_WPEAT_ULARGE_INTEGER@@@Z`
- size: `803`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName, const wchar_t *, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x1400205cc`

## callees

- `0x140005240`
- `0x140005560`
- `0x140006210`
- `0x14000f208`
- `0x14002801c`
- `0x140028044`
- `0x140029b90`
- `0x140033184`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140033393`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140033393`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003337f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140033412`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003345a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003337f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140033412`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003345a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140033420`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140033468`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140033420`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140033468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003324f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140033359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003324f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140033359`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400333ee`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400333ee`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1400331fc`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x14003327b`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1400331fc`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x14003327b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140033340`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140033340`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140033245`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140033245`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14003329b`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14003329b`

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
  size_t v8; // rdx
  HRESULT v9; // eax
  unsigned int v10; // ebx
  size_t v11; // rcx
  HANDLE FileW; // rbx
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  unsigned int *v15; // rdi
  const char *v16; // r9
  HANDLE v17; // rax
  unsigned __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rax
  HANDLE v21; // rax
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
  v9 = StringLengthWorkerW(szVolumeName, v8, &pcchLength);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      (const char *)(unsigned int)v9,
      dwCreationDisposition);
    return v10;
  }
  if ( pcchLength && *((_WORD *)&BytesReturned[5] + pcchLength + 1) == 92 )
  {
    v11 = 2 * pcchLength - 2;
    if ( v11 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v11) = 0;
  }
  FileW = CreateFileW(szVolumeName, 0, 1u, 0, 3u, 0x2000000u, 0);
  pcchLength = (size_t)FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_26;
  }
  BytesReturned[0] = 0;
  ProcessHeap = GetProcessHeap();
  v15 = (unsigned int *)HeapAlloc(ProcessHeap, 0, 0x48C0u);
  if ( !v15 )
  {
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      (const char *)0x8007000ELL,
      dwCreationDispositiona);
LABEL_26:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&pcchLength);
    return v10;
  }
  if ( !DeviceIoControl(FileW, 0x70050u, 0, 0, v15, 0x48C0u, BytesReturned, 0) )
  {
    v10 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x1C4,
            (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
            v16);
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v15);
    goto LABEL_26;
  }
  v18 = 0;
  if ( v15[1] )
  {
    v19 = *(_QWORD *)a2;
    do
    {
      v20 = 9 * v18++;
      v19 += *(_QWORD *)&v15[4 * v20 + 16];
      *(_QWORD *)a2 = v19;
    }
    while ( v18 < v15[1] );
  }
  v21 = GetProcessHeap();
  HeapFree(v21, 0, v15);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&pcchLength);
  return 0;
}

```

## disassembly

```asm
0x140033184  mov     [rsp-8+arg_10], rbx
0x140033189  mov     [rsp-8+arg_18], rsi
0x14003318e  push    rbp
0x14003318f  push    rdi
0x140033190  push    r15
0x140033192  lea     rbp, [rsp-5A0h]
0x14003319a  sub     rsp, 6A0h
0x1400331a1  mov     rax, cs:__security_cookie
0x1400331a8  xor     rax, rsp
0x1400331ab  mov     [rbp+5B0h+var_20], rax
0x1400331b2  mov     rsi, rdx
0x1400331b5  mov     qword ptr [rdx], 0
0x1400331bc  mov     rdi, rcx
0x1400331bf  mov     r15d, 208h
0x1400331c5  mov     r8d, r15d; Size
0x1400331c8  lea     rcx, [rsp+6B0h+szVolumeName]; void *
0x1400331cd  xor     edx, edx; Val
0x1400331cf  call    memset_0
0x1400331d4  mov     r8d, r15d; Size
0x1400331d7  lea     rcx, [rbp+5B0h+szVolumePathName]; void *
0x1400331de  xor     edx, edx; Val
0x1400331e0  call    memset_0
0x1400331e5  test    rdi, rdi
0x1400331e8  jz      short loc_140033226
0x1400331ea  mov     ebx, 104h
0x1400331ef  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x1400331f6  mov     r8d, ebx; cchBufferLength
0x1400331f9  mov     rcx, rdi; lpszFileName
0x1400331fc  call    cs:__imp_GetVolumePathNameW
0x140033202  test    eax, eax
0x140033204  jnz     loc_14003328C
0x14003320a  lea     edx, [r15-6Bh]; void *
0x14003320e  mov     rcx, [rbp+5B8h]; this
0x140033215  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x14003321c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140033221  jmp     loc_14003347A
0x140033226  mov     r8, r15; Size
0x140033229  lea     rcx, [rbp+5B0h+Buffer]; void *
0x140033230  xor     edx, edx; Val
0x140033232  call    memset_0
0x140033237  mov     ebx, 104h
0x14003323c  lea     rcx, [rbp+5B0h+Buffer]; lpBuffer
0x140033243  mov     edx, ebx; uSize
0x140033245  call    cs:__imp_GetSystemDirectoryW
0x14003324b  test    eax, eax
0x14003324d  jnz     short loc_14003326A
0x14003324f  call    cs:__imp_GetLastError
0x140033255  test    eax, eax
0x140033257  jle     loc_14003347A
0x14003325d  movzx   eax, ax
0x140033260  or      eax, 80070000h
0x140033265  jmp     loc_14003347A
0x14003326a  mov     r8d, ebx; cchBufferLength
0x14003326d  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x140033274  lea     rcx, [rbp+5B0h+Buffer]; lpszFileName
0x14003327b  call    cs:__imp_GetVolumePathNameW
0x140033281  test    eax, eax
0x140033283  jnz     short loc_14003328C
0x140033285  mov     edx, 1A7h
0x14003328a  jmp     short loc_14003320E
0x14003328c  mov     r8d, ebx; cchBufferLength
0x14003328f  lea     rdx, [rsp+6B0h+szVolumeName]; lpszVolumeName
0x140033294  lea     rcx, [rbp+5B0h+szVolumePathName]; lpszVolumeMountPoint
0x14003329b  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1400332a1  test    eax, eax
0x1400332a3  jnz     short loc_1400332AF
0x1400332a5  mov     edx, 1AAh
0x1400332aa  jmp     loc_14003320E
0x1400332af  lea     r8, [rsp+6B0h+pcchLength]; pcchLength
0x1400332b4  mov     [rsp+6B0h+pcchLength], 0
0x1400332bd  lea     rcx, [rsp+6B0h+szVolumeName]; psz
0x1400332c2  call    StringLengthWorkerW
0x1400332c7  mov     ebx, eax
0x1400332c9  test    eax, eax
0x1400332cb  jns     short loc_1400332EF
0x1400332cd  mov     rcx, [rbp+5B8h]; this
0x1400332d4  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1400332db  mov     r9d, eax; char *
0x1400332de  mov     edx, 1AEh; void *
0x1400332e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400332e8  mov     eax, ebx
0x1400332ea  jmp     loc_14003347A
0x1400332ef  mov     rax, [rsp+6B0h+pcchLength]
0x1400332f4  test    rax, rax
0x1400332f7  jz      short loc_140033319
0x1400332f9  cmp     [rsp+rax*2+6B0h+var_652], 5Ch ; '\'
0x1400332ff  jnz     short loc_140033319
0x140033301  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x140033309  cmp     rcx, r15
0x14003330c  jnb     loc_1400334A1
0x140033312  xor     eax, eax
0x140033314  mov     [rsp+rcx+6B0h+szVolumeName], ax
0x140033319  xor     r9d, r9d; lpSecurityAttributes
0x14003331c  mov     [rsp+6B0h+hTemplateFile], 0; hTemplateFile
0x140033325  mov     [rsp+6B0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x14003332d  lea     rcx, [rsp+6B0h+szVolumeName]; lpFileName
0x140033332  xor     edx, edx; dwDesiredAccess
0x140033334  mov     [rsp+6B0h+dwCreationDisposition], 3; int
0x14003333c  lea     r8d, [r9+1]; dwShareMode
0x140033340  call    cs:__imp_CreateFileW
0x140033346  mov     rbx, rax
0x140033349  mov     [rsp+6B0h+pcchLength], rax
0x14003334e  inc     rax
0x140033351  test    rax, 0FFFFFFFFFFFFFFFEh
0x140033357  jnz     short loc_140033377
0x140033359  call    cs:__imp_GetLastError
0x14003335f  mov     ebx, eax
0x140033361  test    eax, eax
0x140033363  jle     loc_140033426
0x140033369  movzx   ebx, ax
0x14003336c  or      ebx, 80070000h
0x140033372  jmp     loc_140033426
0x140033377  mov     [rsp+6B0h+BytesReturned], 0
0x14003337f  call    cs:__imp_GetProcessHeap
0x140033385  mov     r15d, 48C0h
0x14003338b  xor     edx, edx; dwFlags
0x14003338d  mov     rcx, rax; hHeap
0x140033390  mov     r8d, r15d; dwBytes
0x140033393  call    cs:__imp_HeapAlloc
0x140033399  mov     rdi, rax
0x14003339c  test    rax, rax
0x14003339f  jnz     short loc_1400333C3
0x1400333a1  mov     rcx, [rbp+5B8h]; this
0x1400333a8  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1400333af  mov     ebx, 8007000Eh
0x1400333b4  mov     edx, 1BEh; void *
0x1400333b9  mov     r9d, ebx; char *
0x1400333bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400333c1  jmp     short loc_140033426
0x1400333c3  mov     [rsp+6B0h+lpOverlapped], 0; lpOverlapped
0x1400333cc  lea     rax, [rsp+6B0h+BytesReturned]
0x1400333d1  mov     [rsp+6B0h+hTemplateFile], rax; lpBytesReturned
0x1400333d6  xor     r9d, r9d; nInBufferSize
0x1400333d9  mov     [rsp+6B0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x1400333de  xor     r8d, r8d; lpInBuffer
0x1400333e1  mov     edx, 70050h; dwIoControlCode
0x1400333e6  mov     qword ptr [rsp+6B0h+dwCreationDisposition], rdi; lpOutBuffer
0x1400333eb  mov     rcx, rbx; hDevice
0x1400333ee  call    cs:__imp_DeviceIoControl
0x1400333f4  test    eax, eax
0x1400333f6  jnz     short loc_140033435
0x1400333f8  mov     rcx, [rbp+5B8h]; this
0x1400333ff  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x140033406  mov     edx, 1C4h; void *
0x14003340b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140033410  mov     ebx, eax
0x140033412  call    cs:__imp_GetProcessHeap
0x140033418  mov     r8, rdi; lpMem
0x14003341b  xor     edx, edx; dwFlags
0x14003341d  mov     rcx, rax; hHeap
0x140033420  call    cs:__imp_HeapFree
0x140033426  lea     rcx, [rsp+6B0h+pcchLength]
0x14003342b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140033430  jmp     loc_1400332E8
0x140033435  xor     ecx, ecx
0x140033437  cmp     [rdi+4], ecx
0x14003343a  jbe     short loc_14003345A
0x14003343c  mov     rdx, [rsi]
0x14003343f  lea     rax, [rcx+rcx*8]
0x140033443  inc     rcx
0x140033446  shl     rax, 4
0x14003344a  add     rdx, [rax+rdi+40h]
0x14003344f  mov     [rsi], rdx
0x140033452  mov     eax, [rdi+4]
0x140033455  cmp     rcx, rax
0x140033458  jb      short loc_14003343F
0x14003345a  call    cs:__imp_GetProcessHeap
0x140033460  mov     r8, rdi; lpMem
0x140033463  xor     edx, edx; dwFlags
0x140033465  mov     rcx, rax; hHeap
0x140033468  call    cs:__imp_HeapFree
0x14003346e  lea     rcx, [rsp+6B0h+pcchLength]
0x140033473  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140033478  xor     eax, eax
0x14003347a  mov     rcx, [rbp+5B0h+var_20]
0x140033481  xor     rcx, rsp; StackCookie
0x140033484  call    __security_check_cookie
0x140033489  lea     r11, [rsp+6B0h+var_10]
0x140033491  mov     rbx, [r11+30h]
0x140033495  mov     rsi, [r11+38h]
0x140033499  mov     rsp, r11
0x14003349c  pop     r15
0x14003349e  pop     rdi
0x14003349f  pop     rbp
0x1400334a0  retn
0x1400334a1  call    __report_rangecheckfailure
```
