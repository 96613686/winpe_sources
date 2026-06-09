# UpdateDstMBNV12(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18003ec90`
- end: `0x18003ed32`
- name: `?UpdateDstMBNV12@@YAXPEAE00PEBE11JJJJ@Z`
- size: `162`
- prototype: `void __fastcall(unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18003ec90`

## pseudocode

```c
void __fastcall UpdateDstMBNV12(
        unsigned __int8 *a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const unsigned __int8 *a5,
        const unsigned __int8 *a6,
        int a7,
        int a8,
        int a9,
        int a10)
{
  int v15; // edx
  unsigned __int8 *v16; // r8
  __int128 v17; // xmm1
  __int64 i; // rcx
  unsigned __int8 v19; // al

  v15 = 8;
  do
  {
    v16 = a3;
    *(_OWORD *)a1 = *(_OWORD *)a4;
    v17 = *(_OWORD *)&a4[a7];
    a4 += 2 * a7;
    *(_OWORD *)&a1[a9] = v17;
    a1 += 2 * a9;
    for ( i = 0; i != 8; ++i )
    {
      *v16 = a5[i];
      v16 += 2;
      v19 = a6[i];
      *(v16 - 1) = v19;
    }
    a5 += a8;
    a6 += a8;
    a3 += 2 * a10;
    --v15;
  }
  while ( v15 );
}

```

## disassembly

```asm
0x18003ec90  push    rbx
0x18003ec92  push    rbp
0x18003ec93  push    rsi
0x18003ec94  push    rdi
0x18003ec95  push    r12
0x18003ec97  push    r13
0x18003ec99  push    r14
0x18003ec9b  push    r15
0x18003ec9d  movsxd  r14, [rsp+40h+arg_30]
0x18003eca2  mov     rsi, r9
0x18003eca5  movsxd  r15, [rsp+40h+arg_40]
0x18003ecad  mov     r11, r8
0x18003ecb0  movsxd  rdi, [rsp+40h+arg_48]
0x18003ecb8  mov     rbp, rcx
0x18003ecbb  movsxd  rbx, [rsp+40h+arg_38]
0x18003ecc3  add     rdi, rdi
0x18003ecc6  mov     r9, [rsp+40h+arg_28]
0x18003eccb  lea     r12, [r14+r14]
0x18003eccf  mov     r10, [rsp+40h+arg_20]
0x18003ecd4  lea     r13, [r15+r15]
0x18003ecd8  mov     edx, 8
0x18003ecdd  movups  xmm0, xmmword ptr [rsi]
0x18003ece0  mov     r8, r11
0x18003ece3  movdqu  xmmword ptr [rbp+0], xmm0
0x18003ece8  movups  xmm1, xmmword ptr [r14+rsi]
0x18003eced  add     rsi, r12
0x18003ecf0  movdqu  xmmword ptr [r15+rbp], xmm1
0x18003ecf6  add     rbp, r13
0x18003ecf9  xor     ecx, ecx
0x18003ecfb  mov     al, [rcx+r10]
0x18003ecff  mov     [r8], al
0x18003ed02  lea     r8, [r8+2]
0x18003ed06  mov     al, [r9+rcx]
0x18003ed0a  inc     rcx
0x18003ed0d  mov     [r8-1], al
0x18003ed11  cmp     rcx, 8
0x18003ed15  jnz     short loc_18003ECFB
0x18003ed17  add     r10, rbx
0x18003ed1a  add     r9, rbx
0x18003ed1d  add     r11, rdi
0x18003ed20  sub     edx, 1
0x18003ed23  jnz     short loc_18003ECDD
0x18003ed25  pop     r15
0x18003ed27  pop     r14
0x18003ed29  pop     r13
0x18003ed2b  pop     r12
0x18003ed2d  pop     rdi
0x18003ed2e  pop     rsi
0x18003ed2f  pop     rbp
0x18003ed30  pop     rbx
0x18003ed31  retn
```
