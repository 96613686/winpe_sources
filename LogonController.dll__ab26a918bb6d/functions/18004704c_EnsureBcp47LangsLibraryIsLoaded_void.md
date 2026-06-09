# EnsureBcp47LangsLibraryIsLoaded(void)

- ea: `0x18004704c`
- end: `0x1800471be`
- name: `?EnsureBcp47LangsLibraryIsLoaded@@YA_NXZ`
- size: `370`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180005500`
- `0x180096a78`

## callees

- `0x18004704c`
- `0x1800471c4`
- `0x18004faf4`
- `0x180096924`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180047093`
- `KERNEL32!LoadLibraryExW` at `0x180047093`
- `KERNEL32!GetProcAddress` at `0x1800470b3`
- `KERNEL32!GetProcAddress` at `0x1800470ce`
- `KERNEL32!GetProcAddress` at `0x1800470e9`
- `KERNEL32!GetProcAddress` at `0x180047104`
- `KERNEL32!GetProcAddress` at `0x18004711f`
- `KERNEL32!GetProcAddress` at `0x18004713a`
- `KERNEL32!GetProcAddress` at `0x180047155`
- `KERNEL32!GetProcAddress` at `0x1800470b3`
- `KERNEL32!GetProcAddress` at `0x1800470ce`
- `KERNEL32!GetProcAddress` at `0x1800470e9`
- `KERNEL32!GetProcAddress` at `0x180047104`
- `KERNEL32!GetProcAddress` at `0x18004711f`
- `KERNEL32!GetProcAddress` at `0x18004713a`
- `KERNEL32!GetProcAddress` at `0x180047155`

## string_xrefs

- `0x18004708a`: `Bcp47Langs.dll`
- `0x180047111`: `RemoveUserLanguageInputMethods`

## pseudocode

```c
char __fastcall EnsureBcp47LangsLibraryIsLoaded(Tsf3OverrideUtil *a1)
{
  Tsf3OverrideUtil *v1; // rcx
  char v2; // bl
  Tsf3OverrideUtil *v3; // rcx
  bool IsRunningOnHub; // al
  HMODULE Library; // rax

  v2 = 1;
  if ( Tsf3OverrideUtil::IsRunningOnDesktop(a1)
    || Tsf3OverrideUtil::IsRunningOnServerSku(v1)
    || (IsRunningOnHub = Tsf3OverrideUtil::IsRunningOnHub(v3)) )
  {
    IsRunningOnHub = 1;
  }
  if ( !hBcp47LangsDll )
  {
    if ( !IsRunningOnHub )
      return 0;
    Library = LoadLibraryExW(L"Bcp47Langs.dll", 0, 0);
    hBcp47LangsDll = Library;
    if ( !Library )
      return 0;
    pfnBcp47FromHkl = (__int64)GetProcAddress(Library, "Bcp47FromHkl");
    pfnBcp47BufferFromLcid = (__int64)GetProcAddress(hBcp47LangsDll, "Bcp47BufferFromLcid");
    pfnAppendUserLanguages = (__int64)GetProcAddress(hBcp47LangsDll, "AppendUserLanguages");
    pfnAppendUserLanguageInputMethods = (__int64)GetProcAddress(hBcp47LangsDll, "AppendUserLanguageInputMethods");
    pfnRemoveUserLanguageInputMethods = (__int64)GetProcAddress(hBcp47LangsDll, "RemoveUserLanguageInputMethods");
    pfnGetUserLanguageInputMethods = (__int64)GetProcAddress(hBcp47LangsDll, "GetUserLanguageInputMethods");
    pfnSetUserLanguageInputMethods = (__int64)GetProcAddress(hBcp47LangsDll, "SetUserLanguageInputMethods");
    if ( !hBcp47LangsDll )
      return 0;
  }
  if ( !pfnBcp47FromHkl
    || !pfnBcp47BufferFromLcid
    || !pfnAppendUserLanguages
    || !pfnAppendUserLanguageInputMethods
    || !pfnRemoveUserLanguageInputMethods
    || !pfnGetUserLanguageInputMethods
    || !pfnSetUserLanguageInputMethods )
  {
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x18004704c  push    rbx
0x18004704e  sub     rsp, 20h
0x180047052  call    ?IsRunningOnDesktop@Tsf3OverrideUtil@@YA_NXZ; Tsf3OverrideUtil::IsRunningOnDesktop(void)
0x180047057  mov     bl, 1
0x180047059  test    al, al
0x18004705b  jnz     short loc_18004706F
0x18004705d  call    ?IsRunningOnServerSku@Tsf3OverrideUtil@@YA_NXZ; Tsf3OverrideUtil::IsRunningOnServerSku(void)
0x180047062  test    al, al
0x180047064  jnz     short loc_18004706F
0x180047066  call    ?IsRunningOnHub@Tsf3OverrideUtil@@YA_NXZ; Tsf3OverrideUtil::IsRunningOnHub(void)
0x18004706b  test    al, al
0x18004706d  jz      short loc_180047071
0x18004706f  mov     al, bl
0x180047071  cmp     cs:hBcp47LangsDll, 0
0x180047079  jnz     loc_18004716E
0x18004707f  test    al, al
0x180047081  jz      loc_1800471B4
0x180047087  xor     r8d, r8d; dwFlags
0x18004708a  lea     rcx, aBcp47langsDll_0; "Bcp47Langs.dll"
0x180047091  xor     edx, edx; hFile
0x180047093  call    cs:__imp_LoadLibraryExW
0x180047099  mov     cs:hBcp47LangsDll, rax
0x1800470a0  test    rax, rax
0x1800470a3  jz      loc_1800471B4
0x1800470a9  lea     rdx, aBcp47fromhkl; "Bcp47FromHkl"
0x1800470b0  mov     rcx, rax; hModule
0x1800470b3  call    cs:__imp_GetProcAddress
0x1800470b9  mov     rcx, cs:hBcp47LangsDll; hModule
0x1800470c0  lea     rdx, aBcp47bufferfro; "Bcp47BufferFromLcid"
0x1800470c7  mov     cs:pfnBcp47FromHkl, rax
0x1800470ce  call    cs:__imp_GetProcAddress
0x1800470d4  mov     rcx, cs:hBcp47LangsDll; hModule
0x1800470db  lea     rdx, aAppenduserlang; "AppendUserLanguages"
0x1800470e2  mov     cs:pfnBcp47BufferFromLcid, rax
0x1800470e9  call    cs:__imp_GetProcAddress
0x1800470ef  mov     rcx, cs:hBcp47LangsDll; hModule
0x1800470f6  lea     rdx, aAppenduserlang_0; "AppendUserLanguageInputMethods"
0x1800470fd  mov     cs:pfnAppendUserLanguages, rax
0x180047104  call    cs:__imp_GetProcAddress
0x18004710a  mov     rcx, cs:hBcp47LangsDll; hModule
0x180047111  lea     rdx, aRemoveuserlang; "RemoveUserLanguageInputMethods"
0x180047118  mov     cs:pfnAppendUserLanguageInputMethods, rax
0x18004711f  call    cs:__imp_GetProcAddress
0x180047125  mov     rcx, cs:hBcp47LangsDll; hModule
0x18004712c  lea     rdx, aGetuserlanguag_3; "GetUserLanguageInputMethods"
0x180047133  mov     cs:pfnRemoveUserLanguageInputMethods, rax
0x18004713a  call    cs:__imp_GetProcAddress
0x180047140  mov     rcx, cs:hBcp47LangsDll; hModule
0x180047147  lea     rdx, aSetuserlanguag_1; "SetUserLanguageInputMethods"
0x18004714e  mov     cs:pfnGetUserLanguageInputMethods, rax
0x180047155  call    cs:__imp_GetProcAddress
0x18004715b  mov     cs:pfnSetUserLanguageInputMethods, rax
0x180047162  mov     rax, cs:hBcp47LangsDll
0x180047169  test    rax, rax
0x18004716c  jz      short loc_1800471B4
0x18004716e  cmp     cs:pfnBcp47FromHkl, 0
0x180047176  jz      short loc_1800471B4
0x180047178  cmp     cs:pfnBcp47BufferFromLcid, 0
0x180047180  jz      short loc_1800471B4
0x180047182  cmp     cs:pfnAppendUserLanguages, 0
0x18004718a  jz      short loc_1800471B4
0x18004718c  cmp     cs:pfnAppendUserLanguageInputMethods, 0
0x180047194  jz      short loc_1800471B4
0x180047196  cmp     cs:pfnRemoveUserLanguageInputMethods, 0
0x18004719e  jz      short loc_1800471B4
0x1800471a0  cmp     cs:pfnGetUserLanguageInputMethods, 0
0x1800471a8  jz      short loc_1800471B4
0x1800471aa  cmp     cs:pfnSetUserLanguageInputMethods, 0
0x1800471b2  jnz     short loc_1800471B6
0x1800471b4  xor     bl, bl
0x1800471b6  mov     al, bl
0x1800471b8  add     rsp, 20h
0x1800471bc  pop     rbx
0x1800471bd  retn
```
