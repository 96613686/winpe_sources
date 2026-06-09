# WaasMedic::IsTrustedLibrary(ushort *)

- ea: `0x180028bec`
- end: `0x180028ecb`
- name: `?IsTrustedLibrary@WaasMedic@@YAJPEAG@Z`
- size: `735`
- prototype: `__int64 __fastcall(LPCWSTR lpwstrFilename, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18001558c`

## callees

- `0x1800050a0`
- `0x180005bbc`
- `0x1800098f0`
- `0x180009cd0`
- `0x180028b9c`
- `0x180028bec`
- `0x180028f34`
- `0x18002a0a0`
- `0x18002e81c`
- `0x180036ce4`
- `0x180036f70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028c9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028c9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028ea7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028ea7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180028c24`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180028c24`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028c88`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028c88`
- `WINTRUST!WTGetSignatureInfo` at `0x180028dcf`
- `WINTRUST!WTGetSignatureInfo` at `0x180028e41`
- `WINTRUST!WTGetSignatureInfo` at `0x180028dcf`
- `WINTRUST!WTGetSignatureInfo` at `0x180028e41`

## string_xrefs

- `0x180028d84`: `Library was not in expected path: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-99h]
  unsigned __int16 v19; // [rsp+40h] [rbp-79h] BYREF
  char *v20; // [rsp+48h] [rbp-71h]
  int v21; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v22[20]; // [rsp+54h] [rbp-65h] BYREF
  unsigned int v23; // [rsp+A4h] [rbp-15h]
  _OWORD v24[2]; // [rsp+B0h] [rbp-9h] BYREF

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
  v20 = FileW;
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
      memset(v24, 0, sizeof(v24));
      do
        ++v8;
      while ( lpwstrFilename[v8] );
      std::wstring::_Construct<1,unsigned short const *>(v24, lpwstrFilename, v8);
      IsUnderUndockedFolder = WaasMedic::IsUnderUndockedFolder(v24, &v19);
      std::wstring::~wstring(v24);
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
    memset_0(v22, 0, 0x54u);
    v21 = 88;
    v14 = WTGetSignatureInfo(lpwstrFilename, FileW, 6147, &v21, 0, 0);
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
    v15 = (WaasMedic *)v22[0];
    if ( v22[0] == 2 )
    {
      LogLevelW(4u, L"First try failed with 'SIGNATURE_STATE_UNSIGNED_POLICY', retrying....");
      IsUnderUndockedFolder = WaasMedic::TimeHelper::SyncSystemTime();
      if ( IsUnderUndockedFolder < 0 )
        goto LABEL_39;
      memset_0(v22, 0, 0x54u);
      v21 = 88;
      v16 = WTGetSignatureInfo(lpwstrFilename, FileW, 6147, &v21, 0, 0);
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
      v15 = (WaasMedic *)v22[0];
    }
    if ( (unsigned int)((_DWORD)v15 - 5) <= 1 )
    {
      if ( v23 == 1 || WaasMedic::IsTestSigningEnabled(v15) )
        goto LABEL_39;
      LODWORD(v15) = v22[0];
    }
    dwCreationDisposition[0] = (unsigned int)v15;
    LogLevelW(
      2u,
      L"Unexpected sigInfo for '%s'.  fOSBinary=%d, SignatureState=%d.",
      lpwstrFilename,
      v23,
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
0x180028bec  push    rbp
0x180028bee  push    rbx
0x180028bef  push    rsi
0x180028bf0  push    rdi
0x180028bf1  push    r14
0x180028bf3  push    r15
0x180028bf5  lea     rbp, [rsp-2Fh]
0x180028bfa  sub     rsp, 0E8h
0x180028c01  mov     rax, cs:__security_cookie
0x180028c08  xor     rax, rsp
0x180028c0b  mov     [rbp+57h+var_40], rax
0x180028c0f  mov     rsi, rcx
0x180028c12  xor     r15d, r15d
0x180028c15  mov     ebx, r15d
0x180028c18  test    rcx, rcx
0x180028c1b  jnz     short loc_180028C24
0x180028c1d  mov     edi, 80004003h
0x180028c22  jmp     short loc_180028C48
0x180028c24  call    cs:__imp_GetFileAttributesW
0x180028c2a  cmp     eax, 0FFFFFFFFh
0x180028c2d  jnz     short loc_180028C64
0x180028c2f  call    cs:__imp_GetLastError
0x180028c35  mov     edi, eax
0x180028c37  test    eax, eax
0x180028c39  jle     short loc_180028C44
0x180028c3b  movzx   edi, ax
0x180028c3e  or      edi, 80070000h
0x180028c44  test    edi, edi
0x180028c46  jns     short loc_180028C64
0x180028c48  lea     rdx, aCheckiffileexi; "CheckIfFileExists failed for %s.  hr = "...
0x180028c4f  mov     r9d, edi
0x180028c52  mov     r8, rsi
0x180028c55  mov     ecx, 2; unsigned __int8
0x180028c5a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180028c5f  jmp     loc_180028E9A
0x180028c64  mov     [rsp+110h+hTemplateFile], r15; hTemplateFile
0x180028c69  mov     [rsp+110h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180028c71  mov     [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x180028c79  xor     r9d, r9d; lpSecurityAttributes
0x180028c7c  mov     edx, 80000000h; dwDesiredAccess
0x180028c81  lea     r8d, [r9+1]; dwShareMode
0x180028c85  mov     rcx, rsi; lpFileName
0x180028c88  call    cs:__imp_CreateFileW
0x180028c8e  mov     rbx, rax
0x180028c91  mov     [rbp+57h+var_C8], rax
0x180028c95  or      r14, 0FFFFFFFFFFFFFFFFh
0x180028c99  cmp     rax, r14
0x180028c9c  jnz     short loc_180028CBC
0x180028c9e  call    cs:__imp_GetLastError
0x180028ca4  mov     edi, eax
0x180028ca6  test    eax, eax
0x180028ca8  jle     loc_180028E9A
0x180028cae  movzx   edi, ax
0x180028cb1  or      edi, 80070000h
0x180028cb7  jmp     loc_180028E9A
0x180028cbc  mov     byte ptr [rbp+57h+var_D0], r15b
0x180028cc0  lea     rdx, [rbp+57h+var_D0]; unsigned __int16 *
0x180028cc4  mov     rcx, rsi; lpwstrFilename
0x180028cc7  call    ?ValidateOriginalFileName@WaasMedic@@YAJPEBGAEA_N@Z; WaasMedic::ValidateOriginalFileName(ushort const *,bool &)
0x180028ccc  mov     edi, eax
0x180028cce  test    eax, eax
0x180028cd0  jns     short loc_180028CE1
0x180028cd2  mov     r9d, eax
0x180028cd5  lea     rdx, aAnErrorOccured; "An error occured while validating the o"...
0x180028cdc  jmp     loc_180028C52
0x180028ce1  cmp     byte ptr [rbp+57h+var_D0], r15b
0x180028ce5  jnz     short loc_180028CF8
0x180028ce7  mov     edi, 80070241h
0x180028cec  lea     rdx, aTheFileNameDoe; "The file name does not match the origin"...
0x180028cf3  jmp     loc_180028C4F
0x180028cf8  mov     byte ptr [rbp+57h+var_D0], r15b
0x180028cfc  lea     rdx, [rbp+57h+var_D0]; unsigned __int16 *
0x180028d00  mov     rcx, rsi; this
0x180028d03  call    ?IsInSystemFolder@WaasMedic@@YAJPEBGAEA_N@Z; WaasMedic::IsInSystemFolder(ushort const *,bool &)
0x180028d08  mov     edi, eax
0x180028d0a  test    eax, eax
0x180028d0c  jns     short loc_180028D1D
0x180028d0e  mov     r9d, eax
0x180028d11  lea     rdx, aErrorValidatin; "Error validating the library folder %s:"...
0x180028d18  jmp     loc_180028C52
0x180028d1d  cmp     byte ptr [rbp+57h+var_D0], r15b
0x180028d21  jnz     short loc_180028D9A
0x180028d23  mov     byte ptr [rbp+57h+var_D0], r15b
0x180028d27  xorps   xmm0, xmm0
0x180028d2a  movups  [rbp+57h+var_60], xmm0
0x180028d2e  xorps   xmm1, xmm1
0x180028d31  movdqu  [rbp+57h+var_50], xmm1
0x180028d36  inc     r14
0x180028d39  cmp     [rsi+r14*2], r15w
0x180028d3e  jnz     short loc_180028D36
0x180028d40  mov     r8, r14
0x180028d43  mov     rdx, rsi
0x180028d46  lea     rcx, [rbp+57h+var_60]
0x180028d4a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180028d4f  nop
0x180028d50  lea     rdx, [rbp+57h+var_D0]
0x180028d54  lea     rcx, [rbp+57h+var_60]
0x180028d58  call    ?IsUnderUndockedFolder@WaasMedic@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z; WaasMedic::IsUnderUndockedFolder(std::wstring const &,bool &)
0x180028d5d  mov     edi, eax
0x180028d5f  lea     rcx, [rbp+57h+var_60]; void *
0x180028d63  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028d68  mov     eax, edi
0x180028d6a  shr     eax, 1Fh
0x180028d6d  test    al, al
0x180028d6f  jz      short loc_180028D76
0x180028d71  mov     r9d, edi
0x180028d74  jmp     short loc_180028D11
0x180028d76  cmp     byte ptr [rbp+57h+var_D0], r15b
0x180028d7a  jnz     short loc_180028D9A
0x180028d7c  mov     edi, 800700A1h
0x180028d81  mov     r8, rsi
0x180028d84  lea     rdx, aLibraryWasNotI; "Library was not in expected path: %s"
0x180028d8b  mov     ecx, 2; unsigned __int8
0x180028d90  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180028d95  jmp     loc_180028E9A
0x180028d9a  mov     r14d, 54h ; 'T'
0x180028da0  mov     r8d, r14d; Size
0x180028da3  xor     edx, edx; Val
0x180028da5  lea     rcx, [rbp+57h+var_BC]; void *
0x180028da9  call    memset_0
0x180028dae  mov     [rbp+57h+var_C0], 58h ; 'X'
0x180028db5  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], r15
0x180028dba  mov     qword ptr [rsp+110h+dwCreationDisposition], r15
0x180028dbf  lea     r9, [rbp+57h+var_C0]
0x180028dc3  mov     r8d, 1803h
0x180028dc9  mov     rdx, rbx
0x180028dcc  mov     rcx, rsi
0x180028dcf  call    cs:__imp_WTGetSignatureInfo
0x180028dd5  mov     edi, eax
0x180028dd7  test    eax, eax
0x180028dd9  jns     short loc_180028DEA
0x180028ddb  mov     r9d, eax
0x180028dde  lea     rdx, aCouldNotEstabl; "Could not establish trust with the requ"...
0x180028de5  jmp     loc_180028C52
0x180028dea  mov     ecx, [rbp+57h+var_BC]
0x180028ded  cmp     ecx, 2
0x180028df0  jnz     short loc_180028E5F
0x180028df2  lea     rdx, aFirstTryFailed; "First try failed with 'SIGNATURE_STATE_"...
0x180028df9  mov     ecx, 4; unsigned __int8
0x180028dfe  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180028e03  call    ?SyncSystemTime@TimeHelper@WaasMedic@@SAJXZ; WaasMedic::TimeHelper::SyncSystemTime(void)
0x180028e08  mov     edi, eax
0x180028e0a  test    eax, eax
0x180028e0c  js      loc_180028E9A
0x180028e12  mov     r8, r14; Size
0x180028e15  xor     edx, edx; Val
0x180028e17  lea     rcx, [rbp+57h+var_BC]; void *
0x180028e1b  call    memset_0
0x180028e20  mov     [rbp+57h+var_C0], 58h ; 'X'
0x180028e27  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], r15
0x180028e2c  mov     qword ptr [rsp+110h+dwCreationDisposition], r15
0x180028e31  lea     r9, [rbp+57h+var_C0]
0x180028e35  mov     r8d, 1803h
0x180028e3b  mov     rdx, rbx
0x180028e3e  mov     rcx, rsi
0x180028e41  call    cs:__imp_WTGetSignatureInfo
0x180028e47  mov     edi, eax
0x180028e49  test    eax, eax
0x180028e4b  jns     short loc_180028E5C
0x180028e4d  mov     r9d, eax
0x180028e50  lea     rdx, aCouldNotEstabl_0; "Could not establish trust with the requ"...
0x180028e57  jmp     loc_180028C52
0x180028e5c  mov     ecx, [rbp+57h+var_BC]; this
0x180028e5f  lea     eax, [rcx-5]
0x180028e62  cmp     eax, 1
0x180028e65  ja      short loc_180028E79
0x180028e67  cmp     [rbp+57h+var_6C], 1
0x180028e6b  jz      short loc_180028E9A
0x180028e6d  call    ?IsTestSigningEnabled@WaasMedic@@YA_NXZ; WaasMedic::IsTestSigningEnabled(void)
0x180028e72  test    al, al
0x180028e74  jnz     short loc_180028E9A
0x180028e76  mov     ecx, [rbp+57h+var_BC]
0x180028e79  mov     [rsp+110h+dwCreationDisposition], ecx
0x180028e7d  mov     r9d, [rbp+57h+var_6C]
0x180028e81  mov     r8, rsi
0x180028e84  lea     rdx, aUnexpectedSigi; "Unexpected sigInfo for '%s'.  fOSBinary"...
0x180028e8b  mov     ecx, 2; unsigned __int8
0x180028e90  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180028e95  mov     edi, 80070241h
0x180028e9a  lea     rax, [rbx-1]
0x180028e9e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028ea2  ja      short loc_180028EAD
0x180028ea4  mov     rcx, rbx; hObject
0x180028ea7  call    cs:__imp_CloseHandle
0x180028ead  mov     eax, edi
0x180028eaf  mov     rcx, [rbp+57h+var_40]
0x180028eb3  xor     rcx, rsp; StackCookie
0x180028eb6  call    __security_check_cookie
0x180028ebb  add     rsp, 0E8h
0x180028ec2  pop     r15
0x180028ec4  pop     r14
0x180028ec6  pop     rdi
0x180028ec7  pop     rsi
0x180028ec8  pop     rbx
0x180028ec9  pop     rbp
0x180028eca  retn
```
