# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800120ac`
- end: `0x180012185`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010f1c`

## callees

- `0x1800120ac`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001210c`
- `msvcrt!memcpy_s` at `0x180012137`
- `msvcrt!memcpy_s` at `0x180012164`
- `msvcrt!memcpy_s` at `0x18001210c`
- `msvcrt!memcpy_s` at `0x180012137`
- `msvcrt!memcpy_s` at `0x180012164`

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
0x1800120ac  push    rbx
0x1800120ae  push    rsi
0x1800120af  push    rdi
0x1800120b0  push    r12
0x1800120b2  push    r14
0x1800120b4  push    r15
0x1800120b6  sub     rsp, 28h
0x1800120ba  mov     rsi, rcx
0x1800120bd  mov     rdi, r8
0x1800120c0  mov     rcx, [rdx]; Destination
0x1800120c3  mov     r12, rdx
0x1800120c6  cmp     byte ptr [rsi+2], 1
0x1800120ca  jnz     short loc_1800120EE
0x1800120cc  lea     rbx, [rcx+2]
0x1800120d0  cmp     rbx, r8
0x1800120d3  ja      short loc_180012153
0x1800120d5  movzx   eax, word ptr [rsi+4]
0x1800120d9  lea     r8, [rsp+58h+arg_0]
0x1800120de  mov     r9d, 2
0x1800120e4  mov     [rsp+58h+arg_0], ax
0x1800120e9  mov     edx, r9d
0x1800120ec  jmp     short loc_18001210C
0x1800120ee  cmp     byte ptr [rsi+2], 2
0x1800120f2  mov     rbx, rcx
0x1800120f5  jnz     short loc_180012112
0x1800120f7  lea     rbx, [rcx+4]
0x1800120fb  cmp     rbx, rdi
0x1800120fe  ja      short loc_180012153
0x180012100  mov     edx, 4; DestinationSize
0x180012105  lea     r8, [rsi+4]; Source
0x180012109  mov     r9d, edx; SourceSize
0x18001210c  call    cs:__imp_memcpy_s
0x180012112  cmp     word ptr [rsi], 0
0x180012116  jnz     short loc_180012142
0x180012118  lea     r15, [rbx+2]
0x18001211c  cmp     r15, rdi
0x18001211f  ja      short loc_180012153
0x180012121  lea     r14, [rsi+8]
0x180012125  mov     rdx, rdi
0x180012128  sub     rdx, rbx; DestinationSize
0x18001212b  mov     r8, r14; Source
0x18001212e  mov     r9d, 2; SourceSize
0x180012134  mov     rcx, rbx; Destination
0x180012137  call    cs:__imp_memcpy_s
0x18001213d  mov     rbx, r15
0x180012140  jmp     short loc_180012146
0x180012142  lea     r14, [rsi+8]
0x180012146  movzx   r9d, word ptr [r14]; SourceSize
0x18001214a  lea     rax, [r9+rbx]
0x18001214e  cmp     rax, rdi
0x180012151  jbe     short loc_180012157
0x180012153  xor     al, al
0x180012155  jmp     short loc_180012177
0x180012157  mov     r8, [rsi+18h]; Source
0x18001215b  sub     rdi, rbx
0x18001215e  mov     rdx, rdi; DestinationSize
0x180012161  mov     rcx, rbx; Destination
0x180012164  call    cs:__imp_memcpy_s
0x18001216a  movzx   ecx, word ptr [r14]
0x18001216e  mov     al, 1
0x180012170  add     rcx, rbx
0x180012173  mov     [r12], rcx
0x180012177  add     rsp, 28h
0x18001217b  pop     r15
0x18001217d  pop     r14
0x18001217f  pop     r12
0x180012181  pop     rdi
0x180012182  pop     rsi
0x180012183  pop     rbx
0x180012184  retn
```
