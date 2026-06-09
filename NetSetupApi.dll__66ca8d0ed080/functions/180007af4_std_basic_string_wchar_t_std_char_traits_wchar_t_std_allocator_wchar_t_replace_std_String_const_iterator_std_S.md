# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::replace(std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,wchar_t *,wchar_t *)

- ea: `0x180007af4`
- end: `0x180007bb1`
- name: `?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@2@0PEA_W1@Z`
- size: `189`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, _BYTE *, _BYTE *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800079b4`

## callees

- `0x180007478`
- `0x180007528`
- `0x180007af4`
- `0x1800119f0`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace(_QWORD *a1, __int64 a2, __int64 a3, _BYTE *a4, _BYTE *a5)
{
  _QWORD *v5; // rbx
  unsigned __int64 v6; // rax
  __int64 v8; // r8
  unsigned __int64 v9; // r8
  _QWORD *v10; // r9

  v5 = a1;
  v6 = 0;
  if ( a4 == a5 )
  {
    if ( a3 )
      v8 = (a3 - a2) >> 1;
    else
      v8 = 0;
    if ( a1[3] >= 8u )
      a1 = (_QWORD *)*a1;
    if ( a2 )
      v6 = (a2 - (__int64)a1) >> 1;
    std::wstring::erase(v5, v6, v8);
  }
  else
  {
    if ( a3 )
      v9 = (a3 - a2) >> 1;
    else
      v9 = 0;
    if ( a1[3] < 8u )
      v10 = a1;
    else
      v10 = (_QWORD *)*a1;
    if ( a2 )
      v6 = (a2 - (__int64)v10) >> 1;
    std::wstring::replace(a1, v6, v9, a4, (a5 - a4) >> 1);
  }
  return v5;
}

```

## disassembly

```asm
0x180007af4  push    rbx
0x180007af6  sub     rsp, 40h
0x180007afa  mov     rax, cs:__security_cookie
0x180007b01  xor     rax, rsp
0x180007b04  mov     [rsp+48h+var_18], rax
0x180007b09  mov     rbx, rcx
0x180007b0c  xor     eax, eax
0x180007b0e  mov     rcx, [rsp+48h+arg_20]
0x180007b13  mov     r10, r9
0x180007b16  cmp     r9, rcx
0x180007b19  jnz     short loc_180007B55
0x180007b1b  test    r8, r8
0x180007b1e  jnz     short loc_180007B25
0x180007b20  mov     r8d, eax
0x180007b23  jmp     short loc_180007B2B
0x180007b25  sub     r8, rdx
0x180007b28  sar     r8, 1
0x180007b2b  cmp     qword ptr [rbx+18h], 8
0x180007b30  jb      short loc_180007B37
0x180007b32  mov     rcx, [rbx]
0x180007b35  jmp     short loc_180007B3A
0x180007b37  mov     rcx, rbx
0x180007b3a  test    rdx, rdx
0x180007b3d  jz      short loc_180007B48
0x180007b3f  mov     rax, rdx
0x180007b42  sub     rax, rcx
0x180007b45  sar     rax, 1
0x180007b48  mov     rdx, rax
0x180007b4b  mov     rcx, rbx
0x180007b4e  call    ?erase@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x180007b53  jmp     short loc_180007B9B
0x180007b55  test    r8, r8
0x180007b58  jnz     short loc_180007B5F
0x180007b5a  mov     r8, rax
0x180007b5d  jmp     short loc_180007B65
0x180007b5f  sub     r8, rdx
0x180007b62  sar     r8, 1
0x180007b65  cmp     qword ptr [rbx+18h], 8
0x180007b6a  jb      short loc_180007B71
0x180007b6c  mov     r9, [rbx]
0x180007b6f  jmp     short loc_180007B74
0x180007b71  mov     r9, rbx
0x180007b74  test    rdx, rdx
0x180007b77  jz      short loc_180007B82
0x180007b79  mov     rax, rdx
0x180007b7c  sub     rax, r9
0x180007b7f  sar     rax, 1
0x180007b82  sub     rcx, r10
0x180007b85  mov     r9, r10
0x180007b88  sar     rcx, 1
0x180007b8b  mov     rdx, rax
0x180007b8e  mov     [rsp+48h+var_28], rcx
0x180007b93  mov     rcx, rbx
0x180007b96  call    ?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K0PEB_W0@Z; std::wstring::replace(unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)
0x180007b9b  mov     rax, rbx
0x180007b9e  mov     rcx, [rsp+48h+var_18]
0x180007ba3  xor     rcx, rsp; StackCookie
0x180007ba6  call    __security_check_cookie
0x180007bab  add     rsp, 40h
0x180007baf  pop     rbx
0x180007bb0  retn
```
