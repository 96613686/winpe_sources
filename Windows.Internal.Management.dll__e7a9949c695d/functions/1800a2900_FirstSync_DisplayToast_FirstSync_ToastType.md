# FirstSync::DisplayToast(FirstSync::ToastType)

- ea: `0x1800a2900`
- end: `0x1800a2b57`
- name: `?DisplayToast@FirstSync@@YAJW4ToastType@1@@Z`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009e96c`

## callees

- `0x18000a284`
- `0x18000a2a4`
- `0x180017204`
- `0x180017224`
- `0x180095004`
- `0x1800a2900`

## import_xrefs

- `DMCmnUtils!DmRaiseToastNotification` at `0x1800a2b14`
- `DMCmnUtils!DmRaiseToastNotification` at `0x1800a2b14`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a2920`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a2920`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a298f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a29b1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a29d7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a2a0e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a2a30`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a2a52`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a298f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a29b1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a29d7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a2a0e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a2a30`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a2a52`

## string_xrefs

- `0x1800a2919`: `DMAppsRes.dll`
- `0x1800a2af8`: `protocol`

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
  const char *v10; // r9
  const unsigned __int16 *v11; // rbx
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  int v16; // [rsp+20h] [rbp-20h]
  const unsigned __int16 *v17; // [rsp+30h] [rbp-10h] BYREF
  HMODULE v18; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  const unsigned __int16 *v20; // [rsp+68h] [rbp+28h] BYREF
  char *Buffer; // [rsp+70h] [rbp+30h] BYREF
  char *v22; // [rsp+78h] [rbp+38h] BYREF

  Library = LoadLibraryExW(L"DMAppsRes.dll", 0, 0x800u);
  v4 = Library;
  v18 = Library;
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
  v22 = 0;
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
          v16);
        goto LABEL_29;
      }
      StringW = LoadStringW(Library, 0x65F8u, (LPWSTR)&Buffer, 0);
      if ( !StringW )
      {
        v5 = 920;
        goto LABEL_13;
      }
      v9 = LoadStringW(v4, 0x65F7u, (LPWSTR)&v22, 0);
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
      v9 = LoadStringW(v4, 0x65F0u, (LPWSTR)&v22, 0);
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
    v9 = LoadStringW(v4, 0x65F6u, (LPWSTR)&v22, 0);
    if ( !v9 )
    {
      v5 = 915;
      goto LABEL_13;
    }
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v20,
    Buffer,
    StringW,
    v3);
  v11 = v20;
  if ( v20 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v17,
      v22,
      v9,
      v10);
    if ( v17 )
    {
      v14 = DmRaiseToastNotification(
              L"Windows.SystemToast.DeviceManagement",
              L"FirstSyncStatus",
              L"ms-settings:workplace",
              L"protocol",
              v17,
              v11);
      LastError = v14;
      if ( v14 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
        LastError = 0;
        goto LABEL_29;
      }
      v12 = (unsigned int)v14;
      v13 = 936;
    }
    else
    {
      LastError = -2147024882;
      v12 = 2147942414LL;
      v13 = 934;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)v12,
      v16);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
  }
  else
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A3,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)0x8007000ELL,
      v16);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
LABEL_29:
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v18);
  return LastError;
}

```

## disassembly

```asm
0x1800a2900  mov     [rsp-18h+arg_0], rbx
0x1800a2905  push    rbp
0x1800a2906  push    rsi
0x1800a2907  push    rdi
0x1800a2908  mov     rbp, rsp
0x1800a290b  sub     rsp, 40h
0x1800a290f  mov     edi, ecx
0x1800a2911  xor     edx, edx; hFile
0x1800a2913  mov     r8d, 800h; dwFlags
0x1800a2919  lea     rcx, LibFileName; "DMAppsRes.dll"
0x1800a2920  call    cs:__imp_LoadLibraryExW
0x1800a2926  mov     rbx, rax
0x1800a2929  mov     [rbp+var_8], rax
0x1800a292d  test    rax, rax
0x1800a2930  jnz     short loc_1800A293C
0x1800a2932  mov     edx, 37Ch
0x1800a2937  jmp     loc_1800A29E8
0x1800a293c  mov     [rbp+Buffer], 0
0x1800a2944  mov     [rbp+arg_18], 0
0x1800a294c  test    edi, edi
0x1800a294e  jz      loc_1800A2A21
0x1800a2954  sub     edi, 1
0x1800a2957  jz      short loc_1800A29C8
0x1800a2959  cmp     edi, 1
0x1800a295c  jz      short loc_1800A2980
0x1800a295e  mov     rcx, [rbp+18h]; this
0x1800a2962  mov     ebx, 80070057h
0x1800a2967  mov     r9d, ebx; char *
0x1800a296a  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a2971  mov     edx, 39Fh; void *
0x1800a2976  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a297b  jmp     loc_1800A2B3F
0x1800a2980  xor     r9d, r9d; cchBufferMax
0x1800a2983  lea     r8, [rbp+Buffer]; lpBuffer
0x1800a2987  mov     edx, 65F8h; uID
0x1800a298c  mov     rcx, rbx; hInstance
0x1800a298f  call    cs:__imp_LoadStringW
0x1800a2995  mov     edi, eax
0x1800a2997  test    eax, eax
0x1800a2999  jnz     short loc_1800A29A2
0x1800a299b  mov     edx, 398h
0x1800a29a0  jmp     short loc_1800A29E8
0x1800a29a2  xor     r9d, r9d; cchBufferMax
0x1800a29a5  lea     r8, [rbp+arg_18]; lpBuffer
0x1800a29a9  mov     edx, 65F7h; uID
0x1800a29ae  mov     rcx, rbx; hInstance
0x1800a29b1  call    cs:__imp_LoadStringW
0x1800a29b7  mov     esi, eax
0x1800a29b9  test    eax, eax
0x1800a29bb  jnz     loc_1800A2A65
0x1800a29c1  mov     edx, 39Bh
0x1800a29c6  jmp     short loc_1800A29E8
0x1800a29c8  xor     r9d, r9d; cchBufferMax
0x1800a29cb  lea     r8, [rbp+Buffer]; lpBuffer
0x1800a29cf  mov     edx, 65F1h; uID
0x1800a29d4  mov     rcx, rbx; hInstance
0x1800a29d7  call    cs:__imp_LoadStringW
0x1800a29dd  mov     edi, eax
0x1800a29df  test    eax, eax
0x1800a29e1  jnz     short loc_1800A29FF
0x1800a29e3  mov     edx, 388h; void *
0x1800a29e8  mov     rcx, [rbp+18h]; this
0x1800a29ec  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a29f3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a29f8  mov     ebx, eax
0x1800a29fa  jmp     loc_1800A2B3F
0x1800a29ff  xor     r9d, r9d; cchBufferMax
0x1800a2a02  lea     r8, [rbp+arg_18]; lpBuffer
0x1800a2a06  mov     edx, 65F0h; uID
0x1800a2a0b  mov     rcx, rbx; hInstance
0x1800a2a0e  call    cs:__imp_LoadStringW
0x1800a2a14  mov     esi, eax
0x1800a2a16  test    eax, eax
0x1800a2a18  jnz     short loc_1800A2A65
0x1800a2a1a  mov     edx, 38Bh
0x1800a2a1f  jmp     short loc_1800A29E8
0x1800a2a21  xor     r9d, r9d; cchBufferMax
0x1800a2a24  lea     r8, [rbp+Buffer]; lpBuffer
0x1800a2a28  mov     edx, 65F2h; uID
0x1800a2a2d  mov     rcx, rbx; hInstance
0x1800a2a30  call    cs:__imp_LoadStringW
0x1800a2a36  mov     edi, eax
0x1800a2a38  test    eax, eax
0x1800a2a3a  jnz     short loc_1800A2A43
0x1800a2a3c  mov     edx, 390h
0x1800a2a41  jmp     short loc_1800A29E8
0x1800a2a43  xor     r9d, r9d; cchBufferMax
0x1800a2a46  lea     r8, [rbp+arg_18]; lpBuffer
0x1800a2a4a  mov     edx, 65F6h; uID
0x1800a2a4f  mov     rcx, rbx; hInstance
0x1800a2a52  call    cs:__imp_LoadStringW
0x1800a2a58  mov     esi, eax
0x1800a2a5a  test    eax, eax
0x1800a2a5c  jnz     short loc_1800A2A65
0x1800a2a5e  mov     edx, 393h
0x1800a2a63  jmp     short loc_1800A29E8
0x1800a2a65  movsxd  r8, edi
0x1800a2a68  mov     rdx, [rbp+Buffer]
0x1800a2a6c  lea     rcx, [rbp+arg_8]
0x1800a2a70  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a2a75  nop
0x1800a2a76  mov     rbx, [rbp+arg_8]
0x1800a2a7a  test    rbx, rbx
0x1800a2a7d  jnz     short loc_1800A2AAB
0x1800a2a7f  mov     rcx, [rbp+18h]; this
0x1800a2a83  mov     ebx, 8007000Eh
0x1800a2a88  mov     r9d, ebx; char *
0x1800a2a8b  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a2a92  mov     edx, 3A3h; void *
0x1800a2a97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2a9c  nop
0x1800a2a9d  lea     rcx, [rbp+arg_8]
0x1800a2aa1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a2aa6  jmp     loc_1800A2B3F
0x1800a2aab  movsxd  r8, esi
0x1800a2aae  mov     rdx, [rbp+arg_18]
0x1800a2ab2  lea     rcx, [rbp+var_10]
0x1800a2ab6  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a2abb  nop
0x1800a2abc  mov     rax, [rbp+var_10]
0x1800a2ac0  test    rax, rax
0x1800a2ac3  jnz     short loc_1800A2AEE
0x1800a2ac5  mov     ebx, 8007000Eh
0x1800a2aca  mov     r9d, ebx; char *
0x1800a2acd  mov     edx, 3A6h; void *
0x1800a2ad2  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a2ad9  mov     rcx, [rbp+18h]; this
0x1800a2add  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2ae2  nop
0x1800a2ae3  lea     rcx, [rbp+var_10]
0x1800a2ae7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a2aec  jmp     short loc_1800A2A9D
0x1800a2aee  mov     [rsp+40h+var_18], rbx
0x1800a2af3  mov     [rsp+40h+var_20], rax
0x1800a2af8  lea     r9, aProtocol; "protocol"
0x1800a2aff  lea     r8, aMsSettingsWork; "ms-settings:workplace"
0x1800a2b06  lea     rdx, aFirstsyncstatu; "FirstSyncStatus"
0x1800a2b0d  lea     rcx, aWindowsSystemt; "Windows.SystemToast.DeviceManagement"
0x1800a2b14  call    cs:__imp_?DmRaiseToastNotification@@YAJPEBG00000@Z; DmRaiseToastNotification(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800a2b1a  mov     ebx, eax
0x1800a2b1c  test    eax, eax
0x1800a2b1e  jns     short loc_1800A2B2A
0x1800a2b20  mov     r9d, eax
0x1800a2b23  mov     edx, 3A8h
0x1800a2b28  jmp     short loc_1800A2AD2
0x1800a2b2a  lea     rcx, [rbp+var_10]
0x1800a2b2e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a2b33  nop
0x1800a2b34  lea     rcx, [rbp+arg_8]
0x1800a2b38  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a2b3d  xor     ebx, ebx
0x1800a2b3f  lea     rcx, [rbp+var_8]
0x1800a2b43  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800a2b48  mov     eax, ebx
0x1800a2b4a  mov     rbx, [rsp+40h+arg_0]
0x1800a2b4f  add     rsp, 40h
0x1800a2b53  pop     rdi
0x1800a2b54  pop     rsi
0x1800a2b55  pop     rbp
0x1800a2b56  retn
```
