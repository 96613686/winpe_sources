# ParseExtensionFromUrl(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x14002e5cc`
- end: `0x14002e67a`
- name: `?ParseExtensionFromUrl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV12@@Z`
- size: `174`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002ec84`
- `0x14002ee58`

## callees

- `0x140005f10`
- `0x14002dfb4`
- `0x14002e5cc`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x14002e629`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x14002e629`

## string_xrefs

- `0x14002e64c`: `onecoreuap\base\appmodel\Search\common\include\SemanticSearchUtil.h`
- `0x14002e640`: `[ParseExtensionFromUrl] Extension: %s`

## pseudocode

```c
__int64 __fastcall ParseExtensionFromUrl(__int64 a1, const WCHAR *a2)
{
  __int64 v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rcx
  LPWSTR ExtensionW; // rax
  const wchar_t *v7; // rbx
  const wchar_t *v8; // rdx

  v3 = *((_QWORD *)a2 + 2);
  if ( !v3 )
    goto LABEL_15;
  v4 = *((_QWORD *)a2 + 3) <= 7u ? (__int64)a2 : *(_QWORD *)a2;
  if ( *(_WORD *)(v4 + 2 * v3 - 2) == 47 )
    goto LABEL_15;
  v5 = *((_QWORD *)a2 + 3) <= 7u ? (__int64)a2 : *(_QWORD *)a2;
  if ( *(_WORD *)(v5 + 2 * v3 - 2) == 92 )
    goto LABEL_15;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  ExtensionW = PathFindExtensionW(a2);
  if ( ExtensionW && *ExtensionW )
  {
    v7 = ExtensionW + 1;
    SearchIndexerTrace::Information(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\common\\include\\SemanticSearchUtil.h",
      (const wchar_t *)0x24E,
      (unsigned int)L"[ParseExtensionFromUrl] Extension: %s",
      ExtensionW + 1,
      -2);
    v8 = v7;
  }
  else
  {
LABEL_15:
    v8 = &dword_140053AD4;
  }
  std::wstring::wstring(a1, (__int64)v8);
  return a1;
}

```

## disassembly

```asm
0x14002e5cc  push    rdi
0x14002e5ce  sub     rsp, 30h
0x14002e5d2  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14002e5db  mov     [rsp+38h+arg_0], rbx
0x14002e5e0  mov     rdi, rcx
0x14002e5e3  mov     rax, [rdx+10h]
0x14002e5e7  xor     ebx, ebx
0x14002e5e9  test    rax, rax
0x14002e5ec  jz      short loc_14002E65D
0x14002e5ee  cmp     qword ptr [rdx+18h], 7
0x14002e5f3  jbe     short loc_14002E5FA
0x14002e5f5  mov     rcx, [rdx]
0x14002e5f8  jmp     short loc_14002E5FD
0x14002e5fa  mov     rcx, rdx
0x14002e5fd  cmp     word ptr [rcx+rax*2-2], 2Fh ; '/'
0x14002e603  jz      short loc_14002E65D
0x14002e605  cmp     qword ptr [rdx+18h], 7
0x14002e60a  jbe     short loc_14002E611
0x14002e60c  mov     rcx, [rdx]
0x14002e60f  jmp     short loc_14002E614
0x14002e611  mov     rcx, rdx
0x14002e614  cmp     word ptr [rcx+rax*2-2], 5Ch ; '\'
0x14002e61a  jz      short loc_14002E65D
0x14002e61c  cmp     qword ptr [rdx+18h], 7
0x14002e621  jbe     short loc_14002E626
0x14002e623  mov     rdx, [rdx]
0x14002e626  mov     rcx, rdx; pszPath
0x14002e629  call    cs:__imp_PathFindExtensionW
0x14002e62f  test    rax, rax
0x14002e632  jz      short loc_14002E65D
0x14002e634  cmp     [rax], bx
0x14002e637  jz      short loc_14002E65D
0x14002e639  lea     rbx, [rax+2]
0x14002e63d  mov     r9, rbx; wchar_t *
0x14002e640  lea     r8, aParseextension; "[ParseExtensionFromUrl] Extension: %s"
0x14002e647  mov     edx, 24Eh; wchar_t *
0x14002e64c  lea     rcx, aOnecoreuapBase_33; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14002e653  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x14002e658  mov     rdx, rbx
0x14002e65b  jmp     short loc_14002E664
0x14002e65d  lea     rdx, dword_140053AD4
0x14002e664  mov     rcx, rdi
0x14002e667  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14002e66c  mov     rax, rdi
0x14002e66f  mov     rbx, [rsp+38h+arg_0]
0x14002e674  add     rsp, 30h
0x14002e678  pop     rdi
0x14002e679  retn
```
