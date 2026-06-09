# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000d38c`
- end: `0x14000d465`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b688`

## callees

- `0x14000d38c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000d3ec`
- `msvcrt!memcpy_s` at `0x14000d417`
- `msvcrt!memcpy_s` at `0x14000d444`
- `msvcrt!memcpy_s` at `0x14000d3ec`
- `msvcrt!memcpy_s` at `0x14000d417`
- `msvcrt!memcpy_s` at `0x14000d444`

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
0x14000d38c  push    rbx
0x14000d38e  push    rsi
0x14000d38f  push    rdi
0x14000d390  push    r12
0x14000d392  push    r14
0x14000d394  push    r15
0x14000d396  sub     rsp, 28h
0x14000d39a  mov     rsi, rcx
0x14000d39d  mov     rdi, r8
0x14000d3a0  mov     rcx, [rdx]; Destination
0x14000d3a3  mov     r12, rdx
0x14000d3a6  cmp     byte ptr [rsi+2], 1
0x14000d3aa  jnz     short loc_14000D3CE
0x14000d3ac  lea     rbx, [rcx+2]
0x14000d3b0  cmp     rbx, r8
0x14000d3b3  ja      short loc_14000D433
0x14000d3b5  movzx   eax, word ptr [rsi+4]
0x14000d3b9  lea     r8, [rsp+58h+arg_0]
0x14000d3be  mov     r9d, 2
0x14000d3c4  mov     [rsp+58h+arg_0], ax
0x14000d3c9  mov     edx, r9d
0x14000d3cc  jmp     short loc_14000D3EC
0x14000d3ce  cmp     byte ptr [rsi+2], 2
0x14000d3d2  mov     rbx, rcx
0x14000d3d5  jnz     short loc_14000D3F2
0x14000d3d7  lea     rbx, [rcx+4]
0x14000d3db  cmp     rbx, rdi
0x14000d3de  ja      short loc_14000D433
0x14000d3e0  mov     edx, 4; DestinationSize
0x14000d3e5  lea     r8, [rsi+4]; Source
0x14000d3e9  mov     r9d, edx; SourceSize
0x14000d3ec  call    cs:__imp_memcpy_s
0x14000d3f2  cmp     word ptr [rsi], 0
0x14000d3f6  jnz     short loc_14000D422
0x14000d3f8  lea     r15, [rbx+2]
0x14000d3fc  cmp     r15, rdi
0x14000d3ff  ja      short loc_14000D433
0x14000d401  lea     r14, [rsi+8]
0x14000d405  mov     rdx, rdi
0x14000d408  sub     rdx, rbx; DestinationSize
0x14000d40b  mov     r8, r14; Source
0x14000d40e  mov     r9d, 2; SourceSize
0x14000d414  mov     rcx, rbx; Destination
0x14000d417  call    cs:__imp_memcpy_s
0x14000d41d  mov     rbx, r15
0x14000d420  jmp     short loc_14000D426
0x14000d422  lea     r14, [rsi+8]
0x14000d426  movzx   r9d, word ptr [r14]; SourceSize
0x14000d42a  lea     rax, [r9+rbx]
0x14000d42e  cmp     rax, rdi
0x14000d431  jbe     short loc_14000D437
0x14000d433  xor     al, al
0x14000d435  jmp     short loc_14000D457
0x14000d437  mov     r8, [rsi+18h]; Source
0x14000d43b  sub     rdi, rbx
0x14000d43e  mov     rdx, rdi; DestinationSize
0x14000d441  mov     rcx, rbx; Destination
0x14000d444  call    cs:__imp_memcpy_s
0x14000d44a  movzx   ecx, word ptr [r14]
0x14000d44e  mov     al, 1
0x14000d450  add     rcx, rbx
0x14000d453  mov     [r12], rcx
0x14000d457  add     rsp, 28h
0x14000d45b  pop     r15
0x14000d45d  pop     r14
0x14000d45f  pop     r12
0x14000d461  pop     rdi
0x14000d462  pop     rsi
0x14000d463  pop     rbx
0x14000d464  retn
```
