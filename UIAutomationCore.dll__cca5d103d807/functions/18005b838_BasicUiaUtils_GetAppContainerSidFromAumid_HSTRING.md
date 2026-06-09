# BasicUiaUtils::GetAppContainerSidFromAumid(HSTRING__ *)

- ea: `0x18005b838`
- end: `0x18005b9b6`
- name: `?GetAppContainerSidFromAumid@BasicUiaUtils@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHSTRING__@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005b494`

## callees

- `0x180032724`
- `0x18005b838`
- `0x18005bad0`
- `0x1800dbd88`
- `0x1801e8320`
- `0x1801e9258`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005b97a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005b97a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b969`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b969`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18005b8ce`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18005b8ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005b8ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005b8ad`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005b940`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005b940`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x18005b907`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x18005b907`

## string_xrefs

- `0x18005b8e2`: `onecore\windows\accessibletech\common\basicuiautils.cpp`
- `0x18005b91b`: `onecore\windows\accessibletech\common\basicuiautils.cpp`
- `0x18005b9a4`: `onecore\windows\accessibletech\common\basicuiautils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void *__fastcall BasicUiaUtils::GetAppContainerSidFromAumid(void *a1, HSTRING a2)
{
  const WCHAR *StringRawBuffer; // rax
  LONG v5; // eax
  int v6; // eax
  const char *v7; // r9
  int packageRelativeApplicationId; // [rsp+20h] [rbp-E0h]
  PSID Sid; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+38h] [rbp-C8h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+3Ch] [rbp-C4h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR packageFamilyName[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v15[140]; // [rsp+54h] [rbp-ACh] BYREF
  WCHAR v16[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v17[140]; // [rsp+E4h] [rbp-1Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  Sid = a1;
  *(_DWORD *)packageFamilyName = 0;
  memset_0(v15, 0, 0x7Eu);
  *(_DWORD *)v16 = 0;
  memset_0(v17, 0, 0x80u);
  packageFamilyNameLength = 65;
  packageRelativeApplicationIdLength = 66;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v5 = ParseApplicationUserModelId(
         StringRawBuffer,
         &packageFamilyNameLength,
         packageFamilyName,
         &packageRelativeApplicationIdLength,
         v16);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basicuiautils.cpp",
      (const char *)(unsigned int)v5,
      packageRelativeApplicationId);
  Sid = 0;
  v6 = DeriveAppContainerSidFromAppContainerName(packageFamilyName, &Sid);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basicuiautils.cpp",
      (const char *)(unsigned int)v6,
      packageRelativeApplicationId);
  StringSid = 0;
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basicuiautils.cpp",
      v7);
  std::wstring::wstring(a1, StringSid);
  if ( StringSid )
    LocalFree(StringSid);
  if ( Sid )
    FreeSid(Sid);
  return a1;
}

```

## disassembly

```asm
0x18005b838  mov     [rsp-8+arg_10], rbx
0x18005b83d  mov     [rsp-8+arg_18], rdi
0x18005b842  push    rbp
0x18005b843  lea     rbp, [rsp-80h]
0x18005b848  sub     rsp, 180h
0x18005b84f  mov     rax, cs:__security_cookie
0x18005b856  xor     rax, rsp
0x18005b859  mov     [rbp+80h+var_10], rax
0x18005b85d  mov     rbx, rdx
0x18005b860  mov     rdi, rcx
0x18005b863  mov     [rsp+180h+Sid], rcx
0x18005b868  mov     dword ptr [rsp+180h+packageFamilyName], 0
0x18005b870  xor     edx, edx; Val
0x18005b872  lea     r8d, [rdx+7Eh]; Size
0x18005b876  lea     rcx, [rsp+180h+var_12C]; void *
0x18005b87b  call    memset_0
0x18005b880  mov     dword ptr [rbp+80h+var_A0], 0
0x18005b887  xor     edx, edx; Val
0x18005b889  mov     r8d, 80h; Size
0x18005b88f  lea     rcx, [rbp+80h+var_9C]; void *
0x18005b893  call    memset_0
0x18005b898  mov     [rsp+180h+packageFamilyNameLength], 41h ; 'A'
0x18005b8a0  mov     [rsp+180h+packageRelativeApplicationIdLength], 42h ; 'B'
0x18005b8a8  xor     edx, edx; length
0x18005b8aa  mov     rcx, rbx; string
0x18005b8ad  call    cs:__imp_WindowsGetStringRawBuffer
0x18005b8b3  mov     rcx, rax; applicationUserModelId
0x18005b8b6  lea     rax, [rbp+80h+var_A0]
0x18005b8ba  mov     qword ptr [rsp+180h+packageRelativeApplicationId], rax; int
0x18005b8bf  lea     r9, [rsp+180h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x18005b8c4  lea     r8, [rsp+180h+packageFamilyName]; packageFamilyName
0x18005b8c9  lea     rdx, [rsp+180h+packageFamilyNameLength]; packageFamilyNameLength
0x18005b8ce  call    cs:__imp_ParseApplicationUserModelId
0x18005b8d4  mov     rcx, [rbp+88h]; this
0x18005b8db  test    eax, eax
0x18005b8dd  jns     short loc_18005B8F4
0x18005b8df  mov     r9d, eax; char *
0x18005b8e2  lea     r8, aOnecoreWindows_70; "onecore\\windows\\accessibletech\\commo"...
0x18005b8e9  mov     edx, 8Ch; void *
0x18005b8ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005b8f4  mov     [rsp+180h+Sid], 0
0x18005b8fd  lea     rdx, [rsp+180h+Sid]
0x18005b902  lea     rcx, [rsp+180h+packageFamilyName]
0x18005b907  call    cs:__imp_DeriveAppContainerSidFromAppContainerName
0x18005b90d  mov     rcx, [rbp+88h]; this
0x18005b914  test    eax, eax
0x18005b916  jns     short loc_18005B92D
0x18005b918  mov     r9d, eax; char *
0x18005b91b  lea     r8, aOnecoreWindows_70; "onecore\\windows\\accessibletech\\commo"...
0x18005b922  mov     edx, 8Fh; void *
0x18005b927  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005b92d  mov     [rsp+180h+StringSid], 0
0x18005b936  lea     rdx, [rsp+180h+StringSid]; StringSid
0x18005b93b  mov     rcx, [rsp+180h+Sid]; Sid
0x18005b940  call    cs:__imp_ConvertSidToStringSidW
0x18005b946  mov     rcx, [rbp+88h]; this
0x18005b94d  test    eax, eax
0x18005b94f  jz      short loc_18005B9A4
0x18005b951  mov     rdx, [rsp+180h+StringSid]
0x18005b956  mov     rcx, rdi
0x18005b959  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005b95e  nop
0x18005b95f  mov     rcx, [rsp+180h+StringSid]; hMem
0x18005b964  test    rcx, rcx
0x18005b967  jz      short loc_18005B970
0x18005b969  call    cs:__imp_LocalFree
0x18005b96f  nop
0x18005b970  mov     rcx, [rsp+180h+Sid]; pSid
0x18005b975  test    rcx, rcx
0x18005b978  jz      short loc_18005B980
0x18005b97a  call    cs:__imp_FreeSid
0x18005b980  mov     rax, rdi
0x18005b983  mov     rcx, [rbp+80h+var_10]
0x18005b987  xor     rcx, rsp; StackCookie
0x18005b98a  call    __security_check_cookie
0x18005b98f  lea     r11, [rsp+180h+var_s0]
0x18005b997  mov     rbx, [r11+20h]
0x18005b99b  mov     rdi, [r11+28h]
0x18005b99f  mov     rsp, r11
0x18005b9a2  pop     rbp
0x18005b9a3  retn
0x18005b9a4  lea     r8, aOnecoreWindows_70; "onecore\\windows\\accessibletech\\commo"...
0x18005b9ab  mov     edx, 92h; void *
0x18005b9b0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
