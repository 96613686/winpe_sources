# IoCopy_ImageRegs(_CRYPT_IMAGE_REG *,_CRYPT_IMAGE_REG *,uchar * *,uchar * *,ulong *,uchar *)

- ea: `0x180019dac`
- end: `0x180019e7c`
- name: `?IoCopy_ImageRegs@@YAKPEAU_CRYPT_IMAGE_REG@@0PEAPEAE1PEAKPEAE@Z`
- size: `208`
- prototype: `unsigned int(struct _CRYPT_IMAGE_REG *, struct _CRYPT_IMAGE_REG *, unsigned __int8 **, unsigned __int8 **, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001253c`

## callees

- `0x180019cbc`
- `0x180019dac`

## pseudocode

```c
unsigned int __fastcall IoCopy_ImageRegs(
        struct _CRYPT_IMAGE_REG *a1,
        struct _CRYPT_IMAGE_REG *a2,
        unsigned __int8 **a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        unsigned __int8 *a6)
{
  unsigned int *v6; // r15
  unsigned int result; // eax
  unsigned __int8 *v11; // rsi
  unsigned int v12; // ebx
  unsigned __int8 *v13; // rdi
  unsigned int v14; // [rsp+60h] [rbp+8h] BYREF

  v6 = a5;
  v14 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( !a1 && !a2 )
    return 87;
  v11 = a6;
  v12 = 0;
  if ( a1 )
  {
    result = IoCopy_ImageReg(a1, (__int64)a2, &v14, a6);
    if ( result )
      return result;
    if ( a3 )
      *a3 = v11;
    v12 = v14;
  }
  if ( !a2 )
    goto LABEL_23;
  if ( v11 )
    v13 = &v11[v12];
  else
    v13 = 0;
  result = IoCopy_ImageReg(a2, (__int64)a2, &v14, v13);
  if ( !result )
  {
    if ( a4 )
      *a4 = v13;
    v12 += v14;
LABEL_23:
    if ( v6 )
      *v6 = v12;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180019dac  push    rbx
0x180019dae  push    rbp
0x180019daf  push    rsi
0x180019db0  push    rdi
0x180019db1  push    r14
0x180019db3  push    r15
0x180019db5  sub     rsp, 28h
0x180019db9  mov     r15, [rsp+58h+arg_20]
0x180019dc1  mov     r14, r9
0x180019dc4  mov     [rsp+58h+arg_0], 0
0x180019dcc  mov     rdi, r8
0x180019dcf  mov     rbp, rdx
0x180019dd2  test    r15, r15
0x180019dd5  jz      short loc_180019DDE
0x180019dd7  mov     dword ptr [r15], 0
0x180019dde  test    rdi, rdi
0x180019de1  jz      short loc_180019DEA
0x180019de3  mov     qword ptr [r8], 0
0x180019dea  test    r14, r14
0x180019ded  jz      short loc_180019DF6
0x180019def  mov     qword ptr [r9], 0
0x180019df6  test    rcx, rcx
0x180019df9  jnz     short loc_180019E05
0x180019dfb  test    rbp, rbp
0x180019dfe  jnz     short loc_180019E05
0x180019e00  lea     eax, [rcx+57h]
0x180019e03  jmp     short loc_180019E6E
0x180019e05  mov     rsi, [rsp+58h+arg_28]
0x180019e0d  xor     ebx, ebx
0x180019e0f  test    rcx, rcx
0x180019e12  jz      short loc_180019E31
0x180019e14  mov     r9, rsi; unsigned __int8 *
0x180019e17  lea     r8, [rsp+58h+arg_0]; unsigned int *
0x180019e1c  call    ?IoCopy_ImageReg@@YAKPEAU_CRYPT_IMAGE_REG@@KPEAKPEAE@Z; IoCopy_ImageReg(_CRYPT_IMAGE_REG *,ulong,ulong *,uchar *)
0x180019e21  test    eax, eax
0x180019e23  jnz     short loc_180019E6E
0x180019e25  test    rdi, rdi
0x180019e28  jz      short loc_180019E2D
0x180019e2a  mov     [rdi], rsi
0x180019e2d  mov     ebx, [rsp+58h+arg_0]
0x180019e31  test    rbp, rbp
0x180019e34  jz      short loc_180019E64
0x180019e36  test    rsi, rsi
0x180019e39  jz      short loc_180019E42
0x180019e3b  mov     edi, ebx
0x180019e3d  add     rdi, rsi
0x180019e40  jmp     short loc_180019E44
0x180019e42  xor     edi, edi
0x180019e44  mov     r9, rdi; unsigned __int8 *
0x180019e47  lea     r8, [rsp+58h+arg_0]; unsigned int *
0x180019e4c  mov     rcx, rbp; struct _CRYPT_IMAGE_REG *
0x180019e4f  call    ?IoCopy_ImageReg@@YAKPEAU_CRYPT_IMAGE_REG@@KPEAKPEAE@Z; IoCopy_ImageReg(_CRYPT_IMAGE_REG *,ulong,ulong *,uchar *)
0x180019e54  test    eax, eax
0x180019e56  jnz     short loc_180019E6E
0x180019e58  test    r14, r14
0x180019e5b  jz      short loc_180019E60
0x180019e5d  mov     [r14], rdi
0x180019e60  add     ebx, [rsp+58h+arg_0]
0x180019e64  test    r15, r15
0x180019e67  jz      short loc_180019E6C
0x180019e69  mov     [r15], ebx
0x180019e6c  xor     eax, eax
0x180019e6e  add     rsp, 28h
0x180019e72  pop     r15
0x180019e74  pop     r14
0x180019e76  pop     rdi
0x180019e77  pop     rsi
0x180019e78  pop     rbp
0x180019e79  pop     rbx
0x180019e7a  retn
```
