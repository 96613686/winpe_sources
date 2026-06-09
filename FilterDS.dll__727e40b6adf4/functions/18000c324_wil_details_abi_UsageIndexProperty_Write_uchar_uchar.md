# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000c324`
- end: `0x18000c3fd`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000af54`

## callees

- `0x18000c324`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c384`
- `msvcrt!memcpy_s` at `0x18000c3af`
- `msvcrt!memcpy_s` at `0x18000c3dc`
- `msvcrt!memcpy_s` at `0x18000c384`
- `msvcrt!memcpy_s` at `0x18000c3af`
- `msvcrt!memcpy_s` at `0x18000c3dc`

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
0x18000c324  push    rbx
0x18000c326  push    rsi
0x18000c327  push    rdi
0x18000c328  push    r12
0x18000c32a  push    r14
0x18000c32c  push    r15
0x18000c32e  sub     rsp, 28h
0x18000c332  mov     rsi, rcx
0x18000c335  mov     rdi, r8
0x18000c338  mov     rcx, [rdx]; Destination
0x18000c33b  mov     r12, rdx
0x18000c33e  cmp     byte ptr [rsi+2], 1
0x18000c342  jnz     short loc_18000C366
0x18000c344  lea     rbx, [rcx+2]
0x18000c348  cmp     rbx, r8
0x18000c34b  ja      short loc_18000C3CB
0x18000c34d  movzx   eax, word ptr [rsi+4]
0x18000c351  lea     r8, [rsp+58h+arg_0]
0x18000c356  mov     r9d, 2
0x18000c35c  mov     [rsp+58h+arg_0], ax
0x18000c361  mov     edx, r9d
0x18000c364  jmp     short loc_18000C384
0x18000c366  cmp     byte ptr [rsi+2], 2
0x18000c36a  mov     rbx, rcx
0x18000c36d  jnz     short loc_18000C38A
0x18000c36f  lea     rbx, [rcx+4]
0x18000c373  cmp     rbx, rdi
0x18000c376  ja      short loc_18000C3CB
0x18000c378  mov     edx, 4; DestinationSize
0x18000c37d  lea     r8, [rsi+4]; Source
0x18000c381  mov     r9d, edx; SourceSize
0x18000c384  call    cs:__imp_memcpy_s
0x18000c38a  cmp     word ptr [rsi], 0
0x18000c38e  jnz     short loc_18000C3BA
0x18000c390  lea     r15, [rbx+2]
0x18000c394  cmp     r15, rdi
0x18000c397  ja      short loc_18000C3CB
0x18000c399  lea     r14, [rsi+8]
0x18000c39d  mov     rdx, rdi
0x18000c3a0  sub     rdx, rbx; DestinationSize
0x18000c3a3  mov     r8, r14; Source
0x18000c3a6  mov     r9d, 2; SourceSize
0x18000c3ac  mov     rcx, rbx; Destination
0x18000c3af  call    cs:__imp_memcpy_s
0x18000c3b5  mov     rbx, r15
0x18000c3b8  jmp     short loc_18000C3BE
0x18000c3ba  lea     r14, [rsi+8]
0x18000c3be  movzx   r9d, word ptr [r14]; SourceSize
0x18000c3c2  lea     rax, [r9+rbx]
0x18000c3c6  cmp     rax, rdi
0x18000c3c9  jbe     short loc_18000C3CF
0x18000c3cb  xor     al, al
0x18000c3cd  jmp     short loc_18000C3EF
0x18000c3cf  mov     r8, [rsi+18h]; Source
0x18000c3d3  sub     rdi, rbx
0x18000c3d6  mov     rdx, rdi; DestinationSize
0x18000c3d9  mov     rcx, rbx; Destination
0x18000c3dc  call    cs:__imp_memcpy_s
0x18000c3e2  movzx   ecx, word ptr [r14]
0x18000c3e6  mov     al, 1
0x18000c3e8  add     rcx, rbx
0x18000c3eb  mov     [r12], rcx
0x18000c3ef  add     rsp, 28h
0x18000c3f3  pop     r15
0x18000c3f5  pop     r14
0x18000c3f7  pop     r12
0x18000c3f9  pop     rdi
0x18000c3fa  pop     rsi
0x18000c3fb  pop     rbx
0x18000c3fc  retn
```
