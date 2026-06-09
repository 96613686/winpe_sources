# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800065d0`
- end: `0x1800066b6`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800049bc`
- `0x1800057d0`
- `0x180005c8c`
- `0x180006b74`
- `0x180007acc`

## callees

- `0x1800065d0`
- `0x18000934c`

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
0x1800065d0  mov     rax, rsp
0x1800065d3  mov     [rax+10h], rbx
0x1800065d7  mov     [rax+18h], rbp
0x1800065db  push    rsi
0x1800065dc  push    rdi
0x1800065dd  push    r12
0x1800065df  push    r14
0x1800065e1  push    r15
0x1800065e3  sub     rsp, 20h
0x1800065e7  xor     r15d, r15d
0x1800065ea  mov     rsi, r8
0x1800065ed  cmp     byte ptr [rcx+2], 1
0x1800065f1  mov     r12, rdx
0x1800065f4  mov     r8, [rdx]; Source
0x1800065f7  mov     rdi, rcx
0x1800065fa  jnz     short loc_18000662E
0x1800065fc  lea     rbx, [r8+2]
0x180006600  cmp     rbx, rsi
0x180006603  ja      loc_180006691
0x180006609  lea     ebp, [r15+2]
0x18000660d  mov     [rcx+10h], r8
0x180006611  mov     r9d, ebp; SourceSize
0x180006614  mov     [rax+8], r15w
0x180006619  mov     edx, ebp; DestinationSize
0x18000661b  lea     rcx, [rax+8]; Destination
0x18000661f  call    memcpy_s
0x180006624  movzx   eax, [rsp+48h+arg_0]
0x180006629  mov     [rdi+4], eax
0x18000662c  jmp     short loc_180006658
0x18000662e  mov     ebp, 2
0x180006633  mov     rbx, r8
0x180006636  cmp     [rcx+2], bpl
0x18000663a  jnz     short loc_180006658
0x18000663c  lea     rbx, [r8+4]
0x180006640  cmp     rbx, rsi
0x180006643  ja      short loc_180006691
0x180006645  lea     edx, [rbp+2]; DestinationSize
0x180006648  mov     [rcx+10h], r8
0x18000664c  mov     r9d, edx; SourceSize
0x18000664f  add     rcx, 4; Destination
0x180006653  call    memcpy_s
0x180006658  movzx   eax, word ptr [rdi]
0x18000665b  lea     r14, [rdi+8]
0x18000665f  mov     [r14], ax
0x180006663  test    ax, ax
0x180006666  jnz     short loc_180006685
0x180006668  lea     r15, [rbx+2]
0x18000666c  cmp     r15, rsi
0x18000666f  ja      short loc_180006691
0x180006671  mov     r9, rbp; SourceSize
0x180006674  mov     r8, rbx; Source
0x180006677  mov     rdx, rbp; DestinationSize
0x18000667a  mov     rcx, r14; Destination
0x18000667d  call    memcpy_s
0x180006682  mov     rbx, r15
0x180006685  movzx   ecx, word ptr [r14]
0x180006689  add     rcx, rbx
0x18000668c  cmp     rcx, rsi
0x18000668f  jbe     short loc_180006695
0x180006691  xor     al, al
0x180006693  jmp     short loc_18000669F
0x180006695  mov     [rdi+18h], rbx
0x180006699  mov     al, 1
0x18000669b  mov     [r12], rcx
0x18000669f  mov     rbx, [rsp+48h+arg_8]
0x1800066a4  mov     rbp, [rsp+48h+arg_10]
0x1800066a9  add     rsp, 20h
0x1800066ad  pop     r15
0x1800066af  pop     r14
0x1800066b1  pop     r12
0x1800066b3  pop     rdi
0x1800066b4  pop     rsi
0x1800066b5  retn
```
