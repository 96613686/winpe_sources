# Dns_StringCopyAllocate_New

- ea: `0x180013544`
- end: `0x1800135e6`
- name: `Dns_StringCopyAllocate_New`
- size: `162`
- prototype: `void *__fastcall(const CHAR *, int, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ea2c`
- `0x18001399c`

## callees

- `0x180013538`
- `0x180013544`
- `0x1800135ec`
- `0x180013bd4`
- `0x180013c44`

## pseudocode

```c
void *__fastcall Dns_StringCopyAllocate_New(const CHAR *a1, int a2, int a3, int a4)
{
  __int64 v6; // rbx
  unsigned int BufferLengthForStringCopy_New; // eax
  void *v8; // rax
  void *v9; // rdi

  LODWORD(v6) = a2;
  if ( !a1 )
    return 0;
  if ( !a2 )
  {
    v6 = -1;
    if ( a3 == 1 )
    {
      do
        ++v6;
      while ( *(_WORD *)&a1[2 * v6] );
    }
    else
    {
      do
        ++v6;
      while ( a1[v6] );
    }
  }
  BufferLengthForStringCopy_New = Dns_GetBufferLengthForStringCopy_New(a1, v6);
  if ( !BufferLengthForStringCopy_New )
    return 0;
  v8 = (void *)Rpc_AllocZero(BufferLengthForStringCopy_New);
  v9 = v8;
  if ( !v8 )
    return 0;
  if ( !(unsigned int)Dns_StringCopyU(v8, a3, a4) )
  {
    Rpc_Free(v9);
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x180013544  push    rbx
0x180013546  push    rbp
0x180013547  push    rsi
0x180013548  push    rdi
0x180013549  push    r14
0x18001354b  push    r15
0x18001354d  sub     rsp, 38h
0x180013551  xor     r15d, r15d
0x180013554  mov     r14d, r9d
0x180013557  mov     [rsp+68h+arg_0], r15d
0x18001355c  mov     ebp, r8d
0x18001355f  mov     ebx, edx
0x180013561  mov     rsi, rcx
0x180013564  test    rcx, rcx
0x180013567  jz      short loc_1800135D2
0x180013569  test    edx, edx
0x18001356b  jnz     short loc_18001358C
0x18001356d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180013571  cmp     r8d, 1
0x180013575  jnz     short loc_180013583
0x180013577  inc     rbx
0x18001357a  cmp     [rcx+rbx*2], r15w
0x18001357f  jnz     short loc_180013577
0x180013581  jmp     short loc_18001358C
0x180013583  inc     rbx
0x180013586  cmp     [rcx+rbx], r15b
0x18001358a  jnz     short loc_180013583
0x18001358c  mov     edx, ebx
0x18001358e  call    Dns_GetBufferLengthForStringCopy_New
0x180013593  mov     [rsp+68h+arg_0], eax
0x180013597  test    eax, eax
0x180013599  jz      short loc_1800135D2
0x18001359b  mov     ecx, eax
0x18001359d  call    Rpc_AllocZero
0x1800135a2  mov     rdi, rax
0x1800135a5  test    rax, rax
0x1800135a8  jz      short loc_1800135D2
0x1800135aa  mov     [rsp+68h+var_40], r14d; int
0x1800135af  lea     rdx, [rsp+68h+arg_0]
0x1800135b4  mov     r9d, ebx
0x1800135b7  mov     [rsp+68h+var_48], ebp; int
0x1800135bb  mov     r8, rsi
0x1800135be  mov     rcx, rax; void *
0x1800135c1  call    Dns_StringCopyU
0x1800135c6  test    eax, eax
0x1800135c8  jnz     short loc_1800135E1
0x1800135ca  mov     rcx, rdi; lpMem
0x1800135cd  call    Rpc_Free
0x1800135d2  xor     eax, eax
0x1800135d4  add     rsp, 38h
0x1800135d8  pop     r15
0x1800135da  pop     r14
0x1800135dc  pop     rdi
0x1800135dd  pop     rsi
0x1800135de  pop     rbp
0x1800135df  pop     rbx
0x1800135e0  retn
0x1800135e1  mov     rax, rdi
0x1800135e4  jmp     short loc_1800135D4
```
