# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x140011524`
- end: `0x1400115fd`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f718`

## callees

- `0x140011524`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140011584`
- `msvcrt!memcpy_s` at `0x1400115af`
- `msvcrt!memcpy_s` at `0x1400115dc`
- `msvcrt!memcpy_s` at `0x140011584`
- `msvcrt!memcpy_s` at `0x1400115af`
- `msvcrt!memcpy_s` at `0x1400115dc`

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
0x140011524  push    rbx
0x140011526  push    rsi
0x140011527  push    rdi
0x140011528  push    r12
0x14001152a  push    r14
0x14001152c  push    r15
0x14001152e  sub     rsp, 28h
0x140011532  mov     rsi, rcx
0x140011535  mov     rdi, r8
0x140011538  mov     rcx, [rdx]; Destination
0x14001153b  mov     r12, rdx
0x14001153e  cmp     byte ptr [rsi+2], 1
0x140011542  jnz     short loc_140011566
0x140011544  lea     rbx, [rcx+2]
0x140011548  cmp     rbx, r8
0x14001154b  ja      short loc_1400115CB
0x14001154d  movzx   eax, word ptr [rsi+4]
0x140011551  lea     r8, [rsp+58h+arg_0]
0x140011556  mov     r9d, 2
0x14001155c  mov     [rsp+58h+arg_0], ax
0x140011561  mov     edx, r9d
0x140011564  jmp     short loc_140011584
0x140011566  cmp     byte ptr [rsi+2], 2
0x14001156a  mov     rbx, rcx
0x14001156d  jnz     short loc_14001158A
0x14001156f  lea     rbx, [rcx+4]
0x140011573  cmp     rbx, rdi
0x140011576  ja      short loc_1400115CB
0x140011578  mov     edx, 4; DestinationSize
0x14001157d  lea     r8, [rsi+4]; Source
0x140011581  mov     r9d, edx; SourceSize
0x140011584  call    cs:__imp_memcpy_s
0x14001158a  cmp     word ptr [rsi], 0
0x14001158e  jnz     short loc_1400115BA
0x140011590  lea     r15, [rbx+2]
0x140011594  cmp     r15, rdi
0x140011597  ja      short loc_1400115CB
0x140011599  lea     r14, [rsi+8]
0x14001159d  mov     rdx, rdi
0x1400115a0  sub     rdx, rbx; DestinationSize
0x1400115a3  mov     r8, r14; Source
0x1400115a6  mov     r9d, 2; SourceSize
0x1400115ac  mov     rcx, rbx; Destination
0x1400115af  call    cs:__imp_memcpy_s
0x1400115b5  mov     rbx, r15
0x1400115b8  jmp     short loc_1400115BE
0x1400115ba  lea     r14, [rsi+8]
0x1400115be  movzx   r9d, word ptr [r14]; SourceSize
0x1400115c2  lea     rax, [r9+rbx]
0x1400115c6  cmp     rax, rdi
0x1400115c9  jbe     short loc_1400115CF
0x1400115cb  xor     al, al
0x1400115cd  jmp     short loc_1400115EF
0x1400115cf  mov     r8, [rsi+18h]; Source
0x1400115d3  sub     rdi, rbx
0x1400115d6  mov     rdx, rdi; DestinationSize
0x1400115d9  mov     rcx, rbx; Destination
0x1400115dc  call    cs:__imp_memcpy_s
0x1400115e2  movzx   ecx, word ptr [r14]
0x1400115e6  mov     al, 1
0x1400115e8  add     rcx, rbx
0x1400115eb  mov     [r12], rcx
0x1400115ef  add     rsp, 28h
0x1400115f3  pop     r15
0x1400115f5  pop     r14
0x1400115f7  pop     r12
0x1400115f9  pop     rdi
0x1400115fa  pop     rsi
0x1400115fb  pop     rbx
0x1400115fc  retn
```
