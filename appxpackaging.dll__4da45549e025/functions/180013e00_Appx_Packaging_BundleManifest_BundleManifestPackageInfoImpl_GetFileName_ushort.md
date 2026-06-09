# Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::GetFileName(ushort * *)

- ea: `0x180013e00`
- end: `0x1800140f2`
- name: `?GetFileName@BundleManifestPackageInfoImpl@BundleManifest@Packaging@Appx@@UEAAJPEAPEAG@Z`
- size: `754`
- prototype: `__int64 __fastcall(Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005eb8`
- `0x180010f40`
- `0x1800133fc`
- `0x180013e00`
- `0x180071f50`
- `0x18009d729`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013fc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014018`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013fc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014018`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013feb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013feb`
- `OLEAUT32!__imp_SysFreeString` at `0x180013f23`
- `OLEAUT32!__imp_SysFreeString` at `0x18001404d`
- `OLEAUT32!__imp_SysFreeString` at `0x180013f23`
- `OLEAUT32!__imp_SysFreeString` at `0x18001404d`
- `OLEAUT32!__imp_SysStringLen` at `0x180013eec`
- `OLEAUT32!__imp_SysStringLen` at `0x180013f54`
- `OLEAUT32!__imp_SysStringLen` at `0x180013eec`
- `OLEAUT32!__imp_SysStringLen` at `0x180013f54`

## string_xrefs

- `0x180013fad`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x180014062`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x180013f92`: `onecore\base\appmodel\common\autocotaskmemstring.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::GetFileName(
        Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl *this,
        unsigned __int16 **a2,
        __int64 a3,
        struct Common::AutoBStr *a4)
{
  BSTR *v6; // rsi
  int v7; // eax
  int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, BSTR, __int64 *); // rbx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rcx
  OLECHAR *v14; // rdi
  UINT v15; // eax
  unsigned __int64 v16; // rbx
  __int64 v17; // rdx
  unsigned int v18; // edi
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rsi
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // [rsp+20h] [rbp-30h] BYREF
  const unsigned __int16 *v25; // [rsp+28h] [rbp-28h]
  int v26; // [rsp+30h] [rbp-20h]
  const wchar_t *v27; // [rsp+38h] [rbp-18h]
  int v28; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 v30; // [rsp+78h] [rbp+28h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+30h] BYREF

  if ( !a2 )
  {
    v8 = -2147467261;
    v22 = 116;
    goto LABEL_27;
  }
  v6 = (BSTR *)((char *)this + 96);
  if ( !*((_QWORD *)this + 12) )
  {
    bstrString = 0;
    v25 = L"FileName";
    v24 = 5;
    v27 = L"']";
    v26 = 8;
    v28 = 0;
    v7 = Appx::Packaging::BuildXPath(
           (Appx::Packaging *)&v24,
           (const struct Appx::Packaging::XPathComponent *)1,
           (unsigned int)&bstrString,
           a4);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
        (const char *)(unsigned int)v7,
        v24);
      SysFreeString(bstrString);
LABEL_26:
      v22 = 120;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
        (const char *)(unsigned int)v8,
        v24);
      return (unsigned int)v8;
    }
    *v6 = 0;
    v9 = *((_QWORD *)this + 5);
    v30 = 0;
    v10 = *(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v9 + 296LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v30);
    v11 = v10(v9, bstrString, &v30);
    v8 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
        (const char *)(unsigned int)v11,
        v24);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v30);
    }
    else
    {
      if ( !v30 )
      {
LABEL_10:
        v8 = 0;
        goto LABEL_11;
      }
      v12 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v30 + 208LL))(v30, v6);
      v8 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x51,
          (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
          (const char *)(unsigned int)v12,
          v24);
      }
      else if ( !SysStringLen(*v6) )
      {
        v13 = v30;
        if ( v30 )
        {
          v30 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
        goto LABEL_10;
      }
      v23 = v30;
      if ( v30 )
      {
        v30 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
    }
LABEL_11:
    SysFreeString(bstrString);
    if ( v8 >= 0 )
      goto LABEL_12;
    goto LABEL_26;
  }
LABEL_12:
  v14 = *v6;
  if ( *v6 )
  {
    CoTaskMemFree(0);
    v15 = SysStringLen(v14);
    if ( v15 > 0x3FFFFFFF )
    {
      v18 = -2147024809;
      goto LABEL_20;
    }
    v16 = 2LL * v15;
    if ( v16 > 0xFFFFFFFF )
    {
      v17 = 27;
LABEL_18:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\base\\appmodel\\common\\autocotaskmemstring.cpp",
        (const char *)0x80070216LL,
        v24);
LABEL_19:
      v18 = -2147024882;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
        (const char *)v18,
        v24);
      CoTaskMemFree(0);
      return v18;
    }
    if ( (int)v16 + 2 < (unsigned int)v16 )
    {
      v17 = 29;
      goto LABEL_18;
    }
    v20 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)(v16 + 2));
    v21 = v20;
    if ( !v20 )
      goto LABEL_19;
    memcpy_0(v20, v14, (unsigned int)v16);
    v21[v16 / 2] = 0;
    *a2 = v21;
    CoTaskMemFree(0);
  }
  else
  {
    *a2 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180013e00  mov     [rsp-18h+arg_0], rbx
0x180013e05  mov     [rsp-18h+arg_18], rsi
0x180013e0a  push    rbp
0x180013e0b  push    rdi
0x180013e0c  push    r14
0x180013e0e  mov     rbp, rsp
0x180013e11  sub     rsp, 50h
0x180013e15  mov     r14, rdx
0x180013e18  mov     rdi, rcx
0x180013e1b  test    rdx, rdx
0x180013e1e  jz      loc_1800140C0
0x180013e24  lea     rsi, [rcx+60h]
0x180013e28  cmp     qword ptr [rsi], 0
0x180013e2c  jnz     loc_180013F37
0x180013e32  lea     rax, ?FileName@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "FileName"
0x180013e39  mov     [rbp+bstrString], 0
0x180013e41  mov     [rbp+var_28], rax
0x180013e45  lea     r8, [rbp+bstrString]; unsigned int
0x180013e49  lea     rax, asc_1801177B4; "']"
0x180013e50  mov     [rbp+var_30], 5
0x180013e57  mov     edx, 1; struct Appx::Packaging::XPathComponent *
0x180013e5c  mov     [rbp+var_18], rax
0x180013e60  lea     rcx, [rbp+var_30]; this
0x180013e64  mov     [rbp+var_20], 8
0x180013e6b  mov     [rbp+var_10], 0
0x180013e72  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x180013e77  mov     ebx, eax
0x180013e79  test    eax, eax
0x180013e7b  js      loc_180014031
0x180013e81  mov     qword ptr [rsi], 0
0x180013e88  lea     rcx, [rbp+arg_8]
0x180013e8c  mov     rdi, [rdi+28h]
0x180013e90  mov     [rbp+arg_8], 0
0x180013e98  mov     rax, [rdi]
0x180013e9b  mov     rbx, [rax+128h]
0x180013ea2  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180013ea7  mov     rdx, [rbp+bstrString]
0x180013eab  lea     r8, [rbp+arg_8]
0x180013eaf  mov     rcx, rdi
0x180013eb2  mov     rax, rbx
0x180013eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013eba  mov     ebx, eax
0x180013ebc  test    eax, eax
0x180013ebe  js      loc_1800140CC
0x180013ec4  mov     rcx, [rbp+arg_8]
0x180013ec8  test    rcx, rcx
0x180013ecb  jz      short loc_180013F1D
0x180013ecd  mov     rax, [rcx]
0x180013ed0  mov     rdx, rsi
0x180013ed3  mov     rax, [rax+0D0h]
0x180013eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013edf  mov     ebx, eax
0x180013ee1  test    eax, eax
0x180013ee3  js      loc_180014078
0x180013ee9  mov     rcx, [rsi]; pbstr
0x180013eec  call    cs:__imp_SysStringLen
0x180013ef3  nop     dword ptr [rax+rax+00h]
0x180013ef8  test    eax, eax
0x180013efa  jnz     loc_180014090
0x180013f00  mov     rcx, [rbp+arg_8]
0x180013f04  test    rcx, rcx
0x180013f07  jz      short loc_180013F1D
0x180013f09  mov     [rbp+arg_8], 0
0x180013f11  mov     rax, [rcx]
0x180013f14  mov     rax, [rax+10h]
0x180013f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f1d  xor     ebx, ebx
0x180013f1f  mov     rcx, [rbp+bstrString]; bstrString
0x180013f23  call    cs:__imp_SysFreeString
0x180013f2a  nop     dword ptr [rax+rax+00h]
0x180013f2f  test    ebx, ebx
0x180013f31  js      loc_180014059
0x180013f37  mov     rdi, [rsi]
0x180013f3a  test    rdi, rdi
0x180013f3d  jz      loc_180014028
0x180013f43  xor     ecx, ecx; pv
0x180013f45  call    cs:__imp_CoTaskMemFree
0x180013f4c  nop     dword ptr [rax+rax+00h]
0x180013f51  mov     rcx, rdi; pbstr
0x180013f54  call    cs:__imp_SysStringLen
0x180013f5b  nop     dword ptr [rax+rax+00h]
0x180013f60  cmp     eax, 3FFFFFFFh
0x180013f65  ja      loc_1800140B6
0x180013f6b  mov     eax, eax
0x180013f6d  lea     rbx, [rax+rax]
0x180013f71  mov     eax, 0FFFFFFFFh
0x180013f76  cmp     rbx, rax
0x180013f79  jbe     short loc_180013F82
0x180013f7b  mov     edx, 1Bh
0x180013f80  jmp     short loc_180013F8E
0x180013f82  lea     eax, [rbx+2]
0x180013f85  cmp     eax, ebx
0x180013f87  jnb     short loc_180013FE9
0x180013f89  mov     edx, 1Dh; void *
0x180013f8e  mov     rcx, [rbp+18h]; this
0x180013f92  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\common\\autoco"...
0x180013f99  mov     r9d, 80070216h; char *
0x180013f9f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180013fa4  mov     edi, 8007000Eh
0x180013fa9  mov     rcx, [rbp+18h]; this
0x180013fad  lea     r8, aOnecorePrintsc_96; "onecore\\printscan\\appxpackaging\\mani"...
0x180013fb4  mov     r9d, edi; char *
0x180013fb7  mov     edx, 82h; void *
0x180013fbc  xor     ebx, ebx
0x180013fbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013fc3  mov     ecx, ebx; pv
0x180013fc5  call    cs:__imp_CoTaskMemFree
0x180013fcc  nop     dword ptr [rax+rax+00h]
0x180013fd1  mov     eax, edi
0x180013fd3  lea     r11, [rsp+50h+var_s0]
0x180013fd8  mov     rbx, [r11+20h]
0x180013fdc  mov     rsi, [r11+38h]
0x180013fe0  mov     rsp, r11
0x180013fe3  pop     r14
0x180013fe5  pop     rdi
0x180013fe6  pop     rbp
0x180013fe7  retn
0x180013fe9  mov     ecx, eax; cb
0x180013feb  call    cs:__imp_CoTaskMemAlloc
0x180013ff2  nop     dword ptr [rax+rax+00h]
0x180013ff7  mov     rsi, rax
0x180013ffa  test    rax, rax
0x180013ffd  jz      short loc_180013FA4
0x180013fff  mov     r8d, ebx; Size
0x180014002  mov     rdx, rdi; Src
0x180014005  mov     rcx, rax; void *
0x180014008  call    memcpy_0
0x18001400d  xor     eax, eax
0x18001400f  xor     ecx, ecx; pv
0x180014011  mov     [rbx+rsi], ax
0x180014015  mov     [r14], rsi
0x180014018  call    cs:__imp_CoTaskMemFree
0x18001401f  nop     dword ptr [rax+rax+00h]
0x180014024  xor     eax, eax
0x180014026  jmp     short loc_180013FD3
0x180014028  mov     qword ptr [r14], 0
0x18001402f  jmp     short loc_180014024
0x180014031  mov     rcx, [rbp+18h]; this
0x180014035  lea     r8, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x18001403c  mov     r9d, eax; char *
0x18001403f  mov     edx, 104h; void *
0x180014044  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014049  mov     rcx, [rbp+bstrString]; bstrString
0x18001404d  call    cs:__imp_SysFreeString
0x180014054  nop     dword ptr [rax+rax+00h]
0x180014059  mov     edx, 78h ; 'x'; void *
0x18001405e  mov     rcx, [rbp+18h]; this
0x180014062  lea     r8, aOnecorePrintsc_96; "onecore\\printscan\\appxpackaging\\mani"...
0x180014069  mov     r9d, ebx; char *
0x18001406c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014071  mov     eax, ebx
0x180014073  jmp     loc_180013FD3
0x180014078  mov     rcx, [rbp+18h]; this
0x18001407c  lea     r8, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x180014083  mov     r9d, eax; char *
0x180014086  mov     edx, 51h ; 'Q'; void *
0x18001408b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014090  mov     rcx, [rbp+arg_8]
0x180014094  test    rcx, rcx
0x180014097  jz      loc_180013F1F
0x18001409d  mov     [rbp+arg_8], 0
0x1800140a5  mov     rax, [rcx]
0x1800140a8  mov     rax, [rax+10h]
0x1800140ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140b1  jmp     loc_180013F1F
0x1800140b6  mov     edi, 80070057h
0x1800140bb  jmp     loc_180013FA9
0x1800140c0  mov     ebx, 80004003h
0x1800140c5  mov     edx, 74h ; 't'
0x1800140ca  jmp     short loc_18001405E
0x1800140cc  mov     rcx, [rbp+18h]; this
0x1800140d0  lea     r8, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x1800140d7  mov     r9d, eax; char *
0x1800140da  mov     edx, 4Dh ; 'M'; void *
0x1800140df  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800140e4  lea     rcx, [rbp+arg_8]
0x1800140e8  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800140ed  jmp     loc_180013F1F
```
