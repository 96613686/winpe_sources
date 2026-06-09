# CSecurityCache::_InitToken(void)

- ea: `0x1800a4ffc`
- end: `0x1800a507e`
- name: `?_InitToken@CSecurityCache@@AEAAXXZ`
- size: `130`
- prototype: `void(CSecurityCache *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a4ef0`

## callees

- `0x180038f08`
- `0x1800a4ffc`
- `0x1801480fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a506d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a506d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a5006`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a5006`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a501b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a501b`

## string_xrefs

- `0x1800a502e`: `[CIWrapper] CSecurityCache: failed to get token handle. Error (%d) \n`
- `0x1800a5058`: `onecoreuap\base\appmodel\search\tquery\mssci\seccache.cxx`
- `0x1800a503a`: `"onecoreuap\\base\\appmodel\\search\\tquery\\mssci\\seccache.cxx"`

## pseudocode

```c
void __fastcall CSecurityCache::_InitToken(CSecurityCache *this)
{
  void **v1; // rbx
  HANDLE CurrentThread; // rax
  signed int v3; // ebx
  DWORD LastError; // eax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (void **)((char *)this + 64);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, v1) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError != 1008 )
    {
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\mssci\\\\seccache.cxx\"",
        (const wchar_t *)0x45,
        (unsigned int)L"[CIWrapper] CSecurityCache: failed to get token handle. Error (%d) \n",
        (const wchar_t *)LastError);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\mssci\\seccache.cxx",
        (const char *)(unsigned int)v3,
        v5);
    }
  }
}

```

## disassembly

```asm
0x1800a4ffc  push    rbx; int
0x1800a4ffe  sub     rsp, 20h
0x1800a5002  lea     rbx, [rcx+40h]
0x1800a5006  call    cs:__imp_GetCurrentThread
0x1800a500c  mov     edx, 0Eh; DesiredAccess
0x1800a5011  mov     r9, rbx; TokenHandle
0x1800a5014  mov     rcx, rax; ThreadHandle
0x1800a5017  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1800a501b  call    cs:__imp_OpenThreadToken
0x1800a5021  test    eax, eax
0x1800a5023  jz      short loc_1800A506D
0x1800a5025  add     rsp, 20h
0x1800a5029  pop     rbx
0x1800a502a  retn
0x1800a502b  mov     r9d, ebx; wchar_t *
0x1800a502e  lea     r8, aCiwrapperCsecu; "[CIWrapper] CSecurityCache: failed to g"...
0x1800a5035  mov     edx, 45h ; 'E'; wchar_t *
0x1800a503a  lea     rcx, aOnecoreuapBase_305; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800a5041  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800a5046  test    ebx, ebx
0x1800a5048  jle     short loc_1800A5053
0x1800a504a  movzx   ebx, bx
0x1800a504d  or      ebx, 80070000h
0x1800a5053  mov     rcx, [rsp+28h]; this
0x1800a5058  lea     r8, aOnecoreuapBase_299; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800a505f  mov     r9d, ebx; char *
0x1800a5062  mov     edx, 47h ; 'G'; void *
0x1800a5067  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a506d  call    cs:__imp_GetLastError
0x1800a5073  mov     ebx, eax
0x1800a5075  cmp     eax, 3F0h
0x1800a507a  jz      short loc_1800A5025
0x1800a507c  jmp     short loc_1800A502B
```
