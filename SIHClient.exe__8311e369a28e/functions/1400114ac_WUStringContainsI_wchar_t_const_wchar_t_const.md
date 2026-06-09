# WUStringContainsI(wchar_t const *,wchar_t const *)

- ea: `0x1400114ac`
- end: `0x14001155f`
- name: `?WUStringContainsI@@YAHPEB_W0@Z`
- size: `179`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000f5ac`

## callees

- `0x140011290`
- `0x1400114ac`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14001152e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14001152e`

## pseudocode

```c
__int64 __fastcall WUStringContainsI(PCNZWCH lpString1, const wchar_t *a2)
{
  unsigned __int64 v2; // rbx
  const WCHAR *v4; // rdi
  int cchCount2; // esi
  unsigned __int64 v6; // rbp
  unsigned __int64 v8; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int64 cchCount1; // [rsp+60h] [rbp+18h] BYREF

  v2 = 0;
  v4 = lpString1;
  if ( !lpString1 )
    return 0xFFFFFFFFLL;
  if ( !a2 )
    return 0xFFFFFFFFLL;
  v8 = 0;
  cchCount1 = 0;
  if ( SusStrCchLen(lpString1, 0x7FFFFFFFu, &v8) < 0 )
    return 0xFFFFFFFFLL;
  if ( SusStrCchLen(a2, 0x7FFFFFFFu, &cchCount1) < 0 )
    return 0xFFFFFFFFLL;
  cchCount2 = cchCount1;
  if ( v8 < cchCount1 || !cchCount1 )
    return 0xFFFFFFFFLL;
  v6 = v8 - cchCount1;
  while ( CompareStringW(0x7Fu, 1u, v4, cchCount2, a2, cchCount2) != 2 )
  {
    ++v2;
    ++v4;
    if ( v2 > v6 )
      return 0xFFFFFFFFLL;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400114ac  mov     rax, rsp
0x1400114af  mov     [rax+10h], rbx
0x1400114b3  mov     [rax+20h], rbp
0x1400114b7  push    rsi
0x1400114b8  push    rdi
0x1400114b9  push    r14
0x1400114bb  sub     rsp, 30h
0x1400114bf  xor     ebx, ebx
0x1400114c1  mov     r14, rdx
0x1400114c4  mov     rdi, rcx
0x1400114c7  test    rcx, rcx
0x1400114ca  jz      short loc_140011545
0x1400114cc  test    rdx, rdx
0x1400114cf  jz      short loc_140011545
0x1400114d1  mov     esi, 7FFFFFFFh
0x1400114d6  mov     [rax+8], rbx
0x1400114da  mov     edx, esi; unsigned __int64
0x1400114dc  mov     [rax+18h], rbx
0x1400114e0  lea     r8, [rax+8]; unsigned __int64 *
0x1400114e4  call    ?SusStrCchLen@@YAJPEB_W_KPEA_K@Z; SusStrCchLen(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x1400114e9  test    eax, eax
0x1400114eb  js      short loc_140011545
0x1400114ed  lea     r8, [rsp+48h+cchCount1]; unsigned __int64 *
0x1400114f2  mov     edx, esi; unsigned __int64
0x1400114f4  mov     rcx, r14; wchar_t *
0x1400114f7  call    ?SusStrCchLen@@YAJPEB_W_KPEA_K@Z; SusStrCchLen(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x1400114fc  test    eax, eax
0x1400114fe  js      short loc_140011545
0x140011500  mov     rbp, [rsp+48h+arg_0]
0x140011505  mov     rsi, [rsp+48h+cchCount1]
0x14001150a  cmp     rbp, rsi
0x14001150d  jb      short loc_140011545
0x14001150f  test    rsi, rsi
0x140011512  jz      short loc_140011545
0x140011514  sub     rbp, rsi
0x140011517  mov     edx, 1; dwCmpFlags
0x14001151c  mov     [rsp+48h+cchCount2], esi; cchCount2
0x140011520  mov     r9d, esi; cchCount1
0x140011523  mov     [rsp+48h+lpString2], r14; lpString2
0x140011528  mov     r8, rdi; lpString1
0x14001152b  lea     ecx, [rdx+7Eh]; Locale
0x14001152e  call    cs:__imp_CompareStringW
0x140011534  cmp     eax, 2
0x140011537  jz      short loc_14001155B
0x140011539  inc     rbx
0x14001153c  add     rdi, 2
0x140011540  cmp     rbx, rbp
0x140011543  jbe     short loc_140011517
0x140011545  or      eax, 0FFFFFFFFh
0x140011548  mov     rbx, [rsp+48h+arg_8]
0x14001154d  mov     rbp, [rsp+48h+arg_18]
0x140011552  add     rsp, 30h
0x140011556  pop     r14
0x140011558  pop     rdi
0x140011559  pop     rsi
0x14001155a  retn
0x14001155b  mov     eax, ebx
0x14001155d  jmp     short loc_140011548
```
