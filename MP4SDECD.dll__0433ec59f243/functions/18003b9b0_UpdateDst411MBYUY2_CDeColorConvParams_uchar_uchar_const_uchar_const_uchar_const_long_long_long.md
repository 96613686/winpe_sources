# UpdateDst411MBYUY2(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18003b9b0`
- end: `0x18003ba3f`
- name: `?UpdateDst411MBYUY2@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `143`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18003be40`

## callees

- `0x18003b9b0`

## pseudocode

```c
void __fastcall UpdateDst411MBYUY2(
        struct CDeColorConvParams *a1,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const unsigned __int8 *a5,
        int a6,
        int a7,
        int a8)
{
  int v8; // r10d
  unsigned __int8 *v10; // rcx
  const unsigned __int8 *v11; // rbx
  const unsigned __int8 *v12; // rsi
  const unsigned __int8 *v13; // r14
  int v14; // r12d
  unsigned __int8 v15; // al
  unsigned __int8 v16; // al
  unsigned __int8 v17; // al

  v8 = 16;
  do
  {
    v10 = a2;
    v11 = a3;
    v12 = a4;
    v13 = a5;
    v14 = 4;
    do
    {
      v15 = *v11;
      v11 += 4;
      *v10 = v15;
      v10 += 8;
      *(v10 - 6) = *(v11 - 3);
      *(v10 - 4) = *(v11 - 2);
      *(v10 - 2) = *(v11 - 1);
      v16 = *v12++;
      *(v10 - 3) = v16;
      *(v10 - 7) = v16;
      v17 = *v13++;
      *(v10 - 1) = v17;
      *(v10 - 5) = v17;
      --v14;
    }
    while ( v14 );
    a2 += a8;
    a3 += a6;
    a4 += a7;
    a5 += a7;
    --v8;
  }
  while ( v8 );
}

```

## disassembly

```asm
0x18003b9b0  push    rbx
0x18003b9b2  push    rbp
0x18003b9b3  push    rsi
0x18003b9b4  push    rdi
0x18003b9b5  push    r12
0x18003b9b7  push    r14
0x18003b9b9  push    r15
0x18003b9bb  movsxd  rbp, [rsp+38h+arg_38]
0x18003b9c0  mov     r10d, 10h
0x18003b9c6  movsxd  r15, [rsp+38h+arg_28]
0x18003b9cb  movsxd  rdi, [rsp+38h+arg_30]
0x18003b9d0  mov     r11, [rsp+38h+arg_20]
0x18003b9d5  mov     rcx, rdx
0x18003b9d8  mov     rbx, r8
0x18003b9db  mov     rsi, r9
0x18003b9de  mov     r14, r11
0x18003b9e1  mov     r12d, 4
0x18003b9e7  mov     al, [rbx]
0x18003b9e9  lea     rbx, [rbx+4]
0x18003b9ed  mov     [rcx], al
0x18003b9ef  lea     rcx, [rcx+8]
0x18003b9f3  mov     al, [rbx-3]
0x18003b9f6  mov     [rcx-6], al
0x18003b9f9  mov     al, [rbx-2]
0x18003b9fc  mov     [rcx-4], al
0x18003b9ff  mov     al, [rbx-1]
0x18003ba02  mov     [rcx-2], al
0x18003ba05  mov     al, [rsi]
0x18003ba07  inc     rsi
0x18003ba0a  mov     [rcx-3], al
0x18003ba0d  mov     [rcx-7], al
0x18003ba10  mov     al, [r14]
0x18003ba13  inc     r14
0x18003ba16  mov     [rcx-1], al
0x18003ba19  mov     [rcx-5], al
0x18003ba1c  sub     r12d, 1
0x18003ba20  jnz     short loc_18003B9E7
0x18003ba22  add     rdx, rbp
0x18003ba25  add     r8, r15
0x18003ba28  add     r9, rdi
0x18003ba2b  add     r11, rdi
0x18003ba2e  sub     r10d, 1
0x18003ba32  jnz     short loc_18003B9D5
0x18003ba34  pop     r15
0x18003ba36  pop     r14
0x18003ba38  pop     r12
0x18003ba3a  pop     rdi
0x18003ba3b  pop     rsi
0x18003ba3c  pop     rbp
0x18003ba3d  pop     rbx
0x18003ba3e  retn
```
