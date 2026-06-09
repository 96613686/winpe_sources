# SystemSettings::WorkAccess::GetDiagnosticsFolderPath(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180043030`
- end: `0x1800431f1`
- name: `?GetDiagnosticsFolderPath@WorkAccess@SystemSettings@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(PCWSTR pszMore, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800297d0`
- `0x18003a340`

## callees

- `0x180002a60`
- `0x180003534`
- `0x1800096ec`
- `0x180009e68`
- `0x1800236d8`
- `0x180029708`
- `0x18002a260`
- `0x180043030`
- `0x1800433e8`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18004317e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18004317e`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800430f3`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800430f3`

## string_xrefs

- `0x1800430af`: `shellcommon\shell\settingshandlers\workaccess\lib\sharedhelpers.cpp`
- `0x18004310c`: `shellcommon\shell\settingshandlers\workaccess\lib\sharedhelpers.cpp`
- `0x180043145`: `shellcommon\shell\settingshandlers\workaccess\lib\sharedhelpers.cpp`
- `0x18004319c`: `shellcommon\shell\settingshandlers\workaccess\lib\sharedhelpers.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::GetDiagnosticsFolderPath(PCWSTR pszMore, __int64 a2)
{
  SystemSettings::WorkAccess *v4; // rcx
  int v5; // eax
  unsigned int v6; // edi
  HRESULT v8; // eax
  HRESULT v9; // ebx
  int v10; // eax
  HRESULT v11; // edi
  __int64 v12; // rdx
  PWSTR ppszPath[2]; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR pszPath; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v15[526]; // [rsp+32h] [rbp-CEh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  pszPath = 0;
  memset_0(v15, 0, 0x206u);
  if ( !SystemSettings::WorkAccess::IsDesktopSKU(v4) )
  {
    ppszPath[0] = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      ppszPath,
      0);
    v8 = SHGetKnownFolderPath(&FOLDERID_Profile, 0x4400u, 0, ppszPath);
    v9 = v8;
    if ( v8 >= 0 )
    {
      v10 = StringCchCopyW(&pszPath, 0x104u, ppszPath[0]);
      v11 = v10;
      if ( v10 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(ppszPath);
        goto LABEL_11;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\sharedhelpers.cpp",
        (const char *)(unsigned int)v10,
        (int)ppszPath[0]);
      v9 = v11;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\sharedhelpers.cpp",
        (const char *)(unsigned int)v8,
        (int)ppszPath[0]);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(ppszPath);
    return (unsigned int)v9;
  }
  v5 = StringCchCopyW(&pszPath, 0x104u, L"%PUBLIC%");
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\sharedhelpers.cpp",
      (const char *)(unsigned int)v5,
      (int)ppszPath[0]);
    return v6;
  }
LABEL_11:
  v9 = PathCchAppend(&pszPath, 0x104u, pszMore);
  if ( v9 < 0 )
  {
    v12 = 113;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\sharedhelpers.cpp",
      (const char *)(unsigned int)v9,
      (int)ppszPath[0]);
    return (unsigned int)v9;
  }
  v9 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
         &pszPath,
         a2);
  if ( v9 < 0 )
  {
    v12 = 116;
    goto LABEL_13;
  }
  return 0;
}

```

## disassembly

```asm
0x180043030  mov     [rsp-8+arg_10], rbx
0x180043035  mov     [rsp-8+arg_18], rsi
0x18004303a  push    rbp
0x18004303b  push    rdi
0x18004303c  push    r14
0x18004303e  lea     rbp, [rsp-150h]
0x180043046  sub     rsp, 250h
0x18004304d  mov     rax, cs:__security_cookie
0x180043054  xor     rax, rsp
0x180043057  mov     [rbp+160h+var_20], rax
0x18004305e  mov     rsi, rdx
0x180043061  mov     r14, rcx
0x180043064  xor     eax, eax
0x180043066  lea     rcx, [rsp+260h+var_22E]; void *
0x18004306b  xor     edx, edx; Val
0x18004306d  mov     [rsp+260h+pszPath], ax
0x180043072  mov     r8d, 206h; Size
0x180043078  call    memset_0
0x18004307d  call    ?IsDesktopSKU@WorkAccess@SystemSettings@@YA_NXZ; SystemSettings::WorkAccess::IsDesktopSKU(void)
0x180043082  test    al, al
0x180043084  jz      short loc_1800430CA
0x180043086  mov     ebx, 104h
0x18004308b  lea     r8, aPublic; "%PUBLIC%"
0x180043092  mov     edx, ebx; unsigned __int64
0x180043094  lea     rcx, [rsp+260h+pszPath]; unsigned __int16 *
0x180043099  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004309e  mov     edi, eax
0x1800430a0  test    eax, eax
0x1800430a2  jns     loc_180043173
0x1800430a8  mov     rcx, [rbp+168h]; this
0x1800430af  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\settingshandlers\\w"...
0x1800430b6  mov     r9d, eax; char *
0x1800430b9  mov     edx, 65h ; 'e'; void *
0x1800430be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800430c3  mov     eax, edi
0x1800430c5  jmp     loc_1800431C9
0x1800430ca  xor     edx, edx
0x1800430cc  mov     [rsp+260h+ppszPath], 0; int
0x1800430d5  lea     rcx, [rsp+260h+ppszPath]
0x1800430da  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800430df  lea     r9, [rsp+260h+ppszPath]; ppszPath
0x1800430e4  xor     r8d, r8d; hToken
0x1800430e7  mov     edx, 4400h; dwFlags
0x1800430ec  lea     rcx, FOLDERID_Profile; rfid
0x1800430f3  call    cs:__imp_SHGetKnownFolderPath
0x1800430fa  nop     dword ptr [rax+rax+00h]
0x1800430ff  mov     ebx, eax
0x180043101  test    eax, eax
0x180043103  jns     short loc_180043122
0x180043105  mov     rcx, [rbp+168h]; this
0x18004310c  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\settingshandlers\\w"...
0x180043113  mov     r9d, eax; char *
0x180043116  mov     edx, 6Ch ; 'l'; void *
0x18004311b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043120  jmp     short loc_18004315B
0x180043122  mov     r8, [rsp+260h+ppszPath]; unsigned __int16 *
0x180043127  lea     rcx, [rsp+260h+pszPath]; unsigned __int16 *
0x18004312c  mov     ebx, 104h
0x180043131  mov     edx, ebx; unsigned __int64
0x180043133  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180043138  mov     edi, eax
0x18004313a  test    eax, eax
0x18004313c  jns     short loc_180043169
0x18004313e  mov     rcx, [rbp+168h]; this
0x180043145  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\settingshandlers\\w"...
0x18004314c  mov     r9d, eax; char *
0x18004314f  mov     edx, 6Dh ; 'm'; void *
0x180043154  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043159  mov     ebx, edi
0x18004315b  lea     rcx, [rsp+260h+ppszPath]
0x180043160  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180043165  mov     eax, ebx
0x180043167  jmp     short loc_1800431C9
0x180043169  lea     rcx, [rsp+260h+ppszPath]
0x18004316e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180043173  mov     r8, r14; pszMore
0x180043176  lea     rcx, [rsp+260h+pszPath]; pszPath
0x18004317b  mov     rdx, rbx; cchPath
0x18004317e  call    cs:__imp_PathCchAppend
0x180043185  nop     dword ptr [rax+rax+00h]
0x18004318a  mov     ebx, eax
0x18004318c  test    eax, eax
0x18004318e  jns     short loc_1800431AD
0x180043190  mov     edx, 71h ; 'q'; void *
0x180043195  mov     rcx, [rbp+168h]; this
0x18004319c  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\settingshandlers\\w"...
0x1800431a3  mov     r9d, ebx; char *
0x1800431a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800431ab  jmp     short loc_180043165
0x1800431ad  mov     rdx, rsi
0x1800431b0  lea     rcx, [rsp+260h+pszPath]
0x1800431b5  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800431ba  mov     ebx, eax
0x1800431bc  test    eax, eax
0x1800431be  jns     short loc_1800431C7
0x1800431c0  mov     edx, 74h ; 't'
0x1800431c5  jmp     short loc_180043195
0x1800431c7  xor     eax, eax
0x1800431c9  mov     rcx, [rbp+160h+var_20]
0x1800431d0  xor     rcx, rsp; StackCookie
0x1800431d3  call    __security_check_cookie
0x1800431d8  lea     r11, [rsp+260h+var_10]
0x1800431e0  mov     rbx, [r11+30h]
0x1800431e4  mov     rsi, [r11+38h]
0x1800431e8  mov     rsp, r11
0x1800431eb  pop     r14
0x1800431ed  pop     rdi
0x1800431ee  pop     rbp
0x1800431ef  retn
```
