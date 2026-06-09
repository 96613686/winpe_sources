# XcCreateXmlDoc(ushort const *,IXMLDOMSchemaCollection *,IXMLDOMDocument2 * *)

- ea: `0x18007b6b4`
- end: `0x18007b848`
- name: `?XcCreateXmlDoc@@YAKPEBGPEAUIXMLDOMSchemaCollection@@PEAPEAUIXMLDOMDocument2@@@Z`
- size: `404`
- prototype: `unsigned int __fastcall(OLECHAR *psz, struct IXMLDOMSchemaCollection *, struct IXMLDOMDocument2 **)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012cc4`
- `0x180017068`
- `0x18007b9b0`

## callees

- `0x18007b4b8`
- `0x18007b4dc`
- `0x18007b52c`
- `0x18007b6b4`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007b717`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007b717`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b81f`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b81f`
- `OLEAUT32!__imp_VariantInit` at `0x18007b6ea`
- `OLEAUT32!__imp_VariantInit` at `0x18007b6f4`
- `OLEAUT32!__imp_VariantInit` at `0x18007b6ea`
- `OLEAUT32!__imp_VariantInit` at `0x18007b6f4`
- `OLEAUT32!__imp_VariantClear` at `0x18007b80c`
- `OLEAUT32!__imp_VariantClear` at `0x18007b816`
- `OLEAUT32!__imp_VariantClear` at `0x18007b80c`
- `OLEAUT32!__imp_VariantClear` at `0x18007b816`

## pseudocode

```c
__int64 __fastcall XcCreateXmlDoc(OLECHAR *psz, struct IXMLDOMSchemaCollection *a2, LPVOID *a3)
{
  OLECHAR *v4; // rbx
  HRESULT v6; // eax
  unsigned int v7; // edi
  int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  VARIANTARG pvarg; // [rsp+38h] [rbp-19h] BYREF
  VARIANTARG v13; // [rsp+58h] [rbp+7h] BYREF
  VARIANTARG v14; // [rsp+78h] [rbp+27h] BYREF
  LPVOID ppv; // [rsp+C0h] [rbp+6Fh] BYREF
  OLECHAR *v16; // [rsp+D0h] [rbp+7Fh] BYREF

  ppv = 0;
  v4 = 0;
  v16 = 0;
  VariantInit(&pvarg);
  VariantInit(&v14);
  v6 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, &ppv);
  v7 = v6;
  if ( v6 >= 0 )
    goto LABEL_5;
  if ( (v6 & 0x1FFF0000) == 0x70000 )
    v7 = (unsigned __int16)v6;
  if ( !v7 )
  {
LABEL_5:
    v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
    v7 = v8;
    if ( v8 < 0 )
    {
      if ( (v8 & 0x1FFF0000) == 0x70000 )
        v7 = (unsigned __int16)v8;
      if ( v7 )
        goto LABEL_20;
    }
    else
    {
      v7 = 0;
    }
    if ( !psz )
    {
LABEL_19:
      *a3 = ppv;
      ppv = 0;
      goto LABEL_20;
    }
    AtlAssignNoThrow((struct ATL::CComBSTR *)&v16, L"SelectionNamespaces");
    AtlAssignNoThrow((struct ATL::CComVariant *)&pvarg, psz);
    v4 = v16;
    v7 = 8;
    if ( v16 && pvarg.vt == 8 && pvarg.llVal )
    {
      v9 = *(_QWORD *)ppv;
      v13 = pvarg;
      v10 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(v9 + 640))(ppv, v16, &v13);
      v7 = v10;
      if ( v10 >= 0 )
      {
        v7 = 0;
        goto LABEL_19;
      }
      if ( (v10 & 0x1FFF0000) == 0x70000 )
        v7 = (unsigned __int16)v10;
      if ( !v7 )
        goto LABEL_19;
    }
  }
LABEL_20:
  VariantClear(&v14);
  VariantClear(&pvarg);
  SysFreeString(v4);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&ppv);
  return v7;
}

```

## disassembly

```asm
0x18007b6b4  mov     rax, rsp
0x18007b6b7  mov     [rax+8], rbx
0x18007b6bb  mov     [rax+18h], rsi
0x18007b6bf  mov     [rax+10h], rdx
0x18007b6c3  push    rbp
0x18007b6c4  push    rdi
0x18007b6c5  push    r14
0x18007b6c7  lea     rbp, [rax-5Fh]
0x18007b6cb  sub     rsp, 90h
0x18007b6d2  mov     rsi, rcx
0x18007b6d5  mov     [rbp+57h+arg_8], 0
0x18007b6dd  xor     ebx, ebx
0x18007b6df  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18007b6e3  mov     [rbp+57h+arg_18], rbx
0x18007b6e7  mov     r14, r8
0x18007b6ea  call    cs:__imp_VariantInit
0x18007b6f0  lea     rcx, [rbp+57h+var_30]; pvarg
0x18007b6f4  call    cs:__imp_VariantInit
0x18007b6fa  lea     rax, [rbp+57h+arg_8]
0x18007b6fe  xor     edx, edx; pUnkOuter
0x18007b700  lea     r9, IID_IXMLDOMDocument2; riid
0x18007b707  mov     [rsp+0A0h+ppv], rax; ppv
0x18007b70c  lea     r8d, [rbx+1]; dwClsContext
0x18007b710  lea     rcx, CLSID_DOMDocument60; rclsid
0x18007b717  call    cs:__imp_CoCreateInstance
0x18007b71d  mov     edi, eax
0x18007b71f  test    eax, eax
0x18007b721  jns     short loc_18007B73A
0x18007b723  and     eax, 1FFF0000h
0x18007b728  cmp     eax, 70000h
0x18007b72d  jnz     short loc_18007B732
0x18007b72f  movzx   edi, di
0x18007b732  test    edi, edi
0x18007b734  jnz     loc_18007B808
0x18007b73a  mov     rcx, [rbp+57h+arg_8]
0x18007b73e  xor     edx, edx
0x18007b740  mov     rax, [rcx]
0x18007b743  mov     rax, [rax+1F8h]
0x18007b74a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b74f  mov     edi, eax
0x18007b751  test    eax, eax
0x18007b753  js      short loc_18007B759
0x18007b755  xor     edi, edi
0x18007b757  jmp     short loc_18007B770
0x18007b759  and     eax, 1FFF0000h
0x18007b75e  cmp     eax, 70000h
0x18007b763  jnz     short loc_18007B768
0x18007b765  movzx   edi, di
0x18007b768  test    edi, edi
0x18007b76a  jnz     loc_18007B808
0x18007b770  test    rsi, rsi
0x18007b773  jz      loc_18007B7F9
0x18007b779  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x18007b780  lea     rcx, [rbp+57h+arg_18]; struct ATL::CComBSTR *
0x18007b784  call    ?AtlAssignNoThrow@@YAXAEAVCComBSTR@ATL@@PEBG@Z; AtlAssignNoThrow(ATL::CComBSTR &,ushort const *)
0x18007b789  mov     rdx, rsi; psz
0x18007b78c  lea     rcx, [rbp+57h+pvarg]; Destination
0x18007b790  call    ?AtlAssignNoThrow@@YAXAEAVCComVariant@ATL@@PEBG@Z; AtlAssignNoThrow(ATL::CComVariant &,ushort const *)
0x18007b795  mov     rbx, [rbp+57h+arg_18]
0x18007b799  mov     edi, 8
0x18007b79e  test    rbx, rbx
0x18007b7a1  jz      short loc_18007B808
0x18007b7a3  cmp     word ptr [rbp+57h+pvarg], di
0x18007b7a7  jnz     short loc_18007B808
0x18007b7a9  cmp     qword ptr [rbp+57h+pvarg+8], 0
0x18007b7ae  jz      short loc_18007B808
0x18007b7b0  mov     rcx, [rbp+57h+arg_8]
0x18007b7b4  lea     r8, [rbp+57h+var_50]
0x18007b7b8  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18007b7bc  mov     rdx, rbx
0x18007b7bf  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18007b7c4  mov     rax, [rcx]
0x18007b7c7  movaps  [rbp+57h+var_50], xmm0
0x18007b7cb  movsd   [rbp+57h+var_40], xmm1
0x18007b7d0  mov     rax, [rax+280h]
0x18007b7d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b7dc  mov     edi, eax
0x18007b7de  test    eax, eax
0x18007b7e0  js      short loc_18007B7E6
0x18007b7e2  xor     edi, edi
0x18007b7e4  jmp     short loc_18007B7F9
0x18007b7e6  and     eax, 1FFF0000h
0x18007b7eb  cmp     eax, 70000h
0x18007b7f0  jnz     short loc_18007B7F5
0x18007b7f2  movzx   edi, di
0x18007b7f5  test    edi, edi
0x18007b7f7  jnz     short loc_18007B808
0x18007b7f9  mov     rcx, [rbp+57h+arg_8]
0x18007b7fd  mov     [r14], rcx
0x18007b800  mov     [rbp+57h+arg_8], 0
0x18007b808  lea     rcx, [rbp+57h+var_30]; pvarg
0x18007b80c  call    cs:__imp_VariantClear
0x18007b812  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18007b816  call    cs:__imp_VariantClear
0x18007b81c  mov     rcx, rbx; bstrString
0x18007b81f  call    cs:__imp_SysFreeString
0x18007b825  lea     rcx, [rbp+57h+arg_8]
0x18007b829  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18007b82e  lea     r11, [rsp+0A0h+var_10]
0x18007b836  mov     eax, edi
0x18007b838  mov     rbx, [r11+20h]
0x18007b83c  mov     rsi, [r11+30h]
0x18007b840  mov     rsp, r11
0x18007b843  pop     r14
0x18007b845  pop     rdi
0x18007b846  pop     rbp
0x18007b847  retn
```
