# RegReader::DecodeRegKeyFromRegPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180015a6c`
- end: `0x180015b98`
- name: `?DecodeRegKeyFromRegPath@RegReader@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `300`
- prototype: `void __fastcall(void **, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180012560`
- `0x1800127b8`

## callees

- `0x18000cde4`
- `0x180015a6c`
- `0x1800163b8`
- `0x180021850`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180015b5f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015b71`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015b5f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015b71`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RegReader::DecodeRegKeyFromRegPath(void **a1, _QWORD *a2)
{
  _WORD *v4; // rcx
  unsigned __int64 last_of; // rax
  unsigned __int64 v6; // rdi
  void *v7[3]; // [rsp+28h] [rbp-48h] BYREF
  unsigned __int64 v8; // [rsp+40h] [rbp-30h]
  void *v9[3]; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 v10; // [rsp+60h] [rbp-10h]

  if ( a2[3] < 8u )
    v4 = a2;
  else
    v4 = (_WORD *)*a2;
  a2[2] = 0;
  *v4 = 0;
  if ( a1[2] )
  {
    last_of = std::wstring::find_last_of(a1);
    v6 = last_of;
    if ( last_of )
    {
      if ( last_of != -1 )
      {
        v10 = 7;
        v9[2] = 0;
        LOWORD(v9[0]) = 0;
        std::wstring::assign(v9, a1, 0, last_of);
        v8 = 7;
        v7[2] = 0;
        LOWORD(v7[0]) = 0;
        std::wstring::assign(v7, a1, v6 + 1, 0xFFFFFFFFFFFFFFFFuLL);
        std::wstring::assign(a1, v9, 0, 0xFFFFFFFFFFFFFFFFuLL);
        std::wstring::assign((void **)a2, v7, 0, 0xFFFFFFFFFFFFFFFFuLL);
        if ( v8 >= 8 )
          operator delete(v7[0]);
        if ( v10 >= 8 )
          operator delete(v9[0]);
      }
    }
  }
}

```

## disassembly

```asm
0x180015a6c  mov     [rsp-18h+arg_10], rbx
0x180015a71  mov     [rsp-18h+arg_18], rsi
0x180015a76  push    rbp
0x180015a77  push    rdi
0x180015a78  push    r12
0x180015a7a  mov     rbp, rsp
0x180015a7d  sub     rsp, 70h
0x180015a81  mov     rax, cs:__security_cookie
0x180015a88  xor     rax, rsp
0x180015a8b  mov     [rbp+var_8], rax
0x180015a8f  mov     rbx, rdx
0x180015a92  mov     rsi, rcx
0x180015a95  cmp     qword ptr [rdx+18h], 8
0x180015a9a  jb      short loc_180015AA1
0x180015a9c  mov     rcx, [rdx]
0x180015a9f  jmp     short loc_180015AA4
0x180015aa1  mov     rcx, rbx
0x180015aa4  mov     qword ptr [rdx+10h], 0
0x180015aac  xor     eax, eax
0x180015aae  mov     [rcx], ax
0x180015ab1  cmp     [rsi+10h], rax
0x180015ab5  jz      loc_180015B77
0x180015abb  mov     rcx, rsi
0x180015abe  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find_last_of(ushort,unsigned __int64)
0x180015ac3  mov     rdi, rax
0x180015ac6  test    rax, rax
0x180015ac9  jz      loc_180015B77
0x180015acf  or      r12, 0FFFFFFFFFFFFFFFFh
0x180015ad3  cmp     rax, r12
0x180015ad6  jz      loc_180015B77
0x180015adc  mov     [rbp+var_10], 7
0x180015ae4  mov     [rbp+var_18], 0
0x180015aec  xor     ecx, ecx
0x180015aee  mov     word ptr [rbp+var_28], cx
0x180015af2  mov     r9, rax
0x180015af5  xor     r8d, r8d
0x180015af8  mov     rdx, rsi
0x180015afb  lea     rcx, [rbp+var_28]; void *
0x180015aff  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180015b04  nop
0x180015b05  mov     [rbp+var_30], 7
0x180015b0d  mov     [rbp+var_38], 0
0x180015b15  xor     eax, eax
0x180015b17  mov     word ptr [rbp+var_48], ax
0x180015b1b  lea     r8, [rdi+1]
0x180015b1f  mov     r9, r12
0x180015b22  mov     rdx, rsi
0x180015b25  lea     rcx, [rbp+var_48]; void *
0x180015b29  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180015b2e  nop
0x180015b2f  mov     r9, r12
0x180015b32  xor     r8d, r8d
0x180015b35  lea     rdx, [rbp+var_28]
0x180015b39  mov     rcx, rsi; void *
0x180015b3c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180015b41  mov     r9, r12
0x180015b44  xor     r8d, r8d
0x180015b47  lea     rdx, [rbp+var_48]
0x180015b4b  mov     rcx, rbx; void *
0x180015b4e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180015b53  nop
0x180015b54  cmp     [rbp+var_30], 8
0x180015b59  jb      short loc_180015B66
0x180015b5b  mov     rcx, [rbp+var_48]
0x180015b5f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180015b65  nop
0x180015b66  cmp     [rbp+var_10], 8
0x180015b6b  jb      short loc_180015B77
0x180015b6d  mov     rcx, [rbp+var_28]
0x180015b71  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180015b77  mov     rcx, [rbp+var_8]
0x180015b7b  xor     rcx, rsp; StackCookie
0x180015b7e  call    __security_check_cookie
0x180015b83  lea     r11, [rsp+70h+var_s0]
0x180015b88  mov     rbx, [r11+30h]
0x180015b8c  mov     rsi, [r11+38h]
0x180015b90  mov     rsp, r11
0x180015b93  pop     r12
0x180015b95  pop     rdi
0x180015b96  pop     rbp
0x180015b97  retn
```
