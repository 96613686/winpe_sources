# __std_exception_copy

- ea: `0x14001da20`
- end: `0x14001daad`
- name: `__std_exception_copy`
- size: `141`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `12`
- callee_count: `4`
- tags: ``

## callers

- `0x1400211b4`
- `0x1400256f4`
- `0x140025730`
- `0x14002578c`
- `0x14003cbcc`
- `0x14003cc20`
- `0x14003cc5c`
- `0x14003ccb0`
- `0x14003ccec`
- `0x14003cd40`
- `0x1400a1d04`
- `0x1400a1d40`

## callees

- `0x140016470`
- `0x14001da20`
- `0x140022c30`
- `0x140022dd8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall _std_exception_copy(__int64 a1, __int64 a2)
{
  __int64 v4; // rdi
  char *v5; // rax
  char *v6; // rbx

  if ( *(_BYTE *)(a1 + 8) && *(_QWORD *)a1 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_BYTE *)(*(_QWORD *)a1 + v4) );
    v5 = (char *)j__malloc_base(v4 + 1);
    v6 = v5;
    if ( v5 )
    {
      strcpy_s(v5, v4 + 1, *(const char **)a1);
      *(_BYTE *)(a2 + 8) = 1;
      *(_QWORD *)a2 = v6;
      v6 = 0;
    }
    free(v6);
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
0x14001da20  mov     [rsp+arg_0], rbx
0x14001da25  mov     [rsp+arg_8], rsi
0x14001da2a  mov     [rsp+arg_10], rdi
0x14001da2f  push    r14
0x14001da31  sub     rsp, 20h
0x14001da35  cmp     byte ptr [rcx+8], 0
0x14001da39  mov     r14, rdx
0x14001da3c  mov     rsi, rcx
0x14001da3f  jz      short loc_14001DA8D
0x14001da41  mov     rax, [rcx]
0x14001da44  test    rax, rax
0x14001da47  jz      short loc_14001DA8D
0x14001da49  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14001da4d  inc     rdi
0x14001da50  cmp     byte ptr [rax+rdi], 0
0x14001da54  jnz     short loc_14001DA4D
0x14001da56  lea     rcx, [rdi+1]; Size
0x14001da5a  call    j__malloc_base
0x14001da5f  mov     rbx, rax
0x14001da62  test    rax, rax
0x14001da65  jz      short loc_14001DA83
0x14001da67  mov     r8, [rsi]; Src
0x14001da6a  lea     rdx, [rdi+1]; Size
0x14001da6e  mov     rcx, rax; Dst
0x14001da71  call    strcpy_s
0x14001da76  mov     rax, rbx
0x14001da79  mov     byte ptr [r14+8], 1
0x14001da7e  mov     [r14], rax
0x14001da81  xor     ebx, ebx
0x14001da83  mov     rcx, rbx; Block
0x14001da86  call    free
0x14001da8b  jmp     short loc_14001DA97
0x14001da8d  mov     rax, [rcx]
0x14001da90  mov     [rdx], rax
0x14001da93  mov     byte ptr [rdx+8], 0
0x14001da97  mov     rbx, [rsp+28h+arg_0]
0x14001da9c  mov     rsi, [rsp+28h+arg_8]
0x14001daa1  mov     rdi, [rsp+28h+arg_10]
0x14001daa6  add     rsp, 20h
0x14001daaa  pop     r14
0x14001daac  retn
```
