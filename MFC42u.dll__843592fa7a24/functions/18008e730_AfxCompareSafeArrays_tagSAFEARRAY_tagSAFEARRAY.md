# _AfxCompareSafeArrays(tagSAFEARRAY *,tagSAFEARRAY *)

- ea: `0x18008e730`
- end: `0x18008ea38`
- name: `?_AfxCompareSafeArrays@@YAHPEAUtagSAFEARRAY@@0@Z`
- size: `776`
- prototype: `__int64 __fastcall(SAFEARRAY *psa, SAFEARRAY *)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18008c800`
- `0x18008c810`
- `0x18008c830`

## callees

- `0x18000ce50`
- `0x180024fc0`
- `0x18008e730`
- `0x1800d1f6e`

## import_xrefs

- `msvcrt!free` at `0x18008e944`
- `msvcrt!free` at `0x18008e94f`
- `msvcrt!free` at `0x18008e958`
- `msvcrt!free` at `0x18008e961`
- `msvcrt!free` at `0x18008e9f0`
- `msvcrt!free` at `0x18008e9fb`
- `msvcrt!free` at `0x18008ea04`
- `msvcrt!free` at `0x18008ea0d`
- `msvcrt!free` at `0x18008e944`
- `msvcrt!free` at `0x18008e94f`
- `msvcrt!free` at `0x18008e958`
- `msvcrt!free` at `0x18008e961`
- `msvcrt!free` at `0x18008e9f0`
- `msvcrt!free` at `0x18008e9fb`
- `msvcrt!free` at `0x18008ea04`
- `msvcrt!free` at `0x18008ea0d`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18008e767`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18008e773`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18008e767`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18008e773`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18008e796`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18008e7a9`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18008e796`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18008e7a9`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008e8e5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008e90f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008e8e5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008e90f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008e88b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008e8b7`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008e88b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008e8b7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18008e985`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18008e99a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18008e985`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18008e99a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18008e9cd`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18008e9dd`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18008e9cd`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18008e9dd`

## pseudocode

```c
_BOOL8 __fastcall _AfxCompareSafeArrays(SAFEARRAY *psa, SAFEARRAY *a2)
{
  unsigned __int64 Dim; // r15
  UINT v5; // eax
  unsigned __int64 v6; // rsi
  UINT Elemsize; // r14d
  size_t v9; // rax
  char *v10; // r13
  char *v11; // r12
  __int64 v12; // r14
  HRESULT LBound; // eax
  HRESULT v14; // eax
  HRESULT UBound; // eax
  HRESULT v16; // eax
  int v17; // edx
  __int64 v18; // rsi
  HRESULT v19; // eax
  HRESULT v20; // eax
  BOOL v21; // esi
  HRESULT v22; // eax
  HRESULT v23; // eax
  HRESULT v24; // eax
  HRESULT v25; // eax
  char *Block; // [rsp+20h] [rbp-98h]
  char *v27; // [rsp+28h] [rbp-90h]
  void *ppvData; // [rsp+30h] [rbp-88h] BYREF
  void *Buf2; // [rsp+38h] [rbp-80h] BYREF
  void *v30; // [rsp+40h] [rbp-78h]
  void *v31; // [rsp+48h] [rbp-70h]
  void *v32; // [rsp+50h] [rbp-68h]
  void *v33; // [rsp+58h] [rbp-60h]
  LONG *v34; // [rsp+60h] [rbp-58h]
  LONG *v35; // [rsp+68h] [rbp-50h]
  LONG *v36; // [rsp+70h] [rbp-48h]
  __int64 v37; // [rsp+78h] [rbp-40h] BYREF
  UINT v40; // [rsp+D0h] [rbp+18h]
  __int64 v41; // [rsp+D8h] [rbp+20h]
  LONG *v42; // [rsp+D8h] [rbp+20h]

  if ( !psa || !a2 )
    return psa == a2;
  Dim = SafeArrayGetDim(psa);
  v5 = SafeArrayGetDim(a2);
  v6 = v5;
  if ( (_DWORD)Dim != v5 )
    return 0;
  if ( !(_DWORD)Dim )
    return 1;
  Elemsize = SafeArrayGetElemsize(psa);
  v40 = Elemsize;
  if ( Elemsize != SafeArrayGetElemsize(a2) )
    return 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  ppvData = 0;
  Buf2 = 0;
  v9 = 4 * Dim;
  if ( !is_mul_ok(Dim, 4u) )
    v9 = -1;
  try
  {
    Block = (char *)operator new(v9);
    v30 = Block;
    v27 = (char *)operator new(saturated_mul(v6, 4u));
    v31 = v27;
    v10 = (char *)operator new(saturated_mul(Dim, 4u));
    v32 = v10;
    v11 = (char *)operator new(saturated_mul(v6, 4u));
    v33 = v11;
    v18 = 1;
    v12 = 0;
  }
  catch ( CException *v37 )
  {
    free(v30);
    free(v31);
    free(v32);
    free(v33);
    if ( ppvData )
    {
      v24 = SafeArrayUnaccessData(psa);
      AfxCheckError(v24);
    }
    if ( Buf2 )
    {
      v25 = SafeArrayUnaccessData(a2);
      AfxCheckError(v25);
    }
    throw;
  }
  while ( (unsigned int)v12 < (unsigned int)Dim )
  {
    v41 = (unsigned int)v12;
    v35 = (LONG *)&Block[4 * v12];
    v12 = (unsigned int)(v12 + 1);
    LBound = SafeArrayGetLBound(psa, v12, v35);
    AfxCheckError(LBound);
    v36 = (LONG *)&v27[4 * v41];
    v14 = SafeArrayGetLBound(a2, v12, v36);
    AfxCheckError(v14);
    v34 = (LONG *)&v10[4 * v41];
    UBound = SafeArrayGetUBound(psa, v12, v34);
    AfxCheckError(UBound);
    v42 = (LONG *)&v11[4 * v41];
    v16 = SafeArrayGetUBound(a2, v12, v42);
    AfxCheckError(v16);
    v17 = *v34 - *v35;
    if ( v17 != *v42 - *v36 )
    {
      free(Block);
      free(v27);
      free(v10);
      free(v11);
      return 0;
    }
    v18 *= v17 + 1;
  }
  v19 = SafeArrayAccessData(psa, &ppvData);
  AfxCheckError(v19);
  v20 = SafeArrayAccessData(a2, &Buf2);
  AfxCheckError(v20);
  v21 = memcmp_0(ppvData, Buf2, v18 * v40) == 0;
  v22 = SafeArrayUnaccessData(psa);
  AfxCheckError(v22);
  v23 = SafeArrayUnaccessData(a2);
  AfxCheckError(v23);
  free(Block);
  free(v27);
  free(v10);
  free(v11);
  return v21;
}

```

## disassembly

```asm
0x18008e730  mov     [rsp+arg_8], rdx
0x18008e735  mov     [rsp+arg_0], rcx
0x18008e73a  push    rbx
0x18008e73b  push    rsi
0x18008e73c  push    rdi
0x18008e73d  push    r12
0x18008e73f  push    r13
0x18008e741  push    r14
0x18008e743  push    r15
0x18008e745  sub     rsp, 80h
0x18008e74c  mov     rbx, rdx
0x18008e74f  mov     rdi, rcx
0x18008e752  xor     r12d, r12d
0x18008e755  test    rcx, rcx
0x18008e758  jz      loc_18008EA1B
0x18008e75e  test    rdx, rdx
0x18008e761  jz      loc_18008EA1B
0x18008e767  call    cs:__imp_SafeArrayGetDim
0x18008e76d  mov     r15d, eax
0x18008e770  mov     rcx, rbx; psa
0x18008e773  call    cs:__imp_SafeArrayGetDim
0x18008e779  mov     esi, eax
0x18008e77b  cmp     r15d, eax
0x18008e77e  jnz     loc_18008EA17
0x18008e784  test    r15d, r15d
0x18008e787  jnz     short loc_18008E793
0x18008e789  lea     eax, [r12+1]
0x18008e78e  jmp     loc_18008EA24
0x18008e793  mov     rcx, rdi; psa
0x18008e796  call    cs:__imp_SafeArrayGetElemsize
0x18008e79c  mov     r14d, eax
0x18008e79f  mov     [rsp+0B8h+arg_10], eax
0x18008e7a6  mov     rcx, rbx; psa
0x18008e7a9  call    cs:__imp_SafeArrayGetElemsize
0x18008e7af  cmp     r14d, eax
0x18008e7b2  jnz     loc_18008EA17
0x18008e7b8  mov     [rsp+0B8h+var_78], r12
0x18008e7bd  mov     [rsp+0B8h+var_70], r12
0x18008e7c2  mov     [rsp+0B8h+var_68], r12
0x18008e7c7  mov     [rsp+0B8h+var_60], r12
0x18008e7cc  mov     [rsp+0B8h+ppvData], r12
0x18008e7d1  mov     [rsp+0B8h+Buf2], r12
0x18008e7d6  mov     r14, r15
0x18008e7d9  mov     r12d, 4
0x18008e7df  mov     eax, r12d
0x18008e7e2  mul     r15
0x18008e7e5  lea     r13, [r12-5]
0x18008e7ea  cmovb   rax, r13
0x18008e7ee  mov     rcx, rax; Size
0x18008e7f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008e7f6  mov     [rsp+0B8h+Block], rax
0x18008e7fb  mov     [rsp+0B8h+var_78], rax
0x18008e800  mov     eax, r12d
0x18008e803  mul     rsi
0x18008e806  cmovb   rax, r13
0x18008e80a  mov     rcx, rax; Size
0x18008e80d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008e812  mov     [rsp+0B8h+var_90], rax
0x18008e817  mov     [rsp+0B8h+var_70], rax
0x18008e81c  mov     eax, r12d
0x18008e81f  mul     r14
0x18008e822  cmovb   rax, r13
0x18008e826  mov     rcx, rax; Size
0x18008e829  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008e82e  mov     r13, rax
0x18008e831  mov     [rsp+0B8h+var_68], rax
0x18008e836  mov     eax, r12d
0x18008e839  mul     rsi
0x18008e83c  lea     rcx, [r12-5]
0x18008e841  cmovb   rax, rcx
0x18008e845  mov     rcx, rax; Size
0x18008e848  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008e84d  mov     r12, rax
0x18008e850  mov     [rsp+0B8h+var_60], rax
0x18008e855  mov     esi, 1
0x18008e85a  xor     r14d, r14d
0x18008e85d  cmp     r14d, r15d
0x18008e860  jnb     loc_18008E97D
0x18008e866  mov     eax, r14d
0x18008e869  mov     [rsp+0B8h+arg_18], rax
0x18008e871  mov     rcx, [rsp+0B8h+Block]
0x18008e876  lea     rax, [rcx+r14*4]
0x18008e87a  mov     [rsp+0B8h+var_50], rax
0x18008e87f  inc     r14d
0x18008e882  mov     r8, rax; plLbound
0x18008e885  mov     edx, r14d; nDim
0x18008e888  mov     rcx, rdi; psa
0x18008e88b  call    cs:__imp_SafeArrayGetLBound
0x18008e891  mov     ecx, eax; int
0x18008e893  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x18008e898  mov     rax, [rsp+0B8h+arg_18]
0x18008e8a0  mov     rcx, [rsp+0B8h+var_90]
0x18008e8a5  lea     rax, [rcx+rax*4]
0x18008e8a9  mov     [rsp+0B8h+var_48], rax
0x18008e8ae  mov     r8, rax; plLbound
0x18008e8b1  mov     edx, r14d; nDim
0x18008e8b4  mov     rcx, rbx; psa
0x18008e8b7  call    cs:__imp_SafeArrayGetLBound
0x18008e8bd  mov     ecx, eax; int
0x18008e8bf  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x18008e8c4  mov     rax, [rsp+0B8h+arg_18]
0x18008e8cc  lea     rax, ds:0[rax*4]
0x18008e8d4  add     rax, r13
0x18008e8d7  mov     [rsp+0B8h+var_58], rax
0x18008e8dc  mov     r8, rax; plUbound
0x18008e8df  mov     edx, r14d; nDim
0x18008e8e2  mov     rcx, rdi; psa
0x18008e8e5  call    cs:__imp_SafeArrayGetUBound
0x18008e8eb  mov     ecx, eax; int
0x18008e8ed  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x18008e8f2  mov     rax, [rsp+0B8h+arg_18]
0x18008e8fa  lea     rax, [r12+rax*4]
0x18008e8fe  mov     [rsp+0B8h+arg_18], rax
0x18008e906  mov     r8, rax; plUbound
0x18008e909  mov     edx, r14d; nDim
0x18008e90c  mov     rcx, rbx; psa
0x18008e90f  call    cs:__imp_SafeArrayGetUBound
0x18008e915  mov     ecx, eax; int
0x18008e917  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x18008e91c  mov     rdx, [rsp+0B8h+var_58]
0x18008e921  mov     edx, [rdx]
0x18008e923  mov     rax, [rsp+0B8h+var_50]
0x18008e928  sub     edx, [rax]
0x18008e92a  mov     rax, [rsp+0B8h+arg_18]
0x18008e932  mov     eax, [rax]
0x18008e934  mov     rcx, [rsp+0B8h+var_48]
0x18008e939  sub     eax, [rcx]
0x18008e93b  cmp     edx, eax
0x18008e93d  jz      short loc_18008E96E
0x18008e93f  mov     rcx, [rsp+0B8h+Block]; Block
0x18008e944  call    cs:__imp_free
0x18008e94a  mov     rcx, [rsp+0B8h+var_90]; Block
0x18008e94f  call    cs:__imp_free
0x18008e955  mov     rcx, r13; Block
0x18008e958  call    cs:__imp_free
0x18008e95e  mov     rcx, r12; Block
0x18008e961  call    cs:__imp_free
0x18008e967  xor     eax, eax
0x18008e969  jmp     loc_18008EA24
0x18008e96e  lea     eax, [rdx+1]
0x18008e971  movsxd  rcx, eax
0x18008e974  imul    rsi, rcx
0x18008e978  jmp     loc_18008E85D
0x18008e97d  lea     rdx, [rsp+0B8h+ppvData]; ppvData
0x18008e982  mov     rcx, rdi; psa
0x18008e985  call    cs:__imp_SafeArrayAccessData
0x18008e98b  mov     ecx, eax; int
0x18008e98d  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x18008e992  lea     rdx, [rsp+0B8h+Buf2]; ppvData
0x18008e997  mov     rcx, rbx; psa
0x18008e99a  call    cs:__imp_SafeArrayAccessData
0x18008e9a0  mov     ecx, eax; int
0x18008e9a2  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x18008e9a7  mov     r8d, [rsp+0B8h+arg_10]
0x18008e9af  imul    r8, rsi; Size
0x18008e9b3  mov     rdx, [rsp+0B8h+Buf2]; Buf2
0x18008e9b8  mov     rcx, [rsp+0B8h+ppvData]; Buf1
0x18008e9bd  call    memcmp_0
0x18008e9c2  xor     esi, esi
0x18008e9c4  test    eax, eax
0x18008e9c6  setz    sil
0x18008e9ca  mov     rcx, rdi; psa
0x18008e9cd  call    cs:__imp_SafeArrayUnaccessData
0x18008e9d3  mov     ecx, eax; int
0x18008e9d5  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x18008e9da  mov     rcx, rbx; psa
0x18008e9dd  call    cs:__imp_SafeArrayUnaccessData
0x18008e9e3  mov     ecx, eax; int
0x18008e9e5  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x18008e9ea  nop
0x18008e9eb  mov     rcx, [rsp+0B8h+Block]; Block
0x18008e9f0  call    cs:__imp_free
0x18008e9f6  mov     rcx, [rsp+0B8h+var_90]; Block
0x18008e9fb  call    cs:__imp_free
0x18008ea01  mov     rcx, r13; Block
0x18008ea04  call    cs:__imp_free
0x18008ea0a  mov     rcx, r12; Block
0x18008ea0d  call    cs:__imp_free
0x18008ea13  mov     eax, esi
0x18008ea15  jmp     short loc_18008EA24
0x18008ea17  xor     eax, eax
0x18008ea19  jmp     short loc_18008EA24
0x18008ea1b  mov     eax, r12d
0x18008ea1e  cmp     rdi, rbx
0x18008ea21  setz    al
0x18008ea24  add     rsp, 80h
0x18008ea2b  pop     r15
0x18008ea2d  pop     r14
0x18008ea2f  pop     r13
0x18008ea31  pop     r12
0x18008ea33  pop     rdi
0x18008ea34  pop     rsi
0x18008ea35  pop     rbx
0x18008ea36  retn
```
