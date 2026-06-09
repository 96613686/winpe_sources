# OException::OException(et::exceptionType,wchar_t const (&)[93])

- ea: `0x180005e18`
- end: `0x180005eaf`
- name: `??$?0$0FN@@OException@@QEAA@W4exceptionType@et@@AEAY0FN@$$CB_W@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000626c`

## callees

- `0x180001cc8`
- `0x1800045ec`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180005e89`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180005e89`

## string_xrefs

- `0x180005e48`: `ORegistryKey.GetValue failure: Cannot get DWORD value. The registry key is closed or not set`

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
  ArgumentWriter::Format(
    Source,
    L"ORegistryKey.GetValue failure: Cannot get DWORD value. The registry key is closed or not set",
    92);
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
0x180005e18  push    rbx
0x180005e1a  sub     rsp, 50h
0x180005e1e  mov     rax, cs:__security_cookie
0x180005e25  xor     rax, rsp
0x180005e28  mov     [rsp+58h+var_10], rax
0x180005e2d  xor     eax, eax
0x180005e2f  mov     dword ptr [rcx], 3Ah ; ':'
0x180005e35  mov     rbx, rcx
0x180005e38  mov     [rcx+204h], eax
0x180005e3e  mov     dword ptr [rcx+388h], 30303030h
0x180005e48  lea     rdx, aOregistrykeyGe_0; "ORegistryKey.GetValue failure: Cannot g"...
0x180005e4f  mov     [rcx+308h], ax
0x180005e56  mov     [rcx+208h], ax
0x180005e5d  lea     r8d, [rax+5Ch]
0x180005e61  lea     rcx, [rsp+58h+Source]
0x180005e66  call    ?Format@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W_K@Z; ArgumentWriter::Format(wchar_t const *,unsigned __int64)
0x180005e6b  cmp     [rsp+58h+var_18], 7
0x180005e71  lea     r8, [rsp+58h+Source]
0x180005e76  lea     rcx, [rbx+4]; Destination
0x180005e7a  mov     edx, 100h; SizeInWords
0x180005e7f  cmova   r8, [rsp+58h+Source]; Source
0x180005e85  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180005e89  call    cs:__imp_wcsncpy_s
0x180005e8f  lea     rcx, [rsp+58h+Source]
0x180005e94  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180005e99  mov     rax, rbx
0x180005e9c  mov     rcx, [rsp+58h+var_10]
0x180005ea1  xor     rcx, rsp; StackCookie
0x180005ea4  call    __security_check_cookie
0x180005ea9  add     rsp, 50h
0x180005ead  pop     rbx
0x180005eae  retn
```
