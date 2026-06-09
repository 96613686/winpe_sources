# ContainerMapDeleteContainer

- ea: `0x18001fca8`
- end: `0x18001fd77`
- name: `ContainerMapDeleteContainer`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001e9b8`

## callees

- `0x18000a772`
- `0x18000de80`
- `0x18001ebf4`
- `0x18001fca8`
- `0x180020204`

## pseudocode

```c
__int64 __fastcall ContainerMapDeleteContainer(__int64 a1, int a2, unsigned __int8 *a3)
{
  unsigned int v5; // eax
  void *v6; // rbx
  unsigned int v7; // edi
  unsigned __int8 v8; // di
  char *v9; // r9
  unsigned __int8 i; // cl
  __int64 v11; // rdx
  char v12; // al
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned __int8 v16; // [rsp+30h] [rbp-38h] BYREF
  char *v17; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int8 v18; // [rsp+88h] [rbp+20h] BYREF

  v17 = 0;
  v16 = 0;
  v18 = 0;
  v5 = I_ContainerMapFind(a1, a2, (unsigned int)&v16, (unsigned int)&v17, (__int64)&v18);
  v6 = v17;
  v7 = v5;
  if ( !v5 )
  {
    v8 = v16;
    v9 = &v17[86 * v16];
    if ( (v9[80] & 2) != 0 )
    {
      for ( i = 0; i < v18; ++i )
      {
        if ( i != v16 )
        {
          v11 = 86LL * i;
          v12 = v17[v11 + 80];
          if ( (v12 & 1) != 0 )
          {
            v17[v11 + 80] = v12 | 2;
            break;
          }
        }
      }
    }
    memset_0(v9, 0, 0x56u);
    v13 = 86 * (unsigned int)v18;
    *a3 = v8;
    v7 = CspWriteFile(a1, v13, "cmapfile", v14, v6, v13);
  }
  if ( v6 )
    CspFreeH(v6);
  return v7;
}

```

## disassembly

```asm
0x18001fca8  mov     r11, rsp
0x18001fcab  push    rbx
0x18001fcac  push    rsi
0x18001fcad  push    rdi
0x18001fcae  push    r14
0x18001fcb0  sub     rsp, 48h
0x18001fcb4  mov     r14, r8
0x18001fcb7  mov     qword ptr [r11-30h], 0
0x18001fcbf  lea     rax, [r11+20h]
0x18001fcc3  mov     [rsp+68h+var_38], 0
0x18001fcc8  lea     r8, [r11-38h]
0x18001fccc  mov     [r11-48h], rax
0x18001fcd0  lea     r9, [r11-30h]
0x18001fcd4  mov     byte ptr [r11+20h], 0
0x18001fcd9  mov     rsi, rcx
0x18001fcdc  call    I_ContainerMapFind
0x18001fce1  mov     rbx, [rsp+68h+var_30]
0x18001fce6  mov     edi, eax
0x18001fce8  test    eax, eax
0x18001fcea  jnz     short loc_18001FD5E
0x18001fcec  movzx   edi, [rsp+68h+var_38]
0x18001fcf1  imul    r9, rdi, 56h ; 'V'
0x18001fcf5  add     r9, rbx
0x18001fcf8  test    byte ptr [r9+50h], 2
0x18001fcfd  jz      short loc_18001FD28
0x18001fcff  xor     cl, cl
0x18001fd01  cmp     cl, [rsp+68h+arg_18]
0x18001fd08  jnb     short loc_18001FD28
0x18001fd0a  cmp     cl, dil
0x18001fd0d  jz      short loc_18001FD1E
0x18001fd0f  movzx   eax, cl
0x18001fd12  imul    rdx, rax, 56h ; 'V'
0x18001fd16  mov     al, [rdx+rbx+50h]
0x18001fd1a  test    al, 1
0x18001fd1c  jnz     short loc_18001FD22
0x18001fd1e  inc     cl
0x18001fd20  jmp     short loc_18001FD01
0x18001fd22  or      al, 2
0x18001fd24  mov     [rdx+rbx+50h], al
0x18001fd28  xor     edx, edx; Val
0x18001fd2a  mov     rcx, r9; void *
0x18001fd2d  lea     r8d, [rdx+56h]; Size
0x18001fd31  call    memset_0
0x18001fd36  movzx   eax, [rsp+68h+arg_18]
0x18001fd3e  lea     r8, aCmapfile; "cmapfile"
0x18001fd45  imul    edx, eax, 56h ; 'V'
0x18001fd48  mov     rcx, rsi
0x18001fd4b  mov     [r14], dil
0x18001fd4e  mov     [rsp+68h+var_40], edx
0x18001fd52  mov     [rsp+68h+var_48], rbx
0x18001fd57  call    CspWriteFile
0x18001fd5c  mov     edi, eax
0x18001fd5e  test    rbx, rbx
0x18001fd61  jz      short loc_18001FD6B
0x18001fd63  mov     rcx, rbx
0x18001fd66  call    CspFreeH
0x18001fd6b  mov     eax, edi
0x18001fd6d  add     rsp, 48h
0x18001fd71  pop     r14
0x18001fd73  pop     rdi
0x18001fd74  pop     rsi
0x18001fd75  pop     rbx
0x18001fd76  retn
```
