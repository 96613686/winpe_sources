# _saveProfileXmlIndented

- ea: `0x18000d2c4`
- end: `0x18000d4b4`
- name: `_saveProfileXmlIndented`
- size: `496`
- prototype: `__int64 __fastcall(__int64, OLECHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000dd90`

## callees

- `0x18000d2c4`
- `0x180011eb8`
- `0x1800125a4`
- `0x180012808`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000d306`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d35d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3b7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3ed`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d486`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d306`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d35d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3b7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3ed`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d486`
- `OLEAUT32!__imp_VariantInit` at `0x18000d412`
- `OLEAUT32!__imp_VariantInit` at `0x18000d412`
- `OLEAUT32!__imp_VariantClear` at `0x18000d47b`
- `OLEAUT32!__imp_VariantClear` at `0x18000d47b`

## pseudocode

```c
__int64 __fastcall saveProfileXmlIndented(__int64 a1, OLECHAR *a2)
{
  unsigned int v4; // ebx
  int v6; // eax
  struct IXMLDOMDocument2 *v7; // rbx
  int v8; // eax
  unsigned int LoadError; // edi
  int v10; // eax
  struct IXMLDOMDocument2 *v11; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-38h] BYREF
  VARIANTARG v13; // [rsp+40h] [rbp-20h] BYREF
  __int16 v14; // [rsp+90h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp+38h] BYREF

  v11 = 0;
  bstrString = 0;
  v14 = 0;
  v4 = XcCreateXmlDoc(0, 0, &v11);
  if ( v4 )
  {
    SysFreeString(bstrString);
    if ( v11 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v11->lpVtbl->Release)(v11);
    return v4;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a1 + 272LL))(a1, &bstrString);
  v4 = v6;
  if ( v6 < 0 )
  {
    if ( (v6 & 0x1FFF0000) == 0x70000 )
      v4 = (unsigned __int16)v6;
    if ( v4 )
    {
      SysFreeString(bstrString);
      if ( v11 )
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v11->lpVtbl->Release)(v11);
      return v4;
    }
  }
  v7 = v11;
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR, __int16 *))v11->lpVtbl->loadXML)(v11, bstrString, &v14);
  LoadError = v8;
  if ( v8 >= 0 )
    goto LABEL_19;
  if ( (v8 & 0x1FFF0000) == 0x70000 )
    LoadError = (unsigned __int16)v8;
  if ( LoadError )
  {
    SysFreeString(bstrString);
    if ( v7 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v7->lpVtbl->Release)(v7);
  }
  else
  {
LABEL_19:
    if ( v14 == -1 )
    {
      VariantInit(&pvarg);
      AtlAssignNoThrow((struct ATL::CComVariant *)&pvarg, a2);
      LoadError = 8;
      if ( pvarg.vt == 8 && pvarg.llVal )
      {
        v13 = pvarg;
        v10 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *))v7->lpVtbl->save)(v7, &v13);
        LoadError = v10;
        if ( v10 < 0 )
        {
          if ( (v10 & 0x1FFF0000) == 0x70000 )
            LoadError = (unsigned __int16)v10;
        }
        else
        {
          LoadError = 0;
        }
      }
      VariantClear(&pvarg);
      SysFreeString(bstrString);
      if ( v7 )
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v7->lpVtbl->Release)(v7);
    }
    else
    {
      LoadError = XcGetLoadError(v7);
      SysFreeString(bstrString);
      if ( v7 )
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v7->lpVtbl->Release)(v7);
    }
  }
  return LoadError;
}

```

## disassembly

```asm
0x18000d2c4  mov     [rsp-18h+arg_0], rbx
0x18000d2c9  push    rbp
0x18000d2ca  push    rsi
0x18000d2cb  push    rdi
0x18000d2cc  mov     rbp, rsp
0x18000d2cf  sub     rsp, 60h
0x18000d2d3  mov     rsi, rdx
0x18000d2d6  mov     rdi, rcx
0x18000d2d9  mov     [rbp+var_40], 0
0x18000d2e1  mov     [rbp+bstrString], 0
0x18000d2e9  xor     eax, eax
0x18000d2eb  mov     [rbp+arg_10], ax
0x18000d2ef  lea     r8, [rbp+var_40]; struct IXMLDOMDocument2 **
0x18000d2f3  xor     edx, edx; struct IXMLDOMSchemaCollection *
0x18000d2f5  xor     ecx, ecx; psz
0x18000d2f7  call    ?XcCreateXmlDoc@@YAKPEBGPEAUIXMLDOMSchemaCollection@@PEAPEAUIXMLDOMDocument2@@@Z; XcCreateXmlDoc(ushort const *,IXMLDOMSchemaCollection *,IXMLDOMDocument2 * *)
0x18000d2fc  mov     ebx, eax
0x18000d2fe  test    eax, eax
0x18000d300  jz      short loc_18000D32A
0x18000d302  mov     rcx, [rbp+bstrString]; bstrString
0x18000d306  call    cs:__imp_SysFreeString
0x18000d30c  nop
0x18000d30d  mov     rcx, [rbp+var_40]
0x18000d311  test    rcx, rcx
0x18000d314  jz      short loc_18000D323
0x18000d316  mov     rdx, [rcx]
0x18000d319  mov     rax, [rdx+10h]
0x18000d31d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d322  nop
0x18000d323  mov     eax, ebx
0x18000d325  jmp     loc_18000D4A4
0x18000d32a  mov     rax, [rdi]
0x18000d32d  lea     rdx, [rbp+bstrString]
0x18000d331  mov     rcx, rdi
0x18000d334  mov     rax, [rax+110h]
0x18000d33b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d340  mov     ebx, eax
0x18000d342  test    eax, eax
0x18000d344  jns     short loc_18000D37C
0x18000d346  and     eax, 1FFF0000h
0x18000d34b  cmp     eax, 70000h
0x18000d350  jnz     short loc_18000D355
0x18000d352  movzx   ebx, bx
0x18000d355  test    ebx, ebx
0x18000d357  jz      short loc_18000D37C
0x18000d359  mov     rcx, [rbp+bstrString]; bstrString
0x18000d35d  call    cs:__imp_SysFreeString
0x18000d363  nop
0x18000d364  mov     rcx, [rbp+var_40]
0x18000d368  test    rcx, rcx
0x18000d36b  jz      short loc_18000D37A
0x18000d36d  mov     rdx, [rcx]
0x18000d370  mov     rax, [rdx+10h]
0x18000d374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d379  nop
0x18000d37a  jmp     short loc_18000D323
0x18000d37c  mov     rbx, [rbp+var_40]
0x18000d380  mov     rax, [rbx]
0x18000d383  lea     r8, [rbp+arg_10]
0x18000d387  mov     rdx, [rbp+bstrString]
0x18000d38b  mov     rcx, rbx
0x18000d38e  mov     rax, [rax+208h]
0x18000d395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d39a  mov     edi, eax
0x18000d39c  test    eax, eax
0x18000d39e  jns     short loc_18000D3D8
0x18000d3a0  and     eax, 1FFF0000h
0x18000d3a5  cmp     eax, 70000h
0x18000d3aa  jnz     short loc_18000D3AF
0x18000d3ac  movzx   edi, di
0x18000d3af  test    edi, edi
0x18000d3b1  jz      short loc_18000D3D8
0x18000d3b3  mov     rcx, [rbp+bstrString]; bstrString
0x18000d3b7  call    cs:__imp_SysFreeString
0x18000d3bd  nop
0x18000d3be  test    rbx, rbx
0x18000d3c1  jz      short loc_18000D3D3
0x18000d3c3  mov     rcx, [rbx]
0x18000d3c6  mov     rax, [rcx+10h]
0x18000d3ca  mov     rcx, rbx
0x18000d3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3d2  nop
0x18000d3d3  jmp     loc_18000D4A2
0x18000d3d8  cmp     [rbp+arg_10], 0FFFFh
0x18000d3dd  jz      short loc_18000D40E
0x18000d3df  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18000d3e2  call    ?XcGetLoadError@@YAKPEAUIXMLDOMDocument2@@@Z; XcGetLoadError(IXMLDOMDocument2 *)
0x18000d3e7  mov     edi, eax
0x18000d3e9  mov     rcx, [rbp+bstrString]; bstrString
0x18000d3ed  call    cs:__imp_SysFreeString
0x18000d3f3  nop
0x18000d3f4  test    rbx, rbx
0x18000d3f7  jz      short loc_18000D409
0x18000d3f9  mov     rcx, [rbx]
0x18000d3fc  mov     rax, [rcx+10h]
0x18000d400  mov     rcx, rbx
0x18000d403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d408  nop
0x18000d409  jmp     loc_18000D4A2
0x18000d40e  lea     rcx, [rbp+pvarg]; pvarg
0x18000d412  call    cs:__imp_VariantInit
0x18000d418  mov     rdx, rsi; psz
0x18000d41b  lea     rcx, [rbp+pvarg]; Destination
0x18000d41f  call    ?AtlAssignNoThrow@@YAXAEAVCComVariant@ATL@@PEBG@Z; AtlAssignNoThrow(ATL::CComVariant &,ushort const *)
0x18000d424  mov     edi, 8
0x18000d429  cmp     word ptr [rbp+pvarg], di
0x18000d42d  jnz     short loc_18000D477
0x18000d42f  cmp     qword ptr [rbp+pvarg+8], 0
0x18000d434  jz      short loc_18000D477
0x18000d436  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000d43a  movaps  [rbp+var_20], xmm0
0x18000d43e  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000d443  movsd   [rbp+var_10], xmm1
0x18000d448  mov     rax, [rbx]
0x18000d44b  lea     rdx, [rbp+var_20]
0x18000d44f  mov     rcx, rbx
0x18000d452  mov     rax, [rax+210h]
0x18000d459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d45e  mov     edi, eax
0x18000d460  test    eax, eax
0x18000d462  js      short loc_18000D468
0x18000d464  xor     edi, edi
0x18000d466  jmp     short loc_18000D477
0x18000d468  and     eax, 1FFF0000h
0x18000d46d  cmp     eax, 70000h
0x18000d472  jnz     short loc_18000D477
0x18000d474  movzx   edi, di
0x18000d477  lea     rcx, [rbp+pvarg]; pvarg
0x18000d47b  call    cs:__imp_VariantClear
0x18000d481  nop
0x18000d482  mov     rcx, [rbp+bstrString]; bstrString
0x18000d486  call    cs:__imp_SysFreeString
0x18000d48c  nop
0x18000d48d  test    rbx, rbx
0x18000d490  jz      short loc_18000D4A2
0x18000d492  mov     rcx, [rbx]
0x18000d495  mov     rax, [rcx+10h]
0x18000d499  mov     rcx, rbx
0x18000d49c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4a1  nop
0x18000d4a2  mov     eax, edi
0x18000d4a4  mov     rbx, [rsp+60h+arg_0]
0x18000d4ac  add     rsp, 60h
0x18000d4b0  pop     rdi
0x18000d4b1  pop     rsi
0x18000d4b2  pop     rbp
0x18000d4b3  retn
```
