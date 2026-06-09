# UserOOBEController::s_CleanupNetworkCredentials(void)

- ea: `0x180027efc`
- end: `0x180027fa7`
- name: `?s_CleanupNetworkCredentials@UserOOBEController@@CAJXZ`
- size: `171`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180029260`

## callees

- `0x180014468`
- `0x180027efc`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180027f15`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180027f65`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180027f15`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180027f65`

## string_xrefs

- `0x180027f2c`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180027f7c`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
__int64 UserOOBEController::s_CleanupNetworkCredentials(void)
{
  int v0; // eax
  int v1; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v0 = SHDeleteValueW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Wlansvc\\UserData", L"Profiles");
  if ( v0 > 0 )
    v0 = (unsigned __int16)v0 | 0x80070000;
  wil::details::in1diag3::Log_IfFailedWithExpected(
    retaddr,
    (void *)0xE7,
    (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
    (const char *)(unsigned int)v0,
    1,
    0x80070002);
  v1 = SHDeleteValueW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ProxyProperties",
         L"ProxyProperties");
  if ( v1 > 0 )
    v1 = (unsigned __int16)v1 | 0x80070000;
  wil::details::in1diag3::Log_IfFailedWithExpected(
    retaddr,
    (void *)0xEA,
    (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
    (const char *)(unsigned int)v1,
    1,
    0x80070002);
  return 0;
}

```

## disassembly

```asm
0x180027efc  sub     rsp, 38h
0x180027f00  lea     r8, aProfiles; "Profiles"
0x180027f07  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180027f0e  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Wlansvc\\UserData"
0x180027f15  call    cs:__imp_SHDeleteValueW
0x180027f1b  test    eax, eax
0x180027f1d  jle     short loc_180027F27
0x180027f1f  movzx   eax, ax
0x180027f22  or      eax, 80070000h
0x180027f27  mov     rcx, [rsp+38h]; this
0x180027f2c  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180027f33  mov     [rsp+38h+var_10], 80070002h; unsigned int
0x180027f3b  mov     r9d, eax; char *
0x180027f3e  mov     edx, 0E7h; void *
0x180027f43  mov     [rsp+38h+var_18], 1; int
0x180027f4b  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180027f50  lea     r8, aProxypropertie; "ProxyProperties"
0x180027f57  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180027f5e  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180027f65  call    cs:__imp_SHDeleteValueW
0x180027f6b  test    eax, eax
0x180027f6d  jle     short loc_180027F77
0x180027f6f  movzx   eax, ax
0x180027f72  or      eax, 80070000h
0x180027f77  mov     rcx, [rsp+38h]; this
0x180027f7c  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180027f83  mov     [rsp+38h+var_10], 80070002h; unsigned int
0x180027f8b  mov     r9d, eax; char *
0x180027f8e  mov     edx, 0EAh; void *
0x180027f93  mov     [rsp+38h+var_18], 1; int
0x180027f9b  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180027fa0  xor     eax, eax
0x180027fa2  add     rsp, 38h
0x180027fa6  retn
```
