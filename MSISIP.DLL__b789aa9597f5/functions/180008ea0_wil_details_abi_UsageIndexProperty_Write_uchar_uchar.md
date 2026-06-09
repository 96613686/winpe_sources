# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180008ea0`
- end: `0x180008f79`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004c5c`

## callees

- `0x180008ea0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008f00`
- `msvcrt!memcpy_s` at `0x180008f2b`
- `msvcrt!memcpy_s` at `0x180008f58`
- `msvcrt!memcpy_s` at `0x180008f00`
- `msvcrt!memcpy_s` at `0x180008f2b`
- `msvcrt!memcpy_s` at `0x180008f58`

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
0x180008ea0  push    rbx
0x180008ea2  push    rsi
0x180008ea3  push    rdi
0x180008ea4  push    r12
0x180008ea6  push    r14
0x180008ea8  push    r15
0x180008eaa  sub     rsp, 28h
0x180008eae  mov     rsi, rcx
0x180008eb1  mov     rdi, r8
0x180008eb4  mov     rcx, [rdx]; Destination
0x180008eb7  mov     r12, rdx
0x180008eba  cmp     byte ptr [rsi+2], 1
0x180008ebe  jnz     short loc_180008EE2
0x180008ec0  lea     rbx, [rcx+2]
0x180008ec4  cmp     rbx, r8
0x180008ec7  ja      short loc_180008F47
0x180008ec9  movzx   eax, word ptr [rsi+4]
0x180008ecd  lea     r8, [rsp+58h+arg_0]
0x180008ed2  mov     r9d, 2
0x180008ed8  mov     [rsp+58h+arg_0], ax
0x180008edd  mov     edx, r9d
0x180008ee0  jmp     short loc_180008F00
0x180008ee2  cmp     byte ptr [rsi+2], 2
0x180008ee6  mov     rbx, rcx
0x180008ee9  jnz     short loc_180008F06
0x180008eeb  lea     rbx, [rcx+4]
0x180008eef  cmp     rbx, rdi
0x180008ef2  ja      short loc_180008F47
0x180008ef4  mov     edx, 4; DestinationSize
0x180008ef9  lea     r8, [rsi+4]; Source
0x180008efd  mov     r9d, edx; SourceSize
0x180008f00  call    cs:__imp_memcpy_s
0x180008f06  cmp     word ptr [rsi], 0
0x180008f0a  jnz     short loc_180008F36
0x180008f0c  lea     r15, [rbx+2]
0x180008f10  cmp     r15, rdi
0x180008f13  ja      short loc_180008F47
0x180008f15  lea     r14, [rsi+8]
0x180008f19  mov     rdx, rdi
0x180008f1c  sub     rdx, rbx; DestinationSize
0x180008f1f  mov     r8, r14; Source
0x180008f22  mov     r9d, 2; SourceSize
0x180008f28  mov     rcx, rbx; Destination
0x180008f2b  call    cs:__imp_memcpy_s
0x180008f31  mov     rbx, r15
0x180008f34  jmp     short loc_180008F3A
0x180008f36  lea     r14, [rsi+8]
0x180008f3a  movzx   r9d, word ptr [r14]; SourceSize
0x180008f3e  lea     rax, [r9+rbx]
0x180008f42  cmp     rax, rdi
0x180008f45  jbe     short loc_180008F4B
0x180008f47  xor     al, al
0x180008f49  jmp     short loc_180008F6B
0x180008f4b  mov     r8, [rsi+18h]; Source
0x180008f4f  sub     rdi, rbx
0x180008f52  mov     rdx, rdi; DestinationSize
0x180008f55  mov     rcx, rbx; Destination
0x180008f58  call    cs:__imp_memcpy_s
0x180008f5e  movzx   ecx, word ptr [r14]
0x180008f62  mov     al, 1
0x180008f64  add     rcx, rbx
0x180008f67  mov     [r12], rcx
0x180008f6b  add     rsp, 28h
0x180008f6f  pop     r15
0x180008f71  pop     r14
0x180008f73  pop     r12
0x180008f75  pop     rdi
0x180008f76  pop     rsi
0x180008f77  pop     rbx
0x180008f78  retn
```
