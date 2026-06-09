# EnumVideoCaptureSources(IMFAttributes *,IMFActivate * * *,uint *)

- ea: `0x1800a0978`
- end: `0x1800a125f`
- name: `?EnumVideoCaptureSources@@YAJPEAUIMFAttributes@@PEAPEAPEAUIMFActivate@@PEAI@Z`
- size: `2279`
- prototype: `int(struct IMFAttributes *, struct IMFActivate ***, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800a0250`

## callees

- `0x180050d6c`
- `0x180063f00`
- `0x18007626c`
- `0x18009efc4`
- `0x1800a0978`
- `0x1800aa468`
- `0x1800caaac`
- `0x1800e7fdc`
- `0x18012d998`
- `0x180258390`
- `0x1802583a8`
- `0x180258480`
- `0x180259174`
- `0x1802592a0`
- `0x180344cd8`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0bb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0bc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0f5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0f72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0bb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0bc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0f5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0f72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a0cc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a1170`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a0cc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a1170`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800a0e2b`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800a0edb`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800a0e2b`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800a0edb`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800a0e14`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800a0ec4`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800a0e14`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800a0ec4`
- `MFPlat!MFTEnumEx` at `0x1800a0ab4`
- `MFPlat!MFTEnumEx` at `0x1800a0b3c`
- `MFPlat!MFTEnumEx` at `0x1800a1106`
- `MFPlat!MFTEnumEx` at `0x1800a0ab4`
- `MFPlat!MFTEnumEx` at `0x1800a0b3c`
- `MFPlat!MFTEnumEx` at `0x1800a1106`

## pseudocode

```c
__int64 __fastcall EnumVideoCaptureSources(struct IMFAttributes *a1, struct IMFActivate ***a2, unsigned int *a3)
{
  unsigned int *v3; // rbx
  struct IMFActivate ***v4; // r13
  BYTE *v5; // r12
  BYTE *v6; // r15
  HRESULT v7; // eax
  signed int v8; // edi
  __int64 v9; // rdx
  HRESULT v10; // eax
  __int64 v11; // rdx
  char v13; // dl
  UINT32 v14; // eax
  SIZE_T v15; // r13
  IMFActivate **v16; // rax
  __int64 i; // r13
  IMFActivate *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rbx
  int v21; // eax
  CONFIGRET Device_Interface_PropertyW; // eax
  signed int v23; // eax
  CONFIGRET v24; // eax
  signed int v25; // eax
  int v26; // ebx
  IMFActivate *v27; // rcx
  __int64 v28; // rdx
  struct IMFActivate **v29; // rax
  int Instance; // eax
  __int64 v31; // rdx
  bool v32; // [rsp+30h] [rbp-79h]
  UINT32 v33; // [rsp+34h] [rbp-75h] BYREF
  struct IMFActivate ***v34; // [rsp+38h] [rbp-71h]
  UINT32 pnumMFTActivate; // [rsp+40h] [rbp-69h] BYREF
  ULONG PropertyBufferSize; // [rsp+44h] [rbp-65h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+48h] [rbp-61h] BYREF
  UINT32 v38; // [rsp+4Ch] [rbp-5Dh]
  __int64 v39; // [rsp+50h] [rbp-59h] BYREF
  __int64 v40; // [rsp+58h] [rbp-51h] BYREF
  IMFActivate **v41; // [rsp+60h] [rbp-49h] BYREF
  unsigned int v42; // [rsp+68h] [rbp-41h]
  unsigned int *v43; // [rsp+70h] [rbp-39h]
  int v44; // [rsp+78h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-29h] BYREF
  LPCWSTR pszDeviceInterface; // [rsp+88h] [rbp-21h] BYREF
  IMFActivate **pppMFTActivate; // [rsp+90h] [rbp-19h] BYREF
  IMFActivate **v48; // [rsp+98h] [rbp-11h] BYREF
  GUID guidCategory; // [rsp+A0h] [rbp-9h] BYREF
  GUID Buf1; // [rsp+B0h] [rbp+7h] BYREF

  v34 = a2;
  v41 = 0;
  v3 = a3;
  v43 = a3;
  v4 = a2;
  pnumMFTActivate = 0;
  v5 = 0;
  pppMFTActivate = 0;
  v6 = 0;
  v33 = 0;
  v48 = 0;
  pv = 0;
  pszDeviceInterface = 0;
  PropertyBufferSize = 0;
  PropertyType = 0;
  v44 = 0;
  Buf1 = GUID_00000000_0000_0000_0000_000000000000;
  if ( !a3 )
  {
    v7 = MF::OriginateError((MF *)0x80004003LL, (int)a2);
    v8 = v7;
    if ( !g_wppLevels )
      goto LABEL_19;
    v9 = 37;
    goto LABEL_4;
  }
  if ( !a2 )
  {
    v7 = MF::OriginateError((MF *)0x80004003LL, 0);
    v8 = v7;
    if ( g_wppLevels )
    {
      v9 = 38;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids, 0, v7);
      goto LABEL_19;
    }
    goto LABEL_19;
  }
  *a3 = 0;
  *a2 = 0;
  ((void (__fastcall *)(struct IMFAttributes *, const IID *, GUID *))a1->lpVtbl->GetGUID)(
    a1,
    &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_CATEGORY,
    &Buf1);
  if ( memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
  {
    guidCategory = Buf1;
    *v3 = 0;
    v7 = MFTEnumEx(&guidCategory, 0x10000004u, 0, 0, &v41, v3);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( g_wppLevels )
      {
        v9 = 53;
        goto LABEL_4;
      }
      goto LABEL_19;
    }
    if ( (unsigned __int8)byte_1803CECED >= 8u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 54, &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids, *v3);
    LODWORD(i) = *v3;
    if ( !*v3 )
      goto LABEL_18;
    goto LABEL_94;
  }
  guidCategory = CLSID_VideoInputDeviceCategory;
  v7 = MFTEnumEx(&guidCategory, 0x10000004u, 0, 0, &pppMFTActivate, &pnumMFTActivate);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( (unsigned __int8)byte_1803CECED >= 8u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        40,
        &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids,
        pnumMFTActivate);
    guidCategory = GUID_e5323777_f976_4f5b_9b55_b94699c46e44;
    v10 = MFTEnumEx(&guidCategory, 0x10000004u, 0, 0, &v48, &v33);
    v8 = v10;
    if ( v10 < 0 )
    {
      if ( g_wppLevels )
      {
        v11 = 41;
LABEL_17:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids, 0, v10);
      }
LABEL_18:
      v4 = v34;
      goto LABEL_19;
    }
    v13 = byte_1803CECED;
    if ( (unsigned __int8)byte_1803CECED >= 8u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 42, &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids, v33);
      v13 = byte_1803CECED;
    }
    v14 = v33 + pnumMFTActivate;
    v38 = v33 + pnumMFTActivate;
    if ( !(v33 + pnumMFTActivate) )
    {
      if ( (unsigned __int8)v13 >= 8u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 43, &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids);
      goto LABEL_18;
    }
    if ( (unsigned __int8)v13 >= 8u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 44, &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids, v14);
      v14 = v38;
    }
    v15 = 8LL * v14;
    v16 = (IMFActivate **)CoTaskMemAlloc(v15);
    v41 = v16;
    if ( !v16 )
    {
      v10 = -2147024882;
      v8 = -2147024882;
      if ( !g_wppLevels )
        goto LABEL_18;
      v11 = 45;
      goto LABEL_17;
    }
    memset_0(v16, 0, v15);
    for ( i = 0; (unsigned int)i < v33; i = (unsigned int)(i + 1) )
    {
      v41[i] = v48[i];
      v18 = v41[i];
      if ( v18 )
        ((void (__fastcall *)(IMFActivate *))v18->lpVtbl->AddRef)(v18);
    }
    v42 = 0;
    if ( pnumMFTActivate )
    {
      while ( 1 )
      {
        v19 = 0;
        v20 = (unsigned int)v6;
        v38 = 0;
        *(_QWORD *)&guidCategory.Data1 = (unsigned int)v6;
        if ( !v33 )
          goto LABEL_70;
        do
        {
          ComSmartPtr<IUnknown>::ComSmartPtr<IUnknown>(&v40, v41[v19]);
          ComSmartPtr<IUnknown>::ComSmartPtr<IUnknown>(&v39, pppMFTActivate[v20]);
          if ( v40 )
          {
            v21 = (*(__int64 (__fastcall **)(__int64, const GUID *, LPVOID *, int *))(*(_QWORD *)v40 + 104LL))(
                    v40,
                    &MFT_ENUM_HARDWARE_URL_Attribute,
                    &pv,
                    &v44);
            v8 = v21;
            if ( v21 < 0 )
            {
              if ( g_wppLevels )
              {
                v28 = 46;
                goto LABEL_78;
              }
LABEL_79:
              ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v39);
              ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v40);
              v5 = 0;
LABEL_80:
              v6 = 0;
LABEL_81:
              v3 = v43;
              goto LABEL_18;
            }
          }
          if ( v39 )
          {
            v21 = (*(__int64 (__fastcall **)(__int64, const GUID *, LPCWSTR *, int *))(*(_QWORD *)v39 + 104LL))(
                    v39,
                    &MFT_ENUM_HARDWARE_URL_Attribute,
                    &pszDeviceInterface,
                    &v44);
            v8 = v21;
            if ( v21 < 0 )
            {
              if ( g_wppLevels )
              {
                v28 = 47;
LABEL_78:
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v28,
                  &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids,
                  0,
                  v21);
              }
              goto LABEL_79;
            }
          }
          v5 = (BYTE *)operator new(0x190u);
          PropertyBufferSize = 400;
          Device_Interface_PropertyW = CM_Get_Device_Interface_PropertyW(
                                         (LPCWSTR)pv,
                                         &DEVPKEY_Device_InstanceId,
                                         &PropertyType,
                                         v5,
                                         &PropertyBufferSize,
                                         0);
          if ( Device_Interface_PropertyW )
          {
            v23 = CM_MapCrToWin32Err(Device_Interface_PropertyW, 0xDu);
            v8 = v23;
            if ( v23 > 0 )
              v8 = (unsigned __int16)v23 | 0x80070000;
            if ( v8 < 0 )
            {
              if ( g_wppLevels )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  48,
                  &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids,
                  0,
                  v8);
              goto LABEL_56;
            }
          }
          else if ( PropertyType != 18 )
          {
            v8 = -2147024883;
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                49,
                &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids,
                0,
                -2147024883);
LABEL_56:
            ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v39);
            ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v40);
            goto LABEL_80;
          }
          v6 = (BYTE *)operator new(0x190u);
          PropertyBufferSize = 400;
          v24 = CM_Get_Device_Interface_PropertyW(
                  pszDeviceInterface,
                  &DEVPKEY_Device_InstanceId,
                  &PropertyType,
                  v6,
                  &PropertyBufferSize,
                  0);
          if ( v24 )
          {
            v25 = CM_MapCrToWin32Err(v24, 0xDu);
            v8 = v25;
            if ( v25 > 0 )
              v8 = (unsigned __int16)v25 | 0x80070000;
            if ( v8 < 0 )
            {
              if ( g_wppLevels )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  50,
                  &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids,
                  0,
                  v8);
              goto LABEL_64;
            }
          }
          else if ( PropertyType != 18 )
          {
            v8 = -2147024883;
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                51,
                &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids,
                0,
                -2147024883);
LABEL_64:
            ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v39);
            ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v40);
            goto LABEL_81;
          }
          v26 = wcsicmp((const wchar_t *)v5, (const wchar_t *)v6);
          v32 = v26 == 0;
          CoTaskMemFree(pv);
          pv = 0;
          CoTaskMemFree((LPVOID)pszDeviceInterface);
          pszDeviceInterface = 0;
          operator delete(v5);
          operator delete(v6);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v39);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v40);
          if ( !v26 )
            break;
          v20 = *(_QWORD *)&guidCategory.Data1;
          v19 = v38 + 1;
          v38 = v19;
        }
        while ( (unsigned int)v19 < v33 );
        LODWORD(v6) = v42;
        if ( v32 )
          goto LABEL_72;
        v20 = v42;
LABEL_70:
        v41[i] = pppMFTActivate[v20];
        v27 = v41[i];
        if ( v27 )
        {
          ((void (__fastcall *)(IMFActivate *))v27->lpVtbl->AddRef)(v27);
          i = (unsigned int)(i + 1);
        }
LABEL_72:
        LODWORD(v6) = (_DWORD)v6 + 1;
        v42 = (unsigned int)v6;
        if ( (unsigned int)v6 >= pnumMFTActivate )
        {
          v3 = v43;
          break;
        }
      }
    }
    *v3 = i;
    if ( (unsigned __int8)byte_1803CECED >= 8u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        52,
        &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids,
        (unsigned int)i);
      LODWORD(i) = *v3;
    }
LABEL_94:
    v29 = (struct IMFActivate **)CoTaskMemAlloc(8LL * (unsigned int)i);
    v4 = v34;
    *v34 = v29;
    if ( v29 )
    {
      memset_0(v29, 0, 8LL * *v3);
      v6 = 0;
      if ( !*v3 )
      {
        v5 = 0;
        goto LABEL_19;
      }
      while ( 1 )
      {
        Instance = CMFDeviceSourceActivate::CreateInstance(v41[(_QWORD)v6], &(*v4)[(_QWORD)v6]);
        v8 = Instance;
        if ( Instance < 0 )
          break;
        Instance = ((__int64 (__fastcall *)(struct IMFActivate *, const IID *, const IID *))(*v4)[(_QWORD)v6]->lpVtbl->SetGUID)(
                     (*v4)[(_QWORD)v6],
                     &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE,
                     &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_GUID);
        v8 = Instance;
        if ( Instance < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_98;
          v31 = 57;
          goto LABEL_97;
        }
        v6 = (BYTE *)(unsigned int)((_DWORD)v6 + 1);
        if ( (unsigned int)v6 >= *v3 )
          goto LABEL_98;
      }
      if ( !g_wppLevels )
        goto LABEL_98;
      v31 = 56;
    }
    else
    {
      Instance = -2147024882;
      v8 = -2147024882;
      if ( !g_wppLevels )
      {
LABEL_98:
        v5 = 0;
        v6 = 0;
        goto LABEL_19;
      }
      v31 = 55;
    }
LABEL_97:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids, 0, Instance);
    goto LABEL_98;
  }
  if ( g_wppLevels )
  {
    v9 = 39;
    goto LABEL_4;
  }
LABEL_19:
  FreeActivateArray(v41, *v3);
  FreeActivateArray(pppMFTActivate, pnumMFTActivate);
  FreeActivateArray(v48, v33);
  FreeActivateArray(0, 0);
  if ( pv )
    CoTaskMemFree(pv);
  if ( pszDeviceInterface )
    CoTaskMemFree((LPVOID)pszDeviceInterface);
  if ( v5 )
    operator delete(v5);
  if ( v6 )
    operator delete(v6);
  if ( v8 < 0 )
  {
    FreeActivateArray(*v4, *v3);
    *v4 = 0;
    *v3 = 0;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800a0978  push    rbp
0x1800a097a  push    rbx
0x1800a097b  push    rsi
0x1800a097c  push    rdi
0x1800a097d  push    r12
0x1800a097f  push    r13
0x1800a0981  push    r15
0x1800a0983  lea     rbp, [rsp-27h]
0x1800a0988  sub     rsp, 0D0h
0x1800a098f  mov     rax, cs:__security_cookie
0x1800a0996  xor     rax, rsp
0x1800a0999  mov     [rbp+57h+var_40], rax
0x1800a099d  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800a09a4  xor     edi, edi
0x1800a09a6  mov     [rbp+57h+var_C8], rdx
0x1800a09aa  mov     [rbp+57h+var_A0], rdi
0x1800a09ae  mov     rbx, r8
0x1800a09b1  mov     [rbp+57h+var_90], rbx
0x1800a09b5  mov     r13, rdx
0x1800a09b8  mov     [rbp+57h+var_C0], edi
0x1800a09bb  mov     r12d, edi
0x1800a09be  mov     [rbp+57h+var_70], rdi
0x1800a09c2  mov     r15d, edi
0x1800a09c5  mov     [rbp+57h+var_CC], edi
0x1800a09c8  mov     [rbp+57h+var_68], rdi
0x1800a09cc  mov     [rbp+57h+pv], rdi
0x1800a09d0  mov     [rbp+57h+pszDeviceInterface], rdi
0x1800a09d4  mov     [rbp+57h+PropertyBufferSize], edi
0x1800a09d7  mov     [rbp+57h+PropertyType], edi
0x1800a09da  mov     [rbp+57h+var_88], edi
0x1800a09dd  movdqu  [rbp+57h+Buf1], xmm0
0x1800a09e2  test    r8, r8
0x1800a09e5  jnz     short loc_1800A0A26
0x1800a09e7  mov     ecx, 80004003h; this
0x1800a09ec  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x1800a09f1  mov     edi, eax
0x1800a09f3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a09fa  jb      loc_1800A0B7E
0x1800a0a00  lea     edx, [rbx+25h]
0x1800a0a03  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0a0a  lea     r8, WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids
0x1800a0a11  xor     r9d, r9d
0x1800a0a14  mov     dword ptr [rsp+100h+pppMFTActivate], eax
0x1800a0a18  mov     rcx, [rcx+10h]
0x1800a0a1c  call    WPP_SF_qD
0x1800a0a21  jmp     loc_1800A0B7E
0x1800a0a26  test    rdx, rdx
0x1800a0a29  jnz     short loc_1800A0A4B
0x1800a0a2b  mov     ecx, 80004003h; this
0x1800a0a30  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x1800a0a35  mov     edi, eax
0x1800a0a37  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a0a3e  jb      loc_1800A0B7E
0x1800a0a44  mov     edx, 26h ; '&'
0x1800a0a49  jmp     short loc_1800A0A03
0x1800a0a4b  mov     [r8], edi
0x1800a0a4e  lea     r8, [rbp+57h+Buf1]
0x1800a0a52  mov     [rdx], rdi
0x1800a0a55  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_CATEGORY
0x1800a0a5c  mov     rax, [rcx]
0x1800a0a5f  mov     rax, [rax+50h]
0x1800a0a63  call    cs:__guard_dispatch_icall_fptr
0x1800a0a69  mov     r8d, 10h; Size
0x1800a0a6f  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x1800a0a76  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800a0a7a  call    memcmp_0
0x1800a0a7f  xor     r9d, r9d; pOutputType
0x1800a0a82  lea     rcx, [rbp+57h+guidCategory]; guidCategory
0x1800a0a86  xor     r8d, r8d; pInputType
0x1800a0a89  mov     edx, 10000004h; Flags
0x1800a0a8e  test    eax, eax
0x1800a0a90  jnz     loc_1800A10ED
0x1800a0a96  movups  xmm0, xmmword ptr cs:CLSID_VideoInputDeviceCategory.Data1
0x1800a0a9d  lea     rax, [rbp+57h+var_C0]
0x1800a0aa1  mov     [rsp+100h+pnumMFTActivate], rax; pnumMFTActivate
0x1800a0aa6  lea     rax, [rbp+57h+var_70]
0x1800a0aaa  mov     [rsp+100h+pppMFTActivate], rax; pppMFTActivate
0x1800a0aaf  movdqu  xmmword ptr [rbp+57h+guidCategory.Data1], xmm0
0x1800a0ab4  call    cs:__imp_MFTEnumEx
0x1800a0abb  nop     dword ptr [rax+rax+00h]
0x1800a0ac0  mov     edi, eax
0x1800a0ac2  test    eax, eax
0x1800a0ac4  jns     short loc_1800A0ADD
0x1800a0ac6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a0acd  jb      loc_1800A0B7E
0x1800a0ad3  mov     edx, 27h ; '''
0x1800a0ad8  jmp     loc_1800A0A03
0x1800a0add  mov     r13b, 8
0x1800a0ae0  lea     rsi, WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids
0x1800a0ae7  cmp     cs:byte_1803CECED, r13b
0x1800a0aee  jb      short loc_1800A0B0F
0x1800a0af0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0af7  mov     edx, 28h ; '('
0x1800a0afc  mov     r9d, [rbp+57h+var_C0]
0x1800a0b00  mov     r8, rsi
0x1800a0b03  mov     rcx, [rcx+0D8h]
0x1800a0b0a  call    WPP_SF_d
0x1800a0b0f  movups  xmm0, xmmword ptr cs:_GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data1
0x1800a0b16  lea     rax, [rbp+57h+var_CC]
0x1800a0b1a  xor     r9d, r9d; pOutputType
0x1800a0b1d  mov     [rsp+100h+pnumMFTActivate], rax; pnumMFTActivate
0x1800a0b22  lea     rcx, [rbp+57h+guidCategory]; guidCategory
0x1800a0b26  lea     rax, [rbp+57h+var_68]
0x1800a0b2a  xor     r8d, r8d; pInputType
0x1800a0b2d  mov     edx, 10000004h; Flags
0x1800a0b32  mov     [rsp+100h+pppMFTActivate], rax; pppMFTActivate
0x1800a0b37  movdqu  xmmword ptr [rbp+57h+guidCategory.Data1], xmm0
0x1800a0b3c  call    cs:__imp_MFTEnumEx
0x1800a0b43  nop     dword ptr [rax+rax+00h]
0x1800a0b48  mov     edi, eax
0x1800a0b4a  test    eax, eax
0x1800a0b4c  jns     loc_1800A0C2C
0x1800a0b52  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a0b59  jb      short loc_1800A0B7A
0x1800a0b5b  mov     edx, 29h ; ')'
0x1800a0b60  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0b67  xor     r9d, r9d
0x1800a0b6a  mov     r8, rsi
0x1800a0b6d  mov     dword ptr [rsp+100h+pppMFTActivate], eax
0x1800a0b71  mov     rcx, [rcx+10h]
0x1800a0b75  call    WPP_SF_qD
0x1800a0b7a  mov     r13, [rbp+57h+var_C8]
0x1800a0b7e  mov     edx, [rbx]; unsigned int
0x1800a0b80  mov     rcx, [rbp+57h+var_A0]; struct IMFActivate **
0x1800a0b84  call    ?FreeActivateArray@@YAXPEAPEAUIMFActivate@@I@Z; FreeActivateArray(IMFActivate * *,uint)
0x1800a0b89  mov     edx, [rbp+57h+var_C0]; unsigned int
0x1800a0b8c  mov     rcx, [rbp+57h+var_70]; struct IMFActivate **
0x1800a0b90  call    ?FreeActivateArray@@YAXPEAPEAUIMFActivate@@I@Z; FreeActivateArray(IMFActivate * *,uint)
0x1800a0b95  mov     edx, [rbp+57h+var_CC]; unsigned int
0x1800a0b98  mov     rcx, [rbp+57h+var_68]; struct IMFActivate **
0x1800a0b9c  call    ?FreeActivateArray@@YAXPEAPEAUIMFActivate@@I@Z; FreeActivateArray(IMFActivate * *,uint)
0x1800a0ba1  xor     edx, edx; unsigned int
0x1800a0ba3  xor     ecx, ecx; struct IMFActivate **
0x1800a0ba5  call    ?FreeActivateArray@@YAXPEAPEAUIMFActivate@@I@Z; FreeActivateArray(IMFActivate * *,uint)
0x1800a0baa  mov     rcx, [rbp+57h+pv]; pv
0x1800a0bae  test    rcx, rcx
0x1800a0bb1  jz      short loc_1800A0BBF
0x1800a0bb3  call    cs:__imp_CoTaskMemFree
0x1800a0bba  nop     dword ptr [rax+rax+00h]
0x1800a0bbf  mov     rcx, [rbp+57h+pszDeviceInterface]; pv
0x1800a0bc3  test    rcx, rcx
0x1800a0bc6  jz      short loc_1800A0BD4
0x1800a0bc8  call    cs:__imp_CoTaskMemFree
0x1800a0bcf  nop     dword ptr [rax+rax+00h]
0x1800a0bd4  test    r12, r12
0x1800a0bd7  jz      short loc_1800A0BE1
0x1800a0bd9  mov     rcx, r12; Block
0x1800a0bdc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a0be1  test    r15, r15
0x1800a0be4  jz      short loc_1800A0BEE
0x1800a0be6  mov     rcx, r15; Block
0x1800a0be9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a0bee  test    edi, edi
0x1800a0bf0  jns     short loc_1800A0C0B
0x1800a0bf2  mov     edx, [rbx]; unsigned int
0x1800a0bf4  mov     rcx, [r13+0]; struct IMFActivate **
0x1800a0bf8  call    ?FreeActivateArray@@YAXPEAPEAUIMFActivate@@I@Z; FreeActivateArray(IMFActivate * *,uint)
0x1800a0bfd  mov     qword ptr [r13+0], 0
0x1800a0c05  mov     dword ptr [rbx], 0
0x1800a0c0b  mov     eax, edi
0x1800a0c0d  mov     rcx, [rbp+57h+var_40]
0x1800a0c11  xor     rcx, rsp; StackCookie
0x1800a0c14  call    __security_check_cookie
0x1800a0c19  add     rsp, 0D0h
0x1800a0c20  pop     r15
0x1800a0c22  pop     r13
0x1800a0c24  pop     r12
0x1800a0c26  pop     rdi
0x1800a0c27  pop     rsi
0x1800a0c28  pop     rbx
0x1800a0c29  pop     rbp
0x1800a0c2a  retn
0x1800a0c2c  mov     dl, cs:byte_1803CECED
0x1800a0c32  cmp     dl, r13b
0x1800a0c35  jb      short loc_1800A0C5C
0x1800a0c37  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0c3e  mov     edx, 2Ah ; '*'
0x1800a0c43  mov     r9d, [rbp+57h+var_CC]
0x1800a0c47  mov     r8, rsi
0x1800a0c4a  mov     rcx, [rcx+0D8h]
0x1800a0c51  call    WPP_SF_d
0x1800a0c56  mov     dl, cs:byte_1803CECED
0x1800a0c5c  mov     eax, [rbp+57h+var_C0]
0x1800a0c5f  add     eax, [rbp+57h+var_CC]
0x1800a0c62  mov     [rbp+57h+var_B4], eax
0x1800a0c65  jnz     short loc_1800A0C90
0x1800a0c67  cmp     dl, r13b
0x1800a0c6a  jb      loc_1800A0B7A
0x1800a0c70  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0c77  mov     edx, 2Bh ; '+'
0x1800a0c7c  mov     r8, rsi
0x1800a0c7f  mov     rcx, [rcx+0D8h]
0x1800a0c86  call    WPP_SF_
0x1800a0c8b  jmp     loc_1800A0B7A
0x1800a0c90  cmp     dl, r13b
0x1800a0c93  jb      short loc_1800A0CB6
0x1800a0c95  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0c9c  mov     edx, 2Ch ; ','
0x1800a0ca1  mov     r9d, eax
0x1800a0ca4  mov     r8, rsi
0x1800a0ca7  mov     rcx, [rcx+0D8h]
0x1800a0cae  call    WPP_SF_d
0x1800a0cb3  mov     eax, [rbp+57h+var_B4]
0x1800a0cb6  mov     r13d, eax
0x1800a0cb9  shl     r13, 3
0x1800a0cbd  mov     rcx, r13; cb
0x1800a0cc0  call    cs:__imp_CoTaskMemAlloc
0x1800a0cc7  nop     dword ptr [rax+rax+00h]
0x1800a0ccc  mov     [rbp+57h+var_A0], rax
0x1800a0cd0  test    rax, rax
0x1800a0cd3  jnz     short loc_1800A0CF3
0x1800a0cd5  mov     eax, 8007000Eh
0x1800a0cda  mov     edi, eax
0x1800a0cdc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a0ce3  jb      loc_1800A0B7A
0x1800a0ce9  mov     edx, 2Dh ; '-'
0x1800a0cee  jmp     loc_1800A0B60
0x1800a0cf3  mov     r8, r13; Size
0x1800a0cf6  xor     edx, edx; Val
0x1800a0cf8  mov     rcx, rax; void *
0x1800a0cfb  call    memset_0
0x1800a0d00  xor     r13d, r13d
0x1800a0d03  cmp     [rbp+57h+var_CC], r12d
0x1800a0d07  jbe     short loc_1800A0D3C
0x1800a0d09  mov     rax, [rbp+57h+var_68]
0x1800a0d0d  mov     rcx, [rax+r13*8]
0x1800a0d11  mov     rax, [rbp+57h+var_A0]
0x1800a0d15  mov     [rax+r13*8], rcx
0x1800a0d19  mov     rax, [rbp+57h+var_A0]
0x1800a0d1d  mov     rcx, [rax+r13*8]
0x1800a0d21  test    rcx, rcx
0x1800a0d24  jz      short loc_1800A0D33
0x1800a0d26  mov     rax, [rcx]
0x1800a0d29  mov     rax, [rax+8]
0x1800a0d2d  call    cs:__guard_dispatch_icall_fptr
0x1800a0d33  inc     r13d
0x1800a0d36  cmp     r13d, [rbp+57h+var_CC]
0x1800a0d3a  jb      short loc_1800A0D09
0x1800a0d3c  mov     [rbp+57h+var_98], r15d
0x1800a0d40  cmp     [rbp+57h+var_C0], r12d
0x1800a0d44  jbe     loc_1800A101A
0x1800a0d4a  xor     eax, eax
0x1800a0d4c  mov     ebx, r15d
0x1800a0d4f  mov     [rbp+57h+var_B4], eax
0x1800a0d52  mov     qword ptr [rbp+57h+guidCategory.Data1], rbx
0x1800a0d56  cmp     [rbp+57h+var_CC], eax
0x1800a0d59  jbe     loc_1800A0FD8
0x1800a0d5f  mov     rdx, [rbp+57h+var_A0]
0x1800a0d63  lea     rcx, [rbp+57h+var_A8]
0x1800a0d67  mov     rdx, [rdx+rax*8]
0x1800a0d6b  call    ??0?$ComSmartPtr@UIUnknown@@@@QEAA@PEAUIUnknown@@@Z; ComSmartPtr<IUnknown>::ComSmartPtr<IUnknown>(IUnknown *)
0x1800a0d70  mov     rdx, [rbp+57h+var_70]
0x1800a0d74  lea     rcx, [rbp+57h+var_B0]
0x1800a0d78  mov     rdx, [rdx+rbx*8]
0x1800a0d7c  call    ??0?$ComSmartPtr@UIUnknown@@@@QEAA@PEAUIUnknown@@@Z; ComSmartPtr<IUnknown>::ComSmartPtr<IUnknown>(IUnknown *)
0x1800a0d81  mov     rcx, [rbp+57h+var_A8]
0x1800a0d85  test    rcx, rcx
0x1800a0d88  jz      short loc_1800A0DB0
0x1800a0d8a  mov     rax, [rcx]
0x1800a0d8d  lea     r9, [rbp+57h+var_88]
0x1800a0d91  lea     r8, [rbp+57h+pv]
0x1800a0d95  lea     rdx, MFT_ENUM_HARDWARE_URL_Attribute
0x1800a0d9c  mov     rax, [rax+68h]
0x1800a0da0  call    cs:__guard_dispatch_icall_fptr
0x1800a0da6  mov     edi, eax
0x1800a0da8  test    eax, eax
0x1800a0daa  js      loc_1800A1050
0x1800a0db0  mov     rcx, [rbp+57h+var_B0]
0x1800a0db4  test    rcx, rcx
0x1800a0db7  jz      short loc_1800A0DDF
0x1800a0db9  mov     rax, [rcx]
0x1800a0dbc  lea     r9, [rbp+57h+var_88]
0x1800a0dc0  lea     r8, [rbp+57h+pszDeviceInterface]
0x1800a0dc4  lea     rdx, MFT_ENUM_HARDWARE_URL_Attribute
0x1800a0dcb  mov     rax, [rax+68h]
0x1800a0dcf  call    cs:__guard_dispatch_icall_fptr
0x1800a0dd5  mov     edi, eax
0x1800a0dd7  test    eax, eax
0x1800a0dd9  js      loc_1800A1099
0x1800a0ddf  mov     ebx, 190h
0x1800a0de4  mov     ecx, ebx; Size
0x1800a0de6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a0deb  mov     rcx, [rbp+57h+pv]; pszDeviceInterface
0x1800a0def  lea     r8, [rbp+57h+PropertyType]; PropertyType
0x1800a0df3  mov     r12, rax
0x1800a0df6  mov     dword ptr [rsp+100h+pnumMFTActivate], 0; ulFlags
0x1800a0dfe  lea     rax, [rbp+57h+PropertyBufferSize]
0x1800a0e02  mov     [rbp+57h+PropertyBufferSize], ebx
0x1800a0e05  mov     r9, r12; PropertyBuffer
0x1800a0e08  mov     [rsp+100h+pppMFTActivate], rax; PropertyBufferSize
0x1800a0e0d  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x1800a0e14  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x1800a0e1b  nop     dword ptr [rax+rax+00h]
0x1800a0e20  test    eax, eax
0x1800a0e22  jz      short loc_1800A0E89
0x1800a0e24  mov     edx, 0Dh; DefaultErr
0x1800a0e29  mov     ecx, eax; CmReturnCode
0x1800a0e2b  call    cs:__imp_CM_MapCrToWin32Err
0x1800a0e32  nop     dword ptr [rax+rax+00h]
0x1800a0e37  mov     edi, eax
  ... truncated ...
```
