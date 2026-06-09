# XT1_WriteAdditionalGlyphDictEntries

- ea: `0x18004e3d4`
- end: `0x18004e4f5`
- name: `XT1_WriteAdditionalGlyphDictEntries`
- size: `289`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800477ac`

## callees

- `0x180001f20`
- `0x180002938`
- `0x18004b354`
- `0x18004b690`
- `0x18004f4e4`
- `0x18005f010`

## string_xrefs

- `0x18004e45f`: `systemdict/languagelevel known not{1 index/CIDFont findresource/GlyphDirectory\n`
- `0x18004e47d`: `length 2 index add dict copy 2 index/CIDFont findresource/GlyphDirectory 2\n`
- `0x18004e48c`: `index put}if}if exch pop exch pop}{pop/CIDFont findresource/GlyphDirectory get\n`
- `0x18004e4b9`: `readstring pop}executeonly def ?{$ begin}if\n`

## pseudocode

```c
__int64 __fastcall XT1_WriteAdditionalGlyphDictEntries(__int64 a1, unsigned int a2, signed int *a3, _DWORD *a4)
{
  _BYTE v9[1024]; // [rsp+30h] [rbp-438h] BYREF

  memset_0(v9, 0, sizeof(v9));
  PutString(a1, (__int64)"/");
  PutFontName(a1);
  (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(v9, 1024, " %ld%s", a2, "\r\n");
  PutString(a1, (__int64)v9);
  PutString(a1, (__int64)"systemdict/languagelevel known not{1 index/CIDFont findresource/GlyphDirectory\r\n");
  PutString(a1, (__int64)"get dup type/dicttype eq{dup dup maxlength exch length sub 2 index lt{dup\r\n");
  PutString(a1, (__int64)"length 2 index add dict copy 2 index/CIDFont findresource/GlyphDirectory 2\r\n");
  PutString(a1, (__int64)"index put}if}if exch pop exch pop}{pop/CIDFont findresource/GlyphDirectory get\r\n");
  PutString(a1, (__int64)"}ifelse 5 dict begin/$ exch def/? $ type/dicttype eq def/|{?{def}{$ 3 1 roll\r\n");
  PutString(a1, (__int64)"put}ifelse}bind def/!{?{end}if end}bind def/:{string currentfile exch\r\n");
  PutString(a1, (__int64)"readstring pop}executeonly def ?{$ begin}if\r\n");
  return XT1_WriteGlyphDictEntries(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18004e3d4  push    rbx
0x18004e3d6  push    rbp
0x18004e3d7  push    rsi
0x18004e3d8  push    rdi
0x18004e3d9  sub     rsp, 448h
0x18004e3e0  mov     rax, cs:__security_cookie
0x18004e3e7  xor     rax, rsp
0x18004e3ea  mov     [rsp+468h+var_38], rax
0x18004e3f2  mov     rsi, r8
0x18004e3f5  mov     edi, edx
0x18004e3f7  mov     rbx, rcx
0x18004e3fa  xor     edx, edx; Val
0x18004e3fc  mov     r8d, 400h; Size
0x18004e402  lea     rcx, [rsp+468h+var_438]; void *
0x18004e407  mov     rbp, r9
0x18004e40a  call    memset_0
0x18004e40f  lea     rdx, asc_1800667DC; "/"
0x18004e416  mov     rcx, rbx
0x18004e419  call    PutString
0x18004e41e  mov     rcx, rbx
0x18004e421  call    PutFontName
0x18004e426  lea     rax, asc_180064FCC; "\r\n"
0x18004e42d  mov     r9d, edi
0x18004e430  mov     [rsp+468h+var_448], rax
0x18004e435  lea     r8, aLdS; " %ld%s"
0x18004e43c  mov     rax, [rbx+168h]
0x18004e443  lea     rcx, [rsp+468h+var_438]
0x18004e448  mov     edx, 400h
0x18004e44d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e452  lea     rdx, [rsp+468h+var_438]
0x18004e457  mov     rcx, rbx
0x18004e45a  call    PutString
0x18004e45f  lea     rdx, aSystemdictLang; "systemdict/languagelevel known not{1 in"...
0x18004e466  mov     rcx, rbx
0x18004e469  call    PutString
0x18004e46e  lea     rdx, aGetDupTypeDict; "get dup type/dicttype eq{dup dup maxlen"...
0x18004e475  mov     rcx, rbx
0x18004e478  call    PutString
0x18004e47d  lea     rdx, aLength2IndexAd; "length 2 index add dict copy 2 index/CI"...
0x18004e484  mov     rcx, rbx
0x18004e487  call    PutString
0x18004e48c  lea     rdx, aIndexPutIfIfEx; "index put}if}if exch pop exch pop}{pop/"...
0x18004e493  mov     rcx, rbx
0x18004e496  call    PutString
0x18004e49b  lea     rdx, aIfelse5DictBeg; "}ifelse 5 dict begin/$ exch def/? $ typ"...
0x18004e4a2  mov     rcx, rbx
0x18004e4a5  call    PutString
0x18004e4aa  lea     rdx, aPutIfelseBindD; "put}ifelse}bind def/!{?{end}if end}bind"...
0x18004e4b1  mov     rcx, rbx
0x18004e4b4  call    PutString
0x18004e4b9  lea     rdx, aReadstringPopE; "readstring pop}executeonly def ?{$ begi"...
0x18004e4c0  mov     rcx, rbx
0x18004e4c3  call    PutString
0x18004e4c8  mov     r9, rbp
0x18004e4cb  mov     r8, rsi
0x18004e4ce  mov     edx, edi
0x18004e4d0  mov     rcx, rbx
0x18004e4d3  call    XT1_WriteGlyphDictEntries
0x18004e4d8  mov     rcx, [rsp+468h+var_38]
0x18004e4e0  xor     rcx, rsp; StackCookie
0x18004e4e3  call    __security_check_cookie
0x18004e4e8  add     rsp, 448h
0x18004e4ef  pop     rdi
0x18004e4f0  pop     rsi
0x18004e4f1  pop     rbp
0x18004e4f2  pop     rbx
0x18004e4f3  retn
```
