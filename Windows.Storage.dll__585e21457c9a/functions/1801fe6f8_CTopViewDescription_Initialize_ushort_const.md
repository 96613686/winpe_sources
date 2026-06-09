# CTopViewDescription::Initialize(ushort const *)

- ea: `0x1801fe6f8`
- end: `0x1801fe9e9`
- name: `?Initialize@CTopViewDescription@@QEAAJPEBG@Z`
- size: `753`
- prototype: `__int64 __fastcall(CTopViewDescription *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1801fe4ec`

## callees

- `0x1801fe6f8`
- `0x1801fea9c`
- `0x1801fec38`
- `0x180354104`
- `0x1803a4cb0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801fe9b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801fe9b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801fe734`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801fe734`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1801fe7bf`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1801fe7bf`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x1801fe89f`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x1801fe89f`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1801fe786`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1801fe869`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1801fe8bb`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1801fe8ef`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1801fe786`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1801fe869`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1801fe8bb`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1801fe8ef`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fe7a9`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fe7d8`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fe7f1`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fe807`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fe820`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fe839`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fe920`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fe7a9`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fe7d8`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fe7f1`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fe807`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fe820`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fe839`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fe920`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1801fe84f`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1801fe84f`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801fe960`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801fe982`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801fe99b`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801fe960`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801fe982`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801fe99b`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x1801fe87f`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x1801fe8d3`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x1801fe907`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x1801fe87f`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x1801fe8d3`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x1801fe907`

## pseudocode

```c
__int64 __fastcall CTopViewDescription::Initialize(CTopViewDescription *this, const unsigned __int16 *a2)
{
  const struct _GUID *v4; // r9
  HRESULT PropertyBag; // edi
  IPropertyBag *v6; // rcx
  IPropertyBag *v7; // rcx
  char IsEnabled; // al
  IPropertyBag *v9; // rcx
  PWSTR *v10; // r8
  IPropertyBag *propBag; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR value[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszName[264]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR v15[264]; // [rsp+460h] [rbp+360h] BYREF

  AcquireSRWLockExclusive((PSRWLOCK)this + 4);
  propBag = 0;
  PropertyBag = CTopViewDescription::_GetPropertyBag(this, a2, 0, v4, (void **)&propBag);
  if ( PropertyBag >= 0 )
  {
    v6 = propBag;
    *((_WORD *)this + 56) = 0;
    PropertyBag = PSPropertyBag_ReadStr(v6, L"Name", (LPWSTR)this + 56, 260);
    if ( PropertyBag < 0 )
    {
LABEL_16:
      ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
      goto LABEL_17;
    }
    PSPropertyBag_ReadDWORD(propBag, L"Version", (DWORD *)this + 158);
    SHLoadIndirectString((PCWSTR)this + 56, (PWSTR)this + 318, 0x104u, 0);
    PSPropertyBag_ReadDWORD(propBag, L"LogicalViewMode", (DWORD *)this + 289);
    PSPropertyBag_ReadDWORD(propBag, L"IconSize", (DWORD *)this + 290);
    PSPropertyBag_ReadDWORD(propBag, L"QueryType", (DWORD *)this + 26);
    PSPropertyBag_ReadDWORD(propBag, L"HideFileNames", (DWORD *)this + 312);
    PSPropertyBag_ReadDWORD(propBag, L"DateCategorizerInfo", (DWORD *)this + 311);
    PSPropertyBag_ReadGUID(propBag, L"ChildViewID", (GUID *)((char *)this + 88));
    if ( PSPropertyBag_ReadStr(propBag, L"GroupBy", value, 260) >= 0 )
      PSGetPropertyKeyFromName(value, (PROPERTYKEY *)((char *)this + 1164));
    v7 = propBag;
    *((_DWORD *)this + 296) = 1;
    PSPropertyBag_ReadBOOL(v7, L"GroupAscending", (BOOL *)this + 296);
    if ( PSPropertyBag_ReadStr(propBag, L"StackBy", pszName, 260) >= 0 )
      PSGetPropertyKeyFromName(pszName, (PROPERTYKEY *)((char *)this + 1224));
    if ( PSPropertyBag_ReadStr(propBag, L"PrimaryProperty", v15, 260) >= 0 )
      PSGetPropertyKeyFromName(v15, (PROPERTYKEY *)((char *)this + 1252));
    PSPropertyBag_ReadDWORD(propBag, L"PrimarySettings", (DWORD *)this + 318);
    if ( CTopViewDescription::_InitializeColumnListWithEncryptionOwners(this, a2, propBag) < 0 )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_53797701>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_53797701>::GetImpl'::`2'::impl);
      v9 = propBag;
      if ( !IsEnabled )
      {
        v10 = (PWSTR *)((char *)this + 1192);
        goto LABEL_14;
      }
      if ( PSPropertyBag_ReadStrAlloc(propBag, L"ColumnList_53797701", (PWSTR *)this + 149) < 0 )
      {
        v9 = propBag;
        v10 = (PWSTR *)((char *)this + 1192);
LABEL_14:
        PSPropertyBag_ReadStrAlloc(v9, L"ColumnList", v10);
      }
    }
    PSPropertyBag_ReadStrAlloc(propBag, L"SortByList", (PWSTR *)this + 150);
    goto LABEL_16;
  }
LABEL_17:
  ReleaseSRWLockExclusive((PSRWLOCK)this + 4);
  return (unsigned int)PropertyBag;
}

```

## disassembly

```asm
0x1801fe6f8  mov     [rsp-8+arg_10], rbx
0x1801fe6fd  mov     [rsp-8+arg_18], rsi
0x1801fe702  push    rbp
0x1801fe703  push    rdi
0x1801fe704  push    r12
0x1801fe706  push    r14
0x1801fe708  push    r15
0x1801fe70a  lea     rbp, [rsp-580h]
0x1801fe712  sub     rsp, 680h
0x1801fe719  mov     rax, cs:__security_cookie
0x1801fe720  xor     rax, rsp
0x1801fe723  mov     [rbp+5A0h+var_30], rax
0x1801fe72a  mov     rbx, rcx
0x1801fe72d  mov     r15, rdx
0x1801fe730  add     rcx, 20h ; ' '; SRWLock
0x1801fe734  call    cs:__imp_AcquireSRWLockExclusive
0x1801fe73a  lea     rax, [rsp+6A0h+propBag]
0x1801fe73f  mov     [rsp+6A0h+propBag], 0
0x1801fe748  xor     r8d, r8d; unsigned int
0x1801fe74b  mov     [rsp+6A0h+var_680], rax; void **
0x1801fe750  mov     rdx, r15; unsigned __int16 *
0x1801fe753  mov     rcx, rbx; this
0x1801fe756  call    ?_GetPropertyBag@CTopViewDescription@@AEAAJPEBGKAEBU_GUID@@PEAPEAX@Z; CTopViewDescription::_GetPropertyBag(ushort const *,ulong,_GUID const &,void * *)
0x1801fe75b  mov     edi, eax
0x1801fe75d  test    eax, eax
0x1801fe75f  js      loc_1801FE9B2
0x1801fe765  mov     rcx, [rsp+6A0h+propBag]; propBag
0x1801fe76a  lea     rsi, [rbx+70h]
0x1801fe76e  xor     eax, eax
0x1801fe770  lea     rdx, aName; "Name"
0x1801fe777  mov     r12d, 104h
0x1801fe77d  mov     [rsi], ax
0x1801fe780  mov     r9d, r12d; characterCount
0x1801fe783  mov     r8, rsi; value
0x1801fe786  call    cs:__imp_PSPropertyBag_ReadStr
0x1801fe78c  mov     edi, eax
0x1801fe78e  test    eax, eax
0x1801fe790  js      loc_1801FE9A1
0x1801fe796  mov     rcx, [rsp+6A0h+propBag]; propBag
0x1801fe79b  lea     r8, [rbx+278h]; value
0x1801fe7a2  lea     rdx, aVersion_0; "Version"
0x1801fe7a9  call    cs:__imp_PSPropertyBag_ReadDWORD
0x1801fe7af  lea     rdx, [rbx+27Ch]; pszOutBuf
0x1801fe7b6  xor     r9d, r9d; ppvReserved
0x1801fe7b9  mov     r8d, r12d; cchOutBuf
0x1801fe7bc  mov     rcx, rsi; pszSource
0x1801fe7bf  call    cs:__imp_SHLoadIndirectString
0x1801fe7c5  mov     rcx, [rsp+6A0h+propBag]; propBag
0x1801fe7ca  lea     r8, [rbx+484h]; value
0x1801fe7d1  lea     rdx, aLogicalviewmod; "LogicalViewMode"
0x1801fe7d8  call    cs:__imp_PSPropertyBag_ReadDWORD
0x1801fe7de  mov     rcx, [rsp+6A0h+propBag]; propBag
0x1801fe7e3  lea     r8, [rbx+488h]; value
0x1801fe7ea  lea     rdx, aIconsize; "IconSize"
0x1801fe7f1  call    cs:__imp_PSPropertyBag_ReadDWORD
0x1801fe7f7  mov     rcx, [rsp+6A0h+propBag]; propBag
0x1801fe7fc  lea     r8, [rbx+68h]; value
0x1801fe800  lea     rdx, aQuerytype; "QueryType"
0x1801fe807  call    cs:__imp_PSPropertyBag_ReadDWORD
0x1801fe80d  mov     rcx, [rsp+6A0h+propBag]; propBag
0x1801fe812  lea     r8, [rbx+4E0h]; value
0x1801fe819  lea     rdx, aHidefilenames; "HideFileNames"
0x1801fe820  call    cs:__imp_PSPropertyBag_ReadDWORD
0x1801fe826  mov     rcx, [rsp+6A0h+propBag]; propBag
0x1801fe82b  lea     r8, [rbx+4DCh]; value
0x1801fe832  lea     rdx, aDatecategorize; "DateCategorizerInfo"
0x1801fe839  call    cs:__imp_PSPropertyBag_ReadDWORD
0x1801fe83f  mov     rcx, [rsp+6A0h+propBag]; propBag
0x1801fe844  lea     r8, [rbx+58h]; value
0x1801fe848  lea     rdx, aChildviewid; "ChildViewID"
0x1801fe84f  call    cs:__imp_PSPropertyBag_ReadGUID
0x1801fe855  mov     rcx, [rsp+6A0h+propBag]; propBag
0x1801fe85a  lea     r8, [rsp+6A0h+value]; value
0x1801fe85f  mov     r9d, r12d; characterCount
0x1801fe862  lea     rdx, aGroupby; "GroupBy"
0x1801fe869  call    cs:__imp_PSPropertyBag_ReadStr
0x1801fe86f  test    eax, eax
0x1801fe871  js      short loc_1801FE885
0x1801fe873  lea     rdx, [rbx+48Ch]; ppropkey
0x1801fe87a  lea     rcx, [rsp+6A0h+value]; pszName
0x1801fe87f  call    cs:__imp_PSGetPropertyKeyFromName
0x1801fe885  mov     rcx, [rsp+6A0h+propBag]; propBag
0x1801fe88a  lea     r8, [rbx+4A0h]; value
0x1801fe891  lea     rdx, aGroupascending; "GroupAscending"
0x1801fe898  mov     dword ptr [r8], 1
0x1801fe89f  call    cs:__imp_PSPropertyBag_ReadBOOL
0x1801fe8a5  mov     rcx, [rsp+6A0h+propBag]; propBag
0x1801fe8aa  lea     r8, [rbp+5A0h+pszName]; value
0x1801fe8b1  mov     r9d, r12d; characterCount
0x1801fe8b4  lea     rdx, aStackby; "StackBy"
0x1801fe8bb  call    cs:__imp_PSPropertyBag_ReadStr
0x1801fe8c1  test    eax, eax
0x1801fe8c3  js      short loc_1801FE8D9
0x1801fe8c5  lea     rdx, [rbx+4C8h]; ppropkey
0x1801fe8cc  lea     rcx, [rbp+5A0h+pszName]; pszName
0x1801fe8d3  call    cs:__imp_PSGetPropertyKeyFromName
0x1801fe8d9  mov     rcx, [rsp+6A0h+propBag]; propBag
0x1801fe8de  lea     r8, [rbp+5A0h+var_240]; value
0x1801fe8e5  mov     r9d, r12d; characterCount
0x1801fe8e8  lea     rdx, aPrimarypropert; "PrimaryProperty"
0x1801fe8ef  call    cs:__imp_PSPropertyBag_ReadStr
0x1801fe8f5  test    eax, eax
0x1801fe8f7  js      short loc_1801FE90D
0x1801fe8f9  lea     rdx, [rbx+4E4h]; ppropkey
0x1801fe900  lea     rcx, [rbp+5A0h+var_240]; pszName
0x1801fe907  call    cs:__imp_PSGetPropertyKeyFromName
0x1801fe90d  mov     rcx, [rsp+6A0h+propBag]; propBag
0x1801fe912  lea     r8, [rbx+4F8h]; value
0x1801fe919  lea     rdx, aPrimarysetting; "PrimarySettings"
0x1801fe920  call    cs:__imp_PSPropertyBag_ReadDWORD
0x1801fe926  mov     r8, [rsp+6A0h+propBag]; struct IPropertyBag *
0x1801fe92b  mov     rdx, r15; unsigned __int16 *
0x1801fe92e  mov     rcx, rbx; this
0x1801fe931  call    ?_InitializeColumnListWithEncryptionOwners@CTopViewDescription@@AEAAJPEBGPEAUIPropertyBag@@@Z; CTopViewDescription::_InitializeColumnListWithEncryptionOwners(ushort const *,IPropertyBag *)
0x1801fe936  test    eax, eax
0x1801fe938  jns     short loc_1801FE988
0x1801fe93a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_53797701@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_53797701@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53797701> `wil::Feature<__WilFeatureTraits_Feature_53797701>::GetImpl(void)'::`2'::impl
0x1801fe941  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_53797701@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53797701>::__private_IsEnabled(void)
0x1801fe946  mov     rcx, [rsp+6A0h+propBag]; propBag
0x1801fe94b  test    al, al
0x1801fe94d  jz      short loc_1801FE974
0x1801fe94f  lea     rsi, [rbx+4A8h]
0x1801fe956  mov     r8, rsi; value
0x1801fe959  lea     rdx, aColumnlist5379; "ColumnList_53797701"
0x1801fe960  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x1801fe966  test    eax, eax
0x1801fe968  jns     short loc_1801FE988
0x1801fe96a  mov     rcx, [rsp+6A0h+propBag]
0x1801fe96f  mov     r8, rsi
0x1801fe972  jmp     short loc_1801FE97B
0x1801fe974  lea     r8, [rbx+4A8h]; value
0x1801fe97b  lea     rdx, aColumnlist; "ColumnList"
0x1801fe982  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x1801fe988  mov     rcx, [rsp+6A0h+propBag]; propBag
0x1801fe98d  lea     r8, [rbx+4B0h]; value
0x1801fe994  lea     rdx, aSortbylist; "SortByList"
0x1801fe99b  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x1801fe9a1  mov     rcx, [rsp+6A0h+propBag]
0x1801fe9a6  mov     rax, [rcx]
0x1801fe9a9  mov     rax, [rax+10h]
0x1801fe9ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fe9b2  lea     rcx, [rbx+20h]; SRWLock
0x1801fe9b6  call    cs:__imp_ReleaseSRWLockExclusive
0x1801fe9bc  mov     eax, edi
0x1801fe9be  mov     rcx, [rbp+5A0h+var_30]
0x1801fe9c5  xor     rcx, rsp; StackCookie
0x1801fe9c8  call    __security_check_cookie
0x1801fe9cd  lea     r11, [rsp+6A0h+var_20]
0x1801fe9d5  mov     rbx, [r11+40h]
0x1801fe9d9  mov     rsi, [r11+48h]
0x1801fe9dd  mov     rsp, r11
0x1801fe9e0  pop     r15
0x1801fe9e2  pop     r14
0x1801fe9e4  pop     r12
0x1801fe9e6  pop     rdi
0x1801fe9e7  pop     rbp
0x1801fe9e8  retn
```
