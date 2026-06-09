# CAvEndpointBuilder::MigrateFxPropertiesInternal(IPnpInterface *,IMMDevice *,_GUID const &,int)

- ea: `0x18000bd2c`
- end: `0x18000c09c`
- name: `?MigrateFxPropertiesInternal@CAvEndpointBuilder@@AEAAJPEAUIPnpInterface@@PEAUIMMDevice@@AEBU_GUID@@H@Z`
- size: `880`
- prototype: `__int64 __fastcall(CAvEndpointBuilder *__hidden this, struct IPnpInterface *, struct IMMDevice *, const struct _GUID *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003b790`

## callees

- `0x180006b0c`
- `0x18000bd2c`
- `0x180010da8`
- `0x180023d28`
- `0x1800280e8`
- `0x18003e920`
- `0x18003f780`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000bed0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000bed0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bdce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000be6f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bfaf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c00e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c053`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bdce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000be6f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bfaf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c00e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c053`

## string_xrefs

- `0x18000bdb8`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18000c03e`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAvEndpointBuilder::MigrateFxPropertiesInternal(
        CAvEndpointBuilder *this,
        struct IPnpInterface *a2,
        struct IMMDevice *a3,
        const struct _GUID *a4,
        int a5)
{
  unsigned int i; // esi
  __int64 v8; // rax
  int v9; // eax
  int v10; // ebx
  __int64 v11; // rax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, __int64, struct IPropertyStore **); // rdi
  struct IPropertyStore *v16; // rcx
  __int64 v17; // rdx
  unsigned __int64 v18; // r9
  int v20; // [rsp+20h] [rbp-60h]
  struct IPropertyStore *v21; // [rsp+30h] [rbp-50h] BYREF
  __int64 v22; // [rsp+38h] [rbp-48h] BYREF
  struct IPropertyStore *v23; // [rsp+40h] [rbp-40h] BYREF
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v25; // [rsp+58h] [rbp-28h]
  struct IMMDevice *v26; // [rsp+60h] [rbp-20h] BYREF
  GUID pclsid; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v26 = a3;
  for ( i = 0; ; ++i )
  {
    v23 = 0;
    pclsid = 0;
    v22 = 0;
    *(_OWORD *)pvar = 0;
    v25 = 0;
    v8 = *(_QWORD *)a2;
    if ( a5 )
      break;
    v21 = 0;
    v10 = (*(__int64 (__fastcall **)(struct IPnpInterface *, _QWORD, _QWORD, struct IPropertyStore **))(v8 + 48))(
            a2,
            i,
            0,
            &v21);
    if ( v10 < 0 )
    {
      v17 = 8563;
      goto LABEL_46;
    }
LABEL_12:
    if ( !v21 )
    {
      PropVariantClear(pvar);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
      return 0;
    }
    if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v21->lpVtbl->GetValue)(
           v21,
           &PKEY_FX_Association,
           pvar) >= 0 )
    {
      if ( LOWORD(pvar[0]) == 31 && CLSIDFromString((LPCOLESTR)pvar[1], &pclsid) >= 0 )
      {
        v11 = *(_QWORD *)&pclsid.Data1 - *(_QWORD *)&a4->Data1;
        if ( *(_QWORD *)&pclsid.Data1 == *(_QWORD *)&a4->Data1 )
          v11 = *(_QWORD *)pclsid.Data4 - *(_QWORD *)a4->Data4;
        if ( !v11 || !memcmp_0(&pclsid, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
        {
          v12 = v22;
          v22 = 0;
          if ( v12 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          v13 = wil::com_query_to_nothrow<IMMEndpointInternal,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(
                  &v26,
                  &v22);
          v10 = v13;
          if ( v13 < 0 )
          {
            v17 = 8591;
LABEL_43:
            v18 = (unsigned int)v13;
LABEL_47:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v17,
              (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
              (const char *)v18,
              v20);
            PropVariantClear(pvar);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
            return (unsigned int)v10;
          }
          v14 = v22;
          if ( !v22 )
          {
            v10 = -2147418113;
            v17 = 8592;
LABEL_46:
            v18 = (unsigned int)v10;
            goto LABEL_47;
          }
          v15 = *(__int64 (__fastcall **)(__int64, __int64, struct IPropertyStore **))(*(_QWORD *)v22 + 40LL);
          v16 = v23;
          v23 = 0;
          if ( v16 )
            ((void (__fastcall *)(struct IPropertyStore *))v16->lpVtbl->Release)(v16);
          v13 = v15(v14, 1, &v23);
          v10 = v13;
          if ( v13 < 0 )
          {
            v17 = 8594;
            goto LABEL_43;
          }
          if ( !v23 )
          {
            v10 = -2147024894;
            v17 = 8595;
            goto LABEL_46;
          }
          v10 = CopyProperties(v23, v21);
          if ( v10 < 0 )
          {
            v17 = 8597;
            goto LABEL_46;
          }
        }
      }
      PropVariantClear(pvar);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
    }
    else
    {
      PropVariantClear(pvar);
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      if ( v21 )
        ((void (__fastcall *)(struct IPropertyStore *))v21->lpVtbl->Release)(v21);
      if ( v23 )
        ((void (__fastcall *)(struct IPropertyStore *))v23->lpVtbl->Release)(v23);
    }
  }
  v21 = 0;
  v9 = (*(__int64 (__fastcall **)(struct IPnpInterface *, _QWORD, _QWORD, struct IPropertyStore **))(v8 + 56))(
         a2,
         i,
         0,
         &v21);
  v10 = v9;
  if ( v9 >= 0 )
    goto LABEL_12;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x216F,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
    (const char *)(unsigned int)v9,
    v20);
  PropVariantClear(pvar);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v21 )
    ((void (__fastcall *)(struct IPropertyStore *))v21->lpVtbl->Release)(v21);
  if ( v23 )
    ((void (__fastcall *)(struct IPropertyStore *))v23->lpVtbl->Release)(v23);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000bd2c  mov     [rsp-28h+arg_0], rbx
0x18000bd31  push    rbp
0x18000bd32  push    rsi
0x18000bd33  push    rdi
0x18000bd34  push    r14
0x18000bd36  push    r15
0x18000bd38  mov     rbp, rsp
0x18000bd3b  sub     rsp, 80h
0x18000bd42  mov     rax, cs:__security_cookie
0x18000bd49  xor     rax, rsp
0x18000bd4c  mov     [rbp+var_8], rax
0x18000bd50  mov     r14, r9
0x18000bd53  mov     r15, rdx
0x18000bd56  mov     [rbp+var_20], r8
0x18000bd5a  xor     esi, esi
0x18000bd5c  mov     [rbp+var_40], 0
0x18000bd64  xorps   xmm0, xmm0
0x18000bd67  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x18000bd6b  mov     [rbp+var_48], 0
0x18000bd73  xor     eax, eax
0x18000bd75  movups  xmmword ptr [rbp+pvar], xmm0
0x18000bd79  mov     [rbp+var_28], rax
0x18000bd7d  mov     rax, [r15]
0x18000bd80  cmp     [rbp+arg_20], 0
0x18000bd84  jz      loc_18000BE1C
0x18000bd8a  mov     [rbp+var_50], 0
0x18000bd92  lea     r9, [rbp+var_50]
0x18000bd96  xor     r8d, r8d
0x18000bd99  mov     edx, esi
0x18000bd9b  mov     rcx, r15
0x18000bd9e  mov     rax, [rax+38h]
0x18000bda2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bda7  mov     ebx, eax
0x18000bda9  test    eax, eax
0x18000bdab  jns     loc_18000BE43
0x18000bdb1  mov     rcx, [rbp+28h]; this
0x18000bdb5  mov     r9d, eax; char *
0x18000bdb8  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18000bdbf  mov     edx, 216Fh; void *
0x18000bdc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bdc9  nop
0x18000bdca  lea     rcx, [rbp+pvar]; pvar
0x18000bdce  call    cs:__imp_PropVariantClear
0x18000bdd4  nop
0x18000bdd5  mov     rcx, [rbp+var_48]
0x18000bdd9  test    rcx, rcx
0x18000bddc  jz      short loc_18000BDEB
0x18000bdde  mov     rax, [rcx]
0x18000bde1  mov     rax, [rax+10h]
0x18000bde5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdea  nop
0x18000bdeb  mov     rcx, [rbp+var_50]
0x18000bdef  test    rcx, rcx
0x18000bdf2  jz      short loc_18000BE01
0x18000bdf4  mov     rax, [rcx]
0x18000bdf7  mov     rax, [rax+10h]
0x18000bdfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be00  nop
0x18000be01  mov     rcx, [rbp+var_40]
0x18000be05  test    rcx, rcx
0x18000be08  jz      short loc_18000BE17
0x18000be0a  mov     rax, [rcx]
0x18000be0d  mov     rax, [rax+10h]
0x18000be11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be16  nop
0x18000be17  jmp     loc_18000C077
0x18000be1c  mov     [rbp+var_50], 0
0x18000be24  lea     r9, [rbp+var_50]
0x18000be28  xor     r8d, r8d
0x18000be2b  mov     edx, esi
0x18000be2d  mov     rcx, r15
0x18000be30  mov     rax, [rax+30h]
0x18000be34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be39  mov     ebx, eax
0x18000be3b  test    eax, eax
0x18000be3d  js      loc_18000C036
0x18000be43  mov     rcx, [rbp+var_50]
0x18000be47  test    rcx, rcx
0x18000be4a  jz      loc_18000C00A
0x18000be50  mov     rax, [rcx]
0x18000be53  lea     r8, [rbp+pvar]
0x18000be57  lea     rdx, PKEY_FX_Association
0x18000be5e  mov     rax, [rax+28h]
0x18000be62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be67  test    eax, eax
0x18000be69  jns     short loc_18000BEBD
0x18000be6b  lea     rcx, [rbp+pvar]; pvar
0x18000be6f  call    cs:__imp_PropVariantClear
0x18000be75  nop
0x18000be76  mov     rcx, [rbp+var_48]
0x18000be7a  test    rcx, rcx
0x18000be7d  jz      short loc_18000BE8C
0x18000be7f  mov     rax, [rcx]
0x18000be82  mov     rax, [rax+10h]
0x18000be86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be8b  nop
0x18000be8c  mov     rcx, [rbp+var_50]
0x18000be90  test    rcx, rcx
0x18000be93  jz      short loc_18000BEA2
0x18000be95  mov     rax, [rcx]
0x18000be98  mov     rax, [rax+10h]
0x18000be9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bea1  nop
0x18000bea2  mov     rcx, [rbp+var_40]
0x18000bea6  test    rcx, rcx
0x18000bea9  jz      short loc_18000BEB8
0x18000beab  mov     rax, [rcx]
0x18000beae  mov     rax, [rax+10h]
0x18000beb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000beb7  nop
0x18000beb8  jmp     loc_18000BFD3
0x18000bebd  cmp     word ptr [rbp+pvar], 1Fh
0x18000bec2  jnz     loc_18000BFAB
0x18000bec8  lea     rdx, [rbp+pclsid]; pclsid
0x18000becc  mov     rcx, [rbp+pvar+8]; lpsz
0x18000bed0  call    cs:__imp_CLSIDFromString
0x18000bed6  test    eax, eax
0x18000bed8  js      loc_18000BFAB
0x18000bede  mov     rax, qword ptr [rbp+pclsid.Data1]
0x18000bee2  sub     rax, [r14]
0x18000bee5  jnz     short loc_18000BEEF
0x18000bee7  mov     rax, qword ptr [rbp+pclsid.Data4]
0x18000beeb  sub     rax, [r14+8]
0x18000beef  test    rax, rax
0x18000bef2  jz      short loc_18000BF12
0x18000bef4  mov     r8d, 10h; Size
0x18000befa  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x18000bf01  lea     rcx, [rbp+pclsid]; Buf1
0x18000bf05  call    memcmp_0
0x18000bf0a  test    eax, eax
0x18000bf0c  jnz     loc_18000BFAB
0x18000bf12  mov     rcx, [rbp+var_48]
0x18000bf16  mov     [rbp+var_48], 0
0x18000bf1e  test    rcx, rcx
0x18000bf21  jz      short loc_18000BF30
0x18000bf23  mov     rax, [rcx]
0x18000bf26  mov     rax, [rax+10h]
0x18000bf2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf2f  nop
0x18000bf30  lea     rdx, [rbp+var_48]
0x18000bf34  lea     rcx, [rbp+var_20]
0x18000bf38  call    ??$com_query_to_nothrow@UIMMEndpointInternal@@AEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@@wil@@YAJAEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@0@PEAPEAUIMMEndpointInternal@@@Z; wil::com_query_to_nothrow<IMMEndpointInternal,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &,IMMEndpointInternal * *)
0x18000bf3d  mov     ebx, eax
0x18000bf3f  test    eax, eax
0x18000bf41  js      loc_18000C000
0x18000bf47  mov     rbx, [rbp+var_48]
0x18000bf4b  test    rbx, rbx
0x18000bf4e  jz      loc_18000BFF4
0x18000bf54  mov     rax, [rbx]
0x18000bf57  mov     rdi, [rax+28h]
0x18000bf5b  mov     rcx, [rbp+var_40]
0x18000bf5f  mov     [rbp+var_40], 0
0x18000bf67  test    rcx, rcx
0x18000bf6a  jz      short loc_18000BF79
0x18000bf6c  mov     rdx, [rcx]
0x18000bf6f  mov     rax, [rdx+10h]
0x18000bf73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf78  nop
0x18000bf79  lea     r8, [rbp+var_40]
0x18000bf7d  mov     edx, 1
0x18000bf82  mov     rcx, rbx
0x18000bf85  mov     rax, rdi
0x18000bf88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf8d  mov     ebx, eax
0x18000bf8f  test    eax, eax
0x18000bf91  js      short loc_18000BFED
0x18000bf93  mov     rcx, [rbp+var_40]; struct IPropertyStore *
0x18000bf97  test    rcx, rcx
0x18000bf9a  jz      short loc_18000BFE1
0x18000bf9c  mov     rdx, [rbp+var_50]; struct IPropertyStore *
0x18000bfa0  call    ?CopyProperties@@YAJPEAUIPropertyStore@@0@Z; CopyProperties(IPropertyStore *,IPropertyStore *)
0x18000bfa5  mov     ebx, eax
0x18000bfa7  test    eax, eax
0x18000bfa9  js      short loc_18000BFDA
0x18000bfab  lea     rcx, [rbp+pvar]; pvar
0x18000bfaf  call    cs:__imp_PropVariantClear
0x18000bfb5  nop
0x18000bfb6  lea     rcx, [rbp+var_48]
0x18000bfba  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000bfbf  nop
0x18000bfc0  lea     rcx, [rbp+var_50]
0x18000bfc4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000bfc9  nop
0x18000bfca  lea     rcx, [rbp+var_40]
0x18000bfce  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000bfd3  inc     esi
0x18000bfd5  jmp     loc_18000BD5C
0x18000bfda  mov     edx, 2195h
0x18000bfdf  jmp     short loc_18000C03B
0x18000bfe1  mov     ebx, 80070002h
0x18000bfe6  mov     edx, 2193h
0x18000bfeb  jmp     short loc_18000C03B
0x18000bfed  mov     edx, 2192h
0x18000bff2  jmp     short loc_18000C005
0x18000bff4  mov     ebx, 8000FFFFh
0x18000bff9  mov     edx, 2190h
0x18000bffe  jmp     short loc_18000C03B
0x18000c000  mov     edx, 218Fh
0x18000c005  mov     r9d, eax
0x18000c008  jmp     short loc_18000C03E
0x18000c00a  lea     rcx, [rbp+pvar]; pvar
0x18000c00e  call    cs:__imp_PropVariantClear
0x18000c014  nop
0x18000c015  lea     rcx, [rbp+var_48]
0x18000c019  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000c01e  nop
0x18000c01f  lea     rcx, [rbp+var_50]
0x18000c023  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000c028  nop
0x18000c029  lea     rcx, [rbp+var_40]
0x18000c02d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000c032  xor     eax, eax
0x18000c034  jmp     short loc_18000C079
0x18000c036  mov     edx, 2173h; void *
0x18000c03b  mov     r9d, ebx; char *
0x18000c03e  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18000c045  mov     rcx, [rbp+28h]; this
0x18000c049  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c04e  nop
0x18000c04f  lea     rcx, [rbp+pvar]; pvar
0x18000c053  call    cs:__imp_PropVariantClear
0x18000c059  nop
0x18000c05a  lea     rcx, [rbp+var_48]
0x18000c05e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000c063  nop
0x18000c064  lea     rcx, [rbp+var_50]
0x18000c068  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000c06d  nop
0x18000c06e  lea     rcx, [rbp+var_40]
0x18000c072  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000c077  mov     eax, ebx
0x18000c079  mov     rcx, [rbp+var_8]
0x18000c07d  xor     rcx, rsp; StackCookie
0x18000c080  call    __security_check_cookie
0x18000c085  mov     rbx, [rsp+80h+arg_0]
0x18000c08d  add     rsp, 80h
0x18000c094  pop     r15
0x18000c096  pop     r14
0x18000c098  pop     rdi
0x18000c099  pop     rsi
0x18000c09a  pop     rbp
0x18000c09b  retn
```
