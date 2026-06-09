# GetProperties(CPropertyBag &,long,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x1800139e8`
- end: `0x180013cb0`
- name: `?GetProperties@@YAXAEAVCPropertyBag@@JPEAUtagPROPVARIANT@@1@Z`
- size: `712`
- prototype: `void __fastcall(struct CPropertyBag *, int, struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800130a0`

## callees

- `0x180003d54`
- `0x180012654`
- `0x1800139e8`
- `0x180017aa0`
- `0x1800434c6`
- `0x180046010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180013bf8`
- `OLEAUT32!__imp_SysFreeString` at `0x180013bf8`
- `OLEAUT32!__imp_VariantInit` at `0x180013b6a`
- `OLEAUT32!__imp_VariantInit` at `0x180013b6a`
- `OLEAUT32!__imp_VariantClear` at `0x180013bee`
- `OLEAUT32!__imp_VariantClear` at `0x180013bee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013a7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013aad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013a7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013aad`
- `PROPSYS!VariantToPropVariant` at `0x180013be2`
- `PROPSYS!VariantToPropVariant` at `0x180013be2`

## string_xrefs

- `0x180013c50`: `com\complus\src\events\tier1\subscription.cpp`
- `0x180013c71`: `com\complus\src\events\tier1\subscription.cpp`
- `0x180013c93`: `com\complus\src\events\tier1\subscription.cpp`

## pseudocode

```c
void __fastcall GetProperties(
        struct CPropertyBag *a1,
        unsigned int a2,
        struct tagPROPVARIANT *a3,
        struct tagPROPVARIANT *a4)
{
  __int64 v4; // rax
  __int64 v6; // rsi
  int v8; // eax
  unsigned int v9; // ecx
  unsigned int v10; // ebx
  size_t v11; // rdi
  BYTE *v12; // rax
  BYTE *v13; // rax
  __int64 i; // rdi
  int v15; // eax
  int v16; // ebx
  HRESULT v17; // ebx
  BYTE *pData; // rax
  __int64 v19; // rcx
  unsigned int v20; // edx
  __int64 v21; // [rsp+30h] [rbp-48h] BYREF
  __int64 v22; // [rsp+38h] [rbp-40h] BYREF
  __int64 v23; // [rsp+40h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-28h] BYREF
  int v26; // [rsp+B0h] [rbp+38h] BYREF

  v4 = *(_QWORD *)a1;
  v6 = a2;
  v22 = 0;
  if ( (*(int (__fastcall **)(struct CPropertyBag *, __int64 *))(v4 + 72))(a1, &v22) < 0 )
    goto LABEL_21;
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 40LL))(v22);
  if ( v8 < 0 || v8 == 1 )
    goto LABEL_21;
  if ( (int)v6 < 0 )
  {
    v20 = 2354;
    goto LABEL_25;
  }
  v9 = 8 * v6;
  if ( (unsigned __int64)(8 * v6) > 0xFFFFFFFF )
  {
    v20 = 2364;
    goto LABEL_25;
  }
  v10 = 24 * v6;
  if ( (unsigned __int64)(24 * v6) > 0xFFFFFFFF )
  {
    v20 = 2371;
LABEL_25:
    InternalAssert(L"com\\complus\\src\\events\\tier1\\subscription.cpp", v20, 0x10u, L"0");
    goto LABEL_21;
  }
  v11 = v9;
  a3->vt = 4127;
  a3->lVal = v6;
  v12 = (BYTE *)CoTaskMemAlloc(v9);
  a3->bstrblobVal.pData = v12;
  if ( !v12 )
    InternalError(L"com\\complus\\src\\events\\tier1\\subscription.cpp", 0x94Au, 0xC0001204, 0x10u);
  memset_0(a3->bstrblobVal.pData, 0, v11);
  a4->vt = 4108;
  a4->lVal = v6;
  v13 = (BYTE *)CoTaskMemAlloc(v10);
  a4->bstrblobVal.pData = v13;
  if ( !v13 )
    InternalError(L"com\\complus\\src\\events\\tier1\\subscription.cpp", 0x94Fu, 0xC0001204, 0x10u);
  memset_0(a4->bstrblobVal.pData, 0, v10);
  for ( i = 0; (int)i < (int)v6; i = (unsigned int)(i + 1) )
  {
    v23 = 0;
    v26 = 1;
    v15 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v22 + 32LL))(v22, 1, &v23, &v26);
    if ( v15 == 1 )
      break;
    if ( v15 < 0 )
      break;
    v21 = 0;
    v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v23)(v23, &IID_IEventProperty, &v21);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    if ( v16 < 0 )
      break;
    bstrString = 0;
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v17 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v21 + 56LL))(v21, &bstrString);
    if ( v17 >= 0 )
    {
      v17 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v21 + 72LL))(v21, &pvarg);
      if ( v17 >= 0 )
      {
        *(_QWORD *)&a3->bstrblobVal.pData[8 * i] = WStringCopy(bstrString);
        if ( !*(_QWORD *)&a3->bstrblobVal.pData[8 * i] )
          break;
        pData = a4->bstrblobVal.pData;
        v19 = 3 * i;
        *(_OWORD *)&pData[8 * v19] = 0;
        *(_QWORD *)&pData[8 * v19 + 16] = 0;
        v17 = VariantToPropVariant(&pvarg, (PROPVARIANT *)&a4->bstrblobVal.pData[24 * i]);
      }
    }
    VariantClear(&pvarg);
    SysFreeString(bstrString);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    if ( v17 < 0 )
      break;
  }
LABEL_21:
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
}

```

## disassembly

```asm
0x1800139e8  push    rbp
0x1800139ea  push    rbx
0x1800139eb  push    rsi
0x1800139ec  push    rdi
0x1800139ed  push    r14
0x1800139ef  push    r15
0x1800139f1  mov     rbp, rsp
0x1800139f4  sub     rsp, 78h
0x1800139f8  mov     rax, [rcx]
0x1800139fb  mov     r15, r9
0x1800139fe  mov     esi, edx
0x180013a00  mov     r14, r8
0x180013a03  lea     rdx, [rbp+var_40]
0x180013a07  mov     [rbp+var_40], 0
0x180013a0f  mov     rax, [rax+48h]
0x180013a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a18  test    eax, eax
0x180013a1a  js      loc_180013C1C
0x180013a20  mov     rcx, [rbp+var_40]
0x180013a24  mov     rax, [rcx]
0x180013a27  mov     rax, [rax+28h]
0x180013a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a30  test    eax, eax
0x180013a32  js      loc_180013C1C
0x180013a38  cmp     eax, 1
0x180013a3b  jz      loc_180013C1C
0x180013a41  test    esi, esi
0x180013a43  js      loc_180013C65
0x180013a49  lea     rcx, ds:0[rsi*8]
0x180013a51  mov     edx, 0FFFFFFFFh
0x180013a56  cmp     rcx, rdx
0x180013a59  ja      loc_180013C5E
0x180013a5f  lea     rbx, [rsi+rsi*2]
0x180013a63  shl     rbx, 3
0x180013a67  cmp     rbx, rdx
0x180013a6a  ja      loc_180013C3E
0x180013a70  mov     edi, ecx
0x180013a72  mov     ecx, ecx; cb
0x180013a74  mov     word ptr [r14], 101Fh
0x180013a7a  mov     [r14+8], esi
0x180013a7e  call    cs:__imp_CoTaskMemAlloc
0x180013a84  mov     [r14+10h], rax
0x180013a88  test    rax, rax
0x180013a8b  jz      loc_180013C6C
0x180013a91  mov     rcx, [r14+10h]; void *
0x180013a95  mov     r8, rdi; Size
0x180013a98  xor     edx, edx; Val
0x180013a9a  call    memset_0
0x180013a9f  mov     ebx, ebx
0x180013aa1  mov     ecx, ebx; cb
0x180013aa3  mov     word ptr [r15], 100Ch
0x180013aa9  mov     [r15+8], esi
0x180013aad  call    cs:__imp_CoTaskMemAlloc
0x180013ab3  mov     [r15+10h], rax
0x180013ab7  test    rax, rax
0x180013aba  jz      loc_180013C8E
0x180013ac0  mov     rcx, [r15+10h]; void *
0x180013ac4  mov     r8, rbx; Size
0x180013ac7  xor     edx, edx; Val
0x180013ac9  call    memset_0
0x180013ace  xor     edi, edi
0x180013ad0  test    esi, esi
0x180013ad2  jle     loc_180013C1C
0x180013ad8  mov     rcx, [rbp+var_40]
0x180013adc  lea     r9, [rbp+arg_0]
0x180013ae0  mov     [rbp+var_38], 0
0x180013ae8  lea     r8, [rbp+var_38]
0x180013aec  mov     [rbp+arg_0], 1
0x180013af3  mov     edx, 1
0x180013af8  mov     rax, [rcx]
0x180013afb  mov     rax, [rax+20h]
0x180013aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b04  cmp     eax, 1
0x180013b07  jz      loc_180013C1C
0x180013b0d  test    eax, eax
0x180013b0f  js      loc_180013C1C
0x180013b15  mov     rcx, [rbp+var_38]
0x180013b19  lea     r8, [rbp+var_48]
0x180013b1d  mov     [rbp+var_48], 0
0x180013b25  lea     rdx, IID_IEventProperty
0x180013b2c  mov     rax, [rcx]
0x180013b2f  mov     rax, [rax]
0x180013b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b37  mov     rcx, [rbp+var_38]
0x180013b3b  mov     ebx, eax
0x180013b3d  mov     rdx, [rcx]
0x180013b40  mov     rax, [rdx+10h]
0x180013b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b49  test    ebx, ebx
0x180013b4b  js      loc_180013C1C
0x180013b51  xorps   xmm0, xmm0
0x180013b54  mov     [rbp+bstrString], 0
0x180013b5c  xor     eax, eax
0x180013b5e  lea     rcx, [rbp+pvarg]; pvarg
0x180013b62  movups  xmmword ptr [rbp+pvarg], xmm0
0x180013b66  mov     qword ptr [rbp+pvarg+10h], rax
0x180013b6a  call    cs:__imp_VariantInit
0x180013b70  mov     rcx, [rbp+var_48]
0x180013b74  lea     rdx, [rbp+bstrString]
0x180013b78  mov     rax, [rcx]
0x180013b7b  mov     rax, [rax+38h]
0x180013b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b84  mov     ebx, eax
0x180013b86  test    eax, eax
0x180013b88  js      short loc_180013BEA
0x180013b8a  mov     rcx, [rbp+var_48]
0x180013b8e  lea     rdx, [rbp+pvarg]
0x180013b92  mov     rax, [rcx]
0x180013b95  mov     rax, [rax+48h]
0x180013b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b9e  mov     ebx, eax
0x180013ba0  test    eax, eax
0x180013ba2  js      short loc_180013BEA
0x180013ba4  mov     rcx, [rbp+bstrString]; Src
0x180013ba8  call    ?WStringCopy@@YAPEAGPEBG@Z; WStringCopy(ushort const *)
0x180013bad  mov     rcx, [r14+10h]
0x180013bb1  mov     [rcx+rdi*8], rax
0x180013bb5  mov     rax, [r14+10h]
0x180013bb9  cmp     qword ptr [rax+rdi*8], 0
0x180013bbe  jz      short loc_180013C1C
0x180013bc0  mov     rax, [r15+10h]
0x180013bc4  lea     rcx, [rdi+rdi*2]
0x180013bc8  xor     edx, edx
0x180013bca  xorps   xmm0, xmm0
0x180013bcd  movups  xmmword ptr [rax+rcx*8], xmm0
0x180013bd1  mov     [rax+rcx*8+10h], rdx
0x180013bd6  mov     rax, [r15+10h]
0x180013bda  lea     rdx, [rax+rcx*8]; pPropVar
0x180013bde  lea     rcx, [rbp+pvarg]; pVar
0x180013be2  call    cs:__imp_VariantToPropVariant
0x180013be8  mov     ebx, eax
0x180013bea  lea     rcx, [rbp+pvarg]; pvarg
0x180013bee  call    cs:__imp_VariantClear
0x180013bf4  mov     rcx, [rbp+bstrString]; bstrString
0x180013bf8  call    cs:__imp_SysFreeString
0x180013bfe  mov     rcx, [rbp+var_48]
0x180013c02  mov     rax, [rcx]
0x180013c05  mov     rax, [rax+10h]
0x180013c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c0e  test    ebx, ebx
0x180013c10  js      short loc_180013C1C
0x180013c12  inc     edi
0x180013c14  cmp     edi, esi
0x180013c16  jl      loc_180013AD8
0x180013c1c  mov     rcx, [rbp+var_40]
0x180013c20  test    rcx, rcx
0x180013c23  jz      short loc_180013C31
0x180013c25  mov     rax, [rcx]
0x180013c28  mov     rax, [rax+10h]
0x180013c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c31  add     rsp, 78h
0x180013c35  pop     r15
0x180013c37  pop     r14
0x180013c39  pop     rdi
0x180013c3a  pop     rsi
0x180013c3b  pop     rbx
0x180013c3c  pop     rbp
0x180013c3d  retn
0x180013c3e  mov     edx, 943h; unsigned int
0x180013c43  lea     r9, a0; "0"
0x180013c4a  mov     r8d, 10h; unsigned __int16
0x180013c50  lea     rcx, aComComplusSrcE_15; "com\\complus\\src\\events\\tier1\\subsc"...
0x180013c57  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x180013c5c  jmp     short loc_180013C1C
0x180013c5e  mov     edx, 93Ch
0x180013c63  jmp     short loc_180013C43
0x180013c65  mov     edx, 932h
0x180013c6a  jmp     short loc_180013C43
0x180013c6c  mov     edx, 94Ah; unsigned int
0x180013c71  lea     rcx, aComComplusSrcE_15; "com\\complus\\src\\events\\tier1\\subsc"...
0x180013c78  mov     r9d, 10h; unsigned __int16
0x180013c7e  mov     r8d, 0C0001204h; unsigned int
0x180013c84  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180013c89  jmp     loc_180013A91
0x180013c8e  mov     edx, 94Fh; unsigned int
0x180013c93  lea     rcx, aComComplusSrcE_15; "com\\complus\\src\\events\\tier1\\subsc"...
0x180013c9a  mov     r9d, 10h; unsigned __int16
0x180013ca0  mov     r8d, 0C0001204h; unsigned int
0x180013ca6  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180013cab  jmp     loc_180013AC0
```
