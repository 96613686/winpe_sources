# std::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)

- ea: `0x18001e894`
- end: `0x18001eb5a`
- name: `??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z`
- size: `710`
- prototype: `VARIANTARG *__fastcall(const VARIANTARG **, const VARIANTARG *, const VARIANTARG *)`
- caller_count: `10`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180022204`
- `0x180023660`
- `0x180024d00`
- `0x180024fa8`
- `0x180025cac`
- `0x1800264a8`
- `0x180027df8`
- `0x180028534`
- `0x180029310`
- `0x18002e670`

## callees

- `0x18000193c`
- `0x180003858`
- `0x1800056c4`
- `0x1800056ec`
- `0x18001e894`
- `0x180020498`
- `0x180029aa0`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18001e9ce`
- `OLEAUT32!__imp_VariantCopy` at `0x18001ea13`
- `OLEAUT32!__imp_VariantCopy` at `0x18001ea54`
- `OLEAUT32!__imp_VariantCopy` at `0x18001eaae`
- `OLEAUT32!__imp_VariantCopy` at `0x18001e9ce`
- `OLEAUT32!__imp_VariantCopy` at `0x18001ea13`
- `OLEAUT32!__imp_VariantCopy` at `0x18001ea54`
- `OLEAUT32!__imp_VariantCopy` at `0x18001eaae`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
VARIANTARG *__fastcall std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(
        const VARIANTARG **a1,
        const VARIANTARG *a2,
        const VARIANTARG *a3)
{
  const VARIANTARG *v6; // rsi
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // rdi
  size_t v11; // rcx
  VARIANTARG *v12; // rbx
  IRecordInfo *v13; // rax
  __int64 v14; // r13
  VARIANTARG *v15; // rsi
  HRESULT v16; // eax
  const VARIANTARG *v17; // rax
  const VARIANTARG *v18; // rsi
  VARIANTARG *v19; // r14
  const VARIANTARG *v20; // r12
  HRESULT v21; // eax
  __int64 v22; // r14
  HRESULT v23; // eax
  VARIANTARG *v24; // rsi
  const VARIANTARG *v25; // r13
  HRESULT v26; // eax
  VARIANTARG *v28; // [rsp+20h] [rbp-40h]
  VARIANTARG *v29; // [rsp+28h] [rbp-38h]
  const VARIANTARG **v30; // [rsp+30h] [rbp-30h]
  _QWORD v31[2]; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v32; // [rsp+48h] [rbp-18h]
  VARIANTARG *v33; // [rsp+50h] [rbp-10h]
  VARIANTARG *v34; // [rsp+58h] [rbp-8h]
  unsigned __int64 v35; // [rsp+A8h] [rbp+48h]

  v6 = *a1;
  v7 = 0xAAAAAAAAAAAAAAABuLL * (((char *)a1[1] - (char *)*a1) >> 3);
  if ( v7 == 0xAAAAAAAAAAAAAAALL )
    std::vector<ATL::CComVariant>::_Xlength();
  v8 = 0xAAAAAAAAAAAAAAABuLL * (((char *)a1[2] - (char *)v6) >> 3);
  v9 = v8 >> 1;
  if ( v8 > 0xAAAAAAAAAAAAAAALL - (v8 >> 1) )
    goto LABEL_31;
  v35 = v7 + 1;
  v10 = v7 + 1;
  if ( v8 + v9 >= v7 + 1 )
    v10 = v8 + v9;
  if ( v10 > 0xAAAAAAAAAAAAAAALL )
    goto LABEL_31;
  v11 = 24 * v10;
  if ( !(24 * v10) )
  {
    v12 = 0;
    goto LABEL_14;
  }
  if ( v11 < 0x1000 )
  {
    v12 = (VARIANTARG *)operator new(v11);
    goto LABEL_14;
  }
  if ( v11 + 39 < v11 )
LABEL_31:
    __scrt_throw_std_bad_array_new_length();
  v13 = (IRecordInfo *)operator new(v11 + 39);
  if ( !v13 )
    __fastfail(5u);
  v12 = (VARIANTARG *)(((unsigned __int64)&v13[4].lpVtbl + 7) & 0xFFFFFFFFFFFFFFE0uLL);
  v12[-1].pRecInfo = v13;
LABEL_14:
  v14 = a2 - v6;
  v15 = &v12[v14];
  v31[0] = a1;
  v31[1] = v12;
  v32 = v10;
  v33 = v15 + 1;
  v34 = v15 + 1;
  v15->vt = 0;
  v16 = VariantCopy(v15, a3);
  if ( v16 < 0 )
  {
    v15->vt = 10;
    v15->lVal = v16;
    ATL::AtlThrowImpl(v16);
  }
  v33 = &v12[v14];
  v17 = a1[1];
  v18 = *a1;
  v28 = v12;
  v19 = v12;
  v29 = v12;
  v30 = a1;
  if ( a2 == v17 )
  {
    if ( v18 != v17 )
    {
      v20 = a1[1];
      do
      {
        v19->vt = 0;
        v21 = VariantCopy(v19, v18);
        if ( v21 < 0 )
        {
          v19->vt = 10;
          v19->lVal = v21;
          ATL::AtlThrowImpl(v21);
        }
        v29 = ++v19;
        ++v18;
      }
      while ( v18 != v20 );
    }
    v22 = v14;
  }
  else
  {
    while ( v18 != a2 )
    {
      v19->vt = 0;
      v23 = VariantCopy(v19, v18);
      if ( v23 < 0 )
      {
        v19->vt = 10;
        v19->lVal = v23;
        ATL::AtlThrowImpl(v23);
      }
      ++v19;
      ++v18;
    }
    v33 = v12;
    v22 = v14;
    v24 = &v12[v14 + 1];
    v25 = a1[1];
    v28 = v24;
    v29 = v24;
    v30 = a1;
    while ( a2 != v25 )
    {
      v24->vt = 0;
      v26 = VariantCopy(v24, a2);
      if ( v26 < 0 )
      {
        v24->vt = 10;
        v24->lVal = v26;
        ATL::AtlThrowImpl(v26);
      }
      v29 = ++v24;
      ++a2;
    }
  }
  std::vector<ATL::CComVariant>::_Change_array(a1, v12, v35, v10, v28, v29, v30, v31[0], 0, v32, v33, v34);
  std::vector<ATL::CComVariant>::_Reallocation_guard::~_Reallocation_guard(v31);
  return &v12[v22];
}

```

## disassembly

```asm
0x18001e894  mov     [rsp-38h+arg_10], rbx
0x18001e899  push    rbp
0x18001e89a  push    rsi
0x18001e89b  push    rdi
0x18001e89c  push    r12
0x18001e89e  push    r13
0x18001e8a0  push    r14
0x18001e8a2  push    r15
0x18001e8a4  mov     rbp, rsp
0x18001e8a7  sub     rsp, 60h
0x18001e8ab  mov     r14, r8
0x18001e8ae  mov     r12, rdx
0x18001e8b1  mov     r15, rcx
0x18001e8b4  mov     rsi, [rcx]
0x18001e8b7  mov     rdx, [rcx+8]
0x18001e8bb  sub     rdx, rsi
0x18001e8be  sar     rdx, 3
0x18001e8c2  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001e8cc  imul    rdx, rax
0x18001e8d0  mov     r9, 0AAAAAAAAAAAAAAAh
0x18001e8da  cmp     rdx, r9
0x18001e8dd  jz      loc_18001EB20
0x18001e8e3  mov     rcx, [rcx+10h]
0x18001e8e7  sub     rcx, rsi
0x18001e8ea  sar     rcx, 3
0x18001e8ee  imul    rcx, rax
0x18001e8f2  mov     r8, rcx
0x18001e8f5  shr     r8, 1
0x18001e8f8  mov     rax, r9
0x18001e8fb  sub     rax, r8
0x18001e8fe  cmp     rcx, rax
0x18001e901  ja      loc_18001EB1A
0x18001e907  inc     rdx
0x18001e90a  mov     [rbp+arg_8], rdx
0x18001e90e  lea     rax, [rcx+r8]
0x18001e912  mov     rdi, rdx
0x18001e915  cmp     rax, rdx
0x18001e918  cmovnb  rdi, rax
0x18001e91c  cmp     rdi, r9
0x18001e91f  ja      loc_18001EB1A
0x18001e925  lea     rax, [rdi+rdi*2]
0x18001e929  lea     rcx, ds:0[rax*8]; Size
0x18001e931  test    rcx, rcx
0x18001e934  jnz     short loc_18001E93A
0x18001e936  xor     ebx, ebx
0x18001e938  jmp     short loc_18001E978
0x18001e93a  cmp     rcx, 1000h
0x18001e941  jb      short loc_18001E970
0x18001e943  lea     rax, [rcx+27h]
0x18001e947  cmp     rax, rcx
0x18001e94a  jbe     loc_18001EB1A
0x18001e950  mov     rcx, rax; Size
0x18001e953  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e958  test    rax, rax
0x18001e95b  jnz     short loc_18001E962
0x18001e95d  lea     ecx, [rax+5]
0x18001e960  int     29h; Win8: RtlFailFast(ecx)
0x18001e962  lea     rbx, [rax+27h]
0x18001e966  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18001e96a  mov     [rbx-8], rax
0x18001e96e  jmp     short loc_18001E978
0x18001e970  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e975  mov     rbx, rax
0x18001e978  mov     rcx, r12
0x18001e97b  sub     rcx, rsi
0x18001e97e  mov     rax, 2AAAAAAAAAAAAAABh
0x18001e988  imul    rcx
0x18001e98b  mov     r13, rdx
0x18001e98e  sar     r13, 2
0x18001e992  mov     rcx, r13
0x18001e995  shr     rcx, 3Fh
0x18001e999  add     r13, rcx
0x18001e99c  lea     rax, ds:0[r13*2]
0x18001e9a4  add     rax, r13
0x18001e9a7  lea     rsi, [rbx+rax*8]
0x18001e9ab  lea     rax, [rsi+18h]
0x18001e9af  mov     [rbp+var_28], r15
0x18001e9b3  mov     [rbp+var_20], rbx
0x18001e9b7  mov     [rbp+var_18], rdi
0x18001e9bb  mov     [rbp+var_10], rax
0x18001e9bf  mov     [rbp+var_8], rax
0x18001e9c3  xor     eax, eax
0x18001e9c5  mov     [rsi], ax
0x18001e9c8  mov     rdx, r14; pvargSrc
0x18001e9cb  mov     rcx, rsi; pvargDest
0x18001e9ce  call    cs:__imp_VariantCopy
0x18001e9d4  test    eax, eax
0x18001e9d6  js      loc_18001EB26
0x18001e9dc  mov     [rbp+var_10], rsi
0x18001e9e0  mov     rax, [r15+8]
0x18001e9e4  mov     [rbp+arg_0], rax
0x18001e9e8  mov     rsi, [r15]
0x18001e9eb  mov     [rbp+var_40], rbx
0x18001e9ef  mov     r14, rbx
0x18001e9f2  mov     [rbp+var_38], rbx
0x18001e9f6  mov     [rbp+var_30], r15
0x18001e9fa  cmp     r12, rax
0x18001e9fd  jnz     short loc_18001EA46
0x18001e9ff  cmp     rsi, rax
0x18001ea02  jz      short loc_18001EA32
0x18001ea04  mov     r12, rax
0x18001ea07  xor     eax, eax
0x18001ea09  mov     [r14], ax
0x18001ea0d  mov     rdx, rsi; pvargSrc
0x18001ea10  mov     rcx, r14; pvargDest
0x18001ea13  call    cs:__imp_VariantCopy
0x18001ea19  test    eax, eax
0x18001ea1b  js      loc_18001EB36
0x18001ea21  add     r14, 18h
0x18001ea25  mov     [rbp+var_38], r14
0x18001ea29  add     rsi, 18h
0x18001ea2d  cmp     rsi, r12
0x18001ea30  jnz     short loc_18001EA07
0x18001ea32  lea     r14, ds:0[r13*2]
0x18001ea3a  add     r14, r13
0x18001ea3d  shl     r14, 3
0x18001ea41  jmp     loc_18001EAC9
0x18001ea46  jmp     short loc_18001EA6E
0x18001ea48  xor     eax, eax
0x18001ea4a  mov     [r14], ax
0x18001ea4e  mov     rdx, rsi; pvargSrc
0x18001ea51  mov     rcx, r14; pvargDest
0x18001ea54  call    cs:__imp_VariantCopy
0x18001ea5a  test    eax, eax
0x18001ea5c  js      loc_18001EB48
0x18001ea62  add     r14, 18h
0x18001ea66  mov     [rbp+var_38], r14
0x18001ea6a  add     rsi, 18h
0x18001ea6e  cmp     rsi, r12
0x18001ea71  jnz     short loc_18001EA48
0x18001ea73  mov     [rbp+var_10], rbx
0x18001ea77  lea     rax, ds:0[r13*2]
0x18001ea7f  add     rax, r13
0x18001ea82  lea     r14, ds:0[rax*8]
0x18001ea8a  lea     rsi, [r14+18h]
0x18001ea8e  add     rsi, rbx
0x18001ea91  mov     r13, [r15+8]
0x18001ea95  mov     [rbp+var_40], rsi
0x18001ea99  mov     [rbp+var_38], rsi
0x18001ea9d  mov     [rbp+var_30], r15
0x18001eaa1  jmp     short loc_18001EAC4
0x18001eaa3  xor     eax, eax
0x18001eaa5  mov     [rsi], ax
0x18001eaa8  mov     rdx, r12; pvargSrc
0x18001eaab  mov     rcx, rsi; pvargDest
0x18001eaae  call    cs:__imp_VariantCopy
0x18001eab4  test    eax, eax
0x18001eab6  js      short loc_18001EB0A
0x18001eab8  add     rsi, 18h
0x18001eabc  mov     [rbp+var_38], rsi
0x18001eac0  add     r12, 18h
0x18001eac4  cmp     r12, r13
0x18001eac7  jnz     short loc_18001EAA3
0x18001eac9  mov     [rbp+var_20], 0
0x18001ead1  mov     r9, rdi
0x18001ead4  mov     r8, [rbp+arg_8]
0x18001ead8  mov     rdx, rbx
0x18001eadb  mov     rcx, r15
0x18001eade  call    ?_Change_array@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAXQEAVCComVariant@ATL@@_K1@Z; std::vector<ATL::CComVariant>::_Change_array(ATL::CComVariant * const,unsigned __int64,unsigned __int64)
0x18001eae3  add     rbx, r14
0x18001eae6  lea     rcx, [rbp+var_28]
0x18001eaea  call    ??1_Reallocation_guard@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CComVariant>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001eaef  mov     rax, rbx
0x18001eaf2  mov     rbx, [rsp+60h+arg_10]
0x18001eafa  add     rsp, 60h
0x18001eafe  pop     r15
0x18001eb00  pop     r14
0x18001eb02  pop     r13
0x18001eb04  pop     r12
0x18001eb06  pop     rdi
0x18001eb07  pop     rsi
0x18001eb08  pop     rbp
0x18001eb09  retn
0x18001eb0a  mov     word ptr [rsi], 0Ah
0x18001eb0f  mov     [rsi+8], eax
0x18001eb12  mov     ecx, eax; int
0x18001eb14  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001eb1a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x18001eb20  call    ?_Xlength@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@CAXXZ; std::vector<ATL::CComVariant>::_Xlength(void)
0x18001eb26  mov     word ptr [rsi], 0Ah
0x18001eb2b  mov     [rsi+8], eax
0x18001eb2e  mov     ecx, eax; int
0x18001eb30  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001eb36  mov     word ptr [r14], 0Ah
0x18001eb3c  mov     [r14+8], eax
0x18001eb40  mov     ecx, eax; int
0x18001eb42  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001eb48  mov     word ptr [r14], 0Ah
0x18001eb4e  mov     [r14+8], eax
0x18001eb52  mov     ecx, eax; int
0x18001eb54  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
