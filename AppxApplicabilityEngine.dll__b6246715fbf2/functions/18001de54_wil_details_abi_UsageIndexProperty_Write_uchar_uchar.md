# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18001de54`
- end: `0x18001df2d`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001d320`

## callees

- `0x18001de54`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001deb4`
- `msvcrt!memcpy_s` at `0x18001dedf`
- `msvcrt!memcpy_s` at `0x18001df0c`
- `msvcrt!memcpy_s` at `0x18001deb4`
- `msvcrt!memcpy_s` at `0x18001dedf`
- `msvcrt!memcpy_s` at `0x18001df0c`

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
0x18001de54  push    rbx
0x18001de56  push    rsi
0x18001de57  push    rdi
0x18001de58  push    r12
0x18001de5a  push    r14
0x18001de5c  push    r15
0x18001de5e  sub     rsp, 28h
0x18001de62  mov     rsi, rcx
0x18001de65  mov     rdi, r8
0x18001de68  mov     rcx, [rdx]; Destination
0x18001de6b  mov     r12, rdx
0x18001de6e  cmp     byte ptr [rsi+2], 1
0x18001de72  jnz     short loc_18001DE96
0x18001de74  lea     rbx, [rcx+2]
0x18001de78  cmp     rbx, r8
0x18001de7b  ja      short loc_18001DEFB
0x18001de7d  movzx   eax, word ptr [rsi+4]
0x18001de81  lea     r8, [rsp+58h+arg_0]
0x18001de86  mov     r9d, 2
0x18001de8c  mov     [rsp+58h+arg_0], ax
0x18001de91  mov     edx, r9d
0x18001de94  jmp     short loc_18001DEB4
0x18001de96  cmp     byte ptr [rsi+2], 2
0x18001de9a  mov     rbx, rcx
0x18001de9d  jnz     short loc_18001DEBA
0x18001de9f  lea     rbx, [rcx+4]
0x18001dea3  cmp     rbx, rdi
0x18001dea6  ja      short loc_18001DEFB
0x18001dea8  mov     edx, 4; DestinationSize
0x18001dead  lea     r8, [rsi+4]; Source
0x18001deb1  mov     r9d, edx; SourceSize
0x18001deb4  call    cs:__imp_memcpy_s
0x18001deba  cmp     word ptr [rsi], 0
0x18001debe  jnz     short loc_18001DEEA
0x18001dec0  lea     r15, [rbx+2]
0x18001dec4  cmp     r15, rdi
0x18001dec7  ja      short loc_18001DEFB
0x18001dec9  lea     r14, [rsi+8]
0x18001decd  mov     rdx, rdi
0x18001ded0  sub     rdx, rbx; DestinationSize
0x18001ded3  mov     r8, r14; Source
0x18001ded6  mov     r9d, 2; SourceSize
0x18001dedc  mov     rcx, rbx; Destination
0x18001dedf  call    cs:__imp_memcpy_s
0x18001dee5  mov     rbx, r15
0x18001dee8  jmp     short loc_18001DEEE
0x18001deea  lea     r14, [rsi+8]
0x18001deee  movzx   r9d, word ptr [r14]; SourceSize
0x18001def2  lea     rax, [r9+rbx]
0x18001def6  cmp     rax, rdi
0x18001def9  jbe     short loc_18001DEFF
0x18001defb  xor     al, al
0x18001defd  jmp     short loc_18001DF1F
0x18001deff  mov     r8, [rsi+18h]; Source
0x18001df03  sub     rdi, rbx
0x18001df06  mov     rdx, rdi; DestinationSize
0x18001df09  mov     rcx, rbx; Destination
0x18001df0c  call    cs:__imp_memcpy_s
0x18001df12  movzx   ecx, word ptr [r14]
0x18001df16  mov     al, 1
0x18001df18  add     rcx, rbx
0x18001df1b  mov     [r12], rcx
0x18001df1f  add     rsp, 28h
0x18001df23  pop     r15
0x18001df25  pop     r14
0x18001df27  pop     r12
0x18001df29  pop     rdi
0x18001df2a  pop     rsi
0x18001df2b  pop     rbx
0x18001df2c  retn
```
