# _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(ushort const *,ushort * *)

- ea: `0x18036bf1c`
- end: `0x18036c103`
- name: `??R_lambda_d8d5e2edaa6c10768996e24008ba8fd8_@@QEBAJPEBGPEAPEAG@Z`
- size: `487`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1800dadbc`

## callees

- `0x18001aca4`
- `0x18002f1fc`
- `0x1800c402c`
- `0x1800f0854`
- `0x1801169d4`
- `0x180122678`
- `0x18036bf1c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18036bf47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18036bf9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18036bfcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18036bf47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18036bf9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18036bfcd`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18036c00f`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18036c00f`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18036bf5b`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18036c046`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18036c08e`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18036c0b7`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18036bf5b`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18036c046`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18036c08e`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18036c0b7`
- `api-ms-win-appmodel-runtime-internal-l1-1-7!IsMrtResourceRedirectionEnabled` at `0x18036bfad`
- `api-ms-win-appmodel-runtime-internal-l1-1-7!IsMrtResourceRedirectionEnabled` at `0x18036bfad`

## string_xrefs

- `0x18036bf74`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x18036c05b`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x18036c0cc`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`

## pseudocode

```c
__int64 __fastcall _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(HSTRING *a1, const WCHAR *a2, PWSTR *a3)
{
  HSTRING v5; // rcx
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
  v5 = *a1;
  if ( !v5 )
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
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &ppszPathOut,
          0);
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
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszPath);
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
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszPath);
    return 0;
  }
  v7 = WindowsGetStringRawBuffer(v5, 0);
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
0x18036bf1c  push    rbp
0x18036bf1e  push    rbx
0x18036bf1f  push    rsi
0x18036bf20  push    rdi
0x18036bf21  push    r12
0x18036bf23  push    r14
0x18036bf25  push    r15; int
0x18036bf27  mov     rbp, rsp
0x18036bf2a  sub     rsp, 20h
0x18036bf2e  xor     r12d, r12d
0x18036bf31  mov     rdi, rcx
0x18036bf34  mov     [r8], r12
0x18036bf37  mov     rsi, r8
0x18036bf3a  mov     rcx, [rcx]; string
0x18036bf3d  mov     r14, rdx
0x18036bf40  test    rcx, rcx
0x18036bf43  jz      short loc_18036BF8A
0x18036bf45  xor     edx, edx; length
0x18036bf47  call    cs:__imp_WindowsGetStringRawBuffer
0x18036bf4d  mov     r9, rsi; ppszPathOut
0x18036bf50  lea     r8d, [r12+1]; dwFlags
0x18036bf55  mov     rcx, rax; pszPathIn
0x18036bf58  mov     rdx, r14; pszMore
0x18036bf5b  call    cs:__imp_PathAllocCombine
0x18036bf61  mov     ebx, eax
0x18036bf63  test    eax, eax
0x18036bf65  jns     loc_18036C0F2
0x18036bf6b  mov     edx, 107h; void *
0x18036bf70  mov     rcx, [rbp+38h]; this
0x18036bf74  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18036bf7b  mov     r9d, ebx; char *
0x18036bf7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18036bf83  mov     eax, ebx
0x18036bf85  jmp     loc_18036C0F4
0x18036bf8a  mov     rcx, [rdi+8]; string
0x18036bf8e  test    rcx, rcx
0x18036bf91  jz      loc_18036C0F2
0x18036bf97  xor     edx, edx; length
0x18036bf99  mov     [rbp+arg_0], r12d
0x18036bf9d  call    cs:__imp_WindowsGetStringRawBuffer
0x18036bfa3  mov     rcx, rax
0x18036bfa6  lea     rdx, [rbp+arg_0]
0x18036bfaa  mov     r15, rax
0x18036bfad  call    cs:__imp_IsMrtResourceRedirectionEnabled
0x18036bfb3  mov     ebx, eax
0x18036bfb5  test    eax, eax
0x18036bfb7  jns     short loc_18036BFC0
0x18036bfb9  mov     edx, 110h
0x18036bfbe  jmp     short loc_18036BF70
0x18036bfc0  cmp     [rbp+arg_0], r12d
0x18036bfc4  mov     rcx, [rdi+8]; string
0x18036bfc8  setz    bl
0x18036bfcb  xor     edx, edx; length
0x18036bfcd  call    cs:__imp_WindowsGetStringRawBuffer
0x18036bfd3  mov     r8b, bl
0x18036bfd6  lea     rcx, [rbp+pszPath]
0x18036bfda  mov     rdx, rax
0x18036bfdd  call    ?TryGetStagedPackagePathByFullNameAlloc@Common@ShellMRTHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG_N@Z; ShellMRTHelper::Common::TryGetStagedPackagePathByFullNameAlloc(ushort const *,bool)
0x18036bfe2  mov     rcx, [rbp+pszPath]; pszPath
0x18036bfe6  test    rcx, rcx
0x18036bfe9  jz      loc_18036C0E9
0x18036bfef  mov     edi, 1
0x18036bff4  cmp     [rbp+arg_0], r12d
0x18036bff8  jz      loc_18036C0AE
0x18036bffe  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18036c002  inc     rdx
0x18036c005  cmp     [rcx+rdx*2], r12w
0x18036c00a  jnz     short loc_18036C002
0x18036c00c  inc     rdx; cchPath
0x18036c00f  call    cs:__imp_PathCchRemoveFileSpec
0x18036c015  mov     ebx, eax
0x18036c017  test    eax, eax
0x18036c019  jns     short loc_18036C025
0x18036c01b  mov     edx, 11Bh
0x18036c020  jmp     loc_18036C0C8
0x18036c025  xor     edx, edx
0x18036c027  mov     [rbp+ppszPathOut], r12
0x18036c02b  lea     rcx, [rbp+ppszPathOut]
0x18036c02f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18036c034  mov     rcx, [rbp+pszPath]; pszPathIn
0x18036c038  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x18036c03c  mov     r8d, edi; dwFlags
0x18036c03f  lea     rdx, ?c_msResourcesRedirectFolderName@Common@ShellMRTHelper@@3QBGB; "Resources"
0x18036c046  call    cs:__imp_PathAllocCombine
0x18036c04c  mov     ebx, eax
0x18036c04e  test    eax, eax
0x18036c050  jns     short loc_18036C075
0x18036c052  mov     edx, 11Dh; void *
0x18036c057  mov     rcx, [rbp+38h]; this
0x18036c05b  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18036c062  mov     r9d, eax; char *
0x18036c065  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18036c06a  lea     rcx, [rbp+ppszPathOut]
0x18036c06e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18036c073  jmp     short loc_18036C0DB
0x18036c075  xor     edx, edx
0x18036c077  lea     rcx, [rbp+pszPath]
0x18036c07b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18036c080  mov     rcx, [rbp+ppszPathOut]; pszPathIn
0x18036c084  lea     r9, [rbp+pszPath]; ppszPathOut
0x18036c088  mov     r8d, edi; dwFlags
0x18036c08b  mov     rdx, r15; pszMore
0x18036c08e  call    cs:__imp_PathAllocCombine
0x18036c094  mov     ebx, eax
0x18036c096  test    eax, eax
0x18036c098  jns     short loc_18036C0A1
0x18036c09a  mov     edx, 11Eh
0x18036c09f  jmp     short loc_18036C057
0x18036c0a1  lea     rcx, [rbp+ppszPathOut]
0x18036c0a5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18036c0aa  mov     rcx, [rbp+pszPath]; pszPathIn
0x18036c0ae  mov     r9, rsi; ppszPathOut
0x18036c0b1  mov     r8d, edi; dwFlags
0x18036c0b4  mov     rdx, r14; pszMore
0x18036c0b7  call    cs:__imp_PathAllocCombine
0x18036c0bd  mov     ebx, eax
0x18036c0bf  test    eax, eax
0x18036c0c1  jns     short loc_18036C0E9
0x18036c0c3  mov     edx, 121h; void *
0x18036c0c8  mov     rcx, [rbp+38h]; this
0x18036c0cc  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18036c0d3  mov     r9d, eax; char *
0x18036c0d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18036c0db  lea     rcx, [rbp+pszPath]
0x18036c0df  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18036c0e4  jmp     loc_18036BF83
0x18036c0e9  lea     rcx, [rbp+pszPath]
0x18036c0ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18036c0f2  xor     eax, eax
0x18036c0f4  add     rsp, 20h
0x18036c0f8  pop     r15
0x18036c0fa  pop     r14
0x18036c0fc  pop     r12
0x18036c0fe  pop     rdi
0x18036c0ff  pop     rsi
0x18036c100  pop     rbx
0x18036c101  pop     rbp
0x18036c102  retn
```
