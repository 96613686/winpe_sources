# IsPrefixed

- ea: `0x180009a78`
- end: `0x180009b4e`
- name: `IsPrefixed`
- size: `214`
- prototype: `bool __fastcall(LPCWSTR lpSrcStr, unsigned int cchSrc, OLECHAR *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path`

## callers

- `0x180008974`
- `0x18000a05c`

## callees

- `0x180009898`
- `0x180009a78`
- `0x18000c4fe`
- `0x18000c530`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009afc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009b29`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009afc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009b29`
- `OLEAUT32!__imp_SysStringLen` at `0x180009aab`
- `OLEAUT32!__imp_SysStringLen` at `0x180009aab`

## pseudocode

```c
bool __fastcall IsPrefixed(LPCWSTR lpSrcStr, unsigned int cchSrc, OLECHAR *a3)
{
  UINT v4; // eax
  const wchar_t *v5; // rdx
  const wchar_t *v6; // rcx
  wchar_t *v7; // rbx
  unsigned __int64 v8; // rdi
  bool v9; // si
  wchar_t *String2[3]; // [rsp+20h] [rbp-50h] BYREF
  unsigned __int64 v12; // [rsp+38h] [rbp-38h]
  wchar_t *String1[2]; // [rsp+40h] [rbp-30h] BYREF
  size_t MaxCount; // [rsp+50h] [rbp-20h]
  unsigned __int64 v15; // [rsp+58h] [rbp-18h]

  JpnStringUtils::GetNormalizedString(String1, lpSrcStr, cchSrc);
  v4 = SysStringLen(a3);
  JpnStringUtils::GetNormalizedString(String2, a3, v4);
  v5 = (const wchar_t *)String2;
  if ( v12 >= 8 )
    v5 = String2[0];
  v6 = (const wchar_t *)String1;
  v7 = String1[0];
  v8 = v15;
  if ( v15 >= 8 )
    v6 = String1[0];
  v9 = wcsncmp_0(v6, v5, (unsigned int)MaxCount) == 0;
  if ( v12 >= 8 )
  {
    operator delete(String2[0]);
    v8 = v15;
    v7 = String1[0];
  }
  v12 = 7;
  String2[2] = 0;
  LOWORD(String2[0]) = 0;
  if ( v8 >= 8 )
    operator delete(v7);
  return v9;
}

```

## disassembly

```asm
0x180009a78  mov     [rsp-18h+arg_18], rbx
0x180009a7d  push    rbp
0x180009a7e  push    rsi
0x180009a7f  push    rdi
0x180009a80  mov     rbp, rsp
0x180009a83  sub     rsp, 70h
0x180009a87  mov     rax, cs:__security_cookie
0x180009a8e  xor     rax, rsp
0x180009a91  mov     [rbp+var_10], rax
0x180009a95  mov     rbx, r8
0x180009a98  mov     r8d, edx; cchSrc
0x180009a9b  mov     rdx, rcx; lpSrcStr
0x180009a9e  lea     rcx, [rbp+String1]; void *
0x180009aa2  call    ?GetNormalizedString@JpnStringUtils@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG_K@Z; JpnStringUtils::GetNormalizedString(ushort const *,unsigned __int64)
0x180009aa7  nop
0x180009aa8  mov     rcx, rbx; pbstr
0x180009aab  call    cs:__imp_SysStringLen
0x180009ab1  mov     r8d, eax; cchSrc
0x180009ab4  mov     rdx, rbx; lpSrcStr
0x180009ab7  lea     rcx, [rbp+String2]; void *
0x180009abb  call    ?GetNormalizedString@JpnStringUtils@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG_K@Z; JpnStringUtils::GetNormalizedString(ushort const *,unsigned __int64)
0x180009ac0  lea     rdx, [rbp+String2]
0x180009ac4  cmp     [rbp+var_38], 8
0x180009ac9  cmovnb  rdx, [rbp+String2]; String2
0x180009ace  lea     rcx, [rbp+String1]
0x180009ad2  mov     rbx, [rbp+String1]
0x180009ad6  mov     rdi, [rbp+var_18]
0x180009ada  cmp     rdi, 8
0x180009ade  cmovnb  rcx, rbx; String1
0x180009ae2  mov     r8d, dword ptr [rbp+MaxCount]; MaxCount
0x180009ae6  call    wcsncmp_0
0x180009aeb  test    eax, eax
0x180009aed  setz    sil
0x180009af1  cmp     [rbp+var_38], 8
0x180009af6  jb      short loc_180009B0A
0x180009af8  mov     rcx, [rbp+String2]
0x180009afc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009b02  mov     rdi, [rbp+var_18]
0x180009b06  mov     rbx, [rbp+String1]
0x180009b0a  mov     [rbp+var_38], 7
0x180009b12  mov     [rbp+var_40], 0
0x180009b1a  xor     edx, edx
0x180009b1c  mov     word ptr [rbp+String2], dx
0x180009b20  cmp     rdi, 8
0x180009b24  jb      short loc_180009B2F
0x180009b26  mov     rcx, rbx
0x180009b29  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009b2f  mov     al, sil
0x180009b32  mov     rcx, [rbp+var_10]
0x180009b36  xor     rcx, rsp; StackCookie
0x180009b39  call    __security_check_cookie
0x180009b3e  mov     rbx, [rsp+70h+arg_18]
0x180009b46  add     rsp, 70h
0x180009b4a  pop     rdi
0x180009b4b  pop     rsi
0x180009b4c  pop     rbp
0x180009b4d  retn
```
