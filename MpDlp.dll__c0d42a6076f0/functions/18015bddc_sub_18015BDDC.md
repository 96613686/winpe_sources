# sub_18015BDDC

- ea: `0x18015bddc`
- end: `0x18015c0d6`
- name: `sub_18015BDDC`
- size: `762`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18015c294`
- `0x18022366c`

## callees

- `0x1800e46c8`
- `0x1800ed500`
- `0x18015bddc`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18015be4f`
- `KERNEL32!CompareStringOrdinal` at `0x18015be9f`
- `KERNEL32!CompareStringOrdinal` at `0x18015bee7`
- `KERNEL32!CompareStringOrdinal` at `0x18015bf2e`
- `KERNEL32!CompareStringOrdinal` at `0x18015bf83`
- `KERNEL32!CompareStringOrdinal` at `0x18015c00b`
- `KERNEL32!CompareStringOrdinal` at `0x18015c055`
- `KERNEL32!CompareStringOrdinal` at `0x18015be4f`
- `KERNEL32!CompareStringOrdinal` at `0x18015be9f`
- `KERNEL32!CompareStringOrdinal` at `0x18015bee7`
- `KERNEL32!CompareStringOrdinal` at `0x18015bf2e`
- `KERNEL32!CompareStringOrdinal` at `0x18015bf83`
- `KERNEL32!CompareStringOrdinal` at `0x18015c00b`
- `KERNEL32!CompareStringOrdinal` at `0x18015c055`

## pseudocode

```c
__int64 __fastcall sub_18015BDDC(_QWORD **a1, __int64 a2, __int64 **a3, const WCHAR *a4)
{
  _QWORD *v4; // rax
  const WCHAR *v5; // rdi
  _QWORD *v9; // rsi
  const WCHAR *v10; // r8
  const WCHAR *v11; // rcx
  const WCHAR *v12; // r8
  const WCHAR *v13; // rcx
  const WCHAR *v14; // rcx
  __int64 *v15; // rax
  const WCHAR *v16; // r8
  __int64 v17; // rsi
  const WCHAR *v18; // rcx
  bool v19; // zf
  const WCHAR *v20; // r8
  const WCHAR *v21; // rcx
  __int64 *v22; // rsi
  __int64 *v23; // rax
  __int64 **v24; // rcx
  __int64 *v25; // rcx
  const WCHAR *v26; // r8
  const WCHAR *v27; // rcx
  __int64 v28; // rsi
  const WCHAR *v29; // r8
  char v30; // al
  __int128 v32; // [rsp+30h] [rbp-48h] BYREF
  __int64 v33; // [rsp+40h] [rbp-38h]
  __int64 **v34; // [rsp+80h] [rbp+8h] BYREF

  v4 = *a1;
  v5 = a4;
  if ( *((_BYTE *)a3 + 25) )
  {
    v9 = v4 + 2;
    if ( *(_BYTE *)(v4[1] + 25LL) )
      goto LABEL_8;
    v10 = a4;
    v11 = (const WCHAR *)(*v9 + 32LL);
    if ( *((_QWORD *)a4 + 3) > 7u )
      v10 = *(const WCHAR **)a4;
    if ( *(_QWORD *)(*v9 + 56LL) > 7u )
      v11 = *(const WCHAR **)v11;
    if ( CompareStringOrdinal(v11, -1, v10, -1, 1) == 1 )
    {
LABEL_8:
      *(_QWORD *)a2 = *v9;
      *(_BYTE *)(a2 + 16) = 0;
LABEL_64:
      *(_QWORD *)(a2 + 8) = 0;
      goto LABEL_65;
    }
    goto LABEL_50;
  }
  v12 = (const WCHAR *)(a3 + 4);
  if ( a3 != (__int64 **)*v4 )
  {
    if ( *((_QWORD *)v12 + 3) > 7u )
      v12 = *(const WCHAR **)v12;
    v14 = a4;
    if ( *((_QWORD *)a4 + 3) > 7u )
      v14 = *(const WCHAR **)a4;
    if ( CompareStringOrdinal(v14, -1, v12, -1, 1) == 1 )
    {
      v34 = a3;
      v15 = (__int64 *)sub_1800E46C8(&v34);
      v16 = v5;
      v17 = *v15;
      if ( *((_QWORD *)v5 + 3) > 7u )
        v16 = *(const WCHAR **)v5;
      v18 = (const WCHAR *)(v17 + 32);
      if ( *(_QWORD *)(v17 + 56) > 7u )
        v18 = *(const WCHAR **)v18;
      if ( CompareStringOrdinal(v18, -1, v16, -1, 1) != 1 )
        goto LABEL_50;
      v19 = *(_BYTE *)(*(_QWORD *)(v17 + 16) + 25LL) == 0;
      *(_BYTE *)(a2 + 16) = 0;
      if ( !v19 )
      {
        *(_QWORD *)a2 = v17;
        goto LABEL_64;
      }
      *(_QWORD *)a2 = a3;
LABEL_30:
      *(_QWORD *)(a2 + 8) = 1;
      goto LABEL_65;
    }
    v20 = v5;
    if ( *((_QWORD *)v5 + 3) > 7u )
      v20 = *(const WCHAR **)v5;
    v21 = (const WCHAR *)(a3 + 4);
    if ( (unsigned __int64)a3[7] > 7 )
      v21 = *(const WCHAR **)v21;
    if ( CompareStringOrdinal(v21, -1, v20, -1, 1) != 1 )
    {
      *(_BYTE *)(a2 + 16) = 1;
      goto LABEL_63;
    }
    v22 = a3[2];
    if ( *((_BYTE *)v22 + 25) )
    {
      v22 = a3[1];
      if ( *((_BYTE *)v22 + 25) )
        goto LABEL_60;
      v23 = (__int64 *)a3;
      do
      {
        v24 = (__int64 **)v22;
        if ( v23 != (__int64 *)v22[2] )
          break;
        v22 = (__int64 *)v22[1];
        v23 = (__int64 *)v24;
      }
      while ( !*((_BYTE *)v22 + 25) );
    }
    else
    {
      v25 = (__int64 *)*v22;
      if ( !*(_BYTE *)(*v22 + 25) )
      {
        do
        {
          v22 = v25;
          v25 = (__int64 *)*v25;
        }
        while ( !*((_BYTE *)v25 + 25) );
      }
    }
    if ( !*((_BYTE *)v22 + 25) )
    {
      v26 = (const WCHAR *)(v22 + 4);
      if ( (unsigned __int64)v22[7] > 7 )
        v26 = *(const WCHAR **)v26;
      v27 = v5;
      if ( *((_QWORD *)v5 + 3) > 7u )
        v27 = *(const WCHAR **)v5;
      if ( CompareStringOrdinal(v27, -1, v26, -1, 1) != 1 )
        goto LABEL_50;
    }
LABEL_60:
    v19 = *((_BYTE *)a3[2] + 25) == 0;
    *(_BYTE *)(a2 + 16) = 0;
    if ( v19 )
    {
      *(_QWORD *)a2 = v22;
      goto LABEL_30;
    }
LABEL_63:
    *(_QWORD *)a2 = a3;
    goto LABEL_64;
  }
  if ( *((_QWORD *)v12 + 3) > 7u )
    v12 = *(const WCHAR **)v12;
  v13 = a4;
  if ( *((_QWORD *)a4 + 3) > 7u )
    v13 = *(const WCHAR **)a4;
  if ( CompareStringOrdinal(v13, -1, v12, -1, 1) != 1 )
  {
LABEL_50:
    sub_1800ED500(a1, &v32, v5);
    v28 = v33;
    if ( *(_BYTE *)(v33 + 25) )
      goto LABEL_56;
    v29 = (const WCHAR *)(v33 + 32);
    if ( *(_QWORD *)(v33 + 56) > 7u )
      v29 = *(const WCHAR **)v29;
    if ( *((_QWORD *)v5 + 3) > 7u )
      v5 = *(const WCHAR **)v5;
    v19 = CompareStringOrdinal(v5, -1, v29, -1, 1) == 1;
    v30 = 1;
    if ( v19 )
LABEL_56:
      v30 = 0;
    if ( v30 )
    {
      *(_QWORD *)a2 = v28;
      *(_QWORD *)(a2 + 8) = 2;
      *(_BYTE *)(a2 + 16) = 1;
      goto LABEL_65;
    }
    *(_OWORD *)a2 = v32;
    goto LABEL_16;
  }
  *(_QWORD *)a2 = a3;
  *(_QWORD *)(a2 + 8) = 1;
LABEL_16:
  *(_BYTE *)(a2 + 16) = 0;
LABEL_65:
  *(_DWORD *)(a2 + 17) = 0;
  *(_WORD *)(a2 + 21) = 0;
  *(_BYTE *)(a2 + 23) = 0;
  return a2;
}

```

## disassembly

```asm
0x18015bddc  mov     [rsp+arg_8], rbx
0x18015bde1  mov     [rsp+arg_10], rbp
0x18015bde6  mov     [rsp+arg_18], rsi
0x18015bdeb  push    rdi
0x18015bdec  push    r12
0x18015bdee  push    r13
0x18015bdf0  push    r14
0x18015bdf2  push    r15
0x18015bdf4  sub     rsp, 50h
0x18015bdf8  mov     rax, [rcx]
0x18015bdfb  xor     r13d, r13d
0x18015bdfe  mov     rdi, r9
0x18015be01  mov     r14, r8
0x18015be04  mov     rbx, rdx
0x18015be07  mov     r12, rcx
0x18015be0a  cmp     [r8+19h], r13b
0x18015be0e  jz      short loc_18015BE6C
0x18015be10  lea     rsi, [rax+10h]
0x18015be14  mov     rax, [rax+8]
0x18015be18  cmp     [rax+19h], r13b
0x18015be1c  jnz     short loc_18015BE5D
0x18015be1e  mov     rcx, [rsi]
0x18015be21  mov     r8, r9
0x18015be24  add     rcx, 20h ; ' '
0x18015be28  cmp     qword ptr [r9+18h], 7
0x18015be2d  jbe     short loc_18015BE32
0x18015be2f  mov     r8, [r9]; lpString2
0x18015be32  cmp     qword ptr [rcx+18h], 7
0x18015be37  jbe     short loc_18015BE3C
0x18015be39  mov     rcx, [rcx]; lpString1
0x18015be3c  or      r15d, 0FFFFFFFFh
0x18015be40  mov     ebp, 1
0x18015be45  mov     r9d, r15d; cchCount2
0x18015be48  mov     [rsp+78h+bIgnoreCase], ebp; bIgnoreCase
0x18015be4c  mov     edx, r15d; cchCount1
0x18015be4f  call    cs:CompareStringOrdinal
0x18015be55  cmp     eax, ebp
0x18015be57  jnz     loc_18015C015
0x18015be5d  mov     rax, [rsi]
0x18015be60  mov     [rbx], rax
0x18015be63  mov     [rbx+10h], r13b
0x18015be67  jmp     loc_18015C0A5
0x18015be6c  add     r8, 20h ; ' '
0x18015be70  cmp     r14, [rax]
0x18015be73  jnz     short loc_18015BEBD
0x18015be75  cmp     qword ptr [r8+18h], 7
0x18015be7a  jbe     short loc_18015BE7F
0x18015be7c  mov     r8, [r8]; lpString2
0x18015be7f  cmp     qword ptr [r9+18h], 7
0x18015be84  mov     rcx, rdi
0x18015be87  jbe     short loc_18015BE8C
0x18015be89  mov     rcx, [r9]; lpString1
0x18015be8c  or      r15d, 0FFFFFFFFh
0x18015be90  mov     ebp, 1
0x18015be95  mov     r9d, r15d; cchCount2
0x18015be98  mov     [rsp+78h+bIgnoreCase], ebp; bIgnoreCase
0x18015be9c  mov     edx, r15d; cchCount1
0x18015be9f  call    cs:CompareStringOrdinal
0x18015bea5  cmp     eax, ebp
0x18015bea7  jnz     loc_18015C015
0x18015bead  mov     [rbx], r14
0x18015beb0  mov     [rbx+8], rbp
0x18015beb4  mov     [rbx+10h], r13b
0x18015beb8  jmp     loc_18015C0A9
0x18015bebd  cmp     qword ptr [r8+18h], 7
0x18015bec2  jbe     short loc_18015BEC7
0x18015bec4  mov     r8, [r8]; lpString2
0x18015bec7  cmp     qword ptr [r9+18h], 7
0x18015becc  mov     rcx, rdi
0x18015becf  jbe     short loc_18015BED4
0x18015bed1  mov     rcx, [r9]; lpString1
0x18015bed4  or      r15d, 0FFFFFFFFh
0x18015bed8  mov     ebp, 1
0x18015bedd  mov     r9d, r15d; cchCount2
0x18015bee0  mov     [rsp+78h+bIgnoreCase], ebp; bIgnoreCase
0x18015bee4  mov     edx, r15d; cchCount1
0x18015bee7  call    cs:CompareStringOrdinal
0x18015beed  cmp     eax, ebp
0x18015beef  jnz     short loc_18015BF5E
0x18015bef1  lea     rcx, [rsp+78h+arg_0]
0x18015bef9  mov     [rsp+78h+arg_0], r14
0x18015bf01  call    sub_1800E46C8
0x18015bf06  cmp     qword ptr [rdi+18h], 7
0x18015bf0b  mov     r8, rdi
0x18015bf0e  mov     rsi, [rax]
0x18015bf11  jbe     short loc_18015BF16
0x18015bf13  mov     r8, [rdi]; lpString2
0x18015bf16  lea     rcx, [rsi+20h]
0x18015bf1a  cmp     qword ptr [rcx+18h], 7
0x18015bf1f  jbe     short loc_18015BF24
0x18015bf21  mov     rcx, [rcx]; lpString1
0x18015bf24  mov     r9d, r15d; cchCount2
0x18015bf27  mov     [rsp+78h+bIgnoreCase], ebp; bIgnoreCase
0x18015bf2b  mov     edx, r15d; cchCount1
0x18015bf2e  call    cs:CompareStringOrdinal
0x18015bf34  cmp     eax, ebp
0x18015bf36  jnz     loc_18015C015
0x18015bf3c  mov     rax, [rsi+10h]
0x18015bf40  cmp     [rax+19h], r13b
0x18015bf44  mov     [rbx+10h], r13b
0x18015bf48  jz      short loc_18015BF52
0x18015bf4a  mov     [rbx], rsi
0x18015bf4d  jmp     loc_18015C0A5
0x18015bf52  mov     [rbx], r14
0x18015bf55  mov     [rbx+8], rbp
0x18015bf59  jmp     loc_18015C0A9
0x18015bf5e  cmp     qword ptr [rdi+18h], 7
0x18015bf63  mov     r8, rdi
0x18015bf66  jbe     short loc_18015BF6B
0x18015bf68  mov     r8, [rdi]; lpString2
0x18015bf6b  lea     rcx, [r14+20h]
0x18015bf6f  cmp     qword ptr [rcx+18h], 7
0x18015bf74  jbe     short loc_18015BF79
0x18015bf76  mov     rcx, [rcx]; lpString1
0x18015bf79  mov     r9d, r15d; cchCount2
0x18015bf7c  mov     [rsp+78h+bIgnoreCase], ebp; bIgnoreCase
0x18015bf80  mov     edx, r15d; cchCount1
0x18015bf83  call    cs:CompareStringOrdinal
0x18015bf89  cmp     eax, ebp
0x18015bf8b  jnz     loc_18015C09E
0x18015bf91  mov     rsi, [r14+10h]
0x18015bf95  cmp     [rsi+19h], r13b
0x18015bf99  jz      short loc_18015BFC4
0x18015bf9b  mov     rsi, [r14+8]
0x18015bf9f  cmp     [rsi+19h], r13b
0x18015bfa3  jnz     loc_18015C088
0x18015bfa9  mov     rax, r14
0x18015bfac  mov     rcx, rsi
0x18015bfaf  cmp     rax, [rsi+10h]
0x18015bfb3  jnz     short loc_18015BFDC
0x18015bfb5  mov     rsi, [rsi+8]
0x18015bfb9  mov     rax, rcx
0x18015bfbc  cmp     [rsi+19h], r13b
0x18015bfc0  jz      short loc_18015BFAC
0x18015bfc2  jmp     short loc_18015BFDC
0x18015bfc4  mov     rcx, [rsi]
0x18015bfc7  cmp     [rcx+19h], r13b
0x18015bfcb  jnz     short loc_18015BFDC
0x18015bfcd  mov     rax, [rcx]
0x18015bfd0  mov     rsi, rcx
0x18015bfd3  mov     rcx, rax
0x18015bfd6  cmp     [rax+19h], r13b
0x18015bfda  jz      short loc_18015BFCD
0x18015bfdc  cmp     [rsi+19h], r13b
0x18015bfe0  jnz     loc_18015C088
0x18015bfe6  lea     r8, [rsi+20h]
0x18015bfea  cmp     qword ptr [r8+18h], 7
0x18015bfef  jbe     short loc_18015BFF4
0x18015bff1  mov     r8, [r8]; lpString2
0x18015bff4  cmp     qword ptr [rdi+18h], 7
0x18015bff9  mov     rcx, rdi
0x18015bffc  jbe     short loc_18015C001
0x18015bffe  mov     rcx, [rdi]; lpString1
0x18015c001  mov     r9d, r15d; cchCount2
0x18015c004  mov     [rsp+78h+bIgnoreCase], ebp; bIgnoreCase
0x18015c008  mov     edx, r15d; cchCount1
0x18015c00b  call    cs:CompareStringOrdinal
0x18015c011  cmp     eax, ebp
0x18015c013  jz      short loc_18015C088
0x18015c015  mov     r8, rdi
0x18015c018  lea     rdx, [rsp+78h+var_48]
0x18015c01d  mov     rcx, r12
0x18015c020  call    sub_1800ED500
0x18015c025  mov     rsi, [rsp+78h+var_38]
0x18015c02a  cmp     [rsi+19h], r13b
0x18015c02e  jnz     short loc_18015C062
0x18015c030  lea     r8, [rsi+20h]
0x18015c034  cmp     qword ptr [r8+18h], 7
0x18015c039  jbe     short loc_18015C03E
0x18015c03b  mov     r8, [r8]; lpString2
0x18015c03e  cmp     qword ptr [rdi+18h], 7
0x18015c043  jbe     short loc_18015C048
0x18015c045  mov     rdi, [rdi]
0x18015c048  mov     r9d, r15d; cchCount2
0x18015c04b  mov     [rsp+78h+bIgnoreCase], ebp; bIgnoreCase
0x18015c04f  mov     edx, r15d; cchCount1
0x18015c052  mov     rcx, rdi; lpString1
0x18015c055  call    cs:CompareStringOrdinal
0x18015c05b  cmp     eax, ebp
0x18015c05d  mov     al, bpl
0x18015c060  jnz     short loc_18015C065
0x18015c062  mov     al, r13b
0x18015c065  test    al, al
0x18015c067  jz      short loc_18015C07A
0x18015c069  mov     [rbx], rsi
0x18015c06c  mov     qword ptr [rbx+8], 2
0x18015c074  mov     [rbx+10h], bpl
0x18015c078  jmp     short loc_18015C0A9
0x18015c07a  movups  xmm0, [rsp+78h+var_48]
0x18015c07f  movdqu  xmmword ptr [rbx], xmm0
0x18015c083  jmp     loc_18015BEB4
0x18015c088  mov     rax, [r14+10h]
0x18015c08c  cmp     [rax+19h], r13b
0x18015c090  mov     [rbx+10h], r13b
0x18015c094  jnz     short loc_18015C0A2
0x18015c096  mov     [rbx], rsi
0x18015c099  jmp     loc_18015BF55
0x18015c09e  mov     [rbx+10h], bpl
0x18015c0a2  mov     [rbx], r14
0x18015c0a5  mov     [rbx+8], r13
0x18015c0a9  xor     eax, eax
0x18015c0ab  lea     r11, [rsp+78h+var_28]
0x18015c0b0  mov     rbp, [r11+40h]
0x18015c0b4  mov     rsi, [r11+48h]
0x18015c0b8  mov     [rbx+11h], eax
0x18015c0bb  mov     [rbx+15h], ax
0x18015c0bf  mov     [rbx+17h], al
0x18015c0c2  mov     rax, rbx
0x18015c0c5  mov     rbx, [r11+38h]
0x18015c0c9  mov     rsp, r11
0x18015c0cc  pop     r15
0x18015c0ce  pop     r14
0x18015c0d0  pop     r13
0x18015c0d2  pop     r12
0x18015c0d4  pop     rdi
0x18015c0d5  retn
```
