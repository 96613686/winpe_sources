# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18001653c`
- end: `0x18001662c`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `240`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014480`

## callees

- `0x18001653c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800165a0`
- `msvcrt!memcpy_s` at `0x1800165d1`
- `msvcrt!memcpy_s` at `0x180016604`
- `msvcrt!memcpy_s` at `0x1800165a0`
- `msvcrt!memcpy_s` at `0x1800165d1`
- `msvcrt!memcpy_s` at `0x180016604`

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
0x18001653c  push    rbx
0x18001653e  push    rsi
0x18001653f  push    rdi
0x180016540  push    r12
0x180016542  push    r14
0x180016544  push    r15
0x180016546  sub     rsp, 28h
0x18001654a  mov     rsi, rcx
0x18001654d  mov     rdi, r8
0x180016550  mov     rcx, [rdx]; Destination
0x180016553  mov     r12, rdx
0x180016556  cmp     byte ptr [rsi+2], 1
0x18001655a  jnz     short loc_180016582
0x18001655c  lea     rbx, [rcx+2]
0x180016560  cmp     rbx, r8
0x180016563  ja      loc_1800165F3
0x180016569  movzx   eax, word ptr [rsi+4]
0x18001656d  lea     r8, [rsp+58h+arg_0]
0x180016572  mov     r9d, 2
0x180016578  mov     [rsp+58h+arg_0], ax
0x18001657d  mov     edx, r9d
0x180016580  jmp     short loc_1800165A0
0x180016582  cmp     byte ptr [rsi+2], 2
0x180016586  mov     rbx, rcx
0x180016589  jnz     short loc_1800165AC
0x18001658b  lea     rbx, [rcx+4]
0x18001658f  cmp     rbx, rdi
0x180016592  ja      short loc_1800165F3
0x180016594  mov     edx, 4; DestinationSize
0x180016599  lea     r8, [rsi+4]; Source
0x18001659d  mov     r9d, edx; SourceSize
0x1800165a0  call    cs:__imp_memcpy_s
0x1800165a7  nop     dword ptr [rax+rax+00h]
0x1800165ac  cmp     word ptr [rsi], 0
0x1800165b0  jnz     short loc_1800165E2
0x1800165b2  lea     r15, [rbx+2]
0x1800165b6  cmp     r15, rdi
0x1800165b9  ja      short loc_1800165F3
0x1800165bb  lea     r14, [rsi+8]
0x1800165bf  mov     rdx, rdi
0x1800165c2  sub     rdx, rbx; DestinationSize
0x1800165c5  mov     r8, r14; Source
0x1800165c8  mov     r9d, 2; SourceSize
0x1800165ce  mov     rcx, rbx; Destination
0x1800165d1  call    cs:__imp_memcpy_s
0x1800165d8  nop     dword ptr [rax+rax+00h]
0x1800165dd  mov     rbx, r15
0x1800165e0  jmp     short loc_1800165E6
0x1800165e2  lea     r14, [rsi+8]
0x1800165e6  movzx   r9d, word ptr [r14]; SourceSize
0x1800165ea  lea     rax, [r9+rbx]
0x1800165ee  cmp     rax, rdi
0x1800165f1  jbe     short loc_1800165F7
0x1800165f3  xor     al, al
0x1800165f5  jmp     short loc_18001661D
0x1800165f7  mov     r8, [rsi+18h]; Source
0x1800165fb  sub     rdi, rbx
0x1800165fe  mov     rdx, rdi; DestinationSize
0x180016601  mov     rcx, rbx; Destination
0x180016604  call    cs:__imp_memcpy_s
0x18001660b  nop     dword ptr [rax+rax+00h]
0x180016610  movzx   ecx, word ptr [r14]
0x180016614  mov     al, 1
0x180016616  add     rcx, rbx
0x180016619  mov     [r12], rcx
0x18001661d  add     rsp, 28h
0x180016621  pop     r15
0x180016623  pop     r14
0x180016625  pop     r12
0x180016627  pop     rdi
0x180016628  pop     rsi
0x180016629  pop     rbx
0x18001662a  retn
```
