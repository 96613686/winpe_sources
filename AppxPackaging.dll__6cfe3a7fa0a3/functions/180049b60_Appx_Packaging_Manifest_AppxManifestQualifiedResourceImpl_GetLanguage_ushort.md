# Appx::Packaging::Manifest::AppxManifestQualifiedResourceImpl::GetLanguage(ushort * *)

- ea: `0x180049b60`
- end: `0x180049f1a`
- name: `?GetLanguage@AppxManifestQualifiedResourceImpl@Manifest@Packaging@Appx@@UEAAJPEAPEAG@Z`
- size: `954`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::AppxManifestQualifiedResourceImpl *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005eb8`
- `0x180010f40`
- `0x1800133fc`
- `0x180049b60`
- `0x180071f50`
- `0x18009d729`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049c7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049d0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049e6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049c7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049d0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049e6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049cd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049cd0`
- `OLEAUT32!__imp_SysFreeString` at `0x180049d33`
- `OLEAUT32!__imp_SysFreeString` at `0x180049d42`
- `OLEAUT32!__imp_SysFreeString` at `0x180049de4`
- `OLEAUT32!__imp_SysFreeString` at `0x180049e34`
- `OLEAUT32!__imp_SysFreeString` at `0x180049e43`
- `OLEAUT32!__imp_SysFreeString` at `0x180049d33`
- `OLEAUT32!__imp_SysFreeString` at `0x180049d42`
- `OLEAUT32!__imp_SysFreeString` at `0x180049de4`
- `OLEAUT32!__imp_SysFreeString` at `0x180049e34`
- `OLEAUT32!__imp_SysFreeString` at `0x180049e43`
- `OLEAUT32!__imp_SysStringLen` at `0x180049c36`
- `OLEAUT32!__imp_SysStringLen` at `0x180049c98`
- `OLEAUT32!__imp_SysStringLen` at `0x180049c36`
- `OLEAUT32!__imp_SysStringLen` at `0x180049c98`

## string_xrefs

- `0x180049d7d`: `onecore\base\appmodel\common\autocotaskmemstring.cpp`
- `0x180049dcc`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestqualifiedresource.cpp`
- `0x180049e1c`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestqualifiedresource.cpp`
- `0x180049e58`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestqualifiedresource.cpp`
- `0x180049ec2`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestqualifiedresource.cpp`
- `0x180049ef9`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestqualifiedresource.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestQualifiedResourceImpl::GetLanguage(
        Appx::Packaging::Manifest::AppxManifestQualifiedResourceImpl *this,
        unsigned __int16 **a2,
        __int64 a3,
        struct Common::AutoBStr *a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  OLECHAR *v9; // r15
  int v10; // eax
  unsigned int v11; // edi
  int v12; // eax
  UINT v13; // eax
  BSTR v14; // rcx
  OLECHAR *v15; // rsi
  char *v16; // rbx
  UINT v17; // eax
  unsigned __int64 v18; // rdi
  char *v19; // rax
  OLECHAR *v20; // rcx
  __int64 v22; // rdx
  BSTR v23; // rcx
  int v24; // [rsp+20h] [rbp-40h] BYREF
  const unsigned __int16 *v25; // [rsp+28h] [rbp-38h]
  int v26; // [rsp+30h] [rbp-30h]
  const wchar_t *v27; // [rsp+38h] [rbp-28h]
  int v28; // [rsp+40h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  BSTR bstrString; // [rsp+88h] [rbp+28h] BYREF
  BSTR pbstr; // [rsp+90h] [rbp+30h] BYREF

  if ( a2 )
  {
    v25 = L"Language";
    v27 = L"']";
    bstrString = 0;
    v24 = 5;
    v26 = 8;
    v28 = 0;
    v6 = Appx::Packaging::BuildXPath(
           (Appx::Packaging *)&v24,
           (const struct Appx::Packaging::XPathComponent *)1,
           &bstrString,
           a4);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v8 = *((_QWORD *)this + 2);
      pbstr = 0;
      v9 = bstrString;
      bstrString = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, BSTR *))(*(_QWORD *)v8 + 296LL))(v8, v9, &bstrString);
      v11 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4D,
          (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
          (const char *)(unsigned int)v10,
          v24);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&bstrString);
      }
      else
      {
        if ( !bstrString )
        {
          v11 = 0;
          goto LABEL_10;
        }
        v12 = (*(__int64 (__fastcall **)(BSTR, BSTR *))(*(_QWORD *)bstrString + 208LL))(bstrString, &pbstr);
        v11 = v12;
        if ( v12 >= 0 )
        {
          v13 = SysStringLen(pbstr);
          v14 = bstrString;
          if ( v13 )
          {
            if ( bstrString )
            {
              bstrString = 0;
              (*(void (__fastcall **)(BSTR))(*(_QWORD *)v14 + 16LL))(v14);
            }
          }
          else
          {
            if ( bstrString )
            {
              bstrString = 0;
              (*(void (__fastcall **)(BSTR))(*(_QWORD *)v14 + 16LL))(v14);
            }
            v11 = 0;
          }
LABEL_10:
          v15 = pbstr;
          if ( !pbstr )
          {
            *a2 = 0;
            if ( (v11 & 0x80000000) == 0 )
              goto LABEL_21;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x45,
              (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestqualifiedresource.cpp",
              (const char *)v11,
              v24);
LABEL_18:
            v15 = pbstr;
LABEL_21:
            v20 = v15;
LABEL_22:
            SysFreeString(v20);
            SysFreeString(v9);
            return v11;
          }
          CoTaskMemFree(0);
          v16 = 0;
          v17 = SysStringLen(v15);
          if ( v17 > 0x3FFFFFFF )
          {
            v11 = -2147024809;
          }
          else
          {
            v18 = 2LL * v17;
            if ( v18 > 0xFFFFFFFF )
            {
              v22 = 27;
            }
            else
            {
              if ( (int)v18 + 2 >= (unsigned int)v18 )
              {
                v19 = (char *)CoTaskMemAlloc((unsigned int)(v18 + 2));
                v16 = v19;
                if ( v19 )
                {
                  memcpy_0(v19, v15, (unsigned int)v18);
                  *(_WORD *)&v16[v18] = 0;
                  v11 = 0;
                }
                else
                {
                  v16 = 0;
                  v11 = -2147024882;
                }
                goto LABEL_16;
              }
              v22 = 29;
            }
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)v22,
              (unsigned int)"onecore\\base\\appmodel\\common\\autocotaskmemstring.cpp",
              (const char *)0x80070216LL,
              v24);
            v11 = -2147024882;
          }
LABEL_16:
          if ( (v11 & 0x80000000) != 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x3D,
              (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestqualifiedresource.cpp",
              (const char *)v11,
              v24);
            CoTaskMemFree(v16);
            v20 = pbstr;
            goto LABEL_22;
          }
          *a2 = (unsigned __int16 *)v16;
          CoTaskMemFree(0);
          goto LABEL_18;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x51,
          (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
          (const char *)(unsigned int)v12,
          v24);
        v23 = bstrString;
        if ( bstrString )
        {
          bstrString = 0;
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)v23 + 16LL))(v23);
        }
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x38,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestqualifiedresource.cpp",
        (const char *)v11,
        v24);
      SysFreeString(pbstr);
      SysFreeString(v9);
      return v11;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestqualifiedresource.cpp",
      (const char *)(unsigned int)v6,
      v24);
    SysFreeString(bstrString);
    return v7;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestqualifiedresource.cpp",
      (const char *)0x80004003LL,
      v24);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180049b60  push    rbp
0x180049b62  push    rdi
0x180049b63  push    r14
0x180049b65  mov     rbp, rsp
0x180049b68  sub     rsp, 60h
0x180049b6c  mov     r14, rdx
0x180049b6f  mov     rdi, rcx
0x180049b72  test    rdx, rdx
0x180049b75  jz      loc_180049EBE
0x180049b7b  lea     rax, ?Language@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Language"
0x180049b82  mov     [rsp+60h+arg_0], rbx
0x180049b8a  mov     [rbp+var_38], rax
0x180049b8e  lea     r8, [rbp+bstrString]; unsigned int
0x180049b92  lea     rax, asc_1801177B4; "']"
0x180049b99  mov     [rsp+60h+var_8], r12
0x180049b9e  xor     r12d, r12d
0x180049ba1  mov     [rbp+var_28], rax
0x180049ba5  mov     edx, 1; struct Appx::Packaging::XPathComponent *
0x180049baa  mov     [rbp+bstrString], r12
0x180049bae  lea     rcx, [rbp+var_40]; this
0x180049bb2  mov     [rbp+var_40], 5
0x180049bb9  mov     [rbp+var_30], 8
0x180049bc0  mov     [rbp+var_20], r12d
0x180049bc4  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x180049bc9  mov     ebx, eax
0x180049bcb  test    eax, eax
0x180049bcd  js      loc_180049DC8
0x180049bd3  mov     rcx, [rdi+10h]
0x180049bd7  lea     r8, [rbp+bstrString]
0x180049bdb  mov     [rbp+pbstr], r12
0x180049bdf  mov     [rsp+60h+var_10], r15
0x180049be4  mov     r15, [rbp+bstrString]
0x180049be8  mov     [rbp+bstrString], r12
0x180049bec  mov     rdx, r15
0x180049bef  mov     rax, [rcx]
0x180049bf2  mov     rax, [rax+128h]
0x180049bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049bfe  mov     edi, eax
0x180049c00  test    eax, eax
0x180049c02  js      loc_180049DF7
0x180049c08  mov     rcx, [rbp+bstrString]
0x180049c0c  test    rcx, rcx
0x180049c0f  jz      loc_180049D1D
0x180049c15  mov     rax, [rcx]
0x180049c18  lea     rdx, [rbp+pbstr]
0x180049c1c  mov     rax, [rax+0D0h]
0x180049c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c28  mov     edi, eax
0x180049c2a  test    eax, eax
0x180049c2c  js      loc_180049E84
0x180049c32  mov     rcx, [rbp+pbstr]; pbstr
0x180049c36  call    cs:__imp_SysStringLen
0x180049c3d  nop     dword ptr [rax+rax+00h]
0x180049c42  mov     rcx, [rbp+bstrString]
0x180049c46  test    eax, eax
0x180049c48  jnz     loc_180049DA0
0x180049c4e  test    rcx, rcx
0x180049c51  jz      short loc_180049C63
0x180049c53  mov     [rbp+bstrString], r12
0x180049c57  mov     rax, [rcx]
0x180049c5a  mov     rax, [rax+10h]
0x180049c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c63  mov     edi, r12d
0x180049c66  mov     [rsp+60h+arg_18], rsi
0x180049c6e  mov     rsi, [rbp+pbstr]
0x180049c72  test    rsi, rsi
0x180049c75  jz      loc_180049D25
0x180049c7b  xor     ecx, ecx; pv
0x180049c7d  call    cs:__imp_CoTaskMemFree
0x180049c84  nop     dword ptr [rax+rax+00h]
0x180049c89  mov     rbx, r12
0x180049c8c  test    rsi, rsi
0x180049c8f  jz      loc_180049F12
0x180049c95  mov     rcx, rsi; pbstr
0x180049c98  call    cs:__imp_SysStringLen
0x180049c9f  nop     dword ptr [rax+rax+00h]
0x180049ca4  cmp     eax, 3FFFFFFFh
0x180049ca9  ja      loc_180049DBE
0x180049caf  mov     eax, eax
0x180049cb1  lea     rdi, [rax+rax]
0x180049cb5  mov     eax, 0FFFFFFFFh
0x180049cba  cmp     rdi, rax
0x180049cbd  ja      loc_180049D99
0x180049cc3  lea     eax, [rdi+2]
0x180049cc6  cmp     eax, edi
0x180049cc8  jb      loc_180049D74
0x180049cce  mov     ecx, eax; cb
0x180049cd0  call    cs:__imp_CoTaskMemAlloc
0x180049cd7  nop     dword ptr [rax+rax+00h]
0x180049cdc  mov     rbx, rax
0x180049cdf  test    rax, rax
0x180049ce2  jz      loc_180049EE8
0x180049ce8  mov     r8d, edi; Size
0x180049ceb  mov     rdx, rsi; Src
0x180049cee  mov     rcx, rax; void *
0x180049cf1  call    memcpy_0
0x180049cf6  mov     [rdi+rbx], r12w
0x180049cfb  mov     edi, r12d
0x180049cfe  test    edi, edi
0x180049d00  js      loc_180049E54
0x180049d06  xor     ecx, ecx; pv
0x180049d08  mov     [r14], rbx
0x180049d0b  call    cs:__imp_CoTaskMemFree
0x180049d12  nop     dword ptr [rax+rax+00h]
0x180049d17  mov     rsi, [rbp+pbstr]
0x180049d1b  jmp     short loc_180049D30
0x180049d1d  mov     edi, r12d
0x180049d20  jmp     loc_180049C66
0x180049d25  mov     [r14], r12
0x180049d28  test    edi, edi
0x180049d2a  js      loc_180049EF5
0x180049d30  mov     rcx, rsi; bstrString
0x180049d33  call    cs:__imp_SysFreeString
0x180049d3a  nop     dword ptr [rax+rax+00h]
0x180049d3f  mov     rcx, r15; bstrString
0x180049d42  call    cs:__imp_SysFreeString
0x180049d49  nop     dword ptr [rax+rax+00h]
0x180049d4e  mov     rsi, [rsp+60h+arg_18]
0x180049d56  mov     r15, [rsp+60h+var_10]
0x180049d5b  mov     eax, edi
0x180049d5d  mov     rbx, [rsp+60h+arg_0]
0x180049d65  mov     r12, [rsp+60h+var_8]
0x180049d6a  add     rsp, 60h
0x180049d6e  pop     r14
0x180049d70  pop     rdi
0x180049d71  pop     rbp
0x180049d72  retn
0x180049d74  mov     edx, 1Dh; void *
0x180049d79  mov     rcx, [rbp+18h]; this
0x180049d7d  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\common\\autoco"...
0x180049d84  mov     r9d, 80070216h; char *
0x180049d8a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049d8f  mov     edi, 8007000Eh
0x180049d94  jmp     loc_180049CFE
0x180049d99  mov     edx, 1Bh
0x180049d9e  jmp     short loc_180049D79
0x180049da0  test    rcx, rcx
0x180049da3  jz      loc_180049C66
0x180049da9  mov     [rbp+bstrString], r12
0x180049dad  mov     rax, [rcx]
0x180049db0  mov     rax, [rax+10h]
0x180049db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049db9  jmp     loc_180049C66
0x180049dbe  mov     edi, 80070057h
0x180049dc3  jmp     loc_180049CFE
0x180049dc8  mov     rcx, [rbp+18h]; this
0x180049dcc  lea     r8, aOnecorePrintsc_115; "onecore\\printscan\\appxpackaging\\mani"...
0x180049dd3  mov     r9d, ebx; char *
0x180049dd6  mov     edx, 36h ; '6'; void *
0x180049ddb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049de0  mov     rcx, [rbp+bstrString]; bstrString
0x180049de4  call    cs:__imp_SysFreeString
0x180049deb  nop     dword ptr [rax+rax+00h]
0x180049df0  mov     eax, ebx
0x180049df2  jmp     loc_180049D5D
0x180049df7  mov     rcx, [rbp+18h]; this
0x180049dfb  lea     r8, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x180049e02  mov     r9d, eax; char *
0x180049e05  mov     edx, 4Dh ; 'M'; void *
0x180049e0a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049e0f  lea     rcx, [rbp+bstrString]
0x180049e13  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180049e18  mov     rcx, [rbp+18h]; this
0x180049e1c  lea     r8, aOnecorePrintsc_115; "onecore\\printscan\\appxpackaging\\mani"...
0x180049e23  mov     r9d, edi; char *
0x180049e26  mov     edx, 38h ; '8'; void *
0x180049e2b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049e30  mov     rcx, [rbp+pbstr]; bstrString
0x180049e34  call    cs:__imp_SysFreeString
0x180049e3b  nop     dword ptr [rax+rax+00h]
0x180049e40  mov     rcx, r15; bstrString
0x180049e43  call    cs:__imp_SysFreeString
0x180049e4a  nop     dword ptr [rax+rax+00h]
0x180049e4f  jmp     loc_180049D56
0x180049e54  mov     rcx, [rbp+18h]; this
0x180049e58  lea     r8, aOnecorePrintsc_115; "onecore\\printscan\\appxpackaging\\mani"...
0x180049e5f  mov     r9d, edi; char *
0x180049e62  mov     edx, 3Dh ; '='; void *
0x180049e67  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049e6c  mov     rcx, rbx; pv
0x180049e6f  call    cs:__imp_CoTaskMemFree
0x180049e76  nop     dword ptr [rax+rax+00h]
0x180049e7b  mov     rcx, [rbp+pbstr]
0x180049e7f  jmp     loc_180049D33
0x180049e84  mov     rcx, [rbp+18h]; this
0x180049e88  lea     r8, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x180049e8f  mov     r9d, eax; char *
0x180049e92  mov     edx, 51h ; 'Q'; void *
0x180049e97  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049e9c  mov     rcx, [rbp+bstrString]
0x180049ea0  test    rcx, rcx
0x180049ea3  jz      loc_180049E18
0x180049ea9  mov     [rbp+bstrString], r12
0x180049ead  mov     rax, [rcx]
0x180049eb0  mov     rax, [rax+10h]
0x180049eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049eb9  jmp     loc_180049E18
0x180049ebe  mov     rcx, [rbp+18h]; this
0x180049ec2  lea     r8, aOnecorePrintsc_115; "onecore\\printscan\\appxpackaging\\mani"...
0x180049ec9  mov     r9d, 80004003h; char *
0x180049ecf  mov     edx, 32h ; '2'; void *
0x180049ed4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049ed9  mov     eax, 80004003h
0x180049ede  add     rsp, 60h
0x180049ee2  pop     r14
0x180049ee4  pop     rdi
0x180049ee5  pop     rbp
0x180049ee6  retn
0x180049ee8  mov     rbx, r12
0x180049eeb  mov     edi, 8007000Eh
0x180049ef0  jmp     loc_180049CFE
0x180049ef5  mov     rcx, [rbp+18h]; this
0x180049ef9  lea     r8, aOnecorePrintsc_115; "onecore\\printscan\\appxpackaging\\mani"...
0x180049f00  mov     r9d, edi; char *
0x180049f03  mov     edx, 45h ; 'E'; void *
0x180049f08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049f0d  jmp     loc_180049D17
0x180049f12  mov     edi, r12d
0x180049f15  jmp     loc_180049D06
```
