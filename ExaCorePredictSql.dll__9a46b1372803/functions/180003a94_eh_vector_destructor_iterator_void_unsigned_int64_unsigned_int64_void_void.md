# `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))

- ea: `0x180003a94`
- end: `0x180003afd`
- name: `??_M@YAXPEAX_K1P6AX0@Z@Z`
- size: `105`
- prototype: `void(void *, unsigned __int64, unsigned __int64, void (*)(void *))`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180001e40`
- `0x180001f80`
- `0x180004f40`
- `0x180004f60`

## callees

- `0x180003a94`
- `0x180003b00`
- `0x180004498`

## pseudocode

```c
void __fastcall `eh vector destructor iterator'(char *a1, __int64 a2, __int64 a3, void (__fastcall *a4)(char *))
{
  __int64 v5; // rbx
  char *i; // rdi

  v5 = a3;
  for ( i = &a1[a3 * a2]; v5--; a4(i) )
    i -= a2;
}

```

## disassembly

```asm
0x180003a94  mov     rax, rsp
0x180003a97  mov     [rax+20h], r9
0x180003a9b  mov     [rax+18h], r8
0x180003a9f  mov     [rax+10h], rdx
0x180003aa3  push    rbx
0x180003aa4  push    rsi
0x180003aa5  push    rdi
0x180003aa6  push    r14
0x180003aa8  sub     rsp, 38h
0x180003aac  mov     rsi, r9
0x180003aaf  mov     rbx, r8
0x180003ab2  mov     r14, rdx
0x180003ab5  mov     byte ptr [rax-38h], 0
0x180003ab9  mov     rdi, rdx
0x180003abc  imul    rdi, r8
0x180003ac0  add     rdi, rcx
0x180003ac3  mov     [rax+8], rdi
0x180003ac7  mov     rax, rbx
0x180003aca  dec     rbx
0x180003acd  mov     [rsp+58h+arg_10], rbx
0x180003ad2  test    rax, rax
0x180003ad5  jz      short loc_180003AEE
0x180003ad7  sub     rdi, r14
0x180003ada  mov     [rsp+58h+arg_0], rdi
0x180003adf  mov     rcx, rsi; Target
0x180003ae2  call    _guard_check_icall
0x180003ae7  mov     rcx, rdi
0x180003aea  call    rsi
0x180003aec  jmp     short loc_180003AC7
0x180003aee  mov     [rsp+58h+var_38], 1
0x180003af3  add     rsp, 38h
0x180003af7  pop     r14
0x180003af9  pop     rdi
0x180003afa  pop     rsi
0x180003afb  pop     rbx
0x180003afc  retn
0x180004e4c  push    rbp
0x180004e4e  sub     rsp, 20h
0x180004e52  mov     rbp, rdx
0x180004e55  cmp     byte ptr [rbp+20h], 0
0x180004e59  jnz     short loc_180004E71
0x180004e5b  mov     r9, [rbp+78h]; void (*)(void *)
0x180004e5f  mov     r8, [rbp+70h]; unsigned __int64
0x180004e63  mov     rdx, [rbp+68h]; unsigned __int64
0x180004e67  mov     rcx, [rbp+60h]; void *
0x180004e6b  call    ?__ArrayUnwind@@YAXPEAX_K1P6AX0@Z@Z
0x180004e70  nop
0x180004e71  add     rsp, 20h
0x180004e75  pop     rbp
0x180004e76  retn
```
