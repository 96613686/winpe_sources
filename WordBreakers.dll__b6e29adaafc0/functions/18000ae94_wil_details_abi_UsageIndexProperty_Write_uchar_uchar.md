# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000ae94`
- end: `0x18000af6d`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009c08`

## callees

- `0x18000ae94`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000aef4`
- `msvcrt!memcpy_s` at `0x18000af1f`
- `msvcrt!memcpy_s` at `0x18000af4c`
- `msvcrt!memcpy_s` at `0x18000aef4`
- `msvcrt!memcpy_s` at `0x18000af1f`
- `msvcrt!memcpy_s` at `0x18000af4c`

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
0x18000ae94  push    rbx
0x18000ae96  push    rsi
0x18000ae97  push    rdi
0x18000ae98  push    r12
0x18000ae9a  push    r14
0x18000ae9c  push    r15
0x18000ae9e  sub     rsp, 28h
0x18000aea2  mov     rsi, rcx
0x18000aea5  mov     rdi, r8
0x18000aea8  mov     rcx, [rdx]; Destination
0x18000aeab  mov     r12, rdx
0x18000aeae  cmp     byte ptr [rsi+2], 1
0x18000aeb2  jnz     short loc_18000AED6
0x18000aeb4  lea     rbx, [rcx+2]
0x18000aeb8  cmp     rbx, r8
0x18000aebb  ja      short loc_18000AF3B
0x18000aebd  movzx   eax, word ptr [rsi+4]
0x18000aec1  lea     r8, [rsp+58h+arg_0]
0x18000aec6  mov     r9d, 2
0x18000aecc  mov     [rsp+58h+arg_0], ax
0x18000aed1  mov     edx, r9d
0x18000aed4  jmp     short loc_18000AEF4
0x18000aed6  cmp     byte ptr [rsi+2], 2
0x18000aeda  mov     rbx, rcx
0x18000aedd  jnz     short loc_18000AEFA
0x18000aedf  lea     rbx, [rcx+4]
0x18000aee3  cmp     rbx, rdi
0x18000aee6  ja      short loc_18000AF3B
0x18000aee8  mov     edx, 4; DestinationSize
0x18000aeed  lea     r8, [rsi+4]; Source
0x18000aef1  mov     r9d, edx; SourceSize
0x18000aef4  call    cs:__imp_memcpy_s
0x18000aefa  cmp     word ptr [rsi], 0
0x18000aefe  jnz     short loc_18000AF2A
0x18000af00  lea     r15, [rbx+2]
0x18000af04  cmp     r15, rdi
0x18000af07  ja      short loc_18000AF3B
0x18000af09  lea     r14, [rsi+8]
0x18000af0d  mov     rdx, rdi
0x18000af10  sub     rdx, rbx; DestinationSize
0x18000af13  mov     r8, r14; Source
0x18000af16  mov     r9d, 2; SourceSize
0x18000af1c  mov     rcx, rbx; Destination
0x18000af1f  call    cs:__imp_memcpy_s
0x18000af25  mov     rbx, r15
0x18000af28  jmp     short loc_18000AF2E
0x18000af2a  lea     r14, [rsi+8]
0x18000af2e  movzx   r9d, word ptr [r14]; SourceSize
0x18000af32  lea     rax, [r9+rbx]
0x18000af36  cmp     rax, rdi
0x18000af39  jbe     short loc_18000AF3F
0x18000af3b  xor     al, al
0x18000af3d  jmp     short loc_18000AF5F
0x18000af3f  mov     r8, [rsi+18h]; Source
0x18000af43  sub     rdi, rbx
0x18000af46  mov     rdx, rdi; DestinationSize
0x18000af49  mov     rcx, rbx; Destination
0x18000af4c  call    cs:__imp_memcpy_s
0x18000af52  movzx   ecx, word ptr [r14]
0x18000af56  mov     al, 1
0x18000af58  add     rcx, rbx
0x18000af5b  mov     [r12], rcx
0x18000af5f  add     rsp, 28h
0x18000af63  pop     r15
0x18000af65  pop     r14
0x18000af67  pop     r12
0x18000af69  pop     rdi
0x18000af6a  pop     rsi
0x18000af6b  pop     rbx
0x18000af6c  retn
```
