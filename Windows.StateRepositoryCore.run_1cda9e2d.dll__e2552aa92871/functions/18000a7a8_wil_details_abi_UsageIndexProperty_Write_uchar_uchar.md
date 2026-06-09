# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000a7a8`
- end: `0x18000a87e`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008428`

## callees

- `0x18000a7a8`
- `0x18000b43c`

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
0x18000a7a8  push    rbx
0x18000a7aa  push    rsi
0x18000a7ab  push    rdi
0x18000a7ac  push    r12
0x18000a7ae  push    r14
0x18000a7b0  push    r15
0x18000a7b2  sub     rsp, 28h
0x18000a7b6  mov     rsi, rcx
0x18000a7b9  mov     rdi, r8
0x18000a7bc  mov     rcx, [rdx]; Destination
0x18000a7bf  mov     r12, rdx
0x18000a7c2  cmp     byte ptr [rsi+2], 1
0x18000a7c6  jnz     short loc_18000A7EA
0x18000a7c8  lea     rbx, [rcx+2]
0x18000a7cc  cmp     rbx, r8
0x18000a7cf  ja      short loc_18000A84D
0x18000a7d1  movzx   eax, word ptr [rsi+4]
0x18000a7d5  lea     r8, [rsp+58h+arg_0]
0x18000a7da  mov     r9d, 2
0x18000a7e0  mov     [rsp+58h+arg_0], ax
0x18000a7e5  mov     edx, r9d
0x18000a7e8  jmp     short loc_18000A808
0x18000a7ea  cmp     byte ptr [rsi+2], 2
0x18000a7ee  mov     rbx, rcx
0x18000a7f1  jnz     short loc_18000A80D
0x18000a7f3  lea     rbx, [rcx+4]
0x18000a7f7  cmp     rbx, rdi
0x18000a7fa  ja      short loc_18000A84D
0x18000a7fc  mov     edx, 4; DestinationSize
0x18000a801  lea     r8, [rsi+4]; Source
0x18000a805  mov     r9d, edx; SourceSize
0x18000a808  call    memcpy_s
0x18000a80d  cmp     word ptr [rsi], 0
0x18000a811  jnz     short loc_18000A83C
0x18000a813  lea     r15, [rbx+2]
0x18000a817  cmp     r15, rdi
0x18000a81a  ja      short loc_18000A84D
0x18000a81c  lea     r14, [rsi+8]
0x18000a820  mov     rdx, rdi
0x18000a823  sub     rdx, rbx; DestinationSize
0x18000a826  mov     r8, r14; Source
0x18000a829  mov     r9d, 2; SourceSize
0x18000a82f  mov     rcx, rbx; Destination
0x18000a832  call    memcpy_s
0x18000a837  mov     rbx, r15
0x18000a83a  jmp     short loc_18000A840
0x18000a83c  lea     r14, [rsi+8]
0x18000a840  movzx   r9d, word ptr [r14]; SourceSize
0x18000a844  lea     rax, [r9+rbx]
0x18000a848  cmp     rax, rdi
0x18000a84b  jbe     short loc_18000A851
0x18000a84d  xor     al, al
0x18000a84f  jmp     short loc_18000A870
0x18000a851  mov     r8, [rsi+18h]; Source
0x18000a855  sub     rdi, rbx
0x18000a858  mov     rdx, rdi; DestinationSize
0x18000a85b  mov     rcx, rbx; Destination
0x18000a85e  call    memcpy_s
0x18000a863  movzx   ecx, word ptr [r14]
0x18000a867  mov     al, 1
0x18000a869  add     rcx, rbx
0x18000a86c  mov     [r12], rcx
0x18000a870  add     rsp, 28h
0x18000a874  pop     r15
0x18000a876  pop     r14
0x18000a878  pop     r12
0x18000a87a  pop     rdi
0x18000a87b  pop     rsi
0x18000a87c  pop     rbx
0x18000a87d  retn
```
