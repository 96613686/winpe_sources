# GetProgramDataBucketConfidenceFilePath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002dc44`
- end: `0x18002dd2b`
- name: `?GetProgramDataBucketConfidenceFilePath@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `231`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002f230`

## callees

- `0x1800078b0`
- `0x18000bcc4`
- `0x18000e410`
- `0x1800248b4`
- `0x18002dc44`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002dcbc`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002dcbc`
- `SHELL32!SHGetKnownFolderPath` at `0x18002dc8f`
- `SHELL32!SHGetKnownFolderPath` at `0x18002dc8f`

## string_xrefs

- `0x18002dc9d`: `SHGetKnownFolderPath failed with %x`
- `0x18002dca6`: `Microsoft\Windows\SecureBootUpdates\BucketConfidenceData.cab`
- `0x18002dcca`: `PathCchCombine failed with %x`

## pseudocode

```c
__int64 __fastcall GetProgramDataBucketConfidenceFilePath(__int64 a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  HRESULT v4; // eax
  __int64 v5; // r8
  PWSTR ppszPath[2]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR pszPathOut[264]; // [rsp+30h] [rbp-228h] BYREF

  ppszPath[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    ppszPath,
    0);
  v2 = SHGetKnownFolderPath(&FOLDERID_ProgramData, 0, 0, ppszPath);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v4 = PathCchCombine(
           pszPathOut,
           0x104u,
           ppszPath[0],
           L"Microsoft\\Windows\\SecureBootUpdates\\BucketConfidenceData.cab");
    v3 = v4;
    if ( v4 >= 0 )
    {
      v5 = -1;
      do
        ++v5;
      while ( pszPathOut[v5] );
      std::wstring::_Assign<unsigned short>(a1, pszPathOut);
      v3 = 0;
    }
    else
    {
      SBServicingLogMessage((wchar_t *)L"PathCchCombine failed with %x", (unsigned int)v4);
    }
  }
  else
  {
    SBServicingLogMessage(L"SHGetKnownFolderPath failed with %x", (unsigned int)v2);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(ppszPath);
  return v3;
}

```

## disassembly

```asm
0x18002dc44  mov     [rsp+arg_8], rbx
0x18002dc49  mov     [rsp+arg_10], rsi
0x18002dc4e  push    rdi
0x18002dc4f  sub     rsp, 250h
0x18002dc56  mov     rax, cs:__security_cookie
0x18002dc5d  xor     rax, rsp
0x18002dc60  mov     [rsp+258h+var_18], rax
0x18002dc68  mov     rdi, rcx
0x18002dc6b  xor     esi, esi
0x18002dc6d  mov     [rsp+258h+ppszPath], rsi
0x18002dc72  xor     edx, edx
0x18002dc74  lea     rcx, [rsp+258h+ppszPath]
0x18002dc79  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002dc7e  lea     r9, [rsp+258h+ppszPath]; ppszPath
0x18002dc83  xor     r8d, r8d; hToken
0x18002dc86  xor     edx, edx; dwFlags
0x18002dc88  lea     rcx, FOLDERID_ProgramData; rfid
0x18002dc8f  call    cs:__imp_SHGetKnownFolderPath
0x18002dc95  mov     ebx, eax
0x18002dc97  test    eax, eax
0x18002dc99  jns     short loc_18002DCA6
0x18002dc9b  mov     edx, eax
0x18002dc9d  lea     rcx, aShgetknownfold_0; "SHGetKnownFolderPath failed with %x"
0x18002dca4  jmp     short loc_18002DCD1
0x18002dca6  lea     r9, pszMore; "Microsoft\\Windows\\SecureBootUpdates\\"...
0x18002dcad  mov     r8, [rsp+258h+ppszPath]; pszPathIn
0x18002dcb2  mov     edx, 104h; cchPathOut
0x18002dcb7  lea     rcx, [rsp+258h+pszPathOut]; pszPathOut
0x18002dcbc  call    cs:__imp_PathCchCombine
0x18002dcc2  mov     ebx, eax
0x18002dcc4  test    eax, eax
0x18002dcc6  jns     short loc_18002DCD8
0x18002dcc8  mov     edx, eax
0x18002dcca  lea     rcx, aPathcchcombine; "PathCchCombine failed with %x"
0x18002dcd1  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002dcd6  jmp     short loc_18002DCFA
0x18002dcd8  lea     rax, [rsp+258h+pszPathOut]
0x18002dcdd  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002dce1  inc     r8
0x18002dce4  cmp     [rax+r8*2], si
0x18002dce9  jnz     short loc_18002DCE1
0x18002dceb  lea     rdx, [rsp+258h+pszPathOut]
0x18002dcf0  mov     rcx, rdi
0x18002dcf3  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002dcf8  mov     ebx, esi
0x18002dcfa  lea     rcx, [rsp+258h+ppszPath]
0x18002dcff  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002dd04  mov     eax, ebx
0x18002dd06  mov     rcx, [rsp+258h+var_18]
0x18002dd0e  xor     rcx, rsp; StackCookie
0x18002dd11  call    __security_check_cookie
0x18002dd16  lea     r11, [rsp+258h+var_8]
0x18002dd1e  mov     rbx, [r11+18h]
0x18002dd22  mov     rsi, [r11+20h]
0x18002dd26  mov     rsp, r11
0x18002dd29  pop     rdi
0x18002dd2a  retn
```
