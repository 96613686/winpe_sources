# RoutePolicyCallout::Init(WDFDRIVER__ *,WDFDEVICE__ *)

- ea: `0x140005034`
- end: `0x140005609`
- name: `?Init@RoutePolicyCallout@@YAJPEAUWDFDRIVER__@@PEAUWDFDEVICE__@@@Z`
- size: `1493`
- prototype: `__int64 __fastcall(RoutePolicyCallout *__hidden this, struct WDFDRIVER__ *, struct WDFDEVICE__ *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14001903c`

## callees

- `0x140001008`
- `0x140002e68`
- `0x140002ff0`
- `0x140005034`
- `0x140005efc`
- `0x140009fb4`
- `0x140009ff8`
- `0x14000a680`
- `0x14000a6c0`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x1400051a2`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400051a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400055c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400055c8`
- `ntoskrnl!ExAllocatePool2` at `0x1400050d9`
- `ntoskrnl!ExAllocatePool2` at `0x1400050d9`
- `fwpkclnt!FwpmEngineClose0` at `0x1400055d8`
- `fwpkclnt!FwpmEngineClose0` at `0x1400055d8`
- `fwpkclnt!FwpmEngineOpen0` at `0x140005078`
- `fwpkclnt!FwpmEngineOpen0` at `0x140005078`

## string_xrefs

- `0x140005170`: `WcmKOpenHandle failed`
- `0x14000509f`: `FwpmEngineOpen failed`

## pseudocode

```c
__int64 __fastcall RoutePolicyCallout::Init(RoutePolicyCallout *this, struct WDFDRIVER__ *a2, struct WDFDEVICE__ *a3)
{
  NTSTATUS v5; // eax
  int v6; // r8d
  int v7; // r9d
  int v8; // ebx
  HANDLE *Pool2; // rax
  int v11; // r8d
  int v12; // r9d
  int v13; // eax
  int v14; // r8d
  int v15; // r9d
  _QWORD *v16; // rcx
  _QWORD *v17; // rax
  __int64 v18; // rdi
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  int v46; // [rsp+30h] [rbp-28h] BYREF
  const char *v47; // [rsp+38h] [rbp-20h] BYREF
  HANDLE engineHandle; // [rsp+40h] [rbp-18h] BYREF

  engineHandle = 0;
  v5 = FwpmEngineOpen0(0, 0xFFFFFFFF, 0, 0, &engineHandle);
  v8 = v5;
  if ( v5 < 0 )
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v46 = v5;
      v47 = "FwpmEngineOpen failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_140012050,
        (unsigned int)&word_14000F8EE,
        v6,
        v7,
        (__int64)&v47,
        (__int64)&v46);
    }
    return (unsigned int)v8;
  }
  Pool2 = (HANDLE *)ExAllocatePool2(64, 80, 1684435058);
  RoutePolicyCallout::g_pCalloutContext = Pool2;
  if ( !Pool2 )
  {
    v8 = -1073741670;
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v46 = -1073741670;
      v47 = "ExAllocatePool2 failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        0,
        (unsigned int)&byte_14000F127,
        v11,
        v12,
        (__int64)&v47,
        (__int64)&v46);
    }
    goto LABEL_48;
  }
  Pool2[2] = this;
  Pool2[3] = a2;
  *Pool2 = engineHandle;
  v13 = WcmKOpenHandle(Pool2 + 4);
  v8 = v13;
  if ( v13 < 0 )
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v46 = v13;
      v47 = "WcmKOpenHandle failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_140012050,
        (unsigned int)word_14000F8B2,
        v14,
        v15,
        (__int64)&v47,
        (__int64)&v46);
    }
    goto LABEL_47;
  }
  KeInitializeSpinLock((PKSPIN_LOCK)RoutePolicyCallout::g_pCalloutContext + 5);
  v16 = RoutePolicyCallout::g_pCalloutContext;
  v17 = (char *)RoutePolicyCallout::g_pCalloutContext + 48;
  *((_QWORD *)RoutePolicyCallout::g_pCalloutContext + 7) = (char *)RoutePolicyCallout::g_pCalloutContext + 48;
  *v17 = v17;
  v16[9] = v16 + 8;
  v16[8] = v16 + 8;
  v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDRIVER__ *))(WdfFunctions_01015 + 248))(
          WdfDriverGlobals,
          a2);
  v8 = AddCallout(v18, engineHandle, &WcmRoutePolicy::c_v4BindCalloutKey, &FWPM_LAYER_ALE_BIND_REDIRECT_V4);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v46 = v8;
      v47 = "AddCallout for V4 Bind failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v19,
        (unsigned int)&word_1400102C6,
        v20,
        v21,
        (__int64)&v47,
        (__int64)&v46);
    }
    goto LABEL_46;
  }
  v8 = AddCallout(v18, engineHandle, &WcmRoutePolicy::c_v6BindCalloutKey, &FWPM_LAYER_ALE_BIND_REDIRECT_V6);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v46 = v8;
      v47 = "AddCallout for V6 Bind failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_14000EE05,
        v23,
        v24,
        (__int64)&v47,
        (__int64)&v46);
    }
    goto LABEL_45;
  }
  v8 = AddCallout(v18, engineHandle, &WcmRoutePolicy::c_v4ConnectCalloutKey, &FWPM_LAYER_ALE_CONNECT_REDIRECT_V4);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v46 = v8;
      v47 = "AddCallout for V4 Connect failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v25,
        (unsigned int)word_140010502,
        v26,
        v27,
        (__int64)&v47,
        (__int64)&v46);
    }
    goto LABEL_44;
  }
  v8 = AddCallout(v18, engineHandle, &WcmRoutePolicy::c_v6ConnectCalloutKey, &FWPM_LAYER_ALE_CONNECT_REDIRECT_V6);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v46 = v8;
      v47 = "AddCallout for V6 Connect failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v28,
        (unsigned int)&word_14000EABE,
        v29,
        v30,
        (__int64)&v47,
        (__int64)&v46);
    }
    goto LABEL_43;
  }
  v8 = AddCallout(
         v18,
         engineHandle,
         &WcmRoutePolicy::c_v4FlowEstablishedCalloutKey,
         &FWPM_LAYER_ALE_FLOW_ESTABLISHED_V4);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v46 = v8;
      v47 = "AddCallout for V4 Flow Established failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v31,
        (unsigned int)byte_14000F213,
        v32,
        v33,
        (__int64)&v47,
        (__int64)&v46);
    }
    goto LABEL_42;
  }
  v8 = AddCallout(
         v18,
         engineHandle,
         &WcmRoutePolicy::c_v6FlowEstablishedCalloutKey,
         &FWPM_LAYER_ALE_FLOW_ESTABLISHED_V6);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v46 = v8;
      v47 = "AddCallout for V6 Flow Established failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v34,
        (unsigned int)&dword_14000F744,
        v35,
        v36,
        (__int64)&v47,
        (__int64)&v46);
    }
    goto LABEL_41;
  }
  v8 = AddCallout(v18, engineHandle, &WcmRoutePolicy::c_v4ClosureCalloutKey, &FWPM_LAYER_ALE_ENDPOINT_CLOSURE_V4);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v46 = v8;
      v47 = "AddCallout for V4 Endpoint Closure failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v37,
        (unsigned int)byte_14000F663,
        v38,
        v39,
        (__int64)&v47,
        (__int64)&v46);
    }
    goto LABEL_40;
  }
  v8 = AddCallout(v18, engineHandle, &WcmRoutePolicy::c_v6ClosureCalloutKey, &FWPM_LAYER_ALE_ENDPOINT_CLOSURE_V6);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v46 = v8;
      v47 = "AddCallout for V6 Endpoint Closure failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v40,
        (unsigned int)word_14000F92A,
        v41,
        v42,
        (__int64)&v47,
        (__int64)&v46);
    }
LABEL_39:
    RemoveCallout(engineHandle, &WcmRoutePolicy::c_v4ClosureCalloutKey);
LABEL_40:
    RemoveCallout(engineHandle, &WcmRoutePolicy::c_v6FlowEstablishedCalloutKey);
LABEL_41:
    RemoveCallout(engineHandle, &WcmRoutePolicy::c_v4FlowEstablishedCalloutKey);
LABEL_42:
    RemoveCallout(engineHandle, &WcmRoutePolicy::c_v6ConnectCalloutKey);
LABEL_43:
    RemoveCallout(engineHandle, &WcmRoutePolicy::c_v4ConnectCalloutKey);
LABEL_44:
    RemoveCallout(engineHandle, &WcmRoutePolicy::c_v6BindCalloutKey);
LABEL_45:
    RemoveCallout(engineHandle, &WcmRoutePolicy::c_v4BindCalloutKey);
LABEL_46:
    WcmKCloseHandle(*((void **)RoutePolicyCallout::g_pCalloutContext + 4));
LABEL_47:
    ExFreePoolWithTag(RoutePolicyCallout::g_pCalloutContext, 0x64667072u);
LABEL_48:
    FwpmEngineClose0(engineHandle);
    return (unsigned int)v8;
  }
  v8 = AddSubLayer(engineHandle);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v46 = v8;
      v47 = "AddSubLayer failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v43,
        (unsigned int)word_14000E95A,
        v44,
        v45,
        (__int64)&v47,
        (__int64)&v46);
    }
    RemoveCallout(engineHandle, &WcmRoutePolicy::c_v6ClosureCalloutKey);
    goto LABEL_39;
  }
  return 0;
}

```

## disassembly

```asm
0x140005034  push    rbp
0x140005036  push    rbx
0x140005037  push    rsi
0x140005038  push    rdi
0x140005039  push    r12
0x14000503b  push    r13
0x14000503d  push    r14
0x14000503f  push    r15
0x140005041  mov     rbp, rsp
0x140005044  sub     rsp, 58h
0x140005048  mov     rax, cs:__security_cookie
0x14000504f  xor     rax, rsp
0x140005052  mov     [rbp+var_10], rax
0x140005056  mov     rdi, rdx
0x140005059  mov     [rbp+var_18], 0
0x140005061  mov     rsi, rcx
0x140005064  lea     rax, [rbp+var_18]
0x140005068  or      edx, 0FFFFFFFFh; authnService
0x14000506b  mov     [rsp+58h+engineHandle], rax; engineHandle
0x140005070  xor     ecx, ecx; serverName
0x140005072  xor     r9d, r9d; session
0x140005075  xor     r8d, r8d; authIdentity
0x140005078  call    cs:__imp_FwpmEngineOpen0
0x14000507f  nop     dword ptr [rax+rax+00h]
0x140005084  mov     ebx, eax
0x140005086  test    eax, eax
0x140005088  jns     short loc_1400050C8
0x14000508a  mov     ecx, cs:dword_140012050
0x140005090  cmp     ecx, 2
0x140005093  jbe     short loc_1400050C1
0x140005095  mov     [rbp+var_28], eax
0x140005098  lea     rdx, word_14000F8EE
0x14000509f  lea     rax, aFwpmengineopen; "FwpmEngineOpen failed"
0x1400050a6  mov     [rbp+var_20], rax
0x1400050aa  lea     rax, [rbp+var_28]
0x1400050ae  mov     [rsp+58h+var_30], rax
0x1400050b3  lea     rax, [rbp+var_20]
0x1400050b7  mov     [rsp+58h+engineHandle], rax
0x1400050bc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400050c1  mov     eax, ebx
0x1400050c3  jmp     loc_1400055EB
0x1400050c8  mov     edx, 50h ; 'P'
0x1400050cd  mov     r14d, 64667072h
0x1400050d3  mov     r8d, r14d
0x1400050d6  lea     ecx, [rdx-10h]
0x1400050d9  call    cs:__imp_ExAllocatePool2
0x1400050e0  nop     dword ptr [rax+rax+00h]
0x1400050e5  mov     cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA, rax; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x1400050ec  mov     rcx, rax
0x1400050ef  test    rax, rax
0x1400050f2  jnz     short loc_140005139
0x1400050f4  mov     eax, cs:dword_140012050
0x1400050fa  mov     ebx, 0C000009Ah
0x1400050ff  cmp     eax, 2
0x140005102  jbe     loc_1400055D4
0x140005108  lea     rax, aExallocatepool; "ExAllocatePool2 failed"
0x14000510f  mov     [rbp+var_28], ebx
0x140005112  mov     [rbp+var_20], rax
0x140005116  lea     rdx, byte_14000F127
0x14000511d  lea     rax, [rbp+var_28]
0x140005121  mov     [rsp+58h+var_30], rax
0x140005126  lea     rax, [rbp+var_20]
0x14000512a  mov     [rsp+58h+engineHandle], rax
0x14000512f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140005134  jmp     loc_1400055D4
0x140005139  mov     [rax+10h], rsi
0x14000513d  mov     [rax+18h], rdi
0x140005141  mov     rax, [rbp+var_18]
0x140005145  mov     [rcx], rax
0x140005148  add     rcx, 20h ; ' '; void **
0x14000514c  call    ?WcmKOpenHandle@@YAJPEAPEAX@Z; WcmKOpenHandle(void * *)
0x140005151  mov     ebx, eax
0x140005153  test    eax, eax
0x140005155  jns     short loc_140005197
0x140005157  mov     ecx, cs:dword_140012050
0x14000515d  cmp     ecx, 2
0x140005160  jbe     loc_1400055BE
0x140005166  mov     [rbp+var_28], eax
0x140005169  lea     rdx, word_14000F8B2
0x140005170  lea     rax, aWcmkopenhandle; "WcmKOpenHandle failed"
0x140005177  mov     [rbp+var_20], rax
0x14000517b  lea     rax, [rbp+var_28]
0x14000517f  mov     [rsp+58h+var_30], rax
0x140005184  lea     rax, [rbp+var_20]
0x140005188  mov     [rsp+58h+engineHandle], rax
0x14000518d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140005192  jmp     loc_1400055BE
0x140005197  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x14000519e  add     rcx, 28h ; '('; SpinLock
0x1400051a2  call    cs:__imp_KeInitializeSpinLock
0x1400051a9  nop     dword ptr [rax+rax+00h]
0x1400051ae  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x1400051b5  mov     rdx, rdi
0x1400051b8  lea     rax, [rcx+30h]
0x1400051bc  mov     [rax+8], rax
0x1400051c0  mov     [rax], rax
0x1400051c3  lea     rax, [rcx+40h]
0x1400051c7  mov     [rax+8], rax
0x1400051cb  mov     [rax], rax
0x1400051ce  mov     rax, cs:WdfFunctions_01015
0x1400051d5  mov     rcx, cs:WdfDriverGlobals
0x1400051dc  mov     rax, [rax+0F8h]
0x1400051e3  call    _guard_dispatch_icall
0x1400051e8  mov     rdx, [rbp+var_18]
0x1400051ec  lea     r15, ?c_v4BindCalloutKey@WcmRoutePolicy@@3U_GUID@@B; _GUID const WcmRoutePolicy::c_v4BindCalloutKey
0x1400051f3  mov     r8, r15
0x1400051f6  lea     r9, FWPM_LAYER_ALE_BIND_REDIRECT_V4
0x1400051fd  mov     rcx, rax
0x140005200  mov     rdi, rax
0x140005203  call    AddCallout
0x140005208  mov     ebx, eax
0x14000520a  test    eax, eax
0x14000520c  jns     short loc_14000524E
0x14000520e  mov     eax, cs:dword_140012050
0x140005214  cmp     eax, 2
0x140005217  jbe     loc_1400055AE
0x14000521d  lea     rax, aAddcalloutForV_6; "AddCallout for V4 Bind failed"
0x140005224  mov     [rbp+var_28], ebx
0x140005227  mov     [rbp+var_20], rax
0x14000522b  lea     rdx, word_1400102C6
0x140005232  lea     rax, [rbp+var_28]
0x140005236  mov     [rsp+58h+var_30], rax
0x14000523b  lea     rax, [rbp+var_20]
0x14000523f  mov     [rsp+58h+engineHandle], rax
0x140005244  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140005249  jmp     loc_1400055AE
0x14000524e  mov     rdx, [rbp+var_18]
0x140005252  lea     rsi, ?c_v6BindCalloutKey@WcmRoutePolicy@@3U_GUID@@B; _GUID const WcmRoutePolicy::c_v6BindCalloutKey
0x140005259  mov     r8, rsi
0x14000525c  lea     r9, FWPM_LAYER_ALE_BIND_REDIRECT_V6
0x140005263  mov     rcx, rdi
0x140005266  call    AddCallout
0x14000526b  mov     ebx, eax
0x14000526d  test    eax, eax
0x14000526f  jns     short loc_1400052B1
0x140005271  mov     eax, cs:dword_140012050
0x140005277  cmp     eax, 2
0x14000527a  jbe     loc_1400055A2
0x140005280  lea     rax, aAddcalloutForV_3; "AddCallout for V6 Bind failed"
0x140005287  mov     [rbp+var_28], ebx
0x14000528a  mov     [rbp+var_20], rax
0x14000528e  lea     rdx, byte_14000EE05
0x140005295  lea     rax, [rbp+var_28]
0x140005299  mov     [rsp+58h+var_30], rax
0x14000529e  lea     rax, [rbp+var_20]
0x1400052a2  mov     [rsp+58h+engineHandle], rax
0x1400052a7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400052ac  jmp     loc_1400055A2
0x1400052b1  mov     rdx, [rbp+var_18]
0x1400052b5  lea     r12, ?c_v4ConnectCalloutKey@WcmRoutePolicy@@3U_GUID@@B; _GUID const WcmRoutePolicy::c_v4ConnectCalloutKey
0x1400052bc  mov     r8, r12
0x1400052bf  lea     r9, FWPM_LAYER_ALE_CONNECT_REDIRECT_V4
0x1400052c6  mov     rcx, rdi
0x1400052c9  call    AddCallout
0x1400052ce  mov     ebx, eax
0x1400052d0  test    eax, eax
0x1400052d2  jns     short loc_140005314
0x1400052d4  mov     eax, cs:dword_140012050
0x1400052da  cmp     eax, 2
0x1400052dd  jbe     loc_140005596
0x1400052e3  lea     rax, aAddcalloutForV; "AddCallout for V4 Connect failed"
0x1400052ea  mov     [rbp+var_28], ebx
0x1400052ed  mov     [rbp+var_20], rax
0x1400052f1  lea     rdx, word_140010502
0x1400052f8  lea     rax, [rbp+var_28]
0x1400052fc  mov     [rsp+58h+var_30], rax
0x140005301  lea     rax, [rbp+var_20]
0x140005305  mov     [rsp+58h+engineHandle], rax
0x14000530a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14000530f  jmp     loc_140005596
0x140005314  mov     rdx, [rbp+var_18]
0x140005318  lea     r13, ?c_v6ConnectCalloutKey@WcmRoutePolicy@@3U_GUID@@B; _GUID const WcmRoutePolicy::c_v6ConnectCalloutKey
0x14000531f  mov     r8, r13
0x140005322  lea     r9, FWPM_LAYER_ALE_CONNECT_REDIRECT_V6
0x140005329  mov     rcx, rdi
0x14000532c  call    AddCallout
0x140005331  mov     ebx, eax
0x140005333  test    eax, eax
0x140005335  jns     short loc_140005377
0x140005337  mov     eax, cs:dword_140012050
0x14000533d  cmp     eax, 2
0x140005340  jbe     loc_14000558A
0x140005346  lea     rax, aAddcalloutForV_4; "AddCallout for V6 Connect failed"
0x14000534d  mov     [rbp+var_28], ebx
0x140005350  mov     [rbp+var_20], rax
0x140005354  lea     rdx, word_14000EABE
0x14000535b  lea     rax, [rbp+var_28]
0x14000535f  mov     [rsp+58h+var_30], rax
0x140005364  lea     rax, [rbp+var_20]
0x140005368  mov     [rsp+58h+engineHandle], rax
0x14000536d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140005372  jmp     loc_14000558A
0x140005377  mov     rdx, [rbp+var_18]
0x14000537b  lea     r9, FWPM_LAYER_ALE_FLOW_ESTABLISHED_V4
0x140005382  lea     r8, ?c_v4FlowEstablishedCalloutKey@WcmRoutePolicy@@3U_GUID@@B; _GUID const WcmRoutePolicy::c_v4FlowEstablishedCalloutKey
0x140005389  mov     rcx, rdi
0x14000538c  call    AddCallout
0x140005391  mov     ebx, eax
0x140005393  test    eax, eax
0x140005395  jns     short loc_1400053D7
0x140005397  mov     eax, cs:dword_140012050
0x14000539d  cmp     eax, 2
0x1400053a0  jbe     loc_14000557E
0x1400053a6  lea     rax, aAddcalloutForV_2; "AddCallout for V4 Flow Established fail"...
0x1400053ad  mov     [rbp+var_28], ebx
0x1400053b0  mov     [rbp+var_20], rax
0x1400053b4  lea     rdx, byte_14000F213
0x1400053bb  lea     rax, [rbp+var_28]
0x1400053bf  mov     [rsp+58h+var_30], rax
0x1400053c4  lea     rax, [rbp+var_20]
0x1400053c8  mov     [rsp+58h+engineHandle], rax
0x1400053cd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400053d2  jmp     loc_14000557E
0x1400053d7  mov     rdx, [rbp+var_18]
0x1400053db  lea     r9, FWPM_LAYER_ALE_FLOW_ESTABLISHED_V6
0x1400053e2  lea     r8, ?c_v6FlowEstablishedCalloutKey@WcmRoutePolicy@@3U_GUID@@B; _GUID const WcmRoutePolicy::c_v6FlowEstablishedCalloutKey
0x1400053e9  mov     rcx, rdi
0x1400053ec  call    AddCallout
0x1400053f1  mov     ebx, eax
0x1400053f3  test    eax, eax
0x1400053f5  jns     short loc_140005437
0x1400053f7  mov     eax, cs:dword_140012050
0x1400053fd  cmp     eax, 2
0x140005400  jbe     loc_14000556E
0x140005406  lea     rax, aAddcalloutForV_0; "AddCallout for V6 Flow Established fail"...
0x14000540d  mov     [rbp+var_28], ebx
0x140005410  mov     [rbp+var_20], rax
0x140005414  lea     rdx, dword_14000F744
0x14000541b  lea     rax, [rbp+var_28]
0x14000541f  mov     [rsp+58h+var_30], rax
0x140005424  lea     rax, [rbp+var_20]
0x140005428  mov     [rsp+58h+engineHandle], rax
0x14000542d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140005432  jmp     loc_14000556E
0x140005437  mov     rdx, [rbp+var_18]
0x14000543b  lea     r9, FWPM_LAYER_ALE_ENDPOINT_CLOSURE_V4
0x140005442  lea     r8, ?c_v4ClosureCalloutKey@WcmRoutePolicy@@3U_GUID@@B; _GUID const WcmRoutePolicy::c_v4ClosureCalloutKey
0x140005449  mov     rcx, rdi
0x14000544c  call    AddCallout
0x140005451  mov     ebx, eax
0x140005453  test    eax, eax
0x140005455  jns     short loc_140005497
0x140005457  mov     eax, cs:dword_140012050
0x14000545d  cmp     eax, 2
0x140005460  jbe     loc_14000555E
0x140005466  lea     rax, aAddcalloutForV_1; "AddCallout for V4 Endpoint Closure fail"...
0x14000546d  mov     [rbp+var_28], ebx
0x140005470  mov     [rbp+var_20], rax
0x140005474  lea     rdx, byte_14000F663
0x14000547b  lea     rax, [rbp+var_28]
0x14000547f  mov     [rsp+58h+var_30], rax
0x140005484  lea     rax, [rbp+var_20]
0x140005488  mov     [rsp+58h+engineHandle], rax
0x14000548d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140005492  jmp     loc_14000555E
0x140005497  mov     rdx, [rbp+var_18]
0x14000549b  lea     r9, FWPM_LAYER_ALE_ENDPOINT_CLOSURE_V6
0x1400054a2  lea     r8, ?c_v6ClosureCalloutKey@WcmRoutePolicy@@3U_GUID@@B; _GUID const WcmRoutePolicy::c_v6ClosureCalloutKey
0x1400054a9  mov     rcx, rdi
0x1400054ac  call    AddCallout
0x1400054b1  mov     ebx, eax
0x1400054b3  test    eax, eax
0x1400054b5  jns     short loc_1400054F4
0x1400054b7  mov     eax, cs:dword_140012050
0x1400054bd  cmp     eax, 2
0x1400054c0  jbe     loc_14000554E
0x1400054c6  lea     rax, aAddcalloutForV_5; "AddCallout for V6 Endpoint Closure fail"...
0x1400054cd  mov     [rbp+var_28], ebx
0x1400054d0  mov     [rbp+var_20], rax
0x1400054d4  lea     rdx, word_14000F92A
0x1400054db  lea     rax, [rbp+var_28]
0x1400054df  mov     [rsp+58h+var_30], rax
0x1400054e4  lea     rax, [rbp+var_20]
0x1400054e8  mov     [rsp+58h+engineHandle], rax
0x1400054ed  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400054f2  jmp     short loc_14000554E
0x1400054f4  mov     rcx, [rbp+var_18]; engineHandle
0x1400054f8  call    AddSubLayer
0x1400054fd  mov     ebx, eax
0x1400054ff  test    eax, eax
0x140005501  jns     loc_1400055E9
0x140005507  mov     eax, cs:dword_140012050
0x14000550d  cmp     eax, 2
0x140005510  jbe     short loc_14000553E
0x140005512  lea     rax, aAddsublayerFai; "AddSubLayer failed"
0x140005519  mov     [rbp+var_28], ebx
0x14000551c  mov     [rbp+var_20], rax
0x140005520  lea     rdx, word_14000E95A
0x140005527  lea     rax, [rbp+var_28]
0x14000552b  mov     [rsp+58h+var_30], rax
0x140005530  lea     rax, [rbp+var_20]
0x140005534  mov     [rsp+58h+engineHandle], rax
0x140005539  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14000553e  mov     rcx, [rbp+var_18]
0x140005542  lea     rdx, ?c_v6ClosureCalloutKey@WcmRoutePolicy@@3U_GUID@@B; _GUID const WcmRoutePolicy::c_v6ClosureCalloutKey
0x140005549  call    RemoveCallout
0x14000554e  mov     rcx, [rbp+var_18]
0x140005552  lea     rdx, ?c_v4ClosureCalloutKey@WcmRoutePolicy@@3U_GUID@@B; _GUID const WcmRoutePolicy::c_v4ClosureCalloutKey
0x140005559  call    RemoveCallout
0x14000555e  mov     rcx, [rbp+var_18]
  ... truncated ...
```
