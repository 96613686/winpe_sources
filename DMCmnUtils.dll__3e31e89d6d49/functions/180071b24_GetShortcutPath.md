# GetShortcutPath

- ea: `0x180071b24`
- end: `0x180071f11`
- name: `GetShortcutPath`
- size: `1005`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800704a0`

## callees

- `0x180007640`
- `0x180007c7c`
- `0x180052114`
- `0x180057c4c`
- `0x180057c6c`
- `0x1800583e8`
- `0x18005b914`
- `0x18005b938`
- `0x18005bd30`
- `0x18005bd8c`
- `0x18005d7f8`
- `0x18005e13c`
- `0x18005fc38`
- `0x180069ef0`
- `0x18006a730`
- `0x18006f2e8`
- `0x18006f8a8`
- `0x18006f9b4`
- `0x180071b24`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180071b4d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180071b4d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180071b7f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180071b7f`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180071de9`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180071e3b`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180071de9`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180071e3b`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x180071cca`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x180071cca`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180071d8e`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180071d8e`

## string_xrefs

- `0x180071b46`: `DMAppsRes.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetShortcutPath(unsigned __int16 **a1)
{
  HMODULE Library; // rax
  const char *v3; // r9
  __int64 v4; // rdx
  int StringW; // eax
  unsigned int LastError; // ebx
  unsigned __int16 *v7; // rbx
  __int64 v8; // rax
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // r14
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rdi
  HRESULT v13; // eax
  __int64 v14; // rdx
  const struct std::nothrow_t *v15; // rdx
  int ActiveUserSid; // eax
  int UserTokenFromSid; // eax
  HRESULT v18; // eax
  HRESULT v19; // eax
  HRESULT v20; // eax
  __int64 v21; // r9
  __int64 v22; // rdx
  unsigned __int16 *v23; // rax
  const struct std::nothrow_t *v24; // rdx
  PWSTR ppszPath; // [rsp+20h] [rbp-30h] BYREF
  PWSTR ppszPathOut; // [rsp+28h] [rbp-28h] BYREF
  PWSTR v28; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v29; // [rsp+38h] [rbp-18h] BYREF
  WCHAR Buffer[4]; // [rsp+40h] [rbp-10h] BYREF
  HMODULE v31; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  unsigned __int16 *v33; // [rsp+98h] [rbp+48h] BYREF
  unsigned __int16 *v34; // [rsp+A0h] [rbp+50h] BYREF
  HANDLE hToken; // [rsp+A8h] [rbp+58h] BYREF

  Library = LoadLibraryExW(L"DMAppsRes.dll", 0, 0x800u);
  v31 = Library;
  if ( Library )
  {
    *(_QWORD *)Buffer = 0;
    StringW = LoadStringW(Library, 0x65F4u, Buffer, 0);
    if ( !StringW )
    {
      v4 = 162;
      goto LABEL_5;
    }
    v33 = 0;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v34,
      *(_QWORD *)Buffer,
      StringW);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v33,
      &v34);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
    v7 = v33;
    if ( !v33 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA6,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)0x8007000ELL,
        (int)ppszPath);
LABEL_8:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
      goto LABEL_42;
    }
    v8 = -1;
    do
      ++v8;
    while ( v33[v8] );
    v9 = v8 + 5;
    v10 = 2 * (v8 + 5);
    if ( !is_mul_ok(v8 + 5, 2u) )
      v10 = -1;
    v11 = (unsigned __int16 *)operator new[](v10, (const struct std::nothrow_t *)std::nothrow);
    v12 = v11;
    if ( v11 )
      memset_0(v11, 0, v10);
    else
      v12 = 0;
    v29 = v12;
    if ( !v12 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAA,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)0x8007000ELL,
        (int)ppszPath);
      goto LABEL_8;
    }
    v13 = StringCchCopyW(v12, v9, v7);
    LastError = v13;
    if ( v13 >= 0 )
    {
      v13 = PathCchRenameExtension(v12, v9, L"lnk");
      LastError = v13;
      if ( v13 >= 0 )
      {
        v34 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v34,
          0);
        ActiveUserSid = DmGetActiveUserSid(&v34);
        LastError = ActiveUserSid;
        if ( ActiveUserSid >= 0 )
        {
          hToken = 0;
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &hToken,
            0);
          UserTokenFromSid = DmGetUserTokenFromSid(v34, &hToken, 0);
          LastError = UserTokenFromSid;
          if ( UserTokenFromSid >= 0 )
          {
            ppszPath = 0;
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &ppszPath,
              0);
            v18 = SHGetKnownFolderPath(&FOLDERID_RoamingAppData, 0, hToken, &ppszPath);
            LastError = v18;
            if ( v18 >= 0 )
            {
              ppszPathOut = 0;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &ppszPathOut,
                0);
              v19 = PathAllocCombine(ppszPath, L"Microsoft\\Windows\\Start Menu\\Programs", 1u, &ppszPathOut);
              LastError = v19;
              if ( v19 >= 0 )
              {
                v28 = 0;
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                  &v28,
                  0);
                v20 = PathAllocCombine(ppszPathOut, v12, 1u, &v28);
                LastError = v20;
                if ( v20 >= 0 )
                {
                  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                    &v29,
                    v28,
                    -1);
                  v23 = v29;
                  v29 = 0;
                  *a1 = v23;
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
                  if ( *a1 )
                  {
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
                    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
                    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
                    operator delete(v12, v24);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
                    LastError = 0;
                    goto LABEL_42;
                  }
                  LastError = -2147024882;
                  v21 = 2147942414LL;
                  v22 = 198;
                }
                else
                {
                  v21 = (unsigned int)v20;
                  v22 = 195;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v22,
                  (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
                  (const char *)v21,
                  (int)ppszPath);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xC0,
                  (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
                  (const char *)(unsigned int)v19,
                  (int)ppszPath);
              }
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xBD,
                (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
                (const char *)(unsigned int)v18,
                (int)ppszPath);
            }
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB5,
              (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
              (const char *)(unsigned int)UserTokenFromSid,
              (int)ppszPath);
          }
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB2,
            (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
            (const char *)(unsigned int)ActiveUserSid,
            (int)ppszPath);
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
        goto LABEL_21;
      }
      v14 = 174;
    }
    else
    {
      v14 = 172;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
      (const char *)(unsigned int)v13,
      (int)ppszPath);
LABEL_21:
    operator delete(v12, v15);
    goto LABEL_8;
  }
  v4 = 158;
LABEL_5:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v4,
                (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
                v3);
LABEL_42:
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v31);
  return LastError;
}

```

## disassembly

```asm
0x180071b24  mov     [rsp-38h+arg_0], rbx
0x180071b29  push    rbp
0x180071b2a  push    rsi
0x180071b2b  push    rdi
0x180071b2c  push    r12
0x180071b2e  push    r13
0x180071b30  push    r14
0x180071b32  push    r15
0x180071b34  mov     rbp, rsp
0x180071b37  sub     rsp, 50h
0x180071b3b  mov     r15, rcx
0x180071b3e  xor     edx, edx; hFile
0x180071b40  mov     r8d, 800h; dwFlags
0x180071b46  lea     rcx, aDmappsresDll; "DMAppsRes.dll"
0x180071b4d  call    cs:__imp_LoadLibraryExW
0x180071b54  nop     dword ptr [rax+rax+00h]
0x180071b59  mov     [rbp+var_8], rax
0x180071b5d  xor     r12d, r12d
0x180071b60  test    rax, rax
0x180071b63  jnz     short loc_180071B6C
0x180071b65  mov     edx, 9Eh
0x180071b6a  jmp     short loc_180071B94
0x180071b6c  mov     qword ptr [rbp+Buffer], r12
0x180071b70  xor     r9d, r9d; cchBufferMax
0x180071b73  lea     r8, [rbp+Buffer]; lpBuffer
0x180071b77  mov     edx, 65F4h; uID
0x180071b7c  mov     rcx, rax; hInstance
0x180071b7f  call    cs:__imp_LoadStringW
0x180071b86  nop     dword ptr [rax+rax+00h]
0x180071b8b  test    eax, eax
0x180071b8d  jnz     short loc_180071BAB
0x180071b8f  mov     edx, 0A2h; void *
0x180071b94  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180071b9b  mov     rcx, [rbp+38h]; this
0x180071b9f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180071ba4  mov     ebx, eax
0x180071ba6  jmp     loc_180071EED
0x180071bab  mov     [rbp+arg_8], r12
0x180071baf  movsxd  r8, eax
0x180071bb2  mov     rdx, qword ptr [rbp+Buffer]
0x180071bb6  lea     rcx, [rbp+arg_10]
0x180071bba  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180071bbf  lea     rdx, [rbp+arg_10]
0x180071bc3  lea     rcx, [rbp+arg_8]
0x180071bc7  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180071bcc  lea     rcx, [rbp+arg_10]
0x180071bd0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180071bd5  mov     rbx, [rbp+arg_8]
0x180071bd9  test    rbx, rbx
0x180071bdc  jnz     short loc_180071C0A
0x180071bde  mov     rcx, [rbp+38h]; this
0x180071be2  mov     ebx, 8007000Eh
0x180071be7  mov     r9d, ebx; char *
0x180071bea  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180071bf1  mov     edx, 0A6h; void *
0x180071bf6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071bfb  nop
0x180071bfc  lea     rcx, [rbp+arg_8]
0x180071c00  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180071c05  jmp     loc_180071EED
0x180071c0a  or      r13, 0FFFFFFFFFFFFFFFFh
0x180071c0e  mov     rax, r13
0x180071c11  inc     rax
0x180071c14  cmp     [rbx+rax*2], r12w
0x180071c19  jnz     short loc_180071C11
0x180071c1b  lea     rsi, [rax+5]
0x180071c1f  mov     eax, 2
0x180071c24  mul     rsi
0x180071c27  mov     r14, rax
0x180071c2a  cmovb   r14, r13
0x180071c2e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180071c35  mov     rcx, r14; unsigned __int64
0x180071c38  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180071c3d  mov     rdi, rax
0x180071c40  test    rax, rax
0x180071c43  jz      short loc_180071C54
0x180071c45  mov     r8, r14; Size
0x180071c48  xor     edx, edx; Val
0x180071c4a  mov     rcx, rax; void *
0x180071c4d  call    memset_0
0x180071c52  jmp     short loc_180071C57
0x180071c54  mov     rdi, r12
0x180071c57  mov     [rbp+var_18], rdi
0x180071c5b  test    rdi, rdi
0x180071c5e  jnz     short loc_180071C83
0x180071c60  mov     rcx, [rbp+38h]; this
0x180071c64  mov     ebx, 8007000Eh
0x180071c69  mov     r9d, ebx; char *
0x180071c6c  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180071c73  mov     edx, 0AAh; void *
0x180071c78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071c7d  nop
0x180071c7e  jmp     loc_180071BFC
0x180071c83  mov     r8, rbx; unsigned __int16 *
0x180071c86  mov     rdx, rsi; unsigned __int64
0x180071c89  mov     rcx, rdi; unsigned __int16 *
0x180071c8c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180071c91  mov     ebx, eax
0x180071c93  test    eax, eax
0x180071c95  jns     short loc_180071CBD
0x180071c97  mov     edx, 0ACh; void *
0x180071c9c  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180071ca3  mov     r9d, eax; char *
0x180071ca6  mov     rcx, [rbp+38h]; this
0x180071caa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071caf  nop
0x180071cb0  mov     rcx, rdi; void *
0x180071cb3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180071cb8  jmp     loc_180071BFC
0x180071cbd  lea     r8, pszExt; "lnk"
0x180071cc4  mov     rdx, rsi; cchPath
0x180071cc7  mov     rcx, rdi; pszPath
0x180071cca  call    cs:__imp_PathCchRenameExtension
0x180071cd1  nop     dword ptr [rax+rax+00h]
0x180071cd6  mov     ebx, eax
0x180071cd8  test    eax, eax
0x180071cda  jns     short loc_180071CE3
0x180071cdc  mov     edx, 0AEh
0x180071ce1  jmp     short loc_180071C9C
0x180071ce3  mov     [rbp+arg_10], r12
0x180071ce7  xor     edx, edx
0x180071ce9  lea     rcx, [rbp+arg_10]
0x180071ced  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180071cf2  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x180071cf6  call    ?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180071cfb  mov     ebx, eax
0x180071cfd  test    eax, eax
0x180071cff  jns     short loc_180071D25
0x180071d01  mov     rcx, [rbp+38h]; this
0x180071d05  mov     r9d, eax; char *
0x180071d08  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180071d0f  mov     edx, 0B2h; void *
0x180071d14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071d19  nop
0x180071d1a  lea     rcx, [rbp+arg_10]
0x180071d1e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180071d23  jmp     short loc_180071CB0
0x180071d25  mov     [rbp+hToken], r12
0x180071d29  xor     edx, edx
0x180071d2b  lea     rcx, [rbp+hToken]
0x180071d2f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180071d34  xor     r8d, r8d; unsigned int *
0x180071d37  lea     rdx, [rbp+hToken]; void **
0x180071d3b  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x180071d3f  call    ?DmGetUserTokenFromSid@@YAJPEBGPEAPEAXPEAK@Z; DmGetUserTokenFromSid(ushort const *,void * *,ulong *)
0x180071d44  mov     ebx, eax
0x180071d46  test    eax, eax
0x180071d48  jns     short loc_180071D6E
0x180071d4a  mov     rcx, [rbp+38h]; this
0x180071d4e  mov     r9d, eax; char *
0x180071d51  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180071d58  mov     edx, 0B5h; void *
0x180071d5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071d62  nop
0x180071d63  lea     rcx, [rbp+hToken]
0x180071d67  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180071d6c  jmp     short loc_180071D1A
0x180071d6e  mov     [rbp+ppszPath], r12
0x180071d72  xor     edx, edx
0x180071d74  lea     rcx, [rbp+ppszPath]
0x180071d78  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180071d7d  lea     r9, [rbp+ppszPath]; ppszPath
0x180071d81  mov     r8, [rbp+hToken]; hToken
0x180071d85  xor     edx, edx; dwFlags
0x180071d87  lea     rcx, FOLDERID_RoamingAppData; rfid
0x180071d8e  call    cs:__imp_SHGetKnownFolderPath
0x180071d95  nop     dword ptr [rax+rax+00h]
0x180071d9a  mov     ebx, eax
0x180071d9c  test    eax, eax
0x180071d9e  jns     short loc_180071DC3
0x180071da0  mov     rcx, [rbp+38h]; this
0x180071da4  mov     r9d, eax; char *
0x180071da7  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180071dae  mov     edx, 0BDh; void *
0x180071db3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071db8  lea     rcx, [rbp+ppszPath]
0x180071dbc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180071dc1  jmp     short loc_180071D63
0x180071dc3  mov     [rbp+ppszPathOut], r12
0x180071dc7  xor     edx, edx
0x180071dc9  lea     rcx, [rbp+ppszPathOut]
0x180071dcd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180071dd2  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x180071dd6  mov     esi, 1
0x180071ddb  mov     r8d, esi; dwFlags
0x180071dde  lea     rdx, pszMore; "Microsoft\\Windows\\Start Menu\\Program"...
0x180071de5  mov     rcx, [rbp+ppszPath]; pszPathIn
0x180071de9  call    cs:__imp_PathAllocCombine
0x180071df0  nop     dword ptr [rax+rax+00h]
0x180071df5  mov     ebx, eax
0x180071df7  test    eax, eax
0x180071df9  jns     short loc_180071E1E
0x180071dfb  mov     rcx, [rbp+38h]; this
0x180071dff  mov     r9d, eax; char *
0x180071e02  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180071e09  mov     edx, 0C0h; void *
0x180071e0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071e13  lea     rcx, [rbp+ppszPathOut]
0x180071e17  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180071e1c  jmp     short loc_180071DB8
0x180071e1e  mov     [rbp+var_20], r12
0x180071e22  xor     edx, edx
0x180071e24  lea     rcx, [rbp+var_20]
0x180071e28  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180071e2d  lea     r9, [rbp+var_20]; ppszPathOut
0x180071e31  mov     r8d, esi; dwFlags
0x180071e34  mov     rdx, rdi; pszMore
0x180071e37  mov     rcx, [rbp+ppszPathOut]; pszPathIn
0x180071e3b  call    cs:__imp_PathAllocCombine
0x180071e42  nop     dword ptr [rax+rax+00h]
0x180071e47  mov     ebx, eax
0x180071e49  test    eax, eax
0x180071e4b  jns     short loc_180071E70
0x180071e4d  mov     r9d, eax; char *
0x180071e50  mov     edx, 0C3h; void *
0x180071e55  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180071e5c  mov     rcx, [rbp+38h]; this
0x180071e60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071e65  lea     rcx, [rbp+var_20]
0x180071e69  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180071e6e  jmp     short loc_180071E13
0x180071e70  mov     r8, r13
0x180071e73  mov     rdx, [rbp+var_20]
0x180071e77  lea     rcx, [rbp+var_18]
0x180071e7b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180071e80  mov     rax, [rbp+var_18]
0x180071e84  mov     [rbp+var_18], r12
0x180071e88  mov     [r15], rax
0x180071e8b  lea     rcx, [rbp+var_18]
0x180071e8f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180071e94  cmp     [r15], r12
0x180071e97  jnz     short loc_180071EA8
0x180071e99  mov     ebx, 8007000Eh
0x180071e9e  mov     r9d, ebx
0x180071ea1  mov     edx, 0C6h
0x180071ea6  jmp     short loc_180071E55
0x180071ea8  lea     rcx, [rbp+var_20]
0x180071eac  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180071eb1  lea     rcx, [rbp+ppszPathOut]
0x180071eb5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180071eba  lea     rcx, [rbp+ppszPath]
0x180071ebe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180071ec3  nop
0x180071ec4  lea     rcx, [rbp+hToken]
0x180071ec8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180071ecd  nop
0x180071ece  lea     rcx, [rbp+arg_10]
0x180071ed2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180071ed7  nop
0x180071ed8  mov     rcx, rdi; void *
0x180071edb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180071ee0  nop
0x180071ee1  lea     rcx, [rbp+arg_8]
0x180071ee5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180071eea  mov     ebx, r12d
0x180071eed  lea     rcx, [rbp+var_8]
0x180071ef1  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180071ef6  mov     eax, ebx
0x180071ef8  mov     rbx, [rsp+50h+arg_0]
0x180071f00  add     rsp, 50h
0x180071f04  pop     r15
0x180071f06  pop     r14
0x180071f08  pop     r13
0x180071f0a  pop     r12
0x180071f0c  pop     rdi
0x180071f0d  pop     rsi
0x180071f0e  pop     rbp
0x180071f0f  retn
```
