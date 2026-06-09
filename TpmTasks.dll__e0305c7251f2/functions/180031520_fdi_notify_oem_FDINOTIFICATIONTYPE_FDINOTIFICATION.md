# fdi_notify_oem(FDINOTIFICATIONTYPE,FDINOTIFICATION *)

- ea: `0x180031520`
- end: `0x180031906`
- name: `?fdi_notify_oem@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z`
- size: `998`
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
- `0x180031520`
- `0x180031c30`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180031800`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180031800`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003169e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003169e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003183d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003183d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003179f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003180a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003184c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003179f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003180a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003184c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031672`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031672`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180031795`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180031795`
- `SHLWAPI!StrStrIA` at `0x1800316f5`
- `SHLWAPI!StrStrIA` at `0x1800316f5`

## string_xrefs

- `0x1800317a5`: `GetTempPath2W failed with error: %x`
- `0x180031810`: `GetTempFileNameW failed with error: %x`
- `0x180031866`: `Failed to create temp file %s for %s with error: %x`
- `0x1800318e7`: `Created temp file %s for %s`

## pseudocode

```c
INT_PTR __fastcall fdi_notify_oem(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)
{
  char v3; // si
  int v4; // ecx
  void *hf; // r12
  __int64 v6; // rcx
  __int64 FileW; // rdi
  __int64 v8; // rbx
  char v9; // r15
  _OWORD *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  const WCHAR *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  bool v16; // bl
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
    v15 = WideToUtf8(v31, qword_1800A3818);
    if ( *(_QWORD *)(v15 + 24) > 0xFu )
      v15 = *(_QWORD *)v15;
    v16 = StrStrIA(pfdin->psz1, (PCSTR)v15) && !qword_1800A3848;
    std::string::_Tidy_deallocate(v31);
    if ( v16 )
    {
      std::string::string(v32, pfdin->psz1);
      Utf8ToWide(&v28, v32);
      std::string::_Tidy_deallocate(v32);
      v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v28);
      SBServicingLogMessage((wchar_t *)L"Targeted OEM file found: %s", v17);
      memset_0(PathName, 0, 0x208u);
      memset_0(TempFileName, 0, 0x208u);
      if ( (unsigned int)GetTempPath2W(260, PathName) )
      {
        if ( GetTempFileNameW(PathName, L"cab_oem", 0, TempFileName) )
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
            v23 = std::string::string(v31, pfdin->psz1);
            v25 = std::map<std::string,std::string>::operator[](v24, v23);
            std::string::operator=(v25, v22);
            std::string::_Tidy_deallocate(v31);
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
      std::wstring::_Tidy_deallocate(&v28);
    }
    return 0;
  }
  if ( v4 != 1 )
    return 0;
  hf = (void *)pfdin->hf;
  std::string::string(v32, pfdin->psz1);
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::find(
    v6,
    &v27,
    v32);
  FileW = 1;
  v8 = v27;
  if ( v27 == g_OrgToTmpFileMap )
  {
    v9 = 0;
    v30[0] = 0;
    v30[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v30[0]) = 0;
    v10 = v30;
    v3 = 4;
  }
  else
  {
    v9 = 1;
    v10 = (_OWORD *)std::string::string(v31, v27 + 64);
  }
  v28 = 0;
  v29 = 0;
  v28 = *v10;
  v29 = v10[1];
  *((_QWORD *)v10 + 2) = 0;
  *((_QWORD *)v10 + 3) = 15;
  *(_BYTE *)v10 = 0;
  if ( (v3 & 4) != 0 )
  {
    v3 &= ~4u;
    std::string::_Tidy_deallocate(v30);
  }
  if ( (v3 & 2) != 0 )
    std::string::_Tidy_deallocate(v31);
  if ( !v9 )
    goto LABEL_13;
  if ( (int)TryParseFromConfidenceFilesForOEMFromFDI(&v28, qword_1800A37F8) < 0 )
  {
    v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_1800A37F8);
    SBServicingLogMessage((wchar_t *)L"Failed in TryParseFromConfidenceFilesForOEM for OEM %s: %x", v11);
LABEL_13:
    FileW = 0;
  }
  CloseHandle(hf);
  pfdin->hf = 0;
  if ( v9 )
  {
    v12 = Utf8ToWide(v31, &v28);
    v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
    DeleteFileW(v13);
    std::wstring::_Tidy_deallocate(v31);
    std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>>,0>(
      v14,
      &v27,
      v8);
  }
  std::string::_Tidy_deallocate(&v28);
  std::string::_Tidy_deallocate(v32);
  return FileW;
}

```

## disassembly

```asm
0x180031520  mov     [rsp-8+arg_0], rbx
0x180031525  mov     [rsp-8+arg_10], rsi
0x18003152a  push    rbp
0x18003152b  push    rdi
0x18003152c  push    r12
0x18003152e  push    r14
0x180031530  push    r15
0x180031532  lea     rbp, [rsp-420h]
0x18003153a  sub     rsp, 520h
0x180031541  mov     rax, cs:__security_cookie
0x180031548  xor     rax, rsp
0x18003154b  mov     [rbp+440h+var_30], rax
0x180031552  mov     r14, rdx
0x180031555  mov     dword ptr [rsp+540h+var_500], 0
0x18003155d  mov     esi, 2
0x180031562  sub     ecx, esi
0x180031564  jz      loc_1800316D4
0x18003156a  cmp     ecx, 1
0x18003156d  jnz     loc_1800317BE
0x180031573  mov     r12, [rdx+28h]
0x180031577  mov     rdx, [rdx+8]
0x18003157b  lea     rcx, [rbp+440h+var_498]
0x18003157f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180031584  nop
0x180031585  lea     r8, [rbp+440h+var_498]
0x180031589  lea     rdx, [rsp+540h+var_500]
0x18003158e  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::find(std::string const &)
0x180031593  lea     edi, [rsi-1]
0x180031596  mov     rbx, [rsp+540h+var_500]
0x18003159b  cmp     rbx, cs:?g_OrgToTmpFileMap@@3V?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@A; std::map<std::string,std::string> g_OrgToTmpFileMap
0x1800315a2  jz      short loc_1800315B6
0x1800315a4  mov     r15b, dil
0x1800315a7  lea     rdx, [rbx+40h]
0x1800315ab  lea     rcx, [rbp+440h+var_4B8]
0x1800315af  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1800315b4  jmp     short loc_1800315DE
0x1800315b6  xor     r15b, r15b
0x1800315b9  xorps   xmm0, xmm0
0x1800315bc  movups  [rsp+540h+var_4D8], xmm0
0x1800315c1  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800315c9  movdqu  [rsp+540h+var_4C8], xmm1
0x1800315cf  mov     byte ptr [rsp+540h+var_4D8], r15b
0x1800315d4  lea     rax, [rsp+540h+var_4D8]
0x1800315d9  mov     esi, 4
0x1800315de  xorps   xmm0, xmm0
0x1800315e1  movups  [rsp+540h+var_4F8], xmm0
0x1800315e6  xorps   xmm1, xmm1
0x1800315e9  movdqu  [rsp+540h+var_4E8], xmm1
0x1800315ef  movups  xmm0, xmmword ptr [rax]
0x1800315f2  movups  [rsp+540h+var_4F8], xmm0
0x1800315f7  movups  xmm1, xmmword ptr [rax+10h]
0x1800315fb  movups  [rsp+540h+var_4E8], xmm1
0x180031600  mov     qword ptr [rax+10h], 0
0x180031608  mov     qword ptr [rax+18h], 0Fh
0x180031610  mov     byte ptr [rax], 0
0x180031613  test    sil, 4
0x180031617  jz      short loc_180031626
0x180031619  and     esi, 0FFFFFFFBh
0x18003161c  lea     rcx, [rsp+540h+var_4D8]
0x180031621  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180031626  test    sil, 2
0x18003162a  jz      short loc_180031635
0x18003162c  lea     rcx, [rbp+440h+var_4B8]
0x180031630  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180031635  test    r15b, r15b
0x180031638  jz      short loc_18003166D
0x18003163a  lea     rdx, qword_1800A37F8
0x180031641  lea     rcx, [rsp+540h+var_4F8]
0x180031646  call    ?TryParseFromConfidenceFilesForOEMFromFDI@@YAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; TryParseFromConfidenceFilesForOEMFromFDI(std::string const &,std::wstring const &)
0x18003164b  mov     r8d, eax
0x18003164e  test    eax, eax
0x180031650  jns     short loc_18003166F
0x180031652  lea     rcx, qword_1800A37F8
0x180031659  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003165e  mov     rdx, rax
0x180031661  lea     rcx, aFailedInTrypar; "Failed in TryParseFromConfidenceFilesFo"...
0x180031668  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003166d  xor     edi, edi
0x18003166f  mov     rcx, r12; hObject
0x180031672  call    cs:__imp_CloseHandle
0x180031678  mov     qword ptr [r14+28h], 0
0x180031680  test    r15b, r15b
0x180031683  jz      short loc_1800316BB
0x180031685  lea     rdx, [rsp+540h+var_4F8]
0x18003168a  lea     rcx, [rbp+440h+var_4B8]
0x18003168e  call    ?Utf8ToWide@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; Utf8ToWide(std::string const &)
0x180031693  mov     rcx, rax
0x180031696  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003169b  mov     rcx, rax; lpFileName
0x18003169e  call    cs:__imp_DeleteFileW
0x1800316a4  lea     rcx, [rbp+440h+var_4B8]
0x1800316a8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800316ad  mov     r8, rbx
0x1800316b0  lea     rdx, [rsp+540h+var_500]
0x1800316b5  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>>)
0x1800316ba  nop
0x1800316bb  lea     rcx, [rsp+540h+var_4F8]
0x1800316c0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800316c5  nop
0x1800316c6  lea     rcx, [rbp+440h+var_498]
0x1800316ca  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800316cf  jmp     loc_1800318FE
0x1800316d4  lea     rdx, qword_1800A3818
0x1800316db  lea     rcx, [rbp+440h+var_4B8]
0x1800316df  call    ?WideToUtf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; WideToUtf8(std::wstring const &)
0x1800316e4  cmp     qword ptr [rax+18h], 0Fh
0x1800316e9  jbe     short loc_1800316EE
0x1800316eb  mov     rax, [rax]
0x1800316ee  mov     rdx, rax; pszSrch
0x1800316f1  mov     rcx, [r14+8]; pszFirst
0x1800316f5  call    cs:__imp_StrStrIA
0x1800316fb  mov     edi, 1
0x180031700  test    rax, rax
0x180031703  jz      short loc_180031714
0x180031705  cmp     cs:qword_1800A3848, 0
0x18003170d  jnz     short loc_180031714
0x18003170f  mov     bl, dil
0x180031712  jmp     short loc_180031716
0x180031714  xor     bl, bl
0x180031716  lea     rcx, [rbp+440h+var_4B8]
0x18003171a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003171f  test    bl, bl
0x180031721  jz      loc_1800317BE
0x180031727  mov     rdx, [r14+8]
0x18003172b  lea     rcx, [rbp+440h+var_498]
0x18003172f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180031734  lea     rdx, [rbp+440h+var_498]
0x180031738  lea     rcx, [rsp+540h+var_4F8]
0x18003173d  call    ?Utf8ToWide@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; Utf8ToWide(std::string const &)
0x180031742  nop
0x180031743  lea     rcx, [rbp+440h+var_498]
0x180031747  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003174c  lea     rcx, [rsp+540h+var_4F8]
0x180031751  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180031756  mov     rdx, rax
0x180031759  lea     rcx, aTargetedOemFil; "Targeted OEM file found: %s"
0x180031760  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180031765  mov     ebx, 208h
0x18003176a  mov     r8d, ebx; Size
0x18003176d  xor     edx, edx; Val
0x18003176f  lea     rcx, [rbp+440h+PathName]; void *
0x180031776  call    memset_0
0x18003177b  mov     r8d, ebx; Size
0x18003177e  xor     edx, edx; Val
0x180031780  lea     rcx, [rbp+440h+TempFileName]; void *
0x180031784  call    memset_0
0x180031789  lea     rdx, [rbp+440h+PathName]
0x180031790  mov     ecx, 104h
0x180031795  call    cs:__imp_GetTempPath2W
0x18003179b  test    eax, eax
0x18003179d  jnz     short loc_1800317EB
0x18003179f  call    cs:__imp_GetLastError
0x1800317a5  lea     rcx, aGettemppath2wF; "GetTempPath2W failed with error: %x"
0x1800317ac  mov     edx, eax
0x1800317ae  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800317b3  nop
0x1800317b4  lea     rcx, [rsp+540h+var_4F8]
0x1800317b9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800317be  xor     eax, eax
0x1800317c0  mov     rcx, [rbp+440h+var_30]
0x1800317c7  xor     rcx, rsp; StackCookie
0x1800317ca  call    __security_check_cookie
0x1800317cf  lea     r11, [rsp+540h+var_20]
0x1800317d7  mov     rbx, [r11+30h]
0x1800317db  mov     rsi, [r11+40h]
0x1800317df  mov     rsp, r11
0x1800317e2  pop     r15
0x1800317e4  pop     r14
0x1800317e6  pop     r12
0x1800317e8  pop     rdi
0x1800317e9  pop     rbp
0x1800317ea  retn
0x1800317eb  lea     r9, [rbp+440h+TempFileName]; lpTempFileName
0x1800317ef  xor     r8d, r8d; uUnique
0x1800317f2  lea     rdx, aCabOem; "cab_oem"
0x1800317f9  lea     rcx, [rbp+440h+PathName]; lpPathName
0x180031800  call    cs:__imp_GetTempFileNameW
0x180031806  test    eax, eax
0x180031808  jnz     short loc_180031819
0x18003180a  call    cs:__imp_GetLastError
0x180031810  lea     rcx, aGettempfilenam; "GetTempFileNameW failed with error: %x"
0x180031817  jmp     short loc_1800317AC
0x180031819  mov     [rsp+540h+hTemplateFile], 0; hTemplateFile
0x180031822  mov     [rsp+540h+dwFlagsAndAttributes], 100h; dwFlagsAndAttributes
0x18003182a  mov     [rsp+540h+dwCreationDisposition], esi; dwCreationDisposition
0x18003182e  xor     r9d, r9d; lpSecurityAttributes
0x180031831  mov     r8d, edi; dwShareMode
0x180031834  mov     edx, 0C0000000h; dwDesiredAccess
0x180031839  lea     rcx, [rbp+440h+TempFileName]; lpFileName
0x18003183d  call    cs:__imp_CreateFileW
0x180031843  mov     rdi, rax
0x180031846  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003184a  jnz     short loc_180031876
0x18003184c  call    cs:__imp_GetLastError
0x180031852  mov     r9d, eax
0x180031855  lea     rcx, [rsp+540h+var_4F8]
0x18003185a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003185f  mov     r8, rax
0x180031862  lea     rdx, [rbp+440h+TempFileName]
0x180031866  lea     rcx, aFailedToCreate_0; "Failed to create temp file %s for %s wi"...
0x18003186d  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180031872  xor     edi, edi
0x180031874  jmp     short loc_1800318F4
0x180031876  lea     rdx, [rbp+440h+TempFileName]
0x18003187a  lea     rcx, [rsp+540h+var_4D8]
0x18003187f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180031884  nop
0x180031885  lea     rdx, [rsp+540h+var_4D8]
0x18003188a  lea     rcx, [rbp+440h+var_478]
0x18003188e  call    ?WideToUtf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; WideToUtf8(std::wstring const &)
0x180031893  mov     rbx, rax
0x180031896  mov     rdx, [r14+8]
0x18003189a  lea     rcx, [rbp+440h+var_4B8]
0x18003189e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800318a3  nop
0x1800318a4  mov     rdx, rax
0x1800318a7  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@$$QEAV21@@Z; std::map<std::string,std::string>::operator[](std::string &&)
0x1800318ac  mov     rcx, rax
0x1800318af  mov     rdx, rbx
0x1800318b2  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800318b7  nop
0x1800318b8  lea     rcx, [rbp+440h+var_4B8]
0x1800318bc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800318c1  nop
0x1800318c2  lea     rcx, [rbp+440h+var_478]
0x1800318c6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800318cb  nop
0x1800318cc  lea     rcx, [rsp+540h+var_4D8]
0x1800318d1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800318d6  lea     rcx, [rsp+540h+var_4F8]
0x1800318db  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800318e0  mov     r8, rax
0x1800318e3  lea     rdx, [rbp+440h+TempFileName]
0x1800318e7  lea     rcx, aCreatedTempFil; "Created temp file %s for %s"
0x1800318ee  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800318f3  nop
0x1800318f4  lea     rcx, [rsp+540h+var_4F8]
0x1800318f9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800318fe  mov     rax, rdi
0x180031901  jmp     loc_1800317C0
```
