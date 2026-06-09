# CopyServiceConfigEx

- ea: `0x18000896c`
- end: `0x180008b87`
- name: `CopyServiceConfigEx`
- size: `539`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180008b90`

## callees

- `0x18000896c`
- `0x18000a4bc`
- `0x18000b080`
- `0x18000c550`

## pseudocode

```c
__int64 __fastcall CopyServiceConfigEx(
        int a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int64 *a5,
        _DWORD *a6)
{
  unsigned __int64 v6; // rbp
  unsigned int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // r12
  unsigned __int64 v16; // rdi
  int v17; // ebp

  v6 = a4;
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_dqqdqq(a1, a2, a3, a1, a2, a3, a4, a5, a6);
  if ( !a2 || !a3 )
    goto LABEL_4;
  v11 = a1 - 8;
  if ( !v11 )
    goto LABEL_15;
  v12 = v11 - 1;
  if ( !v12 )
    goto LABEL_11;
  v13 = v12 - 1;
  if ( !v13 )
  {
LABEL_15:
    if ( (unsigned int)v6 >= 0xA0 )
    {
      v10 = 0;
      *(_OWORD *)a3 = *(_OWORD *)a2;
      *(_OWORD *)(a3 + 16) = *(_OWORD *)(a2 + 16);
      *(_OWORD *)(a3 + 32) = *(_OWORD *)(a2 + 32);
      *(_OWORD *)(a3 + 48) = *(_OWORD *)(a2 + 48);
      *(_OWORD *)(a3 + 64) = *(_OWORD *)(a2 + 64);
      *(_OWORD *)(a3 + 80) = *(_OWORD *)(a2 + 80);
      *(_OWORD *)(a3 + 96) = *(_OWORD *)(a2 + 96);
      *(_OWORD *)(a3 + 112) = *(_OWORD *)(a2 + 112);
      *(_OWORD *)(a3 + 128) = *(_OWORD *)(a2 + 128);
      *(_OWORD *)(a3 + 144) = *(_OWORD *)(a2 + 144);
      v16 = a3 + 160;
      v17 = v6 - 160;
      goto LABEL_17;
    }
LABEL_4:
    v10 = 87;
    goto LABEL_21;
  }
  if ( v13 != 2 )
  {
    v10 = 5023;
    goto LABEL_21;
  }
LABEL_11:
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(*(_QWORD *)(a2 + 128) + 2 * v14) );
  v15 = (unsigned int)(2 * v14 + 2);
  if ( v6 < v15 + 168 )
    goto LABEL_4;
  v10 = 0;
  *(_OWORD *)a3 = *(_OWORD *)a2;
  *(_OWORD *)(a3 + 16) = *(_OWORD *)(a2 + 16);
  *(_OWORD *)(a3 + 32) = *(_OWORD *)(a2 + 32);
  *(_OWORD *)(a3 + 48) = *(_OWORD *)(a2 + 48);
  *(_OWORD *)(a3 + 64) = *(_OWORD *)(a2 + 64);
  *(_OWORD *)(a3 + 80) = *(_OWORD *)(a2 + 80);
  *(_OWORD *)(a3 + 96) = *(_OWORD *)(a2 + 96);
  *(_OWORD *)(a3 + 112) = *(_OWORD *)(a2 + 112);
  *(_OWORD *)(a3 + 128) = *(_OWORD *)(a2 + 128);
  *(_OWORD *)(a3 + 144) = *(_OWORD *)(a2 + 144);
  *(_QWORD *)(a3 + 160) = *(_QWORD *)(a2 + 160);
  *(_QWORD *)(a3 + 128) = a3 + 168;
  memcpy_0((void *)(a3 + 168), *(const void **)(a2 + 128), (unsigned int)v15);
  v16 = (v15 + *(_QWORD *)(a3 + 128) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
  v17 = (v6 - v15 - 168) & 0xFFFFFFF8;
LABEL_17:
  if ( a5 )
    *a5 = v16;
  if ( a6 )
    *a6 = v17;
LABEL_21:
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_d(1050, 32, WPP_9757c9c47725323be14918a4f6df94b6_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18000896c  mov     rax, rsp
0x18000896f  push    rbx
0x180008970  push    rbp
0x180008971  push    rsi
0x180008972  push    rdi
0x180008973  push    r12
0x180008975  push    r13
0x180008977  push    r14
0x180008979  push    r15
0x18000897b  sub     rsp, 58h
0x18000897f  mov     ebp, r9d
0x180008982  mov     rdi, r8
0x180008985  mov     rsi, rdx
0x180008988  mov     ebx, ecx
0x18000898a  test    cs:byte_1800126A3, 4
0x180008991  mov     r14, [rsp+98h+arg_28]
0x180008999  mov     r15, [rsp+98h+arg_20]
0x1800089a1  jz      short loc_1800089BE
0x1800089a3  mov     [rax-58h], r14
0x1800089a7  mov     r9d, ecx
0x1800089aa  mov     [rax-60h], r15
0x1800089ae  mov     [rax-68h], ebp
0x1800089b1  mov     [rax-70h], r8
0x1800089b5  mov     [rax-78h], rdx
0x1800089b9  call    WPP_SF_dqqdqq
0x1800089be  xor     edx, edx
0x1800089c0  test    rsi, rsi
0x1800089c3  jnz     short loc_1800089CF
0x1800089c5  mov     ebx, 57h ; 'W'
0x1800089ca  jmp     loc_180008B52
0x1800089cf  test    rdi, rdi
0x1800089d2  jz      short loc_1800089C5
0x1800089d4  sub     ebx, 8
0x1800089d7  jz      loc_180008ACD
0x1800089dd  sub     ebx, 1
0x1800089e0  jz      short loc_1800089FA
0x1800089e2  sub     ebx, 1
0x1800089e5  jz      loc_180008ACD
0x1800089eb  cmp     ebx, 2
0x1800089ee  jz      short loc_1800089FA
0x1800089f0  mov     ebx, 139Fh
0x1800089f5  jmp     loc_180008B52
0x1800089fa  mov     rcx, [rsi+80h]
0x180008a01  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008a05  inc     rax
0x180008a08  cmp     [rcx+rax*2], dx
0x180008a0c  jnz     short loc_180008A05
0x180008a0e  lea     r12d, ds:2[rax*2]
0x180008a16  lea     rcx, [r12+0A8h]
0x180008a1e  mov     r13d, r12d
0x180008a21  cmp     rbp, rcx
0x180008a24  jb      short loc_1800089C5
0x180008a26  movups  xmm0, xmmword ptr [rsi]
0x180008a29  lea     rcx, [rdi+0A8h]; void *
0x180008a30  mov     ebx, edx
0x180008a32  mov     r8d, r13d; Size
0x180008a35  movups  xmmword ptr [rdi], xmm0
0x180008a38  movups  xmm1, xmmword ptr [rsi+10h]
0x180008a3c  movups  xmmword ptr [rdi+10h], xmm1
0x180008a40  movups  xmm0, xmmword ptr [rsi+20h]
0x180008a44  movups  xmmword ptr [rdi+20h], xmm0
0x180008a48  movups  xmm1, xmmword ptr [rsi+30h]
0x180008a4c  movups  xmmword ptr [rdi+30h], xmm1
0x180008a50  movups  xmm0, xmmword ptr [rsi+40h]
0x180008a54  movups  xmmword ptr [rdi+40h], xmm0
0x180008a58  movups  xmm1, xmmword ptr [rsi+50h]
0x180008a5c  movups  xmmword ptr [rdi+50h], xmm1
0x180008a60  movups  xmm0, xmmword ptr [rsi+60h]
0x180008a64  movups  xmmword ptr [rdi+60h], xmm0
0x180008a68  movups  xmm1, xmmword ptr [rsi+70h]
0x180008a6c  movups  xmmword ptr [rdi+70h], xmm1
0x180008a70  movups  xmm0, xmmword ptr [rsi+80h]
0x180008a77  movups  xmmword ptr [rdi+80h], xmm0
0x180008a7e  movups  xmm1, xmmword ptr [rsi+90h]
0x180008a85  movups  xmmword ptr [rdi+90h], xmm1
0x180008a8c  mov     rax, [rsi+0A0h]
0x180008a93  mov     [rdi+0A0h], rax
0x180008a9a  mov     [rdi+80h], rcx
0x180008aa1  mov     rdx, [rsi+80h]; Src
0x180008aa8  call    memcpy_0
0x180008aad  mov     rdi, [rdi+80h]
0x180008ab4  sub     ebp, r12d
0x180008ab7  add     rdi, 7
0x180008abb  sub     ebp, 0A8h
0x180008ac1  add     rdi, r13
0x180008ac4  and     rdi, 0FFFFFFFFFFFFFFF8h
0x180008ac8  and     ebp, 0FFFFFFF8h
0x180008acb  jmp     short loc_180008B42
0x180008acd  cmp     ebp, 0A0h
0x180008ad3  jb      loc_1800089C5
0x180008ad9  movups  xmm0, xmmword ptr [rsi]
0x180008adc  mov     ebx, edx
0x180008ade  movups  xmmword ptr [rdi], xmm0
0x180008ae1  movups  xmm1, xmmword ptr [rsi+10h]
0x180008ae5  movups  xmmword ptr [rdi+10h], xmm1
0x180008ae9  movups  xmm0, xmmword ptr [rsi+20h]
0x180008aed  movups  xmmword ptr [rdi+20h], xmm0
0x180008af1  movups  xmm1, xmmword ptr [rsi+30h]
0x180008af5  movups  xmmword ptr [rdi+30h], xmm1
0x180008af9  movups  xmm0, xmmword ptr [rsi+40h]
0x180008afd  movups  xmmword ptr [rdi+40h], xmm0
0x180008b01  movups  xmm1, xmmword ptr [rsi+50h]
0x180008b05  movups  xmmword ptr [rdi+50h], xmm1
0x180008b09  movups  xmm0, xmmword ptr [rsi+60h]
0x180008b0d  movups  xmmword ptr [rdi+60h], xmm0
0x180008b11  movups  xmm1, xmmword ptr [rsi+70h]
0x180008b15  movups  xmmword ptr [rdi+70h], xmm1
0x180008b19  movups  xmm0, xmmword ptr [rsi+80h]
0x180008b20  movups  xmmword ptr [rdi+80h], xmm0
0x180008b27  movups  xmm1, xmmword ptr [rsi+90h]
0x180008b2e  movups  xmmword ptr [rdi+90h], xmm1
0x180008b35  add     rdi, 0A0h
0x180008b3c  add     ebp, 0FFFFFF60h
0x180008b42  test    r15, r15
0x180008b45  jz      short loc_180008B4A
0x180008b47  mov     [r15], rdi
0x180008b4a  test    r14, r14
0x180008b4d  jz      short loc_180008B52
0x180008b4f  mov     [r14], ebp
0x180008b52  test    cs:byte_1800126A3, 4
0x180008b59  jz      short loc_180008B74
0x180008b5b  mov     edx, 20h ; ' '
0x180008b60  lea     r8, WPP_9757c9c47725323be14918a4f6df94b6_Traceguids
0x180008b67  mov     ecx, 41Ah
0x180008b6c  mov     r9d, ebx
0x180008b6f  call    WPP_SF_d
0x180008b74  mov     eax, ebx
0x180008b76  add     rsp, 58h
0x180008b7a  pop     r15
0x180008b7c  pop     r14
0x180008b7e  pop     r13
0x180008b80  pop     r12
0x180008b82  pop     rdi
0x180008b83  pop     rsi
0x180008b84  pop     rbp
0x180008b85  pop     rbx
0x180008b86  retn
```
