# std::vector<ushort *,std::allocator<ushort *>>::push_back(ushort * const &)

- ea: `0x180006de0`
- end: `0x180006f13`
- name: `?push_back@?$vector@PEAGV?$allocator@PEAG@std@@@std@@QEAAXAEBQEAG@Z`
- size: `307`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005ee4`
- `0x180006830`

## callees

- `0x180006d14`
- `0x180006db8`
- `0x180006de0`

## pseudocode

```c
__int64 __fastcall std::vector<unsigned short *>::push_back(__int64 *a1, __int64 *a2)
{
  unsigned __int64 v4; // rcx
  bool v5; // al
  __int64 v6; // r8
  __int64 v7; // rsi
  __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // r8
  __int64 result; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // r8
  unsigned __int64 v16; // rdx

  v4 = a1[1];
  v5 = (unsigned __int64)a2 < v4 && *a1 <= (unsigned __int64)a2;
  v6 = a1[2];
  if ( v5 )
  {
    v7 = *a1;
    if ( v4 == v6 && !((__int64)(v6 - v4) >> 3) )
    {
      v8 = (__int64)(v4 - v7) >> 3;
      if ( v8 == 0x1FFFFFFFFFFFFFFFLL )
        std::vector<unsigned short *>::_Xlen();
      v9 = v8 + 1;
      v10 = 0;
      v11 = (v6 - v7) >> 3;
      if ( 0x1FFFFFFFFFFFFFFFLL - (v11 >> 1) >= v11 )
        v10 = v11 + (v11 >> 1);
      if ( v10 < v9 )
        v10 = v9;
      std::vector<unsigned short *>::_Reallocate(a1, v10);
    }
    result = *(_QWORD *)(*a1 + 8 * (((__int64)a2 - v7) >> 3));
  }
  else
  {
    if ( v4 == v6 && !((__int64)(v6 - v4) >> 3) )
    {
      v13 = (__int64)(v4 - *a1) >> 3;
      if ( v13 == 0x1FFFFFFFFFFFFFFFLL )
        std::vector<unsigned short *>::_Xlen();
      v14 = v13 + 1;
      v15 = (v6 - *a1) >> 3;
      v16 = 0;
      if ( 0x1FFFFFFFFFFFFFFFLL - (v15 >> 1) >= v15 )
        v16 = v15 + (v15 >> 1);
      if ( v16 < v14 )
        v16 = v14;
      std::vector<unsigned short *>::_Reallocate(a1, v16);
    }
    result = *a2;
  }
  *(_QWORD *)a1[1] = result;
  a1[1] += 8;
  return result;
}

```

## disassembly

```asm
0x180006de0  mov     [rsp+arg_0], rbx
0x180006de5  mov     [rsp+arg_8], rsi
0x180006dea  push    rdi
0x180006deb  sub     rsp, 20h
0x180006def  mov     rbx, rcx
0x180006df2  mov     rdi, rdx
0x180006df5  mov     rcx, [rcx+8]
0x180006df9  cmp     rdx, rcx
0x180006dfc  jnb     short loc_180006E07
0x180006dfe  cmp     [rbx], rdx
0x180006e01  ja      short loc_180006E07
0x180006e03  mov     al, 1
0x180006e05  jmp     short loc_180006E09
0x180006e07  xor     al, al
0x180006e09  mov     r8, [rbx+10h]
0x180006e0d  test    al, al
0x180006e0f  jz      short loc_180006E88
0x180006e11  mov     rsi, [rbx]
0x180006e14  cmp     rcx, r8
0x180006e17  jnz     short loc_180006E78
0x180006e19  mov     rax, r8
0x180006e1c  sub     rax, rcx
0x180006e1f  sar     rax, 3
0x180006e23  cmp     rax, 1
0x180006e27  jnb     short loc_180006E78
0x180006e29  sub     rcx, rsi
0x180006e2c  mov     r9, 1FFFFFFFFFFFFFFFh
0x180006e36  sar     rcx, 3
0x180006e3a  mov     rax, r9
0x180006e3d  sub     rax, rcx
0x180006e40  cmp     rax, 1
0x180006e44  jb      loc_180006F0D
0x180006e4a  inc     rcx
0x180006e4d  xor     edx, edx
0x180006e4f  sub     r8, rsi
0x180006e52  sar     r8, 3
0x180006e56  mov     rax, r8
0x180006e59  shr     rax, 1
0x180006e5c  sub     r9, rax
0x180006e5f  add     rax, r8
0x180006e62  cmp     r9, r8
0x180006e65  cmovnb  rdx, rax
0x180006e69  cmp     rdx, rcx
0x180006e6c  cmovb   rdx, rcx
0x180006e70  mov     rcx, rbx
0x180006e73  call    ?_Reallocate@?$vector@PEAGV?$allocator@PEAG@std@@@std@@IEAAX_K@Z; std::vector<ushort *>::_Reallocate(unsigned __int64)
0x180006e78  mov     rax, [rbx]
0x180006e7b  sub     rdi, rsi
0x180006e7e  sar     rdi, 3
0x180006e82  mov     rax, [rax+rdi*8]
0x180006e86  jmp     short loc_180006EEB
0x180006e88  cmp     rcx, r8
0x180006e8b  jnz     short loc_180006EE8
0x180006e8d  mov     rax, r8
0x180006e90  sub     rax, rcx
0x180006e93  sar     rax, 3
0x180006e97  cmp     rax, 1
0x180006e9b  jnb     short loc_180006EE8
0x180006e9d  sub     rcx, [rbx]
0x180006ea0  mov     r9, 1FFFFFFFFFFFFFFFh
0x180006eaa  sar     rcx, 3
0x180006eae  mov     rax, r9
0x180006eb1  sub     rax, rcx
0x180006eb4  cmp     rax, 1
0x180006eb8  jb      short loc_180006F07
0x180006eba  sub     r8, [rbx]
0x180006ebd  inc     rcx
0x180006ec0  sar     r8, 3
0x180006ec4  xor     edx, edx
0x180006ec6  mov     rax, r8
0x180006ec9  shr     rax, 1
0x180006ecc  sub     r9, rax
0x180006ecf  add     rax, r8
0x180006ed2  cmp     r9, r8
0x180006ed5  cmovnb  rdx, rax
0x180006ed9  cmp     rdx, rcx
0x180006edc  cmovb   rdx, rcx
0x180006ee0  mov     rcx, rbx
0x180006ee3  call    ?_Reallocate@?$vector@PEAGV?$allocator@PEAG@std@@@std@@IEAAX_K@Z; std::vector<ushort *>::_Reallocate(unsigned __int64)
0x180006ee8  mov     rax, [rdi]
0x180006eeb  mov     rcx, [rbx+8]
0x180006eef  mov     rsi, [rsp+28h+arg_8]
0x180006ef4  mov     [rcx], rax
0x180006ef7  add     qword ptr [rbx+8], 8
0x180006efc  mov     rbx, [rsp+28h+arg_0]
0x180006f01  add     rsp, 20h
0x180006f05  pop     rdi
0x180006f06  retn
0x180006f07  call    ?_Xlen@?$vector@PEAGV?$allocator@PEAG@std@@@std@@IEBAXXZ; std::vector<ushort *>::_Xlen(void)
0x180006f0d  call    ?_Xlen@?$vector@PEAGV?$allocator@PEAG@std@@@std@@IEBAXXZ; std::vector<ushort *>::_Xlen(void)
```
