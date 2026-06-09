# CDBFolder::_GetInFolderDisplayName(_ITEMID_CHILD const *,int,ushort * *)

- ea: `0x180007a00`
- end: `0x180007c5e`
- name: `?_GetInFolderDisplayName@CDBFolder@@AEAAJPEFBU_ITEMID_CHILD@@HPEAPEAG@Z`
- size: `606`
- prototype: `int(CDBFolder *__hidden this, const struct _ITEMID_CHILD *, int, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18005b4ec`
- `0x18005c2b0`
- `0x180086c40`

## callees

- `0x180007a00`
- `0x180008aa0`
- `0x18000a730`
- `0x18006d260`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007bb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007bb4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007bbe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007bdd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007bbe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007bdd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x180007b1f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x180007b29`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x180007b1f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x180007b29`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x180007b3f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x180007b3f`
- `PROPSYS!PropVariantToBSTR` at `0x180007ab6`
- `PROPSYS!PropVariantToBSTR` at `0x180007b0b`
- `PROPSYS!PropVariantToBSTR` at `0x180007c1c`
- `PROPSYS!PropVariantToBSTR` at `0x180007c42`
- `PROPSYS!PropVariantToBSTR` at `0x180007ab6`
- `PROPSYS!PropVariantToBSTR` at `0x180007b0b`
- `PROPSYS!PropVariantToBSTR` at `0x180007c1c`
- `PROPSYS!PropVariantToBSTR` at `0x180007c42`
- `PROPSYS!PSFormatForDisplayAlloc` at `0x180007b77`
- `PROPSYS!PSFormatForDisplayAlloc` at `0x180007b77`
- `OLEAUT32!__imp_SysAllocString` at `0x180007b95`
- `OLEAUT32!__imp_SysAllocString` at `0x180007b95`
- `OLEAUT32!__imp_SysFreeString` at `0x180007bc8`
- `OLEAUT32!__imp_SysFreeString` at `0x180007bd3`
- `OLEAUT32!__imp_SysFreeString` at `0x180007bc8`
- `OLEAUT32!__imp_SysFreeString` at `0x180007bd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDBFolder::_GetInFolderDisplayName(
        CDBFolder *this,
        const struct _ITEMID_CHILD *a2,
        int a3,
        unsigned __int16 **a4)
{
  char *v7; // r15
  char *v8; // rcx
  HRESULT PropertyForItem; // ebx
  PROPDESC_FORMAT_FLAGS v10; // r8d
  PROPVARIANT *v11; // rdx
  const OLECHAR *v12; // rcx
  unsigned __int16 *v13; // rax
  PROPVARIANT *v14; // rcx
  BSTR pszPath; // [rsp+30h] [rbp-40h] BYREF
  BSTR pbstrOut; // [rsp+38h] [rbp-38h] BYREF
  PROPVARIANT propvar[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v19; // [rsp+50h] [rbp-20h]
  PROPVARIANT pvar[2]; // [rsp+58h] [rbp-18h] BYREF
  __int64 v21; // [rsp+68h] [rbp-8h]
  unsigned int v22; // [rsp+B0h] [rbp+40h] BYREF
  PWSTR ppszDisplay; // [rsp+B8h] [rbp+48h] BYREF

  *a4 = 0;
  v7 = (char *)this + 184;
  v8 = (char *)this + 184;
  if ( a3 )
  {
    *(_OWORD *)pvar = 0;
    v21 = 0;
    PropertyForItem = CDBFolder::GetPropertyForItem(v8, a2, &PKEY_ItemNameDisplay, 0, pvar);
    if ( PropertyForItem < 0 )
      return (unsigned int)PropertyForItem;
    PropertyForItem = PropVariantToBSTR(pvar, a4);
    v14 = pvar;
    goto LABEL_22;
  }
  *(_OWORD *)propvar = 0;
  v19 = 0;
  PropertyForItem = CDBFolder::GetPropertyForItem(v8, a2, &PKEY_ItemNameDisplay, 0, propvar);
  if ( PropertyForItem >= 0 )
  {
    v22 = 0;
    if ( CDBFolder::_AttributesForOneItem(this, a2, 0x60400000u, &v22) < 0
      || (v22 & 0x40000000) == 0
      || (v22 & 0x20400000) == 0x20000000 )
    {
      PropertyForItem = PropVariantToBSTR(propvar, a4);
    }
    else
    {
      pbstrOut = 0;
      PropertyForItem = PropVariantToBSTR(propvar, &pbstrOut);
      if ( PropertyForItem >= 0 )
      {
        *(_OWORD *)pvar = 0;
        v21 = 0;
        PropertyForItem = CDBFolder::GetPropertyForItem(v7, a2, &PKEY_ParsingName, 0, pvar);
        if ( PropertyForItem >= 0 )
        {
          pszPath = 0;
          PropertyForItem = PropVariantToBSTR(pvar, &pszPath);
          if ( PropertyForItem >= 0 )
          {
            PathRemoveExtensionW(pszPath);
            PathRemoveExtensionW(pbstrOut);
            ppszDisplay = 0;
            if ( StrCmpW(pszPath, pbstrOut) )
            {
              if ( ppszDisplay )
                wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(ppszDisplay);
              v10 = PDFF_DEFAULT;
              v11 = propvar;
            }
            else
            {
              if ( ppszDisplay )
                wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(ppszDisplay);
              v10 = PDFF_FILENAME;
              v11 = pvar;
            }
            ppszDisplay = 0;
            PropertyForItem = PSFormatForDisplayAlloc(&PKEY_ItemNameDisplay, v11, v10, &ppszDisplay);
            if ( PropertyForItem >= 0 )
            {
              v12 = &pszFormat;
              if ( ppszDisplay )
                v12 = ppszDisplay;
              v13 = SysAllocString(v12);
              *a4 = v13;
              PropertyForItem = v13 == 0 ? 0x8007000E : 0;
            }
            if ( ppszDisplay )
              CoTaskMemFree(ppszDisplay);
          }
          PropVariantClear(pvar);
          SysFreeString(pszPath);
        }
      }
      SysFreeString(pbstrOut);
    }
    v14 = propvar;
LABEL_22:
    PropVariantClear(v14);
  }
  return (unsigned int)PropertyForItem;
}

```

## disassembly

```asm
0x180007a00  mov     [rsp-28h+arg_0], rbx
0x180007a05  push    rbp
0x180007a06  push    rsi
0x180007a07  push    rdi
0x180007a08  push    r14
0x180007a0a  push    r15
0x180007a0c  mov     rbp, rsp
0x180007a0f  sub     rsp, 70h
0x180007a13  mov     rdi, r9
0x180007a16  mov     rsi, rdx
0x180007a19  mov     r14, rcx
0x180007a1c  mov     qword ptr [r9], 0
0x180007a23  lea     r15, [rcx+0B8h]
0x180007a2a  xorps   xmm0, xmm0
0x180007a2d  xor     eax, eax
0x180007a2f  xor     r9d, r9d
0x180007a32  mov     rcx, r15
0x180007a35  test    r8d, r8d
0x180007a38  lea     r8, PKEY_ItemNameDisplay
0x180007a3f  jnz     loc_180007BF9
0x180007a45  movups  xmmword ptr [rbp+propvar], xmm0
0x180007a49  mov     [rbp+var_20], rax
0x180007a4d  lea     rax, [rbp+propvar]
0x180007a51  mov     [rsp+70h+var_50], rax
0x180007a56  call    ?GetPropertyForItem@CDBFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@W4PROPERTY_GET_TYPE@@PEAUtagPROPVARIANT@@@Z; CDBFolder::GetPropertyForItem(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,PROPERTY_GET_TYPE,tagPROPVARIANT *)
0x180007a5b  mov     ebx, eax
0x180007a5d  test    eax, eax
0x180007a5f  js      loc_180007BE3
0x180007a65  mov     [rbp+arg_10], 0
0x180007a6c  lea     r9, [rbp+arg_10]; unsigned int *
0x180007a70  mov     r8d, 60400000h; unsigned int
0x180007a76  mov     rdx, rsi; struct _ITEMID_CHILD *
0x180007a79  mov     rcx, r14; this
0x180007a7c  call    ?_AttributesForOneItem@CDBFolder@@AEAAJPEFBU_ITEMID_CHILD@@KPEAK@Z; CDBFolder::_AttributesForOneItem(_ITEMID_CHILD const *,ulong,ulong *)
0x180007a81  test    eax, eax
0x180007a83  js      loc_180007C3B
0x180007a89  mov     eax, [rbp+arg_10]
0x180007a8c  bt      eax, 1Eh
0x180007a90  jnb     loc_180007C3B
0x180007a96  and     eax, 20400000h
0x180007a9b  cmp     eax, 20000000h
0x180007aa0  jz      loc_180007C3B
0x180007aa6  mov     [rbp+pbstrOut], 0
0x180007aae  lea     rdx, [rbp+pbstrOut]; pbstrOut
0x180007ab2  lea     rcx, [rbp+propvar]; propvar
0x180007ab6  call    cs:__imp_PropVariantToBSTR
0x180007abc  mov     ebx, eax
0x180007abe  test    eax, eax
0x180007ac0  js      loc_180007BCF
0x180007ac6  xorps   xmm0, xmm0
0x180007ac9  xor     eax, eax
0x180007acb  movups  xmmword ptr [rbp+pvar], xmm0
0x180007acf  mov     [rbp+var_8], rax
0x180007ad3  lea     rax, [rbp+pvar]
0x180007ad7  mov     [rsp+70h+var_50], rax
0x180007adc  xor     r9d, r9d
0x180007adf  lea     r8, PKEY_ParsingName
0x180007ae6  mov     rdx, rsi
0x180007ae9  mov     rcx, r15
0x180007aec  call    ?GetPropertyForItem@CDBFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@W4PROPERTY_GET_TYPE@@PEAUtagPROPVARIANT@@@Z; CDBFolder::GetPropertyForItem(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,PROPERTY_GET_TYPE,tagPROPVARIANT *)
0x180007af1  mov     ebx, eax
0x180007af3  test    eax, eax
0x180007af5  js      loc_180007BCF
0x180007afb  mov     [rbp+pszPath], 0
0x180007b03  lea     rdx, [rbp+pszPath]; pbstrOut
0x180007b07  lea     rcx, [rbp+pvar]; propvar
0x180007b0b  call    cs:__imp_PropVariantToBSTR
0x180007b11  mov     ebx, eax
0x180007b13  test    eax, eax
0x180007b15  js      loc_180007BBA
0x180007b1b  mov     rcx, [rbp+pszPath]; pszPath
0x180007b1f  call    cs:__imp_PathRemoveExtensionW
0x180007b25  mov     rcx, [rbp+pbstrOut]; pszPath
0x180007b29  call    cs:__imp_PathRemoveExtensionW
0x180007b2f  mov     [rbp+ppszDisplay], 0
0x180007b37  mov     rdx, [rbp+pbstrOut]; psz2
0x180007b3b  mov     rcx, [rbp+pszPath]; psz1
0x180007b3f  call    cs:__imp_StrCmpW
0x180007b45  mov     rcx, [rbp+ppszDisplay]; pv
0x180007b49  test    eax, eax
0x180007b4b  jnz     loc_180007C2A
0x180007b51  test    rcx, rcx
0x180007b54  jnz     loc_180007C4C
0x180007b5a  mov     r8d, 2; pdff
0x180007b60  lea     rdx, [rbp+pvar]; propvar
0x180007b64  mov     [rbp+ppszDisplay], 0
0x180007b6c  lea     r9, [rbp+ppszDisplay]; ppszDisplay
0x180007b70  lea     rcx, PKEY_ItemNameDisplay; key
0x180007b77  call    cs:__imp_PSFormatForDisplayAlloc
0x180007b7d  mov     ebx, eax
0x180007b7f  test    eax, eax
0x180007b81  js      short loc_180007BAB
0x180007b83  mov     rax, [rbp+ppszDisplay]
0x180007b87  lea     rcx, pszFormat
0x180007b8e  test    rax, rax
0x180007b91  cmovnz  rcx, rax; psz
0x180007b95  call    cs:__imp_SysAllocString
0x180007b9b  mov     [rdi], rax
0x180007b9e  neg     rax
0x180007ba1  sbb     ebx, ebx
0x180007ba3  not     ebx
0x180007ba5  and     ebx, 8007000Eh
0x180007bab  mov     rcx, [rbp+ppszDisplay]; pv
0x180007baf  test    rcx, rcx
0x180007bb2  jz      short loc_180007BBA
0x180007bb4  call    cs:__imp_CoTaskMemFree
0x180007bba  lea     rcx, [rbp+pvar]; pvar
0x180007bbe  call    cs:__imp_PropVariantClear
0x180007bc4  mov     rcx, [rbp+pszPath]; bstrString
0x180007bc8  call    cs:__imp_SysFreeString
0x180007bce  nop
0x180007bcf  mov     rcx, [rbp+pbstrOut]; bstrString
0x180007bd3  call    cs:__imp_SysFreeString
0x180007bd9  lea     rcx, [rbp+propvar]; pvar
0x180007bdd  call    cs:__imp_PropVariantClear
0x180007be3  mov     eax, ebx
0x180007be5  mov     rbx, [rsp+70h+arg_0]
0x180007bed  add     rsp, 70h
0x180007bf1  pop     r15
0x180007bf3  pop     r14
0x180007bf5  pop     rdi
0x180007bf6  pop     rsi
0x180007bf7  pop     rbp
0x180007bf8  retn
0x180007bf9  movups  xmmword ptr [rbp+pvar], xmm0
0x180007bfd  mov     [rbp+var_8], rax
0x180007c01  lea     rax, [rbp+pvar]
0x180007c05  mov     [rsp+70h+var_50], rax
0x180007c0a  call    ?GetPropertyForItem@CDBFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@W4PROPERTY_GET_TYPE@@PEAUtagPROPVARIANT@@@Z; CDBFolder::GetPropertyForItem(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,PROPERTY_GET_TYPE,tagPROPVARIANT *)
0x180007c0f  mov     ebx, eax
0x180007c11  test    eax, eax
0x180007c13  js      short loc_180007BE3
0x180007c15  mov     rdx, rdi; pbstrOut
0x180007c18  lea     rcx, [rbp+pvar]; propvar
0x180007c1c  call    cs:__imp_PropVariantToBSTR
0x180007c22  mov     ebx, eax
0x180007c24  lea     rcx, [rbp+pvar]
0x180007c28  jmp     short loc_180007BDD
0x180007c2a  test    rcx, rcx
0x180007c2d  jnz     short loc_180007C56
0x180007c2f  xor     r8d, r8d
0x180007c32  lea     rdx, [rbp+propvar]
0x180007c36  jmp     loc_180007B64
0x180007c3b  mov     rdx, rdi; pbstrOut
0x180007c3e  lea     rcx, [rbp+propvar]; propvar
0x180007c42  call    cs:__imp_PropVariantToBSTR
0x180007c48  mov     ebx, eax
0x180007c4a  jmp     short loc_180007BD9
0x180007c4c  call    ?close_reset@?$close_invoke_helper@$00P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZPEAG@details@wil@@SAXPEAG@Z; wil::details::close_invoke_helper<1,void (*)(void *),&CoTaskMemFree(void *),ushort *>::close_reset(ushort *)
0x180007c51  jmp     loc_180007B5A
0x180007c56  call    ?close_reset@?$close_invoke_helper@$00P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZPEAG@details@wil@@SAXPEAG@Z; wil::details::close_invoke_helper<1,void (*)(void *),&CoTaskMemFree(void *),ushort *>::close_reset(ushort *)
0x180007c5b  jmp     short loc_180007C2F
```
