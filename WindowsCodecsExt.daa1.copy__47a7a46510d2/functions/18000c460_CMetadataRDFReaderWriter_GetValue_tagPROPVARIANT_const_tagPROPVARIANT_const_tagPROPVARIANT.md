# CMetadataRDFReaderWriter::GetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18000c460`
- end: `0x18000c68c`
- name: `?GetValue@CMetadataRDFReaderWriter@@UEAAJPEBUtagPROPVARIANT@@0PEAU2@@Z`
- size: `556`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000c460`
- `0x1800171c4`
- `0x18001d6e8`
- `0x180022644`
- `0x180022650`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c4cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c505`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c4cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c505`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c540`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c54a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c540`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c54a`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::GetValue(
        CMetadataRDFReaderWriter *this,
        PROPVARIANT *a2,
        PROPVARIANT *a3,
        struct tagPROPVARIANT *a4)
{
  char *v4; // rsi
  PROPVARIANT *v6; // r15
  int v8; // ebx
  unsigned __int16 *v9; // rcx
  bool v10; // zf
  int v11; // edi
  unsigned __int16 *v12; // rcx
  int v14; // eax
  int v15; // ecx
  int v16; // eax
  int v17; // eax
  PROPVARIANT pvar[2]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v19; // [rsp+40h] [rbp-30h]
  int v20; // [rsp+48h] [rbp-28h]
  int v21; // [rsp+4Ch] [rbp-24h]
  PROPVARIANT v22[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v23; // [rsp+60h] [rbp-10h]
  int v24; // [rsp+68h] [rbp-8h]
  int v25; // [rsp+6Ch] [rbp-4h]
  unsigned __int16 *v27; // [rsp+B8h] [rbp+48h] BYREF

  v4 = (char *)this + 40;
  v6 = a3;
  if ( *((_BYTE *)this + 88) )
    EnterCriticalSection_0((LPCRITICAL_SECTION)((char *)this + 48));
  v8 = 0;
  v25 = 1;
  v24 = 0;
  v23 = 0;
  *(_OWORD *)v22 = 0;
  if ( a2 )
  {
    v9 = 0;
    v10 = *(_WORD *)a2 == 30;
    v27 = 0;
    if ( v10 )
    {
      v16 = CoerceAnsiStrToWideStr((LPCCH)a2[1], &v27, (__int64)a3, (UINT)a4);
      v8 = v16;
      if ( v16 >= 0 )
      {
        a2 = v22;
        v22[1] = v27;
        v9 = 0;
        LOWORD(v22[0]) = 31;
      }
      else
      {
        if ( g_doStackCaptures )
          DoStackCapture(v16);
        v9 = v27;
      }
    }
    CoTaskMemFree(v9);
    v24 = v8;
  }
  v11 = 0;
  v21 = 1;
  v20 = 0;
  v19 = 0;
  *(_OWORD *)pvar = 0;
  if ( v6 )
  {
    v12 = 0;
    v10 = *(_WORD *)v6 == 30;
    v27 = 0;
    if ( v10 )
    {
      v17 = CoerceAnsiStrToWideStr((LPCCH)v6[1], &v27, (__int64)a3, (UINT)a4);
      v11 = v17;
      if ( v17 >= 0 )
      {
        v6 = pvar;
        LOWORD(pvar[0]) = 31;
        v12 = 0;
        pvar[1] = v27;
      }
      else
      {
        if ( g_doStackCaptures )
          DoStackCapture(v17);
        v12 = v27;
      }
    }
    CoTaskMemFree(v12);
    v20 = v11;
  }
  v25 = 0;
  if ( v8 >= 0 )
  {
    if ( !v6 )
    {
      v8 = -2147024809;
      v21 = 0;
      goto LABEL_13;
    }
    v8 = v11;
  }
  v21 = 0;
  if ( v8 < 0 )
  {
LABEL_13:
    if ( !g_doStackCaptures )
      goto LABEL_14;
    v15 = v8;
LABEL_24:
    DoStackCapture(v15);
    goto LABEL_14;
  }
  if ( a4 && a4->vt )
  {
    v8 = -2147024809;
    if ( g_doStackCaptures )
      DoStackCapture(-2147024809);
  }
  else
  {
    v14 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, PROPVARIANT *, PROPVARIANT *, struct tagPROPVARIANT *))(*(_QWORD *)this + 160LL))(
            this,
            a2,
            v6,
            a4);
    v8 = v14;
    if ( v14 < 0 && g_doStackCaptures )
    {
      v15 = v14;
      goto LABEL_24;
    }
  }
LABEL_14:
  PropVariantClear(pvar);
  PropVariantClear(v22);
  if ( v4 && v4[48] )
    LeaveCriticalSection_0((LPCRITICAL_SECTION)(v4 + 8));
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000c460  mov     [rsp-38h+arg_10], rbx
0x18000c465  mov     [rsp-38h+arg_0], rcx
0x18000c46a  push    rbp
0x18000c46b  push    rsi
0x18000c46c  push    rdi
0x18000c46d  push    r12
0x18000c46f  push    r13
0x18000c471  push    r14
0x18000c473  push    r15
0x18000c475  mov     rbp, rsp
0x18000c478  sub     rsp, 70h
0x18000c47c  cmp     byte ptr [rcx+58h], 0
0x18000c480  lea     rsi, [rcx+28h]
0x18000c484  mov     r12, r9
0x18000c487  mov     r15, r8
0x18000c48a  mov     r13, rdx
0x18000c48d  jz      short loc_18000C498
0x18000c48f  lea     rcx, [rsi+8]; lpCriticalSection
0x18000c493  call    EnterCriticalSection_0
0x18000c498  xor     ebx, ebx
0x18000c49a  mov     [rbp+var_4], 1
0x18000c4a1  xor     eax, eax
0x18000c4a3  mov     [rbp+var_8], ebx
0x18000c4a6  mov     [rbp+var_10], rax
0x18000c4aa  xorps   xmm0, xmm0
0x18000c4ad  mov     edi, 1Fh
0x18000c4b2  movups  xmmword ptr [rbp+var_20], xmm0
0x18000c4b6  test    r13, r13
0x18000c4b9  jz      short loc_18000C4D6
0x18000c4bb  xor     ecx, ecx; pv
0x18000c4bd  cmp     word ptr [r13+0], 1Eh
0x18000c4c3  mov     [rbp+arg_8], rcx
0x18000c4c7  jz      loc_18000C5CA
0x18000c4cd  call    cs:__imp_CoTaskMemFree
0x18000c4d3  mov     [rbp+var_8], ebx
0x18000c4d6  xor     edi, edi
0x18000c4d8  mov     [rbp+var_24], 1
0x18000c4df  xor     eax, eax
0x18000c4e1  mov     [rbp+var_28], edi
0x18000c4e4  mov     [rbp+var_30], rax
0x18000c4e8  xorps   xmm0, xmm0
0x18000c4eb  movups  xmmword ptr [rbp+pvar], xmm0
0x18000c4ef  test    r15, r15
0x18000c4f2  jz      short loc_18000C50E
0x18000c4f4  xor     ecx, ecx; pv
0x18000c4f6  cmp     word ptr [r15], 1Eh
0x18000c4fb  mov     [rbp+arg_8], rcx
0x18000c4ff  jz      loc_18000C5F6
0x18000c505  call    cs:__imp_CoTaskMemFree
0x18000c50b  mov     [rbp+var_28], edi
0x18000c50e  mov     [rbp+var_4], 0
0x18000c515  test    ebx, ebx
0x18000c517  js      short loc_18000C524
0x18000c519  test    r15, r15
0x18000c51c  jz      loc_18000C67B
0x18000c522  mov     ebx, edi
0x18000c524  mov     [rbp+var_24], 0
0x18000c52b  test    ebx, ebx
0x18000c52d  jns     short loc_18000C57E
0x18000c52f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000c536  jnz     loc_18000C5BE
0x18000c53c  lea     rcx, [rbp+pvar]; pvar
0x18000c540  call    cs:__imp_PropVariantClear
0x18000c546  lea     rcx, [rbp+var_20]; pvar
0x18000c54a  call    cs:__imp_PropVariantClear
0x18000c550  test    rsi, rsi
0x18000c553  jz      short loc_18000C564
0x18000c555  cmp     byte ptr [rsi+30h], 0
0x18000c559  jz      short loc_18000C564
0x18000c55b  lea     rcx, [rsi+8]; lpCriticalSection
0x18000c55f  call    LeaveCriticalSection_0
0x18000c564  mov     eax, ebx
0x18000c566  mov     rbx, [rsp+70h+arg_10]
0x18000c56e  add     rsp, 70h
0x18000c572  pop     r15
0x18000c574  pop     r14
0x18000c576  pop     r13
0x18000c578  pop     r12
0x18000c57a  pop     rdi
0x18000c57b  pop     rsi
0x18000c57c  pop     rbp
0x18000c57d  retn
0x18000c57e  test    r12, r12
0x18000c581  jz      short loc_18000C58F
0x18000c583  cmp     word ptr [r12], 0
0x18000c589  jnz     loc_18000C622
0x18000c58f  mov     rcx, [rbp+arg_0]
0x18000c593  mov     r9, r12
0x18000c596  mov     r8, r15
0x18000c599  mov     rdx, r13
0x18000c59c  mov     rax, [rcx]
0x18000c59f  mov     rax, [rax+0A0h]
0x18000c5a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5ab  mov     ebx, eax
0x18000c5ad  test    eax, eax
0x18000c5af  jns     short loc_18000C53C
0x18000c5b1  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000c5b8  jz      short loc_18000C53C
0x18000c5ba  mov     ecx, eax
0x18000c5bc  jmp     short loc_18000C5C0
0x18000c5be  mov     ecx, ebx; int
0x18000c5c0  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000c5c5  jmp     loc_18000C53C
0x18000c5ca  mov     rcx, [r13+8]; lpMultiByteStr
0x18000c5ce  lea     rdx, [rbp+arg_8]; unsigned __int16 **
0x18000c5d2  call    ?CoerceAnsiStrToWideStr@@YAJPEBDPEAPEAGIH@Z; CoerceAnsiStrToWideStr(char const *,ushort * *,uint,int)
0x18000c5d7  mov     ebx, eax
0x18000c5d9  test    eax, eax
0x18000c5db  jns     short loc_18000C644
0x18000c5dd  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000c5e4  jz      short loc_18000C640
0x18000c5e6  mov     ecx, eax; int
0x18000c5e8  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000c5ed  mov     rcx, [rbp+arg_8]
0x18000c5f1  jmp     loc_18000C4CD
0x18000c5f6  mov     rcx, [r15+8]; lpMultiByteStr
0x18000c5fa  lea     rdx, [rbp+arg_8]; unsigned __int16 **
0x18000c5fe  call    ?CoerceAnsiStrToWideStr@@YAJPEBDPEAPEAGIH@Z; CoerceAnsiStrToWideStr(char const *,ushort * *,uint,int)
0x18000c603  mov     edi, eax
0x18000c605  test    eax, eax
0x18000c607  jns     short loc_18000C65F
0x18000c609  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000c610  jz      short loc_18000C65B
0x18000c612  mov     ecx, eax; int
0x18000c614  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000c619  mov     rcx, [rbp+arg_8]
0x18000c61d  jmp     loc_18000C505
0x18000c622  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000c629  mov     ebx, 80070057h
0x18000c62e  jz      loc_18000C53C
0x18000c634  mov     ecx, ebx; int
0x18000c636  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000c63b  jmp     loc_18000C53C
0x18000c640  test    eax, eax
0x18000c642  js      short loc_18000C5ED
0x18000c644  mov     rax, [rbp+arg_8]
0x18000c648  lea     r13, [rbp+var_20]
0x18000c64c  mov     [rbp+var_20+8], rax
0x18000c650  xor     ecx, ecx
0x18000c652  mov     word ptr [rbp+var_20], di
0x18000c656  jmp     loc_18000C4CD
0x18000c65b  test    eax, eax
0x18000c65d  js      short loc_18000C619
0x18000c65f  mov     eax, 1Fh
0x18000c664  lea     r15, [rbp+pvar]
0x18000c668  mov     word ptr [rbp+pvar], ax
0x18000c66c  xor     ecx, ecx
0x18000c66e  mov     rax, [rbp+arg_8]
0x18000c672  mov     [rbp+pvar+8], rax
0x18000c676  jmp     loc_18000C505
0x18000c67b  mov     ebx, 80070057h
0x18000c680  mov     [rbp+var_24], 0
0x18000c687  jmp     loc_18000C52F
```
