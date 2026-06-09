# Windows::Internal::Flighting::ClientAttributes::PopulateDefaultCtacJson(void)

- ea: `0x180038e28`
- end: `0x1800390fa`
- name: `?PopulateDefaultCtacJson@ClientAttributes@Flighting@Internal@Windows@@CAJXZ`
- size: `722`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180037d20`

## callees

- `0x180004b80`
- `0x180005538`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x180010e9c`
- `0x18001c6f4`
- `0x18002275c`
- `0x180022c0c`
- `0x1800240f0`
- `0x180034a5c`
- `0x180034ebc`
- `0x180034f90`
- `0x1800379f8`
- `0x180038e28`
- `0x180039f30`
- `0x18003a4f4`
- `0x18003a86c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180038f05`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180038f05`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180038f79`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180038f79`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038ec5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038ec5`
- `msvcp_win!??0?$codecvt@GDU_Mbstatet@@@std@@QEAA@_K@Z` at `0x180039028`
- `msvcp_win!??0?$codecvt@GDU_Mbstatet@@@std@@QEAA@_K@Z` at `0x180039028`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180038fd6`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180038fd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038f21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038f21`

## string_xrefs

- `0x180038e8c`: `onecore\base\flighting\flightsettings\broker\libs\ctac\clientattributes.cpp`
- `0x180038edd`: `onecore\base\flighting\flightsettings\broker\libs\ctac\clientattributes.cpp`
- `0x180038f4e`: `onecore\base\flighting\flightsettings\broker\libs\ctac\clientattributes.cpp`
- `0x180038f8b`: `onecore\base\flighting\flightsettings\broker\libs\ctac\clientattributes.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 Windows::Internal::Flighting::ClientAttributes::PopulateDefaultCtacJson(void)
{
  int CtacJsonPath; // eax
  unsigned int LastError; // ebx
  HANDLE FileW; // rax
  const char *v3; // r9
  void *v4; // rbx
  __int64 v5; // rdx
  DWORD LowPart; // esi
  LPVOID v7; // rax
  char *v8; // rdi
  const char *v10; // r9
  __int64 result; // rax
  _QWORD *v12; // rbx
  __int64 v13; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-138h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-138h]
  LPVOID lpBuffer; // [rsp+40h] [rbp-118h] BYREF
  HANDLE v17; // [rsp+48h] [rbp-110h] BYREF
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp-108h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+58h] [rbp-100h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp-F8h] BYREF
  __int64 v21; // [rsp+68h] [rbp-F0h]
  __int64 v22; // [rsp+70h] [rbp-E8h]
  _QWORD *v23; // [rsp+78h] [rbp-E0h]
  _QWORD v24[4]; // [rsp+80h] [rbp-D8h] BYREF
  _BYTE v25[32]; // [rsp+A0h] [rbp-B8h] BYREF
  _BYTE v26[40]; // [rsp+C0h] [rbp-98h] BYREF
  __int16 v27; // [rsp+E8h] [rbp-70h]
  char v28; // [rsp+EAh] [rbp-6Eh]
  _BYTE v29[32]; // [rsp+100h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  lpFileName = 0;
  v21 = 0;
  v22 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpFileName);
  v21 = -1;
  v22 = -1;
  CtacJsonPath = Windows::Internal::Flighting::ClientAttributes::GetCtacJsonPath((unsigned __int16 **)&lpFileName);
  LastError = CtacJsonPath;
  if ( CtacJsonPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\clientattributes.cpp",
      (const char *)(unsigned int)CtacJsonPath,
      dwCreationDisposition);
LABEL_14:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpFileName);
    return LastError;
  }
  FileW = CreateFileW(lpFileName, 0x120089u, 1u, 0, 3u, 0, 0);
  v4 = FileW;
  v17 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v5 = 592;
LABEL_5:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\clientattributes.cpp",
                  v3);
LABEL_13:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
    goto LABEL_14;
  }
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    v5 = 595;
    goto LABEL_5;
  }
  LowPart = FileSize.LowPart;
  lpBuffer = 0;
  v7 = CoTaskMemAlloc(FileSize.LowPart);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &lpBuffer,
    v7);
  v8 = (char *)lpBuffer;
  if ( !lpBuffer )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x258,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\clientattributes.cpp",
      (const char *)0x8007000ELL,
      dwCreationDispositiona);
LABEL_12:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpBuffer);
    goto LABEL_13;
  }
  NumberOfBytesRead = 0;
  if ( !ReadFile(v4, lpBuffer, LowPart, &NumberOfBytesRead, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x25F,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\clientattributes.cpp",
                  v10);
    goto LABEL_12;
  }
  try
  {
    v24[0] = &std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
    v24[3] = std::locale::_Init(1);
    std::string::string(v25);
    std::wstring::wstring(v26);
    v27 = 0;
    v28 = 0;
    v12 = operator new(0x40u);
    v23 = v12;
    std::codecvt<unsigned short,char,_Mbstatet>::codecvt<unsigned short,char,_Mbstatet>(v12, 0);
    *v12 = &std::codecvt_utf8<unsigned short,1114111,0>::`vftable';
    std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::_Init(
      v24,
      v12);
    v13 = std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
            v24,
            v29,
            v8,
            &v8[FileSize.QuadPart]);
    std::wstring::operator=(Windows::Internal::Flighting::ClientAttributes::defaultCtacJson, v13);
    std::wstring::_Tidy_deallocate(v29);
    std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v24);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpBuffer);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpFileName);
    result = 0;
  }
  catch ( ... )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpBuffer);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpFileName);
    return 2147942413LL;
  }
  return result;
}

```

## disassembly

```asm
0x180038e28  push    rbx
0x180038e2a  push    rsi
0x180038e2b  push    rdi
0x180038e2c  push    r14
0x180038e2e  sub     rsp, 138h
0x180038e35  mov     rax, cs:__security_cookie
0x180038e3c  xor     rax, rsp
0x180038e3f  mov     [rsp+158h+var_38], rax
0x180038e47  xor     r14d, r14d
0x180038e4a  mov     [rsp+158h+lpFileName], r14
0x180038e4f  mov     [rsp+158h+var_F0], r14
0x180038e54  mov     [rsp+158h+var_E8], r14
0x180038e59  lea     rcx, [rsp+158h+lpFileName]
0x180038e5e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180038e63  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180038e67  mov     [rsp+158h+var_F0], rdi
0x180038e6c  mov     [rsp+158h+var_E8], rdi
0x180038e71  lea     rcx, [rsp+158h+lpFileName]; unsigned __int16 **
0x180038e76  call    ?GetCtacJsonPath@ClientAttributes@Flighting@Internal@Windows@@CAJPEAPEAG@Z; Windows::Internal::Flighting::ClientAttributes::GetCtacJsonPath(ushort * *)
0x180038e7b  mov     ebx, eax
0x180038e7d  test    eax, eax
0x180038e7f  jns     short loc_180038EA2
0x180038e81  mov     rcx, [rsp+158h]; this
0x180038e89  mov     r9d, eax; char *
0x180038e8c  lea     r8, aOnecoreBaseFli_48; "onecore\\base\\flighting\\flightsetting"...
0x180038e93  mov     edx, 246h; void *
0x180038e98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038e9d  jmp     loc_180038FB4
0x180038ea2  mov     [rsp+158h+hTemplateFile], r14; hTemplateFile
0x180038ea7  mov     [rsp+158h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x180038eac  mov     [rsp+158h+dwCreationDisposition], 3; int
0x180038eb4  xor     r9d, r9d; lpSecurityAttributes
0x180038eb7  mov     edx, 120089h; dwDesiredAccess
0x180038ebc  lea     r8d, [r9+1]; dwShareMode
0x180038ec0  mov     rcx, [rsp+158h+lpFileName]; lpFileName
0x180038ec5  call    cs:__imp_CreateFileW
0x180038ecb  mov     rbx, rax
0x180038ece  mov     [rsp+158h+var_110], rax
0x180038ed3  cmp     rax, rdi
0x180038ed6  jnz     short loc_180038EF8
0x180038ed8  mov     edx, 250h; void *
0x180038edd  lea     r8, aOnecoreBaseFli_48; "onecore\\base\\flighting\\flightsetting"...
0x180038ee4  mov     rcx, [rsp+158h]; this
0x180038eec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180038ef1  mov     ebx, eax
0x180038ef3  jmp     loc_180038FA9
0x180038ef8  mov     qword ptr [rsp+158h+FileSize], r14
0x180038efd  lea     rdx, [rsp+158h+FileSize]; lpFileSize
0x180038f02  mov     rcx, rbx; hFile
0x180038f05  call    cs:__imp_GetFileSizeEx
0x180038f0b  test    eax, eax
0x180038f0d  jnz     short loc_180038F16
0x180038f0f  mov     edx, 253h
0x180038f14  jmp     short loc_180038EDD
0x180038f16  mov     esi, dword ptr [rsp+158h+FileSize]
0x180038f1a  mov     [rsp+158h+lpBuffer], r14
0x180038f1f  mov     ecx, esi; cb
0x180038f21  call    cs:__imp_CoTaskMemAlloc
0x180038f27  mov     rdx, rax
0x180038f2a  lea     rcx, [rsp+158h+lpBuffer]
0x180038f2f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180038f34  mov     rdi, [rsp+158h+lpBuffer]
0x180038f39  test    rdi, rdi
0x180038f3c  jnz     short loc_180038F61
0x180038f3e  mov     rcx, [rsp+158h]; this
0x180038f46  mov     ebx, 8007000Eh
0x180038f4b  mov     r9d, ebx; char *
0x180038f4e  lea     r8, aOnecoreBaseFli_48; "onecore\\base\\flighting\\flightsetting"...
0x180038f55  mov     edx, 258h; void *
0x180038f5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038f5f  jmp     short loc_180038F9E
0x180038f61  mov     [rsp+158h+NumberOfBytesRead], r14d
0x180038f66  mov     qword ptr [rsp+158h+dwCreationDisposition], r14; lpOverlapped
0x180038f6b  lea     r9, [rsp+158h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180038f70  mov     r8d, esi; nNumberOfBytesToRead
0x180038f73  mov     rdx, rdi; lpBuffer
0x180038f76  mov     rcx, rbx; hFile
0x180038f79  call    cs:__imp_ReadFile
0x180038f7f  test    eax, eax
0x180038f81  jnz     short loc_180038FC5
0x180038f83  mov     rcx, [rsp+158h]; this
0x180038f8b  lea     r8, aOnecoreBaseFli_48; "onecore\\base\\flighting\\flightsetting"...
0x180038f92  mov     edx, 25Fh; void *
0x180038f97  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180038f9c  mov     ebx, eax
0x180038f9e  lea     rcx, [rsp+158h+lpBuffer]
0x180038fa3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180038fa8  nop
0x180038fa9  lea     rcx, [rsp+158h+var_110]
0x180038fae  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180038fb3  nop
0x180038fb4  lea     rcx, [rsp+158h+lpFileName]
0x180038fb9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180038fbe  mov     eax, ebx
0x180038fc0  jmp     loc_1800390DD
0x180038fc5  lea     rax, ??_7?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x180038fcc  mov     [rsp+158h+var_D8], rax
0x180038fd4  mov     cl, 1
0x180038fd6  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180038fdc  mov     [rsp+158h+var_C0], rax
0x180038fe4  lea     rcx, [rsp+158h+var_B8]
0x180038fec  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180038ff1  nop
0x180038ff2  lea     rcx, [rsp+158h+var_98]
0x180038ffa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180038fff  nop
0x180039000  mov     [rsp+158h+var_70], r14w
0x180039009  mov     [rsp+158h+var_6E], r14b
0x180039011  mov     ecx, 40h ; '@'; Size
0x180039016  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003901b  mov     rbx, rax
0x18003901e  mov     [rsp+158h+var_E0], rax
0x180039023  xor     edx, edx
0x180039025  mov     rcx, rax
0x180039028  call    cs:__imp_??0?$codecvt@GDU_Mbstatet@@@std@@QEAA@_K@Z; std::codecvt<ushort,char,_Mbstatet>::codecvt<ushort,char,_Mbstatet>(unsigned __int64)
0x18003902e  lea     rax, ??_7?$codecvt_utf8@G$0BAPPPP@$0A@@std@@6B@; const std::codecvt_utf8<ushort,1114111,0>::`vftable'
0x180039035  mov     [rbx], rax
0x180039038  mov     rdx, rbx
0x18003903b  lea     rcx, [rsp+158h+var_D8]
0x180039043  call    ?_Init@?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@AEAAXPEBV?$codecvt_utf8@G$0BAPPPP@$0A@@2@@Z; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::_Init(std::codecvt_utf8<ushort,1114111,0> const *)
0x180039048  nop
0x180039049  mov     r9, qword ptr [rsp+158h+FileSize]
0x18003904e  add     r9, rdi
0x180039051  mov     r8, rdi
0x180039054  lea     rdx, [rsp+158h+var_58]
0x18003905c  lea     rcx, [rsp+158h+var_D8]
0x180039064  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x180039069  mov     rdx, rax
0x18003906c  lea     rcx, ?defaultCtacJson@ClientAttributes@Flighting@Internal@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Windows::Internal::Flighting::ClientAttributes::defaultCtacJson
0x180039073  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180039078  lea     rcx, [rsp+158h+var_58]
0x180039080  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039085  nop
0x180039086  lea     rcx, [rsp+158h+var_D8]
0x18003908e  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180039093  nop
0x180039094  lea     rcx, [rsp+158h+lpBuffer]
0x180039099  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003909e  nop
0x18003909f  lea     rcx, [rsp+158h+var_110]
0x1800390a4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800390a9  nop
0x1800390aa  lea     rcx, [rsp+158h+lpFileName]
0x1800390af  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800390b4  xor     eax, eax
0x1800390b6  jmp     short loc_1800390DD
0x1800390b8  lea     rcx, [rsp+158h+lpBuffer]
0x1800390bd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800390c2  nop
0x1800390c3  lea     rcx, [rsp+158h+var_110]
0x1800390c8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800390cd  nop
0x1800390ce  lea     rcx, [rsp+158h+lpFileName]
0x1800390d3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800390d8  mov     eax, 8007000Dh
0x1800390dd  mov     rcx, [rsp+158h+var_38]
0x1800390e5  xor     rcx, rsp; StackCookie
0x1800390e8  call    __security_check_cookie
0x1800390ed  add     rsp, 138h
0x1800390f4  pop     r14
0x1800390f6  pop     rdi
0x1800390f7  pop     rsi
0x1800390f8  pop     rbx
0x1800390f9  retn
```
