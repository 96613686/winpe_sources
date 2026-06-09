# Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::InitializeXmlDom(IXMLDOMDocument2 * *)

- ea: `0x18001dcdc`
- end: `0x18001de69`
- name: `?InitializeXmlDom@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@CAJPEAPEAUIXMLDOMDocument2@@@Z`
- size: `397`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d92c`
- `0x18001df14`

## callees

- `0x180017f50`
- `0x18001ca24`
- `0x18001dcdc`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001dd19`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001dd19`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ddbb`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ddbb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ddcb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001de4d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ddcb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001de4d`
- `OLEAUT32!__imp_VariantClear` at `0x18001de44`
- `OLEAUT32!__imp_VariantClear` at `0x18001de44`

## string_xrefs

- `0x18001dda3`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`
- `0x18001de1b`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::InitializeXmlDom(LPVOID *a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  unsigned __int64 v4; // r9
  __int64 v5; // rdx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  BSTR v9; // rax
  OLECHAR *v10; // rbx
  BSTR v11; // rdx
  __int64 v12; // rax
  __int64 (__fastcall *v13)(LPVOID, BSTR, __int128 *); // rax
  int v14; // eax
  unsigned int v15; // edi
  VARIANTARG pvarg; // [rsp+30h] [rbp-48h] BYREF
  __int128 v18; // [rsp+50h] [rbp-28h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]
  LPVOID ppv; // [rsp+A8h] [rbp+30h] BYREF

  ppv = 0;
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&ppv);
  v2 = CoCreateInstance(
         &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
         0,
         1u,
         &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
         &ppv);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = (unsigned int)v2;
    v5 = 143;
LABEL_9:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v5,
      (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
      (const char *)v4);
    goto LABEL_16;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  v3 = v6;
  if ( v6 < 0 )
  {
    v4 = (unsigned int)v6;
    v5 = 145;
    goto LABEL_9;
  }
  v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 544LL))(ppv, 0);
  v3 = v7;
  if ( v7 < 0 )
  {
    v4 = (unsigned int)v7;
    v5 = 146;
    goto LABEL_9;
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 576LL))(ppv, 0xFFFFFFFFLL);
  v3 = v8;
  if ( v8 < 0 )
  {
    v4 = (unsigned int)v8;
    v5 = 147;
    goto LABEL_9;
  }
  v9 = SysAllocString(L"NewParser");
  v10 = v9;
  if ( v9 )
  {
    pvarg.vt = 11;
    v11 = v9;
    pvarg.iVal = -1;
    v12 = *(_QWORD *)ppv;
    pRecInfo = pvarg.pRecInfo;
    v13 = *(__int64 (__fastcall **)(LPVOID, BSTR, __int128 *))(v12 + 640);
    v18 = *(_OWORD *)&pvarg.vt;
    v14 = v13(ppv, v11, &v18);
    v15 = v14;
    if ( v14 >= 0 )
    {
      *a1 = ppv;
      ppv = 0;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x98,
        (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
        (const char *)(unsigned int)v14);
    }
    VariantClear(&pvarg);
    SysFreeString(v10);
    v3 = v15;
  }
  else
  {
    SysFreeString(0);
    v3 = -2147024882;
  }
LABEL_16:
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&ppv);
  return v3;
}

```

## disassembly

```asm
0x18001dcdc  push    rbp
0x18001dcde  push    rbx
0x18001dcdf  push    rsi
0x18001dce0  push    rdi
0x18001dce1  mov     rbp, rsp
0x18001dce4  sub     rsp, 78h
0x18001dce8  mov     rsi, rcx
0x18001dceb  mov     [rbp+arg_8], 0
0x18001dcf3  lea     rcx, [rbp+arg_8]
0x18001dcf7  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001dcfc  xor     edx, edx; pUnkOuter
0x18001dcfe  lea     rax, [rbp+arg_8]
0x18001dd02  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18001dd09  mov     [rsp+78h+ppv], rax; int
0x18001dd0e  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18001dd15  lea     r8d, [rdx+1]; dwClsContext
0x18001dd19  call    cs:__imp_CoCreateInstance
0x18001dd1f  mov     ebx, eax
0x18001dd21  test    eax, eax
0x18001dd23  jns     short loc_18001DD2F
0x18001dd25  mov     r9d, eax
0x18001dd28  mov     edx, 8Fh
0x18001dd2d  jmp     short loc_18001DD9F
0x18001dd2f  mov     rcx, [rbp+arg_8]
0x18001dd33  xor     edx, edx
0x18001dd35  mov     rax, [rcx]
0x18001dd38  mov     rax, [rax+1F8h]
0x18001dd3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd44  mov     ebx, eax
0x18001dd46  test    eax, eax
0x18001dd48  jns     short loc_18001DD54
0x18001dd4a  mov     r9d, eax
0x18001dd4d  mov     edx, 91h
0x18001dd52  jmp     short loc_18001DD9F
0x18001dd54  mov     rcx, [rbp+arg_8]
0x18001dd58  xor     edx, edx
0x18001dd5a  mov     rax, [rcx]
0x18001dd5d  mov     rax, [rax+220h]
0x18001dd64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd69  mov     ebx, eax
0x18001dd6b  test    eax, eax
0x18001dd6d  jns     short loc_18001DD79
0x18001dd6f  mov     r9d, eax
0x18001dd72  mov     edx, 92h
0x18001dd77  jmp     short loc_18001DD9F
0x18001dd79  mov     rcx, [rbp+arg_8]
0x18001dd7d  or      edi, 0FFFFFFFFh
0x18001dd80  mov     edx, edi
0x18001dd82  mov     rax, [rcx]
0x18001dd85  mov     rax, [rax+240h]
0x18001dd8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd91  mov     ebx, eax
0x18001dd93  test    eax, eax
0x18001dd95  jns     short loc_18001DDB4
0x18001dd97  mov     r9d, eax; char *
0x18001dd9a  mov     edx, 93h; void *
0x18001dd9f  mov     rcx, [rbp+20h]; this
0x18001dda3  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001ddaa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ddaf  jmp     loc_18001DE55
0x18001ddb4  lea     rcx, aNewparser; "NewParser"
0x18001ddbb  call    cs:__imp_SysAllocString
0x18001ddc1  mov     rbx, rax
0x18001ddc4  test    rax, rax
0x18001ddc7  jnz     short loc_18001DDD8
0x18001ddc9  xor     ecx, ecx; bstrString
0x18001ddcb  call    cs:__imp_SysFreeString
0x18001ddd1  mov     ebx, 8007000Eh
0x18001ddd6  jmp     short loc_18001DE55
0x18001ddd8  mov     rcx, [rbp+arg_8]
0x18001dddc  lea     r8, [rbp+var_28]
0x18001dde0  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18001dde5  mov     eax, 0Bh
0x18001ddea  mov     word ptr [rbp+pvarg], ax
0x18001ddee  mov     rdx, rbx
0x18001ddf1  mov     word ptr [rbp+pvarg+8], di
0x18001ddf5  mov     rax, [rcx]
0x18001ddf8  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18001ddfc  movsd   [rbp+var_18], xmm1
0x18001de01  mov     rax, [rax+280h]
0x18001de08  movaps  [rbp+var_28], xmm0
0x18001de0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de11  mov     edi, eax
0x18001de13  test    eax, eax
0x18001de15  jns     short loc_18001DE31
0x18001de17  mov     rcx, [rbp+20h]; this
0x18001de1b  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001de22  mov     r9d, eax; char *
0x18001de25  mov     edx, 98h; void *
0x18001de2a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001de2f  jmp     short loc_18001DE40
0x18001de31  mov     rax, [rbp+arg_8]
0x18001de35  mov     [rsi], rax
0x18001de38  mov     [rbp+arg_8], 0
0x18001de40  lea     rcx, [rbp+pvarg]; pvarg
0x18001de44  call    cs:__imp_VariantClear
0x18001de4a  mov     rcx, rbx; bstrString
0x18001de4d  call    cs:__imp_SysFreeString
0x18001de53  mov     ebx, edi
0x18001de55  lea     rcx, [rbp+arg_8]
0x18001de59  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001de5e  mov     eax, ebx
0x18001de60  add     rsp, 78h
0x18001de64  pop     rdi
0x18001de65  pop     rsi
0x18001de66  pop     rbx
0x18001de67  pop     rbp
0x18001de68  retn
```
