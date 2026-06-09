# CFormCreds::GetFormCredentialThread(void *)

- ea: `0x18001c980`
- end: `0x18001cdea`
- name: `?GetFormCredentialThread@CFormCreds@@SAKPEAX@Z`
- size: `1130`
- prototype: `__int64 __fastcall(IStream **pParam)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180006060`
- `0x18001c058`
- `0x18001c2f4`
- `0x18001c7a4`
- `0x18001c980`
- `0x18001cdf0`
- `0x18001cf28`
- `0x18001d554`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cdb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cdb4`
- `ntdll!_wcsicmp` at `0x18001cb3b`
- `ntdll!_wcsicmp` at `0x18001cb3b`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x18001c9ea`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x18001c9ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ccb7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ccc0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ccd1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ccda`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cdc4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ccb7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ccc0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ccd1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ccda`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cdc4`
- `OLEAUT32!__imp_VariantInit` at `0x18001ccec`
- `OLEAUT32!__imp_VariantInit` at `0x18001ccf7`
- `OLEAUT32!__imp_VariantInit` at `0x18001ccec`
- `OLEAUT32!__imp_VariantInit` at `0x18001ccf7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001cd7c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001cd8a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001cd7c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001cd8a`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18001cc14`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18001cca7`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18001cc14`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18001cca7`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18001cb83`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18001cb95`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18001cb83`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18001cb95`
- `VAULTCLI!VaultGetItem` at `0x18001cc61`
- `VAULTCLI!VaultGetItem` at `0x18001cc61`
- `VAULTCLI!VaultCloseVault` at `0x18001cdab`
- `VAULTCLI!VaultCloseVault` at `0x18001cdab`
- `VAULTCLI!VaultFree` at `0x18001cc93`
- `VAULTCLI!VaultFree` at `0x18001cd99`
- `VAULTCLI!VaultFree` at `0x18001cc93`
- `VAULTCLI!VaultFree` at `0x18001cd99`
- `VAULTCLI!VaultOpenVault` at `0x18001ca09`
- `VAULTCLI!VaultOpenVault` at `0x18001ca09`
- `VAULTCLI!VaultFindItems` at `0x18001cac6`
- `VAULTCLI!VaultFindItems` at `0x18001cac6`

## pseudocode

```c
__int64 __fastcall CFormCreds::GetFormCredentialThread(IStream **pParam)
{
  unsigned int v1; // r13d
  _GET_FORM_CREDENTIAL_PARAM *v2; // rbx
  IStream *v3; // rcx
  wchar_t *v4; // r14
  HRESULT InterfaceAndReleaseStream; // eax
  wchar_t *lpwszUrl; // rcx
  unsigned int v7; // esi
  char v8; // r12
  ULONG v9; // r15d
  unsigned int v10; // edi
  __int64 v11; // rbx
  unsigned int v12; // eax
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v14; // rcx
  SAFEARRAY *v15; // r12
  ULONG v16; // ecx
  __int64 v17; // rdi
  wchar_t *m_str; // rbx
  const wchar_t *String; // rdx
  _VAULT_ITEM_ELEMENT *pAuthenticatorElement; // rcx
  wchar_t *v21; // rdi
  __int64 v22; // rbx
  _VAULT_ITEM *pItems; // [rsp+40h] [rbp-C0h] BYREF
  SAFEARRAY *psa; // [rsp+48h] [rbp-B8h]
  void *hVault; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v27; // [rsp+58h] [rbp-A8h]
  Microsoft::WRL::ComPtr<IAuthHost> spAuthHost; // [rsp+60h] [rbp-A0h] BYREF
  _VAULT_ITEM *pLocalItem; // [rsp+68h] [rbp-98h] BYREF
  tagVARIANT varPassword; // [rsp+70h] [rbp-90h] BYREF
  tagVARIANT varUserName; // [rsp+88h] [rbp-78h] BYREF
  _VAULT_ITEM_ELEMENT ResourceElement; // [rsp+A0h] [rbp-60h] BYREF
  ATL::CComBSTR bstrUser; // [rsp+C0h] [rbp-40h] BYREF
  ATL::CComBSTR bstrPassword; // [rsp+C8h] [rbp-38h] BYREF
  _VAULT_ITEM_ELEMENT PackageSidElement; // [rsp+D0h] [rbp-30h] BYREF
  _VAULT_ITEM_ELEMENT IdentityElement; // [rsp+F0h] [rbp-10h] BYREF
  char v38; // [rsp+168h] [rbp+68h]
  wchar_t *nIndex; // [rsp+170h] [rbp+70h] BYREF
  unsigned int nItems; // [rsp+178h] [rbp+78h] BYREF

  v1 = 0;
  spAuthHost.ptr_ = 0;
  hVault = 0;
  v2 = (_GET_FORM_CREDENTIAL_PARAM *)pParam;
  pItems = 0;
  v3 = *pParam;
  memset(&ResourceElement, 0, sizeof(ResourceElement));
  nItems = 0;
  v4 = 0;
  nIndex = 0;
  memset(&IdentityElement, 0, sizeof(IdentityElement));
  memset(&PackageSidElement, 0, sizeof(PackageSidElement));
  InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(
                                v3,
                                &GUID_5de7918b_bfd7_4c1e_b4e0_b16d0a3ea76b,
                                (LPVOID *)&spAuthHost.ptr_);
  v2->IAuthHostStream = 0;
  if ( InterfaceAndReleaseStream >= 0
    && !(unsigned int)VaultOpenVault(&Vault_DefaultVault_ID, 0, &hVault)
    && !(unsigned int)CopyIECredentials(hVault, v2->lpwszUrl) )
  {
    lpwszUrl = v2->lpwszUrl;
    v7 = 0;
    v27 = 0;
    v8 = 0;
    GetPreferredAccountForUrl(lpwszUrl, &nIndex);
    ResourceElement.ItemValue.8 = ($A5D428126EF00C1ACC863D9D3F0013C1)(unsigned __int64)v2->lpwszUrl;
    *(_QWORD *)&ResourceElement.SchemaElementId = 1;
    PackageSidElement.ItemValue.String = (wchar_t *)&gWABPackageSidBuffer;
    *(_QWORD *)&ResourceElement.ItemValue.Type = 7;
    *(_QWORD *)&PackageSidElement.SchemaElementId = 5;
    *(_QWORD *)&PackageSidElement.ItemValue.Type = 12;
    PackageSidElement.ItemValue.ByteArray.pByteArray = 0;
    *(_QWORD *)&IdentityElement.SchemaElementId = 2;
    *(_QWORD *)&IdentityElement.ItemValue.Type = 7;
    IdentityElement.ItemValue.8 = 0u;
    VaultFindItems(hVault, &Vault_Schema_WebPassword, &ResourceElement, 0, 512, &nItems, &pItems);
    v9 = 0;
    v4 = nIndex;
    v10 = 0;
    if ( nItems )
    {
      do
      {
        v11 = v10;
        if ( IsWABSavedCredential(&pItems[v11]) )
        {
          if ( (pItems[v11].dwFlags & 0x800) == 0 )
          {
            ++v9;
            v12 = v10;
            if ( v9 != 1 )
              v12 = v7;
            v7 = v12;
            if ( !v8 && v4 && !_wcsicmp(v4, pItems[v11].pIdentityElement->ItemValue.String) )
            {
              v8 = 1;
              v27 = v10;
            }
          }
        }
        else
        {
          pItems[v11].dwFlags |= 0x800u;
        }
        ++v10;
      }
      while ( v10 < nItems );
      v38 = v8;
      if ( v9 )
      {
        memset(&varUserName, 0, sizeof(varUserName));
        memset(&varPassword, 0, sizeof(varPassword));
        psa = SafeArrayCreateVector(8u, 0, v9);
        Vector = SafeArrayCreateVector(8u, 0, v9);
        v14 = psa;
        v15 = Vector;
        if ( psa )
        {
          if ( Vector )
          {
            v16 = 0;
            LODWORD(nIndex) = 0;
            while ( v1 < nItems && v16 < v9 )
            {
              v17 = v1;
              if ( IsWABSavedCredential(&pItems[v17]) )
              {
                ATL::CComBSTR::CComBSTR(&bstrUser, pItems[v17].pIdentityElement->ItemValue.String);
                m_str = bstrUser.m_str;
                if ( SafeArrayPutElement(psa, (LONG *)&nIndex, bstrUser.m_str) < 0 )
                  goto LABEL_30;
                pLocalItem = 0;
                if ( (unsigned int)VaultGetItem(
                                     hVault,
                                     &Vault_Schema_WebPassword,
                                     pItems[v17].pResourceElement,
                                     pItems[v17].pIdentityElement,
                                     pItems[v17].pPackageSid,
                                     0,
                                     0,
                                     &pLocalItem) )
                  goto LABEL_30;
                String = &source;
                pAuthenticatorElement = pLocalItem->pAuthenticatorElement;
                if ( pAuthenticatorElement->ItemValue.String )
                  String = pAuthenticatorElement->ItemValue.String;
                ATL::CComBSTR::CComBSTR(&bstrPassword, String);
                VaultFree(pLocalItem);
                v21 = bstrPassword.m_str;
                if ( SafeArrayPutElement(v15, (LONG *)&nIndex, bstrPassword.m_str) < 0 )
                {
                  SysFreeString(v21);
LABEL_30:
                  SysFreeString(m_str);
                  goto LABEL_37;
                }
                LODWORD(nIndex) = (_DWORD)nIndex + 1;
                SysFreeString(v21);
                SysFreeString(m_str);
              }
              v16 = (unsigned int)nIndex;
              ++v1;
            }
            VariantInit(&varUserName);
            VariantInit(&varPassword);
            varUserName.vt = 8200;
            varPassword.vt = 8200;
            varUserName.llVal = (__int64)psa;
            varPassword.llVal = (__int64)v15;
            if ( v9 == 1 )
            {
              SetFormCredential(hVault, spAuthHost.ptr_, &pItems[v7], &varUserName, &varPassword);
            }
            else
            {
              v22 = v27;
              if ( !v38 )
                v22 = v7;
              SetFormCredential(hVault, spAuthHost.ptr_, &pItems[v22], &varUserName, &varPassword);
            }
LABEL_37:
            v14 = psa;
          }
          SafeArrayDestroy(v14);
        }
        if ( v15 )
          SafeArrayDestroy(v15);
      }
      v2 = (_GET_FORM_CREDENTIAL_PARAM *)pParam;
    }
  }
  VaultFree(pItems);
  if ( hVault )
    VaultCloseVault(&hVault);
  LocalFree(v4);
  FreeGetFormCredentialParam(v2);
  SysFreeString(0);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spAuthHost);
  return 0;
}

```

## disassembly

```asm
0x18001c980  mov     [rsp-8+arg_0], pParam
0x18001c985  push    rbp
0x18001c986  push    rbx
0x18001c987  push    rsi
0x18001c988  push    rdi
0x18001c989  push    r12
0x18001c98b  push    r13
0x18001c98d  push    r14
0x18001c98f  push    r15
0x18001c991  lea     rbp, [rsp-18h]
0x18001c996  sub     rsp, 118h
0x18001c99d  xor     r13d, r13d
0x18001c9a0  lea     r8, [rsp+150h+spAuthHost]; ppv
0x18001c9a5  xorps   xmm0, xmm0
0x18001c9a8  mov     [rsp+150h+spAuthHost.ptr_], r13
0x18001c9ad  xorps   xmm1, xmm1
0x18001c9b0  mov     [rsp+150h+hVault], r13
0x18001c9b5  mov     rbx, pParam
0x18001c9b8  mov     [rsp+150h+pItems], r13
0x18001c9bd  mov     pParam, [pParam]; pStm
0x18001c9c0  lea     rdx, _GUID_5de7918b_bfd7_4c1e_b4e0_b16d0a3ea76b; iid
0x18001c9c7  movups  xmmword ptr [rbp+50h+ResourceElement.SchemaElementId], xmm0
0x18001c9cb  mov     [rbp+50h+nItems], r13d
0x18001c9cf  mov     r14d, r13d
0x18001c9d2  movups  xmmword ptr [rbp+50h+ResourceElement.ItemValue.___u1], xmm0
0x18001c9d6  mov     [rbp+50h+nIndex], r13
0x18001c9da  movups  xmmword ptr [rbp+50h+IdentityElement.SchemaElementId], xmm1
0x18001c9de  movups  xmmword ptr [rbp+50h+IdentityElement.ItemValue.___u1], xmm1
0x18001c9e2  movups  xmmword ptr [rbp+50h+PackageSidElement.SchemaElementId], xmm0
0x18001c9e6  movups  xmmword ptr [rbp+50h+PackageSidElement.ItemValue.___u1], xmm0
0x18001c9ea  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x18001c9f0  mov     [rbx], r13
0x18001c9f3  test    eax, eax
0x18001c9f5  js      loc_18001CD94
0x18001c9fb  lea     r8, [rsp+150h+hVault]
0x18001ca00  xor     edx, edx
0x18001ca02  lea     pParam, Vault_DefaultVault_ID
0x18001ca09  call    cs:__imp_VaultOpenVault
0x18001ca0f  test    eax, eax
0x18001ca11  jnz     loc_18001CD94
0x18001ca17  mov     rdx, [rbx+8]; lpwszUrl
0x18001ca1b  mov     pParam, [rsp+150h+hVault]; hVault
0x18001ca20  call    ?CopyIECredentials@@YAKPEAXPEAG@Z; CopyIECredentials(void *,ushort *)
0x18001ca25  test    eax, eax
0x18001ca27  jnz     loc_18001CD94
0x18001ca2d  mov     pParam, [rbx+8]; lpwszUrl
0x18001ca31  lea     rdx, [rbp+50h+nIndex]; lpwszUserName
0x18001ca35  mov     esi, r13d
0x18001ca38  mov     [rsp+150h+var_F8], r13d
0x18001ca3d  mov     r12b, r13b
0x18001ca40  call    ?GetPreferredAccountForUrl@@YAKPEAGPEAPEAG@Z; GetPreferredAccountForUrl(ushort *,ushort * *)
0x18001ca45  mov     rax, [rbx+8]
0x18001ca49  lea     r8, [rbp+50h+ResourceElement]
0x18001ca4d  mov     pParam, [rsp+150h+hVault]
0x18001ca52  lea     rdx, Vault_Schema_WebPassword
0x18001ca59  mov     qword ptr [rbp+50h+ResourceElement.ItemValue.___u1], rax
0x18001ca5d  xor     r9d, r9d
0x18001ca60  lea     rax, ?gWABPackageSidBuffer@@3U_SID_BUFFER@@A; _SID_BUFFER gWABPackageSidBuffer
0x18001ca67  mov     qword ptr [rbp+50h+ResourceElement.SchemaElementId], 1
0x18001ca6f  mov     qword ptr [rbp+50h+PackageSidElement.ItemValue.___u1], rax
0x18001ca73  lea     rax, [rsp+150h+pItems]
0x18001ca78  mov     [rsp+150h+var_120], rax
0x18001ca7d  lea     rax, [rbp+50h+nItems]
0x18001ca81  mov     [rsp+150h+var_128], rax
0x18001ca86  mov     dword ptr [rsp+150h+pVar2], 200h
0x18001ca8e  mov     qword ptr [rbp+50h+ResourceElement.ItemValue.Type], 7
0x18001ca96  mov     qword ptr [rbp+50h+ResourceElement.ItemValue.___u1+8], r13
0x18001ca9a  mov     qword ptr [rbp+50h+PackageSidElement.SchemaElementId], 5
0x18001caa2  mov     qword ptr [rbp+50h+PackageSidElement.ItemValue.Type], 0Ch
0x18001caaa  mov     qword ptr [rbp+50h+PackageSidElement.ItemValue.___u1+8], r13
0x18001caae  mov     qword ptr [rbp+50h+IdentityElement.SchemaElementId], 2
0x18001cab6  mov     qword ptr [rbp+50h+IdentityElement.ItemValue.Type], 7
0x18001cabe  mov     qword ptr [rbp+50h+IdentityElement.ItemValue.___u1+8], r13
0x18001cac2  mov     qword ptr [rbp+50h+IdentityElement.ItemValue.___u1], r13
0x18001cac6  call    cs:__imp_VaultFindItems
0x18001cacc  mov     r15d, r13d
0x18001cacf  mov     r14, [rbp+50h+nIndex]
0x18001cad3  mov     edi, r13d
0x18001cad6  cmp     [rbp+50h+nItems], r13d
0x18001cada  jbe     loc_18001CD94
0x18001cae0  mov     pParam, [rsp+150h+pItems]
0x18001cae5  mov     eax, edi
0x18001cae7  lea     rbx, [rax+rax*4]
0x18001caeb  shl     rbx, 4
0x18001caef  add     pParam, rbx; pItem
0x18001caf2  call    ?IsWABSavedCredential@@YAEPEAU_VAULT_ITEM@@@Z; IsWABSavedCredential(_VAULT_ITEM *)
0x18001caf7  test    al, al
0x18001caf9  jnz     short loc_18001CB08
0x18001cafb  mov     rax, [rsp+150h+pItems]
0x18001cb00  bts     dword ptr [rbx+rax+40h], 0Bh
0x18001cb06  jmp     short loc_18001CB4C
0x18001cb08  mov     rdx, [rsp+150h+pItems]
0x18001cb0d  test    dword ptr [rbx+rdx+40h], 800h
0x18001cb15  jnz     short loc_18001CB4C
0x18001cb17  inc     r15d
0x18001cb1a  mov     eax, edi
0x18001cb1c  cmp     r15d, 1
0x18001cb20  cmovnz  eax, esi
0x18001cb23  mov     esi, eax
0x18001cb25  test    r12b, r12b
0x18001cb28  jnz     short loc_18001CB4C
0x18001cb2a  test    r14, r14
0x18001cb2d  jz      short loc_18001CB4C
0x18001cb2f  mov     rdx, [rbx+rdx+20h]
0x18001cb34  mov     pParam, r14; String1
0x18001cb37  mov     rdx, [rdx+10h]; String2
0x18001cb3b  call    cs:__imp__wcsicmp
0x18001cb41  test    eax, eax
0x18001cb43  jnz     short loc_18001CB4C
0x18001cb45  mov     r12b, 1
0x18001cb48  mov     [rsp+150h+var_F8], edi
0x18001cb4c  inc     edi
0x18001cb4e  cmp     edi, [rbp+50h+nItems]
0x18001cb51  jb      short loc_18001CAE0
0x18001cb53  mov     [rbp+50h+arg_8], r12b
0x18001cb57  test    r15d, r15d
0x18001cb5a  jz      loc_18001CD90
0x18001cb60  xor     eax, eax
0x18001cb62  xorps   xmm0, xmm0
0x18001cb65  xorps   xmm1, xmm1
0x18001cb68  mov     [rbp+50h+varUserName.pRecInfo], rax
0x18001cb6c  mov     r8d, r15d; cElements
0x18001cb6f  mov     [rbp+50h+varPassword.pRecInfo], rax
0x18001cb73  xor     edx, edx; lLbound
0x18001cb75  lea     ebx, [rax+8]
0x18001cb78  mov     ecx, ebx; vt
0x18001cb7a  movups  xmmword ptr [rbp+50h+varUserName.___u0], xmm0
0x18001cb7e  movups  xmmword ptr [rsp+150h+varPassword.___u0], xmm1
0x18001cb83  call    cs:__imp_SafeArrayCreateVector
0x18001cb89  mov     ecx, ebx; vt
0x18001cb8b  mov     r8d, r15d; cElements
0x18001cb8e  xor     edx, edx; lLbound
0x18001cb90  mov     [rsp+150h+psa], rax
0x18001cb95  call    cs:__imp_SafeArrayCreateVector
0x18001cb9b  mov     pParam, [rsp+150h+psa]
0x18001cba0  mov     r12, rax
0x18001cba3  test    pParam, pParam
0x18001cba6  jz      loc_18001CD82
0x18001cbac  test    rax, rax
0x18001cbaf  jz      $Cleanup_9
0x18001cbb5  xor     ecx, ecx
0x18001cbb7  mov     dword ptr [rbp+50h+nIndex], ecx
0x18001cbba  cmp     r13d, [rbp+50h+nItems]
0x18001cbbe  jnb     loc_18001CCE8
0x18001cbc4  cmp     ecx, r15d
0x18001cbc7  jnb     loc_18001CCE8
0x18001cbcd  mov     pParam, [rsp+150h+pItems]
0x18001cbd2  mov     eax, r13d
0x18001cbd5  lea     rdi, [rax+rax*4]
0x18001cbd9  shl     rdi, 4
0x18001cbdd  add     pParam, rdi; pItem
0x18001cbe0  call    ?IsWABSavedCredential@@YAEPEAU_VAULT_ITEM@@@Z; IsWABSavedCredential(_VAULT_ITEM *)
0x18001cbe5  test    al, al
0x18001cbe7  jz      loc_18001CCC6
0x18001cbed  mov     rax, [rsp+150h+pItems]
0x18001cbf2  lea     pParam, [rbp+50h+bstrUser]; this
0x18001cbf6  mov     rdx, [rdi+rax+20h]
0x18001cbfb  mov     rdx, [rdx+10h]; pSrc
0x18001cbff  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18001cc04  mov     rbx, [rbp+50h+bstrUser.m_str]
0x18001cc08  lea     rdx, [rbp+50h+nIndex]; rgIndices
0x18001cc0c  mov     pParam, [rsp+150h+psa]; psa
0x18001cc11  mov     r8, rbx; pv
0x18001cc14  call    cs:__imp_SafeArrayPutElement
0x18001cc1a  xor     ecx, ecx
0x18001cc1c  test    eax, eax
0x18001cc1e  js      loc_18001CCD7
0x18001cc24  mov     r8, [rsp+150h+pItems]
0x18001cc29  lea     rax, [rsp+150h+pLocalItem]
0x18001cc2e  mov     [rsp+150h+var_118], rax
0x18001cc33  lea     rdx, Vault_Schema_WebPassword
0x18001cc3a  mov     [rsp+150h+pLocalItem], pParam
0x18001cc3f  mov     dword ptr [rsp+150h+var_120], ecx
0x18001cc43  mov     rax, [rdi+r8+30h]
0x18001cc48  mov     r9, [rdi+r8+20h]
0x18001cc4d  mov     r8, [rdi+r8+18h]
0x18001cc52  mov     [rsp+150h+var_128], pParam
0x18001cc57  mov     pParam, [rsp+150h+hVault]
0x18001cc5c  mov     [rsp+150h+pVar2], rax
0x18001cc61  call    cs:__imp_VaultGetItem
0x18001cc67  test    eax, eax
0x18001cc69  jnz     short loc_18001CCD7
0x18001cc6b  mov     rax, [rsp+150h+pLocalItem]
0x18001cc70  lea     rdx, source
0x18001cc77  mov     pParam, [rax+28h]
0x18001cc7b  cmp     qword ptr [pParam+10h], 0
0x18001cc80  cmovnz  rdx, [pParam+10h]; pSrc
0x18001cc85  lea     pParam, [rbp+50h+bstrPassword]; this
0x18001cc89  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18001cc8e  mov     pParam, [rsp+150h+pLocalItem]
0x18001cc93  call    cs:__imp_VaultFree
0x18001cc99  mov     rdi, [rbp+50h+bstrPassword.m_str]
0x18001cc9d  lea     rdx, [rbp+50h+nIndex]; rgIndices
0x18001cca1  mov     r8, rdi; pv
0x18001cca4  mov     pParam, r12; psa
0x18001cca7  call    cs:__imp_SafeArrayPutElement
0x18001ccad  mov     pParam, rdi; bstrString
0x18001ccb0  test    eax, eax
0x18001ccb2  js      short loc_18001CCD1
0x18001ccb4  inc     dword ptr [rbp+50h+nIndex]
0x18001ccb7  call    cs:__imp_SysFreeString
0x18001ccbd  mov     pParam, rbx; bstrString
0x18001ccc0  call    cs:__imp_SysFreeString
0x18001ccc6  mov     ecx, dword ptr [rbp+50h+nIndex]
0x18001ccc9  inc     r13d
0x18001cccc  jmp     loc_18001CBBA
0x18001ccd1  call    cs:__imp_SysFreeString
0x18001ccd7  mov     pParam, rbx; bstrString
0x18001ccda  call    cs:__imp_SysFreeString
0x18001cce0  xor     r13d, r13d
0x18001cce3  jmp     loc_18001CD77
0x18001cce8  lea     pParam, [rbp+50h+varUserName]; pvarg
0x18001ccec  call    cs:__imp_VariantInit
0x18001ccf2  lea     pParam, [rsp+150h+varPassword]; pvarg
0x18001ccf7  call    cs:__imp_VariantInit
0x18001ccfd  mov     rdx, [rsp+150h+spAuthHost.ptr_]; pAuthHost
0x18001cd02  mov     eax, 2008h
0x18001cd07  mov     pParam, [rsp+150h+hVault]; hVault
0x18001cd0c  lea     r9, [rbp+50h+varUserName]; pVar1
0x18001cd10  mov     word ptr [rbp+50h+varUserName.___u0], ax
0x18001cd14  mov     word ptr [rsp+150h+varPassword.___u0], ax
0x18001cd19  mov     rax, [rsp+150h+psa]
0x18001cd1e  mov     qword ptr [rbp+50h+varUserName.___u0+8], rax
0x18001cd22  mov     qword ptr [rsp+150h+varPassword.___u0+8], r12
0x18001cd27  cmp     r15d, 1
0x18001cd2b  jnz     short loc_18001CD4D
0x18001cd2d  mov     eax, esi
0x18001cd2f  lea     r8, [rax+rax*4]
0x18001cd33  shl     r8, 4
0x18001cd37  lea     rax, [rsp+150h+varPassword]
0x18001cd3c  add     r8, [rsp+150h+pItems]; pItem
0x18001cd41  mov     [rsp+150h+pVar2], rax; pVar2
0x18001cd46  call    ?SetFormCredential@@YAJPEAXPEAUIAuthHost@@PEAU_VAULT_ITEM@@PEAUtagVARIANT@@3@Z; SetFormCredential(void *,IAuthHost *,_VAULT_ITEM *,tagVARIANT *,tagVARIANT *)
0x18001cd4b  jmp     short loc_18001CCE0
0x18001cd4d  mov     ebx, [rsp+150h+var_F8]
0x18001cd51  lea     rax, [rsp+150h+varPassword]
0x18001cd56  xor     r13d, r13d
0x18001cd59  mov     [rsp+150h+pVar2], rax; pVar2
0x18001cd5e  cmp     [rbp+50h+arg_8], r13b
0x18001cd62  cmovz   ebx, esi
0x18001cd65  lea     r8, [rbx+rbx*4]
0x18001cd69  shl     r8, 4
0x18001cd6d  add     r8, [rsp+150h+pItems]; pItem
0x18001cd72  call    ?SetFormCredential@@YAJPEAXPEAUIAuthHost@@PEAU_VAULT_ITEM@@PEAUtagVARIANT@@3@Z; SetFormCredential(void *,IAuthHost *,_VAULT_ITEM *,tagVARIANT *,tagVARIANT *)
0x18001cd77  mov     pParam, [rsp+150h+psa]; psa
0x18001cd7c  call    cs:__imp_SafeArrayDestroy
0x18001cd82  test    r12, r12
0x18001cd85  jz      short loc_18001CD90
0x18001cd87  mov     pParam, r12; psa
0x18001cd8a  call    cs:__imp_SafeArrayDestroy
0x18001cd90  mov     rbx, [rbp+50h+arg_0]
0x18001cd94  mov     pParam, [rsp+150h+pItems]
0x18001cd99  call    cs:__imp_VaultFree
0x18001cd9f  cmp     [rsp+150h+hVault], r13
0x18001cda4  jz      short loc_18001CDB1
0x18001cda6  lea     pParam, [rsp+150h+hVault]
0x18001cdab  call    cs:__imp_VaultCloseVault
0x18001cdb1  mov     pParam, r14; hMem
0x18001cdb4  call    cs:__imp_LocalFree
0x18001cdba  mov     pParam, rbx; pParam
0x18001cdbd  call    ?FreeGetFormCredentialParam@@YAXPEAU_GET_FORM_CREDENTIAL_PARAM@@@Z; FreeGetFormCredentialParam(_GET_FORM_CREDENTIAL_PARAM *)
0x18001cdc2  xor     ecx, ecx; bstrString
0x18001cdc4  call    cs:__imp_SysFreeString
0x18001cdca  lea     pParam, [rsp+150h+spAuthHost]; this
0x18001cdcf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001cdd4  xor     eax, eax
0x18001cdd6  add     rsp, 118h
0x18001cddd  pop     r15
0x18001cddf  pop     r14
0x18001cde1  pop     r13
0x18001cde3  pop     r12
0x18001cde5  pop     rdi
0x18001cde6  pop     rsi
0x18001cde7  pop     rbx
0x18001cde8  pop     rbp
0x18001cde9  retn
```
