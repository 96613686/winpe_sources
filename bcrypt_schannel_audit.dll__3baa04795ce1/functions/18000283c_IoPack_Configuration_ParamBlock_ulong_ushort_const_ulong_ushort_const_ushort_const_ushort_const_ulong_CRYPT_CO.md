# IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)

- ea: `0x18000283c`
- end: `0x180002bbd`
- name: `?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z`
- size: `897`
- prototype: `unsigned int __usercall@<eax>(unsigned int@<ecx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, const unsigned __int16 *Src, const unsigned __int16 *, unsigned int, struct _CRYPT_CONTEXT_CONFIG *, struct _CRYPT_CONTEXT_FUNCTION_CONFIG *, size_t Size, unsigned __int8 *, void *, unsigned int *, unsigned __int8 *)`
- caller_count: `17`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180002bd0`
- `0x18000997c`
- `0x180012f40`
- `0x180013330`
- `0x180013510`
- `0x180013720`
- `0x1800138c0`
- `0x1800186e0`
- `0x180018860`
- `0x180018a00`
- `0x180018b80`
- `0x180018e90`
- `0x180019070`
- `0x1800192a0`
- `0x1800195e0`
- `0x180019770`
- `0x180019b1c`

## callees

- `0x180002018`
- `0x18000283c`
- `0x180003d20`
- `0x180004120`
- `0x18001a2bc`
- `0x18001b79d`

## pseudocode

```c
unsigned int __fastcall IoPack_Configuration_ParamBlock(
        unsigned int a1,
        const unsigned __int16 *a2,
        int a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *Src,
        unsigned __int16 *a6,
        unsigned int a7,
        struct _CRYPT_CONTEXT_CONFIG *a8,
        struct _CRYPT_CONTEXT_FUNCTION_CONFIG *a9,
        size_t Size,
        unsigned __int8 *a11,
        void *a12,
        unsigned int *a13,
        unsigned __int8 *a14)
{
  unsigned int v17; // edi
  unsigned __int8 *v18; // rbx
  unsigned __int8 *v19; // r12
  const unsigned __int16 *v20; // r15
  unsigned __int8 *v21; // r14
  unsigned __int8 *v22; // r15
  char *v23; // rsi
  unsigned __int8 *v24; // r13
  int v25; // edx
  __int64 *v26; // rcx
  __int64 v27; // rax
  unsigned __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // r12
  __int64 v31; // r14
  __int64 v32; // r15
  __int64 v33; // rsi
  unsigned int result; // eax
  unsigned __int64 v35; // r15
  unsigned int v36; // edi
  unsigned int v37; // esi
  unsigned int v38; // esi
  int v39; // r8d
  unsigned __int8 *v40; // r10
  ULONG dwFlags; // r8d
  int v42; // r8d
  _DWORD *v43; // r10
  unsigned int v44; // [rsp+20h] [rbp-10h] BYREF
  unsigned __int64 v45; // [rsp+28h] [rbp-8h]
  unsigned __int8 *v47; // [rsp+78h] [rbp+48h] BYREF
  int v48; // [rsp+80h] [rbp+50h]

  v48 = a3;
  v45 = 0;
  v44 = 0;
  v17 = 104;
  if ( a13 )
    *a13 = 0;
  v18 = a14;
  if ( a2 )
  {
    LODWORD(v47) = 0;
    v35 = (unsigned __int64)(a14 + 104) & -(__int64)(a14 != 0);
    v45 = v35;
    result = SzString_CchLength(a2, (unsigned int *)&v47, 0);
    if ( result )
      return result;
    v36 = (2 * (_DWORD)v47 + 9) & 0xFFFFFFF8;
    if ( v35 )
      memcpy_0(
        (void *)((unsigned __int64)(v18 + 104) & -(__int64)(v18 != 0)),
        a2,
        2LL * (unsigned int)((_DWORD)v47 + 1));
    v17 = v36 + 104;
  }
  v19 = 0;
  if ( a4 )
  {
    if ( v18 )
      v19 = &v18[v17];
    LODWORD(v47) = 0;
    result = SzString_CchLength(a4, (unsigned int *)&v47, 0);
    if ( result )
      return result;
    v37 = (2 * (_DWORD)v47 + 9) & 0xFFFFFFF8;
    if ( v19 )
      memcpy_0(v19, a4, 2LL * (unsigned int)((_DWORD)v47 + 1));
    v17 += v37;
  }
  v20 = Src;
  v21 = 0;
  if ( Src )
  {
    if ( v18 )
      v21 = &v18[v17];
    LODWORD(v47) = 0;
    result = SzString_CchLength(Src, (unsigned int *)&v47, 0);
    if ( result )
      return result;
    v38 = (2 * (_DWORD)v47 + 9) & 0xFFFFFFF8;
    if ( v21 )
      memcpy_0(v21, v20, 2LL * (unsigned int)((_DWORD)v47 + 1));
    v17 += v38;
  }
  v22 = 0;
  if ( !a6 )
    goto LABEL_7;
  if ( v18 )
    v22 = &v18[v17];
  result = IoCopy_SzString(a6, &v44, v22);
  if ( !result )
  {
    v17 += v44;
LABEL_7:
    v23 = 0;
    if ( a8 )
    {
      if ( v18 )
        v23 = (char *)&v18[v17];
      if ( !(unsigned int)ValidateConfigurationFlags(0x10010u, a1, a8->dwFlags) )
        return 1004;
      if ( v23 )
        *(_DWORD *)v23 = v39;
      v17 += 8;
    }
    v47 = 0;
    if ( !a9 )
    {
LABEL_9:
      v24 = 0;
      if ( a11 )
      {
        if ( v18 )
        {
          v24 = &v18[v17];
          if ( v24 )
            memcpy_0(&v18[v17], a11, (unsigned int)Size);
        }
        v25 = Size;
        v17 += (Size + 7) & 0xFFFFFFF8;
      }
      else
      {
        v25 = Size;
      }
      if ( v18 )
      {
        v26 = (__int64 *)(v18 + 72);
        *((_DWORD *)v18 + 2) = a1;
        *((_DWORD *)v18 + 6) = v48;
        *((_DWORD *)v18 + 14) = a7;
        *((_QWORD *)v18 + 9) = v47;
        *((_QWORD *)v18 + 12) = a12;
        v27 = -1;
        *((_DWORD *)v18 + 20) = v25;
        v28 = v45;
        *((_QWORD *)v18 + 8) = v23;
        *((_QWORD *)v18 + 11) = v24;
        if ( v28 )
          v29 = v28 - (_QWORD)v18;
        else
          v29 = -1;
        *((_QWORD *)v18 + 2) = v29;
        if ( v19 )
          v30 = v19 - v18;
        else
          v30 = -1;
        *((_QWORD *)v18 + 4) = v30;
        if ( v21 )
          v31 = v21 - v18;
        else
          v31 = -1;
        *((_QWORD *)v18 + 5) = v31;
        if ( v22 )
          v32 = v22 - v18;
        else
          v32 = -1;
        *((_QWORD *)v18 + 6) = v32;
        if ( v23 )
          v33 = v23 - (char *)v18;
        else
          v33 = -1;
        *((_QWORD *)v18 + 8) = v33;
        if ( *v26 )
          v27 = *v26 - (_QWORD)v18;
        *v26 = v27;
        IoPack_Buffer((unsigned __int8 **)v18 + 11, v18);
      }
      if ( a13 )
        *a13 = v17;
      return 0;
    }
    if ( v18 )
      v40 = &v18[v17];
    else
      v40 = 0;
    dwFlags = a9->dwFlags;
    v47 = v40;
    if ( (unsigned int)ValidateConfigurationFlags(0x10030u, 0, dwFlags) )
    {
      if ( v43 )
        *v43 = v42;
      v17 += 8;
      goto LABEL_9;
    }
    return 1004;
  }
  return result;
}

```

## disassembly

```asm
0x18000283c  mov     [rsp-38h+arg_18], rbx
0x180002841  mov     [rsp-38h+arg_10], r8d
0x180002846  mov     [rsp-38h+arg_0], ecx
0x18000284a  push    rbp
0x18000284b  push    rsi
0x18000284c  push    rdi
0x18000284d  push    r12
0x18000284f  push    r13
0x180002851  push    r14
0x180002853  push    r15
0x180002855  mov     rbp, rsp
0x180002858  sub     rsp, 30h
0x18000285c  mov     rax, [rbp+arg_60]
0x180002863  mov     r14, r9
0x180002866  mov     [rbp+var_8], 0
0x18000286e  mov     rsi, rdx
0x180002871  mov     [rbp+var_10], 0
0x180002878  mov     r13d, ecx
0x18000287b  mov     edi, 68h ; 'h'
0x180002880  test    rax, rax
0x180002883  jz      short loc_18000288B
0x180002885  mov     dword ptr [rax], 0
0x18000288b  mov     rbx, [rbp+arg_68]
0x180002892  test    rsi, rsi
0x180002895  jnz     loc_1800029E1
0x18000289b  xor     r12d, r12d
0x18000289e  test    r14, r14
0x1800028a1  jnz     loc_180002A3B
0x1800028a7  mov     r15, [rbp+Src]
0x1800028ab  xor     r14d, r14d
0x1800028ae  test    r15, r15
0x1800028b1  jnz     loc_180002A9A
0x1800028b7  mov     rcx, [rbp+arg_28]; Src
0x1800028bb  xor     r15d, r15d
0x1800028be  test    rcx, rcx
0x1800028c1  jnz     loc_180002AF0
0x1800028c7  mov     rax, [rbp+arg_38]
0x1800028cb  xor     esi, esi
0x1800028cd  test    rax, rax
0x1800028d0  jnz     loc_180002B17
0x1800028d6  mov     rax, [rbp+arg_40]
0x1800028dd  mov     [rbp+arg_8], 0
0x1800028e5  test    rax, rax
0x1800028e8  jnz     loc_180002B45
0x1800028ee  mov     rdx, [rbp+arg_50]; Src
0x1800028f5  xor     r13d, r13d
0x1800028f8  test    rdx, rdx
0x1800028fb  jnz     loc_180002B86
0x180002901  mov     edx, dword ptr [rbp+Size]
0x180002907  test    rbx, rbx
0x18000290a  jz      loc_1800029A4
0x180002910  mov     eax, [rbp+arg_0]
0x180002913  lea     rcx, [rbx+48h]
0x180002917  mov     [rbx+8], eax
0x18000291a  mov     eax, [rbp+arg_10]
0x18000291d  mov     [rbx+18h], eax
0x180002920  mov     eax, [rbp+arg_30]
0x180002923  mov     [rbx+38h], eax
0x180002926  mov     rax, [rbp+arg_8]
0x18000292a  mov     [rcx], rax
0x18000292d  mov     rax, [rbp+arg_58]
0x180002934  mov     [rbx+60h], rax
0x180002938  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000293c  mov     [rbx+50h], edx
0x18000293f  mov     rdx, [rbp+var_8]
0x180002943  mov     [rbx+40h], rsi
0x180002947  mov     [rbx+58h], r13
0x18000294b  test    rdx, rdx
0x18000294e  jz      short loc_1800029CD
0x180002950  sub     rdx, rbx
0x180002953  mov     [rbx+10h], rdx
0x180002957  test    r12, r12
0x18000295a  jz      short loc_1800029D2
0x18000295c  sub     r12, rbx
0x18000295f  mov     [rbx+20h], r12
0x180002963  test    r14, r14
0x180002966  jz      short loc_1800029D7
0x180002968  sub     r14, rbx
0x18000296b  mov     [rbx+28h], r14
0x18000296f  test    r15, r15
0x180002972  jz      short loc_1800029DC
0x180002974  sub     r15, rbx
0x180002977  mov     [rbx+30h], r15
0x18000297b  test    rsi, rsi
0x18000297e  jnz     loc_180002BB5
0x180002984  mov     rsi, rax
0x180002987  mov     [rbx+40h], rsi
0x18000298b  cmp     qword ptr [rcx], 0
0x18000298f  jnz     loc_180002A8F
0x180002995  mov     [rcx], rax
0x180002998  mov     rdx, rbx; unsigned __int8 *
0x18000299b  lea     rcx, [rbx+58h]; unsigned __int8 **
0x18000299f  call    ?IoPack_Buffer@@YAXPEAPEAEPEAE@Z; IoPack_Buffer(uchar * *,uchar *)
0x1800029a4  mov     rax, [rbp+arg_60]
0x1800029ab  test    rax, rax
0x1800029ae  jz      short loc_1800029B2
0x1800029b0  mov     [rax], edi
0x1800029b2  xor     eax, eax
0x1800029b4  mov     rbx, [rsp+30h+arg_18]
0x1800029bc  add     rsp, 30h
0x1800029c0  pop     r15
0x1800029c2  pop     r14
0x1800029c4  pop     r13
0x1800029c6  pop     r12
0x1800029c8  pop     rdi
0x1800029c9  pop     rsi
0x1800029ca  pop     rbp
0x1800029cb  retn
0x1800029cd  mov     rdx, rax
0x1800029d0  jmp     short loc_180002953
0x1800029d2  mov     r12, rax
0x1800029d5  jmp     short loc_18000295F
0x1800029d7  mov     r14, rax
0x1800029da  jmp     short loc_18000296B
0x1800029dc  mov     r15, rax
0x1800029df  jmp     short loc_180002977
0x1800029e1  lea     rcx, [rbx+68h]
0x1800029e5  mov     dword ptr [rbp+arg_8], 0
0x1800029ec  mov     rax, rbx
0x1800029ef  lea     rdx, [rbp+arg_8]; unsigned int *
0x1800029f3  neg     rax
0x1800029f6  sbb     r15, r15
0x1800029f9  xor     r8d, r8d; unsigned int
0x1800029fc  and     r15, rcx
0x1800029ff  mov     rcx, rsi; unsigned __int16 *
0x180002a02  mov     [rbp+var_8], r15
0x180002a06  call    ?SzString_CchLength@@YAKPEBGPEAKK@Z; SzString_CchLength(ushort const *,ulong *,ulong)
0x180002a0b  test    eax, eax
0x180002a0d  jnz     short loc_1800029B4
0x180002a0f  mov     eax, dword ptr [rbp+arg_8]
0x180002a12  lea     edi, ds:9[rax*2]
0x180002a19  and     edi, 0FFFFFFF8h
0x180002a1c  test    r15, r15
0x180002a1f  jz      short loc_180002A33
0x180002a21  lea     r8d, [rax+1]
0x180002a25  mov     rdx, rsi; Src
0x180002a28  add     r8, r8; Size
0x180002a2b  mov     rcx, r15; void *
0x180002a2e  call    memcpy_0
0x180002a33  add     edi, 68h ; 'h'
0x180002a36  jmp     loc_18000289B
0x180002a3b  test    rbx, rbx
0x180002a3e  jz      short loc_180002A46
0x180002a40  mov     r12d, edi
0x180002a43  add     r12, rbx
0x180002a46  xor     r8d, r8d; unsigned int
0x180002a49  mov     dword ptr [rbp+arg_8], 0
0x180002a50  lea     rdx, [rbp+arg_8]; unsigned int *
0x180002a54  mov     rcx, r14; unsigned __int16 *
0x180002a57  call    ?SzString_CchLength@@YAKPEBGPEAKK@Z; SzString_CchLength(ushort const *,ulong *,ulong)
0x180002a5c  test    eax, eax
0x180002a5e  jnz     loc_1800029B4
0x180002a64  mov     eax, dword ptr [rbp+arg_8]
0x180002a67  lea     esi, ds:9[rax*2]
0x180002a6e  and     esi, 0FFFFFFF8h
0x180002a71  test    r12, r12
0x180002a74  jz      short loc_180002A88
0x180002a76  lea     r8d, [rax+1]
0x180002a7a  mov     rdx, r14; Src
0x180002a7d  add     r8, r8; Size
0x180002a80  mov     rcx, r12; void *
0x180002a83  call    memcpy_0
0x180002a88  add     edi, esi
0x180002a8a  jmp     loc_1800028A7
0x180002a8f  mov     rax, [rcx]
0x180002a92  sub     rax, rbx
0x180002a95  jmp     loc_180002995
0x180002a9a  test    rbx, rbx
0x180002a9d  jnz     short loc_180002AE8
0x180002a9f  xor     r8d, r8d; unsigned int
0x180002aa2  mov     dword ptr [rbp+arg_8], 0
0x180002aa9  lea     rdx, [rbp+arg_8]; unsigned int *
0x180002aad  mov     rcx, r15; unsigned __int16 *
0x180002ab0  call    ?SzString_CchLength@@YAKPEBGPEAKK@Z; SzString_CchLength(ushort const *,ulong *,ulong)
0x180002ab5  test    eax, eax
0x180002ab7  jnz     loc_1800029B4
0x180002abd  mov     eax, dword ptr [rbp+arg_8]
0x180002ac0  lea     esi, ds:9[rax*2]
0x180002ac7  and     esi, 0FFFFFFF8h
0x180002aca  test    r14, r14
0x180002acd  jz      short loc_180002AE1
0x180002acf  lea     r8d, [rax+1]
0x180002ad3  mov     rdx, r15; Src
0x180002ad6  add     r8, r8; Size
0x180002ad9  mov     rcx, r14; void *
0x180002adc  call    memcpy_0
0x180002ae1  add     edi, esi
0x180002ae3  jmp     loc_1800028B7
0x180002ae8  mov     r14d, edi
0x180002aeb  add     r14, rbx
0x180002aee  jmp     short loc_180002A9F
0x180002af0  test    rbx, rbx
0x180002af3  jz      short loc_180002AFB
0x180002af5  mov     r15d, edi
0x180002af8  add     r15, rbx
0x180002afb  mov     r8, r15; unsigned __int8 *
0x180002afe  lea     rdx, [rbp+var_10]; unsigned int *
0x180002b02  call    ?IoCopy_SzString@@YAKPEAGPEAKPEAE@Z; IoCopy_SzString(ushort *,ulong *,uchar *)
0x180002b07  test    eax, eax
0x180002b09  jnz     loc_1800029B4
0x180002b0f  add     edi, [rbp+var_10]
0x180002b12  jmp     loc_1800028C7
0x180002b17  test    rbx, rbx
0x180002b1a  jz      short loc_180002B21
0x180002b1c  mov     esi, edi
0x180002b1e  add     rsi, rbx
0x180002b21  mov     r8d, [rax]; unsigned int
0x180002b24  mov     edx, r13d; unsigned int
0x180002b27  mov     ecx, 10010h; unsigned int
0x180002b2c  call    ?ValidateConfigurationFlags@@YAHKKK@Z; ValidateConfigurationFlags(ulong,ulong,ulong)
0x180002b31  test    eax, eax
0x180002b33  jz      short loc_180002B7C
0x180002b35  test    rsi, rsi
0x180002b38  jz      short loc_180002B3D
0x180002b3a  mov     [rsi], r8d
0x180002b3d  add     edi, 8
0x180002b40  jmp     loc_1800028D6
0x180002b45  test    rbx, rbx
0x180002b48  jz      short loc_180002B52
0x180002b4a  mov     r10d, edi
0x180002b4d  add     r10, rbx
0x180002b50  jmp     short loc_180002B55
0x180002b52  xor     r10d, r10d
0x180002b55  mov     r8d, [rax]; unsigned int
0x180002b58  xor     edx, edx; unsigned int
0x180002b5a  mov     ecx, 10030h; unsigned int
0x180002b5f  mov     [rbp+arg_8], r10
0x180002b63  call    ?ValidateConfigurationFlags@@YAHKKK@Z; ValidateConfigurationFlags(ulong,ulong,ulong)
0x180002b68  test    eax, eax
0x180002b6a  jz      short loc_180002B7C
0x180002b6c  test    r10, r10
0x180002b6f  jz      short loc_180002B74
0x180002b71  mov     [r10], r8d
0x180002b74  add     edi, 8
0x180002b77  jmp     loc_1800028EE
0x180002b7c  mov     eax, 3ECh
0x180002b81  jmp     loc_1800029B4
0x180002b86  test    rbx, rbx
0x180002b89  jz      short loc_180002BA2
0x180002b8b  mov     r13d, edi
0x180002b8e  add     r13, rbx
0x180002b91  jz      short loc_180002BA2
0x180002b93  mov     r8d, dword ptr [rbp+Size]; Size
0x180002b9a  mov     rcx, r13; void *
0x180002b9d  call    memcpy_0
0x180002ba2  mov     edx, dword ptr [rbp+Size]
0x180002ba8  lea     eax, [rdx+7]
0x180002bab  and     eax, 0FFFFFFF8h
0x180002bae  add     edi, eax
0x180002bb0  jmp     loc_180002907
0x180002bb5  sub     rsi, rbx
0x180002bb8  jmp     loc_180002987
```
