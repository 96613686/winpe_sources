# Uev::TemplateAdministrator::RebuildTemplateIndex(void)

- ea: `0x14003e0c0`
- end: `0x14003e423`
- name: `?RebuildTemplateIndex@TemplateAdministrator@Uev@@UEBAXXZ`
- size: `867`
- prototype: `void __fastcall(Uev::TemplateAdministrator *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: ``

## callees

- `0x140003e50`
- `0x140004a78`
- `0x140004ab4`
- `0x14000adb4`
- `0x14000ba60`
- `0x14000bacc`
- `0x14000c1cc`
- `0x14000d1d8`
- `0x140019748`
- `0x1400231f8`
- `0x140034c14`
- `0x140034db4`
- `0x14003a044`
- `0x14003a3cc`
- `0x14003c7e8`
- `0x14003e0c0`
- `0x14003f370`
- `0x140045724`
- `0x140045ea8`
- `0x140065c20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003e323`
- `KERNEL32!GetLastError` at `0x14003e33f`
- `KERNEL32!GetLastError` at `0x14003e323`
- `KERNEL32!GetLastError` at `0x14003e33f`
- `KERNEL32!FindNextFileW` at `0x14003e315`
- `KERNEL32!FindNextFileW` at `0x14003e315`
- `KERNEL32!FindFirstFileW` at `0x14003e177`
- `KERNEL32!FindFirstFileW` at `0x14003e177`

## string_xrefs

- `0x14003e3b5`: `Could not open template folder for search`
- `0x14003e3e6`: `Could not retrieve all files from template folder`

## pseudocode

```c
void __fastcall Uev::TemplateAdministrator::RebuildTemplateIndex(Uev::TemplateAdministrator *this)
{
  __int64 v1; // rdx
  __int64 v2; // r8
  void **TemplateFolder; // r9
  void *v4; // rcx
  const WCHAR *v5; // rcx
  char *FirstFileW; // rdi
  __m128i si128; // xmm6
  __int64 v8; // rdx
  __int64 v9; // r8
  void **v10; // r9
  void *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rax
  __int128 *v14; // rax
  __int64 i; // rbx
  DWORD v16; // ebx
  DWORD LastError; // eax
  char *v18; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v19; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v20; // [rsp+60h] [rbp-A8h]
  _BYTE Src[40]; // [rsp+70h] [rbp-98h] BYREF
  void **v22; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v23[33]; // [rsp+A0h] [rbp-68h] BYREF
  __int16 v24; // [rsp+C1h] [rbp-47h]
  _OWORD v25[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v26; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-10h]
  LPCWSTR lpFileName[5]; // [rsp+100h] [rbp-8h] BYREF
  _OWORD pExceptionObject[4]; // [rsp+128h] [rbp+20h] BYREF
  _QWORD v30[2]; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v31[16]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v32[48]; // [rsp+188h] [rbp+80h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+1B8h] [rbp+B0h] BYREF

  Uev::TemplateIndex::TemplateIndex((Uev::TemplateIndex *)v30);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  TemplateFolder = Uev::TemplateFolder::GetTemplateFolder();
  v4 = TemplateFolder[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - (_QWORD)v4) < 3 )
    std::_Xlen_string();
  if ( (unsigned __int64)TemplateFolder[3] > 7 )
    TemplateFolder = (void **)*TemplateFolder;
  std::wstring::wstring(lpFileName, v1, v2, TemplateFolder, v4, L"\\*.", 3);
  v5 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v5 = lpFileName[0];
  FirstFileW = (char *)FindFirstFileW(v5, &FindFileData);
  v18 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    if ( LastError != 3 && LastError != 18 )
    {
      std::wstring::wstring(Src, L"Could not open template folder for search");
      Uev::FileIOException::FileIOException(pExceptionObject, Src);
      throw (Uev::FileIOException *)pExceptionObject;
    }
    Uev::TemplateIndex::SaveIndex((Uev::TemplateIndex *)v30);
  }
  else
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        pExceptionObject[0] = 0;
        pExceptionObject[1] = si128;
        LOWORD(pExceptionObject[0]) = 0;
        v26 = 0;
        v27 = 0;
        v10 = Uev::TemplateFolder::GetTemplateFolder();
        v11 = v10[2];
        if ( v11 == (void *)0x7FFFFFFFFFFFFFFELL )
          std::_Xlen_string();
        if ( (unsigned __int64)v10[3] > 7 )
          v10 = (void **)*v10;
        std::wstring::wstring(Src, v8, v9, v10, v11, L"\\", 1);
        v12 = -1;
        do
          ++v12;
        while ( FindFileData.cFileName[v12] );
        v13 = std::wstring::_Append<wchar_t>(Src);
        v19 = *(_OWORD *)v13;
        v20 = *(_OWORD *)(v13 + 16);
        *(_QWORD *)(v13 + 16) = 0;
        *(_QWORD *)(v13 + 24) = 7;
        *(_WORD *)v13 = 0;
        v22 = &Uev::TemplateParser::`vftable';
        std::wstring::wstring(v23, &v19);
        v24 = 0;
        v25[0] = 0;
        v25[1] = si128;
        LOWORD(v25[0]) = 0;
        v14 = &v19;
        if ( *((_QWORD *)&v20 + 1) > 7u )
          v14 = (__int128 *)v19;
        v23[32] = *(_WORD *)v14 != 60;
        Uev::TemplateParser::ParsePrimaryIdAndProcessFileCriteria(
          (__int64)&v22,
          (__int64)pExceptionObject,
          (__int64)&v26);
        v22 = &Uev::TemplateParser::`vftable';
        std::wstring::_Tidy_deallocate(v25);
        std::wstring::_Tidy_deallocate(v23);
        std::wstring::_Tidy_deallocate(&v19);
        std::wstring::_Tidy_deallocate(Src);
        for ( i = v26; i != *((_QWORD *)&v26 + 1); i += 168 )
          Uev::TemplateIndex::AddTemplateID((__int64)v30, i, (__int64)pExceptionObject);
        std::vector<Uev::ProcessFileCriteria>::_Tidy(&v26);
        std::wstring::_Tidy_deallocate(pExceptionObject);
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    v16 = GetLastError();
    Uev::TemplateIndex::SaveIndex((Uev::TemplateIndex *)v30);
    if ( v16 != 18 )
    {
      std::wstring::wstring(Src, L"Could not retrieve all files from template folder");
      Uev::FileIOException::FileIOException(pExceptionObject, Src);
      throw (Uev::FileIOException *)pExceptionObject;
    }
  }
  Uev::SmartHandle<void *,&void Uev::FindCloseWrapper(void *),-1>::~SmartHandle<void *,&void Uev::FindCloseWrapper(void *),-1>(&v18);
  std::wstring::_Tidy_deallocate(lpFileName);
  v30[0] = &Uev::TemplateIndex::`vftable';
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(v32);
  std::list<std::pair<std::wstring const,std::wstring>>::~list<std::pair<std::wstring const,std::wstring>>(v31);
}

```

## disassembly

```asm
0x14003e0c0  mov     rax, rsp
0x14003e0c3  push    rbp
0x14003e0c4  push    rbx
0x14003e0c5  push    rsi
0x14003e0c6  push    rdi
0x14003e0c7  push    r12
0x14003e0c9  push    r15
0x14003e0cb  lea     rbp, [rax-358h]
0x14003e0d2  sub     rsp, 428h
0x14003e0d9  movaps  xmmword ptr [rax-48h], xmm6
0x14003e0dd  mov     rax, cs:__security_cookie
0x14003e0e4  xor     rax, rsp
0x14003e0e7  mov     [rbp+350h+var_50], rax
0x14003e0ee  xor     esi, esi
0x14003e0f0  lea     rcx, [rbp+350h+var_2F0]; this
0x14003e0f4  call    ??0TemplateIndex@Uev@@QEAA@XZ; Uev::TemplateIndex::TemplateIndex(void)
0x14003e0f9  nop
0x14003e0fa  xor     edx, edx; Val
0x14003e0fc  mov     r8d, 250h; Size
0x14003e102  lea     rcx, [rbp+350h+FindFileData]; void *
0x14003e109  call    memset_0
0x14003e10e  call    ?GetTemplateFolder@TemplateFolder@Uev@@QEAAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Uev::TemplateFolder::GetTemplateFolder(void)
0x14003e113  mov     r9, rax
0x14003e116  mov     rcx, [rax+10h]
0x14003e11a  mov     r15, 7FFFFFFFFFFFFFFEh
0x14003e124  mov     rax, r15
0x14003e127  sub     rax, rcx
0x14003e12a  cmp     rax, 3
0x14003e12e  jb      loc_14003E417
0x14003e134  cmp     qword ptr [r9+18h], 7
0x14003e139  jbe     short loc_14003E13E
0x14003e13b  mov     r9, [r9]
0x14003e13e  mov     qword ptr [rsp+30h], 3
0x14003e147  lea     rax, asc_1400A8EE8; "\\*."
0x14003e14e  mov     [rsp+450h+var_428], rax
0x14003e153  mov     [rsp+450h+var_430], rcx
0x14003e158  lea     rcx, [rbp+350h+lpFileName]
0x14003e15c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14003e161  nop
0x14003e162  lea     rcx, [rbp+350h+lpFileName]
0x14003e166  cmp     [rbp+350h+var_340], 7
0x14003e16b  cmova   rcx, [rbp+350h+lpFileName]; lpFileName
0x14003e170  lea     rdx, [rbp+350h+FindFileData]; lpFindFileData
0x14003e177  call    cs:__imp_FindFirstFileW
0x14003e17d  mov     rdi, rax
0x14003e180  mov     qword ptr [rsp+450h+var_410], rax
0x14003e185  dec     rax
0x14003e188  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003e18c  ja      loc_14003E33F
0x14003e192  lea     r12, ??_7TemplateParser@Uev@@6B@; const Uev::TemplateParser::`vftable'
0x14003e199  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14003e1a1  test    byte ptr [rbp+350h+FindFileData.dwFileAttributes], 10h
0x14003e1a8  jnz     loc_14003E30B
0x14003e1ae  xorps   xmm0, xmm0
0x14003e1b1  movups  [rbp+350h+pExceptionObject], xmm0
0x14003e1b5  movdqu  [rbp+350h+var_320], xmm6
0x14003e1ba  mov     word ptr [rbp+350h+pExceptionObject], si
0x14003e1be  movdqu  [rbp+350h+var_370], xmm0
0x14003e1c3  mov     [rbp+350h+var_360], rsi
0x14003e1c7  call    ?GetTemplateFolder@TemplateFolder@Uev@@QEAAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Uev::TemplateFolder::GetTemplateFolder(void)
0x14003e1cc  mov     r9, rax
0x14003e1cf  mov     rcx, [rax+10h]
0x14003e1d3  mov     rax, r15
0x14003e1d6  sub     rax, rcx
0x14003e1d9  cmp     rax, 1
0x14003e1dd  jb      loc_14003E41D
0x14003e1e3  cmp     qword ptr [r9+18h], 7
0x14003e1e8  jbe     short loc_14003E1ED
0x14003e1ea  mov     r9, [r9]
0x14003e1ed  mov     qword ptr [rsp+30h], 1
0x14003e1f6  lea     rax, SubBlock; "\\"
0x14003e1fd  mov     [rsp+450h+var_428], rax
0x14003e202  mov     [rsp+450h+var_430], rcx
0x14003e207  lea     rcx, [rsp+450h+Src]
0x14003e20c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14003e211  nop
0x14003e212  lea     rax, [rbp+350h+FindFileData.cFileName]
0x14003e219  or      r8, 0FFFFFFFFFFFFFFFFh
0x14003e21d  inc     r8
0x14003e220  cmp     [rax+r8*2], si
0x14003e225  jnz     short loc_14003E21D
0x14003e227  lea     rdx, [rbp+350h+FindFileData.cFileName]
0x14003e22e  lea     rcx, [rsp+450h+Src]; Src
0x14003e233  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14003e238  movups  xmm0, xmmword ptr [rax]
0x14003e23b  movups  [rsp+450h+var_410+8], xmm0
0x14003e240  movups  xmm1, xmmword ptr [rax+10h]
0x14003e244  movups  [rsp+450h+var_400+8], xmm1
0x14003e249  mov     [rax+10h], rsi
0x14003e24d  mov     qword ptr [rax+18h], 7
0x14003e255  mov     [rax], si
0x14003e258  mov     [rbp+350h+var_3C0], r12
0x14003e25c  lea     rdx, [rsp+450h+var_410+8]
0x14003e261  lea     rcx, [rbp+350h+var_3B8]
0x14003e265  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14003e26a  mov     [rbp+350h+var_397], si
0x14003e26e  xorps   xmm0, xmm0
0x14003e271  movups  [rbp+350h+var_390], xmm0
0x14003e275  movdqa  [rbp+350h+var_380], xmm6
0x14003e27a  mov     word ptr [rbp+350h+var_390], si
0x14003e27e  lea     rax, [rsp+450h+var_410+8]
0x14003e283  cmp     qword ptr [rsp+450h+var_3F0], 7
0x14003e289  cmova   rax, qword ptr [rsp+450h+var_410+8]
0x14003e28f  cmp     word ptr [rax], 3Ch ; '<'
0x14003e293  setnz   [rbp+350h+var_398]
0x14003e297  lea     r8, [rbp+350h+var_370]
0x14003e29b  lea     rdx, [rbp+350h+pExceptionObject]
0x14003e29f  lea     rcx, [rbp+350h+var_3C0]
0x14003e2a3  call    ?ParsePrimaryIdAndProcessFileCriteria@TemplateParser@Uev@@QEAAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$vector@VProcessFileCriteria@Uev@@V?$allocator@VProcessFileCriteria@Uev@@@std@@@4@@Z; Uev::TemplateParser::ParsePrimaryIdAndProcessFileCriteria(std::wstring &,std::vector<Uev::ProcessFileCriteria> &)
0x14003e2a8  nop
0x14003e2a9  mov     [rbp+350h+var_3C0], r12
0x14003e2ad  lea     rcx, [rbp+350h+var_390]
0x14003e2b1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003e2b6  lea     rcx, [rbp+350h+var_3B8]
0x14003e2ba  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003e2bf  nop
0x14003e2c0  lea     rcx, [rsp+450h+var_410+8]
0x14003e2c5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003e2ca  nop
0x14003e2cb  lea     rcx, [rsp+450h+Src]
0x14003e2d0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003e2d5  mov     rbx, qword ptr [rbp+350h+var_370]
0x14003e2d9  cmp     rbx, qword ptr [rbp+350h+var_370+8]
0x14003e2dd  jz      short loc_14003E2F8
0x14003e2df  lea     r8, [rbp+350h+pExceptionObject]
0x14003e2e3  mov     rdx, rbx
0x14003e2e6  lea     rcx, [rbp+350h+var_2F0]
0x14003e2ea  call    ?AddTemplateID@TemplateIndex@Uev@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; Uev::TemplateIndex::AddTemplateID(std::wstring const &,std::wstring const &)
0x14003e2ef  add     rbx, 0A8h
0x14003e2f6  jmp     short loc_14003E2D9
0x14003e2f8  lea     rcx, [rbp+350h+var_370]
0x14003e2fc  call    ?_Tidy@?$vector@VProcessFileCriteria@Uev@@V?$allocator@VProcessFileCriteria@Uev@@@std@@@std@@AEAAXXZ; std::vector<Uev::ProcessFileCriteria>::_Tidy(void)
0x14003e301  nop
0x14003e302  lea     rcx, [rbp+350h+pExceptionObject]
0x14003e306  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003e30b  lea     rdx, [rbp+350h+FindFileData]; lpFindFileData
0x14003e312  mov     rcx, rdi; hFindFile
0x14003e315  call    cs:__imp_FindNextFileW
0x14003e31b  test    eax, eax
0x14003e31d  jnz     loc_14003E1A1
0x14003e323  call    cs:__imp_GetLastError
0x14003e329  mov     ebx, eax
0x14003e32b  lea     rcx, [rbp+350h+var_2F0]; this
0x14003e32f  call    ?SaveIndex@TemplateIndex@Uev@@QEBAXXZ; Uev::TemplateIndex::SaveIndex(void)
0x14003e334  cmp     ebx, 12h
0x14003e337  jnz     loc_14003E3E6
0x14003e33d  jmp     short loc_14003E359
0x14003e33f  call    cs:__imp_GetLastError
0x14003e345  cmp     eax, 3
0x14003e348  jz      short loc_14003E34F
0x14003e34a  cmp     eax, 12h
0x14003e34d  jnz     short loc_14003E3B5
0x14003e34f  lea     rcx, [rbp+350h+var_2F0]; this
0x14003e353  call    ?SaveIndex@TemplateIndex@Uev@@QEBAXXZ; Uev::TemplateIndex::SaveIndex(void)
0x14003e358  nop
0x14003e359  lea     rcx, [rsp+450h+var_410]
0x14003e35e  call    ??1?$SmartHandle@PEAX$1?FindCloseWrapper@Uev@@YAXPEAX@Z$0?0@Uev@@QEAA@XZ; Uev::SmartHandle<void *,&Uev::FindCloseWrapper(void *),-1>::~SmartHandle<void *,&Uev::FindCloseWrapper(void *),-1>(void)
0x14003e363  nop
0x14003e364  lea     rcx, [rbp+350h+lpFileName]
0x14003e368  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003e36d  nop
0x14003e36e  lea     rax, ??_7TemplateIndex@Uev@@6B@; const Uev::TemplateIndex::`vftable'
0x14003e375  mov     [rbp+350h+var_2F0], rax
0x14003e379  lea     rcx, [rbp+350h+var_2D0]
0x14003e380  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(void)
0x14003e385  lea     rcx, [rbp+350h+var_2E0]
0x14003e389  call    ??1?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::wstring const,std::wstring>>::~list<std::pair<std::wstring const,std::wstring>>(void)
0x14003e38e  mov     rcx, [rbp+350h+var_50]
0x14003e395  xor     rcx, rsp; StackCookie
0x14003e398  call    __security_check_cookie
0x14003e39d  movaps  xmm6, [rsp+450h+var_48+8]
0x14003e3a5  add     rsp, 428h
0x14003e3ac  pop     r15
0x14003e3ae  pop     r12
0x14003e3b0  pop     rdi
0x14003e3b1  pop     rsi
0x14003e3b2  pop     rbx
0x14003e3b3  pop     rbp
0x14003e3b4  retn
0x14003e3b5  lea     rdx, aCouldNotOpenTe; "Could not open template folder for sear"...
0x14003e3bc  lea     rcx, [rsp+450h+Src]
0x14003e3c1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14003e3c6  nop
0x14003e3c7  lea     rdx, [rsp+450h+Src]
0x14003e3cc  lea     rcx, [rbp+350h+pExceptionObject]
0x14003e3d0  call    ??0FileIOException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::FileIOException::FileIOException(std::wstring const &)
0x14003e3d5  lea     rdx, _TI3?AVFileIOException@Uev@@; pThrowInfo
0x14003e3dc  lea     rcx, [rbp+350h+pExceptionObject]; pExceptionObject
0x14003e3e0  call    _CxxThrowException_0
0x14003e3e6  lea     rdx, aCouldNotRetrie; "Could not retrieve all files from templ"...
0x14003e3ed  lea     rcx, [rsp+450h+Src]
0x14003e3f2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14003e3f7  nop
0x14003e3f8  lea     rdx, [rsp+450h+Src]
0x14003e3fd  lea     rcx, [rbp+350h+pExceptionObject]
0x14003e401  call    ??0FileIOException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::FileIOException::FileIOException(std::wstring const &)
0x14003e406  lea     rdx, _TI3?AVFileIOException@Uev@@; pThrowInfo
0x14003e40d  lea     rcx, [rbp+350h+pExceptionObject]; pExceptionObject
0x14003e411  call    _CxxThrowException_0
0x14003e417  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x14003e41d  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
