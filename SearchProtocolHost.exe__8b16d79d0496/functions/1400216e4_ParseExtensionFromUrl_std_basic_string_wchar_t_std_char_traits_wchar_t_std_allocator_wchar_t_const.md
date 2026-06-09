# ParseExtensionFromUrl(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1400216e4`
- end: `0x140021792`
- name: `?ParseExtensionFromUrl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV12@@Z`
- size: `174`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001f90c`
- `0x14003ffd0`
- `0x140041564`
- `0x140051cb0`
- `0x140051e84`

## callees

- `0x14000cce4`
- `0x14001eb94`
- `0x1400216e4`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x140021741`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x140021741`

## string_xrefs

- `0x140021764`: `"onecoreuap\\base\\appmodel\\Search\\common\\include\\SemanticSearchUtil.h"`
- `0x140021758`: `[ParseExtensionFromUrl] Extension: %s`

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
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\Search\\\\common\\\\include\\\\SemanticSearchUtil.h\"",
      (const wchar_t *)0x24E,
      (unsigned int)L"[ParseExtensionFromUrl] Extension: %s",
      ExtensionW + 1,
      -2);
    v8 = v7;
  }
  else
  {
LABEL_15:
    v8 = &dword_14007696C;
  }
  std::wstring::wstring(a1, v8);
  return a1;
}

```

## disassembly

```asm
0x1400216e4  push    rdi
0x1400216e6  sub     rsp, 30h
0x1400216ea  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1400216f3  mov     [rsp+38h+arg_0], rbx
0x1400216f8  mov     rdi, rcx
0x1400216fb  mov     rax, [rdx+10h]
0x1400216ff  xor     ebx, ebx
0x140021701  test    rax, rax
0x140021704  jz      short loc_140021775
0x140021706  cmp     qword ptr [rdx+18h], 7
0x14002170b  jbe     short loc_140021712
0x14002170d  mov     rcx, [rdx]
0x140021710  jmp     short loc_140021715
0x140021712  mov     rcx, rdx
0x140021715  cmp     word ptr [rcx+rax*2-2], 2Fh ; '/'
0x14002171b  jz      short loc_140021775
0x14002171d  cmp     qword ptr [rdx+18h], 7
0x140021722  jbe     short loc_140021729
0x140021724  mov     rcx, [rdx]
0x140021727  jmp     short loc_14002172C
0x140021729  mov     rcx, rdx
0x14002172c  cmp     word ptr [rcx+rax*2-2], 5Ch ; '\'
0x140021732  jz      short loc_140021775
0x140021734  cmp     qword ptr [rdx+18h], 7
0x140021739  jbe     short loc_14002173E
0x14002173b  mov     rdx, [rdx]
0x14002173e  mov     rcx, rdx; pszPath
0x140021741  call    cs:__imp_PathFindExtensionW
0x140021747  test    rax, rax
0x14002174a  jz      short loc_140021775
0x14002174c  cmp     [rax], bx
0x14002174f  jz      short loc_140021775
0x140021751  lea     rbx, [rax+2]
0x140021755  mov     r9, rbx; wchar_t *
0x140021758  lea     r8, aParseextension; "[ParseExtensionFromUrl] Extension: %s"
0x14002175f  mov     edx, 24Eh; wchar_t *
0x140021764  lea     rcx, aOnecoreuapBase_33; "\"onecoreuap\\\\base\\\\appmodel\\\\Sea"...
0x14002176b  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x140021770  mov     rdx, rbx
0x140021773  jmp     short loc_14002177C
0x140021775  lea     rdx, dword_14007696C
0x14002177c  mov     rcx, rdi
0x14002177f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140021784  mov     rax, rdi
0x140021787  mov     rbx, [rsp+38h+arg_0]
0x14002178c  add     rsp, 30h
0x140021790  pop     rdi
0x140021791  retn
```
