# JScriptLib::CScriptReader::LoadText(void)

- ea: `0x180157d50`
- end: `0x18015826d`
- name: `?LoadText@CScriptReader@JScriptLib@@AEAAXXZ`
- size: `1309`
- prototype: `void __fastcall(JScriptLib::CScriptReader *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180157718`
- `0x180158300`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x180004424`
- `0x18000da28`
- `0x18000dadc`
- `0x18000e23c`
- `0x18000f380`
- `0x18000f590`
- `0x180018c5c`
- `0x18002c8b4`
- `0x1800325a8`
- `0x180156d04`
- `0x1801579a0`
- `0x180157ab4`
- `0x180157d50`
- `0x180158590`
- `0x1801586b0`
- `0x1801adb58`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x18015800c`
- `KERNEL32!CreateFileMappingW` at `0x18015800c`
- `KERNEL32!UnmapViewOfFile` at `0x180158121`
- `KERNEL32!UnmapViewOfFile` at `0x180158121`
- `KERNEL32!MapViewOfFile` at `0x18015803e`
- `KERNEL32!MapViewOfFile` at `0x18015803e`
- `KERNEL32!GetFileSize` at `0x180157df0`
- `KERNEL32!GetFileSize` at `0x180157df0`
- `KERNEL32!CreateFileW` at `0x180157dc8`
- `KERNEL32!CreateFileW` at `0x180157dc8`
- `KERNEL32!CloseHandle` at `0x18015812b`
- `KERNEL32!CloseHandle` at `0x18015813a`
- `KERNEL32!CloseHandle` at `0x18015812b`
- `KERNEL32!CloseHandle` at `0x18015813a`
- `KERNEL32!GetLastError` at `0x180157e8c`
- `KERNEL32!GetLastError` at `0x180158051`
- `KERNEL32!GetLastError` at `0x180157e8c`
- `KERNEL32!GetLastError` at `0x180158051`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180157e67`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180157e67`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall JScriptLib::CScriptReader::LoadText(JScriptLib::CScriptReader *this)
{
  JScriptLib::CScriptReader *v1; // r14
  HANDLE FileW; // rax
  const char *v3; // r9
  void *v4; // rdi
  DWORD FileSize; // eax
  JScriptLib::CScriptReader *v6; // rcx
  const char *v7; // r9
  unsigned __int64 v8; // r15
  DWORD FinalPathNameByHandleW; // ebx
  JScriptLib::CScriptReader *v10; // rcx
  char LastError; // al
  __int64 v12; // rcx
  unsigned __int16 *v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rcx
  JScriptLib::CScriptReader *v16; // rcx
  unsigned __int16 *v17; // rdx
  char v18; // bl
  HANDLE FileMappingW; // rsi
  const char *v20; // r9
  const char *v21; // rbx
  const char *v22; // r9
  signed int v23; // eax
  bool v24; // sf
  unsigned __int64 v25; // rax
  void **v26; // rcx
  unsigned __int64 v27; // rdx
  char *v28; // r15
  __int64 v29; // r14
  unsigned __int64 v30; // r9
  const char *v31; // r8
  unsigned int v32; // edx
  unsigned __int16 **v33; // r9
  DWORD FileSizeHigh[2]; // [rsp+48h] [rbp-C0h] BYREF
  HANDLE v35; // [rsp+50h] [rbp-B8h]
  __int64 v36; // [rsp+58h] [rbp-B0h]
  HANDLE v37; // [rsp+60h] [rbp-A8h]
  _BYTE pExceptionObject[40]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int16 *v39[3]; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 v40; // [rsp+A8h] [rbp-60h]
  _OWORD v41[2]; // [rsp+B0h] [rbp-58h] BYREF
  WCHAR szFilePath[520]; // [rsp+D8h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+520h] [rbp+418h]

  v36 = -2;
  v1 = this;
  LODWORD(v35) = 0;
  if ( *((_QWORD *)this + 3) > 7u )
    this = *(JScriptLib::CScriptReader **)this;
  FileW = CreateFileW((LPCWSTR)this, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v4 = FileW;
  v37 = FileW;
  if ( FileW == (HANDLE)-1LL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x189,
      (unsigned int)"onecoreuap\\printscan\\print\\spooler\\jscriptlib\\jscriptdocument.cpp",
      v3);
  FileSizeHigh[0] = 0;
  FileSize = GetFileSize(FileW, FileSizeHigh);
  v8 = FileSize;
  if ( FileSize == -1 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x191,
      (unsigned int)"onecoreuap\\printscan\\print\\spooler\\jscriptlib\\jscriptdocument.cpp",
      v7);
  if ( FileSizeHigh[0] )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject[8], -2147024673);
    throw (hr_error *)&pExceptionObject[8];
  }
  if ( !(unsigned int)JScriptLib::CScriptReader::IsIntegrityLevelLow(v6) )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids);
    }
    memset_0(szFilePath, 0, sizeof(szFilePath));
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(v4, szFilePath, 0x208u, 0);
    v10 = (JScriptLib::CScriptReader *)(FinalPathNameByHandleW - 1);
    if ( (unsigned int)v10 <= 0x207 )
      goto LABEL_18;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      if ( *((_QWORD *)v1 + 3) <= 7u )
        v12 = (__int64)v1;
      else
        v12 = *(_QWORD *)v1;
      WPP_SF_DSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, (__int64)szFilePath, LastError);
    }
    if ( FinalPathNameByHandleW )
    {
LABEL_18:
      if ( *((_QWORD *)v1 + 3) <= 7u )
        v13 = (unsigned __int16 *)v1;
      else
        v13 = *(unsigned __int16 **)v1;
      if ( !JScriptLib::CScriptReader::IsFileNameValid(v10, v13, szFilePath) )
      {
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          if ( *((_QWORD *)v1 + 3) <= 7u )
            LODWORD(v14) = (_DWORD)v1;
          else
            v14 = *(_QWORD *)v1;
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            (unsigned int)&WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids,
            v14,
            (__int64)szFilePath);
        }
        std::wstring::wstring((__int64)v39, (__int64)v1);
        memset(&pExceptionObject[8], 0, 32);
        std::wstring::_Construct<1,unsigned short const *>((char **)&pExceptionObject[8], L"\\", 1u);
        LODWORD(v35) = 1;
        memset(v41, 0, sizeof(v41));
        std::wstring::_Construct<1,unsigned short const *>((char **)v41, L"\\.\\", 3u);
        LODWORD(v35) = 3;
        if ( !JScriptLib::CScriptReader::ReplaceSubstring(v15, v39, v41, &pExceptionObject[8]) )
          goto LABEL_33;
        v17 = (unsigned __int16 *)v39;
        if ( v40 > 7 )
          v17 = v39[0];
        if ( JScriptLib::CScriptReader::IsFileNameValid(v16, v17, szFilePath) )
          v18 = 0;
        else
LABEL_33:
          v18 = 1;
        std::wstring::~wstring(v41);
        std::wstring::~wstring(&pExceptionObject[8]);
        if ( v18 )
        {
          if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v33 = v39;
            if ( v40 > 7 )
              LODWORD(v33) = v39[0];
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              (unsigned int)&WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids,
              (_DWORD)v33,
              (__int64)szFilePath);
          }
          hr_error::hr_error((hr_error *)&pExceptionObject[8], -2147024773);
          throw (hr_error *)&pExceptionObject[8];
        }
        std::wstring::~wstring(v39);
      }
    }
  }
  FileMappingW = CreateFileMappingW(v4, 0, 2u, 0, 0, 0);
  v35 = FileMappingW;
  if ( (((unsigned __int64)FileMappingW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1C1,
      (unsigned int)"onecoreuap\\printscan\\print\\spooler\\jscriptlib\\jscriptdocument.cpp",
      v20);
  v21 = (const char *)MapViewOfFile(FileMappingW, 1u, 0, 0, 0);
  *(_QWORD *)pExceptionObject = v21;
  if ( !v21 )
  {
    v23 = GetLastError();
    v24 = v23 < 0;
    if ( v23 > 0 )
    {
      v23 = (unsigned __int16)v23 | 0x80070000;
      v24 = v23 < 0;
    }
    if ( v24 )
    {
      hr_error::hr_error((hr_error *)&pExceptionObject[8], v23);
      throw (hr_error *)&pExceptionObject[8];
    }
  }
  if ( !v21 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC,
      (unsigned int)"onecoreuap\\printscan\\print\\spooler\\jscriptlib\\jscriptdocument.cpp",
      v22);
  if ( (unsigned int)v8 > 2 && *v21 == -1 && v21[1] == -2 )
  {
    v25 = v8 >> 1;
    if ( v8 >> 1 > 1 )
    {
      v26 = (void **)((char *)v1 + 32);
      v27 = v25 - 1;
      if ( v25 - 1 > *((_QWORD *)v1 + 7) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v26);
      }
      else
      {
        if ( *((_QWORD *)v1 + 7) <= 7u )
          v28 = (char *)v1 + 32;
        else
          v28 = (char *)*v26;
        *((_QWORD *)v1 + 6) = v27;
        v29 = 2 * v27;
        memmove_0(v28, v21 + 2, 2 * v27);
        *(_WORD *)&v28[v29] = 0;
      }
    }
  }
  else
  {
    if ( (unsigned int)v8 > 3 && *v21 == -17 && v21[1] == -69 && v21[2] == -65 )
    {
      v30 = v8 - 3;
      v31 = v21 + 3;
      v32 = 65001;
    }
    else
    {
      v30 = v8;
      v31 = v21;
      v32 = 3;
    }
    JScriptLib::CScriptReader::ConvertToUnicodeAndSetText(v1, v32, v31, v30);
  }
  UnmapViewOfFile(v21);
  CloseHandle(FileMappingW);
  if ( v4 )
    CloseHandle(v4);
}

```

## disassembly

```asm
0x180157d50  mov     rax, rsp
0x180157d53  push    rbp
0x180157d54  push    rdi
0x180157d55  push    r13
0x180157d57  push    r14
0x180157d59  push    r15
0x180157d5b  lea     rbp, [rax-418h]
0x180157d62  sub     rsp, 4F0h
0x180157d69  mov     [rsp+510h+var_4C0], 0FFFFFFFFFFFFFFFEh
0x180157d72  mov     [rax+10h], rbx
0x180157d76  mov     [rax+18h], rsi
0x180157d7a  mov     rax, cs:__security_cookie
0x180157d81  xor     rax, rsp
0x180157d84  mov     [rbp+410h+var_30], rax
0x180157d8b  mov     r14, rcx
0x180157d8e  mov     dword ptr [rsp+510h+var_4C8], 0
0x180157d96  cmp     qword ptr [rcx+18h], 7
0x180157d9b  jbe     short loc_180157DA0
0x180157d9d  mov     rcx, [rcx]; lpFileName
0x180157da0  mov     [rsp+510h+hTemplateFile], 0; hTemplateFile
0x180157da9  mov     [rsp+510h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180157db1  mov     [rsp+510h+dwCreationDisposition], 3; dwCreationDisposition
0x180157db9  xor     r9d, r9d; lpSecurityAttributes
0x180157dbc  lea     r13d, [r9+1]
0x180157dc0  mov     r8d, r13d; dwShareMode
0x180157dc3  mov     edx, 80000000h; dwDesiredAccess
0x180157dc8  call    cs:__imp_CreateFileW
0x180157dce  mov     rdi, rax
0x180157dd1  mov     [rsp+510h+var_4B8], rax
0x180157dd6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180157dda  jz      loc_180158184
0x180157de0  mov     [rsp+510h+FileSizeHigh], 0
0x180157de8  lea     rdx, [rsp+510h+FileSizeHigh]; lpFileSizeHigh
0x180157ded  mov     rcx, rax; hFile
0x180157df0  call    cs:__imp_GetFileSize
0x180157df6  mov     r15d, eax
0x180157df9  cmp     eax, 0FFFFFFFFh
0x180157dfc  jz      loc_18015819D
0x180157e02  cmp     [rsp+510h+FileSizeHigh], 0
0x180157e07  ja      loc_1801581B6
0x180157e0d  call    ?IsIntegrityLevelLow@CScriptReader@JScriptLib@@AEAAHXZ; JScriptLib::CScriptReader::IsIntegrityLevelLow(void)
0x180157e12  test    eax, eax
0x180157e14  jnz     loc_180157FEF
0x180157e1a  lea     rsi, WPP_GLOBAL_Control
0x180157e21  mov     rcx, cs:WPP_GLOBAL_Control
0x180157e28  cmp     rcx, rsi
0x180157e2b  jz      short loc_180157E46
0x180157e2d  test    byte ptr [rcx+1Ch], 8
0x180157e31  jz      short loc_180157E46
0x180157e33  lea     edx, [rax+14h]
0x180157e36  lea     r8, WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids
0x180157e3d  mov     rcx, [rcx+10h]
0x180157e41  call    WPP_SF_
0x180157e46  xor     edx, edx; Val
0x180157e48  mov     r8d, 410h; Size
0x180157e4e  lea     rcx, [rbp+410h+szFilePath]; void *
0x180157e52  call    memset_0
0x180157e57  xor     r9d, r9d; dwFlags
0x180157e5a  mov     r8d, 208h; cchFilePath
0x180157e60  lea     rdx, [rbp+410h+szFilePath]; lpszFilePath
0x180157e64  mov     rcx, rdi; hFile
0x180157e67  call    cs:__imp_GetFinalPathNameByHandleW
0x180157e6d  mov     ebx, eax
0x180157e6f  lea     ecx, [rax-1]
0x180157e72  cmp     ecx, 207h
0x180157e78  jbe     short loc_180157ECE
0x180157e7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180157e81  cmp     rcx, rsi
0x180157e84  jz      short loc_180157EC6
0x180157e86  test    [rcx+1Ch], r13b
0x180157e8a  jz      short loc_180157EC6
0x180157e8c  call    cs:__imp_GetLastError
0x180157e92  cmp     qword ptr [r14+18h], 7
0x180157e97  jbe     short loc_180157E9E
0x180157e99  mov     rcx, [r14]
0x180157e9c  jmp     short loc_180157EA1
0x180157e9e  mov     rcx, r14
0x180157ea1  mov     dword ptr [rsp+510h+hTemplateFile], eax; char
0x180157ea5  lea     rax, [rbp+410h+szFilePath]
0x180157ea9  mov     qword ptr [rsp+510h+dwFlagsAndAttributes], rax; __int64
0x180157eae  mov     qword ptr [rsp+510h+dwCreationDisposition], rcx; __int64
0x180157eb3  mov     r9d, ebx
0x180157eb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180157ebd  mov     rcx, [rcx+10h]; LoggerHandle
0x180157ec1  call    WPP_SF_DSSD
0x180157ec6  test    ebx, ebx
0x180157ec8  jz      loc_180157FEF
0x180157ece  cmp     qword ptr [r14+18h], 7
0x180157ed3  jbe     short loc_180157EDA
0x180157ed5  mov     rdx, [r14]
0x180157ed8  jmp     short loc_180157EDD
0x180157eda  mov     rdx, r14; unsigned __int16 *
0x180157edd  lea     r8, [rbp+410h+szFilePath]; unsigned __int16 *
0x180157ee1  call    ?IsFileNameValid@CScriptReader@JScriptLib@@AEAAHPEAG0@Z; JScriptLib::CScriptReader::IsFileNameValid(ushort *,ushort *)
0x180157ee6  test    eax, eax
0x180157ee8  jnz     loc_180157FEF
0x180157eee  mov     rcx, cs:WPP_GLOBAL_Control
0x180157ef5  cmp     rcx, rsi
0x180157ef8  jz      short loc_180157F2D
0x180157efa  test    [rcx+1Ch], r13b
0x180157efe  jz      short loc_180157F2D
0x180157f00  cmp     qword ptr [r14+18h], 7
0x180157f05  jbe     short loc_180157F0C
0x180157f07  mov     r9, [r14]
0x180157f0a  jmp     short loc_180157F0F
0x180157f0c  mov     r9, r14
0x180157f0f  mov     edx, 16h
0x180157f14  lea     rax, [rbp+410h+szFilePath]
0x180157f18  mov     qword ptr [rsp+510h+dwCreationDisposition], rax
0x180157f1d  lea     r8, WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids
0x180157f24  mov     rcx, [rcx+10h]
0x180157f28  call    WPP_SF_SS
0x180157f2d  mov     rdx, r14
0x180157f30  lea     rcx, [rbp+410h+var_488]
0x180157f34  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180157f39  nop
0x180157f3a  xorps   xmm0, xmm0
0x180157f3d  movups  [rsp+510h+pExceptionObject+8], xmm0
0x180157f42  xorps   xmm1, xmm1
0x180157f45  movdqu  [rsp+510h+var_4A0+8], xmm1
0x180157f4b  mov     r8, r13
0x180157f4e  lea     rdx, SubBlock; "\\"
0x180157f55  lea     rcx, [rsp+510h+pExceptionObject+8]
0x180157f5a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180157f5f  nop
0x180157f60  mov     dword ptr [rsp+510h+var_4C8], r13d
0x180157f65  xorps   xmm0, xmm0
0x180157f68  movups  [rbp+410h+var_468], xmm0
0x180157f6c  xorps   xmm1, xmm1
0x180157f6f  movdqu  [rbp+410h+var_458], xmm1
0x180157f74  mov     ebx, 3
0x180157f79  mov     r8d, ebx
0x180157f7c  lea     rdx, asc_18020D4E8; "\\.\\"
0x180157f83  lea     rcx, [rbp+410h+var_468]
0x180157f87  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180157f8c  nop
0x180157f8d  mov     dword ptr [rsp+510h+var_4C8], ebx
0x180157f91  lea     r9, [rsp+510h+pExceptionObject+8]
0x180157f96  lea     r8, [rbp+410h+var_468]
0x180157f9a  lea     rdx, [rbp+410h+var_488]
0x180157f9e  call    ?ReplaceSubstring@CScriptReader@JScriptLib@@AEAA_KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@1@Z; JScriptLib::CScriptReader::ReplaceSubstring(std::wstring &,std::wstring const &,std::wstring const &)
0x180157fa3  test    rax, rax
0x180157fa6  jz      short loc_180157FC7
0x180157fa8  lea     rdx, [rbp+410h+var_488]
0x180157fac  cmp     [rbp+410h+var_470], 7
0x180157fb1  cmova   rdx, [rbp+410h+var_488]; unsigned __int16 *
0x180157fb6  lea     r8, [rbp+410h+szFilePath]; unsigned __int16 *
0x180157fba  call    ?IsFileNameValid@CScriptReader@JScriptLib@@AEAAHPEAG0@Z; JScriptLib::CScriptReader::IsFileNameValid(ushort *,ushort *)
0x180157fbf  test    eax, eax
0x180157fc1  jz      short loc_180157FC7
0x180157fc3  xor     bl, bl
0x180157fc5  jmp     short loc_180157FCA
0x180157fc7  mov     bl, r13b
0x180157fca  lea     rcx, [rbp+410h+var_468]
0x180157fce  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180157fd3  nop
0x180157fd4  lea     rcx, [rsp+510h+pExceptionObject+8]
0x180157fd9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180157fde  test    bl, bl
0x180157fe0  jnz     loc_1801581D7
0x180157fe6  lea     rcx, [rbp+410h+var_488]
0x180157fea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180157fef  mov     qword ptr [rsp+510h+dwFlagsAndAttributes], 0; lpName
0x180157ff8  mov     [rsp+510h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180158000  xor     r9d, r9d; dwMaximumSizeHigh
0x180158003  xor     edx, edx; lpFileMappingAttributes
0x180158005  lea     r8d, [r9+2]; flProtect
0x180158009  mov     rcx, rdi; hFile
0x18015800c  call    cs:__imp_CreateFileMappingW
0x180158012  mov     rsi, rax
0x180158015  mov     [rsp+510h+var_4C8], rax
0x18015801a  inc     rax
0x18015801d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180158023  jz      loc_180158236
0x180158029  mov     qword ptr [rsp+510h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180158032  xor     r9d, r9d; dwFileOffsetLow
0x180158035  xor     r8d, r8d; dwFileOffsetHigh
0x180158038  mov     edx, r13d; dwDesiredAccess
0x18015803b  mov     rcx, rsi; hFileMappingObject
0x18015803e  call    cs:__imp_MapViewOfFile
0x180158044  mov     rbx, rax
0x180158047  mov     qword ptr [rsp+510h+pExceptionObject], rax
0x18015804c  test    rax, rax
0x18015804f  jnz     short loc_18015806B
0x180158051  call    cs:__imp_GetLastError
0x180158057  test    eax, eax
0x180158059  jle     short loc_180158065
0x18015805b  movzx   eax, ax
0x18015805e  or      eax, 80070000h
0x180158063  test    eax, eax
0x180158065  js      loc_18015824F
0x18015806b  test    rbx, rbx
0x18015806e  jz      loc_18015816B
0x180158074  cmp     r15d, 2
0x180158078  jbe     short loc_1801580DB
0x18015807a  cmp     byte ptr [rbx], 0FFh
0x18015807d  jnz     short loc_1801580DB
0x18015807f  cmp     byte ptr [rbx+1], 0FEh
0x180158083  jnz     short loc_1801580DB
0x180158085  mov     rax, r15
0x180158088  shr     rax, 1
0x18015808b  cmp     rax, r13
0x18015808e  jbe     loc_18015811E
0x180158094  lea     rcx, [r14+20h]
0x180158098  lea     rdx, [rax-1]
0x18015809c  lea     r9, [rbx+2]
0x1801580a0  cmp     rdx, [rcx+18h]
0x1801580a4  ja      short loc_1801580D4
0x1801580a6  cmp     qword ptr [rcx+18h], 7
0x1801580ab  jbe     short loc_1801580B2
0x1801580ad  mov     r15, [rcx]
0x1801580b0  jmp     short loc_1801580B5
0x1801580b2  mov     r15, rcx
0x1801580b5  mov     [rcx+10h], rdx
0x1801580b9  lea     r14, [rdx+rdx]
0x1801580bd  mov     r8, r14; Size
0x1801580c0  mov     rdx, r9; Src
0x1801580c3  mov     rcx, r15; void *
0x1801580c6  call    memmove_0
0x1801580cb  xor     eax, eax
0x1801580cd  mov     [r14+r15], ax
0x1801580d2  jmp     short loc_18015811E
0x1801580d4  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1801580d9  jmp     short loc_18015811E
0x1801580db  cmp     r15d, 3
0x1801580df  jbe     short loc_18015810A
0x1801580e1  cmp     byte ptr [rbx], 0EFh
0x1801580e4  jnz     short loc_18015810A
0x1801580e6  cmp     byte ptr [rbx+1], 0BBh
0x1801580ea  jnz     short loc_18015810A
0x1801580ec  cmp     byte ptr [rbx+2], 0BFh
0x1801580f0  jnz     short loc_18015810A
0x1801580f2  mov     r9, r15
0x1801580f5  cmp     r15, 3
0x1801580f9  jbe     short loc_18015811E
0x1801580fb  add     r9, 0FFFFFFFFFFFFFFFDh
0x1801580ff  lea     r8, [rbx+3]
0x180158103  mov     edx, 0FDE9h
0x180158108  jmp     short loc_180158115
0x18015810a  mov     r9, r15; unsigned __int64
0x18015810d  mov     r8, rbx; char *
0x180158110  mov     edx, 3; unsigned int
0x180158115  mov     rcx, r14; this
0x180158118  call    ?ConvertToUnicodeAndSetText@CScriptReader@JScriptLib@@AEAAXIPEBD_K@Z; JScriptLib::CScriptReader::ConvertToUnicodeAndSetText(uint,char const *,unsigned __int64)
0x18015811d  nop
0x18015811e  mov     rcx, rbx; lpBaseAddress
0x180158121  call    cs:__imp_UnmapViewOfFile
0x180158127  nop
0x180158128  mov     rcx, rsi; hObject
0x18015812b  call    cs:__imp_CloseHandle
0x180158131  nop
0x180158132  test    rdi, rdi
0x180158135  jz      short loc_180158140
0x180158137  mov     rcx, rdi; hObject
0x18015813a  call    cs:__imp_CloseHandle
0x180158140  mov     rcx, [rbp+410h+var_30]
0x180158147  xor     rcx, rsp; StackCookie
0x18015814a  call    __security_check_cookie
0x18015814f  lea     r11, [rsp+510h+var_20]
0x180158157  mov     rbx, [r11+38h]
0x18015815b  mov     rsi, [r11+40h]
0x18015815f  mov     rsp, r11
0x180158162  pop     r15
0x180158164  pop     r14
0x180158166  pop     r13
0x180158168  pop     rdi
0x180158169  pop     rbp
0x18015816a  retn
0x18015816b  mov     rcx, [rbp+418h]; this
0x180158172  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\spooler\\"...
0x180158179  mov     edx, 1CCh; void *
0x18015817e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180158184  mov     rcx, [rbp+418h]; this
0x18015818b  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\spooler\\"...
0x180158192  mov     edx, 189h; void *
0x180158197  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18015819d  mov     rcx, [rbp+418h]; this
0x1801581a4  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\spooler\\"...
0x1801581ab  mov     edx, 191h; void *
0x1801581b0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801581b6  mov     edx, 800700DFh; int
0x1801581bb  lea     rcx, [rsp+510h+pExceptionObject+8]; this
0x1801581c0  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1801581c5  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1801581cc  lea     rcx, [rsp+510h+pExceptionObject+8]; pExceptionObject
0x1801581d1  call    _CxxThrowException_0
0x1801581d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1801581de  cmp     rcx, rsi
0x1801581e1  jz      short loc_180158215
0x1801581e3  test    [rcx+1Ch], r13b
0x1801581e7  jz      short loc_180158215
0x1801581e9  lea     r9, [rbp+410h+var_488]
0x1801581ed  cmp     [rbp+410h+var_470], 7
0x1801581f2  cmova   r9, [rbp+410h+var_488]
0x1801581f7  mov     edx, 17h
0x1801581fc  lea     rax, [rbp+410h+szFilePath]
0x180158200  mov     qword ptr [rsp+510h+dwCreationDisposition], rax
0x180158205  lea     r8, WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids
0x18015820c  mov     rcx, [rcx+10h]
0x180158210  call    WPP_SF_SS
  ... truncated ...
```
