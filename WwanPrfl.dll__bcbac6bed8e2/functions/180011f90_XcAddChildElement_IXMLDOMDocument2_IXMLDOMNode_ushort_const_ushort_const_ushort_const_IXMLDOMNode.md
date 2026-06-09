# XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)

- ea: `0x180011f90`
- end: `0x180012258`
- name: `?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z`
- size: `712`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, OLECHAR *psz, OLECHAR *, OLECHAR *psza, struct IXMLDOMNode **)`
- caller_count: `18`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800092fc`
- `0x180009574`
- `0x1800097a4`
- `0x180009c84`
- `0x180009f74`
- `0x18000a0f0`
- `0x18000a298`
- `0x18000b060`
- `0x18000ec80`
- `0x18000f05c`
- `0x18000f73c`
- `0x18000f854`
- `0x18000fc08`
- `0x1800100ac`
- `0x1800103ac`
- `0x180012260`
- `0x180012310`
- `0x1800123d4`

## callees

- `0x1800030fc`
- `0x180011f90`
- `0x1800124bc`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180011fe1`
- `OLEAUT32!__imp_SysAllocString` at `0x180012007`
- `OLEAUT32!__imp_SysAllocString` at `0x18001202e`
- `OLEAUT32!__imp_SysAllocString` at `0x180011fe1`
- `OLEAUT32!__imp_SysAllocString` at `0x180012007`
- `OLEAUT32!__imp_SysAllocString` at `0x18001202e`
- `OLEAUT32!__imp_SysFreeString` at `0x180011fd6`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ff1`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ffc`
- `OLEAUT32!__imp_SysFreeString` at `0x180012017`
- `OLEAUT32!__imp_SysFreeString` at `0x180012022`
- `OLEAUT32!__imp_SysFreeString` at `0x18001203e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001209d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800120a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800120af`
- `OLEAUT32!__imp_SysFreeString` at `0x180011fd6`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ff1`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ffc`
- `OLEAUT32!__imp_SysFreeString` at `0x180012017`
- `OLEAUT32!__imp_SysFreeString` at `0x180012022`
- `OLEAUT32!__imp_SysFreeString` at `0x18001203e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001209d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800120a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800120af`
- `OLEAUT32!__imp_VariantInit` at `0x180011fb5`
- `OLEAUT32!__imp_VariantInit` at `0x180011fb5`
- `OLEAUT32!__imp_VariantClear` at `0x180012094`
- `OLEAUT32!__imp_VariantClear` at `0x18001212f`
- `OLEAUT32!__imp_VariantClear` at `0x180012094`
- `OLEAUT32!__imp_VariantClear` at `0x18001212f`

## pseudocode

```c
__int64 __fastcall XcAddChildElement(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        OLECHAR *psz,
        OLECHAR *a4,
        OLECHAR *psza,
        struct IXMLDOMNode **a6)
{
  OLECHAR *v10; // rsi
  BSTR v11; // rbx
  OLECHAR *v12; // rdi
  BSTR v13; // rbx
  OLECHAR *v14; // rbx
  BSTR v15; // r14
  unsigned int v16; // r14d
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  struct IXMLDOMNode *v22; // rax
  struct IXMLDOMNode *v23; // [rsp+30h] [rbp-50h] BYREF
  __int64 v24; // [rsp+38h] [rbp-48h] BYREF
  __int64 v25; // [rsp+40h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG v27; // [rsp+60h] [rbp-20h] BYREF

  VariantInit(&pvarg);
  v25 = 0;
  v23 = 0;
  v24 = 0;
  SysFreeString(0);
  v10 = 0;
  v11 = SysAllocString(psz);
  if ( v11 )
  {
    SysFreeString(0);
    v10 = v11;
  }
  SysFreeString(0);
  v12 = 0;
  v13 = SysAllocString(a4);
  if ( v13 )
  {
    SysFreeString(0);
    v12 = v13;
  }
  SysFreeString(0);
  v14 = 0;
  v15 = SysAllocString(psza);
  if ( v15 )
  {
    SysFreeString(0);
    v14 = v15;
  }
  if ( !v10 || !v12 )
    goto LABEL_11;
  if ( v14 )
  {
    v18 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, OLECHAR *, __int64 *))a1->lpVtbl->createTextNode)(
            a1,
            v14,
            &v24);
    v16 = v18;
    if ( v18 < 0 )
    {
      if ( (v18 & 0x1FFF0000) == 0x70000 )
        v16 = (unsigned __int16)v18;
      if ( v16 )
        goto LABEL_12;
    }
  }
  else if ( psza )
  {
LABEL_11:
    v16 = 14;
    goto LABEL_12;
  }
  if ( a2 == (struct IXMLDOMNode *)a1 || (v16 = XcAddWhitespace(a1, a2)) == 0 )
  {
    if ( pvarg.vt != 3 )
    {
      VariantClear(&pvarg);
      pvarg.vt = 3;
    }
    pvarg.lVal = 1;
    v27 = pvarg;
    v19 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *, OLECHAR *, OLECHAR *, __int64 *))a1->lpVtbl->createNode)(
            a1,
            &v27,
            v10,
            v12,
            &v25);
    v16 = v19;
    if ( v19 >= 0 )
      goto LABEL_27;
    if ( (v19 & 0x1FFF0000) == 0x70000 )
      v16 = (unsigned __int16)v19;
    if ( !v16 )
    {
LABEL_27:
      v20 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, struct IXMLDOMNode **))a2->lpVtbl->appendChild)(
              a2,
              v25,
              &v23);
      v16 = v20;
      if ( v20 < 0 )
      {
        if ( (v20 & 0x1FFF0000) == 0x70000 )
          v16 = (unsigned __int16)v20;
        if ( v16 )
          goto LABEL_12;
      }
      else
      {
        v16 = 0;
      }
      if ( !v14 )
        goto LABEL_38;
      v21 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, _QWORD))v23->lpVtbl->appendChild)(v23, v24, 0);
      v16 = v21;
      if ( v21 >= 0 )
      {
        v16 = 0;
LABEL_38:
        if ( a2 == (struct IXMLDOMNode *)a1 || (v16 = XcAddWhitespace(a1, a2)) == 0 )
        {
          if ( a6 )
          {
            v22 = v23;
            v23 = 0;
            *a6 = v22;
          }
        }
        goto LABEL_12;
      }
      if ( (v21 & 0x1FFF0000) == 0x70000 )
        v16 = (unsigned __int16)v21;
      if ( !v16 )
        goto LABEL_38;
    }
  }
LABEL_12:
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v23);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v25);
  VariantClear(&pvarg);
  SysFreeString(v14);
  SysFreeString(v12);
  SysFreeString(v10);
  return v16;
}

```

## disassembly

```asm
0x180011f90  push    rbp
0x180011f92  push    rbx
0x180011f93  push    rsi
0x180011f94  push    rdi
0x180011f95  push    r12
0x180011f97  push    r14
0x180011f99  push    r15
0x180011f9b  mov     rbp, rsp
0x180011f9e  sub     rsp, 80h
0x180011fa5  mov     r14, r9
0x180011fa8  mov     rbx, r8
0x180011fab  mov     r12, rdx
0x180011fae  mov     r15, rcx
0x180011fb1  lea     rcx, [rbp+pvarg]; pvarg
0x180011fb5  call    cs:__imp_VariantInit
0x180011fbb  nop
0x180011fbc  mov     [rbp+var_40], 0
0x180011fc4  mov     [rbp+var_50], 0
0x180011fcc  mov     [rbp+var_48], 0
0x180011fd4  xor     ecx, ecx; bstrString
0x180011fd6  call    cs:__imp_SysFreeString
0x180011fdc  xor     esi, esi
0x180011fde  mov     rcx, rbx; psz
0x180011fe1  call    cs:__imp_SysAllocString
0x180011fe7  mov     rbx, rax
0x180011fea  test    rax, rax
0x180011fed  jz      short loc_180011FFA
0x180011fef  xor     ecx, ecx; bstrString
0x180011ff1  call    cs:__imp_SysFreeString
0x180011ff7  mov     rsi, rbx
0x180011ffa  xor     ecx, ecx; bstrString
0x180011ffc  call    cs:__imp_SysFreeString
0x180012002  xor     edi, edi
0x180012004  mov     rcx, r14; psz
0x180012007  call    cs:__imp_SysAllocString
0x18001200d  mov     rbx, rax
0x180012010  test    rax, rax
0x180012013  jz      short loc_180012020
0x180012015  xor     ecx, ecx; bstrString
0x180012017  call    cs:__imp_SysFreeString
0x18001201d  mov     rdi, rbx
0x180012020  xor     ecx, ecx; bstrString
0x180012022  call    cs:__imp_SysFreeString
0x180012028  xor     ebx, ebx
0x18001202a  mov     rcx, [rbp+psz]; psz
0x18001202e  call    cs:__imp_SysAllocString
0x180012034  mov     r14, rax
0x180012037  test    rax, rax
0x18001203a  jz      short loc_180012047
0x18001203c  xor     ecx, ecx; bstrString
0x18001203e  call    cs:__imp_SysFreeString
0x180012044  mov     rbx, r14
0x180012047  test    rsi, rsi
0x18001204a  jz      short loc_180012060
0x18001204c  test    rdi, rdi
0x18001204f  jz      short loc_180012060
0x180012051  test    rbx, rbx
0x180012054  jnz     short loc_1800120CA
0x180012056  cmp     [rbp+psz], rbx
0x18001205a  jz      loc_180012103
0x180012060  mov     r14d, 0Eh
0x180012066  mov     rcx, [rbp+var_48]
0x18001206a  test    rcx, rcx
0x18001206d  jz      short loc_18001207C
0x18001206f  mov     rax, [rcx]
0x180012072  mov     rax, [rax+10h]
0x180012076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001207b  nop
0x18001207c  lea     rcx, [rbp+var_50]
0x180012080  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180012085  nop
0x180012086  lea     rcx, [rbp+var_40]
0x18001208a  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001208f  nop
0x180012090  lea     rcx, [rbp+pvarg]; pvarg
0x180012094  call    cs:__imp_VariantClear
0x18001209a  mov     rcx, rbx; bstrString
0x18001209d  call    cs:__imp_SysFreeString
0x1800120a3  mov     rcx, rdi; bstrString
0x1800120a6  call    cs:__imp_SysFreeString
0x1800120ac  mov     rcx, rsi; bstrString
0x1800120af  call    cs:__imp_SysFreeString
0x1800120b5  mov     eax, r14d
0x1800120b8  add     rsp, 80h
0x1800120bf  pop     r15
0x1800120c1  pop     r14
0x1800120c3  pop     r12
0x1800120c5  pop     rdi
0x1800120c6  pop     rsi
0x1800120c7  pop     rbx
0x1800120c8  pop     rbp
0x1800120c9  retn
0x1800120ca  mov     rax, [r15]
0x1800120cd  lea     r8, [rbp+var_48]
0x1800120d1  mov     rdx, rbx
0x1800120d4  mov     rcx, r15
0x1800120d7  mov     rax, [rax+188h]
0x1800120de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120e3  mov     r14d, eax
0x1800120e6  test    eax, eax
0x1800120e8  jns     short loc_180012103
0x1800120ea  and     eax, 1FFF0000h
0x1800120ef  cmp     eax, 70000h
0x1800120f4  jnz     short loc_1800120FA
0x1800120f6  movzx   r14d, r14w
0x1800120fa  test    r14d, r14d
0x1800120fd  jnz     loc_180012066
0x180012103  cmp     r12, r15
0x180012106  jz      short loc_18001211E
0x180012108  mov     rdx, r12; struct IXMLDOMNode *
0x18001210b  mov     rcx, r15; struct IXMLDOMDocument2 *
0x18001210e  call    ?XcAddWhitespace@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z; XcAddWhitespace(IXMLDOMDocument2 *,IXMLDOMNode *)
0x180012113  mov     r14d, eax
0x180012116  test    eax, eax
0x180012118  jnz     loc_180012066
0x18001211e  mov     r14d, 3
0x180012124  cmp     word ptr [rbp+pvarg], r14w
0x180012129  jz      short loc_18001213A
0x18001212b  lea     rcx, [rbp+pvarg]; pvarg
0x18001212f  call    cs:__imp_VariantClear
0x180012135  mov     word ptr [rbp+pvarg], r14w
0x18001213a  mov     dword ptr [rbp+pvarg+8], 1
0x180012141  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180012145  movaps  [rbp+var_20], xmm0
0x180012149  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18001214e  movsd   [rbp+var_10], xmm1
0x180012153  mov     rax, [r15]
0x180012156  lea     rcx, [rbp+var_40]
0x18001215a  mov     [rsp+80h+var_60], rcx
0x18001215f  mov     r9, rdi
0x180012162  mov     r8, rsi
0x180012165  lea     rdx, [rbp+var_20]
0x180012169  mov     rcx, r15
0x18001216c  mov     rax, [rax+1C0h]
0x180012173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012178  mov     r14d, eax
0x18001217b  test    eax, eax
0x18001217d  jns     short loc_180012198
0x18001217f  and     eax, 1FFF0000h
0x180012184  cmp     eax, 70000h
0x180012189  jnz     short loc_18001218F
0x18001218b  movzx   r14d, r14w
0x18001218f  test    r14d, r14d
0x180012192  jnz     loc_180012066
0x180012198  mov     rax, [r12]
0x18001219c  lea     r8, [rbp+var_50]
0x1800121a0  mov     rdx, [rbp+var_40]
0x1800121a4  mov     rcx, r12
0x1800121a7  mov     rax, [rax+0A8h]
0x1800121ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121b3  mov     r14d, eax
0x1800121b6  test    eax, eax
0x1800121b8  js      short loc_1800121BF
0x1800121ba  xor     r14d, r14d
0x1800121bd  jmp     short loc_1800121D8
0x1800121bf  and     eax, 1FFF0000h
0x1800121c4  cmp     eax, 70000h
0x1800121c9  jnz     short loc_1800121CF
0x1800121cb  movzx   r14d, r14w
0x1800121cf  test    r14d, r14d
0x1800121d2  jnz     loc_180012066
0x1800121d8  test    rbx, rbx
0x1800121db  jz      short loc_18001221C
0x1800121dd  mov     rcx, [rbp+var_50]
0x1800121e1  mov     rax, [rcx]
0x1800121e4  xor     r8d, r8d
0x1800121e7  mov     rdx, [rbp+var_48]
0x1800121eb  mov     rax, [rax+0A8h]
0x1800121f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121f7  mov     r14d, eax
0x1800121fa  test    eax, eax
0x1800121fc  js      short loc_180012203
0x1800121fe  xor     r14d, r14d
0x180012201  jmp     short loc_18001221C
0x180012203  and     eax, 1FFF0000h
0x180012208  cmp     eax, 70000h
0x18001220d  jnz     short loc_180012213
0x18001220f  movzx   r14d, r14w
0x180012213  test    r14d, r14d
0x180012216  jnz     loc_180012066
0x18001221c  cmp     r12, r15
0x18001221f  jz      short loc_180012237
0x180012221  mov     rdx, r12; struct IXMLDOMNode *
0x180012224  mov     rcx, r15; struct IXMLDOMDocument2 *
0x180012227  call    ?XcAddWhitespace@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z; XcAddWhitespace(IXMLDOMDocument2 *,IXMLDOMNode *)
0x18001222c  mov     r14d, eax
0x18001222f  test    eax, eax
0x180012231  jnz     loc_180012066
0x180012237  mov     rcx, [rbp+arg_28]
0x18001223b  test    rcx, rcx
0x18001223e  jz      loc_180012066
0x180012244  mov     rax, [rbp+var_50]
0x180012248  mov     [rbp+var_50], 0
0x180012250  mov     [rcx], rax
0x180012253  jmp     loc_180012066
```
