# MsixPackage::Provisioning::Library::PackageSource::ProcessReplaceFullPackageWithStub(ushort const *,bool)

- ea: `0x18005d674`
- end: `0x18005d9de`
- name: `?ProcessReplaceFullPackageWithStub@PackageSource@Library@Provisioning@MsixPackage@@AEAAJPEBG_N@Z`
- size: `874`
- prototype: `int(MsixPackage::Provisioning::Library::PackageSource *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180056d60`

## callees

- `0x18000cfe8`
- `0x18001bf0c`
- `0x18001c5b8`
- `0x180031ed8`
- `0x180039e60`
- `0x18003ae3c`
- `0x180040400`
- `0x18005d674`
- `0x180066db2`
- `0x180066df0`

## import_xrefs

- `msvcrt!wcschr` at `0x18005d6d2`
- `msvcrt!wcschr` at `0x18005d6d2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005d813`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005d84f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005d97c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005d9a2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005d813`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005d84f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005d97c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005d9a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d940`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d7fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d7fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d946`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18005d7e9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18005d7e9`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18005d86b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18005d86b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005d968`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005d98e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005d968`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005d98e`

## string_xrefs

- `0x18005d8ff`: `MsixPackage::Provisioning::Library::PackageSource::ProcessReplaceFullPackageWithStub`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall MsixPackage::Provisioning::Library::PackageSource::ProcessReplaceFullPackageWithStub(
        MsixPackage::Provisioning::Library::PackageSource *this,
        wchar_t *a2,
        char a3)
{
  wchar_t *v5; // rax
  char *v6; // rbx
  __int64 result; // rax
  char *v8; // rdx
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // r8
  const WCHAR *v12; // rcx
  HANDLE FirstFileW; // rbx
  const char *v14; // r9
  unsigned int LastErrorMsg; // ebx
  int v16; // eax
  void *v17; // rdi
  int v18; // eax
  signed int LastError; // eax
  unsigned int v20; // edi
  const char *v21; // [rsp+20h] [rbp-2B8h]
  LPVOID pv[2]; // [rsp+30h] [rbp-2A8h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+40h] [rbp-298h] BYREF
  unsigned __int64 v24; // [rsp+58h] [rbp-280h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-278h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  if ( *(_DWORD *)(*(_QWORD *)this + 600LL) || *(_DWORD *)(*(_QWORD *)this + 676LL) || a3 )
    return 0;
  v5 = wcschr(a2, 0x5Fu);
  v6 = (char *)v5;
  if ( v5 )
  {
    v8 = *(char **)(*(_QWORD *)this + 560LL);
    v24 = 7;
    lpFileName[2] = 0;
    LOWORD(lpFileName[0]) = 0;
    v9 = -1;
    if ( *(_WORD *)v8 )
    {
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)&v8[2 * v10] );
    }
    else
    {
      v10 = 0;
    }
    try
    {
      std::wstring::assign(lpFileName, v8, v10);
      std::wstring::append(lpFileName, (char *)L"\\", pszSrc[0] != 0);
      std::wstring::append(lpFileName, (char *)a2, (v6 - (char *)a2) >> 1);
      std::wstring::append(lpFileName, (char *)L"*~", 2u);
      if ( *(_WORD *)v6 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)&v6[2 * v11] );
      }
      else
      {
        v11 = 0;
      }
      std::wstring::append(lpFileName, v6, v11);
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      v12 = (const WCHAR *)lpFileName;
      if ( v24 >= 8 )
        v12 = lpFileName[0];
      FirstFileW = FindFirstFileW(v12, &FindFileData);
      pv[1] = FirstFileW;
      if ( FirstFileW == (HANDLE)-1LL )
      {
        if ( GetLastError() == 2 )
        {
          if ( v24 >= 8 )
            operator delete((void *)lpFileName[0]);
          result = 0;
        }
        else
        {
          LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                           retaddr,
                           (void *)0xDA,
                           (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagesource.cpp",
                           "Unexpected error while enumerating packages.",
                           v21);
          if ( v24 >= 8 )
            operator delete((void *)lpFileName[0]);
          result = LastErrorMsg;
        }
      }
      else
      {
        while ( (FindFileData.dwFileAttributes & 0x10) == 0 )
        {
          if ( !FindNextFileW(FirstFileW, &FindFileData) )
            goto LABEL_37;
        }
        if ( FindFileData.cFileName[0] )
        {
          do
            ++v9;
          while ( FindFileData.cFileName[v9] );
        }
        else
        {
          v9 = 0;
        }
        std::wstring::assign((_QWORD *)this + 7, (char *)FindFileData.cFileName, v9);
        pv[0] = 0;
        v16 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                (char *)pv,
                L"Found existing full bundle %s",
                FindFileData.cFileName);
        if ( v16 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xE9,
            (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagesource.cpp",
            (const char *)(unsigned int)v16);
        v17 = pv[0];
        v18 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
                (__int64)pv[0],
                (__int64)L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagesource.cpp",
                (int)L"MsixPackage::Provisioning::Library::PackageSource::ProcessReplaceFullPackageWithStub",
                236,
                2u,
                0);
        if ( v18 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xEC,
            (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagesource.cpp",
            (const char *)(unsigned int)v18);
        if ( v17 )
          CoTaskMemFree(v17);
LABEL_37:
        LastError = GetLastError();
        v20 = LastError;
        if ( LastError == 18 )
        {
          if ( FirstFileW )
            FindClose(FirstFileW);
          if ( v24 >= 8 )
            operator delete((void *)lpFileName[0]);
          result = 0;
        }
        else
        {
          if ( LastError > 0 )
            v20 = (unsigned __int16)LastError | 0x80070000;
          if ( FirstFileW )
            FindClose(FirstFileW);
          if ( v24 >= 8 )
            operator delete((void *)lpFileName[0]);
          result = v20;
        }
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0xF8,
                             (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagesource.cpp",
                             v14);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagesource.cpp",
      (const char *)0x8000FFFFLL,
      (int)v21);
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x18005d674  mov     [rsp+arg_10], rbx
0x18005d679  mov     [rsp+arg_18], rsi
0x18005d67e  push    rdi
0x18005d67f  push    r14
0x18005d681  push    r15
0x18005d683  sub     rsp, 2C0h
0x18005d68a  mov     rax, cs:__security_cookie
0x18005d691  xor     rax, rsp
0x18005d694  mov     [rsp+2D8h+var_28], rax
0x18005d69c  mov     rsi, rdx
0x18005d69f  mov     r14, rcx
0x18005d6a2  mov     rax, [rcx]
0x18005d6a5  xor     r15d, r15d
0x18005d6a8  cmp     [rax+258h], r15d
0x18005d6af  jnz     loc_18005D9AC
0x18005d6b5  cmp     [rax+2A4h], r15d
0x18005d6bc  jnz     loc_18005D9AC
0x18005d6c2  test    r8b, r8b
0x18005d6c5  jnz     loc_18005D9AC
0x18005d6cb  lea     edx, [r15+5Fh]; Ch
0x18005d6cf  mov     rcx, rsi; Str
0x18005d6d2  call    cs:__imp_wcschr
0x18005d6d8  mov     rbx, rax
0x18005d6db  test    rax, rax
0x18005d6de  jnz     short loc_18005D708
0x18005d6e0  mov     rcx, [rsp+2D8h]; this
0x18005d6e8  mov     ebx, 8000FFFFh
0x18005d6ed  mov     r9d, ebx; char *
0x18005d6f0  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005d6f7  mov     edx, 0C5h; void *
0x18005d6fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d701  mov     eax, ebx
0x18005d703  jmp     loc_18005D9B4
0x18005d708  mov     rax, [r14]
0x18005d70b  mov     rdx, [rax+230h]; Src
0x18005d712  mov     [rsp+2D8h+var_280], 7
0x18005d71b  mov     [rsp+2D8h+var_288], r15
0x18005d720  mov     word ptr [rsp+2D8h+lpFileName], r15w
0x18005d726  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005d72a  cmp     [rdx], r15w
0x18005d72e  jnz     short loc_18005D735
0x18005d730  mov     r8, r15
0x18005d733  jmp     short loc_18005D742
0x18005d735  mov     r8, rdi
0x18005d738  inc     r8
0x18005d73b  cmp     [rdx+r8*2], r15w
0x18005d740  jnz     short loc_18005D738
0x18005d742  lea     rcx, [rsp+2D8h+lpFileName]; void *
0x18005d747  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18005d74c  nop
0x18005d74d  mov     r8, r15
0x18005d750  cmp     word ptr cs:pszSrc, r15w; "\\"
0x18005d758  setnz   r8b
0x18005d75c  lea     rdx, pszSrc; "\\"
0x18005d763  lea     rcx, [rsp+2D8h+lpFileName]; Src
0x18005d768  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18005d76d  mov     r8, rbx
0x18005d770  sub     r8, rsi
0x18005d773  sar     r8, 1
0x18005d776  mov     rdx, rsi; void *
0x18005d779  lea     rcx, [rsp+2D8h+lpFileName]; Src
0x18005d77e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18005d783  mov     esi, 2
0x18005d788  mov     r8d, esi
0x18005d78b  lea     rdx, asc_18007DB0C; "*~"
0x18005d792  lea     rcx, [rsp+2D8h+lpFileName]; Src
0x18005d797  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18005d79c  cmp     [rbx], r15w
0x18005d7a0  jnz     short loc_18005D7A7
0x18005d7a2  mov     r8, r15
0x18005d7a5  jmp     short loc_18005D7B4
0x18005d7a7  mov     r8, rdi
0x18005d7aa  inc     r8
0x18005d7ad  cmp     [rbx+r8*2], r15w
0x18005d7b2  jnz     short loc_18005D7AA
0x18005d7b4  mov     rdx, rbx; void *
0x18005d7b7  lea     rcx, [rsp+2D8h+lpFileName]; Src
0x18005d7bc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18005d7c1  xor     edx, edx; Val
0x18005d7c3  mov     r8d, 250h; Size
0x18005d7c9  lea     rcx, [rsp+2D8h+FindFileData]; void *
0x18005d7ce  call    memset_0
0x18005d7d3  lea     rcx, [rsp+2D8h+lpFileName]
0x18005d7d8  cmp     [rsp+2D8h+var_280], 8
0x18005d7de  cmovnb  rcx, [rsp+2D8h+lpFileName]; lpFileName
0x18005d7e4  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x18005d7e9  call    cs:__imp_FindFirstFileW
0x18005d7ef  mov     rbx, rax
0x18005d7f2  mov     [rsp+2D8h+var_2A0], rax
0x18005d7f7  cmp     rax, rdi
0x18005d7fa  jnz     short loc_18005D85C
0x18005d7fc  call    cs:__imp_GetLastError
0x18005d802  cmp     eax, esi
0x18005d804  jnz     short loc_18005D820
0x18005d806  cmp     [rsp+2D8h+var_280], 8
0x18005d80c  jb      short loc_18005D819
0x18005d80e  mov     rcx, [rsp+2D8h+lpFileName]
0x18005d813  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18005d819  xor     eax, eax
0x18005d81b  jmp     loc_18005D9B4
0x18005d820  mov     rcx, [rsp+2D8h]; this
0x18005d828  lea     r9, aUnexpectedErro; "Unexpected error while enumerating pack"...
0x18005d82f  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005d836  mov     edx, 0DAh; void *
0x18005d83b  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18005d840  mov     ebx, eax
0x18005d842  cmp     [rsp+2D8h+var_280], 8
0x18005d848  jb      short loc_18005D855
0x18005d84a  mov     rcx, [rsp+2D8h+lpFileName]
0x18005d84f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18005d855  mov     eax, ebx
0x18005d857  jmp     loc_18005D9B4
0x18005d85c  test    byte ptr [rsp+2D8h+FindFileData.dwFileAttributes], 10h
0x18005d861  jnz     short loc_18005D87A
0x18005d863  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x18005d868  mov     rcx, rbx; hFindFile
0x18005d86b  call    cs:__imp_FindNextFileW
0x18005d871  test    eax, eax
0x18005d873  jnz     short loc_18005D85C
0x18005d875  jmp     loc_18005D946
0x18005d87a  lea     rcx, [r14+38h]; void *
0x18005d87e  cmp     [rsp+2D8h+FindFileData.cFileName], r15w
0x18005d887  jnz     short loc_18005D88E
0x18005d889  mov     rdi, r15
0x18005d88c  jmp     short loc_18005D8A0
0x18005d88e  lea     rax, [rsp+2D8h+FindFileData.cFileName]
0x18005d896  inc     rdi
0x18005d899  cmp     [rax+rdi*2], r15w
0x18005d89e  jnz     short loc_18005D896
0x18005d8a0  mov     r8, rdi
0x18005d8a3  lea     rdx, [rsp+2D8h+FindFileData.cFileName]; Src
0x18005d8ab  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18005d8b0  mov     [rsp+2D8h+pv], r15
0x18005d8b5  lea     r8, [rsp+2D8h+FindFileData.cFileName]
0x18005d8bd  lea     rdx, aFoundExistingF; "Found existing full bundle %s"
0x18005d8c4  lea     rcx, [rsp+2D8h+pv]
0x18005d8c9  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18005d8ce  mov     rcx, [rsp+2D8h]; this
0x18005d8d6  test    eax, eax
0x18005d8d8  jns     short loc_18005D8EE
0x18005d8da  mov     r9d, eax; char *
0x18005d8dd  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005d8e4  mov     edx, 0E9h; void *
0x18005d8e9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005d8ee  mov     [rsp+2D8h+var_2B0], r15d
0x18005d8f3  mov     dword ptr [rsp+2D8h+var_2B8], esi; int
0x18005d8f7  mov     esi, 0ECh
0x18005d8fc  mov     r9d, esi
0x18005d8ff  lea     r8, aMsixpackagePro_18; "MsixPackage::Provisioning::Library::Pac"...
0x18005d906  lea     rdx, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005d90d  mov     rdi, [rsp+2D8h+pv]
0x18005d912  mov     rcx, rdi
0x18005d915  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18005d91a  mov     rcx, [rsp+2D8h]; this
0x18005d922  test    eax, eax
0x18005d924  jns     short loc_18005D938
0x18005d926  mov     r9d, eax; char *
0x18005d929  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005d930  mov     edx, esi; void *
0x18005d932  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005d937  nop
0x18005d938  test    rdi, rdi
0x18005d93b  jz      short loc_18005D946
0x18005d93d  mov     rcx, rdi; pv
0x18005d940  call    cs:__imp_CoTaskMemFree
0x18005d946  call    cs:__imp_GetLastError
0x18005d94c  mov     edi, eax
0x18005d94e  cmp     eax, 12h
0x18005d951  jz      short loc_18005D986
0x18005d953  test    eax, eax
0x18005d955  jle     short loc_18005D960
0x18005d957  movzx   edi, ax
0x18005d95a  or      edi, 80070000h
0x18005d960  test    rbx, rbx
0x18005d963  jz      short loc_18005D96F
0x18005d965  mov     rcx, rbx; hFindFile
0x18005d968  call    cs:__imp_FindClose
0x18005d96e  nop
0x18005d96f  cmp     [rsp+2D8h+var_280], 8
0x18005d975  jb      short loc_18005D982
0x18005d977  mov     rcx, [rsp+2D8h+lpFileName]
0x18005d97c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18005d982  mov     eax, edi
0x18005d984  jmp     short loc_18005D9B4
0x18005d986  test    rbx, rbx
0x18005d989  jz      short loc_18005D995
0x18005d98b  mov     rcx, rbx; hFindFile
0x18005d98e  call    cs:__imp_FindClose
0x18005d994  nop
0x18005d995  cmp     [rsp+2D8h+var_280], 8
0x18005d99b  jb      short loc_18005D9A8
0x18005d99d  mov     rcx, [rsp+2D8h+lpFileName]
0x18005d9a2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18005d9a8  xor     eax, eax
0x18005d9aa  jmp     short loc_18005D9B4
0x18005d9ac  xor     eax, eax
0x18005d9ae  jmp     short loc_18005D9B4
0x18005d9b0  mov     eax, dword ptr [rsp+2D8h+pv]
0x18005d9b4  mov     rcx, [rsp+2D8h+var_28]
0x18005d9bc  xor     rcx, rsp; StackCookie
0x18005d9bf  call    __security_check_cookie
0x18005d9c4  lea     r11, [rsp+2D8h+var_18]
0x18005d9cc  mov     rbx, [r11+30h]
0x18005d9d0  mov     rsi, [r11+38h]
0x18005d9d4  mov     rsp, r11
0x18005d9d7  pop     r15
0x18005d9d9  pop     r14
0x18005d9db  pop     rdi
0x18005d9dc  retn
```
