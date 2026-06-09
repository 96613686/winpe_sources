# XT1_WriteAdditionalGlyphDictEntries

- ea: `0x18004cb44`
- end: `0x18004cc64`
- name: `XT1_WriteAdditionalGlyphDictEntries`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180045e88`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x180049adc`
- `0x180049e14`
- `0x18004dc54`
- `0x18005d010`

## string_xrefs

- `0x18004cbcf`: `systemdict/languagelevel known not{1 index/CIDFont findresource/GlyphDirectory\n`
- `0x18004cbed`: `length 2 index add dict copy 2 index/CIDFont findresource/GlyphDirectory 2\n`
- `0x18004cbfc`: `index put}if}if exch pop exch pop}{pop/CIDFont findresource/GlyphDirectory get\n`
- `0x18004cc29`: `readstring pop}executeonly def ?{$ begin}if\n`

## pseudocode

```c
__int64 __fastcall XT1_WriteAdditionalGlyphDictEntries(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  _BYTE v9[1024]; // [rsp+30h] [rbp-438h] BYREF

  memset_0(v9, 0, sizeof(v9));
  PutString(a1, "/");
  PutFontName(a1);
  (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(v9, 1024, " %ld%s", a2, "\r\n");
  PutString(a1, v9);
  PutString(a1, "systemdict/languagelevel known not{1 index/CIDFont findresource/GlyphDirectory\r\n");
  PutString(a1, "get dup type/dicttype eq{dup dup maxlength exch length sub 2 index lt{dup\r\n");
  PutString(a1, "length 2 index add dict copy 2 index/CIDFont findresource/GlyphDirectory 2\r\n");
  PutString(a1, "index put}if}if exch pop exch pop}{pop/CIDFont findresource/GlyphDirectory get\r\n");
  PutString(a1, "}ifelse 5 dict begin/$ exch def/? $ type/dicttype eq def/|{?{def}{$ 3 1 roll\r\n");
  PutString(a1, "put}ifelse}bind def/!{?{end}if end}bind def/:{string currentfile exch\r\n");
  PutString(a1, "readstring pop}executeonly def ?{$ begin}if\r\n");
  return XT1_WriteGlyphDictEntries(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18004cb44  push    rbx
0x18004cb46  push    rbp
0x18004cb47  push    rsi
0x18004cb48  push    rdi
0x18004cb49  sub     rsp, 448h
0x18004cb50  mov     rax, cs:__security_cookie
0x18004cb57  xor     rax, rsp
0x18004cb5a  mov     [rsp+468h+var_38], rax
0x18004cb62  mov     rsi, r8
0x18004cb65  mov     edi, edx
0x18004cb67  mov     rbx, rcx
0x18004cb6a  xor     edx, edx; Val
0x18004cb6c  mov     r8d, 400h; Size
0x18004cb72  lea     rcx, [rsp+468h+var_438]; void *
0x18004cb77  mov     rbp, r9
0x18004cb7a  call    memset_0
0x18004cb7f  lea     rdx, asc_1800647FC; "/"
0x18004cb86  mov     rcx, rbx
0x18004cb89  call    PutString
0x18004cb8e  mov     rcx, rbx
0x18004cb91  call    PutFontName
0x18004cb96  lea     rax, asc_180062FDC; "\r\n"
0x18004cb9d  mov     r9d, edi
0x18004cba0  mov     [rsp+468h+var_448], rax
0x18004cba5  lea     r8, aLdS; " %ld%s"
0x18004cbac  mov     rax, [rbx+168h]
0x18004cbb3  lea     rcx, [rsp+468h+var_438]
0x18004cbb8  mov     edx, 400h
0x18004cbbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbc2  lea     rdx, [rsp+468h+var_438]
0x18004cbc7  mov     rcx, rbx
0x18004cbca  call    PutString
0x18004cbcf  lea     rdx, aSystemdictLang; "systemdict/languagelevel known not{1 in"...
0x18004cbd6  mov     rcx, rbx
0x18004cbd9  call    PutString
0x18004cbde  lea     rdx, aGetDupTypeDict; "get dup type/dicttype eq{dup dup maxlen"...
0x18004cbe5  mov     rcx, rbx
0x18004cbe8  call    PutString
0x18004cbed  lea     rdx, aLength2IndexAd; "length 2 index add dict copy 2 index/CI"...
0x18004cbf4  mov     rcx, rbx
0x18004cbf7  call    PutString
0x18004cbfc  lea     rdx, aIndexPutIfIfEx; "index put}if}if exch pop exch pop}{pop/"...
0x18004cc03  mov     rcx, rbx
0x18004cc06  call    PutString
0x18004cc0b  lea     rdx, aIfelse5DictBeg; "}ifelse 5 dict begin/$ exch def/? $ typ"...
0x18004cc12  mov     rcx, rbx
0x18004cc15  call    PutString
0x18004cc1a  lea     rdx, aPutIfelseBindD; "put}ifelse}bind def/!{?{end}if end}bind"...
0x18004cc21  mov     rcx, rbx
0x18004cc24  call    PutString
0x18004cc29  lea     rdx, aReadstringPopE; "readstring pop}executeonly def ?{$ begi"...
0x18004cc30  mov     rcx, rbx
0x18004cc33  call    PutString
0x18004cc38  mov     r9, rbp
0x18004cc3b  mov     r8, rsi
0x18004cc3e  mov     edx, edi
0x18004cc40  mov     rcx, rbx
0x18004cc43  call    XT1_WriteGlyphDictEntries
0x18004cc48  mov     rcx, [rsp+468h+var_38]
0x18004cc50  xor     rcx, rsp; StackCookie
0x18004cc53  call    __security_check_cookie
0x18004cc58  add     rsp, 448h
0x18004cc5f  pop     rdi
0x18004cc60  pop     rsi
0x18004cc61  pop     rbp
0x18004cc62  pop     rbx
0x18004cc63  retn
```
