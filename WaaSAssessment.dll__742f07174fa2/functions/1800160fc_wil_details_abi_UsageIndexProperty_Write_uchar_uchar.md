# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800160fc`
- end: `0x1800161d5`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014964`

## callees

- `0x1800160fc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001615c`
- `msvcrt!memcpy_s` at `0x180016187`
- `msvcrt!memcpy_s` at `0x1800161b4`
- `msvcrt!memcpy_s` at `0x18001615c`
- `msvcrt!memcpy_s` at `0x180016187`
- `msvcrt!memcpy_s` at `0x1800161b4`

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
0x1800160fc  push    rbx
0x1800160fe  push    rsi
0x1800160ff  push    rdi
0x180016100  push    r12
0x180016102  push    r14
0x180016104  push    r15
0x180016106  sub     rsp, 28h
0x18001610a  mov     rsi, rcx
0x18001610d  mov     rdi, r8
0x180016110  mov     rcx, [rdx]; Destination
0x180016113  mov     r12, rdx
0x180016116  cmp     byte ptr [rsi+2], 1
0x18001611a  jnz     short loc_18001613E
0x18001611c  lea     rbx, [rcx+2]
0x180016120  cmp     rbx, r8
0x180016123  ja      short loc_1800161A3
0x180016125  movzx   eax, word ptr [rsi+4]
0x180016129  lea     r8, [rsp+58h+arg_0]
0x18001612e  mov     r9d, 2
0x180016134  mov     [rsp+58h+arg_0], ax
0x180016139  mov     edx, r9d
0x18001613c  jmp     short loc_18001615C
0x18001613e  cmp     byte ptr [rsi+2], 2
0x180016142  mov     rbx, rcx
0x180016145  jnz     short loc_180016162
0x180016147  lea     rbx, [rcx+4]
0x18001614b  cmp     rbx, rdi
0x18001614e  ja      short loc_1800161A3
0x180016150  mov     edx, 4; DestinationSize
0x180016155  lea     r8, [rsi+4]; Source
0x180016159  mov     r9d, edx; SourceSize
0x18001615c  call    cs:__imp_memcpy_s
0x180016162  cmp     word ptr [rsi], 0
0x180016166  jnz     short loc_180016192
0x180016168  lea     r15, [rbx+2]
0x18001616c  cmp     r15, rdi
0x18001616f  ja      short loc_1800161A3
0x180016171  lea     r14, [rsi+8]
0x180016175  mov     rdx, rdi
0x180016178  sub     rdx, rbx; DestinationSize
0x18001617b  mov     r8, r14; Source
0x18001617e  mov     r9d, 2; SourceSize
0x180016184  mov     rcx, rbx; Destination
0x180016187  call    cs:__imp_memcpy_s
0x18001618d  mov     rbx, r15
0x180016190  jmp     short loc_180016196
0x180016192  lea     r14, [rsi+8]
0x180016196  movzx   r9d, word ptr [r14]; SourceSize
0x18001619a  lea     rax, [r9+rbx]
0x18001619e  cmp     rax, rdi
0x1800161a1  jbe     short loc_1800161A7
0x1800161a3  xor     al, al
0x1800161a5  jmp     short loc_1800161C7
0x1800161a7  mov     r8, [rsi+18h]; Source
0x1800161ab  sub     rdi, rbx
0x1800161ae  mov     rdx, rdi; DestinationSize
0x1800161b1  mov     rcx, rbx; Destination
0x1800161b4  call    cs:__imp_memcpy_s
0x1800161ba  movzx   ecx, word ptr [r14]
0x1800161be  mov     al, 1
0x1800161c0  add     rcx, rbx
0x1800161c3  mov     [r12], rcx
0x1800161c7  add     rsp, 28h
0x1800161cb  pop     r15
0x1800161cd  pop     r14
0x1800161cf  pop     r12
0x1800161d1  pop     rdi
0x1800161d2  pop     rsi
0x1800161d3  pop     rbx
0x1800161d4  retn
```
