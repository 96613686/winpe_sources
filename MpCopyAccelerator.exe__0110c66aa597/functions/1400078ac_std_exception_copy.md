# __std_exception_copy

- ea: `0x1400078ac`
- end: `0x14000792a`
- name: `__std_exception_copy`
- size: `126`
- prototype: ``
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x140002d48`
- `0x140002d84`
- `0x140005840`
- `0x14000587c`
- `0x1400058c4`
- `0x14000a2f8`
- `0x1400204a8`
- `0x1400204e4`
- `0x140020544`

## callees

- `0x1400078ac`
- `0x140013080`
- `0x140013650`
- `0x1400136b0`
- `0x140025830`

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
    v5 = strlen(v4) + 1;
    v6 = (char *)malloc(v5);
    v7 = v6;
    if ( v6 )
    {
      strcpy_s(v6, v5, *(const char **)a1);
      v7 = 0;
      *(_QWORD *)a2 = v6;
      *(_BYTE *)(a2 + 8) = 1;
    }
    free(v7);
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
0x1400078ac  mov     [rsp+arg_0], rbx
0x1400078b1  mov     [rsp+arg_8], rbp
0x1400078b6  mov     [rsp+arg_10], rsi
0x1400078bb  push    rdi
0x1400078bc  sub     rsp, 20h
0x1400078c0  cmp     byte ptr [rcx+8], 0
0x1400078c4  mov     rdi, rdx
0x1400078c7  mov     rbx, rcx
0x1400078ca  jz      short loc_14000790B
0x1400078cc  mov     rcx, [rcx]; Str
0x1400078cf  test    rcx, rcx
0x1400078d2  jz      short loc_14000790B
0x1400078d4  call    strlen
0x1400078d9  lea     rbp, [rax+1]
0x1400078dd  mov     rcx, rbp; Size
0x1400078e0  call    malloc
0x1400078e5  mov     rsi, rax
0x1400078e8  mov     rcx, rax; Destination
0x1400078eb  test    rax, rax
0x1400078ee  jz      short loc_140007904
0x1400078f0  mov     r8, [rbx]; Source
0x1400078f3  mov     rdx, rbp; SizeInBytes
0x1400078f6  call    strcpy_s
0x1400078fb  xor     ecx, ecx; Block
0x1400078fd  mov     [rdi], rsi
0x140007900  mov     byte ptr [rdi+8], 1
0x140007904  call    free
0x140007909  jmp     short loc_140007915
0x14000790b  mov     rax, [rbx]
0x14000790e  mov     [rdx], rax
0x140007911  mov     byte ptr [rdx+8], 0
0x140007915  mov     rbx, [rsp+28h+arg_0]
0x14000791a  mov     rbp, [rsp+28h+arg_8]
0x14000791f  mov     rsi, [rsp+28h+arg_10]
0x140007924  add     rsp, 20h
0x140007928  pop     rdi
0x140007929  retn
```
