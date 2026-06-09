# WindowsStorage::Utilities::NtObjectPath::FromRegistry(ushort const *)

- ea: `0x18000e20c`
- end: `0x18000e2d0`
- name: `?FromRegistry@NtObjectPath@Utilities@WindowsStorage@@SA?AV123@PEBG@Z`
- size: `196`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800102cc`

## callees

- `0x18000e20c`
- `0x18000f064`
- `0x180010670`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e2be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e2be`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsSameRootW` at `0x18000e22c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsSameRootW` at `0x18000e22c`

## string_xrefs

- `0x18000e23c`: `onecore\internal\sdk\inc\NtObjectPath.h`
- `0x18000e29d`: `onecore\internal\sdk\inc\NtObjectPath.h`
- `0x18000e222`: `\REGISTRY`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall WindowsStorage::Utilities::NtObjectPath::FromRegistry(_QWORD *a1, const WCHAR *a2)
{
  unsigned __int64 v4; // r8
  const unsigned __int16 *v5; // rdx
  int v6; // eax
  int v8; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v10; // [rsp+70h] [rbp+18h] BYREF

  if ( !PathIsSameRootW(a2, L"\\REGISTRY") )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x39,
      (int)"onecore\\internal\\sdk\\inc\\NtObjectPath.h",
      (const char *)0x80070057LL,
      v8);
  v10 = 0;
  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
    if ( v4 > 0xFFFFFFFF )
    {
      v6 = -2147024362;
      goto LABEL_11;
    }
    v5 = a2;
  }
  else
  {
    LODWORD(v4) = 0;
    v5 = &dword_180028344;
  }
  v6 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v10, v5, v4);
LABEL_11:
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3C,
      (int)"onecore\\internal\\sdk\\inc\\NtObjectPath.h",
      (const char *)(unsigned int)v6,
      v8);
  *a1 = v10;
  v10 = 0;
  WindowsDeleteString(0);
  return a1;
}

```

## disassembly

```asm
0x18000e20c  push    rbx
0x18000e20e  push    rbp
0x18000e20f  push    rsi
0x18000e210  push    rdi
0x18000e211  sub     rsp, 38h
0x18000e215  mov     rbx, rdx
0x18000e218  mov     rdi, rcx
0x18000e21b  xor     ebp, ebp
0x18000e21d  mov     rsi, [rsp+58h]
0x18000e222  lea     rdx, pszPath2; "\\REGISTRY"
0x18000e229  mov     rcx, rbx; pszPath1
0x18000e22c  call    cs:__imp_PathIsSameRootW
0x18000e232  test    eax, eax
0x18000e234  jnz     short loc_18000E24F
0x18000e236  mov     r9d, 80070057h; char *
0x18000e23c  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\NtObjectPa"...
0x18000e243  lea     edx, [rbp+39h]; void *
0x18000e246  mov     rcx, rsi; this
0x18000e249  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e24f  mov     [rsp+58h+arg_10], rbp
0x18000e254  test    rbx, rbx
0x18000e257  jz      short loc_18000E27D
0x18000e259  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000e25d  inc     r8
0x18000e260  cmp     [rbx+r8*2], bp
0x18000e265  jnz     short loc_18000E25D
0x18000e267  mov     eax, 0FFFFFFFFh
0x18000e26c  cmp     r8, rax
0x18000e26f  ja      short loc_18000E276
0x18000e271  mov     rdx, rbx
0x18000e274  jmp     short loc_18000E287
0x18000e276  mov     eax, 80070216h
0x18000e27b  jmp     short loc_18000E291
0x18000e27d  xor     r8d, r8d; unsigned int
0x18000e280  lea     rdx, dword_180028344; unsigned __int16 *
0x18000e287  lea     rcx, [rsp+58h+arg_10]; this
0x18000e28c  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18000e291  mov     rcx, [rsp+58h]; this
0x18000e296  test    eax, eax
0x18000e298  jns     short loc_18000E2AF
0x18000e29a  mov     r9d, eax; char *
0x18000e29d  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\NtObjectPa"...
0x18000e2a4  mov     edx, 3Ch ; '<'; void *
0x18000e2a9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e2af  mov     rax, [rsp+58h+arg_10]
0x18000e2b4  mov     [rdi], rax
0x18000e2b7  mov     [rsp+58h+arg_10], rbp
0x18000e2bc  xor     ecx, ecx; string
0x18000e2be  call    cs:__imp_WindowsDeleteString
0x18000e2c4  mov     rax, rdi
0x18000e2c7  add     rsp, 38h
0x18000e2cb  pop     rdi
0x18000e2cc  pop     rsi
0x18000e2cd  pop     rbp
0x18000e2ce  pop     rbx
0x18000e2cf  retn
```
