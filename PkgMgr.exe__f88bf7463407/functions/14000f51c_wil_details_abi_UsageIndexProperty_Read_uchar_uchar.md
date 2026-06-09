# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000f51c`
- end: `0x14000f61e`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `258`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ed00`
- `0x14000ef54`
- `0x14000f0b0`
- `0x14000fa98`
- `0x140010084`

## callees

- `0x140002360`
- `0x14000f51c`
- `0x140011fb8`

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
    memcpy_s_0(&v11, 2u, v5, 2u);
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
      memcpy_s_0((char *)this + 4, 4u, v5, 4u);
    }
  }
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_10;
  if ( v7 + 2 > (char *)a3 )
    return 0;
  memcpy_s_0((char *)this + 8, 2u, v7, 2u);
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
0x14000f51c  mov     r11, rsp
0x14000f51f  mov     [r11+18h], rbx
0x14000f523  mov     [r11+20h], rbp
0x14000f527  push    rsi
0x14000f528  push    rdi
0x14000f529  push    r12
0x14000f52b  push    r14
0x14000f52d  push    r15
0x14000f52f  sub     rsp, 30h
0x14000f533  mov     rax, cs:__security_cookie
0x14000f53a  xor     rax, rsp
0x14000f53d  mov     [rsp+58h+var_30], rax
0x14000f542  xor     r15d, r15d
0x14000f545  mov     rsi, r8
0x14000f548  cmp     byte ptr [rcx+2], 1
0x14000f54c  mov     r12, rdx
0x14000f54f  mov     r8, [rdx]; Source
0x14000f552  mov     rdi, rcx
0x14000f555  jnz     short loc_14000F589
0x14000f557  lea     rbx, [r8+2]
0x14000f55b  cmp     rbx, rsi
0x14000f55e  ja      loc_14000F5EC
0x14000f564  lea     ebp, [r15+2]
0x14000f568  mov     [rcx+10h], r8
0x14000f56c  mov     r9d, ebp; SourceSize
0x14000f56f  mov     [r11-38h], r15w
0x14000f574  mov     edx, ebp; DestinationSize
0x14000f576  lea     rcx, [r11-38h]; Destination
0x14000f57a  call    memcpy_s_0
0x14000f57f  movzx   eax, [rsp+58h+var_38]
0x14000f584  mov     [rdi+4], eax
0x14000f587  jmp     short loc_14000F5B3
0x14000f589  mov     ebp, 2
0x14000f58e  mov     rbx, r8
0x14000f591  cmp     [rcx+2], bpl
0x14000f595  jnz     short loc_14000F5B3
0x14000f597  lea     rbx, [r8+4]
0x14000f59b  cmp     rbx, rsi
0x14000f59e  ja      short loc_14000F5EC
0x14000f5a0  lea     edx, [rbp+2]; DestinationSize
0x14000f5a3  mov     [rcx+10h], r8
0x14000f5a7  mov     r9d, edx; SourceSize
0x14000f5aa  add     rcx, 4; Destination
0x14000f5ae  call    memcpy_s_0
0x14000f5b3  movzx   eax, word ptr [rdi]
0x14000f5b6  lea     r14, [rdi+8]
0x14000f5ba  mov     [r14], ax
0x14000f5be  test    ax, ax
0x14000f5c1  jnz     short loc_14000F5E0
0x14000f5c3  lea     r15, [rbx+2]
0x14000f5c7  cmp     r15, rsi
0x14000f5ca  ja      short loc_14000F5EC
0x14000f5cc  mov     r9, rbp; SourceSize
0x14000f5cf  mov     r8, rbx; Source
0x14000f5d2  mov     rdx, rbp; DestinationSize
0x14000f5d5  mov     rcx, r14; Destination
0x14000f5d8  call    memcpy_s_0
0x14000f5dd  mov     rbx, r15
0x14000f5e0  movzx   ecx, word ptr [r14]
0x14000f5e4  add     rcx, rbx
0x14000f5e7  cmp     rcx, rsi
0x14000f5ea  jbe     short loc_14000F5F0
0x14000f5ec  xor     al, al
0x14000f5ee  jmp     short loc_14000F5FA
0x14000f5f0  mov     [rdi+18h], rbx
0x14000f5f4  mov     al, 1
0x14000f5f6  mov     [r12], rcx
0x14000f5fa  mov     rcx, [rsp+58h+var_30]
0x14000f5ff  xor     rcx, rsp; StackCookie
0x14000f602  call    __security_check_cookie
0x14000f607  mov     rbx, [rsp+58h+arg_10]
0x14000f60c  mov     rbp, [rsp+58h+arg_18]
0x14000f611  add     rsp, 30h
0x14000f615  pop     r15
0x14000f617  pop     r14
0x14000f619  pop     r12
0x14000f61b  pop     rdi
0x14000f61c  pop     rsi
0x14000f61d  retn
```
