# GetLanguageOverlayAbsoluteKeyPath(LanguageOverlayHive,ushort const *)

- ea: `0x18005feb0`
- end: `0x18006006a`
- name: `?GetLanguageOverlayAbsoluteKeyPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4LanguageOverlayHive@@PEBG@Z`
- size: `442`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005fb74`
- `0x180060320`

## callees

- `0x180003a00`
- `0x1800099c4`
- `0x180011334`
- `0x180012a98`
- `0x1800137bc`
- `0x18005feb0`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18005ff03`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18005ff03`

## string_xrefs

- `0x180060001`: `onecore\base\languageoverlay\common\platformutils.cpp`
- `0x18006001e`: `onecore\base\languageoverlay\common\platformutils.cpp`
- `0x18006003b`: `onecore\base\languageoverlay\common\platformutils.cpp`
- `0x180060055`: `onecore\base\languageoverlay\common\platformutils.cpp`

## pseudocode

```c
__int64 __fastcall GetLanguageOverlayAbsoluteKeyPath(__int64 a1, int a2, const unsigned __int16 *a3)
{
  unsigned __int16 *v5; // r8
  unsigned int PersistedRegistryLocationW; // eax
  unsigned __int64 v7; // rdx
  __int64 v8; // rcx
  const wchar_t *v9; // rax
  unsigned __int16 *v10; // rcx
  int v11; // eax
  unsigned __int64 v12; // rdx
  int v13; // eax
  unsigned __int64 v14; // r8
  int v16; // [rsp+20h] [rbp-248h]
  __int64 v17; // [rsp+38h] [rbp-230h]
  unsigned __int16 v18[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  HIWORD(v17) = HIWORD(a1);
  v5 = v18;
  if ( a2 )
  {
    v8 = 2147483646;
    v9 = L"Software\\Microsoft\\LanguageOverlay";
    v7 = 260;
    do
    {
      if ( !v8 )
        break;
      if ( !*v9 )
        break;
      *v5++ = *v9++;
      --v8;
      --v7;
    }
    while ( v7 );
    v10 = v5 - 1;
    if ( v7 )
      v10 = v5;
    *v10 = 0;
    if ( !v7 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x25,
        (unsigned int)"onecore\\base\\languageoverlay\\common\\platformutils.cpp",
        (const char *)0x8007007ALL,
        v16);
  }
  else
  {
    v16 = 0;
    PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                   L"LanguageOverlayKeyName",
                                   L"Software\\Microsoft\\LanguageOverlay",
                                   v18,
                                   520);
    if ( PersistedRegistryLocationW )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x21,
        (unsigned int)"onecore\\base\\languageoverlay\\common\\platformutils.cpp",
        (const char *)PersistedRegistryLocationW,
        0);
  }
  if ( a3 && *a3 )
  {
    v11 = StringCchCatW(v18, v7, L"\\");
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecore\\base\\languageoverlay\\common\\platformutils.cpp",
        (const char *)(unsigned int)v11,
        v16);
    v13 = StringCchCatW(v18, v12, a3);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2B,
        (unsigned int)"onecore\\base\\languageoverlay\\common\\platformutils.cpp",
        (const char *)(unsigned int)v13,
        v16);
  }
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v14 = -1;
  *(_QWORD *)(a1 + 24) = 0;
  do
    ++v14;
  while ( v18[v14] );
  std::wstring::_Construct<1,unsigned short const *>((char **)a1, v18, v14);
  return a1;
}

```

## disassembly

```asm
0x18005feb0  mov     [rsp+arg_8], rbx
0x18005feb5  mov     [rsp+arg_18], rsi
0x18005feba  push    rdi
0x18005febb  sub     rsp, 260h
0x18005fec2  mov     rax, cs:__security_cookie
0x18005fec9  xor     rax, rsp
0x18005fecc  mov     [rsp+268h+var_18], rax
0x18005fed4  xor     esi, esi
0x18005fed6  mov     [rsp+268h+var_230], rcx
0x18005fedb  mov     rdi, r8
0x18005fede  mov     rbx, rcx
0x18005fee1  lea     r8, [rsp+268h+var_228]
0x18005fee6  test    edx, edx
0x18005fee8  jnz     short loc_18005FF13
0x18005feea  mov     r9d, 208h
0x18005fef0  mov     qword ptr [rsp+268h+var_248], rsi; unsigned int
0x18005fef5  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\LanguageOverlay"
0x18005fefc  lea     rcx, aLanguageoverla_1; "LanguageOverlayKeyName"
0x18005ff03  call    cs:__imp_GetPersistedRegistryLocationW
0x18005ff09  test    eax, eax
0x18005ff0b  jnz     loc_180060016
0x18005ff11  jmp     short loc_18005FF6F
0x18005ff13  mov     ecx, 7FFFFFFEh
0x18005ff18  lea     rax, aSoftwareMicros_0; "Software\\Microsoft\\LanguageOverlay"
0x18005ff1f  mov     edx, 104h
0x18005ff24  test    rcx, rcx
0x18005ff27  jz      short loc_18005FF48
0x18005ff29  movzx   r9d, word ptr [rax]
0x18005ff2d  test    r9w, r9w
0x18005ff31  jz      short loc_18005FF48
0x18005ff33  mov     [r8], r9w
0x18005ff37  add     rax, 2
0x18005ff3b  add     r8, 2
0x18005ff3f  dec     rcx
0x18005ff42  sub     rdx, 1; unsigned __int64
0x18005ff46  jnz     short loc_18005FF24
0x18005ff48  mov     rax, rdx
0x18005ff4b  lea     rcx, [r8-2]
0x18005ff4f  neg     rax
0x18005ff52  sbb     r9d, r9d
0x18005ff55  not     r9d
0x18005ff58  and     r9d, 8007007Ah; char *
0x18005ff5f  test    rdx, rdx
0x18005ff62  cmovnz  rcx, r8
0x18005ff66  mov     [rcx], si
0x18005ff69  jz      loc_180060033
0x18005ff6f  test    rdi, rdi
0x18005ff72  jz      short loc_18005FFA3
0x18005ff74  cmp     si, [rdi]
0x18005ff77  jz      short loc_18005FFA3
0x18005ff79  lea     r8, asc_180071408; "\\"
0x18005ff80  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18005ff85  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005ff8a  test    eax, eax
0x18005ff8c  js      loc_18006004D
0x18005ff92  mov     r8, rdi; unsigned __int16 *
0x18005ff95  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18005ff9a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005ff9f  test    eax, eax
0x18005ffa1  js      short loc_18005FFF9
0x18005ffa3  xorps   xmm0, xmm0
0x18005ffa6  lea     rax, [rsp+268h+var_228]
0x18005ffab  movups  xmmword ptr [rbx], xmm0
0x18005ffae  mov     [rbx+10h], rsi
0x18005ffb2  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005ffb6  mov     [rbx+18h], rsi
0x18005ffba  inc     r8
0x18005ffbd  cmp     [rax+r8*2], si
0x18005ffc2  jnz     short loc_18005FFBA
0x18005ffc4  lea     rdx, [rsp+268h+var_228]
0x18005ffc9  mov     rcx, rbx
0x18005ffcc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005ffd1  mov     rax, rbx
0x18005ffd4  mov     rcx, [rsp+268h+var_18]
0x18005ffdc  xor     rcx, rsp; StackCookie
0x18005ffdf  call    __security_check_cookie
0x18005ffe4  lea     r11, [rsp+268h+var_8]
0x18005ffec  mov     rbx, [r11+18h]
0x18005fff0  mov     rsi, [r11+28h]
0x18005fff4  mov     rsp, r11
0x18005fff7  pop     rdi
0x18005fff8  retn
0x18005fff9  mov     rcx, [rsp+268h]; this
0x180060001  lea     r8, aOnecoreBaseLan_2; "onecore\\base\\languageoverlay\\common"...
0x180060008  mov     r9d, eax; char *
0x18006000b  mov     edx, 2Bh ; '+'; void *
0x180060010  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180060016  mov     rcx, [rsp+268h]; this
0x18006001e  lea     r8, aOnecoreBaseLan_2; "onecore\\base\\languageoverlay\\common"...
0x180060025  mov     r9d, eax; char *
0x180060028  mov     edx, 21h ; '!'; void *
0x18006002d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180060033  mov     rcx, [rsp+268h]; this
0x18006003b  lea     r8, aOnecoreBaseLan_2; "onecore\\base\\languageoverlay\\common"...
0x180060042  mov     edx, 25h ; '%'; void *
0x180060047  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006004d  mov     rcx, [rsp+268h]; this
0x180060055  lea     r8, aOnecoreBaseLan_2; "onecore\\base\\languageoverlay\\common"...
0x18006005c  mov     r9d, eax; char *
0x18006005f  mov     edx, 2Ah ; '*'; void *
0x180060064  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
