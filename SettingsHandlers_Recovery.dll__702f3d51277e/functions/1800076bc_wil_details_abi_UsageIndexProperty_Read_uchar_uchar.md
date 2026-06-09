# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800076bc`
- end: `0x1800077b4`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005d20`
- `0x180007f48`
- `0x18000831c`

## callees

- `0x180002e3a`
- `0x1800076bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800076f9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000773b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000777a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800076f9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000773b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000777a`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  unsigned __int8 *v3; // rax
  wil::details_abi::UsageIndexProperty *v6; // rdi
  unsigned __int8 *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al

  v3 = *a2;
  v6 = this;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v3 + 2;
    if ( v3 + 2 > a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    if ( v3 )
    {
      this = (wil::details_abi::UsageIndexProperty *)*(unsigned __int16 *)v3;
    }
    else
    {
      *(_DWORD *)_o__errno(this, a2, a3) = 22;
      invalid_parameter_noinfo();
      this = 0;
    }
    *((_DWORD *)v6 + 1) = (unsigned __int16)this;
  }
  else if ( *((_BYTE *)this + 2) == 2 )
  {
    v7 = v3 + 4;
    if ( v3 + 4 > a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    this = (wil::details_abi::UsageIndexProperty *)((char *)this + 4);
    if ( this )
    {
      if ( v3 )
      {
        *(_DWORD *)this = *(_DWORD *)v3;
        goto LABEL_15;
      }
      *(_DWORD *)this = 0;
    }
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
  }
  else
  {
    v7 = *a2;
  }
LABEL_15:
  v8 = *(_WORD *)v6;
  *((_WORD *)v6 + 4) = *(_WORD *)v6;
  if ( v8 )
    goto LABEL_21;
  if ( v7 + 2 > a3 )
    return 0;
  if ( v7 )
  {
    *((_WORD *)v6 + 4) = *(_WORD *)v7;
  }
  else
  {
    *((_WORD *)v6 + 4) = 0;
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
  }
  v7 += 2;
LABEL_21:
  v9 = &v7[*((unsigned __int16 *)v6 + 4)];
  if ( v9 > a3 )
    return 0;
  *((_QWORD *)v6 + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x1800076bc  push    rbx
0x1800076be  push    rbp
0x1800076bf  push    rsi
0x1800076c0  push    rdi
0x1800076c1  push    r14
0x1800076c3  push    r15
0x1800076c5  sub     rsp, 28h
0x1800076c9  mov     rax, [rdx]
0x1800076cc  xor     r15d, r15d
0x1800076cf  cmp     byte ptr [rcx+2], 1
0x1800076d3  mov     rbp, r8
0x1800076d6  mov     r14, rdx
0x1800076d9  mov     rdi, rcx
0x1800076dc  jnz     short loc_180007715
0x1800076de  lea     rbx, [rax+2]
0x1800076e2  cmp     rbx, r8
0x1800076e5  ja      loc_18000779A
0x1800076eb  mov     [rcx+10h], rax
0x1800076ef  test    rax, rax
0x1800076f2  jz      short loc_1800076F9
0x1800076f4  movzx   ecx, word ptr [rax]
0x1800076f7  jmp     short loc_18000770D
0x1800076f9  call    cs:__imp__o__errno
0x1800076ff  mov     dword ptr [rax], 16h
0x180007705  call    _invalid_parameter_noinfo
0x18000770a  mov     ecx, r15d
0x18000770d  movzx   eax, cx
0x180007710  mov     [rdi+4], eax
0x180007713  jmp     short loc_180007751
0x180007715  cmp     byte ptr [rcx+2], 2
0x180007719  jnz     short loc_18000774E
0x18000771b  lea     rbx, [rax+4]
0x18000771f  cmp     rbx, rbp
0x180007722  ja      short loc_18000779A
0x180007724  mov     [rcx+10h], rax
0x180007728  add     rcx, 4
0x18000772c  jz      short loc_18000773B
0x18000772e  test    rax, rax
0x180007731  jz      short loc_180007739
0x180007733  mov     eax, [rax]
0x180007735  mov     [rcx], eax
0x180007737  jmp     short loc_180007751
0x180007739  mov     [rcx], eax
0x18000773b  call    cs:__imp__o__errno
0x180007741  mov     dword ptr [rax], 16h
0x180007747  call    _invalid_parameter_noinfo
0x18000774c  jmp     short loc_180007751
0x18000774e  mov     rbx, rax
0x180007751  movzx   eax, word ptr [rdi]
0x180007754  mov     [rdi+8], ax
0x180007758  test    ax, ax
0x18000775b  jnz     short loc_18000778E
0x18000775d  lea     rsi, [rbx+2]
0x180007761  cmp     rsi, rbp
0x180007764  ja      short loc_18000779A
0x180007766  test    rbx, rbx
0x180007769  jz      short loc_180007774
0x18000776b  movzx   eax, word ptr [rbx]
0x18000776e  mov     [rdi+8], ax
0x180007772  jmp     short loc_18000778B
0x180007774  xor     eax, eax
0x180007776  mov     [rdi+8], ax
0x18000777a  call    cs:__imp__o__errno
0x180007780  mov     dword ptr [rax], 16h
0x180007786  call    _invalid_parameter_noinfo
0x18000778b  mov     rbx, rsi
0x18000778e  movzx   ecx, word ptr [rdi+8]
0x180007792  add     rcx, rbx
0x180007795  cmp     rcx, rbp
0x180007798  jbe     short loc_18000779E
0x18000779a  xor     al, al
0x18000779c  jmp     short loc_1800077A7
0x18000779e  mov     [rdi+18h], rbx
0x1800077a2  mov     al, 1
0x1800077a4  mov     [r14], rcx
0x1800077a7  add     rsp, 28h
0x1800077ab  pop     r15
0x1800077ad  pop     r14
0x1800077af  pop     rdi
0x1800077b0  pop     rsi
0x1800077b1  pop     rbp
0x1800077b2  pop     rbx
0x1800077b3  retn
```
