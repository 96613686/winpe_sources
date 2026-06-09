# MsixPackage::Provisioning::Library::PackageSource::ProcessReplaceFullPackageWithStub(ushort const *,bool)

- ea: `0x1800622c0`
- end: `0x180062672`
- name: `?ProcessReplaceFullPackageWithStub@PackageSource@Library@Provisioning@MsixPackage@@AEAAJPEBG_N@Z`
- size: `946`
- prototype: `int(MsixPackage::Provisioning::Library::PackageSource *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005b444`

## callees

- `0x18000d3dc`
- `0x18001d160`
- `0x18001d65c`
- `0x180034d7c`
- `0x18003d4b0`
- `0x18003e50c`
- `0x180043fb4`
- `0x1800622c0`
- `0x18006c8d2`
- `0x18006c910`

## import_xrefs

- `msvcrt!wcschr` at `0x18006231e`
- `msvcrt!wcschr` at `0x18006231e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180062471`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800624b3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800625fe`
- `msvcrt!??3@YAXPEAX@Z` at `0x180062630`
- `msvcrt!??3@YAXPEAX@Z` at `0x180062471`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800624b3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800625fe`
- `msvcrt!??3@YAXPEAX@Z` at `0x180062630`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800625b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800625b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800625bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800625bc`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006243b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006243b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800624d5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800624d5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800625e4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180062616`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800625e4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180062616`

## string_xrefs

- `0x18006256f`: `MsixPackage::Provisioning::Library::PackageSource::ProcessReplaceFullPackageWithStub`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall MsixPackage::Provisioning::Library::PackageSource::ProcessReplaceFullPackageWithStub(
        MsixPackage::Provisioning::Library::PackageSource *this,
        wchar_t *a2,
        char a3)
{
  wchar_t *v5; // rax
  wchar_t *v6; // rbx
  __int64 result; // rax
  _WORD *v8; // rdx
  __int64 v9; // rdi
  __int64 v10; // r8
  __int64 v11; // r8
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
  int v22; // [rsp+20h] [rbp-2B8h]
  LPVOID pv[2]; // [rsp+30h] [rbp-2A8h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+40h] [rbp-298h] BYREF
  unsigned __int64 v25; // [rsp+58h] [rbp-280h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-278h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  if ( *(_DWORD *)(*(_QWORD *)this + 600LL) || *(_DWORD *)(*(_QWORD *)this + 676LL) || a3 )
    return 0;
  v5 = wcschr(a2, 0x5Fu);
  v6 = v5;
  if ( v5 )
  {
    v8 = *(_WORD **)(*(_QWORD *)this + 560LL);
    v25 = 7;
    lpFileName[2] = 0;
    LOWORD(lpFileName[0]) = 0;
    v9 = -1;
    if ( *v8 )
    {
      v10 = -1;
      do
        ++v10;
      while ( v8[v10] );
    }
    try
    {
      std::wstring::assign(lpFileName, v8);
      std::wstring::append(lpFileName, (void *)L"\\");
      std::wstring::append(lpFileName, a2);
      std::wstring::append(lpFileName, L"*~");
      if ( *v6 )
      {
        v11 = -1;
        do
          ++v11;
        while ( v6[v11] );
      }
      std::wstring::append(lpFileName, v6);
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      v12 = (const WCHAR *)lpFileName;
      if ( v25 >= 8 )
        v12 = lpFileName[0];
      FirstFileW = FindFirstFileW(v12, &FindFileData);
      pv[1] = FirstFileW;
      if ( FirstFileW == (HANDLE)-1LL )
      {
        if ( GetLastError() == 2 )
        {
          if ( v25 >= 8 )
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
          if ( v25 >= 8 )
            operator delete((void *)lpFileName[0]);
          result = LastErrorMsg;
        }
      }
      else
      {
        while ( (FindFileData.dwFileAttributes & 0x10) == 0 )
        {
          if ( !FindNextFileW(FirstFileW, &FindFileData) )
            goto LABEL_34;
        }
        if ( FindFileData.cFileName[0] )
        {
          do
            ++v9;
          while ( FindFileData.cFileName[v9] );
        }
        std::wstring::assign((char *)this + 56, FindFileData.cFileName);
        pv[0] = 0;
        v16 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                (char *)pv,
                L"Found existing full bundle %s",
                FindFileData.cFileName);
        if ( v16 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xE9,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagesource.cpp",
            (const char *)(unsigned int)v16,
            (int)v21);
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
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagesource.cpp",
            (const char *)(unsigned int)v18,
            v22);
        if ( v17 )
          CoTaskMemFree(v17);
LABEL_34:
        LastError = GetLastError();
        v20 = LastError;
        if ( LastError == 18 )
        {
          if ( FirstFileW )
            FindClose(FirstFileW);
          if ( v25 >= 8 )
            operator delete((void *)lpFileName[0]);
          result = 0;
        }
        else
        {
          if ( LastError > 0 )
            v20 = (unsigned __int16)LastError | 0x80070000;
          if ( FirstFileW )
            FindClose(FirstFileW);
          if ( v25 >= 8 )
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
0x1800622c0  mov     [rsp+arg_10], rbx
0x1800622c5  mov     [rsp+arg_18], rsi
0x1800622ca  push    rdi
0x1800622cb  push    r14
0x1800622cd  push    r15
0x1800622cf  sub     rsp, 2C0h
0x1800622d6  mov     rax, cs:__security_cookie
0x1800622dd  xor     rax, rsp
0x1800622e0  mov     [rsp+2D8h+var_28], rax
0x1800622e8  mov     rsi, rdx
0x1800622eb  mov     r14, rcx
0x1800622ee  mov     rax, [rcx]
0x1800622f1  xor     r15d, r15d
0x1800622f4  cmp     [rax+258h], r15d
0x1800622fb  jnz     loc_180062640
0x180062301  cmp     [rax+2A4h], r15d
0x180062308  jnz     loc_180062640
0x18006230e  test    r8b, r8b
0x180062311  jnz     loc_180062640
0x180062317  lea     edx, [r15+5Fh]; Ch
0x18006231b  mov     rcx, rsi; Str
0x18006231e  call    cs:__imp_wcschr
0x180062325  nop     dword ptr [rax+rax+00h]
0x18006232a  mov     rbx, rax
0x18006232d  test    rax, rax
0x180062330  jnz     short loc_18006235A
0x180062332  mov     rcx, [rsp+2D8h]; this
0x18006233a  mov     ebx, 8000FFFFh
0x18006233f  mov     r9d, ebx; char *
0x180062342  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180062349  mov     edx, 0C5h; void *
0x18006234e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062353  mov     eax, ebx
0x180062355  jmp     loc_180062648
0x18006235a  mov     rax, [r14]
0x18006235d  mov     rdx, [rax+230h]; Src
0x180062364  mov     [rsp+2D8h+var_280], 7
0x18006236d  mov     [rsp+2D8h+var_288], r15
0x180062372  mov     word ptr [rsp+2D8h+lpFileName], r15w
0x180062378  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006237c  cmp     [rdx], r15w
0x180062380  jnz     short loc_180062387
0x180062382  mov     r8, r15
0x180062385  jmp     short loc_180062394
0x180062387  mov     r8, rdi
0x18006238a  inc     r8
0x18006238d  cmp     [rdx+r8*2], r15w
0x180062392  jnz     short loc_18006238A
0x180062394  lea     rcx, [rsp+2D8h+lpFileName]; void *
0x180062399  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18006239e  nop
0x18006239f  mov     r8, r15
0x1800623a2  cmp     word ptr cs:pszSrc, r15w; "\\"
0x1800623aa  setnz   r8b
0x1800623ae  lea     rdx, pszSrc; "\\"
0x1800623b5  lea     rcx, [rsp+2D8h+lpFileName]; Src
0x1800623ba  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800623bf  mov     r8, rbx
0x1800623c2  sub     r8, rsi
0x1800623c5  sar     r8, 1
0x1800623c8  mov     rdx, rsi; void *
0x1800623cb  lea     rcx, [rsp+2D8h+lpFileName]; Src
0x1800623d0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800623d5  mov     esi, 2
0x1800623da  mov     r8d, esi
0x1800623dd  lea     rdx, asc_180083BDC; "*~"
0x1800623e4  lea     rcx, [rsp+2D8h+lpFileName]; Src
0x1800623e9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800623ee  cmp     [rbx], r15w
0x1800623f2  jnz     short loc_1800623F9
0x1800623f4  mov     r8, r15
0x1800623f7  jmp     short loc_180062406
0x1800623f9  mov     r8, rdi
0x1800623fc  inc     r8
0x1800623ff  cmp     [rbx+r8*2], r15w
0x180062404  jnz     short loc_1800623FC
0x180062406  mov     rdx, rbx; void *
0x180062409  lea     rcx, [rsp+2D8h+lpFileName]; Src
0x18006240e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180062413  xor     edx, edx; Val
0x180062415  mov     r8d, 250h; Size
0x18006241b  lea     rcx, [rsp+2D8h+FindFileData]; void *
0x180062420  call    memset_0
0x180062425  lea     rcx, [rsp+2D8h+lpFileName]
0x18006242a  cmp     [rsp+2D8h+var_280], 8
0x180062430  cmovnb  rcx, [rsp+2D8h+lpFileName]; lpFileName
0x180062436  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x18006243b  call    cs:__imp_FindFirstFileW
0x180062442  nop     dword ptr [rax+rax+00h]
0x180062447  mov     rbx, rax
0x18006244a  mov     [rsp+2D8h+var_2A0], rax
0x18006244f  cmp     rax, rdi
0x180062452  jnz     short loc_1800624C6
0x180062454  call    cs:__imp_GetLastError
0x18006245b  nop     dword ptr [rax+rax+00h]
0x180062460  cmp     eax, esi
0x180062462  jnz     short loc_180062484
0x180062464  cmp     [rsp+2D8h+var_280], 8
0x18006246a  jb      short loc_18006247D
0x18006246c  mov     rcx, [rsp+2D8h+lpFileName]
0x180062471  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180062478  nop     dword ptr [rax+rax+00h]
0x18006247d  xor     eax, eax
0x18006247f  jmp     loc_180062648
0x180062484  mov     rcx, [rsp+2D8h]; this
0x18006248c  lea     r9, aUnexpectedErro; "Unexpected error while enumerating pack"...
0x180062493  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18006249a  mov     edx, 0DAh; void *
0x18006249f  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800624a4  mov     ebx, eax
0x1800624a6  cmp     [rsp+2D8h+var_280], 8
0x1800624ac  jb      short loc_1800624BF
0x1800624ae  mov     rcx, [rsp+2D8h+lpFileName]
0x1800624b3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800624ba  nop     dword ptr [rax+rax+00h]
0x1800624bf  mov     eax, ebx
0x1800624c1  jmp     loc_180062648
0x1800624c6  test    byte ptr [rsp+2D8h+FindFileData.dwFileAttributes], 10h
0x1800624cb  jnz     short loc_1800624EA
0x1800624cd  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x1800624d2  mov     rcx, rbx; hFindFile
0x1800624d5  call    cs:__imp_FindNextFileW
0x1800624dc  nop     dword ptr [rax+rax+00h]
0x1800624e1  test    eax, eax
0x1800624e3  jnz     short loc_1800624C6
0x1800624e5  jmp     loc_1800625BC
0x1800624ea  lea     rcx, [r14+38h]; void *
0x1800624ee  cmp     [rsp+2D8h+FindFileData.cFileName], r15w
0x1800624f7  jnz     short loc_1800624FE
0x1800624f9  mov     rdi, r15
0x1800624fc  jmp     short loc_180062510
0x1800624fe  lea     rax, [rsp+2D8h+FindFileData.cFileName]
0x180062506  inc     rdi
0x180062509  cmp     [rax+rdi*2], r15w
0x18006250e  jnz     short loc_180062506
0x180062510  mov     r8, rdi
0x180062513  lea     rdx, [rsp+2D8h+FindFileData.cFileName]; Src
0x18006251b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180062520  mov     [rsp+2D8h+pv], r15
0x180062525  lea     r8, [rsp+2D8h+FindFileData.cFileName]
0x18006252d  lea     rdx, aFoundExistingF; "Found existing full bundle %s"
0x180062534  lea     rcx, [rsp+2D8h+pv]
0x180062539  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18006253e  mov     rcx, [rsp+2D8h]; this
0x180062546  test    eax, eax
0x180062548  jns     short loc_18006255E
0x18006254a  mov     r9d, eax; char *
0x18006254d  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180062554  mov     edx, 0E9h; void *
0x180062559  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006255e  mov     [rsp+2D8h+var_2B0], r15d
0x180062563  mov     dword ptr [rsp+2D8h+var_2B8], esi; int
0x180062567  mov     esi, 0ECh
0x18006256c  mov     r9d, esi
0x18006256f  lea     r8, aMsixpackagePro_18; "MsixPackage::Provisioning::Library::Pac"...
0x180062576  lea     rdx, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18006257d  mov     rdi, [rsp+2D8h+pv]
0x180062582  mov     rcx, rdi
0x180062585  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18006258a  mov     rcx, [rsp+2D8h]; this
0x180062592  test    eax, eax
0x180062594  jns     short loc_1800625A8
0x180062596  mov     r9d, eax; char *
0x180062599  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800625a0  mov     edx, esi; void *
0x1800625a2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800625a7  nop
0x1800625a8  test    rdi, rdi
0x1800625ab  jz      short loc_1800625BC
0x1800625ad  mov     rcx, rdi; pv
0x1800625b0  call    cs:__imp_CoTaskMemFree
0x1800625b7  nop     dword ptr [rax+rax+00h]
0x1800625bc  call    cs:__imp_GetLastError
0x1800625c3  nop     dword ptr [rax+rax+00h]
0x1800625c8  mov     edi, eax
0x1800625ca  cmp     eax, 12h
0x1800625cd  jz      short loc_18006260E
0x1800625cf  test    eax, eax
0x1800625d1  jle     short loc_1800625DC
0x1800625d3  movzx   edi, ax
0x1800625d6  or      edi, 80070000h
0x1800625dc  test    rbx, rbx
0x1800625df  jz      short loc_1800625F1
0x1800625e1  mov     rcx, rbx; hFindFile
0x1800625e4  call    cs:__imp_FindClose
0x1800625eb  nop     dword ptr [rax+rax+00h]
0x1800625f0  nop
0x1800625f1  cmp     [rsp+2D8h+var_280], 8
0x1800625f7  jb      short loc_18006260A
0x1800625f9  mov     rcx, [rsp+2D8h+lpFileName]
0x1800625fe  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180062605  nop     dword ptr [rax+rax+00h]
0x18006260a  mov     eax, edi
0x18006260c  jmp     short loc_180062648
0x18006260e  test    rbx, rbx
0x180062611  jz      short loc_180062623
0x180062613  mov     rcx, rbx; hFindFile
0x180062616  call    cs:__imp_FindClose
0x18006261d  nop     dword ptr [rax+rax+00h]
0x180062622  nop
0x180062623  cmp     [rsp+2D8h+var_280], 8
0x180062629  jb      short loc_18006263C
0x18006262b  mov     rcx, [rsp+2D8h+lpFileName]
0x180062630  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180062637  nop     dword ptr [rax+rax+00h]
0x18006263c  xor     eax, eax
0x18006263e  jmp     short loc_180062648
0x180062640  xor     eax, eax
0x180062642  jmp     short loc_180062648
0x180062644  mov     eax, dword ptr [rsp+2D8h+pv]
0x180062648  mov     rcx, [rsp+2D8h+var_28]
0x180062650  xor     rcx, rsp; StackCookie
0x180062653  call    __security_check_cookie
0x180062658  lea     r11, [rsp+2D8h+var_18]
0x180062660  mov     rbx, [r11+30h]
0x180062664  mov     rsi, [r11+38h]
0x180062668  mov     rsp, r11
0x18006266b  pop     r15
0x18006266d  pop     r14
0x18006266f  pop     rdi
0x180062670  retn
```
