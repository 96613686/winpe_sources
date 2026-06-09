# EnterpriseModernAppManagement::CreateXmlDomDocument(IXMLDOMDocument2 * *)

- ea: `0x18002c2bc`
- end: `0x18002c58c`
- name: `?CreateXmlDomDocument@EnterpriseModernAppManagement@@YAJPEAPEAUIXMLDOMDocument2@@@Z`
- size: `720`
- prototype: `__int64 __fastcall(EnterpriseModernAppManagement *__hidden this, struct IXMLDOMDocument2 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d1cc`
- `0x180030010`

## callees

- `0x180007404`
- `0x18001d65c`
- `0x18002c2bc`
- `0x18003442c`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c313`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c313`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c3a6`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c455`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c4e2`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c3a6`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c455`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c4e2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c3e2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c491`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c51a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c3e2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c491`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c51a`
- `OLEAUT32!__imp_VariantClear` at `0x18002c3f2`
- `OLEAUT32!__imp_VariantClear` at `0x18002c4a1`
- `OLEAUT32!__imp_VariantClear` at `0x18002c52a`
- `OLEAUT32!__imp_VariantClear` at `0x18002c3f2`
- `OLEAUT32!__imp_VariantClear` at `0x18002c4a1`
- `OLEAUT32!__imp_VariantClear` at `0x18002c52a`

## string_xrefs

- `0x18002c4bf`: `MaxXMLSize`

## pseudocode

```c
__int64 __fastcall EnterpriseModernAppManagement::CreateXmlDomDocument(
        EnterpriseModernAppManagement *this,
        struct IXMLDOMDocument2 **a2)
{
  HRESULT v3; // ebx
  __int64 v4; // rdx
  void (*v5)(void); // rax
  LPVOID v6; // rbx
  __int64 v7; // r14
  BSTR v8; // rax
  OLECHAR *v9; // rsi
  BSTR v10; // rdx
  __int64 (__fastcall *v11)(LPVOID, BSTR, __int128 *); // rax
  __int64 v12; // rdx
  LPVOID v13; // rbx
  IRecordInfo *v14; // xmm7_8
  __int64 v15; // r14
  __int128 v16; // xmm6
  BSTR v17; // rax
  OLECHAR *v18; // rsi
  BSTR v19; // rdx
  __int64 (__fastcall *v20)(LPVOID, BSTR, __int128 *); // rax
  LPVOID v21; // rbx
  IRecordInfo *v22; // xmm7_8
  __int64 v23; // r14
  __int128 v24; // xmm6
  BSTR v25; // rax
  OLECHAR *v26; // rsi
  BSTR v27; // rdx
  __int64 (__fastcall *v28)(LPVOID, BSTR, __int128 *); // rax
  int v30; // [rsp+28h] [rbp-49h]
  VARIANTARG pvarg; // [rsp+38h] [rbp-39h] BYREF
  __int128 v32; // [rsp+58h] [rbp-19h] BYREF
  IRecordInfo *pRecInfo; // [rsp+68h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]
  LPVOID ppv; // [rsp+D8h] [rbp+67h] BYREF

  if ( !this )
    MicrosoftTelemetryAssertTriggeredNoArgs(0);
  *(_QWORD *)this = 0;
  ppv = 0;
  v3 = CoCreateInstance(
         &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
         0,
         1u,
         &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
         &ppv);
  if ( v3 < 0 )
  {
    v4 = 153;
    goto LABEL_5;
  }
  v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 560LL))(ppv, 0);
  if ( v3 < 0 )
  {
    v4 = 156;
LABEL_5:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)(unsigned int)v3,
      v30);
    if ( ppv )
    {
      v5 = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
LABEL_7:
      v5();
      return (unsigned int)v3;
    }
    return (unsigned int)v3;
  }
  v6 = ppv;
  v7 = *(_QWORD *)ppv;
  pvarg.vt = 11;
  pvarg.iVal = -1;
  v8 = SysAllocString(L"ProhibitDTD");
  v9 = v8;
  if ( !v8 )
    ATL::AtlThrowImpl(-2147024882);
  v10 = v8;
  v32 = *(_OWORD *)&pvarg.vt;
  v11 = *(__int64 (__fastcall **)(LPVOID, BSTR, __int128 *))(v7 + 640);
  pRecInfo = pvarg.pRecInfo;
  v3 = v11(v6, v10, &v32);
  SysFreeString(v9);
  VariantClear(&pvarg);
  if ( v3 >= 0 )
  {
    v13 = ppv;
    v14 = pvarg.pRecInfo;
    v15 = *(_QWORD *)ppv;
    pvarg.vt = 11;
    pvarg.iVal = 0;
    v16 = *(_OWORD *)&pvarg.vt;
    v17 = SysAllocString(L"AllowXsltScript");
    v18 = v17;
    if ( !v17 )
      ATL::AtlThrowImpl(-2147024882);
    v19 = v17;
    v32 = v16;
    v20 = *(__int64 (__fastcall **)(LPVOID, BSTR, __int128 *))(v15 + 640);
    pRecInfo = v14;
    v3 = v20(v13, v19, &v32);
    SysFreeString(v18);
    VariantClear(&pvarg);
    if ( v3 >= 0 )
    {
      v21 = ppv;
      v22 = pvarg.pRecInfo;
      v23 = *(_QWORD *)ppv;
      pvarg.vt = 3;
      pvarg.lVal = 51200;
      v24 = *(_OWORD *)&pvarg.vt;
      v25 = SysAllocString(L"MaxXMLSize");
      v26 = v25;
      if ( !v25 )
        ATL::AtlThrowImpl(-2147024882);
      v27 = v25;
      v32 = v24;
      v28 = *(__int64 (__fastcall **)(LPVOID, BSTR, __int128 *))(v23 + 640);
      pRecInfo = v22;
      v3 = v28(v21, v27, &v32);
      SysFreeString(v26);
      VariantClear(&pvarg);
      if ( v3 >= 0 )
      {
        *(_QWORD *)this = ppv;
        return (unsigned int)v3;
      }
      v12 = 159;
    }
    else
    {
      v12 = 158;
    }
  }
  else
  {
    v12 = 157;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
    (const char *)(unsigned int)v3,
    v30);
  if ( ppv )
  {
    v5 = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
    goto LABEL_7;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002c2bc  mov     rax, rsp
0x18002c2bf  push    rbp
0x18002c2c0  push    rbx
0x18002c2c1  push    rsi
0x18002c2c2  push    rdi
0x18002c2c3  push    r14
0x18002c2c5  push    r15
0x18002c2c7  lea     rbp, [rax-5Fh]
0x18002c2cb  sub     rsp, 98h
0x18002c2d2  movaps  xmmword ptr [rax-48h], xmm6
0x18002c2d6  mov     rdi, rcx
0x18002c2d9  movaps  xmmword ptr [rax-58h], xmm7
0x18002c2dd  test    rcx, rcx
0x18002c2e0  jnz     short loc_18002C2E7
0x18002c2e2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002c2e7  xor     edx, edx; pUnkOuter
0x18002c2e9  mov     qword ptr [rdi], 0
0x18002c2f0  lea     rax, [rbp+57h+ppv]
0x18002c2f4  mov     [rbp+57h+ppv], 0
0x18002c2fc  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18002c303  mov     [rsp+20h], rax; int
0x18002c308  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18002c30f  lea     r8d, [rdx+1]; dwClsContext
0x18002c313  call    cs:__imp_CoCreateInstance
0x18002c31a  nop     dword ptr [rax+rax+00h]
0x18002c31f  mov     ebx, eax
0x18002c321  test    eax, eax
0x18002c323  jns     short loc_18002C35B
0x18002c325  mov     edx, 99h; void *
0x18002c32a  mov     rcx, [rbp+5Fh]; this
0x18002c32e  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002c335  mov     r9d, ebx; char *
0x18002c338  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c33d  mov     rcx, [rbp+57h+ppv]
0x18002c341  test    rcx, rcx
0x18002c344  jz      loc_18002C54B
0x18002c34a  mov     rdx, [rcx]
0x18002c34d  mov     rax, [rdx+10h]
0x18002c351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c356  jmp     loc_18002C54B
0x18002c35b  mov     rcx, [rbp+57h+ppv]
0x18002c35f  xor     edx, edx
0x18002c361  mov     rax, [rcx]
0x18002c364  mov     rax, [rax+230h]
0x18002c36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c370  mov     ebx, eax
0x18002c372  test    eax, eax
0x18002c374  jns     short loc_18002C37D
0x18002c376  mov     edx, 9Ch
0x18002c37b  jmp     short loc_18002C32A
0x18002c37d  mov     rbx, [rbp+57h+ppv]
0x18002c381  lea     rcx, ?c_ProhibitDTD@EnterpriseModernAppManagement@@3QBGB; "ProhibitDTD"
0x18002c388  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x18002c38d  or      eax, 0FFFFFFFFh
0x18002c390  mov     r15d, 0Bh
0x18002c396  mov     r14, [rbx]
0x18002c399  mov     word ptr [rbp+57h+pvarg], r15w
0x18002c39e  mov     word ptr [rbp+57h+pvarg+8], ax
0x18002c3a2  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x18002c3a6  call    cs:__imp_SysAllocString
0x18002c3ad  nop     dword ptr [rax+rax+00h]
0x18002c3b2  mov     rsi, rax
0x18002c3b5  test    rax, rax
0x18002c3b8  jz      loc_18002C576
0x18002c3be  mov     rdx, rax
0x18002c3c1  movaps  [rbp+57h+var_70], xmm6
0x18002c3c5  mov     rax, [r14+280h]
0x18002c3cc  lea     r8, [rbp+57h+var_70]
0x18002c3d0  mov     rcx, rbx
0x18002c3d3  movsd   [rbp+57h+var_60], xmm7
0x18002c3d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c3dd  mov     rcx, rsi; bstrString
0x18002c3e0  mov     ebx, eax
0x18002c3e2  call    cs:__imp_SysFreeString
0x18002c3e9  nop     dword ptr [rax+rax+00h]
0x18002c3ee  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002c3f2  call    cs:__imp_VariantClear
0x18002c3f9  nop     dword ptr [rax+rax+00h]
0x18002c3fe  test    ebx, ebx
0x18002c400  jns     short loc_18002C433
0x18002c402  mov     edx, 9Dh; void *
0x18002c407  mov     rcx, [rbp+5Fh]; this
0x18002c40b  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002c412  mov     r9d, ebx; char *
0x18002c415  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c41a  mov     rcx, [rbp+57h+ppv]
0x18002c41e  test    rcx, rcx
0x18002c421  jz      loc_18002C54B
0x18002c427  mov     rax, [rcx]
0x18002c42a  mov     rax, [rax+10h]
0x18002c42e  jmp     loc_18002C351
0x18002c433  mov     rbx, [rbp+57h+ppv]
0x18002c437  lea     rcx, ?c_AllowXsltScript@EnterpriseModernAppManagement@@3QBGB; "AllowXsltScript"
0x18002c43e  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x18002c443  xor     eax, eax
0x18002c445  mov     r14, [rbx]
0x18002c448  mov     word ptr [rbp+57h+pvarg], r15w
0x18002c44d  mov     word ptr [rbp+57h+pvarg+8], ax
0x18002c451  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x18002c455  call    cs:__imp_SysAllocString
0x18002c45c  nop     dword ptr [rax+rax+00h]
0x18002c461  mov     rsi, rax
0x18002c464  test    rax, rax
0x18002c467  jz      loc_18002C581
0x18002c46d  mov     rdx, rax
0x18002c470  movaps  [rbp+57h+var_70], xmm6
0x18002c474  mov     rax, [r14+280h]
0x18002c47b  lea     r8, [rbp+57h+var_70]
0x18002c47f  mov     rcx, rbx
0x18002c482  movsd   [rbp+57h+var_60], xmm7
0x18002c487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c48c  mov     rcx, rsi; bstrString
0x18002c48f  mov     ebx, eax
0x18002c491  call    cs:__imp_SysFreeString
0x18002c498  nop     dword ptr [rax+rax+00h]
0x18002c49d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002c4a1  call    cs:__imp_VariantClear
0x18002c4a8  nop     dword ptr [rax+rax+00h]
0x18002c4ad  test    ebx, ebx
0x18002c4af  jns     short loc_18002C4BB
0x18002c4b1  mov     edx, 9Eh
0x18002c4b6  jmp     loc_18002C407
0x18002c4bb  mov     rbx, [rbp+57h+ppv]
0x18002c4bf  lea     rcx, ?c_MaxXMLSize@EnterpriseModernAppManagement@@3QBGB; "MaxXMLSize"
0x18002c4c6  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x18002c4cb  mov     eax, 3
0x18002c4d0  mov     r14, [rbx]
0x18002c4d3  mov     word ptr [rbp+57h+pvarg], ax
0x18002c4d7  mov     dword ptr [rbp+57h+pvarg+8], 0C800h
0x18002c4de  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x18002c4e2  call    cs:__imp_SysAllocString
0x18002c4e9  nop     dword ptr [rax+rax+00h]
0x18002c4ee  mov     rsi, rax
0x18002c4f1  test    rax, rax
0x18002c4f4  jz      short loc_18002C56B
0x18002c4f6  mov     rdx, rax
0x18002c4f9  movaps  [rbp+57h+var_70], xmm6
0x18002c4fd  mov     rax, [r14+280h]
0x18002c504  lea     r8, [rbp+57h+var_70]
0x18002c508  mov     rcx, rbx
0x18002c50b  movsd   [rbp+57h+var_60], xmm7
0x18002c510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c515  mov     rcx, rsi; bstrString
0x18002c518  mov     ebx, eax
0x18002c51a  call    cs:__imp_SysFreeString
0x18002c521  nop     dword ptr [rax+rax+00h]
0x18002c526  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002c52a  call    cs:__imp_VariantClear
0x18002c531  nop     dword ptr [rax+rax+00h]
0x18002c536  test    ebx, ebx
0x18002c538  jns     short loc_18002C544
0x18002c53a  mov     edx, 9Fh
0x18002c53f  jmp     loc_18002C407
0x18002c544  mov     rax, [rbp+57h+ppv]
0x18002c548  mov     [rdi], rax
0x18002c54b  movaps  xmm6, [rsp+0C0h+var_48+8]
0x18002c553  mov     eax, ebx
0x18002c555  movaps  xmm7, [rsp+0C0h+var_58+8]
0x18002c55a  add     rsp, 98h
0x18002c561  pop     r15
0x18002c563  pop     r14
0x18002c565  pop     rdi
0x18002c566  pop     rsi
0x18002c567  pop     rbx
0x18002c568  pop     rbp
0x18002c569  retn
0x18002c56b  mov     ecx, 8007000Eh; int
0x18002c570  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002c576  mov     ecx, 8007000Eh; int
0x18002c57b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002c581  mov     ecx, 8007000Eh; int
0x18002c586  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
