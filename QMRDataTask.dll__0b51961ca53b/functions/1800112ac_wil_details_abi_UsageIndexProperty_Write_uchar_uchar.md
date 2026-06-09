# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800112ac`
- end: `0x180011385`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d218`

## callees

- `0x1800112ac`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001130c`
- `msvcrt!memcpy_s` at `0x180011337`
- `msvcrt!memcpy_s` at `0x180011364`
- `msvcrt!memcpy_s` at `0x18001130c`
- `msvcrt!memcpy_s` at `0x180011337`
- `msvcrt!memcpy_s` at `0x180011364`

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
0x1800112ac  push    rbx
0x1800112ae  push    rsi
0x1800112af  push    rdi
0x1800112b0  push    r12
0x1800112b2  push    r14
0x1800112b4  push    r15
0x1800112b6  sub     rsp, 28h
0x1800112ba  mov     rsi, rcx
0x1800112bd  mov     rdi, r8
0x1800112c0  mov     rcx, [rdx]; Destination
0x1800112c3  mov     r12, rdx
0x1800112c6  cmp     byte ptr [rsi+2], 1
0x1800112ca  jnz     short loc_1800112EE
0x1800112cc  lea     rbx, [rcx+2]
0x1800112d0  cmp     rbx, r8
0x1800112d3  ja      short loc_180011353
0x1800112d5  movzx   eax, word ptr [rsi+4]
0x1800112d9  lea     r8, [rsp+58h+arg_0]
0x1800112de  mov     r9d, 2
0x1800112e4  mov     [rsp+58h+arg_0], ax
0x1800112e9  mov     edx, r9d
0x1800112ec  jmp     short loc_18001130C
0x1800112ee  cmp     byte ptr [rsi+2], 2
0x1800112f2  mov     rbx, rcx
0x1800112f5  jnz     short loc_180011312
0x1800112f7  lea     rbx, [rcx+4]
0x1800112fb  cmp     rbx, rdi
0x1800112fe  ja      short loc_180011353
0x180011300  mov     edx, 4; DestinationSize
0x180011305  lea     r8, [rsi+4]; Source
0x180011309  mov     r9d, edx; SourceSize
0x18001130c  call    cs:__imp_memcpy_s
0x180011312  cmp     word ptr [rsi], 0
0x180011316  jnz     short loc_180011342
0x180011318  lea     r15, [rbx+2]
0x18001131c  cmp     r15, rdi
0x18001131f  ja      short loc_180011353
0x180011321  lea     r14, [rsi+8]
0x180011325  mov     rdx, rdi
0x180011328  sub     rdx, rbx; DestinationSize
0x18001132b  mov     r8, r14; Source
0x18001132e  mov     r9d, 2; SourceSize
0x180011334  mov     rcx, rbx; Destination
0x180011337  call    cs:__imp_memcpy_s
0x18001133d  mov     rbx, r15
0x180011340  jmp     short loc_180011346
0x180011342  lea     r14, [rsi+8]
0x180011346  movzx   r9d, word ptr [r14]; SourceSize
0x18001134a  lea     rax, [r9+rbx]
0x18001134e  cmp     rax, rdi
0x180011351  jbe     short loc_180011357
0x180011353  xor     al, al
0x180011355  jmp     short loc_180011377
0x180011357  mov     r8, [rsi+18h]; Source
0x18001135b  sub     rdi, rbx
0x18001135e  mov     rdx, rdi; DestinationSize
0x180011361  mov     rcx, rbx; Destination
0x180011364  call    cs:__imp_memcpy_s
0x18001136a  movzx   ecx, word ptr [r14]
0x18001136e  mov     al, 1
0x180011370  add     rcx, rbx
0x180011373  mov     [r12], rcx
0x180011377  add     rsp, 28h
0x18001137b  pop     r15
0x18001137d  pop     r14
0x18001137f  pop     r12
0x180011381  pop     rdi
0x180011382  pop     rsi
0x180011383  pop     rbx
0x180011384  retn
```
