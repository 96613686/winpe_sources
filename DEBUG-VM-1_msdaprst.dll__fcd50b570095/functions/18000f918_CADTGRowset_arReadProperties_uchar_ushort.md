# CADTGRowset::arReadProperties(uchar *,ushort)

- ea: `0x18000f918`
- end: `0x180010144`
- name: `?arReadProperties@CADTGRowset@@AEAAXPEAEG@Z`
- size: `2092`
- prototype: `void __fastcall(CADTGRowset *__hidden this, unsigned __int8 *, unsigned __int16)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x1800102a4`
- `0x1800103a0`

## callees

- `0x180001d94`
- `0x180001dd8`
- `0x1800027c0`
- `0x18000f918`
- `0x180015fb4`
- `0x18001a6c8`
- `0x18002ca58`
- `0x18002cd54`
- `0x18002e02a`
- `0x18002e060`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000ffac`
- `ole32!CoTaskMemFree` at `0x18000ffc4`
- `ole32!CoTaskMemFree` at `0x18000ffd0`
- `ole32!CoTaskMemFree` at `0x18000ffac`
- `ole32!CoTaskMemFree` at `0x18000ffc4`
- `ole32!CoTaskMemFree` at `0x18000ffd0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000ff63`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000ff63`
- `OLEAUT32!__imp_VariantInit` at `0x18000fcfd`
- `OLEAUT32!__imp_VariantInit` at `0x18000fcfd`
- `OLEAUT32!__imp_VariantClear` at `0x180010083`
- `OLEAUT32!__imp_VariantClear` at `0x180010083`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CADTGRowset::arReadProperties(CADTGRowset *this, unsigned __int8 *a2, unsigned __int16 a3)
{
  int v5; // eax
  int v6; // r14d
  unsigned int v7; // eax
  unsigned __int8 *v8; // r12
  unsigned __int16 v9; // si
  __int64 v10; // r15
  unsigned __int128 v11; // rax
  unsigned __int64 v12; // kr10_8
  struct tagDBPROPSET *v13; // r14
  unsigned __int16 v14; // ax
  int v15; // eax
  int v16; // r15d
  __int64 v17; // r15
  GUID v18; // xmm0
  unsigned __int16 v19; // si
  int v20; // eax
  int v21; // r15d
  unsigned __int64 v22; // rcx
  unsigned __int128 v23; // rax
  unsigned __int8 *v24; // rax
  unsigned __int16 v25; // cx
  __int64 v26; // r15
  __int64 v27; // r13
  int v28; // eax
  int v29; // r15d
  unsigned __int16 v30; // si
  int v31; // eax
  int v32; // r15d
  __int64 v33; // r13
  __int16 v34; // r9
  unsigned int j; // ecx
  int v36; // eax
  int v37; // r15d
  __int16 v38; // ax
  int v39; // eax
  int v40; // r15d
  int v41; // eax
  int v42; // r15d
  int v43; // eax
  int v44; // r15d
  BSTR v45; // rax
  unsigned int i; // r15d
  unsigned __int16 v47; // dx
  unsigned __int16 v48; // r12
  __int64 v49; // r13
  __int64 v50; // rsi
  unsigned __int16 v51; // r15
  unsigned __int8 *rgProperties; // rcx
  int v53; // esi
  unsigned __int16 v54; // [rsp+40h] [rbp-B8h]
  unsigned __int16 v55; // [rsp+42h] [rbp-B6h]
  unsigned __int16 v56; // [rsp+44h] [rbp-B4h]
  unsigned __int16 v57; // [rsp+48h] [rbp-B0h]
  unsigned int v58; // [rsp+4Ch] [rbp-ACh] BYREF
  int v59; // [rsp+50h] [rbp-A8h]
  __int64 v60; // [rsp+58h] [rbp-A0h]
  __int64 v61; // [rsp+60h] [rbp-98h]
  LPVOID v62; // [rsp+68h] [rbp-90h] BYREF
  VARIANTARG *v63; // [rsp+70h] [rbp-88h]
  __int64 v64; // [rsp+78h] [rbp-80h]
  LPVOID pv; // [rsp+80h] [rbp-78h] BYREF
  unsigned int v66[2]; // [rsp+88h] [rbp-70h]
  struct tagDBPROPSET *v67; // [rsp+90h] [rbp-68h]
  int v68; // [rsp+98h] [rbp-60h] BYREF
  _OWORD v69[2]; // [rsp+A0h] [rbp-58h] BYREF

  try
  {
    *(_QWORD *)v66 = this;
    v59 = 0;
    v67 = 0;
    v58 = 0;
    if ( a3 < 2u )
    {
      v5 = Exit(-2147467259, 0x85u);
      v6 = v5;
      if ( v5 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_1800487D0[0] )
            bidTraceW(off_1800481C8[0], 875520, off_1800487D0[0], (unsigned int)v5, 855);
        }
        ThrowHR(v6);
      }
    }
    v7 = *(unsigned __int16 *)a2;
    v54 = *(_WORD *)a2;
    v57 = *(_WORD *)a2;
    v8 = a2 + 2;
    v9 = a3 - 2;
    v10 = v7;
    v12 = v7;
    v11 = v7 * (unsigned __int128)0x20uLL;
    if ( !is_mul_ok(v12, 0x20u) )
      LODWORD(v11) = -1;
    v13 = (struct tagDBPROPSET *)MMMAlloc(v11, DWORD2(v11));
    v67 = v13;
    OnNullThrowOOM(v13);
    memset_0(v13, 0, 32 * v10);
    v14 = 0;
    v55 = 0;
LABEL_11:
    if ( v14 < v54 )
    {
      memset(v69, 0, sizeof(v69));
      v62 = 0;
      pv = 0;
      if ( v9 < 0x10u )
      {
        v15 = Exit(-2147467259, 0x85u);
        v16 = v15;
        if ( v15 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1800487C8[0] )
            bidTraceW(off_1800481C8[0], 896000, off_1800487C8[0], (unsigned int)v15, 875);
          ThrowHR(v16);
        }
        v14 = v55;
      }
      v17 = 32LL * v14;
      v64 = v17;
      v18 = *(GUID *)v8;
      *(GUID *)((char *)&v13->guidPropertySet + v17) = *(GUID *)v8;
      v19 = v9 - 16;
      *(GUID *)((char *)v69 + 12) = v18;
      DWORD2(v69[0]) = 0;
      *(_QWORD *)&v69[0] = 0;
      v58 = 0;
      (*(void (__fastcall **)(_QWORD, __int64, _OWORD *, unsigned int *, LPVOID *, LPVOID *))(**(_QWORD **)(*(_QWORD *)v66 + 536LL)
                                                                                            + 32LL))(
        *(_QWORD *)(*(_QWORD *)v66 + 536LL),
        1,
        v69,
        &v58,
        &v62,
        &pv);
      if ( v19 < 2u )
      {
        v20 = Exit(-2147467259, 0x85u);
        v21 = v20;
        if ( v20 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1800487C0[0] )
            bidTraceW(off_1800481C8[0], 912384, off_1800487C0[0], (unsigned int)v20, 891);
          ThrowHR(v21);
        }
        v17 = v64;
      }
      v22 = *((unsigned __int16 *)v8 + 8);
      *(ULONG *)((char *)&v13->cProperties + v17) = v22;
      v8 += 18;
      v9 = v19 - 2;
      v23 = v22 * (unsigned __int128)0x48uLL;
      if ( !is_mul_ok(v22, 0x48u) )
        LODWORD(v23) = -1;
      v24 = MMMAlloc(v23, DWORD2(v23));
      *(DBPROP **)((char *)&v13->rgProperties + v17) = (DBPROP *)v24;
      OnNullThrowOOM(v24);
      v25 = 0;
      while ( 1 )
      {
        v56 = v25;
        if ( v25 >= *(ULONG *)((char *)&v13->cProperties + v17) )
        {
          for ( i = 0; i < v58; ++i )
            CoTaskMemFree(*((LPVOID *)v62 + 4 * i));
          CoTaskMemFree(pv);
          CoTaskMemFree(v62);
          v14 = ++v55;
          goto LABEL_11;
        }
        v26 = 9LL * v25;
        v60 = v26;
        v27 = *(__int64 *)((char *)&v13->rgProperties + v64);
        v61 = v27;
        *(_DWORD *)(v27 + 8 * v26 + 4) = 0;
        if ( v9 < 4u )
        {
          v28 = Exit(-2147467259, 0x85u);
          v29 = v28;
          if ( v28 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_1800487B8[0] )
              bidTraceW(off_1800481C8[0], 930816, off_1800487B8[0], (unsigned int)v28, 909);
            ThrowHR(v29);
          }
          v26 = v60;
        }
        *(_DWORD *)(v27 + 8 * v26) = *(_DWORD *)v8;
        v30 = v9 - 4;
        if ( v30 < 2u )
        {
          v31 = Exit(-2147467259, 0x85u);
          v32 = v31;
          if ( v31 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_1800487B0[0] )
              bidTraceW(off_1800481C8[0], 937984, off_1800487B0[0], (unsigned int)v31, 916);
            ThrowHR(v32);
          }
          v26 = v60;
        }
        v33 = *((unsigned __int16 *)v8 + 2);
        v8 += 6;
        v9 = v30 - 2;
        v63 = (VARIANTARG *)(v61 + 8 * v26 + 48);
        VariantInit(v63);
        v34 = 1;
        if ( v62 )
        {
          for ( j = 0; j < *((_DWORD *)v62 + 2); ++j )
          {
            if ( *(_DWORD *)(*(_QWORD *)v62 + 48LL * j + 8) == *(_DWORD *)(v61 + 8 * v26) )
            {
              v34 = *(_WORD *)(*(_QWORD *)v62 + 48LL * j + 16);
              if ( v34 != 3 )
                break;
              v63->vt = 3;
              if ( v9 < 4u )
              {
                v36 = Exit(-2147467259, 0x85u);
                v37 = v36;
                if ( v36 < 0 )
                {
                  if ( (bidGblFlags & 2) != 0 && off_1800487A0[0] )
                    bidTraceW(off_1800481C8[0], 961536, off_1800487A0[0], (unsigned int)v36, 939);
                  ThrowHR(v37);
                }
                v26 = v60;
              }
              *(_DWORD *)(v61 + 8 * v26 + 56) = *(_DWORD *)v8;
              v8 += 4;
              v38 = -4;
              goto LABEL_74;
            }
          }
        }
        if ( v34 == 8 )
        {
          if ( v9 < (unsigned __int16)v33 )
          {
            v43 = Exit(-2147467259, 0x85u);
            v44 = v43;
            if ( v43 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_180048798[0] )
                bidTraceW(off_1800481C8[0], 970752, off_180048798[0], (unsigned int)v43, 948);
              ThrowHR(v44);
            }
            v26 = v60;
          }
          if ( (_WORD)v33 )
          {
            v63->vt = 8;
            v45 = SysAllocStringLen((const OLECHAR *)v8, (unsigned int)v33 >> 1);
            *(_QWORD *)(v61 + 8 * v26 + 56) = v45;
LABEL_84:
            v8 += v33;
            v9 -= v33;
          }
        }
        else
        {
          if ( v34 != 11 )
          {
            if ( v9 < (unsigned __int16)v33 )
            {
              v39 = Exit(-2147467259, 0x85u);
              v40 = v39;
              if ( v39 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 && off_180048790[0] )
                  bidTraceW(off_1800481C8[0], 985088, off_180048790[0], (unsigned int)v39, 962);
                ThrowHR(v40);
              }
            }
            goto LABEL_84;
          }
          v63->vt = 11;
          if ( v9 < 2u )
          {
            v41 = Exit(-2147467259, 0x85u);
            v42 = v41;
            if ( v41 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_1800487A8[0] )
                bidTraceW(off_1800481C8[0], 951296, off_1800487A8[0], (unsigned int)v41, 929);
              ThrowHR(v42);
            }
            v26 = v60;
          }
          *(_WORD *)(v61 + 8 * v26 + 56) = *(_WORD *)v8;
          v8 += 2;
          v38 = -2;
LABEL_74:
          v9 += v38;
        }
        v25 = v56 + 1;
        v17 = v64;
      }
    }
    CUtlProps::utlSetProperties(
      (CUtlProps *)(*(_QWORD *)v66 + 400LL),
      v66[0],
      v54,
      v13,
      (const struct CBidGenericBase *)(*(_QWORD *)v66 + 112LL),
      1);
    v47 = v54;
  }
  catch ( long v68 )
  {
    v59 = v68;
    v47 = v57;
    v54 = v57;
    v13 = v67;
  }
  if ( v13 )
  {
    v48 = 0;
    if ( v47 )
    {
      v49 = 0;
      do
      {
        v50 = v49;
        if ( v13[v49].rgProperties )
        {
          v51 = 0;
          if ( v13[v50].cProperties )
          {
            do
              VariantClear(&v13[v50].rgProperties[v51++].vValue);
            while ( v51 < v13[v50].cProperties );
            v47 = v54;
          }
          rgProperties = (unsigned __int8 *)v13[v50].rgProperties;
          if ( rgProperties )
          {
            MMMFree(rgProperties);
            v47 = v54;
          }
        }
        ++v48;
        ++v49;
      }
      while ( v48 < v47 );
    }
    MMMFree((unsigned __int8 *)v13);
  }
  v53 = v59;
  if ( v59 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 && off_180048788[0] )
      bidTraceW(off_1800481C8[0], 1018880, off_180048788[0], (unsigned int)v59, 995);
    ThrowHR(v53);
  }
}

```

## disassembly

```asm
0x18000f918  mov     [rsp+arg_10], rbx
0x18000f91d  mov     [rsp+arg_18], rsi
0x18000f922  push    rdi
0x18000f923  push    r12
0x18000f925  push    r13
0x18000f927  push    r14
0x18000f929  push    r15
0x18000f92b  sub     rsp, 0D0h
0x18000f932  mov     rax, cs:__security_cookie
0x18000f939  xor     rax, rsp
0x18000f93c  mov     [rsp+0F8h+var_38], rax
0x18000f944  movzx   esi, r8w
0x18000f948  mov     r12, rdx
0x18000f94b  mov     qword ptr [rsp+0F8h+var_70], rcx
0x18000f953  xor     ebx, ebx
0x18000f955  mov     [rsp+0F8h+var_B0], bx
0x18000f95a  mov     [rsp+0F8h+var_A8], ebx
0x18000f95e  mov     [rsp+0F8h+var_68], rbx
0x18000f966  mov     [rsp+0F8h+var_AC], ebx
0x18000f96a  lea     edi, [rbx+2]
0x18000f96d  cmp     r8w, di
0x18000f971  jnb     short loc_18000F9C9
0x18000f973  mov     edx, 85h; unsigned int
0x18000f978  mov     ecx, 80004005h; int
0x18000f97d  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18000f982  mov     r14d, eax
0x18000f985  test    eax, eax
0x18000f987  jns     short loc_18000F9C9
0x18000f989  test    byte ptr cs:_bidGblFlags, dil
0x18000f990  jz      short loc_18000F9C1
0x18000f992  mov     rcx, cs:off_1800487D0; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000f999  test    rcx, rcx
0x18000f99c  jz      short loc_18000F9C1
0x18000f99e  mov     dword ptr [rsp+0F8h+var_D8], 357h
0x18000f9a6  mov     r9d, eax
0x18000f9a9  mov     r8, cs:off_1800487D0; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000f9b0  mov     edx, 0D5C00h
0x18000f9b5  mov     rcx, cs:off_1800481C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000f9bc  call    _bidTraceW
0x18000f9c1  mov     ecx, r14d; int
0x18000f9c4  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000f9c9  movzx   eax, word ptr [r12]
0x18000f9ce  mov     [rsp+0F8h+var_B8], ax
0x18000f9d3  mov     [rsp+0F8h+var_B0], ax
0x18000f9d8  add     r12, rdi
0x18000f9db  mov     ecx, 0FFFEh
0x18000f9e0  add     si, cx
0x18000f9e3  mov     r15d, eax
0x18000f9e6  mov     eax, 20h ; ' '
0x18000f9eb  mul     r15
0x18000f9ee  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000f9f5  cmovb   rax, rcx
0x18000f9f9  mov     ecx, eax; unsigned int
0x18000f9fb  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000fa00  mov     r14, rax
0x18000fa03  mov     [rsp+0F8h+var_68], rax
0x18000fa0b  mov     rcx, rax; void *
0x18000fa0e  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18000fa13  shl     r15, 5
0x18000fa17  mov     r8, r15; Size
0x18000fa1a  xor     edx, edx; Val
0x18000fa1c  mov     rcx, r14; void *
0x18000fa1f  call    memset_0
0x18000fa24  movzx   eax, bx
0x18000fa27  mov     [rsp+0F8h+var_B6], bx
0x18000fa2c  mov     r13d, 1
0x18000fa32  movzx   ecx, [rsp+0F8h+var_B8]
0x18000fa37  cmp     ax, cx
0x18000fa3a  jnb     loc_18000FFE9
0x18000fa40  xorps   xmm0, xmm0
0x18000fa43  movups  [rsp+0F8h+var_58], xmm0
0x18000fa4b  movups  [rsp+0F8h+var_48], xmm0
0x18000fa53  mov     [rsp+0F8h+var_90], rbx
0x18000fa58  mov     [rsp+0F8h+pv], rbx
0x18000fa60  cmp     si, 10h
0x18000fa64  jnb     short loc_18000FAC1
0x18000fa66  mov     edx, 85h; unsigned int
0x18000fa6b  mov     ecx, 80004005h; int
0x18000fa70  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18000fa75  mov     r15d, eax
0x18000fa78  test    eax, eax
0x18000fa7a  jns     short loc_18000FABC
0x18000fa7c  test    byte ptr cs:_bidGblFlags, dil
0x18000fa83  jz      short loc_18000FAB4
0x18000fa85  mov     rcx, cs:off_1800487C8; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fa8c  test    rcx, rcx
0x18000fa8f  jz      short loc_18000FAB4
0x18000fa91  mov     dword ptr [rsp+0F8h+var_D8], 36Bh
0x18000fa99  mov     r9d, eax
0x18000fa9c  mov     r8, cs:off_1800487C8; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000faa3  mov     edx, 0DAC00h
0x18000faa8  mov     rcx, cs:off_1800481C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000faaf  call    _bidTraceW
0x18000fab4  mov     ecx, r15d; int
0x18000fab7  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000fabc  movzx   eax, [rsp+0F8h+var_B6]
0x18000fac1  movzx   r15d, ax
0x18000fac5  shl     r15, 5
0x18000fac9  mov     [rsp+0F8h+var_80], r15
0x18000face  movups  xmm0, xmmword ptr [r12]
0x18000fad3  movdqu  xmmword ptr [r15+r14+0Ch], xmm0
0x18000fada  sub     si, 10h
0x18000fade  movdqu  [rsp+0F8h+var_58+0Ch], xmm0
0x18000fae7  mov     dword ptr [rsp+0F8h+var_58+8], ebx
0x18000faee  mov     qword ptr [rsp+0F8h+var_58], rbx
0x18000faf6  mov     [rsp+0F8h+var_AC], ebx
0x18000fafa  mov     rdx, qword ptr [rsp+0F8h+var_70]
0x18000fb02  mov     rcx, [rdx+218h]
0x18000fb09  mov     rax, [rcx]
0x18000fb0c  lea     rdx, [rsp+0F8h+pv]
0x18000fb14  mov     qword ptr [rsp+0F8h+var_D0], rdx
0x18000fb19  lea     rdx, [rsp+0F8h+var_90]
0x18000fb1e  mov     [rsp+0F8h+var_D8], rdx
0x18000fb23  lea     r9, [rsp+0F8h+var_AC]
0x18000fb28  lea     r8, [rsp+0F8h+var_58]
0x18000fb30  mov     edx, r13d
0x18000fb33  mov     rax, [rax+20h]
0x18000fb37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb3c  cmp     si, di
0x18000fb3f  jnb     short loc_18000FB9C
0x18000fb41  mov     edx, 85h; unsigned int
0x18000fb46  mov     ecx, 80004005h; int
0x18000fb4b  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18000fb50  mov     r15d, eax
0x18000fb53  test    eax, eax
0x18000fb55  jns     short loc_18000FB97
0x18000fb57  test    byte ptr cs:_bidGblFlags, dil
0x18000fb5e  jz      short loc_18000FB8F
0x18000fb60  mov     rcx, cs:off_1800487C0; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fb67  test    rcx, rcx
0x18000fb6a  jz      short loc_18000FB8F
0x18000fb6c  mov     dword ptr [rsp+0F8h+var_D8], 37Bh
0x18000fb74  mov     r9d, eax
0x18000fb77  mov     r8, cs:off_1800487C0; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fb7e  mov     edx, 0DEC00h
0x18000fb83  mov     rcx, cs:off_1800481C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000fb8a  call    _bidTraceW
0x18000fb8f  mov     ecx, r15d; int
0x18000fb92  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000fb97  mov     r15, [rsp+0F8h+var_80]
0x18000fb9c  movzx   ecx, word ptr [r12+10h]
0x18000fba2  mov     [r15+r14+8], ecx
0x18000fba7  add     r12, 12h
0x18000fbab  sub     si, di
0x18000fbae  mov     eax, 48h ; 'H'
0x18000fbb3  mul     rcx
0x18000fbb6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000fbbd  cmovb   rax, rcx
0x18000fbc1  mov     ecx, eax; unsigned int
0x18000fbc3  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000fbc8  mov     [r15+r14], rax
0x18000fbcc  mov     rcx, rax; void *
0x18000fbcf  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18000fbd4  movzx   ecx, bx
0x18000fbd7  mov     [rsp+0F8h+var_B4], cx
0x18000fbdc  movzx   eax, cx
0x18000fbdf  cmp     eax, [r15+r14+8]
0x18000fbe4  jnb     loc_18000FF93
0x18000fbea  movzx   eax, cx
0x18000fbed  lea     r15, [rax+rax*8]
0x18000fbf1  mov     [rsp+0F8h+var_A0], r15
0x18000fbf6  mov     r13, [rsp+0F8h+var_80]
0x18000fbfb  mov     r13, [r14+r13]
0x18000fbff  mov     [rsp+0F8h+var_98], r13
0x18000fc04  mov     [r13+r15*8+4], ebx
0x18000fc09  mov     eax, 4
0x18000fc0e  cmp     si, ax
0x18000fc11  jnb     short loc_18000FC6E
0x18000fc13  mov     edx, 85h; unsigned int
0x18000fc18  mov     ecx, 80004005h; int
0x18000fc1d  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18000fc22  mov     r15d, eax
0x18000fc25  test    eax, eax
0x18000fc27  jns     short loc_18000FC69
0x18000fc29  test    byte ptr cs:_bidGblFlags, dil
0x18000fc30  jz      short loc_18000FC61
0x18000fc32  mov     rcx, cs:off_1800487B8; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fc39  test    rcx, rcx
0x18000fc3c  jz      short loc_18000FC61
0x18000fc3e  mov     dword ptr [rsp+0F8h+var_D8], 38Dh
0x18000fc46  mov     r9d, eax
0x18000fc49  mov     r8, cs:off_1800487B8; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fc50  mov     edx, 0E3400h
0x18000fc55  mov     rcx, cs:off_1800481C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000fc5c  call    _bidTraceW
0x18000fc61  mov     ecx, r15d; int
0x18000fc64  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000fc69  mov     r15, [rsp+0F8h+var_A0]
0x18000fc6e  mov     eax, [r12]
0x18000fc72  mov     [r13+r15*8+0], eax
0x18000fc77  sub     si, 4
0x18000fc7b  cmp     si, di
0x18000fc7e  jnb     short loc_18000FCDB
0x18000fc80  mov     edx, 85h; unsigned int
0x18000fc85  mov     ecx, 80004005h; int
0x18000fc8a  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18000fc8f  mov     r15d, eax
0x18000fc92  test    eax, eax
0x18000fc94  jns     short loc_18000FCD6
0x18000fc96  test    byte ptr cs:_bidGblFlags, dil
0x18000fc9d  jz      short loc_18000FCCE
0x18000fc9f  mov     rcx, cs:off_1800487B0; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fca6  test    rcx, rcx
0x18000fca9  jz      short loc_18000FCCE
0x18000fcab  mov     dword ptr [rsp+0F8h+var_D8], 394h
0x18000fcb3  mov     r9d, eax
0x18000fcb6  mov     r8, cs:off_1800487B0; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fcbd  mov     edx, 0E5000h
0x18000fcc2  mov     rcx, cs:off_1800481C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000fcc9  call    _bidTraceW
0x18000fcce  mov     ecx, r15d; int
0x18000fcd1  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000fcd6  mov     r15, [rsp+0F8h+var_A0]
0x18000fcdb  movzx   r13d, word ptr [r12+4]
0x18000fce1  add     r12, 6
0x18000fce5  sub     si, di
0x18000fce8  mov     rax, [rsp+0F8h+var_98]
0x18000fced  lea     rax, [rax+r15*8]
0x18000fcf1  add     rax, 30h ; '0'
0x18000fcf5  mov     [rsp+0F8h+var_88], rax
0x18000fcfa  mov     rcx, rax; pvarg
0x18000fcfd  call    cs:__imp_VariantInit
0x18000fd03  mov     r10, [rsp+0F8h+var_90]
0x18000fd08  mov     edx, 1
0x18000fd0d  movzx   r9d, dx
0x18000fd11  test    r10, r10
0x18000fd14  jz      loc_18000FDE3
0x18000fd1a  mov     rax, [rsp+0F8h+var_98]
0x18000fd1f  mov     r11d, [rax+r15*8]
0x18000fd23  mov     ecx, ebx
0x18000fd25  cmp     ecx, [r10+8]
0x18000fd29  jnb     loc_18000FDE3
0x18000fd2f  mov     eax, ecx
0x18000fd31  lea     r8, [rax+rax*2]
0x18000fd35  add     r8, r8
0x18000fd38  mov     rax, [r10]
0x18000fd3b  cmp     [rax+r8*8+8], r11d
0x18000fd40  jz      short loc_18000FD46
0x18000fd42  add     ecx, edx
0x18000fd44  jmp     short loc_18000FD25
0x18000fd46  movzx   r9d, word ptr [rax+r8*8+10h]
0x18000fd4c  mov     ecx, 3
0x18000fd51  cmp     r9w, cx
0x18000fd55  jnz     loc_18000FDE3
0x18000fd5b  mov     rax, [rsp+0F8h+var_88]
0x18000fd60  mov     [rax], cx
0x18000fd63  lea     r13d, [rcx+1]
0x18000fd67  cmp     si, r13w
0x18000fd6b  jnb     short loc_18000FDC8
0x18000fd6d  mov     edx, 85h; unsigned int
0x18000fd72  mov     ecx, 80004005h; int
0x18000fd77  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18000fd7c  mov     r15d, eax
0x18000fd7f  test    eax, eax
0x18000fd81  jns     short loc_18000FDC3
0x18000fd83  test    byte ptr cs:_bidGblFlags, dil
0x18000fd8a  jz      short loc_18000FDBB
0x18000fd8c  mov     rcx, cs:off_1800487A0; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fd93  test    rcx, rcx
0x18000fd96  jz      short loc_18000FDBB
0x18000fd98  mov     dword ptr [rsp+0F8h+var_D8], 3ABh
0x18000fda0  mov     r9d, eax
0x18000fda3  mov     r8, cs:off_1800487A0; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fdaa  mov     edx, 0EAC00h
0x18000fdaf  mov     rcx, cs:off_1800481C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000fdb6  call    _bidTraceW
0x18000fdbb  mov     ecx, r15d; int
0x18000fdbe  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000fdc3  mov     r15, [rsp+0F8h+var_A0]
0x18000fdc8  mov     eax, [r12]
0x18000fdcc  mov     rcx, [rsp+0F8h+var_98]
0x18000fdd1  mov     [rcx+r15*8+38h], eax
0x18000fdd6  add     r12, r13
0x18000fdd9  mov     eax, 0FFFCh
0x18000fdde  jmp     loc_18000FEDF
0x18000fde3  mov     ecx, 8
0x18000fde8  cmp     r9w, cx
0x18000fdec  jz      loc_18000FEE7
0x18000fdf2  mov     ecx, 0Bh
0x18000fdf7  cmp     r9w, cx
0x18000fdfb  jz      short loc_18000FE5F
0x18000fdfd  cmp     si, r13w
0x18000fe01  jnb     loc_18000FF73
0x18000fe07  lea     edx, [rcx+7Ah]; unsigned int
0x18000fe0a  mov     ecx, 80004005h; int
0x18000fe0f  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18000fe14  mov     r15d, eax
0x18000fe17  test    eax, eax
0x18000fe19  jns     loc_18000FF73
0x18000fe1f  test    byte ptr cs:_bidGblFlags, dil
0x18000fe26  jz      short loc_18000FE57
0x18000fe28  mov     rcx, cs:off_180048790; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fe2f  test    rcx, rcx
0x18000fe32  jz      short loc_18000FE57
0x18000fe34  mov     dword ptr [rsp+0F8h+var_D8], 3C2h
0x18000fe3c  mov     r9d, eax
0x18000fe3f  mov     r8, cs:off_180048790; "<CADTGRowset::arReadProperties|ADO|ERR>"...
0x18000fe46  mov     edx, 0F0800h
0x18000fe4b  mov     rcx, cs:off_1800481C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000fe52  call    _bidTraceW
  ... truncated ...
```
