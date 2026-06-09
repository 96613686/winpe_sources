# CDlpHelpersT<CEmptyType>::CalculateHash(ushort const *,WINDLP_RECOVERCRYPTO_HASH_TYPE,uchar *,ulong)

- ea: `0x14000663c`
- end: `0x1400069a0`
- name: `?CalculateHash@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBGW4WINDLP_RECOVERCRYPTO_HASH_TYPE@@PEAEK@Z`
- size: `868`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, __int64, UCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000e878`

## callees

- `0x140006538`
- `0x14000663c`
- `0x1400076c8`
- `0x1400135b8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140006950`
- `KERNEL32!CloseHandle` at `0x140006950`
- `KERNEL32!HeapFree` at `0x140006976`
- `KERNEL32!HeapFree` at `0x140006976`
- `KERNEL32!HeapAlloc` at `0x140006792`
- `KERNEL32!HeapAlloc` at `0x140006792`
- `KERNEL32!GetProcessHeap` at `0x14000677e`
- `KERNEL32!GetProcessHeap` at `0x140006962`
- `KERNEL32!GetProcessHeap` at `0x14000677e`
- `KERNEL32!GetProcessHeap` at `0x140006962`
- `KERNEL32!GetLastError` at `0x1400068dc`
- `KERNEL32!GetLastError` at `0x1400068dc`
- `KERNEL32!ReadFile` at `0x14000685a`
- `KERNEL32!ReadFile` at `0x14000685a`
- `KERNEL32!GetFileSizeEx` at `0x140006803`
- `KERNEL32!GetFileSizeEx` at `0x140006803`
- `KERNEL32!CreateFileW` at `0x1400067db`
- `KERNEL32!CreateFileW` at `0x1400067db`
- `bcrypt!BCryptFinishHash` at `0x1400068bc`
- `bcrypt!BCryptFinishHash` at `0x1400068bc`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x14000691a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x14000691a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1400066d1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1400066d1`
- `bcrypt!BCryptDestroyHash` at `0x140006933`
- `bcrypt!BCryptDestroyHash` at `0x140006933`
- `bcrypt!BCryptHashData` at `0x14000687d`
- `bcrypt!BCryptHashData` at `0x14000687d`
- `bcrypt!BCryptCreateHash` at `0x140006759`
- `bcrypt!BCryptCreateHash` at `0x140006759`
- `bcrypt!BCryptGetProperty` at `0x140006717`
- `bcrypt!BCryptGetProperty` at `0x140006717`

## pseudocode

```c
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
  DWORD LowPart; // r15d
  HANDLE ProcessHeap; // rax
  LPVOID v15; // rax
  char *FileW; // rax
  union _LARGE_INTEGER i; // rdi
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  BOOL v20; // eax
  signed int LastError; // eax
  HANDLE v22; // rax
  UCHAR pbOutput[8]; // [rsp+48h] [rbp-39h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-31h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-29h] BYREF
  ULONG pcbResult; // [rsp+60h] [rbp-21h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+68h] [rbp-19h] BYREF
  LPVOID v29; // [rsp+70h] [rbp-11h]
  __int64 v30; // [rsp+78h] [rbp-9h]
  _OVERLAPPED Overlapped; // [rsp+80h] [rbp-1h] BYREF
  __int64 v32; // [rsp+A0h] [rbp+1Fh]
  DWORD NumberOfBytesRead; // [rsp+F0h] [rbp+6Fh] BYREF
  unsigned int v34; // [rsp+100h] [rbp+7Fh] BYREF

  v32 = -2;
  v5 = 0;
  v29 = 0;
  NumberOfBytesRead = 0;
  v6 = -1;
  v30 = -1;
  v7 = 0;
  FileSize.QuadPart = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  phHash = 0;
  phAlgorithm = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  v34 = 0;
  if ( !lpFileName || !a3 )
    goto LABEL_2;
  v10 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", 0, 0);
  if ( !SErrorConverterT<CEmptyType>::C_NtStatus2HR(v10, &v34) )
    goto LABEL_5;
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
  if ( !SErrorConverterT<CEmptyType>::C_NtStatus2HR(Property, &v34) )
    goto LABEL_5;
  if ( *(_DWORD *)pbOutput != 20 )
  {
LABEL_2:
    v8 = 2147942487LL;
    v9 = -2147024809;
LABEL_28:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_29;
  }
  v12 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
  if ( !SErrorConverterT<CEmptyType>::C_NtStatus2HR(v12, &v34) )
  {
LABEL_5:
    v9 = v34;
LABEL_27:
    v8 = v9;
    goto LABEL_28;
  }
  LowPart = 0x100000;
  ProcessHeap = GetProcessHeap();
  v15 = HeapAlloc(ProcessHeap, 0, 0x100000u);
  v5 = v15;
  if ( !v15 )
  {
    v5 = 0;
    v9 = -2147024882;
    goto LABEL_27;
  }
  v29 = v15;
  FileW = (char *)CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x8000000u, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL
    || (v6 = (__int64)FileW, v30 = (__int64)FileW, !GetFileSizeEx(FileW, &FileSize)) )
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
    if ( !SErrorConverterT<CEmptyType>::C_NtStatus2HR(v18, &v34) )
      goto LABEL_5;
    v7 += NumberOfBytesRead;
  }
  v19 = BCryptFinishHash(phHash, a3, 0x14u, 0);
  v20 = SErrorConverterT<CEmptyType>::C_NtStatus2HR(v19, &v34);
  v9 = v34;
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
0x14000663c  mov     rax, rsp
0x14000663f  mov     [rax+20h], r9d
0x140006643  mov     [rax+10h], edx
0x140006646  push    rbp
0x140006647  push    rsi
0x140006648  push    rdi
0x140006649  push    r12
0x14000664b  push    r13
0x14000664d  push    r14
0x14000664f  push    r15
0x140006651  lea     rbp, [rax-5Fh]
0x140006655  sub     rsp, 0A0h
0x14000665c  mov     [rbp+57h+var_38], 0FFFFFFFFFFFFFFFEh
0x140006664  mov     [rax+8], rbx
0x140006668  mov     r12, r8
0x14000666b  mov     rdi, rcx
0x14000666e  xor     r13d, r13d
0x140006671  mov     esi, r13d
0x140006674  mov     [rbp+57h+var_68], r13
0x140006678  mov     [rbp+57h+NumberOfBytesRead], r13d
0x14000667c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140006680  mov     [rbp+57h+var_60], rbx
0x140006684  mov     r14d, r13d
0x140006687  mov     qword ptr [rbp+57h+FileSize], r13
0x14000668b  xorps   xmm0, xmm0
0x14000668e  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x140006692  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x140006696  mov     [rbp+57h+phHash], r13
0x14000669a  mov     [rbp+57h+phAlgorithm], r13
0x14000669e  mov     dword ptr [rbp+57h+pbOutput], r13d
0x1400066a2  mov     [rbp+57h+var_78], r13d
0x1400066a6  mov     [rbp+57h+arg_18], r13d
0x1400066aa  test    rcx, rcx
0x1400066ad  jnz     short loc_1400066BB
0x1400066af  mov     ecx, 80070057h
0x1400066b4  mov     edi, ecx
0x1400066b6  jmp     loc_140006902
0x1400066bb  test    r12, r12
0x1400066be  jz      short loc_1400066AF
0x1400066c0  xor     r9d, r9d; dwFlags
0x1400066c3  xor     r8d, r8d; pszImplementation
0x1400066c6  lea     rdx, pszAlgId; "SHA1"
0x1400066cd  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x1400066d1  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400066d8  nop     dword ptr [rax+rax+00h]
0x1400066dd  mov     ecx, eax
0x1400066df  lea     rdx, [rbp+57h+arg_18]
0x1400066e3  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x1400066e8  test    eax, eax
0x1400066ea  jnz     short loc_1400066F4
0x1400066ec  mov     edi, [rbp+57h+arg_18]
0x1400066ef  jmp     loc_140006900
0x1400066f4  mov     [rsp+0D0h+dwFlags], r13d; dwFlags
0x1400066f9  lea     rax, [rbp+57h+var_78]
0x1400066fd  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x140006702  mov     r9d, 4; cbOutput
0x140006708  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x14000670c  lea     rdx, pszProperty; "HashDigestLength"
0x140006713  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x140006717  call    cs:__imp_BCryptGetProperty
0x14000671e  nop     dword ptr [rax+rax+00h]
0x140006723  mov     ecx, eax
0x140006725  lea     rdx, [rbp+57h+arg_18]
0x140006729  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x14000672e  test    eax, eax
0x140006730  jz      short loc_1400066EC
0x140006732  cmp     dword ptr [rbp+57h+pbOutput], 14h
0x140006736  jnz     loc_1400066AF
0x14000673c  mov     [rsp+30h], r13d; dwFlags
0x140006741  mov     [rsp+0D0h+dwFlags], r13d; cbSecret
0x140006746  mov     [rsp+0D0h+pcbResult], r13; pbSecret
0x14000674b  xor     r9d, r9d; cbHashObject
0x14000674e  xor     r8d, r8d; pbHashObject
0x140006751  lea     rdx, [rbp+57h+phHash]; phHash
0x140006755  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x140006759  call    cs:__imp_BCryptCreateHash
0x140006760  nop     dword ptr [rax+rax+00h]
0x140006765  mov     ecx, eax
0x140006767  lea     rdx, [rbp+57h+arg_18]
0x14000676b  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x140006770  test    eax, eax
0x140006772  jz      loc_1400066EC
0x140006778  mov     r15d, 100000h
0x14000677e  call    cs:__imp_GetProcessHeap
0x140006785  nop     dword ptr [rax+rax+00h]
0x14000678a  mov     rcx, rax; hHeap
0x14000678d  mov     r8d, r15d; dwBytes
0x140006790  xor     edx, edx; dwFlags
0x140006792  call    cs:__imp_HeapAlloc
0x140006799  nop     dword ptr [rax+rax+00h]
0x14000679e  mov     rsi, rax
0x1400067a1  test    rax, rax
0x1400067a4  jnz     short loc_1400067B3
0x1400067a6  mov     rsi, r13
0x1400067a9  mov     edi, 8007000Eh
0x1400067ae  jmp     loc_140006900
0x1400067b3  mov     [rbp+57h+var_68], rsi
0x1400067b7  mov     [rsp+30h], r13; hTemplateFile
0x1400067bc  mov     [rsp+0D0h+dwFlags], 8000000h; dwFlagsAndAttributes
0x1400067c4  mov     dword ptr [rsp+0D0h+pcbResult], 3; dwCreationDisposition
0x1400067cc  xor     r9d, r9d; lpSecurityAttributes
0x1400067cf  mov     edx, 80000000h; dwDesiredAccess
0x1400067d4  lea     r8d, [r9+7]; dwShareMode
0x1400067d8  mov     rcx, rdi; lpFileName
0x1400067db  call    cs:__imp_CreateFileW
0x1400067e2  nop     dword ptr [rax+rax+00h]
0x1400067e7  lea     rcx, [rax-1]
0x1400067eb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1400067ef  ja      loc_1400068DC
0x1400067f5  mov     rbx, rax
0x1400067f8  mov     [rbp+57h+var_60], rax
0x1400067fc  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x140006800  mov     rcx, rax; hFile
0x140006803  call    cs:__imp_GetFileSizeEx
0x14000680a  nop     dword ptr [rax+rax+00h]
0x14000680f  test    eax, eax
0x140006811  jz      loc_1400068DC
0x140006817  mov     rdi, qword ptr [rbp+57h+FileSize]
0x14000681b  jmp     loc_1400068A5
0x140006820  mov     eax, r15d
0x140006823  cmp     rax, rdi
0x140006826  cmovg   r15d, edi
0x14000682a  mov     [rbp+57h+Overlapped.Internal], r13
0x14000682e  mov     [rbp+57h+Overlapped.InternalHigh], r13
0x140006832  mov     [rbp+57h+Overlapped.hEvent], r13
0x140006836  mov     dword ptr [rbp+57h+Overlapped.10h], r14d
0x14000683a  mov     rax, r14
0x14000683d  shr     rax, 20h
0x140006841  mov     dword ptr [rbp+57h+Overlapped.10h+4], eax
0x140006844  lea     rax, [rbp+57h+Overlapped]
0x140006848  mov     [rsp+0D0h+pcbResult], rax; lpOverlapped
0x14000684d  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140006851  mov     r8d, r15d; nNumberOfBytesToRead
0x140006854  mov     rdx, rsi; lpBuffer
0x140006857  mov     rcx, rbx; hFile
0x14000685a  call    cs:__imp_ReadFile
0x140006861  nop     dword ptr [rax+rax+00h]
0x140006866  test    eax, eax
0x140006868  jz      short loc_1400068DC
0x14000686a  mov     r8d, [rbp+57h+NumberOfBytesRead]; cbInput
0x14000686e  cmp     r15d, r8d
0x140006871  jnz     short loc_1400068EE
0x140006873  xor     r9d, r9d; dwFlags
0x140006876  mov     rdx, rsi; pbInput
0x140006879  mov     rcx, [rbp+57h+phHash]; hHash
0x14000687d  call    cs:__imp_BCryptHashData
0x140006884  nop     dword ptr [rax+rax+00h]
0x140006889  mov     ecx, eax
0x14000688b  lea     rdx, [rbp+57h+arg_18]
0x14000688f  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x140006894  test    eax, eax
0x140006896  jz      loc_1400066EC
0x14000689c  mov     eax, [rbp+57h+NumberOfBytesRead]
0x14000689f  add     r14, rax
0x1400068a2  sub     rdi, rax
0x1400068a5  test    rdi, rdi
0x1400068a8  jg      loc_140006820
0x1400068ae  xor     r9d, r9d; dwFlags
0x1400068b1  lea     r8d, [r9+14h]; cbOutput
0x1400068b5  mov     rdx, r12; pbOutput
0x1400068b8  mov     rcx, [rbp+57h+phHash]; hHash
0x1400068bc  call    cs:__imp_BCryptFinishHash
0x1400068c3  nop     dword ptr [rax+rax+00h]
0x1400068c8  mov     ecx, eax
0x1400068ca  lea     rdx, [rbp+57h+arg_18]
0x1400068ce  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x1400068d3  mov     edi, [rbp+57h+arg_18]
0x1400068d6  test    eax, eax
0x1400068d8  jz      short loc_140006900
0x1400068da  jmp     short loc_140006907
0x1400068dc  call    cs:__imp_GetLastError
0x1400068e3  nop     dword ptr [rax+rax+00h]
0x1400068e8  mov     edi, eax
0x1400068ea  test    eax, eax
0x1400068ec  jnz     short loc_1400068F5
0x1400068ee  mov     edi, 80004005h
0x1400068f3  jmp     short loc_140006900
0x1400068f5  jle     short loc_140006900
0x1400068f7  movzx   edi, ax
0x1400068fa  or      edi, 80070000h
0x140006900  mov     ecx, edi
0x140006902  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140006907  mov     ecx, edi
0x140006909  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000690e  nop
0x14000690f  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x140006913  test    rcx, rcx
0x140006916  jz      short loc_14000692A
0x140006918  xor     edx, edx; dwFlags
0x14000691a  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140006921  nop     dword ptr [rax+rax+00h]
0x140006926  mov     [rbp+57h+phAlgorithm], r13
0x14000692a  mov     rcx, [rbp+57h+phHash]; hHash
0x14000692e  test    rcx, rcx
0x140006931  jz      short loc_140006943
0x140006933  call    cs:__imp_BCryptDestroyHash
0x14000693a  nop     dword ptr [rax+rax+00h]
0x14000693f  mov     [rbp+57h+phHash], r13
0x140006943  lea     rax, [rbx-1]
0x140006947  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000694b  ja      short loc_14000695D
0x14000694d  mov     rcx, rbx; hObject
0x140006950  call    cs:__imp_CloseHandle
0x140006957  nop     dword ptr [rax+rax+00h]
0x14000695c  nop
0x14000695d  test    rsi, rsi
0x140006960  jz      short loc_140006982
0x140006962  call    cs:__imp_GetProcessHeap
0x140006969  nop     dword ptr [rax+rax+00h]
0x14000696e  mov     rcx, rax; hHeap
0x140006971  mov     r8, rsi; lpMem
0x140006974  xor     edx, edx; dwFlags
0x140006976  call    cs:__imp_HeapFree
0x14000697d  nop     dword ptr [rax+rax+00h]
0x140006982  mov     eax, edi
0x140006984  mov     rbx, [rsp+0D0h+arg_0]
0x14000698c  add     rsp, 0A0h
0x140006993  pop     r15
0x140006995  pop     r14
0x140006997  pop     r13
0x140006999  pop     r12
0x14000699b  pop     rdi
0x14000699c  pop     rsi
0x14000699d  pop     rbp
0x14000699e  retn
```
