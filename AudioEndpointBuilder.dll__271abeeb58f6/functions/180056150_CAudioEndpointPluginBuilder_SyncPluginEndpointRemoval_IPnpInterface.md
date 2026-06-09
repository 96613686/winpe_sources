# CAudioEndpointPluginBuilder::SyncPluginEndpointRemoval(IPnpInterface *)

- ea: `0x180056150`
- end: `0x1800565d4`
- name: `?SyncPluginEndpointRemoval@CAudioEndpointPluginBuilder@@SAJPEAUIPnpInterface@@@Z`
- size: `1156`
- prototype: `__int64 __fastcall(struct IPnpInterface *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800077ec`

## callees

- `0x1800035d0`
- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x180023d28`
- `0x180023fbc`
- `0x180034c5c`
- `0x180056150`
- `0x180068010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180056454`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180056454`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180056499`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180056499`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800564fa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056505`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056567`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056572`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800564fa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056505`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056567`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056572`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056250`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056590`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056250`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056590`

## string_xrefs

- `0x180056225`: `avcore\audiocore\server\audioendpointbuilder\dll\audioendpointpluginbuilder.cpp`
- `0x180056556`: `avcore\audiocore\server\audioendpointbuilder\dll\audioendpointpluginbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CAudioEndpointPluginBuilder::SyncPluginEndpointRemoval(struct IPnpInterface *a1)
{
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  unsigned int i; // edi
  __int64 v7; // rbx
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64 *); // rsi
  __int64 v9; // rcx
  HRESULT v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64 *); // rsi
  __int64 v14; // rcx
  __int64 (__fastcall *v15)(struct IPnpInterface *, LPVOID *); // rbx
  LPVOID v16; // rcx
  __int64 v17; // rdx
  int ppv; // [rsp+20h] [rbp-49h]
  __int64 v20; // [rsp+30h] [rbp-39h] BYREF
  __int64 v21; // [rsp+38h] [rbp-31h] BYREF
  __int64 v22; // [rsp+40h] [rbp-29h] BYREF
  LPVOID v23; // [rsp+48h] [rbp-21h] BYREF
  __int64 v24; // [rsp+50h] [rbp-19h] BYREF
  PROPVARIANT pvar[2]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v26; // [rsp+68h] [rbp-1h]
  PROPVARIANT v27[2]; // [rsp+70h] [rbp+7h] BYREF
  __int64 v28; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  unsigned int v30; // [rsp+D8h] [rbp+6Fh] BYREF
  int v31; // [rsp+E0h] [rbp+77h] BYREF
  LPVOID pv; // [rsp+E8h] [rbp+7Fh] BYREF

  v30 = 0;
  v24 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  pv = 0;
  v20 = 0;
  v31 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids);
  }
  QueryInterface = g_DeviceEnumerator->lpVtbl[1].QueryInterface;
  wil::com_ptr_t<IMMDeviceCollection,wil::err_returncode_policy>::reset(&v24);
  v3 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64 *))QueryInterface)(
         g_DeviceEnumerator,
         2,
         15,
         &v24);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 704;
    goto LABEL_9;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v24 + 24LL))(v24, &v30);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 707;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audioendpointpluginbuilder.cpp",
      (const char *)(unsigned int)v3,
      ppv);
LABEL_10:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_61;
  }
  for ( i = 0; i < v30; ++i )
  {
    *(_OWORD *)v27 = 0;
    v28 = 0;
    *(_OWORD *)pvar = 0;
    v26 = 0;
    v7 = v24;
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 32LL);
    v9 = v21;
    v21 = 0;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v10 = v8(v7, i, &v21);
    v4 = v10;
    if ( v10 < 0 )
    {
      v17 = 715;
      goto LABEL_57;
    }
    v11 = v20;
    v20 = 0;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v10 = wil::com_query_to_nothrow<IMMEndpointInternal,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(
            &v21,
            &v20);
    v4 = v10;
    if ( v10 < 0 )
    {
      v17 = 718;
      goto LABEL_57;
    }
    v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 32LL))(v20, &v31);
    v4 = v10;
    if ( v10 < 0 )
    {
      v17 = 719;
      goto LABEL_57;
    }
    if ( (v31 & 0x20000000) == 0 )
    {
      v12 = v21;
      v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v21 + 32LL);
      v14 = v22;
      v22 = 0;
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v10 = v13(v12, 0, &v22);
      v4 = v10;
      if ( v10 < 0 )
      {
        v17 = 728;
        goto LABEL_57;
      }
      v10 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v22 + 40LL))(
              v22,
              &DEVPKEY_AudioEndpointPlugin_FactoryCLSID,
              v27);
      v4 = v10;
      if ( v10 < 0 )
      {
        v17 = 731;
        goto LABEL_57;
      }
      if ( LOWORD(v27[0]) == 72 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids);
        }
        v10 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v22 + 40LL))(
                v22,
                &DEVPKEY_AudioEndpointPlugin_PnPInterface,
                pvar);
        v4 = v10;
        if ( v10 < 0 )
        {
          v17 = 738;
          goto LABEL_57;
        }
        if ( LOWORD(pvar[0]) == 31 )
        {
          v15 = *(__int64 (__fastcall **)(struct IPnpInterface *, LPVOID *))(*(_QWORD *)a1 + 32LL);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &pv,
            0);
          v10 = v15(a1, &pv);
          v4 = v10;
          if ( v10 < 0 )
          {
            v17 = 743;
            goto LABEL_57;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids, pv);
          }
          if ( !(unsigned int)_o__wcsicmp(pv, pvar[1]) )
          {
            v16 = v23;
            v23 = 0;
            if ( v16 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
            v10 = CoCreateInstance(
                    &GUID_06cca63e_9941_441b_b004_39f999ada412,
                    0,
                    0x17u,
                    &GUID_6ca19947_8747_46ab_879e_349c4dbb88fb,
                    &v23);
            v4 = v10;
            if ( v10 < 0 )
            {
              v17 = 750;
              goto LABEL_57;
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids, pv);
            }
            v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v23 + 40LL))(v23, v21, 4);
            v4 = v10;
            if ( v10 < 0 )
            {
              v17 = 753;
LABEL_57:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v17,
                (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audioendpointpluginbuilder.cpp",
                (const char *)(unsigned int)v10,
                ppv);
              PropVariantClear(pvar);
              PropVariantClear(v27);
              goto LABEL_10;
            }
          }
        }
      }
    }
    PropVariantClear(pvar);
    PropVariantClear(v27);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
  if ( pv )
    CoTaskMemFree(pv);
  v4 = 0;
LABEL_61:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
  return v4;
}

```

## disassembly

```asm
0x180056150  push    rbp
0x180056152  push    rbx
0x180056153  push    rsi
0x180056154  push    rdi
0x180056155  push    r13
0x180056157  push    r14
0x180056159  push    r15
0x18005615b  lea     rbp, [rsp-27h]
0x180056160  sub     rsp, 90h
0x180056167  mov     r14, rcx
0x18005616a  xor     r15d, r15d
0x18005616d  mov     [rbp+57h+arg_8], r15d
0x180056171  mov     [rbp+57h+var_70], r15
0x180056175  mov     [rbp+57h+var_88], r15
0x180056179  mov     [rbp+57h+var_80], r15
0x18005617d  mov     [rbp+57h+var_78], r15
0x180056181  mov     [rbp+57h+pv], r15
0x180056185  mov     [rbp+57h+var_90], r15
0x180056189  mov     [rbp+57h+arg_10], r15d
0x18005618d  lea     rsi, WPP_GLOBAL_Control
0x180056194  mov     r13d, 80000h
0x18005619a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800561a1  cmp     rcx, rsi
0x1800561a4  jz      short loc_1800561C6
0x1800561a6  test    [rcx+1Ch], r13d
0x1800561aa  jz      short loc_1800561C6
0x1800561ac  cmp     byte ptr [rcx+19h], 4
0x1800561b0  jb      short loc_1800561C6
0x1800561b2  lea     edx, [r15+1Bh]
0x1800561b6  lea     r8, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids
0x1800561bd  mov     rcx, [rcx+10h]
0x1800561c1  call    WPP_SF_
0x1800561c6  mov     rax, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x1800561cd  mov     rcx, [rax]
0x1800561d0  mov     rbx, [rcx+18h]
0x1800561d4  lea     rcx, [rbp+57h+var_70]
0x1800561d8  call    ?reset@?$com_ptr_t@UIMMDeviceCollection@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDeviceCollection,wil::err_returncode_policy>::reset(void)
0x1800561dd  lea     r9, [rbp+57h+var_70]
0x1800561e1  mov     edx, 2
0x1800561e6  lea     r8d, [rdx+0Dh]
0x1800561ea  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x1800561f1  mov     rax, rbx
0x1800561f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561f9  mov     ebx, eax
0x1800561fb  test    eax, eax
0x1800561fd  jns     short loc_180056206
0x1800561ff  mov     edx, 2C0h
0x180056204  jmp     short loc_180056225
0x180056206  mov     rcx, [rbp+57h+var_70]
0x18005620a  mov     rax, [rcx]
0x18005620d  lea     rdx, [rbp+57h+arg_8]
0x180056211  mov     rax, [rax+18h]
0x180056215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005621a  mov     ebx, eax
0x18005621c  test    eax, eax
0x18005621e  jns     short loc_18005625B
0x180056220  mov     edx, 2C3h; void *
0x180056225  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audioendpoin"...
0x18005622c  mov     r9d, eax; char *
0x18005622f  mov     rcx, [rbp+5Fh]; this
0x180056233  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056238  nop
0x180056239  lea     rcx, [rbp+57h+var_90]
0x18005623d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180056242  nop
0x180056243  mov     rcx, [rbp+57h+pv]; pv
0x180056247  test    rcx, rcx
0x18005624a  jz      loc_180056599
0x180056250  call    cs:__imp_CoTaskMemFree
0x180056256  jmp     loc_180056599
0x18005625b  mov     edi, r15d
0x18005625e  cmp     edi, [rbp+57h+arg_8]
0x180056261  jnb     loc_18005657D
0x180056267  xorps   xmm0, xmm0
0x18005626a  xor     eax, eax
0x18005626c  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x180056270  mov     [rbp+57h+var_40], rax
0x180056274  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180056278  mov     [rbp+57h+var_58], rax
0x18005627c  mov     rbx, [rbp+57h+var_70]
0x180056280  mov     rax, [rbx]
0x180056283  mov     rsi, [rax+20h]
0x180056287  mov     rcx, [rbp+57h+var_88]
0x18005628b  mov     [rbp+57h+var_88], r15
0x18005628f  test    rcx, rcx
0x180056292  jz      short loc_1800562A1
0x180056294  mov     rdx, [rcx]
0x180056297  mov     rax, [rdx+10h]
0x18005629b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800562a0  nop
0x1800562a1  lea     r8, [rbp+57h+var_88]
0x1800562a5  mov     edx, edi
0x1800562a7  mov     rcx, rbx
0x1800562aa  mov     rax, rsi
0x1800562ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800562b2  mov     ebx, eax
0x1800562b4  test    eax, eax
0x1800562b6  js      loc_18005654A
0x1800562bc  mov     rcx, [rbp+57h+var_90]
0x1800562c0  mov     [rbp+57h+var_90], r15
0x1800562c4  test    rcx, rcx
0x1800562c7  jz      short loc_1800562D6
0x1800562c9  mov     rax, [rcx]
0x1800562cc  mov     rax, [rax+10h]
0x1800562d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800562d5  nop
0x1800562d6  lea     rdx, [rbp+57h+var_90]
0x1800562da  lea     rcx, [rbp+57h+var_88]
0x1800562de  call    ??$com_query_to_nothrow@UIMMEndpointInternal@@AEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@@wil@@YAJAEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@0@PEAPEAUIMMEndpointInternal@@@Z; wil::com_query_to_nothrow<IMMEndpointInternal,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &,IMMEndpointInternal * *)
0x1800562e3  mov     ebx, eax
0x1800562e5  test    eax, eax
0x1800562e7  js      loc_180056543
0x1800562ed  mov     rcx, [rbp+57h+var_90]
0x1800562f1  mov     rax, [rcx]
0x1800562f4  lea     rdx, [rbp+57h+arg_10]
0x1800562f8  mov     rax, [rax+20h]
0x1800562fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056301  mov     ebx, eax
0x180056303  test    eax, eax
0x180056305  js      loc_18005653C
0x18005630b  test    [rbp+57h+arg_10], 20000000h
0x180056312  jnz     loc_1800564F6
0x180056318  mov     rbx, [rbp+57h+var_88]
0x18005631c  mov     rax, [rbx]
0x18005631f  mov     rsi, [rax+20h]
0x180056323  mov     rcx, [rbp+57h+var_80]
0x180056327  mov     [rbp+57h+var_80], r15
0x18005632b  test    rcx, rcx
0x18005632e  jz      short loc_18005633D
0x180056330  mov     rdx, [rcx]
0x180056333  mov     rax, [rdx+10h]
0x180056337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005633c  nop
0x18005633d  lea     r8, [rbp+57h+var_80]
0x180056341  xor     edx, edx
0x180056343  mov     rcx, rbx
0x180056346  mov     rax, rsi
0x180056349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005634e  mov     ebx, eax
0x180056350  test    eax, eax
0x180056352  js      loc_180056535
0x180056358  mov     rcx, [rbp+57h+var_80]
0x18005635c  mov     rax, [rcx]
0x18005635f  lea     r8, [rbp+57h+var_50]
0x180056363  lea     rdx, DEVPKEY_AudioEndpointPlugin_FactoryCLSID
0x18005636a  mov     rax, [rax+28h]
0x18005636e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056373  mov     ebx, eax
0x180056375  test    eax, eax
0x180056377  js      loc_18005652E
0x18005637d  cmp     word ptr [rbp+57h+var_50], 48h ; 'H'
0x180056382  jnz     loc_1800564F6
0x180056388  mov     rcx, cs:WPP_GLOBAL_Control
0x18005638f  lea     rsi, WPP_GLOBAL_Control
0x180056396  cmp     rcx, rsi
0x180056399  jz      short loc_1800563BC
0x18005639b  test    [rcx+1Ch], r13d
0x18005639f  jz      short loc_1800563BC
0x1800563a1  cmp     byte ptr [rcx+19h], 4
0x1800563a5  jb      short loc_1800563BC
0x1800563a7  mov     edx, 1Ch
0x1800563ac  lea     r8, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids
0x1800563b3  mov     rcx, [rcx+10h]
0x1800563b7  call    WPP_SF_
0x1800563bc  mov     rcx, [rbp+57h+var_80]
0x1800563c0  mov     rax, [rcx]
0x1800563c3  lea     r8, [rbp+57h+pvar]
0x1800563c7  lea     rdx, DEVPKEY_AudioEndpointPlugin_PnPInterface
0x1800563ce  mov     rax, [rax+28h]
0x1800563d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800563d7  mov     ebx, eax
0x1800563d9  test    eax, eax
0x1800563db  js      loc_180056527
0x1800563e1  mov     eax, 1Fh
0x1800563e6  cmp     ax, word ptr [rbp+57h+pvar]
0x1800563ea  jnz     loc_1800564F6
0x1800563f0  mov     rax, [r14]
0x1800563f3  mov     rbx, [rax+20h]
0x1800563f7  xor     edx, edx
0x1800563f9  lea     rcx, [rbp+57h+pv]
0x1800563fd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180056402  lea     rdx, [rbp+57h+pv]
0x180056406  mov     rcx, r14
0x180056409  mov     rax, rbx
0x18005640c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056411  mov     ebx, eax
0x180056413  test    eax, eax
0x180056415  js      loc_180056520
0x18005641b  mov     rcx, cs:WPP_GLOBAL_Control
0x180056422  cmp     rcx, rsi
0x180056425  jz      short loc_18005644C
0x180056427  test    [rcx+1Ch], r13d
0x18005642b  jz      short loc_18005644C
0x18005642d  cmp     byte ptr [rcx+19h], 4
0x180056431  jb      short loc_18005644C
0x180056433  mov     edx, 1Dh
0x180056438  mov     r9, [rbp+57h+pv]
0x18005643c  lea     r8, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids
0x180056443  mov     rcx, [rcx+10h]
0x180056447  call    WPP_SF_S
0x18005644c  mov     rdx, [rbp+57h+pvar+8]
0x180056450  mov     rcx, [rbp+57h+pv]
0x180056454  call    cs:__imp__o__wcsicmp
0x18005645a  test    eax, eax
0x18005645c  jnz     loc_1800564F6
0x180056462  mov     rcx, [rbp+57h+var_78]
0x180056466  mov     [rbp+57h+var_78], r15
0x18005646a  test    rcx, rcx
0x18005646d  jz      short loc_18005647C
0x18005646f  mov     rax, [rcx]
0x180056472  mov     rax, [rax+10h]
0x180056476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005647b  nop
0x18005647c  lea     rax, [rbp+57h+var_78]
0x180056480  mov     qword ptr [rsp+0C0h+ppv], rax; ppv
0x180056485  lea     r9, _GUID_6ca19947_8747_46ab_879e_349c4dbb88fb; riid
0x18005648c  xor     edx, edx; pUnkOuter
0x18005648e  lea     r8d, [rdx+17h]; dwClsContext
0x180056492  lea     rcx, _GUID_06cca63e_9941_441b_b004_39f999ada412; rclsid
0x180056499  call    cs:__imp_CoCreateInstance
0x18005649f  mov     ebx, eax
0x1800564a1  test    eax, eax
0x1800564a3  js      short loc_180056519
0x1800564a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800564ac  cmp     rcx, rsi
0x1800564af  jz      short loc_1800564D6
0x1800564b1  test    [rcx+1Ch], r13d
0x1800564b5  jz      short loc_1800564D6
0x1800564b7  cmp     byte ptr [rcx+19h], 4
0x1800564bb  jb      short loc_1800564D6
0x1800564bd  mov     edx, 1Eh
0x1800564c2  mov     r9, [rbp+57h+pv]
0x1800564c6  lea     r8, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids
0x1800564cd  mov     rcx, [rcx+10h]
0x1800564d1  call    WPP_SF_S
0x1800564d6  mov     rcx, [rbp+57h+var_78]
0x1800564da  mov     rax, [rcx]
0x1800564dd  mov     r8d, 4
0x1800564e3  mov     rdx, [rbp+57h+var_88]
0x1800564e7  mov     rax, [rax+28h]
0x1800564eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800564f0  mov     ebx, eax
0x1800564f2  test    eax, eax
0x1800564f4  js      short loc_180056512
0x1800564f6  lea     rcx, [rbp+57h+pvar]; pvar
0x1800564fa  call    cs:__imp_PropVariantClear
0x180056500  nop
0x180056501  lea     rcx, [rbp+57h+var_50]; pvar
0x180056505  call    cs:__imp_PropVariantClear
0x18005650b  inc     edi
0x18005650d  jmp     loc_18005625E
0x180056512  mov     edx, 2F1h
0x180056517  jmp     short loc_18005654F
0x180056519  mov     edx, 2EEh
0x18005651e  jmp     short loc_18005654F
0x180056520  mov     edx, 2E7h
0x180056525  jmp     short loc_18005654F
0x180056527  mov     edx, 2E2h
0x18005652c  jmp     short loc_18005654F
0x18005652e  mov     edx, 2DBh
0x180056533  jmp     short loc_18005654F
0x180056535  mov     edx, 2D8h
0x18005653a  jmp     short loc_18005654F
0x18005653c  mov     edx, 2CFh
0x180056541  jmp     short loc_18005654F
0x180056543  mov     edx, 2CEh
0x180056548  jmp     short loc_18005654F
0x18005654a  mov     edx, 2CBh; void *
0x18005654f  mov     rcx, [rbp+5Fh]; this
0x180056553  mov     r9d, eax; char *
0x180056556  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audioendpoin"...
0x18005655d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056562  nop
0x180056563  lea     rcx, [rbp+57h+pvar]; pvar
0x180056567  call    cs:__imp_PropVariantClear
0x18005656d  nop
0x18005656e  lea     rcx, [rbp+57h+var_50]; pvar
0x180056572  call    cs:__imp_PropVariantClear
0x180056578  jmp     loc_180056239
0x18005657d  lea     rcx, [rbp+57h+var_90]
0x180056581  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180056586  nop
0x180056587  mov     rcx, [rbp+57h+pv]; pv
0x18005658b  test    rcx, rcx
0x18005658e  jz      short loc_180056596
0x180056590  call    cs:__imp_CoTaskMemFree
0x180056596  mov     ebx, r15d
0x180056599  lea     rcx, [rbp+57h+var_78]
0x18005659d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800565a2  nop
0x1800565a3  lea     rcx, [rbp+57h+var_80]
0x1800565a7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800565ac  nop
0x1800565ad  lea     rcx, [rbp+57h+var_88]
0x1800565b1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800565b6  nop
0x1800565b7  lea     rcx, [rbp+57h+var_70]
0x1800565bb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800565c0  mov     eax, ebx
0x1800565c2  add     rsp, 90h
  ... truncated ...
```
