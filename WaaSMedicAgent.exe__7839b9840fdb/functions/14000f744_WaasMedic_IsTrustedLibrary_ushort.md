# WaasMedic::IsTrustedLibrary(ushort *)

- ea: `0x14000f744`
- end: `0x14000fa35`
- name: `?IsTrustedLibrary@WaasMedic@@YAJPEAG@Z`
- size: `753`
- prototype: `__int64 __fastcall(WCHAR *lpwstrFilename, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x140009580`

## callees

- `0x140002a30`
- `0x14000369c`
- `0x140004290`
- `0x140004670`
- `0x14000b470`
- `0x14000f6f4`
- `0x14000f744`
- `0x14000fa3c`
- `0x140010a24`
- `0x140010c94`
- `0x140010f14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f790`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f7ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f790`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f7ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fa11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fa11`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000f7e9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000f7e9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000f785`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000f785`
- `WINTRUST!WTGetSignatureInfo` at `0x14000f939`
- `WINTRUST!WTGetSignatureInfo` at `0x14000f9ab`
- `WINTRUST!WTGetSignatureInfo` at `0x14000f939`
- `WINTRUST!WTGetSignatureInfo` at `0x14000f9ab`

## string_xrefs

- `0x14000f8ee`: `Library was not in expected path: %s`

## pseudocode

```c
__int64 __fastcall WaasMedic::IsTrustedLibrary(WCHAR *lpwstrFilename, unsigned __int16 *a2)
{
  char *FileW; // rbx
  signed int IsUnderUndockedFolder; // edi
  signed int LastError; // eax
  const unsigned __int16 *v6; // rdx
  bool *v7; // r8
  __int64 v8; // r14
  signed int v9; // eax
  int v10; // eax
  bool *v11; // r8
  int v12; // eax
  __int64 v13; // r9
  int v14; // eax
  WaasMedic *v15; // rcx
  int v16; // eax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-A9h]
  unsigned __int16 v19; // [rsp+40h] [rbp-89h] BYREF
  __int64 v20; // [rsp+48h] [rbp-81h]
  char *v21; // [rsp+50h] [rbp-79h]
  int v22; // [rsp+60h] [rbp-69h] BYREF
  unsigned int v23[20]; // [rsp+64h] [rbp-65h] BYREF
  unsigned int v24; // [rsp+B4h] [rbp-15h]
  _OWORD v25[2]; // [rsp+C0h] [rbp-9h] BYREF

  v20 = -2;
  FileW = 0;
  if ( !lpwstrFilename )
  {
    IsUnderUndockedFolder = -2147467261;
LABEL_7:
    v6 = L"CheckIfFileExists failed for %s.  hr = 0x%08x";
LABEL_8:
    LogLevelW(2u, v6, lpwstrFilename, (unsigned int)IsUnderUndockedFolder);
    goto LABEL_39;
  }
  if ( GetFileAttributesW(lpwstrFilename) == -1 )
  {
    LastError = GetLastError();
    IsUnderUndockedFolder = LastError;
    if ( LastError > 0 )
      IsUnderUndockedFolder = (unsigned __int16)LastError | 0x80070000;
    if ( IsUnderUndockedFolder < 0 )
      goto LABEL_7;
  }
  FileW = (char *)CreateFileW(lpwstrFilename, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v21 = FileW;
  v8 = -1;
  if ( FileW != (char *)-1LL )
  {
    LOBYTE(v19) = 0;
    v10 = WaasMedic::ValidateOriginalFileName(lpwstrFilename, &v19, v7);
    IsUnderUndockedFolder = v10;
    if ( v10 < 0 )
    {
      LogLevelW(
        2u,
        L"An error occured while validating the original file name for %s. Error code was 0x%08x",
        lpwstrFilename,
        (unsigned int)v10);
      goto LABEL_39;
    }
    if ( !(_BYTE)v19 )
    {
      IsUnderUndockedFolder = -2147024319;
      v6 = L"The file name does not match the original name.";
      goto LABEL_8;
    }
    LOBYTE(v19) = 0;
    v12 = WaasMedic::IsInSystemFolder((WaasMedic *)lpwstrFilename, &v19, v11);
    IsUnderUndockedFolder = v12;
    if ( v12 < 0 )
    {
      v13 = (unsigned int)v12;
LABEL_19:
      LogLevelW(2u, L"Error validating the library folder %s: 0x%08x", lpwstrFilename, v13);
      goto LABEL_39;
    }
    if ( !(_BYTE)v19 )
    {
      LOBYTE(v19) = 0;
      memset(v25, 0, sizeof(v25));
      do
        ++v8;
      while ( lpwstrFilename[v8] );
      std::wstring::_Construct<1,unsigned short const *>(v25, lpwstrFilename);
      IsUnderUndockedFolder = WaasMedic::IsUnderUndockedFolder(v25, &v19);
      std::wstring::~wstring(v25);
      if ( IsUnderUndockedFolder < 0 )
      {
        v13 = (unsigned int)IsUnderUndockedFolder;
        goto LABEL_19;
      }
      if ( !(_BYTE)v19 )
      {
        IsUnderUndockedFolder = -2147024735;
        LogLevelW(2u, L"Library was not in expected path: %s", lpwstrFilename);
        goto LABEL_39;
      }
    }
    memset_0(v23, 0, 0x54u);
    v22 = 88;
    v14 = WTGetSignatureInfo(lpwstrFilename, FileW, 6147, &v22, 0, 0);
    IsUnderUndockedFolder = v14;
    if ( v14 < 0 )
    {
      LogLevelW(
        2u,
        L"Could not establish trust with the requested library %s. Error code was 0x%08x",
        lpwstrFilename,
        (unsigned int)v14);
      goto LABEL_39;
    }
    v15 = (WaasMedic *)v23[0];
    if ( v23[0] == 2 )
    {
      LogLevelW(4u, L"First try failed with 'SIGNATURE_STATE_UNSIGNED_POLICY', retrying....");
      IsUnderUndockedFolder = WaasMedic::TimeHelper::SyncSystemTime();
      if ( IsUnderUndockedFolder < 0 )
        goto LABEL_39;
      memset_0(v23, 0, 0x54u);
      v22 = 88;
      v16 = WTGetSignatureInfo(lpwstrFilename, FileW, 6147, &v22, 0, 0);
      IsUnderUndockedFolder = v16;
      if ( v16 < 0 )
      {
        LogLevelW(
          2u,
          L"Could not establish trust with the requested library %s in retry. Error code was 0x%08x",
          lpwstrFilename,
          (unsigned int)v16);
        goto LABEL_39;
      }
      v15 = (WaasMedic *)v23[0];
    }
    if ( (unsigned int)((_DWORD)v15 - 5) <= 1 )
    {
      if ( v24 == 1 || WaasMedic::IsTestSigningEnabled(v15) )
        goto LABEL_39;
      LODWORD(v15) = v23[0];
    }
    dwCreationDisposition[0] = (unsigned int)v15;
    LogLevelW(
      2u,
      L"Unexpected sigInfo for '%s'.  fOSBinary=%d, SignatureState=%d.",
      lpwstrFilename,
      v24,
      *(_QWORD *)dwCreationDisposition);
    IsUnderUndockedFolder = -2147024319;
    goto LABEL_39;
  }
  v9 = GetLastError();
  IsUnderUndockedFolder = v9;
  if ( v9 > 0 )
    IsUnderUndockedFolder = (unsigned __int16)v9 | 0x80070000;
LABEL_39:
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return (unsigned int)IsUnderUndockedFolder;
}

```

## disassembly

```asm
0x14000f744  push    rbp
0x14000f746  push    rbx
0x14000f747  push    rsi
0x14000f748  push    rdi
0x14000f749  push    r14
0x14000f74b  push    r15
0x14000f74d  lea     rbp, [rsp-2Fh]
0x14000f752  sub     rsp, 0F8h
0x14000f759  mov     [rsp+120h+var_D8], 0FFFFFFFFFFFFFFFEh
0x14000f762  mov     rax, cs:__security_cookie
0x14000f769  xor     rax, rsp
0x14000f76c  mov     [rbp+57h+var_40], rax
0x14000f770  mov     rsi, rcx
0x14000f773  xor     r15d, r15d
0x14000f776  mov     ebx, r15d
0x14000f779  test    rcx, rcx
0x14000f77c  jnz     short loc_14000F785
0x14000f77e  mov     edi, 80004003h
0x14000f783  jmp     short loc_14000F7A9
0x14000f785  call    cs:__imp_GetFileAttributesW
0x14000f78b  cmp     eax, 0FFFFFFFFh
0x14000f78e  jnz     short loc_14000F7C5
0x14000f790  call    cs:__imp_GetLastError
0x14000f796  mov     edi, eax
0x14000f798  test    eax, eax
0x14000f79a  jle     short loc_14000F7A5
0x14000f79c  movzx   edi, ax
0x14000f79f  or      edi, 80070000h
0x14000f7a5  test    edi, edi
0x14000f7a7  jns     short loc_14000F7C5
0x14000f7a9  lea     rdx, aCheckiffileexi; "CheckIfFileExists failed for %s.  hr = "...
0x14000f7b0  mov     r9d, edi
0x14000f7b3  mov     r8, rsi
0x14000f7b6  mov     ecx, 2; unsigned __int8
0x14000f7bb  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000f7c0  jmp     loc_14000FA04
0x14000f7c5  mov     [rsp+120h+hTemplateFile], r15; hTemplateFile
0x14000f7ca  mov     [rsp+120h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14000f7d2  mov     [rsp+120h+dwCreationDisposition], 3; dwCreationDisposition
0x14000f7da  xor     r9d, r9d; lpSecurityAttributes
0x14000f7dd  mov     edx, 80000000h; dwDesiredAccess
0x14000f7e2  lea     r8d, [r9+1]; dwShareMode
0x14000f7e6  mov     rcx, rsi; lpFileName
0x14000f7e9  call    cs:__imp_CreateFileW
0x14000f7ef  mov     rbx, rax
0x14000f7f2  mov     [rbp+57h+var_D0], rax
0x14000f7f6  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000f7fa  cmp     rax, r14
0x14000f7fd  jnz     short loc_14000F81D
0x14000f7ff  call    cs:__imp_GetLastError
0x14000f805  mov     edi, eax
0x14000f807  test    eax, eax
0x14000f809  jle     loc_14000FA04
0x14000f80f  movzx   edi, ax
0x14000f812  or      edi, 80070000h
0x14000f818  jmp     loc_14000FA04
0x14000f81d  mov     byte ptr [rsp+120h+var_E0], r15b
0x14000f822  lea     rdx, [rsp+120h+var_E0]; unsigned __int16 *
0x14000f827  mov     rcx, rsi; lpwstrFilename
0x14000f82a  call    ?ValidateOriginalFileName@WaasMedic@@YAJPEBGAEA_N@Z; WaasMedic::ValidateOriginalFileName(ushort const *,bool &)
0x14000f82f  mov     edi, eax
0x14000f831  test    eax, eax
0x14000f833  jns     short loc_14000F844
0x14000f835  mov     r9d, eax
0x14000f838  lea     rdx, aAnErrorOccured; "An error occured while validating the o"...
0x14000f83f  jmp     loc_14000F7B3
0x14000f844  cmp     byte ptr [rsp+120h+var_E0], r15b
0x14000f849  jnz     short loc_14000F85C
0x14000f84b  mov     edi, 80070241h
0x14000f850  lea     rdx, aTheFileNameDoe; "The file name does not match the origin"...
0x14000f857  jmp     loc_14000F7B0
0x14000f85c  mov     byte ptr [rsp+120h+var_E0], r15b
0x14000f861  lea     rdx, [rsp+120h+var_E0]; unsigned __int16 *
0x14000f866  mov     rcx, rsi; this
0x14000f869  call    ?IsInSystemFolder@WaasMedic@@YAJPEBGAEA_N@Z; WaasMedic::IsInSystemFolder(ushort const *,bool &)
0x14000f86e  mov     edi, eax
0x14000f870  test    eax, eax
0x14000f872  jns     short loc_14000F883
0x14000f874  mov     r9d, eax
0x14000f877  lea     rdx, aErrorValidatin; "Error validating the library folder %s:"...
0x14000f87e  jmp     loc_14000F7B3
0x14000f883  cmp     byte ptr [rsp+120h+var_E0], r15b
0x14000f888  jnz     short loc_14000F904
0x14000f88a  mov     byte ptr [rsp+120h+var_E0], r15b
0x14000f88f  xorps   xmm0, xmm0
0x14000f892  movups  [rbp+57h+var_60], xmm0
0x14000f896  xorps   xmm1, xmm1
0x14000f899  movdqu  [rbp+57h+var_50], xmm1
0x14000f89e  inc     r14
0x14000f8a1  cmp     [rsi+r14*2], r15w
0x14000f8a6  jnz     short loc_14000F89E
0x14000f8a8  mov     r8, r14
0x14000f8ab  mov     rdx, rsi
0x14000f8ae  lea     rcx, [rbp+57h+var_60]
0x14000f8b2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000f8b7  nop
0x14000f8b8  lea     rdx, [rsp+120h+var_E0]
0x14000f8bd  lea     rcx, [rbp+57h+var_60]
0x14000f8c1  call    ?IsUnderUndockedFolder@WaasMedic@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z; WaasMedic::IsUnderUndockedFolder(std::wstring const &,bool &)
0x14000f8c6  mov     edi, eax
0x14000f8c8  lea     rcx, [rbp+57h+var_60]; void *
0x14000f8cc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f8d1  mov     eax, edi
0x14000f8d3  shr     eax, 1Fh
0x14000f8d6  test    al, al
0x14000f8d8  jz      short loc_14000F8DF
0x14000f8da  mov     r9d, edi
0x14000f8dd  jmp     short loc_14000F877
0x14000f8df  cmp     byte ptr [rsp+120h+var_E0], r15b
0x14000f8e4  jnz     short loc_14000F904
0x14000f8e6  mov     edi, 800700A1h
0x14000f8eb  mov     r8, rsi
0x14000f8ee  lea     rdx, aLibraryWasNotI; "Library was not in expected path: %s"
0x14000f8f5  mov     ecx, 2; unsigned __int8
0x14000f8fa  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000f8ff  jmp     loc_14000FA04
0x14000f904  mov     r14d, 54h ; 'T'
0x14000f90a  mov     r8d, r14d; Size
0x14000f90d  xor     edx, edx; Val
0x14000f90f  lea     rcx, [rbp+57h+var_BC]; void *
0x14000f913  call    memset_0
0x14000f918  mov     [rbp+57h+var_C0], 58h ; 'X'
0x14000f91f  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], r15
0x14000f924  mov     qword ptr [rsp+120h+dwCreationDisposition], r15
0x14000f929  lea     r9, [rbp+57h+var_C0]
0x14000f92d  mov     r8d, 1803h
0x14000f933  mov     rdx, rbx
0x14000f936  mov     rcx, rsi
0x14000f939  call    cs:__imp_WTGetSignatureInfo
0x14000f93f  mov     edi, eax
0x14000f941  test    eax, eax
0x14000f943  jns     short loc_14000F954
0x14000f945  mov     r9d, eax
0x14000f948  lea     rdx, aCouldNotEstabl; "Could not establish trust with the requ"...
0x14000f94f  jmp     loc_14000F7B3
0x14000f954  mov     ecx, [rbp+57h+var_BC]
0x14000f957  cmp     ecx, 2
0x14000f95a  jnz     short loc_14000F9C9
0x14000f95c  lea     rdx, aFirstTryFailed; "First try failed with 'SIGNATURE_STATE_"...
0x14000f963  mov     ecx, 4; unsigned __int8
0x14000f968  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000f96d  call    ?SyncSystemTime@TimeHelper@WaasMedic@@SAJXZ; WaasMedic::TimeHelper::SyncSystemTime(void)
0x14000f972  mov     edi, eax
0x14000f974  test    eax, eax
0x14000f976  js      loc_14000FA04
0x14000f97c  mov     r8, r14; Size
0x14000f97f  xor     edx, edx; Val
0x14000f981  lea     rcx, [rbp+57h+var_BC]; void *
0x14000f985  call    memset_0
0x14000f98a  mov     [rbp+57h+var_C0], 58h ; 'X'
0x14000f991  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], r15
0x14000f996  mov     qword ptr [rsp+120h+dwCreationDisposition], r15
0x14000f99b  lea     r9, [rbp+57h+var_C0]
0x14000f99f  mov     r8d, 1803h
0x14000f9a5  mov     rdx, rbx
0x14000f9a8  mov     rcx, rsi
0x14000f9ab  call    cs:__imp_WTGetSignatureInfo
0x14000f9b1  mov     edi, eax
0x14000f9b3  test    eax, eax
0x14000f9b5  jns     short loc_14000F9C6
0x14000f9b7  mov     r9d, eax
0x14000f9ba  lea     rdx, aCouldNotEstabl_0; "Could not establish trust with the requ"...
0x14000f9c1  jmp     loc_14000F7B3
0x14000f9c6  mov     ecx, [rbp+57h+var_BC]; this
0x14000f9c9  lea     eax, [rcx-5]
0x14000f9cc  cmp     eax, 1
0x14000f9cf  ja      short loc_14000F9E3
0x14000f9d1  cmp     [rbp+57h+var_6C], 1
0x14000f9d5  jz      short loc_14000FA04
0x14000f9d7  call    ?IsTestSigningEnabled@WaasMedic@@YA_NXZ; WaasMedic::IsTestSigningEnabled(void)
0x14000f9dc  test    al, al
0x14000f9de  jnz     short loc_14000FA04
0x14000f9e0  mov     ecx, [rbp+57h+var_BC]
0x14000f9e3  mov     [rsp+120h+dwCreationDisposition], ecx
0x14000f9e7  mov     r9d, [rbp+57h+var_6C]
0x14000f9eb  mov     r8, rsi
0x14000f9ee  lea     rdx, aUnexpectedSigi; "Unexpected sigInfo for '%s'.  fOSBinary"...
0x14000f9f5  mov     ecx, 2; unsigned __int8
0x14000f9fa  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000f9ff  mov     edi, 80070241h
0x14000fa04  lea     rax, [rbx-1]
0x14000fa08  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000fa0c  ja      short loc_14000FA17
0x14000fa0e  mov     rcx, rbx; hObject
0x14000fa11  call    cs:__imp_CloseHandle
0x14000fa17  mov     eax, edi
0x14000fa19  mov     rcx, [rbp+57h+var_40]
0x14000fa1d  xor     rcx, rsp; StackCookie
0x14000fa20  call    __security_check_cookie
0x14000fa25  add     rsp, 0F8h
0x14000fa2c  pop     r15
0x14000fa2e  pop     r14
0x14000fa30  pop     rdi
0x14000fa31  pop     rsi
0x14000fa32  pop     rbx
0x14000fa33  pop     rbp
0x14000fa34  retn
```
