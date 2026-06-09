# Windows::Networking::UX::Internal::CAccessPointHelper::_FilterMsmConnectionNotification(_L2_NOTIFICATION_DATA const &,std::unique_ptr<Windows::Networking::UX::Internal::CWlanNotificationList,std::default_delete<Windows::Networking::UX::Internal::CWlanNotificationList>> &,bool *)

- ea: `0x180032868`
- end: `0x180032b5f`
- name: `?_FilterMsmConnectionNotification@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAJAEBU_L2_NOTIFICATION_DATA@@AEAV?$unique_ptr@VCWlanNotificationList@Internal@UX@Networking@Windows@@U?$default_delete@VCWlanNotificationList@Internal@UX@Networking@Windows@@@std@@@std@@PEA_N@Z`
- size: `759`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAccessPointHelper *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002fce0`

## callees

- `0x180003ed0`
- `0x180004a70`
- `0x1800097b4`
- `0x18000de4c`
- `0x18001d4d4`
- `0x18002f0dc`
- `0x180031490`
- `0x180032868`
- `0x180033180`
- `0x180034050`
- `0x180034368`
- `0x1800344b4`
- `0x180057c3c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032a93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032a93`

## string_xrefs

- `0x1800328e9`: `onecoreuap\net\ux\wlanmediamanager\lib\accesspointhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::Internal::CAccessPointHelper::_FilterMsmConnectionNotification(
        Windows::Networking::UX::Internal::CAccessPointHelper *this,
        __int64 a2,
        __int64 a3,
        _BYTE *a4)
{
  unsigned int v7; // ebx
  __int64 v8; // r13
  Windows::Networking::UX::Internal::CAccessPointHelper *v9; // rcx
  int v10; // r8d
  int TetheringInfoForSsid; // eax
  void *v12; // rcx
  int v13; // r8d
  int v14; // edx
  PVOID *v15; // rcx
  __int64 v16; // r14
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // r8
  int v21; // [rsp+20h] [rbp-E0h]
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v24[16]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v26[40]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v27[256]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  v22 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids);
  if ( *(_DWORD *)(a2 + 24) < 0x244u )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x510,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\accesspointhelpers.cpp",
      (const char *)0x80070057LL,
      v21);
    return v7;
  }
  v8 = *(_QWORD *)(a2 + 32);
  *a4 = 0;
  memset_0(v24, 0, 0x68u);
  Windows::Networking::UX::Internal::CAccessPointHelper::_SsidToString(
    v9,
    (const struct _DOT11_SSID *)(v8 + 516),
    v10,
    v26);
  TetheringInfoForSsid = Windows::Networking::UX::Internal::CAccessPointHelper::_GetTetheringInfoForSsid(
                           this,
                           (const struct _GUID *)(a2 + 8),
                           (const struct _DOT11_SSID *)(v8 + 516),
                           (struct TETHERING_INTERFACE_INFO *)v24,
                           256,
                           v27);
  v7 = TetheringInfoForSsid;
  if ( TetheringInfoForSsid < 0 )
  {
    if ( TetheringInfoForSsid == -2147023728 )
    {
      v7 = 0;
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v7;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_23;
      WPP_SF_SL(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, v13, (unsigned int)v26, *(_DWORD *)(a2 + 4));
    }
    else
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v7;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_23;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        130,
        &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids,
        (unsigned int)TetheringInfoForSsid);
    }
    goto LABEL_31;
  }
  v14 = *(_DWORD *)(a2 + 4);
  if ( v14 != 4 )
  {
    pv = 0;
    v16 = v25;
    v17 = Windows::Networking::UX::Internal::CAccessPointHelper::_AllocMsmNotificationData(
            v12,
            v14,
            *(_DWORD *)(v8 + 576),
            (_OWORD *)(a2 + 8),
            v8 + 516,
            (unsigned __int16 *)v25,
            (__int64)&pv);
    v7 = v17;
    if ( v17 < 0 )
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_21:
        if ( pv )
        {
          CoTaskMemFree(pv);
          v15 = (PVOID *)WPP_GLOBAL_Control;
        }
        goto LABEL_23;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_16:
        if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 )
        {
          WPP_SF_LSS((TRACEHANDLE)v15[2], (__int64)v26, v16);
          v15 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( (v7 & 0x80000000) == 0 )
        {
          v18 = wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
                  &v22,
                  (__int64 *)&pv);
          Windows::Networking::UX::Internal::CWlanNotificationList::Add(v19, v18);
          *a4 = 1;
          v15 = (PVOID *)WPP_GLOBAL_Control;
        }
        goto LABEL_21;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        127,
        &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids,
        (unsigned int)v17);
    }
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  *a4 = 1;
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    goto LABEL_23;
  WPP_SF_LSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v26, v25);
LABEL_31:
  v15 = (PVOID *)WPP_GLOBAL_Control;
LABEL_23:
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x40) != 0 )
    WPP_SF_d(v15[2], 131, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180032868  push    rbp
0x18003286a  push    rbx
0x18003286b  push    rsi
0x18003286c  push    rdi
0x18003286d  push    r12
0x18003286f  push    r13
0x180032871  push    r14
0x180032873  push    r15
0x180032875  lea     rbp, [rsp-228h]
0x18003287d  sub     rsp, 328h
0x180032884  mov     rax, cs:__security_cookie
0x18003288b  xor     rax, rsp
0x18003288e  mov     [rbp+260h+var_50], rax
0x180032895  mov     rsi, r9
0x180032898  mov     [rsp+360h+var_320], r8
0x18003289d  mov     rdi, rdx
0x1800328a0  mov     rbx, rcx
0x1800328a3  lea     r14, WPP_GLOBAL_Control
0x1800328aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800328b1  cmp     rcx, r14
0x1800328b4  jz      short loc_1800328D1
0x1800328b6  test    byte ptr [rcx+1Ch], 40h
0x1800328ba  jz      short loc_1800328D1
0x1800328bc  mov     edx, 7Dh ; '}'
0x1800328c1  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x1800328c8  mov     rcx, [rcx+10h]
0x1800328cc  call    WPP_SF_
0x1800328d1  cmp     dword ptr [rdi+18h], 244h
0x1800328d8  jnb     short loc_1800328FF
0x1800328da  mov     rcx, [rbp+268h]; this
0x1800328e1  mov     ebx, 80070057h
0x1800328e6  mov     r9d, ebx; char *
0x1800328e9  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800328f0  mov     edx, 510h; void *
0x1800328f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800328fa  jmp     loc_180032ACA
0x1800328ff  mov     r13, [rdi+20h]
0x180032903  mov     byte ptr [rsi], 0
0x180032906  xor     edx, edx; Val
0x180032908  lea     r8d, [rdx+68h]; Size
0x18003290c  lea     rcx, [rsp+360h+var_310]; void *
0x180032911  call    memset_0
0x180032916  lea     r15, [r13+204h]
0x18003291d  lea     r9, [rbp+260h+var_2A0]; unsigned __int16 *
0x180032921  mov     rdx, r15; struct _DOT11_SSID *
0x180032924  call    ?_SsidToString@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAXAEBU_DOT11_SSID@@HPEAG@Z; Windows::Networking::UX::Internal::CAccessPointHelper::_SsidToString(_DOT11_SSID const &,int,ushort *)
0x180032929  lea     rax, [rbp+260h+var_250]
0x18003292d  mov     [rsp+360h+var_338], rax; unsigned __int16 *
0x180032932  mov     dword ptr [rsp+360h+var_340], 100h; int
0x18003293a  lea     r9, [rsp+360h+var_310]; struct TETHERING_INTERFACE_INFO *
0x18003293f  mov     r8, r15; struct _DOT11_SSID *
0x180032942  lea     rdx, [rdi+8]; struct _GUID *
0x180032946  mov     rcx, rbx; this
0x180032949  call    ?_GetTetheringInfoForSsid@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAJAEBU_GUID@@AEBU_DOT11_SSID@@PEAUTETHERING_INTERFACE_INFO@@HPEAG@Z; Windows::Networking::UX::Internal::CAccessPointHelper::_GetTetheringInfoForSsid(_GUID const &,_DOT11_SSID const &,TETHERING_INTERFACE_INFO *,int,ushort *)
0x18003294e  mov     ebx, eax
0x180032950  test    eax, eax
0x180032952  js      loc_180032AEF
0x180032958  mov     edx, [rdi+4]
0x18003295b  cmp     edx, 4
0x18003295e  jnz     short loc_1800329A7
0x180032960  mov     byte ptr [rsi], 1
0x180032963  mov     rcx, cs:WPP_GLOBAL_Control
0x18003296a  cmp     rcx, r14
0x18003296d  jz      loc_180032ACA
0x180032973  test    byte ptr [rcx+1Ch], 8
0x180032977  jz      loc_180032AA7
0x18003297d  mov     edx, 7Eh ; '~'
0x180032982  mov     rax, [rsp+360h+var_300]
0x180032987  mov     [rsp+360h+var_338], rax; __int64
0x18003298c  lea     rax, [rbp+260h+var_2A0]
0x180032990  mov     [rsp+360h+var_340], rax; __int64
0x180032995  mov     r9d, [rdi+4]
0x180032999  mov     rcx, [rcx+10h]; LoggerHandle
0x18003299d  call    WPP_SF_LSS
0x1800329a2  jmp     loc_180032B23
0x1800329a7  mov     [rsp+360h+pv], 0
0x1800329b0  lea     rax, [rsp+360h+pv]
0x1800329b5  mov     [rsp+360h+var_330], rax
0x1800329ba  mov     r14, [rsp+360h+var_300]
0x1800329bf  mov     [rsp+360h+var_338], r14
0x1800329c4  mov     [rsp+360h+var_340], r15
0x1800329c9  lea     r9, [rdi+8]
0x1800329cd  mov     r8d, [r13+240h]
0x1800329d4  call    ?_AllocMsmNotificationData@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAJKKAEBU_GUID@@AEBU_DOT11_SSID@@PEBGAEAV?$unique_ptr@U_L2_NOTIFICATION_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; Windows::Networking::UX::Internal::CAccessPointHelper::_AllocMsmNotificationData(ulong,ulong,_GUID const &,_DOT11_SSID const &,ushort const *,wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)
0x1800329d9  mov     ebx, eax
0x1800329db  test    eax, eax
0x1800329dd  jns     short loc_180032A16
0x1800329df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800329e6  lea     r15, WPP_GLOBAL_Control
0x1800329ed  cmp     rcx, r15
0x1800329f0  jz      loc_180032A86
0x1800329f6  test    byte ptr [rcx+1Ch], 2
0x1800329fa  jz      short loc_180032A24
0x1800329fc  mov     edx, 7Fh
0x180032a01  mov     r9d, eax
0x180032a04  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x180032a0b  mov     rcx, [rcx+10h]
0x180032a0f  call    WPP_SF_d
0x180032a14  jmp     short loc_180032A1D
0x180032a16  lea     r15, WPP_GLOBAL_Control
0x180032a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180032a24  cmp     rcx, r15
0x180032a27  jz      short loc_180032A56
0x180032a29  test    byte ptr [rcx+1Ch], 8
0x180032a2d  jz      short loc_180032A56
0x180032a2f  mov     edx, 80h
0x180032a34  mov     [rsp+360h+var_338], r14; __int64
0x180032a39  lea     rax, [rbp+260h+var_2A0]
0x180032a3d  mov     [rsp+360h+var_340], rax; __int64
0x180032a42  mov     r9d, [rdi+4]
0x180032a46  mov     rcx, [rcx+10h]; LoggerHandle
0x180032a4a  call    WPP_SF_LSS
0x180032a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032a56  test    ebx, ebx
0x180032a58  js      short loc_180032A86
0x180032a5a  mov     r8, [rsp+360h+var_320]
0x180032a5f  mov     r8, [r8]
0x180032a62  lea     rdx, [rsp+360h+pv]
0x180032a67  lea     rcx, [rsp+360h+var_320]
0x180032a6c  call    ??0?$unique_ptr@U_L2_UI_REQUEST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180032a71  mov     rdx, rax
0x180032a74  mov     rcx, r8
0x180032a77  call    ?Add@CWlanNotificationList@Internal@UX@Networking@Windows@@QEAAXV?$unique_ptr@U_L2_NOTIFICATION_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; Windows::Networking::UX::Internal::CWlanNotificationList::Add(wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>)
0x180032a7c  mov     byte ptr [rsi], 1
0x180032a7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032a86  mov     rax, [rsp+360h+pv]
0x180032a8b  test    rax, rax
0x180032a8e  jz      short loc_180032AA0
0x180032a90  mov     rcx, rax; pv
0x180032a93  call    cs:__imp_CoTaskMemFree
0x180032a99  mov     rcx, cs:WPP_GLOBAL_Control
0x180032aa0  lea     r14, WPP_GLOBAL_Control
0x180032aa7  cmp     rcx, r14
0x180032aaa  jz      short loc_180032ACA
0x180032aac  test    byte ptr [rcx+1Ch], 40h
0x180032ab0  jz      short loc_180032ACA
0x180032ab2  mov     edx, 83h
0x180032ab7  mov     r9d, ebx
0x180032aba  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x180032ac1  mov     rcx, [rcx+10h]
0x180032ac5  call    WPP_SF_d
0x180032aca  mov     eax, ebx
0x180032acc  mov     rcx, [rbp+260h+var_50]
0x180032ad3  xor     rcx, rsp; StackCookie
0x180032ad6  call    __security_check_cookie
0x180032adb  add     rsp, 328h
0x180032ae2  pop     r15
0x180032ae4  pop     r14
0x180032ae6  pop     r13
0x180032ae8  pop     r12
0x180032aea  pop     rdi
0x180032aeb  pop     rsi
0x180032aec  pop     rbx
0x180032aed  pop     rbp
0x180032aee  retn
0x180032aef  cmp     eax, 80070490h
0x180032af4  jnz     short loc_180032B2F
0x180032af6  xor     ebx, ebx
0x180032af8  mov     rcx, cs:WPP_GLOBAL_Control
0x180032aff  cmp     rcx, r14
0x180032b02  jz      short loc_180032ACA
0x180032b04  test    byte ptr [rcx+1Ch], 8
0x180032b08  jz      short loc_180032AA7
0x180032b0a  mov     edx, 81h
0x180032b0f  mov     eax, [rdi+4]
0x180032b12  mov     dword ptr [rsp+360h+var_340], eax
0x180032b16  lea     r9, [rbp+260h+var_2A0]
0x180032b1a  mov     rcx, [rcx+10h]
0x180032b1e  call    WPP_SF_SL
0x180032b23  mov     rcx, cs:WPP_GLOBAL_Control
0x180032b2a  jmp     loc_180032AA7
0x180032b2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032b36  cmp     rcx, r14
0x180032b39  jz      short loc_180032ACA
0x180032b3b  test    byte ptr [rcx+1Ch], 2
0x180032b3f  jz      loc_180032AA7
0x180032b45  mov     edx, 82h
0x180032b4a  mov     r9d, eax
0x180032b4d  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x180032b54  mov     rcx, [rcx+10h]
0x180032b58  call    WPP_SF_d
0x180032b5d  jmp     short loc_180032B23
```
