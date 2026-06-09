# DeviceAccessHandler::InternalLoadDeviceConfiguration_CameraStudioEffects_Enabled(IFSService *,ushort const *,ushort const *,ushort const *,IMFAttributes * *)

- ea: `0x18007ef70`
- end: `0x18007f663`
- name: `?InternalLoadDeviceConfiguration_CameraStudioEffects_Enabled@DeviceAccessHandler@@AEAAJPEAUIFSService@@PEBG11PEAPEAUIMFAttributes@@@Z`
- size: `1779`
- prototype: `int(DeviceAccessHandler *__hidden this, struct IFSService *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IMFAttributes **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007e94c`

## callees

- `0x180003e20`
- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x180009658`
- `0x180017f60`
- `0x180030f00`
- `0x180032934`
- `0x180033050`
- `0x180034f9c`
- `0x18003b884`
- `0x18007ef70`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007f3c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007f441`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007f3c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007f441`
- `MFPlat!MFCreateAttributes` at `0x18007f303`
- `MFPlat!MFCreateAttributes` at `0x18007f4c4`
- `MFPlat!MFCreateAttributes` at `0x18007f56d`
- `MFPlat!MFCreateAttributes` at `0x18007f303`
- `MFPlat!MFCreateAttributes` at `0x18007f4c4`
- `MFPlat!MFCreateAttributes` at `0x18007f56d`

## pseudocode

```c
__int64 __fastcall DeviceAccessHandler::InternalLoadDeviceConfiguration_CameraStudioEffects_Enabled(
        DeviceAccessHandler *this,
        struct IFSService *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct IMFAttributes **a6)
{
  __int64 v6; // rbx
  const char *v10; // rax
  const char *v11; // rax
  const char *v12; // rax
  char v13; // di
  __int64 v14; // rax
  char v15; // di
  __int64 v16; // rax
  __int64 *v17; // rdx
  HRESULT v18; // eax
  int v19; // edi
  __int64 v20; // rdx
  UINT32 v21; // edi
  unsigned int v22; // r14d
  int v23; // eax
  __int64 v24; // rdx
  UINT32 v25; // ebx
  UINT32 v26; // edi
  __int64 v27; // rdx
  UINT32 cInitialSize[2]; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v30; // [rsp+38h] [rbp-51h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+40h] [rbp-49h] BYREF
  struct IFSConfiguration *v32; // [rsp+48h] [rbp-41h] BYREF
  struct IFSConfiguration *v33; // [rsp+50h] [rbp-39h] BYREF
  struct IFSConfiguration *v34; // [rsp+58h] [rbp-31h] BYREF
  __int64 v35; // [rsp+60h] [rbp-29h] BYREF
  PROPVARIANT pvar[2]; // [rsp+68h] [rbp-21h] BYREF
  __int64 v37; // [rsp+78h] [rbp-11h]
  GUID v38; // [rsp+80h] [rbp-9h] BYREF

  v6 = 0;
  v35 = 0;
  v32 = 0;
  v34 = 0;
  v33 = 0;
  ppMFAttributes = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v10 = (const char *)a3;
    if ( !a3 )
      v10 = L"<nullptr>";
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      110,
      (unsigned int)&WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
      (_DWORD)this,
      (__int64)v10);
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v11 = (const char *)a4;
      if ( !a4 )
        v11 = L"<nullptr>";
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        111,
        (unsigned int)&WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
        (_DWORD)this,
        (__int64)v11);
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        v12 = (const char *)a5;
        if ( !a5 )
          v12 = L"<nullptr>";
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          112,
          (unsigned int)&WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
          (_DWORD)this,
          (__int64)v12);
      }
    }
  }
  *a6 = 0;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v32);
  if ( (int)FSLoadAllAppsDeviceConfiguration(a3, &v32) >= 0 && (unsigned __int8)byte_18010EC4D >= 0x10u )
  {
    v30 = 0;
    (*(void (__fastcall **)(struct IFSConfiguration *, unsigned int *))(*(_QWORD *)v32 + 240LL))(v32, &v30);
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 113, &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids, this, v30);
  }
  if ( a4 )
  {
    *(_QWORD *)cInitialSize = 0;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(cInitialSize);
    if ( (int)FSCreateConfigurationKey(a3, a4, 0, (struct IFSConfigurationKey **)cInitialSize) < 0 )
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(cInitialSize);
    if ( *(_QWORD *)cInitialSize )
    {
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v34);
      v13 = FSLoadDeviceConfigurationByKey(*(struct IFSConfigurationKey **)cInitialSize, &v34);
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        v14 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)cInitialSize + 48LL))(*(_QWORD *)cInitialSize);
        WPP_SF_qDS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          114,
          (unsigned int)&WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
          (_DWORD)this,
          v13,
          v14);
      }
    }
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)cInitialSize);
  }
  if ( a5 )
  {
    *(_QWORD *)cInitialSize = 0;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(cInitialSize);
    if ( (int)FSCreateConfigurationKey(a3, 0, a5, (struct IFSConfigurationKey **)cInitialSize) < 0 )
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(cInitialSize);
    if ( *(_QWORD *)cInitialSize )
    {
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v33);
      v15 = FSLoadDeviceConfigurationByKey(*(struct IFSConfigurationKey **)cInitialSize, &v33);
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        v16 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)cInitialSize + 48LL))(*(_QWORD *)cInitialSize);
        WPP_SF_qDS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          115,
          (unsigned int)&WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
          (_DWORD)this,
          v15,
          v16);
      }
    }
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)cInitialSize);
  }
  if ( v34 )
  {
    v17 = (__int64 *)&v34;
  }
  else
  {
    if ( !v33 )
      goto LABEL_34;
    v17 = (__int64 *)&v33;
  }
  wil::com_ptr_t<IFSControl,wil::err_returncode_policy>::operator=(&v35, v17);
  v6 = v35;
LABEL_34:
  if ( v32 )
  {
    cInitialSize[0] = 0;
    if ( v6 )
    {
      v30 = 0;
      v18 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, UINT32 *))(*(_QWORD *)v32 + 240LL))(v32, cInitialSize);
      v19 = v18;
      if ( v18 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_87;
        v20 = 116;
        goto LABEL_39;
      }
      v18 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v6 + 240LL))(v6, &v30);
      v19 = v18;
      if ( v18 < 0 )
      {
        if ( g_wppLevels )
        {
          v20 = 117;
LABEL_39:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v20,
            &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
            this,
            v18);
          goto LABEL_87;
        }
        goto LABEL_87;
      }
      v21 = cInitialSize[0] + v30;
      if ( cInitialSize[0] + v30 < cInitialSize[0] )
      {
        v19 = -2147024362;
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            118,
            &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
            this,
            -2147024362);
        goto LABEL_87;
      }
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
      v18 = MFCreateAttributes(&ppMFAttributes, v21);
      v19 = v18;
      if ( v18 < 0 )
      {
        if ( g_wppLevels )
        {
          v20 = 119;
          goto LABEL_39;
        }
LABEL_87:
        if ( byte_18010EC4D )
        {
          v27 = 130;
LABEL_91:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            v27,
            &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
            this,
            v19);
          goto LABEL_92;
        }
        goto LABEL_92;
      }
      v18 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, IMFAttributes *))(*(_QWORD *)v32 + 256LL))(
              v32,
              ppMFAttributes);
      v19 = v18;
      if ( v18 < 0 )
      {
        if ( g_wppLevels )
        {
          v20 = 120;
          goto LABEL_39;
        }
        goto LABEL_87;
      }
      v22 = 0;
      if ( v30 )
      {
        while ( 1 )
        {
          v37 = 0;
          *(_OWORD *)pvar = 0;
          v38 = GUID_00000000_0000_0000_0000_000000000000;
          v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, PROPVARIANT *))(*(_QWORD *)v6 + 248LL))(
                  v6,
                  v22,
                  &v38,
                  pvar);
          v19 = v23;
          if ( v23 < 0 )
            break;
          v23 = ((__int64 (__fastcall *)(IMFAttributes *, GUID *, PROPVARIANT *))ppMFAttributes->lpVtbl->SetItem)(
                  ppMFAttributes,
                  &v38,
                  pvar);
          v19 = v23;
          if ( v23 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_62;
            v24 = 122;
            goto LABEL_61;
          }
          PropVariantClear(pvar);
          if ( ++v22 >= v30 )
            goto LABEL_54;
        }
        if ( !g_wppLevels )
          goto LABEL_62;
        v24 = 121;
LABEL_61:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids, this, v23);
LABEL_62:
        PropVariantClear(pvar);
        goto LABEL_87;
      }
LABEL_54:
      v18 = FSMergeCameraControlConfigurationsToAttribute(v32, v6, ppMFAttributes);
      v19 = v18;
      if ( v18 < 0 )
      {
        if ( g_wppLevels )
        {
          v20 = 123;
          goto LABEL_39;
        }
        goto LABEL_87;
      }
    }
    else
    {
      v18 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, UINT32 *))(*(_QWORD *)v32 + 240LL))(v32, cInitialSize);
      v19 = v18;
      if ( v18 < 0 )
      {
        if ( g_wppLevels )
        {
          v20 = 124;
          goto LABEL_39;
        }
        goto LABEL_87;
      }
      v25 = cInitialSize[0];
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
      v18 = MFCreateAttributes(&ppMFAttributes, v25);
      v19 = v18;
      if ( v18 < 0 )
      {
        if ( g_wppLevels )
        {
          v20 = 125;
          goto LABEL_39;
        }
        goto LABEL_87;
      }
      v18 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, IMFAttributes *))(*(_QWORD *)v32 + 256LL))(
              v32,
              ppMFAttributes);
      v19 = v18;
      if ( v18 < 0 )
      {
        if ( g_wppLevels )
        {
          v20 = 126;
          goto LABEL_39;
        }
        goto LABEL_87;
      }
    }
  }
  else if ( v6 )
  {
    cInitialSize[0] = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v6 + 240LL))(v6, cInitialSize);
    v19 = v18;
    if ( v18 < 0 )
    {
      if ( g_wppLevels )
      {
        v20 = 127;
        goto LABEL_39;
      }
      goto LABEL_87;
    }
    v26 = cInitialSize[0];
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
    v18 = MFCreateAttributes(&ppMFAttributes, v26);
    v19 = v18;
    if ( v18 < 0 )
    {
      if ( g_wppLevels )
      {
        v20 = 128;
        goto LABEL_39;
      }
      goto LABEL_87;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, IMFAttributes *))(*(_QWORD *)v6 + 256LL))(v6, ppMFAttributes);
    v19 = v18;
    if ( v18 < 0 )
    {
      if ( g_wppLevels )
      {
        v20 = 129;
        goto LABEL_39;
      }
      goto LABEL_87;
    }
  }
  else
  {
    v19 = 0;
  }
  *a6 = ppMFAttributes;
  ppMFAttributes = 0;
  if ( v19 < 0 )
    goto LABEL_87;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v27 = 131;
    goto LABEL_91;
  }
LABEL_92:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v33);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v34);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v35);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v32);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18007ef70  mov     [rsp-8+arg_8], rbx
0x18007ef75  push    rbp
0x18007ef76  push    rsi
0x18007ef77  push    rdi
0x18007ef78  push    r12
0x18007ef7a  push    r13
0x18007ef7c  push    r14
0x18007ef7e  push    r15
0x18007ef80  lea     rbp, [rsp-17h]
0x18007ef85  sub     rsp, 0A0h
0x18007ef8c  mov     rax, cs:__security_cookie
0x18007ef93  xor     rax, rsp
0x18007ef96  mov     [rbp+47h+var_40], rax
0x18007ef9a  mov     r15, [rbp+47h+arg_20]
0x18007ef9e  xor     r13d, r13d
0x18007efa1  mov     r12, [rbp+47h+arg_28]
0x18007efa5  mov     ebx, r13d
0x18007efa8  mov     [rbp+47h+var_70], rbx
0x18007efac  mov     rdi, r9
0x18007efaf  mov     r14, r8
0x18007efb2  mov     [rbp+47h+var_88], r13
0x18007efb6  mov     rsi, rcx
0x18007efb9  mov     [rbp+47h+var_78], r13
0x18007efbd  mov     [rbp+47h+var_80], r13
0x18007efc1  mov     [rbp+47h+ppMFAttributes], r13
0x18007efc5  cmp     cs:byte_18010EC4D, 8
0x18007efcc  jb      loc_18007F089
0x18007efd2  test    r8, r8
0x18007efd5  lea     rcx, aNullptr_0; "<nullptr>"
0x18007efdc  mov     rax, r8
0x18007efdf  lea     edx, [r13+6Eh]
0x18007efe3  cmovz   rax, rcx
0x18007efe7  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007efee  mov     rcx, cs:WPP_GLOBAL_Control
0x18007eff5  mov     r9, rsi
0x18007eff8  mov     [rsp+0D0h+var_B0], rax
0x18007effd  mov     rcx, [rcx+0D8h]
0x18007f004  call    WPP_SF_qS
0x18007f009  cmp     cs:byte_18010EC4D, 8
0x18007f010  jb      short loc_18007F089
0x18007f012  test    rdi, rdi
0x18007f015  lea     rcx, aNullptr_0; "<nullptr>"
0x18007f01c  mov     rax, rdi
0x18007f01f  lea     edx, [r13+6Fh]
0x18007f023  cmovz   rax, rcx
0x18007f027  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007f02e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f035  mov     r9, rsi
0x18007f038  mov     [rsp+0D0h+var_B0], rax
0x18007f03d  mov     rcx, [rcx+0D8h]
0x18007f044  call    WPP_SF_qS
0x18007f049  cmp     cs:byte_18010EC4D, 8
0x18007f050  jb      short loc_18007F089
0x18007f052  test    r15, r15
0x18007f055  lea     rcx, aNullptr_0; "<nullptr>"
0x18007f05c  mov     rax, r15
0x18007f05f  lea     edx, [r13+70h]
0x18007f063  cmovz   rax, rcx
0x18007f067  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007f06e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f075  mov     r9, rsi
0x18007f078  mov     [rsp+0D0h+var_B0], rax
0x18007f07d  mov     rcx, [rcx+0D8h]
0x18007f084  call    WPP_SF_qS
0x18007f089  lea     rcx, [rbp+47h+var_88]
0x18007f08d  mov     [r12], r13
0x18007f091  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18007f096  lea     rdx, [rbp+47h+var_88]; struct IFSConfiguration **
0x18007f09a  mov     rcx, r14; unsigned __int16 *
0x18007f09d  call    FSLoadAllAppsDeviceConfiguration
0x18007f0a2  test    eax, eax
0x18007f0a4  js      short loc_18007F0FC
0x18007f0a6  cmp     cs:byte_18010EC4D, 10h
0x18007f0ad  jb      short loc_18007F0FC
0x18007f0af  mov     rcx, [rbp+47h+var_88]
0x18007f0b3  lea     rdx, [rbp+47h+var_98]
0x18007f0b7  mov     [rbp+47h+var_98], r13d
0x18007f0bb  mov     rax, [rcx]
0x18007f0be  mov     rax, [rax+0F0h]
0x18007f0c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f0ca  cmp     cs:byte_18010EC4D, 8
0x18007f0d1  jb      short loc_18007F0FC
0x18007f0d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f0da  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007f0e1  mov     eax, [rbp+47h+var_98]
0x18007f0e4  mov     edx, 71h ; 'q'
0x18007f0e9  mov     r9, rsi
0x18007f0ec  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18007f0f0  mov     rcx, [rcx+0D8h]
0x18007f0f7  call    WPP_SF_qD
0x18007f0fc  test    rdi, rdi
0x18007f0ff  jz      loc_18007F19C
0x18007f105  lea     rcx, [rbp+47h+cInitialSize]
0x18007f109  mov     qword ptr [rbp+47h+cInitialSize], r13
0x18007f10d  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18007f112  lea     r9, [rbp+47h+cInitialSize]; struct IFSConfigurationKey **
0x18007f116  xor     r8d, r8d; unsigned __int16 *
0x18007f119  mov     rdx, rdi; unsigned __int16 *
0x18007f11c  mov     rcx, r14; unsigned __int16 *
0x18007f11f  call    FSCreateConfigurationKey
0x18007f124  test    eax, eax
0x18007f126  jns     short loc_18007F131
0x18007f128  lea     rcx, [rbp+47h+cInitialSize]
0x18007f12c  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18007f131  cmp     qword ptr [rbp+47h+cInitialSize], r13
0x18007f135  jz      short loc_18007F193
0x18007f137  lea     rcx, [rbp+47h+var_78]
0x18007f13b  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18007f140  mov     rcx, qword ptr [rbp+47h+cInitialSize]; struct IFSConfigurationKey *
0x18007f144  lea     rdx, [rbp+47h+var_78]; struct IFSConfiguration **
0x18007f148  call    FSLoadDeviceConfigurationByKey
0x18007f14d  mov     edi, eax
0x18007f14f  cmp     cs:byte_18010EC4D, 8
0x18007f156  jb      short loc_18007F193
0x18007f158  mov     rcx, qword ptr [rbp+47h+cInitialSize]
0x18007f15c  mov     rdx, [rcx]
0x18007f15f  mov     rax, [rdx+30h]
0x18007f163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f168  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f16f  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007f176  mov     [rsp+0D0h+var_A8], rax
0x18007f17b  mov     edx, 72h ; 'r'
0x18007f180  mov     r9, rsi
0x18007f183  mov     dword ptr [rsp+0D0h+var_B0], edi
0x18007f187  mov     rcx, [rcx+0D8h]
0x18007f18e  call    WPP_SF_qDS
0x18007f193  lea     rcx, [rbp+47h+cInitialSize]; void *
0x18007f197  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18007f19c  test    r15, r15
0x18007f19f  jz      loc_18007F23B
0x18007f1a5  lea     rcx, [rbp+47h+cInitialSize]
0x18007f1a9  mov     qword ptr [rbp+47h+cInitialSize], r13
0x18007f1ad  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18007f1b2  lea     r9, [rbp+47h+cInitialSize]; struct IFSConfigurationKey **
0x18007f1b6  mov     r8, r15; unsigned __int16 *
0x18007f1b9  xor     edx, edx; unsigned __int16 *
0x18007f1bb  mov     rcx, r14; unsigned __int16 *
0x18007f1be  call    FSCreateConfigurationKey
0x18007f1c3  test    eax, eax
0x18007f1c5  jns     short loc_18007F1D0
0x18007f1c7  lea     rcx, [rbp+47h+cInitialSize]
0x18007f1cb  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18007f1d0  cmp     qword ptr [rbp+47h+cInitialSize], r13
0x18007f1d4  jz      short loc_18007F232
0x18007f1d6  lea     rcx, [rbp+47h+var_80]
0x18007f1da  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18007f1df  mov     rcx, qword ptr [rbp+47h+cInitialSize]; struct IFSConfigurationKey *
0x18007f1e3  lea     rdx, [rbp+47h+var_80]; struct IFSConfiguration **
0x18007f1e7  call    FSLoadDeviceConfigurationByKey
0x18007f1ec  mov     edi, eax
0x18007f1ee  cmp     cs:byte_18010EC4D, 8
0x18007f1f5  jb      short loc_18007F232
0x18007f1f7  mov     rcx, qword ptr [rbp+47h+cInitialSize]
0x18007f1fb  mov     rdx, [rcx]
0x18007f1fe  mov     rax, [rdx+30h]
0x18007f202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f207  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f20e  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007f215  mov     [rsp+0D0h+var_A8], rax
0x18007f21a  mov     edx, 73h ; 's'
0x18007f21f  mov     r9, rsi
0x18007f222  mov     dword ptr [rsp+0D0h+var_B0], edi
0x18007f226  mov     rcx, [rcx+0D8h]
0x18007f22d  call    WPP_SF_qDS
0x18007f232  lea     rcx, [rbp+47h+cInitialSize]; void *
0x18007f236  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18007f23b  cmp     [rbp+47h+var_78], r13
0x18007f23f  jz      short loc_18007F247
0x18007f241  lea     rdx, [rbp+47h+var_78]
0x18007f245  jmp     short loc_18007F251
0x18007f247  cmp     [rbp+47h+var_80], r13
0x18007f24b  jz      short loc_18007F25E
0x18007f24d  lea     rdx, [rbp+47h+var_80]
0x18007f251  lea     rcx, [rbp+47h+var_70]
0x18007f255  call    ??4?$com_ptr_t@UIFSControl@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IFSControl,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IFSControl,wil::err_returncode_policy> const &)
0x18007f25a  mov     rbx, [rbp+47h+var_70]
0x18007f25e  mov     rcx, [rbp+47h+var_88]
0x18007f262  mov     r15d, 1
0x18007f268  test    rcx, rcx
0x18007f26b  jz      loc_18007F51F
0x18007f271  mov     [rbp+47h+cInitialSize], r13d
0x18007f275  lea     rdx, [rbp+47h+cInitialSize]
0x18007f279  test    rbx, rbx
0x18007f27c  jz      loc_18007F486
0x18007f282  mov     [rbp+47h+var_98], r13d
0x18007f286  mov     rax, [rcx]
0x18007f289  mov     rax, [rax+0F0h]
0x18007f290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f295  mov     edi, eax
0x18007f297  test    eax, eax
0x18007f299  jns     short loc_18007F2B5
0x18007f29b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007f2a2  jb      loc_18007F5CE
0x18007f2a8  lea     edx, [r15+73h]
0x18007f2ac  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18007f2b0  jmp     loc_18007F467
0x18007f2b5  mov     rax, [rbx]
0x18007f2b8  lea     rdx, [rbp+47h+var_98]
0x18007f2bc  mov     rcx, rbx
0x18007f2bf  mov     rax, [rax+0F0h]
0x18007f2c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f2cb  mov     edi, eax
0x18007f2cd  test    eax, eax
0x18007f2cf  jns     short loc_18007F2E5
0x18007f2d1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007f2d8  jb      loc_18007F5CE
0x18007f2de  mov     edx, 75h ; 'u'
0x18007f2e3  jmp     short loc_18007F2AC
0x18007f2e5  mov     edi, [rbp+47h+var_98]
0x18007f2e8  add     edi, [rbp+47h+cInitialSize]
0x18007f2eb  cmp     edi, [rbp+47h+cInitialSize]
0x18007f2ee  jb      loc_18007F44C
0x18007f2f4  lea     rcx, [rbp+47h+ppMFAttributes]
0x18007f2f8  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18007f2fd  mov     edx, edi; cInitialSize
0x18007f2ff  lea     rcx, [rbp+47h+ppMFAttributes]; ppMFAttributes
0x18007f303  call    cs:__imp_MFCreateAttributes
0x18007f309  mov     edi, eax
0x18007f30b  test    eax, eax
0x18007f30d  jns     short loc_18007F323
0x18007f30f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007f316  jb      loc_18007F5CE
0x18007f31c  mov     edx, 77h ; 'w'
0x18007f321  jmp     short loc_18007F2AC
0x18007f323  mov     rcx, [rbp+47h+var_88]
0x18007f327  mov     rdx, [rbp+47h+ppMFAttributes]
0x18007f32b  mov     rax, [rcx]
0x18007f32e  mov     rax, [rax+100h]
0x18007f335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f33a  mov     edi, eax
0x18007f33c  test    eax, eax
0x18007f33e  jns     short loc_18007F357
0x18007f340  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007f347  jb      loc_18007F5CE
0x18007f34d  mov     edx, 78h ; 'x'
0x18007f352  jmp     loc_18007F2AC
0x18007f357  mov     r14d, r13d
0x18007f35a  cmp     [rbp+47h+var_98], r13d
0x18007f35e  jbe     short loc_18007F3D0
0x18007f360  movaps  xmm1, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18007f367  lea     r9, [rbp+47h+pvar]
0x18007f36b  xor     eax, eax
0x18007f36d  lea     r8, [rbp+47h+var_50]
0x18007f371  mov     [rbp+47h+var_58], rax
0x18007f375  xorps   xmm0, xmm0
0x18007f378  movups  xmmword ptr [rbp+47h+pvar], xmm0
0x18007f37c  mov     edx, r14d
0x18007f37f  mov     rcx, rbx
0x18007f382  movdqu  [rbp+47h+var_50], xmm1
0x18007f387  mov     rax, [rbx]
0x18007f38a  mov     rax, [rax+0F8h]
0x18007f391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f396  mov     edi, eax
0x18007f398  test    eax, eax
0x18007f39a  js      short loc_18007F411
0x18007f39c  mov     rcx, [rbp+47h+ppMFAttributes]
0x18007f3a0  lea     r8, [rbp+47h+pvar]
0x18007f3a4  lea     rdx, [rbp+47h+var_50]
0x18007f3a8  mov     rax, [rcx]
0x18007f3ab  mov     rax, [rax+90h]
0x18007f3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f3b7  mov     edi, eax
0x18007f3b9  test    eax, eax
0x18007f3bb  js      short loc_18007F401
0x18007f3bd  lea     rcx, [rbp+47h+pvar]; pvar
0x18007f3c1  call    cs:__imp_PropVariantClear
0x18007f3c7  add     r14d, r15d
0x18007f3ca  cmp     r14d, [rbp+47h+var_98]
0x18007f3ce  jb      short loc_18007F360
0x18007f3d0  mov     r8, [rbp+47h+ppMFAttributes]
0x18007f3d4  mov     rdx, rbx
0x18007f3d7  mov     rcx, [rbp+47h+var_88]
0x18007f3db  call    FSMergeCameraControlConfigurationsToAttribute
0x18007f3e0  mov     edi, eax
0x18007f3e2  test    eax, eax
0x18007f3e4  jns     loc_18007F5BE
0x18007f3ea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007f3f1  jb      loc_18007F5CE
0x18007f3f7  mov     edx, 7Bh ; '{'
0x18007f3fc  jmp     loc_18007F2AC
0x18007f401  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007f408  jb      short loc_18007F43D
0x18007f40a  mov     edx, 7Ah ; 'z'
0x18007f40f  jmp     short loc_18007F41F
0x18007f411  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007f418  jb      short loc_18007F43D
0x18007f41a  mov     edx, 79h ; 'y'
0x18007f41f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f426  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007f42d  mov     r9, rsi
0x18007f430  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18007f434  mov     rcx, [rcx+10h]
0x18007f438  call    WPP_SF_qD
0x18007f43d  lea     rcx, [rbp+47h+pvar]; pvar
0x18007f441  call    cs:__imp_PropVariantClear
0x18007f447  jmp     loc_18007F5CE
0x18007f44c  mov     edi, 80070216h
0x18007f451  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007f458  jb      loc_18007F5CE
0x18007f45e  mov     edx, 76h ; 'v'
  ... truncated ...
```
