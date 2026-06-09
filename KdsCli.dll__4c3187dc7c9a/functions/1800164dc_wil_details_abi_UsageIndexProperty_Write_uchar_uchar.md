# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800164dc`
- end: `0x1800165b2`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014c04`

## callees

- `0x180001f4c`
- `0x1800164dc`

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
0x1800164dc  push    rbx
0x1800164de  push    rsi
0x1800164df  push    rdi
0x1800164e0  push    r12
0x1800164e2  push    r14
0x1800164e4  push    r15
0x1800164e6  sub     rsp, 28h
0x1800164ea  mov     rsi, rcx
0x1800164ed  mov     rdi, r8
0x1800164f0  mov     rcx, [rdx]; Destination
0x1800164f3  mov     r12, rdx
0x1800164f6  cmp     byte ptr [rsi+2], 1
0x1800164fa  jnz     short loc_18001651E
0x1800164fc  lea     rbx, [rcx+2]
0x180016500  cmp     rbx, r8
0x180016503  ja      short loc_180016581
0x180016505  movzx   eax, word ptr [rsi+4]
0x180016509  lea     r8, [rsp+58h+arg_0]
0x18001650e  mov     r9d, 2
0x180016514  mov     [rsp+58h+arg_0], ax
0x180016519  mov     edx, r9d
0x18001651c  jmp     short loc_18001653C
0x18001651e  cmp     byte ptr [rsi+2], 2
0x180016522  mov     rbx, rcx
0x180016525  jnz     short loc_180016541
0x180016527  lea     rbx, [rcx+4]
0x18001652b  cmp     rbx, rdi
0x18001652e  ja      short loc_180016581
0x180016530  mov     edx, 4; DestinationSize
0x180016535  lea     r8, [rsi+4]; Source
0x180016539  mov     r9d, edx; SourceSize
0x18001653c  call    memcpy_s
0x180016541  cmp     word ptr [rsi], 0
0x180016545  jnz     short loc_180016570
0x180016547  lea     r15, [rbx+2]
0x18001654b  cmp     r15, rdi
0x18001654e  ja      short loc_180016581
0x180016550  lea     r14, [rsi+8]
0x180016554  mov     rdx, rdi
0x180016557  sub     rdx, rbx; DestinationSize
0x18001655a  mov     r8, r14; Source
0x18001655d  mov     r9d, 2; SourceSize
0x180016563  mov     rcx, rbx; Destination
0x180016566  call    memcpy_s
0x18001656b  mov     rbx, r15
0x18001656e  jmp     short loc_180016574
0x180016570  lea     r14, [rsi+8]
0x180016574  movzx   r9d, word ptr [r14]; SourceSize
0x180016578  lea     rax, [r9+rbx]
0x18001657c  cmp     rax, rdi
0x18001657f  jbe     short loc_180016585
0x180016581  xor     al, al
0x180016583  jmp     short loc_1800165A4
0x180016585  mov     r8, [rsi+18h]; Source
0x180016589  sub     rdi, rbx
0x18001658c  mov     rdx, rdi; DestinationSize
0x18001658f  mov     rcx, rbx; Destination
0x180016592  call    memcpy_s
0x180016597  movzx   ecx, word ptr [r14]
0x18001659b  mov     al, 1
0x18001659d  add     rcx, rbx
0x1800165a0  mov     [r12], rcx
0x1800165a4  add     rsp, 28h
0x1800165a8  pop     r15
0x1800165aa  pop     r14
0x1800165ac  pop     r12
0x1800165ae  pop     rdi
0x1800165af  pop     rsi
0x1800165b0  pop     rbx
0x1800165b1  retn
```
