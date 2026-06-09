# SaveOriginalConfigurationDocument(DeclaredConfigurationScopeData *,DCDocument *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18009a348`
- end: `0x18009a820`
- name: `?SaveOriginalConfigurationDocument@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1240`
- prototype: `__int64 __fastcall(struct DeclaredConfigurationScopeData *, struct DCDocument *, LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180084570`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x18001438c`
- `0x1800143c8`
- `0x180018ac0`
- `0x180019d38`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001dea8`
- `0x18004dc70`
- `0x180058630`
- `0x18005e7dc`
- `0x1800601c0`
- `0x1800726a4`
- `0x18009a348`
- `0x1800a0de4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009a6d5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009a6d5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009a619`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009a619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a5d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a6df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a5d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a6df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a710`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009a6aa`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009a6aa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009a5c2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009a5c2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18009a6ca`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18009a6ca`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18009a706`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18009a706`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18009a39f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18009a39f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009a3cb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009a3cb`

## string_xrefs

- `0x18009a3e3`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009a578`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009a635`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009a77d`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SaveOriginalConfigurationDocument(
        struct DeclaredConfigurationScopeData *a1,
        char **a2,
        const WCHAR *lpWideCharStr)
{
  HRESULT v6; // eax
  int FilePathForOriginalDocStorage; // ebx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // r8
  __int64 last_of; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  const unsigned __int16 *v15; // rdx
  wil *v16; // rcx
  const WCHAR *v17; // rcx
  HANDLE FileW; // rbx
  signed int LastError; // eax
  __int64 v20; // rdx
  unsigned __int64 v21; // rax
  int v22; // r14d
  CHAR *v23; // rax
  CHAR *v24; // rsi
  int v25; // eax
  DWORD v26; // r8d
  int v27; // eax
  BOOL v28; // edi
  signed int v29; // eax
  signed int v30; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-1A8h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-1A8h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-1A8h]
  HANDLE v35; // [rsp+40h] [rbp-188h] BYREF
  __int64 v36; // [rsp+48h] [rbp-180h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-178h] BYREF
  __int64 *v38; // [rsp+58h] [rbp-170h] BYREF
  unsigned __int16 *v39; // [rsp+60h] [rbp-168h] BYREF
  char v40; // [rsp+68h] [rbp-160h]
  LPCWSTR lpFileName[4]; // [rsp+78h] [rbp-150h] BYREF
  wil *v42[4]; // [rsp+98h] [rbp-130h] BYREF
  GUID pguid; // [rsp+B8h] [rbp-110h] BYREF
  _BYTE v44[40]; // [rsp+C8h] [rbp-100h] BYREF
  unsigned __int16 v45[40]; // [rsp+F0h] [rbp-D8h] BYREF
  OLECHAR sz[40]; // [rsp+140h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  v36 = 0;
  pguid = 0;
  v45[0] = 0;
  sz[0] = 0;
  v6 = CoCreateGuid(&pguid);
  FilePathForOriginalDocStorage = v6;
  if ( v6 >= 0 )
  {
    if ( StringFromGUID2(&pguid, sz, 39) != 39 )
    {
      FilePathForOriginalDocStorage = -2147418113;
      v9 = 22210;
LABEL_5:
      v8 = (unsigned int)FilePathForOriginalDocStorage;
      goto LABEL_6;
    }
    v10 = DCTrimGuidBracket(sz, v45);
    FilePathForOriginalDocStorage = v10;
    if ( v10 < 0 )
    {
      v8 = (unsigned int)v10;
      v9 = 22216;
      goto LABEL_6;
    }
    v11 = -1;
    do
      ++v11;
    while ( v45[v11] );
    std::wstring::_Assign<unsigned short>(a2 + 56, v45, (char *)v11);
    v38 = &v36;
    v39 = 0;
    v40 = 1;
    FilePathForOriginalDocStorage = DeclaredConfigurationStore_GetFilePathForOriginalDocStorage(
                                      a1,
                                      v45,
                                      (struct DCDocument *)a2,
                                      &v39);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v38);
    if ( FilePathForOriginalDocStorage < 0 )
    {
      v9 = 22224;
      goto LABEL_5;
    }
    std::wstring::wstring((__int64)lpFileName, v36);
    last_of = std::wstring::find_last_of(lpFileName, L"\\");
    std::wstring::wstring((__int64)v42);
    std::wstring::wstring((__int64)&v38);
    try
    {
      v13 = std::wstring::substr(lpFileName, v44, 0, last_of);
      std::wstring::operator=(v42, v13);
      std::wstring::_Tidy_deallocate(v44);
      v14 = std::wstring::substr(lpFileName, v44, last_of + 1, -1);
      std::wstring::operator=(&v38, v14);
      std::wstring::_Tidy_deallocate(v44);
    }
    catch ( std::bad_alloc )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x56DF,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)0x8007000ELL,
        dwCreationDisposition);
      std::wstring::_Tidy_deallocate(&v38);
      std::wstring::_Tidy_deallocate(v42);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v36);
      return 2147942414LL;
    }
    v16 = (wil *)v42;
    if ( v42[3] > (wil *)7 )
      v16 = v42[0];
    FilePathForOriginalDocStorage = wil::CreateDirectoryDeepNoThrow(v16, v15);
    if ( (int)(FilePathForOriginalDocStorage + 0x80000000) >= 0 && FilePathForOriginalDocStorage != -2147024713 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x56E9,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)FilePathForOriginalDocStorage,
        dwCreationDispositiona);
LABEL_47:
      std::wstring::_Tidy_deallocate(&v38);
      std::wstring::_Tidy_deallocate(v42);
      std::wstring::_Tidy_deallocate(lpFileName);
      goto LABEL_48;
    }
    v17 = (const WCHAR *)lpFileName;
    if ( lpFileName[3] > (LPCWSTR)7 )
      v17 = lpFileName[0];
    FileW = CreateFileW(v17, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    v35 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      FilePathForOriginalDocStorage = LastError;
      if ( LastError > 0 )
        FilePathForOriginalDocStorage = (unsigned __int16)LastError | 0x80070000;
      if ( FilePathForOriginalDocStorage >= 0 )
        goto LABEL_46;
      v20 = 22263;
    }
    else
    {
      NumberOfBytesWritten = 0;
      v21 = *((_QWORD *)lpWideCharStr + 2);
      if ( v21 > 0x7FFFFFFF )
      {
        FilePathForOriginalDocStorage = -2147024362;
        v20 = 22269;
      }
      else
      {
        v22 = 2 * v21;
        v23 = (CHAR *)malloc(2 * (int)v21);
        v24 = v23;
        if ( !v23 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5704,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)0x8007000ELL,
            dwCreationDispositionb);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
          std::wstring::_Tidy_deallocate(&v38);
          std::wstring::_Tidy_deallocate(v42);
          std::wstring::_Tidy_deallocate(lpFileName);
          FilePathForOriginalDocStorage = -2147024882;
          goto LABEL_48;
        }
        if ( *((_QWORD *)lpWideCharStr + 3) > 7u )
          lpWideCharStr = *(const WCHAR **)lpWideCharStr;
        v25 = WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, -1, v23, v22, 0, 0);
        v26 = 0;
        v27 = v25 - 1;
        if ( v27 >= 0 )
          v26 = v27;
        v28 = WriteFile(FileW, v24, v26, &NumberOfBytesWritten, 0);
        free(v24);
        if ( v28 )
        {
          if ( FlushFileBuffers(FileW) )
          {
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
            std::wstring::_Tidy_deallocate(&v38);
            std::wstring::_Tidy_deallocate(v42);
            std::wstring::_Tidy_deallocate(lpFileName);
            std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v36);
            return 0;
          }
          v30 = GetLastError();
          FilePathForOriginalDocStorage = v30;
          if ( v30 > 0 )
            FilePathForOriginalDocStorage = (unsigned __int16)v30 | 0x80070000;
          if ( FilePathForOriginalDocStorage >= 0 )
            goto LABEL_46;
          v20 = 22292;
        }
        else
        {
          v29 = GetLastError();
          FilePathForOriginalDocStorage = v29;
          if ( v29 > 0 )
            FilePathForOriginalDocStorage = (unsigned __int16)v29 | 0x80070000;
          if ( FilePathForOriginalDocStorage >= 0 )
            goto LABEL_46;
          v20 = 22287;
        }
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)FilePathForOriginalDocStorage,
      dwCreationDispositionb);
LABEL_46:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
    goto LABEL_47;
  }
  v8 = (unsigned int)v6;
  v9 = 22205;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
    (const char *)v8,
    dwCreationDispositiona);
LABEL_48:
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v36);
  return (unsigned int)FilePathForOriginalDocStorage;
}

```

## disassembly

```asm
0x18009a348  push    rbx
0x18009a34a  push    rsi
0x18009a34b  push    rdi
0x18009a34c  push    r14
0x18009a34e  push    r15
0x18009a350  sub     rsp, 1A0h
0x18009a357  mov     rax, cs:__security_cookie
0x18009a35e  xor     rax, rsp
0x18009a361  mov     [rsp+1C8h+var_38], rax
0x18009a369  mov     rdi, r8
0x18009a36c  mov     rsi, rdx
0x18009a36f  mov     r14, rcx
0x18009a372  xor     r15d, r15d
0x18009a375  mov     [rsp+1C8h+var_180], r15
0x18009a37a  xorps   xmm0, xmm0
0x18009a37d  movups  xmmword ptr [rsp+1C8h+pguid.Data1], xmm0
0x18009a385  mov     [rsp+1C8h+var_D8], r15w
0x18009a38e  mov     [rsp+1C8h+sz], r15w
0x18009a397  lea     rcx, [rsp+1C8h+pguid]; pguid
0x18009a39f  call    cs:__imp_CoCreateGuid
0x18009a3a5  mov     ebx, eax
0x18009a3a7  test    eax, eax
0x18009a3a9  jns     short loc_18009A3B5
0x18009a3ab  mov     r9d, eax
0x18009a3ae  mov     edx, 56BDh
0x18009a3b3  jmp     short loc_18009A3E3
0x18009a3b5  mov     r8d, 27h ; '''; cchMax
0x18009a3bb  lea     rdx, [rsp+1C8h+sz]; lpsz
0x18009a3c3  lea     rcx, [rsp+1C8h+pguid]; rguid
0x18009a3cb  call    cs:__imp_StringFromGUID2
0x18009a3d1  cmp     eax, 27h ; '''
0x18009a3d4  jz      short loc_18009A3FC
0x18009a3d6  mov     ebx, 8000FFFFh
0x18009a3db  mov     edx, 56C2h; void *
0x18009a3e0  mov     r9d, ebx; char *
0x18009a3e3  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18009a3ea  mov     rcx, [rsp+1C8h]; this
0x18009a3f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a3f7  jmp     loc_18009A7C0
0x18009a3fc  lea     rdx, [rsp+1C8h+var_D8]; unsigned __int16 *
0x18009a404  lea     rcx, [rsp+1C8h+sz]; unsigned __int16 *
0x18009a40c  call    ?DCTrimGuidBracket@@YAJPEBGPEAG@Z; DCTrimGuidBracket(ushort const *,ushort *)
0x18009a411  mov     ebx, eax
0x18009a413  test    eax, eax
0x18009a415  jns     short loc_18009A421
0x18009a417  mov     r9d, eax
0x18009a41a  mov     edx, 56C8h
0x18009a41f  jmp     short loc_18009A3E3
0x18009a421  lea     rax, [rsp+1C8h+var_D8]
0x18009a429  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009a42d  inc     r8
0x18009a430  cmp     [rax+r8*2], r15w
0x18009a435  jnz     short loc_18009A42D
0x18009a437  lea     rcx, [rsi+1C0h]
0x18009a43e  lea     rdx, [rsp+1C8h+var_D8]
0x18009a446  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18009a44b  lea     rax, [rsp+1C8h+var_180]
0x18009a450  mov     [rsp+1C8h+var_170], rax
0x18009a455  mov     [rsp+1C8h+var_168], r15
0x18009a45a  mov     [rsp+1C8h+var_160], 1
0x18009a45f  lea     r9, [rsp+1C8h+var_168]; unsigned __int16 **
0x18009a464  mov     r8, rsi; struct DCDocument *
0x18009a467  lea     rdx, [rsp+1C8h+var_D8]; unsigned __int16 *
0x18009a46f  mov     rcx, r14; struct DeclaredConfigurationScopeData *
0x18009a472  call    ?DeclaredConfigurationStore_GetFilePathForOriginalDocStorage@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAVDCDocument@@PEAPEAG@Z; DeclaredConfigurationStore_GetFilePathForOriginalDocStorage(DeclaredConfigurationScopeData *,ushort const *,DCDocument *,ushort * *)
0x18009a477  mov     ebx, eax
0x18009a479  lea     rcx, [rsp+1C8h+var_170]
0x18009a47e  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x18009a483  test    ebx, ebx
0x18009a485  jns     short loc_18009A491
0x18009a487  mov     edx, 56D0h
0x18009a48c  jmp     loc_18009A3E0
0x18009a491  mov     rdx, [rsp+1C8h+var_180]
0x18009a496  lea     rcx, [rsp+1C8h+lpFileName]
0x18009a49b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009a4a0  nop
0x18009a4a1  lea     rdx, StringValue; "\\"
0x18009a4a8  lea     rcx, [rsp+1C8h+lpFileName]
0x18009a4ad  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x18009a4b2  mov     rbx, rax
0x18009a4b5  lea     rcx, [rsp+1C8h+var_130]
0x18009a4bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009a4c2  nop
0x18009a4c3  lea     rcx, [rsp+1C8h+var_170]
0x18009a4c8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009a4cd  nop
0x18009a4ce  mov     r9, rbx
0x18009a4d1  xor     r8d, r8d
0x18009a4d4  lea     rdx, [rsp+1C8h+var_100]
0x18009a4dc  lea     rcx, [rsp+1C8h+lpFileName]
0x18009a4e1  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18009a4e6  mov     rdx, rax
0x18009a4e9  lea     rcx, [rsp+1C8h+var_130]
0x18009a4f1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18009a4f6  lea     rcx, [rsp+1C8h+var_100]
0x18009a4fe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a503  lea     r8, [rbx+1]
0x18009a507  or      r9, 0FFFFFFFFFFFFFFFFh
0x18009a50b  lea     rdx, [rsp+1C8h+var_100]
0x18009a513  lea     rcx, [rsp+1C8h+lpFileName]
0x18009a518  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18009a51d  mov     rdx, rax
0x18009a520  lea     rcx, [rsp+1C8h+var_170]
0x18009a525  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18009a52a  lea     rcx, [rsp+1C8h+var_100]
0x18009a532  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a537  nop
0x18009a538  lea     rcx, [rsp+1C8h+var_130]
0x18009a540  cmp     [rsp+1C8h+var_118], 7
0x18009a549  cmova   rcx, [rsp+1C8h+var_130]; this
0x18009a552  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x18009a557  mov     ebx, eax
0x18009a559  mov     eax, 80000000h
0x18009a55e  lea     ecx, [rbx+rax]
0x18009a561  test    eax, ecx
0x18009a563  jnz     short loc_18009A58E
0x18009a565  cmp     ebx, 800700B7h
0x18009a56b  jz      short loc_18009A58E
0x18009a56d  mov     rcx, [rsp+1C8h]; this
0x18009a575  mov     r9d, ebx; char *
0x18009a578  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18009a57f  mov     edx, 56E9h; void *
0x18009a584  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a589  jmp     loc_18009A79C
0x18009a58e  lea     rcx, [rsp+1C8h+lpFileName]
0x18009a593  cmp     [rsp+1C8h+var_138], 7
0x18009a59c  cmova   rcx, [rsp+1C8h+lpFileName]; lpFileName
0x18009a5a2  mov     [rsp+1C8h+hTemplateFile], r15; hTemplateFile
0x18009a5a7  mov     [rsp+1C8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18009a5af  mov     [rsp+1C8h+dwCreationDisposition], 2; int
0x18009a5b7  xor     r9d, r9d; lpSecurityAttributes
0x18009a5ba  xor     r8d, r8d; dwShareMode
0x18009a5bd  mov     edx, 40000000h; dwDesiredAccess
0x18009a5c2  call    cs:__imp_CreateFileW
0x18009a5c8  mov     rbx, rax
0x18009a5cb  mov     [rsp+1C8h+var_188], rax
0x18009a5d0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009a5d4  jnz     short loc_18009A5FD
0x18009a5d6  call    cs:__imp_GetLastError
0x18009a5dc  mov     ebx, eax
0x18009a5de  test    eax, eax
0x18009a5e0  jle     short loc_18009A5EB
0x18009a5e2  movzx   ebx, ax
0x18009a5e5  or      ebx, 80070000h
0x18009a5eb  test    ebx, ebx
0x18009a5ed  jns     loc_18009A791
0x18009a5f3  mov     edx, 56F7h
0x18009a5f8  jmp     loc_18009A77A
0x18009a5fd  mov     [rsp+1C8h+NumberOfBytesWritten], r15d
0x18009a602  mov     rax, [rdi+10h]
0x18009a606  cmp     rax, 7FFFFFFFh
0x18009a60c  ja      loc_18009A770
0x18009a612  lea     r14d, [rax+rax]
0x18009a616  movsxd  rcx, r14d; Size
0x18009a619  call    cs:__imp_malloc
0x18009a61f  mov     rsi, rax
0x18009a622  test    rax, rax
0x18009a625  jnz     short loc_18009A67E
0x18009a627  mov     rcx, [rsp+1C8h]; this
0x18009a62f  mov     r9d, 8007000Eh; char *
0x18009a635  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18009a63c  mov     edx, 5704h; void *
0x18009a641  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a646  lea     rcx, [rsp+1C8h+var_188]
0x18009a64b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009a650  nop
0x18009a651  lea     rcx, [rsp+1C8h+var_170]
0x18009a656  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a65b  nop
0x18009a65c  lea     rcx, [rsp+1C8h+var_130]
0x18009a664  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a669  nop
0x18009a66a  lea     rcx, [rsp+1C8h+lpFileName]
0x18009a66f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a674  mov     ebx, 8007000Eh
0x18009a679  jmp     loc_18009A7C0
0x18009a67e  cmp     qword ptr [rdi+18h], 7
0x18009a683  jbe     short loc_18009A688
0x18009a685  mov     rdi, [rdi]
0x18009a688  mov     [rsp+1C8h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x18009a68d  mov     [rsp+1C8h+hTemplateFile], r15; lpDefaultChar
0x18009a692  mov     [rsp+1C8h+dwFlagsAndAttributes], r14d; cbMultiByte
0x18009a697  mov     qword ptr [rsp+1C8h+dwCreationDisposition], rsi; lpMultiByteStr
0x18009a69c  or      r9d, 0FFFFFFFFh; cchWideChar
0x18009a6a0  mov     r8, rdi; lpWideCharStr
0x18009a6a3  xor     edx, edx; dwFlags
0x18009a6a5  mov     ecx, 0FDE9h; CodePage
0x18009a6aa  call    cs:__imp_WideCharToMultiByte
0x18009a6b0  mov     r8d, r15d
0x18009a6b3  sub     eax, 1
0x18009a6b6  cmovns  r8d, eax; nNumberOfBytesToWrite
0x18009a6ba  mov     qword ptr [rsp+1C8h+dwCreationDisposition], r15; lpOverlapped
0x18009a6bf  lea     r9, [rsp+1C8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18009a6c4  mov     rdx, rsi; lpBuffer
0x18009a6c7  mov     rcx, rbx; hFile
0x18009a6ca  call    cs:__imp_WriteFile
0x18009a6d0  mov     edi, eax
0x18009a6d2  mov     rcx, rsi; Block
0x18009a6d5  call    cs:__imp_free
0x18009a6db  test    edi, edi
0x18009a6dd  jnz     short loc_18009A703
0x18009a6df  call    cs:__imp_GetLastError
0x18009a6e5  mov     ebx, eax
0x18009a6e7  test    eax, eax
0x18009a6e9  jle     short loc_18009A6F4
0x18009a6eb  movzx   ebx, ax
0x18009a6ee  or      ebx, 80070000h
0x18009a6f4  test    ebx, ebx
0x18009a6f6  jns     loc_18009A791
0x18009a6fc  mov     edx, 570Fh
0x18009a701  jmp     short loc_18009A77A
0x18009a703  mov     rcx, rbx; hFile
0x18009a706  call    cs:__imp_FlushFileBuffers
0x18009a70c  test    eax, eax
0x18009a70e  jnz     short loc_18009A730
0x18009a710  call    cs:__imp_GetLastError
0x18009a716  mov     ebx, eax
0x18009a718  test    eax, eax
0x18009a71a  jle     short loc_18009A725
0x18009a71c  movzx   ebx, ax
0x18009a71f  or      ebx, 80070000h
0x18009a725  test    ebx, ebx
0x18009a727  jns     short loc_18009A791
0x18009a729  mov     edx, 5714h
0x18009a72e  jmp     short loc_18009A77A
0x18009a730  lea     rcx, [rsp+1C8h+var_188]
0x18009a735  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009a73a  nop
0x18009a73b  lea     rcx, [rsp+1C8h+var_170]
0x18009a740  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a745  nop
0x18009a746  lea     rcx, [rsp+1C8h+var_130]
0x18009a74e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a753  nop
0x18009a754  lea     rcx, [rsp+1C8h+lpFileName]
0x18009a759  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a75e  nop
0x18009a75f  lea     rcx, [rsp+1C8h+var_180]
0x18009a764  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x18009a769  xor     eax, eax
0x18009a76b  jmp     loc_18009A801
0x18009a770  mov     ebx, 80070216h
0x18009a775  mov     edx, 56FDh; void *
0x18009a77a  mov     r9d, ebx; char *
0x18009a77d  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18009a784  mov     rcx, [rsp+1C8h]; this
0x18009a78c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a791  lea     rcx, [rsp+1C8h+var_188]
0x18009a796  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009a79b  nop
0x18009a79c  lea     rcx, [rsp+1C8h+var_170]
0x18009a7a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a7a6  nop
0x18009a7a7  lea     rcx, [rsp+1C8h+var_130]
0x18009a7af  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a7b4  nop
0x18009a7b5  lea     rcx, [rsp+1C8h+lpFileName]
0x18009a7ba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a7bf  nop
0x18009a7c0  lea     rcx, [rsp+1C8h+var_180]
0x18009a7c5  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x18009a7ca  mov     eax, ebx
0x18009a7cc  jmp     short loc_18009A801
0x18009a7ce  lea     rcx, [rsp+1C8h+var_170]
0x18009a7d3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a7d8  nop
0x18009a7d9  lea     rcx, [rsp+1C8h+var_130]
0x18009a7e1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a7e6  nop
0x18009a7e7  lea     rcx, [rsp+1C8h+lpFileName]
0x18009a7ec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a7f1  nop
0x18009a7f2  lea     rcx, [rsp+1C8h+var_180]
0x18009a7f7  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x18009a7fc  mov     eax, 8007000Eh
0x18009a801  mov     rcx, [rsp+1C8h+var_38]
0x18009a809  xor     rcx, rsp; StackCookie
0x18009a80c  call    __security_check_cookie
0x18009a811  add     rsp, 1A0h
0x18009a818  pop     r15
0x18009a81a  pop     r14
0x18009a81c  pop     rdi
0x18009a81d  pop     rsi
0x18009a81e  pop     rbx
0x18009a81f  retn
```
