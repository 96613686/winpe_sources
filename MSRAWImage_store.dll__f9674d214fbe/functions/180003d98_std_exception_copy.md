# __std_exception_copy

- ea: `0x180003d98`
- end: `0x180003e16`
- name: `__std_exception_copy`
- size: `126`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800052d0`
- `0x18009edc8`
- `0x1800b029c`

## callees

- `0x180003d98`
- `0x180005cc7`
- `0x180005cd3`
- `0x180005cf7`
- `0x180005d0f`

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
0x180003d98  mov     [rsp+arg_0], rbx
0x180003d9d  mov     [rsp+arg_8], rbp
0x180003da2  mov     [rsp+arg_10], rsi
0x180003da7  push    rdi
0x180003da8  sub     rsp, 20h
0x180003dac  cmp     byte ptr [rcx+8], 0
0x180003db0  mov     rdi, rdx
0x180003db3  mov     rbx, rcx
0x180003db6  jz      short loc_180003DF7
0x180003db8  mov     rcx, [rcx]; Str
0x180003dbb  test    rcx, rcx
0x180003dbe  jz      short loc_180003DF7
0x180003dc0  call    strlen_0
0x180003dc5  lea     rbp, [rax+1]
0x180003dc9  mov     rcx, rbp; Size
0x180003dcc  call    malloc_0
0x180003dd1  mov     rsi, rax
0x180003dd4  mov     rcx, rax; Destination
0x180003dd7  test    rax, rax
0x180003dda  jz      short loc_180003DF0
0x180003ddc  mov     r8, [rbx]; Source
0x180003ddf  mov     rdx, rbp; SizeInBytes
0x180003de2  call    strcpy_s_0
0x180003de7  xor     ecx, ecx; Block
0x180003de9  mov     [rdi], rsi
0x180003dec  mov     byte ptr [rdi+8], 1
0x180003df0  call    free_0
0x180003df5  jmp     short loc_180003E01
0x180003df7  mov     rax, [rbx]
0x180003dfa  mov     [rdx], rax
0x180003dfd  mov     byte ptr [rdx+8], 0
0x180003e01  mov     rbx, [rsp+28h+arg_0]
0x180003e06  mov     rbp, [rsp+28h+arg_8]
0x180003e0b  mov     rsi, [rsp+28h+arg_10]
0x180003e10  add     rsp, 20h
0x180003e14  pop     rdi
0x180003e15  retn
```
