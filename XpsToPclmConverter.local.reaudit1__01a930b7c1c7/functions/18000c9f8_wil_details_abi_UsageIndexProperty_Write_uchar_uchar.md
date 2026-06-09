# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000c9f8`
- end: `0x18000cace`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b1a4`

## callees

- `0x18000c9f8`
- `0x18000d374`

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
0x18000c9f8  push    rbx
0x18000c9fa  push    rsi
0x18000c9fb  push    rdi
0x18000c9fc  push    r12
0x18000c9fe  push    r14
0x18000ca00  push    r15
0x18000ca02  sub     rsp, 28h
0x18000ca06  mov     rsi, rcx
0x18000ca09  mov     rdi, r8
0x18000ca0c  mov     rcx, [rdx]; Destination
0x18000ca0f  mov     r12, rdx
0x18000ca12  cmp     byte ptr [rsi+2], 1
0x18000ca16  jnz     short loc_18000CA3A
0x18000ca18  lea     rbx, [rcx+2]
0x18000ca1c  cmp     rbx, r8
0x18000ca1f  ja      short loc_18000CA9D
0x18000ca21  movzx   eax, word ptr [rsi+4]
0x18000ca25  lea     r8, [rsp+58h+arg_0]
0x18000ca2a  mov     r9d, 2
0x18000ca30  mov     [rsp+58h+arg_0], ax
0x18000ca35  mov     edx, r9d
0x18000ca38  jmp     short loc_18000CA58
0x18000ca3a  cmp     byte ptr [rsi+2], 2
0x18000ca3e  mov     rbx, rcx
0x18000ca41  jnz     short loc_18000CA5D
0x18000ca43  lea     rbx, [rcx+4]
0x18000ca47  cmp     rbx, rdi
0x18000ca4a  ja      short loc_18000CA9D
0x18000ca4c  mov     edx, 4; DestinationSize
0x18000ca51  lea     r8, [rsi+4]; Source
0x18000ca55  mov     r9d, edx; SourceSize
0x18000ca58  call    memcpy_s
0x18000ca5d  cmp     word ptr [rsi], 0
0x18000ca61  jnz     short loc_18000CA8C
0x18000ca63  lea     r15, [rbx+2]
0x18000ca67  cmp     r15, rdi
0x18000ca6a  ja      short loc_18000CA9D
0x18000ca6c  lea     r14, [rsi+8]
0x18000ca70  mov     rdx, rdi
0x18000ca73  sub     rdx, rbx; DestinationSize
0x18000ca76  mov     r8, r14; Source
0x18000ca79  mov     r9d, 2; SourceSize
0x18000ca7f  mov     rcx, rbx; Destination
0x18000ca82  call    memcpy_s
0x18000ca87  mov     rbx, r15
0x18000ca8a  jmp     short loc_18000CA90
0x18000ca8c  lea     r14, [rsi+8]
0x18000ca90  movzx   r9d, word ptr [r14]; SourceSize
0x18000ca94  lea     rax, [r9+rbx]
0x18000ca98  cmp     rax, rdi
0x18000ca9b  jbe     short loc_18000CAA1
0x18000ca9d  xor     al, al
0x18000ca9f  jmp     short loc_18000CAC0
0x18000caa1  mov     r8, [rsi+18h]; Source
0x18000caa5  sub     rdi, rbx
0x18000caa8  mov     rdx, rdi; DestinationSize
0x18000caab  mov     rcx, rbx; Destination
0x18000caae  call    memcpy_s
0x18000cab3  movzx   ecx, word ptr [r14]
0x18000cab7  mov     al, 1
0x18000cab9  add     rcx, rbx
0x18000cabc  mov     [r12], rcx
0x18000cac0  add     rsp, 28h
0x18000cac4  pop     r15
0x18000cac6  pop     r14
0x18000cac8  pop     r12
0x18000caca  pop     rdi
0x18000cacb  pop     rsi
0x18000cacc  pop     rbx
0x18000cacd  retn
```
