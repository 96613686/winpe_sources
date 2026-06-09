# UpdateDst411MBYVYU(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18003ba50`
- end: `0x18003badf`
- name: `?UpdateDst411MBYVYU@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `143`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18003bf20`

## callees

- `0x18003ba50`

## pseudocode

```c
void __fastcall UpdateDst411MBYVYU(
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
      v16 = *v13++;
      *(v10 - 3) = v16;
      *(v10 - 7) = v16;
      v17 = *v12++;
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
0x18003ba50  push    rbx
0x18003ba52  push    rbp
0x18003ba53  push    rsi
0x18003ba54  push    rdi
0x18003ba55  push    r12
0x18003ba57  push    r14
0x18003ba59  push    r15
0x18003ba5b  movsxd  rbp, [rsp+38h+arg_38]
0x18003ba60  mov     r10d, 10h
0x18003ba66  movsxd  r15, [rsp+38h+arg_28]
0x18003ba6b  movsxd  rdi, [rsp+38h+arg_30]
0x18003ba70  mov     r11, [rsp+38h+arg_20]
0x18003ba75  mov     rcx, rdx
0x18003ba78  mov     rbx, r8
0x18003ba7b  mov     rsi, r9
0x18003ba7e  mov     r14, r11
0x18003ba81  mov     r12d, 4
0x18003ba87  mov     al, [rbx]
0x18003ba89  lea     rbx, [rbx+4]
0x18003ba8d  mov     [rcx], al
0x18003ba8f  lea     rcx, [rcx+8]
0x18003ba93  mov     al, [rbx-3]
0x18003ba96  mov     [rcx-6], al
0x18003ba99  mov     al, [rbx-2]
0x18003ba9c  mov     [rcx-4], al
0x18003ba9f  mov     al, [rbx-1]
0x18003baa2  mov     [rcx-2], al
0x18003baa5  mov     al, [r14]
0x18003baa8  inc     r14
0x18003baab  mov     [rcx-3], al
0x18003baae  mov     [rcx-7], al
0x18003bab1  mov     al, [rsi]
0x18003bab3  inc     rsi
0x18003bab6  mov     [rcx-1], al
0x18003bab9  mov     [rcx-5], al
0x18003babc  sub     r12d, 1
0x18003bac0  jnz     short loc_18003BA87
0x18003bac2  add     rdx, rbp
0x18003bac5  add     r8, r15
0x18003bac8  add     r9, rdi
0x18003bacb  add     r11, rdi
0x18003bace  sub     r10d, 1
0x18003bad2  jnz     short loc_18003BA75
0x18003bad4  pop     r15
0x18003bad6  pop     r14
0x18003bad8  pop     r12
0x18003bada  pop     rdi
0x18003badb  pop     rsi
0x18003badc  pop     rbp
0x18003badd  pop     rbx
0x18003bade  retn
```
