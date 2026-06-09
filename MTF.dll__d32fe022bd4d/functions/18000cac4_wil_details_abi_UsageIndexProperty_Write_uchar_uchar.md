# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000cac4`
- end: `0x18000cb9d`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b594`

## callees

- `0x18000cac4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000cb24`
- `msvcrt!memcpy_s` at `0x18000cb4f`
- `msvcrt!memcpy_s` at `0x18000cb7c`
- `msvcrt!memcpy_s` at `0x18000cb24`
- `msvcrt!memcpy_s` at `0x18000cb4f`
- `msvcrt!memcpy_s` at `0x18000cb7c`

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
0x18000cac4  push    rbx
0x18000cac6  push    rsi
0x18000cac7  push    rdi
0x18000cac8  push    r12
0x18000caca  push    r14
0x18000cacc  push    r15
0x18000cace  sub     rsp, 28h
0x18000cad2  mov     rsi, rcx
0x18000cad5  mov     rdi, r8
0x18000cad8  mov     rcx, [rdx]; Destination
0x18000cadb  mov     r12, rdx
0x18000cade  cmp     byte ptr [rsi+2], 1
0x18000cae2  jnz     short loc_18000CB06
0x18000cae4  lea     rbx, [rcx+2]
0x18000cae8  cmp     rbx, r8
0x18000caeb  ja      short loc_18000CB6B
0x18000caed  movzx   eax, word ptr [rsi+4]
0x18000caf1  lea     r8, [rsp+58h+arg_0]
0x18000caf6  mov     r9d, 2
0x18000cafc  mov     [rsp+58h+arg_0], ax
0x18000cb01  mov     edx, r9d
0x18000cb04  jmp     short loc_18000CB24
0x18000cb06  cmp     byte ptr [rsi+2], 2
0x18000cb0a  mov     rbx, rcx
0x18000cb0d  jnz     short loc_18000CB2A
0x18000cb0f  lea     rbx, [rcx+4]
0x18000cb13  cmp     rbx, rdi
0x18000cb16  ja      short loc_18000CB6B
0x18000cb18  mov     edx, 4; DestinationSize
0x18000cb1d  lea     r8, [rsi+4]; Source
0x18000cb21  mov     r9d, edx; SourceSize
0x18000cb24  call    cs:__imp_memcpy_s
0x18000cb2a  cmp     word ptr [rsi], 0
0x18000cb2e  jnz     short loc_18000CB5A
0x18000cb30  lea     r15, [rbx+2]
0x18000cb34  cmp     r15, rdi
0x18000cb37  ja      short loc_18000CB6B
0x18000cb39  lea     r14, [rsi+8]
0x18000cb3d  mov     rdx, rdi
0x18000cb40  sub     rdx, rbx; DestinationSize
0x18000cb43  mov     r8, r14; Source
0x18000cb46  mov     r9d, 2; SourceSize
0x18000cb4c  mov     rcx, rbx; Destination
0x18000cb4f  call    cs:__imp_memcpy_s
0x18000cb55  mov     rbx, r15
0x18000cb58  jmp     short loc_18000CB5E
0x18000cb5a  lea     r14, [rsi+8]
0x18000cb5e  movzx   r9d, word ptr [r14]; SourceSize
0x18000cb62  lea     rax, [r9+rbx]
0x18000cb66  cmp     rax, rdi
0x18000cb69  jbe     short loc_18000CB6F
0x18000cb6b  xor     al, al
0x18000cb6d  jmp     short loc_18000CB8F
0x18000cb6f  mov     r8, [rsi+18h]; Source
0x18000cb73  sub     rdi, rbx
0x18000cb76  mov     rdx, rdi; DestinationSize
0x18000cb79  mov     rcx, rbx; Destination
0x18000cb7c  call    cs:__imp_memcpy_s
0x18000cb82  movzx   ecx, word ptr [r14]
0x18000cb86  mov     al, 1
0x18000cb88  add     rcx, rbx
0x18000cb8b  mov     [r12], rcx
0x18000cb8f  add     rsp, 28h
0x18000cb93  pop     r15
0x18000cb95  pop     r14
0x18000cb97  pop     r12
0x18000cb99  pop     rdi
0x18000cb9a  pop     rsi
0x18000cb9b  pop     rbx
0x18000cb9c  retn
```
