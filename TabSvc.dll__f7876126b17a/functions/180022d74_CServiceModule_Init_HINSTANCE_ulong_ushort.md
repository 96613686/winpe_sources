# CServiceModule::Init(HINSTANCE__ *,ulong,ushort * *)

- ea: `0x180022d74`
- end: `0x180023243`
- name: `?Init@CServiceModule@@QEAAHPEAUHINSTANCE__@@KPEAPEAG@Z`
- size: `1231`
- prototype: `__int64 __fastcall(CServiceModule *this, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x180025ae0`

## callees

- `0x180001008`
- `0x180001c78`
- `0x1800021f8`
- `0x1800110e0`
- `0x180011ae0`
- `0x180015630`
- `0x18001bc20`
- `0x180022d74`
- `0x18002b3a8`
- `0x18002b4cc`
- `0x18002fb34`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180022eb0`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180022eb0`
- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x1800231d6`
- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x1800231d6`

## string_xrefs

- `0x180022dda`: `TextInputManagementService`
- `0x180022db2`: `PENSERVICE_CServiceModule::Init`
- `0x180022df4`: `PENSERVICE_CServiceModule::Init`
- `0x180023168`: `PENSERVICE_CServiceModule::Init`
- `0x180023212`: `PENSERVICE_CServiceModule::Init`

## pseudocode

```c
__int64 __fastcall CServiceModule::Init(
        CServiceModule *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 **a4)
{
  struct _GUID *v6; // rcx
  unsigned int v7; // edi
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // r9d
  char *v15; // rax
  char *v16; // rax
  char *v17; // rax
  char *v18; // rax
  char *v19; // rax
  char *v20; // rax
  __int64 i; // rbx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  const char *v26; // [rsp+68h] [rbp+10h] BYREF

  v26 = (const char *)a2;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      16,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::Init");
    v6 = WPP_GLOBAL_Control;
  }
  v7 = 1;
  if ( v6 != (struct _GUID *)&WPP_GLOBAL_Control && (v6[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sS(
      *(_QWORD *)&v6[1].Data1,
      17,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::Init",
      (__int64)L"TextInputManagementService");
  TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation(&dword_1800411A8);
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
  {
    v26 = (const char *)L"TextInputManagementService";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v11,
      (int)byte_18003A3F3,
      v9,
      v10,
      (const WCHAR **)&v26);
  }
  hRecipient = 0;
  *(_OWORD *)&TokenHandle = 0;
  byte_180041270 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(
                          (wil::details *)`wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl'::`2'::impl,
                          v8,
                          v9,
                          v10) )
    byte_180041271 = 0;
  qword_180041278 = 0;
  dword_180041280 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_KBBLS_55832275>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_KBBLS_55832275>::GetImpl'::`2'::impl) )
    RtlGetDeviceFamilyInfoEnum(0, &dword_1800414A0, 0);
  dword_180041240 = 16;
  dword_180041244 = 1;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_KBBLS_55832275>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_KBBLS_55832275>::GetImpl'::`2'::impl)
    || (dword_180041248 = 192, dword_1800414A0 != 3) )
  {
    dword_180041248 = 128;
  }
  qword_18004124C = 0;
  qword_180041254 = 0;
  WaitHandle = 0;
  qword_180041290 = 0;
  qword_1800412A8 = 0;
  qword_1800412B0 = 0;
  qword_1800412C0 = 0;
  hEvent = 0;
  dword_180041284 = 0;
  qword_1800412E8 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(
                          (wil::details *)`wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl'::`2'::impl,
                          v12,
                          v13,
                          v14) )
    qword_1800412D0 = 0;
  qword_1800412A0 = 0;
  qword_180041298 = 0;
  xmmword_180041460 = 0;
  xmmword_180041470 = 0;
  xmmword_180041480 = 0;
  v15 = (char *)operator new(0x228u, (const struct std::nothrow_t *)&std::nothrow);
  v26 = v15;
  if ( v15 )
  {
    *((_QWORD *)v15 + 1) = 0;
    *((_QWORD *)v15 + 68) = L"TabTip";
    *((_DWORD *)v15 + 4) = 1;
    *((_WORD *)v15 + 10) = 0;
    *(_QWORD *)v15 = &CTabTipProcessInfo::`vftable';
  }
  else
  {
    v15 = 0;
  }
  *(_QWORD *)&xmmword_180041460 = v15;
  v16 = (char *)operator new(0x228u, (const struct std::nothrow_t *)&std::nothrow);
  v26 = v16;
  if ( v16 )
  {
    *((_QWORD *)v16 + 1) = 1;
    *((_QWORD *)v16 + 68) = L"OobeTabtip";
    *((_DWORD *)v16 + 4) = 1;
    *((_WORD *)v16 + 10) = 0;
    *(_QWORD *)v16 = &COobeTabTipProcessInfo::`vftable';
  }
  else
  {
    v16 = 0;
  }
  *((_QWORD *)&xmmword_180041460 + 1) = v16;
  v17 = (char *)operator new(0x228u, (const struct std::nothrow_t *)&std::nothrow);
  v26 = v17;
  if ( v17 )
  {
    *((_QWORD *)v17 + 1) = 2;
    *((_QWORD *)v17 + 68) = L"SystemTabtip";
    *((_DWORD *)v17 + 4) = 1;
    *((_WORD *)v17 + 10) = 0;
    *(_QWORD *)v17 = &CSystemTabTipProcessInfo::`vftable';
  }
  else
  {
    v17 = 0;
  }
  *(_QWORD *)&xmmword_180041470 = v17;
  v18 = (char *)operator new(0x228u, (const struct std::nothrow_t *)&std::nothrow);
  v26 = v18;
  if ( v18 )
  {
    *((_QWORD *)v18 + 1) = 3;
    *((_QWORD *)v18 + 68) = L"Ctfmon";
    *((_DWORD *)v18 + 4) = 1;
    *((_WORD *)v18 + 10) = 0;
    *(_QWORD *)v18 = &CCtfmonProcessInfo::`vftable';
  }
  else
  {
    v18 = 0;
  }
  *((_QWORD *)&xmmword_180041470 + 1) = v18;
  v19 = (char *)operator new(0x228u, (const struct std::nothrow_t *)&std::nothrow);
  v26 = v19;
  if ( v19 )
  {
    *((_QWORD *)v19 + 1) = 4;
    *((_QWORD *)v19 + 68) = L"SystemCtfmon";
    *((_DWORD *)v19 + 4) = 1;
    *((_WORD *)v19 + 10) = 0;
    *(_QWORD *)v19 = &CSystemCtfmonProcessInfo::`vftable';
  }
  else
  {
    v19 = 0;
  }
  *(_QWORD *)&xmmword_180041480 = v19;
  v20 = (char *)operator new(0x228u, (const struct std::nothrow_t *)&std::nothrow);
  v26 = v20;
  if ( v20 )
  {
    *((_QWORD *)v20 + 1) = 5;
    *((_QWORD *)v20 + 68) = L"OobeCtfmon";
    *((_DWORD *)v20 + 4) = 1;
    *((_WORD *)v20 + 10) = 0;
    *(_QWORD *)v20 = &COobeCtfmonProcessInfo::`vftable';
  }
  else
  {
    v20 = 0;
  }
  *((_QWORD *)&xmmword_180041480 + 1) = v20;
  for ( i = 0; i != 6; ++i )
  {
    if ( !*((_QWORD *)&xmmword_180041460 + i) )
    {
      v7 = 0;
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
        WPP_SF_s(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          18,
          WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          "PENSERVICE_CServiceModule::Init");
      if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
      {
        v26 = "Failed to allocate ProcessInfo.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v22,
          (unsigned __int8 *)&unk_180039228,
          v23,
          v24,
          (const unsigned __int16 **)&v26);
      }
    }
  }
  InitializeSListHead(&ListHead);
  if ( a3 >= 2 && !wcscmp_0(a4[1], L"TriggerStarted") )
    LODWORD(qword_180041278) = 1;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      19,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::Init");
  return v7;
}

```

## disassembly

```asm
0x180022d74  mov     [rsp+arg_0], rbx
0x180022d79  mov     [rsp+arg_10], rbp
0x180022d7e  mov     [rsp+arg_8], rdx
0x180022d83  push    rsi
0x180022d84  push    rdi
0x180022d85  push    r12
0x180022d87  push    r14
0x180022d89  push    r15
0x180022d8b  sub     rsp, 30h
0x180022d8f  mov     rbp, r9
0x180022d92  mov     esi, r8d
0x180022d95  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d9c  lea     r14, WPP_GLOBAL_Control
0x180022da3  cmp     rcx, r14
0x180022da6  jz      short loc_180022DD1
0x180022da8  test    byte ptr [rcx+1Ch], 10h
0x180022dac  jz      short loc_180022DD1
0x180022dae  mov     rcx, [rcx+10h]
0x180022db2  lea     r9, aPenserviceCser_2; "PENSERVICE_CServiceModule::Init"
0x180022db9  mov     edx, 10h
0x180022dbe  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180022dc5  call    WPP_SF_s
0x180022dca  mov     rcx, cs:WPP_GLOBAL_Control
0x180022dd1  mov     r15d, 1
0x180022dd7  mov     edi, r15d
0x180022dda  lea     rbx, ServiceName; "TextInputManagementService"
0x180022de1  cmp     rcx, r14
0x180022de4  jz      short loc_180022E0C
0x180022de6  test    byte ptr [rcx+1Ch], 10h
0x180022dea  jz      short loc_180022E0C
0x180022dec  mov     rcx, [rcx+10h]
0x180022df0  lea     edx, [r15+10h]
0x180022df4  lea     r9, aPenserviceCser_2; "PENSERVICE_CServiceModule::Init"
0x180022dfb  mov     [rsp+58h+var_38], rbx
0x180022e00  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180022e07  call    WPP_SF_sS
0x180022e0c  lea     rcx, dword_1800411A8
0x180022e13  call    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation
0x180022e18  mov     eax, cs:dword_1800411A8
0x180022e1e  xor     r14d, r14d
0x180022e21  cmp     eax, 5
0x180022e24  jbe     short loc_180022E56
0x180022e26  mov     edx, 4000000h
0x180022e2b  lea     rcx, dword_1800411A8
0x180022e32  call    _tlgKeywordOn
0x180022e37  test    al, al
0x180022e39  jz      short loc_180022E56
0x180022e3b  lea     rax, [rsp+58h+arg_8]
0x180022e40  mov     [rsp+58h+arg_8], rbx
0x180022e45  lea     rdx, byte_18003A3F3
0x180022e4c  mov     [rsp+58h+var_38], rax
0x180022e51  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180022e56  xorps   xmm0, xmm0
0x180022e59  mov     cs:hRecipient, r14
0x180022e60  movdqa  cs:TokenHandle, xmm0
0x180022e68  mov     cs:byte_180041270, r14b
0x180022e6f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController> `wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl(void)'::`2'::impl
0x180022e76  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(void)
0x180022e7b  test    al, al
0x180022e7d  jz      short loc_180022E86
0x180022e7f  mov     cs:byte_180041271, r14b
0x180022e86  mov     cs:qword_180041278, r14
0x180022e8d  mov     cs:dword_180041280, r14d
0x180022e94  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_KBBLS_55832275@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_KBBLS_55832275@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KBBLS_55832275> `wil::Feature<__WilFeatureTraits_Feature_KBBLS_55832275>::GetImpl(void)'::`2'::impl
0x180022e9b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_KBBLS_55832275@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KBBLS_55832275>::__private_IsEnabled(void)
0x180022ea0  test    al, al
0x180022ea2  jz      short loc_180022EB6
0x180022ea4  xor     r8d, r8d
0x180022ea7  lea     rdx, dword_1800414A0
0x180022eae  xor     ecx, ecx
0x180022eb0  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180022eb6  mov     cs:dword_180041240, 10h
0x180022ec0  mov     cs:dword_180041244, r15d
0x180022ec7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_KBBLS_55832275@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_KBBLS_55832275@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KBBLS_55832275> `wil::Feature<__WilFeatureTraits_Feature_KBBLS_55832275>::GetImpl(void)'::`2'::impl
0x180022ece  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_KBBLS_55832275@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KBBLS_55832275>::__private_IsEnabled(void)
0x180022ed3  test    al, al
0x180022ed5  jz      short loc_180022EEA
0x180022ed7  cmp     cs:dword_1800414A0, 3
0x180022ede  mov     cs:dword_180041248, 0C0h
0x180022ee8  jz      short loc_180022EF4
0x180022eea  mov     cs:dword_180041248, 80h
0x180022ef4  mov     cs:qword_18004124C, r14
0x180022efb  mov     cs:qword_180041254, r14
0x180022f02  mov     cs:WaitHandle, r14
0x180022f09  mov     cs:qword_180041290, r14
0x180022f10  mov     cs:qword_1800412A8, r14
0x180022f17  mov     cs:qword_1800412B0, r14
0x180022f1e  mov     cs:qword_1800412C0, r14
0x180022f25  mov     cs:hEvent, r14
0x180022f2c  mov     cs:dword_180041284, r14d
0x180022f33  mov     cs:qword_1800412E8, r14
0x180022f3a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController> `wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl(void)'::`2'::impl
0x180022f41  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(void)
0x180022f46  test    al, al
0x180022f48  jz      short loc_180022F51
0x180022f4a  mov     cs:qword_1800412D0, r14
0x180022f51  xorps   xmm0, xmm0
0x180022f54  mov     cs:qword_1800412A0, r14
0x180022f5b  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180022f62  mov     cs:qword_180041298, r14
0x180022f69  mov     r12d, 228h
0x180022f6f  mov     rdx, rbx; struct std::nothrow_t *
0x180022f72  mov     ecx, r12d; unsigned __int64
0x180022f75  movups  cs:xmmword_180041460, xmm0
0x180022f7c  movups  cs:xmmword_180041470, xmm0
0x180022f83  movups  cs:xmmword_180041480, xmm0
0x180022f8a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180022f8f  mov     [rsp+58h+arg_8], rax
0x180022f94  test    rax, rax
0x180022f97  jz      short loc_180022FC0
0x180022f99  lea     rcx, aTabtip; "TabTip"
0x180022fa0  mov     [rax+8], r14
0x180022fa4  mov     [rax+220h], rcx
0x180022fab  lea     rcx, ??_7CTabTipProcessInfo@@6B@; const CTabTipProcessInfo::`vftable'
0x180022fb2  mov     [rax+10h], r15d
0x180022fb6  mov     [rax+14h], r14w
0x180022fbb  mov     [rax], rcx
0x180022fbe  jmp     short loc_180022FC3
0x180022fc0  mov     rax, r14
0x180022fc3  mov     rdx, rbx; struct std::nothrow_t *
0x180022fc6  mov     qword ptr cs:xmmword_180041460, rax
0x180022fcd  mov     rcx, r12; unsigned __int64
0x180022fd0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180022fd5  mov     [rsp+58h+arg_8], rax
0x180022fda  test    rax, rax
0x180022fdd  jz      short loc_180023006
0x180022fdf  lea     rcx, aOobetabtip; "OobeTabtip"
0x180022fe6  mov     [rax+8], rdi
0x180022fea  mov     [rax+220h], rcx
0x180022ff1  lea     rcx, ??_7COobeTabTipProcessInfo@@6B@; const COobeTabTipProcessInfo::`vftable'
0x180022ff8  mov     [rax+10h], r15d
0x180022ffc  mov     [rax+14h], r14w
0x180023001  mov     [rax], rcx
0x180023004  jmp     short loc_180023009
0x180023006  mov     rax, r14
0x180023009  mov     rdx, rbx; struct std::nothrow_t *
0x18002300c  mov     qword ptr cs:xmmword_180041460+8, rax
0x180023013  mov     rcx, r12; unsigned __int64
0x180023016  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002301b  mov     [rsp+58h+arg_8], rax
0x180023020  test    rax, rax
0x180023023  jz      short loc_180023050
0x180023025  lea     rcx, aSystemtabtip; "SystemTabtip"
0x18002302c  mov     qword ptr [rax+8], 2
0x180023034  mov     [rax+220h], rcx
0x18002303b  lea     rcx, ??_7CSystemTabTipProcessInfo@@6B@; const CSystemTabTipProcessInfo::`vftable'
0x180023042  mov     [rax+10h], r15d
0x180023046  mov     [rax+14h], r14w
0x18002304b  mov     [rax], rcx
0x18002304e  jmp     short loc_180023053
0x180023050  mov     rax, r14
0x180023053  mov     rdx, rbx; struct std::nothrow_t *
0x180023056  mov     qword ptr cs:xmmword_180041470, rax
0x18002305d  mov     rcx, r12; unsigned __int64
0x180023060  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180023065  mov     [rsp+58h+arg_8], rax
0x18002306a  test    rax, rax
0x18002306d  jz      short loc_18002309A
0x18002306f  lea     rcx, aCtfmon; "Ctfmon"
0x180023076  mov     qword ptr [rax+8], 3
0x18002307e  mov     [rax+220h], rcx
0x180023085  lea     rcx, ??_7CCtfmonProcessInfo@@6B@; const CCtfmonProcessInfo::`vftable'
0x18002308c  mov     [rax+10h], r15d
0x180023090  mov     [rax+14h], r14w
0x180023095  mov     [rax], rcx
0x180023098  jmp     short loc_18002309D
0x18002309a  mov     rax, r14
0x18002309d  mov     rdx, rbx; struct std::nothrow_t *
0x1800230a0  mov     qword ptr cs:xmmword_180041470+8, rax
0x1800230a7  mov     rcx, r12; unsigned __int64
0x1800230aa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800230af  mov     [rsp+58h+arg_8], rax
0x1800230b4  test    rax, rax
0x1800230b7  jz      short loc_1800230E4
0x1800230b9  lea     rcx, aSystemctfmon; "SystemCtfmon"
0x1800230c0  mov     qword ptr [rax+8], 4
0x1800230c8  mov     [rax+220h], rcx
0x1800230cf  lea     rcx, ??_7CSystemCtfmonProcessInfo@@6B@; const CSystemCtfmonProcessInfo::`vftable'
0x1800230d6  mov     [rax+10h], r15d
0x1800230da  mov     [rax+14h], r14w
0x1800230df  mov     [rax], rcx
0x1800230e2  jmp     short loc_1800230E7
0x1800230e4  mov     rax, r14
0x1800230e7  mov     rdx, rbx; struct std::nothrow_t *
0x1800230ea  mov     qword ptr cs:xmmword_180041480, rax
0x1800230f1  mov     rcx, r12; unsigned __int64
0x1800230f4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800230f9  mov     [rsp+58h+arg_8], rax
0x1800230fe  test    rax, rax
0x180023101  jz      short loc_18002312E
0x180023103  lea     rcx, aOobectfmon; "OobeCtfmon"
0x18002310a  mov     qword ptr [rax+8], 5
0x180023112  mov     [rax+220h], rcx
0x180023119  lea     rcx, ??_7COobeCtfmonProcessInfo@@6B@; const COobeCtfmonProcessInfo::`vftable'
0x180023120  mov     [rax+10h], r15d
0x180023124  mov     [rax+14h], r14w
0x180023129  mov     [rax], rcx
0x18002312c  jmp     short loc_180023131
0x18002312e  mov     rax, r14
0x180023131  mov     qword ptr cs:xmmword_180041480+8, rax
0x180023138  lea     r12, WPP_GLOBAL_Control
0x18002313f  mov     rbx, r14
0x180023142  lea     rax, xmmword_180041460
0x180023149  cmp     [rax+rbx*8], r14
0x18002314d  jnz     short loc_1800231C2
0x18002314f  mov     edi, r14d
0x180023152  mov     rcx, cs:WPP_GLOBAL_Control
0x180023159  cmp     rcx, r12
0x18002315c  jz      short loc_180023180
0x18002315e  test    byte ptr [rcx+1Ch], 4
0x180023162  jz      short loc_180023180
0x180023164  mov     rcx, [rcx+10h]
0x180023168  lea     r9, aPenserviceCser_2; "PENSERVICE_CServiceModule::Init"
0x18002316f  mov     edx, 12h
0x180023174  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18002317b  call    WPP_SF_s
0x180023180  mov     eax, cs:dword_1800411A8
0x180023186  cmp     eax, 5
0x180023189  jbe     short loc_1800231C2
0x18002318b  mov     edx, 4000000h
0x180023190  lea     rcx, dword_1800411A8
0x180023197  call    _tlgKeywordOn
0x18002319c  test    al, al
0x18002319e  jz      short loc_1800231C2
0x1800231a0  lea     rax, aFailedToAlloca; "Failed to allocate ProcessInfo."
0x1800231a7  mov     [rsp+58h+arg_8], rax
0x1800231ac  lea     rdx, unk_180039228
0x1800231b3  lea     rax, [rsp+58h+arg_8]
0x1800231b8  mov     [rsp+58h+var_38], rax
0x1800231bd  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800231c2  add     rbx, r15
0x1800231c5  cmp     rbx, 6
0x1800231c9  jnz     loc_180023142
0x1800231cf  lea     rcx, ListHead; ListHead
0x1800231d6  call    cs:__imp_InitializeSListHead
0x1800231dc  cmp     esi, 2
0x1800231df  jb      short loc_1800231FC
0x1800231e1  mov     rcx, [rbp+8]; String1
0x1800231e5  lea     rdx, aTriggerstarted; "TriggerStarted"
0x1800231ec  call    wcscmp_0
0x1800231f1  test    eax, eax
0x1800231f3  jnz     short loc_1800231FC
0x1800231f5  mov     dword ptr cs:qword_180041278, r15d
0x1800231fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180023203  cmp     rcx, r12
0x180023206  jz      short loc_18002322A
0x180023208  test    byte ptr [rcx+1Ch], 10h
0x18002320c  jz      short loc_18002322A
0x18002320e  mov     rcx, [rcx+10h]
0x180023212  lea     r9, aPenserviceCser_2; "PENSERVICE_CServiceModule::Init"
0x180023219  mov     edx, 13h
0x18002321e  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180023225  call    WPP_SF_s
0x18002322a  mov     rbx, [rsp+58h+arg_0]
0x18002322f  mov     eax, edi
0x180023231  mov     rbp, [rsp+58h+arg_10]
0x180023236  add     rsp, 30h
0x18002323a  pop     r15
0x18002323c  pop     r14
0x18002323e  pop     r12
0x180023240  pop     rdi
0x180023241  pop     rsi
0x180023242  retn
```
