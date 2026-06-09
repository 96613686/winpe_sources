# DeleteLanguageOperationStateInRegistry(ushort const *,LanguageOperationState)

- ea: `0x180035dbc`
- end: `0x180035f27`
- name: `?DeleteLanguageOperationStateInRegistry@@YAJPEBGW4LanguageOperationState@@@Z`
- size: `363`
- prototype: `int __high(const unsigned __int16 *, enum LanguageOperationState)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180020f60`

## callees

- `0x180009084`
- `0x1800166e0`
- `0x180035dbc`
- `0x18005f678`
- `0x180060320`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035e16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035e69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035e83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035e94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035ede`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035eef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035efc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035f0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035e16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035e69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035e83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035e94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035ede`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035eef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035efc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035f0d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180035eb6`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180035eb6`

## string_xrefs

- `0x180035ea1`: `EnableLanguageFeatureInstallations`
- `0x180035eaa`: `CopyToDeviceInternationalSettings`
- `0x180035dfa`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180035e4d`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180035ec8`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeleteLanguageOperationStateInRegistry(__int64 a1, int a2)
{
  const char *v4; // r9
  __int64 result; // rax
  HKEY v6; // rbx
  int v7; // edi
  const WCHAR *v8; // r8
  unsigned int v9; // eax
  unsigned int v10; // edi
  unsigned int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HKEY hKey; // [rsp+40h] [rbp+18h]
  HKEY v14; // [rsp+48h] [rbp+20h] BYREF

  try
  {
    TryOpenLanguageOverlayKey();
    if ( !hKey )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x223,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
        (const char *)0x80070003LL,
        v11);
      return 2147942403LL;
    }
    TryOpenRegKey(&v14, hKey, a1, 983103);
    v6 = v14;
    if ( !v14 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x228,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
        (const char *)0x80070003LL,
        v11);
      if ( hKey )
        RegCloseKey(hKey);
      return 2147942403LL;
    }
    v7 = a2 - 2;
    if ( v7 )
    {
      if ( v7 != 1 )
      {
        RegCloseKey(v14);
        if ( hKey )
          RegCloseKey(hKey);
        return 2147942487LL;
      }
      v8 = L"EnableLanguageFeatureInstallations";
    }
    else
    {
      v8 = L"CopyToDeviceInternationalSettings";
    }
    v9 = RegDeleteKeyValueW(v14, 0, v8);
    if ( v9 )
    {
      v10 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x237,
              (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
              (const char *)v9,
              v11);
      RegCloseKey(v6);
      if ( hKey )
        RegCloseKey(hKey);
      result = v10;
    }
    else
    {
      RegCloseKey(v6);
      if ( hKey )
        RegCloseKey(hKey);
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x23A,
                           (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\language"
                                         "providerutils.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x180035dbc  mov     [rsp+arg_0], rbx
0x180035dc1  push    rdi; unsigned int
0x180035dc2  sub     rsp, 20h
0x180035dc6  mov     edi, edx
0x180035dc8  mov     rbx, rcx
0x180035dcb  mov     r9d, 0F003Fh
0x180035dd1  lea     r8, aOperations; "Operations"
0x180035dd8  lea     rcx, [rsp+28h+hKey]
0x180035ddd  call    ?TryOpenLanguageOverlayKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4LanguageOverlayHive@@PEBGK@Z; TryOpenLanguageOverlayKey(LanguageOverlayHive,ushort const *,ulong)
0x180035de2  nop
0x180035de3  mov     rdx, [rsp+28h+hKey]
0x180035de8  test    rdx, rdx
0x180035deb  jnz     short loc_180035E23
0x180035ded  mov     rcx, [rsp+28h]; this
0x180035df2  mov     ebx, 80070003h
0x180035df7  mov     r9d, ebx; char *
0x180035dfa  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180035e01  mov     edx, 223h; void *
0x180035e06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035e0b  nop
0x180035e0c  mov     rcx, [rsp+28h+hKey]; hKey
0x180035e11  test    rcx, rcx
0x180035e14  jz      short loc_180035E1C
0x180035e16  call    cs:__imp_RegCloseKey
0x180035e1c  mov     eax, ebx
0x180035e1e  jmp     loc_180035F1B
0x180035e23  mov     r9d, 0F003Fh
0x180035e29  mov     r8, rbx
0x180035e2c  lea     rcx, [rsp+28h+arg_18]
0x180035e31  call    ?TryOpenRegKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBGK@Z; TryOpenRegKey(HKEY__ *,ushort const *,ulong)
0x180035e36  mov     rbx, [rsp+28h+arg_18]
0x180035e3b  test    rbx, rbx
0x180035e3e  jnz     short loc_180035E76
0x180035e40  mov     rcx, [rsp+28h]; this
0x180035e45  mov     ebx, 80070003h
0x180035e4a  mov     r9d, ebx; char *
0x180035e4d  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180035e54  mov     edx, 228h; void *
0x180035e59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035e5e  nop
0x180035e5f  mov     rcx, [rsp+28h+hKey]; hKey
0x180035e64  test    rcx, rcx
0x180035e67  jz      short loc_180035E6F
0x180035e69  call    cs:__imp_RegCloseKey
0x180035e6f  mov     eax, ebx
0x180035e71  jmp     loc_180035F1B
0x180035e76  sub     edi, 2
0x180035e79  jz      short loc_180035EAA
0x180035e7b  cmp     edi, 1
0x180035e7e  jz      short loc_180035EA1
0x180035e80  mov     rcx, rbx; hKey
0x180035e83  call    cs:__imp_RegCloseKey
0x180035e89  nop
0x180035e8a  mov     rcx, [rsp+28h+hKey]; hKey
0x180035e8f  test    rcx, rcx
0x180035e92  jz      short loc_180035E9A
0x180035e94  call    cs:__imp_RegCloseKey
0x180035e9a  mov     eax, 80070057h
0x180035e9f  jmp     short loc_180035F1B
0x180035ea1  lea     r8, aEnablelanguage; "EnableLanguageFeatureInstallations"
0x180035ea8  jmp     short loc_180035EB1
0x180035eaa  lea     r8, ValueName; "CopyToDeviceInternationalSettings"
0x180035eb1  xor     edx, edx; lpSubKey
0x180035eb3  mov     rcx, rbx; hKey
0x180035eb6  call    cs:__imp_RegDeleteKeyValueW
0x180035ebc  test    eax, eax
0x180035ebe  jz      short loc_180035EF9
0x180035ec0  mov     rcx, [rsp+28h]; this
0x180035ec5  mov     r9d, eax; char *
0x180035ec8  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180035ecf  mov     edx, 237h; void *
0x180035ed4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035ed9  mov     edi, eax
0x180035edb  mov     rcx, rbx; hKey
0x180035ede  call    cs:__imp_RegCloseKey
0x180035ee4  nop
0x180035ee5  mov     rcx, [rsp+28h+hKey]; hKey
0x180035eea  test    rcx, rcx
0x180035eed  jz      short loc_180035EF5
0x180035eef  call    cs:__imp_RegCloseKey
0x180035ef5  mov     eax, edi
0x180035ef7  jmp     short loc_180035F1B
0x180035ef9  mov     rcx, rbx; hKey
0x180035efc  call    cs:__imp_RegCloseKey
0x180035f02  nop
0x180035f03  mov     rcx, [rsp+28h+hKey]; hKey
0x180035f08  test    rcx, rcx
0x180035f0b  jz      short loc_180035F13
0x180035f0d  call    cs:__imp_RegCloseKey
0x180035f13  xor     eax, eax
0x180035f15  jmp     short loc_180035F1B
0x180035f17  mov     eax, dword ptr [rsp+28h+hKey]
0x180035f1b  mov     rbx, [rsp+28h+arg_0]
0x180035f20  add     rsp, 20h
0x180035f24  pop     rdi
0x180035f25  retn
```
