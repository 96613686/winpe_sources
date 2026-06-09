# collectFileSelection

- ea: `0x1800efea4`
- end: `0x1800f02ab`
- name: `collectFileSelection`
- size: `1031`
- prototype: `signed int __fastcall(const WCHAR *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting`

## callers

- `0x1800f21ac`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800a9e20`
- `0x1800e66dc`
- `0x1800ece5c`
- `0x1800ed5fc`
- `0x1800ed6e4`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef900`
- `0x1800efea4`
- `0x180118a64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800efff0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f0009`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800efff0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f0009`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800f008e`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800f00e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800f008e`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800f00e0`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800effa7`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800effa7`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f00b3`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f0100`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f00b3`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f0100`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800f01ef`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800f01ef`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800effb9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800effb9`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800f0277`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800f0277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800effc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0183`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f01fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800effc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0183`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f01fd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800eff62`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800eff62`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800f0179`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800f0179`

## string_xrefs

- `0x1800f022d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800f0251`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800f0198`: `Failed to copy file: `

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall collectFileSelection(const WCHAR *a1, const unsigned __int16 *a2)
{
  HANDLE FirstFileW; // r15
  signed int result; // eax
  unsigned int v6; // ebx
  int v7; // edi
  char v8; // dl
  __int16 v9; // r8
  int v10; // r9d
  char v11; // di
  __int64 i; // r14
  char v13; // dl
  __int16 v14; // r8
  int v15; // r9d
  __int64 j; // rdi
  int v17; // r14d
  signed int v18; // eax
  const unsigned __int16 *v19; // rax
  TelemetryWriter *v20; // rcx
  signed int LastError; // eax
  __int64 v22; // rdx
  __int64 v23; // rdx
  int DirCount; // [rsp+20h] [rbp-E0h]
  wchar_t DirCounta; // [rsp+20h] [rbp-E0h]
  wchar_t *Filename; // [rsp+28h] [rbp-D8h]
  wchar_t *Filenamea; // [rsp+28h] [rbp-D8h]
  _BYTE v28[32]; // [rsp+50h] [rbp-B0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Dst[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+4D0h] [rbp+3D0h] BYREF
  WCHAR NewFileName[264]; // [rsp+6E0h] [rbp+5E0h] BYREF
  wchar_t Drive[264]; // [rsp+8F0h] [rbp+7F0h] BYREF
  wchar_t Dir[264]; // [rsp+B00h] [rbp+A00h] BYREF
  wchar_t Ext[264]; // [rsp+D10h] [rbp+C10h] BYREF
  wchar_t v36[264]; // [rsp+F20h] [rbp+E20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1168h] [rbp+1068h]

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(Drive, 0, 0x208u);
  memset_0(Dir, 0, 0x208u);
  memset_0(v36, 0, 0x208u);
  memset_0(Ext, 0, 0x208u);
  memset_0(Dst, 0, 0x208u);
  ExpandEnvironmentStringsW(a1, Dst, 0x104u);
  _wsplitpath_s(Dst, Drive, 0x104u, Dir, 0x104u, v36, 0x104u, Ext, 0x104u);
  FirstFileW = FindFirstFileW(Dst, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v6 = 0;
  while ( !(unsigned int)_o__wcsicmp(FindFileData.cFileName, L".")
       || !(unsigned int)_o__wcsicmp(FindFileData.cFileName, L"..")
       || (FindFileData.dwFileAttributes & 0x10) != 0 )
  {
LABEL_26:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      LastError = GetLastError();
      if ( LastError != 18 )
      {
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        else
          v6 = LastError;
      }
      goto LABEL_39;
    }
  }
  memset_0(NewFileName, 0, 0x208u);
  memset_0(ExistingFileName, 0, 0x208u);
  v7 = StringCchCopyW(ExistingFileName, 0x104u, Drive);
  if ( v7 < 0 )
  {
    v23 = 314;
    goto LABEL_37;
  }
  v7 = StringCchCatW(ExistingFileName, 0x104u, Dir);
  if ( v7 < 0 )
  {
    v23 = 316;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
      (const char *)(unsigned int)v7,
      DirCount);
    return v7;
  }
  v11 = 0;
  o((wchar_t)Dst, v8, v9, v10, DirCount, *(long double *)&Filename);
  for ( i = 0; i != 6; ++i )
  {
    if ( wcsstr(Dst, (const wchar_t *)&(&whitelistedFoldersExpanded)[65 * i]) )
      v11 = 1;
  }
  if ( v11 )
  {
    o((wchar_t)FindFileData.cFileName, v13, v14, v15, DirCounta, *(long double *)&Filenamea);
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      if ( (unsigned int)j >= 9 )
        goto LABEL_26;
      if ( wcsstr(FindFileData.cFileName, off_18019B8F0[j]) )
      {
        v17 = StringCchCatW(ExistingFileName, 0x104u, FindFileData.cFileName);
        if ( v17 < 0 )
        {
          v22 = 339;
          goto LABEL_33;
        }
        v17 = StringCchCopyW(NewFileName, 0x104u, a2);
        if ( v17 < 0 )
        {
          v22 = 341;
          goto LABEL_33;
        }
        v17 = StringCchCatW(NewFileName, 0x104u, FindFileData.cFileName);
        if ( v17 < 0 )
        {
          v22 = 343;
LABEL_33:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v22,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
            (const char *)(unsigned int)v17,
            DirCount);
          return v17;
        }
        if ( !CopyFileW(ExistingFileName, NewFileName, 0) )
        {
          v18 = GetLastError();
          v6 = v18;
          if ( v18 > 0 )
            v6 = (unsigned __int16)v18 | 0x80070000;
          std::wstring::wstring(v28, L"Failed to copy file: ");
          std::wstring::append(v28, ExistingFileName);
          v19 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
          TelemetryWriter::Write(v20, v19, v6);
          std::wstring::_Tidy_deallocate(v28);
        }
      }
    }
  }
  v6 = -2147418113;
LABEL_39:
  FindClose(FirstFileW);
  return v6;
}

```

## disassembly

```asm
0x1800efea4  mov     [rsp-8+arg_10], rbx
0x1800efea9  mov     [rsp-8+arg_18], rdi
0x1800efeae  push    rbp
0x1800efeaf  push    r12
0x1800efeb1  push    r13
0x1800efeb3  push    r14
0x1800efeb5  push    r15
0x1800efeb7  lea     rbp, [rsp-1040h]
0x1800efebf  mov     eax, 1140h
0x1800efec4  call    _alloca_probe
0x1800efec9  sub     rsp, rax
0x1800efecc  mov     rax, cs:__security_cookie
0x1800efed3  xor     rax, rsp
0x1800efed6  mov     [rbp+1060h+var_30], rax
0x1800efedd  mov     r12, rdx
0x1800efee0  mov     rbx, rcx
0x1800efee3  xor     edx, edx; Val
0x1800efee5  mov     r8d, 250h; Size
0x1800efeeb  lea     rcx, [rsp+1160h+FindFileData]; void *
0x1800efef0  call    memset_0
0x1800efef5  mov     edi, 208h
0x1800efefa  mov     r8d, edi; Size
0x1800efefd  xor     edx, edx; Val
0x1800efeff  lea     rcx, [rbp+1060h+Drive]; void *
0x1800eff06  call    memset_0
0x1800eff0b  mov     r8d, edi; Size
0x1800eff0e  xor     edx, edx; Val
0x1800eff10  lea     rcx, [rbp+1060h+Dir]; void *
0x1800eff17  call    memset_0
0x1800eff1c  mov     r8d, edi; Size
0x1800eff1f  xor     edx, edx; Val
0x1800eff21  lea     rcx, [rbp+1060h+var_240]; void *
0x1800eff28  call    memset_0
0x1800eff2d  mov     r8d, edi; Size
0x1800eff30  xor     edx, edx; Val
0x1800eff32  lea     rcx, [rbp+1060h+var_450]; void *
0x1800eff39  call    memset_0
0x1800eff3e  mov     r8d, edi; Size
0x1800eff41  xor     edx, edx; Val
0x1800eff43  lea     rcx, [rbp+1060h+Dst]; void *
0x1800eff4a  call    memset_0
0x1800eff4f  mov     r13d, 104h
0x1800eff55  mov     r8d, r13d; nSize
0x1800eff58  lea     rdx, [rbp+1060h+Dst]; lpDst
0x1800eff5f  mov     rcx, rbx; lpSrc
0x1800eff62  call    cs:__imp_ExpandEnvironmentStringsW
0x1800eff68  mov     [rsp+1160h+ExtCount], r13; ExtCount
0x1800eff6d  lea     rax, [rbp+1060h+var_450]
0x1800eff74  mov     [rsp+1160h+Ext], rax; Ext
0x1800eff79  mov     [rsp+1160h+FilenameCount], r13; FilenameCount
0x1800eff7e  lea     rax, [rbp+1060h+var_240]
0x1800eff85  mov     [rsp+1160h+Filename], rax; Filename
0x1800eff8a  mov     [rsp+1160h+DirCount], r13; int
0x1800eff8f  lea     r9, [rbp+1060h+Dir]; Dir
0x1800eff96  mov     r8d, r13d; DriveCount
0x1800eff99  lea     rdx, [rbp+1060h+Drive]; Drive
0x1800effa0  lea     rcx, [rbp+1060h+Dst]; FullPath
0x1800effa7  call    cs:__imp__wsplitpath_s
0x1800effad  lea     rdx, [rsp+1160h+FindFileData]; lpFindFileData
0x1800effb2  lea     rcx, [rbp+1060h+Dst]; lpFileName
0x1800effb9  call    cs:__imp_FindFirstFileW
0x1800effbf  mov     r15, rax
0x1800effc2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800effc6  jnz     short loc_1800EFFE3
0x1800effc8  call    cs:__imp_GetLastError
0x1800effce  test    eax, eax
0x1800effd0  jle     loc_1800F027F
0x1800effd6  movzx   eax, ax
0x1800effd9  or      eax, 80070000h
0x1800effde  jmp     loc_1800F027F
0x1800effe3  xor     ebx, ebx
0x1800effe5  lea     rdx, asc_1801BA058; "."
0x1800effec  lea     rcx, [rbp+1060h+FindFileData.cFileName]
0x1800efff0  call    cs:__imp__o__wcsicmp
0x1800efff6  test    eax, eax
0x1800efff8  jz      loc_1800F01E7
0x1800efffe  lea     rdx, asc_1801BAB04; ".."
0x1800f0005  lea     rcx, [rbp+1060h+FindFileData.cFileName]
0x1800f0009  call    cs:__imp__o__wcsicmp
0x1800f000f  test    eax, eax
0x1800f0011  jz      loc_1800F01E7
0x1800f0017  test    byte ptr [rsp+1160h+FindFileData.dwFileAttributes], 10h
0x1800f001c  jnz     loc_1800F01E7
0x1800f0022  mov     r8, rdi; Size
0x1800f0025  xor     edx, edx; Val
0x1800f0027  lea     rcx, [rbp+1060h+NewFileName]; void *
0x1800f002e  call    memset_0
0x1800f0033  mov     r8, rdi; Size
0x1800f0036  xor     edx, edx; Val
0x1800f0038  lea     rcx, [rbp+1060h+ExistingFileName]; void *
0x1800f003f  call    memset_0
0x1800f0044  lea     r8, [rbp+1060h+Drive]; unsigned __int16 *
0x1800f004b  mov     rdx, r13; unsigned __int64
0x1800f004e  lea     rcx, [rbp+1060h+ExistingFileName]; unsigned __int16 *
0x1800f0055  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f005a  mov     edi, eax
0x1800f005c  test    eax, eax
0x1800f005e  js      loc_1800F024C
0x1800f0064  lea     r8, [rbp+1060h+Dir]; unsigned __int16 *
0x1800f006b  mov     rdx, r13; unsigned __int64
0x1800f006e  lea     rcx, [rbp+1060h+ExistingFileName]; unsigned __int16 *
0x1800f0075  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f007a  mov     edi, eax
0x1800f007c  test    eax, eax
0x1800f007e  js      loc_1800F0245
0x1800f0084  xor     dil, dil
0x1800f0087  lea     rcx, [rbp+1060h+Dst]
0x1800f008e  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1800f0094  xor     r14d, r14d
0x1800f0097  lea     r13d, [r14+1]
0x1800f009b  imul    rdx, r14, 208h
0x1800f00a2  lea     rax, ?whitelistedFoldersExpanded@@3PAY0BAE@GA; ushort (near * whitelistedFoldersExpanded)[260]
0x1800f00a9  add     rdx, rax; SubStr
0x1800f00ac  lea     rcx, [rbp+1060h+Dst]; Str
0x1800f00b3  call    cs:__imp_wcsstr
0x1800f00b9  movzx   edi, dil
0x1800f00bd  test    rax, rax
0x1800f00c0  cmovnz  edi, r13d
0x1800f00c4  add     r14, r13
0x1800f00c7  cmp     r14, 6
0x1800f00cb  jnz     short loc_1800F009B
0x1800f00cd  mov     r13d, 104h
0x1800f00d3  test    dil, dil
0x1800f00d6  jz      loc_1800F023E
0x1800f00dc  lea     rcx, [rbp+1060h+FindFileData.cFileName]
0x1800f00e0  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1800f00e6  xor     edi, edi
0x1800f00e8  cmp     edi, 9
0x1800f00eb  jnb     loc_1800F01E2
0x1800f00f1  lea     rax, off_18019B8F0; ".log"
0x1800f00f8  mov     rdx, [rax+rdi*8]; SubStr
0x1800f00fc  lea     rcx, [rbp+1060h+FindFileData.cFileName]; Str
0x1800f0100  call    cs:__imp_wcsstr
0x1800f0106  test    rax, rax
0x1800f0109  jz      loc_1800F01DB
0x1800f010f  lea     r8, [rbp+1060h+FindFileData.cFileName]; unsigned __int16 *
0x1800f0113  mov     rdx, r13; unsigned __int64
0x1800f0116  lea     rcx, [rbp+1060h+ExistingFileName]; unsigned __int16 *
0x1800f011d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f0122  mov     r14d, eax
0x1800f0125  test    eax, eax
0x1800f0127  js      loc_1800F021E
0x1800f012d  mov     r8, r12; unsigned __int16 *
0x1800f0130  mov     rdx, r13; unsigned __int64
0x1800f0133  lea     rcx, [rbp+1060h+NewFileName]; unsigned __int16 *
0x1800f013a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f013f  mov     r14d, eax
0x1800f0142  test    eax, eax
0x1800f0144  js      loc_1800F0217
0x1800f014a  lea     r8, [rbp+1060h+FindFileData.cFileName]; unsigned __int16 *
0x1800f014e  mov     rdx, r13; unsigned __int64
0x1800f0151  lea     rcx, [rbp+1060h+NewFileName]; unsigned __int16 *
0x1800f0158  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f015d  mov     r14d, eax
0x1800f0160  test    eax, eax
0x1800f0162  js      loc_1800F0210
0x1800f0168  xor     r8d, r8d; bFailIfExists
0x1800f016b  lea     rdx, [rbp+1060h+NewFileName]; lpNewFileName
0x1800f0172  lea     rcx, [rbp+1060h+ExistingFileName]; lpExistingFileName
0x1800f0179  call    cs:__imp_CopyFileW
0x1800f017f  test    eax, eax
0x1800f0181  jnz     short loc_1800F01DB
0x1800f0183  call    cs:__imp_GetLastError
0x1800f0189  mov     ebx, eax
0x1800f018b  test    eax, eax
0x1800f018d  jle     short loc_1800F0198
0x1800f018f  movzx   ebx, ax
0x1800f0192  or      ebx, 80070000h
0x1800f0198  lea     rdx, aFailedToCopyFi; "Failed to copy file: "
0x1800f019f  lea     rcx, [rsp+1160h+var_1110]
0x1800f01a4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f01a9  nop
0x1800f01aa  lea     rdx, [rbp+1060h+ExistingFileName]
0x1800f01b1  lea     rcx, [rsp+1160h+var_1110]
0x1800f01b6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800f01bb  lea     rcx, [rsp+1160h+var_1110]
0x1800f01c0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f01c5  mov     rdx, rax; unsigned __int16 *
0x1800f01c8  mov     r8d, ebx; int
0x1800f01cb  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x1800f01d0  nop
0x1800f01d1  lea     rcx, [rsp+1160h+var_1110]
0x1800f01d6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f01db  inc     edi
0x1800f01dd  jmp     loc_1800F00E8
0x1800f01e2  mov     edi, 208h
0x1800f01e7  lea     rdx, [rsp+1160h+FindFileData]; lpFindFileData
0x1800f01ec  mov     rcx, r15; hFindFile
0x1800f01ef  call    cs:__imp_FindNextFileW
0x1800f01f5  test    eax, eax
0x1800f01f7  jnz     loc_1800EFFE5
0x1800f01fd  call    cs:__imp_GetLastError
0x1800f0203  cmp     eax, 12h
0x1800f0206  jz      short loc_1800F0274
0x1800f0208  test    eax, eax
0x1800f020a  jg      short loc_1800F026B
0x1800f020c  mov     ebx, eax
0x1800f020e  jmp     short loc_1800F0274
0x1800f0210  mov     edx, 157h
0x1800f0215  jmp     short loc_1800F0223
0x1800f0217  mov     edx, 155h
0x1800f021c  jmp     short loc_1800F0223
0x1800f021e  mov     edx, 153h; void *
0x1800f0223  mov     rcx, [rbp+1068h]; this
0x1800f022a  mov     r9d, r14d; char *
0x1800f022d  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f0234  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0239  mov     eax, r14d
0x1800f023c  jmp     short loc_1800F027F
0x1800f023e  mov     ebx, 8000FFFFh
0x1800f0243  jmp     short loc_1800F0274
0x1800f0245  mov     edx, 13Ch
0x1800f024a  jmp     short loc_1800F0251
0x1800f024c  mov     edx, 13Ah; void *
0x1800f0251  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f0258  mov     r9d, edi; char *
0x1800f025b  mov     rcx, [rbp+1068h]; this
0x1800f0262  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0267  mov     eax, edi
0x1800f0269  jmp     short loc_1800F027F
0x1800f026b  movzx   ebx, ax
0x1800f026e  or      ebx, 80070000h
0x1800f0274  mov     rcx, r15; hFindFile
0x1800f0277  call    cs:__imp_FindClose
0x1800f027d  mov     eax, ebx
0x1800f027f  mov     rcx, [rbp+1060h+var_30]
0x1800f0286  xor     rcx, rsp; StackCookie
0x1800f0289  call    __security_check_cookie
0x1800f028e  lea     r11, [rsp+1160h+var_20]
0x1800f0296  mov     rbx, [r11+40h]
0x1800f029a  mov     rdi, [r11+48h]
0x1800f029e  mov     rsp, r11
0x1800f02a1  pop     r15
0x1800f02a3  pop     r14
0x1800f02a5  pop     r13
0x1800f02a7  pop     r12
0x1800f02a9  pop     rbp
0x1800f02aa  retn
```
