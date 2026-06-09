# OException::OException(et::exceptionType,wchar_t const (&)[46])

- ea: `0x18000635c`
- end: `0x1800063f3`
- name: `??$?0$0CO@@OException@@QEAA@W4exceptionType@et@@AEAY0CO@$$CB_W@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800052dc`

## callees

- `0x180001cc8`
- `0x1800045ec`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1800063cd`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1800063cd`

## string_xrefs

- `0x18000638c`: `ORegistryKey.Open failure: Parent key is NULL`

## pseudocode

```c
__int64 __fastcall OException::OException(__int64 a1)
{
  const wchar_t *v2; // r8
  wchar_t *Source[4]; // [rsp+28h] [rbp-30h] BYREF

  *(_DWORD *)a1 = 58;
  *(_DWORD *)(a1 + 516) = 0;
  *(_DWORD *)(a1 + 904) = 808464432;
  *(_WORD *)(a1 + 776) = 0;
  *(_WORD *)(a1 + 520) = 0;
  ArgumentWriter::Format(Source, L"ORegistryKey.Open failure: Parent key is NULL", 45);
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
0x18000635c  push    rbx
0x18000635e  sub     rsp, 50h
0x180006362  mov     rax, cs:__security_cookie
0x180006369  xor     rax, rsp
0x18000636c  mov     [rsp+58h+var_10], rax
0x180006371  xor     eax, eax
0x180006373  mov     dword ptr [rcx], 3Ah ; ':'
0x180006379  mov     rbx, rcx
0x18000637c  mov     [rcx+204h], eax
0x180006382  mov     dword ptr [rcx+388h], 30303030h
0x18000638c  lea     rdx, aOregistrykeyOp_0; "ORegistryKey.Open failure: Parent key i"...
0x180006393  mov     [rcx+308h], ax
0x18000639a  mov     [rcx+208h], ax
0x1800063a1  lea     r8d, [rax+2Dh]
0x1800063a5  lea     rcx, [rsp+58h+Source]
0x1800063aa  call    ?Format@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W_K@Z; ArgumentWriter::Format(wchar_t const *,unsigned __int64)
0x1800063af  cmp     [rsp+58h+var_18], 7
0x1800063b5  lea     r8, [rsp+58h+Source]
0x1800063ba  lea     rcx, [rbx+4]; Destination
0x1800063be  mov     edx, 100h; SizeInWords
0x1800063c3  cmova   r8, [rsp+58h+Source]; Source
0x1800063c9  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800063cd  call    cs:__imp_wcsncpy_s
0x1800063d3  lea     rcx, [rsp+58h+Source]
0x1800063d8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800063dd  mov     rax, rbx
0x1800063e0  mov     rcx, [rsp+58h+var_10]
0x1800063e5  xor     rcx, rsp; StackCookie
0x1800063e8  call    __security_check_cookie
0x1800063ed  add     rsp, 50h
0x1800063f1  pop     rbx
0x1800063f2  retn
```
