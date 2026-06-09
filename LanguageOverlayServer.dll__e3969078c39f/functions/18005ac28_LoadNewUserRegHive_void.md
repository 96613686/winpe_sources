# LoadNewUserRegHive(void)

- ea: `0x18005ac28`
- end: `0x18005ad37`
- name: `?LoadNewUserRegHive@@YAJXZ`
- size: `271`
- prototype: `int(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180042b24`
- `0x18005c350`

## callees

- `0x180003a00`
- `0x1800044b8`
- `0x180009064`
- `0x180009084`
- `0x1800099c4`
- `0x1800166e0`
- `0x18005ac28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18005aca1`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18005aca1`
- `USERENV!GetDefaultUserProfileDirectoryW` at `0x18005ac67`
- `USERENV!GetDefaultUserProfileDirectoryW` at `0x18005ac67`

## string_xrefs

- `0x18005ac79`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemutils.cpp`
- `0x18005acb3`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemutils.cpp`
- `0x18005ace8`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemutils.cpp`
- `0x18005ad04`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int LoadNewUserRegHive(void)
{
  unsigned __int64 v0; // rdx
  const char *v1; // r9
  int LastError; // ebx
  unsigned int KeyW; // eax
  int v5; // eax
  DWORD cchSize[4]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR ProfileDir[264]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  memset_0(ProfileDir, 0, 0x208u);
  cchSize[0] = 260;
  if ( !GetDefaultUserProfileDirectoryW(ProfileDir, cchSize) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x49,
                  (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemutils.cpp",
                  v1);
    if ( LastError >= 0 )
      goto LABEL_3;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemutils.cpp",
      (const char *)(unsigned int)LastError,
      cchSize[0]);
    return LastError;
  }
  v5 = StringCchCatW(ProfileDir, v0, L"\\NTUSER.DAT");
  LastError = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemutils.cpp",
      (const char *)(unsigned int)v5,
      cchSize[0]);
    goto LABEL_7;
  }
LABEL_3:
  KeyW = RegLoadKeyW(HKEY_USERS, L"NewUserDefaultHive", ProfileDir);
  if ( KeyW )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x53,
             (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemutils.cpp",
             (const char *)KeyW,
             cchSize[0]);
  else
    return 0;
}

```

## disassembly

```asm
0x18005ac28  push    rbx
0x18005ac2a  sub     rsp, 250h
0x18005ac31  mov     rax, cs:__security_cookie
0x18005ac38  xor     rax, rsp
0x18005ac3b  mov     [rsp+258h+var_18], rax
0x18005ac43  xor     edx, edx; Val
0x18005ac45  lea     rcx, [rsp+258h+ProfileDir]; void *
0x18005ac4a  mov     r8d, 208h; Size
0x18005ac50  call    memset_0
0x18005ac55  lea     rdx, [rsp+258h+cchSize]; lpcchSize
0x18005ac5a  mov     [rsp+258h+cchSize], 104h; int
0x18005ac62  lea     rcx, [rsp+258h+ProfileDir]; lpProfileDir
0x18005ac67  call    cs:__imp_GetDefaultUserProfileDirectoryW
0x18005ac6d  test    eax, eax
0x18005ac6f  jnz     short loc_18005ACC9
0x18005ac71  mov     rcx, [rsp+258h]; this
0x18005ac79  lea     r8, aOnecoreBaseLan_0; "onecore\\base\\languageoverlay\\service"...
0x18005ac80  lea     edx, [rax+49h]; void *
0x18005ac83  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005ac88  mov     ebx, eax
0x18005ac8a  test    eax, eax
0x18005ac8c  js      short loc_18005ACFC
0x18005ac8e  lea     r8, [rsp+258h+ProfileDir]; lpFile
0x18005ac93  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18005ac9a  lea     rdx, SubKey; "NewUserDefaultHive"
0x18005aca1  call    cs:__imp_RegLoadKeyW
0x18005aca7  test    eax, eax
0x18005aca9  jz      short loc_18005AD1C
0x18005acab  mov     rcx, [rsp+258h]; this
0x18005acb3  lea     r8, aOnecoreBaseLan_0; "onecore\\base\\languageoverlay\\service"...
0x18005acba  mov     r9d, eax; char *
0x18005acbd  mov     edx, 53h ; 'S'; void *
0x18005acc2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005acc7  jmp     short loc_18005AD1E
0x18005acc9  lea     r8, aNtuserDat; "\\NTUSER.DAT"
0x18005acd0  lea     rcx, [rsp+258h+ProfileDir]; unsigned __int16 *
0x18005acd5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005acda  mov     ebx, eax
0x18005acdc  test    eax, eax
0x18005acde  jns     short loc_18005AC8E
0x18005ace0  mov     rcx, [rsp+258h]; this
0x18005ace8  lea     r8, aOnecoreBaseLan_0; "onecore\\base\\languageoverlay\\service"...
0x18005acef  mov     r9d, eax; char *
0x18005acf2  mov     edx, 4Ah ; 'J'; void *
0x18005acf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005acfc  mov     rcx, [rsp+258h]; this
0x18005ad04  lea     r8, aOnecoreBaseLan_0; "onecore\\base\\languageoverlay\\service"...
0x18005ad0b  mov     r9d, ebx; char *
0x18005ad0e  mov     edx, 52h ; 'R'; void *
0x18005ad13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ad18  mov     eax, ebx
0x18005ad1a  jmp     short loc_18005AD1E
0x18005ad1c  xor     eax, eax
0x18005ad1e  mov     rcx, [rsp+258h+var_18]
0x18005ad26  xor     rcx, rsp; StackCookie
0x18005ad29  call    __security_check_cookie
0x18005ad2e  add     rsp, 250h
0x18005ad35  pop     rbx
0x18005ad36  retn
```
