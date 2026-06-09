# __std_exception_copy

- ea: `0x180019b34`
- end: `0x180019bb2`
- name: `__std_exception_copy`
- size: `126`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `15`
- callee_count: `5`
- tags: ``

## callers

- `0x180002570`
- `0x180003860`
- `0x1800038d0`
- `0x180003910`
- `0x180003980`
- `0x1800039e0`
- `0x180013c70`
- `0x1800162e0`
- `0x180016334`
- `0x180016370`
- `0x1800163b8`
- `0x180016c04`
- `0x180016ce8`
- `0x180016d38`
- `0x180017368`

## callees

- `0x180019b34`
- `0x18001c57f`
- `0x18001c585`
- `0x18001c58b`
- `0x18001c5d9`

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
0x180019b34  mov     [rsp+arg_0], rbx
0x180019b39  mov     [rsp+arg_8], rbp
0x180019b3e  mov     [rsp+arg_10], rsi
0x180019b43  push    rdi
0x180019b44  sub     rsp, 20h
0x180019b48  cmp     byte ptr [rcx+8], 0
0x180019b4c  mov     rdi, rdx
0x180019b4f  mov     rbx, rcx
0x180019b52  jz      short loc_180019B93
0x180019b54  mov     rcx, [rcx]; Str
0x180019b57  test    rcx, rcx
0x180019b5a  jz      short loc_180019B93
0x180019b5c  call    strlen_0
0x180019b61  lea     rbp, [rax+1]
0x180019b65  mov     rcx, rbp; Size
0x180019b68  call    malloc_0
0x180019b6d  mov     rsi, rax
0x180019b70  mov     rcx, rax; Destination
0x180019b73  test    rax, rax
0x180019b76  jz      short loc_180019B8C
0x180019b78  mov     r8, [rbx]; Source
0x180019b7b  mov     rdx, rbp; SizeInBytes
0x180019b7e  call    strcpy_s_0
0x180019b83  xor     ecx, ecx; Block
0x180019b85  mov     [rdi], rsi
0x180019b88  mov     byte ptr [rdi+8], 1
0x180019b8c  call    free_0
0x180019b91  jmp     short loc_180019B9D
0x180019b93  mov     rax, [rbx]
0x180019b96  mov     [rdx], rax
0x180019b99  mov     byte ptr [rdx+8], 0
0x180019b9d  mov     rbx, [rsp+28h+arg_0]
0x180019ba2  mov     rbp, [rsp+28h+arg_8]
0x180019ba7  mov     rsi, [rsp+28h+arg_10]
0x180019bac  add     rsp, 20h
0x180019bb0  pop     rdi
0x180019bb1  retn
```
