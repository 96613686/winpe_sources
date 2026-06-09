# IoPack_Registration_ParamBlock(ushort const *,ulong,ulong,ulong,_CRYPT_PROVIDER_REG *,ulong *,uchar *)

- ea: `0x180001c04`
- end: `0x180001d26`
- name: `?IoPack_Registration_ParamBlock@@YAKPEBGKKKPEAU_CRYPT_PROVIDER_REG@@PEAKPEAE@Z`
- size: `290`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, struct _CRYPT_PROVIDER_REG *, unsigned int *, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180001dd0`
- `0x180012780`
- `0x180019a00`

## callees

- `0x180001c04`
- `0x180001d2c`
- `0x180004120`
- `0x18001253c`
- `0x18001b79d`

## pseudocode

```c
unsigned int __fastcall IoPack_Registration_ParamBlock(
        const unsigned __int16 *a1,
        int a2,
        int a3,
        int a4,
        struct _CRYPT_PROVIDER_REG *a5,
        unsigned int *a6,
        unsigned __int8 *a7)
{
  unsigned int *v7; // r14
  unsigned __int64 v8; // rdi
  unsigned int v13; // ebp
  unsigned __int8 *v14; // rbx
  unsigned int result; // eax
  unsigned int v16; // ebp
  unsigned __int8 *v17; // rsi
  __int64 v18; // rdi
  unsigned int v19; // [rsp+70h] [rbp+8h] BYREF

  v7 = a6;
  v8 = 0;
  v19 = 0;
  v13 = 40;
  if ( a6 )
    *a6 = 0;
  v14 = a7;
  if ( a1 )
  {
    LODWORD(a6) = 0;
    v8 = (unsigned __int64)(a7 + 40) & -(__int64)(a7 != 0);
    result = SzString_CchLength(a1, (unsigned int *)&a6, 0);
    if ( result )
      return result;
    v16 = (2 * (_DWORD)a6 + 9) & 0xFFFFFFF8;
    if ( v8 )
      memcpy_0((void *)((unsigned __int64)(v14 + 40) & -(__int64)(v14 != 0)), a1, 2LL * (unsigned int)((_DWORD)a6 + 1));
    v13 = v16 + 40;
  }
  v17 = 0;
  if ( !a5 )
    goto LABEL_9;
  if ( v14 )
    v17 = &v14[v13];
  result = IoCopy_ProviderReg(a5, &v19, v17);
  if ( !result )
  {
    v13 += v19;
LABEL_9:
    if ( v14 )
    {
      *((_DWORD *)v14 + 4) = a2;
      *((_QWORD *)v14 + 4) = v17;
      *((_DWORD *)v14 + 5) = a3;
      *((_DWORD *)v14 + 6) = a4;
      if ( v8 )
        v18 = v8 - (_QWORD)v14;
      else
        v18 = -1;
      *((_QWORD *)v14 + 1) = v18;
      IoPack_ProviderReg((struct _CRYPT_PROVIDER_REG **)v14 + 4, v14);
    }
    if ( v7 )
      *v7 = v13;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001c04  push    rbx
0x180001c06  push    rbp
0x180001c07  push    rsi
0x180001c08  push    rdi
0x180001c09  push    r12
0x180001c0b  push    r13
0x180001c0d  push    r14
0x180001c0f  push    r15
0x180001c11  sub     rsp, 28h
0x180001c15  mov     r14, [rsp+68h+arg_28]
0x180001c1d  xor     edi, edi
0x180001c1f  mov     [rsp+68h+arg_0], edi
0x180001c23  mov     r15d, r9d
0x180001c26  mov     r12d, r8d
0x180001c29  mov     r13d, edx
0x180001c2c  mov     rsi, rcx
0x180001c2f  mov     ebp, 28h ; '('
0x180001c34  test    r14, r14
0x180001c37  jz      short loc_180001C3C
0x180001c39  mov     [r14], edi
0x180001c3c  mov     rbx, [rsp+68h+arg_30]
0x180001c44  test    rsi, rsi
0x180001c47  jz      short loc_180001CA6
0x180001c49  lea     rcx, [rbx+28h]
0x180001c4d  mov     dword ptr [rsp+68h+arg_28], 0
0x180001c58  mov     rax, rbx
0x180001c5b  lea     rdx, [rsp+68h+arg_28]; unsigned int *
0x180001c63  neg     rax
0x180001c66  sbb     rdi, rdi
0x180001c69  xor     r8d, r8d; unsigned int
0x180001c6c  and     rdi, rcx
0x180001c6f  mov     rcx, rsi; unsigned __int16 *
0x180001c72  call    ?SzString_CchLength@@YAKPEBGPEAKK@Z; SzString_CchLength(ushort const *,ulong *,ulong)
0x180001c77  test    eax, eax
0x180001c79  jnz     short loc_180001CEB
0x180001c7b  mov     eax, dword ptr [rsp+68h+arg_28]
0x180001c82  lea     ebp, ds:9[rax*2]
0x180001c89  and     ebp, 0FFFFFFF8h
0x180001c8c  test    rdi, rdi
0x180001c8f  jz      short loc_180001CA3
0x180001c91  lea     r8d, [rax+1]
0x180001c95  mov     rdx, rsi; Src
0x180001c98  add     r8, r8; Size
0x180001c9b  mov     rcx, rdi; void *
0x180001c9e  call    memcpy_0
0x180001ca3  add     ebp, 28h ; '('
0x180001ca6  mov     rcx, [rsp+68h+arg_20]; struct _CRYPT_PROVIDER_REG *
0x180001cae  xor     esi, esi
0x180001cb0  test    rcx, rcx
0x180001cb3  jnz     short loc_180001D03
0x180001cb5  test    rbx, rbx
0x180001cb8  jz      short loc_180001CE1
0x180001cba  mov     [rbx+10h], r13d
0x180001cbe  lea     rcx, [rbx+20h]; struct _CRYPT_PROVIDER_REG **
0x180001cc2  mov     [rcx], rsi
0x180001cc5  mov     [rbx+14h], r12d
0x180001cc9  mov     [rbx+18h], r15d
0x180001ccd  test    rdi, rdi
0x180001cd0  jz      short loc_180001CFD
0x180001cd2  sub     rdi, rbx
0x180001cd5  mov     rdx, rbx; unsigned __int8 *
0x180001cd8  mov     [rbx+8], rdi
0x180001cdc  call    ?IoPack_ProviderReg@@YAXPEAPEAU_CRYPT_PROVIDER_REG@@PEAE@Z; IoPack_ProviderReg(_CRYPT_PROVIDER_REG * *,uchar *)
0x180001ce1  test    r14, r14
0x180001ce4  jz      short loc_180001CE9
0x180001ce6  mov     [r14], ebp
0x180001ce9  xor     eax, eax
0x180001ceb  add     rsp, 28h
0x180001cef  pop     r15
0x180001cf1  pop     r14
0x180001cf3  pop     r13
0x180001cf5  pop     r12
0x180001cf7  pop     rdi
0x180001cf8  pop     rsi
0x180001cf9  pop     rbp
0x180001cfa  pop     rbx
0x180001cfb  retn
0x180001cfd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180001d01  jmp     short loc_180001CD5
0x180001d03  test    rbx, rbx
0x180001d06  jnz     short loc_180001D1F
0x180001d08  mov     r8, rsi; unsigned __int8 *
0x180001d0b  lea     rdx, [rsp+68h+arg_0]; unsigned int *
0x180001d10  call    ?IoCopy_ProviderReg@@YAKPEAU_CRYPT_PROVIDER_REG@@PEAKPEAE@Z; IoCopy_ProviderReg(_CRYPT_PROVIDER_REG *,ulong *,uchar *)
0x180001d15  test    eax, eax
0x180001d17  jnz     short loc_180001CEB
0x180001d19  add     ebp, [rsp+68h+arg_0]
0x180001d1d  jmp     short loc_180001CB5
0x180001d1f  mov     esi, ebp
0x180001d21  add     rsi, rbx
0x180001d24  jmp     short loc_180001D08
```
