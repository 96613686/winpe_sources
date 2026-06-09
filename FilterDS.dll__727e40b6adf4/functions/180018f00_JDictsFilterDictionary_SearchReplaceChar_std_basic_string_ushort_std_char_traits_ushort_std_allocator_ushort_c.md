# JDictsFilterDictionary::SearchReplaceChar(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180018f00`
- end: `0x180018fff`
- name: `?SearchReplaceChar@JDictsFilterDictionary@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z`
- size: `255`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180018030`

## callees

- `0x18000cde4`
- `0x18000cef4`
- `0x180018f00`
- `0x18001c238`
- `0x18001e060`
- `0x180021850`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180018fdf`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018fdf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JDictsFilterDictionary::SearchReplaceChar(__int64 a1, void **a2, void **a3)
{
  int v7; // ebx
  FilterReplaceChar *v8; // rcx
  FilterReplaceCharSur *v9; // rcx
  void *v10[3]; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int64 v11; // [rsp+38h] [rbp-40h]

  if ( !*(_DWORD *)(a1 + 48) )
    return 2147500037LL;
  v7 = 0;
  std::wstring::assign(a3, (char *)&dword_180028204, 0);
  v11 = 7;
  v10[2] = 0;
  LOWORD(v10[0]) = 0;
  std::wstring::assign(v10, a2, 0, 0xFFFFFFFFFFFFFFFFuLL);
  v8 = *(FilterReplaceChar **)(a1 + 72);
  if ( v8 && !(unsigned int)FilterReplaceChar::ReplaceChars(v8, a2, a3) )
  {
    if ( v10 != a3 )
      std::wstring::assign(v10, a3, 0, 0xFFFFFFFFFFFFFFFFuLL);
    v7 = 1;
  }
  v9 = *(FilterReplaceCharSur **)(a1 + 80);
  if ( v9 && !(unsigned int)FilterReplaceCharSur::ReplaceChars(v9, v10, a3) )
    v7 = 1;
  if ( v11 >= 8 )
    operator delete(v10[0]);
  return v7 == 0;
}

```

## disassembly

```asm
0x180018f00  push    rbx
0x180018f02  push    rbp
0x180018f03  push    rsi
0x180018f04  push    rdi
0x180018f05  push    r14
0x180018f07  sub     rsp, 50h
0x180018f0b  mov     rax, cs:__security_cookie
0x180018f12  xor     rax, rsp
0x180018f15  mov     [rsp+78h+var_38], rax
0x180018f1a  mov     rdi, r8
0x180018f1d  mov     rbp, rdx
0x180018f20  mov     rsi, rcx
0x180018f23  cmp     dword ptr [rcx+30h], 0
0x180018f27  jnz     short loc_180018F33
0x180018f29  mov     eax, 80004005h
0x180018f2e  jmp     loc_180018FE7
0x180018f33  xor     ebx, ebx
0x180018f35  xor     r8d, r8d
0x180018f38  lea     rdx, dword_180028204; Src
0x180018f3f  mov     rcx, rdi; void *
0x180018f42  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180018f47  mov     [rsp+78h+var_40], 7
0x180018f50  mov     [rsp+78h+var_48], rbx
0x180018f55  xor     eax, eax
0x180018f57  mov     word ptr [rsp+78h+var_58], ax
0x180018f5c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180018f60  xor     r8d, r8d
0x180018f63  mov     rdx, rbp
0x180018f66  lea     rcx, [rsp+78h+var_58]; void *
0x180018f6b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180018f70  nop
0x180018f71  mov     rcx, [rsi+48h]
0x180018f75  lea     r14d, [rbx+1]
0x180018f79  test    rcx, rcx
0x180018f7c  jz      short loc_180018FAE
0x180018f7e  mov     r8, rdi
0x180018f81  mov     rdx, rbp
0x180018f84  call    ?ReplaceChars@FilterReplaceChar@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; FilterReplaceChar::ReplaceChars(std::wstring const &,std::wstring &)
0x180018f89  test    eax, eax
0x180018f8b  jnz     short loc_180018FAE
0x180018f8d  lea     rax, [rsp+78h+var_58]
0x180018f92  cmp     rax, rdi
0x180018f95  jz      short loc_180018FAB
0x180018f97  or      r9, 0FFFFFFFFFFFFFFFFh
0x180018f9b  xor     r8d, r8d
0x180018f9e  mov     rdx, rdi
0x180018fa1  lea     rcx, [rsp+78h+var_58]; void *
0x180018fa6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180018fab  mov     ebx, r14d
0x180018fae  mov     rcx, [rsi+50h]
0x180018fb2  test    rcx, rcx
0x180018fb5  jz      short loc_180018FCA
0x180018fb7  mov     r8, rdi
0x180018fba  lea     rdx, [rsp+78h+var_58]
0x180018fbf  call    ?ReplaceChars@FilterReplaceCharSur@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; FilterReplaceCharSur::ReplaceChars(std::wstring const &,std::wstring &)
0x180018fc4  test    eax, eax
0x180018fc6  cmovz   ebx, r14d
0x180018fca  xor     edi, edi
0x180018fcc  test    ebx, ebx
0x180018fce  setz    dil
0x180018fd2  cmp     [rsp+78h+var_40], 8
0x180018fd8  jb      short loc_180018FE5
0x180018fda  mov     rcx, [rsp+78h+var_58]
0x180018fdf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180018fe5  mov     eax, edi
0x180018fe7  mov     rcx, [rsp+78h+var_38]
0x180018fec  xor     rcx, rsp; StackCookie
0x180018fef  call    __security_check_cookie
0x180018ff4  add     rsp, 50h
0x180018ff8  pop     r14
0x180018ffa  pop     rdi
0x180018ffb  pop     rsi
0x180018ffc  pop     rbp
0x180018ffd  pop     rbx
0x180018ffe  retn
```
