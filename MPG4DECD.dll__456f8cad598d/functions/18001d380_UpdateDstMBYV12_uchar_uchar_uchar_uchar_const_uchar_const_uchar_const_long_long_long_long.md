# UpdateDstMBYV12(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18001d380`
- end: `0x18001d3fd`
- name: `?UpdateDstMBYV12@@YAXPEAE00PEBE11JJJJ@Z`
- size: `125`
- prototype: `void __fastcall(unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18001d380`

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
0x18001d380  push    rbx
0x18001d382  push    rbp
0x18001d383  push    rsi
0x18001d384  push    rdi
0x18001d385  push    r12
0x18001d387  push    r14
0x18001d389  push    r15
0x18001d38b  movsxd  r14, [rsp+38h+arg_30]
0x18001d390  mov     esi, 8
0x18001d395  movsxd  r15, [rsp+38h+arg_40]
0x18001d39d  movsxd  rbx, [rsp+38h+arg_38]
0x18001d3a2  movsxd  rdi, [rsp+38h+arg_48]
0x18001d3aa  mov     r10, [rsp+38h+arg_28]
0x18001d3af  lea     rbp, [r14+r14]
0x18001d3b3  mov     r11, [rsp+38h+arg_20]
0x18001d3b8  lea     r12, [r15+r15]
0x18001d3bc  movups  xmm0, xmmword ptr [r9]
0x18001d3c0  movdqu  xmmword ptr [rcx], xmm0
0x18001d3c4  movups  xmm1, xmmword ptr [r14+r9]
0x18001d3c9  add     r9, rbp
0x18001d3cc  movdqu  xmmword ptr [r15+rcx], xmm1
0x18001d3d2  mov     rax, [r11]
0x18001d3d5  add     rcx, r12
0x18001d3d8  mov     [rdx], rax
0x18001d3db  add     r11, rbx
0x18001d3de  mov     rax, [r10]
0x18001d3e1  add     rdx, rdi
0x18001d3e4  mov     [r8], rax
0x18001d3e7  add     r10, rbx
0x18001d3ea  add     r8, rdi
0x18001d3ed  sub     esi, 1
0x18001d3f0  jnz     short loc_18001D3BC
0x18001d3f2  pop     r15
0x18001d3f4  pop     r14
0x18001d3f6  pop     r12
0x18001d3f8  pop     rdi
0x18001d3f9  pop     rsi
0x18001d3fa  pop     rbp
0x18001d3fb  pop     rbx
0x18001d3fc  retn
```
