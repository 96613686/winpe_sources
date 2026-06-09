# CDlpHelpersT<CEmptyType>::CalculateHash(wchar_t const *,WINDLP_RECOVERCRYPTO_HASH_TYPE,uchar *,ulong)

- ea: `0x18003734c`
- end: `0x1800376c3`
- name: `?CalculateHash@?$CDlpHelpersT@VCEmptyType@@@@SAJPEB_WW4WINDLP_RECOVERCRYPTO_HASH_TYPE@@PEAEK@Z`
- size: `887`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18004f0b0`
- `0x180073f2c`

## callees

- `0x1800059d0`
- `0x180037234`
- `0x18003734c`
- `0x180039f90`
- `0x180077664`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180037571`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180037571`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003751a`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003751a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800374f2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800374f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003748f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037679`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003748f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037679`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003768d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003768d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800374a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800374a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800375f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800375f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037667`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037667`
- `bcrypt!BCryptCreateHash` at `0x180037470`
- `bcrypt!BCryptCreateHash` at `0x180037470`
- `bcrypt!BCryptHashData` at `0x180037594`
- `bcrypt!BCryptHashData` at `0x180037594`
- `bcrypt!BCryptDestroyHash` at `0x18003764a`
- `bcrypt!BCryptDestroyHash` at `0x18003764a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180037631`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180037631`
- `bcrypt!BCryptFinishHash` at `0x1800375d3`
- `bcrypt!BCryptFinishHash` at `0x1800375d3`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800373e8`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800373e8`
- `bcrypt!BCryptGetProperty` at `0x18003742e`
- `bcrypt!BCryptGetProperty` at `0x18003742e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDlpHelpersT<CEmptyType>::CalculateHash(LPCWSTR lpFileName, __int64 a2, UCHAR *a3)
{
  void *v5; // rsi
  __int64 v6; // rbx
  char *v7; // r14
  __int64 v8; // rcx
  unsigned int v9; // edi
  NTSTATUS v10; // ecx
  NTSTATUS Property; // eax
  NTSTATUS v12; // eax
  HANDLE ProcessHeap; // rax
  DWORD LowPart; // r15d
  LPVOID v15; // rax
  char *FileW; // rax
  union _LARGE_INTEGER i; // rdi
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  int v20; // eax
  signed int LastError; // eax
  HANDLE v22; // rax
  int v24; // [rsp+48h] [rbp-49h] BYREF
  LPVOID v25; // [rsp+50h] [rbp-41h]
  __int64 v26; // [rsp+58h] [rbp-39h]
  __int64 v27; // [rsp+60h] [rbp-31h]
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp-29h] BYREF
  UCHAR pbOutput[4]; // [rsp+6Ch] [rbp-25h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+70h] [rbp-21h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+78h] [rbp-19h] BYREF
  ULONG pcbResult; // [rsp+80h] [rbp-11h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+88h] [rbp-9h] BYREF
  _OVERLAPPED Overlapped; // [rsp+90h] [rbp-1h] BYREF

  v27 = -2;
  v5 = 0;
  v25 = 0;
  NumberOfBytesRead = 0;
  v6 = -1;
  v26 = -1;
  v7 = 0;
  FileSize.QuadPart = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  phHash = 0;
  phAlgorithm = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  v24 = 0;
  if ( !lpFileName || !a3 )
    goto LABEL_2;
  v10 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( !(unsigned int)SErrorConverter::C_NtStatus2HR(v10, &v24) )
    goto LABEL_5;
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
  if ( !(unsigned int)SErrorConverter::C_NtStatus2HR(Property, &v24) )
    goto LABEL_5;
  if ( *(_DWORD *)pbOutput != 32 )
  {
LABEL_2:
    v8 = 2147942487LL;
    v9 = -2147024809;
LABEL_28:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_29;
  }
  v12 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
  if ( !(unsigned int)SErrorConverter::C_NtStatus2HR(v12, &v24) )
  {
LABEL_5:
    v9 = v24;
LABEL_27:
    v8 = v9;
    goto LABEL_28;
  }
  ProcessHeap = GetProcessHeap();
  LowPart = 0x100000;
  v15 = HeapAlloc(ProcessHeap, 0, 0x100000u);
  v5 = v15;
  if ( !v15 )
  {
    v5 = 0;
    v9 = -2147024882;
    goto LABEL_27;
  }
  v25 = v15;
  FileW = (char *)CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x8000000u, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL
    || (v6 = (__int64)FileW, v26 = (__int64)FileW, !GetFileSizeEx(FileW, &FileSize)) )
  {
LABEL_23:
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
LABEL_24:
      v9 = -2147467259;
    }
    goto LABEL_27;
  }
  for ( i = FileSize; i.QuadPart > 0; i.QuadPart -= NumberOfBytesRead )
  {
    if ( LowPart > i.QuadPart )
      LowPart = i.LowPart;
    Overlapped.Internal = 0;
    Overlapped.InternalHigh = 0;
    Overlapped.hEvent = 0;
    Overlapped.Pointer = v7;
    if ( !ReadFile((HANDLE)v6, v5, LowPart, &NumberOfBytesRead, &Overlapped) )
      goto LABEL_23;
    if ( LowPart != NumberOfBytesRead )
      goto LABEL_24;
    v18 = BCryptHashData(phHash, (PUCHAR)v5, NumberOfBytesRead, 0);
    if ( !(unsigned int)SErrorConverter::C_NtStatus2HR(v18, &v24) )
      goto LABEL_5;
    v7 += NumberOfBytesRead;
  }
  v19 = BCryptFinishHash(phHash, a3, 0x20u, 0);
  v20 = SErrorConverter::C_NtStatus2HR(v19, &v24);
  v9 = v24;
  if ( !v20 )
    goto LABEL_27;
LABEL_29:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    phAlgorithm = 0;
  }
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v6);
  if ( v5 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v5);
  }
  return v9;
}

```

## disassembly

```asm
0x18003734c  mov     rax, rsp
0x18003734f  push    rbp
0x180037350  push    rsi
0x180037351  push    rdi
0x180037352  push    r12
0x180037354  push    r13
0x180037356  push    r14
0x180037358  push    r15
0x18003735a  lea     rbp, [rax-5Fh]
0x18003735e  sub     rsp, 0B0h
0x180037365  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x18003736d  mov     [rax+10h], rbx
0x180037371  mov     rax, cs:__security_cookie
0x180037378  xor     rax, rsp
0x18003737b  mov     [rbp+57h+var_38], rax
0x18003737f  mov     r12, r8
0x180037382  mov     rdi, rcx
0x180037385  xor     r13d, r13d
0x180037388  mov     esi, r13d
0x18003738b  mov     [rbp+57h+var_98], r13
0x18003738f  mov     [rbp+57h+NumberOfBytesRead], r13d
0x180037393  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180037397  mov     [rbp+57h+var_90], rbx
0x18003739b  mov     r14d, r13d
0x18003739e  mov     qword ptr [rbp+57h+FileSize], r13
0x1800373a2  xorps   xmm0, xmm0
0x1800373a5  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x1800373a9  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x1800373ad  mov     [rbp+57h+phHash], r13
0x1800373b1  mov     [rbp+57h+phAlgorithm], r13
0x1800373b5  mov     dword ptr [rbp+57h+pbOutput], r13d
0x1800373b9  mov     [rbp+57h+var_68], r13d
0x1800373bd  mov     [rbp+57h+var_A0], r13d
0x1800373c1  test    rcx, rcx
0x1800373c4  jnz     short loc_1800373D2
0x1800373c6  mov     ecx, 80070057h
0x1800373cb  mov     edi, ecx
0x1800373cd  jmp     loc_180037619
0x1800373d2  test    r12, r12
0x1800373d5  jz      short loc_1800373C6
0x1800373d7  xor     r9d, r9d; dwFlags
0x1800373da  xor     r8d, r8d; pszImplementation
0x1800373dd  lea     rdx, pszAlgId; "SHA256"
0x1800373e4  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x1800373e8  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800373ef  nop     dword ptr [rax+rax+00h]
0x1800373f4  mov     ecx, eax; int
0x1800373f6  lea     rdx, [rbp+57h+var_A0]; int *
0x1800373fa  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x1800373ff  test    eax, eax
0x180037401  jnz     short loc_18003740B
0x180037403  mov     edi, [rbp+57h+var_A0]
0x180037406  jmp     loc_180037617
0x18003740b  mov     [rsp+0E0h+dwFlags], r13d; dwFlags
0x180037410  lea     rax, [rbp+57h+var_68]
0x180037414  mov     [rsp+0E0h+pcbResult], rax; pcbResult
0x180037419  mov     r9d, 4; cbOutput
0x18003741f  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x180037423  lea     rdx, pszProperty; "HashDigestLength"
0x18003742a  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x18003742e  call    cs:__imp_BCryptGetProperty
0x180037435  nop     dword ptr [rax+rax+00h]
0x18003743a  mov     ecx, eax; int
0x18003743c  lea     rdx, [rbp+57h+var_A0]; int *
0x180037440  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x180037445  test    eax, eax
0x180037447  jz      short loc_180037403
0x180037449  cmp     dword ptr [rbp+57h+pbOutput], 20h ; ' '
0x18003744d  jnz     loc_1800373C6
0x180037453  mov     [rsp+30h], r13d; dwFlags
0x180037458  mov     [rsp+0E0h+dwFlags], r13d; cbSecret
0x18003745d  mov     [rsp+0E0h+pcbResult], r13; pbSecret
0x180037462  xor     r9d, r9d; cbHashObject
0x180037465  xor     r8d, r8d; pbHashObject
0x180037468  lea     rdx, [rbp+57h+phHash]; phHash
0x18003746c  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180037470  call    cs:__imp_BCryptCreateHash
0x180037477  nop     dword ptr [rax+rax+00h]
0x18003747c  mov     ecx, eax; int
0x18003747e  lea     rdx, [rbp+57h+var_A0]; int *
0x180037482  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x180037487  test    eax, eax
0x180037489  jz      loc_180037403
0x18003748f  call    cs:__imp_GetProcessHeap
0x180037496  nop     dword ptr [rax+rax+00h]
0x18003749b  mov     rcx, rax; hHeap
0x18003749e  mov     r15d, 100000h
0x1800374a4  mov     r8d, r15d; dwBytes
0x1800374a7  xor     edx, edx; dwFlags
0x1800374a9  call    cs:__imp_HeapAlloc
0x1800374b0  nop     dword ptr [rax+rax+00h]
0x1800374b5  mov     rsi, rax
0x1800374b8  test    rax, rax
0x1800374bb  jnz     short loc_1800374CA
0x1800374bd  mov     rsi, r13
0x1800374c0  mov     edi, 8007000Eh
0x1800374c5  jmp     loc_180037617
0x1800374ca  mov     [rbp+57h+var_98], rsi
0x1800374ce  mov     [rsp+30h], r13; hTemplateFile
0x1800374d3  mov     [rsp+0E0h+dwFlags], 8000000h; dwFlagsAndAttributes
0x1800374db  mov     dword ptr [rsp+0E0h+pcbResult], 3; dwCreationDisposition
0x1800374e3  xor     r9d, r9d; lpSecurityAttributes
0x1800374e6  mov     edx, 80000000h; dwDesiredAccess
0x1800374eb  lea     r8d, [r9+7]; dwShareMode
0x1800374ef  mov     rcx, rdi; lpFileName
0x1800374f2  call    cs:__imp_CreateFileW
0x1800374f9  nop     dword ptr [rax+rax+00h]
0x1800374fe  lea     rcx, [rax-1]
0x180037502  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180037506  ja      loc_1800375F3
0x18003750c  mov     rbx, rax
0x18003750f  mov     [rbp+57h+var_90], rax
0x180037513  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x180037517  mov     rcx, rax; hFile
0x18003751a  call    cs:__imp_GetFileSizeEx
0x180037521  nop     dword ptr [rax+rax+00h]
0x180037526  test    eax, eax
0x180037528  jz      loc_1800375F3
0x18003752e  mov     rdi, qword ptr [rbp+57h+FileSize]
0x180037532  jmp     loc_1800375BC
0x180037537  mov     eax, r15d
0x18003753a  cmp     rax, rdi
0x18003753d  cmovg   r15d, edi
0x180037541  mov     [rbp+57h+Overlapped.Internal], r13
0x180037545  mov     [rbp+57h+Overlapped.InternalHigh], r13
0x180037549  mov     [rbp+57h+Overlapped.hEvent], r13
0x18003754d  mov     dword ptr [rbp+57h+Overlapped.10h], r14d
0x180037551  mov     rax, r14
0x180037554  shr     rax, 20h
0x180037558  mov     dword ptr [rbp+57h+Overlapped.10h+4], eax
0x18003755b  lea     rax, [rbp+57h+Overlapped]
0x18003755f  mov     [rsp+0E0h+pcbResult], rax; lpOverlapped
0x180037564  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180037568  mov     r8d, r15d; nNumberOfBytesToRead
0x18003756b  mov     rdx, rsi; lpBuffer
0x18003756e  mov     rcx, rbx; hFile
0x180037571  call    cs:__imp_ReadFile
0x180037578  nop     dword ptr [rax+rax+00h]
0x18003757d  test    eax, eax
0x18003757f  jz      short loc_1800375F3
0x180037581  mov     r8d, [rbp+57h+NumberOfBytesRead]; cbInput
0x180037585  cmp     r15d, r8d
0x180037588  jnz     short loc_180037605
0x18003758a  xor     r9d, r9d; dwFlags
0x18003758d  mov     rdx, rsi; pbInput
0x180037590  mov     rcx, [rbp+57h+phHash]; hHash
0x180037594  call    cs:__imp_BCryptHashData
0x18003759b  nop     dword ptr [rax+rax+00h]
0x1800375a0  mov     ecx, eax; int
0x1800375a2  lea     rdx, [rbp+57h+var_A0]; int *
0x1800375a6  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x1800375ab  test    eax, eax
0x1800375ad  jz      loc_180037403
0x1800375b3  mov     eax, [rbp+57h+NumberOfBytesRead]
0x1800375b6  add     r14, rax
0x1800375b9  sub     rdi, rax
0x1800375bc  test    rdi, rdi
0x1800375bf  jg      loc_180037537
0x1800375c5  xor     r9d, r9d; dwFlags
0x1800375c8  lea     r8d, [r9+20h]; cbOutput
0x1800375cc  mov     rdx, r12; pbOutput
0x1800375cf  mov     rcx, [rbp+57h+phHash]; hHash
0x1800375d3  call    cs:__imp_BCryptFinishHash
0x1800375da  nop     dword ptr [rax+rax+00h]
0x1800375df  mov     ecx, eax; int
0x1800375e1  lea     rdx, [rbp+57h+var_A0]; int *
0x1800375e5  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x1800375ea  mov     edi, [rbp+57h+var_A0]
0x1800375ed  test    eax, eax
0x1800375ef  jz      short loc_180037617
0x1800375f1  jmp     short loc_18003761E
0x1800375f3  call    cs:__imp_GetLastError
0x1800375fa  nop     dword ptr [rax+rax+00h]
0x1800375ff  mov     edi, eax
0x180037601  test    eax, eax
0x180037603  jnz     short loc_18003760C
0x180037605  mov     edi, 80004005h
0x18003760a  jmp     short loc_180037617
0x18003760c  jle     short loc_180037617
0x18003760e  movzx   edi, ax
0x180037611  or      edi, 80070000h
0x180037617  mov     ecx, edi
0x180037619  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003761e  mov     ecx, edi
0x180037620  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180037625  nop
0x180037626  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x18003762a  test    rcx, rcx
0x18003762d  jz      short loc_180037641
0x18003762f  xor     edx, edx; dwFlags
0x180037631  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180037638  nop     dword ptr [rax+rax+00h]
0x18003763d  mov     [rbp+57h+phAlgorithm], r13
0x180037641  mov     rcx, [rbp+57h+phHash]; hHash
0x180037645  test    rcx, rcx
0x180037648  jz      short loc_18003765A
0x18003764a  call    cs:__imp_BCryptDestroyHash
0x180037651  nop     dword ptr [rax+rax+00h]
0x180037656  mov     [rbp+57h+phHash], r13
0x18003765a  lea     rax, [rbx-1]
0x18003765e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180037662  ja      short loc_180037674
0x180037664  mov     rcx, rbx; hObject
0x180037667  call    cs:__imp_CloseHandle
0x18003766e  nop     dword ptr [rax+rax+00h]
0x180037673  nop
0x180037674  test    rsi, rsi
0x180037677  jz      short loc_180037699
0x180037679  call    cs:__imp_GetProcessHeap
0x180037680  nop     dword ptr [rax+rax+00h]
0x180037685  mov     rcx, rax; hHeap
0x180037688  mov     r8, rsi; lpMem
0x18003768b  xor     edx, edx; dwFlags
0x18003768d  call    cs:__imp_HeapFree
0x180037694  nop     dword ptr [rax+rax+00h]
0x180037699  mov     eax, edi
0x18003769b  mov     rcx, [rbp+57h+var_38]
0x18003769f  xor     rcx, rsp; StackCookie
0x1800376a2  call    __security_check_cookie
0x1800376a7  mov     rbx, [rsp+0E0h+arg_8]
0x1800376af  add     rsp, 0B0h
0x1800376b6  pop     r15
0x1800376b8  pop     r14
0x1800376ba  pop     r13
0x1800376bc  pop     r12
0x1800376be  pop     rdi
0x1800376bf  pop     rsi
0x1800376c0  pop     rbp
0x1800376c1  retn
```
