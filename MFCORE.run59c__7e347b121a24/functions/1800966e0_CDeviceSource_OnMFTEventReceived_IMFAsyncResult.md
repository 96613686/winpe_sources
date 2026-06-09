# CDeviceSource::OnMFTEventReceived(IMFAsyncResult *)

- ea: `0x1800966e0`
- end: `0x180097333`
- name: `?OnMFTEventReceived@CDeviceSource@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `3155`
- prototype: `void __fastcall(CDeviceSource *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800966c0`

## callees

- `0x180027b48`
- `0x180050d6c`
- `0x18005a3d4`
- `0x180063f00`
- `0x18006b388`
- `0x1800966e0`
- `0x1800cf200`
- `0x180109ce0`
- `0x180112390`
- `0x180258390`
- `0x180258480`
- `0x1802d136c`
- `0x180344cd8`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180096924`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180096924`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096714`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096714`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800968e7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800968f7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800968e7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800968f7`
- `MFPlat!MFInvokeCallback` at `0x180096e69`
- `MFPlat!MFInvokeCallback` at `0x180096f39`
- `MFPlat!MFInvokeCallback` at `0x180097068`
- `MFPlat!MFInvokeCallback` at `0x180096e69`
- `MFPlat!MFInvokeCallback` at `0x180096f39`
- `MFPlat!MFInvokeCallback` at `0x180097068`
- `MFPlat!MFCreateAsyncResult` at `0x180096c00`
- `MFPlat!MFCreateAsyncResult` at `0x180096e45`
- `MFPlat!MFCreateAsyncResult` at `0x180096f15`
- `MFPlat!MFCreateAsyncResult` at `0x180096c00`
- `MFPlat!MFCreateAsyncResult` at `0x180096e45`
- `MFPlat!MFCreateAsyncResult` at `0x180096f15`

## pseudocode

```c
void __fastcall CDeviceSource::OnMFTEventReceived(CDeviceSource *this, struct IMFAsyncResult *a2)
{
  int v4; // eax
  char v5; // r12
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rdx
  int v10; // eax
  unsigned int i; // r14d
  __int64 v12; // rax
  IMFAsyncCallback *v13; // rdx
  HRESULT v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rax
  int v17; // r9d
  unsigned int v18; // edx
  IMFAsyncCallback *v19; // rdx
  IMFAsyncCallback *v20; // rdx
  HRESULT v21; // eax
  __int64 v22; // rdx
  int (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // rcx
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  PROPVARIANT v29; // rcx
  int (__fastcall **v30)(PROPVARIANT, GUID *, __int64 *); // rax
  __int64 v31; // rdx
  int (__fastcall *v32)(PROPVARIANT, GUID *, __int64 *); // r14
  int v33; // [rsp+20h] [rbp-49h]
  int v34; // [rsp+30h] [rbp-39h] BYREF
  unsigned int v35; // [rsp+34h] [rbp-35h] BYREF
  __int64 v36; // [rsp+38h] [rbp-31h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+40h] [rbp-29h] BYREF
  IUnknown *punkObject; // [rsp+48h] [rbp-21h] BYREF
  struct tagPROPVARIANT v39; // [rsp+50h] [rbp-19h] BYREF
  PROPVARIANT pvar[2]; // [rsp+68h] [rbp-1h] BYREF
  __int64 v41; // [rsp+78h] [rbp+Fh]

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  punkObject = 0;
  v35 = 0;
  v34 = 0;
  memset(&v39, 0, sizeof(v39));
  if ( *((int *)this + 28) < 0 )
    goto LABEL_24;
  v4 = (*(__int64 (__fastcall **)(_QWORD, struct IMFAsyncResult *, IUnknown **))(**((_QWORD **)this + 54) + 40LL))(
         *((_QWORD *)this + 54),
         a2,
         &punkObject);
  if ( v4 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_24;
    v8 = 176;
    goto LABEL_29;
  }
  v4 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)this + 54) + 32LL))(
         *((_QWORD *)this + 54),
         (char *)this + 168,
         0);
  if ( v4 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_24;
    v8 = 177;
LABEL_29:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids, this, v4);
    goto LABEL_24;
  }
  v4 = ((__int64 (__fastcall *)(IUnknown *, unsigned int *))punkObject->lpVtbl[11].QueryInterface)(punkObject, &v35);
  if ( v4 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_24;
    v8 = 178;
    goto LABEL_29;
  }
  v4 = ((__int64 (__fastcall *)(IUnknown *, int *))punkObject->lpVtbl[11].Release)(punkObject, &v34);
  if ( v4 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_24;
    v8 = 179;
    goto LABEL_29;
  }
  v5 = 0;
  switch ( v35 )
  {
    case 1u:
      goto LABEL_123;
    case 2u:
      *(GUID *)pvar = GUID_00000000_0000_0000_0000_000000000000;
      v10 = ((__int64 (__fastcall *)(IUnknown *, PROPVARIANT *))punkObject->lpVtbl[11].AddRef)(punkObject, pvar);
      if ( v10 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_24;
        v9 = 180;
        goto LABEL_67;
      }
      if ( !memcmp_0(pvar, &MF_DEVICESOURCE_EXCLUSIVECONTROL_STATUS_CHANGED, 0x10u) )
      {
        if ( (unsigned __int8)byte_1803CECED >= 8u )
          WPP_SF_qDD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            181,
            &WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids,
            this,
            v35,
            v34);
        v19 = (IMFAsyncCallback *)*((_QWORD *)this + 77);
        if ( !v19 )
          break;
        ppAsyncResult = 0;
        v14 = MFCreateAsyncResult(punkObject, v19, 0, &ppAsyncResult);
        if ( v14 >= 0 )
        {
          v14 = MFInvokeCallback(ppAsyncResult);
          if ( v14 >= 0 || !g_wppLevels )
            goto LABEL_96;
          v15 = 183;
          goto LABEL_95;
        }
        if ( g_wppLevels )
        {
          v15 = 182;
          goto LABEL_95;
        }
LABEL_96:
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppAsyncResult);
        goto LABEL_24;
      }
      if ( memcmp_0(pvar, &MF_DEVICESOURCE_MT_CHANGEREQUEST, 0x10u) )
      {
        if ( memcmp_0(pvar, &MF_DEVICESOURCE_MT_CHANGEREQUEST_COMPLETED, 0x10u) )
          break;
        if ( (unsigned __int8)byte_1803CECED >= 8u )
          WPP_SF_qDD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            190,
            &WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids,
            this,
            v35,
            v34);
        v13 = (IMFAsyncCallback *)*((_QWORD *)this + 77);
        if ( !v13 )
          break;
        ppAsyncResult = 0;
        v14 = MFCreateAsyncResult(punkObject, v13, 0, &ppAsyncResult);
        if ( v14 >= 0 )
        {
          v14 = MFInvokeCallback(ppAsyncResult);
          if ( v14 >= 0 || !g_wppLevels )
            goto LABEL_96;
          v15 = 192;
          goto LABEL_95;
        }
        if ( g_wppLevels )
        {
          v15 = 191;
LABEL_95:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v15,
            &WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids,
            this,
            v14);
          goto LABEL_96;
        }
        goto LABEL_96;
      }
      if ( (unsigned __int8)byte_1803CECED >= 8u )
        WPP_SF_qDD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          184,
          &WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids,
          this,
          v35,
          v34);
      v20 = (IMFAsyncCallback *)*((_QWORD *)this + 77);
      v36 = 0;
      if ( !v20 )
      {
        v23 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 53);
        if ( !v23 || (**v23)(v23, &GUID_b8c67621_7341_4a44_b74b_99582c32fc28, &v36) < 0 )
          goto LABEL_109;
        if ( (unsigned __int8)byte_1803CECED >= 8u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 187, &WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids, this);
        ppAsyncResult = 0;
        v24 = ((__int64 (__fastcall *)(IUnknown *, void *, IMFAsyncResult **))punkObject->lpVtbl[2].Release)(
                punkObject,
                &MF_DEVICESOURCE_MT_CHANGEREQUEST_TOKEN,
                &ppAsyncResult);
        if ( v24 >= 0 )
        {
          v24 = (*(__int64 (__fastcall **)(__int64, IMFAsyncResult *, _QWORD))(*(_QWORD *)v36 + 32LL))(
                  v36,
                  ppAsyncResult,
                  0);
          if ( v24 >= 0 || !g_wppLevels )
            goto LABEL_109;
          v25 = 189;
        }
        else
        {
          if ( !g_wppLevels )
            goto LABEL_109;
          v25 = 188;
        }
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, &WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids, this, v24);
LABEL_109:
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v36);
        goto LABEL_24;
      }
      ppAsyncResult = 0;
      v21 = MFCreateAsyncResult(punkObject, v20, 0, &ppAsyncResult);
      if ( v21 >= 0 )
      {
        v21 = MFInvokeCallback(ppAsyncResult);
        if ( v21 >= 0 || !g_wppLevels )
          goto LABEL_107;
        v22 = 186;
      }
      else
      {
        if ( !g_wppLevels )
        {
LABEL_107:
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppAsyncResult);
          goto LABEL_109;
        }
        v22 = 185;
      }
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, &WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids, this, v21);
      goto LABEL_107;
    case 0x320u:
    case 0x321u:
LABEL_123:
      if ( !*((_QWORD *)this + 67) )
        ComSmartPtr<IKsControl>::operator=((char *)this + 536, &punkObject);
      break;
    case 0x3B6u:
      if ( ((int (__fastcall *)(IUnknown *, struct tagPROPVARIANT *))punkObject->lpVtbl[12].QueryInterface)(
             punkObject,
             &v39) < 0
        || v39.vt != 19 )
      {
        if ( byte_1803CECED )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            194,
            &WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids,
            this,
            v39.vt);
        v17 = -1072875843;
        v18 = 1;
        goto LABEL_82;
      }
      if ( (unsigned __int8)byte_1803CECED >= 8u )
        WPP_SF_qDD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          193,
          &WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids,
          this,
          *((_DWORD *)this + 158),
          v39.lVal);
      if ( *((_DWORD *)this + 158) != v39.lVal )
      {
        v5 = 1;
        *((_DWORD *)this + 158) = v39.lVal;
      }
      break;
  }
  v6 = *((_QWORD *)this + 64);
  if ( v6 )
  {
    if ( v35 - 800 <= 1 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 48LL))(v6);
      if ( v10 < 0 )
      {
        if ( g_wppLevels )
        {
          v9 = 195;
          goto LABEL_67;
        }
        goto LABEL_24;
      }
    }
  }
  if ( *((_DWORD *)this + 46) != 1 )
  {
    if ( v35 == 800 && *((_DWORD *)this + 131) == 1 )
    {
      *((_BYTE *)this + 160) = 1;
      if ( (unsigned __int8)byte_1803CECED >= 8u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          196,
          &WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids,
          this,
          v34);
      CDeviceSourceObjectBase::_QueueEvent(
        (CDeviceSource *)((char *)this + 48),
        v35,
        &GUID_00000000_0000_0000_0000_000000000000,
        v34,
        0);
    }
    if ( g_wppLevels )
    {
      v9 = 197;
      v33 = -1072873829;
LABEL_68:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids, this, v33);
      goto LABEL_24;
    }
    goto LABEL_24;
  }
  if ( v35 > 0x146 )
  {
    if ( v35 != 327 )
    {
      switch ( v35 )
      {
        case 0x25Au:
          v36 = 0;
          v41 = 0;
          v7 = v34;
          *(_OWORD *)pvar = 0;
          if ( v34 >= 0 )
          {
            if ( ((int (__fastcall *)(IUnknown *, PROPVARIANT *))punkObject->lpVtbl[12].QueryInterface)(
                   punkObject,
                   pvar) < 0 )
              goto LABEL_20;
            if ( LOWORD(pvar[0]) != 13 )
              goto LABEL_20;
            v29 = pvar[1];
            if ( !pvar[1] )
              goto LABEL_20;
            v30 = *(int (__fastcall ***)(PROPVARIANT, GUID *, __int64 *))pvar[1];
            v31 = v36;
            v36 = 0;
            v32 = *v30;
            if ( v31 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
              v29 = pvar[1];
            }
            if ( v32(v29, &GUID_5bc8a76b_869a_46a3_9b03_fa218a66aebe, &v36) >= 0 )
            {
              v7 = (*(__int64 (__fastcall **)(CDeviceSource *, __int64))(*(_QWORD *)this + 184LL))(this, v36);
              if ( v7 < 0 )
              {
                if ( g_wppLevels )
                {
                  v28 = 199;
                  goto LABEL_165;
                }
                goto LABEL_166;
              }
            }
            else
            {
LABEL_20:
              v7 = (*(__int64 (__fastcall **)(CDeviceSource *))(*(_QWORD *)this + 176LL))(this);
              if ( v7 < 0 )
              {
                if ( g_wppLevels )
                {
                  v28 = 200;
                  goto LABEL_165;
                }
                goto LABEL_166;
              }
            }
            ++*((_QWORD *)this + 60);
            if ( v36 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            goto LABEL_23;
          }
          if ( g_wppLevels )
          {
            v28 = 198;
LABEL_165:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v28,
              &WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids,
              this,
              v7);
          }
LABEL_166:
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v36);
LABEL_23:
          PropVariantClear(pvar);
          goto LABEL_24;
        case 0x320u:
          *((_BYTE *)this + 160) = 1;
          if ( !byte_1803CECED )
            goto LABEL_81;
          v27 = 206;
          break;
        case 0x321u:
          if ( !byte_1803CECED )
            goto LABEL_81;
          v27 = 207;
          break;
        case 0x3B6u:
LABEL_44:
          if ( !v5 )
            goto LABEL_24;
          if ( (unsigned __int8)byte_1803CECED >= 8u )
            WPP_SF_qDD(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              204,
              &WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids,
              this,
              v39.lVal,
              v34);
          v10 = CDeviceSourceObjectBase::_QueueEvent(
                  (CDeviceSource *)((char *)this + 48),
                  v35,
                  &GUID_00000000_0000_0000_0000_000000000000,
                  v34,
                  &v39);
          if ( v10 >= 0 || !g_wppLevels )
            goto LABEL_24;
          v9 = 205;
LABEL_67:
          v33 = v10;
          goto LABEL_68;
        default:
          goto LABEL_24;
      }
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v27, &WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids, this, v34);
LABEL_81:
      v17 = v34;
      v18 = v35;
LABEL_82:
      CDeviceSourceObjectBase::_QueueEvent(
        (CDeviceSource *)((char *)this + 48),
        v18,
        &GUID_00000000_0000_0000_0000_000000000000,
        v17,
        0);
      goto LABEL_24;
    }
LABEL_136:
    if ( (unsigned __int8)byte_1803CECED >= 8u )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 201, &WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids, this, v35);
    if ( !memcmp_0(&MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_AUDCAP_GUID, (char *)this + 400, 0x10u) )
    {
      v16 = CTPtrArray<_KS_COMPLETED_IO_REQUEST,20>::operator[]((char *)this + 192, 0);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v16 + 176LL))(v16, v35, 0, (unsigned int)v34);
    }
    goto LABEL_24;
  }
  if ( v35 == 326 )
    goto LABEL_136;
  if ( !v35 )
  {
    LODWORD(v36) = 0;
    *(GUID *)pvar = GUID_00000000_0000_0000_0000_000000000000;
    if ( !((unsigned int (__fastcall *)(IUnknown *, PROPVARIANT *))punkObject->lpVtbl[11].AddRef)(punkObject, pvar)
      && !memcmp_0(pvar, &MEDeviceStreamCreated, 0x10u) )
    {
      v10 = ((__int64 (__fastcall *)(IUnknown *, const GUID *, __int64 *))punkObject->lpVtbl[2].AddRef)(
              punkObject,
              &MF_EVENT_MFT_INPUT_STREAM_ID,
              &v36);
      if ( v10 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_24;
        v9 = 202;
        goto LABEL_67;
      }
      for ( i = 0; i < *((_DWORD *)this + 98); ++i )
      {
        v12 = CTPtrArray<_KS_COMPLETED_IO_REQUEST,20>::operator[]((char *)this + 192, i);
        if ( *(_DWORD *)(v12 + 112) == (_DWORD)v36 )
        {
          _InterlockedExchange(
            (volatile __int32 *)(CTPtrArray<_KS_COMPLETED_IO_REQUEST,20>::operator[]((char *)this + 192, i) + 1132),
            0);
          if ( (unsigned __int8)byte_1803CECED >= 8u )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              203,
              &WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids,
              this,
              v36);
        }
      }
      goto LABEL_24;
    }
    goto LABEL_44;
  }
  if ( v35 != 1 )
  {
    if ( v35 != 322 && v35 != 323 && v35 - 324 > 1 )
      goto LABEL_24;
    goto LABEL_136;
  }
  CDeviceSourceObjectBase::_QueueEvent(
    (CDeviceSource *)((char *)this + 48),
    1u,
    &GUID_00000000_0000_0000_0000_000000000000,
    v34,
    0);
  if ( v35 == 1
    && (unsigned int)CSourceStateManager::IsValidOperation((char *)this + 184, 0)
    && *((_DWORD *)this + 131) == 1 )
  {
    CDeviceSource::DoStop(this);
    if ( !byte_1803CECED )
      goto LABEL_24;
    v26 = 208;
  }
  else
  {
    if ( !byte_1803CECED )
      goto LABEL_24;
    v26 = 209;
  }
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v26, &WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids, this, v34);
LABEL_24:
  PropVariantClear((PROPVARIANT *)&v39);
  operator delete(0);
  if ( punkObject )
    ((void (__fastcall *)(IUnknown *))punkObject->lpVtbl->Release)(punkObject);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
}

```

## disassembly

```asm
0x1800966e0  mov     [rsp-8+arg_10], rbx
0x1800966e5  push    rbp
0x1800966e6  push    rsi
0x1800966e7  push    rdi
0x1800966e8  push    r12
0x1800966ea  push    r13
0x1800966ec  push    r14
0x1800966ee  push    r15
0x1800966f0  lea     rbp, [rsp-27h]
0x1800966f5  sub     rsp, 90h
0x1800966fc  mov     rax, cs:__security_cookie
0x180096703  xor     rax, rsp
0x180096706  mov     [rbp+57h+var_40], rax
0x18009670a  mov     rdi, rcx
0x18009670d  mov     rsi, rdx
0x180096710  add     rcx, 40h ; '@'; lpCriticalSection
0x180096714  call    cs:__imp_EnterCriticalSection
0x18009671b  nop     dword ptr [rax+rax+00h]
0x180096720  xor     r13d, r13d
0x180096723  lea     r15, [rdi+30h]
0x180096727  xor     eax, eax
0x180096729  mov     [rbp+57h+punkObject], r13
0x18009672d  xorps   xmm0, xmm0
0x180096730  mov     [rbp+57h+var_8C], r13d
0x180096734  mov     [rbp+57h+var_90], r13d
0x180096738  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18009673c  mov     [rbp+57h+var_60], rax
0x180096740  cmp     [r15+40h], r13d
0x180096744  jl      loc_1800968F3
0x18009674a  mov     rcx, [rdi+1B0h]
0x180096751  lea     r8, [rbp+57h+punkObject]
0x180096755  mov     rdx, rsi
0x180096758  mov     rax, [rcx]
0x18009675b  mov     rax, [rax+28h]
0x18009675f  call    cs:__guard_dispatch_icall_fptr
0x180096765  test    eax, eax
0x180096767  js      loc_180096976
0x18009676d  mov     rcx, [rdi+1B0h]
0x180096774  lea     rdx, [rdi+0A8h]
0x18009677b  xor     r8d, r8d
0x18009677e  mov     rax, [rcx]
0x180096781  mov     rax, [rax+20h]
0x180096785  call    cs:__guard_dispatch_icall_fptr
0x18009678b  test    eax, eax
0x18009678d  js      loc_180096CA3
0x180096793  mov     rcx, [rbp+57h+punkObject]
0x180096797  lea     rdx, [rbp+57h+var_8C]
0x18009679b  mov     rax, [rcx]
0x18009679e  mov     rax, [rax+108h]
0x1800967a5  call    cs:__guard_dispatch_icall_fptr
0x1800967ab  test    eax, eax
0x1800967ad  js      loc_18009698A
0x1800967b3  mov     rcx, [rbp+57h+punkObject]
0x1800967b7  lea     rdx, [rbp+57h+var_90]
0x1800967bb  mov     rax, [rcx]
0x1800967be  mov     rax, [rax+118h]
0x1800967c5  call    cs:__guard_dispatch_icall_fptr
0x1800967cb  test    eax, eax
0x1800967cd  js      loc_180096958
0x1800967d3  mov     eax, [rbp+57h+var_8C]
0x1800967d6  lea     rsi, WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids
0x1800967dd  mov     r12b, r13b
0x1800967e0  mov     r14b, 8
0x1800967e3  sub     eax, 1
0x1800967e6  jz      loc_18009708E
0x1800967ec  sub     eax, 1
0x1800967ef  jz      loc_180096DB3
0x1800967f5  sub     eax, 31Eh
0x1800967fa  jz      loc_18009708E
0x180096800  sub     eax, 1
0x180096803  jz      loc_18009708E
0x180096809  cmp     eax, 95h
0x18009680e  jz      loc_180096CBA
0x180096814  mov     rcx, [rdi+200h]
0x18009681b  test    rcx, rcx
0x18009681e  jz      short loc_180096831
0x180096820  mov     eax, [rbp+57h+var_8C]
0x180096823  add     eax, 0FFFFFCE0h
0x180096828  cmp     eax, 1
0x18009682b  jbe     loc_1800970AC
0x180096831  lea     r14, [rdi+0B8h]
0x180096838  cmp     dword ptr [r14], 1
0x18009683c  jnz     loc_18009699E
0x180096842  mov     eax, [rbp+57h+var_8C]
0x180096845  mov     ecx, 146h
0x18009684a  cmp     eax, ecx
0x18009684c  jbe     loc_1800969CA
0x180096852  sub     eax, 147h
0x180096857  jz      loc_180097159
0x18009685d  sub     eax, 113h
0x180096862  jnz     loc_18009721B
0x180096868  xor     eax, eax
0x18009686a  mov     [rbp+57h+var_88], r13
0x18009686e  mov     [rbp+57h+var_48], rax
0x180096872  xorps   xmm0, xmm0
0x180096875  mov     eax, [rbp+57h+var_90]
0x180096878  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18009687c  test    eax, eax
0x18009687e  js      loc_180097267
0x180096884  mov     rcx, [rbp+57h+punkObject]
0x180096888  lea     rdx, [rbp+57h+pvar]
0x18009688c  mov     rax, [rcx]
0x18009688f  mov     rax, [rax+120h]
0x180096896  call    cs:__guard_dispatch_icall_fptr
0x18009689c  test    eax, eax
0x18009689e  js      short loc_1800968AB
0x1800968a0  cmp     word ptr [rbp+57h+pvar], 0Dh
0x1800968a5  jz      loc_18009727E
0x1800968ab  mov     rax, [rdi]
0x1800968ae  mov     rcx, rdi
0x1800968b1  mov     rax, [rax+0B0h]
0x1800968b8  call    cs:__guard_dispatch_icall_fptr
0x1800968be  test    eax, eax
0x1800968c0  js      loc_1800972FD
0x1800968c6  inc     qword ptr [rdi+1E0h]
0x1800968cd  mov     rcx, [rbp+57h+var_88]
0x1800968d1  test    rcx, rcx
0x1800968d4  jz      short loc_1800968E3
0x1800968d6  mov     rax, [rcx]
0x1800968d9  mov     rax, [rax+10h]
0x1800968dd  call    cs:__guard_dispatch_icall_fptr
0x1800968e3  lea     rcx, [rbp+57h+pvar]; pvar
0x1800968e7  call    cs:__imp_PropVariantClear
0x1800968ee  nop     dword ptr [rax+rax+00h]
0x1800968f3  lea     rcx, [rbp+57h+var_70]; pvar
0x1800968f7  call    cs:__imp_PropVariantClear
0x1800968fe  nop     dword ptr [rax+rax+00h]
0x180096903  xor     ecx, ecx; Block
0x180096905  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009690a  mov     rcx, [rbp+57h+punkObject]
0x18009690e  test    rcx, rcx
0x180096911  jz      short loc_180096920
0x180096913  mov     rax, [rcx]
0x180096916  mov     rax, [rax+10h]
0x18009691a  call    cs:__guard_dispatch_icall_fptr
0x180096920  lea     rcx, [rdi+40h]; lpCriticalSection
0x180096924  call    cs:__imp_LeaveCriticalSection
0x18009692b  nop     dword ptr [rax+rax+00h]
0x180096930  mov     rcx, [rbp+57h+var_40]
0x180096934  xor     rcx, rsp; StackCookie
0x180096937  call    __security_check_cookie
0x18009693c  mov     rbx, [rsp+0C0h+arg_10]
0x180096944  add     rsp, 90h
0x18009694b  pop     r15
0x18009694d  pop     r14
0x18009694f  pop     r13
0x180096951  pop     r12
0x180096953  pop     rdi
0x180096954  pop     rsi
0x180096955  pop     rbp
0x180096956  retn
0x180096958  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009695f  jb      short loc_1800968F3
0x180096961  mov     edx, 0B3h
0x180096966  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18009696a  lea     r8, WPP_2e30fba05cf337ae621c2ed1c0c3ea9d_Traceguids
0x180096971  jmp     loc_180096C8B
0x180096976  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009697d  jb      loc_1800968F3
0x180096983  mov     edx, 0B0h
0x180096988  jmp     short loc_180096966
0x18009698a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180096991  jb      loc_1800968F3
0x180096997  mov     edx, 0B2h
0x18009699c  jmp     short loc_180096966
0x18009699e  cmp     [rbp+57h+var_8C], 320h
0x1800969a5  jz      loc_1800970D8
0x1800969ab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800969b2  jb      loc_1800968F3
0x1800969b8  mov     edx, 0C5h
0x1800969bd  mov     dword ptr [rsp+0C0h+var_A0], 0C00D3E9Bh
0x1800969c5  jmp     loc_180096C88
0x1800969ca  jz      loc_180097159
0x1800969d0  test    eax, eax
0x1800969d2  jnz     loc_18009713A
0x1800969d8  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800969df  mov     rcx, [rbp+57h+punkObject]
0x1800969e3  lea     rdx, [rbp+57h+pvar]
0x1800969e7  mov     dword ptr [rbp+57h+var_88], r13d
0x1800969eb  movdqu  xmmword ptr [rbp+57h+pvar], xmm0
0x1800969f0  mov     rax, [rcx]
0x1800969f3  mov     rax, [rax+110h]
0x1800969fa  call    cs:__guard_dispatch_icall_fptr
0x180096a00  test    eax, eax
0x180096a02  jnz     short loc_180096A57
0x180096a04  lea     r8d, [rax+10h]; Size
0x180096a08  lea     rdx, MEDeviceStreamCreated; Buf2
0x180096a0f  lea     rcx, [rbp+57h+pvar]; Buf1
0x180096a13  call    memcmp_0
0x180096a18  test    eax, eax
0x180096a1a  jnz     short loc_180096A57
0x180096a1c  mov     rcx, [rbp+57h+punkObject]
0x180096a20  lea     r8, [rbp+57h+var_88]
0x180096a24  lea     rdx, MF_EVENT_MFT_INPUT_STREAM_ID
0x180096a2b  mov     rax, [rcx]
0x180096a2e  mov     rax, [rax+38h]
0x180096a32  call    cs:__guard_dispatch_icall_fptr
0x180096a38  test    eax, eax
0x180096a3a  jns     loc_180096AD3
0x180096a40  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180096a47  jb      loc_1800968F3
0x180096a4d  mov     edx, 0CAh
0x180096a52  jmp     loc_180096C84
0x180096a57  test    r12b, r12b
0x180096a5a  jz      loc_1800968F3
0x180096a60  cmp     cs:byte_1803CECED, 8
0x180096a67  jb      short loc_180096A95
0x180096a69  mov     eax, [rbp+57h+var_90]
0x180096a6c  mov     edx, 0CCh
0x180096a71  mov     rcx, cs:WPP_GLOBAL_Control
0x180096a78  mov     r9, rdi
0x180096a7b  mov     [rsp+0C0h+var_98], eax
0x180096a7f  mov     r8, rsi
0x180096a82  mov     eax, dword ptr [rbp+57h+var_70+8]
0x180096a85  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180096a89  mov     rcx, [rcx+0D8h]
0x180096a90  call    WPP_SF_qDD
0x180096a95  mov     r9d, [rbp+57h+var_90]; int
0x180096a99  lea     rax, [rbp+57h+var_70]
0x180096a9d  mov     edx, [rbp+57h+var_8C]; unsigned int
0x180096aa0  lea     r8, _GUID_00000000_0000_0000_0000_000000000000; struct _GUID *
0x180096aa7  mov     rcx, r15; this
0x180096aaa  mov     [rsp+0C0h+var_A0], rax; struct tagPROPVARIANT *
0x180096aaf  call    ?_QueueEvent@CDeviceSourceObjectBase@@QEAAJKAEBU_GUID@@JPEBUtagPROPVARIANT@@@Z; CDeviceSourceObjectBase::_QueueEvent(ulong,_GUID const &,long,tagPROPVARIANT const *)
0x180096ab4  test    eax, eax
0x180096ab6  jns     loc_1800968F3
0x180096abc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180096ac3  jb      loc_1800968F3
0x180096ac9  mov     edx, 0CDh
0x180096ace  jmp     loc_180096C84
0x180096ad3  mov     r14d, r13d
0x180096ad6  cmp     [rdi+188h], r13d
0x180096add  jbe     loc_1800968F3
0x180096ae3  lea     r15, [rdi+0C0h]
0x180096aea  mov     edx, r14d
0x180096aed  mov     rcx, r15
0x180096af0  call    ??A?$CTPtrArray@U_KS_COMPLETED_IO_REQUEST@@$0BE@@@QEBAPEAU_KS_COMPLETED_IO_REQUEST@@K@Z; CTPtrArray<_KS_COMPLETED_IO_REQUEST,20>::operator[](ulong)
0x180096af5  mov     ecx, dword ptr [rbp+57h+var_88]
0x180096af8  cmp     [rax+70h], ecx
0x180096afb  jz      short loc_180096B0E
0x180096afd  inc     r14d
0x180096b00  cmp     r14d, [rdi+188h]
0x180096b07  jb      short loc_180096AEA
0x180096b09  jmp     loc_1800968F3
0x180096b0e  mov     edx, r14d
0x180096b11  mov     rcx, r15
0x180096b14  call    ??A?$CTPtrArray@U_KS_COMPLETED_IO_REQUEST@@$0BE@@@QEBAPEAU_KS_COMPLETED_IO_REQUEST@@K@Z; CTPtrArray<_KS_COMPLETED_IO_REQUEST,20>::operator[](ulong)
0x180096b19  mov     ecx, r13d
0x180096b1c  xchg    ecx, [rax+46Ch]
0x180096b22  cmp     cs:byte_1803CECED, 8
0x180096b29  jb      short loc_180096AFD
0x180096b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180096b32  mov     edx, 0CBh
0x180096b37  mov     eax, dword ptr [rbp+57h+var_88]
0x180096b3a  mov     r9, rdi
0x180096b3d  mov     r8, rsi
0x180096b40  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180096b44  mov     rcx, [rcx+0D8h]
0x180096b4b  call    WPP_SF_qD
0x180096b50  jmp     short loc_180096AFD
0x180096b52  mov     r8d, 10h; Size
0x180096b58  lea     rdx, MF_DEVICESOURCE_EXCLUSIVECONTROL_STATUS_CHANGED; Buf2
0x180096b5f  lea     rcx, [rbp+57h+pvar]; Buf1
0x180096b63  call    memcmp_0
0x180096b68  test    eax, eax
0x180096b6a  jz      loc_180096DF1
0x180096b70  mov     r8d, 10h; Size
0x180096b76  lea     rdx, MF_DEVICESOURCE_MT_CHANGEREQUEST; Buf2
0x180096b7d  lea     rcx, [rbp+57h+pvar]; Buf1
0x180096b81  call    memcmp_0
0x180096b86  test    eax, eax
0x180096b88  jz      loc_180096EB6
0x180096b8e  mov     r8d, 10h; Size
0x180096b94  lea     rdx, MF_DEVICESOURCE_MT_CHANGEREQUEST_COMPLETED; Buf2
0x180096b9b  lea     rcx, [rbp+57h+pvar]; Buf1
0x180096b9f  call    memcmp_0
0x180096ba4  test    eax, eax
0x180096ba6  jnz     loc_180096814
0x180096bac  cmp     cs:byte_1803CECED, r14b
0x180096bb3  jb      short loc_180096BE1
0x180096bb5  mov     eax, [rbp+57h+var_90]
0x180096bb8  mov     edx, 0BEh
0x180096bbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180096bc4  mov     r9, rdi
0x180096bc7  mov     [rsp+0C0h+var_98], eax
0x180096bcb  mov     r8, rsi
0x180096bce  mov     eax, [rbp+57h+var_8C]
0x180096bd1  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180096bd5  mov     rcx, [rcx+0D8h]
0x180096bdc  call    WPP_SF_qDD
0x180096be1  mov     rdx, [rdi+268h]; pCallback
0x180096be8  test    rdx, rdx
0x180096beb  jz      loc_180096814
0x180096bf1  mov     rcx, [rbp+57h+punkObject]; punkObject
0x180096bf5  lea     r9, [rbp+57h+ppAsyncResult]; ppAsyncResult
0x180096bf9  xor     r8d, r8d; punkState
0x180096bfc  mov     [rbp+57h+ppAsyncResult], r13
0x180096c00  call    cs:__imp_MFCreateAsyncResult
0x180096c07  nop     dword ptr [rax+rax+00h]
0x180096c0c  test    eax, eax
  ... truncated ...
```
