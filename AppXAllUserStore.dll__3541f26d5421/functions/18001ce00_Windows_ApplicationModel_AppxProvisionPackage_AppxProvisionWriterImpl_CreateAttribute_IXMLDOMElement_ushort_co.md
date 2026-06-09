# Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateAttribute(IXMLDOMElement *,ushort const *,ushort const *)

- ea: `0x18001ce00`
- end: `0x18001cfaf`
- name: `?CreateAttribute@AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@AEAAJPEAUIXMLDOMElement@@PEBG1@Z`
- size: `431`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *this, struct IXMLDOMElement *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ca50`

## callees

- `0x180017f50`
- `0x18001ca24`
- `0x18001ce00`
- `0x180048ae8`
- `0x18004d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001ce1c`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ceab`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ce1c`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ceab`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ce2c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cf9a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ce2c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cf9a`
- `OLEAUT32!__imp_VariantClear` at `0x18001cf88`
- `OLEAUT32!__imp_VariantClear` at `0x18001cf88`

## string_xrefs

- `0x18001ce77`: `onecore\base\appmodel\appxprovisionpackage\src\appxprovisionwriter.cpp`
- `0x18001cf19`: `onecore\base\appmodel\appxprovisionpackage\src\appxprovisionwriter.cpp`
- `0x18001cf67`: `onecore\base\appmodel\appxprovisionpackage\src\appxprovisionwriter.cpp`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateAttribute(
        Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *this,
        struct IXMLDOMElement *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  OLECHAR *v7; // rbx
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, OLECHAR *, __int64 **); // rdi
  int v11; // eax
  unsigned int v12; // edi
  VARTYPE vt; // ax
  __int64 v14; // rax
  int v15; // eax
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  HRESULT (__stdcall *setAttributeNode)(IXMLDOMElement *, IXMLDOMAttribute *, IXMLDOMAttribute **); // rdi
  int v18; // eax
  __int64 *v19; // [rsp+20h] [rbp-58h] BYREF
  __int64 v20; // [rsp+28h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-48h] BYREF
  VARIANTARG v22; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  v7 = SysAllocString(a3);
  if ( v7 )
  {
    v9 = *((_QWORD *)this + 4);
    v19 = 0;
    v10 = *(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 **))(*(_QWORD *)v9 + 424LL);
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v19);
    v11 = v10(v9, v7, &v19);
    v12 = v11;
    if ( v11 >= 0 )
    {
      pvarg.vt = 0;
      Common::AutoVariant::InternalClear((Common::AutoVariant *)&pvarg);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)SysAllocString(a4);
      v12 = -2147024882;
      if ( pvarg.llVal || !a4 )
      {
        vt = pvarg.vt;
      }
      else
      {
        vt = 10;
        pvarg.lVal = -2147024882;
        pvarg.vt = 10;
      }
      if ( vt == 8 )
      {
        v14 = *v19;
        v22 = pvarg;
        v15 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *))(v14 + 360))(v19, &v22);
        v12 = v15;
        if ( v15 >= 0 )
        {
          lpVtbl = a2->lpVtbl;
          v20 = 0;
          setAttributeNode = lpVtbl->setAttributeNode;
          Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v20);
          v18 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *, __int64 *))setAttributeNode)(a2, v19, &v20);
          v12 = v18;
          if ( v18 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x172,
              (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\appxprovisionwriter.cpp",
              (const char *)(unsigned int)v18);
          Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v20);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x16E,
            (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\appxprovisionwriter.cpp",
            (const char *)(unsigned int)v15);
        }
      }
      VariantClear(&pvarg);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x169,
        (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\appxprovisionwriter.cpp",
        (const char *)(unsigned int)v11);
    }
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v19);
    SysFreeString(v7);
    return v12;
  }
  else
  {
    SysFreeString(0);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001ce00  push    rbp
0x18001ce02  push    rbx
0x18001ce03  push    rsi
0x18001ce04  push    rdi
0x18001ce05  push    r14
0x18001ce07  push    r15
0x18001ce09  mov     rbp, rsp
0x18001ce0c  sub     rsp, 78h
0x18001ce10  mov     rsi, rcx
0x18001ce13  mov     r14, r9
0x18001ce16  mov     rcx, r8; psz
0x18001ce19  mov     r15, rdx
0x18001ce1c  call    cs:__imp_SysAllocString
0x18001ce22  mov     rbx, rax
0x18001ce25  test    rax, rax
0x18001ce28  jnz     short loc_18001CE3C
0x18001ce2a  xor     ecx, ecx; bstrString
0x18001ce2c  call    cs:__imp_SysFreeString
0x18001ce32  mov     eax, 8007000Eh
0x18001ce37  jmp     loc_18001CFA2
0x18001ce3c  mov     rsi, [rsi+20h]
0x18001ce40  lea     rcx, [rbp+var_58]
0x18001ce44  mov     [rbp+var_58], 0
0x18001ce4c  mov     rax, [rsi]
0x18001ce4f  mov     rdi, [rax+1A8h]
0x18001ce56  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001ce5b  lea     r8, [rbp+var_58]
0x18001ce5f  mov     rdx, rbx
0x18001ce62  mov     rcx, rsi
0x18001ce65  mov     rax, rdi
0x18001ce68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce6d  mov     edi, eax
0x18001ce6f  test    eax, eax
0x18001ce71  jns     short loc_18001CE90
0x18001ce73  mov     rcx, [rbp+30h]; this
0x18001ce77  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001ce7e  mov     r9d, eax; char *
0x18001ce81  mov     edx, 169h; void *
0x18001ce86  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ce8b  jmp     loc_18001CF8E
0x18001ce90  xor     eax, eax
0x18001ce92  lea     rcx, [rbp+pvarg]; this
0x18001ce96  mov     word ptr [rbp+pvarg], ax
0x18001ce9a  call    ?InternalClear@AutoVariant@Common@@IEAAJXZ; Common::AutoVariant::InternalClear(void)
0x18001ce9f  mov     esi, 8
0x18001cea4  mov     rcx, r14; psz
0x18001cea7  mov     word ptr [rbp+pvarg], si
0x18001ceab  call    cs:__imp_SysAllocString
0x18001ceb1  mov     rcx, rax
0x18001ceb4  mov     dword ptr [rbp+pvarg+8], eax
0x18001ceb7  sar     rcx, 20h
0x18001cebb  mov     edi, 8007000Eh
0x18001cec0  mov     dword ptr [rbp+pvarg+0Ch], ecx
0x18001cec3  test    rax, rax
0x18001cec6  jnz     short loc_18001CED9
0x18001cec8  test    r14, r14
0x18001cecb  jz      short loc_18001CED9
0x18001cecd  lea     eax, [rsi+2]
0x18001ced0  mov     dword ptr [rbp+pvarg+8], edi
0x18001ced3  mov     word ptr [rbp+pvarg], ax
0x18001ced7  jmp     short loc_18001CEDD
0x18001ced9  movzx   eax, word ptr [rbp+pvarg]
0x18001cedd  cmp     ax, si
0x18001cee0  jnz     loc_18001CF84
0x18001cee6  mov     rcx, [rbp+var_58]
0x18001ceea  lea     rdx, [rbp+var_28]
0x18001ceee  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18001cef2  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18001cef7  mov     rax, [rcx]
0x18001cefa  movaps  [rbp+var_28], xmm0
0x18001cefe  movsd   [rbp+var_18], xmm1
0x18001cf03  mov     rax, [rax+168h]
0x18001cf0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf0f  mov     edi, eax
0x18001cf11  test    eax, eax
0x18001cf13  jns     short loc_18001CF2F
0x18001cf15  mov     rcx, [rbp+30h]; this
0x18001cf19  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001cf20  mov     r9d, eax; char *
0x18001cf23  mov     edx, 16Eh; void *
0x18001cf28  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cf2d  jmp     short loc_18001CF84
0x18001cf2f  mov     rax, [r15]
0x18001cf32  lea     rcx, [rbp+var_50]
0x18001cf36  mov     [rbp+var_50], 0
0x18001cf3e  mov     rdi, [rax+180h]
0x18001cf45  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001cf4a  mov     rdx, [rbp+var_58]
0x18001cf4e  lea     r8, [rbp+var_50]
0x18001cf52  mov     rcx, r15
0x18001cf55  mov     rax, rdi
0x18001cf58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf5d  mov     edi, eax
0x18001cf5f  test    eax, eax
0x18001cf61  jns     short loc_18001CF7B
0x18001cf63  mov     rcx, [rbp+30h]; this
0x18001cf67  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001cf6e  mov     r9d, eax; char *
0x18001cf71  mov     edx, 172h; void *
0x18001cf76  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cf7b  lea     rcx, [rbp+var_50]
0x18001cf7f  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001cf84  lea     rcx, [rbp+pvarg]; pvarg
0x18001cf88  call    cs:__imp_VariantClear
0x18001cf8e  lea     rcx, [rbp+var_58]
0x18001cf92  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001cf97  mov     rcx, rbx; bstrString
0x18001cf9a  call    cs:__imp_SysFreeString
0x18001cfa0  mov     eax, edi
0x18001cfa2  add     rsp, 78h
0x18001cfa6  pop     r15
0x18001cfa8  pop     r14
0x18001cfaa  pop     rdi
0x18001cfab  pop     rsi
0x18001cfac  pop     rbx
0x18001cfad  pop     rbp
0x18001cfae  retn
```
