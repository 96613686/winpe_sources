# ParseAccessTypeFromUrl(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1400214d4`
- end: `0x1400215b1`
- name: `?ParseAccessTypeFromUrl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV12@@Z`
- size: `221`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001f90c`
- `0x140051cb0`
- `0x140051e84`

## callees

- `0x140005240`
- `0x14000cce4`
- `0x14001eb94`
- `0x1400214d4`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x140021519`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x140021519`
- `api-ms-win-core-url-l1-1-0!UrlGetPartW` at `0x140021550`
- `api-ms-win-core-url-l1-1-0!UrlGetPartW` at `0x140021550`

## string_xrefs

- `0x14002156b`: `"onecoreuap\\base\\appmodel\\Search\\common\\include\\SemanticSearchUtil.h"`
- `0x14002155f`: `[ParseAccessTypeFromUrl] accessType: %s`

## pseudocode

```c
__int64 __fastcall ParseAccessTypeFromUrl(__int64 a1, const WCHAR *a2)
{
  const WCHAR *v2; // rbx
  const WCHAR *v4; // rcx
  WCHAR *v5; // rdx
  DWORD pcchOut; // [rsp+30h] [rbp-68h] BYREF
  __int64 v8; // [rsp+38h] [rbp-60h]
  WCHAR pszOut[32]; // [rsp+40h] [rbp-58h] BYREF

  v8 = -2;
  v2 = a2;
  if ( !*((_QWORD *)a2 + 2) )
    goto LABEL_10;
  v4 = *((_QWORD *)a2 + 3) <= 7u ? a2 : *(const WCHAR **)a2;
  if ( !PathIsURLW(v4) )
    goto LABEL_10;
  pcchOut = 32;
  if ( *((_QWORD *)v2 + 3) > 7u )
    v2 = *(const WCHAR **)v2;
  if ( UrlGetPartW(v2, pszOut, &pcchOut, 1u, 0) >= 0 )
  {
    SearchIndexerTrace::Information(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\Search\\\\common\\\\include\\\\SemanticSearchUtil.h\"",
      (const wchar_t *)0x232,
      (unsigned int)L"[ParseAccessTypeFromUrl] accessType: %s",
      pszOut);
    v5 = pszOut;
  }
  else
  {
LABEL_10:
    v5 = (WCHAR *)&dword_14007696C;
  }
  std::wstring::wstring(a1, v5);
  return a1;
}

```

## disassembly

```asm
0x1400214d4  mov     rax, rsp
0x1400214d7  push    rdi
0x1400214d8  sub     rsp, 90h
0x1400214df  mov     qword ptr [rax-60h], 0FFFFFFFFFFFFFFFEh
0x1400214e7  mov     [rax+18h], rbx
0x1400214eb  mov     rax, cs:__security_cookie
0x1400214f2  xor     rax, rsp
0x1400214f5  mov     [rsp+98h+var_18], rax
0x1400214fd  mov     rbx, rdx
0x140021500  mov     rdi, rcx
0x140021503  cmp     qword ptr [rdx+10h], 0
0x140021508  jz      short loc_14002157E
0x14002150a  cmp     qword ptr [rdx+18h], 7
0x14002150f  jbe     short loc_140021516
0x140021511  mov     rcx, [rdx]
0x140021514  jmp     short loc_140021519
0x140021516  mov     rcx, rbx; pszPath
0x140021519  call    cs:__imp_PathIsURLW
0x14002151f  test    eax, eax
0x140021521  jz      short loc_14002157E
0x140021523  mov     [rsp+98h+pcchOut], 20h ; ' '
0x14002152b  cmp     qword ptr [rbx+18h], 7
0x140021530  jbe     short loc_140021535
0x140021532  mov     rbx, [rbx]
0x140021535  mov     [rsp+98h+dwFlags], 0; dwFlags
0x14002153d  mov     r9d, 1; dwPart
0x140021543  lea     r8, [rsp+98h+pcchOut]; pcchOut
0x140021548  lea     rdx, [rsp+98h+pszOut]; pszOut
0x14002154d  mov     rcx, rbx; pszIn
0x140021550  call    cs:__imp_UrlGetPartW
0x140021556  test    eax, eax
0x140021558  js      short loc_14002157E
0x14002155a  lea     r9, [rsp+98h+pszOut]; wchar_t *
0x14002155f  lea     r8, aParseaccesstyp; "[ParseAccessTypeFromUrl] accessType: %s"
0x140021566  mov     edx, 232h; wchar_t *
0x14002156b  lea     rcx, aOnecoreuapBase_33; "\"onecoreuap\\\\base\\\\appmodel\\\\Sea"...
0x140021572  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x140021577  lea     rdx, [rsp+98h+pszOut]
0x14002157c  jmp     short loc_140021585
0x14002157e  lea     rdx, dword_14007696C
0x140021585  mov     rcx, rdi
0x140021588  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14002158d  mov     rax, rdi
0x140021590  mov     rcx, [rsp+98h+var_18]
0x140021598  xor     rcx, rsp; StackCookie
0x14002159b  call    __security_check_cookie
0x1400215a0  mov     rbx, [rsp+98h+arg_10]
0x1400215a8  add     rsp, 90h
0x1400215af  pop     rdi
0x1400215b0  retn
```
