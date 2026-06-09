# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000e86c`
- end: `0x14000e945`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c7a8`

## callees

- `0x14000e86c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000e8cc`
- `msvcrt!memcpy_s` at `0x14000e8f7`
- `msvcrt!memcpy_s` at `0x14000e924`
- `msvcrt!memcpy_s` at `0x14000e8cc`
- `msvcrt!memcpy_s` at `0x14000e8f7`
- `msvcrt!memcpy_s` at `0x14000e924`

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
0x14000e86c  push    rbx
0x14000e86e  push    rsi
0x14000e86f  push    rdi
0x14000e870  push    r12
0x14000e872  push    r14
0x14000e874  push    r15
0x14000e876  sub     rsp, 28h
0x14000e87a  mov     rsi, rcx
0x14000e87d  mov     rdi, r8
0x14000e880  mov     rcx, [rdx]; Destination
0x14000e883  mov     r12, rdx
0x14000e886  cmp     byte ptr [rsi+2], 1
0x14000e88a  jnz     short loc_14000E8AE
0x14000e88c  lea     rbx, [rcx+2]
0x14000e890  cmp     rbx, r8
0x14000e893  ja      short loc_14000E913
0x14000e895  movzx   eax, word ptr [rsi+4]
0x14000e899  lea     r8, [rsp+58h+arg_0]
0x14000e89e  mov     r9d, 2
0x14000e8a4  mov     [rsp+58h+arg_0], ax
0x14000e8a9  mov     edx, r9d
0x14000e8ac  jmp     short loc_14000E8CC
0x14000e8ae  cmp     byte ptr [rsi+2], 2
0x14000e8b2  mov     rbx, rcx
0x14000e8b5  jnz     short loc_14000E8D2
0x14000e8b7  lea     rbx, [rcx+4]
0x14000e8bb  cmp     rbx, rdi
0x14000e8be  ja      short loc_14000E913
0x14000e8c0  mov     edx, 4; DestinationSize
0x14000e8c5  lea     r8, [rsi+4]; Source
0x14000e8c9  mov     r9d, edx; SourceSize
0x14000e8cc  call    cs:__imp_memcpy_s
0x14000e8d2  cmp     word ptr [rsi], 0
0x14000e8d6  jnz     short loc_14000E902
0x14000e8d8  lea     r15, [rbx+2]
0x14000e8dc  cmp     r15, rdi
0x14000e8df  ja      short loc_14000E913
0x14000e8e1  lea     r14, [rsi+8]
0x14000e8e5  mov     rdx, rdi
0x14000e8e8  sub     rdx, rbx; DestinationSize
0x14000e8eb  mov     r8, r14; Source
0x14000e8ee  mov     r9d, 2; SourceSize
0x14000e8f4  mov     rcx, rbx; Destination
0x14000e8f7  call    cs:__imp_memcpy_s
0x14000e8fd  mov     rbx, r15
0x14000e900  jmp     short loc_14000E906
0x14000e902  lea     r14, [rsi+8]
0x14000e906  movzx   r9d, word ptr [r14]; SourceSize
0x14000e90a  lea     rax, [r9+rbx]
0x14000e90e  cmp     rax, rdi
0x14000e911  jbe     short loc_14000E917
0x14000e913  xor     al, al
0x14000e915  jmp     short loc_14000E937
0x14000e917  mov     r8, [rsi+18h]; Source
0x14000e91b  sub     rdi, rbx
0x14000e91e  mov     rdx, rdi; DestinationSize
0x14000e921  mov     rcx, rbx; Destination
0x14000e924  call    cs:__imp_memcpy_s
0x14000e92a  movzx   ecx, word ptr [r14]
0x14000e92e  mov     al, 1
0x14000e930  add     rcx, rbx
0x14000e933  mov     [r12], rcx
0x14000e937  add     rsp, 28h
0x14000e93b  pop     r15
0x14000e93d  pop     r14
0x14000e93f  pop     r12
0x14000e941  pop     rdi
0x14000e942  pop     rsi
0x14000e943  pop     rbx
0x14000e944  retn
```
