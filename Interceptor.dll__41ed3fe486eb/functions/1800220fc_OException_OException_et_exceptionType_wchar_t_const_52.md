# OException::OException(et::exceptionType,wchar_t const (&)[52])

- ea: `0x1800220fc`
- end: `0x180022193`
- name: `??$?0$0DE@@OException@@QEAA@W4exceptionType@et@@AEAY0DE@$$CB_W@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010f0`

## callees

- `0x180001cc8`
- `0x1800045ec`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18002216d`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18002216d`

## string_xrefs

- `0x18002212c`: `A log for this process has already been initialized`

## pseudocode

```c
__int64 __fastcall OException::OException(__int64 a1)
{
  const wchar_t *v2; // r8
  wchar_t *Source[4]; // [rsp+28h] [rbp-30h] BYREF

  *(_DWORD *)a1 = 47;
  *(_DWORD *)(a1 + 516) = 0;
  *(_DWORD *)(a1 + 904) = 808464432;
  *(_WORD *)(a1 + 776) = 0;
  *(_WORD *)(a1 + 520) = 0;
  ArgumentWriter::Format(Source, L"A log for this process has already been initialized", 51);
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
0x1800220fc  push    rbx
0x1800220fe  sub     rsp, 50h
0x180022102  mov     rax, cs:__security_cookie
0x180022109  xor     rax, rsp
0x18002210c  mov     [rsp+58h+var_10], rax
0x180022111  xor     eax, eax
0x180022113  mov     dword ptr [rcx], 2Fh ; '/'
0x180022119  mov     rbx, rcx
0x18002211c  mov     [rcx+204h], eax
0x180022122  mov     dword ptr [rcx+388h], 30303030h
0x18002212c  lea     rdx, aALogForThisPro; "A log for this process has already been"...
0x180022133  mov     [rcx+308h], ax
0x18002213a  mov     [rcx+208h], ax
0x180022141  lea     r8d, [rax+33h]
0x180022145  lea     rcx, [rsp+58h+Source]
0x18002214a  call    ?Format@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W_K@Z; ArgumentWriter::Format(wchar_t const *,unsigned __int64)
0x18002214f  cmp     [rsp+58h+var_18], 7
0x180022155  lea     r8, [rsp+58h+Source]
0x18002215a  lea     rcx, [rbx+4]; Destination
0x18002215e  mov     edx, 100h; SizeInWords
0x180022163  cmova   r8, [rsp+58h+Source]; Source
0x180022169  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18002216d  call    cs:__imp_wcsncpy_s
0x180022173  lea     rcx, [rsp+58h+Source]
0x180022178  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002217d  mov     rax, rbx
0x180022180  mov     rcx, [rsp+58h+var_10]
0x180022185  xor     rcx, rsp; StackCookie
0x180022188  call    __security_check_cookie
0x18002218d  add     rsp, 50h
0x180022191  pop     rbx
0x180022192  retn
```
