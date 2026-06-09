# OException::OException(et::exceptionType,wchar_t const (&)[66],std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180003bb0`
- end: `0x180003c6e`
- name: `??$?0$0EC@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@OException@@QEAA@W4exceptionType@et@@AEAY0EC@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800035bc`

## callees

- `0x1800045ec`
- `0x1800048a8`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180003c05`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180003c43`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180003c05`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180003c43`

## string_xrefs

- `0x180003bd7`: `Failed to create registry key: registry key name "%s" is too long`
- `0x180003c0e`: `Failed to create registry key: registry key name "%s" is too long`

## pseudocode

```c
__int64 __fastcall OException::OException(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  const wchar_t *v6; // r8
  wchar_t *Source[4]; // [rsp+28h] [rbp-30h] BYREF

  *(_DWORD *)a1 = 33;
  *(_DWORD *)(a1 + 516) = 0;
  *(_WORD *)(a1 + 776) = 0;
  *(_DWORD *)(a1 + 904) = 808464432;
  wcsncpy_s(
    (wchar_t *)(a1 + 520),
    0x80u,
    L"Failed to create registry key: registry key name \"%s\" is too long",
    0xFFFFFFFFFFFFFFFFuLL);
  ArgumentWriter::Format<std::wstring>(
    Source,
    L"Failed to create registry key: registry key name \"%s\" is too long",
    65,
    a4);
  v6 = (const wchar_t *)Source;
  if ( Source[3] > (wchar_t *)7 )
    v6 = Source[0];
  wcsncpy_s((wchar_t *)(a1 + 4), 0x100u, v6, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::_Tidy_deallocate(Source);
  return a1;
}

```

## disassembly

```asm
0x180003bb0  mov     [rsp+arg_8], rbx
0x180003bb5  push    rdi
0x180003bb6  sub     rsp, 50h
0x180003bba  mov     rax, cs:__security_cookie
0x180003bc1  xor     rax, rsp
0x180003bc4  mov     [rsp+58h+var_10], rax
0x180003bc9  xor     eax, eax
0x180003bcb  mov     dword ptr [rcx], 21h ; '!'
0x180003bd1  mov     [rcx+204h], eax
0x180003bd7  lea     r8, aFailedToCreate; "Failed to create registry key: registry"...
0x180003bde  mov     [rcx+308h], ax
0x180003be5  mov     rbx, r9
0x180003be8  mov     rdi, rcx
0x180003beb  mov     dword ptr [rcx+388h], 30303030h
0x180003bf5  add     rcx, 208h; Destination
0x180003bfc  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180003c00  mov     edx, 80h; SizeInWords
0x180003c05  call    cs:__imp_wcsncpy_s
0x180003c0b  mov     r9, rbx
0x180003c0e  lea     rdx, aFailedToCreate; "Failed to create registry key: registry"...
0x180003c15  mov     r8d, 41h ; 'A'
0x180003c1b  lea     rcx, [rsp+58h+Source]
0x180003c20  call    ??$Format@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W_KAEBV12@@Z; ArgumentWriter::Format<std::wstring>(wchar_t const *,unsigned __int64,std::wstring const &)
0x180003c25  cmp     [rsp+58h+var_18], 7
0x180003c2b  lea     r8, [rsp+58h+Source]
0x180003c30  lea     rcx, [rdi+4]; Destination
0x180003c34  mov     edx, 100h; SizeInWords
0x180003c39  cmova   r8, [rsp+58h+Source]; Source
0x180003c3f  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180003c43  call    cs:__imp_wcsncpy_s
0x180003c49  lea     rcx, [rsp+58h+Source]
0x180003c4e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003c53  mov     rax, rdi
0x180003c56  mov     rcx, [rsp+58h+var_10]
0x180003c5b  xor     rcx, rsp; StackCookie
0x180003c5e  call    __security_check_cookie
0x180003c63  mov     rbx, [rsp+58h+arg_8]
0x180003c68  add     rsp, 50h
0x180003c6c  pop     rdi
0x180003c6d  retn
```
