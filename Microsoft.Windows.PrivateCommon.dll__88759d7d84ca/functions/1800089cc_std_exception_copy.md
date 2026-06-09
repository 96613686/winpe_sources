# __std_exception_copy

- ea: `0x1800089cc`
- end: `0x180008a4a`
- name: `__std_exception_copy`
- size: `126`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x1800010b0`
- `0x1800011b0`
- `0x1800011f0`
- `0x180001260`
- `0x1800012a0`
- `0x180003890`
- `0x180007b88`
- `0x18000a4c4`

## callees

- `0x1800089cc`
- `0x18000b5bc`
- `0x18000b604`
- `0x18000b60a`
- `0x18000b610`

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
0x1800089cc  mov     [rsp+arg_0], rbx
0x1800089d1  mov     [rsp+arg_8], rbp
0x1800089d6  mov     [rsp+arg_10], rsi
0x1800089db  push    rdi
0x1800089dc  sub     rsp, 20h
0x1800089e0  cmp     byte ptr [rcx+8], 0
0x1800089e4  mov     rdi, rdx
0x1800089e7  mov     rbx, rcx
0x1800089ea  jz      short loc_180008A2B
0x1800089ec  mov     rcx, [rcx]; Str
0x1800089ef  test    rcx, rcx
0x1800089f2  jz      short loc_180008A2B
0x1800089f4  call    strlen_0
0x1800089f9  lea     rbp, [rax+1]
0x1800089fd  mov     rcx, rbp; Size
0x180008a00  call    malloc_0
0x180008a05  mov     rsi, rax
0x180008a08  mov     rcx, rax; Destination
0x180008a0b  test    rax, rax
0x180008a0e  jz      short loc_180008A24
0x180008a10  mov     r8, [rbx]; Source
0x180008a13  mov     rdx, rbp; SizeInBytes
0x180008a16  call    strcpy_s_0
0x180008a1b  xor     ecx, ecx; Block
0x180008a1d  mov     [rdi], rsi
0x180008a20  mov     byte ptr [rdi+8], 1
0x180008a24  call    free_0
0x180008a29  jmp     short loc_180008A35
0x180008a2b  mov     rax, [rbx]
0x180008a2e  mov     [rdx], rax
0x180008a31  mov     byte ptr [rdx+8], 0
0x180008a35  mov     rbx, [rsp+28h+arg_0]
0x180008a3a  mov     rbp, [rsp+28h+arg_8]
0x180008a3f  mov     rsi, [rsp+28h+arg_10]
0x180008a44  add     rsp, 20h
0x180008a48  pop     rdi
0x180008a49  retn
```
