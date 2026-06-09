# fdi_notify_generic(FDINOTIFICATIONTYPE,FDINOTIFICATION *)

- ea: `0x180030d60`
- end: `0x180031162`
- name: `?fdi_notify_generic@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z`
- size: `1026`
- prototype: `INT_PTR __fastcall(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, installer_update`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x18000d524`
- `0x180023634`
- `0x18002386c`
- `0x180029c3c`
- `0x18002a948`
- `0x18002a9ec`
- `0x18002b63c`
- `0x18002b9f4`
- `0x18002f764`
- `0x18002fa88`
- `0x18002fc44`
- `0x18003084c`
- `0x180030d60`
- `0x180031c30`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18003105b`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18003105b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180030ef5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180030ef5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031099`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800310a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800310a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030ec9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030ec9`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180030ff0`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180030ff0`
- `SHLWAPI!StrStrIA` at `0x180030f92`
- `SHLWAPI!StrStrIA` at `0x180030f92`

## string_xrefs

- `0x180031000`: `GetTempPath2W failed with error: %x`
- `0x18003106b`: `GetTempFileNameW failed with error: %x`
- `0x1800310c2`: `Failed to create temp file %s for %s with error: %x`
- `0x180031143`: `Created temp file %s for %s`

## pseudocode

```c
INT_PTR __fastcall fdi_notify_generic(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)
{
  char v3; // si
  int v4; // ecx
  void *hf; // r12
  __int64 v6; // rcx
  __int64 FileW; // rdi
  __int64 v8; // rbx
  char v9; // r15
  _OWORD *v10; // rax
  int v11; // esi
  __int64 v12; // rax
  __int64 v13; // rax
  const WCHAR *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  DWORD v18; // eax
  DWORD LastError; // eax
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v28; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v29; // [rsp+58h] [rbp-A8h]
  _OWORD v30[2]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v31[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v32[32]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v33[40]; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR TempFileName[264]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR PathName[264]; // [rsp+300h] [rbp+200h] BYREF

  LODWORD(v27) = 0;
  v3 = 2;
  v4 = fdint - 2;
  if ( !v4 )
  {
    std::string::string(v31, pfdin->psz1);
    Utf8ToWide(&v28, v31);
    std::string::_Tidy_deallocate(v31);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v28);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_1800A37F8);
    v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_1800A3838);
    SBServicingLogMessage((wchar_t *)L"Generic For ConfidenceLevel %s Generic OEMName %s checking file %s", v16);
    if ( StrStrIA(pfdin->psz1, "Generic") && !qword_1800A3848 )
    {
      v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v28);
      SBServicingLogMessage((wchar_t *)L"Generic OEM file found: %s", v17);
      memset_0(PathName, 0, 0x208u);
      memset_0(TempFileName, 0, 0x208u);
      if ( (unsigned int)GetTempPath2W(260, PathName) )
      {
        if ( GetTempFileNameW(PathName, L"cab_generic", 0, TempFileName) )
        {
          FileW = (__int64)CreateFileW(TempFileName, 0xC0000000, 1u, 0, 2u, 0x100u, 0);
          if ( FileW == -1 )
          {
            GetLastError();
            v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v28);
            SBServicingLogMessage((wchar_t *)L"Failed to create temp file %s for %s with error: %x", TempFileName, v21);
            FileW = 0;
          }
          else
          {
            std::wstring::wstring(v30, TempFileName);
            v22 = WideToUtf8(v33, v30);
            v23 = std::string::string(v32, pfdin->psz1);
            v25 = std::map<std::string,std::string>::operator[](v24, v23);
            std::string::operator=(v25, v22);
            std::string::_Tidy_deallocate(v32);
            std::string::_Tidy_deallocate(v33);
            std::wstring::_Tidy_deallocate(v30);
            v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v28);
            SBServicingLogMessage((wchar_t *)L"Created temp file %s for %s", TempFileName, v26);
          }
          std::wstring::_Tidy_deallocate(&v28);
          return FileW;
        }
        LastError = GetLastError();
        SBServicingLogMessage(L"GetTempFileNameW failed with error: %x", LastError);
      }
      else
      {
        v18 = GetLastError();
        SBServicingLogMessage((wchar_t *)L"GetTempPath2W failed with error: %x", v18);
      }
    }
    std::wstring::_Tidy_deallocate(&v28);
    return 0;
  }
  if ( v4 != 1 )
    return 0;
  hf = (void *)pfdin->hf;
  std::string::string(v31, pfdin->psz1);
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::find(
    v6,
    &v27,
    v31);
  FileW = 1;
  v8 = v27;
  if ( v27 == g_OrgToTmpFileMap )
  {
    v9 = 0;
    v30[0] = 0;
    v30[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v30[0]) = 0;
    v10 = v30;
  }
  else
  {
    v9 = 1;
    v10 = (_OWORD *)std::string::string(v32, v27 + 64);
    v3 = 1;
  }
  v28 = 0;
  v29 = 0;
  v28 = *v10;
  v29 = v10[1];
  *((_QWORD *)v10 + 2) = 0;
  *((_QWORD *)v10 + 3) = 15;
  *(_BYTE *)v10 = 0;
  if ( (v3 & 2) != 0 )
  {
    v3 &= ~2u;
    std::string::_Tidy_deallocate(v30);
  }
  if ( (v3 & 1) != 0 )
    std::string::_Tidy_deallocate(v32);
  if ( !v9 )
    goto LABEL_13;
  std::wstring::wstring(v30, L"Generic OEM");
  v11 = TryParseFromConfidenceFilesForOEMFromFDI(&v28, v30);
  std::wstring::_Tidy_deallocate(v30);
  if ( v11 < 0 )
  {
    v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_1800A37F8);
    SBServicingLogMessage(
      (wchar_t *)L"Failed in TryParseFromConfidenceFilesForOEM for OEM %s: %x",
      v12,
      (unsigned int)v11);
LABEL_13:
    FileW = 0;
  }
  CloseHandle(hf);
  pfdin->hf = 0;
  if ( v9 )
  {
    v13 = Utf8ToWide(v32, &v28);
    v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
    DeleteFileW(v14);
    std::wstring::_Tidy_deallocate(v32);
    std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>>,0>(
      v15,
      &v27,
      v8);
  }
  std::string::_Tidy_deallocate(&v28);
  std::string::_Tidy_deallocate(v31);
  return FileW;
}

```

## disassembly

```asm
0x180030d60  mov     [rsp-8+arg_0], rbx
0x180030d65  mov     [rsp-8+arg_10], rsi
0x180030d6a  push    rbp
0x180030d6b  push    rdi
0x180030d6c  push    r12
0x180030d6e  push    r14
0x180030d70  push    r15
0x180030d72  lea     rbp, [rsp-420h]
0x180030d7a  sub     rsp, 520h
0x180030d81  mov     rax, cs:__security_cookie
0x180030d88  xor     rax, rsp
0x180030d8b  mov     [rbp+440h+var_30], rax
0x180030d92  mov     r14, rdx
0x180030d95  mov     dword ptr [rsp+540h+var_500], 0
0x180030d9d  mov     esi, 2
0x180030da2  sub     ecx, esi
0x180030da4  jz      loc_180030F2B
0x180030daa  cmp     ecx, 1
0x180030dad  jnz     loc_180031019
0x180030db3  mov     r12, [rdx+28h]
0x180030db7  mov     rdx, [rdx+8]
0x180030dbb  lea     rcx, [rbp+440h+var_4B8]
0x180030dbf  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180030dc4  nop
0x180030dc5  lea     r8, [rbp+440h+var_4B8]
0x180030dc9  lea     rdx, [rsp+540h+var_500]
0x180030dce  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::find(std::string const &)
0x180030dd3  lea     edi, [rsi-1]
0x180030dd6  mov     rbx, [rsp+540h+var_500]
0x180030ddb  cmp     rbx, cs:?g_OrgToTmpFileMap@@3V?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@A; std::map<std::string,std::string> g_OrgToTmpFileMap
0x180030de2  jz      short loc_180030DF8
0x180030de4  mov     r15b, dil
0x180030de7  lea     rdx, [rbx+40h]
0x180030deb  lea     rcx, [rbp+440h+var_498]
0x180030def  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180030df4  mov     esi, edi
0x180030df6  jmp     short loc_180030E1B
0x180030df8  xor     r15b, r15b
0x180030dfb  xorps   xmm0, xmm0
0x180030dfe  movups  [rsp+540h+var_4D8], xmm0
0x180030e03  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180030e0b  movdqu  [rsp+540h+var_4C8], xmm1
0x180030e11  mov     byte ptr [rsp+540h+var_4D8], r15b
0x180030e16  lea     rax, [rsp+540h+var_4D8]
0x180030e1b  xorps   xmm0, xmm0
0x180030e1e  movups  [rsp+540h+var_4F8], xmm0
0x180030e23  xorps   xmm1, xmm1
0x180030e26  movdqu  [rsp+540h+var_4E8], xmm1
0x180030e2c  movups  xmm0, xmmword ptr [rax]
0x180030e2f  movups  [rsp+540h+var_4F8], xmm0
0x180030e34  movups  xmm1, xmmword ptr [rax+10h]
0x180030e38  movups  [rsp+540h+var_4E8], xmm1
0x180030e3d  mov     qword ptr [rax+10h], 0
0x180030e45  mov     qword ptr [rax+18h], 0Fh
0x180030e4d  mov     byte ptr [rax], 0
0x180030e50  test    sil, 2
0x180030e54  jz      short loc_180030E63
0x180030e56  and     esi, 0FFFFFFFDh
0x180030e59  lea     rcx, [rsp+540h+var_4D8]
0x180030e5e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180030e63  test    dil, sil
0x180030e66  jz      short loc_180030E71
0x180030e68  lea     rcx, [rbp+440h+var_498]
0x180030e6c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180030e71  test    r15b, r15b
0x180030e74  jz      short loc_180030EC4
0x180030e76  lea     rdx, aGenericOem_0; "Generic OEM"
0x180030e7d  lea     rcx, [rsp+540h+var_4D8]
0x180030e82  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180030e87  lea     rdx, [rsp+540h+var_4D8]
0x180030e8c  lea     rcx, [rsp+540h+var_4F8]
0x180030e91  call    ?TryParseFromConfidenceFilesForOEMFromFDI@@YAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; TryParseFromConfidenceFilesForOEMFromFDI(std::string const &,std::wstring const &)
0x180030e96  mov     esi, eax
0x180030e98  lea     rcx, [rsp+540h+var_4D8]
0x180030e9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030ea2  test    esi, esi
0x180030ea4  jns     short loc_180030EC6
0x180030ea6  lea     rcx, qword_1800A37F8
0x180030ead  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030eb2  mov     rdx, rax
0x180030eb5  mov     r8d, esi
0x180030eb8  lea     rcx, aFailedInTrypar; "Failed in TryParseFromConfidenceFilesFo"...
0x180030ebf  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180030ec4  xor     edi, edi
0x180030ec6  mov     rcx, r12; hObject
0x180030ec9  call    cs:__imp_CloseHandle
0x180030ecf  mov     qword ptr [r14+28h], 0
0x180030ed7  test    r15b, r15b
0x180030eda  jz      short loc_180030F12
0x180030edc  lea     rdx, [rsp+540h+var_4F8]
0x180030ee1  lea     rcx, [rbp+440h+var_498]
0x180030ee5  call    ?Utf8ToWide@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; Utf8ToWide(std::string const &)
0x180030eea  mov     rcx, rax
0x180030eed  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030ef2  mov     rcx, rax; lpFileName
0x180030ef5  call    cs:__imp_DeleteFileW
0x180030efb  lea     rcx, [rbp+440h+var_498]
0x180030eff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030f04  mov     r8, rbx
0x180030f07  lea     rdx, [rsp+540h+var_500]
0x180030f0c  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>>)
0x180030f11  nop
0x180030f12  lea     rcx, [rsp+540h+var_4F8]
0x180030f17  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180030f1c  nop
0x180030f1d  lea     rcx, [rbp+440h+var_4B8]
0x180030f21  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180030f26  jmp     loc_18003115A
0x180030f2b  mov     rdx, [rdx+8]
0x180030f2f  lea     rcx, [rbp+440h+var_4B8]
0x180030f33  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180030f38  lea     rdx, [rbp+440h+var_4B8]
0x180030f3c  lea     rcx, [rsp+540h+var_4F8]
0x180030f41  call    ?Utf8ToWide@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; Utf8ToWide(std::string const &)
0x180030f46  nop
0x180030f47  lea     rcx, [rbp+440h+var_4B8]
0x180030f4b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180030f50  lea     rcx, [rsp+540h+var_4F8]
0x180030f55  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030f5a  mov     r9, rax
0x180030f5d  lea     rcx, qword_1800A37F8
0x180030f64  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030f69  mov     r8, rax
0x180030f6c  lea     rcx, qword_1800A3838
0x180030f73  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030f78  mov     rdx, rax
0x180030f7b  lea     rcx, aGenericForConf; "Generic For ConfidenceLevel %s Generic "...
0x180030f82  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180030f87  lea     rdx, pszSrch; "Generic"
0x180030f8e  mov     rcx, [r14+8]; pszFirst
0x180030f92  call    cs:__imp_StrStrIA
0x180030f98  test    rax, rax
0x180030f9b  jz      short loc_18003100F
0x180030f9d  cmp     cs:qword_1800A3848, 0
0x180030fa5  jnz     short loc_18003100F
0x180030fa7  lea     rcx, [rsp+540h+var_4F8]
0x180030fac  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030fb1  mov     rdx, rax
0x180030fb4  lea     rcx, aGenericOemFile; "Generic OEM file found: %s"
0x180030fbb  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180030fc0  mov     ebx, 208h
0x180030fc5  mov     r8d, ebx; Size
0x180030fc8  xor     edx, edx; Val
0x180030fca  lea     rcx, [rbp+440h+PathName]; void *
0x180030fd1  call    memset_0
0x180030fd6  mov     r8d, ebx; Size
0x180030fd9  xor     edx, edx; Val
0x180030fdb  lea     rcx, [rbp+440h+TempFileName]; void *
0x180030fdf  call    memset_0
0x180030fe4  lea     rdx, [rbp+440h+PathName]
0x180030feb  mov     ecx, 104h
0x180030ff0  call    cs:__imp_GetTempPath2W
0x180030ff6  test    eax, eax
0x180030ff8  jnz     short loc_180031046
0x180030ffa  call    cs:__imp_GetLastError
0x180031000  lea     rcx, aGettemppath2wF; "GetTempPath2W failed with error: %x"
0x180031007  mov     edx, eax
0x180031009  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003100e  nop
0x18003100f  lea     rcx, [rsp+540h+var_4F8]
0x180031014  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031019  xor     eax, eax
0x18003101b  mov     rcx, [rbp+440h+var_30]
0x180031022  xor     rcx, rsp; StackCookie
0x180031025  call    __security_check_cookie
0x18003102a  lea     r11, [rsp+540h+var_20]
0x180031032  mov     rbx, [r11+30h]
0x180031036  mov     rsi, [r11+40h]
0x18003103a  mov     rsp, r11
0x18003103d  pop     r15
0x18003103f  pop     r14
0x180031041  pop     r12
0x180031043  pop     rdi
0x180031044  pop     rbp
0x180031045  retn
0x180031046  lea     r9, [rbp+440h+TempFileName]; lpTempFileName
0x18003104a  xor     r8d, r8d; uUnique
0x18003104d  lea     rdx, PrefixString; "cab_generic"
0x180031054  lea     rcx, [rbp+440h+PathName]; lpPathName
0x18003105b  call    cs:__imp_GetTempFileNameW
0x180031061  test    eax, eax
0x180031063  jnz     short loc_180031074
0x180031065  call    cs:__imp_GetLastError
0x18003106b  lea     rcx, aGettempfilenam; "GetTempFileNameW failed with error: %x"
0x180031072  jmp     short loc_180031007
0x180031074  mov     [rsp+540h+hTemplateFile], 0; hTemplateFile
0x18003107d  mov     [rsp+540h+dwFlagsAndAttributes], 100h; dwFlagsAndAttributes
0x180031085  mov     [rsp+540h+dwCreationDisposition], esi; dwCreationDisposition
0x180031089  xor     r9d, r9d; lpSecurityAttributes
0x18003108c  mov     edx, 0C0000000h; dwDesiredAccess
0x180031091  lea     r8d, [r9+1]; dwShareMode
0x180031095  lea     rcx, [rbp+440h+TempFileName]; lpFileName
0x180031099  call    cs:__imp_CreateFileW
0x18003109f  mov     rdi, rax
0x1800310a2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800310a6  jnz     short loc_1800310D2
0x1800310a8  call    cs:__imp_GetLastError
0x1800310ae  mov     r9d, eax
0x1800310b1  lea     rcx, [rsp+540h+var_4F8]
0x1800310b6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800310bb  mov     r8, rax
0x1800310be  lea     rdx, [rbp+440h+TempFileName]
0x1800310c2  lea     rcx, aFailedToCreate_0; "Failed to create temp file %s for %s wi"...
0x1800310c9  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800310ce  xor     edi, edi
0x1800310d0  jmp     short loc_180031150
0x1800310d2  lea     rdx, [rbp+440h+TempFileName]
0x1800310d6  lea     rcx, [rsp+540h+var_4D8]
0x1800310db  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800310e0  nop
0x1800310e1  lea     rdx, [rsp+540h+var_4D8]
0x1800310e6  lea     rcx, [rbp+440h+var_478]
0x1800310ea  call    ?WideToUtf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; WideToUtf8(std::wstring const &)
0x1800310ef  mov     rbx, rax
0x1800310f2  mov     rdx, [r14+8]
0x1800310f6  lea     rcx, [rbp+440h+var_498]
0x1800310fa  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800310ff  nop
0x180031100  mov     rdx, rax
0x180031103  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@$$QEAV21@@Z; std::map<std::string,std::string>::operator[](std::string &&)
0x180031108  mov     rcx, rax
0x18003110b  mov     rdx, rbx
0x18003110e  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180031113  nop
0x180031114  lea     rcx, [rbp+440h+var_498]
0x180031118  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003111d  nop
0x18003111e  lea     rcx, [rbp+440h+var_478]
0x180031122  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180031127  nop
0x180031128  lea     rcx, [rsp+540h+var_4D8]
0x18003112d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031132  lea     rcx, [rsp+540h+var_4F8]
0x180031137  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003113c  mov     r8, rax
0x18003113f  lea     rdx, [rbp+440h+TempFileName]
0x180031143  lea     rcx, aCreatedTempFil; "Created temp file %s for %s"
0x18003114a  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003114f  nop
0x180031150  lea     rcx, [rsp+540h+var_4F8]
0x180031155  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003115a  mov     rax, rdi
0x18003115d  jmp     loc_18003101B
```
