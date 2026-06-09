# CDefaultDeviceManager::GetDefaultEndpoint(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *,IMMDevice * *)

- ea: `0x18000b258`
- end: `0x18000b744`
- name: `?GetDefaultEndpoint@CDefaultDeviceManager@@QEAAJW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@W4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@PEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@PEAPEAUIMMDevice@@@Z`
- size: `1260`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d400`
- `0x180135780`

## callees

- `0x18000ae1c`
- `0x18000b258`
- `0x18000b860`
- `0x18000b9b0`
- `0x18000ba40`
- `0x18000bb48`
- `0x18004c9a0`
- `0x180058570`
- `0x1800cd8d0`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000b535`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000b575`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000b535`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000b575`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b2e3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b2e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b3e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b5cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b643`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b3e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b5cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b643`
- `MMDevAPI!__imp_GetNeverSetAsDefaultProperty` at `0x18000b3d1`
- `MMDevAPI!__imp_GetNeverSetAsDefaultProperty` at `0x18000b3d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CDefaultDeviceManager::GetDefaultEndpoint(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5)
{
  struct IMMDevice *v7; // rbx
  struct IMMDevice *v8; // rdi
  HRESULT EndpointCreationTime; // esi
  __int64 v10; // r12
  unsigned int v11; // r15d
  unsigned int v12; // r14d
  unsigned int i; // r13d
  unsigned int v14; // ebx
  struct IMMDevice *v15; // rcx
  struct IMMDevice *v16; // rbx
  __int64 v17; // rbx
  struct IMMDevice *v18; // rbx
  struct IMMDevice *v19; // rax
  _QWORD *v20; // rcx
  int v21; // eax
  LPVOID pv; // [rsp+30h] [rbp-91h] BYREF
  struct IMMDevice *v24; // [rsp+38h] [rbp-89h] BYREF
  unsigned int v25; // [rsp+40h] [rbp-81h] BYREF
  struct IMMDevice *v26; // [rsp+48h] [rbp-79h] BYREF
  struct IMMDevice *v27; // [rsp+50h] [rbp-71h] BYREF
  unsigned int v28; // [rsp+58h] [rbp-69h] BYREF
  unsigned int v29; // [rsp+5Ch] [rbp-65h]
  int v30; // [rsp+60h] [rbp-61h] BYREF
  unsigned int v31; // [rsp+64h] [rbp-5Dh]
  FILETIME FileTime1; // [rsp+68h] [rbp-59h] BYREF
  __int64 v33; // [rsp+70h] [rbp-51h] BYREF
  __int64 v34; // [rsp+78h] [rbp-49h]
  LPVOID ppv; // [rsp+80h] [rbp-41h] BYREF
  __int64 v36; // [rsp+88h] [rbp-39h] BYREF
  FILETIME FileTime2; // [rsp+90h] [rbp-31h] BYREF
  FILETIME v38; // [rsp+98h] [rbp-29h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-21h]
  struct IMMDevice *v40; // [rsp+A8h] [rbp-19h]
  unsigned __int16 v41[16]; // [rsp+B0h] [rbp-11h] BYREF

  v39 = a4;
  v29 = a3;
  v31 = a2;
  v34 = a5;
  v28 = 0;
  ppv = 0;
  v33 = 0;
  v7 = 0;
  v27 = 0;
  FileTime2 = 0;
  v8 = 0;
  v40 = 0;
  v38 = 0;
  EndpointCreationTime = CoCreateInstance(
                           &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
                           0,
                           0x17u,
                           &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
                           &ppv);
  if ( EndpointCreationTime >= 0 )
  {
    EndpointCreationTime = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, __int64 *))(*(_QWORD *)ppv + 24LL))(
                             ppv,
                             a2,
                             1,
                             &v33);
    if ( EndpointCreationTime >= 0 )
    {
      EndpointCreationTime = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v33 + 24LL))(v33, &v28);
      if ( EndpointCreationTime >= 0 )
      {
        if ( !v28 )
        {
          EndpointCreationTime = -2147023728;
          goto LABEL_65;
        }
        EndpointCreationTime = StringCchPrintfW(v41, 0xDu, L"Level:%x", a3);
        if ( EndpointCreationTime >= 0 )
        {
          v10 = -1;
          v11 = 0;
          v12 = 0;
          for ( i = 0; i < v28; ++i )
          {
            v24 = 0;
            v26 = 0;
            pv = 0;
            FileTime1 = 0;
            v36 = 0;
            v25 = 0;
            EndpointCreationTime = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IMMDevice **))(*(_QWORD *)v33 + 32LL))(
                                     v33,
                                     i,
                                     &v24);
            if ( EndpointCreationTime < 0 )
            {
              CoTaskMemFree(pv);
              pv = 0;
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v26);
              if ( v24 )
                ((void (__fastcall *)(struct IMMDevice *))v24->lpVtbl->Release)(v24);
              goto LABEL_53;
            }
            v30 = 0;
            v14 = v29;
            if ( (int)GetNeverSetAsDefaultProperty(v24, v31, v29, &v30) >= 0 && v30 )
              goto LABEL_12;
            EndpointCreationTime = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))v24->lpVtbl->GetId)(v24, &pv);
            if ( EndpointCreationTime < 0 )
              goto LABEL_50;
            if ( v39
              && ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
                   v39,
                   pv)
              || (unsigned int)IsAvoidAsDefault(v24, v31, v14) )
            {
LABEL_12:
              CoTaskMemFree(pv);
              pv = 0;
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v26);
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v24);
            }
            else
            {
              v15 = v26;
              if ( v26 != v24 )
              {
                v16 = v26;
                v15 = 0;
                v26 = 0;
                if ( v24 )
                {
                  ((void (__fastcall *)(struct IMMDevice *, GUID *, struct IMMDevice **))v24->lpVtbl->QueryInterface)(
                    v24,
                    &GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21,
                    &v26);
                  v15 = v26;
                }
                if ( v16 )
                {
                  ((void (__fastcall *)(struct IMMDevice *))v16->lpVtbl->Release)(v16);
                  v15 = v26;
                }
                v14 = v29;
              }
              if ( !v15 )
              {
                EndpointCreationTime = -2147024809;
LABEL_50:
                CoTaskMemFree(pv);
                pv = 0;
                wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v26);
                wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v24);
LABEL_53:
                v7 = v27;
                goto LABEL_65;
              }
              EndpointCreationTime = ((__int64 (__fastcall *)(struct IMMDevice *, _QWORD, unsigned int *))v15->lpVtbl[1].Release)(
                                       v15,
                                       v14,
                                       &v25);
              if ( EndpointCreationTime < 0 )
                goto LABEL_50;
              EndpointCreationTime = GetEndpointCreationTime(v24, &FileTime1);
              if ( EndpointCreationTime < 0 )
                goto LABEL_50;
              if ( (int)GetEndpointLevel(v24, v14, &v36) < 0 )
              {
                if ( v25 > v12 || v25 == v12 && CompareFileTime(&FileTime1, &v38) == 1 )
                {
                  v18 = v24;
                  if ( v8 != v24 )
                  {
                    if ( v24 )
                      ((void (__fastcall *)(struct IMMDevice *))v24->lpVtbl->AddRef)(v24);
                    if ( v8 )
                      ((void (__fastcall *)(struct IMMDevice *))v8->lpVtbl->Release)(v8);
                    v8 = v18;
                    v40 = v18;
                  }
                  v12 = v25;
                  v38 = FileTime1;
                }
              }
              else
              {
                v17 = v36;
                if ( v36 > v10
                  || v36 == v10
                  && (v25 > v11 || v36 == v10 && v25 == v11 && CompareFileTime(&FileTime1, &FileTime2) == 1) )
                {
                  ATL::CComPtr<IMMDevice>::operator=(&v27, &v24);
                  v10 = v17;
                  v11 = v25;
                  FileTime2 = FileTime1;
                }
              }
              CoTaskMemFree(pv);
              pv = 0;
              if ( v26 )
                ((void (__fastcall *)(struct IMMDevice *))v26->lpVtbl->Release)(v26);
              if ( v24 )
                ((void (__fastcall *)(struct IMMDevice *))v24->lpVtbl->Release)(v24);
            }
          }
          v7 = v27;
          if ( !v8 || v27 && v12 <= v11 && v12 < 0x60000000 )
          {
            v20 = (_QWORD *)v34;
            if ( !v27 )
            {
LABEL_62:
              v21 = EndpointCreationTime;
              if ( !*v20 )
                v21 = -2147023728;
              EndpointCreationTime = v21;
              goto LABEL_65;
            }
            v19 = v27;
            v7 = 0;
            v27 = 0;
          }
          else
          {
            v19 = v8;
            v8 = 0;
            v20 = (_QWORD *)v34;
          }
          *v20 = v19;
          goto LABEL_62;
        }
      }
    }
  }
LABEL_65:
  if ( v8 )
    ((void (__fastcall *)(struct IMMDevice *))v8->lpVtbl->Release)(v8);
  if ( v7 )
    ((void (__fastcall *)(struct IMMDevice *))v7->lpVtbl->Release)(v7);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)EndpointCreationTime;
}

```

## disassembly

```asm
0x18000b258  mov     [rsp-8+arg_0], rbx
0x18000b25d  push    rbp
0x18000b25e  push    rsi
0x18000b25f  push    rdi
0x18000b260  push    r12
0x18000b262  push    r13
0x18000b264  push    r14
0x18000b266  push    r15
0x18000b268  lea     rbp, [rsp-1Fh]
0x18000b26d  sub     rsp, 0E0h
0x18000b274  mov     rax, cs:__security_cookie
0x18000b27b  xor     rax, rsp
0x18000b27e  mov     [rbp+4Fh+var_40], rax
0x18000b282  mov     [rbp+4Fh+var_70], r9
0x18000b286  mov     r14d, r8d
0x18000b289  mov     [rbp+4Fh+var_B4], r8d
0x18000b28d  mov     r15d, edx
0x18000b290  mov     [rbp+4Fh+var_AC], edx
0x18000b293  mov     rax, [rbp+4Fh+arg_20]
0x18000b297  mov     [rbp+4Fh+var_98], rax
0x18000b29b  mov     [rbp+4Fh+var_B8], 0
0x18000b2a2  mov     [rbp+4Fh+var_90], 0
0x18000b2aa  mov     [rbp+4Fh+var_A0], 0
0x18000b2b2  xor     ebx, ebx
0x18000b2b4  mov     [rbp+4Fh+var_C0], rbx
0x18000b2b8  mov     qword ptr [rbp+4Fh+FileTime2.dwLowDateTime], rbx
0x18000b2bc  xor     edi, edi
0x18000b2be  mov     [rbp+4Fh+var_68], rdi
0x18000b2c2  mov     qword ptr [rbp+4Fh+var_78.dwLowDateTime], rdi
0x18000b2c6  lea     rax, [rbp+4Fh+var_90]
0x18000b2ca  mov     [rsp+110h+ppv], rax; ppv
0x18000b2cf  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x18000b2d6  xor     edx, edx; pUnkOuter
0x18000b2d8  lea     r8d, [rbx+17h]; dwClsContext
0x18000b2dc  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x18000b2e3  call    cs:__imp_CoCreateInstance
0x18000b2e9  mov     esi, eax
0x18000b2eb  test    eax, eax
0x18000b2ed  js      loc_18000B6C5
0x18000b2f3  mov     rcx, [rbp+4Fh+var_90]
0x18000b2f7  mov     rax, [rcx]
0x18000b2fa  lea     r9, [rbp+4Fh+var_A0]
0x18000b2fe  lea     r8d, [rbx+1]
0x18000b302  mov     edx, r15d
0x18000b305  mov     rax, [rax+18h]
0x18000b309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b30e  mov     esi, eax
0x18000b310  test    eax, eax
0x18000b312  js      loc_18000B6C5
0x18000b318  mov     rcx, [rbp+4Fh+var_A0]
0x18000b31c  mov     rax, [rcx]
0x18000b31f  lea     rdx, [rbp+4Fh+var_B8]
0x18000b323  mov     rax, [rax+18h]
0x18000b327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b32c  mov     esi, eax
0x18000b32e  test    eax, eax
0x18000b330  js      loc_18000B6C5
0x18000b336  cmp     [rbp+4Fh+var_B8], edi
0x18000b339  jnz     short loc_18000B345
0x18000b33b  mov     esi, 80070490h
0x18000b340  jmp     loc_18000B6C5
0x18000b345  mov     r9d, r14d
0x18000b348  lea     r8, aLevelX; "Level:%x"
0x18000b34f  mov     edx, 0Dh; unsigned __int64
0x18000b354  lea     rcx, [rbp+4Fh+var_60]; unsigned __int16 *
0x18000b358  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b35d  mov     esi, eax
0x18000b35f  test    eax, eax
0x18000b361  js      loc_18000B6C5
0x18000b367  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000b36b  xor     r15d, r15d
0x18000b36e  xor     r14d, r14d
0x18000b371  xor     r13d, r13d
0x18000b374  cmp     r13d, [rbp+4Fh+var_B8]
0x18000b378  jnb     loc_18000B679
0x18000b37e  xor     ebx, ebx
0x18000b380  mov     [rsp+110h+var_D8], rbx
0x18000b385  mov     [rbp+4Fh+var_C8], rbx
0x18000b389  mov     [rsp+110h+pv], rbx
0x18000b38e  mov     qword ptr [rbp+4Fh+FileTime1.dwLowDateTime], rbx
0x18000b392  mov     [rbp+4Fh+var_88], rbx
0x18000b396  mov     [rsp+110h+var_D0], ebx
0x18000b39a  mov     rcx, [rbp+4Fh+var_A0]
0x18000b39e  mov     rax, [rcx]
0x18000b3a1  lea     r8, [rsp+110h+var_D8]
0x18000b3a6  mov     edx, r13d
0x18000b3a9  mov     rax, [rax+20h]
0x18000b3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3b2  mov     esi, eax
0x18000b3b4  test    eax, eax
0x18000b3b6  js      loc_18000B63E
0x18000b3bc  mov     [rbp+4Fh+var_B0], ebx
0x18000b3bf  lea     r9, [rbp+4Fh+var_B0]
0x18000b3c3  mov     ebx, [rbp+4Fh+var_B4]
0x18000b3c6  mov     r8d, ebx
0x18000b3c9  mov     edx, [rbp+4Fh+var_AC]
0x18000b3cc  mov     rcx, [rsp+110h+var_D8]
0x18000b3d1  call    cs:__imp_GetNeverSetAsDefaultProperty
0x18000b3d7  test    eax, eax
0x18000b3d9  js      short loc_18000B40E
0x18000b3db  cmp     [rbp+4Fh+var_B0], 0
0x18000b3df  jz      short loc_18000B40E
0x18000b3e1  mov     rcx, [rsp+110h+pv]; pv
0x18000b3e6  call    cs:__imp_CoTaskMemFree
0x18000b3ec  mov     [rsp+110h+pv], 0
0x18000b3f5  lea     rcx, [rbp+4Fh+var_C8]
0x18000b3f9  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18000b3fe  nop
0x18000b3ff  lea     rcx, [rsp+110h+var_D8]
0x18000b404  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18000b409  jmp     loc_18000B607
0x18000b40e  mov     rcx, [rsp+110h+var_D8]
0x18000b413  mov     rax, [rcx]
0x18000b416  lea     rdx, [rsp+110h+pv]
0x18000b41b  mov     rax, [rax+28h]
0x18000b41f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b424  mov     esi, eax
0x18000b426  test    eax, eax
0x18000b428  js      loc_18000B614
0x18000b42e  mov     rax, [rbp+4Fh+var_70]
0x18000b432  test    rax, rax
0x18000b435  jz      short loc_18000B449
0x18000b437  mov     rdx, [rsp+110h+pv]
0x18000b43c  mov     rcx, rax
0x18000b43f  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x18000b444  test    rax, rax
0x18000b447  jnz     short loc_18000B3E1
0x18000b449  mov     r8d, ebx
0x18000b44c  mov     edx, [rbp+4Fh+var_AC]
0x18000b44f  mov     rcx, [rsp+110h+var_D8]
0x18000b454  call    ?IsAvoidAsDefault@@YAHPEAUIMMDevice@@W4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@W4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@@Z; IsAvoidAsDefault(IMMDevice *,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001)
0x18000b459  test    eax, eax
0x18000b45b  jnz     short loc_18000B3E1
0x18000b45d  mov     r9, [rsp+110h+var_D8]
0x18000b462  mov     rcx, [rbp+4Fh+var_C8]
0x18000b466  cmp     rcx, r9
0x18000b469  jz      short loc_18000B4B1
0x18000b46b  mov     rbx, rcx
0x18000b46e  xor     ecx, ecx
0x18000b470  mov     [rbp+4Fh+var_C8], rcx
0x18000b474  test    r9, r9
0x18000b477  jz      short loc_18000B496
0x18000b479  mov     rax, [r9]
0x18000b47c  lea     r8, [rbp+4Fh+var_C8]
0x18000b480  lea     rdx, _GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21
0x18000b487  mov     rcx, r9
0x18000b48a  mov     rax, [rax]
0x18000b48d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b492  mov     rcx, [rbp+4Fh+var_C8]
0x18000b496  test    rbx, rbx
0x18000b499  jz      short loc_18000B4AE
0x18000b49b  mov     rax, [rbx]
0x18000b49e  mov     rcx, rbx
0x18000b4a1  mov     rax, [rax+10h]
0x18000b4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4aa  mov     rcx, [rbp+4Fh+var_C8]
0x18000b4ae  mov     ebx, [rbp+4Fh+var_B4]
0x18000b4b1  test    rcx, rcx
0x18000b4b4  jz      loc_18000B60F
0x18000b4ba  mov     rax, [rcx]
0x18000b4bd  lea     r8, [rsp+110h+var_D0]
0x18000b4c2  mov     edx, ebx
0x18000b4c4  mov     rax, [rax+48h]
0x18000b4c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4cd  mov     esi, eax
0x18000b4cf  test    eax, eax
0x18000b4d1  js      loc_18000B614
0x18000b4d7  lea     rdx, [rbp+4Fh+FileTime1]; struct _FILETIME *
0x18000b4db  mov     rcx, [rsp+110h+var_D8]; struct IMMDevice *
0x18000b4e0  call    ?GetEndpointCreationTime@@YAJPEAUIMMDevice@@PEAU_FILETIME@@@Z; GetEndpointCreationTime(IMMDevice *,_FILETIME *)
0x18000b4e5  mov     esi, eax
0x18000b4e7  test    eax, eax
0x18000b4e9  js      loc_18000B614
0x18000b4ef  lea     r8, [rbp+4Fh+var_88]
0x18000b4f3  mov     edx, ebx
0x18000b4f5  mov     rcx, [rsp+110h+var_D8]
0x18000b4fa  call    ?GetEndpointLevel@@YAJPEAUIMMDevice@@W4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@PEA_J@Z; GetEndpointLevel(IMMDevice *,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001,__int64 *)
0x18000b4ff  test    eax, eax
0x18000b501  js      short loc_18000B564
0x18000b503  mov     rbx, [rbp+4Fh+var_88]
0x18000b507  cmp     rbx, r12
0x18000b50a  jg      short loc_18000B544
0x18000b50c  jnz     loc_18000B5C6
0x18000b512  cmp     [rsp+110h+var_D0], r15d
0x18000b517  ja      short loc_18000B544
0x18000b519  cmp     rbx, r12
0x18000b51c  jnz     loc_18000B5C6
0x18000b522  cmp     [rsp+110h+var_D0], r15d
0x18000b527  jnz     loc_18000B5C6
0x18000b52d  lea     rdx, [rbp+4Fh+FileTime2]; lpFileTime2
0x18000b531  lea     rcx, [rbp+4Fh+FileTime1]; lpFileTime1
0x18000b535  call    cs:__imp_CompareFileTime
0x18000b53b  cmp     eax, 1
0x18000b53e  jnz     loc_18000B5C6
0x18000b544  lea     rdx, [rsp+110h+var_D8]
0x18000b549  lea     rcx, [rbp+4Fh+var_C0]
0x18000b54d  call    ??4?$CComPtr@UIMMDevice@@@ATL@@QEAAPEAUIMMDevice@@AEBV01@@Z; ATL::CComPtr<IMMDevice>::operator=(ATL::CComPtr<IMMDevice> const &)
0x18000b552  mov     r12, rbx
0x18000b555  mov     r15d, [rsp+110h+var_D0]
0x18000b55a  mov     rax, qword ptr [rbp+4Fh+FileTime1.dwLowDateTime]
0x18000b55e  mov     qword ptr [rbp+4Fh+FileTime2.dwLowDateTime], rax
0x18000b562  jmp     short loc_18000B5C6
0x18000b564  cmp     [rsp+110h+var_D0], r14d
0x18000b569  ja      short loc_18000B580
0x18000b56b  jnz     short loc_18000B5C6
0x18000b56d  lea     rdx, [rbp+4Fh+var_78]; lpFileTime2
0x18000b571  lea     rcx, [rbp+4Fh+FileTime1]; lpFileTime1
0x18000b575  call    cs:__imp_CompareFileTime
0x18000b57b  cmp     eax, 1
0x18000b57e  jnz     short loc_18000B5C6
0x18000b580  mov     rbx, [rsp+110h+var_D8]
0x18000b585  cmp     rdi, rbx
0x18000b588  jz      short loc_18000B5B9
0x18000b58a  test    rbx, rbx
0x18000b58d  jz      short loc_18000B59E
0x18000b58f  mov     rax, [rbx]
0x18000b592  mov     rcx, rbx
0x18000b595  mov     rax, [rax+8]
0x18000b599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b59e  test    rdi, rdi
0x18000b5a1  jz      short loc_18000B5B2
0x18000b5a3  mov     rax, [rdi]
0x18000b5a6  mov     rcx, rdi
0x18000b5a9  mov     rax, [rax+10h]
0x18000b5ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5b2  mov     rdi, rbx
0x18000b5b5  mov     [rbp+4Fh+var_68], rbx
0x18000b5b9  mov     r14d, [rsp+110h+var_D0]
0x18000b5be  mov     rax, qword ptr [rbp+4Fh+FileTime1.dwLowDateTime]
0x18000b5c2  mov     qword ptr [rbp+4Fh+var_78.dwLowDateTime], rax
0x18000b5c6  mov     rcx, [rsp+110h+pv]; pv
0x18000b5cb  call    cs:__imp_CoTaskMemFree
0x18000b5d1  mov     [rsp+110h+pv], 0
0x18000b5da  mov     rcx, [rbp+4Fh+var_C8]
0x18000b5de  test    rcx, rcx
0x18000b5e1  jz      short loc_18000B5F0
0x18000b5e3  mov     rax, [rcx]
0x18000b5e6  mov     rax, [rax+10h]
0x18000b5ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5ef  nop
0x18000b5f0  mov     rcx, [rsp+110h+var_D8]
0x18000b5f5  test    rcx, rcx
0x18000b5f8  jz      short loc_18000B607
0x18000b5fa  mov     rax, [rcx]
0x18000b5fd  mov     rax, [rax+10h]
0x18000b601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b606  nop
0x18000b607  inc     r13d
0x18000b60a  jmp     loc_18000B374
0x18000b60f  mov     esi, 80070057h
0x18000b614  mov     rcx, [rsp+110h+pv]; pv
0x18000b619  call    cs:__imp_CoTaskMemFree
0x18000b61f  mov     [rsp+110h+pv], 0
0x18000b628  lea     rcx, [rbp+4Fh+var_C8]
0x18000b62c  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18000b631  nop
0x18000b632  lea     rcx, [rsp+110h+var_D8]
0x18000b637  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18000b63c  jmp     short loc_18000B673
0x18000b63e  mov     rcx, [rsp+110h+pv]; pv
0x18000b643  call    cs:__imp_CoTaskMemFree
0x18000b649  mov     [rsp+110h+pv], 0
0x18000b652  lea     rcx, [rbp+4Fh+var_C8]
0x18000b656  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18000b65b  nop
0x18000b65c  mov     rcx, [rsp+110h+var_D8]
0x18000b661  test    rcx, rcx
0x18000b664  jz      short loc_18000B673
0x18000b666  mov     rax, [rcx]
0x18000b669  mov     rax, [rax+10h]
0x18000b66d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b672  nop
0x18000b673  mov     rbx, [rbp+4Fh+var_C0]
0x18000b677  jmp     short loc_18000B6C5
0x18000b679  mov     rbx, [rbp+4Fh+var_C0]
0x18000b67d  test    rdi, rdi
0x18000b680  jz      short loc_18000B6A0
0x18000b682  test    rbx, rbx
0x18000b685  jz      short loc_18000B695
0x18000b687  cmp     r14d, r15d
0x18000b68a  ja      short loc_18000B695
0x18000b68c  cmp     r14d, 60000000h
0x18000b693  jb      short loc_18000B6A0
0x18000b695  mov     rax, rdi
0x18000b698  xor     edi, edi
0x18000b69a  mov     rcx, [rbp+4Fh+var_98]
0x18000b69e  jmp     short loc_18000B6B2
0x18000b6a0  mov     rcx, [rbp+4Fh+var_98]
0x18000b6a4  test    rbx, rbx
0x18000b6a7  jz      short loc_18000B6B5
0x18000b6a9  mov     rax, rbx
0x18000b6ac  xor     ebx, ebx
0x18000b6ae  mov     [rbp+4Fh+var_C0], rbx
0x18000b6b2  mov     [rcx], rax
0x18000b6b5  mov     eax, esi
0x18000b6b7  mov     esi, 80070490h
0x18000b6bc  cmp     qword ptr [rcx], 0
0x18000b6c0  cmovz   eax, esi
0x18000b6c3  mov     esi, eax
0x18000b6c5  test    rdi, rdi
  ... truncated ...
```
