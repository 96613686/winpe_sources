# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x140006e7c`
- end: `0x140006f52`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001e60`

## callees

- `0x140001cdc`
- `0x140006e7c`

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
0x140006e7c  push    rbx
0x140006e7e  push    rsi
0x140006e7f  push    rdi
0x140006e80  push    r12
0x140006e82  push    r14
0x140006e84  push    r15
0x140006e86  sub     rsp, 28h
0x140006e8a  mov     rsi, rcx
0x140006e8d  mov     rdi, r8
0x140006e90  mov     rcx, [rdx]; Destination
0x140006e93  mov     r12, rdx
0x140006e96  cmp     byte ptr [rsi+2], 1
0x140006e9a  jnz     short loc_140006EBE
0x140006e9c  lea     rbx, [rcx+2]
0x140006ea0  cmp     rbx, r8
0x140006ea3  ja      short loc_140006F21
0x140006ea5  movzx   eax, word ptr [rsi+4]
0x140006ea9  lea     r8, [rsp+58h+arg_0]
0x140006eae  mov     r9d, 2
0x140006eb4  mov     [rsp+58h+arg_0], ax
0x140006eb9  mov     edx, r9d
0x140006ebc  jmp     short loc_140006EDC
0x140006ebe  cmp     byte ptr [rsi+2], 2
0x140006ec2  mov     rbx, rcx
0x140006ec5  jnz     short loc_140006EE1
0x140006ec7  lea     rbx, [rcx+4]
0x140006ecb  cmp     rbx, rdi
0x140006ece  ja      short loc_140006F21
0x140006ed0  mov     edx, 4; DestinationSize
0x140006ed5  lea     r8, [rsi+4]; Source
0x140006ed9  mov     r9d, edx; SourceSize
0x140006edc  call    memcpy_s
0x140006ee1  cmp     word ptr [rsi], 0
0x140006ee5  jnz     short loc_140006F10
0x140006ee7  lea     r15, [rbx+2]
0x140006eeb  cmp     r15, rdi
0x140006eee  ja      short loc_140006F21
0x140006ef0  lea     r14, [rsi+8]
0x140006ef4  mov     rdx, rdi
0x140006ef7  sub     rdx, rbx; DestinationSize
0x140006efa  mov     r8, r14; Source
0x140006efd  mov     r9d, 2; SourceSize
0x140006f03  mov     rcx, rbx; Destination
0x140006f06  call    memcpy_s
0x140006f0b  mov     rbx, r15
0x140006f0e  jmp     short loc_140006F14
0x140006f10  lea     r14, [rsi+8]
0x140006f14  movzx   r9d, word ptr [r14]; SourceSize
0x140006f18  lea     rax, [r9+rbx]
0x140006f1c  cmp     rax, rdi
0x140006f1f  jbe     short loc_140006F25
0x140006f21  xor     al, al
0x140006f23  jmp     short loc_140006F44
0x140006f25  mov     r8, [rsi+18h]; Source
0x140006f29  sub     rdi, rbx
0x140006f2c  mov     rdx, rdi; DestinationSize
0x140006f2f  mov     rcx, rbx; Destination
0x140006f32  call    memcpy_s
0x140006f37  movzx   ecx, word ptr [r14]
0x140006f3b  mov     al, 1
0x140006f3d  add     rcx, rbx
0x140006f40  mov     [r12], rcx
0x140006f44  add     rsp, 28h
0x140006f48  pop     r15
0x140006f4a  pop     r14
0x140006f4c  pop     r12
0x140006f4e  pop     rdi
0x140006f4f  pop     rsi
0x140006f50  pop     rbx
0x140006f51  retn
```
