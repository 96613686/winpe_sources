# Windows::TestHooks::GetTestSettings(void)

- ea: `0x180058e50`
- end: `0x180059066`
- name: `?GetTestSettings@TestHooks@Windows@@UEAA?AW4TestLevel@SystemInterface@@XZ`
- size: `534`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800209fc`
- `0x180023a18`
- `0x180058020`
- `0x180058210`
- `0x1800583a0`
- `0x180058e50`
- `0x180067558`
- `0x180071010`

## import_xrefs

- `msvcp_win!?good@ios_base@std@@QEBA_NXZ` at `0x180058ea4`
- `msvcp_win!?good@ios_base@std@@QEBA_NXZ` at `0x180058ea4`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180058ef3`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180058f2c`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180058ef3`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180058f2c`
- `msvcp_win!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180058ee5`
- `msvcp_win!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180058f1e`
- `msvcp_win!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180058ee5`
- `msvcp_win!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180058f1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058f96`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058f96`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180059005`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180059005`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058f07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058f50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059019`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058f07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058f50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059019`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180058f65`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180058f65`

## string_xrefs

- `0x180058e6c`: `%WINDIR%\System32\UsoSelfhost.dll`
- `0x180059030`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\testhooks.cpp`
- `0x180059041`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\testhooks.cpp`
- `0x180059053`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\testhooks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::TestHooks::GetTestSettings(__int64 a1)
{
  __int64 result; // rax
  bool v3; // zf
  const char *v4; // r9
  const unsigned __int16 *v5; // rdx
  bool v6; // r8
  HMODULE LibraryW; // rbx
  const char *v8; // r9
  FARPROC ProcAddress; // rax
  const char *v10; // r9
  int v11; // eax
  unsigned int v12; // esi
  int v13; // [rsp+20h] [rbp-138h]
  int v14; // [rsp+2Ch] [rbp-12Ch]
  _QWORD v15[2]; // [rsp+30h] [rbp-128h] BYREF
  _BYTE v16[8]; // [rsp+40h] [rbp-118h] BYREF
  _BYTE v17[152]; // [rsp+48h] [rbp-110h] BYREF
  _BYTE v18[120]; // [rsp+E0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]
  int v20; // [rsp+160h] [rbp+8h] BYREF
  __int16 v21; // [rsp+165h] [rbp+Dh]
  char v22; // [rsp+167h] [rbp+Fh]
  LPVOID pv; // [rsp+168h] [rbp+10h] BYREF
  HMODULE v24; // [rsp+170h] [rbp+18h]

  if ( *(_BYTE *)(a1 + 12) )
    return *(unsigned int *)(a1 + 8);
  try
  {
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
      &pv,
      L"%WINDIR%\\System32\\UsoSelfhost.dll");
    std::ifstream::ifstream(v15, pv);
    v3 = !std::ios_base::good((std::ios_base *)((char *)v15 + *(int *)(v15[0] + 4LL)));
    *(_QWORD *)((char *)v15 + *(int *)(v15[0] + 4LL)) = &std::ifstream::`vftable';
    *(int *)((char *)&v14 + *(int *)(v15[0] + 4LL)) = *(_DWORD *)(v15[0] + 4LL) - 176;
    if ( v3 )
    {
      std::filebuf::~filebuf<char,std::char_traits<char>>(v16);
      std::istream::~istream<char,std::char_traits<char>>(v17);
      std::ios::~ios<char,std::char_traits<char>>(v18);
      if ( pv )
        CoTaskMemFree(pv);
      result = 0;
    }
    else
    {
      std::filebuf::~filebuf<char,std::char_traits<char>>(v16);
      std::istream::~istream<char,std::char_traits<char>>(v17);
      std::ios::~ios<char,std::char_traits<char>>(v18);
      if ( Windows::Trust::VerifySelfSignedFile((Windows::Trust *)pv, v5, v6) )
      {
        LibraryW = LoadLibraryW((LPCWSTR)pv);
        v24 = LibraryW;
        if ( !LibraryW )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x26,
            (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\testhooks.cpp",
            v8);
        ProcAddress = GetProcAddress(LibraryW, "IsTestMode");
        if ( !ProcAddress )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x29,
            (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\testhooks.cpp",
            v10);
        v20 = 0;
        v11 = ((__int64 (__fastcall *)(int *))ProcAddress)(&v20);
        if ( v11 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2C,
            (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\testhooks.cpp",
            (const char *)(unsigned int)v11,
            v13);
        v12 = (v20 != 0) + 1;
        *(_DWORD *)(a1 + 8) = v12;
        *(_BYTE *)(a1 + 12) = 1;
        *(_WORD *)(a1 + 13) = v21;
        *(_BYTE *)(a1 + 15) = v22;
        FreeLibrary(LibraryW);
        if ( pv )
          CoTaskMemFree(pv);
        result = v12;
      }
      else
      {
        if ( pv )
          CoTaskMemFree(pv);
        result = 0;
      }
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\testhooks.cpp",
      v4);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180058e50  push    rbx
0x180058e52  push    rsi
0x180058e53  push    rdi
0x180058e54  sub     rsp, 140h
0x180058e5b  mov     rdi, rcx
0x180058e5e  cmp     byte ptr [rcx+0Ch], 0
0x180058e62  jz      short loc_180058E6C
0x180058e64  mov     eax, [rcx+8]
0x180058e67  jmp     loc_180059025
0x180058e6c  lea     rdx, aWindirSystem32; "%WINDIR%\\System32\\UsoSelfhost.dll"
0x180058e73  lea     rcx, [rsp+158h+pv]
0x180058e7b  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x180058e80  nop
0x180058e81  mov     rdx, [rsp+158h+pv]
0x180058e89  lea     rcx, [rsp+158h+var_128]
0x180058e8e  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEBGHH@Z; std::ifstream::ifstream(ushort const *,int,int)
0x180058e93  mov     rax, [rsp+158h+var_128]
0x180058e98  movsxd  rcx, dword ptr [rax+4]
0x180058e9c  lea     rax, [rsp+158h+var_128]
0x180058ea1  add     rcx, rax
0x180058ea4  call    cs:__imp_?good@ios_base@std@@QEBA_NXZ; std::ios_base::good(void)
0x180058eaa  test    al, al
0x180058eac  mov     rax, [rsp+158h+var_128]
0x180058eb1  movsxd  rcx, dword ptr [rax+4]
0x180058eb5  lea     rax, ??_7?$basic_ifstream@DU?$char_traits@D@std@@@std@@6B@; const std::ifstream::`vftable'
0x180058ebc  mov     [rsp+rcx+158h+var_128], rax
0x180058ec1  mov     rax, [rsp+158h+var_128]
0x180058ec6  movsxd  rcx, dword ptr [rax+4]
0x180058eca  lea     edx, [rcx-0B0h]
0x180058ed0  mov     [rsp+rcx+158h+var_12C], edx
0x180058ed4  lea     rcx, [rsp+158h+var_118]
0x180058ed9  jnz     short loc_180058F14
0x180058edb  call    ??1?$basic_filebuf@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::filebuf::~filebuf<char,std::char_traits<char>>(void)
0x180058ee0  lea     rcx, [rsp+158h+var_110]
0x180058ee5  call    cs:__imp_??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::istream::~istream<char,std::char_traits<char>>(void)
0x180058eeb  lea     rcx, [rsp+158h+var_78]
0x180058ef3  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x180058ef9  nop
0x180058efa  mov     rcx, [rsp+158h+pv]; pv
0x180058f02  test    rcx, rcx
0x180058f05  jz      short loc_180058F0D
0x180058f07  call    cs:__imp_CoTaskMemFree
0x180058f0d  xor     eax, eax
0x180058f0f  jmp     loc_180059025
0x180058f14  call    ??1?$basic_filebuf@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::filebuf::~filebuf<char,std::char_traits<char>>(void)
0x180058f19  lea     rcx, [rsp+158h+var_110]
0x180058f1e  call    cs:__imp_??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::istream::~istream<char,std::char_traits<char>>(void)
0x180058f24  lea     rcx, [rsp+158h+var_78]
0x180058f2c  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x180058f32  mov     rcx, [rsp+158h+pv]; this
0x180058f3a  call    ?VerifySelfSignedFile@Trust@Windows@@YA_NPEBG_N@Z; Windows::Trust::VerifySelfSignedFile(ushort const *,bool)
0x180058f3f  test    al, al
0x180058f41  jnz     short loc_180058F5D
0x180058f43  mov     rcx, [rsp+158h+pv]; pv
0x180058f4b  test    rcx, rcx
0x180058f4e  jz      short loc_180058F56
0x180058f50  call    cs:__imp_CoTaskMemFree
0x180058f56  xor     eax, eax
0x180058f58  jmp     loc_180059025
0x180058f5d  mov     rcx, [rsp+158h+pv]; lpLibFileName
0x180058f65  call    cs:__imp_LoadLibraryW
0x180058f6b  mov     rbx, rax
0x180058f6e  mov     [rsp+158h+arg_10], rax
0x180058f76  test    rax, rax
0x180058f79  setz    al
0x180058f7c  mov     rcx, [rsp+158h]; this
0x180058f84  test    al, al
0x180058f86  jnz     loc_180059030
0x180058f8c  lea     rdx, aIstestmode; "IsTestMode"
0x180058f93  mov     rcx, rbx; hModule
0x180058f96  call    cs:__imp_GetProcAddress
0x180058f9c  mov     rcx, [rsp+158h]; this
0x180058fa4  test    rax, rax
0x180058fa7  jz      loc_180059041
0x180058fad  mov     [rsp+158h+arg_0], 0
0x180058fb8  lea     rcx, [rsp+158h+arg_0]
0x180058fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058fc5  mov     rcx, [rsp+158h]; this
0x180058fcd  test    eax, eax
0x180058fcf  js      short loc_180059050
0x180058fd1  mov     eax, [rsp+158h+arg_0]
0x180058fd8  neg     eax
0x180058fda  sbb     esi, esi
0x180058fdc  neg     esi
0x180058fde  inc     esi
0x180058fe0  mov     [rdi+8], esi
0x180058fe3  mov     byte ptr [rdi+0Ch], 1
0x180058fe7  movzx   eax, [rsp+158h+arg_5]
0x180058fef  mov     [rdi+0Dh], ax
0x180058ff3  mov     al, [rsp+158h+arg_7]
0x180058ffa  mov     [rdi+0Fh], al
0x180058ffd  test    rbx, rbx
0x180059000  jz      short loc_18005900C
0x180059002  mov     rcx, rbx; hLibModule
0x180059005  call    cs:__imp_FreeLibrary
0x18005900b  nop
0x18005900c  mov     rcx, [rsp+158h+pv]; pv
0x180059014  test    rcx, rcx
0x180059017  jz      short loc_18005901F
0x180059019  call    cs:__imp_CoTaskMemFree
0x18005901f  mov     eax, esi
0x180059021  jmp     short loc_180059025
0x180059023  xor     eax, eax
0x180059025  add     rsp, 140h
0x18005902c  pop     rdi
0x18005902d  pop     rsi
0x18005902e  pop     rbx
0x18005902f  retn
0x180059030  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180059037  mov     edx, 26h ; '&'; void *
0x18005903c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180059041  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180059048  lea     edx, [rax+29h]; void *
0x18005904b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180059050  mov     r9d, eax; char *
0x180059053  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005905a  mov     edx, 2Ch ; ','; void *
0x18005905f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
