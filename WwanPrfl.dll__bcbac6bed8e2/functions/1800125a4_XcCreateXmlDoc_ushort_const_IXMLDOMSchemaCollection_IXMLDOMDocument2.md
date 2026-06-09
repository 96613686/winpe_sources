# XcCreateXmlDoc(ushort const *,IXMLDOMSchemaCollection *,IXMLDOMDocument2 * *)

- ea: `0x1800125a4`
- end: `0x1800127ca`
- name: `?XcCreateXmlDoc@@YAKPEBGPEAUIXMLDOMSchemaCollection@@PEAPEAUIXMLDOMDocument2@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(OLECHAR *psz, struct IXMLDOMSchemaCollection *, struct IXMLDOMDocument2 **)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b5a0`
- `0x18000d2c4`
- `0x18000dd90`
- `0x18000dea0`
- `0x18000e3f0`
- `0x180012fe0`

## callees

- `0x1800030fc`
- `0x180011eb8`
- `0x1800125a4`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012604`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012604`
- `OLEAUT32!__imp_SysAllocString` at `0x180012677`
- `OLEAUT32!__imp_SysAllocString` at `0x180012677`
- `OLEAUT32!__imp_SysFreeString` at `0x18001266a`
- `OLEAUT32!__imp_SysFreeString` at `0x180012687`
- `OLEAUT32!__imp_SysFreeString` at `0x18001279b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001266a`
- `OLEAUT32!__imp_SysFreeString` at `0x180012687`
- `OLEAUT32!__imp_SysFreeString` at `0x18001279b`
- `OLEAUT32!__imp_VariantInit` at `0x1800125d7`
- `OLEAUT32!__imp_VariantInit` at `0x1800125e1`
- `OLEAUT32!__imp_VariantInit` at `0x1800125d7`
- `OLEAUT32!__imp_VariantInit` at `0x1800125e1`
- `OLEAUT32!__imp_VariantClear` at `0x18001270f`
- `OLEAUT32!__imp_VariantClear` at `0x180012788`
- `OLEAUT32!__imp_VariantClear` at `0x180012792`
- `OLEAUT32!__imp_VariantClear` at `0x18001270f`
- `OLEAUT32!__imp_VariantClear` at `0x180012788`
- `OLEAUT32!__imp_VariantClear` at `0x180012792`

## pseudocode

```c
__int64 __fastcall XcCreateXmlDoc(OLECHAR *psz, struct IXMLDOMSchemaCollection *a2, struct IXMLDOMDocument2 **a3)
{
  OLECHAR *v6; // rbx
  HRESULT v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  BSTR v10; // rdi
  int v11; // eax
  int v12; // eax
  struct IXMLDOMDocument2 *v13; // rcx
  VARIANTARG v15; // [rsp+30h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG v17; // [rsp+60h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+C8h] [rbp+48h] BYREF

  ppv = 0;
  v6 = 0;
  VariantInit(&pvarg);
  VariantInit(&v15);
  v7 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, &ppv);
  v8 = v7;
  if ( v7 >= 0 )
    goto LABEL_5;
  if ( (v7 & 0x1FFF0000) == 0x70000 )
    v8 = (unsigned __int16)v7;
  if ( !v8 )
  {
LABEL_5:
    v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
    v8 = v9;
    if ( v9 < 0 )
    {
      if ( (v9 & 0x1FFF0000) == 0x70000 )
        v8 = (unsigned __int16)v9;
      if ( v8 )
        goto LABEL_28;
    }
    else
    {
      v8 = 0;
    }
    if ( psz )
    {
      SysFreeString(0);
      v10 = SysAllocString(L"SelectionNamespaces");
      if ( v10 )
      {
        SysFreeString(0);
        v6 = v10;
      }
      AtlAssignNoThrow((struct ATL::CComVariant *)&pvarg, psz);
      v8 = 8;
      if ( !v6 || pvarg.vt != 8 || !pvarg.llVal )
        goto LABEL_28;
      v17 = pvarg;
      v11 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(*(_QWORD *)ppv + 640LL))(ppv, v6, &v17);
      v8 = v11;
      if ( v11 < 0 )
      {
        if ( (v11 & 0x1FFF0000) == 0x70000 )
          v8 = (unsigned __int16)v11;
        if ( v8 )
          goto LABEL_28;
      }
      else
      {
        v8 = 0;
      }
    }
    if ( !a2 )
    {
LABEL_27:
      v13 = (struct IXMLDOMDocument2 *)ppv;
      ppv = 0;
      *a3 = v13;
      goto LABEL_28;
    }
    VariantClear(&v15);
    v15.vt = 9;
    v15.llVal = (LONGLONG)a2;
    ((void (__fastcall *)(struct IXMLDOMSchemaCollection *))a2->lpVtbl->AddRef)(a2);
    v17 = v15;
    v12 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *))(*(_QWORD *)ppv + 624LL))(ppv, &v17);
    v8 = v12;
    if ( v12 >= 0 )
    {
      v8 = 0;
      goto LABEL_27;
    }
    if ( (v12 & 0x1FFF0000) == 0x70000 )
      v8 = (unsigned __int16)v12;
    if ( !v8 )
      goto LABEL_27;
  }
LABEL_28:
  VariantClear(&v15);
  VariantClear(&pvarg);
  SysFreeString(v6);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x1800125a4  mov     [rsp-28h+arg_0], rbx
0x1800125a9  mov     [rsp-28h+arg_8], rsi
0x1800125ae  push    rbp
0x1800125af  push    rdi
0x1800125b0  push    r13
0x1800125b2  push    r14
0x1800125b4  push    r15
0x1800125b6  mov     rbp, rsp
0x1800125b9  sub     rsp, 80h
0x1800125c0  mov     r15, r8
0x1800125c3  mov     r14, rdx
0x1800125c6  mov     rsi, rcx
0x1800125c9  mov     [rbp+arg_18], 0
0x1800125d1  xor     ebx, ebx
0x1800125d3  lea     rcx, [rbp+pvarg]; pvarg
0x1800125d7  call    cs:__imp_VariantInit
0x1800125dd  lea     rcx, [rbp+var_50]; pvarg
0x1800125e1  call    cs:__imp_VariantInit
0x1800125e7  lea     rax, [rbp+arg_18]
0x1800125eb  mov     [rsp+80h+ppv], rax; ppv
0x1800125f0  lea     r9, IID_IXMLDOMDocument2; riid
0x1800125f7  xor     edx, edx; pUnkOuter
0x1800125f9  lea     r8d, [rbx+1]; dwClsContext
0x1800125fd  lea     rcx, CLSID_DOMDocument60; rclsid
0x180012604  call    cs:__imp_CoCreateInstance
0x18001260a  mov     edi, eax
0x18001260c  mov     r13d, 1FFF0000h
0x180012612  test    eax, eax
0x180012614  jns     short loc_18001262B
0x180012616  and     eax, r13d
0x180012619  cmp     eax, 70000h
0x18001261e  jnz     short loc_180012623
0x180012620  movzx   edi, di
0x180012623  test    edi, edi
0x180012625  jnz     loc_180012784
0x18001262b  mov     rcx, [rbp+arg_18]
0x18001262f  mov     rax, [rcx]
0x180012632  xor     edx, edx
0x180012634  mov     rax, [rax+1F8h]
0x18001263b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012640  mov     edi, eax
0x180012642  test    eax, eax
0x180012644  js      short loc_18001264A
0x180012646  xor     edi, edi
0x180012648  jmp     short loc_18001265F
0x18001264a  and     eax, r13d
0x18001264d  cmp     eax, 70000h
0x180012652  jnz     short loc_180012657
0x180012654  movzx   edi, di
0x180012657  test    edi, edi
0x180012659  jnz     loc_180012784
0x18001265f  test    rsi, rsi
0x180012662  jz      loc_180012706
0x180012668  xor     ecx, ecx; bstrString
0x18001266a  call    cs:__imp_SysFreeString
0x180012670  lea     rcx, aSelectionnames; "SelectionNamespaces"
0x180012677  call    cs:__imp_SysAllocString
0x18001267d  mov     rdi, rax
0x180012680  test    rax, rax
0x180012683  jz      short loc_180012690
0x180012685  xor     ecx, ecx; bstrString
0x180012687  call    cs:__imp_SysFreeString
0x18001268d  mov     rbx, rdi
0x180012690  mov     rdx, rsi; psz
0x180012693  lea     rcx, [rbp+pvarg]; Destination
0x180012697  call    ?AtlAssignNoThrow@@YAXAEAVCComVariant@ATL@@PEBG@Z; AtlAssignNoThrow(ATL::CComVariant &,ushort const *)
0x18001269c  mov     edi, 8
0x1800126a1  test    rbx, rbx
0x1800126a4  jz      loc_180012784
0x1800126aa  cmp     word ptr [rbp+pvarg], di
0x1800126ae  jnz     loc_180012784
0x1800126b4  cmp     qword ptr [rbp+pvarg+8], 0
0x1800126b9  jz      loc_180012784
0x1800126bf  mov     rcx, [rbp+arg_18]
0x1800126c3  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800126c7  movaps  [rbp+var_20], xmm0
0x1800126cb  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800126d0  movsd   [rbp+var_10], xmm1
0x1800126d5  mov     rax, [rcx]
0x1800126d8  lea     r8, [rbp+var_20]
0x1800126dc  mov     rdx, rbx
0x1800126df  mov     rax, [rax+280h]
0x1800126e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126eb  mov     edi, eax
0x1800126ed  test    eax, eax
0x1800126ef  js      short loc_1800126F5
0x1800126f1  xor     edi, edi
0x1800126f3  jmp     short loc_180012706
0x1800126f5  and     eax, r13d
0x1800126f8  cmp     eax, 70000h
0x1800126fd  jnz     short loc_180012702
0x1800126ff  movzx   edi, di
0x180012702  test    edi, edi
0x180012704  jnz     short loc_180012784
0x180012706  test    r14, r14
0x180012709  jz      short loc_180012775
0x18001270b  lea     rcx, [rbp+var_50]; pvarg
0x18001270f  call    cs:__imp_VariantClear
0x180012715  mov     eax, 9
0x18001271a  mov     word ptr [rbp+var_50], ax
0x18001271e  mov     qword ptr [rbp+var_50+8], r14
0x180012722  mov     rax, [r14]
0x180012725  mov     rcx, r14
0x180012728  mov     rax, [rax+8]
0x18001272c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012731  mov     rcx, [rbp+arg_18]
0x180012735  movups  xmm0, xmmword ptr [rbp+var_50]
0x180012739  movaps  [rbp+var_20], xmm0
0x18001273d  movsd   xmm1, qword ptr [rbp+var_50+10h]
0x180012742  movsd   [rbp+var_10], xmm1
0x180012747  mov     rax, [rcx]
0x18001274a  lea     rdx, [rbp+var_20]
0x18001274e  mov     rax, [rax+270h]
0x180012755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001275a  mov     edi, eax
0x18001275c  test    eax, eax
0x18001275e  js      short loc_180012764
0x180012760  xor     edi, edi
0x180012762  jmp     short loc_180012775
0x180012764  and     eax, r13d
0x180012767  cmp     eax, 70000h
0x18001276c  jnz     short loc_180012771
0x18001276e  movzx   edi, di
0x180012771  test    edi, edi
0x180012773  jnz     short loc_180012784
0x180012775  mov     rcx, [rbp+arg_18]
0x180012779  mov     [rbp+arg_18], 0
0x180012781  mov     [r15], rcx
0x180012784  lea     rcx, [rbp+var_50]; pvarg
0x180012788  call    cs:__imp_VariantClear
0x18001278e  lea     rcx, [rbp+pvarg]; pvarg
0x180012792  call    cs:__imp_VariantClear
0x180012798  mov     rcx, rbx; bstrString
0x18001279b  call    cs:__imp_SysFreeString
0x1800127a1  nop
0x1800127a2  lea     rcx, [rbp+arg_18]
0x1800127a6  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800127ab  nop
0x1800127ac  mov     eax, edi
0x1800127ae  lea     r11, [rsp+80h+var_s0]
0x1800127b6  mov     rbx, [r11+30h]
0x1800127ba  mov     rsi, [r11+38h]
0x1800127be  mov     rsp, r11
0x1800127c1  pop     r15
0x1800127c3  pop     r14
0x1800127c5  pop     r13
0x1800127c7  pop     rdi
0x1800127c8  pop     rbp
0x1800127c9  retn
```
