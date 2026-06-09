# FirstSync::DisplayToast(FirstSync::ToastType)

- ea: `0x1800a5c50`
- end: `0x1800a5edb`
- name: `?DisplayToast@FirstSync@@YAJW4ToastType@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a1970`

## callees

- `0x18000a5a4`
- `0x18000a5c4`
- `0x1800179f8`
- `0x180017a1c`
- `0x180097928`
- `0x1800a5c50`

## import_xrefs

- `DMCmnUtils!DmRaiseToastNotification` at `0x1800a5e91`
- `DMCmnUtils!DmRaiseToastNotification` at `0x1800a5e91`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a5c70`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a5c70`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a5ce5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a5d0d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a5d39`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a5d76`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a5d9e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a5dc6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a5ce5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a5d0d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a5d39`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a5d76`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a5d9e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a5dc6`

## string_xrefs

- `0x1800a5c69`: `DMAppsRes.dll`
- `0x1800a5e75`: `protocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FirstSync::DisplayToast(int a1)
{
  HMODULE Library; // rax
  const char *v3; // r9
  HINSTANCE v4; // rbx
  __int64 v5; // rdx
  int v6; // edi
  unsigned int LastError; // ebx
  int StringW; // edi
  int v9; // esi
  const unsigned __int16 *v10; // rbx
  __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  int v15; // [rsp+20h] [rbp-20h]
  const unsigned __int16 *v16; // [rsp+30h] [rbp-10h] BYREF
  HMODULE v17; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  const unsigned __int16 *v19; // [rsp+68h] [rbp+28h] BYREF
  __int64 Buffer; // [rsp+70h] [rbp+30h] BYREF
  __int64 v21; // [rsp+78h] [rbp+38h] BYREF

  Library = LoadLibraryExW(L"DMAppsRes.dll", 0, 0x800u);
  v4 = Library;
  v17 = Library;
  if ( !Library )
  {
    v5 = 892;
LABEL_13:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
                  v3);
    goto LABEL_29;
  }
  Buffer = 0;
  v21 = 0;
  if ( a1 )
  {
    v6 = a1 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
      {
        LastError = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x39F,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
          (const char *)0x80070057LL,
          v15);
        goto LABEL_29;
      }
      StringW = LoadStringW(Library, 0x65F8u, (LPWSTR)&Buffer, 0);
      if ( !StringW )
      {
        v5 = 920;
        goto LABEL_13;
      }
      v9 = LoadStringW(v4, 0x65F7u, (LPWSTR)&v21, 0);
      if ( !v9 )
      {
        v5 = 923;
        goto LABEL_13;
      }
    }
    else
    {
      StringW = LoadStringW(Library, 0x65F1u, (LPWSTR)&Buffer, 0);
      if ( !StringW )
      {
        v5 = 904;
        goto LABEL_13;
      }
      v9 = LoadStringW(v4, 0x65F0u, (LPWSTR)&v21, 0);
      if ( !v9 )
      {
        v5 = 907;
        goto LABEL_13;
      }
    }
  }
  else
  {
    StringW = LoadStringW(Library, 0x65F2u, (LPWSTR)&Buffer, 0);
    if ( !StringW )
    {
      v5 = 912;
      goto LABEL_13;
    }
    v9 = LoadStringW(v4, 0x65F6u, (LPWSTR)&v21, 0);
    if ( !v9 )
    {
      v5 = 915;
      goto LABEL_13;
    }
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v19,
    Buffer,
    StringW);
  v10 = v19;
  if ( v19 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v16,
      v21,
      v9);
    if ( v16 )
    {
      v13 = DmRaiseToastNotification(
              L"Windows.SystemToast.DeviceManagement",
              L"FirstSyncStatus",
              L"ms-settings:workplace",
              L"protocol",
              v16,
              v10);
      LastError = v13;
      if ( v13 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
        LastError = 0;
        goto LABEL_29;
      }
      v11 = (unsigned int)v13;
      v12 = 936;
    }
    else
    {
      LastError = -2147024882;
      v11 = 2147942414LL;
      v12 = 934;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)v11,
      v15);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
  }
  else
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A3,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)0x8007000ELL,
      v15);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
LABEL_29:
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v17);
  return LastError;
}

```

## disassembly

```asm
0x1800a5c50  mov     [rsp-18h+arg_0], rbx
0x1800a5c55  push    rbp
0x1800a5c56  push    rsi
0x1800a5c57  push    rdi
0x1800a5c58  mov     rbp, rsp
0x1800a5c5b  sub     rsp, 40h
0x1800a5c5f  mov     edi, ecx
0x1800a5c61  xor     edx, edx; hFile
0x1800a5c63  mov     r8d, 800h; dwFlags
0x1800a5c69  lea     rcx, LibFileName; "DMAppsRes.dll"
0x1800a5c70  call    cs:__imp_LoadLibraryExW
0x1800a5c77  nop     dword ptr [rax+rax+00h]
0x1800a5c7c  mov     rbx, rax
0x1800a5c7f  mov     [rbp+var_8], rax
0x1800a5c83  test    rax, rax
0x1800a5c86  jnz     short loc_1800A5C92
0x1800a5c88  mov     edx, 37Ch
0x1800a5c8d  jmp     loc_1800A5D50
0x1800a5c92  mov     [rbp+Buffer], 0
0x1800a5c9a  mov     [rbp+arg_18], 0
0x1800a5ca2  test    edi, edi
0x1800a5ca4  jz      loc_1800A5D8F
0x1800a5caa  sub     edi, 1
0x1800a5cad  jz      short loc_1800A5D2A
0x1800a5caf  cmp     edi, 1
0x1800a5cb2  jz      short loc_1800A5CD6
0x1800a5cb4  mov     rcx, [rbp+18h]; this
0x1800a5cb8  mov     ebx, 80070057h
0x1800a5cbd  mov     r9d, ebx; char *
0x1800a5cc0  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a5cc7  mov     edx, 39Fh; void *
0x1800a5ccc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5cd1  jmp     loc_1800A5EC2
0x1800a5cd6  xor     r9d, r9d; cchBufferMax
0x1800a5cd9  lea     r8, [rbp+Buffer]; lpBuffer
0x1800a5cdd  mov     edx, 65F8h; uID
0x1800a5ce2  mov     rcx, rbx; hInstance
0x1800a5ce5  call    cs:__imp_LoadStringW
0x1800a5cec  nop     dword ptr [rax+rax+00h]
0x1800a5cf1  mov     edi, eax
0x1800a5cf3  test    eax, eax
0x1800a5cf5  jnz     short loc_1800A5CFE
0x1800a5cf7  mov     edx, 398h
0x1800a5cfc  jmp     short loc_1800A5D50
0x1800a5cfe  xor     r9d, r9d; cchBufferMax
0x1800a5d01  lea     r8, [rbp+arg_18]; lpBuffer
0x1800a5d05  mov     edx, 65F7h; uID
0x1800a5d0a  mov     rcx, rbx; hInstance
0x1800a5d0d  call    cs:__imp_LoadStringW
0x1800a5d14  nop     dword ptr [rax+rax+00h]
0x1800a5d19  mov     esi, eax
0x1800a5d1b  test    eax, eax
0x1800a5d1d  jnz     loc_1800A5DE2
0x1800a5d23  mov     edx, 39Bh
0x1800a5d28  jmp     short loc_1800A5D50
0x1800a5d2a  xor     r9d, r9d; cchBufferMax
0x1800a5d2d  lea     r8, [rbp+Buffer]; lpBuffer
0x1800a5d31  mov     edx, 65F1h; uID
0x1800a5d36  mov     rcx, rbx; hInstance
0x1800a5d39  call    cs:__imp_LoadStringW
0x1800a5d40  nop     dword ptr [rax+rax+00h]
0x1800a5d45  mov     edi, eax
0x1800a5d47  test    eax, eax
0x1800a5d49  jnz     short loc_1800A5D67
0x1800a5d4b  mov     edx, 388h; void *
0x1800a5d50  mov     rcx, [rbp+18h]; this
0x1800a5d54  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a5d5b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a5d60  mov     ebx, eax
0x1800a5d62  jmp     loc_1800A5EC2
0x1800a5d67  xor     r9d, r9d; cchBufferMax
0x1800a5d6a  lea     r8, [rbp+arg_18]; lpBuffer
0x1800a5d6e  mov     edx, 65F0h; uID
0x1800a5d73  mov     rcx, rbx; hInstance
0x1800a5d76  call    cs:__imp_LoadStringW
0x1800a5d7d  nop     dword ptr [rax+rax+00h]
0x1800a5d82  mov     esi, eax
0x1800a5d84  test    eax, eax
0x1800a5d86  jnz     short loc_1800A5DE2
0x1800a5d88  mov     edx, 38Bh
0x1800a5d8d  jmp     short loc_1800A5D50
0x1800a5d8f  xor     r9d, r9d; cchBufferMax
0x1800a5d92  lea     r8, [rbp+Buffer]; lpBuffer
0x1800a5d96  mov     edx, 65F2h; uID
0x1800a5d9b  mov     rcx, rbx; hInstance
0x1800a5d9e  call    cs:__imp_LoadStringW
0x1800a5da5  nop     dword ptr [rax+rax+00h]
0x1800a5daa  mov     edi, eax
0x1800a5dac  test    eax, eax
0x1800a5dae  jnz     short loc_1800A5DB7
0x1800a5db0  mov     edx, 390h
0x1800a5db5  jmp     short loc_1800A5D50
0x1800a5db7  xor     r9d, r9d; cchBufferMax
0x1800a5dba  lea     r8, [rbp+arg_18]; lpBuffer
0x1800a5dbe  mov     edx, 65F6h; uID
0x1800a5dc3  mov     rcx, rbx; hInstance
0x1800a5dc6  call    cs:__imp_LoadStringW
0x1800a5dcd  nop     dword ptr [rax+rax+00h]
0x1800a5dd2  mov     esi, eax
0x1800a5dd4  test    eax, eax
0x1800a5dd6  jnz     short loc_1800A5DE2
0x1800a5dd8  mov     edx, 393h
0x1800a5ddd  jmp     loc_1800A5D50
0x1800a5de2  movsxd  r8, edi
0x1800a5de5  mov     rdx, [rbp+Buffer]
0x1800a5de9  lea     rcx, [rbp+arg_8]
0x1800a5ded  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a5df2  nop
0x1800a5df3  mov     rbx, [rbp+arg_8]
0x1800a5df7  test    rbx, rbx
0x1800a5dfa  jnz     short loc_1800A5E28
0x1800a5dfc  mov     rcx, [rbp+18h]; this
0x1800a5e00  mov     ebx, 8007000Eh
0x1800a5e05  mov     r9d, ebx; char *
0x1800a5e08  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a5e0f  mov     edx, 3A3h; void *
0x1800a5e14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5e19  nop
0x1800a5e1a  lea     rcx, [rbp+arg_8]
0x1800a5e1e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a5e23  jmp     loc_1800A5EC2
0x1800a5e28  movsxd  r8, esi
0x1800a5e2b  mov     rdx, [rbp+arg_18]
0x1800a5e2f  lea     rcx, [rbp+var_10]
0x1800a5e33  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a5e38  nop
0x1800a5e39  mov     rax, [rbp+var_10]
0x1800a5e3d  test    rax, rax
0x1800a5e40  jnz     short loc_1800A5E6B
0x1800a5e42  mov     ebx, 8007000Eh
0x1800a5e47  mov     r9d, ebx; char *
0x1800a5e4a  mov     edx, 3A6h; void *
0x1800a5e4f  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a5e56  mov     rcx, [rbp+18h]; this
0x1800a5e5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5e5f  nop
0x1800a5e60  lea     rcx, [rbp+var_10]
0x1800a5e64  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a5e69  jmp     short loc_1800A5E1A
0x1800a5e6b  mov     [rsp+40h+var_18], rbx
0x1800a5e70  mov     [rsp+40h+var_20], rax
0x1800a5e75  lea     r9, aProtocol; "protocol"
0x1800a5e7c  lea     r8, aMsSettingsWork; "ms-settings:workplace"
0x1800a5e83  lea     rdx, aFirstsyncstatu; "FirstSyncStatus"
0x1800a5e8a  lea     rcx, aWindowsSystemt; "Windows.SystemToast.DeviceManagement"
0x1800a5e91  call    cs:__imp_?DmRaiseToastNotification@@YAJPEBG00000@Z; DmRaiseToastNotification(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800a5e98  nop     dword ptr [rax+rax+00h]
0x1800a5e9d  mov     ebx, eax
0x1800a5e9f  test    eax, eax
0x1800a5ea1  jns     short loc_1800A5EAD
0x1800a5ea3  mov     r9d, eax
0x1800a5ea6  mov     edx, 3A8h
0x1800a5eab  jmp     short loc_1800A5E4F
0x1800a5ead  lea     rcx, [rbp+var_10]
0x1800a5eb1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a5eb6  nop
0x1800a5eb7  lea     rcx, [rbp+arg_8]
0x1800a5ebb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a5ec0  xor     ebx, ebx
0x1800a5ec2  lea     rcx, [rbp+var_8]
0x1800a5ec6  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800a5ecb  mov     eax, ebx
0x1800a5ecd  mov     rbx, [rsp+40h+arg_0]
0x1800a5ed2  add     rsp, 40h
0x1800a5ed6  pop     rdi
0x1800a5ed7  pop     rsi
0x1800a5ed8  pop     rbp
0x1800a5ed9  retn
```
