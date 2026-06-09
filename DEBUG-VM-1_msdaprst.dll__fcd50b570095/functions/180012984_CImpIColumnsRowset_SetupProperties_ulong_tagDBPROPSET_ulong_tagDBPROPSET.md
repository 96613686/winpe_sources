# CImpIColumnsRowset::SetupProperties(ulong *,tagDBPROPSET * *,ulong,tagDBPROPSET *)

- ea: `0x180012984`
- end: `0x180012d44`
- name: `?SetupProperties@CImpIColumnsRowset@@AEAAXPEAKPEAPEAUtagDBPROPSET@@KPEAU2@@Z`
- size: `960`
- prototype: `void __fastcall(CImpIColumnsRowset *__hidden this, unsigned int *, struct tagDBPROPSET **, unsigned int, struct tagDBPROPSET *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180011f90`

## callees

- `0x180012984`
- `0x18001a6c8`
- `0x18002ccd0`
- `0x18002cd54`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180012a34`
- `ole32!CoTaskMemAlloc` at `0x180012ae7`
- `ole32!CoTaskMemAlloc` at `0x180012c6a`
- `ole32!CoTaskMemAlloc` at `0x180012a34`
- `ole32!CoTaskMemAlloc` at `0x180012ae7`
- `ole32!CoTaskMemAlloc` at `0x180012c6a`
- `OLEAUT32!__imp_VariantInit` at `0x180012b4c`
- `OLEAUT32!__imp_VariantInit` at `0x180012d0d`
- `OLEAUT32!__imp_VariantInit` at `0x180012b4c`
- `OLEAUT32!__imp_VariantInit` at `0x180012d0d`
- `OLEAUT32!__imp_VariantCopy` at `0x180012b88`
- `OLEAUT32!__imp_VariantCopy` at `0x180012b88`

## pseudocode

```c
void __fastcall CImpIColumnsRowset::SetupProperties(
        CImpIColumnsRowset *this,
        unsigned int *a2,
        struct tagDBPROPSET **a3,
        unsigned int a4,
        struct tagDBPROPSET *a5)
{
  int v5; // r14d
  unsigned int i; // r8d
  int v10; // r8d
  __int64 v11; // r9
  __int64 j; // rdx
  struct tagDBPROPSET *v13; // rax
  unsigned int k; // r12d
  __int64 v15; // rbx
  struct tagDBPROPSET *v16; // rcx
  __int64 v17; // rax
  ULONG cProperties; // eax
  __int64 m; // rbp
  __int64 v20; // r8
  __int64 n; // rbp
  HRESULT v22; // r14d
  unsigned int v23; // ebp
  __int64 v24; // rbx
  __int64 v25; // rdi
  __int64 v26; // rbx
  int v27; // [rsp+70h] [rbp+8h]
  int v28; // [rsp+88h] [rbp+20h]

  v5 = 0;
  v28 = 0;
  v27 = -1;
  for ( i = 0; ; i = v10 + 1 )
  {
    if ( i >= a4 )
      goto LABEL_11;
    if ( (unsigned int)IsSame(&a5[i].guidPropertySet, &DBPROPSET_ROWSET) )
      break;
  }
  v27 = v10;
  if ( v10 == -1 )
  {
LABEL_11:
    *a2 = a4 + 1;
    goto LABEL_12;
  }
  *a2 = a4;
  for ( j = 0; (unsigned int)j < *(ULONG *)((char *)&a5->cProperties + v11); j = (unsigned int)(j + 1) )
  {
    if ( (*(DBPROP **)((char *)&a5->rgProperties + v11))[j].dwPropertyID == 134 )
    {
      v5 = 1;
      v28 = 1;
      break;
    }
  }
LABEL_12:
  v13 = (struct tagDBPROPSET *)CoTaskMemAlloc(32LL * *a2);
  *a3 = v13;
  if ( !v13 )
  {
    *a2 = 0;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_180048930[0] )
        bidTraceW(off_1800481D0[0], 324608, off_180048930[0], 2147942414LL, 317);
    }
    goto LABEL_44;
  }
  for ( k = 0; k < a4; ++k )
  {
    v15 = k;
    (*a3)[v15].guidPropertySet = a5[v15].guidPropertySet;
    v16 = &(*a3)[v15];
    v17 = *(_QWORD *)&v16->guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_ROWSET.Data1;
    if ( !v17 )
      v17 = *(_QWORD *)v16->guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_ROWSET.Data4;
    if ( v17 || v5 )
      cProperties = a5[v15].cProperties;
    else
      cProperties = a5[v15].cProperties + 1;
    v16->cProperties = cProperties;
    (*a3)[v15].rgProperties = (DBPROP *)CoTaskMemAlloc(72LL * (*a3)[v15].cProperties);
    if ( !(*a3)[k].rgProperties )
    {
      (*a3)[v15].cProperties = 0;
      if ( (bidGblFlags & 2) != 0 && off_180048928[0] )
        bidTraceW(off_1800481D0[0], 339968, off_180048928[0], 2147942414LL, 332);
      goto LABEL_44;
    }
    for ( m = 0; (unsigned int)m < a5[v15].cProperties; m = (unsigned int)(m + 1) )
    {
      v20 = m;
      (*a3)[k].rgProperties[v20].dwPropertyID = a5[k].rgProperties[m].dwPropertyID;
      (*a3)[k].rgProperties[v20].dwOptions = a5[k].rgProperties[m].dwOptions;
      VariantInit(&(*a3)[v15].rgProperties[m].vValue);
    }
    for ( n = 0; (unsigned int)n < a5[v15].cProperties; n = (unsigned int)(n + 1) )
    {
      v22 = VariantCopy(&(*a3)[k].rgProperties[n].vValue, &a5[k].rgProperties[n].vValue);
      if ( v22 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048920[0] )
          bidTraceW(off_1800481D0[0], 354304, off_180048920[0], (unsigned int)v22, 346);
        ThrowHR(v22);
      }
    }
    v5 = v28;
  }
  v23 = v27;
  if ( v27 == -1 )
  {
    v23 = *a2 - 1;
    v24 = v23;
    (*a3)[v24].guidPropertySet = DBPROPSET_ROWSET;
    (*a3)[v24].cProperties = 1;
    (*a3)[v24].rgProperties = (DBPROP *)CoTaskMemAlloc(72LL * (*a3)[v24].cProperties);
    if ( !(*a3)[v24].rgProperties )
    {
      (*a3)[v24].cProperties = 0;
      if ( (bidGblFlags & 2) != 0 && off_180048918[0] )
        bidTraceW(off_1800481D0[0], 368640, off_180048918[0], 2147942414LL, 360);
LABEL_44:
      ThrowHR(-2147024882);
    }
  }
  if ( !v5 )
  {
    v25 = v23;
    v26 = (*a3)[v25].cProperties - 1;
    (*a3)[v25].rgProperties[v26].dwPropertyID = 134;
    (*a3)[v25].rgProperties[v26].dwOptions = 0;
    VariantInit(&(*a3)[v25].rgProperties[v26].vValue);
    (*a3)[v25].rgProperties[v26].vValue.vt = 11;
    (*a3)[v25].rgProperties[v26].vValue.iVal = -1;
  }
}

```

## disassembly

```asm
0x180012984  mov     [rsp+arg_8], rbx
0x180012989  mov     [rsp+arg_0], rcx
0x18001298e  push    rbp
0x18001298f  push    rsi
0x180012990  push    rdi
0x180012991  push    r12
0x180012993  push    r13
0x180012995  push    r14
0x180012997  push    r15
0x180012999  sub     rsp, 30h
0x18001299d  mov     rdi, [rsp+68h+arg_20]
0x1800129a5  xor     r14d, r14d
0x1800129a8  or      ebx, 0FFFFFFFFh
0x1800129ab  mov     [rsp+68h+arg_18], r14d
0x1800129b3  mov     rsi, r8
0x1800129b6  mov     dword ptr [rsp+68h+arg_0], ebx
0x1800129ba  xor     r8d, r8d
0x1800129bd  mov     r13d, r9d
0x1800129c0  mov     r15, rdx
0x1800129c3  cmp     r8d, r13d
0x1800129c6  jnb     short loc_180012A26
0x1800129c8  mov     r9d, r8d
0x1800129cb  lea     rcx, [rdi+0Ch]
0x1800129cf  shl     r9, 5
0x1800129d3  lea     rdx, DBPROPSET_ROWSET; struct _GUID *
0x1800129da  add     rcx, r9; struct _GUID *
0x1800129dd  call    ?IsSame@@YAHAEBU_GUID@@0@Z; IsSame(_GUID const &,_GUID const &)
0x1800129e2  test    eax, eax
0x1800129e4  jnz     short loc_1800129EB
0x1800129e6  inc     r8d
0x1800129e9  jmp     short loc_1800129C3
0x1800129eb  mov     dword ptr [rsp+68h+arg_0], r8d
0x1800129f0  cmp     r8d, ebx
0x1800129f3  jz      short loc_180012A26
0x1800129f5  mov     [r15], r13d
0x1800129f8  xor     edx, edx
0x1800129fa  cmp     edx, [r9+rdi+8]
0x1800129ff  jnb     short loc_180012A2D
0x180012a01  mov     rax, [r9+rdi]
0x180012a05  lea     rcx, [rdx+rdx*8]
0x180012a09  cmp     dword ptr [rax+rcx*8], 86h
0x180012a10  jz      short loc_180012A16
0x180012a12  inc     edx
0x180012a14  jmp     short loc_1800129FA
0x180012a16  mov     r14d, 1
0x180012a1c  mov     [rsp+68h+arg_18], r14d
0x180012a24  jmp     short loc_180012A2D
0x180012a26  lea     eax, [r13+1]
0x180012a2a  mov     [r15], eax
0x180012a2d  mov     ecx, [r15]
0x180012a30  shl     rcx, 5; cb
0x180012a34  call    cs:__imp_CoTaskMemAlloc
0x180012a3a  mov     [rsi], rax
0x180012a3d  test    rax, rax
0x180012a40  jnz     short loc_180012A7B
0x180012a42  mov     [r15], eax
0x180012a45  test    byte ptr cs:_bidGblFlags, 2
0x180012a4c  jz      loc_180012CC4
0x180012a52  mov     rax, cs:off_180048930; "<CImpIColumnsRowset::SetupProperties|AD"...
0x180012a59  test    rax, rax
0x180012a5c  jz      loc_180012CC4
0x180012a62  mov     r8, cs:off_180048930; "<CImpIColumnsRowset::SetupProperties|AD"...
0x180012a69  mov     edx, 4F400h
0x180012a6e  mov     [rsp+68h+var_48], 13Dh
0x180012a76  jmp     loc_180012CB2
0x180012a7b  xor     r12d, r12d
0x180012a7e  cmp     r12d, r13d
0x180012a81  jnb     loc_180012C28
0x180012a87  mov     rax, [rsi]
0x180012a8a  mov     ebx, r12d
0x180012a8d  shl     rbx, 5
0x180012a91  movups  xmm0, xmmword ptr [rbx+rdi+0Ch]
0x180012a96  movdqu  xmmword ptr [rax+rbx+0Ch], xmm0
0x180012a9c  mov     rcx, [rsi]
0x180012a9f  add     rcx, rbx
0x180012aa2  mov     rax, [rcx+0Ch]
0x180012aa6  sub     rax, qword ptr cs:DBPROPSET_ROWSET.Data1
0x180012aad  jnz     short loc_180012ABA
0x180012aaf  mov     rax, [rcx+14h]
0x180012ab3  sub     rax, qword ptr cs:DBPROPSET_ROWSET.Data4
0x180012aba  test    rax, rax
0x180012abd  jnz     short loc_180012ACC
0x180012abf  test    r14d, r14d
0x180012ac2  jnz     short loc_180012ACC
0x180012ac4  mov     eax, [rbx+rdi+8]
0x180012ac8  inc     eax
0x180012aca  jmp     short loc_180012AD0
0x180012acc  mov     eax, [rbx+rdi+8]
0x180012ad0  mov     edx, 8
0x180012ad5  mov     [rdx+rcx], eax
0x180012ad8  mov     rax, [rsi]
0x180012adb  mov     ecx, [rax+rbx+8]
0x180012adf  lea     rcx, [rcx+rcx*8]
0x180012ae3  shl     rcx, 3; cb
0x180012ae7  call    cs:__imp_CoTaskMemAlloc
0x180012aed  mov     rcx, [rsi]
0x180012af0  mov     [rbx+rcx], rax
0x180012af4  mov     rax, [rsi]
0x180012af7  cmp     qword ptr [rax+rbx], 0
0x180012afc  jz      loc_180012BEA
0x180012b02  xor     ebp, ebp
0x180012b04  cmp     [rbx+rdi+8], ebp
0x180012b08  jbe     short loc_180012B5A
0x180012b0a  mov     rax, [rsi]
0x180012b0d  lea     r8, ds:0[rbp*8]
0x180012b15  mov     rdx, [rbx+rdi]
0x180012b19  add     r8, rbp
0x180012b1c  mov     rcx, [rax+rbx]
0x180012b20  mov     eax, [rdx+r8*8]
0x180012b24  mov     [rcx+r8*8], eax
0x180012b28  mov     rax, [rsi]
0x180012b2b  mov     rdx, [rbx+rdi]
0x180012b2f  mov     rcx, [rax+rbx]
0x180012b33  mov     eax, [rdx+r8*8+4]
0x180012b38  mov     [rcx+r8*8+4], eax
0x180012b3d  mov     rax, [rsi]
0x180012b40  mov     rcx, [rbx+rax]
0x180012b44  lea     rcx, [rcx+r8*8]
0x180012b48  add     rcx, 30h ; '0'; pvarg
0x180012b4c  call    cs:__imp_VariantInit
0x180012b52  inc     ebp
0x180012b54  cmp     ebp, [rbx+rdi+8]
0x180012b58  jb      short loc_180012B0A
0x180012b5a  xor     ebp, ebp
0x180012b5c  cmp     ebp, [rbx+rdi+8]
0x180012b60  jnb     short loc_180012B99
0x180012b62  mov     rax, [rsi]
0x180012b65  lea     r8, ds:0[rbp*8]
0x180012b6d  mov     rdx, [rbx+rdi]
0x180012b71  add     r8, rbp
0x180012b74  add     rdx, 30h ; '0'
0x180012b78  mov     rcx, [rax+rbx]
0x180012b7c  lea     rdx, [rdx+r8*8]; pvargSrc
0x180012b80  lea     rcx, [rcx+r8*8]
0x180012b84  add     rcx, 30h ; '0'; pvargDest
0x180012b88  call    cs:__imp_VariantCopy
0x180012b8e  mov     r14d, eax
0x180012b91  test    eax, eax
0x180012b93  js      short loc_180012BA9
0x180012b95  inc     ebp
0x180012b97  jmp     short loc_180012B5C
0x180012b99  mov     r14d, [rsp+68h+arg_18]
0x180012ba1  inc     r12d
0x180012ba4  jmp     loc_180012A7E
0x180012ba9  test    byte ptr cs:_bidGblFlags, 2
0x180012bb0  jz      short loc_180012BE1
0x180012bb2  mov     rax, cs:off_180048920; "<CImpIColumnsRowset::SetupProperties|AD"...
0x180012bb9  test    rax, rax
0x180012bbc  jz      short loc_180012BE1
0x180012bbe  mov     r8, cs:off_180048920; "<CImpIColumnsRowset::SetupProperties|AD"...
0x180012bc5  mov     r9d, r14d
0x180012bc8  mov     rcx, cs:off_1800481D0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180012bcf  mov     edx, 56800h
0x180012bd4  mov     [rsp+68h+var_48], 15Ah
0x180012bdc  call    _bidTraceW
0x180012be1  mov     ecx, r14d; int
0x180012be4  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180012bea  mov     dword ptr [rax+rbx+8], 0
0x180012bf2  test    byte ptr cs:_bidGblFlags, 2
0x180012bf9  jz      loc_180012CC4
0x180012bff  mov     rax, cs:off_180048928; "<CImpIColumnsRowset::SetupProperties|AD"...
0x180012c06  test    rax, rax
0x180012c09  jz      loc_180012CC4
0x180012c0f  mov     r8, cs:off_180048928; "<CImpIColumnsRowset::SetupProperties|AD"...
0x180012c16  mov     edx, 53000h
0x180012c1b  mov     [rsp+68h+var_48], 14Ch
0x180012c23  jmp     loc_180012CB2
0x180012c28  mov     ebp, dword ptr [rsp+68h+arg_0]
0x180012c2c  cmp     ebp, 0FFFFFFFFh
0x180012c2f  jnz     loc_180012CCF
0x180012c35  mov     ebp, [r15]
0x180012c38  mov     rax, [rsi]
0x180012c3b  dec     ebp
0x180012c3d  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x180012c44  mov     ebx, ebp
0x180012c46  shl     rbx, 5
0x180012c4a  movdqu  xmmword ptr [rbx+rax+0Ch], xmm0
0x180012c50  mov     rax, [rsi]
0x180012c53  mov     dword ptr [rbx+rax+8], 1
0x180012c5b  mov     rax, [rsi]
0x180012c5e  mov     ecx, [rbx+rax+8]
0x180012c62  lea     rcx, [rcx+rcx*8]
0x180012c66  shl     rcx, 3; cb
0x180012c6a  call    cs:__imp_CoTaskMemAlloc
0x180012c70  mov     rcx, [rsi]
0x180012c73  mov     [rbx+rcx], rax
0x180012c77  mov     rax, [rsi]
0x180012c7a  cmp     qword ptr [rbx+rax], 0
0x180012c7f  jnz     short loc_180012CCF
0x180012c81  mov     dword ptr [rbx+rax+8], 0
0x180012c89  test    byte ptr cs:_bidGblFlags, 2
0x180012c90  jz      short loc_180012CC4
0x180012c92  mov     rax, cs:off_180048918; "<CImpIColumnsRowset::SetupProperties|AD"...
0x180012c99  test    rax, rax
0x180012c9c  jz      short loc_180012CC4
0x180012c9e  mov     r8, cs:off_180048918; "<CImpIColumnsRowset::SetupProperties|AD"...
0x180012ca5  mov     edx, 5A000h
0x180012caa  mov     [rsp+68h+var_48], 168h
0x180012cb2  mov     rcx, cs:off_1800481D0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180012cb9  mov     r9d, 8007000Eh
0x180012cbf  call    _bidTraceW
0x180012cc4  mov     ecx, 8007000Eh; int
0x180012cc9  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180012ccf  test    r14d, r14d
0x180012cd2  jnz     short loc_180012D2F
0x180012cd4  mov     rcx, [rsi]
0x180012cd7  mov     edi, ebp
0x180012cd9  shl     rdi, 5
0x180012cdd  mov     eax, [rdi+rcx+8]
0x180012ce1  dec     eax
0x180012ce3  lea     rbx, [rax+rax*8]
0x180012ce7  mov     rax, [rdi+rcx]
0x180012ceb  mov     dword ptr [rax+rbx*8], 86h
0x180012cf2  mov     rax, [rsi]
0x180012cf5  mov     rcx, [rdi+rax]
0x180012cf9  mov     [rcx+rbx*8+4], r14d
0x180012cfe  mov     rax, [rsi]
0x180012d01  mov     rcx, [rdi+rax]
0x180012d05  lea     rcx, [rcx+rbx*8]
0x180012d09  add     rcx, 30h ; '0'; pvarg
0x180012d0d  call    cs:__imp_VariantInit
0x180012d13  mov     rax, [rsi]
0x180012d16  mov     rcx, [rdi+rax]
0x180012d1a  mov     word ptr [rcx+rbx*8+30h], 0Bh
0x180012d21  mov     rax, [rsi]
0x180012d24  mov     rcx, [rdi+rax]
0x180012d28  mov     word ptr [rcx+rbx*8+38h], 0FFFFh
0x180012d2f  mov     rbx, [rsp+68h+arg_8]
0x180012d34  add     rsp, 30h
0x180012d38  pop     r15
0x180012d3a  pop     r14
0x180012d3c  pop     r13
0x180012d3e  pop     r12
0x180012d40  pop     rdi
0x180012d41  pop     rsi
0x180012d42  pop     rbp
0x180012d43  retn
```
