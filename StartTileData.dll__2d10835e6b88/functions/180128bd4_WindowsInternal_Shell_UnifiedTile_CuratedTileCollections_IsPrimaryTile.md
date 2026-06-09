# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::IsPrimaryTile

- ea: `0x180128bd4`
- end: `0x180128dd7`
- name: `WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::IsPrimaryTile`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1801474d4`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x18004ffc0`
- `0x180128bd4`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180128dd0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180128dd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180128cc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180128d38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180128cc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180128d38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180128c0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180128c35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180128d6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180128d7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180128da7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180128db7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180128c0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180128c35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180128d6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180128d7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180128da7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180128db7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180128c67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180128c67`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180128c8f`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180128c8f`

## string_xrefs

- `0x180128c9f`: `shellcommon\shell\Tiles\CuratedTileCollections\Common\UtmHelpers.h`
- `0x180128cda`: `shellcommon\shell\Tiles\CuratedTileCollections\Common\UtmHelpers.h`
- `0x180128d4c`: `shellcommon\shell\Tiles\CuratedTileCollections\Common\UtmHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::IsPrimaryTile(__int64 a1)
{
  void (__fastcall *v2)(__int64, HSTRING *); // rbx
  void (__fastcall *v3)(__int64, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  HRESULT v5; // eax
  unsigned __int64 v6; // rbx
  unsigned int v7; // eax
  HRESULT v8; // eax
  int packageRelativeApplicationId; // [rsp+20h] [rbp-E0h]
  HSTRING string1; // [rsp+30h] [rbp-D0h] BYREF
  INT32 result; // [rsp+38h] [rbp-C8h] BYREF
  INT32 v13; // [rsp+3Ch] [rbp-C4h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+48h] [rbp-B8h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+4Ch] [rbp-B4h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string2; // [rsp+68h] [rbp-98h]
  WCHAR sourceString[72]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

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
      (unsigned int)"shellcommon\\shell\\Tiles\\CuratedTileCollections\\Common\\UtmHelpers.h",
      (const char *)0x80070057LL,
      packageRelativeApplicationId);
  }
  result = 0;
  v13 = 0;
  v5 = WindowsCompareStringOrdinal(string1, 0, &result);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"shellcommon\\shell\\Tiles\\CuratedTileCollections\\Common\\UtmHelpers.h",
      (const char *)(unsigned int)v5,
      packageRelativeApplicationId);
  v6 = -1;
  do
    ++v6;
  while ( sourceString[v6] );
  if ( v6 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x180128DD6LL);
  }
  v7 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v6);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, sourceString, v7, v6);
  v8 = WindowsCompareStringOrdinal(string1, string2, &v13);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"shellcommon\\shell\\Tiles\\CuratedTileCollections\\Common\\UtmHelpers.h",
      (const char *)(unsigned int)v8,
      packageRelativeApplicationId);
  if ( result && v13 )
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
0x180128bd4  push    rbp
0x180128bd6  push    rbx
0x180128bd7  push    rsi
0x180128bd8  push    rdi
0x180128bd9  lea     rbp, [rsp-0A8h]
0x180128be1  sub     rsp, 1A8h
0x180128be8  mov     rax, cs:__security_cookie
0x180128bef  xor     rax, rsp
0x180128bf2  mov     [rbp+0C0h+var_30], rax
0x180128bf9  mov     rdi, rcx
0x180128bfc  xor     esi, esi
0x180128bfe  mov     [rsp+1C0h+string], rsi
0x180128c03  mov     rax, [rcx]
0x180128c06  mov     rbx, [rax+30h]
0x180128c0a  xor     ecx, ecx; string
0x180128c0c  call    cs:__imp_WindowsDeleteString
0x180128c12  mov     [rsp+1C0h+string], rsi
0x180128c17  lea     rdx, [rsp+1C0h+string]
0x180128c1c  mov     rcx, rdi
0x180128c1f  mov     rax, rbx
0x180128c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128c27  mov     [rsp+1C0h+string1], rsi
0x180128c2c  mov     rax, [rdi]
0x180128c2f  mov     rbx, [rax+38h]
0x180128c33  xor     ecx, ecx; string
0x180128c35  call    cs:__imp_WindowsDeleteString
0x180128c3b  mov     [rsp+1C0h+string1], rsi
0x180128c40  lea     rdx, [rsp+1C0h+string1]
0x180128c45  mov     rcx, rdi
0x180128c48  mov     rax, rbx
0x180128c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128c50  mov     [rsp+1C0h+packageFamilyNameLength], 41h ; 'A'
0x180128c58  mov     [rsp+1C0h+packageRelativeApplicationIdLength], 42h ; 'B'
0x180128c60  xor     edx, edx; length
0x180128c62  mov     rcx, [rsp+1C0h+string]; string
0x180128c67  call    cs:__imp_WindowsGetStringRawBuffer
0x180128c6d  mov     rbx, [rbp+0C8h]
0x180128c74  lea     rcx, [rsp+1C0h+sourceString]
0x180128c79  mov     qword ptr [rsp+1C0h+packageRelativeApplicationId], rcx; int
0x180128c7e  lea     r9, [rsp+1C0h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x180128c83  lea     r8, [rbp+0C0h+packageFamilyName]; packageFamilyName
0x180128c87  lea     rdx, [rsp+1C0h+packageFamilyNameLength]; packageFamilyNameLength
0x180128c8c  mov     rcx, rax; applicationUserModelId
0x180128c8f  call    cs:__imp_ParseApplicationUserModelId
0x180128c95  test    eax, eax
0x180128c97  jz      short loc_180128CB2
0x180128c99  mov     r9d, 80070057h; char *
0x180128c9f  lea     r8, aShellcommonShe_196; "shellcommon\\shell\\Tiles\\CuratedTileC"...
0x180128ca6  lea     edx, [rsi+50h]; void *
0x180128ca9  mov     rcx, rbx; this
0x180128cac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180128cb2  mov     [rsp+1C0h+result], esi
0x180128cb6  mov     [rsp+1C0h+var_184], esi
0x180128cba  lea     r8, [rsp+1C0h+result]; result
0x180128cbf  xor     edx, edx; string2
0x180128cc1  mov     rcx, [rsp+1C0h+string1]; string1
0x180128cc6  call    cs:__imp_WindowsCompareStringOrdinal
0x180128ccc  mov     rcx, [rbp+0C8h]; this
0x180128cd3  test    eax, eax
0x180128cd5  jns     short loc_180128CEC
0x180128cd7  mov     r9d, eax; char *
0x180128cda  lea     r8, aShellcommonShe_196; "shellcommon\\shell\\Tiles\\CuratedTileC"...
0x180128ce1  mov     edx, 54h ; 'T'; void *
0x180128ce6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180128cec  lea     rax, [rsp+1C0h+sourceString]
0x180128cf1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180128cf5  inc     rbx
0x180128cf8  cmp     [rax+rbx*2], si
0x180128cfc  jnz     short loc_180128CF5
0x180128cfe  mov     eax, 0FFFFFFFFh
0x180128d03  cmp     rbx, rax
0x180128d06  ja      loc_180128DC1
0x180128d0c  mov     ecx, ebx; unsigned int
0x180128d0e  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180128d13  mov     r9d, ebx; unsigned int
0x180128d16  mov     r8d, eax; unsigned int
0x180128d19  lea     rdx, [rsp+1C0h+sourceString]; sourceString
0x180128d1e  lea     rcx, [rsp+1C0h+hstringHeader]; hstringHeader
0x180128d23  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180128d28  nop
0x180128d29  lea     r8, [rsp+1C0h+var_184]; result
0x180128d2e  mov     rdx, [rsp+1C0h+string2]; string2
0x180128d33  mov     rcx, [rsp+1C0h+string1]; string1
0x180128d38  call    cs:__imp_WindowsCompareStringOrdinal
0x180128d3e  mov     rcx, [rbp+0C8h]; this
0x180128d45  test    eax, eax
0x180128d47  jns     short loc_180128D5E
0x180128d49  mov     r9d, eax; char *
0x180128d4c  lea     r8, aShellcommonShe_196; "shellcommon\\shell\\Tiles\\CuratedTileC"...
0x180128d53  mov     edx, 55h ; 'U'; void *
0x180128d58  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180128d5e  cmp     [rsp+1C0h+result], esi
0x180128d62  jz      short loc_180128DA2
0x180128d64  cmp     [rsp+1C0h+var_184], esi
0x180128d68  jz      short loc_180128DA2
0x180128d6a  mov     rcx, [rsp+1C0h+string1]; string
0x180128d6f  call    cs:__imp_WindowsDeleteString
0x180128d75  mov     [rsp+1C0h+string1], rsi
0x180128d7a  mov     rcx, [rsp+1C0h+string]; string
0x180128d7f  call    cs:__imp_WindowsDeleteString
0x180128d85  xor     al, al
0x180128d87  mov     rcx, [rbp+0C0h+var_30]
0x180128d8e  xor     rcx, rsp; StackCookie
0x180128d91  call    __security_check_cookie
0x180128d96  add     rsp, 1A8h
0x180128d9d  pop     rdi
0x180128d9e  pop     rsi
0x180128d9f  pop     rbx
0x180128da0  pop     rbp
0x180128da1  retn
0x180128da2  mov     rcx, [rsp+1C0h+string1]; string
0x180128da7  call    cs:__imp_WindowsDeleteString
0x180128dad  mov     [rsp+1C0h+string1], rsi
0x180128db2  mov     rcx, [rsp+1C0h+string]; string
0x180128db7  call    cs:__imp_WindowsDeleteString
0x180128dbd  mov     al, 1
0x180128dbf  jmp     short loc_180128D87
0x180128dc1  xor     r9d, r9d; lpArguments
0x180128dc4  xor     r8d, r8d; nNumberOfArguments
0x180128dc7  lea     edx, [r9+1]; dwExceptionFlags
0x180128dcb  mov     ecx, 80070216h; dwExceptionCode
0x180128dd0  call    cs:__imp_RaiseException
```
