# InternalStringHash

- ea: `0x14004c144`
- end: `0x14004c1dd`
- name: `InternalStringHash`
- size: `153`
- prototype: `__int64 __fastcall(LPCWSTR lpSrcStr, int cchSrc)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14004c1e4`
- `0x14004c290`

## callees

- `0x14001eb94`
- `0x14003241c`
- `0x14004c144`
- `0x14004f150`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x14004c170`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x14004c170`

## string_xrefs

- `0x14004c18f`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\namestr.cxx"`
- `0x14004c1bf`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\namestr.cxx"`
- `0x14004c183`: `[UtilCommon] LCMapString() converted %ld out of %ld characters`
- `0x14004c1b3`: `[UtilCommon] InternalStringHash is returning fixed value, 0, as hash value.Possibly caused by empty string.`

## pseudocode

```c
unsigned int __fastcall InternalStringHash(WCHAR *lpSrcStr, int cchSrc)
{
  int v2; // ebx
  unsigned int v4; // eax
  const wchar_t *v5; // r9
  unsigned int v6; // edi
  __int64 v8; // [rsp+20h] [rbp-18h]

  v2 = cchSrc;
  v4 = LCMapStringW(0x800u, 0x200u, lpSrcStr, cchSrc, lpSrcStr, cchSrc);
  v6 = v4;
  if ( v4 != v2 )
  {
    LODWORD(v8) = v2;
    SearchIndexerTrace::Warning(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutild\\\\namestr.cxx\"",
      (const wchar_t *)0x2C,
      (unsigned int)L"[UtilCommon] LCMapString() converted %ld out of %ld characters",
      (const wchar_t *)v4,
      v8);
    if ( !v6 )
      goto LABEL_6;
    v2 = v6 - 1;
  }
  if ( v2 )
    return CDiffCrc::Crc32((const unsigned __int8 *)lpSrcStr, 2 * v2);
LABEL_6:
  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutild\\\\namestr.cxx\"",
    (const wchar_t *)0x3D,
    (unsigned int)L"[UtilCommon] InternalStringHash is returning fixed value, 0, as hash value.Possibly caused by empty string.",
    v5);
  return 0;
}

```

## disassembly

```asm
0x14004c144  mov     rax, rsp
0x14004c147  mov     [rax+8], rbx
0x14004c14b  mov     [rax+10h], rsi
0x14004c14f  push    rdi
0x14004c150  sub     rsp, 30h
0x14004c154  mov     [rax-10h], edx
0x14004c157  mov     ebx, edx
0x14004c159  mov     [rax-18h], rcx
0x14004c15d  mov     rsi, rcx
0x14004c160  mov     r9d, edx; cchSrc
0x14004c163  mov     r8, rcx; lpSrcStr
0x14004c166  mov     ecx, 800h; Locale
0x14004c16b  mov     edx, 200h; dwMapFlags
0x14004c170  call    cs:__imp_LCMapStringW
0x14004c176  mov     edi, eax
0x14004c178  cmp     eax, ebx
0x14004c17a  jz      short loc_14004C1A2
0x14004c17c  mov     r9d, eax; wchar_t *
0x14004c17f  mov     dword ptr [rsp+38h+var_18], ebx
0x14004c183  lea     r8, aUtilcommonLcma; "[UtilCommon] LCMapString() converted %l"...
0x14004c18a  mov     edx, 2Ch ; ','; wchar_t *
0x14004c18f  lea     rcx, aOnecoreuapBase_52; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x14004c196  call    ?Warning@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Warning(wchar_t const *,uint,wchar_t const *,...)
0x14004c19b  test    edi, edi
0x14004c19d  jz      short loc_14004C1B3
0x14004c19f  lea     ebx, [rdi-1]
0x14004c1a2  test    ebx, ebx
0x14004c1a4  jz      short loc_14004C1B3
0x14004c1a6  lea     edx, [rbx+rbx]; unsigned int
0x14004c1a9  mov     rcx, rsi; unsigned __int8 *
0x14004c1ac  call    ?Crc32@CDiffCrc@@SAKPEBEK@Z; CDiffCrc::Crc32(uchar const *,ulong)
0x14004c1b1  jmp     short loc_14004C1CD
0x14004c1b3  lea     r8, aUtilcommonInte; "[UtilCommon] InternalStringHash is retu"...
0x14004c1ba  mov     edx, 3Dh ; '='; wchar_t *
0x14004c1bf  lea     rcx, aOnecoreuapBase_52; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x14004c1c6  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x14004c1cb  xor     eax, eax
0x14004c1cd  mov     rbx, [rsp+38h+arg_0]
0x14004c1d2  mov     rsi, [rsp+38h+arg_8]
0x14004c1d7  add     rsp, 30h
0x14004c1db  pop     rdi
0x14004c1dc  retn
```
