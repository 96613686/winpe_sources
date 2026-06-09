# CAvEndpointBuilder::MigrateAudioSystemEffectsProperties(IPnpInterface *,IMMDevice *,_GUID const &,int)

- ea: `0x18004edfc`
- end: `0x18004f299`
- name: `?MigrateAudioSystemEffectsProperties@CAvEndpointBuilder@@AEAAJPEAUIPnpInterface@@PEAUIMMDevice@@AEBU_GUID@@H@Z`
- size: `1181`
- prototype: `__int64 __fastcall(CAvEndpointBuilder *__hidden this, struct IPnpInterface *, struct IMMDevice *, const struct _GUID *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003b790`

## callees

- `0x180006b0c`
- `0x180010da8`
- `0x18001deb0`
- `0x180023d28`
- `0x18003e920`
- `0x18003f780`
- `0x18004edfc`
- `0x18004f2a0`
- `0x18005da2c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f0e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f1b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f26a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f0e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f1b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f26a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004efa4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004efa4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004f087`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004f125`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004f182`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004f087`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004f125`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004f182`

## string_xrefs

- `0x18004f0f9`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18004f158`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18004f1d4`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18004f1fa`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18004f21e`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18004f24d`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CAvEndpointBuilder::MigrateAudioSystemEffectsProperties(
        CAvEndpointBuilder *this,
        struct IPnpInterface *a2,
        struct IMMDevice *a3,
        const struct _GUID *a4,
        int a5)
{
  unsigned int v8; // esi
  __int64 v9; // rbx
  int v10; // eax
  int v11; // ebx
  __int64 v12; // rdx
  HKEY v13; // rdx
  int v14; // r14d
  unsigned int i; // r15d
  __int64 v16; // rax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  CAvEndpointBuilder *v22; // rcx
  __int64 v23; // rdx
  __int64 v25; // rdx
  int *v26; // [rsp+20h] [rbp-91h]
  HKEY hKey; // [rsp+40h] [rbp-71h] BYREF
  __int64 v28; // [rsp+48h] [rbp-69h] BYREF
  __int64 *v29; // [rsp+50h] [rbp-61h] BYREF
  struct IAudioSystemEffectsPropertyStore *v30; // [rsp+58h] [rbp-59h] BYREF
  __int64 *v31; // [rsp+60h] [rbp-51h] BYREF
  struct IAudioSystemEffectsPropertyStore *v32; // [rsp+68h] [rbp-49h] BYREF
  LPCOLESTR lpsz[2]; // [rsp+70h] [rbp-41h] BYREF
  __int64 v34; // [rsp+80h] [rbp-31h]
  struct IMMDevice *v35; // [rsp+88h] [rbp-29h] BYREF
  __int128 v36; // [rsp+90h] [rbp-21h] BYREF
  GUID pclsid; // [rsp+A0h] [rbp-11h] BYREF
  int v38[4]; // [rsp+B0h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  v35 = a3;
  v8 = 0;
LABEL_2:
  hKey = 0;
  v9 = *(_QWORD *)a2;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  if ( a5 )
  {
    v10 = (*(__int64 (__fastcall **)(struct IPnpInterface *, _QWORD, _QWORD, HKEY *))(v9 + 104))(a2, v8, 0, &hKey);
    v11 = v10;
    if ( v10 < 0 )
    {
      if ( v10 != -2147024894 && v10 != -536870396 )
      {
        v12 = 11893;
        goto LABEL_53;
      }
      goto LABEL_54;
    }
  }
  else
  {
    v11 = (*(__int64 (__fastcall **)(struct IPnpInterface *, _QWORD, _QWORD, HKEY *))(v9 + 96))(a2, v8, 0, &hKey);
    if ( v11 < 0 )
    {
      if ( v11 != -2147024894 && v11 != -536870396 )
      {
        v12 = 11898;
LABEL_53:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)(unsigned int)v11,
          (int)v26);
      }
LABEL_54:
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v11;
    }
  }
  v13 = hKey;
  if ( !hKey )
    return 0;
  v14 = 0;
  for ( i = 0; ; ++i )
  {
    *(GUID *)v38 = GUID_00000000_0000_0000_0000_000000000000;
    v16 = *(_QWORD *)a2;
    v30 = 0;
    v26 = v38;
    v17 = (*(__int64 (__fastcall **)(struct IPnpInterface *, HKEY, _QWORD, _QWORD))(v16 + 112))(a2, v13, i, 0);
    v11 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E87,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v17,
        (int)v38);
      goto LABEL_38;
    }
    if ( !v30 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
      if ( v14 )
      {
        v11 = CAvEndpointBuilder::MigrateFxPropertiesInternal(v22, a2, a3, hKey);
        if ( v11 < 0 )
        {
          v12 = 11959;
          goto LABEL_53;
        }
      }
      if ( hKey )
        RegCloseKey(hKey);
      ++v8;
      goto LABEL_2;
    }
    v29 = 0;
    v18 = (**(__int64 (__fastcall ***)(struct IAudioSystemEffectsPropertyStore *, GUID *, __int64 **))v30)(
            v30,
            &GUID_13dfcc0a_15ea_4b9e_a5a6_cc1e5c0bb317,
            &v29);
    v11 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E8F,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v18,
        (int)v38);
      goto LABEL_37;
    }
    v28 = 0;
    v19 = *v29;
    v28 = 0;
    if ( (*(int (__fastcall **)(__int64 *, _QWORD, __int64 *))(v19 + 24))(v29, 0, &v28) < 0 )
      goto LABEL_28;
    *(_OWORD *)lpsz = 0;
    v34 = 0;
    if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, LPCOLESTR *))(*(_QWORD *)v28 + 40LL))(
           v28,
           &PKEY_FX_Association,
           lpsz) >= 0
      && LOWORD(lpsz[0]) == 31 )
    {
      pclsid = 0;
      if ( CLSIDFromString(lpsz[1], &pclsid) >= 0 )
      {
        v20 = *(_QWORD *)&pclsid.Data1 - *(_QWORD *)&a4->Data1;
        if ( *(_QWORD *)&pclsid.Data1 == *(_QWORD *)&a4->Data1 )
          v20 = *(_QWORD *)pclsid.Data4 - *(_QWORD *)a4->Data4;
        if ( !v20 || !memcmp_0(&pclsid, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
          break;
      }
    }
LABEL_27:
    PropVariantClear((PROPVARIANT *)lpsz);
LABEL_28:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
    v13 = hKey;
  }
  v31 = 0;
  v11 = wil::com_query_to_nothrow<IMMEndpointInternal,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(
          &v35,
          &v31);
  if ( v11 < 0 )
  {
    v25 = 11947;
    goto LABEL_44;
  }
  if ( !v31 )
  {
    v11 = -2147418113;
    v25 = 11948;
LABEL_44:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v11,
      (int)v38);
LABEL_36:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
    PropVariantClear((PROPVARIANT *)lpsz);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
LABEL_37:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
LABEL_38:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
    goto LABEL_54;
  }
  v32 = 0;
  v21 = *v31;
  v32 = 0;
  v36 = *(_OWORD *)v38;
  v11 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int128 *, struct IAudioSystemEffectsPropertyStore **))(v21 + 144))(
          v31,
          2,
          &v36,
          &v32);
  if ( v11 < 0 )
  {
    v23 = 11951;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v11,
      (int)v38);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
    goto LABEL_36;
  }
  if ( v32 )
  {
    v11 = CopyAudioSystemEffectsProperties(v32, v30);
    if ( v11 < 0 )
    {
      v23 = 11954;
      goto LABEL_35;
    }
    v14 = 1;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
    goto LABEL_27;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2EB0,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
    (const char *)0x80070002LL,
    (int)v38);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
  PropVariantClear((PROPVARIANT *)lpsz);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
  if ( hKey )
    RegCloseKey(hKey);
  return 2147942402LL;
}

```

## disassembly

```asm
0x18004edfc  mov     [rsp-8+arg_0], rbx
0x18004ee01  push    rbp
0x18004ee02  push    rsi
0x18004ee03  push    rdi
0x18004ee04  push    r12
0x18004ee06  push    r13
0x18004ee08  push    r14
0x18004ee0a  push    r15
0x18004ee0c  lea     rbp, [rsp-1Fh]
0x18004ee11  sub     rsp, 0D0h
0x18004ee18  mov     rax, cs:__security_cookie
0x18004ee1f  xor     rax, rsp
0x18004ee22  mov     [rbp+4Fh+var_40], rax
0x18004ee26  mov     r12, r9
0x18004ee29  mov     r13, r8
0x18004ee2c  mov     rdi, rdx
0x18004ee2f  mov     [rbp+4Fh+var_78], r8
0x18004ee33  xor     esi, esi
0x18004ee35  mov     [rbp+4Fh+hKey], 0
0x18004ee3d  mov     rbx, [rdi]
0x18004ee40  xor     edx, edx
0x18004ee42  lea     rcx, [rbp+4Fh+hKey]
0x18004ee46  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004ee4b  lea     r9, [rbp+4Fh+hKey]
0x18004ee4f  xor     r8d, r8d
0x18004ee52  mov     edx, esi
0x18004ee54  mov     rcx, rdi
0x18004ee57  cmp     [rbp+4Fh+arg_20], r8d
0x18004ee5b  jz      short loc_18004EE8C
0x18004ee5d  mov     rax, [rbx+68h]
0x18004ee61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee66  mov     ebx, eax
0x18004ee68  test    eax, eax
0x18004ee6a  jns     short loc_18004EE9F
0x18004ee6c  cmp     eax, 80070002h
0x18004ee71  jz      loc_18004F261
0x18004ee77  cmp     eax, 0E0000204h
0x18004ee7c  jz      loc_18004F261
0x18004ee82  mov     edx, 2E75h
0x18004ee87  jmp     loc_18004F24D
0x18004ee8c  mov     rax, [rbx+60h]
0x18004ee90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee95  mov     ebx, eax
0x18004ee97  test    eax, eax
0x18004ee99  js      loc_18004F238
0x18004ee9f  mov     rdx, [rbp+4Fh+hKey]
0x18004eea3  test    rdx, rdx
0x18004eea6  jz      loc_18004F234
0x18004eeac  xor     r14d, r14d
0x18004eeaf  xor     r15d, r15d
0x18004eeb2  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004eeb9  movdqu  xmmword ptr [rbp+4Fh+var_50], xmm0
0x18004eebe  mov     rax, [rdi]
0x18004eec1  mov     [rbp+4Fh+var_A8], 0
0x18004eec9  lea     rcx, [rbp+4Fh+var_A8]
0x18004eecd  mov     [rsp+100h+var_D8], rcx
0x18004eed2  lea     rcx, [rbp+4Fh+var_50]
0x18004eed6  mov     qword ptr [rsp+100h+var_E0], rcx; int
0x18004eedb  xor     r9d, r9d
0x18004eede  mov     r8d, r15d
0x18004eee1  mov     rcx, rdi
0x18004eee4  mov     rax, [rax+70h]
0x18004eee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eeed  mov     ebx, eax
0x18004eeef  test    eax, eax
0x18004eef1  js      loc_18004F217
0x18004eef7  mov     rcx, [rbp+4Fh+var_A8]
0x18004eefb  test    rcx, rcx
0x18004eefe  jz      loc_18004F0B7
0x18004ef04  mov     [rbp+4Fh+var_B0], 0
0x18004ef0c  mov     rax, [rcx]
0x18004ef0f  lea     r8, [rbp+4Fh+var_B0]
0x18004ef13  lea     rdx, _GUID_13dfcc0a_15ea_4b9e_a5a6_cc1e5c0bb317
0x18004ef1a  mov     rax, [rax]
0x18004ef1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef22  mov     ebx, eax
0x18004ef24  test    eax, eax
0x18004ef26  js      loc_18004F1F3
0x18004ef2c  mov     [rbp+4Fh+var_B8], 0
0x18004ef34  mov     rcx, [rbp+4Fh+var_B0]
0x18004ef38  mov     rax, [rcx]
0x18004ef3b  mov     [rbp+4Fh+var_B8], 0
0x18004ef43  lea     r8, [rbp+4Fh+var_B8]
0x18004ef47  xor     edx, edx
0x18004ef49  mov     rax, [rax+18h]
0x18004ef4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef52  test    eax, eax
0x18004ef54  js      loc_18004F08E
0x18004ef5a  xorps   xmm0, xmm0
0x18004ef5d  xor     eax, eax
0x18004ef5f  movups  xmmword ptr [rbp+4Fh+lpsz], xmm0
0x18004ef63  mov     [rbp+4Fh+var_80], rax
0x18004ef67  mov     rcx, [rbp+4Fh+var_B8]
0x18004ef6b  mov     rax, [rcx]
0x18004ef6e  lea     r8, [rbp+4Fh+lpsz]
0x18004ef72  lea     rdx, PKEY_FX_Association
0x18004ef79  mov     rax, [rax+28h]
0x18004ef7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef82  test    eax, eax
0x18004ef84  js      loc_18004F083
0x18004ef8a  cmp     word ptr [rbp+4Fh+lpsz], 1Fh
0x18004ef8f  jnz     loc_18004F083
0x18004ef95  xorps   xmm0, xmm0
0x18004ef98  movups  xmmword ptr [rbp+4Fh+pclsid.Data1], xmm0
0x18004ef9c  lea     rdx, [rbp+4Fh+pclsid]; pclsid
0x18004efa0  mov     rcx, [rbp+4Fh+lpsz+8]; lpsz
0x18004efa4  call    cs:__imp_CLSIDFromString
0x18004efaa  test    eax, eax
0x18004efac  js      loc_18004F083
0x18004efb2  mov     rax, qword ptr [rbp+4Fh+pclsid.Data1]
0x18004efb6  sub     rax, [r12]
0x18004efba  jnz     short loc_18004EFC5
0x18004efbc  mov     rax, qword ptr [rbp+4Fh+pclsid.Data4]
0x18004efc0  sub     rax, [r12+8]
0x18004efc5  test    rax, rax
0x18004efc8  jz      short loc_18004EFE8
0x18004efca  mov     r8d, 10h; Size
0x18004efd0  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x18004efd7  lea     rcx, [rbp+4Fh+pclsid]; Buf1
0x18004efdb  call    memcmp_0
0x18004efe0  test    eax, eax
0x18004efe2  jnz     loc_18004F083
0x18004efe8  xor     r14d, r14d
0x18004efeb  mov     [rbp+4Fh+var_A0], r14
0x18004efef  lea     rdx, [rbp+4Fh+var_A0]
0x18004eff3  lea     rcx, [rbp+4Fh+var_78]
0x18004eff7  call    ??$com_query_to_nothrow@UIMMEndpointInternal@@AEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@@wil@@YAJAEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@0@PEAPEAUIMMEndpointInternal@@@Z; wil::com_query_to_nothrow<IMMEndpointInternal,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &,IMMEndpointInternal * *)
0x18004effc  mov     ebx, eax
0x18004effe  test    eax, eax
0x18004f000  js      loc_18004F1EC
0x18004f006  mov     rcx, [rbp+4Fh+var_A0]
0x18004f00a  test    rcx, rcx
0x18004f00d  jz      loc_18004F1CA
0x18004f013  mov     [rbp+4Fh+var_98], r14
0x18004f017  mov     rax, [rcx]
0x18004f01a  mov     [rbp+4Fh+var_98], r14
0x18004f01e  movaps  xmm0, xmmword ptr [rbp+4Fh+var_50]
0x18004f022  movdqa  [rbp+4Fh+var_70], xmm0
0x18004f027  lea     r9, [rbp+4Fh+var_98]
0x18004f02b  lea     r8, [rbp+4Fh+var_70]
0x18004f02f  lea     edx, [r14+2]
0x18004f033  mov     rax, [rax+90h]
0x18004f03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f03f  mov     ebx, eax
0x18004f041  test    eax, eax
0x18004f043  js      loc_18004F1C0
0x18004f049  mov     rcx, [rbp+4Fh+var_98]; struct IAudioSystemEffectsPropertyStore *
0x18004f04d  test    rcx, rcx
0x18004f050  jz      loc_18004F14E
0x18004f056  mov     rdx, [rbp+4Fh+var_A8]; struct IAudioSystemEffectsPropertyStore *
0x18004f05a  call    ?CopyAudioSystemEffectsProperties@@YAJPEAUIAudioSystemEffectsPropertyStore@@0@Z; CopyAudioSystemEffectsProperties(IAudioSystemEffectsPropertyStore *,IAudioSystemEffectsPropertyStore *)
0x18004f05f  mov     ebx, eax
0x18004f061  test    eax, eax
0x18004f063  js      loc_18004F0F4
0x18004f069  mov     r14d, 1
0x18004f06f  lea     rcx, [rbp+4Fh+var_98]
0x18004f073  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f078  nop
0x18004f079  lea     rcx, [rbp+4Fh+var_A0]
0x18004f07d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f082  nop
0x18004f083  lea     rcx, [rbp+4Fh+lpsz]; pvar
0x18004f087  call    cs:__imp_PropVariantClear
0x18004f08d  nop
0x18004f08e  lea     rcx, [rbp+4Fh+var_B8]
0x18004f092  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f097  nop
0x18004f098  lea     rcx, [rbp+4Fh+var_B0]
0x18004f09c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f0a1  nop
0x18004f0a2  lea     rcx, [rbp+4Fh+var_A8]
0x18004f0a6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f0ab  inc     r15d
0x18004f0ae  mov     rdx, [rbp+4Fh+hKey]
0x18004f0b2  jmp     loc_18004EEB2
0x18004f0b7  lea     rcx, [rbp+4Fh+var_A8]
0x18004f0bb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f0c0  test    r14d, r14d
0x18004f0c3  jz      short loc_18004F0DE
0x18004f0c5  mov     r9, [rbp+4Fh+hKey]; HKEY
0x18004f0c9  mov     r8, r13; struct IMMDevice *
0x18004f0cc  mov     rdx, rdi; struct IPnpInterface *
0x18004f0cf  call    ?MigrateFxPropertiesInternal@CAvEndpointBuilder@@AEAAJPEAUIPnpInterface@@PEAUIMMDevice@@PEAUHKEY__@@@Z; CAvEndpointBuilder::MigrateFxPropertiesInternal(IPnpInterface *,IMMDevice *,HKEY__ *)
0x18004f0d4  mov     ebx, eax
0x18004f0d6  test    eax, eax
0x18004f0d8  js      loc_18004F210
0x18004f0de  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18004f0e2  test    rcx, rcx
0x18004f0e5  jz      short loc_18004F0ED
0x18004f0e7  call    cs:__imp_RegCloseKey
0x18004f0ed  inc     esi
0x18004f0ef  jmp     loc_18004EE35
0x18004f0f4  mov     edx, 2EB2h; void *
0x18004f0f9  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18004f100  mov     r9d, ebx; char *
0x18004f103  mov     rcx, [rbp+57h]; this
0x18004f107  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f10c  nop
0x18004f10d  lea     rcx, [rbp+4Fh+var_98]
0x18004f111  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f116  nop
0x18004f117  lea     rcx, [rbp+4Fh+var_A0]
0x18004f11b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f120  nop
0x18004f121  lea     rcx, [rbp+4Fh+lpsz]; pvar
0x18004f125  call    cs:__imp_PropVariantClear
0x18004f12b  nop
0x18004f12c  lea     rcx, [rbp+4Fh+var_B8]
0x18004f130  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f135  nop
0x18004f136  lea     rcx, [rbp+4Fh+var_B0]
0x18004f13a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f13f  nop
0x18004f140  lea     rcx, [rbp+4Fh+var_A8]
0x18004f144  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f149  jmp     loc_18004F261
0x18004f14e  mov     rcx, [rbp+57h]; this
0x18004f152  mov     r9d, 80070002h; char *
0x18004f158  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18004f15f  mov     edx, 2EB0h; void *
0x18004f164  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f169  nop
0x18004f16a  lea     rcx, [rbp+4Fh+var_98]
0x18004f16e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f173  nop
0x18004f174  lea     rcx, [rbp+4Fh+var_A0]
0x18004f178  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f17d  nop
0x18004f17e  lea     rcx, [rbp+4Fh+lpsz]; pvar
0x18004f182  call    cs:__imp_PropVariantClear
0x18004f188  nop
0x18004f189  lea     rcx, [rbp+4Fh+var_B8]
0x18004f18d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f192  nop
0x18004f193  lea     rcx, [rbp+4Fh+var_B0]
0x18004f197  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f19c  nop
0x18004f19d  lea     rcx, [rbp+4Fh+var_A8]
0x18004f1a1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f1a6  nop
0x18004f1a7  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18004f1ab  test    rcx, rcx
0x18004f1ae  jz      short loc_18004F1B6
0x18004f1b0  call    cs:__imp_RegCloseKey
0x18004f1b6  mov     eax, 80070002h
0x18004f1bb  jmp     loc_18004F272
0x18004f1c0  mov     edx, 2EAFh
0x18004f1c5  jmp     loc_18004F0F9
0x18004f1ca  mov     ebx, 8000FFFFh
0x18004f1cf  mov     edx, 2EACh; void *
0x18004f1d4  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18004f1db  mov     r9d, ebx; char *
0x18004f1de  mov     rcx, [rbp+57h]; this
0x18004f1e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f1e7  jmp     loc_18004F117
0x18004f1ec  mov     edx, 2EABh
0x18004f1f1  jmp     short loc_18004F1D4
0x18004f1f3  mov     rcx, [rbp+57h]; this
0x18004f1f7  mov     r9d, ebx; char *
0x18004f1fa  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18004f201  mov     edx, 2E8Fh; void *
0x18004f206  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f20b  jmp     loc_18004F136
0x18004f210  mov     edx, 2EB7h
0x18004f215  jmp     short loc_18004F24D
0x18004f217  mov     rcx, [rbp+57h]; this
0x18004f21b  mov     r9d, ebx; char *
0x18004f21e  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18004f225  mov     edx, 2E87h; void *
0x18004f22a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f22f  jmp     loc_18004F140
0x18004f234  xor     eax, eax
0x18004f236  jmp     short loc_18004F272
0x18004f238  cmp     ebx, 80070002h
0x18004f23e  jz      short loc_18004F261
0x18004f240  cmp     ebx, 0E0000204h
0x18004f246  jz      short loc_18004F261
0x18004f248  mov     edx, 2E7Ah; void *
0x18004f24d  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18004f254  mov     r9d, ebx; char *
0x18004f257  mov     rcx, [rbp+57h]; this
0x18004f25b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f260  nop
0x18004f261  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18004f265  test    rcx, rcx
0x18004f268  jz      short loc_18004F270
0x18004f26a  call    cs:__imp_RegCloseKey
0x18004f270  mov     eax, ebx
0x18004f272  mov     rcx, [rbp+4Fh+var_40]
0x18004f276  xor     rcx, rsp; StackCookie
0x18004f279  call    __security_check_cookie
0x18004f27e  mov     rbx, [rsp+100h+arg_0]
0x18004f286  add     rsp, 0D0h
0x18004f28d  pop     r15
0x18004f28f  pop     r14
0x18004f291  pop     r13
0x18004f293  pop     r12
0x18004f295  pop     rdi
0x18004f296  pop     rsi
0x18004f297  pop     rbp
  ... truncated ...
```
