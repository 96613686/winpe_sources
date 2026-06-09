# CMetadataIPTCReaderWriter::CreateVectorFromVariants(CMetadataIPTCReaderWriter::DataSet *,tagPROPVARIANT *)

- ea: `0x1800aa990`
- end: `0x1800aab8c`
- name: `?CreateVectorFromVariants@CMetadataIPTCReaderWriter@@AEAAJPEAUDataSet@1@PEAUtagPROPVARIANT@@@Z`
- size: `508`
- prototype: `int(CMetadataIPTCReaderWriter *__hidden this, struct CMetadataIPTCReaderWriter::DataSet *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800224b0`
- `0x1801a8bc0`

## callees

- `0x1800aa990`
- `0x1800bb784`
- `0x1800e3c04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aa9db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aaa97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aa9db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aaa97`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800aaa7f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800aaa7f`

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
0x1800aa990  push    rbx
0x1800aa992  push    rbp
0x1800aa993  push    rsi
0x1800aa994  push    rdi
0x1800aa995  push    r14
0x1800aa997  push    r15
0x1800aa999  sub     rsp, 28h
0x1800aa99d  xor     r15d, r15d
0x1800aa9a0  mov     r14, r8
0x1800aa9a3  mov     rsi, rdx
0x1800aa9a6  mov     rax, rdx
0x1800aa9a9  mov     ebx, r15d
0x1800aa9ac  test    rdx, rdx
0x1800aa9af  jnz     loc_1800AAB5B
0x1800aa9b5  xor     eax, eax
0x1800aa9b7  mov     ecx, ebx
0x1800aa9b9  xorps   xmm0, xmm0
0x1800aa9bc  movups  xmmword ptr [r8], xmm0
0x1800aa9c0  mov     [r8+10h], rax
0x1800aa9c4  mov     eax, 8
0x1800aa9c9  mul     rcx
0x1800aa9cc  mov     rdi, rax
0x1800aa9cf  test    rdx, rdx
0x1800aa9d2  jnz     loc_1800AAA6A
0x1800aa9d8  mov     rcx, rax; cb
0x1800aa9db  call    cs:__imp_CoTaskMemAlloc
0x1800aa9e1  mov     [r14+10h], rax
0x1800aa9e5  test    rax, rax
0x1800aa9e8  jz      loc_1800AAB6B
0x1800aa9ee  mov     r8, rdi; Size
0x1800aa9f1  xor     edx, edx; Val
0x1800aa9f3  mov     rcx, rax; void *
0x1800aa9f6  call    memset_0
0x1800aa9fb  mov     [r14+8], ebx
0x1800aa9ff  mov     ebp, r15d
0x1800aaa02  mov     ebx, r15d
0x1800aaa05  mov     word ptr [r14], 101Fh
0x1800aaa0b  mov     eax, ebx
0x1800aaa0d  test    rsi, rsi
0x1800aaa10  jz      loc_1800AAB4E
0x1800aaa16  mov     rax, [rsi+10h]
0x1800aaa1a  test    rax, rax
0x1800aaa1d  jz      loc_1800AAB25
0x1800aaa23  mov     edx, 3FFFFFFFh
0x1800aaa28  cmp     [rax], r15w
0x1800aaa2c  jz      short loc_1800AAA38
0x1800aaa2e  add     rax, 2
0x1800aaa32  sub     rdx, 1
0x1800aaa36  jnz     short loc_1800AAA28
0x1800aaa38  mov     rax, rdx
0x1800aaa3b  neg     rax
0x1800aaa3e  sbb     ebx, ebx
0x1800aaa40  not     ebx
0x1800aaa42  and     ebx, 80070057h
0x1800aaa48  test    rdx, rdx
0x1800aaa4b  jz      short loc_1800AAA6F
0x1800aaa4d  mov     ecx, 3FFFFFFFh
0x1800aaa52  sub     rcx, rdx
0x1800aaa55  add     rcx, rcx
0x1800aaa58  neg     rdx
0x1800aaa5b  sbb     rax, rax
0x1800aaa5e  and     rax, rcx
0x1800aaa61  lea     rdi, [rax+2]
0x1800aaa65  cmp     rdi, rax
0x1800aaa68  jnb     short loc_1800AAA94
0x1800aaa6a  mov     ebx, 80070216h
0x1800aaa6f  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800aaa76  jnz     loc_1800AAB42
0x1800aaa7c  mov     rcx, r14; pvar
0x1800aaa7f  call    cs:__imp_PropVariantClear
0x1800aaa85  mov     eax, ebx
0x1800aaa87  add     rsp, 28h
0x1800aaa8b  pop     r15
0x1800aaa8d  pop     r14
0x1800aaa8f  pop     rdi
0x1800aaa90  pop     rsi
0x1800aaa91  pop     rbp
0x1800aaa92  pop     rbx
0x1800aaa93  retn
0x1800aaa94  mov     rcx, rdi; cb
0x1800aaa97  call    cs:__imp_CoTaskMemAlloc
0x1800aaa9d  mov     rcx, [r14+10h]
0x1800aaaa1  mov     edx, ebp
0x1800aaaa3  mov     [rcx+rdx*8], rax
0x1800aaaa7  mov     rax, [r14+10h]
0x1800aaaab  mov     r8, [rax+rdx*8]
0x1800aaaaf  test    r8, r8
0x1800aaab2  jz      loc_1800AAB6B
0x1800aaab8  shr     rdi, 1
0x1800aaabb  jz      loc_1800AAB7C
0x1800aaac1  cmp     rdi, 7FFFFFFFh
0x1800aaac8  ja      loc_1800AAB75
0x1800aaace  mov     rcx, [rsi+10h]
0x1800aaad2  mov     eax, 7FFFFFFEh
0x1800aaad7  test    rax, rax
0x1800aaada  jz      short loc_1800AAAF9
0x1800aaadc  movzx   edx, word ptr [rcx]
0x1800aaadf  test    dx, dx
0x1800aaae2  jz      short loc_1800AAAF9
0x1800aaae4  mov     [r8], dx
0x1800aaae8  add     rcx, 2
0x1800aaaec  add     r8, 2
0x1800aaaf0  dec     rax
0x1800aaaf3  sub     rdi, 1
0x1800aaaf7  jnz     short loc_1800AAAD7
0x1800aaaf9  test    rdi, rdi
0x1800aaafc  lea     rcx, [r8-2]
0x1800aab00  mov     rax, rdi
0x1800aab03  cmovnz  rcx, r8
0x1800aab07  neg     rax
0x1800aab0a  sbb     ebx, ebx
0x1800aab0c  not     ebx
0x1800aab0e  and     ebx, 8007007Ah
0x1800aab14  mov     [rcx], r15w
0x1800aab18  test    rdi, rdi
0x1800aab1b  jz      short loc_1800AAB30
0x1800aab1d  test    ebx, ebx
0x1800aab1f  js      loc_1800AAA7C
0x1800aab25  mov     rsi, [rsi+38h]
0x1800aab29  inc     ebp
0x1800aab2b  jmp     loc_1800AAA0B
0x1800aab30  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800aab37  jz      short loc_1800AAB1D
0x1800aab39  mov     ecx, ebx; int
0x1800aab3b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800aab40  jmp     short loc_1800AAB1D
0x1800aab42  mov     ecx, ebx; int
0x1800aab44  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800aab49  jmp     loc_1800AAA7C
0x1800aab4e  test    eax, eax
0x1800aab50  jns     loc_1800AAA85
0x1800aab56  jmp     loc_1800AAA7C
0x1800aab5b  mov     rax, [rax+38h]
0x1800aab5f  inc     ebx
0x1800aab61  test    rax, rax
0x1800aab64  jnz     short loc_1800AAB5B
0x1800aab66  jmp     loc_1800AA9B5
0x1800aab6b  mov     ebx, 8007000Eh
0x1800aab70  jmp     loc_1800AAA6F
0x1800aab75  mov     ebx, 80070057h
0x1800aab7a  jmp     short loc_1800AAB86
0x1800aab7c  mov     ebx, 80070057h
0x1800aab81  test    rdi, rdi
0x1800aab84  jz      short loc_1800AAB30
0x1800aab86  mov     [r8], r15w
0x1800aab8a  jmp     short loc_1800AAB30
```
