# CMetadataIPTCReaderWriter::CreateVectorFromVariants(CMetadataIPTCReaderWriter::DataSet *,tagPROPVARIANT *)

- ea: `0x1800ac94c`
- end: `0x1800acb5b`
- name: `?CreateVectorFromVariants@CMetadataIPTCReaderWriter@@AEAAJPEAUDataSet@1@PEAUtagPROPVARIANT@@@Z`
- size: `527`
- prototype: `int(CMetadataIPTCReaderWriter *__hidden this, struct CMetadataIPTCReaderWriter::DataSet *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004e420`
- `0x1801ac060`

## callees

- `0x1800ac94c`
- `0x1800bd9d4`
- `0x1800e6af4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ac997`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aca60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ac997`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aca60`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800aca41`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800aca41`

## pseudocode

```c
__int64 __fastcall CMetadataIPTCReaderWriter::CreateVectorFromVariants(
        CMetadataIPTCReaderWriter *this,
        struct CMetadataIPTCReaderWriter::DataSet *a2,
        PROPVARIANT *a3)
{
  struct CMetadataIPTCReaderWriter::DataSet *v4; // rsi
  struct CMetadataIPTCReaderWriter::DataSet *v5; // rax
  unsigned int i; // ebx
  BYTE *v7; // rax
  unsigned int v8; // ebp
  int v9; // ebx
  _WORD *v10; // rax
  __int64 v11; // rdx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rdi
  _WORD *v15; // r8
  unsigned __int64 v16; // rdi
  _WORD *v17; // rcx
  __int64 v18; // rax
  _WORD *v19; // rcx

  v4 = a2;
  v5 = a2;
  for ( i = 0; v5; ++i )
    v5 = (struct CMetadataIPTCReaderWriter::DataSet *)*((_QWORD *)v5 + 7);
  *(_OWORD *)a3 = 0;
  a3[2] = 0;
  if ( is_mul_ok(i, 8u) )
  {
    v7 = (BYTE *)CoTaskMemAlloc(8LL * i);
    a3[2] = v7;
    if ( v7 )
    {
      memset_0(v7, 0, 8LL * i);
      *((_DWORD *)a3 + 2) = i;
      v8 = 0;
      v9 = 0;
      *(_WORD *)a3 = 4127;
      while ( 1 )
      {
        if ( !v4 )
          return (unsigned int)v9;
        v10 = (_WORD *)*((_QWORD *)v4 + 2);
        if ( v10 )
          break;
LABEL_28:
        v4 = (struct CMetadataIPTCReaderWriter::DataSet *)*((_QWORD *)v4 + 7);
        ++v8;
      }
      v11 = 0x3FFFFFFF;
      do
      {
        if ( !*v10 )
          break;
        ++v10;
        --v11;
      }
      while ( v11 );
      v9 = v11 == 0 ? 0x80070057 : 0;
      if ( !v11 )
        goto LABEL_13;
      v12 = (2 * (0x3FFFFFFF - v11)) & -(__int64)(v11 != 0);
      v13 = v12 + 2;
      if ( v12 + 2 < v12 )
        goto LABEL_12;
      *((_QWORD *)a3[2] + v8) = CoTaskMemAlloc(v12 + 2);
      v15 = (_WORD *)*((_QWORD *)a3[2] + v8);
      if ( !v15 )
        goto LABEL_34;
      v16 = v13 >> 1;
      if ( v16 )
      {
        if ( v16 > 0x7FFFFFFF )
        {
          v9 = -2147024809;
          *v15 = 0;
        }
        else
        {
          v17 = (_WORD *)*((_QWORD *)v4 + 2);
          v18 = 2147483646;
          do
          {
            if ( !v18 )
              break;
            if ( !*v17 )
              break;
            *v15++ = *v17++;
            --v18;
            --v16;
          }
          while ( v16 );
          v19 = v15 - 1;
          if ( v16 )
            v19 = v15;
          v9 = v16 == 0 ? 0x8007007A : 0;
          *v19 = 0;
          if ( v16 )
          {
LABEL_27:
            if ( v9 < 0 )
              goto LABEL_15;
            goto LABEL_28;
          }
        }
      }
      else
      {
        v9 = -2147024809;
      }
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(v9);
      goto LABEL_27;
    }
LABEL_34:
    v9 = -2147024882;
  }
  else
  {
LABEL_12:
    v9 = -2147024362;
  }
LABEL_13:
  if ( (_DWORD)g_doStackCaptures )
    DoStackCapture(v9);
LABEL_15:
  PropVariantClear(a3);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800ac94c  push    rbx
0x1800ac94e  push    rbp
0x1800ac94f  push    rsi
0x1800ac950  push    rdi
0x1800ac951  push    r14
0x1800ac953  push    r15
0x1800ac955  sub     rsp, 28h
0x1800ac959  xor     r15d, r15d
0x1800ac95c  mov     r14, r8
0x1800ac95f  mov     rsi, rdx
0x1800ac962  mov     rax, rdx
0x1800ac965  mov     ebx, r15d
0x1800ac968  test    rdx, rdx
0x1800ac96b  jnz     loc_1800ACB2A
0x1800ac971  xor     eax, eax
0x1800ac973  mov     ecx, ebx
0x1800ac975  xorps   xmm0, xmm0
0x1800ac978  movups  xmmword ptr [r8], xmm0
0x1800ac97c  mov     [r8+10h], rax
0x1800ac980  mov     eax, 8
0x1800ac985  mul     rcx
0x1800ac988  mov     rdi, rax
0x1800ac98b  test    rdx, rdx
0x1800ac98e  jnz     loc_1800ACA2C
0x1800ac994  mov     rcx, rax; cb
0x1800ac997  call    cs:__imp_CoTaskMemAlloc
0x1800ac99e  nop     dword ptr [rax+rax+00h]
0x1800ac9a3  mov     [r14+10h], rax
0x1800ac9a7  test    rax, rax
0x1800ac9aa  jz      loc_1800ACB3A
0x1800ac9b0  mov     r8, rdi; Size
0x1800ac9b3  xor     edx, edx; Val
0x1800ac9b5  mov     rcx, rax; void *
0x1800ac9b8  call    memset_0
0x1800ac9bd  mov     [r14+8], ebx
0x1800ac9c1  mov     ebp, r15d
0x1800ac9c4  mov     ebx, r15d
0x1800ac9c7  mov     word ptr [r14], 101Fh
0x1800ac9cd  mov     eax, ebx
0x1800ac9cf  test    rsi, rsi
0x1800ac9d2  jz      loc_1800ACB1D
0x1800ac9d8  mov     rax, [rsi+10h]
0x1800ac9dc  test    rax, rax
0x1800ac9df  jz      loc_1800ACAF4
0x1800ac9e5  mov     edx, 3FFFFFFFh
0x1800ac9ea  cmp     [rax], r15w
0x1800ac9ee  jz      short loc_1800AC9FA
0x1800ac9f0  add     rax, 2
0x1800ac9f4  sub     rdx, 1
0x1800ac9f8  jnz     short loc_1800AC9EA
0x1800ac9fa  mov     rax, rdx
0x1800ac9fd  neg     rax
0x1800aca00  sbb     ebx, ebx
0x1800aca02  not     ebx
0x1800aca04  and     ebx, 80070057h
0x1800aca0a  test    rdx, rdx
0x1800aca0d  jz      short loc_1800ACA31
0x1800aca0f  mov     ecx, 3FFFFFFFh
0x1800aca14  sub     rcx, rdx
0x1800aca17  add     rcx, rcx
0x1800aca1a  neg     rdx
0x1800aca1d  sbb     rax, rax
0x1800aca20  and     rax, rcx
0x1800aca23  lea     rdi, [rax+2]
0x1800aca27  cmp     rdi, rax
0x1800aca2a  jnb     short loc_1800ACA5D
0x1800aca2c  mov     ebx, 80070216h
0x1800aca31  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800aca38  jnz     loc_1800ACB11
0x1800aca3e  mov     rcx, r14; pvar
0x1800aca41  call    cs:__imp_PropVariantClear
0x1800aca48  nop     dword ptr [rax+rax+00h]
0x1800aca4d  mov     eax, ebx
0x1800aca4f  add     rsp, 28h
0x1800aca53  pop     r15
0x1800aca55  pop     r14
0x1800aca57  pop     rdi
0x1800aca58  pop     rsi
0x1800aca59  pop     rbp
0x1800aca5a  pop     rbx
0x1800aca5b  retn
0x1800aca5d  mov     rcx, rdi; cb
0x1800aca60  call    cs:__imp_CoTaskMemAlloc
0x1800aca67  nop     dword ptr [rax+rax+00h]
0x1800aca6c  mov     rcx, [r14+10h]
0x1800aca70  mov     edx, ebp
0x1800aca72  mov     [rcx+rdx*8], rax
0x1800aca76  mov     rax, [r14+10h]
0x1800aca7a  mov     r8, [rax+rdx*8]
0x1800aca7e  test    r8, r8
0x1800aca81  jz      loc_1800ACB3A
0x1800aca87  shr     rdi, 1
0x1800aca8a  jz      loc_1800ACB4B
0x1800aca90  cmp     rdi, 7FFFFFFFh
0x1800aca97  ja      loc_1800ACB44
0x1800aca9d  mov     rcx, [rsi+10h]
0x1800acaa1  mov     eax, 7FFFFFFEh
0x1800acaa6  test    rax, rax
0x1800acaa9  jz      short loc_1800ACAC8
0x1800acaab  movzx   edx, word ptr [rcx]
0x1800acaae  test    dx, dx
0x1800acab1  jz      short loc_1800ACAC8
0x1800acab3  mov     [r8], dx
0x1800acab7  add     rcx, 2
0x1800acabb  add     r8, 2
0x1800acabf  dec     rax
0x1800acac2  sub     rdi, 1
0x1800acac6  jnz     short loc_1800ACAA6
0x1800acac8  test    rdi, rdi
0x1800acacb  lea     rcx, [r8-2]
0x1800acacf  mov     rax, rdi
0x1800acad2  cmovnz  rcx, r8
0x1800acad6  neg     rax
0x1800acad9  sbb     ebx, ebx
0x1800acadb  not     ebx
0x1800acadd  and     ebx, 8007007Ah
0x1800acae3  mov     [rcx], r15w
0x1800acae7  test    rdi, rdi
0x1800acaea  jz      short loc_1800ACAFF
0x1800acaec  test    ebx, ebx
0x1800acaee  js      loc_1800ACA3E
0x1800acaf4  mov     rsi, [rsi+38h]
0x1800acaf8  inc     ebp
0x1800acafa  jmp     loc_1800AC9CD
0x1800acaff  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800acb06  jz      short loc_1800ACAEC
0x1800acb08  mov     ecx, ebx; int
0x1800acb0a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800acb0f  jmp     short loc_1800ACAEC
0x1800acb11  mov     ecx, ebx; int
0x1800acb13  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800acb18  jmp     loc_1800ACA3E
0x1800acb1d  test    eax, eax
0x1800acb1f  jns     loc_1800ACA4D
0x1800acb25  jmp     loc_1800ACA3E
0x1800acb2a  mov     rax, [rax+38h]
0x1800acb2e  inc     ebx
0x1800acb30  test    rax, rax
0x1800acb33  jnz     short loc_1800ACB2A
0x1800acb35  jmp     loc_1800AC971
0x1800acb3a  mov     ebx, 8007000Eh
0x1800acb3f  jmp     loc_1800ACA31
0x1800acb44  mov     ebx, 80070057h
0x1800acb49  jmp     short loc_1800ACB55
0x1800acb4b  mov     ebx, 80070057h
0x1800acb50  test    rdi, rdi
0x1800acb53  jz      short loc_1800ACAFF
0x1800acb55  mov     [r8], r15w
0x1800acb59  jmp     short loc_1800ACAFF
```
