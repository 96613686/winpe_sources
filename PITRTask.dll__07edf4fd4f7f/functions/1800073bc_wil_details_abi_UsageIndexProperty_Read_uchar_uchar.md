# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800073bc`
- end: `0x1800074c1`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `261`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005240`
- `0x180007c84`
- `0x180008020`

## callees

- `0x1800073bc`
- `0x1800107c0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000741a`
- `msvcrt!memcpy_s` at `0x18000744f`
- `msvcrt!memcpy_s` at `0x18000747a`
- `msvcrt!memcpy_s` at `0x18000741a`
- `msvcrt!memcpy_s` at `0x18000744f`
- `msvcrt!memcpy_s` at `0x18000747a`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char *v5; // r8
  char *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al
  unsigned __int16 v11; // [rsp+20h] [rbp-38h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    v11 = 0;
    memcpy_s(&v11, 2u, v5, 2u);
    *((_DWORD *)this + 1) = v11;
  }
  else
  {
    v7 = (char *)*a2;
    if ( *((_BYTE *)this + 2) == 2 )
    {
      v7 = v5 + 4;
      if ( v5 + 4 > (char *)a3 )
        return 0;
      *((_QWORD *)this + 2) = v5;
      memcpy_s((char *)this + 4, 4u, v5, 4u);
    }
  }
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_10;
  if ( v7 + 2 > (char *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v7, 2u);
  v7 += 2;
LABEL_10:
  v9 = (unsigned __int8 *)&v7[*((unsigned __int16 *)this + 4)];
  if ( v9 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x1800073bc  mov     r11, rsp
0x1800073bf  mov     [r11+18h], rbx
0x1800073c3  mov     [r11+20h], rbp
0x1800073c7  push    rsi
0x1800073c8  push    rdi
0x1800073c9  push    r12
0x1800073cb  push    r14
0x1800073cd  push    r15
0x1800073cf  sub     rsp, 30h
0x1800073d3  mov     rax, cs:__security_cookie
0x1800073da  xor     rax, rsp
0x1800073dd  mov     [rsp+58h+var_30], rax
0x1800073e2  xor     r15d, r15d
0x1800073e5  mov     rsi, r8
0x1800073e8  cmp     byte ptr [rcx+2], 1
0x1800073ec  mov     r12, rdx
0x1800073ef  mov     r8, [rdx]; Source
0x1800073f2  mov     rdi, rcx
0x1800073f5  jnz     short loc_18000742A
0x1800073f7  lea     rbx, [r8+2]
0x1800073fb  cmp     rbx, rsi
0x1800073fe  ja      loc_18000748F
0x180007404  lea     ebp, [r15+2]
0x180007408  mov     [rcx+10h], r8
0x18000740c  mov     r9d, ebp; SourceSize
0x18000740f  mov     [r11-38h], r15w
0x180007414  mov     edx, ebp; DestinationSize
0x180007416  lea     rcx, [r11-38h]; Destination
0x18000741a  call    cs:__imp_memcpy_s
0x180007420  movzx   eax, [rsp+58h+var_38]
0x180007425  mov     [rdi+4], eax
0x180007428  jmp     short loc_180007455
0x18000742a  mov     ebp, 2
0x18000742f  mov     rbx, r8
0x180007432  cmp     [rcx+2], bpl
0x180007436  jnz     short loc_180007455
0x180007438  lea     rbx, [r8+4]
0x18000743c  cmp     rbx, rsi
0x18000743f  ja      short loc_18000748F
0x180007441  lea     edx, [rbp+2]; DestinationSize
0x180007444  mov     [rcx+10h], r8
0x180007448  mov     r9d, edx; SourceSize
0x18000744b  add     rcx, 4; Destination
0x18000744f  call    cs:__imp_memcpy_s
0x180007455  movzx   eax, word ptr [rdi]
0x180007458  lea     r14, [rdi+8]
0x18000745c  mov     [r14], ax
0x180007460  test    ax, ax
0x180007463  jnz     short loc_180007483
0x180007465  lea     r15, [rbx+2]
0x180007469  cmp     r15, rsi
0x18000746c  ja      short loc_18000748F
0x18000746e  mov     r9, rbp; SourceSize
0x180007471  mov     r8, rbx; Source
0x180007474  mov     rdx, rbp; DestinationSize
0x180007477  mov     rcx, r14; Destination
0x18000747a  call    cs:__imp_memcpy_s
0x180007480  mov     rbx, r15
0x180007483  movzx   ecx, word ptr [r14]
0x180007487  add     rcx, rbx
0x18000748a  cmp     rcx, rsi
0x18000748d  jbe     short loc_180007493
0x18000748f  xor     al, al
0x180007491  jmp     short loc_18000749D
0x180007493  mov     [rdi+18h], rbx
0x180007497  mov     al, 1
0x180007499  mov     [r12], rcx
0x18000749d  mov     rcx, [rsp+58h+var_30]
0x1800074a2  xor     rcx, rsp; StackCookie
0x1800074a5  call    __security_check_cookie
0x1800074aa  mov     rbx, [rsp+58h+arg_10]
0x1800074af  mov     rbp, [rsp+58h+arg_18]
0x1800074b4  add     rsp, 30h
0x1800074b8  pop     r15
0x1800074ba  pop     r14
0x1800074bc  pop     r12
0x1800074be  pop     rdi
0x1800074bf  pop     rsi
0x1800074c0  retn
```
