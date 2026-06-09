# CAvEndpointBuilder::PopulateBtLeAudioProperties(IPnpDevnode *,IPropertyStore *)

- ea: `0x1800513ac`
- end: `0x180051ad9`
- name: `?PopulateBtLeAudioProperties@CAvEndpointBuilder@@AEAAJPEAUIPnpDevnode@@PEAUIPropertyStore@@@Z`
- size: `1837`
- prototype: `__int64 __fastcall(CAvEndpointBuilder *__hidden this, struct IPnpDevnode *, struct IPropertyStore *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004a344`

## callees

- `0x180005e0c`
- `0x180006b0c`
- `0x180008404`
- `0x180010da8`
- `0x180021030`
- `0x180024fd4`
- `0x18003e920`
- `0x18003edfc`
- `0x180048b38`
- `0x1800513ac`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800514c0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800514c0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005150d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800515b8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800516d1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800516dd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800516e8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800519c3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800519cf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800519da`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180051a4c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005150d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800515b8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800516d1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800516dd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800516e8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800519c3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800519cf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800519da`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180051a4c`

## string_xrefs

- `0x1800515f1`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180051613`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18005163f`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x1800516b8`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180051a10`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180051a36`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180051a5e`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180051a86`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CAvEndpointBuilder::PopulateBtLeAudioProperties(
        CAvEndpointBuilder *this,
        struct IPnpDevnode *a2,
        struct IPropertyStore *a3)
{
  struct IPnpDevnode *v4; // r9
  __int64 v5; // rbx
  int v6; // eax
  unsigned int v7; // edi
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  unsigned int v11; // edi
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, PROPVARIANT, struct IPnpDevnode **); // rdi
  __int64 v17; // rdx
  PROPVARIANT *v18; // rcx
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r9
  __int64 v22; // rax
  rsize_t v23; // rsi
  __int64 v24; // rdi
  wchar_t *v25; // rax
  wchar_t *v26; // rbx
  __int64 v27; // r9
  int v28; // eax
  __int64 v29; // r9
  __int64 v30; // rdx
  int v31; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  __int64 v34; // [rsp+30h] [rbp-D0h] BYREF
  struct IPnpDevnode *v35; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v36; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v37; // [rsp+48h] [rbp-B8h] BYREF
  PROPVARIANT v38[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h]
  PROPVARIANT v40[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h]
  PROPVARIANT Source[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v43; // [rsp+90h] [rbp-70h]
  __int64 v44; // [rsp+98h] [rbp-68h] BYREF
  __int64 v45; // [rsp+A0h] [rbp-60h] BYREF
  PROPVARIANT v46[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v47; // [rsp+B8h] [rbp-48h]
  PROPVARIANT pvar[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v49; // [rsp+D0h] [rbp-30h]
  __int128 v50; // [rsp+D8h] [rbp-28h] BYREF
  const wchar_t **v51; // [rsp+E8h] [rbp-18h]
  _QWORD v52[3]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v53[3]; // [rsp+108h] [rbp+8h] BYREF
  __int128 v54; // [rsp+120h] [rbp+20h] BYREF
  __int64 v55; // [rsp+130h] [rbp+30h]
  __int128 v56; // [rsp+138h] [rbp+38h] BYREF
  __int64 v57; // [rsp+148h] [rbp+48h]
  __int128 v58; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v4 = a2;
  v35 = a2;
  if ( a2 )
  {
    (*(void (__fastcall **)(struct IPnpDevnode *))(*(_QWORD *)a2 + 8LL))(a2);
    v4 = v35;
  }
  v5 = 0;
  v45 = 0;
  while ( 1 )
  {
    v36 = 0;
    v6 = (**(__int64 (__fastcall ***)(struct IPnpDevnode *, GUID *, __int64 **))v4)(
           v4,
           &GUID_d666063f_1587_4e43_81f1_b948e807363f,
           &v36);
    v7 = v6;
    if ( v6 < 0 )
      break;
    v34 = 0;
    v8 = *v36;
    v34 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v8 + 32))(v36, 0, &v34);
    v7 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A47,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v9,
        bIgnoreCase);
      goto LABEL_65;
    }
    *(_OWORD *)pvar = 0;
    v49 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v34 + 40LL))(
            v34,
            &DEVPKEY_Device_CompatibleIds,
            pvar);
    v7 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A4C,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v10,
        bIgnoreCase);
      v18 = pvar;
      goto LABEL_63;
    }
    if ( LOWORD(pvar[0]) == 4127 )
    {
      v11 = 0;
      if ( LODWORD(pvar[1]) )
      {
        while ( CompareStringOrdinal(*(LPCWCH *)(v49 + 8LL * v11), -1, L"APXENUM\\APXUNIT", -1, 1) != 2 )
        {
          if ( ++v11 >= LODWORD(pvar[1]) )
            goto LABEL_14;
        }
        v5 = v34;
        v45 = v34;
        if ( v34 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 8LL))(v34);
      }
    }
LABEL_14:
    PropVariantClear(pvar);
    if ( v5 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
      *(_OWORD *)Source = 0;
      v43 = 0;
      *(_OWORD *)v38 = 0;
      v39 = 0;
      *(_OWORD *)v40 = 0;
      v41 = 0;
      v19 = (*(__int64 (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v5 + 40LL))(
              v5,
              &DEVPKEY_Device_ContainerId,
              Source);
      v7 = v19;
      if ( v19 < 0 )
      {
        v20 = 6774;
        goto LABEL_29;
      }
      if ( LOWORD(Source[0]) != 72 )
      {
        v7 = -2147418113;
        v21 = 2147549183LL;
        v20 = 6775;
        goto LABEL_30;
      }
      v19 = (*(__int64 (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v5 + 40LL))(
              v5,
              &DEVPKEY_Device_InstallDate,
              v40);
      v7 = v19;
      if ( v19 < 0 )
      {
        v20 = 6777;
LABEL_29:
        v21 = (unsigned int)v19;
        goto LABEL_30;
      }
      if ( LOWORD(v40[0]) != 64 )
      {
        v7 = -2147418113;
        v21 = 2147549183LL;
        v20 = 6778;
        goto LABEL_30;
      }
      v19 = (*(__int64 (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v5 + 40LL))(
              v5,
              &DEVPKEY_Device_InstanceId,
              v38);
      v7 = v19;
      if ( v19 < 0 )
      {
        v20 = 6780;
        goto LABEL_29;
      }
      if ( LOWORD(v38[0]) == 31 )
      {
        v22 = -1;
        do
          ++v22;
        while ( *((_WORD *)v38[1] + v22) );
        v23 = 2 * v22;
        v24 = 2 * v22 + 24;
        v25 = (wchar_t *)operator new[](v24, (const struct std::nothrow_t *)&std::nothrow);
        v26 = v25;
        v37 = v25;
        if ( v25 )
        {
          memcpy_s(v25, v24, Source[1], 0x10u);
          memcpy_s(v26 + 8, v24 - 16, &v40[1], 8u);
          v27 = -1;
          do
            ++v27;
          while ( *((_WORD *)v38[1] + v27) );
          memcpy_s(v26 + 12, v23, v38[1], 2 * v27);
          v58 = 0;
          v28 = GenerateClass5Guid(BLUETOOTHLE_AUDIO_RESOURCE_MANAGER, v26, (unsigned int)v24, &v58);
          v7 = v28;
          if ( v28 >= 0 )
          {
            v52[2] = 0;
            v52[0] = 72;
            v52[1] = &v58;
            v31 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, _QWORD *))a3->lpVtbl->SetValue)(
                    a3,
                    PKEY_Endpoint_CustomResourceManagerContext,
                    v52);
            v7 = v31;
            if ( v31 >= 0 )
            {
              std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v37);
              v53[2] = 0;
              v53[0] = 72;
              v53[1] = BLUETOOTHLE_AUDIO_RESOURCE_MANAGER;
              v19 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, _QWORD *))a3->lpVtbl->SetValue)(
                      a3,
                      PKEY_Endpoint_CustomResourceManager,
                      v53);
              v7 = v19;
              if ( v19 >= 0 )
              {
                v37 = L"{C18E2F7E-933D-4965-B7D1-1EEF228D2AF3}";
                v50 = 0;
                LOWORD(v50) = 4127;
                DWORD2(v50) = 1;
                v51 = &v37;
                v19 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))a3->lpVtbl->SetValue)(
                        a3,
                        PKEY_Constrained_APO_ProcessingMode_List_For_Streaming,
                        &v50);
                v7 = v19;
                if ( v19 >= 0 )
                {
                  v54 = 0;
                  v55 = 0;
                  LOWORD(v54) = 11;
                  WORD4(v54) = -1;
                  v19 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))a3->lpVtbl->SetValue)(
                          a3,
                          PKEY_ConnectorProcessingModes_Available_When_EnhancementsDisabled,
                          &v54);
                  v7 = v19;
                  if ( v19 >= 0 )
                  {
                    v56 = 0;
                    v57 = 0;
                    LOWORD(v56) = 11;
                    WORD4(v56) = -1;
                    v19 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))a3->lpVtbl->SetValue)(
                            a3,
                            PKEY_Endpoint_IsSideband,
                            &v56);
                    v7 = v19;
                    if ( v19 >= 0 )
                    {
                      PropVariantClear(v40);
                      PropVariantClear(v38);
                      PropVariantClear(Source);
                      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
                      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
                      return 0;
                    }
                    v20 = 6844;
                  }
                  else
                  {
                    v20 = 6835;
                  }
                }
                else
                {
                  v20 = 6827;
                }
              }
              else
              {
                v20 = 6816;
              }
              goto LABEL_29;
            }
            v29 = (unsigned int)v31;
            v30 = 6808;
          }
          else
          {
            v29 = (unsigned int)v28;
            v30 = 6803;
          }
        }
        else
        {
          v7 = -2147024882;
          v29 = 2147942414LL;
          v30 = 6790;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)v29,
          bIgnoreCase);
        std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v37);
      }
      else
      {
        v7 = -2147418113;
        v21 = 2147549183LL;
        v20 = 6781;
LABEL_30:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)v21,
          bIgnoreCase);
      }
      PropVariantClear(v40);
      PropVariantClear(v38);
      PropVariantClear(Source);
      goto LABEL_68;
    }
    wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v35);
    *(_OWORD *)v46 = 0;
    v47 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v34 + 40LL))(
            v34,
            &DEVPKEY_Device_Parent,
            v46);
    v7 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A62,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v12,
        bIgnoreCase);
LABEL_26:
      v18 = v46;
LABEL_63:
      PropVariantClear(v18);
LABEL_65:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
      goto LABEL_67;
    }
    if ( LOWORD(v46[0]) == 31 )
    {
      v44 = 0;
      v14 = wil::com_query_to_nothrow<IPnpDeviceEnumerator,IMMDeviceEnumerator * &>(v13, &v44);
      v7 = v14;
      if ( v14 < 0 )
      {
        v17 = 6759;
        goto LABEL_24;
      }
      v15 = v44;
      v16 = *(__int64 (__fastcall **)(__int64, PROPVARIANT, struct IPnpDevnode **))(*(_QWORD *)v44 + 64LL);
      wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v35);
      v14 = v16(v15, v46[1], &v35);
      v7 = v14;
      if ( v14 < 0 )
      {
        v17 = 6760;
LABEL_24:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)(unsigned int)v14,
          bIgnoreCase);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v44);
        goto LABEL_26;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v44);
    }
    PropVariantClear(v46);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
    v4 = v35;
    if ( !v35 )
    {
      v7 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A6F,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)0x8000FFFFLL,
        bIgnoreCase);
      goto LABEL_68;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1A44,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
    (const char *)(unsigned int)v6,
    bIgnoreCase);
LABEL_67:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
LABEL_68:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
  return v7;
}

```

## disassembly

```asm
0x1800513ac  push    rbp
0x1800513ae  push    rbx
0x1800513af  push    rsi
0x1800513b0  push    rdi
0x1800513b1  push    r12
0x1800513b3  push    r13
0x1800513b5  push    r14
0x1800513b7  push    r15
0x1800513b9  lea     rbp, [rsp-78h]
0x1800513be  sub     rsp, 178h
0x1800513c5  mov     rax, cs:__security_cookie
0x1800513cc  xor     rax, rsp
0x1800513cf  mov     [rbp+0B0h+var_50], rax
0x1800513d3  mov     r14, r8
0x1800513d6  mov     r9, rdx
0x1800513d9  mov     [rsp+1B0h+var_178], rdx
0x1800513de  xor     r15d, r15d
0x1800513e1  test    rdx, rdx
0x1800513e4  jz      short loc_1800513FA
0x1800513e6  mov     rax, [rdx]
0x1800513e9  mov     rcx, rdx
0x1800513ec  mov     rax, [rax+8]
0x1800513f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800513f5  mov     r9, [rsp+1B0h+var_178]
0x1800513fa  mov     rbx, r15
0x1800513fd  mov     [rbp+0B0h+var_110], rbx
0x180051401  mov     esi, 101Fh
0x180051406  or      r12, 0FFFFFFFFFFFFFFFFh
0x18005140a  mov     [rsp+1B0h+var_170], r15
0x18005140f  mov     rax, [r9]
0x180051412  lea     r8, [rsp+1B0h+var_170]
0x180051417  lea     rdx, _GUID_d666063f_1587_4e43_81f1_b948e807363f
0x18005141e  mov     rcx, r9
0x180051421  mov     rax, [rax]
0x180051424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051429  mov     edi, eax
0x18005142b  test    eax, eax
0x18005142d  js      loc_180051A7C
0x180051433  mov     [rsp+1B0h+var_180], r15
0x180051438  mov     rcx, [rsp+1B0h+var_170]
0x18005143d  mov     rax, [rcx]
0x180051440  mov     [rsp+1B0h+var_180], r15
0x180051445  lea     r8, [rsp+1B0h+var_180]
0x18005144a  xor     edx, edx
0x18005144c  mov     rax, [rax+20h]
0x180051450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051455  mov     edi, eax
0x180051457  test    eax, eax
0x180051459  js      loc_180051A54
0x18005145f  xorps   xmm0, xmm0
0x180051462  xor     eax, eax
0x180051464  movups  xmmword ptr [rbp+0B0h+pvar], xmm0
0x180051468  mov     [rbp+0B0h+var_E0], rax
0x18005146c  mov     rcx, [rsp+1B0h+var_180]
0x180051471  mov     rax, [rcx]
0x180051474  lea     r8, [rbp+0B0h+pvar]
0x180051478  lea     rdx, DEVPKEY_Device_CompatibleIds
0x18005147f  mov     rax, [rax+28h]
0x180051483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051488  mov     edi, eax
0x18005148a  test    eax, eax
0x18005148c  js      loc_180051A2C
0x180051492  cmp     word ptr [rbp+0B0h+pvar], si
0x180051496  jnz     short loc_180051509
0x180051498  mov     edi, r15d
0x18005149b  cmp     dword ptr [rbp+0B0h+pvar+8], r15d
0x18005149f  jbe     short loc_180051509
0x1800514a1  mov     eax, edi
0x1800514a3  mov     [rsp+1B0h+bIgnoreCase], 1; int
0x1800514ab  mov     r9d, r12d; cchCount2
0x1800514ae  lea     r8, aApxenumApxunit; "APXENUM\\APXUNIT"
0x1800514b5  mov     edx, r12d; cchCount1
0x1800514b8  mov     rcx, [rbp+0B0h+var_E0]
0x1800514bc  mov     rcx, [rcx+rax*8]; lpString1
0x1800514c0  call    cs:__imp_CompareStringOrdinal
0x1800514c6  cmp     eax, 2
0x1800514c9  jz      short loc_1800514D4
0x1800514cb  inc     edi
0x1800514cd  cmp     edi, dword ptr [rbp+0B0h+pvar+8]
0x1800514d0  jb      short loc_1800514A1
0x1800514d2  jmp     short loc_180051509
0x1800514d4  mov     rcx, [rsp+1B0h+var_180]
0x1800514d9  mov     rdi, rbx
0x1800514dc  mov     rbx, rcx
0x1800514df  mov     [rbp+0B0h+var_110], rcx
0x1800514e3  test    rcx, rcx
0x1800514e6  jz      short loc_1800514F4
0x1800514e8  mov     rax, [rcx]
0x1800514eb  mov     rax, [rax+8]
0x1800514ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800514f4  test    rdi, rdi
0x1800514f7  jz      short loc_180051509
0x1800514f9  mov     rax, [rdi]
0x1800514fc  mov     rcx, rdi
0x1800514ff  mov     rax, [rax+10h]
0x180051503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051508  nop
0x180051509  lea     rcx, [rbp+0B0h+pvar]; pvar
0x18005150d  call    cs:__imp_PropVariantClear
0x180051513  test    rbx, rbx
0x180051516  jnz     loc_18005165A
0x18005151c  lea     rcx, [rsp+1B0h+var_178]
0x180051521  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x180051526  xorps   xmm0, xmm0
0x180051529  xor     eax, eax
0x18005152b  movups  xmmword ptr [rbp+0B0h+var_108], xmm0
0x18005152f  mov     [rbp+0B0h+var_F8], rax
0x180051533  mov     rcx, [rsp+1B0h+var_180]
0x180051538  mov     rax, [rcx]
0x18005153b  lea     r8, [rbp+0B0h+var_108]
0x18005153f  lea     rdx, DEVPKEY_Device_Parent
0x180051546  mov     rax, [rax+28h]
0x18005154a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005154f  mov     edi, eax
0x180051551  test    eax, eax
0x180051553  js      loc_180051635
0x180051559  cmp     word ptr [rbp+0B0h+var_108], 1Fh
0x18005155e  jnz     short loc_1800515B4
0x180051560  mov     [rbp+0B0h+var_118], r15
0x180051564  lea     rdx, [rbp+0B0h+var_118]
0x180051568  call    ??$com_query_to_nothrow@UIPnpDeviceEnumerator@@AEAPEAUIMMDeviceEnumerator@@@wil@@YAJAEAPEAUIMMDeviceEnumerator@@PEAPEAUIPnpDeviceEnumerator@@@Z; wil::com_query_to_nothrow<IPnpDeviceEnumerator,IMMDeviceEnumerator * &>(IMMDeviceEnumerator * &,IPnpDeviceEnumerator * *)
0x18005156d  mov     edi, eax
0x18005156f  test    eax, eax
0x180051571  js      loc_18005160E
0x180051577  mov     rsi, [rbp+0B0h+var_118]
0x18005157b  mov     rax, [rsi]
0x18005157e  mov     rdi, [rax+40h]
0x180051582  lea     rcx, [rsp+1B0h+var_178]
0x180051587  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x18005158c  lea     r8, [rsp+1B0h+var_178]
0x180051591  mov     rdx, [rbp+0B0h+var_108+8]
0x180051595  mov     rcx, rsi
0x180051598  mov     rax, rdi
0x18005159b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800515a0  mov     edi, eax
0x1800515a2  test    eax, eax
0x1800515a4  js      short loc_180051607
0x1800515a6  lea     rcx, [rbp+0B0h+var_118]
0x1800515aa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800515af  mov     esi, 101Fh
0x1800515b4  lea     rcx, [rbp+0B0h+var_108]; pvar
0x1800515b8  call    cs:__imp_PropVariantClear
0x1800515be  nop
0x1800515bf  lea     rcx, [rsp+1B0h+var_180]
0x1800515c4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800515c9  nop
0x1800515ca  lea     rcx, [rsp+1B0h+var_170]
0x1800515cf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800515d4  mov     r9, [rsp+1B0h+var_178]
0x1800515d9  test    r9, r9
0x1800515dc  jnz     loc_18005140A
0x1800515e2  mov     rcx, [rbp+0B8h]; this
0x1800515e9  mov     edi, 8000FFFFh
0x1800515ee  mov     r9d, edi; char *
0x1800515f1  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x1800515f8  mov     edx, 1A6Fh; void *
0x1800515fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051602  jmp     loc_180051AA3
0x180051607  mov     edx, 1A68h
0x18005160c  jmp     short loc_180051613
0x18005160e  mov     edx, 1A67h; void *
0x180051613  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18005161a  mov     r9d, eax; char *
0x18005161d  mov     rcx, [rbp+0B8h]; this
0x180051624  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051629  nop
0x18005162a  lea     rcx, [rbp+0B0h+var_118]
0x18005162e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051633  jmp     short loc_180051651
0x180051635  mov     rcx, [rbp+0B8h]; this
0x18005163c  mov     r9d, eax; char *
0x18005163f  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180051646  mov     edx, 1A62h; void *
0x18005164b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051650  nop
0x180051651  lea     rcx, [rbp+0B0h+var_108]
0x180051655  jmp     loc_180051A4C
0x18005165a  lea     rcx, [rsp+1B0h+var_180]
0x18005165f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051664  nop
0x180051665  lea     rcx, [rsp+1B0h+var_170]
0x18005166a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005166f  xorps   xmm0, xmm0
0x180051672  xor     eax, eax
0x180051674  movups  xmmword ptr [rbp+0B0h+Source], xmm0
0x180051678  mov     [rbp+0B0h+var_120], rax
0x18005167c  movups  xmmword ptr [rsp+1B0h+var_160], xmm0
0x180051681  mov     [rsp+1B0h+var_150], rax
0x180051686  movups  xmmword ptr [rsp+1B0h+var_148], xmm0
0x18005168b  mov     [rsp+1B0h+var_138], rax
0x180051690  mov     rax, [rbx]
0x180051693  lea     r8, [rbp+0B0h+Source]
0x180051697  lea     rdx, DEVPKEY_Device_ContainerId
0x18005169e  mov     rcx, rbx
0x1800516a1  mov     rax, [rax+28h]
0x1800516a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516aa  mov     edi, eax
0x1800516ac  test    eax, eax
0x1800516ae  jns     short loc_1800516F3
0x1800516b0  mov     edx, 1A76h; void *
0x1800516b5  mov     r9d, eax; char *
0x1800516b8  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x1800516bf  mov     rcx, [rbp+0B8h]; this
0x1800516c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800516cb  nop
0x1800516cc  lea     rcx, [rsp+1B0h+var_148]; pvar
0x1800516d1  call    cs:__imp_PropVariantClear
0x1800516d7  nop
0x1800516d8  lea     rcx, [rsp+1B0h+var_160]; pvar
0x1800516dd  call    cs:__imp_PropVariantClear
0x1800516e3  nop
0x1800516e4  lea     rcx, [rbp+0B0h+Source]; pvar
0x1800516e8  call    cs:__imp_PropVariantClear
0x1800516ee  jmp     loc_180051AA3
0x1800516f3  mov     r13d, 48h ; 'H'
0x1800516f9  cmp     word ptr [rbp+0B0h+Source], r13w
0x1800516fe  jz      short loc_18005170F
0x180051700  mov     edi, 8000FFFFh
0x180051705  mov     r9d, edi
0x180051708  mov     edx, 1A77h
0x18005170d  jmp     short loc_1800516B8
0x18005170f  mov     rax, [rbx]
0x180051712  lea     r8, [rsp+1B0h+var_148]
0x180051717  lea     rdx, DEVPKEY_Device_InstallDate
0x18005171e  mov     rcx, rbx
0x180051721  mov     rax, [rax+28h]
0x180051725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005172a  mov     edi, eax
0x18005172c  test    eax, eax
0x18005172e  jns     short loc_18005173A
0x180051730  mov     edx, 1A79h
0x180051735  jmp     loc_1800516B5
0x18005173a  cmp     word ptr [rsp+1B0h+var_148], 40h ; '@'
0x180051740  jz      short loc_180051754
0x180051742  mov     edi, 8000FFFFh
0x180051747  mov     r9d, edi
0x18005174a  mov     edx, 1A7Ah
0x18005174f  jmp     loc_1800516B8
0x180051754  mov     rax, [rbx]
0x180051757  lea     r8, [rsp+1B0h+var_160]
0x18005175c  lea     rdx, DEVPKEY_Device_InstanceId
0x180051763  mov     rcx, rbx
0x180051766  mov     rax, [rax+28h]
0x18005176a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005176f  mov     edi, eax
0x180051771  test    eax, eax
0x180051773  jns     short loc_18005177F
0x180051775  mov     edx, 1A7Ch
0x18005177a  jmp     loc_1800516B5
0x18005177f  cmp     word ptr [rsp+1B0h+var_160], 1Fh
0x180051785  jz      short loc_180051799
0x180051787  mov     edi, 8000FFFFh
0x18005178c  mov     r9d, edi
0x18005178f  mov     edx, 1A7Dh
0x180051794  jmp     loc_1800516B8
0x180051799  mov     rcx, [rsp+1B0h+var_160+8]
0x18005179e  mov     rax, r12
0x1800517a1  inc     rax
0x1800517a4  cmp     [rcx+rax*2], r15w
0x1800517a9  jnz     short loc_1800517A1
0x1800517ab  lea     rsi, [rax+rax]
0x1800517af  lea     rdi, [rsi+18h]
0x1800517b3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800517ba  mov     rcx, rdi; unsigned __int64
0x1800517bd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800517c2  mov     rbx, rax
0x1800517c5  mov     [rsp+1B0h+var_168], rax
0x1800517ca  test    rax, rax
0x1800517cd  jz      loc_1800519FC
0x1800517d3  mov     r9d, 10h; SourceSize
0x1800517d9  mov     r8, [rbp+0B0h+Source+8]; Source
0x1800517dd  mov     rdx, rdi; DestinationSize
0x1800517e0  mov     rcx, rax; Destination
0x1800517e3  call    memcpy_s
0x1800517e8  lea     rdx, [rdi-10h]; DestinationSize
0x1800517ec  lea     rcx, [rbx+10h]; Destination
0x1800517f0  mov     r9d, 8; SourceSize
0x1800517f6  lea     r8, [rsp+1B0h+var_148+8]; Source
0x1800517fb  call    memcpy_s
0x180051800  mov     r8, [rsp+1B0h+var_160+8]; Source
0x180051805  mov     r9, r12
0x180051808  inc     r9
0x18005180b  cmp     [r8+r9*2], r15w
0x180051810  jnz     short loc_180051808
0x180051812  add     r9, r9; SourceSize
0x180051815  lea     rcx, [rbx+18h]; Destination
0x180051819  mov     rdx, rsi; DestinationSize
0x18005181c  call    memcpy_s
0x180051821  xorps   xmm0, xmm0
0x180051824  movups  [rbp+0B0h+var_60], xmm0
0x180051828  mov     r8d, edi
0x18005182b  lea     r9, [rbp+0B0h+var_60]
0x18005182f  mov     rdx, rbx
0x180051832  lea     rbx, BLUETOOTHLE_AUDIO_RESOURCE_MANAGER
0x180051839  mov     rcx, rbx
0x18005183c  call    GenerateClass5Guid
0x180051841  mov     edi, eax
0x180051843  test    eax, eax
0x180051845  jns     short loc_180051854
0x180051847  mov     r9d, eax
  ... truncated ...
```
