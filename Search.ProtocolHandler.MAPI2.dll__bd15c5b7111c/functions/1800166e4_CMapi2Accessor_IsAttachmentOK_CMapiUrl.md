# CMapi2Accessor::IsAttachmentOK(CMapiUrl &)

- ea: `0x1800166e4`
- end: `0x1800168be`
- name: `?IsAttachmentOK@CMapi2Accessor@@QEAAJAEAVCMapiUrl@@@Z`
- size: `474`
- prototype: `__int64 __fastcall(CMapi2Accessor *__hidden this, struct CMapiUrl *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016044`
- `0x18001afa8`

## callees

- `0x18000ad14`
- `0x18000e658`
- `0x18000f1c4`
- `0x180011884`
- `0x1800122d8`
- `0x1800143b4`
- `0x1800149cc`
- `0x180014b6c`
- `0x1800166e4`
- `0x180016948`
- `0x1800172fc`
- `0x18003f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016867`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016867`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016742`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016742`

## pseudocode

```c
__int64 __fastcall CMapi2Accessor::IsAttachmentOK(CMapi2Accessor *this, struct CMapiUrl *a2)
{
  int v3; // eax
  unsigned int v4; // edi
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rbx
  int *v8; // rsi
  __int64 v9; // rbx
  __int64 v10; // rbx
  ATL::CStringData *v11; // rcx
  const wchar_t *v12; // rax
  const wchar_t **v13; // rsi
  ATL::CStringData *v14; // rcx
  __int64 v16; // [rsp+30h] [rbp-10h] BYREF
  __int64 v17; // [rsp+38h] [rbp-8h] BYREF
  __int64 v18; // [rsp+70h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+38h] BYREF

  v3 = CMapi2Accessor::CheckAttachmentSecurity(this, a2);
  v4 = v3;
  if ( v3 < 0 && v3 != -2147216891 )
  {
    ppv = 0;
    CMapiUrl::AttachmentName(a2, &v16);
    if ( CoCreateInstance(&rclsid, 0, 0x17u, &GUID_00000000_0000_0000_c000_000000000046, &ppv) >= 0 )
    {
      v18 = 0;
      ATL::CComQIPtr<IAttachmentExecute,&__s_GUID const _GUID_73db1241_1e85_4581_8e4f_a81e1d0f8c57>::operator=(
        &v18,
        ppv);
      if ( v18 )
      {
        (*(void (__fastcall **)(__int64, GUID *))(*(_QWORD *)v18 + 32LL))(
          v18,
          &GUID_9e175baf_f52a_11d8_b9a5_505054503030);
        v10 = v16;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 48LL))(v18, v16);
        v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 72LL))(v18);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
        v11 = (ATL::CStringData *)(v10 - 24);
LABEL_22:
        ATL::CStringData::Release(v11);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
        return v4;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
    }
    v4 = 0;
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
      &v18,
      &v16);
    v5 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::ReverseFind(&v18, 46);
    if ( v5 < 0 )
    {
      v14 = (ATL::CStringData *)(v18 - 24);
    }
    else
    {
      v6 = *(_QWORD *)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Mid(
                        &v18,
                        &v17,
                        (unsigned int)(v5 + 1));
      v7 = v18;
      v8 = (int *)(v18 - 24);
      if ( v6 - 24 != v18 - 24 )
      {
        if ( v8[4] >= 0 && *(_QWORD *)(v6 - 24) == *(_QWORD *)v8 )
        {
          v9 = ATL::CSimpleStringT<wchar_t,0>::CloneData();
          ATL::CStringData::Release((ATL::CStringData *)v8);
          v7 = v9 + 24;
        }
        else
        {
          ATL::CSimpleStringT<wchar_t,0>::SetString(&v18, v6, *(unsigned int *)(v6 - 16));
          v7 = v18;
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
      v12 = L"ade";
      if ( L"ade" )
      {
        v13 = (const wchar_t **)off_180040FD0;
        while ( (unsigned int)_o__wcsicmp(v7, v12) )
        {
          v12 = *++v13;
          if ( !*v13 )
            goto LABEL_19;
        }
        v4 = -2147216891;
      }
LABEL_19:
      v14 = (ATL::CStringData *)(v7 - 24);
    }
    ATL::CStringData::Release(v14);
    v11 = (ATL::CStringData *)(v16 - 24);
    goto LABEL_22;
  }
  return v4;
}

```

## disassembly

```asm
0x1800166e4  mov     [rsp-18h+arg_0], rbx
0x1800166e9  push    rbp
0x1800166ea  push    rsi
0x1800166eb  push    rdi
0x1800166ec  mov     rbp, rsp
0x1800166ef  sub     rsp, 40h
0x1800166f3  mov     rbx, rdx
0x1800166f6  call    ?CheckAttachmentSecurity@CMapi2Accessor@@AEAAJAEAVCMapiUrl@@@Z; CMapi2Accessor::CheckAttachmentSecurity(CMapiUrl &)
0x1800166fb  mov     edi, eax
0x1800166fd  test    eax, eax
0x1800166ff  jns     loc_1800168AF
0x180016705  cmp     eax, 80041205h
0x18001670a  jz      loc_1800168AF
0x180016710  mov     [rbp+arg_18], 0
0x180016718  lea     rdx, [rbp+var_10]
0x18001671c  mov     rcx, rbx
0x18001671f  call    ?AttachmentName@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::AttachmentName(void)
0x180016724  nop
0x180016725  lea     rax, [rbp+arg_18]
0x180016729  mov     [rsp+40h+ppv], rax; ppv
0x18001672e  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180016735  xor     edx, edx; pUnkOuter
0x180016737  lea     r8d, [rdx+17h]; dwClsContext
0x18001673b  lea     rcx, rclsid; rclsid
0x180016742  call    cs:__imp_CoCreateInstance
0x180016748  test    eax, eax
0x18001674a  js      short loc_180016773
0x18001674c  mov     [rbp+arg_10], 0
0x180016754  mov     rdx, [rbp+arg_18]
0x180016758  lea     rcx, [rbp+arg_10]
0x18001675c  call    ??4?$CComQIPtr@UIAttachmentExecute@@$1?_GUID_73db1241_1e85_4581_8e4f_a81e1d0f8c57@@3U__s_GUID@@B@ATL@@QEAAPEAUIAttachmentExecute@@PEAUIUnknown@@@Z; ATL::CComQIPtr<IAttachmentExecute,&__s_GUID const _GUID_73db1241_1e85_4581_8e4f_a81e1d0f8c57>::operator=(IUnknown *)
0x180016761  mov     rcx, [rbp+arg_10]
0x180016765  test    rcx, rcx
0x180016768  jnz     short loc_1800167E4
0x18001676a  lea     rcx, [rbp+arg_10]
0x18001676e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180016773  xor     edi, edi
0x180016775  lea     rdx, [rbp+var_10]
0x180016779  lea     rcx, [rbp+arg_10]
0x18001677d  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180016782  nop
0x180016783  lea     edx, [rdi+2Eh]
0x180016786  lea     rcx, [rbp+arg_10]
0x18001678a  call    ?ReverseFind@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBAH_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::ReverseFind(wchar_t)
0x18001678f  test    eax, eax
0x180016791  js      loc_18001688A
0x180016797  lea     r8d, [rax+1]
0x18001679b  lea     rdx, [rbp+var_8]
0x18001679f  lea     rcx, [rbp+arg_10]
0x1800167a3  call    ?Mid@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Mid(int)
0x1800167a8  nop
0x1800167a9  mov     rdx, [rax]
0x1800167ac  lea     rcx, [rdx-18h]
0x1800167b0  mov     rbx, [rbp+arg_10]
0x1800167b4  lea     rsi, [rbx-18h]
0x1800167b8  cmp     rcx, rsi
0x1800167bb  jz      loc_180016841
0x1800167c1  cmp     [rsi+10h], edi
0x1800167c4  jl      short loc_180016830
0x1800167c6  mov     rax, [rsi]
0x1800167c9  cmp     [rcx], rax
0x1800167cc  jnz     short loc_180016830
0x1800167ce  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x1800167d3  mov     rbx, rax
0x1800167d6  mov     rcx, rsi; this
0x1800167d9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800167de  add     rbx, 18h
0x1800167e2  jmp     short loc_180016841
0x1800167e4  mov     rax, [rcx]
0x1800167e7  lea     rdx, _GUID_9e175baf_f52a_11d8_b9a5_505054503030
0x1800167ee  mov     rax, [rax+20h]
0x1800167f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167f7  mov     rcx, [rbp+arg_10]
0x1800167fb  mov     rax, [rcx]
0x1800167fe  mov     rbx, [rbp+var_10]
0x180016802  mov     rdx, rbx
0x180016805  mov     rax, [rax+30h]
0x180016809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001680e  mov     rcx, [rbp+arg_10]
0x180016812  mov     rax, [rcx]
0x180016815  mov     rax, [rax+48h]
0x180016819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001681e  mov     edi, eax
0x180016820  lea     rcx, [rbp+arg_10]
0x180016824  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180016829  nop
0x18001682a  lea     rcx, [rbx-18h]
0x18001682e  jmp     short loc_1800168A0
0x180016830  mov     r8d, [rdx-10h]
0x180016834  lea     rcx, [rbp+arg_10]
0x180016838  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18001683d  mov     rbx, [rbp+arg_10]
0x180016841  mov     rcx, [rbp+var_8]
0x180016845  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180016849  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001684e  mov     rax, cs:off_180040FD0; "ade"
0x180016855  test    rax, rax
0x180016858  jz      short loc_180016884
0x18001685a  lea     rsi, off_180040FD0; "ade"
0x180016861  mov     rdx, rax
0x180016864  mov     rcx, rbx
0x180016867  call    cs:__imp__o__wcsicmp
0x18001686d  test    eax, eax
0x18001686f  jz      short loc_18001687F
0x180016871  add     rsi, 8
0x180016875  mov     rax, [rsi]
0x180016878  test    rax, rax
0x18001687b  jnz     short loc_180016861
0x18001687d  jmp     short loc_180016884
0x18001687f  mov     edi, 80041205h
0x180016884  lea     rcx, [rbx-18h]
0x180016888  jmp     short loc_180016892
0x18001688a  mov     rcx, [rbp+arg_10]
0x18001688e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180016892  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180016897  nop
0x180016898  mov     rcx, [rbp+var_10]
0x18001689c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800168a0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800168a5  nop
0x1800168a6  lea     rcx, [rbp+arg_18]
0x1800168aa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800168af  mov     eax, edi
0x1800168b1  mov     rbx, [rsp+40h+arg_0]
0x1800168b6  add     rsp, 40h
0x1800168ba  pop     rdi
0x1800168bb  pop     rsi
0x1800168bc  pop     rbp
0x1800168bd  retn
```
