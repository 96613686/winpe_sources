# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180007b6c`
- end: `0x180007c45`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005fa4`

## callees

- `0x180007b6c`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180007bcc`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180007bf7`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180007c24`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180007bcc`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180007bf7`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180007c24`

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
0x180007b6c  push    rbx
0x180007b6e  push    rsi
0x180007b6f  push    rdi
0x180007b70  push    r12
0x180007b72  push    r14
0x180007b74  push    r15
0x180007b76  sub     rsp, 28h
0x180007b7a  mov     rsi, rcx
0x180007b7d  mov     rdi, r8
0x180007b80  mov     rcx, [rdx]; Destination
0x180007b83  mov     r12, rdx
0x180007b86  cmp     byte ptr [rsi+2], 1
0x180007b8a  jnz     short loc_180007BAE
0x180007b8c  lea     rbx, [rcx+2]
0x180007b90  cmp     rbx, r8
0x180007b93  ja      short loc_180007C13
0x180007b95  movzx   eax, word ptr [rsi+4]
0x180007b99  lea     r8, [rsp+58h+arg_0]
0x180007b9e  mov     r9d, 2
0x180007ba4  mov     [rsp+58h+arg_0], ax
0x180007ba9  mov     edx, r9d
0x180007bac  jmp     short loc_180007BCC
0x180007bae  cmp     byte ptr [rsi+2], 2
0x180007bb2  mov     rbx, rcx
0x180007bb5  jnz     short loc_180007BD2
0x180007bb7  lea     rbx, [rcx+4]
0x180007bbb  cmp     rbx, rdi
0x180007bbe  ja      short loc_180007C13
0x180007bc0  mov     edx, 4; DestinationSize
0x180007bc5  lea     r8, [rsi+4]; Source
0x180007bc9  mov     r9d, edx; SourceSize
0x180007bcc  call    cs:__imp_memcpy_s
0x180007bd2  cmp     word ptr [rsi], 0
0x180007bd6  jnz     short loc_180007C02
0x180007bd8  lea     r15, [rbx+2]
0x180007bdc  cmp     r15, rdi
0x180007bdf  ja      short loc_180007C13
0x180007be1  lea     r14, [rsi+8]
0x180007be5  mov     rdx, rdi
0x180007be8  sub     rdx, rbx; DestinationSize
0x180007beb  mov     r8, r14; Source
0x180007bee  mov     r9d, 2; SourceSize
0x180007bf4  mov     rcx, rbx; Destination
0x180007bf7  call    cs:__imp_memcpy_s
0x180007bfd  mov     rbx, r15
0x180007c00  jmp     short loc_180007C06
0x180007c02  lea     r14, [rsi+8]
0x180007c06  movzx   r9d, word ptr [r14]; SourceSize
0x180007c0a  lea     rax, [r9+rbx]
0x180007c0e  cmp     rax, rdi
0x180007c11  jbe     short loc_180007C17
0x180007c13  xor     al, al
0x180007c15  jmp     short loc_180007C37
0x180007c17  mov     r8, [rsi+18h]; Source
0x180007c1b  sub     rdi, rbx
0x180007c1e  mov     rdx, rdi; DestinationSize
0x180007c21  mov     rcx, rbx; Destination
0x180007c24  call    cs:__imp_memcpy_s
0x180007c2a  movzx   ecx, word ptr [r14]
0x180007c2e  mov     al, 1
0x180007c30  add     rcx, rbx
0x180007c33  mov     [r12], rcx
0x180007c37  add     rsp, 28h
0x180007c3b  pop     r15
0x180007c3d  pop     r14
0x180007c3f  pop     r12
0x180007c41  pop     rdi
0x180007c42  pop     rsi
0x180007c43  pop     rbx
0x180007c44  retn
```
