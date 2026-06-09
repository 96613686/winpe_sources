# JScriptLib::CScriptReader::LoadText(void)

- ea: `0x18015f184`
- end: `0x18015f6de`
- name: `?LoadText@CScriptReader@JScriptLib@@AEAAXXZ`
- size: `1370`
- prototype: `void __fastcall(JScriptLib::CScriptReader *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x18015eadc`
- `0x18015f780`

## callees

- `0x180003400`
- `0x180004558`
- `0x180004564`
- `0x18000de1c`
- `0x18000ded0`
- `0x18000e644`
- `0x18000f830`
- `0x18000fa4c`
- `0x180019860`
- `0x18002dbc8`
- `0x180033598`
- `0x18015e094`
- `0x18015ed68`
- `0x18015ee98`
- `0x18015f184`
- `0x18015fa10`
- `0x18015fb30`
- `0x1801b56c8`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x18015f458`
- `KERNEL32!CreateFileMappingW` at `0x18015f458`
- `KERNEL32!UnmapViewOfFile` at `0x18015f57f`
- `KERNEL32!UnmapViewOfFile` at `0x18015f57f`
- `KERNEL32!MapViewOfFile` at `0x18015f490`
- `KERNEL32!MapViewOfFile` at `0x18015f490`
- `KERNEL32!GetFileSize` at `0x18015f22a`
- `KERNEL32!GetFileSize` at `0x18015f22a`
- `KERNEL32!CreateFileW` at `0x18015f1fc`
- `KERNEL32!CreateFileW` at `0x18015f1fc`
- `KERNEL32!CloseHandle` at `0x18015f58f`
- `KERNEL32!CloseHandle` at `0x18015f5a4`
- `KERNEL32!CloseHandle` at `0x18015f58f`
- `KERNEL32!CloseHandle` at `0x18015f5a4`
- `KERNEL32!GetLastError` at `0x18015f2d2`
- `KERNEL32!GetLastError` at `0x18015f4a9`
- `KERNEL32!GetLastError` at `0x18015f2d2`
- `KERNEL32!GetLastError` at `0x18015f4a9`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18015f2a7`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18015f2a7`

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
  DWORD LastError; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned __int16 *v14; // rcx
  unsigned __int16 *v15; // rdx
  const wchar_t *v16; // r9
  __int64 v17; // rcx
  JScriptLib::CScriptReader *v18; // rcx
  unsigned __int16 *v19; // rdx
  char v20; // bl
  HANDLE FileMappingW; // rsi
  const char *v22; // r9
  const char *v23; // rbx
  __int64 v24; // r8
  const char *v25; // r9
  signed int v26; // eax
  bool v27; // sf
  unsigned __int64 v28; // rax
  char **v29; // rcx
  unsigned __int64 v30; // rdx
  char *v31; // r15
  __int64 v32; // r14
  __int64 v33; // r9
  const char *v34; // r8
  UINT v35; // edx
  const wchar_t *v36; // r9
  HANDLE hTemplateFile; // [rsp+38h] [rbp-D0h]
  DWORD FileSizeHigh[2]; // [rsp+48h] [rbp-C0h] BYREF
  HANDLE v39; // [rsp+50h] [rbp-B8h]
  __int64 v40; // [rsp+58h] [rbp-B0h]
  HANDLE v41; // [rsp+60h] [rbp-A8h]
  _BYTE pExceptionObject[40]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int16 *v43[3]; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 v44; // [rsp+A8h] [rbp-60h]
  __m128i v45[2]; // [rsp+B0h] [rbp-58h] BYREF
  WCHAR szFilePath[520]; // [rsp+D8h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+520h] [rbp+418h]

  v40 = -2;
  v1 = this;
  LODWORD(v39) = 0;
  if ( *((_QWORD *)this + 3) > 7u )
    this = *(JScriptLib::CScriptReader **)this;
  FileW = CreateFileW((LPCWSTR)this, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v4 = FileW;
  v41 = FileW;
  if ( FileW == (HANDLE)-1LL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x189,
      (__int64)"onecoreuap\\printscan\\print\\spooler\\jscriptlib\\jscriptdocument.cpp",
      v3);
  FileSizeHigh[0] = 0;
  FileSize = GetFileSize(FileW, FileSizeHigh);
  v8 = FileSize;
  if ( FileSize == -1 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x191,
      (__int64)"onecoreuap\\printscan\\print\\spooler\\jscriptlib\\jscriptdocument.cpp",
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x14u, &WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids);
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
        v14 = (unsigned __int16 *)v1;
      else
        v14 = *(unsigned __int16 **)v1;
      LODWORD(hTemplateFile) = LastError;
      WPP_SF_DSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, FinalPathNameByHandleW, v14, szFilePath, hTemplateFile);
    }
    if ( FinalPathNameByHandleW )
    {
LABEL_18:
      if ( *((_QWORD *)v1 + 3) <= 7u )
        v15 = (unsigned __int16 *)v1;
      else
        v15 = *(unsigned __int16 **)v1;
      if ( !(unsigned int)JScriptLib::CScriptReader::IsFileNameValid(v10, v15, szFilePath) )
      {
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          if ( *((_QWORD *)v1 + 3) <= 7u )
            v16 = (const wchar_t *)v1;
          else
            v16 = *(const wchar_t **)v1;
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            0x16u,
            &WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids,
            v16,
            szFilePath);
        }
        std::wstring::wstring((__int64)v43, (__int64)v1);
        memset(&pExceptionObject[8], 0, 32);
        std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject[8], L"\\", 1u);
        LODWORD(v39) = 1;
        memset(v45, 0, sizeof(v45));
        std::wstring::_Construct<1,unsigned short const *>(v45, L"\\.\\", 3u);
        LODWORD(v39) = 3;
        if ( !JScriptLib::CScriptReader::ReplaceSubstring(v17, (const __m128i **)v43, v45, &pExceptionObject[8]) )
          goto LABEL_33;
        v19 = (unsigned __int16 *)v43;
        if ( v44 > 7 )
          v19 = v43[0];
        if ( (unsigned int)JScriptLib::CScriptReader::IsFileNameValid(v18, v19, szFilePath) )
          v20 = 0;
        else
LABEL_33:
          v20 = 1;
        std::wstring::~wstring((char **)v45);
        std::wstring::~wstring((char **)&pExceptionObject[8]);
        if ( v20 )
        {
          if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v36 = (const wchar_t *)v43;
            if ( v44 > 7 )
              v36 = v43[0];
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              0x17u,
              &WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids,
              v36,
              szFilePath);
          }
          hr_error::hr_error((hr_error *)&pExceptionObject[8], -2147024773);
          throw (hr_error *)&pExceptionObject[8];
        }
        std::wstring::~wstring((char **)v43);
      }
    }
  }
  FileMappingW = CreateFileMappingW(v4, 0, 2u, 0, 0, 0);
  v39 = FileMappingW;
  if ( (((unsigned __int64)FileMappingW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1C1,
      (__int64)"onecoreuap\\printscan\\print\\spooler\\jscriptlib\\jscriptdocument.cpp",
      v22);
  v23 = (const char *)MapViewOfFile(FileMappingW, 1u, 0, 0, 0);
  *(_QWORD *)pExceptionObject = v23;
  if ( !v23 )
  {
    v26 = GetLastError();
    v27 = v26 < 0;
    if ( v26 > 0 )
    {
      v26 = (unsigned __int16)v26 | 0x80070000;
      v27 = v26 < 0;
    }
    if ( v27 )
    {
      hr_error::hr_error((hr_error *)&pExceptionObject[8], v26);
      throw (hr_error *)&pExceptionObject[8];
    }
  }
  if ( !v23 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC,
      (__int64)"onecoreuap\\printscan\\print\\spooler\\jscriptlib\\jscriptdocument.cpp",
      v25);
  if ( (unsigned int)v8 > 2 && *v23 == -1 && v23[1] == -2 )
  {
    v28 = v8 >> 1;
    if ( v8 >> 1 > 1 )
    {
      v29 = (char **)((char *)v1 + 32);
      v30 = v28 - 1;
      if ( v28 - 1 > *((_QWORD *)v1 + 7) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v29,
          v30,
          v24,
          v23 + 2);
      }
      else
      {
        if ( *((_QWORD *)v1 + 7) <= 7u )
          v31 = (char *)v1 + 32;
        else
          v31 = *v29;
        *((_QWORD *)v1 + 6) = v30;
        v32 = 2 * v30;
        memmove_0(v31, v23 + 2, 2 * v30);
        *(_WORD *)&v31[v32] = 0;
      }
    }
  }
  else
  {
    if ( (unsigned int)v8 > 3 && *v23 == -17 && v23[1] == -69 && v23[2] == -65 )
    {
      v33 = v8 - 3;
      v34 = v23 + 3;
      v35 = 65001;
    }
    else
    {
      v33 = v8;
      v34 = v23;
      v35 = 3;
    }
    JScriptLib::CScriptReader::ConvertToUnicodeAndSetText(v1, v35, v34, v33);
  }
  UnmapViewOfFile(v23);
  CloseHandle(FileMappingW);
  if ( v4 )
    CloseHandle(v4);
}

```

## disassembly

```asm
0x18015f184  mov     rax, rsp
0x18015f187  push    rbp
0x18015f188  push    rdi
0x18015f189  push    r13
0x18015f18b  push    r14
0x18015f18d  push    r15
0x18015f18f  lea     rbp, [rax-418h]
0x18015f196  sub     rsp, 4F0h
0x18015f19d  mov     [rsp+510h+var_4C0], 0FFFFFFFFFFFFFFFEh
0x18015f1a6  mov     [rax+10h], rbx
0x18015f1aa  mov     [rax+18h], rsi
0x18015f1ae  mov     rax, cs:__security_cookie
0x18015f1b5  xor     rax, rsp
0x18015f1b8  mov     [rbp+410h+var_30], rax
0x18015f1bf  mov     r14, rcx
0x18015f1c2  mov     dword ptr [rsp+510h+var_4C8], 0
0x18015f1ca  cmp     qword ptr [rcx+18h], 7
0x18015f1cf  jbe     short loc_18015F1D4
0x18015f1d1  mov     rcx, [rcx]; lpFileName
0x18015f1d4  mov     [rsp+510h+hTemplateFile], 0; hTemplateFile
0x18015f1dd  mov     [rsp+510h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18015f1e5  mov     [rsp+510h+dwCreationDisposition], 3; dwCreationDisposition
0x18015f1ed  xor     r9d, r9d; lpSecurityAttributes
0x18015f1f0  lea     r13d, [r9+1]
0x18015f1f4  mov     r8d, r13d; dwShareMode
0x18015f1f7  mov     edx, 80000000h; dwDesiredAccess
0x18015f1fc  call    cs:__imp_CreateFileW
0x18015f203  nop     dword ptr [rax+rax+00h]
0x18015f208  mov     rdi, rax
0x18015f20b  mov     [rsp+510h+var_4B8], rax
0x18015f210  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18015f214  jz      loc_18015F5F5
0x18015f21a  mov     [rsp+510h+FileSizeHigh], 0
0x18015f222  lea     rdx, [rsp+510h+FileSizeHigh]; lpFileSizeHigh
0x18015f227  mov     rcx, rax; hFile
0x18015f22a  call    cs:__imp_GetFileSize
0x18015f231  nop     dword ptr [rax+rax+00h]
0x18015f236  mov     r15d, eax
0x18015f239  cmp     eax, 0FFFFFFFFh
0x18015f23c  jz      loc_18015F60E
0x18015f242  cmp     [rsp+510h+FileSizeHigh], 0
0x18015f247  ja      loc_18015F627
0x18015f24d  call    ?IsIntegrityLevelLow@CScriptReader@JScriptLib@@AEAAHXZ; JScriptLib::CScriptReader::IsIntegrityLevelLow(void)
0x18015f252  test    eax, eax
0x18015f254  jnz     loc_18015F43B
0x18015f25a  lea     rsi, WPP_GLOBAL_Control
0x18015f261  mov     rcx, cs:WPP_GLOBAL_Control
0x18015f268  cmp     rcx, rsi
0x18015f26b  jz      short loc_18015F286
0x18015f26d  test    byte ptr [rcx+1Ch], 8
0x18015f271  jz      short loc_18015F286
0x18015f273  lea     edx, [rax+14h]
0x18015f276  lea     r8, WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids
0x18015f27d  mov     rcx, [rcx+10h]
0x18015f281  call    WPP_SF_
0x18015f286  xor     edx, edx; Val
0x18015f288  mov     r8d, 410h; Size
0x18015f28e  lea     rcx, [rbp+410h+szFilePath]; void *
0x18015f292  call    memset_0
0x18015f297  xor     r9d, r9d; dwFlags
0x18015f29a  mov     r8d, 208h; cchFilePath
0x18015f2a0  lea     rdx, [rbp+410h+szFilePath]; lpszFilePath
0x18015f2a4  mov     rcx, rdi; hFile
0x18015f2a7  call    cs:__imp_GetFinalPathNameByHandleW
0x18015f2ae  nop     dword ptr [rax+rax+00h]
0x18015f2b3  mov     ebx, eax
0x18015f2b5  lea     ecx, [rax-1]
0x18015f2b8  cmp     ecx, 207h
0x18015f2be  jbe     short loc_18015F31A
0x18015f2c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18015f2c7  cmp     rcx, rsi
0x18015f2ca  jz      short loc_18015F312
0x18015f2cc  test    [rcx+1Ch], r13b
0x18015f2d0  jz      short loc_18015F312
0x18015f2d2  call    cs:__imp_GetLastError
0x18015f2d9  nop     dword ptr [rax+rax+00h]
0x18015f2de  cmp     qword ptr [r14+18h], 7
0x18015f2e3  jbe     short loc_18015F2EA
0x18015f2e5  mov     rcx, [r14]
0x18015f2e8  jmp     short loc_18015F2ED
0x18015f2ea  mov     rcx, r14
0x18015f2ed  mov     dword ptr [rsp+510h+hTemplateFile], eax; char
0x18015f2f1  lea     rax, [rbp+410h+szFilePath]
0x18015f2f5  mov     qword ptr [rsp+510h+dwFlagsAndAttributes], rax; __int64
0x18015f2fa  mov     qword ptr [rsp+510h+dwCreationDisposition], rcx; __int64
0x18015f2ff  mov     r9d, ebx
0x18015f302  mov     rcx, cs:WPP_GLOBAL_Control
0x18015f309  mov     rcx, [rcx+10h]; LoggerHandle
0x18015f30d  call    WPP_SF_DSSD
0x18015f312  test    ebx, ebx
0x18015f314  jz      loc_18015F43B
0x18015f31a  cmp     qword ptr [r14+18h], 7
0x18015f31f  jbe     short loc_18015F326
0x18015f321  mov     rdx, [r14]
0x18015f324  jmp     short loc_18015F329
0x18015f326  mov     rdx, r14; unsigned __int16 *
0x18015f329  lea     r8, [rbp+410h+szFilePath]; unsigned __int16 *
0x18015f32d  call    ?IsFileNameValid@CScriptReader@JScriptLib@@AEAAHPEAG0@Z; JScriptLib::CScriptReader::IsFileNameValid(ushort *,ushort *)
0x18015f332  test    eax, eax
0x18015f334  jnz     loc_18015F43B
0x18015f33a  mov     rcx, cs:WPP_GLOBAL_Control
0x18015f341  cmp     rcx, rsi
0x18015f344  jz      short loc_18015F379
0x18015f346  test    [rcx+1Ch], r13b
0x18015f34a  jz      short loc_18015F379
0x18015f34c  cmp     qword ptr [r14+18h], 7
0x18015f351  jbe     short loc_18015F358
0x18015f353  mov     r9, [r14]
0x18015f356  jmp     short loc_18015F35B
0x18015f358  mov     r9, r14
0x18015f35b  mov     edx, 16h
0x18015f360  lea     rax, [rbp+410h+szFilePath]
0x18015f364  mov     qword ptr [rsp+510h+dwCreationDisposition], rax
0x18015f369  lea     r8, WPP_9e5a8fd5af7d3ff7a0d6c0aaa8413012_Traceguids
0x18015f370  mov     rcx, [rcx+10h]
0x18015f374  call    WPP_SF_SS
0x18015f379  mov     rdx, r14
0x18015f37c  lea     rcx, [rbp+410h+var_488]
0x18015f380  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18015f385  nop
0x18015f386  xorps   xmm0, xmm0
0x18015f389  movups  [rsp+510h+pExceptionObject+8], xmm0
0x18015f38e  xorps   xmm1, xmm1
0x18015f391  movdqu  [rsp+510h+var_4A0+8], xmm1
0x18015f397  mov     r8, r13
0x18015f39a  lea     rdx, SubBlock; "\\"
0x18015f3a1  lea     rcx, [rsp+510h+pExceptionObject+8]
0x18015f3a6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18015f3ab  nop
0x18015f3ac  mov     dword ptr [rsp+510h+var_4C8], r13d
0x18015f3b1  xorps   xmm0, xmm0
0x18015f3b4  movups  [rbp+410h+var_468], xmm0
0x18015f3b8  xorps   xmm1, xmm1
0x18015f3bb  movdqu  [rbp+410h+var_458], xmm1
0x18015f3c0  mov     ebx, 3
0x18015f3c5  mov     r8d, ebx
0x18015f3c8  lea     rdx, asc_1802150F0; "\\.\\"
0x18015f3cf  lea     rcx, [rbp+410h+var_468]
0x18015f3d3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18015f3d8  nop
0x18015f3d9  mov     dword ptr [rsp+510h+var_4C8], ebx
0x18015f3dd  lea     r9, [rsp+510h+pExceptionObject+8]
0x18015f3e2  lea     r8, [rbp+410h+var_468]
0x18015f3e6  lea     rdx, [rbp+410h+var_488]
0x18015f3ea  call    ?ReplaceSubstring@CScriptReader@JScriptLib@@AEAA_KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@1@Z; JScriptLib::CScriptReader::ReplaceSubstring(std::wstring &,std::wstring const &,std::wstring const &)
0x18015f3ef  test    rax, rax
0x18015f3f2  jz      short loc_18015F413
0x18015f3f4  lea     rdx, [rbp+410h+var_488]
0x18015f3f8  cmp     [rbp+410h+var_470], 7
0x18015f3fd  cmova   rdx, [rbp+410h+var_488]; unsigned __int16 *
0x18015f402  lea     r8, [rbp+410h+szFilePath]; unsigned __int16 *
0x18015f406  call    ?IsFileNameValid@CScriptReader@JScriptLib@@AEAAHPEAG0@Z; JScriptLib::CScriptReader::IsFileNameValid(ushort *,ushort *)
0x18015f40b  test    eax, eax
0x18015f40d  jz      short loc_18015F413
0x18015f40f  xor     bl, bl
0x18015f411  jmp     short loc_18015F416
0x18015f413  mov     bl, r13b
0x18015f416  lea     rcx, [rbp+410h+var_468]
0x18015f41a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18015f41f  nop
0x18015f420  lea     rcx, [rsp+510h+pExceptionObject+8]
0x18015f425  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18015f42a  test    bl, bl
0x18015f42c  jnz     loc_18015F648
0x18015f432  lea     rcx, [rbp+410h+var_488]
0x18015f436  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18015f43b  mov     qword ptr [rsp+510h+dwFlagsAndAttributes], 0; lpName
0x18015f444  mov     [rsp+510h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18015f44c  xor     r9d, r9d; dwMaximumSizeHigh
0x18015f44f  xor     edx, edx; lpFileMappingAttributes
0x18015f451  lea     r8d, [r9+2]; flProtect
0x18015f455  mov     rcx, rdi; hFile
0x18015f458  call    cs:__imp_CreateFileMappingW
0x18015f45f  nop     dword ptr [rax+rax+00h]
0x18015f464  mov     rsi, rax
0x18015f467  mov     [rsp+510h+var_4C8], rax
0x18015f46c  inc     rax
0x18015f46f  test    rax, 0FFFFFFFFFFFFFFFEh
0x18015f475  jz      loc_18015F6A7
0x18015f47b  mov     qword ptr [rsp+510h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18015f484  xor     r9d, r9d; dwFileOffsetLow
0x18015f487  xor     r8d, r8d; dwFileOffsetHigh
0x18015f48a  mov     edx, r13d; dwDesiredAccess
0x18015f48d  mov     rcx, rsi; hFileMappingObject
0x18015f490  call    cs:__imp_MapViewOfFile
0x18015f497  nop     dword ptr [rax+rax+00h]
0x18015f49c  mov     rbx, rax
0x18015f49f  mov     qword ptr [rsp+510h+pExceptionObject], rax
0x18015f4a4  test    rax, rax
0x18015f4a7  jnz     short loc_18015F4C9
0x18015f4a9  call    cs:__imp_GetLastError
0x18015f4b0  nop     dword ptr [rax+rax+00h]
0x18015f4b5  test    eax, eax
0x18015f4b7  jle     short loc_18015F4C3
0x18015f4b9  movzx   eax, ax
0x18015f4bc  or      eax, 80070000h
0x18015f4c1  test    eax, eax
0x18015f4c3  js      loc_18015F6C0
0x18015f4c9  test    rbx, rbx
0x18015f4cc  jz      loc_18015F5DC
0x18015f4d2  cmp     r15d, 2
0x18015f4d6  jbe     short loc_18015F539
0x18015f4d8  cmp     byte ptr [rbx], 0FFh
0x18015f4db  jnz     short loc_18015F539
0x18015f4dd  cmp     byte ptr [rbx+1], 0FEh
0x18015f4e1  jnz     short loc_18015F539
0x18015f4e3  mov     rax, r15
0x18015f4e6  shr     rax, 1
0x18015f4e9  cmp     rax, r13
0x18015f4ec  jbe     loc_18015F57C
0x18015f4f2  lea     rcx, [r14+20h]
0x18015f4f6  lea     rdx, [rax-1]
0x18015f4fa  lea     r9, [rbx+2]
0x18015f4fe  cmp     rdx, [rcx+18h]
0x18015f502  ja      short loc_18015F532
0x18015f504  cmp     qword ptr [rcx+18h], 7
0x18015f509  jbe     short loc_18015F510
0x18015f50b  mov     r15, [rcx]
0x18015f50e  jmp     short loc_18015F513
0x18015f510  mov     r15, rcx
0x18015f513  mov     [rcx+10h], rdx
0x18015f517  lea     r14, [rdx+rdx]
0x18015f51b  mov     r8, r14; Size
0x18015f51e  mov     rdx, r9; Src
0x18015f521  mov     rcx, r15; void *
0x18015f524  call    memmove_0
0x18015f529  xor     eax, eax
0x18015f52b  mov     [r14+r15], ax
0x18015f530  jmp     short loc_18015F57C
0x18015f532  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18015f537  jmp     short loc_18015F57C
0x18015f539  cmp     r15d, 3
0x18015f53d  jbe     short loc_18015F568
0x18015f53f  cmp     byte ptr [rbx], 0EFh
0x18015f542  jnz     short loc_18015F568
0x18015f544  cmp     byte ptr [rbx+1], 0BBh
0x18015f548  jnz     short loc_18015F568
0x18015f54a  cmp     byte ptr [rbx+2], 0BFh
0x18015f54e  jnz     short loc_18015F568
0x18015f550  mov     r9, r15
0x18015f553  cmp     r15, 3
0x18015f557  jbe     short loc_18015F57C
0x18015f559  add     r9, 0FFFFFFFFFFFFFFFDh
0x18015f55d  lea     r8, [rbx+3]
0x18015f561  mov     edx, 0FDE9h
0x18015f566  jmp     short loc_18015F573
0x18015f568  mov     r9, r15; unsigned __int64
0x18015f56b  mov     r8, rbx; char *
0x18015f56e  mov     edx, 3; unsigned int
0x18015f573  mov     rcx, r14; this
0x18015f576  call    ?ConvertToUnicodeAndSetText@CScriptReader@JScriptLib@@AEAAXIPEBD_K@Z; JScriptLib::CScriptReader::ConvertToUnicodeAndSetText(uint,char const *,unsigned __int64)
0x18015f57b  nop
0x18015f57c  mov     rcx, rbx; lpBaseAddress
0x18015f57f  call    cs:__imp_UnmapViewOfFile
0x18015f586  nop     dword ptr [rax+rax+00h]
0x18015f58b  nop
0x18015f58c  mov     rcx, rsi; hObject
0x18015f58f  call    cs:__imp_CloseHandle
0x18015f596  nop     dword ptr [rax+rax+00h]
0x18015f59b  nop
0x18015f59c  test    rdi, rdi
0x18015f59f  jz      short loc_18015F5B0
0x18015f5a1  mov     rcx, rdi; hObject
0x18015f5a4  call    cs:__imp_CloseHandle
0x18015f5ab  nop     dword ptr [rax+rax+00h]
0x18015f5b0  mov     rcx, [rbp+410h+var_30]
0x18015f5b7  xor     rcx, rsp; StackCookie
0x18015f5ba  call    __security_check_cookie
0x18015f5bf  lea     r11, [rsp+510h+var_20]
0x18015f5c7  mov     rbx, [r11+38h]
0x18015f5cb  mov     rsi, [r11+40h]
0x18015f5cf  mov     rsp, r11
0x18015f5d2  pop     r15
0x18015f5d4  pop     r14
0x18015f5d6  pop     r13
0x18015f5d8  pop     rdi
0x18015f5d9  pop     rbp
0x18015f5da  retn
0x18015f5dc  mov     rcx, [rbp+418h]; this
0x18015f5e3  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\spooler\\"...
0x18015f5ea  mov     edx, 1CCh; void *
0x18015f5ef  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18015f5f5  mov     rcx, [rbp+418h]; this
0x18015f5fc  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\spooler\\"...
0x18015f603  mov     edx, 189h; void *
0x18015f608  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18015f60e  mov     rcx, [rbp+418h]; this
0x18015f615  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\spooler\\"...
0x18015f61c  mov     edx, 191h; void *
0x18015f621  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18015f627  mov     edx, 800700DFh; int
0x18015f62c  lea     rcx, [rsp+510h+pExceptionObject+8]; this
0x18015f631  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18015f636  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18015f63d  lea     rcx, [rsp+510h+pExceptionObject+8]; pExceptionObject
0x18015f642  call    _CxxThrowException_0
0x18015f648  mov     rcx, cs:WPP_GLOBAL_Control
0x18015f64f  cmp     rcx, rsi
0x18015f652  jz      short loc_18015F686
0x18015f654  test    [rcx+1Ch], r13b
  ... truncated ...
```
