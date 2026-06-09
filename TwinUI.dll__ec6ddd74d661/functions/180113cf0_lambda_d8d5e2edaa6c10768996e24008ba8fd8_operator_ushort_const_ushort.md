# _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(ushort const *,ushort * *)

- ea: `0x180113cf0`
- end: `0x180113f03`
- name: `??R_lambda_d8d5e2edaa6c10768996e24008ba8fd8_@@QEBAJPEBGPEAPEAG@Z`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18033a11c`

## callees

- `0x18000e498`
- `0x1800378dc`
- `0x180055268`
- `0x1800b5a1c`
- `0x180113cf0`
- `0x180113f0c`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180113d35`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180113e33`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180113e81`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180113eb0`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180113d35`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180113e33`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180113e81`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180113eb0`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180113e01`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180113e01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180113d1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180113d7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180113db9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180113d1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180113d7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180113db9`
- `api-ms-win-appmodel-runtime-internal-l1-1-7!IsMrtResourceRedirectionEnabled` at `0x180113d93`
- `api-ms-win-appmodel-runtime-internal-l1-1-7!IsMrtResourceRedirectionEnabled` at `0x180113d93`

## string_xrefs

- `0x180113d50`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x180113e4a`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x180113eca`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(HSTRING *a1, const WCHAR *a2, PWSTR *a3)
{
  HSTRING v6; // rcx
  const WCHAR *v7; // rax
  HRESULT v8; // ebx
  __int64 v9; // rdx
  HSTRING v11; // rcx
  const WCHAR *StringRawBuffer; // r15
  bool v13; // bl
  PCWSTR v14; // rax
  __int64 v15; // r8
  const WCHAR *v16; // rcx
  __int64 v17; // rdx
  HRESULT v18; // eax
  __int64 v19; // rdx
  HRESULT v20; // eax
  __int64 v21; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+38h]
  int v24; // [rsp+60h] [rbp+40h] BYREF
  PWSTR pszPath; // [rsp+70h] [rbp+50h] BYREF
  PWSTR ppszPathOut; // [rsp+78h] [rbp+58h] BYREF

  *a3 = 0;
  v6 = *a1;
  if ( !v6 )
  {
    v11 = a1[1];
    if ( !v11 )
      return 0;
    v24 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(v11, 0);
    v8 = IsMrtResourceRedirectionEnabled(StringRawBuffer, &v24);
    if ( v8 < 0 )
    {
      v9 = 272;
      goto LABEL_4;
    }
    v13 = v24 == 0;
    v14 = WindowsGetStringRawBuffer(a1[1], 0);
    LOBYTE(v15) = v13;
    ShellMRTHelper::Common::TryGetStagedPackagePathByFullNameAlloc(&pszPath, v14, v15);
    v16 = pszPath;
    if ( pszPath )
    {
      if ( v24 )
      {
        v17 = -1;
        do
          ++v17;
        while ( pszPath[v17] );
        v18 = PathCchRemoveFileSpec(pszPath, v17 + 1);
        v8 = v18;
        if ( v18 < 0 )
        {
          v19 = 283;
LABEL_23:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
            (const char *)(unsigned int)v18,
            savedregs);
          goto LABEL_24;
        }
        ppszPathOut = 0;
        v20 = PathAllocCombine(pszPath, L"Resources", 1u, &ppszPathOut);
        v8 = v20;
        if ( v20 < 0 )
        {
          v21 = 285;
LABEL_17:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v21,
            (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
            (const char *)(unsigned int)v20,
            savedregs);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
LABEL_24:
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPath);
          return (unsigned int)v8;
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pszPath,
          0);
        v20 = PathAllocCombine(ppszPathOut, StringRawBuffer, 1u, &pszPath);
        v8 = v20;
        if ( v20 < 0 )
        {
          v21 = 286;
          goto LABEL_17;
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
        v16 = pszPath;
      }
      v18 = PathAllocCombine(v16, a2, 1u, a3);
      v8 = v18;
      if ( v18 < 0 )
      {
        v19 = 289;
        goto LABEL_23;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPath);
    return 0;
  }
  v7 = WindowsGetStringRawBuffer(v6, 0);
  v8 = PathAllocCombine(v7, a2, 1u, a3);
  if ( v8 < 0 )
  {
    v9 = 263;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
      (const char *)(unsigned int)v8,
      savedregs);
    return (unsigned int)v8;
  }
  return 0;
}

```

## disassembly

```asm
0x180113cf0  push    rbp
0x180113cf2  push    rbx
0x180113cf3  push    rsi
0x180113cf4  push    rdi
0x180113cf5  push    r12
0x180113cf7  push    r14
0x180113cf9  push    r15; int
0x180113cfb  mov     rbp, rsp
0x180113cfe  sub     rsp, 20h
0x180113d02  mov     rsi, r8
0x180113d05  mov     r14, rdx
0x180113d08  mov     rdi, rcx
0x180113d0b  xor     r12d, r12d
0x180113d0e  mov     [r8], r12
0x180113d11  mov     rcx, [rcx]; string
0x180113d14  test    rcx, rcx
0x180113d17  jz      short loc_180113D6A
0x180113d19  xor     edx, edx; length
0x180113d1b  call    cs:__imp_WindowsGetStringRawBuffer
0x180113d22  nop     dword ptr [rax+rax+00h]
0x180113d27  mov     rcx, rax; pszPathIn
0x180113d2a  mov     r9, rsi; ppszPathOut
0x180113d2d  lea     r8d, [r12+1]; dwFlags
0x180113d32  mov     rdx, r14; pszMore
0x180113d35  call    cs:__imp_PathAllocCombine
0x180113d3c  nop     dword ptr [rax+rax+00h]
0x180113d41  mov     ebx, eax
0x180113d43  test    eax, eax
0x180113d45  jns     loc_180113EF1
0x180113d4b  mov     edx, 107h; void *
0x180113d50  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180113d57  mov     r9d, ebx; char *
0x180113d5a  mov     rcx, [rbp+38h]; this
0x180113d5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180113d63  mov     eax, ebx
0x180113d65  jmp     loc_180113EF3
0x180113d6a  mov     rcx, [rdi+8]; string
0x180113d6e  test    rcx, rcx
0x180113d71  jz      loc_180113EF1
0x180113d77  mov     [rbp+arg_0], r12d
0x180113d7b  xor     edx, edx; length
0x180113d7d  call    cs:__imp_WindowsGetStringRawBuffer
0x180113d84  nop     dword ptr [rax+rax+00h]
0x180113d89  mov     r15, rax
0x180113d8c  lea     rdx, [rbp+arg_0]
0x180113d90  mov     rcx, rax
0x180113d93  call    cs:__imp_IsMrtResourceRedirectionEnabled
0x180113d9a  nop     dword ptr [rax+rax+00h]
0x180113d9f  mov     ebx, eax
0x180113da1  test    eax, eax
0x180113da3  jns     short loc_180113DAC
0x180113da5  mov     edx, 110h
0x180113daa  jmp     short loc_180113D50
0x180113dac  cmp     [rbp+arg_0], r12d
0x180113db0  setz    bl
0x180113db3  xor     edx, edx; length
0x180113db5  mov     rcx, [rdi+8]; string
0x180113db9  call    cs:__imp_WindowsGetStringRawBuffer
0x180113dc0  nop     dword ptr [rax+rax+00h]
0x180113dc5  mov     rdx, rax
0x180113dc8  mov     r8b, bl
0x180113dcb  lea     rcx, [rbp+pszPath]
0x180113dcf  call    ?TryGetStagedPackagePathByFullNameAlloc@Common@ShellMRTHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG_N@Z; ShellMRTHelper::Common::TryGetStagedPackagePathByFullNameAlloc(ushort const *,bool)
0x180113dd4  mov     rcx, [rbp+pszPath]; pszPath
0x180113dd8  test    rcx, rcx
0x180113ddb  jz      loc_180113EE8
0x180113de1  mov     edi, 1
0x180113de6  cmp     [rbp+arg_0], r12d
0x180113dea  jz      loc_180113EA7
0x180113df0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180113df4  inc     rdx
0x180113df7  cmp     [rcx+rdx*2], r12w
0x180113dfc  jnz     short loc_180113DF4
0x180113dfe  inc     rdx; cchPath
0x180113e01  call    cs:__imp_PathCchRemoveFileSpec
0x180113e08  nop     dword ptr [rax+rax+00h]
0x180113e0d  mov     ebx, eax
0x180113e0f  test    eax, eax
0x180113e11  jns     short loc_180113E1D
0x180113e13  mov     edx, 11Bh
0x180113e18  jmp     loc_180113EC7
0x180113e1d  mov     [rbp+ppszPathOut], r12
0x180113e21  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x180113e25  mov     r8d, edi; dwFlags
0x180113e28  lea     rdx, ?c_msResourcesRedirectFolderName@Common@ShellMRTHelper@@3QBGB; "Resources"
0x180113e2f  mov     rcx, [rbp+pszPath]; pszPathIn
0x180113e33  call    cs:__imp_PathAllocCombine
0x180113e3a  nop     dword ptr [rax+rax+00h]
0x180113e3f  mov     ebx, eax
0x180113e41  test    eax, eax
0x180113e43  jns     short loc_180113E68
0x180113e45  mov     edx, 11Dh; void *
0x180113e4a  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180113e51  mov     r9d, eax; char *
0x180113e54  mov     rcx, [rbp+38h]; this
0x180113e58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180113e5d  lea     rcx, [rbp+ppszPathOut]
0x180113e61  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180113e66  jmp     short loc_180113EDA
0x180113e68  xor     edx, edx
0x180113e6a  lea     rcx, [rbp+pszPath]
0x180113e6e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180113e73  lea     r9, [rbp+pszPath]; ppszPathOut
0x180113e77  mov     r8d, edi; dwFlags
0x180113e7a  mov     rdx, r15; pszMore
0x180113e7d  mov     rcx, [rbp+ppszPathOut]; pszPathIn
0x180113e81  call    cs:__imp_PathAllocCombine
0x180113e88  nop     dword ptr [rax+rax+00h]
0x180113e8d  mov     ebx, eax
0x180113e8f  test    eax, eax
0x180113e91  jns     short loc_180113E9A
0x180113e93  mov     edx, 11Eh
0x180113e98  jmp     short loc_180113E4A
0x180113e9a  lea     rcx, [rbp+ppszPathOut]
0x180113e9e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180113ea3  mov     rcx, [rbp+pszPath]; pszPathIn
0x180113ea7  mov     r9, rsi; ppszPathOut
0x180113eaa  mov     r8d, edi; dwFlags
0x180113ead  mov     rdx, r14; pszMore
0x180113eb0  call    cs:__imp_PathAllocCombine
0x180113eb7  nop     dword ptr [rax+rax+00h]
0x180113ebc  mov     ebx, eax
0x180113ebe  test    eax, eax
0x180113ec0  jns     short loc_180113EE8
0x180113ec2  mov     edx, 121h; void *
0x180113ec7  mov     r9d, eax; char *
0x180113eca  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180113ed1  mov     rcx, [rbp+38h]; this
0x180113ed5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180113eda  lea     rcx, [rbp+pszPath]
0x180113ede  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180113ee3  jmp     loc_180113D63
0x180113ee8  lea     rcx, [rbp+pszPath]
0x180113eec  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180113ef1  xor     eax, eax
0x180113ef3  add     rsp, 20h
0x180113ef7  pop     r15
0x180113ef9  pop     r14
0x180113efb  pop     r12
0x180113efd  pop     rdi
0x180113efe  pop     rsi
0x180113eff  pop     rbx
0x180113f00  pop     rbp
0x180113f01  retn
```
