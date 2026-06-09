# CRdpIdAdapter::UpdateAllMonitors(std::vector<std::shared_ptr<CMonitorConfig>,std::allocator<std::shared_ptr<CMonitorConfig>>> const &)

- ea: `0x18001de94`
- end: `0x18001e27b`
- name: `?UpdateAllMonitors@CRdpIdAdapter@@AEAAXAEBV?$vector@V?$shared_ptr@VCMonitorConfig@@@std@@V?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@2@@std@@@Z`
- size: `999`
- prototype: `__int64 __fastcall(CRdpIdAdapter *this)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a860`
- `0x18001adec`

## callees

- `0x180001af0`
- `0x18000402c`
- `0x1800089f0`
- `0x18000cb5c`
- `0x18000d614`
- `0x18000e190`
- `0x18001072c`
- `0x180013bb0`
- `0x18001534c`
- `0x180017674`
- `0x18001d5f0`
- `0x18001ddbc`
- `0x18001ddf4`
- `0x18001de94`
- `0x18001e634`
- `0x18001f2a0`
- `0x180021058`
- `0x180021570`
- `0x18003f010`

## string_xrefs

- `0x18001df8d`: `AdapterUpdateMonitors: %d`
- `0x18001e110`: `Failed to commit monitors`
- `0x18001df7b`: `CRdpIdAdapter::UpdateAllMonitors`
- `0x18001e1a2`: `CRdpIdAdapter::UpdateAllMonitors`

## pseudocode

```c
__int64 __fastcall CRdpIdAdapter::UpdateAllMonitors(CRdpIdAdapter *this, __int64 a2)
{
  _DWORD *v4; // r8
  int v5; // r8d
  int v6; // r9d
  const struct RDP_MONITORCONFIG_MONITOR_ID **v7; // rsi
  _QWORD *v8; // rdi
  _QWORD *v9; // r14
  __int64 *v10; // rax
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  std::_Ref_count_base *v15; // rcx
  const struct RDP_MONITORCONFIG_MONITOR_ID *v16; // rax
  LONG v17; // r9d
  LONG v18; // r10d
  const struct RDP_MONITORCONFIG_MONITOR_ID *v19; // rax
  LONG v20; // r11d
  LONG v21; // edi
  _DWORD *v22; // r8
  LONG v23; // ecx
  LONG v24; // edx
  LONG v25; // ecx
  LONG v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  __int64 **v30; // rdx
  unsigned int v31; // eax
  CMonitorConfig *v33; // rax
  const struct RDP_MONITORCONFIG_MONITOR_ID *MonitorId; // r13
  int v35; // ebx
  int v36; // edi
  int v37; // esi
  int v38; // r14d
  int v39; // r15d
  Rdp::Modern::Utils::CInflightRecorder *Ifr; // rax
  int v41; // edx
  int v42; // r8d
  int v43; // r9d
  int v44; // r10d
  int v45; // r11d
  int v46; // ebx
  int v47; // edi
  int v48; // esi
  int v49; // r14d
  int v50; // r15d
  int v51; // r12d
  unsigned int v52; // eax
  int v53; // edx
  int v54; // r10d
  int v55; // r11d
  char *v56; // [rsp+28h] [rbp-61h]
  char *v57; // [rsp+28h] [rbp-61h]
  __int64 v58; // [rsp+30h] [rbp-59h]
  __int64 v59; // [rsp+30h] [rbp-59h]
  __int64 v60; // [rsp+38h] [rbp-51h]
  __int64 v61; // [rsp+38h] [rbp-51h]
  __int64 v62; // [rsp+40h] [rbp-49h]
  __int64 v63; // [rsp+40h] [rbp-49h]
  __int64 v64; // [rsp+48h] [rbp-41h]
  __int64 v65; // [rsp+48h] [rbp-41h]
  int v66; // [rsp+50h] [rbp-39h]
  __int64 v67; // [rsp+50h] [rbp-39h]
  int v68; // [rsp+58h] [rbp-31h]
  __int64 v69; // [rsp+58h] [rbp-31h]
  int v70; // [rsp+60h] [rbp-29h]
  __int64 v71; // [rsp+60h] [rbp-29h]
  int v72; // [rsp+68h] [rbp-21h]
  __int64 v73; // [rsp+68h] [rbp-21h]
  int v74; // [rsp+70h] [rbp-19h]
  __int64 v75; // [rsp+70h] [rbp-19h]
  int v76; // [rsp+78h] [rbp-11h]
  __int64 v77; // [rsp+78h] [rbp-11h]
  __int64 v78; // [rsp+80h] [rbp-9h] BYREF
  tagRECT v79; // [rsp+88h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  const struct RDP_MONITORCONFIG_MONITOR_ID *v81; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v82; // [rsp+F8h] [rbp+6Fh] BYREF
  GUID *v83; // [rsp+100h] [rbp+77h] BYREF
  const char *v84; // [rsp+108h] [rbp+7Fh] BYREF

  v4 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v4 > 4u && (unsigned __int8)tlgKeywordOn(v4, 0x470000000000LL) )
  {
    v82 = *((_QWORD *)this + 21);
    LODWORD(v81) = *((_DWORD *)this + 129);
    v83 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
    v84 = "RdpIdd";
    *(_QWORD *)&v79.left = "Checkpoint";
    v78 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v5,
      (unsigned int)word_18004D93A,
      v5,
      v6,
      (__int64)&v79,
      (__int64)&v78,
      (__int64)&v84,
      (__int64)&v83,
      (__int64)&v81,
      (__int64)&v82);
  }
  v7 = (const struct RDP_MONITORCONFIG_MONITOR_ID **)((char *)this + 160);
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"AdapterUpdateMonitors: %d",
    "CRdpIdAdapter::UpdateAllMonitors",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    0x4B2u,
    *((_QWORD *)this + 21));
  v8 = *(_QWORD **)a2;
  v9 = *(_QWORD **)(a2 + 8);
  while ( v8 != v9 )
  {
    std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::find(
      (char *)this + 160,
      &v81,
      *v8 + 36LL);
    if ( v81 == *v7 )
    {
      v33 = (CMonitorConfig *)std::shared_ptr<CRdpIdMonitor>::operator-><CRdpIdMonitor,0>(v8);
      MonitorId = CMonitorConfig::GetMonitorId(v33);
      v81 = MonitorId;
      v35 = *((unsigned __int8 *)MonitorId + 10);
      v36 = *((unsigned __int8 *)MonitorId + 9);
      v37 = *((unsigned __int8 *)MonitorId + 8);
      v38 = *((unsigned __int16 *)MonitorId + 3);
      v39 = *((unsigned __int16 *)MonitorId + 2);
      Ifr = Rdp::Modern::Utils::CInflightRecorder::GetIfr();
      v76 = v41;
      v74 = v42;
      v72 = v43;
      v70 = v44;
      v68 = v45;
      v66 = v35;
      LODWORD(v64) = v36;
      LODWORD(v62) = v37;
      LODWORD(v60) = v38;
      LODWORD(v58) = v39;
      LODWORD(v56) = *(_DWORD *)MonitorId;
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        Ifr,
        (wchar_t *)L"Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX} is not found",
        "CRdpIdAdapter::UpdateAllMonitors",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x4C5u,
        v56,
        v58,
        v60,
        v62,
        v64,
        v66,
        v68,
        v70,
        v72,
        v74,
        v76);
      v46 = *((unsigned __int8 *)MonitorId + 12);
      v47 = *((unsigned __int8 *)MonitorId + 11);
      v48 = *((unsigned __int8 *)MonitorId + 10);
      v49 = *((unsigned __int8 *)MonitorId + 9);
      v50 = *((unsigned __int8 *)MonitorId + 8);
      v51 = *((unsigned __int16 *)MonitorId + 3);
      LODWORD(MonitorId) = *((unsigned __int16 *)MonitorId + 2);
      v52 = wil::verify_hresult<long>(2147943568LL);
      LODWORD(v77) = v53;
      LODWORD(v75) = v54;
      LODWORD(v73) = v55;
      LODWORD(v71) = v46;
      LODWORD(v69) = v47;
      LODWORD(v67) = v48;
      LODWORD(v65) = v49;
      LODWORD(v63) = v50;
      LODWORD(v61) = v51;
      LODWORD(v59) = (_DWORD)MonitorId;
      LODWORD(v57) = *(_DWORD *)v81;
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x4CC,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        (const char *)v52,
        (int)"Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX} is not found",
        v57,
        v59,
        v61,
        v63,
        v65,
        v67,
        v69,
        v71,
        v73,
        v75,
        v77);
    }
    v10 = (__int64 *)std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(&v79, v8);
    v12 = *v10;
    *v10 = *(_QWORD *)(v11 + 208);
    v13 = *(_QWORD *)(v11 + 216);
    *(_QWORD *)(v11 + 208) = v12;
    v14 = v10[1];
    v10[1] = v13;
    v15 = *(std::_Ref_count_base **)&v79.right;
    *(_QWORD *)(v11 + 216) = v14;
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    v8 += 2;
  }
  v16 = *v7;
  v79 = 0;
  v17 = 0;
  v18 = 0;
  v19 = *(const struct RDP_MONITORCONFIG_MONITOR_ID **)v16;
  v20 = 0;
  v21 = 0;
  v81 = v19;
  while ( !*((_BYTE *)v19 + 25) )
  {
    v22 = *(_DWORD **)(*((_QWORD *)v19 + 6) + 208LL);
    v23 = v22[22];
    v24 = v22[23];
    if ( v21 >= v23 )
      v21 = v22[22];
    v79.left = v21;
    if ( v20 >= v24 )
      v20 = v24;
    v25 = v22[24] + v23;
    v79.top = v20;
    if ( v18 <= v25 )
      v18 = v25;
    v26 = v24 + v22[25];
    v79.right = v18;
    if ( v17 <= v26 )
      v17 = v26;
    v27 = v22[31];
    v79.bottom = v17;
    v28 = v27 - 1;
    if ( v28 )
    {
      if ( (unsigned int)(v28 - 1) > 1 )
        goto LABEL_27;
      v29 = v22[7];
      if ( (v29 & 0x10) != 0 )
        v22[6] |= 8u;
      if ( (v29 & 0x20) != 0 )
        v22[6] |= 0x10u;
    }
    v22[6] |= 1u;
LABEL_27:
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>,std::_Iterator_base0>::operator++(&v81);
    v19 = v81;
  }
  CRdpIdAdapter::SetVirtualDesktopInfo(this, &v79);
  v30 = (__int64 **)((char *)this + 160);
  if ( *((_DWORD *)this + 110) == 3 )
    CRdpIdAdapter::UpdateDisplayConfigContainer((__int64)this, v30);
  else
    CRdpIdAdapter::UpdateDisplayConfigNative((__int64)this, v30);
  v31 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 70) + 64LL))(*((_QWORD *)this + 70));
  return wil::details::in1diag3::Throw_IfFailedMsg(
           retaddr,
           (void *)0x4F7,
           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
           (const char *)v31,
           (int)"Failed to commit monitors",
           v56);
}

```

## disassembly

```asm
0x18001de94  push    rbp
0x18001de96  push    rbx
0x18001de97  push    rsi
0x18001de98  push    rdi
0x18001de99  push    r12
0x18001de9b  push    r13
0x18001de9d  push    r14
0x18001de9f  push    r15
0x18001dea1  lea     rbp, [rsp-1Fh]
0x18001dea6  sub     rsp, 0A8h
0x18001dead  mov     r14, rdx
0x18001deb0  mov     rbx, rcx
0x18001deb3  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001deb8  mov     r8, [rax+8]
0x18001debc  mov     eax, [r8]
0x18001debf  cmp     eax, 4
0x18001dec2  jbe     loc_18001DF64
0x18001dec8  mov     rdx, 470000000000h
0x18001ded2  mov     rcx, r8
0x18001ded5  call    _tlgKeywordOn
0x18001deda  test    al, al
0x18001dedc  jz      loc_18001DF64
0x18001dee2  mov     rax, [rbx+0A8h]
0x18001dee9  lea     rdx, word_18004D93A
0x18001def0  mov     [rbp+57h+arg_8], rax
0x18001def4  mov     rcx, r8
0x18001def7  mov     eax, [rbx+204h]
0x18001defd  mov     dword ptr [rbp+57h+arg_0], eax
0x18001df00  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x18001df07  mov     [rbp+57h+arg_10], rax
0x18001df0b  lea     rax, aRdpidd; "RdpIdd"
0x18001df12  mov     [rbp+57h+arg_18], rax
0x18001df16  lea     rax, aCheckpoint; "Checkpoint"
0x18001df1d  mov     qword ptr [rbp+57h+var_58.left], rax
0x18001df21  lea     rax, [rbp+57h+arg_8]
0x18001df25  mov     [rsp+0E0h+var_98], rax
0x18001df2a  lea     rax, [rbp+57h+arg_0]
0x18001df2e  mov     [rsp+0E0h+var_A0], rax
0x18001df33  lea     rax, [rbp+57h+arg_10]
0x18001df37  mov     [rsp+0E0h+var_A8], rax
0x18001df3c  lea     rax, [rbp+57h+arg_18]
0x18001df40  mov     [rsp+0E0h+var_B0], rax
0x18001df45  lea     rax, [rbp+57h+var_60]
0x18001df49  mov     [rsp+0E0h+var_B8], rax
0x18001df4e  lea     rax, [rbp+57h+var_58]
0x18001df52  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18001df57  mov     [rbp+57h+var_60], 1000000h
0x18001df5f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001df64  lea     rsi, [rbx+0A0h]
0x18001df6b  mov     rax, [rsi+8]
0x18001df6f  lea     r12, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001df76  mov     [rsp+0E0h+var_B8], rax
0x18001df7b  lea     r8, aCrdpidadapterU_3; "CRdpIdAdapter::UpdateAllMonitors"
0x18001df82  mov     r9, r12; char *
0x18001df85  mov     [rsp+0E0h+var_C0], 4B2h; unsigned int
0x18001df8d  lea     rdx, aAdapterupdatem; "AdapterUpdateMonitors: %d"
0x18001df94  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001df9b  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001dfa0  mov     rdi, [r14]
0x18001dfa3  mov     r14, [r14+8]
0x18001dfa7  jmp     short loc_18001E015
0x18001dfa9  mov     r8, [rdi]
0x18001dfac  lea     rdx, [rbp+57h+arg_0]
0x18001dfb0  add     r8, 24h ; '$'
0x18001dfb4  mov     rcx, rsi
0x18001dfb7  call    ?find@?$_Tree@V?$_Tmap_traits@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@@2@AEBURDP_MONITORCONFIG_MONITOR_ID@@@Z; std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::find(RDP_MONITORCONFIG_MONITOR_ID const &)
0x18001dfbc  mov     rax, [rbp+57h+arg_0]
0x18001dfc0  cmp     rax, [rsi]
0x18001dfc3  jz      loc_18001E141
0x18001dfc9  mov     r8, [rax+30h]
0x18001dfcd  lea     rcx, [rbp+57h+var_58]
0x18001dfd1  mov     rdx, rdi
0x18001dfd4  call    ??0?$shared_ptr@VCRdpIdAdapter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(std::shared_ptr<CRdpIdAdapter> const &)
0x18001dfd9  mov     rcx, [r8+0D0h]
0x18001dfe0  mov     rdx, [rax]
0x18001dfe3  mov     [rax], rcx
0x18001dfe6  mov     rcx, [r8+0D8h]
0x18001dfed  mov     [r8+0D0h], rdx
0x18001dff4  mov     rdx, [rax+8]
0x18001dff8  mov     [rax+8], rcx
0x18001dffc  mov     rcx, qword ptr [rbp+57h+var_58.right]; this
0x18001e000  mov     [r8+0D8h], rdx
0x18001e007  test    rcx, rcx
0x18001e00a  jz      short loc_18001E011
0x18001e00c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e011  add     rdi, 10h
0x18001e015  cmp     rdi, r14
0x18001e018  jnz     short loc_18001DFA9
0x18001e01a  mov     rax, [rsi]
0x18001e01d  xorps   xmm0, xmm0
0x18001e020  movups  xmmword ptr [rbp+57h+var_58.left], xmm0
0x18001e024  mov     r9d, [rbp+57h+var_58.bottom]
0x18001e028  mov     r10d, [rbp+57h+var_58.right]
0x18001e02c  mov     rax, [rax]
0x18001e02f  mov     r11d, [rbp+57h+var_58.top]
0x18001e033  mov     edi, [rbp+57h+var_58.left]
0x18001e036  mov     [rbp+57h+arg_0], rax
0x18001e03a  cmp     byte ptr [rax+19h], 0
0x18001e03e  jnz     loc_18001E0D2
0x18001e044  mov     rcx, [rax+30h]
0x18001e048  mov     r8, [rcx+0D0h]
0x18001e04f  mov     ecx, [r8+58h]
0x18001e053  cmp     edi, ecx
0x18001e055  mov     edx, [r8+5Ch]
0x18001e059  cmovge  edi, ecx
0x18001e05c  cmp     r11d, edx
0x18001e05f  mov     [rbp+57h+var_58.left], edi
0x18001e062  cmovge  r11d, edx
0x18001e066  add     ecx, [r8+60h]
0x18001e06a  cmp     r10d, ecx
0x18001e06d  mov     [rbp+57h+var_58.top], r11d
0x18001e071  cmovle  r10d, ecx
0x18001e075  mov     ecx, [r8+64h]
0x18001e079  add     ecx, edx
0x18001e07b  mov     [rbp+57h+var_58.right], r10d
0x18001e07f  cmp     r9d, ecx
0x18001e082  cmovle  r9d, ecx
0x18001e086  mov     ecx, [r8+7Ch]
0x18001e08a  mov     [rbp+57h+var_58.bottom], r9d
0x18001e08e  sub     ecx, 1
0x18001e091  jz      short loc_18001E0BB
0x18001e093  sub     ecx, 1
0x18001e096  jz      short loc_18001E09D
0x18001e098  cmp     ecx, 1
0x18001e09b  jnz     short loc_18001E0C0
0x18001e09d  mov     ecx, [r8+1Ch]
0x18001e0a1  test    cl, 10h
0x18001e0a4  jz      short loc_18001E0AB
0x18001e0a6  or      dword ptr [r8+18h], 8
0x18001e0ab  mov     eax, [r8+18h]
0x18001e0af  test    cl, 20h
0x18001e0b2  jz      short loc_18001E0BB
0x18001e0b4  or      eax, 10h
0x18001e0b7  mov     [r8+18h], eax
0x18001e0bb  or      dword ptr [r8+18h], 1
0x18001e0c0  lea     rcx, [rbp+57h+arg_0]
0x18001e0c4  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>,std::_Iterator_base0>::operator++(void)
0x18001e0c9  mov     rax, [rbp+57h+arg_0]
0x18001e0cd  jmp     loc_18001E03A
0x18001e0d2  lea     rdx, [rbp+57h+var_58]; struct tagRECT *
0x18001e0d6  mov     rcx, rbx; this
0x18001e0d9  call    ?SetVirtualDesktopInfo@CRdpIdAdapter@@AEAAXAEBUtagRECT@@@Z; CRdpIdAdapter::SetVirtualDesktopInfo(tagRECT const &)
0x18001e0de  cmp     dword ptr [rbx+1B8h], 3
0x18001e0e5  mov     rdx, rsi
0x18001e0e8  mov     rcx, rbx
0x18001e0eb  jnz     short loc_18001E0F4
0x18001e0ed  call    ?UpdateDisplayConfigContainer@CRdpIdAdapter@@AEAAXAEBV?$map@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@@std@@@Z; CRdpIdAdapter::UpdateDisplayConfigContainer(std::map<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>> const &)
0x18001e0f2  jmp     short loc_18001E0F9
0x18001e0f4  call    ?UpdateDisplayConfigNative@CRdpIdAdapter@@AEAAXAEBV?$map@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@@std@@@Z; CRdpIdAdapter::UpdateDisplayConfigNative(std::map<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>> const &)
0x18001e0f9  mov     rcx, [rbx+230h]
0x18001e100  mov     rax, [rcx]
0x18001e103  mov     rax, [rax+40h]
0x18001e107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e10c  mov     rcx, [rbp+5Fh]; this
0x18001e110  lea     rdx, aFailedToCommit; "Failed to commit monitors"
0x18001e117  mov     qword ptr [rsp+0E0h+var_C0], rdx; int
0x18001e11c  mov     r9d, eax; char *
0x18001e11f  mov     edx, 4F7h; void *
0x18001e124  mov     r8, r12; unsigned int
0x18001e127  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001e12c  add     rsp, 0A8h
0x18001e133  pop     r15
0x18001e135  pop     r14
0x18001e137  pop     r13
0x18001e139  pop     r12
0x18001e13b  pop     rdi
0x18001e13c  pop     rsi
0x18001e13d  pop     rbx
0x18001e13e  pop     rbp
0x18001e13f  retn
0x18001e141  mov     rcx, rdi
0x18001e144  call    ??$?CVCRdpIdMonitor@@$0A@@?$shared_ptr@VCRdpIdMonitor@@@std@@QEBAPEAVCRdpIdMonitor@@XZ; std::shared_ptr<CRdpIdMonitor>::operator-><CRdpIdMonitor,0>(void)
0x18001e149  mov     rcx, rax; this
0x18001e14c  call    ?GetMonitorId@CMonitorConfig@@QEBAAEBURDP_MONITORCONFIG_MONITOR_ID@@XZ; CMonitorConfig::GetMonitorId(void)
0x18001e151  mov     r13, rax
0x18001e154  mov     [rbp+57h+arg_0], rax
0x18001e158  movzx   edx, byte ptr [rax+0Fh]
0x18001e15c  movzx   r8d, byte ptr [rax+0Eh]
0x18001e161  movzx   r9d, byte ptr [rax+0Dh]
0x18001e166  movzx   r10d, byte ptr [rax+0Ch]
0x18001e16b  movzx   r11d, byte ptr [rax+0Bh]
0x18001e170  movzx   ebx, byte ptr [rax+0Ah]
0x18001e174  movzx   edi, byte ptr [rax+9]
0x18001e178  movzx   esi, byte ptr [rax+8]
0x18001e17c  movzx   r14d, word ptr [rax+6]
0x18001e181  movzx   r15d, word ptr [rax+4]
0x18001e186  call    ?GetIfr@CInflightRecorder@Utils@Modern@Rdp@@SAAEAV1234@XZ; Rdp::Modern::Utils::CInflightRecorder::GetIfr(void)
0x18001e18b  mov     dword ptr [rsp+0E0h+var_68], edx
0x18001e18f  mov     rcx, rax; this
0x18001e192  mov     eax, [r13+0]
0x18001e196  lea     rdx, aMonitor08lx04h; "Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX"...
0x18001e19d  mov     dword ptr [rsp+0E0h+var_70], r8d
0x18001e1a2  lea     r8, aCrdpidadapterU_3; "CRdpIdAdapter::UpdateAllMonitors"
0x18001e1a9  mov     dword ptr [rsp+0E0h+var_78], r9d
0x18001e1ae  mov     r9, r12; char *
0x18001e1b1  mov     dword ptr [rsp+0E0h+var_80], r10d
0x18001e1b6  mov     dword ptr [rsp+0E0h+var_88], r11d
0x18001e1bb  mov     dword ptr [rsp+0E0h+var_90], ebx
0x18001e1bf  mov     dword ptr [rsp+0E0h+var_98], edi
0x18001e1c3  mov     dword ptr [rsp+0E0h+var_A0], esi
0x18001e1c7  mov     dword ptr [rsp+0E0h+var_A8], r14d
0x18001e1cc  mov     dword ptr [rsp+0E0h+var_B0], r15d
0x18001e1d1  mov     dword ptr [rsp+0E0h+var_B8], eax
0x18001e1d5  mov     [rsp+0E0h+var_C0], 4C5h; unsigned int
0x18001e1dd  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001e1e2  movzx   edx, byte ptr [r13+0Fh]
0x18001e1e7  mov     ecx, 80070490h
0x18001e1ec  movzx   r10d, byte ptr [r13+0Eh]
0x18001e1f1  movzx   r11d, byte ptr [r13+0Dh]
0x18001e1f6  movzx   ebx, byte ptr [r13+0Ch]
0x18001e1fb  movzx   edi, byte ptr [r13+0Bh]
0x18001e200  movzx   esi, byte ptr [r13+0Ah]
0x18001e205  movzx   r14d, byte ptr [r13+9]
0x18001e20a  movzx   r15d, byte ptr [r13+8]
0x18001e20f  movzx   r12d, word ptr [r13+6]
0x18001e214  movzx   r13d, word ptr [r13+4]
0x18001e219  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001e21e  mov     rcx, [rbp+5Fh]; this
0x18001e222  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001e229  mov     dword ptr [rsp+0E0h+var_68], edx
0x18001e22d  mov     r9d, eax; char *
0x18001e230  mov     rax, [rbp+57h+arg_0]
0x18001e234  mov     edx, 4CCh; void *
0x18001e239  mov     dword ptr [rsp+0E0h+var_70], r10d
0x18001e23e  mov     dword ptr [rsp+0E0h+var_78], r11d
0x18001e243  mov     dword ptr [rsp+0E0h+var_80], ebx
0x18001e247  mov     eax, [rax]
0x18001e249  mov     dword ptr [rsp+0E0h+var_88], edi
0x18001e24d  mov     dword ptr [rsp+0E0h+var_90], esi
0x18001e251  mov     dword ptr [rsp+0E0h+var_98], r14d
0x18001e256  mov     dword ptr [rsp+0E0h+var_A0], r15d
0x18001e25b  mov     dword ptr [rsp+0E0h+var_A8], r12d
0x18001e260  mov     dword ptr [rsp+0E0h+var_B0], r13d
0x18001e265  mov     dword ptr [rsp+0E0h+var_B8], eax; char *
0x18001e269  lea     rax, aMonitor08lx04h_0; "Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX"...
0x18001e270  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18001e275  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
