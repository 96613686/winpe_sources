# UpdateDst411MBUYVY(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18003b910`
- end: `0x18003b99f`
- name: `?UpdateDst411MBUYVY@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `143`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18003bd60`

## callees

- `0x18003b910`

## pseudocode

```c
void __fastcall UpdateDst411MBUYVY(
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
      v10[1] = v15;
      v10[3] = *(v11 - 3);
      v10[5] = *(v11 - 2);
      v10[7] = *(v11 - 1);
      v16 = *v12++;
      v10[4] = v16;
      *v10 = v16;
      v10 += 8;
      v17 = *v13++;
      *(v10 - 2) = v17;
      *(v10 - 6) = v17;
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
0x18003b910  push    rbx
0x18003b912  push    rbp
0x18003b913  push    rsi
0x18003b914  push    rdi
0x18003b915  push    r12
0x18003b917  push    r14
0x18003b919  push    r15
0x18003b91b  movsxd  rbp, [rsp+38h+arg_38]
0x18003b920  mov     r10d, 10h
0x18003b926  movsxd  r15, [rsp+38h+arg_28]
0x18003b92b  movsxd  rdi, [rsp+38h+arg_30]
0x18003b930  mov     r11, [rsp+38h+arg_20]
0x18003b935  mov     rcx, rdx
0x18003b938  mov     rbx, r8
0x18003b93b  mov     rsi, r9
0x18003b93e  mov     r14, r11
0x18003b941  mov     r12d, 4
0x18003b947  mov     al, [rbx]
0x18003b949  lea     rbx, [rbx+4]
0x18003b94d  mov     [rcx+1], al
0x18003b950  mov     al, [rbx-3]
0x18003b953  mov     [rcx+3], al
0x18003b956  mov     al, [rbx-2]
0x18003b959  mov     [rcx+5], al
0x18003b95c  mov     al, [rbx-1]
0x18003b95f  mov     [rcx+7], al
0x18003b962  mov     al, [rsi]
0x18003b964  inc     rsi
0x18003b967  mov     [rcx+4], al
0x18003b96a  mov     [rcx], al
0x18003b96c  lea     rcx, [rcx+8]
0x18003b970  mov     al, [r14]
0x18003b973  inc     r14
0x18003b976  mov     [rcx-2], al
0x18003b979  mov     [rcx-6], al
0x18003b97c  sub     r12d, 1
0x18003b980  jnz     short loc_18003B947
0x18003b982  add     rdx, rbp
0x18003b985  add     r8, r15
0x18003b988  add     r9, rdi
0x18003b98b  add     r11, rdi
0x18003b98e  sub     r10d, 1
0x18003b992  jnz     short loc_18003B935
0x18003b994  pop     r15
0x18003b996  pop     r14
0x18003b998  pop     r12
0x18003b99a  pop     rdi
0x18003b99b  pop     rsi
0x18003b99c  pop     rbp
0x18003b99d  pop     rbx
0x18003b99e  retn
```
