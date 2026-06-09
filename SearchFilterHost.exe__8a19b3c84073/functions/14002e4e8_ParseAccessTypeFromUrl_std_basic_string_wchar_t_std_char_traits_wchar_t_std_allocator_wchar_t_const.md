# ParseAccessTypeFromUrl(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x14002e4e8`
- end: `0x14002e5c5`
- name: `?ParseAccessTypeFromUrl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV12@@Z`
- size: `221`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002ec84`
- `0x14002ee58`

## callees

- `0x1400030a0`
- `0x140005f10`
- `0x14002dfb4`
- `0x14002e4e8`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x14002e52d`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x14002e52d`
- `api-ms-win-core-url-l1-1-0!UrlGetPartW` at `0x14002e564`
- `api-ms-win-core-url-l1-1-0!UrlGetPartW` at `0x14002e564`

## string_xrefs

- `0x14002e57f`: `onecoreuap\base\appmodel\Search\common\include\SemanticSearchUtil.h`
- `0x14002e573`: `[ParseAccessTypeFromUrl] accessType: %s`

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
      (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\common\\include\\SemanticSearchUtil.h",
      (const wchar_t *)0x232,
      (unsigned int)L"[ParseAccessTypeFromUrl] accessType: %s",
      pszOut);
    v5 = pszOut;
  }
  else
  {
LABEL_10:
    v5 = (WCHAR *)&dword_140053AD4;
  }
  std::wstring::wstring(a1, (__int64)v5);
  return a1;
}

```

## disassembly

```asm
0x14002e4e8  mov     rax, rsp
0x14002e4eb  push    rdi
0x14002e4ec  sub     rsp, 90h
0x14002e4f3  mov     qword ptr [rax-60h], 0FFFFFFFFFFFFFFFEh
0x14002e4fb  mov     [rax+18h], rbx
0x14002e4ff  mov     rax, cs:__security_cookie
0x14002e506  xor     rax, rsp
0x14002e509  mov     [rsp+98h+var_18], rax
0x14002e511  mov     rbx, rdx
0x14002e514  mov     rdi, rcx
0x14002e517  cmp     qword ptr [rdx+10h], 0
0x14002e51c  jz      short loc_14002E592
0x14002e51e  cmp     qword ptr [rdx+18h], 7
0x14002e523  jbe     short loc_14002E52A
0x14002e525  mov     rcx, [rdx]
0x14002e528  jmp     short loc_14002E52D
0x14002e52a  mov     rcx, rbx; pszPath
0x14002e52d  call    cs:__imp_PathIsURLW
0x14002e533  test    eax, eax
0x14002e535  jz      short loc_14002E592
0x14002e537  mov     [rsp+98h+pcchOut], 20h ; ' '
0x14002e53f  cmp     qword ptr [rbx+18h], 7
0x14002e544  jbe     short loc_14002E549
0x14002e546  mov     rbx, [rbx]
0x14002e549  mov     [rsp+98h+dwFlags], 0; dwFlags
0x14002e551  mov     r9d, 1; dwPart
0x14002e557  lea     r8, [rsp+98h+pcchOut]; pcchOut
0x14002e55c  lea     rdx, [rsp+98h+pszOut]; pszOut
0x14002e561  mov     rcx, rbx; pszIn
0x14002e564  call    cs:__imp_UrlGetPartW
0x14002e56a  test    eax, eax
0x14002e56c  js      short loc_14002E592
0x14002e56e  lea     r9, [rsp+98h+pszOut]; wchar_t *
0x14002e573  lea     r8, aParseaccesstyp; "[ParseAccessTypeFromUrl] accessType: %s"
0x14002e57a  mov     edx, 232h; wchar_t *
0x14002e57f  lea     rcx, aOnecoreuapBase_33; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14002e586  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x14002e58b  lea     rdx, [rsp+98h+pszOut]
0x14002e590  jmp     short loc_14002E599
0x14002e592  lea     rdx, dword_140053AD4
0x14002e599  mov     rcx, rdi
0x14002e59c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14002e5a1  mov     rax, rdi
0x14002e5a4  mov     rcx, [rsp+98h+var_18]
0x14002e5ac  xor     rcx, rsp; StackCookie
0x14002e5af  call    __security_check_cookie
0x14002e5b4  mov     rbx, [rsp+98h+arg_10]
0x14002e5bc  add     rsp, 90h
0x14002e5c3  pop     rdi
0x14002e5c4  retn
```
