# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000af6c`
- end: `0x18000b045`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008b50`

## callees

- `0x18000af6c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000afcc`
- `msvcrt!memcpy_s` at `0x18000aff7`
- `msvcrt!memcpy_s` at `0x18000b024`
- `msvcrt!memcpy_s` at `0x18000afcc`
- `msvcrt!memcpy_s` at `0x18000aff7`
- `msvcrt!memcpy_s` at `0x18000b024`

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
0x18000af6c  push    rbx
0x18000af6e  push    rsi
0x18000af6f  push    rdi
0x18000af70  push    r12
0x18000af72  push    r14
0x18000af74  push    r15
0x18000af76  sub     rsp, 28h
0x18000af7a  mov     rsi, rcx
0x18000af7d  mov     rdi, r8
0x18000af80  mov     rcx, [rdx]; Destination
0x18000af83  mov     r12, rdx
0x18000af86  cmp     byte ptr [rsi+2], 1
0x18000af8a  jnz     short loc_18000AFAE
0x18000af8c  lea     rbx, [rcx+2]
0x18000af90  cmp     rbx, r8
0x18000af93  ja      short loc_18000B013
0x18000af95  movzx   eax, word ptr [rsi+4]
0x18000af99  lea     r8, [rsp+58h+arg_0]
0x18000af9e  mov     r9d, 2
0x18000afa4  mov     [rsp+58h+arg_0], ax
0x18000afa9  mov     edx, r9d
0x18000afac  jmp     short loc_18000AFCC
0x18000afae  cmp     byte ptr [rsi+2], 2
0x18000afb2  mov     rbx, rcx
0x18000afb5  jnz     short loc_18000AFD2
0x18000afb7  lea     rbx, [rcx+4]
0x18000afbb  cmp     rbx, rdi
0x18000afbe  ja      short loc_18000B013
0x18000afc0  mov     edx, 4; DestinationSize
0x18000afc5  lea     r8, [rsi+4]; Source
0x18000afc9  mov     r9d, edx; SourceSize
0x18000afcc  call    cs:__imp_memcpy_s
0x18000afd2  cmp     word ptr [rsi], 0
0x18000afd6  jnz     short loc_18000B002
0x18000afd8  lea     r15, [rbx+2]
0x18000afdc  cmp     r15, rdi
0x18000afdf  ja      short loc_18000B013
0x18000afe1  lea     r14, [rsi+8]
0x18000afe5  mov     rdx, rdi
0x18000afe8  sub     rdx, rbx; DestinationSize
0x18000afeb  mov     r8, r14; Source
0x18000afee  mov     r9d, 2; SourceSize
0x18000aff4  mov     rcx, rbx; Destination
0x18000aff7  call    cs:__imp_memcpy_s
0x18000affd  mov     rbx, r15
0x18000b000  jmp     short loc_18000B006
0x18000b002  lea     r14, [rsi+8]
0x18000b006  movzx   r9d, word ptr [r14]; SourceSize
0x18000b00a  lea     rax, [r9+rbx]
0x18000b00e  cmp     rax, rdi
0x18000b011  jbe     short loc_18000B017
0x18000b013  xor     al, al
0x18000b015  jmp     short loc_18000B037
0x18000b017  mov     r8, [rsi+18h]; Source
0x18000b01b  sub     rdi, rbx
0x18000b01e  mov     rdx, rdi; DestinationSize
0x18000b021  mov     rcx, rbx; Destination
0x18000b024  call    cs:__imp_memcpy_s
0x18000b02a  movzx   ecx, word ptr [r14]
0x18000b02e  mov     al, 1
0x18000b030  add     rcx, rbx
0x18000b033  mov     [r12], rcx
0x18000b037  add     rsp, 28h
0x18000b03b  pop     r15
0x18000b03d  pop     r14
0x18000b03f  pop     r12
0x18000b041  pop     rdi
0x18000b042  pop     rsi
0x18000b043  pop     rbx
0x18000b044  retn
```
