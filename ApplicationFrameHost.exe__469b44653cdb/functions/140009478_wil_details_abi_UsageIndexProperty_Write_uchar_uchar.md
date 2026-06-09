# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x140009478`
- end: `0x14000954e`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007a7c`

## callees

- `0x140009478`
- `0x140009d98`

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
0x140009478  push    rbx
0x14000947a  push    rsi
0x14000947b  push    rdi
0x14000947c  push    r12
0x14000947e  push    r14
0x140009480  push    r15
0x140009482  sub     rsp, 28h
0x140009486  mov     rsi, rcx
0x140009489  mov     rdi, r8
0x14000948c  mov     rcx, [rdx]; Destination
0x14000948f  mov     r12, rdx
0x140009492  cmp     byte ptr [rsi+2], 1
0x140009496  jnz     short loc_1400094BA
0x140009498  lea     rbx, [rcx+2]
0x14000949c  cmp     rbx, r8
0x14000949f  ja      short loc_14000951D
0x1400094a1  movzx   eax, word ptr [rsi+4]
0x1400094a5  lea     r8, [rsp+58h+arg_0]
0x1400094aa  mov     r9d, 2
0x1400094b0  mov     [rsp+58h+arg_0], ax
0x1400094b5  mov     edx, r9d
0x1400094b8  jmp     short loc_1400094D8
0x1400094ba  cmp     byte ptr [rsi+2], 2
0x1400094be  mov     rbx, rcx
0x1400094c1  jnz     short loc_1400094DD
0x1400094c3  lea     rbx, [rcx+4]
0x1400094c7  cmp     rbx, rdi
0x1400094ca  ja      short loc_14000951D
0x1400094cc  mov     edx, 4; DestinationSize
0x1400094d1  lea     r8, [rsi+4]; Source
0x1400094d5  mov     r9d, edx; SourceSize
0x1400094d8  call    memcpy_s
0x1400094dd  cmp     word ptr [rsi], 0
0x1400094e1  jnz     short loc_14000950C
0x1400094e3  lea     r15, [rbx+2]
0x1400094e7  cmp     r15, rdi
0x1400094ea  ja      short loc_14000951D
0x1400094ec  lea     r14, [rsi+8]
0x1400094f0  mov     rdx, rdi
0x1400094f3  sub     rdx, rbx; DestinationSize
0x1400094f6  mov     r8, r14; Source
0x1400094f9  mov     r9d, 2; SourceSize
0x1400094ff  mov     rcx, rbx; Destination
0x140009502  call    memcpy_s
0x140009507  mov     rbx, r15
0x14000950a  jmp     short loc_140009510
0x14000950c  lea     r14, [rsi+8]
0x140009510  movzx   r9d, word ptr [r14]; SourceSize
0x140009514  lea     rax, [r9+rbx]
0x140009518  cmp     rax, rdi
0x14000951b  jbe     short loc_140009521
0x14000951d  xor     al, al
0x14000951f  jmp     short loc_140009540
0x140009521  mov     r8, [rsi+18h]; Source
0x140009525  sub     rdi, rbx
0x140009528  mov     rdx, rdi; DestinationSize
0x14000952b  mov     rcx, rbx; Destination
0x14000952e  call    memcpy_s
0x140009533  movzx   ecx, word ptr [r14]
0x140009537  mov     al, 1
0x140009539  add     rcx, rbx
0x14000953c  mov     [r12], rcx
0x140009540  add     rsp, 28h
0x140009544  pop     r15
0x140009546  pop     r14
0x140009548  pop     r12
0x14000954a  pop     rdi
0x14000954b  pop     rsi
0x14000954c  pop     rbx
0x14000954d  retn
```
