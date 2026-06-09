# Windows::Networking::UX::Internal::CAccessPointHelper::_CreateNotificationListForFlowEvents(unsigned __int64,Windows::Networking::UX::Internal::CAccessPointHelper::CONNECTION_FLOW_EVENT_ENTRY const *,ulong,_GUID const &,_DOT11_SSID const &,ushort const *,bool,ushort const *,std::unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList,std::default_delete<Windows::Networking::UX::Internal::IWlanNotificationList>> &)

- ea: `0x180031b6c`
- end: `0x180031d34`
- name: `?_CreateNotificationListForFlowEvents@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAJ_KPEBUCONNECTION_FLOW_EVENT_ENTRY@12345@KAEBU_GUID@@AEBU_DOT11_SSID@@PEBG_N4AEAV?$unique_ptr@UIWlanNotificationList@Internal@UX@Networking@Windows@@U?$default_delete@UIWlanNotificationList@Internal@UX@Networking@Windows@@@std@@@std@@@Z`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180033650`

## callees

- `0x1800097b4`
- `0x18000de4c`
- `0x18001d4d4`
- `0x18002ece8`
- `0x18002f0ac`
- `0x18002f0dc`
- `0x18002f1c4`
- `0x180031700`
- `0x180031b6c`
- `0x180057c3c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031c6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031cb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031c6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031cb5`

## string_xrefs

- `0x180031c4e`: `onecoreuap\net\ux\wlanmediamanager\lib\accesspointhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Networking::UX::Internal::CAccessPointHelper::_CreateNotificationListForFlowEvents(
        void *a1,
        unsigned __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        char a8,
        __int64 a9,
        __int64 a10)
{
  int v10; // ebx
  __int64 v12; // r14
  char v13; // r15
  __int64 v14; // r12
  int v15; // r13d
  int v16; // eax
  __int64 v17; // r9
  unsigned int v18; // ebx
  const char *v19; // r9
  __int64 result; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  int v23; // ecx
  unsigned __int64 v24; // rdi
  int v25; // [rsp+20h] [rbp-88h]
  __int64 v26; // [rsp+50h] [rbp-58h] BYREF
  _BYTE v27[80]; // [rsp+58h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  LPVOID pv; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v30; // [rsp+C0h] [rbp+18h]
  int v31; // [rsp+C8h] [rbp+20h]

  v31 = a4;
  v30 = a3;
  pv = a1;
  v10 = a4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids);
  try
  {
    std::make_unique<Windows::Networking::UX::Internal::CWlanNotificationList,,0>();
    v24 = 0;
    v12 = a9;
    v13 = a8;
    v14 = a7;
    v15 = a6;
    while ( v24 < a2 )
    {
      pv = 0;
      v16 = Windows::Networking::UX::Internal::CAccessPointHelper::_AllocWlanNotificationData(
              v23,
              (int)v30 + 8 * (int)v24,
              v10,
              a5,
              v15,
              v14,
              v13,
              v12,
              (__int64)&pv);
      v18 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x675,
          (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\accesspointhelpers.cpp",
          (const char *)(unsigned int)v16,
          v25);
        if ( pv )
          CoTaskMemFree(pv);
        std::unique_ptr<Windows::Networking::UX::Internal::CWlanNotificationList>::~unique_ptr<Windows::Networking::UX::Internal::CWlanNotificationList>(&v26);
        return v18;
      }
      v21 = wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
              v27,
              &pv,
              v26,
              v17);
      Windows::Networking::UX::Internal::CWlanNotificationList::Add(v22, v21);
      v23 = (int)pv;
      if ( pv )
        CoTaskMemFree(pv);
      ++v24;
      v10 = v31;
    }
    std::unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList>::operator=<Windows::Networking::UX::Internal::CWlanNotificationList,std::default_delete<Windows::Networking::UX::Internal::CWlanNotificationList>,0>(
      a10,
      &v26);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids, 0);
    std::unique_ptr<Windows::Networking::UX::Internal::CWlanNotificationList>::~unique_ptr<Windows::Networking::UX::Internal::CWlanNotificationList>(&v26);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x67D,
                           (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\accesspointhelpers.cpp",
                           v19);
  }
  return result;
}

```

## disassembly

```asm
0x180031b6c  mov     [rsp+arg_18], r9d
0x180031b71  mov     [rsp+arg_10], r8
0x180031b76  mov     [rsp+pv], rcx
0x180031b7b  push    rbx
0x180031b7c  push    rsi
0x180031b7d  push    rdi
0x180031b7e  push    r12
0x180031b80  push    r13
0x180031b82  push    r14
0x180031b84  push    r15
0x180031b86  sub     rsp, 70h
0x180031b8a  mov     ebx, r9d
0x180031b8d  mov     rsi, rdx
0x180031b90  lea     rax, WPP_GLOBAL_Control
0x180031b97  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b9e  cmp     rcx, rax
0x180031ba1  jz      short loc_180031BBE
0x180031ba3  test    byte ptr [rcx+1Ch], 40h
0x180031ba7  jz      short loc_180031BBE
0x180031ba9  mov     edx, 98h
0x180031bae  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x180031bb5  mov     rcx, [rcx+10h]
0x180031bb9  call    WPP_SF_
0x180031bbe  lea     rcx, [rsp+0A8h+var_58]
0x180031bc3  call    ??$make_unique@VCWlanNotificationList@Internal@UX@Networking@Windows@@$$V$0A@@std@@YA?AV?$unique_ptr@VCWlanNotificationList@Internal@UX@Networking@Windows@@U?$default_delete@VCWlanNotificationList@Internal@UX@Networking@Windows@@@std@@@0@XZ; std::make_unique<Windows::Networking::UX::Internal::CWlanNotificationList,,0>(void)
0x180031bc8  nop
0x180031bc9  xor     edi, edi
0x180031bcb  mov     r14, [rsp+0A8h+arg_40]
0x180031bd3  mov     r15b, [rsp+0A8h+arg_38]
0x180031bdb  mov     r12, [rsp+0A8h+arg_30]
0x180031be3  mov     r13, qword ptr [rsp+0A8h+arg_28]
0x180031beb  cmp     rdi, rsi
0x180031bee  jnb     loc_180031CCA
0x180031bf4  mov     [rsp+0A8h+pv], 0
0x180031c00  mov     rax, [rsp+0A8h+arg_10]
0x180031c08  lea     rdx, [rax+rdi*8]
0x180031c0c  lea     rax, [rsp+0A8h+pv]
0x180031c14  mov     [rsp+0A8h+var_68], rax
0x180031c19  mov     [rsp+0A8h+var_70], r14
0x180031c1e  mov     [rsp+0A8h+var_78], r15b
0x180031c23  mov     [rsp+0A8h+var_80], r12
0x180031c28  mov     qword ptr [rsp+0A8h+var_88], r13; int
0x180031c2d  mov     r9, [rsp+0A8h+arg_20]
0x180031c35  mov     r8d, ebx
0x180031c38  call    ?_AllocWlanNotificationData@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAJAEBUCONNECTION_FLOW_EVENT_ENTRY@12345@KAEBU_GUID@@AEBU_DOT11_SSID@@PEBG_N3AEAV?$unique_ptr@U_L2_NOTIFICATION_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; Windows::Networking::UX::Internal::CAccessPointHelper::_AllocWlanNotificationData(Windows::Networking::UX::Internal::CAccessPointHelper::CONNECTION_FLOW_EVENT_ENTRY const &,ulong,_GUID const &,_DOT11_SSID const &,ushort const *,bool,ushort const *,wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)
0x180031c3d  mov     ebx, eax
0x180031c3f  test    eax, eax
0x180031c41  jns     short loc_180031C85
0x180031c43  mov     rcx, [rsp+0A8h]; this
0x180031c4b  mov     r9d, eax; char *
0x180031c4e  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180031c55  mov     edx, 675h; void *
0x180031c5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031c5f  nop
0x180031c60  mov     rcx, [rsp+0A8h+pv]; pv
0x180031c68  test    rcx, rcx
0x180031c6b  jz      short loc_180031C74
0x180031c6d  call    cs:__imp_CoTaskMemFree
0x180031c73  nop
0x180031c74  lea     rcx, [rsp+0A8h+var_58]
0x180031c79  call    ??1?$unique_ptr@VCWlanNotificationList@Internal@UX@Networking@Windows@@U?$default_delete@VCWlanNotificationList@Internal@UX@Networking@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Networking::UX::Internal::CWlanNotificationList>::~unique_ptr<Windows::Networking::UX::Internal::CWlanNotificationList>(void)
0x180031c7e  mov     eax, ebx
0x180031c80  jmp     loc_180031D23
0x180031c85  mov     r8, [rsp+0A8h+var_58]
0x180031c8a  lea     rdx, [rsp+0A8h+pv]
0x180031c92  lea     rcx, [rsp+0A8h+var_50]
0x180031c97  call    ??0?$unique_ptr@U_L2_UI_REQUEST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180031c9c  mov     rdx, rax
0x180031c9f  mov     rcx, r8
0x180031ca2  call    ?Add@CWlanNotificationList@Internal@UX@Networking@Windows@@QEAAXV?$unique_ptr@U_L2_NOTIFICATION_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; Windows::Networking::UX::Internal::CWlanNotificationList::Add(wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>)
0x180031ca7  nop
0x180031ca8  mov     rcx, [rsp+0A8h+pv]; pv
0x180031cb0  test    rcx, rcx
0x180031cb3  jz      short loc_180031CBB
0x180031cb5  call    cs:__imp_CoTaskMemFree
0x180031cbb  inc     rdi
0x180031cbe  mov     ebx, [rsp+0A8h+arg_18]
0x180031cc5  jmp     loc_180031BEB
0x180031cca  lea     rdx, [rsp+0A8h+var_58]
0x180031ccf  mov     rcx, [rsp+0A8h+arg_48]
0x180031cd7  call    ??$?4VCWlanNotificationList@Internal@UX@Networking@Windows@@U?$default_delete@VCWlanNotificationList@Internal@UX@Networking@Windows@@@std@@$0A@@?$unique_ptr@UIWlanNotificationList@Internal@UX@Networking@Windows@@U?$default_delete@UIWlanNotificationList@Internal@UX@Networking@Windows@@@std@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@VCWlanNotificationList@Internal@UX@Networking@Windows@@U?$default_delete@VCWlanNotificationList@Internal@UX@Networking@Windows@@@std@@@1@@Z; std::unique_ptr<Windows::Networking::UX::Internal::IWlanNotificationList>::operator=<Windows::Networking::UX::Internal::CWlanNotificationList,std::default_delete<Windows::Networking::UX::Internal::CWlanNotificationList>,0>(std::unique_ptr<Windows::Networking::UX::Internal::CWlanNotificationList> &&)
0x180031cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ce3  lea     rax, WPP_GLOBAL_Control
0x180031cea  cmp     rcx, rax
0x180031ced  jz      short loc_180031D0E
0x180031cef  test    byte ptr [rcx+1Ch], 40h
0x180031cf3  jz      short loc_180031D0E
0x180031cf5  mov     edx, 99h
0x180031cfa  xor     r9d, r9d
0x180031cfd  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x180031d04  mov     rcx, [rcx+10h]
0x180031d08  call    WPP_SF_d
0x180031d0d  nop
0x180031d0e  lea     rcx, [rsp+0A8h+var_58]
0x180031d13  call    ??1?$unique_ptr@VCWlanNotificationList@Internal@UX@Networking@Windows@@U?$default_delete@VCWlanNotificationList@Internal@UX@Networking@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Networking::UX::Internal::CWlanNotificationList>::~unique_ptr<Windows::Networking::UX::Internal::CWlanNotificationList>(void)
0x180031d18  xor     eax, eax
0x180031d1a  jmp     short loc_180031D23
0x180031d1c  mov     eax, dword ptr [rsp+0A8h+pv]
0x180031d23  add     rsp, 70h
0x180031d27  pop     r15
0x180031d29  pop     r14
0x180031d2b  pop     r13
0x180031d2d  pop     r12
0x180031d2f  pop     rdi
0x180031d30  pop     rsi
0x180031d31  pop     rbx
0x180031d32  retn
```
