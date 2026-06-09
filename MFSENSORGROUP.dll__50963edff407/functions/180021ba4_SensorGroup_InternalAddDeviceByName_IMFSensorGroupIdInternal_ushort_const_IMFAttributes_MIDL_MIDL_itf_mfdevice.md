# SensorGroup::InternalAddDeviceByName(IMFSensorGroupIdInternal *,ushort const *,IMFAttributes *,__MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0009 *,ulong)

- ea: `0x180021ba4`
- end: `0x1800223a0`
- name: `?InternalAddDeviceByName@SensorGroup@@IEAAJPEAUIMFSensorGroupIdInternal@@PEBGPEAUIMFAttributes@@PEAU__MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0009@@K@Z`
- size: `2044`
- prototype: `__int64 __fastcall(SensorGroup *__hidden this, struct IMFSensorGroupIdInternal *, const unsigned __int16 *, struct IMFAttributes *, struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0009 *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004ba04`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x18000aa08`
- `0x180021ba4`
- `0x1800231c8`
- `0x180023c94`
- `0x180028d34`
- `0x18002c008`
- `0x180044f30`
- `0x18004c758`
- `0x18004dfe8`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021fe3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002201e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021fe3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002201e`
- `MFPlat!MFCreateAttributes` at `0x180021c42`
- `MFPlat!MFCreateAttributes` at `0x180021c42`

## pseudocode

```c
__int64 __fastcall SensorGroup::InternalAddDeviceByName(
        SensorGroup *this,
        struct IMFSensorGroupIdInternal *a2,
        const unsigned __int16 *a3,
        struct IMFAttributes *a4)
{
  const char *v7; // rax
  HRESULT v8; // eax
  int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rdx
  struct IMFSensorDeviceInternal *v12; // rcx
  __int64 v13; // rcx
  int (__fastcall ***v14)(_QWORD, GUID *, struct IMFSensorGroupPlugin2 **); // rcx
  unsigned int v15; // r15d
  int v16; // eax
  __int64 v17; // rdx
  __int64 *v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v22)(_QWORD, GUID *, __int64 *); // rax
  __int64 (__fastcall *v23)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, __int64 *); // rbx
  unsigned int i; // edi
  int v27; // eax
  __int64 (__fastcall ***v28)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v29)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v30; // rcx
  struct IMFSensorDeviceInternal *v31; // rbx
  __int64 (__fastcall **v32)(struct IMFSensorDeviceInternal *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v33)(struct IMFSensorDeviceInternal *, GUID *, __int64 *); // rdi
  bool v34; // sf
  unsigned int v35; // eax
  __int64 v36; // rdx
  __int64 (__fastcall ***v38)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-79h] BYREF
  __int64 v39; // [rsp+48h] [rbp-71h] BYREF
  __int64 v40; // [rsp+50h] [rbp-69h] BYREF
  __int64 v41; // [rsp+58h] [rbp-61h] BYREF
  struct IMFSensorGroupPlugin2 *v42; // [rsp+60h] [rbp-59h] BYREF
  unsigned int v43; // [rsp+68h] [rbp-51h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+70h] [rbp-49h] BYREF
  int v45; // [rsp+78h] [rbp-41h] BYREF
  struct IMFSensorDeviceInternal *v46; // [rsp+80h] [rbp-39h] BYREF
  int v47; // [rsp+88h] [rbp-31h] BYREF
  __int64 v48; // [rsp+90h] [rbp-29h] BYREF
  PROPVARIANT pvar[2]; // [rsp+98h] [rbp-21h] BYREF
  __int64 v50; // [rsp+A8h] [rbp-11h]
  GUID v51; // [rsp+B0h] [rbp-9h] BYREF

  v48 = 0;
  v46 = 0;
  v45 = 0;
  v47 = 0;
  ppMFAttributes = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v7 = L"<nullptr>";
    if ( a3 )
      v7 = (const char *)a3;
    WPP_SF_qqS(*((_QWORD *)WPP_GLOBAL_Control + 27), (_DWORD)a2, (_DWORD)a3, (_DWORD)this, (char)a2, (__int64)v7);
  }
  ppMFAttributes = 0;
  v8 = MFCreateAttributes(&ppMFAttributes, 1u);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( !g_wppLevels )
    {
LABEL_82:
      if ( !byte_18008D62D )
        goto LABEL_87;
      v36 = 190;
      goto LABEL_86;
    }
    v10 = 172;
LABEL_8:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v8);
    goto LABEL_82;
  }
  if ( !a3 )
  {
    v9 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_82;
    v11 = 173;
LABEL_81:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v9);
    goto LABEL_82;
  }
  v12 = v46;
  v46 = 0;
  if ( v12 )
    (*(void (__fastcall **)(struct IMFSensorDeviceInternal *))(*(_QWORD *)v12 + 16LL))(v12);
  v8 = SensorDevice::CreateSensorDeviceInternal(a2, (const unsigned __int16 *)this + 120, &v46);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_82;
    v10 = 174;
    goto LABEL_8;
  }
  v13 = *((_QWORD *)this + 24);
  if ( v13
    && (*(int (__fastcall **)(__int64, const unsigned __int16 *, int *))(*(_QWORD *)v13 + 24LL))(v13, a3, &v47) >= 0
    && v47 )
  {
    v14 = (int (__fastcall ***)(_QWORD, GUID *, struct IMFSensorGroupPlugin2 **))*((_QWORD *)this + 24);
    v38 = 0;
    v40 = 0;
    v15 = 3;
    v41 = 0;
    v39 = 0;
    v43 = 0;
    v42 = 0;
    if ( (**v14)(v14, &GUID_ab032154_d616_44d4_89c8_8cc04619ebf3, &v42) >= 0
      && SensorGroup::InternalSetMEPProperty(this, a3, a2, v42) >= 0 )
    {
      v15 = 2;
      if ( (unsigned __int8)byte_18008D62D >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 175, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this);
    }
    v16 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            MF_DEVSOURCE_ATTRIBUTE_DEVICETYPE,
            v15);
    v9 = v16;
    if ( v16 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_28:
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v42);
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v39);
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v41);
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v40);
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v38);
        goto LABEL_82;
      }
      v17 = 176;
LABEL_27:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v16);
      goto LABEL_28;
    }
    if ( v15 == 3 )
    {
      (*(void (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a2 + 192LL))(
        a2,
        22,
        0,
        0,
        0);
      (*(void (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a2 + 192LL))(
        a2,
        23,
        0,
        0,
        0);
      v18 = (__int64 *)*((_QWORD *)this + 24);
      v19 = *v18;
      v38 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, _QWORD))(v19 + 32))(v18, a3, &v38);
      v9 = v16;
      if ( v16 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_28;
        v17 = 177;
        goto LABEL_27;
      }
      v20 = v40;
      v21 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v38;
      v22 = *v38;
      v40 = 0;
      v23 = *v22;
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v16 = v23(v21, &GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8, &v40);
      v9 = v16;
      if ( v16 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_28;
        v17 = 178;
        goto LABEL_27;
      }
      v24 = v40;
      v25 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 104LL);
      wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(&v39);
      v16 = v25(v24, &v39);
      v9 = v16;
      if ( v16 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_28;
        v17 = 179;
        goto LABEL_27;
      }
      v16 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v39 + 240LL))(v39, &v43);
      v9 = v16;
      if ( v16 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_28;
        v17 = 180;
        goto LABEL_27;
      }
      for ( i = 0; i < v43; ++i )
      {
        v50 = 0;
        v51 = GUID_00000000_0000_0000_0000_000000000000;
        *(_OWORD *)pvar = 0;
        if ( (*(int (__fastcall **)(__int64, _QWORD, GUID *, PROPVARIANT *))(*(_QWORD *)v39 + 248LL))(
               v39,
               i,
               &v51,
               pvar) >= 0 )
        {
          v27 = ((__int64 (__fastcall *)(IMFAttributes *, GUID *, PROPVARIANT *))ppMFAttributes->lpVtbl->SetItem)(
                  ppMFAttributes,
                  &v51,
                  pvar);
          v9 = v27;
          if ( v27 < 0 )
          {
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                181,
                &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
                this,
                v27);
            PropVariantClear(pvar);
            goto LABEL_28;
          }
        }
        PropVariantClear(pvar);
      }
      v28 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v38;
      v29 = **v38;
      wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v41);
      v16 = v29(v28, &GUID_00000000_0000_0000_c000_000000000046, &v41);
      v9 = v16;
      if ( v16 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_28;
        v17 = 182;
        goto LABEL_27;
      }
      v16 = (*(__int64 (__fastcall **)(struct IMFSensorDeviceInternal *, __int64, const unsigned __int16 *, IMFAttributes *, _DWORD, _QWORD, int *))(*(_QWORD *)v46 + 24LL))(
              v46,
              v41,
              a3,
              ppMFAttributes,
              *((_DWORD *)this + 42),
              0,
              &v45);
      v9 = v16;
      if ( v16 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_28;
        v17 = 183;
        goto LABEL_27;
      }
      if ( (unsigned __int8)byte_18008D62D >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 184, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this);
    }
    else
    {
      v16 = (*(__int64 (__fastcall **)(struct IMFSensorDeviceInternal *, const unsigned __int16 *, IMFAttributes *, _QWORD, int *))(*(_QWORD *)v46 + 32LL))(
              v46,
              a3,
              ppMFAttributes,
              *((unsigned int *)this + 42),
              &v45);
      v9 = v16;
      if ( v16 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_28;
        v17 = 185;
        goto LABEL_27;
      }
    }
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v42);
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v39);
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v41);
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v40);
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v38);
  }
  else
  {
    (*(void (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD))(*(_QWORD *)a2 + 192LL))(a2, 22, 0);
    (*(void (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD))(*(_QWORD *)a2 + 192LL))(a2, 23, 0);
    v43 = 0;
    v34 = ((int (__fastcall *)(IMFAttributes *, __int64 *, unsigned int *))ppMFAttributes->lpVtbl->GetUINT32)(
            ppMFAttributes,
            MF_DEVSOURCE_ATTRIBUTE_DEVICETYPE,
            &v43) < 0;
    v35 = 0;
    if ( !v34 )
      v35 = v43;
    if ( !v35 )
    {
      v8 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
             ppMFAttributes,
             MF_DEVSOURCE_ATTRIBUTE_DEVICETYPE,
             1);
      v9 = v8;
      if ( v8 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_82;
        v10 = 186;
        goto LABEL_8;
      }
    }
    v8 = (*(__int64 (__fastcall **)(struct IMFSensorDeviceInternal *, const unsigned __int16 *, IMFAttributes *, _QWORD, int *))(*(_QWORD *)v46 + 32LL))(
           v46,
           a3,
           ppMFAttributes,
           *((unsigned int *)this + 42),
           &v45);
    v9 = v8;
    if ( v8 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_82;
      v10 = 187;
      goto LABEL_8;
    }
  }
  v30 = v48;
  v31 = v46;
  v32 = *(__int64 (__fastcall ***)(struct IMFSensorDeviceInternal *, GUID *, __int64 *))v46;
  v48 = 0;
  v33 = *v32;
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  v9 = v33(v31, &GUID_fb9f48f2_2a18_4e28_9730_786f30f04dc4, &v48);
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_82;
    v11 = 188;
    goto LABEL_81;
  }
  if ( !(unsigned int)CTUnkArray<IMFSensorDevice>::Add((char *)this + 96, v48) )
  {
    v9 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_82;
    v11 = 189;
    goto LABEL_81;
  }
  *((_DWORD *)this + 42) += v45;
  if ( (unsigned __int8)byte_18008D62D < 8u )
    goto LABEL_87;
  v36 = 191;
LABEL_86:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v36, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v9);
LABEL_87:
  if ( ppMFAttributes )
    ((void (__fastcall *)(IMFAttributes *))ppMFAttributes->lpVtbl->Release)(ppMFAttributes);
  if ( v46 )
    (*(void (__fastcall **)(struct IMFSensorDeviceInternal *))(*(_QWORD *)v46 + 16LL))(v46);
  if ( v48 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180021ba4  mov     [rsp-8+arg_18], rbx
0x180021ba9  push    rbp
0x180021baa  push    rsi
0x180021bab  push    rdi
0x180021bac  push    r12
0x180021bae  push    r13
0x180021bb0  push    r14
0x180021bb2  push    r15
0x180021bb4  lea     rbp, [rsp-17h]
0x180021bb9  sub     rsp, 0D0h
0x180021bc0  mov     rax, cs:__security_cookie
0x180021bc7  xor     rax, rsp
0x180021bca  mov     [rbp+47h+var_40], rax
0x180021bce  xor     r12d, r12d
0x180021bd1  mov     r14, r8
0x180021bd4  mov     [rbp+47h+var_70], r12
0x180021bd8  mov     rdi, rdx
0x180021bdb  mov     [rbp+47h+var_80], r12
0x180021bdf  mov     rsi, rcx
0x180021be2  mov     [rbp+47h+var_88], r12d
0x180021be6  mov     [rbp+47h+var_78], r12d
0x180021bea  mov     [rbp+47h+ppMFAttributes], r12
0x180021bee  cmp     cs:byte_18008D62D, 8
0x180021bf5  lea     r15, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x180021bfc  lea     r13d, [r12+1]
0x180021c01  jb      short loc_180021C37
0x180021c03  mov     r9, rcx
0x180021c06  lea     rax, aNullptr; "<nullptr>"
0x180021c0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c14  test    r8, r8
0x180021c17  cmovnz  rax, r8
0x180021c1b  mov     [rsp+100h+var_D8], rax
0x180021c20  mov     rcx, [rcx+0D8h]
0x180021c27  mov     [rsp+100h+var_E0], rdx
0x180021c2c  call    WPP_SF_qqS
0x180021c31  cmp     [rbp+47h+ppMFAttributes], r12
0x180021c35  jnz     short loc_180021C69
0x180021c37  mov     edx, r13d; cInitialSize
0x180021c3a  mov     [rbp+47h+ppMFAttributes], r12
0x180021c3e  lea     rcx, [rbp+47h+ppMFAttributes]; ppMFAttributes
0x180021c42  call    cs:__imp_MFCreateAttributes
0x180021c48  mov     ebx, eax
0x180021c4a  test    eax, eax
0x180021c4c  jns     short loc_180021C69
0x180021c4e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180021c55  jb      loc_1800222ED
0x180021c5b  mov     edx, 0ACh
0x180021c60  mov     dword ptr [rsp+100h+var_E0], eax
0x180021c64  jmp     loc_1800222D7
0x180021c69  test    r14, r14
0x180021c6c  jnz     short loc_180021C8A
0x180021c6e  mov     ebx, 80070057h
0x180021c73  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180021c7a  jb      loc_1800222ED
0x180021c80  mov     edx, 0ADh
0x180021c85  jmp     loc_1800222D3
0x180021c8a  mov     rcx, [rbp+47h+var_80]
0x180021c8e  mov     [rbp+47h+var_80], r12
0x180021c92  test    rcx, rcx
0x180021c95  jz      short loc_180021CA3
0x180021c97  mov     rax, [rcx]
0x180021c9a  mov     rax, [rax+10h]
0x180021c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ca3  lea     rdx, [rsi+0F0h]; unsigned __int16 *
0x180021caa  mov     rcx, rdi; struct IMFSensorGroupIdInternal *
0x180021cad  lea     r8, [rbp+47h+var_80]; struct IMFSensorDeviceInternal **
0x180021cb1  call    ?CreateSensorDeviceInternal@SensorDevice@@SAJPEAUIMFSensorGroupIdInternal@@PEBGPEAPEAUIMFSensorDeviceInternal@@@Z; SensorDevice::CreateSensorDeviceInternal(IMFSensorGroupIdInternal *,ushort const *,IMFSensorDeviceInternal * *)
0x180021cb6  mov     ebx, eax
0x180021cb8  test    eax, eax
0x180021cba  jns     short loc_180021CD0
0x180021cbc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180021cc3  jb      loc_1800222ED
0x180021cc9  mov     edx, 0AEh
0x180021cce  jmp     short loc_180021C60
0x180021cd0  mov     rcx, [rsi+0C0h]
0x180021cd7  test    rcx, rcx
0x180021cda  jz      loc_1800221C2
0x180021ce0  mov     rax, [rcx]
0x180021ce3  lea     r8, [rbp+47h+var_78]
0x180021ce7  mov     rdx, r14
0x180021cea  mov     rax, [rax+18h]
0x180021cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cf3  test    eax, eax
0x180021cf5  js      loc_1800221C2
0x180021cfb  cmp     [rbp+47h+var_78], r12d
0x180021cff  jz      loc_1800221C2
0x180021d05  mov     rcx, [rsi+0C0h]
0x180021d0c  lea     r8, [rbp+47h+var_A0]
0x180021d10  mov     [rbp+47h+var_C0], r12
0x180021d14  lea     rdx, _GUID_ab032154_d616_44d4_89c8_8cc04619ebf3
0x180021d1b  mov     [rbp+47h+var_B0], r12
0x180021d1f  mov     r15d, 3
0x180021d25  mov     [rbp+47h+var_A8], r12
0x180021d29  mov     [rbp+47h+var_B8], r12
0x180021d2d  mov     [rbp+47h+var_98], r12d
0x180021d31  mov     [rbp+47h+var_A0], r12
0x180021d35  mov     rax, [rcx]
0x180021d38  mov     rax, [rax]
0x180021d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d40  test    eax, eax
0x180021d42  js      short loc_180021D8B
0x180021d44  mov     r9, [rbp+47h+var_A0]; struct IMFSensorGroupPlugin2 *
0x180021d48  mov     r8, rdi; struct IMFSensorGroupIdInternal *
0x180021d4b  mov     rdx, r14; unsigned __int16 *
0x180021d4e  mov     rcx, rsi; this
0x180021d51  call    ?InternalSetMEPProperty@SensorGroup@@IEAAJPEBGPEAUIMFSensorGroupIdInternal@@PEAUIMFSensorGroupPlugin2@@@Z; SensorGroup::InternalSetMEPProperty(ushort const *,IMFSensorGroupIdInternal *,IMFSensorGroupPlugin2 *)
0x180021d56  test    eax, eax
0x180021d58  js      short loc_180021D8B
0x180021d5a  mov     r15d, 2
0x180021d60  cmp     cs:byte_18008D62D, 8
0x180021d67  jb      short loc_180021D8B
0x180021d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d70  lea     r8, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x180021d77  mov     edx, 0AFh
0x180021d7c  mov     r9, rsi
0x180021d7f  mov     rcx, [rcx+0D8h]
0x180021d86  call    WPP_SF_q
0x180021d8b  mov     rcx, [rbp+47h+ppMFAttributes]
0x180021d8f  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_DEVICETYPE
0x180021d96  mov     r8d, r15d
0x180021d99  mov     rax, [rcx]
0x180021d9c  mov     rax, [rax+0A8h]
0x180021da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021da8  mov     ebx, eax
0x180021daa  test    eax, eax
0x180021dac  jns     short loc_180021E0C
0x180021dae  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180021db5  jb      short loc_180021DDA
0x180021db7  mov     edx, 0B0h
0x180021dbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180021dc3  lea     r8, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x180021dca  mov     r9, rsi
0x180021dcd  mov     dword ptr [rsp+100h+var_E0], eax
0x180021dd1  mov     rcx, [rcx+10h]
0x180021dd5  call    WPP_SF_qD
0x180021dda  lea     rcx, [rbp+47h+var_A0]
0x180021dde  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180021de3  lea     rcx, [rbp+47h+var_B8]
0x180021de7  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180021dec  lea     rcx, [rbp+47h+var_A8]
0x180021df0  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180021df5  lea     rcx, [rbp+47h+var_B0]
0x180021df9  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180021dfe  lea     rcx, [rbp+47h+var_C0]
0x180021e02  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180021e07  jmp     loc_1800222ED
0x180021e0c  cmp     r15d, 3
0x180021e10  jnz     loc_18002217A
0x180021e16  mov     rax, [rdi]
0x180021e19  lea     edx, [r15+13h]
0x180021e1d  xor     r9d, r9d
0x180021e20  mov     [rsp+100h+var_E0], r12
0x180021e25  xor     r8d, r8d
0x180021e28  mov     rcx, rdi
0x180021e2b  mov     rax, [rax+0C0h]
0x180021e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e37  mov     rax, [rdi]
0x180021e3a  lea     edx, [r15+14h]
0x180021e3e  xor     r9d, r9d
0x180021e41  mov     [rsp+100h+var_E0], r12
0x180021e46  xor     r8d, r8d
0x180021e49  mov     rcx, rdi
0x180021e4c  mov     rax, [rax+0C0h]
0x180021e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e58  mov     rcx, [rbp+47h+var_C0]
0x180021e5c  mov     rbx, [rsi+0C0h]
0x180021e63  mov     rax, [rbx]
0x180021e66  mov     [rbp+47h+var_C0], r12
0x180021e6a  mov     rdi, [rax+20h]
0x180021e6e  test    rcx, rcx
0x180021e71  jz      short loc_180021E7F
0x180021e73  mov     rdx, [rcx]
0x180021e76  mov     rax, [rdx+10h]
0x180021e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e7f  lea     r8, [rbp+47h+var_C0]
0x180021e83  mov     rdx, r14
0x180021e86  mov     rcx, rbx
0x180021e89  mov     rax, rdi
0x180021e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e91  mov     ebx, eax
0x180021e93  test    eax, eax
0x180021e95  jns     short loc_180021EAE
0x180021e97  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180021e9e  jb      loc_180021DDA
0x180021ea4  mov     edx, 0B1h
0x180021ea9  jmp     loc_180021DBC
0x180021eae  mov     rcx, [rbp+47h+var_B0]
0x180021eb2  mov     rbx, [rbp+47h+var_C0]
0x180021eb6  mov     rax, [rbx]
0x180021eb9  mov     [rbp+47h+var_B0], r12
0x180021ebd  mov     rdi, [rax]
0x180021ec0  test    rcx, rcx
0x180021ec3  jz      short loc_180021ED1
0x180021ec5  mov     rdx, [rcx]
0x180021ec8  mov     rax, [rdx+10h]
0x180021ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ed1  lea     r8, [rbp+47h+var_B0]
0x180021ed5  mov     rcx, rbx
0x180021ed8  lea     rdx, _GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8
0x180021edf  mov     rax, rdi
0x180021ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ee7  mov     ebx, eax
0x180021ee9  test    eax, eax
0x180021eeb  jns     short loc_180021F04
0x180021eed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180021ef4  jb      loc_180021DDA
0x180021efa  mov     edx, 0B2h
0x180021eff  jmp     loc_180021DBC
0x180021f04  mov     rdi, [rbp+47h+var_B0]
0x180021f08  lea     rcx, [rbp+47h+var_B8]
0x180021f0c  mov     rax, [rdi]
0x180021f0f  mov     rbx, [rax+68h]
0x180021f13  call    ?reset@?$com_ptr_t@UIMFAttributes@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(void)
0x180021f18  lea     rdx, [rbp+47h+var_B8]
0x180021f1c  mov     rcx, rdi
0x180021f1f  mov     rax, rbx
0x180021f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f27  mov     ebx, eax
0x180021f29  test    eax, eax
0x180021f2b  jns     short loc_180021F44
0x180021f2d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180021f34  jb      loc_180021DDA
0x180021f3a  mov     edx, 0B3h
0x180021f3f  jmp     loc_180021DBC
0x180021f44  mov     rcx, [rbp+47h+var_B8]
0x180021f48  lea     rdx, [rbp+47h+var_98]
0x180021f4c  mov     rax, [rcx]
0x180021f4f  mov     rax, [rax+0F0h]
0x180021f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f5b  mov     ebx, eax
0x180021f5d  test    eax, eax
0x180021f5f  jns     short loc_180021F78
0x180021f61  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180021f68  jb      loc_180021DDA
0x180021f6e  mov     edx, 0B4h
0x180021f73  jmp     loc_180021DBC
0x180021f78  mov     edi, r12d
0x180021f7b  cmp     edi, [rbp+47h+var_98]
0x180021f7e  jnb     loc_180022029
0x180021f84  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180021f8b  mov     rcx, [rbp+47h+var_B8]
0x180021f8f  lea     r9, [rbp+47h+pvar]
0x180021f93  xor     eax, eax
0x180021f95  lea     r8, [rbp+47h+var_50]
0x180021f99  mov     [rbp+47h+var_58], rax
0x180021f9d  xorps   xmm1, xmm1
0x180021fa0  movdqu  [rbp+47h+var_50], xmm0
0x180021fa5  mov     edx, edi
0x180021fa7  movups  xmmword ptr [rbp+47h+pvar], xmm1
0x180021fab  mov     rax, [rcx]
0x180021fae  mov     rax, [rax+0F8h]
0x180021fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fba  test    eax, eax
0x180021fbc  js      short loc_180021FDF
0x180021fbe  mov     rcx, [rbp+47h+ppMFAttributes]
0x180021fc2  lea     r8, [rbp+47h+pvar]
0x180021fc6  lea     rdx, [rbp+47h+var_50]
0x180021fca  mov     rax, [rcx]
0x180021fcd  mov     rax, [rax+90h]
0x180021fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fd9  mov     ebx, eax
0x180021fdb  test    eax, eax
0x180021fdd  js      short loc_180021FEE
0x180021fdf  lea     rcx, [rbp+47h+pvar]; pvar
0x180021fe3  call    cs:__imp_PropVariantClear
0x180021fe9  add     edi, r13d
0x180021fec  jmp     short loc_180021F7B
0x180021fee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180021ff5  jb      short loc_18002201A
0x180021ff7  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ffe  lea     r8, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x180022005  mov     edx, 0B5h
0x18002200a  mov     dword ptr [rsp+100h+var_E0], eax
0x18002200e  mov     r9, rsi
0x180022011  mov     rcx, [rcx+10h]
0x180022015  call    WPP_SF_qD
0x18002201a  lea     rcx, [rbp+47h+pvar]; pvar
0x18002201e  call    cs:__imp_PropVariantClear
0x180022024  jmp     loc_180021DDA
0x180022029  mov     rdi, [rbp+47h+var_C0]
0x18002202d  lea     rcx, [rbp+47h+var_A8]
0x180022031  mov     rax, [rdi]
0x180022034  mov     rbx, [rax]
0x180022037  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x18002203c  lea     r8, [rbp+47h+var_A8]
0x180022040  mov     rcx, rdi
0x180022043  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18002204a  mov     rax, rbx
0x18002204d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022052  mov     ebx, eax
0x180022054  test    eax, eax
0x180022056  jns     short loc_18002206F
0x180022058  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18002205f  jb      loc_180021DDA
0x180022065  mov     edx, 0B6h
0x18002206a  jmp     loc_180021DBC
0x18002206f  mov     r9d, [rsi+0A8h]
0x180022076  lea     rdx, [rbp+47h+var_88]
0x18002207a  mov     rcx, [rbp+47h+var_80]
0x18002207e  mov     r8, r14
  ... truncated ...
```
