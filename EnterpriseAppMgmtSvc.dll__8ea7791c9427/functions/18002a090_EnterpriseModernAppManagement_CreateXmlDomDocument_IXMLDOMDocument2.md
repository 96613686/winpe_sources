# EnterpriseModernAppManagement::CreateXmlDomDocument(IXMLDOMDocument2 * *)

- ea: `0x18002a090`
- end: `0x18002a323`
- name: `?CreateXmlDomDocument@EnterpriseModernAppManagement@@YAJPEAPEAUIXMLDOMDocument2@@@Z`
- size: `659`
- prototype: `__int64 __fastcall(EnterpriseModernAppManagement *__hidden this, struct IXMLDOMDocument2 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ace0`
- `0x18002d838`

## callees

- `0x18000715c`
- `0x18001c5b8`
- `0x18002a090`
- `0x1800315d4`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a0e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a0e7`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a174`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a211`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a28c`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a174`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a211`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a28c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a1aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a247`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a2be`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a1aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a247`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a2be`
- `OLEAUT32!__imp_VariantClear` at `0x18002a1b4`
- `OLEAUT32!__imp_VariantClear` at `0x18002a251`
- `OLEAUT32!__imp_VariantClear` at `0x18002a2c8`
- `OLEAUT32!__imp_VariantClear` at `0x18002a1b4`
- `OLEAUT32!__imp_VariantClear` at `0x18002a251`
- `OLEAUT32!__imp_VariantClear` at `0x18002a2c8`

## string_xrefs

- `0x18002a269`: `MaxXMLSize`

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
  VARIANTARG pvarg; // [rsp+38h] [rbp-39h] BYREF
  __int128 v31; // [rsp+58h] [rbp-19h] BYREF
  IRecordInfo *pRecInfo; // [rsp+68h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]
  LPVOID ppv; // [rsp+D8h] [rbp+67h] BYREF

  if ( !this )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, a2);
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
      (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
      (const char *)(unsigned int)v3);
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
  v31 = *(_OWORD *)&pvarg.vt;
  v11 = *(__int64 (__fastcall **)(LPVOID, BSTR, __int128 *))(v7 + 640);
  pRecInfo = pvarg.pRecInfo;
  v3 = v11(v6, v10, &v31);
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
    v31 = v16;
    v20 = *(__int64 (__fastcall **)(LPVOID, BSTR, __int128 *))(v15 + 640);
    pRecInfo = v14;
    v3 = v20(v13, v19, &v31);
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
      v31 = v24;
      v28 = *(__int64 (__fastcall **)(LPVOID, BSTR, __int128 *))(v23 + 640);
      pRecInfo = v22;
      v3 = v28(v21, v27, &v31);
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
    (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
    (const char *)(unsigned int)v3);
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
0x18002a090  mov     rax, rsp
0x18002a093  push    rbp
0x18002a094  push    rbx
0x18002a095  push    rsi
0x18002a096  push    rdi
0x18002a097  push    r14
0x18002a099  push    r15
0x18002a09b  lea     rbp, [rax-5Fh]
0x18002a09f  sub     rsp, 98h
0x18002a0a6  movaps  xmmword ptr [rax-48h], xmm6
0x18002a0aa  mov     rdi, rcx
0x18002a0ad  movaps  xmmword ptr [rax-58h], xmm7
0x18002a0b1  test    rcx, rcx
0x18002a0b4  jnz     short loc_18002A0BB
0x18002a0b6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002a0bb  xor     edx, edx; pUnkOuter
0x18002a0bd  mov     qword ptr [rdi], 0
0x18002a0c4  lea     rax, [rbp+57h+ppv]
0x18002a0c8  mov     [rbp+57h+ppv], 0
0x18002a0d0  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18002a0d7  mov     [rsp+20h], rax; int
0x18002a0dc  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18002a0e3  lea     r8d, [rdx+1]; dwClsContext
0x18002a0e7  call    cs:__imp_CoCreateInstance
0x18002a0ed  mov     ebx, eax
0x18002a0ef  test    eax, eax
0x18002a0f1  jns     short loc_18002A129
0x18002a0f3  mov     edx, 99h; void *
0x18002a0f8  mov     rcx, [rbp+5Fh]; this
0x18002a0fc  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002a103  mov     r9d, ebx; char *
0x18002a106  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002a10b  mov     rcx, [rbp+57h+ppv]
0x18002a10f  test    rcx, rcx
0x18002a112  jz      loc_18002A2E3
0x18002a118  mov     rdx, [rcx]
0x18002a11b  mov     rax, [rdx+10h]
0x18002a11f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a124  jmp     loc_18002A2E3
0x18002a129  mov     rcx, [rbp+57h+ppv]
0x18002a12d  xor     edx, edx
0x18002a12f  mov     rax, [rcx]
0x18002a132  mov     rax, [rax+230h]
0x18002a139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a13e  mov     ebx, eax
0x18002a140  test    eax, eax
0x18002a142  jns     short loc_18002A14B
0x18002a144  mov     edx, 9Ch
0x18002a149  jmp     short loc_18002A0F8
0x18002a14b  mov     rbx, [rbp+57h+ppv]
0x18002a14f  lea     rcx, ?c_ProhibitDTD@EnterpriseModernAppManagement@@3QBGB; "ProhibitDTD"
0x18002a156  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x18002a15b  or      eax, 0FFFFFFFFh
0x18002a15e  mov     r15d, 0Bh
0x18002a164  mov     r14, [rbx]
0x18002a167  mov     word ptr [rbp+57h+pvarg], r15w
0x18002a16c  mov     word ptr [rbp+57h+pvarg+8], ax
0x18002a170  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x18002a174  call    cs:__imp_SysAllocString
0x18002a17a  mov     rsi, rax
0x18002a17d  test    rax, rax
0x18002a180  jz      loc_18002A30D
0x18002a186  mov     rdx, rax
0x18002a189  movaps  [rbp+57h+var_70], xmm6
0x18002a18d  mov     rax, [r14+280h]
0x18002a194  lea     r8, [rbp+57h+var_70]
0x18002a198  mov     rcx, rbx
0x18002a19b  movsd   [rbp+57h+var_60], xmm7
0x18002a1a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1a5  mov     rcx, rsi; bstrString
0x18002a1a8  mov     ebx, eax
0x18002a1aa  call    cs:__imp_SysFreeString
0x18002a1b0  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002a1b4  call    cs:__imp_VariantClear
0x18002a1ba  test    ebx, ebx
0x18002a1bc  jns     short loc_18002A1EF
0x18002a1be  mov     edx, 9Dh; void *
0x18002a1c3  mov     rcx, [rbp+5Fh]; this
0x18002a1c7  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002a1ce  mov     r9d, ebx; char *
0x18002a1d1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002a1d6  mov     rcx, [rbp+57h+ppv]
0x18002a1da  test    rcx, rcx
0x18002a1dd  jz      loc_18002A2E3
0x18002a1e3  mov     rax, [rcx]
0x18002a1e6  mov     rax, [rax+10h]
0x18002a1ea  jmp     loc_18002A11F
0x18002a1ef  mov     rbx, [rbp+57h+ppv]
0x18002a1f3  lea     rcx, ?c_AllowXsltScript@EnterpriseModernAppManagement@@3QBGB; "AllowXsltScript"
0x18002a1fa  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x18002a1ff  xor     eax, eax
0x18002a201  mov     r14, [rbx]
0x18002a204  mov     word ptr [rbp+57h+pvarg], r15w
0x18002a209  mov     word ptr [rbp+57h+pvarg+8], ax
0x18002a20d  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x18002a211  call    cs:__imp_SysAllocString
0x18002a217  mov     rsi, rax
0x18002a21a  test    rax, rax
0x18002a21d  jz      loc_18002A318
0x18002a223  mov     rdx, rax
0x18002a226  movaps  [rbp+57h+var_70], xmm6
0x18002a22a  mov     rax, [r14+280h]
0x18002a231  lea     r8, [rbp+57h+var_70]
0x18002a235  mov     rcx, rbx
0x18002a238  movsd   [rbp+57h+var_60], xmm7
0x18002a23d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a242  mov     rcx, rsi; bstrString
0x18002a245  mov     ebx, eax
0x18002a247  call    cs:__imp_SysFreeString
0x18002a24d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002a251  call    cs:__imp_VariantClear
0x18002a257  test    ebx, ebx
0x18002a259  jns     short loc_18002A265
0x18002a25b  mov     edx, 9Eh
0x18002a260  jmp     loc_18002A1C3
0x18002a265  mov     rbx, [rbp+57h+ppv]
0x18002a269  lea     rcx, ?c_MaxXMLSize@EnterpriseModernAppManagement@@3QBGB; "MaxXMLSize"
0x18002a270  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x18002a275  mov     eax, 3
0x18002a27a  mov     r14, [rbx]
0x18002a27d  mov     word ptr [rbp+57h+pvarg], ax
0x18002a281  mov     dword ptr [rbp+57h+pvarg+8], 0C800h
0x18002a288  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x18002a28c  call    cs:__imp_SysAllocString
0x18002a292  mov     rsi, rax
0x18002a295  test    rax, rax
0x18002a298  jz      short loc_18002A302
0x18002a29a  mov     rdx, rax
0x18002a29d  movaps  [rbp+57h+var_70], xmm6
0x18002a2a1  mov     rax, [r14+280h]
0x18002a2a8  lea     r8, [rbp+57h+var_70]
0x18002a2ac  mov     rcx, rbx
0x18002a2af  movsd   [rbp+57h+var_60], xmm7
0x18002a2b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2b9  mov     rcx, rsi; bstrString
0x18002a2bc  mov     ebx, eax
0x18002a2be  call    cs:__imp_SysFreeString
0x18002a2c4  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002a2c8  call    cs:__imp_VariantClear
0x18002a2ce  test    ebx, ebx
0x18002a2d0  jns     short loc_18002A2DC
0x18002a2d2  mov     edx, 9Fh
0x18002a2d7  jmp     loc_18002A1C3
0x18002a2dc  mov     rax, [rbp+57h+ppv]
0x18002a2e0  mov     [rdi], rax
0x18002a2e3  movaps  xmm6, [rsp+0C0h+var_48+8]
0x18002a2eb  mov     eax, ebx
0x18002a2ed  movaps  xmm7, [rsp+0C0h+var_58+8]
0x18002a2f2  add     rsp, 98h
0x18002a2f9  pop     r15
0x18002a2fb  pop     r14
0x18002a2fd  pop     rdi
0x18002a2fe  pop     rsi
0x18002a2ff  pop     rbx
0x18002a300  pop     rbp
0x18002a301  retn
0x18002a302  mov     ecx, 8007000Eh; int
0x18002a307  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002a30d  mov     ecx, 8007000Eh; int
0x18002a312  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002a318  mov     ecx, 8007000Eh; int
0x18002a31d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
