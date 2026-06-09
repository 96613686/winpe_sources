# Windows::Networking::UX::Internal::CAccessPointHelper::_FilterAcmConnectionNotification(_L2_NOTIFICATION_DATA const &,std::unique_ptr<Windows::Networking::UX::Internal::CWlanNotificationList,std::default_delete<Windows::Networking::UX::Internal::CWlanNotificationList>> &,bool *)

- ea: `0x18003243c`
- end: `0x180032755`
- name: `?_FilterAcmConnectionNotification@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAJAEBU_L2_NOTIFICATION_DATA@@AEAV?$unique_ptr@VCWlanNotificationList@Internal@UX@Networking@Windows@@U?$default_delete@VCWlanNotificationList@Internal@UX@Networking@Windows@@@std@@@std@@PEA_N@Z`
- size: `793`
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
- `0x180031290`
- `0x18003243c`
- `0x180033180`
- `0x180034050`
- `0x180034368`
- `0x1800344b4`
- `0x180057c3c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032635`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032635`

## string_xrefs

- `0x1800324b6`: `onecoreuap\net\ux\wlanmediamanager\lib\accesspointhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::Internal::CAccessPointHelper::_FilterAcmConnectionNotification(
        Windows::Networking::UX::Internal::CAccessPointHelper *this,
        __int64 a2,
        __int64 a3,
        _BYTE *a4)
{
  __int64 v8; // r13
  Windows::Networking::UX::Internal::CAccessPointHelper *v9; // rcx
  int v10; // r8d
  int TetheringInfoForSsid; // eax
  int v12; // r8d
  unsigned int v13; // ebx
  int v14; // edx
  __int64 v15; // r14
  int v16; // eax
  PVOID *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  int v20; // [rsp+20h] [rbp-348h]
  LPVOID pv; // [rsp+50h] [rbp-318h] BYREF
  __int64 v22; // [rsp+58h] [rbp-310h] BYREF
  _BYTE v23[16]; // [rsp+60h] [rbp-308h] BYREF
  __int64 v24; // [rsp+70h] [rbp-2F8h]
  unsigned __int16 v25[40]; // [rsp+D0h] [rbp-298h] BYREF
  unsigned __int16 v26[256]; // [rsp+120h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+0h]

  v22 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids);
  if ( *(_DWORD *)(a2 + 24) < 0x23Cu )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4BC,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\accesspointhelpers.cpp",
      (const char *)0x80070057LL,
      v20);
    return 2147942487LL;
  }
  v8 = *(_QWORD *)(a2 + 32);
  *a4 = 0;
  memset_0(v23, 0, 0x68u);
  Windows::Networking::UX::Internal::CAccessPointHelper::_SsidToString(
    v9,
    (const struct _DOT11_SSID *)(v8 + 516),
    v10,
    v25);
  TetheringInfoForSsid = Windows::Networking::UX::Internal::CAccessPointHelper::_GetTetheringInfoForSsid(
                           this,
                           (const struct _GUID *)(a2 + 8),
                           (const struct _DOT11_SSID *)(v8 + 516),
                           (struct TETHERING_INTERFACE_INFO *)v23,
                           256,
                           v26);
  v13 = TetheringInfoForSsid;
  if ( TetheringInfoForSsid < 0 )
  {
    if ( TetheringInfoForSsid == -2147023728 )
    {
      v13 = 0;
      v17 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_20;
        WPP_SF_SL(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, v12, (unsigned int)v25, *(_DWORD *)(a2 + 4));
        goto LABEL_31;
      }
    }
    else
    {
      v17 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
LABEL_20:
          if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 0x40) != 0 )
            WPP_SF_d(v17[2], 124, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids, v13);
          return v13;
        }
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          123,
          &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids,
          (unsigned int)TetheringInfoForSsid);
LABEL_31:
        v17 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_20;
      }
    }
  }
  else
  {
    v14 = *(_DWORD *)(a2 + 4);
    if ( (unsigned int)(v14 - 9) > 2 )
    {
      pv = 0;
      v15 = v24;
      v16 = Windows::Networking::UX::Internal::CAccessPointHelper::_AllocAcmNotificationData(
              0,
              v14,
              *(_DWORD *)(v8 + 560),
              (_OWORD *)(a2 + 8),
              v8 + 516,
              (unsigned __int16 *)v24,
              0,
              0,
              (__int64)&pv);
      v13 = v16;
      if ( v16 < 0 )
      {
        v17 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        {
LABEL_18:
          if ( pv )
          {
            CoTaskMemFree(pv);
            v17 = (PVOID *)WPP_GLOBAL_Control;
          }
          goto LABEL_20;
        }
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
LABEL_13:
          if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 8) != 0 )
          {
            WPP_SF_LSS((TRACEHANDLE)v17[2], (__int64)v25, v15);
            v17 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( (v13 & 0x80000000) == 0 )
          {
            v18 = wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
                    &v22,
                    (__int64 *)&pv);
            Windows::Networking::UX::Internal::CWlanNotificationList::Add(v19, v18);
            *a4 = 1;
            v17 = (PVOID *)WPP_GLOBAL_Control;
          }
          goto LABEL_18;
        }
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          120,
          &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids,
          (unsigned int)v16);
      }
      v17 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_13;
    }
    *a4 = 1;
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_20;
      WPP_SF_LSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v25, v24);
      goto LABEL_31;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x18003243c  push    rbx
0x18003243e  push    rsi
0x18003243f  push    rdi
0x180032440  push    r12
0x180032442  push    r13
0x180032444  push    r14
0x180032446  push    r15
0x180032448  sub     rsp, 330h
0x18003244f  mov     rax, cs:__security_cookie
0x180032456  xor     rax, rsp
0x180032459  mov     [rsp+368h+var_48], rax
0x180032461  mov     rsi, r9
0x180032464  mov     [rsp+368h+var_310], r8
0x180032469  mov     rdi, rdx
0x18003246c  mov     rbx, rcx
0x18003246f  lea     r14, WPP_GLOBAL_Control
0x180032476  mov     rcx, cs:WPP_GLOBAL_Control
0x18003247d  cmp     rcx, r14
0x180032480  jz      short loc_18003249D
0x180032482  test    byte ptr [rcx+1Ch], 40h
0x180032486  jz      short loc_18003249D
0x180032488  mov     edx, 76h ; 'v'
0x18003248d  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x180032494  mov     rcx, [rcx+10h]
0x180032498  call    WPP_SF_
0x18003249d  cmp     dword ptr [rdi+18h], 23Ch
0x1800324a4  jnb     short loc_1800324CE
0x1800324a6  mov     rcx, [rsp+368h]; this
0x1800324ae  mov     ebx, 80070057h
0x1800324b3  mov     r9d, ebx; char *
0x1800324b6  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800324bd  mov     edx, 4BCh; void *
0x1800324c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800324c7  mov     eax, ebx
0x1800324c9  jmp     loc_180032674
0x1800324ce  mov     r13, [rdi+20h]
0x1800324d2  mov     byte ptr [rsi], 0
0x1800324d5  xor     edx, edx; Val
0x1800324d7  lea     r8d, [rdx+68h]; Size
0x1800324db  lea     rcx, [rsp+368h+var_308]; void *
0x1800324e0  call    memset_0
0x1800324e5  lea     r15, [r13+204h]
0x1800324ec  lea     r9, [rsp+368h+var_298]; unsigned __int16 *
0x1800324f4  mov     rdx, r15; struct _DOT11_SSID *
0x1800324f7  call    ?_SsidToString@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAXAEBU_DOT11_SSID@@HPEAG@Z; Windows::Networking::UX::Internal::CAccessPointHelper::_SsidToString(_DOT11_SSID const &,int,ushort *)
0x1800324fc  lea     rax, [rsp+368h+var_248]
0x180032504  mov     [rsp+368h+var_340], rax; unsigned __int16 *
0x180032509  mov     dword ptr [rsp+368h+var_348], 100h; int
0x180032511  lea     r9, [rsp+368h+var_308]; struct TETHERING_INTERFACE_INFO *
0x180032516  mov     r8, r15; struct _DOT11_SSID *
0x180032519  lea     rdx, [rdi+8]; struct _GUID *
0x18003251d  mov     rcx, rbx; this
0x180032520  call    ?_GetTetheringInfoForSsid@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAJAEBU_GUID@@AEBU_DOT11_SSID@@PEAUTETHERING_INTERFACE_INFO@@HPEAG@Z; Windows::Networking::UX::Internal::CAccessPointHelper::_GetTetheringInfoForSsid(_GUID const &,_DOT11_SSID const &,TETHERING_INTERFACE_INFO *,int,ushort *)
0x180032525  mov     ebx, eax
0x180032527  xor     ecx, ecx
0x180032529  test    eax, eax
0x18003252b  js      loc_1800326D7
0x180032531  mov     edx, [rdi+4]
0x180032534  lea     eax, [rdx-9]
0x180032537  cmp     eax, 2
0x18003253a  jbe     loc_180032697
0x180032540  mov     [rsp+368h+pv], rcx
0x180032545  lea     rax, [rsp+368h+pv]
0x18003254a  mov     [rsp+368h+var_328], rax
0x18003254f  mov     [rsp+368h+var_330], rcx
0x180032554  mov     [rsp+368h+var_338], cl
0x180032558  mov     r14, [rsp+368h+var_2F8]
0x18003255d  mov     [rsp+368h+var_340], r14
0x180032562  mov     [rsp+368h+var_348], r15
0x180032567  lea     r9, [rdi+8]
0x18003256b  mov     r8d, [r13+230h]
0x180032572  call    ?_AllocAcmNotificationData@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAJKKAEBU_GUID@@AEBU_DOT11_SSID@@PEBG_N2AEAV?$unique_ptr@U_L2_NOTIFICATION_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; Windows::Networking::UX::Internal::CAccessPointHelper::_AllocAcmNotificationData(ulong,ulong,_GUID const &,_DOT11_SSID const &,ushort const *,bool,ushort const *,wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)
0x180032577  mov     ebx, eax
0x180032579  test    eax, eax
0x18003257b  jns     short loc_1800325B4
0x18003257d  mov     rcx, cs:WPP_GLOBAL_Control
0x180032584  lea     r15, WPP_GLOBAL_Control
0x18003258b  cmp     rcx, r15
0x18003258e  jz      loc_180032628
0x180032594  test    byte ptr [rcx+1Ch], 2
0x180032598  jz      short loc_1800325C2
0x18003259a  mov     edx, 78h ; 'x'
0x18003259f  mov     r9d, eax
0x1800325a2  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x1800325a9  mov     rcx, [rcx+10h]
0x1800325ad  call    WPP_SF_d
0x1800325b2  jmp     short loc_1800325BB
0x1800325b4  lea     r15, WPP_GLOBAL_Control
0x1800325bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800325c2  cmp     rcx, r15
0x1800325c5  jz      short loc_1800325F8
0x1800325c7  test    byte ptr [rcx+1Ch], 8
0x1800325cb  jz      short loc_1800325F8
0x1800325cd  mov     edx, 79h ; 'y'
0x1800325d2  mov     [rsp+368h+var_340], r14; __int64
0x1800325d7  lea     rax, [rsp+368h+var_298]
0x1800325df  mov     [rsp+368h+var_348], rax; __int64
0x1800325e4  mov     r9d, [rdi+4]
0x1800325e8  mov     rcx, [rcx+10h]; LoggerHandle
0x1800325ec  call    WPP_SF_LSS
0x1800325f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800325f8  test    ebx, ebx
0x1800325fa  js      short loc_180032628
0x1800325fc  mov     r8, [rsp+368h+var_310]
0x180032601  mov     r8, [r8]
0x180032604  lea     rdx, [rsp+368h+pv]
0x180032609  lea     rcx, [rsp+368h+var_310]
0x18003260e  call    ??0?$unique_ptr@U_L2_UI_REQUEST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180032613  mov     rdx, rax
0x180032616  mov     rcx, r8
0x180032619  call    ?Add@CWlanNotificationList@Internal@UX@Networking@Windows@@QEAAXV?$unique_ptr@U_L2_NOTIFICATION_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; Windows::Networking::UX::Internal::CWlanNotificationList::Add(wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>)
0x18003261e  mov     byte ptr [rsi], 1
0x180032621  mov     rcx, cs:WPP_GLOBAL_Control
0x180032628  mov     rax, [rsp+368h+pv]
0x18003262d  test    rax, rax
0x180032630  jz      short loc_180032642
0x180032632  mov     rcx, rax; pv
0x180032635  call    cs:__imp_CoTaskMemFree
0x18003263b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032642  lea     r14, WPP_GLOBAL_Control
0x180032649  cmp     rcx, r14
0x18003264c  jz      short loc_18003266C
0x18003264e  test    byte ptr [rcx+1Ch], 40h
0x180032652  jz      short loc_18003266C
0x180032654  mov     edx, 7Ch ; '|'
0x180032659  mov     r9d, ebx
0x18003265c  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x180032663  mov     rcx, [rcx+10h]
0x180032667  call    WPP_SF_d
0x18003266c  mov     eax, ebx
0x18003266e  jmp     short loc_180032674
0x180032670  mov     eax, dword ptr [rsp+368h+pv]
0x180032674  mov     rcx, [rsp+368h+var_48]
0x18003267c  xor     rcx, rsp; StackCookie
0x18003267f  call    __security_check_cookie
0x180032684  add     rsp, 330h
0x18003268b  pop     r15
0x18003268d  pop     r14
0x18003268f  pop     r13
0x180032691  pop     r12
0x180032693  pop     rdi
0x180032694  pop     rsi
0x180032695  pop     rbx
0x180032696  retn
0x180032697  mov     byte ptr [rsi], 1
0x18003269a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326a1  cmp     rcx, r14
0x1800326a4  jz      short loc_18003266C
0x1800326a6  test    byte ptr [rcx+1Ch], 8
0x1800326aa  jz      short loc_180032649
0x1800326ac  mov     edx, 77h ; 'w'
0x1800326b1  mov     rax, [rsp+368h+var_2F8]
0x1800326b6  mov     [rsp+368h+var_340], rax; __int64
0x1800326bb  lea     rax, [rsp+368h+var_298]
0x1800326c3  mov     [rsp+368h+var_348], rax; __int64
0x1800326c8  mov     r9d, [rdi+4]
0x1800326cc  mov     rcx, [rcx+10h]; LoggerHandle
0x1800326d0  call    WPP_SF_LSS
0x1800326d5  jmp     short loc_180032713
0x1800326d7  cmp     eax, 80070490h
0x1800326dc  jnz     short loc_18003271F
0x1800326de  mov     ebx, ecx
0x1800326e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326e7  cmp     rcx, r14
0x1800326ea  jz      short loc_18003266C
0x1800326ec  test    byte ptr [rcx+1Ch], 8
0x1800326f0  jz      loc_180032649
0x1800326f6  mov     edx, 7Ah ; 'z'
0x1800326fb  mov     eax, [rdi+4]
0x1800326fe  mov     dword ptr [rsp+368h+var_348], eax
0x180032702  lea     r9, [rsp+368h+var_298]
0x18003270a  mov     rcx, [rcx+10h]
0x18003270e  call    WPP_SF_SL
0x180032713  mov     rcx, cs:WPP_GLOBAL_Control
0x18003271a  jmp     loc_180032649
0x18003271f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032726  cmp     rcx, r14
0x180032729  jz      loc_18003266C
0x18003272f  test    byte ptr [rcx+1Ch], 2
0x180032733  jz      loc_180032649
0x180032739  mov     edx, 7Bh ; '{'
0x18003273e  mov     r9d, eax
0x180032741  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x180032748  mov     rcx, [rcx+10h]
0x18003274c  call    WPP_SF_d
0x180032751  jmp     short loc_180032713
```
