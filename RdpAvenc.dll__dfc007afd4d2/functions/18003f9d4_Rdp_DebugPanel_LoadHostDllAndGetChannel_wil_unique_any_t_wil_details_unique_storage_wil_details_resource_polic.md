# Rdp::DebugPanel::LoadHostDllAndGetChannel(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &,wil::com_ptr_t<Rdp::DebugPanel::IDebugPanelChannel,wil::err_exception_policy> &)

- ea: `0x18003f9d4`
- end: `0x18003fc04`
- name: `?LoadHostDllAndGetChannel@DebugPanel@Rdp@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$com_ptr_t@UIDebugPanelChannel@DebugPanel@Rdp@@Uerr_exception_policy@wil@@@4@@Z`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003fc50`

## callees

- `0x180006580`
- `0x180007018`
- `0x18000aaf4`
- `0x180018d88`
- `0x18003eea4`
- `0x18003f9d4`
- `0x18003fc0c`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18003fac3`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18003fac3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003fb3d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003fb3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18003fa9c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18003fa9c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003fa5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003fa5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003fb6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003fb6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fb45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fb45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb32`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18003fb21`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18003fb21`

## string_xrefs

- `0x18003fad4`: `DebugPanelHost.dll`
- `0x18003fb53`: `Failed to load DebugPanelHost dll`
- `0x18003faee`: `StringCchCat of file path failed`
- `0x18003fb7a`: `Failed to get ClassFactory address from DebugPanelHost.dll.`
- `0x18003fbc4`: `Failed to get IDebugPanelChannel interface from DebugPanelHost.dll.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::DebugPanel::LoadHostDllAndGetChannel(HMODULE *a1, __int64 *a2)
{
  const char *v4; // r9
  __int64 v5; // rdx
  wchar_t *v7; // rax
  int v8; // ebx
  const char *v9; // rax
  __int64 v10; // rdx
  HMODULE LibraryW; // rdi
  HMODULE v12; // rsi
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rbx
  __int64 v15; // rcx
  const char *v16; // [rsp+20h] [rbp-E0h]
  const char *v17; // [rsp+28h] [rbp-D8h]
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  HMODULE phModule; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v18 = 0;
  if ( (int)wil::reg::get_value_nothrow<unsigned long,0>(a1, a2, L"DSEnableDebugPanelHost", &v18) < 0 || !v18 )
    return 2147500037LL;
  phModule = 0;
  memset_0(Filename, 0, 0x20Au);
  if ( !GetModuleHandleExW(6u, &word_18008F93C, &phModule) )
  {
    v4 = "Failed to get module handle to itself.";
    v5 = 51;
    return wil::details::in1diag3::Return_GetLastErrorMsg(
             retaddr,
             (void *)v5,
             (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\debugpanelhost\\inc\\DebugPanelHostLoader.h",
             v4,
             v16);
  }
  if ( GetModuleFileNameW(phModule, Filename, 0x105u) - 1 > 0x103 )
  {
    v4 = "Failed to get the module file name";
    v5 = 54;
    return wil::details::in1diag3::Return_GetLastErrorMsg(
             retaddr,
             (void *)v5,
             (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\debugpanelhost\\inc\\DebugPanelHostLoader.h",
             v4,
             v16);
  }
  v7 = wcsrchr(Filename, 0x5Cu);
  if ( v7 )
    v7[1] = 0;
  v8 = StringCchCatW(Filename, 0x105u, L"DebugPanelHost.dll");
  if ( v8 < 0 )
  {
    v9 = "StringCchCat of file path failed";
    v10 = 64;
LABEL_12:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\debugpanelhost\\inc\\DebugPanelHostLoader.h",
      (const char *)(unsigned int)v8,
      (int)v9,
      v17);
    return (unsigned int)v8;
  }
  LibraryW = LoadLibraryW(Filename);
  v12 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    FreeLibrary(v12);
    SetLastError(LastError);
  }
  *a1 = LibraryW;
  if ( !LibraryW )
  {
    v4 = "Failed to load DebugPanelHost dll";
    v5 = 67;
    return wil::details::in1diag3::Return_GetLastErrorMsg(
             retaddr,
             (void *)v5,
             (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\debugpanelhost\\inc\\DebugPanelHostLoader.h",
             v4,
             v16);
  }
  ProcAddress = GetProcAddress(LibraryW, "ClassFactory");
  if ( !ProcAddress )
  {
    v4 = "Failed to get ClassFactory address from DebugPanelHost.dll.";
    v5 = 71;
    return wil::details::in1diag3::Return_GetLastErrorMsg(
             retaddr,
             (void *)v5,
             (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\debugpanelhost\\inc\\DebugPanelHostLoader.h",
             v4,
             v16);
  }
  v15 = *a2;
  *a2 = 0;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  v8 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(
         &CLSID_DebugPanelChannel,
         &GUID_2a2ae89c_51e7_4841_aea1_06f7c1577025,
         a2);
  if ( v8 < 0 )
  {
    v9 = "Failed to get IDebugPanelChannel interface from DebugPanelHost.dll.";
    v10 = 74;
    goto LABEL_12;
  }
  return 0;
}

```

## disassembly

```asm
0x18003f9d4  mov     [rsp-8+arg_10], rbx
0x18003f9d9  push    rbp
0x18003f9da  push    rsi
0x18003f9db  push    rdi
0x18003f9dc  push    r14
0x18003f9de  push    r15
0x18003f9e0  lea     rbp, [rsp-160h]
0x18003f9e8  sub     rsp, 260h
0x18003f9ef  mov     rax, cs:__security_cookie
0x18003f9f6  xor     rax, rsp
0x18003f9f9  mov     [rbp+180h+var_30], rax
0x18003fa00  mov     r14, rdx
0x18003fa03  mov     r15, rcx
0x18003fa06  mov     [rsp+280h+var_250], 0
0x18003fa0e  lea     r9, [rsp+280h+var_250]
0x18003fa13  lea     r8, aDsenabledebugp; "DSEnableDebugPanelHost"
0x18003fa1a  call    ??$get_value_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18003fa1f  test    eax, eax
0x18003fa21  js      loc_18003FBD9
0x18003fa27  cmp     [rsp+280h+var_250], 0
0x18003fa2c  jz      loc_18003FBD9
0x18003fa32  mov     [rsp+280h+phModule], 0
0x18003fa3b  xor     edx, edx; Val
0x18003fa3d  mov     r8d, 20Ah; Size
0x18003fa43  lea     rcx, [rsp+280h+Filename]; void *
0x18003fa48  call    memset_0
0x18003fa4d  lea     r8, [rsp+280h+phModule]; phModule
0x18003fa52  lea     rdx, word_18008F93C; lpModuleName
0x18003fa59  mov     ecx, 6; dwFlags
0x18003fa5e  call    cs:__imp_GetModuleHandleExW
0x18003fa64  test    eax, eax
0x18003fa66  jnz     short loc_18003FA8A
0x18003fa68  lea     r9, aFailedToGetMod; "Failed to get module handle to itself."
0x18003fa6f  lea     edx, [rax+33h]; void *
0x18003fa72  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\debu"...
0x18003fa79  mov     rcx, [rbp+188h]; this
0x18003fa80  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18003fa85  jmp     loc_18003FBDE
0x18003fa8a  mov     ebx, 105h
0x18003fa8f  mov     r8d, ebx; nSize
0x18003fa92  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18003fa97  mov     rcx, [rsp+280h+phModule]; hModule
0x18003fa9c  call    cs:__imp_GetModuleFileNameW
0x18003faa2  dec     eax
0x18003faa4  cmp     eax, 103h
0x18003faa9  jbe     short loc_18003FAB9
0x18003faab  lea     r9, aFailedToGetThe; "Failed to get the module file name"
0x18003fab2  mov     edx, 36h ; '6'
0x18003fab7  jmp     short loc_18003FA72
0x18003fab9  mov     edx, 5Ch ; '\'; Ch
0x18003fabe  lea     rcx, [rsp+280h+Filename]; Str
0x18003fac3  call    cs:__imp_wcsrchr
0x18003fac9  test    rax, rax
0x18003facc  jz      short loc_18003FAD4
0x18003face  xor     ecx, ecx
0x18003fad0  mov     [rax+2], cx
0x18003fad4  lea     r8, aDebugpanelhost; "DebugPanelHost.dll"
0x18003fadb  mov     rdx, rbx; unsigned __int64
0x18003fade  lea     rcx, [rsp+280h+Filename]; unsigned __int16 *
0x18003fae3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003fae8  mov     ebx, eax
0x18003faea  test    eax, eax
0x18003faec  jns     short loc_18003FB1C
0x18003faee  lea     rax, aStringcchcatOf; "StringCchCat of file path failed"
0x18003faf5  mov     edx, 40h ; '@'; void *
0x18003fafa  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\debu"...
0x18003fb01  mov     r9d, ebx; char *
0x18003fb04  mov     qword ptr [rsp+280h+var_260], rax; int
0x18003fb09  mov     rcx, [rbp+188h]; this
0x18003fb10  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003fb15  mov     eax, ebx
0x18003fb17  jmp     loc_18003FBDE
0x18003fb1c  lea     rcx, [rsp+280h+Filename]; lpLibFileName
0x18003fb21  call    cs:__imp_LoadLibraryW
0x18003fb27  mov     rdi, rax
0x18003fb2a  mov     rsi, [r15]
0x18003fb2d  test    rsi, rsi
0x18003fb30  jz      short loc_18003FB4B
0x18003fb32  call    cs:__imp_GetLastError
0x18003fb38  mov     ebx, eax
0x18003fb3a  mov     rcx, rsi; hLibModule
0x18003fb3d  call    cs:__imp_FreeLibrary
0x18003fb43  mov     ecx, ebx; dwErrCode
0x18003fb45  call    cs:__imp_SetLastError
0x18003fb4b  mov     [r15], rdi
0x18003fb4e  test    rdi, rdi
0x18003fb51  jnz     short loc_18003FB62
0x18003fb53  lea     r9, aFailedToLoadDe; "Failed to load DebugPanelHost dll"
0x18003fb5a  lea     edx, [rdi+43h]
0x18003fb5d  jmp     loc_18003FA72
0x18003fb62  lea     rdx, aClassfactory_0; "ClassFactory"
0x18003fb69  mov     rcx, rdi; hModule
0x18003fb6c  call    cs:__imp_GetProcAddress
0x18003fb72  mov     rbx, rax
0x18003fb75  test    rax, rax
0x18003fb78  jnz     short loc_18003FB89
0x18003fb7a  lea     r9, aFailedToGetCla; "Failed to get ClassFactory address from"...
0x18003fb81  lea     edx, [rax+47h]
0x18003fb84  jmp     loc_18003FA72
0x18003fb89  mov     rcx, [r14]
0x18003fb8c  mov     qword ptr [r14], 0
0x18003fb93  test    rcx, rcx
0x18003fb96  jz      short loc_18003FBA5
0x18003fb98  mov     rax, [rcx]
0x18003fb9b  mov     rax, [rax+10h]
0x18003fb9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fba4  nop
0x18003fba5  mov     r8, r14
0x18003fba8  lea     rdx, _GUID_2a2ae89c_51e7_4841_aea1_06f7c1577025
0x18003fbaf  lea     rcx, CLSID_DebugPanelChannel
0x18003fbb6  mov     rax, rbx
0x18003fbb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fbbe  mov     ebx, eax
0x18003fbc0  test    eax, eax
0x18003fbc2  jns     short loc_18003FBD5
0x18003fbc4  lea     rax, aFailedToGetIde; "Failed to get IDebugPanelChannel interf"...
0x18003fbcb  mov     edx, 4Ah ; 'J'
0x18003fbd0  jmp     loc_18003FAFA
0x18003fbd5  xor     eax, eax
0x18003fbd7  jmp     short loc_18003FBDE
0x18003fbd9  mov     eax, 80004005h
0x18003fbde  mov     rcx, [rbp+180h+var_30]
0x18003fbe5  xor     rcx, rsp; StackCookie
0x18003fbe8  call    __security_check_cookie
0x18003fbed  mov     rbx, [rsp+280h+arg_10]
0x18003fbf5  add     rsp, 260h
0x18003fbfc  pop     r15
0x18003fbfe  pop     r14
0x18003fc00  pop     rdi
0x18003fc01  pop     rsi
0x18003fc02  pop     rbp
0x18003fc03  retn
```
