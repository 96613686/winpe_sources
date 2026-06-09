# OException::OException(et::exceptionType,wchar_t const (&)[93],std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800063f4`
- end: `0x1800064aa`
- name: `??$?0$0FN@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@OException@@QEAA@W4exceptionType@et@@AEAY0FN@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800052dc`

## callees

- `0x1800045ec`
- `0x1800048a8`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180006442`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180006484`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180006442`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180006484`

## string_xrefs

- `0x180006417`: `ORegistryKey.Open failure: The length of subkey %s is longer than the maximum length allowed`
- `0x180006455`: `ORegistryKey.Open failure: The length of subkey %s is longer than the maximum length allowed`

## pseudocode

```c
__int64 __fastcall OException::OException(__int64 a1)
{
  const wchar_t *v2; // r8
  wchar_t *Source[4]; // [rsp+28h] [rbp-30h] BYREF

  *(_DWORD *)a1 = 29;
  *(_DWORD *)(a1 + 516) = 0;
  *(_WORD *)(a1 + 776) = 0;
  *(_DWORD *)(a1 + 904) = 808464432;
  wcsncpy_s(
    (wchar_t *)(a1 + 520),
    0x80u,
    L"ORegistryKey.Open failure: The length of subkey %s is longer than the maximum length allowed",
    0xFFFFFFFFFFFFFFFFuLL);
  ArgumentWriter::Format<std::wstring>(
    Source,
    L"ORegistryKey.Open failure: The length of subkey %s is longer than the maximum length allowed",
    92,
    &lpSubKey);
  v2 = (const wchar_t *)Source;
  if ( Source[3] > (wchar_t *)7 )
    v2 = Source[0];
  wcsncpy_s((wchar_t *)(a1 + 4), 0x100u, v2, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::_Tidy_deallocate(Source);
  return a1;
}

```

## disassembly

```asm
0x1800063f4  push    rbx
0x1800063f6  sub     rsp, 50h
0x1800063fa  mov     rax, cs:__security_cookie
0x180006401  xor     rax, rsp
0x180006404  mov     [rsp+58h+var_10], rax
0x180006409  xor     eax, eax
0x18000640b  mov     dword ptr [rcx], 1Dh
0x180006411  mov     [rcx+204h], eax
0x180006417  lea     r8, aOregistrykeyOp; "ORegistryKey.Open failure: The length o"...
0x18000641e  mov     [rcx+308h], ax
0x180006425  mov     rbx, rcx
0x180006428  mov     dword ptr [rcx+388h], 30303030h
0x180006432  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180006436  add     rcx, 208h; Destination
0x18000643d  mov     edx, 80h; SizeInWords
0x180006442  call    cs:__imp_wcsncpy_s
0x180006448  lea     r9, lpSubKey
0x18000644f  mov     r8d, 5Ch ; '\'
0x180006455  lea     rdx, aOregistrykeyOp; "ORegistryKey.Open failure: The length o"...
0x18000645c  lea     rcx, [rsp+58h+Source]
0x180006461  call    ??$Format@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W_KAEBV12@@Z; ArgumentWriter::Format<std::wstring>(wchar_t const *,unsigned __int64,std::wstring const &)
0x180006466  cmp     [rsp+58h+var_18], 7
0x18000646c  lea     r8, [rsp+58h+Source]
0x180006471  lea     rcx, [rbx+4]; Destination
0x180006475  mov     edx, 100h; SizeInWords
0x18000647a  cmova   r8, [rsp+58h+Source]; Source
0x180006480  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180006484  call    cs:__imp_wcsncpy_s
0x18000648a  lea     rcx, [rsp+58h+Source]
0x18000648f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180006494  mov     rax, rbx
0x180006497  mov     rcx, [rsp+58h+var_10]
0x18000649c  xor     rcx, rsp; StackCookie
0x18000649f  call    __security_check_cookie
0x1800064a4  add     rsp, 50h
0x1800064a8  pop     rbx
0x1800064a9  retn
```
