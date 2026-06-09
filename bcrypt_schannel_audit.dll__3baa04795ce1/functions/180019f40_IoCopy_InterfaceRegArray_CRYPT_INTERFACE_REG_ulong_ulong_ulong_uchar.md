# IoCopy_InterfaceRegArray(_CRYPT_INTERFACE_REG * *,ulong,ulong,ulong *,uchar *)

- ea: `0x180019f40`
- end: `0x18001a001`
- name: `?IoCopy_InterfaceRegArray@@YAKPEAPEAU_CRYPT_INTERFACE_REG@@KKPEAKPEAE@Z`
- size: `193`
- prototype: `unsigned int __fastcall(struct _CRYPT_INTERFACE_REG **, unsigned int, unsigned int, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180019cbc`

## callees

- `0x180019e84`
- `0x180019f40`

## pseudocode

```c
unsigned int __fastcall IoCopy_InterfaceRegArray(
        struct _CRYPT_INTERFACE_REG **a1,
        __int64 a2,
        __int64 a3,
        unsigned int *a4,
        unsigned __int8 *a5)
{
  unsigned int v6; // r15d
  unsigned __int8 *v8; // r12
  unsigned int v9; // edi
  __int64 i; // rbp
  struct _CRYPT_INTERFACE_REG *v11; // rcx
  unsigned __int8 *v12; // rsi
  unsigned int result; // eax
  unsigned int v14; // [rsp+60h] [rbp+18h] BYREF

  v14 = 0;
  v6 = a2;
  if ( !a1 || !(_DWORD)a2 )
    return 87;
  v8 = a5;
  if ( a4 )
    *a4 = 0;
  v9 = 8 * a2;
  for ( i = 0; (unsigned int)i < v6; i = (unsigned int)(i + 1) )
  {
    v11 = a1[i];
    if ( !v11 )
      return 87;
    if ( a5 )
      v12 = &a5[v9];
    else
      v12 = 0;
    result = IoCopy_InterfaceReg(v11, a2, &v14, v12);
    if ( result )
      return result;
    if ( a5 )
    {
      *(_QWORD *)v8 = v12;
      v8 += 8;
    }
    v9 += v14;
  }
  if ( a4 )
    *a4 = v9;
  return 0;
}

```

## disassembly

```asm
0x180019f40  mov     rax, rsp
0x180019f43  mov     [rax+8], rbx
0x180019f47  mov     [rax+10h], rbp
0x180019f4b  mov     [rax+18h], r8d
0x180019f4f  push    rsi
0x180019f50  push    rdi
0x180019f51  push    r12
0x180019f53  push    r13
0x180019f55  push    r15
0x180019f57  sub     rsp, 20h
0x180019f5b  mov     dword ptr [rax+18h], 0
0x180019f62  mov     rbx, r9
0x180019f65  mov     r15d, edx
0x180019f68  mov     r13, rcx
0x180019f6b  test    rcx, rcx
0x180019f6e  jz      short loc_180019FE4
0x180019f70  test    edx, edx
0x180019f72  jz      short loc_180019FE4
0x180019f74  mov     r12, [rsp+48h+arg_20]
0x180019f79  test    rbx, rbx
0x180019f7c  jz      short loc_180019F85
0x180019f7e  mov     dword ptr [r9], 0
0x180019f85  lea     edi, ds:0[rdx*8]
0x180019f8c  xor     ebp, ebp
0x180019f8e  cmp     ebp, r15d
0x180019f91  jnb     short loc_180019FD9
0x180019f93  mov     rcx, [r13+rbp*8+0]; struct _CRYPT_INTERFACE_REG *
0x180019f98  test    rcx, rcx
0x180019f9b  jz      short loc_180019FE4
0x180019f9d  cmp     [rsp+48h+arg_20], 0
0x180019fa3  jz      short loc_180019FAE
0x180019fa5  mov     esi, edi
0x180019fa7  add     rsi, [rsp+48h+arg_20]
0x180019fac  jmp     short loc_180019FB0
0x180019fae  xor     esi, esi
0x180019fb0  mov     r9, rsi; unsigned __int8 *
0x180019fb3  lea     r8, [rsp+48h+arg_10]; unsigned int *
0x180019fb8  call    ?IoCopy_InterfaceReg@@YAKPEAU_CRYPT_INTERFACE_REG@@KPEAKPEAE@Z; IoCopy_InterfaceReg(_CRYPT_INTERFACE_REG *,ulong,ulong *,uchar *)
0x180019fbd  test    eax, eax
0x180019fbf  jnz     short loc_180019FE9
0x180019fc1  cmp     [rsp+48h+arg_20], 0
0x180019fc7  jz      short loc_180019FD1
0x180019fc9  mov     [r12], rsi
0x180019fcd  add     r12, 8
0x180019fd1  add     edi, [rsp+48h+arg_10]
0x180019fd5  inc     ebp
0x180019fd7  jmp     short loc_180019F8E
0x180019fd9  test    rbx, rbx
0x180019fdc  jz      short loc_180019FE0
0x180019fde  mov     [rbx], edi
0x180019fe0  xor     eax, eax
0x180019fe2  jmp     short loc_180019FE9
0x180019fe4  mov     eax, 57h ; 'W'
0x180019fe9  mov     rbx, [rsp+48h+arg_0]
0x180019fee  mov     rbp, [rsp+48h+arg_8]
0x180019ff3  add     rsp, 20h
0x180019ff7  pop     r15
0x180019ff9  pop     r13
0x180019ffb  pop     r12
0x180019ffd  pop     rdi
0x180019ffe  pop     rsi
0x180019fff  retn
```
