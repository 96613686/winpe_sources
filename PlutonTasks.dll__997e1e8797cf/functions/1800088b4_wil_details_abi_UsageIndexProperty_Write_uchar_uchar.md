# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800088b4`
- end: `0x18000898a`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006b74`

## callees

- `0x1800088b4`
- `0x18000934c`

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
0x1800088b4  push    rbx
0x1800088b6  push    rsi
0x1800088b7  push    rdi
0x1800088b8  push    r12
0x1800088ba  push    r14
0x1800088bc  push    r15
0x1800088be  sub     rsp, 28h
0x1800088c2  mov     rsi, rcx
0x1800088c5  mov     rdi, r8
0x1800088c8  mov     rcx, [rdx]; Destination
0x1800088cb  mov     r12, rdx
0x1800088ce  cmp     byte ptr [rsi+2], 1
0x1800088d2  jnz     short loc_1800088F6
0x1800088d4  lea     rbx, [rcx+2]
0x1800088d8  cmp     rbx, r8
0x1800088db  ja      short loc_180008959
0x1800088dd  movzx   eax, word ptr [rsi+4]
0x1800088e1  lea     r8, [rsp+58h+arg_0]
0x1800088e6  mov     r9d, 2
0x1800088ec  mov     [rsp+58h+arg_0], ax
0x1800088f1  mov     edx, r9d
0x1800088f4  jmp     short loc_180008914
0x1800088f6  cmp     byte ptr [rsi+2], 2
0x1800088fa  mov     rbx, rcx
0x1800088fd  jnz     short loc_180008919
0x1800088ff  lea     rbx, [rcx+4]
0x180008903  cmp     rbx, rdi
0x180008906  ja      short loc_180008959
0x180008908  mov     edx, 4; DestinationSize
0x18000890d  lea     r8, [rsi+4]; Source
0x180008911  mov     r9d, edx; SourceSize
0x180008914  call    memcpy_s
0x180008919  cmp     word ptr [rsi], 0
0x18000891d  jnz     short loc_180008948
0x18000891f  lea     r15, [rbx+2]
0x180008923  cmp     r15, rdi
0x180008926  ja      short loc_180008959
0x180008928  lea     r14, [rsi+8]
0x18000892c  mov     rdx, rdi
0x18000892f  sub     rdx, rbx; DestinationSize
0x180008932  mov     r8, r14; Source
0x180008935  mov     r9d, 2; SourceSize
0x18000893b  mov     rcx, rbx; Destination
0x18000893e  call    memcpy_s
0x180008943  mov     rbx, r15
0x180008946  jmp     short loc_18000894C
0x180008948  lea     r14, [rsi+8]
0x18000894c  movzx   r9d, word ptr [r14]; SourceSize
0x180008950  lea     rax, [r9+rbx]
0x180008954  cmp     rax, rdi
0x180008957  jbe     short loc_18000895D
0x180008959  xor     al, al
0x18000895b  jmp     short loc_18000897C
0x18000895d  mov     r8, [rsi+18h]; Source
0x180008961  sub     rdi, rbx
0x180008964  mov     rdx, rdi; DestinationSize
0x180008967  mov     rcx, rbx; Destination
0x18000896a  call    memcpy_s
0x18000896f  movzx   ecx, word ptr [r14]
0x180008973  mov     al, 1
0x180008975  add     rcx, rbx
0x180008978  mov     [r12], rcx
0x18000897c  add     rsp, 28h
0x180008980  pop     r15
0x180008982  pop     r14
0x180008984  pop     r12
0x180008986  pop     rdi
0x180008987  pop     rsi
0x180008988  pop     rbx
0x180008989  retn
```
