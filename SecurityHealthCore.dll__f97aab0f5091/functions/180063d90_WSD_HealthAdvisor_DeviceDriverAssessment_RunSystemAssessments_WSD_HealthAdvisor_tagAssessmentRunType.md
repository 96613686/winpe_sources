# WSD::HealthAdvisor::DeviceDriverAssessment::RunSystemAssessments(WSD::HealthAdvisor::_tagAssessmentRunType)

- ea: `0x180063d90`
- end: `0x18006460e`
- name: `?RunSystemAssessments@DeviceDriverAssessment@HealthAdvisor@WSD@@UEAAJW4_tagAssessmentRunType@23@@Z`
- size: `2174`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000116c`
- `0x180001a1c`
- `0x18000206c`
- `0x180004710`
- `0x18000517c`
- `0x18000af28`
- `0x18000ccb0`
- `0x18000d7fc`
- `0x18000e288`
- `0x180016d08`
- `0x180053f88`
- `0x18006348c`
- `0x180063d90`
- `0x1800e7010`

## import_xrefs

- `ole32!CoSetProxyBlanket` at `0x180063ef2`
- `ole32!CoSetProxyBlanket` at `0x180063ef2`
- `ole32!CoCreateInstance` at `0x180063e15`
- `ole32!CoCreateInstance` at `0x180063e15`
- `SETUPAPI!CM_Get_DevNode_Status` at `0x180064125`
- `SETUPAPI!CM_Get_DevNode_Status` at `0x180064125`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x1800640fd`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x1800640fd`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18006441d`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800644c0`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800645c2`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18006441d`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800644c0`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800645c2`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180063fcb`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180063fcb`
- `OLEAUT32!__imp_VariantClear` at `0x18006423b`
- `OLEAUT32!__imp_VariantClear` at `0x18006427c`
- `OLEAUT32!__imp_VariantClear` at `0x18006428e`
- `OLEAUT32!__imp_VariantClear` at `0x1800643b6`
- `OLEAUT32!__imp_VariantClear` at `0x1800643fe`
- `OLEAUT32!__imp_VariantClear` at `0x18006423b`
- `OLEAUT32!__imp_VariantClear` at `0x18006427c`
- `OLEAUT32!__imp_VariantClear` at `0x18006428e`
- `OLEAUT32!__imp_VariantClear` at `0x1800643b6`
- `OLEAUT32!__imp_VariantClear` at `0x1800643fe`

## string_xrefs

- `0x180063f5f`: `SELECT ConfigManagerErrorCode, Name, Status FROM Win32_PnPEntity`
- `0x1800640ce`: `ConfigManagerErrorCode`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WSD::HealthAdvisor::DeviceDriverAssessment::RunSystemAssessments(__int64 a1)
{
  __int64 v2; // rcx
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  HRESULT v9; // eax
  int v10; // eax
  char *ClassDevsW; // rbx
  int v12; // eax
  int v13; // edi
  __int64 v14; // rax
  int v15; // esi
  DWORD v16; // r12d
  int v17; // eax
  int LastError; // eax
  __int64 v19; // rcx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  int v31; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v32; // [rsp+68h] [rbp-98h] BYREF
  __int64 v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+80h] [rbp-80h] BYREF
  ULONG pulStatus; // [rsp+84h] [rbp-7Ch] BYREF
  IUnknown *pProxy; // [rsp+88h] [rbp-78h] BYREF
  LPVOID ppv; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG v38; // [rsp+98h] [rbp-68h] BYREF
  ULONG pulProblemNumber; // [rsp+B0h] [rbp-50h] BYREF
  int v40; // [rsp+B4h] [rbp-4Ch] BYREF
  VARIANTARG pvarg; // [rsp+B8h] [rbp-48h] BYREF
  char *v42; // [rsp+D0h] [rbp-30h]
  _SP_DEVINFO_DATA DeviceInfoData; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v44[4]; // [rsp+100h] [rbp+0h] BYREF
  int v45; // [rsp+104h] [rbp+4h]
  unsigned __int16 v46[260]; // [rsp+108h] [rbp+8h] BYREF

  if ( (unsigned int)dword_18012F2B8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18012F2B8, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v2,
      word_18012199A);
  ppv = 0;
  v3 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &ppv);
  v4 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_be44ba144e493abd9ee8a6aab454c74d_Traceguids,
        (unsigned int)v3);
    goto LABEL_116;
  }
  pProxy = 0;
  v5 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)ppv + 24LL))(
         ppv,
         L"ROOT\\CIMV2",
         0,
         0,
         0,
         0,
         0,
         0,
         &pProxy);
  v4 = v5;
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_115;
    v7 = 14;
    v8 = (unsigned int)v5;
    goto LABEL_16;
  }
  v9 = CoSetProxyBlanket(pProxy, 0xAu, 0, 0, 3u, 3u, 0, 0);
  v4 = v9;
  if ( v9 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_115;
    v7 = 15;
    v8 = (unsigned int)v9;
LABEL_16:
    WPP_SF_d(v6[2], v7, WPP_be44ba144e493abd9ee8a6aab454c74d_Traceguids, v8);
    goto LABEL_115;
  }
  v29 = 0;
  v10 = ((__int64 (__fastcall *)(IUnknown *, const unsigned __int16 *, const wchar_t *, __int64, _QWORD, __int64 *))pProxy->lpVtbl[6].Release)(
          pProxy,
          L"WQL",
          L"SELECT ConfigManagerErrorCode, Name, Status FROM Win32_PnPEntity",
          32,
          0,
          &v29);
  v4 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_be44ba144e493abd9ee8a6aab454c74d_Traceguids,
        (unsigned int)v10);
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v29);
    goto LABEL_115;
  }
  ClassDevsW = (char *)SetupDiGetClassDevsW(0, 0, 0, 6u);
  v42 = ClassDevsW;
  if ( ClassDevsW != (char *)-1LL || (v12 = HrGetLastError(), v13 = v12, v12 >= 0) )
  {
    memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
    DeviceInfoData.cbSize = 32;
    pulStatus = 0;
    pulProblemNumber = 0;
    v34 = 0;
    v14 = *(_QWORD *)(a1 + 32);
    if ( v14 != *(_QWORD *)(a1 + 40) )
      *(_QWORD *)(a1 + 40) = v14;
    v15 = 262147;
    v31 = 262147;
    v16 = 0;
    while ( 1 )
    {
      if ( !v29 )
        goto LABEL_66;
      v30 = 0;
      v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, int *))(*(_QWORD *)v29 + 32LL))(
              v29,
              0xFFFFFFFFLL,
              1,
              &v30,
              &v34);
      v13 = v17;
      if ( v17 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            WPP_be44ba144e493abd9ee8a6aab454c74d_Traceguids,
            (unsigned int)v17);
        goto LABEL_96;
      }
      if ( !v34 )
      {
        CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v30);
LABEL_66:
        if ( (unsigned int)dword_18012F2B8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18012F2B8, 0x400000000000LL) )
        {
          v40 = v15;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            v22,
            (unsigned int)&dword_18012194C,
            v23,
            v24,
            (__int64)&v40);
        }
        v32 = 0;
        v33 = 0;
        v13 = CommonUtil::HrStdPushBack<CommonUtil::CStdVector<unsigned int,std::allocator<unsigned int>>,unsigned int>(
                &v32,
                &v31);
        if ( v13 < 0 )
        {
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v26 = 23;
            goto LABEL_73;
          }
LABEL_74:
          if ( (_QWORD)v32 )
          {
            std::_Deallocate<16>(v32, (v33 - v32) & 0xFFFFFFFFFFFFFFFCuLL);
            v32 = 0;
            v33 = 0;
          }
          goto LABEL_97;
        }
        v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *))(**(_QWORD **)(a1 + 16) + 32LL))(
                *(_QWORD *)(a1 + 16),
                *(unsigned int *)(a1 + 8),
                &v32);
        if ( v13 >= 0 )
        {
          v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 16) + 24LL))(
                  *(_QWORD *)(a1 + 16),
                  *(unsigned int *)(a1 + 8));
          if ( v13 >= 0 )
          {
            if ( (unsigned int)dword_18012F2B8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18012F2B8, 0x200000000000LL) )
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                v27,
                &dword_180121974);
            if ( (_QWORD)v32 )
            {
              std::_Deallocate<16>(v32, (v33 - v32) & 0xFFFFFFFFFFFFFFFCuLL);
              v32 = 0;
              v33 = 0;
            }
            if ( (unsigned __int64)(ClassDevsW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              SetupDiDestroyDeviceInfoList(ClassDevsW);
            CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v29);
            v4 = 0;
            goto LABEL_115;
          }
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_74;
          v26 = 25;
        }
        else
        {
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_74;
          v26 = 24;
        }
LABEL_73:
        WPP_SF_d(v25[2], v26, WPP_be44ba144e493abd9ee8a6aab454c74d_Traceguids, (unsigned int)v13);
        goto LABEL_74;
      }
      v38.vt = 0;
      memset_0(v44, 0, 0x208u);
      v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v30 + 32LL))(
              v30,
              L"ConfigManagerErrorCode",
              0,
              &v38,
              0,
              0);
      if ( v13 < 0 || v38.vt < 2u )
        goto LABEL_46;
      if ( !SetupDiEnumDeviceInfo(ClassDevsW, v16, &DeviceInfoData) )
      {
        LastError = HrGetLastError();
        v13 = LastError;
        if ( LastError < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19,
              WPP_be44ba144e493abd9ee8a6aab454c74d_Traceguids,
              (unsigned int)LastError);
LABEL_79:
          if ( v38.vt )
            VariantClear(&v38);
LABEL_96:
          CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v30);
LABEL_97:
          if ( (unsigned __int64)(ClassDevsW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            SetupDiDestroyDeviceInfoList(ClassDevsW);
          goto LABEL_27;
        }
      }
      if ( CM_Get_DevNode_Status(&pulStatus, &pulProblemNumber, DeviceInfoData.DevInst, 0) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_be44ba144e493abd9ee8a6aab454c74d_Traceguids,
            (unsigned int)v13);
        if ( v38.vt )
          VariantClear(&v38);
        CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v30);
        if ( (unsigned __int64)(ClassDevsW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          SetupDiDestroyDeviceInfoList(ClassDevsW);
        CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v29);
        v4 = -2147467259;
        goto LABEL_115;
      }
      if ( !v38.lVal || v38.lVal == 22 || (pulStatus & 0x40000000) != 0 )
      {
        v45 = 262147;
        goto LABEL_47;
      }
      if ( v38.lVal > 0x28u )
        break;
      v19 = 0x1A0800C040ALL;
      if ( !_bittest64(&v19, v38.cyVal.Lo) )
        break;
      v15 = 262145;
      v31 = 262145;
      v45 = 262145;
LABEL_47:
      pvarg.vt = 0;
      if ( (*(int (__fastcall **)(__int64, const WCHAR *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v30 + 32LL))(
             v30,
             L"Name",
             0,
             &pvarg,
             0,
             0) < 0
        || pvarg.vt < 2u )
      {
        v46[0] = 0;
      }
      else
      {
        v13 = StringCchCopyW(v46, 0x100u, pvarg.bstrVal);
        if ( (int)(v13 + 0x80000000) >= 0 && v13 != -2147024774 )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v21 = 21;
            goto LABEL_54;
          }
          goto LABEL_55;
        }
      }
      v13 = CommonUtil::HrStdPushBack<CommonUtil::CStdVector<_tagDriverPropertiesInfo,std::allocator<_tagDriverPropertiesInfo>>,_tagDriverPropertiesInfo>(
              a1 + 32,
              v44);
      if ( v13 < 0 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v21 = 22;
LABEL_54:
          WPP_SF_d(v20[2], v21, WPP_be44ba144e493abd9ee8a6aab454c74d_Traceguids, (unsigned int)v13);
        }
LABEL_55:
        if ( pvarg.vt )
          VariantClear(&pvarg);
        goto LABEL_79;
      }
      ++v16;
      if ( pvarg.vt )
        VariantClear(&pvarg);
      if ( v38.vt )
        VariantClear(&v38);
      CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v30);
    }
    if ( v15 != 262145 )
    {
      v15 = 0x40000;
      v31 = 0x40000;
    }
LABEL_46:
    v45 = 0x40000;
    goto LABEL_47;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_be44ba144e493abd9ee8a6aab454c74d_Traceguids,
      (unsigned int)v12);
LABEL_27:
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v29);
  v4 = v13;
LABEL_115:
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&pProxy);
LABEL_116:
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&ppv);
  return v4;
}

```

## disassembly

```asm
0x180063d90  push    rbp
0x180063d92  push    rbx
0x180063d93  push    rsi
0x180063d94  push    rdi
0x180063d95  push    r12
0x180063d97  push    r13
0x180063d99  push    r14
0x180063d9b  push    r15
0x180063d9d  lea     rbp, [rsp-228h]
0x180063da5  sub     rsp, 328h
0x180063dac  mov     rax, cs:__security_cookie
0x180063db3  xor     rax, rsp
0x180063db6  mov     [rbp+260h+var_50], rax
0x180063dbd  mov     r15, rcx
0x180063dc0  mov     eax, cs:dword_18012F2B8
0x180063dc6  xor     r13d, r13d
0x180063dc9  cmp     eax, 5
0x180063dcc  jbe     short loc_180063DF4
0x180063dce  mov     rdx, 200000000000h
0x180063dd8  lea     rcx, dword_18012F2B8
0x180063ddf  call    _tlgKeywordOn
0x180063de4  test    al, al
0x180063de6  jz      short loc_180063DF4
0x180063de8  lea     rdx, word_18012199A
0x180063def  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180063df4  mov     [rbp+260h+var_2D0], r13
0x180063df8  lea     rax, [rbp+260h+var_2D0]
0x180063dfc  mov     [rsp+360h+ppv], rax; ppv
0x180063e01  lea     r9, IID_IWbemLocator; riid
0x180063e08  xor     edx, edx; pUnkOuter
0x180063e0a  lea     r8d, [rdx+1]; dwClsContext
0x180063e0e  lea     rcx, CLSID_WbemLocator; rclsid
0x180063e15  call    cs:__imp_CoCreateInstance
0x180063e1b  mov     ebx, eax
0x180063e1d  test    eax, eax
0x180063e1f  jns     short loc_180063E5F
0x180063e21  lea     rdx, WPP_GLOBAL_Control
0x180063e28  mov     rcx, cs:WPP_GLOBAL_Control
0x180063e2f  cmp     rcx, rdx
0x180063e32  jz      loc_1800645E0
0x180063e38  test    byte ptr [rcx+1Ch], 1
0x180063e3c  jz      loc_1800645E0
0x180063e42  mov     edx, 0Dh
0x180063e47  mov     r9d, eax
0x180063e4a  lea     r8, WPP_be44ba144e493abd9ee8a6aab454c74d_Traceguids
0x180063e51  mov     rcx, [rcx+10h]
0x180063e55  call    WPP_SF_d
0x180063e5a  jmp     loc_1800645E0
0x180063e5f  mov     [rbp+260h+pProxy], r13
0x180063e63  mov     rcx, [rbp+260h+var_2D0]
0x180063e67  mov     rax, [rcx]
0x180063e6a  lea     rdx, [rbp+260h+pProxy]
0x180063e6e  mov     [rsp+360h+var_320], rdx
0x180063e73  mov     qword ptr [rsp+360h+dwCapabilities], r13
0x180063e78  mov     [rsp+360h+pAuthInfo], r13
0x180063e7d  mov     [rsp+360h+dwImpLevel], r13d
0x180063e82  mov     [rsp+360h+ppv], r13
0x180063e87  xor     r9d, r9d
0x180063e8a  xor     r8d, r8d
0x180063e8d  lea     rdx, aRootCimv2; "ROOT\\CIMV2"
0x180063e94  mov     rax, [rax+18h]
0x180063e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063e9d  mov     ebx, eax
0x180063e9f  test    eax, eax
0x180063ea1  jns     short loc_180063ECE
0x180063ea3  lea     rdx, WPP_GLOBAL_Control
0x180063eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180063eb1  cmp     rcx, rdx
0x180063eb4  jz      loc_1800645D6
0x180063eba  test    byte ptr [rcx+1Ch], 1
0x180063ebe  jz      loc_1800645D6
0x180063ec4  mov     edx, 0Eh
0x180063ec9  mov     r9d, eax
0x180063ecc  jmp     short loc_180063F27
0x180063ece  mov     [rsp+360h+dwCapabilities], r13d; dwCapabilities
0x180063ed3  mov     [rsp+360h+pAuthInfo], r13; pAuthInfo
0x180063ed8  mov     eax, 3
0x180063edd  mov     [rsp+360h+dwImpLevel], eax; dwImpLevel
0x180063ee1  mov     dword ptr [rsp+360h+ppv], eax; dwAuthnLevel
0x180063ee5  xor     r9d, r9d; pServerPrincName
0x180063ee8  xor     r8d, r8d; dwAuthzSvc
0x180063eeb  lea     edx, [rax+7]; dwAuthnSvc
0x180063eee  mov     rcx, [rbp+260h+pProxy]; pProxy
0x180063ef2  call    cs:__imp_CoSetProxyBlanket
0x180063ef8  mov     ebx, eax
0x180063efa  test    eax, eax
0x180063efc  jns     short loc_180063F3C
0x180063efe  lea     rdx, WPP_GLOBAL_Control
0x180063f05  mov     rcx, cs:WPP_GLOBAL_Control
0x180063f0c  cmp     rcx, rdx
0x180063f0f  jz      loc_1800645D6
0x180063f15  test    byte ptr [rcx+1Ch], 1
0x180063f19  jz      loc_1800645D6
0x180063f1f  mov     edx, 0Fh
0x180063f24  mov     r9d, eax
0x180063f27  lea     r8, WPP_be44ba144e493abd9ee8a6aab454c74d_Traceguids
0x180063f2e  mov     rcx, [rcx+10h]
0x180063f32  call    WPP_SF_d
0x180063f37  jmp     loc_1800645D6
0x180063f3c  mov     [rsp+360h+var_310], r13
0x180063f41  mov     rcx, [rbp+260h+pProxy]
0x180063f45  mov     rax, [rcx]
0x180063f48  lea     rdx, [rsp+360h+var_310]
0x180063f4d  mov     qword ptr [rsp+360h+dwImpLevel], rdx
0x180063f52  mov     [rsp+360h+ppv], r13
0x180063f57  mov     esi, 20h ; ' '
0x180063f5c  mov     r9d, esi
0x180063f5f  lea     r8, aSelectConfigma; "SELECT ConfigManagerErrorCode, Name, St"...
0x180063f66  lea     rdx, aWql; "WQL"
0x180063f6d  mov     rax, [rax+0A0h]
0x180063f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063f79  mov     ebx, eax
0x180063f7b  test    eax, eax
0x180063f7d  jns     short loc_180063FBE
0x180063f7f  lea     rdx, WPP_GLOBAL_Control
0x180063f86  mov     rcx, cs:WPP_GLOBAL_Control
0x180063f8d  cmp     rcx, rdx
0x180063f90  jz      short loc_180063FAF
0x180063f92  test    byte ptr [rcx+1Ch], 1
0x180063f96  jz      short loc_180063FAF
0x180063f98  lea     edx, [rsi-10h]
0x180063f9b  mov     r9d, eax
0x180063f9e  lea     r8, WPP_be44ba144e493abd9ee8a6aab454c74d_Traceguids
0x180063fa5  mov     rcx, [rcx+10h]
0x180063fa9  call    WPP_SF_d
0x180063fae  nop
0x180063faf  lea     rcx, [rsp+360h+var_310]
0x180063fb4  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180063fb9  jmp     loc_1800645D6
0x180063fbe  mov     r9d, 6; Flags
0x180063fc4  xor     r8d, r8d; hwndParent
0x180063fc7  xor     edx, edx; Enumerator
0x180063fc9  xor     ecx, ecx; ClassGuid
0x180063fcb  call    cs:__imp_SetupDiGetClassDevsW
0x180063fd1  mov     rbx, rax
0x180063fd4  mov     [rbp+260h+var_290], rax
0x180063fd8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180063fdc  jnz     short loc_18006402A
0x180063fde  call    HrGetLastError
0x180063fe3  mov     edi, eax
0x180063fe5  test    eax, eax
0x180063fe7  jns     short loc_18006402A
0x180063fe9  lea     rdx, WPP_GLOBAL_Control
0x180063ff0  mov     rcx, cs:WPP_GLOBAL_Control
0x180063ff7  cmp     rcx, rdx
0x180063ffa  jz      short loc_180064019
0x180063ffc  test    byte ptr [rcx+1Ch], 1
0x180064000  jz      short loc_180064019
0x180064002  lea     edx, [rbx+12h]
0x180064005  mov     r9d, eax
0x180064008  lea     r8, WPP_be44ba144e493abd9ee8a6aab454c74d_Traceguids
0x18006400f  mov     rcx, [rcx+10h]
0x180064013  call    WPP_SF_d
0x180064018  nop
0x180064019  lea     rcx, [rsp+360h+var_310]
0x18006401e  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180064023  mov     ebx, edi
0x180064025  jmp     loc_1800645D6
0x18006402a  xorps   xmm0, xmm0
0x18006402d  movups  xmmword ptr [rbp+260h+DeviceInfoData.cbSize], xmm0
0x180064031  movups  xmmword ptr [rbp+260h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x180064035  mov     [rbp+260h+DeviceInfoData.cbSize], esi
0x180064038  mov     [rbp+260h+pulStatus], r13d
0x18006403c  mov     [rbp+260h+pulProblemNumber], r13d
0x180064040  mov     [rbp+260h+var_2E0], r13d
0x180064044  mov     rax, [r15+20h]
0x180064048  cmp     rax, [r15+28h]
0x18006404c  jz      short loc_180064052
0x18006404e  mov     [r15+28h], rax
0x180064052  mov     esi, 40003h
0x180064057  mov     [rsp+360h+var_300], esi
0x18006405b  mov     r12d, r13d
0x18006405e  jmp     loc_18006429F
0x180064063  mov     [rsp+360h+var_308], r13
0x180064068  mov     rax, [rcx]
0x18006406b  lea     rdx, [rbp+260h+var_2E0]
0x18006406f  mov     [rsp+360h+ppv], rdx
0x180064074  lea     r9, [rsp+360h+var_308]
0x180064079  mov     r8d, 1
0x18006407f  or      edx, 0FFFFFFFFh
0x180064082  mov     rax, [rax+20h]
0x180064086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006408b  mov     edi, eax
0x18006408d  test    eax, eax
0x18006408f  js      loc_180064472
0x180064095  cmp     [rbp+260h+var_2E0], r13d
0x180064099  jz      loc_180064463
0x18006409f  mov     word ptr [rbp+260h+var_2C8], r13w
0x1800640a4  xor     edx, edx; Val
0x1800640a6  mov     r8d, 208h; Size
0x1800640ac  lea     rcx, [rbp+260h+var_260]; void *
0x1800640b0  call    memset_0
0x1800640b5  mov     rcx, [rsp+360h+var_308]
0x1800640ba  mov     rax, [rcx]
0x1800640bd  mov     qword ptr [rsp+360h+dwImpLevel], r13
0x1800640c2  mov     [rsp+360h+ppv], r13
0x1800640c7  lea     r9, [rbp+260h+var_2C8]
0x1800640cb  xor     r8d, r8d
0x1800640ce  lea     rdx, aConfigmanagere; "ConfigManagerErrorCode"
0x1800640d5  mov     rax, [rax+20h]
0x1800640d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800640de  mov     edi, eax
0x1800640e0  test    eax, eax
0x1800640e2  js      loc_18006418A
0x1800640e8  cmp     word ptr [rbp+260h+var_2C8], 2
0x1800640ed  jb      loc_18006418A
0x1800640f3  lea     r8, [rbp+260h+DeviceInfoData]; DeviceInfoData
0x1800640f7  mov     edx, r12d; MemberIndex
0x1800640fa  mov     rcx, rbx; DeviceInfoSet
0x1800640fd  call    cs:__imp_SetupDiEnumDeviceInfo
0x180064103  test    eax, eax
0x180064105  jnz     short loc_180064116
0x180064107  call    HrGetLastError
0x18006410c  mov     edi, eax
0x18006410e  test    eax, eax
0x180064110  js      loc_180064375
0x180064116  xor     r9d, r9d; ulFlags
0x180064119  mov     r8d, [rbp+260h+DeviceInfoData.DevInst]; dnDevInst
0x18006411d  lea     rdx, [rbp+260h+pulProblemNumber]; pulProblemNumber
0x180064121  lea     rcx, [rbp+260h+pulStatus]; pulStatus
0x180064125  call    cs:__imp_CM_Get_DevNode_Status
0x18006412b  test    eax, eax
0x18006412d  jnz     loc_1800643C1
0x180064133  mov     eax, dword ptr [rbp+260h+var_2C8+8]
0x180064136  test    eax, eax
0x180064138  jz      loc_180064246
0x18006413e  cmp     eax, 16h
0x180064141  jz      loc_180064246
0x180064147  test    [rbp+260h+pulStatus], 40000000h
0x18006414e  jnz     loc_180064246
0x180064154  cmp     eax, 28h ; '('
0x180064157  ja      short loc_180064179
0x180064159  mov     rcx, 1A0800C040Ah
0x180064163  bt      rcx, rax
0x180064167  jnb     short loc_180064179
0x180064169  mov     eax, 40001h
0x18006416e  mov     esi, eax
0x180064170  mov     [rsp+360h+var_300], eax
0x180064174  mov     [rbp+260h+var_25C], eax
0x180064177  jmp     short loc_180064191
0x180064179  cmp     esi, 40001h
0x18006417f  jz      short loc_18006418A
0x180064181  mov     esi, 40000h
0x180064186  mov     [rsp+360h+var_300], esi
0x18006418a  mov     [rbp+260h+var_25C], 40000h
0x180064191  mov     word ptr [rbp+260h+pvarg], r13w
0x180064196  mov     rcx, [rsp+360h+var_308]
0x18006419b  mov     rax, [rcx]
0x18006419e  mov     qword ptr [rsp+360h+dwImpLevel], r13
0x1800641a3  mov     [rsp+360h+ppv], r13
0x1800641a8  lea     r9, [rbp+260h+pvarg]
0x1800641ac  xor     r8d, r8d
0x1800641af  lea     rdx, KeyName; "Name"
0x1800641b6  mov     rax, [rax+20h]
0x1800641ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800641bf  test    eax, eax
0x1800641c1  js      loc_180064252
0x1800641c7  cmp     word ptr [rbp+260h+pvarg], 2
0x1800641cc  jb      loc_180064252
0x1800641d2  mov     r8, qword ptr [rbp+260h+pvarg+8]; unsigned __int16 *
0x1800641d6  mov     edx, 100h; unsigned __int64
0x1800641db  lea     rcx, [rbp+260h+var_258]; unsigned __int16 *
0x1800641df  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800641e4  mov     edi, eax
0x1800641e6  mov     eax, 80000000h
0x1800641eb  lea     ecx, [rdi+rax]
0x1800641ee  test    eax, ecx
0x1800641f0  jnz     short loc_180064257
0x1800641f2  cmp     edi, 8007007Ah
0x1800641f8  jz      short loc_180064257
0x1800641fa  lea     rdx, WPP_GLOBAL_Control
0x180064201  mov     rcx, cs:WPP_GLOBAL_Control
0x180064208  cmp     rcx, rdx
0x18006420b  jz      short loc_18006422C
0x18006420d  test    byte ptr [rcx+1Ch], 1
0x180064211  jz      short loc_18006422C
0x180064213  mov     edx, 15h
0x180064218  mov     r9d, edi
0x18006421b  lea     r8, WPP_be44ba144e493abd9ee8a6aab454c74d_Traceguids
0x180064222  mov     rcx, [rcx+10h]
0x180064226  call    WPP_SF_d
0x18006422b  nop
0x18006422c  cmp     word ptr [rbp+260h+pvarg], r13w
0x180064231  jz      loc_1800643A7
0x180064237  lea     rcx, [rbp+260h+pvarg]; pvarg
0x18006423b  call    cs:__imp_VariantClear
0x180064241  jmp     loc_1800643A7
0x180064246  mov     [rbp+260h+var_25C], 40003h
0x18006424d  jmp     loc_180064191
0x180064252  mov     [rbp+260h+var_258], r13w
0x180064257  lea     rdx, [rbp+260h+var_260]
0x18006425b  lea     rcx, [r15+20h]
0x18006425f  call    ??$HrStdPushBack@V?$CStdVector@U_tagDriverPropertiesInfo@@V?$allocator@U_tagDriverPropertiesInfo@@@std@@@CommonUtil@@U_tagDriverPropertiesInfo@@@CommonUtil@@YAJAEAV?$CStdVector@U_tagDriverPropertiesInfo@@V?$allocator@U_tagDriverPropertiesInfo@@@std@@@0@AEBU_tagDriverPropertiesInfo@@@Z; CommonUtil::HrStdPushBack<CommonUtil::CStdVector<_tagDriverPropertiesInfo,std::allocator<_tagDriverPropertiesInfo>>,_tagDriverPropertiesInfo>(CommonUtil::CStdVector<_tagDriverPropertiesInfo,std::allocator<_tagDriverPropertiesInfo>> &,_tagDriverPropertiesInfo const &)
0x180064264  mov     edi, eax
0x180064266  test    eax, eax
0x180064268  js      loc_180064438
0x18006426e  inc     r12d
0x180064271  cmp     word ptr [rbp+260h+pvarg], r13w
0x180064276  jz      short loc_180064283
0x180064278  lea     rcx, [rbp+260h+pvarg]; pvarg
  ... truncated ...
```
