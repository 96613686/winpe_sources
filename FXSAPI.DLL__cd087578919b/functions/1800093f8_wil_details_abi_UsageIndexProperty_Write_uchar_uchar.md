# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800093f8`
- end: `0x1800094e8`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `240`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006fb0`

## callees

- `0x1800093f8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000945c`
- `msvcrt!memcpy_s` at `0x18000948d`
- `msvcrt!memcpy_s` at `0x1800094c0`
- `msvcrt!memcpy_s` at `0x18000945c`
- `msvcrt!memcpy_s` at `0x18000948d`
- `msvcrt!memcpy_s` at `0x1800094c0`

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
0x1800093f8  push    rbx
0x1800093fa  push    rsi
0x1800093fb  push    rdi
0x1800093fc  push    r12
0x1800093fe  push    r14
0x180009400  push    r15
0x180009402  sub     rsp, 28h
0x180009406  mov     rsi, rcx
0x180009409  mov     rdi, r8
0x18000940c  mov     rcx, [rdx]; Destination
0x18000940f  mov     r12, rdx
0x180009412  cmp     byte ptr [rsi+2], 1
0x180009416  jnz     short loc_18000943E
0x180009418  lea     rbx, [rcx+2]
0x18000941c  cmp     rbx, r8
0x18000941f  ja      loc_1800094AF
0x180009425  movzx   eax, word ptr [rsi+4]
0x180009429  lea     r8, [rsp+58h+arg_0]
0x18000942e  mov     r9d, 2
0x180009434  mov     [rsp+58h+arg_0], ax
0x180009439  mov     edx, r9d
0x18000943c  jmp     short loc_18000945C
0x18000943e  cmp     byte ptr [rsi+2], 2
0x180009442  mov     rbx, rcx
0x180009445  jnz     short loc_180009468
0x180009447  lea     rbx, [rcx+4]
0x18000944b  cmp     rbx, rdi
0x18000944e  ja      short loc_1800094AF
0x180009450  mov     edx, 4; DestinationSize
0x180009455  lea     r8, [rsi+4]; Source
0x180009459  mov     r9d, edx; SourceSize
0x18000945c  call    cs:__imp_memcpy_s
0x180009463  nop     dword ptr [rax+rax+00h]
0x180009468  cmp     word ptr [rsi], 0
0x18000946c  jnz     short loc_18000949E
0x18000946e  lea     r15, [rbx+2]
0x180009472  cmp     r15, rdi
0x180009475  ja      short loc_1800094AF
0x180009477  lea     r14, [rsi+8]
0x18000947b  mov     rdx, rdi
0x18000947e  sub     rdx, rbx; DestinationSize
0x180009481  mov     r8, r14; Source
0x180009484  mov     r9d, 2; SourceSize
0x18000948a  mov     rcx, rbx; Destination
0x18000948d  call    cs:__imp_memcpy_s
0x180009494  nop     dword ptr [rax+rax+00h]
0x180009499  mov     rbx, r15
0x18000949c  jmp     short loc_1800094A2
0x18000949e  lea     r14, [rsi+8]
0x1800094a2  movzx   r9d, word ptr [r14]; SourceSize
0x1800094a6  lea     rax, [r9+rbx]
0x1800094aa  cmp     rax, rdi
0x1800094ad  jbe     short loc_1800094B3
0x1800094af  xor     al, al
0x1800094b1  jmp     short loc_1800094D9
0x1800094b3  mov     r8, [rsi+18h]; Source
0x1800094b7  sub     rdi, rbx
0x1800094ba  mov     rdx, rdi; DestinationSize
0x1800094bd  mov     rcx, rbx; Destination
0x1800094c0  call    cs:__imp_memcpy_s
0x1800094c7  nop     dword ptr [rax+rax+00h]
0x1800094cc  movzx   ecx, word ptr [r14]
0x1800094d0  mov     al, 1
0x1800094d2  add     rcx, rbx
0x1800094d5  mov     [r12], rcx
0x1800094d9  add     rsp, 28h
0x1800094dd  pop     r15
0x1800094df  pop     r14
0x1800094e1  pop     r12
0x1800094e3  pop     rdi
0x1800094e4  pop     rsi
0x1800094e5  pop     rbx
0x1800094e6  retn
```
