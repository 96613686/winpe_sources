# RoutePolicyCallout::Deinit(void)

- ea: `0x140003f18`
- end: `0x140004329`
- name: `?Deinit@RoutePolicyCallout@@YAXXZ`
- size: `1041`
- prototype: `void __fastcall(RoutePolicyCallout *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008060`
- `0x14001903c`

## callees

- `0x140001008`
- `0x1400012f0`
- `0x140003f18`
- `0x140004e54`
- `0x140005efc`
- `0x140006e28`
- `0x140007d28`
- `0x140007d7c`
- `0x14000935c`
- `0x140009fb4`
- `0x14000a680`
- `0x14000a6c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400041b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400042b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400042f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400041b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400042b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400042f0`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x140003f57`
- `fwpkclnt!FwpmSubLayerDeleteByKey0` at `0x140003f57`
- `fwpkclnt!FwpmEngineClose0` at `0x140004058`
- `fwpkclnt!FwpmEngineClose0` at `0x140004058`

## string_xrefs

- `0x140003f7c`: `FwpmSubLayerDeleteByKey failed`

## pseudocode

```c
void __fastcall RoutePolicyCallout::Deinit(RoutePolicyCallout *this)
{
  char *v1; // rdx
  NTSTATUS v2; // eax
  int v3; // r8d
  int v4; // r9d
  void *v5; // r8
  PVOID *v6; // rcx
  PVOID **v7; // rax
  PVOID *v8; // rdx
  PVOID *v9; // rcx
  PVOID *v10; // rcx
  PVOID **v11; // rax
  PVOID *v12; // rdx
  PVOID *v13; // rcx
  PVOID v14; // rcx
  __int64 v15; // rax
  _QWORD *v16; // rdi
  _QWORD **v17; // rbx
  _QWORD *v18; // rcx
  _QWORD *v19; // rax
  void *v20; // rdx
  unsigned int v21; // eax
  __int64 v22; // rcx
  PVOID v23; // rcx
  __int64 v24; // rax
  void *v25; // rcx
  _DWORD v26[4]; // [rsp+30h] [rbp-49h] BYREF
  __int128 v27; // [rsp+40h] [rbp-39h] BYREF
  __int128 v28; // [rsp+50h] [rbp-29h] BYREF
  PVOID P; // [rsp+60h] [rbp-19h] BYREF
  PVOID *p_P; // [rsp+68h] [rbp-11h]
  PVOID v31; // [rsp+70h] [rbp-9h] BYREF
  PVOID *v32; // [rsp+78h] [rbp-1h]
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+80h] [rbp+7h] BYREF
  _DWORD *v34; // [rsp+A0h] [rbp+27h]
  __int64 v35; // [rsp+A8h] [rbp+2Fh]
  __int128 *v36; // [rsp+B0h] [rbp+37h]
  __int64 v37; // [rsp+B8h] [rbp+3Fh]

  v1 = (char *)RoutePolicyCallout::g_pCalloutContext;
  if ( *(_QWORD *)RoutePolicyCallout::g_pCalloutContext )
  {
    v2 = FwpmSubLayerDeleteByKey0(
           *(HANDLE *)RoutePolicyCallout::g_pCalloutContext,
           &WcmRoutePolicy::c_calloutSubLayerKey);
    if ( v2 < 0 && (unsigned int)dword_140012050 > 3 )
    {
      v26[0] = v2;
      *(_QWORD *)&v27 = "FwpmSubLayerDeleteByKey failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_140012050,
        (unsigned int)byte_14000EC2B,
        v3,
        v4,
        (__int64)&v27,
        (__int64)v26);
    }
    RemoveCallout(*(_QWORD *)RoutePolicyCallout::g_pCalloutContext, &WcmRoutePolicy::c_v6ClosureCalloutKey);
    RemoveCallout(*(_QWORD *)RoutePolicyCallout::g_pCalloutContext, &WcmRoutePolicy::c_v4ClosureCalloutKey);
    RemoveCallout(*(_QWORD *)RoutePolicyCallout::g_pCalloutContext, &WcmRoutePolicy::c_v6FlowEstablishedCalloutKey);
    RemoveCallout(*(_QWORD *)RoutePolicyCallout::g_pCalloutContext, &WcmRoutePolicy::c_v4FlowEstablishedCalloutKey);
    RemoveCallout(*(_QWORD *)RoutePolicyCallout::g_pCalloutContext, &WcmRoutePolicy::c_v6ConnectCalloutKey);
    RemoveCallout(*(_QWORD *)RoutePolicyCallout::g_pCalloutContext, &WcmRoutePolicy::c_v4ConnectCalloutKey);
    RemoveCallout(*(_QWORD *)RoutePolicyCallout::g_pCalloutContext, &WcmRoutePolicy::c_v6BindCalloutKey);
    RemoveCallout(*(_QWORD *)RoutePolicyCallout::g_pCalloutContext, &WcmRoutePolicy::c_v4BindCalloutKey);
    FwpmEngineClose0(*(HANDLE *)RoutePolicyCallout::g_pCalloutContext);
    v1 = (char *)RoutePolicyCallout::g_pCalloutContext;
    *(_QWORD *)RoutePolicyCallout::g_pCalloutContext = 0;
  }
  AcquireSpinLock(&v27, v1 + 40);
  p_P = &P;
  P = &P;
  while ( 1 )
  {
    v6 = (PVOID *)((char *)RoutePolicyCallout::g_pCalloutContext + 64);
    v7 = (PVOID **)*((_QWORD *)RoutePolicyCallout::g_pCalloutContext + 8);
    if ( v7 == (PVOID **)((char *)RoutePolicyCallout::g_pCalloutContext + 64) )
      break;
    if ( v7[1] != v6 )
      goto LABEL_38;
    v8 = *v7;
    if ( (*v7)[1] != v7 )
      goto LABEL_38;
    *v6 = v8;
    v8[1] = v6;
    v9 = p_P;
    if ( *p_P != &P )
      goto LABEL_38;
    v7[1] = p_P;
    *v7 = &P;
    *v9 = v7;
    p_P = (PVOID *)v7;
  }
  v32 = &v31;
  v10 = (PVOID *)((char *)RoutePolicyCallout::g_pCalloutContext + 48);
  v31 = &v31;
  v11 = (PVOID **)*((_QWORD *)RoutePolicyCallout::g_pCalloutContext + 6);
  if ( v11 != (PVOID **)((char *)RoutePolicyCallout::g_pCalloutContext + 48) )
  {
    if ( v11[1] != v10 || (v12 = *v11, (*v11)[1] != v11) || (*v10 = v12, v12[1] = v10, v13 = v32, *v32 != &v31) )
LABEL_38:
      __fastfail(3u);
    v11[1] = v32;
    *v11 = &v31;
    *v13 = v11;
    v32 = (PVOID *)v11;
  }
  if ( (_QWORD)v27 )
  {
    v28 = v27;
    SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v28);
  }
  while ( P != &P )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 3056))(
      WdfDriverGlobals,
      *((_QWORD *)P + 2));
    v14 = P;
    if ( *((PVOID **)P + 1) != &P )
      goto LABEL_38;
    v15 = *(_QWORD *)P;
    if ( *(PVOID *)(*(_QWORD *)P + 8LL) != P )
      goto LABEL_38;
    P = *(PVOID *)P;
    *(_QWORD *)(v15 + 8) = &P;
    ExFreePoolWithTag(v14, 0x64667072u);
  }
  while ( 1 )
  {
    v16 = v31;
    if ( v31 == &v31 )
      break;
    v17 = (_QWORD **)((char *)v31 + 32);
    while ( 1 )
    {
      v18 = *v17;
      if ( *v17 == v17 )
        break;
      if ( (_QWORD **)v18[1] != v17 )
        goto LABEL_38;
      v19 = (_QWORD *)*v18;
      if ( *(_QWORD **)(*v18 + 8LL) != v18 )
        goto LABEL_38;
      *v17 = v19;
      v19[1] = v17;
      FreeConnectionContext(v18);
    }
    if ( !v16[3] )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    v20 = (void *)v16[3];
    if ( v20 )
    {
      v21 = RoutePolicyCallout::Wrapper_WcmKReleaseInterface(
              *((RoutePolicyCallout **)RoutePolicyCallout::g_pCalloutContext + 4),
              v20,
              v5);
      if ( v21 )
      {
        if ( (unsigned int)dword_140012050 > 3 )
        {
          v22 = v16[2];
          v26[0] = v21;
          *(_QWORD *)&v27 = v22;
          v36 = &v27;
          v37 = 8;
          v34 = v26;
          v35 = 4;
          tlgWriteTransfer_EtwWriteTransfer((int)&dword_140012050, (int)&byte_14001013B, 0, 0, 4u, &v33);
        }
      }
    }
    v23 = v31;
    if ( *((PVOID **)v31 + 1) != &v31 )
      goto LABEL_38;
    v24 = *(_QWORD *)v31;
    if ( *(PVOID *)(*(_QWORD *)v31 + 8LL) != v31 )
      goto LABEL_38;
    v31 = *(PVOID *)v31;
    *(_QWORD *)(v24 + 8) = &v31;
    ExFreePoolWithTag(v23, 0x64667072u);
  }
  v25 = (void *)*((_QWORD *)RoutePolicyCallout::g_pCalloutContext + 4);
  if ( v25 )
    WcmKCloseHandle(v25);
  ExFreePoolWithTag(RoutePolicyCallout::g_pCalloutContext, 0x64667072u);
  RoutePolicyCallout::g_pCalloutContext = 0;
}

```

## disassembly

```asm
0x140003f18  mov     [rsp-8+arg_0], rbx
0x140003f1d  mov     [rsp-8+arg_8], rdi
0x140003f22  push    rbp
0x140003f23  lea     rbp, [rsp-57h]
0x140003f28  sub     rsp, 0D0h
0x140003f2f  mov     rax, cs:__security_cookie
0x140003f36  xor     rax, rsp
0x140003f39  mov     [rbp+57h+var_10], rax
0x140003f3d  mov     rdx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140003f44  mov     rcx, [rdx]; engineHandle
0x140003f47  test    rcx, rcx
0x140003f4a  jz      loc_140004072
0x140003f50  lea     rdx, ?c_calloutSubLayerKey@WcmRoutePolicy@@3U_GUID@@B; key
0x140003f57  call    cs:__imp_FwpmSubLayerDeleteByKey0
0x140003f5e  nop     dword ptr [rax+rax+00h]
0x140003f63  test    eax, eax
0x140003f65  jns     short loc_140003F9E
0x140003f67  mov     ecx, cs:dword_140012050
0x140003f6d  cmp     ecx, 3
0x140003f70  jbe     short loc_140003F9E
0x140003f72  mov     [rbp+57h+var_A0], eax
0x140003f75  lea     rdx, byte_14000EC2B
0x140003f7c  lea     rax, aFwpmsublayerde; "FwpmSubLayerDeleteByKey failed"
0x140003f83  mov     qword ptr [rbp+57h+var_90], rax
0x140003f87  lea     rax, [rbp+57h+var_A0]
0x140003f8b  mov     [rsp+0D0h+var_A8], rax
0x140003f90  lea     rax, [rbp+57h+var_90]
0x140003f94  mov     qword ptr [rsp+0D0h+var_B0], rax
0x140003f99  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003f9e  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140003fa5  lea     rdx, ?c_v6ClosureCalloutKey@WcmRoutePolicy@@3U_GUID@@B; _GUID const WcmRoutePolicy::c_v6ClosureCalloutKey
0x140003fac  mov     rcx, [rcx]
0x140003faf  call    RemoveCallout
0x140003fb4  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140003fbb  lea     rdx, ?c_v4ClosureCalloutKey@WcmRoutePolicy@@3U_GUID@@B; _GUID const WcmRoutePolicy::c_v4ClosureCalloutKey
0x140003fc2  mov     rcx, [rcx]
0x140003fc5  call    RemoveCallout
0x140003fca  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140003fd1  lea     rdx, ?c_v6FlowEstablishedCalloutKey@WcmRoutePolicy@@3U_GUID@@B; _GUID const WcmRoutePolicy::c_v6FlowEstablishedCalloutKey
0x140003fd8  mov     rcx, [rcx]
0x140003fdb  call    RemoveCallout
0x140003fe0  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140003fe7  lea     rdx, ?c_v4FlowEstablishedCalloutKey@WcmRoutePolicy@@3U_GUID@@B; _GUID const WcmRoutePolicy::c_v4FlowEstablishedCalloutKey
0x140003fee  mov     rcx, [rcx]
0x140003ff1  call    RemoveCallout
0x140003ff6  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140003ffd  lea     rdx, ?c_v6ConnectCalloutKey@WcmRoutePolicy@@3U_GUID@@B; _GUID const WcmRoutePolicy::c_v6ConnectCalloutKey
0x140004004  mov     rcx, [rcx]
0x140004007  call    RemoveCallout
0x14000400c  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140004013  lea     rdx, ?c_v4ConnectCalloutKey@WcmRoutePolicy@@3U_GUID@@B; _GUID const WcmRoutePolicy::c_v4ConnectCalloutKey
0x14000401a  mov     rcx, [rcx]
0x14000401d  call    RemoveCallout
0x140004022  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140004029  lea     rdx, ?c_v6BindCalloutKey@WcmRoutePolicy@@3U_GUID@@B; _GUID const WcmRoutePolicy::c_v6BindCalloutKey
0x140004030  mov     rcx, [rcx]
0x140004033  call    RemoveCallout
0x140004038  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x14000403f  lea     rdx, ?c_v4BindCalloutKey@WcmRoutePolicy@@3U_GUID@@B; _GUID const WcmRoutePolicy::c_v4BindCalloutKey
0x140004046  mov     rcx, [rcx]
0x140004049  call    RemoveCallout
0x14000404e  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140004055  mov     rcx, [rcx]; engineHandle
0x140004058  call    cs:__imp_FwpmEngineClose0
0x14000405f  nop     dword ptr [rax+rax+00h]
0x140004064  mov     rdx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x14000406b  mov     qword ptr [rdx], 0
0x140004072  add     rdx, 28h ; '('
0x140004076  lea     rcx, [rbp+57h+var_90]
0x14000407a  call    ?AcquireSpinLock@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUSpinLockAndSavedIrql@@@Z$1?Release@1@SAX0@ZU?$integral_constant@_K$01@wistd@@U1@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_K@Z; AcquireSpinLock(unsigned __int64 *)
0x14000407f  lea     rax, [rbp+57h+P]
0x140004083  mov     [rbp+57h+var_68], rax
0x140004087  lea     rax, [rbp+57h+P]
0x14000408b  mov     [rbp+57h+P], rax
0x14000408f  mov     rdx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140004096  lea     rcx, [rdx+40h]
0x14000409a  mov     rax, [rcx]
0x14000409d  cmp     rax, rcx
0x1400040a0  jz      short loc_1400040E5
0x1400040a2  cmp     [rax+8], rcx
0x1400040a6  jnz     loc_1400042C8
0x1400040ac  mov     rdx, [rax]
0x1400040af  cmp     [rdx+8], rax
0x1400040b3  jnz     loc_1400042C8
0x1400040b9  mov     [rcx], rdx
0x1400040bc  mov     [rdx+8], rcx
0x1400040c0  lea     rdx, [rbp+57h+P]
0x1400040c4  mov     rcx, [rbp+57h+var_68]
0x1400040c8  cmp     [rcx], rdx
0x1400040cb  jnz     loc_1400042C8
0x1400040d1  mov     [rax+8], rcx
0x1400040d5  lea     rdx, [rbp+57h+P]
0x1400040d9  mov     [rax], rdx
0x1400040dc  mov     [rcx], rax
0x1400040df  mov     [rbp+57h+var_68], rax
0x1400040e3  jmp     short loc_14000408F
0x1400040e5  lea     rax, [rbp+57h+var_60]
0x1400040e9  mov     [rbp+57h+var_58], rax
0x1400040ed  lea     rcx, [rdx+30h]
0x1400040f1  lea     rax, [rbp+57h+var_60]
0x1400040f5  mov     [rbp+57h+var_60], rax
0x1400040f9  mov     rax, [rcx]
0x1400040fc  cmp     rax, rcx
0x1400040ff  jz      short loc_140004142
0x140004101  cmp     [rax+8], rcx
0x140004105  jnz     loc_1400042C8
0x14000410b  mov     rdx, [rax]
0x14000410e  cmp     [rdx+8], rax
0x140004112  jnz     loc_1400042C8
0x140004118  mov     [rcx], rdx
0x14000411b  mov     [rdx+8], rcx
0x14000411f  lea     rdx, [rbp+57h+var_60]
0x140004123  mov     rcx, [rbp+57h+var_58]
0x140004127  cmp     [rcx], rdx
0x14000412a  jnz     loc_1400042C8
0x140004130  mov     [rax+8], rcx
0x140004134  lea     rdx, [rbp+57h+var_60]
0x140004138  mov     [rax], rdx
0x14000413b  mov     [rcx], rax
0x14000413e  mov     [rbp+57h+var_58], rax
0x140004142  cmp     qword ptr [rbp+57h+var_90], 0
0x140004147  jz      short loc_14000415B
0x140004149  movaps  xmm0, [rbp+57h+var_90]
0x14000414d  lea     rcx, [rbp+57h+var_80]; struct SpinLockAndSavedIrql *
0x140004151  movdqa  [rbp+57h+var_80], xmm0
0x140004156  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x14000415b  mov     rdx, [rbp+57h+P]
0x14000415f  lea     rax, [rbp+57h+P]
0x140004163  cmp     rdx, rax
0x140004166  jz      short loc_1400041C4
0x140004168  mov     rax, cs:WdfFunctions_01015
0x14000416f  mov     rdx, [rdx+10h]
0x140004173  mov     rcx, cs:WdfDriverGlobals
0x14000417a  mov     rax, [rax+0BF0h]
0x140004181  call    _guard_dispatch_icall
0x140004186  mov     rcx, [rbp+57h+P]; P
0x14000418a  lea     rax, [rbp+57h+P]
0x14000418e  cmp     [rcx+8], rax
0x140004192  jnz     loc_1400042C8
0x140004198  mov     rax, [rcx]
0x14000419b  cmp     [rax+8], rcx
0x14000419f  jnz     loc_1400042C8
0x1400041a5  lea     rdx, [rbp+57h+P]
0x1400041a9  mov     [rbp+57h+P], rax
0x1400041ad  mov     [rax+8], rdx
0x1400041b1  mov     edx, 64667072h; Tag
0x1400041b6  call    cs:__imp_ExFreePoolWithTag
0x1400041bd  nop     dword ptr [rax+rax+00h]
0x1400041c2  jmp     short loc_14000415B
0x1400041c4  mov     rdi, [rbp+57h+var_60]
0x1400041c8  lea     rax, [rbp+57h+var_60]
0x1400041cc  cmp     rdi, rax
0x1400041cf  jz      loc_1400042CF
0x1400041d5  lea     rbx, [rdi+20h]
0x1400041d9  mov     rcx, [rbx]; P
0x1400041dc  cmp     rcx, rbx
0x1400041df  jz      short loc_140004206
0x1400041e1  cmp     [rcx+8], rbx
0x1400041e5  jnz     loc_1400042C8
0x1400041eb  mov     rax, [rcx]
0x1400041ee  cmp     [rax+8], rcx
0x1400041f2  jnz     loc_1400042C8
0x1400041f8  mov     [rbx], rax
0x1400041fb  mov     [rax+8], rbx
0x1400041ff  call    FreeConnectionContext
0x140004204  jmp     short loc_1400041D9
0x140004206  cmp     qword ptr [rdi+18h], 0
0x14000420b  jnz     short loc_140004212
0x14000420d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140004212  mov     rdx, [rdi+18h]; void *
0x140004216  test    rdx, rdx
0x140004219  jz      short loc_14000428F
0x14000421b  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140004222  mov     rcx, [rcx+20h]; this
0x140004226  call    ?Wrapper_WcmKReleaseInterface@RoutePolicyCallout@@YAKPEAX0@Z; RoutePolicyCallout::Wrapper_WcmKReleaseInterface(void *,void *)
0x14000422b  test    eax, eax
0x14000422d  jz      short loc_14000428F
0x14000422f  mov     ecx, cs:dword_140012050
0x140004235  cmp     ecx, 3
0x140004238  jbe     short loc_14000428F
0x14000423a  mov     rcx, [rdi+10h]
0x14000423e  lea     rdx, byte_14001013B; int
0x140004245  mov     [rbp+57h+var_A0], eax
0x140004248  xor     r9d, r9d; int
0x14000424b  lea     rax, [rbp+57h+var_90]
0x14000424f  mov     qword ptr [rbp+57h+var_90], rcx
0x140004253  mov     [rbp+57h+var_20], rax
0x140004257  lea     rcx, dword_140012050; int
0x14000425e  lea     rax, [rbp+57h+var_A0]
0x140004262  mov     [rbp+57h+var_18], 8
0x14000426a  mov     [rbp+57h+var_30], rax
0x14000426e  xor     r8d, r8d; int
0x140004271  lea     rax, [rbp+57h+var_50]
0x140004275  mov     [rbp+57h+var_28], 4
0x14000427d  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x140004282  mov     [rsp+0D0h+var_B0], 4; ULONG
0x14000428a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000428f  mov     rcx, [rbp+57h+var_60]; P
0x140004293  lea     rax, [rbp+57h+var_60]
0x140004297  cmp     [rcx+8], rax
0x14000429b  jnz     short loc_1400042C8
0x14000429d  mov     rax, [rcx]
0x1400042a0  cmp     [rax+8], rcx
0x1400042a4  jnz     short loc_1400042C8
0x1400042a6  lea     rdx, [rbp+57h+var_60]
0x1400042aa  mov     [rbp+57h+var_60], rax
0x1400042ae  mov     [rax+8], rdx
0x1400042b2  mov     edx, 64667072h; Tag
0x1400042b7  call    cs:__imp_ExFreePoolWithTag
0x1400042be  nop     dword ptr [rax+rax+00h]
0x1400042c3  jmp     loc_1400041C4
0x1400042c8  mov     ecx, 3
0x1400042cd  int     29h; Win8: RtlFailFast(ecx)
0x1400042cf  mov     rax, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x1400042d6  mov     rcx, [rax+20h]; void *
0x1400042da  test    rcx, rcx
0x1400042dd  jz      short loc_1400042E4
0x1400042df  call    ?WcmKCloseHandle@@YAXPEAX@Z; WcmKCloseHandle(void *)
0x1400042e4  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; P
0x1400042eb  mov     edx, 64667072h; Tag
0x1400042f0  call    cs:__imp_ExFreePoolWithTag
0x1400042f7  nop     dword ptr [rax+rax+00h]
0x1400042fc  mov     cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA, 0; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140004307  mov     rcx, [rbp+57h+var_10]
0x14000430b  xor     rcx, rsp; StackCookie
0x14000430e  call    __security_check_cookie
0x140004313  lea     r11, [rsp+0D0h+var_s0]
0x14000431b  mov     rbx, [r11+10h]
0x14000431f  mov     rdi, [r11+18h]
0x140004323  mov     rsp, r11
0x140004326  pop     rbp
0x140004327  retn
```
