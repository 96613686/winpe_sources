# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000e8b4`
- end: `0x18000e98d`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d468`

## callees

- `0x18000e8b4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000e914`
- `msvcrt!memcpy_s` at `0x18000e93f`
- `msvcrt!memcpy_s` at `0x18000e96c`
- `msvcrt!memcpy_s` at `0x18000e914`
- `msvcrt!memcpy_s` at `0x18000e93f`
- `msvcrt!memcpy_s` at `0x18000e96c`

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
0x18000e8b4  push    rbx
0x18000e8b6  push    rsi
0x18000e8b7  push    rdi
0x18000e8b8  push    r12
0x18000e8ba  push    r14
0x18000e8bc  push    r15
0x18000e8be  sub     rsp, 28h
0x18000e8c2  mov     rsi, rcx
0x18000e8c5  mov     rdi, r8
0x18000e8c8  mov     rcx, [rdx]; Destination
0x18000e8cb  mov     r12, rdx
0x18000e8ce  cmp     byte ptr [rsi+2], 1
0x18000e8d2  jnz     short loc_18000E8F6
0x18000e8d4  lea     rbx, [rcx+2]
0x18000e8d8  cmp     rbx, r8
0x18000e8db  ja      short loc_18000E95B
0x18000e8dd  movzx   eax, word ptr [rsi+4]
0x18000e8e1  lea     r8, [rsp+58h+arg_0]
0x18000e8e6  mov     r9d, 2
0x18000e8ec  mov     [rsp+58h+arg_0], ax
0x18000e8f1  mov     edx, r9d
0x18000e8f4  jmp     short loc_18000E914
0x18000e8f6  cmp     byte ptr [rsi+2], 2
0x18000e8fa  mov     rbx, rcx
0x18000e8fd  jnz     short loc_18000E91A
0x18000e8ff  lea     rbx, [rcx+4]
0x18000e903  cmp     rbx, rdi
0x18000e906  ja      short loc_18000E95B
0x18000e908  mov     edx, 4; DestinationSize
0x18000e90d  lea     r8, [rsi+4]; Source
0x18000e911  mov     r9d, edx; SourceSize
0x18000e914  call    cs:__imp_memcpy_s
0x18000e91a  cmp     word ptr [rsi], 0
0x18000e91e  jnz     short loc_18000E94A
0x18000e920  lea     r15, [rbx+2]
0x18000e924  cmp     r15, rdi
0x18000e927  ja      short loc_18000E95B
0x18000e929  lea     r14, [rsi+8]
0x18000e92d  mov     rdx, rdi
0x18000e930  sub     rdx, rbx; DestinationSize
0x18000e933  mov     r8, r14; Source
0x18000e936  mov     r9d, 2; SourceSize
0x18000e93c  mov     rcx, rbx; Destination
0x18000e93f  call    cs:__imp_memcpy_s
0x18000e945  mov     rbx, r15
0x18000e948  jmp     short loc_18000E94E
0x18000e94a  lea     r14, [rsi+8]
0x18000e94e  movzx   r9d, word ptr [r14]; SourceSize
0x18000e952  lea     rax, [r9+rbx]
0x18000e956  cmp     rax, rdi
0x18000e959  jbe     short loc_18000E95F
0x18000e95b  xor     al, al
0x18000e95d  jmp     short loc_18000E97F
0x18000e95f  mov     r8, [rsi+18h]; Source
0x18000e963  sub     rdi, rbx
0x18000e966  mov     rdx, rdi; DestinationSize
0x18000e969  mov     rcx, rbx; Destination
0x18000e96c  call    cs:__imp_memcpy_s
0x18000e972  movzx   ecx, word ptr [r14]
0x18000e976  mov     al, 1
0x18000e978  add     rcx, rbx
0x18000e97b  mov     [r12], rcx
0x18000e97f  add     rsp, 28h
0x18000e983  pop     r15
0x18000e985  pop     r14
0x18000e987  pop     r12
0x18000e989  pop     rdi
0x18000e98a  pop     rsi
0x18000e98b  pop     rbx
0x18000e98c  retn
```
