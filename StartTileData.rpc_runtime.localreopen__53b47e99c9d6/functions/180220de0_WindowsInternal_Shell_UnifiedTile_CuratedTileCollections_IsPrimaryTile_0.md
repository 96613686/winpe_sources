# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::IsPrimaryTile_0

- ea: `0x180220de0`
- end: `0x180220fd0`
- name: `WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::IsPrimaryTile_0`
- size: `496`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18017e110`
- `0x1801808f8`
- `0x1801b1528`

## callees

- `0x18001dac0`
- `0x18012fd64`
- `0x180201e50`
- `0x180220de0`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180220ef0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180220f34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180220ef0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180220f34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180220e20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180220e51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180220f6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180220f81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180220f90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180220fa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180220e20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180220e51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180220f6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180220f81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180220f90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180220fa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180220e87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180220e87`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180220eaf`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180220eaf`

## string_xrefs

- `0x180220ebf`: `shellcommon\shell\tiles\CuratedTileCollections\Common\UtmHelpers.h`
- `0x180220f04`: `shellcommon\shell\tiles\CuratedTileCollections\Common\UtmHelpers.h`
- `0x180220f48`: `shellcommon\shell\tiles\CuratedTileCollections\Common\UtmHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::IsPrimaryTile_0(__int64 a1)
{
  void (__fastcall *v2)(__int64, HSTRING *); // rbx
  void (__fastcall *v3)(__int64, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  HRESULT v5; // eax
  __int64 v6; // rax
  HRESULT v7; // eax
  int packageRelativeApplicationId; // [rsp+20h] [rbp-E0h]
  HSTRING string1; // [rsp+30h] [rbp-D0h] BYREF
  INT32 result; // [rsp+38h] [rbp-C8h] BYREF
  INT32 v12; // [rsp+3Ch] [rbp-C4h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+48h] [rbp-B8h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+4Ch] [rbp-B4h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR sourceString[72]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  string = 0;
  v2 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a1 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v2(a1, &string);
  string1 = 0;
  v3 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a1 + 56LL);
  WindowsDeleteString(0);
  string1 = 0;
  v3(a1, &string1);
  packageFamilyNameLength = 65;
  packageRelativeApplicationIdLength = 66;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( ParseApplicationUserModelId(
         StringRawBuffer,
         &packageFamilyNameLength,
         packageFamilyName,
         &packageRelativeApplicationIdLength,
         sourceString) )
  {
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"shellcommon\\shell\\tiles\\CuratedTileCollections\\Common\\UtmHelpers.h",
      (const char *)0x80070057LL,
      packageRelativeApplicationId);
  }
  result = 0;
  v12 = 0;
  v5 = WindowsCompareStringOrdinal(string1, 0, &result);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"shellcommon\\shell\\tiles\\CuratedTileCollections\\Common\\UtmHelpers.h",
      (const char *)(unsigned int)v5,
      packageRelativeApplicationId);
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString);
  v7 = WindowsCompareStringOrdinal(string1, *(HSTRING *)(v6 + 24), &v12);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"shellcommon\\shell\\tiles\\CuratedTileCollections\\Common\\UtmHelpers.h",
      (const char *)(unsigned int)v7,
      packageRelativeApplicationId);
  if ( result && v12 )
  {
    WindowsDeleteString(string1);
    string1 = 0;
    WindowsDeleteString(string);
    return 0;
  }
  else
  {
    WindowsDeleteString(string1);
    string1 = 0;
    WindowsDeleteString(string);
    return 1;
  }
}

```

## disassembly

```asm
0x180220de0  mov     [rsp-8+arg_8], rbx
0x180220de5  mov     [rsp-8+arg_10], rdi
0x180220dea  push    rbp
0x180220deb  lea     rbp, [rsp-0A0h]
0x180220df3  sub     rsp, 1A0h
0x180220dfa  mov     rax, cs:__security_cookie
0x180220e01  xor     rax, rsp
0x180220e04  mov     [rbp+0A0h+var_10], rax
0x180220e0b  mov     rdi, rcx
0x180220e0e  mov     [rsp+1A0h+string], 0
0x180220e17  mov     rax, [rcx]
0x180220e1a  mov     rbx, [rax+30h]
0x180220e1e  xor     ecx, ecx; string
0x180220e20  call    cs:__imp_WindowsDeleteString
0x180220e26  mov     [rsp+1A0h+string], 0
0x180220e2f  lea     rdx, [rsp+1A0h+string]
0x180220e34  mov     rcx, rdi
0x180220e37  mov     rax, rbx
0x180220e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180220e3f  mov     [rsp+1A0h+string1], 0
0x180220e48  mov     rax, [rdi]
0x180220e4b  mov     rbx, [rax+38h]
0x180220e4f  xor     ecx, ecx; string
0x180220e51  call    cs:__imp_WindowsDeleteString
0x180220e57  mov     [rsp+1A0h+string1], 0
0x180220e60  lea     rdx, [rsp+1A0h+string1]
0x180220e65  mov     rcx, rdi
0x180220e68  mov     rax, rbx
0x180220e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180220e70  mov     [rsp+1A0h+packageFamilyNameLength], 41h ; 'A'
0x180220e78  mov     [rsp+1A0h+packageRelativeApplicationIdLength], 42h ; 'B'
0x180220e80  xor     edx, edx; length
0x180220e82  mov     rcx, [rsp+1A0h+string]; string
0x180220e87  call    cs:__imp_WindowsGetStringRawBuffer
0x180220e8d  mov     rbx, [rbp+0A8h]
0x180220e94  lea     rcx, [rsp+1A0h+sourceString]
0x180220e99  mov     qword ptr [rsp+1A0h+packageRelativeApplicationId], rcx; int
0x180220e9e  lea     r9, [rsp+1A0h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x180220ea3  lea     r8, [rbp+0A0h+packageFamilyName]; packageFamilyName
0x180220ea7  lea     rdx, [rsp+1A0h+packageFamilyNameLength]; packageFamilyNameLength
0x180220eac  mov     rcx, rax; applicationUserModelId
0x180220eaf  call    cs:__imp_ParseApplicationUserModelId
0x180220eb5  test    eax, eax
0x180220eb7  jz      short loc_180220ED4
0x180220eb9  mov     r9d, 80070057h; char *
0x180220ebf  lea     r8, aShellcommonShe_21; "shellcommon\\shell\\tiles\\CuratedTileC"...
0x180220ec6  mov     edx, 50h ; 'P'; void *
0x180220ecb  mov     rcx, rbx; this
0x180220ece  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180220ed4  mov     [rsp+1A0h+result], 0
0x180220edc  mov     [rsp+1A0h+var_164], 0
0x180220ee4  lea     r8, [rsp+1A0h+result]; result
0x180220ee9  xor     edx, edx; string2
0x180220eeb  mov     rcx, [rsp+1A0h+string1]; string1
0x180220ef0  call    cs:__imp_WindowsCompareStringOrdinal
0x180220ef6  mov     rcx, [rbp+0A8h]; this
0x180220efd  test    eax, eax
0x180220eff  jns     short loc_180220F16
0x180220f01  mov     r9d, eax; char *
0x180220f04  lea     r8, aShellcommonShe_21; "shellcommon\\shell\\tiles\\CuratedTileC"...
0x180220f0b  mov     edx, 54h ; 'T'; void *
0x180220f10  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180220f16  lea     rdx, [rsp+1A0h+sourceString]; sourceString
0x180220f1b  lea     rcx, [rsp+1A0h+hstringHeader]; hstringHeader
0x180220f20  call    ??$?0$0BAE@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0BAE@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[260])
0x180220f25  nop
0x180220f26  lea     r8, [rsp+1A0h+var_164]; result
0x180220f2b  mov     rdx, [rax+18h]; string2
0x180220f2f  mov     rcx, [rsp+1A0h+string1]; string1
0x180220f34  call    cs:__imp_WindowsCompareStringOrdinal
0x180220f3a  mov     rcx, [rbp+0A8h]; this
0x180220f41  test    eax, eax
0x180220f43  jns     short loc_180220F5A
0x180220f45  mov     r9d, eax; char *
0x180220f48  lea     r8, aShellcommonShe_21; "shellcommon\\shell\\tiles\\CuratedTileC"...
0x180220f4f  mov     edx, 55h ; 'U'; void *
0x180220f54  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180220f5a  cmp     [rsp+1A0h+result], 0
0x180220f5f  jz      short loc_180220F8B
0x180220f61  cmp     [rsp+1A0h+var_164], 0
0x180220f66  jz      short loc_180220F8B
0x180220f68  mov     rcx, [rsp+1A0h+string1]; string
0x180220f6d  call    cs:__imp_WindowsDeleteString
0x180220f73  mov     [rsp+1A0h+string1], 0
0x180220f7c  mov     rcx, [rsp+1A0h+string]; string
0x180220f81  call    cs:__imp_WindowsDeleteString
0x180220f87  xor     al, al
0x180220f89  jmp     short loc_180220FAC
0x180220f8b  mov     rcx, [rsp+1A0h+string1]; string
0x180220f90  call    cs:__imp_WindowsDeleteString
0x180220f96  mov     [rsp+1A0h+string1], 0
0x180220f9f  mov     rcx, [rsp+1A0h+string]; string
0x180220fa4  call    cs:__imp_WindowsDeleteString
0x180220faa  mov     al, 1
0x180220fac  mov     rcx, [rbp+0A0h+var_10]
0x180220fb3  xor     rcx, rsp; StackCookie
0x180220fb6  call    __security_check_cookie
0x180220fbb  lea     r11, [rsp+1A0h+var_s0]
0x180220fc3  mov     rbx, [r11+18h]
0x180220fc7  mov     rdi, [r11+20h]
0x180220fcb  mov     rsp, r11
0x180220fce  pop     rbp
0x180220fcf  retn
```
