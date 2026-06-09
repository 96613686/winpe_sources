# sub_18000CCAC

- ea: `0x18000ccac`
- end: `0x18000cd92`
- name: `sub_18000CCAC`
- size: `230`
- prototype: `char __fastcall(__int16 *, const void **, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b824`
- `0x18000c22c`
- `0x18000c3d8`
- `0x18000d1d8`
- `0x18000dee4`

## callees

- `0x1800093f8`
- `0x18000ccac`

## pseudocode

```c
char __fastcall sub_18000CCAC(__int16 *a1, const void **a2, unsigned __int64 a3)
{
  char *v5; // r8
  char *v7; // rbx
  __int16 v8; // ax
  char *v9; // rcx
  char result; // al
  unsigned __int16 v11; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)a1 + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( (unsigned __int64)(v5 + 2) > a3 )
      return 0;
    *((_QWORD *)a1 + 2) = v5;
    v11 = 0;
    sub_1800093F8(&v11, 2u, v5, 2u);
    *((_DWORD *)a1 + 1) = v11;
  }
  else
  {
    v7 = (char *)*a2;
    if ( *((_BYTE *)a1 + 2) == 2 )
    {
      v7 = v5 + 4;
      if ( (unsigned __int64)(v5 + 4) > a3 )
        return 0;
      *((_QWORD *)a1 + 2) = v5;
      sub_1800093F8(a1 + 2, 4u, v5, 4u);
    }
  }
  v8 = *a1;
  a1[4] = *a1;
  if ( v8 )
    goto LABEL_10;
  if ( (unsigned __int64)(v7 + 2) > a3 )
    return 0;
  sub_1800093F8(a1 + 4, 2u, v7, 2u);
  v7 += 2;
LABEL_10:
  v9 = &v7[(unsigned __int16)a1[4]];
  if ( (unsigned __int64)v9 > a3 )
    return 0;
  *((_QWORD *)a1 + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x18000ccac  mov     rax, rsp
0x18000ccaf  mov     [rax+10h], rbx
0x18000ccb3  mov     [rax+18h], rbp
0x18000ccb7  push    rsi
0x18000ccb8  push    rdi
0x18000ccb9  push    r12
0x18000ccbb  push    r14
0x18000ccbd  push    r15
0x18000ccbf  sub     rsp, 20h
0x18000ccc3  xor     r15d, r15d
0x18000ccc6  mov     rsi, r8
0x18000ccc9  cmp     byte ptr [rcx+2], 1
0x18000cccd  mov     r12, rdx
0x18000ccd0  mov     r8, [rdx]
0x18000ccd3  mov     rdi, rcx
0x18000ccd6  jnz     short loc_18000CD0A
0x18000ccd8  lea     rbx, [r8+2]
0x18000ccdc  cmp     rbx, rsi
0x18000ccdf  ja      loc_18000CD6D
0x18000cce5  lea     ebp, [r15+2]
0x18000cce9  mov     [rcx+10h], r8
0x18000cced  mov     r9d, ebp
0x18000ccf0  mov     [rax+8], r15w
0x18000ccf5  mov     edx, ebp
0x18000ccf7  lea     rcx, [rax+8]
0x18000ccfb  call    sub_1800093F8
0x18000cd00  movzx   eax, [rsp+48h+arg_0]
0x18000cd05  mov     [rdi+4], eax
0x18000cd08  jmp     short loc_18000CD34
0x18000cd0a  mov     ebp, 2
0x18000cd0f  mov     rbx, r8
0x18000cd12  cmp     [rcx+2], bpl
0x18000cd16  jnz     short loc_18000CD34
0x18000cd18  lea     rbx, [r8+4]
0x18000cd1c  cmp     rbx, rsi
0x18000cd1f  ja      short loc_18000CD6D
0x18000cd21  lea     edx, [rbp+2]
0x18000cd24  mov     [rcx+10h], r8
0x18000cd28  mov     r9d, edx
0x18000cd2b  add     rcx, 4
0x18000cd2f  call    sub_1800093F8
0x18000cd34  movzx   eax, word ptr [rdi]
0x18000cd37  lea     r14, [rdi+8]
0x18000cd3b  mov     [r14], ax
0x18000cd3f  test    ax, ax
0x18000cd42  jnz     short loc_18000CD61
0x18000cd44  lea     r15, [rbx+2]
0x18000cd48  cmp     r15, rsi
0x18000cd4b  ja      short loc_18000CD6D
0x18000cd4d  mov     r9, rbp
0x18000cd50  mov     r8, rbx
0x18000cd53  mov     rdx, rbp
0x18000cd56  mov     rcx, r14
0x18000cd59  call    sub_1800093F8
0x18000cd5e  mov     rbx, r15
0x18000cd61  movzx   ecx, word ptr [r14]
0x18000cd65  add     rcx, rbx
0x18000cd68  cmp     rcx, rsi
0x18000cd6b  jbe     short loc_18000CD71
0x18000cd6d  xor     al, al
0x18000cd6f  jmp     short loc_18000CD7B
0x18000cd71  mov     [rdi+18h], rbx
0x18000cd75  mov     al, 1
0x18000cd77  mov     [r12], rcx
0x18000cd7b  mov     rbx, [rsp+48h+arg_8]
0x18000cd80  mov     rbp, [rsp+48h+arg_10]
0x18000cd85  add     rsp, 20h
0x18000cd89  pop     r15
0x18000cd8b  pop     r14
0x18000cd8d  pop     r12
0x18000cd8f  pop     rdi
0x18000cd90  pop     rsi
0x18000cd91  retn
```
