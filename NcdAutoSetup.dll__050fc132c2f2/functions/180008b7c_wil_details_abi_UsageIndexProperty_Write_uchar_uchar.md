# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180008b7c`
- end: `0x180008c55`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006810`

## callees

- `0x180008b7c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008bdc`
- `msvcrt!memcpy_s` at `0x180008c07`
- `msvcrt!memcpy_s` at `0x180008c34`
- `msvcrt!memcpy_s` at `0x180008bdc`
- `msvcrt!memcpy_s` at `0x180008c07`
- `msvcrt!memcpy_s` at `0x180008c34`

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
0x180008b7c  push    rbx
0x180008b7e  push    rsi
0x180008b7f  push    rdi
0x180008b80  push    r12
0x180008b82  push    r14
0x180008b84  push    r15
0x180008b86  sub     rsp, 28h
0x180008b8a  mov     rsi, rcx
0x180008b8d  mov     rdi, r8
0x180008b90  mov     rcx, [rdx]; Destination
0x180008b93  mov     r12, rdx
0x180008b96  cmp     byte ptr [rsi+2], 1
0x180008b9a  jnz     short loc_180008BBE
0x180008b9c  lea     rbx, [rcx+2]
0x180008ba0  cmp     rbx, r8
0x180008ba3  ja      short loc_180008C23
0x180008ba5  movzx   eax, word ptr [rsi+4]
0x180008ba9  lea     r8, [rsp+58h+arg_0]
0x180008bae  mov     r9d, 2
0x180008bb4  mov     [rsp+58h+arg_0], ax
0x180008bb9  mov     edx, r9d
0x180008bbc  jmp     short loc_180008BDC
0x180008bbe  cmp     byte ptr [rsi+2], 2
0x180008bc2  mov     rbx, rcx
0x180008bc5  jnz     short loc_180008BE2
0x180008bc7  lea     rbx, [rcx+4]
0x180008bcb  cmp     rbx, rdi
0x180008bce  ja      short loc_180008C23
0x180008bd0  mov     edx, 4; DestinationSize
0x180008bd5  lea     r8, [rsi+4]; Source
0x180008bd9  mov     r9d, edx; SourceSize
0x180008bdc  call    cs:__imp_memcpy_s
0x180008be2  cmp     word ptr [rsi], 0
0x180008be6  jnz     short loc_180008C12
0x180008be8  lea     r15, [rbx+2]
0x180008bec  cmp     r15, rdi
0x180008bef  ja      short loc_180008C23
0x180008bf1  lea     r14, [rsi+8]
0x180008bf5  mov     rdx, rdi
0x180008bf8  sub     rdx, rbx; DestinationSize
0x180008bfb  mov     r8, r14; Source
0x180008bfe  mov     r9d, 2; SourceSize
0x180008c04  mov     rcx, rbx; Destination
0x180008c07  call    cs:__imp_memcpy_s
0x180008c0d  mov     rbx, r15
0x180008c10  jmp     short loc_180008C16
0x180008c12  lea     r14, [rsi+8]
0x180008c16  movzx   r9d, word ptr [r14]; SourceSize
0x180008c1a  lea     rax, [r9+rbx]
0x180008c1e  cmp     rax, rdi
0x180008c21  jbe     short loc_180008C27
0x180008c23  xor     al, al
0x180008c25  jmp     short loc_180008C47
0x180008c27  mov     r8, [rsi+18h]; Source
0x180008c2b  sub     rdi, rbx
0x180008c2e  mov     rdx, rdi; DestinationSize
0x180008c31  mov     rcx, rbx; Destination
0x180008c34  call    cs:__imp_memcpy_s
0x180008c3a  movzx   ecx, word ptr [r14]
0x180008c3e  mov     al, 1
0x180008c40  add     rcx, rbx
0x180008c43  mov     [r12], rcx
0x180008c47  add     rsp, 28h
0x180008c4b  pop     r15
0x180008c4d  pop     r14
0x180008c4f  pop     r12
0x180008c51  pop     rdi
0x180008c52  pop     rsi
0x180008c53  pop     rbx
0x180008c54  retn
```
