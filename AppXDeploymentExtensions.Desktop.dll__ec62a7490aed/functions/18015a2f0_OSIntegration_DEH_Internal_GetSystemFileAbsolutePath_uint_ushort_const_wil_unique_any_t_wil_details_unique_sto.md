# OSIntegration::DEH::Internal::GetSystemFileAbsolutePath(uint,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18015a2f0`
- end: `0x18015a433`
- name: `?GetSystemFileAbsolutePath@Internal@DEH@OSIntegration@@YAJIPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `323`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18014e968`
- `0x18015192c`

## callees

- `0x1800530c0`
- `0x18006a4c8`
- `0x18007cdc0`
- `0x1800aed10`
- `0x1800af918`
- `0x18015a2f0`
- `0x1801636a8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18015a35a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18015a35a`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18015a3cf`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18015a3cf`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x18015a342`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x18015a342`

## string_xrefs

- `0x18015a395`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18015a400`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18015a3ed`: `PathAllocCombine(systemDirectoryCharacters, relativePath, PATHCCH_ALLOW_LONG_PATHS, &absolutePath)`
- `0x18015a376`: `Failed call to GetSystemDirectory/GetSystemWow64Directory2. imageFileMachine=%u`
- `0x18015a38e`: `OSIntegration::DEH::Internal::GetSystemFileAbsolutePath`
- `0x18015a3f9`: `OSIntegration::DEH::Internal::GetSystemFileAbsolutePath`
- `0x18015a382`: `systemDirectoryLength == 0`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::GetSystemFileAbsolutePath(
        char *a1,
        PCWSTR pszMore,
        PWSTR *ppszPathOut)
{
  int v5; // ebx
  UINT SystemDirectoryW; // eax
  __int64 v7; // rcx
  HRESULT v9; // eax
  unsigned int v10; // ebx
  char *v11; // [rsp+28h] [rbp-250h]
  char *v12; // [rsp+30h] [rbp-248h]
  WCHAR Buffer[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+278h] [rbp+0h]

  v5 = (int)a1;
  memset_0(Buffer, 0, 0x208u);
  if ( v5 == 34404 || v5 == 1 )
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  else
    SystemDirectoryW = GetSystemWow64Directory2W(Buffer, 260, (unsigned __int16)v5);
  if ( SystemDirectoryW )
  {
    if ( SystemDirectoryW >= 0x104 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v7);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      ppszPathOut,
      0);
    v9 = PathAllocCombine(Buffer, pszMore, 1u, ppszPathOut);
    v10 = v9;
    if ( v9 >= 0 )
    {
      return 0;
    }
    else
    {
      LODWORD(v11) = v9;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x1FA,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
        "OSIntegration::DEH::Internal::GetSystemFileAbsolutePath",
        "PathAllocCombine(systemDirectoryCharacters, relativePath, PATHCCH_ALLOW_LONG_PATHS, &absolutePath)",
        v11,
        (int)v12);
      return v10;
    }
  }
  else
  {
    LODWORD(v12) = v5;
    return wil::details::in1diag5::Return_GetLastErrorMsg(
             retaddr,
             (void *)0x1F3,
             (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
             "OSIntegration::DEH::Internal::GetSystemFileAbsolutePath",
             "systemDirectoryLength == 0",
             "Failed call to GetSystemDirectory/GetSystemWow64Directory2. imageFileMachine=%u",
             v12);
  }
}

```

## disassembly

```asm
0x18015a2f0  push    rbx
0x18015a2f2  push    rsi
0x18015a2f3  push    rdi
0x18015a2f4  sub     rsp, 260h
0x18015a2fb  mov     rax, cs:__security_cookie
0x18015a302  xor     rax, rsp
0x18015a305  mov     [rsp+278h+var_28], rax
0x18015a30d  mov     rdi, r8
0x18015a310  mov     rsi, rdx
0x18015a313  mov     ebx, ecx
0x18015a315  xor     edx, edx; Val
0x18015a317  mov     r8d, 208h; Size
0x18015a31d  lea     rcx, [rsp+278h+Buffer]; void *
0x18015a322  call    memset_0
0x18015a327  cmp     ebx, 8664h
0x18015a32d  jz      short loc_18015A350
0x18015a32f  cmp     ebx, 1
0x18015a332  jz      short loc_18015A350
0x18015a334  movzx   r8d, bx
0x18015a338  mov     edx, 104h
0x18015a33d  lea     rcx, [rsp+278h+Buffer]
0x18015a342  call    cs:__imp_GetSystemWow64Directory2W
0x18015a349  nop     dword ptr [rax+rax+00h]
0x18015a34e  jmp     short loc_18015A366
0x18015a350  mov     edx, 104h; uSize
0x18015a355  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x18015a35a  call    cs:__imp_GetSystemDirectoryW
0x18015a361  nop     dword ptr [rax+rax+00h]
0x18015a366  test    eax, eax
0x18015a368  jnz     short loc_18015A3A8
0x18015a36a  mov     rcx, [rsp+278h]; this
0x18015a372  mov     dword ptr [rsp+278h+var_248], ebx; char *
0x18015a376  lea     rax, aFailedCallToGe; "Failed call to GetSystemDirectory/GetSy"...
0x18015a37d  mov     [rsp+278h+var_250], rax; char *
0x18015a382  lea     rax, aSystemdirector; "systemDirectoryLength == 0"
0x18015a389  mov     [rsp+278h+var_258], rax; char *
0x18015a38e  lea     r9, aOsintegrationD_35; "OSIntegration::DEH::Internal::GetSystem"...
0x18015a395  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18015a39c  mov     edx, 1F3h; void *
0x18015a3a1  call    ?Return_GetLastErrorMsg@in1diag5@details@wil@@YAJPEAXIPEBD111ZZ; wil::details::in1diag5::Return_GetLastErrorMsg(void *,uint,char const *,char const *,char const *,char const *,...)
0x18015a3a6  jmp     short loc_18015A417
0x18015a3a8  cmp     eax, 104h
0x18015a3ad  jb      short loc_18015A3B4
0x18015a3af  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "systemDirectoryLength < ARRAYSIZE(systemDirectoryCharacters)")
0x18015a3b4  xor     edx, edx
0x18015a3b6  mov     rcx, rdi
0x18015a3b9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18015a3be  mov     r9, rdi; ppszPathOut
0x18015a3c1  mov     r8d, 1; dwFlags
0x18015a3c7  mov     rdx, rsi; pszMore
0x18015a3ca  lea     rcx, [rsp+278h+Buffer]; pszPathIn
0x18015a3cf  call    cs:__imp_PathAllocCombine
0x18015a3d6  nop     dword ptr [rax+rax+00h]
0x18015a3db  mov     ebx, eax
0x18015a3dd  test    eax, eax
0x18015a3df  jns     short loc_18015A415
0x18015a3e1  mov     rcx, [rsp+278h]; this
0x18015a3e9  mov     dword ptr [rsp+278h+var_250], eax; char *
0x18015a3ed  lea     rax, aPathalloccombi; "PathAllocCombine(systemDirectoryCharact"...
0x18015a3f4  mov     [rsp+278h+var_258], rax; char *
0x18015a3f9  lea     r9, aOsintegrationD_35; "OSIntegration::DEH::Internal::GetSystem"...
0x18015a400  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18015a407  mov     edx, 1FAh; void *
0x18015a40c  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18015a411  mov     eax, ebx
0x18015a413  jmp     short loc_18015A417
0x18015a415  xor     eax, eax
0x18015a417  mov     rcx, [rsp+278h+var_28]
0x18015a41f  xor     rcx, rsp; StackCookie
0x18015a422  call    __security_check_cookie
0x18015a427  add     rsp, 260h
0x18015a42e  pop     rdi
0x18015a42f  pop     rsi
0x18015a430  pop     rbx
0x18015a431  retn
```
