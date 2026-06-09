# ?GetGfAppBoundary@VisitsHelper@@SAJPEAPEAUIGeofenceAppBoundary@@AEAV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Z

- ea: `0x18012f668`
- end: `0x18012f854`
- name: `?GetGfAppBoundary@VisitsHelper@@SAJPEAPEAUIGeofenceAppBoundary@@AEAV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Z`
- size: `492`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18012fcbc`

## callees

- `0x180012398`
- `0x180046104`
- `0x180048a04`
- `0x18009c310`
- `0x1800a98c0`
- `0x18012f668`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18012f7bf`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18012f7bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012f7d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012f7d6`
- `OLEAUT32!__imp_SysFreeString` at `0x18012f744`
- `OLEAUT32!__imp_SysFreeString` at `0x18012f81b`
- `OLEAUT32!__imp_SysFreeString` at `0x18012f744`
- `OLEAUT32!__imp_SysFreeString` at `0x18012f81b`

## string_xrefs

- `0x18012f7a3`: `tempGfAppBoundary->get_ForegroundEventName(LOCATION_TRIGGER_TYPE_GEOFENCE, &statusChangedName)`
- `0x18012f717`: `locMgr->GetGeofenceAppBoundary(&tempGfAppBoundary)`
- `0x18012f775`: `tempGfAppBoundary->RegisterForChanges(LOCATION_TRIGGER_TYPE_GEOFENCE)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall VisitsHelper::GetGfAppBoundary(_QWORD *a1, _QWORD *a2)
{
  int LocationManagerInternal; // eax
  signed int v6; // ebx
  int v7; // eax
  const char *v8; // rax
  __int64 v9; // rdx
  int v10; // eax
  int v11; // eax
  HANDLE v12; // rax
  signed int LastError; // eax
  __int64 v14; // rax
  wil::details *v15; // [rsp+28h] [rbp-28h]
  BSTR bstrString; // [rsp+30h] [rbp-20h] BYREF
  __int64 v17; // [rsp+38h] [rbp-18h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+68h] [rbp+18h]

  if ( !a1 )
    return 2147942487LL;
  *a1 = 0;
  ppv = 0;
  LocationManagerInternal = LocationHelper::GetLocationManagerInternal(&ppv);
  v6 = LocationManagerInternal;
  if ( LocationManagerInternal >= 0 )
  {
    v17 = 0;
    bstrString = 0;
    v7 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 40LL))(ppv, &v17);
    v6 = v7;
    if ( v7 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 64LL))(v17, 0);
      v6 = v10;
      if ( v10 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR *))(*(_QWORD *)v17 + 56LL))(v17, 0, &bstrString);
        v6 = v11;
        if ( v11 >= 0 )
        {
          v12 = OpenEventW(0x100000u, 0, bstrString);
          _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
            a2,
            v12);
          if ( *a2 )
          {
            v14 = v17;
            v17 = 0;
            *a1 = v14;
            SysFreeString(bstrString);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
            v6 = 0;
            goto LABEL_19;
          }
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError > 0 )
            v6 = (unsigned __int16)LastError | 0x80070000;
          if ( v6 >= 0 )
            goto LABEL_8;
          LODWORD(v15) = v6;
          v8 = "!(wil::verify_bool(gfNotificationEvent))";
          v9 = 117;
        }
        else
        {
          LODWORD(v15) = v11;
          v8 = "tempGfAppBoundary->get_ForegroundEventName(LOCATION_TRIGGER_TYPE_GEOFENCE, &statusChangedName)";
          v9 = 114;
        }
      }
      else
      {
        LODWORD(v15) = v10;
        v8 = "tempGfAppBoundary->RegisterForChanges(LOCATION_TRIGGER_TYPE_GEOFENCE)";
        v9 = 113;
      }
    }
    else
    {
      LODWORD(v15) = v7;
      v8 = "locMgr->GetGeofenceAppBoundary(&tempGfAppBoundary)";
      v9 = 112;
    }
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\visitsengine\\LocationVisitsHelper.h",
      "VisitsHelper::GetGfAppBoundary",
      v8,
      v15,
      (int)bstrString);
LABEL_8:
    SysFreeString(bstrString);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
    goto LABEL_19;
  }
  LODWORD(v15) = LocationManagerInternal;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0x6B,
    (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\visitsengine\\LocationVisitsHelper.h",
    "VisitsHelper::GetGfAppBoundary",
    "LocationHelper::GetLocationManagerInternal(&locMgr)",
    v15,
    (int)bstrString);
LABEL_19:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18012f668  mov     [rsp-18h+arg_10], rbx
0x18012f66d  push    rbp
0x18012f66e  push    rsi
0x18012f66f  push    rdi
0x18012f670  mov     rbp, rsp
0x18012f673  sub     rsp, 50h
0x18012f677  mov     rax, cs:__security_cookie
0x18012f67e  xor     rax, rsp
0x18012f681  mov     [rbp+var_8], rax
0x18012f685  mov     rsi, rdx
0x18012f688  mov     rdi, rcx
0x18012f68b  test    rcx, rcx
0x18012f68e  jnz     short loc_18012F69A
0x18012f690  mov     eax, 80070057h
0x18012f695  jmp     loc_18012F838
0x18012f69a  mov     qword ptr [rcx], 0
0x18012f6a1  mov     [rbp+ppv], 0
0x18012f6a9  lea     rcx, [rbp+ppv]; ppv
0x18012f6ad  call    ?GetLocationManagerInternal@LocationHelper@@SAJPEAPEAUILocationManagerInternal@@@Z; LocationHelper::GetLocationManagerInternal(ILocationManagerInternal * *)
0x18012f6b2  mov     ebx, eax
0x18012f6b4  test    eax, eax
0x18012f6b6  jns     short loc_18012F6E9
0x18012f6b8  mov     rcx, [rbp+18h]; this
0x18012f6bc  mov     dword ptr [rsp+50h+var_28], eax; wil::details *
0x18012f6c0  lea     rax, aLocationhelper_0; "LocationHelper::GetLocationManagerInter"...
0x18012f6c7  mov     [rsp+50h+var_30], rax; char *
0x18012f6cc  lea     r9, aVisitshelperGe; "VisitsHelper::GetGfAppBoundary"
0x18012f6d3  lea     r8, aOnecoreuapDriv_89; "onecoreuap\\drivers\\mobilepc\\location"...
0x18012f6da  mov     edx, 6Bh ; 'k'; void *
0x18012f6df  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18012f6e4  jmp     loc_18012F82D
0x18012f6e9  mov     [rbp+var_18], 0
0x18012f6f1  mov     [rbp+bstrString], 0
0x18012f6f9  mov     rcx, [rbp+ppv]
0x18012f6fd  mov     rax, [rcx]
0x18012f700  lea     rdx, [rbp+var_18]
0x18012f704  mov     rax, [rax+28h]
0x18012f708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f70d  mov     ebx, eax
0x18012f70f  test    eax, eax
0x18012f711  jns     short loc_18012F759
0x18012f713  mov     dword ptr [rsp+50h+var_28], eax; wil::details *
0x18012f717  lea     rax, aLocmgrGetgeofe; "locMgr->GetGeofenceAppBoundary(&tempGfA"...
0x18012f71e  mov     edx, 70h ; 'p'; void *
0x18012f723  lea     r8, aOnecoreuapDriv_89; "onecoreuap\\drivers\\mobilepc\\location"...
0x18012f72a  lea     r9, aVisitshelperGe; "VisitsHelper::GetGfAppBoundary"
0x18012f731  mov     [rsp+50h+var_30], rax; char *
0x18012f736  mov     rcx, [rbp+18h]; this
0x18012f73a  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18012f73f  nop
0x18012f740  mov     rcx, [rbp+bstrString]; bstrString
0x18012f744  call    cs:__imp_SysFreeString
0x18012f74a  nop
0x18012f74b  lea     rcx, [rbp+var_18]
0x18012f74f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18012f754  jmp     loc_18012F82D
0x18012f759  mov     rcx, [rbp+var_18]
0x18012f75d  mov     rax, [rcx]
0x18012f760  xor     edx, edx
0x18012f762  mov     rax, [rax+40h]
0x18012f766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f76b  mov     ebx, eax
0x18012f76d  test    eax, eax
0x18012f76f  jns     short loc_18012F783
0x18012f771  mov     dword ptr [rsp+50h+var_28], eax
0x18012f775  lea     rax, aTempgfappbound; "tempGfAppBoundary->RegisterForChanges(L"...
0x18012f77c  mov     edx, 71h ; 'q'
0x18012f781  jmp     short loc_18012F723
0x18012f783  mov     rcx, [rbp+var_18]
0x18012f787  mov     rax, [rcx]
0x18012f78a  lea     r8, [rbp+bstrString]
0x18012f78e  xor     edx, edx
0x18012f790  mov     rax, [rax+38h]
0x18012f794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f799  mov     ebx, eax
0x18012f79b  test    eax, eax
0x18012f79d  jns     short loc_18012F7B4
0x18012f79f  mov     dword ptr [rsp+50h+var_28], eax
0x18012f7a3  lea     rax, aTempgfappbound_0; "tempGfAppBoundary->get_ForegroundEventN"...
0x18012f7aa  mov     edx, 72h ; 'r'
0x18012f7af  jmp     loc_18012F723
0x18012f7b4  mov     r8, [rbp+bstrString]; lpName
0x18012f7b8  xor     edx, edx; bInheritHandle
0x18012f7ba  mov     ecx, 100000h; dwDesiredAccess
0x18012f7bf  call    cs:__imp_OpenEventW
0x18012f7c5  mov     rdx, rax
0x18012f7c8  mov     rcx, rsi
0x18012f7cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18012f7d0  cmp     qword ptr [rsi], 0
0x18012f7d4  jnz     short loc_18012F808
0x18012f7d6  call    cs:__imp_GetLastError
0x18012f7dc  mov     ebx, eax
0x18012f7de  test    eax, eax
0x18012f7e0  jle     short loc_18012F7EB
0x18012f7e2  movzx   ebx, ax
0x18012f7e5  or      ebx, 80070000h
0x18012f7eb  test    ebx, ebx
0x18012f7ed  jns     loc_18012F740
0x18012f7f3  mov     dword ptr [rsp+50h+var_28], ebx
0x18012f7f7  lea     rax, aWilVerifyBoolG; "!(wil::verify_bool(gfNotificationEvent)"...
0x18012f7fe  mov     edx, 75h ; 'u'
0x18012f803  jmp     loc_18012F723
0x18012f808  mov     rax, [rbp+var_18]
0x18012f80c  mov     [rbp+var_18], 0
0x18012f814  mov     [rdi], rax
0x18012f817  mov     rcx, [rbp+bstrString]; bstrString
0x18012f81b  call    cs:__imp_SysFreeString
0x18012f821  nop
0x18012f822  lea     rcx, [rbp+var_18]
0x18012f826  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18012f82b  xor     ebx, ebx
0x18012f82d  lea     rcx, [rbp+ppv]
0x18012f831  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18012f836  mov     eax, ebx
0x18012f838  mov     rcx, [rbp+var_8]
0x18012f83c  xor     rcx, rsp; StackCookie
0x18012f83f  call    __security_check_cookie
0x18012f844  mov     rbx, [rsp+50h+arg_10]
0x18012f84c  add     rsp, 50h
0x18012f850  pop     rdi
0x18012f851  pop     rsi
0x18012f852  pop     rbp
0x18012f853  retn
```
