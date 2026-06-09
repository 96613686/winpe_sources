# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x140011054`
- end: `0x14001112a`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000cca8`

## callees

- `0x140007ea4`
- `0x140011054`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        char **a2,
        char *a3)
{
  char *v5; // rcx
  char *v7; // rbx
  char *v8; // r8
  rsize_t v9; // r9
  rsize_t v10; // rdx
  unsigned __int16 *v11; // r14
  rsize_t v12; // r9
  bool result; // al
  __int16 v14; // [rsp+60h] [rbp+8h] BYREF

  v5 = *a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > a3 )
      return 0;
    v8 = (char *)&v14;
    v9 = 2;
    v14 = *((_WORD *)this + 2);
    v10 = 2;
  }
  else
  {
    v7 = *a2;
    if ( *((_BYTE *)this + 2) != 2 )
      goto LABEL_8;
    v7 = v5 + 4;
    if ( v5 + 4 > a3 )
      return 0;
    v10 = 4;
    v8 = (char *)this + 4;
    v9 = 4;
  }
  memcpy_s(v5, v10, v8, v9);
LABEL_8:
  if ( !*(_WORD *)this )
  {
    if ( v7 + 2 <= a3 )
    {
      v11 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v7, a3 - v7, (char *)this + 8, 2u);
      v7 += 2;
      goto LABEL_12;
    }
    return 0;
  }
  v11 = (unsigned __int16 *)((char *)this + 8);
LABEL_12:
  v12 = *v11;
  if ( &v7[v12] > a3 )
    return 0;
  memcpy_s(v7, a3 - v7, *((const void *const *)this + 3), v12);
  result = 1;
  *a2 = &v7[*v11];
  return result;
}

```

## disassembly

```asm
0x140011054  push    rbx
0x140011056  push    rsi
0x140011057  push    rdi
0x140011058  push    r12
0x14001105a  push    r14
0x14001105c  push    r15
0x14001105e  sub     rsp, 28h
0x140011062  mov     rsi, rcx
0x140011065  mov     rdi, r8
0x140011068  mov     rcx, [rdx]; Destination
0x14001106b  mov     r12, rdx
0x14001106e  cmp     byte ptr [rsi+2], 1
0x140011072  jnz     short loc_140011096
0x140011074  lea     rbx, [rcx+2]
0x140011078  cmp     rbx, r8
0x14001107b  ja      short loc_1400110F9
0x14001107d  movzx   eax, word ptr [rsi+4]
0x140011081  lea     r8, [rsp+58h+arg_0]
0x140011086  mov     r9d, 2
0x14001108c  mov     [rsp+58h+arg_0], ax
0x140011091  mov     edx, r9d
0x140011094  jmp     short loc_1400110B4
0x140011096  cmp     byte ptr [rsi+2], 2
0x14001109a  mov     rbx, rcx
0x14001109d  jnz     short loc_1400110B9
0x14001109f  lea     rbx, [rcx+4]
0x1400110a3  cmp     rbx, rdi
0x1400110a6  ja      short loc_1400110F9
0x1400110a8  mov     edx, 4; DestinationSize
0x1400110ad  lea     r8, [rsi+4]; Source
0x1400110b1  mov     r9d, edx; SourceSize
0x1400110b4  call    memcpy_s
0x1400110b9  cmp     word ptr [rsi], 0
0x1400110bd  jnz     short loc_1400110E8
0x1400110bf  lea     r15, [rbx+2]
0x1400110c3  cmp     r15, rdi
0x1400110c6  ja      short loc_1400110F9
0x1400110c8  lea     r14, [rsi+8]
0x1400110cc  mov     rdx, rdi
0x1400110cf  sub     rdx, rbx; DestinationSize
0x1400110d2  mov     r8, r14; Source
0x1400110d5  mov     r9d, 2; SourceSize
0x1400110db  mov     rcx, rbx; Destination
0x1400110de  call    memcpy_s
0x1400110e3  mov     rbx, r15
0x1400110e6  jmp     short loc_1400110EC
0x1400110e8  lea     r14, [rsi+8]
0x1400110ec  movzx   r9d, word ptr [r14]; SourceSize
0x1400110f0  lea     rax, [r9+rbx]
0x1400110f4  cmp     rax, rdi
0x1400110f7  jbe     short loc_1400110FD
0x1400110f9  xor     al, al
0x1400110fb  jmp     short loc_14001111C
0x1400110fd  mov     r8, [rsi+18h]; Source
0x140011101  sub     rdi, rbx
0x140011104  mov     rdx, rdi; DestinationSize
0x140011107  mov     rcx, rbx; Destination
0x14001110a  call    memcpy_s
0x14001110f  movzx   ecx, word ptr [r14]
0x140011113  mov     al, 1
0x140011115  add     rcx, rbx
0x140011118  mov     [r12], rcx
0x14001111c  add     rsp, 28h
0x140011120  pop     r15
0x140011122  pop     r14
0x140011124  pop     r12
0x140011126  pop     rdi
0x140011127  pop     rsi
0x140011128  pop     rbx
0x140011129  retn
```
