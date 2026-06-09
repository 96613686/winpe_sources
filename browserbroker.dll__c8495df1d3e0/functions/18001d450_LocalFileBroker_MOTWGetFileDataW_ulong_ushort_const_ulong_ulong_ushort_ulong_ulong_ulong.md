# LocalFileBroker::MOTWGetFileDataW(ulong,ushort const *,ulong,ulong,ushort *,ulong *,ulong *,ulong *)

- ea: `0x18001d450`
- end: `0x18001d730`
- name: `?MOTWGetFileDataW@LocalFileBroker@@UEAAJKPEBGKKPEAGPEAK22@Z`
- size: `736`
- prototype: `int(LocalFileBroker *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, unsigned int, unsigned __int16 *, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006cc4`
- `0x18000e428`
- `0x18001d450`
- `0x18001e08c`
- `0x18001e468`
- `0x1800211c0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d54b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d69b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d6ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d54b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d69b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d6ed`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001d618`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001d618`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18001d53c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18001d53c`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18001d67f`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18001d67f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001d6e5`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001d6e5`
- `urlmon!CoInternetCreateSecurityManager` at `0x18001d5ab`
- `urlmon!CoInternetCreateSecurityManager` at `0x18001d5ab`
- `MPR!WNetGetConnectionW` at `0x18001d56d`
- `MPR!WNetGetConnectionW` at `0x18001d56d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LocalFileBroker::MOTWGetFileDataW(
        LocalFileBroker *this,
        int a2,
        const unsigned __int16 *a3,
        int a4,
        DWORD cchBuffer,
        unsigned __int16 *lpFileInformation,
        char *FilePart,
        LPDWORD lpnLength,
        unsigned int *a9)
{
  char *v12; // rsi
  unsigned int *v13; // r12
  unsigned int *v14; // r15
  unsigned int PIC; // ebx
  int v16; // edi
  int v17; // edi
  int v18; // edi
  int v19; // edi
  int v20; // edi
  int v21; // edi
  DWORD v22; // eax
  HRESULT SecurityManager; // ebx
  DWORD FileAttributesW; // r12d
  signed int v25; // eax
  signed int LastError; // eax
  unsigned __int64 v28; // rax
  int v29; // ecx

  v12 = FilePart;
  *(_DWORD *)FilePart = 0;
  v13 = lpnLength;
  *lpnLength = 0;
  v14 = a9;
  *a9 = 5;
  LODWORD(FilePart) = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(2, (unsigned int *)&FilePart);
  if ( (PIC & 0x80000000) != 0 )
    return PIC;
  if ( !a2 )
  {
    FilePart = 0;
    if ( !(unsigned __int8)FileAccessAllowed(a3) )
      return PIC;
    *(_DWORD *)v12 = GetFullPathNameW(a3, cchBuffer, lpFileInformation, (LPWSTR *)&FilePart);
    *v14 = GetLastError();
    if ( *(_DWORD *)v12 && *(_DWORD *)v12 <= cchBuffer )
    {
      if ( FilePart )
      {
        v28 = (FilePart - (char *)lpFileInformation) >> 1;
        v29 = v28;
        if ( v28 > 0xFFFFFFFF )
          v29 = -1;
        *v13 = v29;
        return v28 > 0xFFFFFFFF ? 0x80070216 : 0;
      }
      return PIC;
    }
LABEL_42:
    LastError = GetLastError();
    PIC = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return PIC;
  }
  v16 = a2 - 1;
  if ( !v16 )
  {
    if ( !(unsigned __int8)FileAccessAllowed(a3) )
      return PIC;
    *(_DWORD *)v12 = GetLongPathNameW(a3, lpFileInformation, cchBuffer);
    *v14 = GetLastError();
    if ( *(_DWORD *)v12 )
    {
      if ( *(_DWORD *)v12 <= cchBuffer )
        return PIC;
    }
    goto LABEL_42;
  }
  v17 = v16 - 1;
  if ( v17 )
  {
    v18 = v17 - 1;
    if ( !v18 )
      goto LABEL_19;
    v19 = v18 - 1;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( v21 )
        {
          if ( v21 != 1 )
            return (unsigned int)-2147418113;
          *v14 = 0;
          FileIsWebDav(a3, v12);
          return 0;
        }
        v22 = IEIsLowIntegrityFile(a3);
        *(_DWORD *)v12 = v22 == 0;
        *v13 = 0;
LABEL_20:
        *v14 = v22;
        return 0;
      }
      if ( (unsigned __int8)FileAccessAllowed(a3) )
      {
        if ( !a4 && cchBuffer == 18 )
          *(_DWORD *)v12 = GetFileAttributesExW(a3, GetFileExInfoStandard, lpFileInformation);
        *v14 = GetLastError();
        if ( !*(_DWORD *)v12 )
          GetLastError();
      }
LABEL_19:
      *v13 = cchBuffer;
      *(_DWORD *)v12 = WNetGetConnectionW(a3, lpFileInformation, v13);
      v22 = GetLastError();
      goto LABEL_20;
    }
    if ( (unsigned __int8)FileAccessAllowed(a3) )
    {
      LODWORD(FilePart) = 0;
      lpnLength = 0;
      SecurityManager = CoInternetCreateSecurityManager(0, (IInternetSecurityManager **)&lpnLength, 0);
      if ( SecurityManager >= 0 )
      {
        (*(void (__fastcall **)(LPDWORD, const unsigned __int16 *, char **, _QWORD))(*(_QWORD *)lpnLength + 40LL))(
          lpnLength,
          a3,
          &FilePart,
          0);
        if ( (_DWORD)FilePart == -1 )
        {
          SecurityManager = -2147024891;
        }
        else
        {
          *(_DWORD *)v12 = (_DWORD)FilePart;
          SecurityManager = 0;
        }
      }
      ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&lpnLength);
    }
    else
    {
      SecurityManager = -2147024891;
    }
    *v13 = SecurityManager;
    *v14 = 0;
    return 0;
  }
  else
  {
    *(_DWORD *)v12 = -1;
    FileAttributesW = GetFileAttributesW(a3);
    v25 = GetLastError();
    *v14 = v25;
    if ( FileAttributesW == -1 )
    {
      if ( v25 > 0 )
        PIC = (unsigned __int16)v25 | 0x80070000;
      else
        PIC = v25;
    }
    else
    {
      if ( (unsigned __int8)FileAccessAllowed(a3) )
      {
        *(_DWORD *)v12 = FileAttributesW;
        return PIC;
      }
      if ( (FileAttributesW & 0x10) != 0 )
      {
        *(_DWORD *)v12 = 16;
        return PIC;
      }
    }
    *v14 = 5;
  }
  return PIC;
}

```

## disassembly

```asm
0x18001d450  push    rbp
0x18001d452  push    rbx
0x18001d453  push    rsi
0x18001d454  push    rdi
0x18001d455  push    r12
0x18001d457  push    r13
0x18001d459  push    r14
0x18001d45b  push    r15
0x18001d45d  mov     rbp, rsp
0x18001d460  sub     rsp, 38h
0x18001d464  mov     r13d, r9d
0x18001d467  mov     r14, r8
0x18001d46a  mov     edi, edx
0x18001d46c  xor     eax, eax
0x18001d46e  mov     rsi, [rbp+FilePart]
0x18001d472  mov     [rsi], eax
0x18001d474  mov     r12, [rbp+lpnLength]
0x18001d47b  mov     [r12], eax
0x18001d47f  mov     r15, [rbp+arg_40]
0x18001d486  mov     dword ptr [r15], 5
0x18001d48d  mov     dword ptr [rbp+FilePart], eax
0x18001d490  lea     rdx, [rbp+FilePart]; unsigned int *
0x18001d494  lea     ecx, [rax+2]; unsigned int
0x18001d497  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x18001d49c  mov     ebx, eax
0x18001d49e  test    eax, eax
0x18001d4a0  js      loc_18001D6B0
0x18001d4a6  test    edi, edi
0x18001d4a8  jz      loc_18001D6C3
0x18001d4ae  sub     edi, 1
0x18001d4b1  jz      loc_18001D668
0x18001d4b7  sub     edi, 1
0x18001d4ba  jz      loc_18001D60E
0x18001d4c0  mov     ebx, [rbp+cchBuffer]
0x18001d4c3  sub     edi, 1
0x18001d4c6  jz      loc_18001D55F
0x18001d4cc  sub     edi, 1
0x18001d4cf  jz      loc_18001D585
0x18001d4d5  sub     edi, 1
0x18001d4d8  jz      short loc_18001D51D
0x18001d4da  sub     edi, 1
0x18001d4dd  jz      short loc_18001D502
0x18001d4df  cmp     edi, 1
0x18001d4e2  jz      short loc_18001D4EE
0x18001d4e4  mov     ebx, 8000FFFFh
0x18001d4e9  jmp     loc_18001D6B0
0x18001d4ee  mov     dword ptr [r15], 0
0x18001d4f5  mov     rdx, rsi
0x18001d4f8  mov     rcx, r14
0x18001d4fb  call    _FileIsWebDav
0x18001d500  jmp     short loc_18001D57E
0x18001d502  mov     rcx, r14; unsigned __int16 *
0x18001d505  call    ?IEIsLowIntegrityFile@@YAJPEBG@Z; IEIsLowIntegrityFile(ushort const *)
0x18001d50a  xor     ecx, ecx
0x18001d50c  test    eax, eax
0x18001d50e  setz    cl
0x18001d511  mov     [rsi], ecx
0x18001d513  mov     dword ptr [r12], 0
0x18001d51b  jmp     short loc_18001D57B
0x18001d51d  mov     rcx, r14
0x18001d520  call    _FileAccessAllowed
0x18001d525  test    al, al
0x18001d527  jz      short loc_18001D55F
0x18001d529  test    r13d, r13d
0x18001d52c  jnz     short loc_18001D54B
0x18001d52e  cmp     ebx, 12h
0x18001d531  jnz     short loc_18001D54B
0x18001d533  mov     r8, [rbp+lpFileInformation]; lpFileInformation
0x18001d537  xor     edx, edx; fInfoLevelId
0x18001d539  mov     rcx, r14; lpFileName
0x18001d53c  call    cs:__imp_GetFileAttributesExW
0x18001d542  xor     ecx, ecx
0x18001d544  test    eax, eax
0x18001d546  setnz   cl
0x18001d549  mov     [rsi], ecx
0x18001d54b  call    cs:__imp_GetLastError
0x18001d551  mov     [r15], eax
0x18001d554  cmp     dword ptr [rsi], 0
0x18001d557  jnz     short loc_18001D55F
0x18001d559  call    cs:__imp_GetLastError
0x18001d55f  mov     [r12], ebx
0x18001d563  mov     r8, r12; lpnLength
0x18001d566  mov     rdx, [rbp+lpFileInformation]; lpRemoteName
0x18001d56a  mov     rcx, r14; lpLocalName
0x18001d56d  call    cs:__imp_WNetGetConnectionW
0x18001d573  mov     [rsi], eax
0x18001d575  call    cs:__imp_GetLastError
0x18001d57b  mov     [r15], eax
0x18001d57e  xor     ebx, ebx
0x18001d580  jmp     loc_18001D6B0
0x18001d585  mov     rcx, r14
0x18001d588  call    _FileAccessAllowed
0x18001d58d  xor     r13d, r13d
0x18001d590  test    al, al
0x18001d592  jz      short loc_18001D5FA
0x18001d594  mov     dword ptr [rbp+FilePart], r13d
0x18001d598  mov     [rbp+lpnLength], r13
0x18001d59f  xor     r8d, r8d; dwReserved
0x18001d5a2  lea     rdx, [rbp+lpnLength]; ppSM
0x18001d5a9  xor     ecx, ecx; pSP
0x18001d5ab  call    cs:__imp_CoInternetCreateSecurityManager
0x18001d5b1  mov     ebx, eax
0x18001d5b3  test    eax, eax
0x18001d5b5  js      short loc_18001D5EC
0x18001d5b7  mov     rcx, [rbp+lpnLength]
0x18001d5be  mov     rax, [rcx]
0x18001d5c1  xor     r9d, r9d
0x18001d5c4  lea     r8, [rbp+FilePart]
0x18001d5c8  mov     rdx, r14
0x18001d5cb  mov     rax, [rax+28h]
0x18001d5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5d4  mov     eax, dword ptr [rbp+FilePart]
0x18001d5d7  mov     edi, 0FFFFFFFFh
0x18001d5dc  cmp     eax, edi
0x18001d5de  jz      short loc_18001D5E7
0x18001d5e0  mov     [rsi], eax
0x18001d5e2  mov     ebx, r13d
0x18001d5e5  jmp     short loc_18001D5EC
0x18001d5e7  mov     ebx, 80070005h
0x18001d5ec  lea     rcx, [rbp+lpnLength]
0x18001d5f3  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x18001d5f8  jmp     short loc_18001D5FF
0x18001d5fa  mov     ebx, 80070005h
0x18001d5ff  mov     [r12], ebx
0x18001d603  mov     [r15], r13d
0x18001d606  mov     ebx, r13d
0x18001d609  jmp     loc_18001D6B0
0x18001d60e  mov     edi, 0FFFFFFFFh
0x18001d613  mov     [rsi], edi
0x18001d615  mov     rcx, r14; lpFileName
0x18001d618  call    cs:__imp_GetFileAttributesW
0x18001d61e  mov     r12d, eax
0x18001d621  call    cs:__imp_GetLastError
0x18001d627  mov     [r15], eax
0x18001d62a  cmp     r12d, edi
0x18001d62d  jnz     short loc_18001D649
0x18001d62f  test    eax, eax
0x18001d631  jg      short loc_18001D63E
0x18001d633  mov     ebx, eax
0x18001d635  mov     dword ptr [r15], 5
0x18001d63c  jmp     short loc_18001D6B0
0x18001d63e  movzx   ebx, ax
0x18001d641  or      ebx, 80070000h
0x18001d647  jmp     short loc_18001D635
0x18001d649  mov     rcx, r14
0x18001d64c  call    _FileAccessAllowed
0x18001d651  test    al, al
0x18001d653  jz      short loc_18001D65A
0x18001d655  mov     [rsi], r12d
0x18001d658  jmp     short loc_18001D6B0
0x18001d65a  test    r12b, 10h
0x18001d65e  jz      short loc_18001D635
0x18001d660  mov     dword ptr [rsi], 10h
0x18001d666  jmp     short loc_18001D6B0
0x18001d668  mov     rcx, r14
0x18001d66b  call    _FileAccessAllowed
0x18001d670  test    al, al
0x18001d672  jz      short loc_18001D6B0
0x18001d674  mov     r8d, [rbp+cchBuffer]; cchBuffer
0x18001d678  mov     rdx, [rbp+lpFileInformation]; lpszLongPath
0x18001d67c  mov     rcx, r14; lpszShortPath
0x18001d67f  call    cs:__imp_GetLongPathNameW
0x18001d685  mov     [rsi], eax
0x18001d687  call    cs:__imp_GetLastError
0x18001d68d  mov     [r15], eax
0x18001d690  mov     eax, [rsi]
0x18001d692  test    eax, eax
0x18001d694  jz      short loc_18001D69B
0x18001d696  cmp     eax, [rbp+cchBuffer]
0x18001d699  jbe     short loc_18001D6B0
0x18001d69b  call    cs:__imp_GetLastError
0x18001d6a1  test    eax, eax
0x18001d6a3  mov     ebx, eax
0x18001d6a5  jle     short loc_18001D6B0
0x18001d6a7  movzx   ebx, ax
0x18001d6aa  or      ebx, 80070000h
0x18001d6b0  mov     eax, ebx
0x18001d6b2  add     rsp, 38h
0x18001d6b6  pop     r15
0x18001d6b8  pop     r14
0x18001d6ba  pop     r13
0x18001d6bc  pop     r12
0x18001d6be  pop     rdi
0x18001d6bf  pop     rsi
0x18001d6c0  pop     rbx
0x18001d6c1  pop     rbp
0x18001d6c2  retn
0x18001d6c3  mov     [rbp+FilePart], 0
0x18001d6cb  mov     rcx, r14
0x18001d6ce  call    _FileAccessAllowed
0x18001d6d3  test    al, al
0x18001d6d5  jz      short loc_18001D6B0
0x18001d6d7  lea     r9, [rbp+FilePart]; lpFilePart
0x18001d6db  mov     r8, [rbp+lpFileInformation]; lpBuffer
0x18001d6df  mov     edx, [rbp+cchBuffer]; nBufferLength
0x18001d6e2  mov     rcx, r14; lpFileName
0x18001d6e5  call    cs:__imp_GetFullPathNameW
0x18001d6eb  mov     [rsi], eax
0x18001d6ed  call    cs:__imp_GetLastError
0x18001d6f3  mov     [r15], eax
0x18001d6f6  mov     eax, [rsi]
0x18001d6f8  test    eax, eax
0x18001d6fa  jz      short loc_18001D69B
0x18001d6fc  cmp     eax, [rbp+cchBuffer]
0x18001d6ff  ja      short loc_18001D69B
0x18001d701  mov     rax, [rbp+FilePart]
0x18001d705  test    rax, rax
0x18001d708  jz      short loc_18001D6B0
0x18001d70a  sub     rax, [rbp+lpFileInformation]
0x18001d70e  sar     rax, 1
0x18001d711  mov     edi, 0FFFFFFFFh
0x18001d716  cmp     rax, rdi
0x18001d719  mov     ecx, eax
0x18001d71b  jbe     short loc_18001D71F
0x18001d71d  mov     ecx, edi
0x18001d71f  mov     [r12], ecx
0x18001d723  cmp     rdi, rax
0x18001d726  sbb     ebx, ebx
0x18001d728  and     ebx, 80070216h
0x18001d72e  jmp     short loc_18001D6B0
```
