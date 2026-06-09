# CDefaultDeviceManager::GetDefaultEndpoint(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *,IMMDevice * *)

- ea: `0x18000b108`
- end: `0x18000b5f4`
- name: `?GetDefaultEndpoint@CDefaultDeviceManager@@QEAAJW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@W4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@PEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@PEAPEAUIMMDevice@@@Z`
- size: `1260`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d2b0`
- `0x1801354f0`

## callees

- `0x18000accc`
- `0x18000b108`
- `0x18000b710`
- `0x18000b860`
- `0x18000b8f0`
- `0x18000b9f8`
- `0x18004ce30`
- `0x180058a00`
- `0x1800cf8c0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000b3e5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000b425`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000b3e5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000b425`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b193`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b193`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b296`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b47b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b4c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b4f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b296`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b47b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b4c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b4f3`
- `MMDevAPI!__imp_GetNeverSetAsDefaultProperty` at `0x18000b281`
- `MMDevAPI!__imp_GetNeverSetAsDefaultProperty` at `0x18000b281`

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
0x18000b108  mov     [rsp-8+arg_0], rbx
0x18000b10d  push    rbp
0x18000b10e  push    rsi
0x18000b10f  push    rdi
0x18000b110  push    r12
0x18000b112  push    r13
0x18000b114  push    r14
0x18000b116  push    r15
0x18000b118  lea     rbp, [rsp-1Fh]
0x18000b11d  sub     rsp, 0E0h
0x18000b124  mov     rax, cs:__security_cookie
0x18000b12b  xor     rax, rsp
0x18000b12e  mov     [rbp+4Fh+var_40], rax
0x18000b132  mov     [rbp+4Fh+var_70], r9
0x18000b136  mov     r14d, r8d
0x18000b139  mov     [rbp+4Fh+var_B4], r8d
0x18000b13d  mov     r15d, edx
0x18000b140  mov     [rbp+4Fh+var_AC], edx
0x18000b143  mov     rax, [rbp+4Fh+arg_20]
0x18000b147  mov     [rbp+4Fh+var_98], rax
0x18000b14b  mov     [rbp+4Fh+var_B8], 0
0x18000b152  mov     [rbp+4Fh+var_90], 0
0x18000b15a  mov     [rbp+4Fh+var_A0], 0
0x18000b162  xor     ebx, ebx
0x18000b164  mov     [rbp+4Fh+var_C0], rbx
0x18000b168  mov     qword ptr [rbp+4Fh+FileTime2.dwLowDateTime], rbx
0x18000b16c  xor     edi, edi
0x18000b16e  mov     [rbp+4Fh+var_68], rdi
0x18000b172  mov     qword ptr [rbp+4Fh+var_78.dwLowDateTime], rdi
0x18000b176  lea     rax, [rbp+4Fh+var_90]
0x18000b17a  mov     [rsp+110h+ppv], rax; ppv
0x18000b17f  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x18000b186  xor     edx, edx; pUnkOuter
0x18000b188  lea     r8d, [rbx+17h]; dwClsContext
0x18000b18c  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x18000b193  call    cs:__imp_CoCreateInstance
0x18000b199  mov     esi, eax
0x18000b19b  test    eax, eax
0x18000b19d  js      loc_18000B575
0x18000b1a3  mov     rcx, [rbp+4Fh+var_90]
0x18000b1a7  mov     rax, [rcx]
0x18000b1aa  lea     r9, [rbp+4Fh+var_A0]
0x18000b1ae  lea     r8d, [rbx+1]
0x18000b1b2  mov     edx, r15d
0x18000b1b5  mov     rax, [rax+18h]
0x18000b1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1be  mov     esi, eax
0x18000b1c0  test    eax, eax
0x18000b1c2  js      loc_18000B575
0x18000b1c8  mov     rcx, [rbp+4Fh+var_A0]
0x18000b1cc  mov     rax, [rcx]
0x18000b1cf  lea     rdx, [rbp+4Fh+var_B8]
0x18000b1d3  mov     rax, [rax+18h]
0x18000b1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1dc  mov     esi, eax
0x18000b1de  test    eax, eax
0x18000b1e0  js      loc_18000B575
0x18000b1e6  cmp     [rbp+4Fh+var_B8], edi
0x18000b1e9  jnz     short loc_18000B1F5
0x18000b1eb  mov     esi, 80070490h
0x18000b1f0  jmp     loc_18000B575
0x18000b1f5  mov     r9d, r14d
0x18000b1f8  lea     r8, aLevelX; "Level:%x"
0x18000b1ff  mov     edx, 0Dh; unsigned __int64
0x18000b204  lea     rcx, [rbp+4Fh+var_60]; unsigned __int16 *
0x18000b208  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b20d  mov     esi, eax
0x18000b20f  test    eax, eax
0x18000b211  js      loc_18000B575
0x18000b217  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000b21b  xor     r15d, r15d
0x18000b21e  xor     r14d, r14d
0x18000b221  xor     r13d, r13d
0x18000b224  cmp     r13d, [rbp+4Fh+var_B8]
0x18000b228  jnb     loc_18000B529
0x18000b22e  xor     ebx, ebx
0x18000b230  mov     [rsp+110h+var_D8], rbx
0x18000b235  mov     [rbp+4Fh+var_C8], rbx
0x18000b239  mov     [rsp+110h+pv], rbx
0x18000b23e  mov     qword ptr [rbp+4Fh+FileTime1.dwLowDateTime], rbx
0x18000b242  mov     [rbp+4Fh+var_88], rbx
0x18000b246  mov     [rsp+110h+var_D0], ebx
0x18000b24a  mov     rcx, [rbp+4Fh+var_A0]
0x18000b24e  mov     rax, [rcx]
0x18000b251  lea     r8, [rsp+110h+var_D8]
0x18000b256  mov     edx, r13d
0x18000b259  mov     rax, [rax+20h]
0x18000b25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b262  mov     esi, eax
0x18000b264  test    eax, eax
0x18000b266  js      loc_18000B4EE
0x18000b26c  mov     [rbp+4Fh+var_B0], ebx
0x18000b26f  lea     r9, [rbp+4Fh+var_B0]
0x18000b273  mov     ebx, [rbp+4Fh+var_B4]
0x18000b276  mov     r8d, ebx
0x18000b279  mov     edx, [rbp+4Fh+var_AC]
0x18000b27c  mov     rcx, [rsp+110h+var_D8]
0x18000b281  call    cs:__imp_GetNeverSetAsDefaultProperty
0x18000b287  test    eax, eax
0x18000b289  js      short loc_18000B2BE
0x18000b28b  cmp     [rbp+4Fh+var_B0], 0
0x18000b28f  jz      short loc_18000B2BE
0x18000b291  mov     rcx, [rsp+110h+pv]; pv
0x18000b296  call    cs:__imp_CoTaskMemFree
0x18000b29c  mov     [rsp+110h+pv], 0
0x18000b2a5  lea     rcx, [rbp+4Fh+var_C8]
0x18000b2a9  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18000b2ae  nop
0x18000b2af  lea     rcx, [rsp+110h+var_D8]
0x18000b2b4  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18000b2b9  jmp     loc_18000B4B7
0x18000b2be  mov     rcx, [rsp+110h+var_D8]
0x18000b2c3  mov     rax, [rcx]
0x18000b2c6  lea     rdx, [rsp+110h+pv]
0x18000b2cb  mov     rax, [rax+28h]
0x18000b2cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2d4  mov     esi, eax
0x18000b2d6  test    eax, eax
0x18000b2d8  js      loc_18000B4C4
0x18000b2de  mov     rax, [rbp+4Fh+var_70]
0x18000b2e2  test    rax, rax
0x18000b2e5  jz      short loc_18000B2F9
0x18000b2e7  mov     rdx, [rsp+110h+pv]
0x18000b2ec  mov     rcx, rax
0x18000b2ef  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x18000b2f4  test    rax, rax
0x18000b2f7  jnz     short loc_18000B291
0x18000b2f9  mov     r8d, ebx
0x18000b2fc  mov     edx, [rbp+4Fh+var_AC]
0x18000b2ff  mov     rcx, [rsp+110h+var_D8]
0x18000b304  call    ?IsAvoidAsDefault@@YAHPEAUIMMDevice@@W4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@W4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@@Z; IsAvoidAsDefault(IMMDevice *,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001)
0x18000b309  test    eax, eax
0x18000b30b  jnz     short loc_18000B291
0x18000b30d  mov     r9, [rsp+110h+var_D8]
0x18000b312  mov     rcx, [rbp+4Fh+var_C8]
0x18000b316  cmp     rcx, r9
0x18000b319  jz      short loc_18000B361
0x18000b31b  mov     rbx, rcx
0x18000b31e  xor     ecx, ecx
0x18000b320  mov     [rbp+4Fh+var_C8], rcx
0x18000b324  test    r9, r9
0x18000b327  jz      short loc_18000B346
0x18000b329  mov     rax, [r9]
0x18000b32c  lea     r8, [rbp+4Fh+var_C8]
0x18000b330  lea     rdx, _GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21
0x18000b337  mov     rcx, r9
0x18000b33a  mov     rax, [rax]
0x18000b33d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b342  mov     rcx, [rbp+4Fh+var_C8]
0x18000b346  test    rbx, rbx
0x18000b349  jz      short loc_18000B35E
0x18000b34b  mov     rax, [rbx]
0x18000b34e  mov     rcx, rbx
0x18000b351  mov     rax, [rax+10h]
0x18000b355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b35a  mov     rcx, [rbp+4Fh+var_C8]
0x18000b35e  mov     ebx, [rbp+4Fh+var_B4]
0x18000b361  test    rcx, rcx
0x18000b364  jz      loc_18000B4BF
0x18000b36a  mov     rax, [rcx]
0x18000b36d  lea     r8, [rsp+110h+var_D0]
0x18000b372  mov     edx, ebx
0x18000b374  mov     rax, [rax+48h]
0x18000b378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b37d  mov     esi, eax
0x18000b37f  test    eax, eax
0x18000b381  js      loc_18000B4C4
0x18000b387  lea     rdx, [rbp+4Fh+FileTime1]; struct _FILETIME *
0x18000b38b  mov     rcx, [rsp+110h+var_D8]; struct IMMDevice *
0x18000b390  call    ?GetEndpointCreationTime@@YAJPEAUIMMDevice@@PEAU_FILETIME@@@Z; GetEndpointCreationTime(IMMDevice *,_FILETIME *)
0x18000b395  mov     esi, eax
0x18000b397  test    eax, eax
0x18000b399  js      loc_18000B4C4
0x18000b39f  lea     r8, [rbp+4Fh+var_88]
0x18000b3a3  mov     edx, ebx
0x18000b3a5  mov     rcx, [rsp+110h+var_D8]
0x18000b3aa  call    ?GetEndpointLevel@@YAJPEAUIMMDevice@@W4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@PEA_J@Z; GetEndpointLevel(IMMDevice *,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001,__int64 *)
0x18000b3af  test    eax, eax
0x18000b3b1  js      short loc_18000B414
0x18000b3b3  mov     rbx, [rbp+4Fh+var_88]
0x18000b3b7  cmp     rbx, r12
0x18000b3ba  jg      short loc_18000B3F4
0x18000b3bc  jnz     loc_18000B476
0x18000b3c2  cmp     [rsp+110h+var_D0], r15d
0x18000b3c7  ja      short loc_18000B3F4
0x18000b3c9  cmp     rbx, r12
0x18000b3cc  jnz     loc_18000B476
0x18000b3d2  cmp     [rsp+110h+var_D0], r15d
0x18000b3d7  jnz     loc_18000B476
0x18000b3dd  lea     rdx, [rbp+4Fh+FileTime2]; lpFileTime2
0x18000b3e1  lea     rcx, [rbp+4Fh+FileTime1]; lpFileTime1
0x18000b3e5  call    cs:__imp_CompareFileTime
0x18000b3eb  cmp     eax, 1
0x18000b3ee  jnz     loc_18000B476
0x18000b3f4  lea     rdx, [rsp+110h+var_D8]
0x18000b3f9  lea     rcx, [rbp+4Fh+var_C0]
0x18000b3fd  call    ??4?$CComPtr@UIMMDevice@@@ATL@@QEAAPEAUIMMDevice@@AEBV01@@Z; ATL::CComPtr<IMMDevice>::operator=(ATL::CComPtr<IMMDevice> const &)
0x18000b402  mov     r12, rbx
0x18000b405  mov     r15d, [rsp+110h+var_D0]
0x18000b40a  mov     rax, qword ptr [rbp+4Fh+FileTime1.dwLowDateTime]
0x18000b40e  mov     qword ptr [rbp+4Fh+FileTime2.dwLowDateTime], rax
0x18000b412  jmp     short loc_18000B476
0x18000b414  cmp     [rsp+110h+var_D0], r14d
0x18000b419  ja      short loc_18000B430
0x18000b41b  jnz     short loc_18000B476
0x18000b41d  lea     rdx, [rbp+4Fh+var_78]; lpFileTime2
0x18000b421  lea     rcx, [rbp+4Fh+FileTime1]; lpFileTime1
0x18000b425  call    cs:__imp_CompareFileTime
0x18000b42b  cmp     eax, 1
0x18000b42e  jnz     short loc_18000B476
0x18000b430  mov     rbx, [rsp+110h+var_D8]
0x18000b435  cmp     rdi, rbx
0x18000b438  jz      short loc_18000B469
0x18000b43a  test    rbx, rbx
0x18000b43d  jz      short loc_18000B44E
0x18000b43f  mov     rax, [rbx]
0x18000b442  mov     rcx, rbx
0x18000b445  mov     rax, [rax+8]
0x18000b449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b44e  test    rdi, rdi
0x18000b451  jz      short loc_18000B462
0x18000b453  mov     rax, [rdi]
0x18000b456  mov     rcx, rdi
0x18000b459  mov     rax, [rax+10h]
0x18000b45d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b462  mov     rdi, rbx
0x18000b465  mov     [rbp+4Fh+var_68], rbx
0x18000b469  mov     r14d, [rsp+110h+var_D0]
0x18000b46e  mov     rax, qword ptr [rbp+4Fh+FileTime1.dwLowDateTime]
0x18000b472  mov     qword ptr [rbp+4Fh+var_78.dwLowDateTime], rax
0x18000b476  mov     rcx, [rsp+110h+pv]; pv
0x18000b47b  call    cs:__imp_CoTaskMemFree
0x18000b481  mov     [rsp+110h+pv], 0
0x18000b48a  mov     rcx, [rbp+4Fh+var_C8]
0x18000b48e  test    rcx, rcx
0x18000b491  jz      short loc_18000B4A0
0x18000b493  mov     rax, [rcx]
0x18000b496  mov     rax, [rax+10h]
0x18000b49a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b49f  nop
0x18000b4a0  mov     rcx, [rsp+110h+var_D8]
0x18000b4a5  test    rcx, rcx
0x18000b4a8  jz      short loc_18000B4B7
0x18000b4aa  mov     rax, [rcx]
0x18000b4ad  mov     rax, [rax+10h]
0x18000b4b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4b6  nop
0x18000b4b7  inc     r13d
0x18000b4ba  jmp     loc_18000B224
0x18000b4bf  mov     esi, 80070057h
0x18000b4c4  mov     rcx, [rsp+110h+pv]; pv
0x18000b4c9  call    cs:__imp_CoTaskMemFree
0x18000b4cf  mov     [rsp+110h+pv], 0
0x18000b4d8  lea     rcx, [rbp+4Fh+var_C8]
0x18000b4dc  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18000b4e1  nop
0x18000b4e2  lea     rcx, [rsp+110h+var_D8]
0x18000b4e7  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18000b4ec  jmp     short loc_18000B523
0x18000b4ee  mov     rcx, [rsp+110h+pv]; pv
0x18000b4f3  call    cs:__imp_CoTaskMemFree
0x18000b4f9  mov     [rsp+110h+pv], 0
0x18000b502  lea     rcx, [rbp+4Fh+var_C8]
0x18000b506  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18000b50b  nop
0x18000b50c  mov     rcx, [rsp+110h+var_D8]
0x18000b511  test    rcx, rcx
0x18000b514  jz      short loc_18000B523
0x18000b516  mov     rax, [rcx]
0x18000b519  mov     rax, [rax+10h]
0x18000b51d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b522  nop
0x18000b523  mov     rbx, [rbp+4Fh+var_C0]
0x18000b527  jmp     short loc_18000B575
0x18000b529  mov     rbx, [rbp+4Fh+var_C0]
0x18000b52d  test    rdi, rdi
0x18000b530  jz      short loc_18000B550
0x18000b532  test    rbx, rbx
0x18000b535  jz      short loc_18000B545
0x18000b537  cmp     r14d, r15d
0x18000b53a  ja      short loc_18000B545
0x18000b53c  cmp     r14d, 60000000h
0x18000b543  jb      short loc_18000B550
0x18000b545  mov     rax, rdi
0x18000b548  xor     edi, edi
0x18000b54a  mov     rcx, [rbp+4Fh+var_98]
0x18000b54e  jmp     short loc_18000B562
0x18000b550  mov     rcx, [rbp+4Fh+var_98]
0x18000b554  test    rbx, rbx
0x18000b557  jz      short loc_18000B565
0x18000b559  mov     rax, rbx
0x18000b55c  xor     ebx, ebx
0x18000b55e  mov     [rbp+4Fh+var_C0], rbx
0x18000b562  mov     [rcx], rax
0x18000b565  mov     eax, esi
0x18000b567  mov     esi, 80070490h
0x18000b56c  cmp     qword ptr [rcx], 0
0x18000b570  cmovz   eax, esi
0x18000b573  mov     esi, eax
0x18000b575  test    rdi, rdi
  ... truncated ...
```
