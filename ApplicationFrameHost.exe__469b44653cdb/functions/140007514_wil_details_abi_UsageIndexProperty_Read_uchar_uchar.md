# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140007514`
- end: `0x1400075fa`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140005d20`
- `0x1400068ac`
- `0x140006d48`
- `0x140007a7c`
- `0x14000893c`

## callees

- `0x140007514`
- `0x140009d98`

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
  unsigned __int16 v11; // [rsp+50h] [rbp+8h] BYREF

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
0x140007514  mov     rax, rsp
0x140007517  mov     [rax+10h], rbx
0x14000751b  mov     [rax+18h], rbp
0x14000751f  push    rsi
0x140007520  push    rdi
0x140007521  push    r12
0x140007523  push    r14
0x140007525  push    r15
0x140007527  sub     rsp, 20h
0x14000752b  xor     r15d, r15d
0x14000752e  mov     rsi, r8
0x140007531  cmp     byte ptr [rcx+2], 1
0x140007535  mov     r12, rdx
0x140007538  mov     r8, [rdx]; Source
0x14000753b  mov     rdi, rcx
0x14000753e  jnz     short loc_140007572
0x140007540  lea     rbx, [r8+2]
0x140007544  cmp     rbx, rsi
0x140007547  ja      loc_1400075D5
0x14000754d  lea     ebp, [r15+2]
0x140007551  mov     [rcx+10h], r8
0x140007555  mov     r9d, ebp; SourceSize
0x140007558  mov     [rax+8], r15w
0x14000755d  mov     edx, ebp; DestinationSize
0x14000755f  lea     rcx, [rax+8]; Destination
0x140007563  call    memcpy_s
0x140007568  movzx   eax, [rsp+48h+arg_0]
0x14000756d  mov     [rdi+4], eax
0x140007570  jmp     short loc_14000759C
0x140007572  mov     ebp, 2
0x140007577  mov     rbx, r8
0x14000757a  cmp     [rcx+2], bpl
0x14000757e  jnz     short loc_14000759C
0x140007580  lea     rbx, [r8+4]
0x140007584  cmp     rbx, rsi
0x140007587  ja      short loc_1400075D5
0x140007589  lea     edx, [rbp+2]; DestinationSize
0x14000758c  mov     [rcx+10h], r8
0x140007590  mov     r9d, edx; SourceSize
0x140007593  add     rcx, 4; Destination
0x140007597  call    memcpy_s
0x14000759c  movzx   eax, word ptr [rdi]
0x14000759f  lea     r14, [rdi+8]
0x1400075a3  mov     [r14], ax
0x1400075a7  test    ax, ax
0x1400075aa  jnz     short loc_1400075C9
0x1400075ac  lea     r15, [rbx+2]
0x1400075b0  cmp     r15, rsi
0x1400075b3  ja      short loc_1400075D5
0x1400075b5  mov     r9, rbp; SourceSize
0x1400075b8  mov     r8, rbx; Source
0x1400075bb  mov     rdx, rbp; DestinationSize
0x1400075be  mov     rcx, r14; Destination
0x1400075c1  call    memcpy_s
0x1400075c6  mov     rbx, r15
0x1400075c9  movzx   ecx, word ptr [r14]
0x1400075cd  add     rcx, rbx
0x1400075d0  cmp     rcx, rsi
0x1400075d3  jbe     short loc_1400075D9
0x1400075d5  xor     al, al
0x1400075d7  jmp     short loc_1400075E3
0x1400075d9  mov     [rdi+18h], rbx
0x1400075dd  mov     al, 1
0x1400075df  mov     [r12], rcx
0x1400075e3  mov     rbx, [rsp+48h+arg_8]
0x1400075e8  mov     rbp, [rsp+48h+arg_10]
0x1400075ed  add     rsp, 20h
0x1400075f1  pop     r15
0x1400075f3  pop     r14
0x1400075f5  pop     r12
0x1400075f7  pop     rdi
0x1400075f8  pop     rsi
0x1400075f9  retn
```
