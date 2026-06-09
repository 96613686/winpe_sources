# __std_exception_copy

- ea: `0x180036c58`
- end: `0x180036cd6`
- name: `__std_exception_copy`
- size: `126`
- prototype: ``
- caller_count: `21`
- callee_count: `5`
- tags: ``

## callers

- `0x180002990`
- `0x180004190`
- `0x180004200`
- `0x180004240`
- `0x1800042b0`
- `0x180004310`
- `0x180012440`
- `0x180013000`
- `0x180015460`
- `0x1800156d0`
- `0x180015730`
- `0x180015780`
- `0x18002be50`
- `0x18002c090`
- `0x18002df40`
- `0x1800321e4`
- `0x180032238`
- `0x180032274`
- `0x1800322bc`
- `0x1800322f8`
- `0x180033898`

## callees

- `0x1800321d2`
- `0x1800321d8`
- `0x180036c58`
- `0x180039715`
- `0x18003979f`

## pseudocode

```c
void __fastcall _std_exception_copy(__int64 a1, __int64 a2)
{
  const char *v4; // rcx
  size_t v5; // rbp
  char *v6; // rsi
  char *v7; // rcx

  if ( *(_BYTE *)(a1 + 8) && (v4 = *(const char **)a1) != 0 )
  {
    v5 = strlen_0(v4) + 1;
    v6 = (char *)malloc_0(v5);
    v7 = v6;
    if ( v6 )
    {
      strcpy_s_0(v6, v5, *(const char **)a1);
      v7 = 0;
      *(_QWORD *)a2 = v6;
      *(_BYTE *)(a2 + 8) = 1;
    }
    free_0(v7);
  }
  else
  {
    *(_QWORD *)a2 = *(_QWORD *)a1;
    *(_BYTE *)(a2 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180036c58  mov     [rsp+arg_0], rbx
0x180036c5d  mov     [rsp+arg_8], rbp
0x180036c62  mov     [rsp+arg_10], rsi
0x180036c67  push    rdi
0x180036c68  sub     rsp, 20h
0x180036c6c  cmp     byte ptr [rcx+8], 0
0x180036c70  mov     rdi, rdx
0x180036c73  mov     rbx, rcx
0x180036c76  jz      short loc_180036CB7
0x180036c78  mov     rcx, [rcx]; Str
0x180036c7b  test    rcx, rcx
0x180036c7e  jz      short loc_180036CB7
0x180036c80  call    strlen_0
0x180036c85  lea     rbp, [rax+1]
0x180036c89  mov     rcx, rbp; Size
0x180036c8c  call    malloc_0
0x180036c91  mov     rsi, rax
0x180036c94  mov     rcx, rax; Destination
0x180036c97  test    rax, rax
0x180036c9a  jz      short loc_180036CB0
0x180036c9c  mov     r8, [rbx]; Source
0x180036c9f  mov     rdx, rbp; SizeInBytes
0x180036ca2  call    strcpy_s_0
0x180036ca7  xor     ecx, ecx; Block
0x180036ca9  mov     [rdi], rsi
0x180036cac  mov     byte ptr [rdi+8], 1
0x180036cb0  call    free_0
0x180036cb5  jmp     short loc_180036CC1
0x180036cb7  mov     rax, [rbx]
0x180036cba  mov     [rdx], rax
0x180036cbd  mov     byte ptr [rdx+8], 0
0x180036cc1  mov     rbx, [rsp+28h+arg_0]
0x180036cc6  mov     rbp, [rsp+28h+arg_8]
0x180036ccb  mov     rsi, [rsp+28h+arg_10]
0x180036cd0  add     rsp, 20h
0x180036cd4  pop     rdi
0x180036cd5  retn
```
