# fdi_notify_metadata(FDINOTIFICATIONTYPE,FDINOTIFICATION *)

- ea: `0x180031170`
- end: `0x18003150c`
- name: `?fdi_notify_metadata@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z`
- size: `924`
- prototype: `INT_PTR __fastcall(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, installer_update`

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
- `0x18002cfac`
- `0x18002fa88`
- `0x18002fc44`
- `0x18003084c`
- `0x180031170`
- `0x180031c30`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180031405`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180031405`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800312f9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800312f9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031443`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800313a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003140f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800313a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003140f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031452`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800312cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800312cd`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18003139a`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18003139a`
- `SHLWAPI!StrStrIA` at `0x18003133a`
- `SHLWAPI!StrStrIA` at `0x18003133a`

## string_xrefs

- `0x18003132f`: `BucketConfidenceMetadata.json`
- `0x1800313aa`: `GetTempPath2W failed with error: %x`
- `0x180031415`: `GetTempFileNameW failed with error: %x`
- `0x18003146c`: `Failed to create temp file %s for %s with error: %x`
- `0x1800314ed`: `Created temp file %s for %s`
- `0x1800312b2`: `Failed to parse Metadata JSON file %s: %x`

## pseudocode

```c
INT_PTR __fastcall fdi_notify_metadata(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)
{
  char v3; // si
  int v4; // ecx
  void *hf; // r12
  __int64 v6; // rcx
  __int64 FileW; // rdi
  __int64 v8; // rbx
  char v9; // r15
  _OWORD *v10; // rax
  int ConfidenceFileMetadataInfo; // esi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  const WCHAR *v15; // rax
  __int64 v16; // rcx
  DWORD v17; // eax
  DWORD LastError; // eax
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v27; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v28; // [rsp+58h] [rbp-A8h]
  _OWORD v29[2]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v30[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v31[32]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v32[40]; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR TempFileName[264]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR PathName[264]; // [rsp+300h] [rbp+200h] BYREF

  LODWORD(v26) = 0;
  v3 = 2;
  v4 = fdint - 2;
  if ( !v4 )
  {
    if ( StrStrIA(pfdin->psz1, "BucketConfidenceMetadata.json") )
    {
      std::string::string(v31, pfdin->psz1);
      Utf8ToWide(&v27, v31);
      std::string::_Tidy_deallocate(v31);
      memset_0(PathName, 0, 0x208u);
      memset_0(TempFileName, 0, 0x208u);
      if ( (unsigned int)GetTempPath2W(260, PathName) )
      {
        if ( GetTempFileNameW(PathName, L"cab_metadata", 0, TempFileName) )
        {
          FileW = (__int64)CreateFileW(TempFileName, 0xC0000000, 1u, 0, 2u, 0x100u, 0);
          if ( FileW == -1 )
          {
            GetLastError();
            v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v27);
            SBServicingLogMessage((wchar_t *)L"Failed to create temp file %s for %s with error: %x", TempFileName, v20);
            FileW = 0;
          }
          else
          {
            std::wstring::wstring(v29, TempFileName);
            v21 = WideToUtf8(v32, v29);
            v22 = std::string::string(v30, pfdin->psz1);
            v24 = std::map<std::string,std::string>::operator[](v23, v22);
            std::string::operator=(v24, v21);
            std::string::_Tidy_deallocate(v30);
            std::string::_Tidy_deallocate(v32);
            std::wstring::_Tidy_deallocate(v29);
            v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v27);
            SBServicingLogMessage((wchar_t *)L"Created temp file %s for %s", TempFileName, v25);
          }
          std::wstring::_Tidy_deallocate(&v27);
          return FileW;
        }
        LastError = GetLastError();
        SBServicingLogMessage(L"GetTempFileNameW failed with error: %x", LastError);
      }
      else
      {
        v17 = GetLastError();
        SBServicingLogMessage((wchar_t *)L"GetTempPath2W failed with error: %x", v17);
      }
      std::wstring::_Tidy_deallocate(&v27);
    }
    return 0;
  }
  if ( v4 != 1 )
    return 0;
  hf = (void *)pfdin->hf;
  std::string::string(v31, pfdin->psz1);
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::find(
    v6,
    &v26,
    v31);
  FileW = 1;
  v8 = v26;
  if ( v26 == g_OrgToTmpFileMap )
  {
    v9 = 0;
    v29[0] = 0;
    v29[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v29[0]) = 0;
    v10 = v29;
  }
  else
  {
    v9 = 1;
    v10 = (_OWORD *)std::string::string(v30, v26 + 64);
    v3 = 1;
  }
  v27 = 0;
  v28 = 0;
  v27 = *v10;
  v28 = v10[1];
  *((_QWORD *)v10 + 2) = 0;
  *((_QWORD *)v10 + 3) = 15;
  *(_BYTE *)v10 = 0;
  if ( (v3 & 2) != 0 )
  {
    v3 &= ~2u;
    std::string::_Tidy_deallocate(v29);
  }
  if ( (v3 & 1) != 0 )
    std::string::_Tidy_deallocate(v30);
  if ( !v9 )
    goto LABEL_13;
  ConfidenceFileMetadataInfo = GetConfidenceFileMetadataInfo(&v27);
  if ( ConfidenceFileMetadataInfo < 0 )
  {
    v12 = Utf8ToWide(v30, v31);
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
    SBServicingLogMessage(
      (wchar_t *)L"Failed to parse Metadata JSON file %s: %x",
      v13,
      (unsigned int)ConfidenceFileMetadataInfo);
    std::wstring::_Tidy_deallocate(v30);
LABEL_13:
    FileW = 0;
  }
  CloseHandle(hf);
  pfdin->hf = 0;
  if ( v9 )
  {
    v14 = Utf8ToWide(v30, &v27);
    v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
    DeleteFileW(v15);
    std::wstring::_Tidy_deallocate(v30);
    std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>>,0>(
      v16,
      &v26,
      v8);
  }
  std::string::_Tidy_deallocate(&v27);
  std::string::_Tidy_deallocate(v31);
  return FileW;
}

```

## disassembly

```asm
0x180031170  mov     [rsp-8+arg_0], rbx
0x180031175  mov     [rsp-8+arg_10], rsi
0x18003117a  push    rbp
0x18003117b  push    rdi
0x18003117c  push    r12
0x18003117e  push    r14
0x180031180  push    r15
0x180031182  lea     rbp, [rsp-420h]
0x18003118a  sub     rsp, 520h
0x180031191  mov     rax, cs:__security_cookie
0x180031198  xor     rax, rsp
0x18003119b  mov     [rbp+440h+var_30], rax
0x1800311a2  mov     r14, rdx
0x1800311a5  mov     dword ptr [rsp+540h+var_500], 0
0x1800311ad  mov     esi, 2
0x1800311b2  sub     ecx, esi
0x1800311b4  jz      loc_18003132F
0x1800311ba  cmp     ecx, 1
0x1800311bd  jnz     loc_1800313C3
0x1800311c3  mov     r12, [rdx+28h]
0x1800311c7  mov     rdx, [rdx+8]
0x1800311cb  lea     rcx, [rbp+440h+var_498]
0x1800311cf  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800311d4  nop
0x1800311d5  lea     r8, [rbp+440h+var_498]
0x1800311d9  lea     rdx, [rsp+540h+var_500]
0x1800311de  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::find(std::string const &)
0x1800311e3  lea     edi, [rsi-1]
0x1800311e6  mov     rbx, [rsp+540h+var_500]
0x1800311eb  cmp     rbx, cs:?g_OrgToTmpFileMap@@3V?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@A; std::map<std::string,std::string> g_OrgToTmpFileMap
0x1800311f2  jz      short loc_180031208
0x1800311f4  mov     r15b, dil
0x1800311f7  lea     rdx, [rbx+40h]
0x1800311fb  lea     rcx, [rbp+440h+var_4B8]
0x1800311ff  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180031204  mov     esi, edi
0x180031206  jmp     short loc_18003122B
0x180031208  xor     r15b, r15b
0x18003120b  xorps   xmm0, xmm0
0x18003120e  movups  [rsp+540h+var_4D8], xmm0
0x180031213  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18003121b  movdqu  [rsp+540h+var_4C8], xmm1
0x180031221  mov     byte ptr [rsp+540h+var_4D8], r15b
0x180031226  lea     rax, [rsp+540h+var_4D8]
0x18003122b  xorps   xmm0, xmm0
0x18003122e  movups  [rsp+540h+var_4F8], xmm0
0x180031233  xorps   xmm1, xmm1
0x180031236  movdqu  [rsp+540h+var_4E8], xmm1
0x18003123c  movups  xmm0, xmmword ptr [rax]
0x18003123f  movups  [rsp+540h+var_4F8], xmm0
0x180031244  movups  xmm1, xmmword ptr [rax+10h]
0x180031248  movups  [rsp+540h+var_4E8], xmm1
0x18003124d  mov     qword ptr [rax+10h], 0
0x180031255  mov     qword ptr [rax+18h], 0Fh
0x18003125d  mov     byte ptr [rax], 0
0x180031260  test    sil, 2
0x180031264  jz      short loc_180031273
0x180031266  and     esi, 0FFFFFFFDh
0x180031269  lea     rcx, [rsp+540h+var_4D8]
0x18003126e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180031273  test    dil, sil
0x180031276  jz      short loc_180031281
0x180031278  lea     rcx, [rbp+440h+var_4B8]
0x18003127c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180031281  test    r15b, r15b
0x180031284  jz      short loc_1800312C8
0x180031286  lea     rcx, [rsp+540h+var_4F8]
0x18003128b  call    ?GetConfidenceFileMetadataInfo@@YAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; GetConfidenceFileMetadataInfo(std::string const &)
0x180031290  mov     esi, eax
0x180031292  test    eax, eax
0x180031294  jns     short loc_1800312CA
0x180031296  lea     rdx, [rbp+440h+var_498]
0x18003129a  lea     rcx, [rbp+440h+var_4B8]
0x18003129e  call    ?Utf8ToWide@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; Utf8ToWide(std::string const &)
0x1800312a3  nop
0x1800312a4  mov     rcx, rax
0x1800312a7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800312ac  mov     r8d, esi
0x1800312af  mov     rdx, rax
0x1800312b2  lea     rcx, aFailedToParseM; "Failed to parse Metadata JSON file %s: "...
0x1800312b9  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800312be  nop
0x1800312bf  lea     rcx, [rbp+440h+var_4B8]
0x1800312c3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800312c8  xor     edi, edi
0x1800312ca  mov     rcx, r12; hObject
0x1800312cd  call    cs:__imp_CloseHandle
0x1800312d3  mov     qword ptr [r14+28h], 0
0x1800312db  test    r15b, r15b
0x1800312de  jz      short loc_180031316
0x1800312e0  lea     rdx, [rsp+540h+var_4F8]
0x1800312e5  lea     rcx, [rbp+440h+var_4B8]
0x1800312e9  call    ?Utf8ToWide@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; Utf8ToWide(std::string const &)
0x1800312ee  mov     rcx, rax
0x1800312f1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800312f6  mov     rcx, rax; lpFileName
0x1800312f9  call    cs:__imp_DeleteFileW
0x1800312ff  lea     rcx, [rbp+440h+var_4B8]
0x180031303  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031308  mov     r8, rbx
0x18003130b  lea     rdx, [rsp+540h+var_500]
0x180031310  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>>)
0x180031315  nop
0x180031316  lea     rcx, [rsp+540h+var_4F8]
0x18003131b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180031320  nop
0x180031321  lea     rcx, [rbp+440h+var_498]
0x180031325  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003132a  jmp     loc_180031504
0x18003132f  lea     rdx, aBucketconfiden; "BucketConfidenceMetadata.json"
0x180031336  mov     rcx, [r14+8]; pszFirst
0x18003133a  call    cs:__imp_StrStrIA
0x180031340  test    rax, rax
0x180031343  jz      short loc_1800313C3
0x180031345  mov     rdx, [r14+8]
0x180031349  lea     rcx, [rbp+440h+var_498]
0x18003134d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180031352  lea     rdx, [rbp+440h+var_498]
0x180031356  lea     rcx, [rsp+540h+var_4F8]
0x18003135b  call    ?Utf8ToWide@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; Utf8ToWide(std::string const &)
0x180031360  nop
0x180031361  lea     rcx, [rbp+440h+var_498]
0x180031365  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003136a  mov     ebx, 208h
0x18003136f  mov     r8d, ebx; Size
0x180031372  xor     edx, edx; Val
0x180031374  lea     rcx, [rbp+440h+PathName]; void *
0x18003137b  call    memset_0
0x180031380  mov     r8d, ebx; Size
0x180031383  xor     edx, edx; Val
0x180031385  lea     rcx, [rbp+440h+TempFileName]; void *
0x180031389  call    memset_0
0x18003138e  lea     rdx, [rbp+440h+PathName]
0x180031395  mov     ecx, 104h
0x18003139a  call    cs:__imp_GetTempPath2W
0x1800313a0  test    eax, eax
0x1800313a2  jnz     short loc_1800313F0
0x1800313a4  call    cs:__imp_GetLastError
0x1800313aa  lea     rcx, aGettemppath2wF; "GetTempPath2W failed with error: %x"
0x1800313b1  mov     edx, eax
0x1800313b3  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800313b8  nop
0x1800313b9  lea     rcx, [rsp+540h+var_4F8]
0x1800313be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800313c3  xor     eax, eax
0x1800313c5  mov     rcx, [rbp+440h+var_30]
0x1800313cc  xor     rcx, rsp; StackCookie
0x1800313cf  call    __security_check_cookie
0x1800313d4  lea     r11, [rsp+540h+var_20]
0x1800313dc  mov     rbx, [r11+30h]
0x1800313e0  mov     rsi, [r11+40h]
0x1800313e4  mov     rsp, r11
0x1800313e7  pop     r15
0x1800313e9  pop     r14
0x1800313eb  pop     r12
0x1800313ed  pop     rdi
0x1800313ee  pop     rbp
0x1800313ef  retn
0x1800313f0  lea     r9, [rbp+440h+TempFileName]; lpTempFileName
0x1800313f4  xor     r8d, r8d; uUnique
0x1800313f7  lea     rdx, aCabMetadata; "cab_metadata"
0x1800313fe  lea     rcx, [rbp+440h+PathName]; lpPathName
0x180031405  call    cs:__imp_GetTempFileNameW
0x18003140b  test    eax, eax
0x18003140d  jnz     short loc_18003141E
0x18003140f  call    cs:__imp_GetLastError
0x180031415  lea     rcx, aGettempfilenam; "GetTempFileNameW failed with error: %x"
0x18003141c  jmp     short loc_1800313B1
0x18003141e  mov     [rsp+540h+hTemplateFile], 0; hTemplateFile
0x180031427  mov     [rsp+540h+dwFlagsAndAttributes], 100h; dwFlagsAndAttributes
0x18003142f  mov     [rsp+540h+dwCreationDisposition], esi; dwCreationDisposition
0x180031433  xor     r9d, r9d; lpSecurityAttributes
0x180031436  mov     edx, 0C0000000h; dwDesiredAccess
0x18003143b  lea     r8d, [r9+1]; dwShareMode
0x18003143f  lea     rcx, [rbp+440h+TempFileName]; lpFileName
0x180031443  call    cs:__imp_CreateFileW
0x180031449  mov     rdi, rax
0x18003144c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031450  jnz     short loc_18003147C
0x180031452  call    cs:__imp_GetLastError
0x180031458  mov     r9d, eax
0x18003145b  lea     rcx, [rsp+540h+var_4F8]
0x180031460  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180031465  mov     r8, rax
0x180031468  lea     rdx, [rbp+440h+TempFileName]
0x18003146c  lea     rcx, aFailedToCreate_0; "Failed to create temp file %s for %s wi"...
0x180031473  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180031478  xor     edi, edi
0x18003147a  jmp     short loc_1800314FA
0x18003147c  lea     rdx, [rbp+440h+TempFileName]
0x180031480  lea     rcx, [rsp+540h+var_4D8]
0x180031485  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003148a  nop
0x18003148b  lea     rdx, [rsp+540h+var_4D8]
0x180031490  lea     rcx, [rbp+440h+var_478]
0x180031494  call    ?WideToUtf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; WideToUtf8(std::wstring const &)
0x180031499  mov     rbx, rax
0x18003149c  mov     rdx, [r14+8]
0x1800314a0  lea     rcx, [rbp+440h+var_4B8]
0x1800314a4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800314a9  nop
0x1800314aa  mov     rdx, rax
0x1800314ad  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@$$QEAV21@@Z; std::map<std::string,std::string>::operator[](std::string &&)
0x1800314b2  mov     rcx, rax
0x1800314b5  mov     rdx, rbx
0x1800314b8  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800314bd  nop
0x1800314be  lea     rcx, [rbp+440h+var_4B8]
0x1800314c2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800314c7  nop
0x1800314c8  lea     rcx, [rbp+440h+var_478]
0x1800314cc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800314d1  nop
0x1800314d2  lea     rcx, [rsp+540h+var_4D8]
0x1800314d7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800314dc  lea     rcx, [rsp+540h+var_4F8]
0x1800314e1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800314e6  mov     r8, rax
0x1800314e9  lea     rdx, [rbp+440h+TempFileName]
0x1800314ed  lea     rcx, aCreatedTempFil; "Created temp file %s for %s"
0x1800314f4  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800314f9  nop
0x1800314fa  lea     rcx, [rsp+540h+var_4F8]
0x1800314ff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031504  mov     rax, rdi
0x180031507  jmp     loc_1800313C5
```
