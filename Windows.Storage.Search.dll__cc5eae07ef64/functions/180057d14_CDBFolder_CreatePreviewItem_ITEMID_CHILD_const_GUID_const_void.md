# CDBFolder::_CreatePreviewItem(_ITEMID_CHILD const *,_GUID const &,void * *)

- ea: `0x180057d14`
- end: `0x180057fad`
- name: `?_CreatePreviewItem@CDBFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z`
- size: `665`
- prototype: `__int64 __fastcall(IShellFolder *psfParent, LPCITEMIDLIST pidl, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001a640`

## callees

- `0x180008744`
- `0x18000a730`
- `0x180015588`
- `0x180057d14`
- `0x180069f58`
- `0x180071dc0`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!SHCreateItemWithParent` at `0x180057e2a`
- `Windows.Storage!SHCreateItemWithParent` at `0x180057e2a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180057da1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180057da1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180057df9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180057df9`
- `PROPSYS!PropVariantToBSTR` at `0x180057d95`
- `PROPSYS!PropVariantToBSTR` at `0x180057d95`
- `OLEAUT32!__imp_SysFreeString` at `0x180057f5b`
- `OLEAUT32!__imp_SysFreeString` at `0x180057f7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180057f89`
- `OLEAUT32!__imp_SysFreeString` at `0x180057f5b`
- `OLEAUT32!__imp_SysFreeString` at `0x180057f7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180057f89`
- `urlmon!CreateUri` at `0x180057efc`
- `urlmon!CreateUri` at `0x180057efc`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDBFolder::_CreatePreviewItem(
        IShellFolder *psfParent,
        LPCITEMIDLIST pidl,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT v8; // ebx
  CDBFolder *v9; // rcx
  unsigned int PreviewRelatedItem; // ebx
  CDBFolder *v11; // rcx
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR pwzURI; // [rsp+48h] [rbp-B8h] BYREF
  int v15; // [rsp+50h] [rbp-B0h] BYREF
  IUri *ppURI; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+60h] [rbp-A0h] BYREF
  void *ppvItem; // [rsp+68h] [rbp-98h] BYREF
  PCWSTR pszSrch; // [rsp+70h] [rbp-90h] BYREF
  BSTR pbstrOut; // [rsp+78h] [rbp-88h] BYREF
  PROPVARIANT propvar[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v22; // [rsp+90h] [rbp-70h]
  _BYTE v23[80]; // [rsp+A0h] [rbp-60h] BYREF

  *a4 = 0;
  pszSrch = 0;
  pbstrOut = 0;
  *(_OWORD *)propvar = 0;
  v22 = 0;
  if ( (int)CDBFolder::GetPropertyForItem(&psfParent[23], pidl, PKEY_WebPreviewUrl, 0, propvar) < 0
    || (v8 = PropVariantToBSTR(propvar, &pbstrOut), PropVariantClear(propvar), v8 < 0) )
  {
    PreviewRelatedItem = -2147467262;
    if ( (int)CDBFolder::_GetStringDetailsOf(psfParent, 0, pidl, &PKEY_Kind, &pszSrch) >= 0
      && StrStrIW(L"picture", pszSrch) )
    {
      ppvItem = 0;
      if ( SHCreateItemWithParent(0, psfParent, pidl, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppvItem) >= 0 )
      {
        v17 = 0;
        if ( (*(int (__fastcall **)(void *, _QWORD, const GUID *, GUID *, __int64 *))(*(_QWORD *)ppvItem + 24LL))(
               ppvItem,
               0,
               &BHID_AssociationArray,
               &GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57,
               &v17) >= 0 )
        {
          v15 = 39;
          if ( (*(int (__fastcall **)(__int64, __int64, __int64, const wchar_t *, _BYTE *, int *))(*(_QWORD *)v17 + 32LL))(
                 v17,
                 16,
                 16,
                 L"{8895b1c6-b41f-4c1c-a562-0d564250836f}",
                 v23,
                 &v15) < 0 )
          {
            pwzURI = 0;
            if ( (int)CDBFolder::_GetStringDetailsOf(psfParent, 0, pidl, PKEY_ContentUrl, &pwzURI) >= 0 )
            {
              ppURI = 0;
              if ( CreateUri(pwzURI, 4u, 0, &ppURI) >= 0 )
              {
                v13 = 0;
                if ( ((int (__fastcall *)(IUri *, int *))ppURI->lpVtbl->GetScheme)(ppURI, &v13) >= 0
                  && (v13 == 2 || v13 == 11) )
                {
                  PreviewRelatedItem = CDBFolder::_CreatePreviewRelatedItem(v11, pwzURI, a3, a4);
                }
              }
              ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(&ppURI);
            }
            SysFreeString((BSTR)pwzURI);
          }
        }
        ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(&v17);
      }
      ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(&ppvItem);
    }
  }
  else
  {
    PreviewRelatedItem = CDBFolder::_CreatePreviewRelatedItem(v9, pbstrOut, a3, a4);
  }
  SysFreeString((BSTR)pszSrch);
  SysFreeString(pbstrOut);
  return PreviewRelatedItem;
}

```

## disassembly

```asm
0x180057d14  push    rbp
0x180057d16  push    rbx
0x180057d17  push    rsi
0x180057d18  push    rdi
0x180057d19  push    r14
0x180057d1b  push    r15
0x180057d1d  lea     rbp, [rsp-8]
0x180057d22  sub     rsp, 108h
0x180057d29  mov     rax, cs:__security_cookie
0x180057d30  xor     rax, rsp
0x180057d33  mov     [rbp+30h+var_40], rax
0x180057d37  mov     r14, r9
0x180057d3a  mov     r15, r8
0x180057d3d  mov     rsi, rdx
0x180057d40  mov     rdi, rcx
0x180057d43  mov     qword ptr [r9], 0
0x180057d4a  mov     [rsp+130h+pszSrch], 0
0x180057d53  mov     [rsp+130h+pbstrOut], 0
0x180057d5c  xorps   xmm0, xmm0
0x180057d5f  xor     eax, eax
0x180057d61  movups  xmmword ptr [rbp+30h+propvar], xmm0
0x180057d65  mov     [rbp+30h+var_A0], rax
0x180057d69  add     rcx, 0B8h
0x180057d70  lea     rax, [rbp+30h+propvar]
0x180057d74  mov     [rsp+130h+ppvItem], rax
0x180057d79  xor     r9d, r9d
0x180057d7c  lea     r8, PKEY_WebPreviewUrl
0x180057d83  call    ?GetPropertyForItem@CDBFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@W4PROPERTY_GET_TYPE@@PEAUtagPROPVARIANT@@@Z; CDBFolder::GetPropertyForItem(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,PROPERTY_GET_TYPE,tagPROPVARIANT *)
0x180057d88  test    eax, eax
0x180057d8a  js      short loc_180057DC2
0x180057d8c  lea     rdx, [rsp+130h+pbstrOut]; pbstrOut
0x180057d91  lea     rcx, [rbp+30h+propvar]; propvar
0x180057d95  call    cs:__imp_PropVariantToBSTR
0x180057d9b  mov     ebx, eax
0x180057d9d  lea     rcx, [rbp+30h+propvar]; pvar
0x180057da1  call    cs:__imp_PropVariantClear
0x180057da7  test    ebx, ebx
0x180057da9  js      short loc_180057DC2
0x180057dab  mov     r9, r14; void **
0x180057dae  mov     r8, r15; struct _GUID *
0x180057db1  mov     rdx, [rsp+130h+pbstrOut]; unsigned __int16 *
0x180057db6  call    ?_CreatePreviewRelatedItem@CDBFolder@@AEAAJPEBGAEBU_GUID@@PEAPEAX@Z; CDBFolder::_CreatePreviewRelatedItem(ushort const *,_GUID const &,void * *)
0x180057dbb  mov     ebx, eax
0x180057dbd  jmp     loc_180057F78
0x180057dc2  mov     ebx, 80004002h
0x180057dc7  lea     rax, [rsp+130h+pszSrch]
0x180057dcc  mov     [rsp+130h+ppvItem], rax
0x180057dd1  lea     r9, PKEY_Kind
0x180057dd8  mov     r8, rsi
0x180057ddb  xor     edx, edx
0x180057ddd  mov     rcx, rdi
0x180057de0  call    ?_GetStringDetailsOf@CDBFolder@@AEAAJW4PROPERTY_GET_TYPE@@PEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAPEAG@Z; CDBFolder::_GetStringDetailsOf(PROPERTY_GET_TYPE,_ITEMID_CHILD const *,_tagpropertykey const &,ushort * *)
0x180057de5  test    eax, eax
0x180057de7  js      loc_180057F78
0x180057ded  mov     rdx, [rsp+130h+pszSrch]; pszSrch
0x180057df2  lea     rcx, aPicture; "picture"
0x180057df9  call    cs:__imp_StrStrIW
0x180057dff  test    rax, rax
0x180057e02  jz      loc_180057F78
0x180057e08  mov     [rsp+130h+var_C8], 0
0x180057e11  lea     rax, [rsp+130h+var_C8]
0x180057e16  mov     [rsp+130h+ppvItem], rax; ppvItem
0x180057e1b  lea     r9, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180057e22  mov     r8, rsi; pidl
0x180057e25  mov     rdx, rdi; psfParent
0x180057e28  xor     ecx, ecx; pidlParent
0x180057e2a  call    cs:__imp_SHCreateItemWithParent
0x180057e30  test    eax, eax
0x180057e32  js      loc_180057F6D
0x180057e38  mov     [rsp+130h+var_D0], 0
0x180057e41  mov     rcx, [rsp+130h+var_C8]
0x180057e46  mov     rax, [rcx]
0x180057e49  lea     rdx, [rsp+130h+var_D0]
0x180057e4e  mov     [rsp+130h+ppvItem], rdx
0x180057e53  lea     r9, _GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57
0x180057e5a  lea     r8, BHID_AssociationArray
0x180057e61  xor     edx, edx
0x180057e63  mov     rax, [rax+18h]
0x180057e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057e6c  test    eax, eax
0x180057e6e  js      loc_180057F62
0x180057e74  mov     [rsp+130h+var_E0], 27h ; '''
0x180057e7c  mov     rcx, [rsp+130h+var_D0]
0x180057e81  mov     rax, [rcx]
0x180057e84  lea     rdx, [rsp+130h+var_E0]
0x180057e89  mov     [rsp+130h+var_108], rdx
0x180057e8e  lea     rdx, [rbp+30h+var_90]
0x180057e92  mov     [rsp+130h+ppvItem], rdx
0x180057e97  lea     r9, a8895b1c6B41f4c; "{8895b1c6-b41f-4c1c-a562-0d564250836f}"
0x180057e9e  mov     edx, 10h
0x180057ea3  mov     r8d, edx
0x180057ea6  mov     rax, [rax+20h]
0x180057eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057eaf  test    eax, eax
0x180057eb1  jns     loc_180057F62
0x180057eb7  mov     [rsp+130h+pwzURI], 0
0x180057ec0  lea     rax, [rsp+130h+pwzURI]
0x180057ec5  mov     [rsp+130h+ppvItem], rax
0x180057eca  lea     r9, PKEY_ContentUrl
0x180057ed1  mov     r8, rsi
0x180057ed4  xor     edx, edx
0x180057ed6  mov     rcx, rdi
0x180057ed9  call    ?_GetStringDetailsOf@CDBFolder@@AEAAJW4PROPERTY_GET_TYPE@@PEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAPEAG@Z; CDBFolder::_GetStringDetailsOf(PROPERTY_GET_TYPE,_ITEMID_CHILD const *,_tagpropertykey const &,ushort * *)
0x180057ede  test    eax, eax
0x180057ee0  js      short loc_180057F56
0x180057ee2  mov     [rsp+130h+ppURI], 0
0x180057eeb  lea     r9, [rsp+130h+ppURI]; ppURI
0x180057ef0  xor     r8d, r8d; dwReserved
0x180057ef3  lea     edx, [r8+4]; dwFlags
0x180057ef7  mov     rcx, [rsp+130h+pwzURI]; pwzURI
0x180057efc  call    cs:__imp_CreateUri
0x180057f02  test    eax, eax
0x180057f04  js      short loc_180057F4B
0x180057f06  mov     [rsp+130h+var_F0], 0
0x180057f0e  mov     rcx, [rsp+130h+ppURI]
0x180057f13  mov     rax, [rcx]
0x180057f16  lea     rdx, [rsp+130h+var_F0]
0x180057f1b  mov     rax, [rax+0C0h]
0x180057f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f27  test    eax, eax
0x180057f29  js      short loc_180057F4B
0x180057f2b  cmp     [rsp+130h+var_F0], 2
0x180057f30  jz      short loc_180057F39
0x180057f32  cmp     [rsp+130h+var_F0], 0Bh
0x180057f37  jnz     short loc_180057F4B
0x180057f39  mov     r9, r14; void **
0x180057f3c  mov     r8, r15; struct _GUID *
0x180057f3f  mov     rdx, [rsp+130h+pwzURI]; unsigned __int16 *
0x180057f44  call    ?_CreatePreviewRelatedItem@CDBFolder@@AEAAJPEBGAEBU_GUID@@PEAPEAX@Z; CDBFolder::_CreatePreviewRelatedItem(ushort const *,_GUID const &,void * *)
0x180057f49  mov     ebx, eax
0x180057f4b  lea     rcx, [rsp+130h+ppURI]
0x180057f50  call    ??1?$CComPtr@UIResultShape@@@ATL@@QEAA@XZ; ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(void)
0x180057f55  nop
0x180057f56  mov     rcx, [rsp+130h+pwzURI]; bstrString
0x180057f5b  call    cs:__imp_SysFreeString
0x180057f61  nop
0x180057f62  lea     rcx, [rsp+130h+var_D0]
0x180057f67  call    ??1?$CComPtr@UIResultShape@@@ATL@@QEAA@XZ; ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(void)
0x180057f6c  nop
0x180057f6d  lea     rcx, [rsp+130h+var_C8]
0x180057f72  call    ??1?$CComPtr@UIResultShape@@@ATL@@QEAA@XZ; ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(void)
0x180057f77  nop
0x180057f78  mov     rcx, [rsp+130h+pszSrch]; bstrString
0x180057f7d  call    cs:__imp_SysFreeString
0x180057f83  nop
0x180057f84  mov     rcx, [rsp+130h+pbstrOut]; bstrString
0x180057f89  call    cs:__imp_SysFreeString
0x180057f8f  mov     eax, ebx
0x180057f91  mov     rcx, [rbp+30h+var_40]
0x180057f95  xor     rcx, rsp; StackCookie
0x180057f98  call    __security_check_cookie
0x180057f9d  add     rsp, 108h
0x180057fa4  pop     r15
0x180057fa6  pop     r14
0x180057fa8  pop     rdi
0x180057fa9  pop     rsi
0x180057faa  pop     rbx
0x180057fab  pop     rbp
0x180057fac  retn
```
