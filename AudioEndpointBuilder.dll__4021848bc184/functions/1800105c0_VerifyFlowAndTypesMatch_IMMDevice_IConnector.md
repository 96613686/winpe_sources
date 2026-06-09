# VerifyFlowAndTypesMatch(IMMDevice *,IConnector *)

- ea: `0x1800105c0`
- end: `0x180010b61`
- name: `?VerifyFlowAndTypesMatch@@YAJPEAUIMMDevice@@PEAUIConnector@@@Z`
- size: `1441`
- prototype: `__int64 __fastcall(struct IMMDevice *, struct IConnector *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180052ffc`

## callees

- `0x180006b0c`
- `0x1800105c0`
- `0x180010da8`
- `0x180010e60`
- `0x18003e920`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800106de`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800107e8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001085f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800108cc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010948`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800109b5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010a22`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010a8f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010ad7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010b33`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800106de`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800107e8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001085f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800108cc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010948`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800109b5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010a22`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010a8f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010ad7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010b33`

## string_xrefs

- `0x1800106c9`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180010849`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x1800108b6`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180010932`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18001099f`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180010a0c`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180010a79`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180010ac1`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180010b1d`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall VerifyFlowAndTypesMatch(struct IMMDevice *a1, struct IConnector *a2)
{
  int v4; // eax
  unsigned int v5; // esi
  int v6; // eax
  unsigned int v7; // esi
  int v8; // eax
  unsigned int v9; // esi
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  HRESULT (__stdcall *OpenPropertyStore)(IMMDevice *, DWORD, IPropertyStore **); // rbx
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // edi
  int v20; // eax
  unsigned int v21; // ebx
  int EndpointDescriptorRoot; // eax
  __int64 v23; // [rsp+20h] [rbp-29h] BYREF
  __int64 v24; // [rsp+28h] [rbp-21h] BYREF
  __int64 v25; // [rsp+30h] [rbp-19h] BYREF
  __MIDL___MIDL_itf_devicetopology_0000_0000_0011 v26; // [rsp+38h] [rbp-11h] BYREF
  int v27; // [rsp+3Ch] [rbp-Dh] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-9h] BYREF
  __int64 v29; // [rsp+50h] [rbp+7h]
  struct _GUID Buf1; // [rsp+60h] [rbp+17h] BYREF
  struct _GUID v31; // [rsp+70h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v24 = 0;
  v27 = 0;
  v26 = In;
  v23 = 0;
  *(_OWORD *)pvar = 0;
  v29 = 0;
  v31 = 0;
  v25 = 0;
  v4 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
         a1,
         &GUID_1be09788_6894_4089_8586_9a2a6c265ac5,
         &v25);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBC7,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v4,
      v23);
    PropVariantClear(pvar);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    return v5;
  }
  v24 = 0;
  v6 = ((__int64 (__fastcall *)(struct IConnector *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9,
         &v24);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBC8,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v6,
      v23);
    PropVariantClear(pvar);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
    return v7;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 24LL))(v25, &v27);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBCB,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v8,
      v23);
    PropVariantClear(pvar);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    return v9;
  }
  v10 = ((__int64 (__fastcall *)(struct IConnector *, __MIDL___MIDL_itf_devicetopology_0000_0000_0011 *))a2->lpVtbl->GetDataFlow)(
          a2,
          &v26);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBCE,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v10,
      v23);
    PropVariantClear(pvar);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
    return v11;
  }
  if ( !v27 )
  {
    if ( v26 == Out )
      goto LABEL_10;
LABEL_7:
    v12 = 3026;
    goto LABEL_8;
  }
  if ( v27 != 1 || v26 )
    goto LABEL_7;
LABEL_10:
  OpenPropertyStore = a1->lpVtbl->OpenPropertyStore;
  v23 = 0;
  v15 = ((__int64 (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))OpenPropertyStore)(a1, 0, &v23);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD5,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v15,
      v23);
    PropVariantClear(pvar);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    return v16;
  }
  else
  {
    v17 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v23 + 40LL))(
            v23,
            &PKEY_AudioEndpoint_FormFactor,
            pvar);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBD7,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v17,
        v23);
      PropVariantClear(pvar);
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      return v18;
    }
    else
    {
      if ( LOWORD(pvar[0]) != 19 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBD8,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)0x80004005LL,
          v23);
        PropVariantClear(pvar);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
        return 2147500037LL;
      }
      v19 = (int)pvar[1];
      v20 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v24 + 56LL))(v24, &v31);
      v21 = v20;
      if ( v20 >= 0 )
      {
        Buf1 = v31;
        EndpointDescriptorRoot = GetEndpointDescriptorRoot(&Buf1, v26);
        if ( EndpointDescriptorRoot != -1 && LODWORD(qword_18006A170[6 * EndpointDescriptorRoot]) == v19 )
        {
          PropVariantClear(pvar);
          if ( v23 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          if ( v24 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          if ( v25 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          return 0;
        }
        v12 = 3042;
LABEL_8:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)0x8007065DLL,
          v23);
        PropVariantClear(pvar);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
        return 2147944029LL;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBDD,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v20,
        v23);
      PropVariantClear(pvar);
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      return v21;
    }
  }
}

```

## disassembly

```asm
0x1800105c0  mov     [rsp-8+arg_10], rbx
0x1800105c5  mov     [rsp-8+arg_18], rsi
0x1800105ca  push    rbp
0x1800105cb  push    rdi
0x1800105cc  push    r14
0x1800105ce  lea     rbp, [rsp-47h]
0x1800105d3  sub     rsp, 90h
0x1800105da  mov     rax, cs:__security_cookie
0x1800105e1  xor     rax, rsp
0x1800105e4  mov     [rbp+57h+var_20], rax
0x1800105e8  mov     rbx, rdx
0x1800105eb  mov     rdi, rcx
0x1800105ee  xor     r14d, r14d
0x1800105f1  mov     [rbp+57h+var_78], r14
0x1800105f5  mov     [rbp+57h+var_64], r14d
0x1800105f9  mov     [rbp+57h+var_68], r14d
0x1800105fd  mov     [rbp+57h+var_80], r14
0x180010601  xorps   xmm0, xmm0
0x180010604  xor     eax, eax
0x180010606  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18001060a  mov     [rbp+57h+var_50], rax
0x18001060e  movups  [rbp+57h+var_30], xmm0
0x180010612  mov     [rbp+57h+var_70], r14
0x180010616  mov     rax, [rcx]
0x180010619  lea     r8, [rbp+57h+var_70]
0x18001061d  lea     rdx, _GUID_1be09788_6894_4089_8586_9a2a6c265ac5
0x180010624  mov     rax, [rax]
0x180010627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001062c  mov     esi, eax
0x18001062e  test    eax, eax
0x180010630  js      loc_180010998
0x180010636  mov     rcx, [rbp+57h+var_78]
0x18001063a  mov     [rbp+57h+var_78], r14
0x18001063e  test    rcx, rcx
0x180010641  jz      short loc_180010650
0x180010643  mov     rax, [rcx]
0x180010646  mov     rax, [rax+10h]
0x18001064a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001064f  nop
0x180010650  mov     rax, [rbx]
0x180010653  lea     r8, [rbp+57h+var_78]
0x180010657  lea     rdx, _GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9
0x18001065e  mov     rcx, rbx
0x180010661  mov     rax, [rax]
0x180010664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010669  mov     esi, eax
0x18001066b  test    eax, eax
0x18001066d  js      loc_180010A72
0x180010673  mov     rcx, [rbp+57h+var_70]
0x180010677  mov     rax, [rcx]
0x18001067a  lea     rdx, [rbp+57h+var_64]
0x18001067e  mov     rax, [rax+18h]
0x180010682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010687  mov     esi, eax
0x180010689  test    eax, eax
0x18001068b  js      loc_18001092B
0x180010691  mov     rax, [rbx]
0x180010694  lea     rdx, [rbp+57h+var_68]
0x180010698  mov     rcx, rbx
0x18001069b  mov     rax, [rax+20h]
0x18001069f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106a4  mov     ebx, eax
0x1800106a6  test    eax, eax
0x1800106a8  js      loc_180010ABA
0x1800106ae  mov     eax, [rbp+57h+var_64]
0x1800106b1  test    eax, eax
0x1800106b3  jz      short loc_18001072B
0x1800106b5  cmp     eax, 1
0x1800106b8  jz      loc_18001091C
0x1800106be  mov     edx, 0BD2h; void *
0x1800106c3  mov     r9d, 8007065Dh; char *
0x1800106c9  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x1800106d0  mov     rcx, [rbp+5Fh]; this
0x1800106d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800106d9  nop
0x1800106da  lea     rcx, [rbp+57h+pvar]; pvar
0x1800106de  call    cs:__imp_PropVariantClear
0x1800106e4  nop
0x1800106e5  lea     rcx, [rbp+57h+var_80]
0x1800106e9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800106ee  nop
0x1800106ef  lea     rcx, [rbp+57h+var_78]
0x1800106f3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800106f8  nop
0x1800106f9  lea     rcx, [rbp+57h+var_70]
0x1800106fd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180010702  mov     eax, 8007065Dh
0x180010707  mov     rcx, [rbp+57h+var_20]
0x18001070b  xor     rcx, rsp; StackCookie
0x18001070e  call    __security_check_cookie
0x180010713  lea     r11, [rsp+0A0h+var_10]
0x18001071b  mov     rbx, [r11+30h]
0x18001071f  mov     rsi, [r11+38h]
0x180010723  mov     rsp, r11
0x180010726  pop     r14
0x180010728  pop     rdi
0x180010729  pop     rbp
0x18001072a  retn
0x18001072b  cmp     [rbp+57h+var_68], 1
0x18001072f  jnz     short loc_1800106BE
0x180010731  mov     rax, [rdi]
0x180010734  mov     rbx, [rax+20h]
0x180010738  mov     rcx, [rbp+57h+var_80]
0x18001073c  mov     [rbp+57h+var_80], r14
0x180010740  test    rcx, rcx
0x180010743  jnz     loc_180010B02
0x180010749  lea     r8, [rbp+57h+var_80]
0x18001074d  xor     edx, edx
0x18001074f  mov     rcx, rdi
0x180010752  mov     rax, rbx
0x180010755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001075a  mov     ebx, eax
0x18001075c  test    eax, eax
0x18001075e  js      loc_180010A05
0x180010764  mov     rcx, [rbp+57h+var_80]
0x180010768  mov     rax, [rcx]
0x18001076b  lea     r8, [rbp+57h+pvar]
0x18001076f  lea     rdx, PKEY_AudioEndpoint_FormFactor
0x180010776  mov     rax, [rax+28h]
0x18001077a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001077f  mov     ebx, eax
0x180010781  test    eax, eax
0x180010783  js      loc_180010842
0x180010789  cmp     word ptr [rbp+57h+pvar], 13h
0x18001078e  jnz     loc_180010B13
0x180010794  mov     edi, dword ptr [rbp+57h+pvar+8]
0x180010797  mov     rcx, [rbp+57h+var_78]
0x18001079b  mov     rax, [rcx]
0x18001079e  lea     rdx, [rbp+57h+var_30]
0x1800107a2  mov     rax, [rax+38h]
0x1800107a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107ab  mov     ebx, eax
0x1800107ad  test    eax, eax
0x1800107af  js      loc_1800108AF
0x1800107b5  movaps  xmm0, [rbp+57h+var_30]
0x1800107b9  movdqa  xmmword ptr [rbp+57h+Buf1.Data1], xmm0
0x1800107be  mov     edx, [rbp+57h+var_68]; enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011
0x1800107c1  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800107c5  call    ?GetEndpointDescriptorRoot@@YAHU_GUID@@W4__MIDL___MIDL_itf_devicetopology_0000_0000_0011@@@Z; GetEndpointDescriptorRoot(_GUID,__MIDL___MIDL_itf_devicetopology_0000_0000_0011)
0x1800107ca  cmp     eax, 0FFFFFFFFh
0x1800107cd  jz      short loc_180010838
0x1800107cf  cdqe
0x1800107d1  lea     rcx, [rax+rax*2]
0x1800107d5  add     rcx, rcx
0x1800107d8  lea     rax, qword_18006A170
0x1800107df  cmp     [rax+rcx*8], edi
0x1800107e2  jnz     short loc_180010838
0x1800107e4  lea     rcx, [rbp+57h+pvar]; pvar
0x1800107e8  call    cs:__imp_PropVariantClear
0x1800107ee  nop
0x1800107ef  mov     rcx, [rbp+57h+var_80]
0x1800107f3  test    rcx, rcx
0x1800107f6  jz      short loc_180010805
0x1800107f8  mov     rax, [rcx]
0x1800107fb  mov     rax, [rax+10h]
0x1800107ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010804  nop
0x180010805  mov     rcx, [rbp+57h+var_78]
0x180010809  test    rcx, rcx
0x18001080c  jz      short loc_18001081B
0x18001080e  mov     rax, [rcx]
0x180010811  mov     rax, [rax+10h]
0x180010815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001081a  nop
0x18001081b  mov     rcx, [rbp+57h+var_70]
0x18001081f  test    rcx, rcx
0x180010822  jz      short loc_180010831
0x180010824  mov     rax, [rcx]
0x180010827  mov     rax, [rax+10h]
0x18001082b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010830  nop
0x180010831  xor     eax, eax
0x180010833  jmp     loc_180010707
0x180010838  mov     edx, 0BE2h
0x18001083d  jmp     loc_1800106C3
0x180010842  mov     rcx, [rbp+5Fh]; this
0x180010846  mov     r9d, ebx; char *
0x180010849  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180010850  mov     edx, 0BD7h; void *
0x180010855  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001085a  nop
0x18001085b  lea     rcx, [rbp+57h+pvar]; pvar
0x18001085f  call    cs:__imp_PropVariantClear
0x180010865  nop
0x180010866  mov     rcx, [rbp+57h+var_80]
0x18001086a  test    rcx, rcx
0x18001086d  jz      short loc_18001087C
0x18001086f  mov     rax, [rcx]
0x180010872  mov     rax, [rax+10h]
0x180010876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001087b  nop
0x18001087c  mov     rcx, [rbp+57h+var_78]
0x180010880  test    rcx, rcx
0x180010883  jz      short loc_180010892
0x180010885  mov     rax, [rcx]
0x180010888  mov     rax, [rax+10h]
0x18001088c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010891  nop
0x180010892  mov     rcx, [rbp+57h+var_70]
0x180010896  test    rcx, rcx
0x180010899  jz      short loc_1800108A8
0x18001089b  mov     rax, [rcx]
0x18001089e  mov     rax, [rax+10h]
0x1800108a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108a7  nop
0x1800108a8  mov     eax, ebx
0x1800108aa  jmp     loc_180010707
0x1800108af  mov     rcx, [rbp+5Fh]; this
0x1800108b3  mov     r9d, ebx; char *
0x1800108b6  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x1800108bd  mov     edx, 0BDDh; void *
0x1800108c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800108c7  nop
0x1800108c8  lea     rcx, [rbp+57h+pvar]; pvar
0x1800108cc  call    cs:__imp_PropVariantClear
0x1800108d2  nop
0x1800108d3  mov     rcx, [rbp+57h+var_80]
0x1800108d7  test    rcx, rcx
0x1800108da  jz      short loc_1800108E9
0x1800108dc  mov     rax, [rcx]
0x1800108df  mov     rax, [rax+10h]
0x1800108e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108e8  nop
0x1800108e9  mov     rcx, [rbp+57h+var_78]
0x1800108ed  test    rcx, rcx
0x1800108f0  jz      short loc_1800108FF
0x1800108f2  mov     rax, [rcx]
0x1800108f5  mov     rax, [rax+10h]
0x1800108f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108fe  nop
0x1800108ff  mov     rcx, [rbp+57h+var_70]
0x180010903  test    rcx, rcx
0x180010906  jz      short loc_180010915
0x180010908  mov     rax, [rcx]
0x18001090b  mov     rax, [rax+10h]
0x18001090f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010914  nop
0x180010915  mov     eax, ebx
0x180010917  jmp     loc_180010707
0x18001091c  cmp     [rbp+57h+var_68], 0
0x180010920  jnz     loc_1800106BE
0x180010926  jmp     loc_180010731
0x18001092b  mov     rcx, [rbp+5Fh]; this
0x18001092f  mov     r9d, esi; char *
0x180010932  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180010939  mov     edx, 0BCBh; void *
0x18001093e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010943  nop
0x180010944  lea     rcx, [rbp+57h+pvar]; pvar
0x180010948  call    cs:__imp_PropVariantClear
0x18001094e  nop
0x18001094f  mov     rcx, [rbp+57h+var_80]
0x180010953  test    rcx, rcx
0x180010956  jz      short loc_180010965
0x180010958  mov     rax, [rcx]
0x18001095b  mov     rax, [rax+10h]
0x18001095f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010964  nop
0x180010965  mov     rcx, [rbp+57h+var_78]
0x180010969  test    rcx, rcx
0x18001096c  jz      short loc_18001097B
0x18001096e  mov     rax, [rcx]
0x180010971  mov     rax, [rax+10h]
0x180010975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001097a  nop
0x18001097b  mov     rcx, [rbp+57h+var_70]
0x18001097f  test    rcx, rcx
0x180010982  jz      short loc_180010991
0x180010984  mov     rax, [rcx]
0x180010987  mov     rax, [rax+10h]
0x18001098b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010990  nop
0x180010991  mov     eax, esi
0x180010993  jmp     loc_180010707
0x180010998  mov     rcx, [rbp+5Fh]; this
0x18001099c  mov     r9d, esi; char *
0x18001099f  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x1800109a6  mov     edx, 0BC7h; void *
0x1800109ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800109b0  nop
0x1800109b1  lea     rcx, [rbp+57h+pvar]; pvar
0x1800109b5  call    cs:__imp_PropVariantClear
0x1800109bb  nop
0x1800109bc  mov     rcx, [rbp+57h+var_80]
0x1800109c0  test    rcx, rcx
0x1800109c3  jz      short loc_1800109D2
0x1800109c5  mov     rax, [rcx]
0x1800109c8  mov     rax, [rax+10h]
0x1800109cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109d1  nop
0x1800109d2  mov     rcx, [rbp+57h+var_78]
0x1800109d6  test    rcx, rcx
0x1800109d9  jz      short loc_1800109E8
0x1800109db  mov     rax, [rcx]
0x1800109de  mov     rax, [rax+10h]
0x1800109e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109e7  nop
0x1800109e8  mov     rcx, [rbp+57h+var_70]
0x1800109ec  test    rcx, rcx
0x1800109ef  jz      short loc_1800109FE
  ... truncated ...
```
