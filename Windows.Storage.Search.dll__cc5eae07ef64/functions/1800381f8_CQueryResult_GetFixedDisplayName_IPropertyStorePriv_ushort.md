# CQueryResult::_GetFixedDisplayName(IPropertyStorePriv *,ushort * *)

- ea: `0x1800381f8`
- end: `0x1800383ff`
- name: `?_GetFixedDisplayName@CQueryResult@@AEAAJPEAUIPropertyStorePriv@@PEAPEAG@Z`
- size: `519`
- prototype: `__int64 __fastcall(CQueryResult *__hidden this, struct IPropertyStorePriv *, PWSTR *ppszDisplay)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180038020`

## callees

- `0x180037a28`
- `0x180037f10`
- `0x1800381f8`
- `0x180063a68`
- `0x180071dc0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800383e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800383e0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x180038329`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x180038334`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x180038329`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x180038334`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800383ee`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800383ee`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x180038346`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x180038346`
- `PROPSYS!PropVariantToUInt32WithDefault` at `0x180038265`
- `PROPSYS!PropVariantToUInt32WithDefault` at `0x180038265`
- `PROPSYS!PSFormatForDisplayAlloc` at `0x180038369`
- `PROPSYS!PSFormatForDisplayAlloc` at `0x180038369`
- `PROPSYS!PropVariantToString` at `0x1800382f9`
- `PROPSYS!PropVariantToString` at `0x180038316`
- `PROPSYS!PropVariantToString` at `0x1800382f9`
- `PROPSYS!PropVariantToString` at `0x180038316`

## pseudocode

```c
__int64 __fastcall CQueryResult::_GetFixedDisplayName(
        CQueryResult *this,
        struct IPropertyStorePriv *a2,
        PWSTR *ppszDisplay)
{
  __int64 v4; // rax
  HRESULT v7; // ebx
  ULONG v8; // edi
  __int64 v9; // rax
  __int64 v10; // rax
  int v11; // eax
  PROPVARIANT *v12; // rdx
  CQueryResult *v14; // rcx
  const WCHAR *FixedParsingPath; // rax
  WCHAR *v16; // r14
  PROPVARIANT *propvarIn; // [rsp+20h] [rbp-E0h] BYREF
  PROPVARIANT *propvar; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR pszPath[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR psz[264]; // [rsp+240h] [rbp+140h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+388h]

  *ppszDisplay = 0;
  v4 = *(_QWORD *)a2;
  v7 = 0;
  propvarIn = 0;
  if ( (*(int (__fastcall **)(struct IPropertyStorePriv *, const PROPERTYKEY *, PROPVARIANT **))(v4 + 88))(
         a2,
         &PKEY_SFGAOFlags,
         &propvarIn) >= 0 )
  {
    v8 = PropVariantToUInt32WithDefault(propvarIn, 0);
    if ( (v8 & 0x40000000) == 0 && CQueryResult::_IsWdsOrGrepDataSource(this, a2) )
    {
      FixedParsingPath = CQueryResult::_GetFixedParsingPath(v14, a2);
      v16 = (WCHAR *)FixedParsingPath;
      if ( FixedParsingPath && PathGetDriveNumberW(FixedParsingPath) != -1 )
        v8 |= 0x40000000u;
      CoTaskMemFree(v16);
    }
    if ( (v8 & 0x40000000) != 0 && (v8 & 0x20400000) != 0x20000000 )
    {
      v9 = *(_QWORD *)a2;
      propvar = 0;
      if ( (*(int (__fastcall **)(struct IPropertyStorePriv *, const PROPERTYKEY *, PROPVARIANT **))(v9 + 88))(
             a2,
             &PKEY_ItemNameDisplay,
             &propvar) >= 0 )
      {
        v10 = *(_QWORD *)a2;
        propvarIn = 0;
        v7 = (*(__int64 (__fastcall **)(struct IPropertyStorePriv *, const PROPERTYKEY *, PROPVARIANT **))(v10 + 88))(
               a2,
               &PKEY_ParsingName,
               &propvarIn);
        if ( v7 < 0 )
          goto LABEL_13;
        v7 = PropVariantToString(propvar, psz, 0x104u);
        if ( v7 < 0 )
          goto LABEL_13;
        v7 = PropVariantToString(propvarIn, pszPath, 0x104u);
        if ( v7 < 0 )
          goto LABEL_13;
        PathRemoveExtensionW(psz);
        PathRemoveExtensionW(pszPath);
        v11 = StrCmpW(psz, pszPath);
        v12 = propvar;
        if ( !v11 )
          v12 = propvarIn;
        v7 = PSFormatForDisplayAlloc(&PKEY_ItemNameDisplay, v12, PDFF_FILENAME, ppszDisplay);
        if ( v7 < 0 )
LABEL_13:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9CB,
            (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
            (const char *)(unsigned int)v7,
            (int)propvarIn);
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800381f8  mov     [rsp-8+arg_18], rbx
0x1800381fd  push    rbp
0x1800381fe  push    rsi
0x1800381ff  push    rdi
0x180038200  push    r14
0x180038202  push    r15
0x180038204  lea     rbp, [rsp-360h]
0x18003820c  sub     rsp, 460h
0x180038213  mov     rax, cs:__security_cookie
0x18003821a  xor     rax, rsp
0x18003821d  mov     [rbp+380h+var_30], rax
0x180038224  mov     qword ptr [r8], 0
0x18003822b  mov     rsi, rdx
0x18003822e  mov     rax, [rdx]
0x180038231  mov     r15, r8
0x180038234  mov     r14, rcx
0x180038237  lea     r8, [rsp+480h+propvarIn]
0x18003823c  xor     ebx, ebx
0x18003823e  lea     rdx, PKEY_SFGAOFlags
0x180038245  mov     rcx, rsi
0x180038248  mov     [rsp+480h+propvarIn], rbx
0x18003824d  mov     rax, [rax+58h]
0x180038251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038256  test    eax, eax
0x180038258  js      loc_180038375
0x18003825e  mov     rcx, [rsp+480h+propvarIn]; propvarIn
0x180038263  xor     edx, edx; ulDefault
0x180038265  call    cs:__imp_PropVariantToUInt32WithDefault
0x18003826b  mov     edi, eax
0x18003826d  bt      eax, 1Eh
0x180038271  jnb     loc_1800383BA
0x180038277  bt      edi, 1Eh
0x18003827b  jnb     loc_180038375
0x180038281  and     edi, 20400000h
0x180038287  cmp     edi, 20000000h
0x18003828d  jz      loc_180038375
0x180038293  mov     rax, [rsi]
0x180038296  lea     r8, [rsp+480h+propvar]
0x18003829b  lea     rdx, PKEY_ItemNameDisplay
0x1800382a2  mov     [rsp+480h+propvar], rbx
0x1800382a7  mov     rcx, rsi
0x1800382aa  mov     rax, [rax+58h]
0x1800382ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382b3  test    eax, eax
0x1800382b5  js      loc_180038375
0x1800382bb  mov     rax, [rsi]
0x1800382be  lea     r8, [rsp+480h+propvarIn]
0x1800382c3  lea     rdx, PKEY_ParsingName
0x1800382ca  mov     [rsp+480h+propvarIn], rbx; int
0x1800382cf  mov     rcx, rsi
0x1800382d2  mov     rax, [rax+58h]
0x1800382d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382db  mov     ebx, eax
0x1800382dd  test    eax, eax
0x1800382df  js      loc_18003839D
0x1800382e5  mov     rcx, [rsp+480h+propvar]; propvar
0x1800382ea  lea     rdx, [rbp+380h+psz]; psz
0x1800382f1  mov     edi, 104h
0x1800382f6  mov     r8d, edi; cch
0x1800382f9  call    cs:__imp_PropVariantToString
0x1800382ff  mov     ebx, eax
0x180038301  test    eax, eax
0x180038303  js      loc_18003839D
0x180038309  mov     rcx, [rsp+480h+propvarIn]; propvar
0x18003830e  lea     rdx, [rsp+480h+pszPath]; psz
0x180038313  mov     r8d, edi; cch
0x180038316  call    cs:__imp_PropVariantToString
0x18003831c  mov     ebx, eax
0x18003831e  test    eax, eax
0x180038320  js      short loc_18003839D
0x180038322  lea     rcx, [rbp+380h+psz]; pszPath
0x180038329  call    cs:__imp_PathRemoveExtensionW
0x18003832f  lea     rcx, [rsp+480h+pszPath]; pszPath
0x180038334  call    cs:__imp_PathRemoveExtensionW
0x18003833a  lea     rdx, [rsp+480h+pszPath]; psz2
0x18003833f  lea     rcx, [rbp+380h+psz]; psz1
0x180038346  call    cs:__imp_StrCmpW
0x18003834c  mov     rdx, [rsp+480h+propvar]
0x180038351  lea     rcx, PKEY_ItemNameDisplay; key
0x180038358  test    eax, eax
0x18003835a  mov     r9, r15; ppszDisplay
0x18003835d  mov     r8d, 2; pdff
0x180038363  cmovz   rdx, [rsp+480h+propvarIn]; propvar
0x180038369  call    cs:__imp_PSFormatForDisplayAlloc
0x18003836f  mov     ebx, eax
0x180038371  test    eax, eax
0x180038373  js      short loc_18003839D
0x180038375  mov     eax, ebx
0x180038377  mov     rcx, [rbp+380h+var_30]
0x18003837e  xor     rcx, rsp; StackCookie
0x180038381  call    __security_check_cookie
0x180038386  mov     rbx, [rsp+480h+arg_18]
0x18003838e  add     rsp, 460h
0x180038395  pop     r15
0x180038397  pop     r14
0x180038399  pop     rdi
0x18003839a  pop     rsi
0x18003839b  pop     rbp
0x18003839c  retn
0x18003839d  mov     rcx, [rbp+388h]; this
0x1800383a4  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x1800383ab  mov     r9d, ebx; char *
0x1800383ae  mov     edx, 9CBh; void *
0x1800383b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800383b8  jmp     short loc_180038375
0x1800383ba  mov     rdx, rsi; struct IPropertyStorePriv *
0x1800383bd  mov     rcx, r14; this
0x1800383c0  call    ?_IsWdsOrGrepDataSource@CQueryResult@@AEAA_NPEAUIPropertyStorePriv@@@Z; CQueryResult::_IsWdsOrGrepDataSource(IPropertyStorePriv *)
0x1800383c5  test    al, al
0x1800383c7  jz      loc_180038277
0x1800383cd  mov     rdx, rsi; struct IPropertyStorePriv *
0x1800383d0  call    ?_GetFixedParsingPath@CQueryResult@@AEAAPEAGPEAUIPropertyStorePriv@@@Z; CQueryResult::_GetFixedParsingPath(IPropertyStorePriv *)
0x1800383d5  mov     r14, rax
0x1800383d8  test    rax, rax
0x1800383db  jnz     short loc_1800383EB
0x1800383dd  mov     rcx, r14; pv
0x1800383e0  call    cs:__imp_CoTaskMemFree
0x1800383e6  jmp     loc_180038277
0x1800383eb  mov     rcx, r14; pszPath
0x1800383ee  call    cs:__imp_PathGetDriveNumberW
0x1800383f4  cmp     eax, 0FFFFFFFFh
0x1800383f7  jz      short loc_1800383DD
0x1800383f9  bts     edi, 1Eh
0x1800383fd  jmp     short loc_1800383DD
```
