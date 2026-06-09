# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180009408`
- end: `0x1800094ee`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800089b0`
- `0x180008dfc`
- `0x180008f6c`
- `0x180009938`
- `0x18000a28c`

## callees

- `0x1800076d8`
- `0x180009408`

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
0x180009408  mov     rax, rsp
0x18000940b  mov     [rax+10h], rbx
0x18000940f  mov     [rax+18h], rbp
0x180009413  push    rsi
0x180009414  push    rdi
0x180009415  push    r12
0x180009417  push    r14
0x180009419  push    r15
0x18000941b  sub     rsp, 20h
0x18000941f  xor     r15d, r15d
0x180009422  mov     rsi, r8
0x180009425  cmp     byte ptr [rcx+2], 1
0x180009429  mov     r12, rdx
0x18000942c  mov     r8, [rdx]; Source
0x18000942f  mov     rdi, rcx
0x180009432  jnz     short loc_180009466
0x180009434  lea     rbx, [r8+2]
0x180009438  cmp     rbx, rsi
0x18000943b  ja      loc_1800094C9
0x180009441  lea     ebp, [r15+2]
0x180009445  mov     [rcx+10h], r8
0x180009449  mov     r9d, ebp; SourceSize
0x18000944c  mov     [rax+8], r15w
0x180009451  mov     edx, ebp; DestinationSize
0x180009453  lea     rcx, [rax+8]; Destination
0x180009457  call    memcpy_s
0x18000945c  movzx   eax, [rsp+48h+arg_0]
0x180009461  mov     [rdi+4], eax
0x180009464  jmp     short loc_180009490
0x180009466  mov     ebp, 2
0x18000946b  mov     rbx, r8
0x18000946e  cmp     [rcx+2], bpl
0x180009472  jnz     short loc_180009490
0x180009474  lea     rbx, [r8+4]
0x180009478  cmp     rbx, rsi
0x18000947b  ja      short loc_1800094C9
0x18000947d  lea     edx, [rbp+2]; DestinationSize
0x180009480  mov     [rcx+10h], r8
0x180009484  mov     r9d, edx; SourceSize
0x180009487  add     rcx, 4; Destination
0x18000948b  call    memcpy_s
0x180009490  movzx   eax, word ptr [rdi]
0x180009493  lea     r14, [rdi+8]
0x180009497  mov     [r14], ax
0x18000949b  test    ax, ax
0x18000949e  jnz     short loc_1800094BD
0x1800094a0  lea     r15, [rbx+2]
0x1800094a4  cmp     r15, rsi
0x1800094a7  ja      short loc_1800094C9
0x1800094a9  mov     r9, rbp; SourceSize
0x1800094ac  mov     r8, rbx; Source
0x1800094af  mov     rdx, rbp; DestinationSize
0x1800094b2  mov     rcx, r14; Destination
0x1800094b5  call    memcpy_s
0x1800094ba  mov     rbx, r15
0x1800094bd  movzx   ecx, word ptr [r14]
0x1800094c1  add     rcx, rbx
0x1800094c4  cmp     rcx, rsi
0x1800094c7  jbe     short loc_1800094CD
0x1800094c9  xor     al, al
0x1800094cb  jmp     short loc_1800094D7
0x1800094cd  mov     [rdi+18h], rbx
0x1800094d1  mov     al, 1
0x1800094d3  mov     [r12], rcx
0x1800094d7  mov     rbx, [rsp+48h+arg_8]
0x1800094dc  mov     rbp, [rsp+48h+arg_10]
0x1800094e1  add     rsp, 20h
0x1800094e5  pop     r15
0x1800094e7  pop     r14
0x1800094e9  pop     r12
0x1800094eb  pop     rdi
0x1800094ec  pop     rsi
0x1800094ed  retn
```
