# Windows::Registry::SystemValueExists(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x180023570`
- end: `0x1800236e4`
- name: `?SystemValueExists@Registry@Windows@@UEAA_NV?$basic_zstring_view@_W@wil@@00@Z`
- size: `372`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x180009380`
- `0x180023570`
- `0x18003c020`
- `0x18003df70`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023602`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800236ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023602`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800236ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800235eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800235eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023661`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023661`

## string_xrefs

- `0x180023637`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x180023691`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Windows::Registry::SystemValueExists(__int64 a1, __int128 *a2, __int128 *a3, __int128 *a4)
{
  __int128 v4; // xmm6
  char v5; // bl
  const WCHAR *v6; // rdx
  unsigned int v7; // eax
  const char *v8; // r9
  LPCWSTR *v9; // rax
  unsigned int Value; // eax
  const char *v11; // r9
  LPCWSTR *v12; // rax
  __int128 v14; // [rsp+48h] [rbp-19h] BYREF
  __int128 v15; // [rsp+58h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+7h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+70h] [rbp+Fh] BYREF
  unsigned __int64 v18; // [rsp+88h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]

  v4 = *a4;
  v14 = *a3;
  v15 = *a2;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, lpSubKey, &v15, &v14);
  v5 = 0;
  hKey = 0;
  v6 = (const WCHAR *)lpSubKey;
  if ( v18 > 7 )
    v6 = lpSubKey[0];
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey);
  v8 = (const char *)v7;
  if ( v7 == 2 )
    goto LABEL_4;
  v9 = lpSubKey;
  if ( v18 > 7 )
    v9 = (LPCWSTR *)lpSubKey[0];
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0xA3,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
    v8,
    (unsigned int)"%ws[%ws]",
    (const char *)v9,
    (_QWORD)v4);
  Value = RegQueryValueExW(hKey, (LPCWSTR)v4, 0, 0, 0, 0);
  v11 = (const char *)Value;
  if ( Value == 2 )
  {
LABEL_4:
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    v12 = lpSubKey;
    if ( v18 > 7 )
      v12 = (LPCWSTR *)lpSubKey[0];
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0xB0,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
      v11,
      (unsigned int)"%ws[%ws]",
      (const char *)v12,
      (_QWORD)v4);
    if ( hKey )
      RegCloseKey(hKey);
    v5 = 1;
  }
  std::wstring::~wstring(lpSubKey);
  return v5;
}

```

## disassembly

```asm
0x180023570  mov     rax, rsp
0x180023573  mov     [rax+8], rbx
0x180023577  push    rbp
0x180023578  push    rsi
0x180023579  push    rdi
0x18002357a  lea     rbp, [rax-5Fh]
0x18002357e  sub     rsp, 0A0h
0x180023585  movaps  xmmword ptr [rax-28h], xmm6
0x180023589  mov     rax, cs:__security_cookie
0x180023590  xor     rax, rsp
0x180023593  mov     [rbp+57h+var_28], rax
0x180023597  movups  xmm6, xmmword ptr [r9]
0x18002359b  movups  xmm0, xmmword ptr [r8]
0x18002359f  movdqu  [rbp+57h+var_70], xmm0
0x1800235a4  movups  xmm1, xmmword ptr [rdx]
0x1800235a7  movdqu  [rbp+57h+var_60], xmm1
0x1800235ac  lea     r9, [rbp+57h+var_70]
0x1800235b0  lea     r8, [rbp+57h+var_60]
0x1800235b4  lea     rdx, [rbp+57h+lpSubKey]
0x1800235b8  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x1800235bd  nop
0x1800235be  xor     ebx, ebx
0x1800235c0  mov     [rbp+57h+hKey], rbx
0x1800235c4  lea     rdx, [rbp+57h+lpSubKey]
0x1800235c8  cmp     [rbp+57h+var_30], 7
0x1800235cd  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800235d2  lea     rax, [rbp+57h+hKey]
0x1800235d6  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800235db  mov     r9d, 20019h; samDesired
0x1800235e1  xor     r8d, r8d; ulOptions
0x1800235e4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800235eb  call    cs:__imp_RegOpenKeyExW
0x1800235f1  mov     r9d, eax; char *
0x1800235f4  cmp     eax, 2
0x1800235f7  jnz     short loc_18002360E
0x1800235f9  mov     rcx, [rbp+57h+hKey]; hKey
0x1800235fd  test    rcx, rcx
0x180023600  jz      short loc_180023609
0x180023602  call    cs:__imp_RegCloseKey
0x180023608  nop
0x180023609  jmp     loc_1800236B5
0x18002360e  lea     rax, [rbp+57h+lpSubKey]
0x180023612  cmp     [rbp+57h+var_30], 7
0x180023617  cmova   rax, [rbp+57h+lpSubKey]
0x18002361c  mov     rcx, [rbp+5Fh]; this
0x180023620  movq    [rsp+0B0h+var_80], xmm6
0x180023626  mov     [rsp+0B0h+lpcbData], rax; char *
0x18002362b  lea     rsi, aWsWs_0; "%ws[%ws]"
0x180023632  mov     [rsp+0B0h+phkResult], rsi; unsigned int
0x180023637  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18002363e  mov     edx, 0A3h; void *
0x180023643  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180023648  mov     [rsp+0B0h+lpcbData], rbx; lpcbData
0x18002364d  mov     [rsp+0B0h+phkResult], rbx; lpData
0x180023652  xor     r9d, r9d; lpType
0x180023655  xor     r8d, r8d; lpReserved
0x180023658  movq    rdx, xmm6; lpValueName
0x18002365d  mov     rcx, [rbp+57h+hKey]; hKey
0x180023661  call    cs:__imp_RegQueryValueExW
0x180023667  mov     r9d, eax; char *
0x18002366a  cmp     eax, 2
0x18002366d  jz      short loc_1800235F9
0x18002366f  lea     rax, [rbp+57h+lpSubKey]
0x180023673  cmp     [rbp+57h+var_30], 7
0x180023678  cmova   rax, [rbp+57h+lpSubKey]
0x18002367d  mov     rcx, [rbp+5Fh]; this
0x180023681  movq    [rsp+0B0h+var_80], xmm6
0x180023687  mov     [rsp+0B0h+lpcbData], rax; char *
0x18002368c  mov     [rsp+0B0h+phkResult], rsi; unsigned int
0x180023691  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180023698  mov     edx, 0B0h; void *
0x18002369d  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800236a2  nop
0x1800236a3  mov     rcx, [rbp+57h+hKey]; hKey
0x1800236a7  test    rcx, rcx
0x1800236aa  jz      short loc_1800236B3
0x1800236ac  call    cs:__imp_RegCloseKey
0x1800236b2  nop
0x1800236b3  mov     bl, 1
0x1800236b5  lea     rcx, [rbp+57h+lpSubKey]; void *
0x1800236b9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800236be  mov     al, bl
0x1800236c0  mov     rcx, [rbp+57h+var_28]
0x1800236c4  xor     rcx, rsp; StackCookie
0x1800236c7  call    __security_check_cookie
0x1800236cc  lea     r11, [rsp+0B0h+var_10]
0x1800236d4  mov     rbx, [r11+20h]
0x1800236d8  movaps  xmm6, xmmword ptr [r11-10h]
0x1800236dd  mov     rsp, r11
0x1800236e0  pop     rdi
0x1800236e1  pop     rsi
0x1800236e2  pop     rbp
0x1800236e3  retn
```
