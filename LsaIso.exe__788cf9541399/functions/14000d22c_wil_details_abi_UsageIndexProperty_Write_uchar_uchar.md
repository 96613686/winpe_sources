# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000d22c`
- end: `0x14000d305`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000b978`

## callees

- `0x14000d22c`

## import_xrefs

- `ntdll!memcpy_s` at `0x14000d28c`
- `ntdll!memcpy_s` at `0x14000d2b7`
- `ntdll!memcpy_s` at `0x14000d2e4`
- `ntdll!memcpy_s` at `0x14000d28c`
- `ntdll!memcpy_s` at `0x14000d2b7`
- `ntdll!memcpy_s` at `0x14000d2e4`

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
0x14000d22c  push    rbx
0x14000d22e  push    rsi
0x14000d22f  push    rdi
0x14000d230  push    r12
0x14000d232  push    r14
0x14000d234  push    r15
0x14000d236  sub     rsp, 28h
0x14000d23a  mov     rsi, rcx
0x14000d23d  mov     rdi, r8
0x14000d240  mov     rcx, [rdx]; Destination
0x14000d243  mov     r12, rdx
0x14000d246  cmp     byte ptr [rsi+2], 1
0x14000d24a  jnz     short loc_14000D26E
0x14000d24c  lea     rbx, [rcx+2]
0x14000d250  cmp     rbx, r8
0x14000d253  ja      short loc_14000D2D3
0x14000d255  movzx   eax, word ptr [rsi+4]
0x14000d259  lea     r8, [rsp+58h+arg_0]
0x14000d25e  mov     r9d, 2
0x14000d264  mov     [rsp+58h+arg_0], ax
0x14000d269  mov     edx, r9d
0x14000d26c  jmp     short loc_14000D28C
0x14000d26e  cmp     byte ptr [rsi+2], 2
0x14000d272  mov     rbx, rcx
0x14000d275  jnz     short loc_14000D292
0x14000d277  lea     rbx, [rcx+4]
0x14000d27b  cmp     rbx, rdi
0x14000d27e  ja      short loc_14000D2D3
0x14000d280  mov     edx, 4; DestinationSize
0x14000d285  lea     r8, [rsi+4]; Source
0x14000d289  mov     r9d, edx; SourceSize
0x14000d28c  call    cs:__imp_memcpy_s
0x14000d292  cmp     word ptr [rsi], 0
0x14000d296  jnz     short loc_14000D2C2
0x14000d298  lea     r15, [rbx+2]
0x14000d29c  cmp     r15, rdi
0x14000d29f  ja      short loc_14000D2D3
0x14000d2a1  lea     r14, [rsi+8]
0x14000d2a5  mov     rdx, rdi
0x14000d2a8  sub     rdx, rbx; DestinationSize
0x14000d2ab  mov     r8, r14; Source
0x14000d2ae  mov     r9d, 2; SourceSize
0x14000d2b4  mov     rcx, rbx; Destination
0x14000d2b7  call    cs:__imp_memcpy_s
0x14000d2bd  mov     rbx, r15
0x14000d2c0  jmp     short loc_14000D2C6
0x14000d2c2  lea     r14, [rsi+8]
0x14000d2c6  movzx   r9d, word ptr [r14]; SourceSize
0x14000d2ca  lea     rax, [r9+rbx]
0x14000d2ce  cmp     rax, rdi
0x14000d2d1  jbe     short loc_14000D2D7
0x14000d2d3  xor     al, al
0x14000d2d5  jmp     short loc_14000D2F7
0x14000d2d7  mov     r8, [rsi+18h]; Source
0x14000d2db  sub     rdi, rbx
0x14000d2de  mov     rdx, rdi; DestinationSize
0x14000d2e1  mov     rcx, rbx; Destination
0x14000d2e4  call    cs:__imp_memcpy_s
0x14000d2ea  movzx   ecx, word ptr [r14]
0x14000d2ee  mov     al, 1
0x14000d2f0  add     rcx, rbx
0x14000d2f3  mov     [r12], rcx
0x14000d2f7  add     rsp, 28h
0x14000d2fb  pop     r15
0x14000d2fd  pop     r14
0x14000d2ff  pop     r12
0x14000d301  pop     rdi
0x14000d302  pop     rsi
0x14000d303  pop     rbx
0x14000d304  retn
```
