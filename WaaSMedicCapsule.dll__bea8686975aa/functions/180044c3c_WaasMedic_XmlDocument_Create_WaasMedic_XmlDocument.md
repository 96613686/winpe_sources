# WaasMedic::XmlDocument::Create(WaasMedic::XmlDocument * *)

- ea: `0x180044c3c`
- end: `0x180044edc`
- name: `?Create@XmlDocument@WaasMedic@@SAJPEAPEAV12@@Z`
- size: `672`
- prototype: `__int64 __fastcall(struct WaasMedic::XmlDocument **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180046c94`

## callees

- `0x180003bb0`
- `0x180003c18`
- `0x18002543c`
- `0x180044c3c`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180044c95`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180044c95`
- `OLEAUT32!__imp_SysAllocString` at `0x180044d85`
- `OLEAUT32!__imp_SysAllocString` at `0x180044d99`
- `OLEAUT32!__imp_SysAllocString` at `0x180044d85`
- `OLEAUT32!__imp_SysAllocString` at `0x180044d99`
- `OLEAUT32!__imp_SysFreeString` at `0x180044dbd`
- `OLEAUT32!__imp_SysFreeString` at `0x180044e24`
- `OLEAUT32!__imp_SysFreeString` at `0x180044e5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180044e9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180044dbd`
- `OLEAUT32!__imp_SysFreeString` at `0x180044e24`
- `OLEAUT32!__imp_SysFreeString` at `0x180044e5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180044e9a`

## string_xrefs

- `0x180044ca4`: `Failed to create IXMLDOMDocument3 instance. Err=0x%08x`
- `0x180044d49`: `Failed to set IXMLDOMDocument3::validateOnParse. Err=0x%08x`
- `0x180044cf9`: `Failed to set IXMLDOMDocument3::async. Err=0x%08x`
- `0x180044e0f`: `Failed to set IXMLDOMDocument3 MultipleErrorMessages. Err=0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WaasMedic::XmlDocument::Create(struct WaasMedic::XmlDocument **a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  LPVOID v4; // rcx
  int v6; // eax
  LPVOID v7; // rcx
  int v8; // eax
  LPVOID v9; // rcx
  const OLECHAR *v10; // rax
  OLECHAR *v11; // rbx
  int v12; // eax
  unsigned int v13; // edi
  struct WaasMedic::XmlDocument *v14; // rax
  LPVOID v15; // rcx
  LPVOID v16; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-29h] BYREF
  void *v18; // [rsp+38h] [rbp-21h]
  __int128 v19; // [rsp+40h] [rbp-19h] BYREF
  __int64 v20; // [rsp+50h] [rbp-9h]
  IID riid; // [rsp+60h] [rbp+7h] BYREF
  IID rclsid; // [rsp+70h] [rbp+17h] BYREF

  rclsid = CLSID_DOMDocument60;
  riid = IID_IXMLDOMDocument3;
  ppv = 0;
  v2 = CoCreateInstance(&rclsid, 0, 1u, &riid, &ppv);
  v3 = v2;
  if ( v2 < 0 )
  {
    LogLevelW(2u, L"Failed to create IXMLDOMDocument3 instance. Err=0x%08x", (unsigned int)v2);
    v4 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
    }
    return v3;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  v3 = v6;
  if ( v6 < 0 )
  {
    LogLevelW(2u, L"Failed to set IXMLDOMDocument3::async. Err=0x%08x", (unsigned int)v6);
    v7 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return v3;
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 544LL))(ppv, 0);
  v3 = v8;
  if ( v8 < 0 )
  {
    LogLevelW(2u, L"Failed to set IXMLDOMDocument3::validateOnParse. Err=0x%08x", (unsigned int)v8);
    v9 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v3;
  }
  v10 = SysAllocString(L"MultipleErrorMessages");
  v11 = 0;
  v18 = 0;
  if ( v10 )
  {
    v11 = SysAllocString(v10);
    v18 = v11;
  }
  if ( !v11 )
  {
    LogLevelW(2u, L"Failed to allocate multipleErrorMessages");
    SysFreeString(0);
LABEL_25:
    v16 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return 2147942414LL;
  }
  v19 = 0;
  LOWORD(v19) = 11;
  WORD4(v19) = -1;
  v20 = 0;
  v12 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int128 *))(*(_QWORD *)ppv + 640LL))(ppv, v11, &v19);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v14 = (struct WaasMedic::XmlDocument *)operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
    v18 = v14;
    if ( !v14 )
    {
      LogLevelW(2u, L"Failed to allocate xdoc");
      SysFreeString(v11);
      goto LABEL_25;
    }
    *(_QWORD *)v14 = ppv;
    ppv = 0;
    *a1 = v14;
    SysFreeString(v11);
  }
  else
  {
    LogLevelW(2u, L"Failed to set IXMLDOMDocument3 MultipleErrorMessages. Err=0x%08x", (unsigned int)v12);
    SysFreeString(v11);
  }
  v15 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return v13;
}

```

## disassembly

```asm
0x180044c3c  push    rbp
0x180044c3e  push    rbx
0x180044c3f  push    rsi
0x180044c40  push    rdi
0x180044c41  lea     rbp, [rsp-3Fh]
0x180044c46  sub     rsp, 98h
0x180044c4d  mov     rax, cs:__security_cookie
0x180044c54  xor     rax, rsp
0x180044c57  mov     [rbp+57h+var_30], rax
0x180044c5b  mov     rsi, rcx
0x180044c5e  movups  xmm0, xmmword ptr cs:CLSID_DOMDocument60.Data1
0x180044c65  movdqu  xmmword ptr [rbp+57h+rclsid.Data1], xmm0
0x180044c6a  movups  xmm1, xmmword ptr cs:IID_IXMLDOMDocument3.Data1
0x180044c71  movdqu  xmmword ptr [rbp+57h+riid.Data1], xmm1
0x180044c76  mov     [rbp+57h+var_80], 0
0x180044c7e  lea     rax, [rbp+57h+var_80]
0x180044c82  mov     [rsp+0B0h+ppv], rax; ppv
0x180044c87  lea     r9, [rbp+57h+riid]; riid
0x180044c8b  xor     edx, edx; pUnkOuter
0x180044c8d  lea     r8d, [rdx+1]; dwClsContext
0x180044c91  lea     rcx, [rbp+57h+rclsid]; rclsid
0x180044c95  call    cs:__imp_CoCreateInstance
0x180044c9b  mov     ebx, eax
0x180044c9d  test    eax, eax
0x180044c9f  jns     short loc_180044CDB
0x180044ca1  mov     r8d, eax
0x180044ca4  lea     rdx, aFailedToCreate_18; "Failed to create IXMLDOMDocument3 insta"...
0x180044cab  mov     ecx, 2; unsigned __int8
0x180044cb0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180044cb5  nop
0x180044cb6  mov     rcx, [rbp+57h+var_80]
0x180044cba  test    rcx, rcx
0x180044cbd  jz      short loc_180044CD4
0x180044cbf  mov     [rbp+57h+var_80], 0
0x180044cc7  mov     rax, [rcx]
0x180044cca  mov     rax, [rax+10h]
0x180044cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044cd3  nop
0x180044cd4  mov     eax, ebx
0x180044cd6  jmp     loc_180044EC4
0x180044cdb  mov     rcx, [rbp+57h+var_80]
0x180044cdf  mov     rax, [rcx]
0x180044ce2  xor     edx, edx
0x180044ce4  mov     rax, [rax+1F8h]
0x180044ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044cf0  mov     ebx, eax
0x180044cf2  test    eax, eax
0x180044cf4  jns     short loc_180044D2B
0x180044cf6  mov     r8d, eax
0x180044cf9  lea     rdx, aFailedToSetIxm_0; "Failed to set IXMLDOMDocument3::async. "...
0x180044d00  mov     ecx, 2; unsigned __int8
0x180044d05  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180044d0a  nop
0x180044d0b  mov     rcx, [rbp+57h+var_80]
0x180044d0f  test    rcx, rcx
0x180044d12  jz      short loc_180044D29
0x180044d14  mov     [rbp+57h+var_80], 0
0x180044d1c  mov     rax, [rcx]
0x180044d1f  mov     rax, [rax+10h]
0x180044d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d28  nop
0x180044d29  jmp     short loc_180044CD4
0x180044d2b  mov     rcx, [rbp+57h+var_80]
0x180044d2f  mov     rax, [rcx]
0x180044d32  xor     edx, edx
0x180044d34  mov     rax, [rax+220h]
0x180044d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d40  mov     ebx, eax
0x180044d42  test    eax, eax
0x180044d44  jns     short loc_180044D7E
0x180044d46  mov     r8d, eax
0x180044d49  lea     rdx, aFailedToSetIxm; "Failed to set IXMLDOMDocument3::validat"...
0x180044d50  mov     ecx, 2; unsigned __int8
0x180044d55  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180044d5a  nop
0x180044d5b  mov     rcx, [rbp+57h+var_80]
0x180044d5f  test    rcx, rcx
0x180044d62  jz      short loc_180044D79
0x180044d64  mov     [rbp+57h+var_80], 0
0x180044d6c  mov     rax, [rcx]
0x180044d6f  mov     rax, [rax+10h]
0x180044d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d78  nop
0x180044d79  jmp     loc_180044CD4
0x180044d7e  lea     rcx, aMultipleerrorm; "MultipleErrorMessages"
0x180044d85  call    cs:__imp_SysAllocString
0x180044d8b  xor     ebx, ebx
0x180044d8d  mov     [rbp+57h+var_78], rbx
0x180044d91  test    rax, rax
0x180044d94  jz      short loc_180044DA6
0x180044d96  mov     rcx, rax; psz
0x180044d99  call    cs:__imp_SysAllocString
0x180044d9f  mov     rbx, rax
0x180044da2  mov     [rbp+57h+var_78], rax
0x180044da6  test    rbx, rbx
0x180044da9  jnz     short loc_180044DC9
0x180044dab  lea     rdx, aFailedToAlloca_27; "Failed to allocate multipleErrorMessage"...
0x180044db2  lea     ecx, [rbx+2]; unsigned __int8
0x180044db5  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180044dba  nop
0x180044dbb  xor     ecx, ecx; bstrString
0x180044dbd  call    cs:__imp_SysFreeString
0x180044dc3  nop
0x180044dc4  jmp     loc_180044EA1
0x180044dc9  xorps   xmm0, xmm0
0x180044dcc  xor     edx, edx
0x180044dce  movups  [rbp+57h+var_70], xmm0
0x180044dd2  lea     eax, [rdx+0Bh]
0x180044dd5  mov     word ptr [rbp+57h+var_70], ax
0x180044dd9  or      eax, 0FFFFFFFFh
0x180044ddc  mov     word ptr [rbp+57h+var_70+8], ax
0x180044de0  mov     rcx, [rbp+57h+var_80]
0x180044de4  movups  xmm0, [rbp+57h+var_70]
0x180044de8  movaps  [rbp+57h+var_70], xmm0
0x180044dec  mov     [rbp+57h+var_60], rdx
0x180044df0  mov     rax, [rcx]
0x180044df3  lea     r8, [rbp+57h+var_70]
0x180044df7  mov     rdx, rbx
0x180044dfa  mov     rax, [rax+280h]
0x180044e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e06  mov     edi, eax
0x180044e08  test    eax, eax
0x180044e0a  jns     short loc_180044E2D
0x180044e0c  mov     r8d, eax
0x180044e0f  lea     rdx, aFailedToSetIxm_1; "Failed to set IXMLDOMDocument3 Multiple"...
0x180044e16  mov     ecx, 2; unsigned __int8
0x180044e1b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180044e20  nop
0x180044e21  mov     rcx, rbx; bstrString
0x180044e24  call    cs:__imp_SysFreeString
0x180044e2a  nop
0x180044e2b  jmp     short loc_180044E63
0x180044e2d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180044e34  mov     ecx, 8; unsigned __int64
0x180044e39  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180044e3e  mov     [rbp+57h+var_78], rax
0x180044e42  test    rax, rax
0x180044e45  jz      short loc_180044E85
0x180044e47  mov     rcx, [rbp+57h+var_80]
0x180044e4b  mov     [rax], rcx
0x180044e4e  mov     [rbp+57h+var_80], 0
0x180044e56  mov     [rsi], rax
0x180044e59  mov     rcx, rbx; bstrString
0x180044e5c  call    cs:__imp_SysFreeString
0x180044e62  nop
0x180044e63  mov     rcx, [rbp+57h+var_80]
0x180044e67  test    rcx, rcx
0x180044e6a  jz      short loc_180044E81
0x180044e6c  mov     [rbp+57h+var_80], 0
0x180044e74  mov     rax, [rcx]
0x180044e77  mov     rax, [rax+10h]
0x180044e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e80  nop
0x180044e81  mov     eax, edi
0x180044e83  jmp     short loc_180044EC4
0x180044e85  lea     rdx, aFailedToAlloca_5; "Failed to allocate xdoc"
0x180044e8c  mov     ecx, 2; unsigned __int8
0x180044e91  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180044e96  nop
0x180044e97  mov     rcx, rbx; bstrString
0x180044e9a  call    cs:__imp_SysFreeString
0x180044ea0  nop
0x180044ea1  mov     rcx, [rbp+57h+var_80]
0x180044ea5  test    rcx, rcx
0x180044ea8  jz      short loc_180044EBF
0x180044eaa  mov     [rbp+57h+var_80], 0
0x180044eb2  mov     rax, [rcx]
0x180044eb5  mov     rax, [rax+10h]
0x180044eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ebe  nop
0x180044ebf  mov     eax, 8007000Eh
0x180044ec4  mov     rcx, [rbp+57h+var_30]
0x180044ec8  xor     rcx, rsp; StackCookie
0x180044ecb  call    __security_check_cookie
0x180044ed0  add     rsp, 98h
0x180044ed7  pop     rdi
0x180044ed8  pop     rsi
0x180044ed9  pop     rbx
0x180044eda  pop     rbp
0x180044edb  retn
```
