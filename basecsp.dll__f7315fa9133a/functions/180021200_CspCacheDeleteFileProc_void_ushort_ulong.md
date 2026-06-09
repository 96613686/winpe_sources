# CspCacheDeleteFileProc(void *,ushort *,ulong)

- ea: `0x180021200`
- end: `0x18002129e`
- name: `?CspCacheDeleteFileProc@@YAKPEAXPEAGK@Z`
- size: `158`
- prototype: `unsigned int __fastcall(void *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x18000a772`
- `0x18001c71c`
- `0x1800226f8`
- `0x18002cfa0`

## string_xrefs

- `0x180021237`: `Cached_CardmodFile`

## pseudocode

```c
__int64 __fastcall CspCacheDeleteFileProc(void *a1, unsigned __int16 *a2)
{
  void *v5; // [rsp+30h] [rbp-258h] BYREF
  int v6; // [rsp+38h] [rbp-250h]
  int v7; // [rsp+3Ch] [rbp-24Ch]
  int v8; // [rsp+40h] [rbp-248h]
  wchar_t pszDest[278]; // [rsp+44h] [rbp-244h] BYREF

  memset_0(&v5, 0, 0x238u);
  StringCbPrintfW(pszDest, 0x104u, L"%s\\%s", L"Cached_CardmodFile", a2);
  v6 = 7;
  v8 = 1;
  v7 = 1;
  v5 = a1;
  return MyCacheDeleteItem(&v5);
}

```

## disassembly

```asm
0x180021200  mov     [rsp+arg_0], rbx
0x180021205  push    rdi
0x180021206  sub     rsp, 280h
0x18002120d  mov     rax, cs:__security_cookie
0x180021214  xor     rax, rsp
0x180021217  mov     [rsp+288h+var_18], rax
0x18002121f  mov     rbx, rdx
0x180021222  mov     rdi, rcx
0x180021225  xor     edx, edx; Val
0x180021227  lea     rcx, [rsp+288h+var_258]; void *
0x18002122c  mov     r8d, 238h; Size
0x180021232  call    memset_0
0x180021237  lea     r9, aCachedCardmodf; "Cached_CardmodFile"
0x18002123e  mov     [rsp+288h+var_268], rbx
0x180021243  lea     r8, aSS; "%s\\%s"
0x18002124a  mov     edx, 104h; cbDest
0x18002124f  lea     rcx, [rsp+288h+pszDest]; pszDest
0x180021254  call    StringCbPrintfW
0x180021259  mov     eax, 1
0x18002125e  mov     [rsp+288h+var_250], 7
0x180021266  lea     rcx, [rsp+288h+var_258]
0x18002126b  mov     [rsp+288h+var_248], eax
0x18002126f  mov     [rsp+288h+var_24C], eax
0x180021273  mov     [rsp+288h+var_258], rdi
0x180021278  call    MyCacheDeleteItem
0x18002127d  mov     rcx, [rsp+288h+var_18]
0x180021285  xor     rcx, rsp; StackCookie
0x180021288  call    __security_check_cookie
0x18002128d  mov     rbx, [rsp+288h+arg_0]
0x180021295  add     rsp, 280h
0x18002129c  pop     rdi
0x18002129d  retn
```
