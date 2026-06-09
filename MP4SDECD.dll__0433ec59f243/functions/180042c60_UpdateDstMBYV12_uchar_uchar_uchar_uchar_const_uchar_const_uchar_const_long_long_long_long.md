# UpdateDstMBYV12(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x180042c60`
- end: `0x180042cdd`
- name: `?UpdateDstMBYV12@@YAXPEAE00PEBE11JJJJ@Z`
- size: `125`
- prototype: `void __fastcall(unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180042c60`

## pseudocode

```c
void __fastcall UpdateDstMBYV12(
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
  int v10; // esi
  __int128 v13; // xmm1

  v10 = 8;
  do
  {
    *(_OWORD *)a1 = *(_OWORD *)a4;
    v13 = *(_OWORD *)&a4[a7];
    a4 += 2 * a7;
    *(_OWORD *)&a1[a9] = v13;
    a1 += 2 * a9;
    *(_QWORD *)a2 = *(_QWORD *)a5;
    a5 += a8;
    a2 += a10;
    *(_QWORD *)a3 = *(_QWORD *)a6;
    a6 += a8;
    a3 += a10;
    --v10;
  }
  while ( v10 );
}

```

## disassembly

```asm
0x180042c60  push    rbx
0x180042c62  push    rbp
0x180042c63  push    rsi
0x180042c64  push    rdi
0x180042c65  push    r12
0x180042c67  push    r14
0x180042c69  push    r15
0x180042c6b  movsxd  r14, [rsp+38h+arg_30]
0x180042c70  mov     esi, 8
0x180042c75  movsxd  r15, [rsp+38h+arg_40]
0x180042c7d  movsxd  rbx, [rsp+38h+arg_38]
0x180042c82  movsxd  rdi, [rsp+38h+arg_48]
0x180042c8a  mov     r10, [rsp+38h+arg_28]
0x180042c8f  lea     rbp, [r14+r14]
0x180042c93  mov     r11, [rsp+38h+arg_20]
0x180042c98  lea     r12, [r15+r15]
0x180042c9c  movups  xmm0, xmmword ptr [r9]
0x180042ca0  movdqu  xmmword ptr [rcx], xmm0
0x180042ca4  movups  xmm1, xmmword ptr [r14+r9]
0x180042ca9  add     r9, rbp
0x180042cac  movdqu  xmmword ptr [r15+rcx], xmm1
0x180042cb2  mov     rax, [r11]
0x180042cb5  add     rcx, r12
0x180042cb8  mov     [rdx], rax
0x180042cbb  add     r11, rbx
0x180042cbe  mov     rax, [r10]
0x180042cc1  add     rdx, rdi
0x180042cc4  mov     [r8], rax
0x180042cc7  add     r10, rbx
0x180042cca  add     r8, rdi
0x180042ccd  sub     esi, 1
0x180042cd0  jnz     short loc_180042C9C
0x180042cd2  pop     r15
0x180042cd4  pop     r14
0x180042cd6  pop     r12
0x180042cd8  pop     rdi
0x180042cd9  pop     rsi
0x180042cda  pop     rbp
0x180042cdb  pop     rbx
0x180042cdc  retn
```
