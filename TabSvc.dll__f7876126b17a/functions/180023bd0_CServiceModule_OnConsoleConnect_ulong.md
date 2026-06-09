# CServiceModule::OnConsoleConnect(ulong)

- ea: `0x180023bd0`
- end: `0x180023e28`
- name: `?OnConsoleConnect@CServiceModule@@QEAAXK@Z`
- size: `600`
- prototype: `void __fastcall(struct _GUID *Context, DWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x18000fa00`

## callees

- `0x180001ec0`
- `0x1800110e0`
- `0x180012060`
- `0x180013b64`
- `0x18001506c`
- `0x180015630`
- `0x18001a760`
- `0x18001ff9c`
- `0x180023bd0`
- `0x1800286b0`
- `0x180028964`
- `0x18002b3a8`
- `0x18002b404`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d91`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180023d08`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180023d08`
- `WTSAPI32!WTSFreeMemory` at `0x180023d31`
- `WTSAPI32!WTSFreeMemory` at `0x180023e04`
- `WTSAPI32!WTSFreeMemory` at `0x180023d31`
- `WTSAPI32!WTSFreeMemory` at `0x180023e04`

## string_xrefs

- `0x180023e16`: `drivers\tablet\platform\pen\penservice\penservice.cpp`
- `0x180023bff`: `PENSERVICE_CServiceModule::OnConsoleConnect`
- `0x180023d65`: `PENSERVICE_CServiceModule::OnConsoleConnect`
- `0x180023d9e`: `PENSERVICE_CServiceModule::OnConsoleConnect`
- `0x180023de2`: `PENSERVICE_CServiceModule::OnConsoleConnect`

## pseudocode

```c
void __fastcall CServiceModule::OnConsoleConnect(struct _GUID *Context, DWORD a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // r9d
  int Data1_low; // edx
  unsigned int v11; // eax
  struct _GUID *v12; // r8
  unsigned int v13; // r9d
  LPWSTR v14; // rcx
  unsigned int v15; // ebx
  char LastError; // al
  DWORD *pBytesReturned; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD v19; // [rsp+60h] [rbp+8h] BYREF
  LPWSTR ppBuffer; // [rsp+70h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      106,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::OnConsoleConnect");
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
  {
    v19 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v4,
      (int)&byte_18003A21F,
      v5,
      v6,
      (__int64)&v19);
  }
  if ( *(_DWORD *)&Context[4].Data2 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::GetImpl'::`2'::impl) )
    {
      CServiceModule::_StopOobeProcesses(Context, a2, v8, v9);
    }
    else
    {
      *(_DWORD *)&Context[4].Data2 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(
                              (wil::details *)`wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl'::`2'::impl,
                              v7,
                              v8,
                              v9) )
        Data1_low = LOBYTE(Context[4].Data1) || BYTE1(Context[4].Data1);
      else
        Data1_low = LOBYTE(Context[4].Data1);
      v11 = CServiceModule::_EnableDisablePenProcessTypes(Context, Data1_low);
      CServiceModule::_CheckLicense((CServiceModule *)Context, v11, v12, v13);
      CServiceModule::_RemovePenProcessesWorker((CServiceModule *)Context, 1, 0x18u, a2);
    }
  }
  CServiceModule::_RemovePenProcessesWorker((CServiceModule *)Context, 2, 0, a2);
  ppBuffer = 0;
  v19 = 0;
  if ( WTSQuerySessionInformationW(0, a2, WTSConnectState, &ppBuffer, &v19) )
  {
    v14 = ppBuffer;
    if ( v19 != 4 || !ppBuffer )
    {
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
      {
        WPP_SF_sd(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          107,
          (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          (unsigned int)"PENSERVICE_CServiceModule::OnConsoleConnect",
          v19);
        v14 = ppBuffer;
      }
      WTSFreeMemory(v14);
      wil::details::in1diag3::FailFast_UnexpectedMsg(
        retaddr,
        (void *)0x919,
        (unsigned int)"drivers\\tablet\\platform\\pen\\penservice\\penservice.cpp",
        "unexpected return from WTSQuerySessionInformation",
        (const char *)pBytesReturned);
    }
    v15 = *(_DWORD *)ppBuffer;
    WTSFreeMemory(ppBuffer);
    CServiceModule::_StartPenProcessesWorker(Context, a2, v15, 0, (int)pBytesReturned, 0);
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
      WPP_SF_s(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        109,
        WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
        "PENSERVICE_CServiceModule::OnConsoleConnect");
  }
  else if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      108,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::OnConsoleConnect",
      LastError);
  }
}

```

## disassembly

```asm
0x180023bd0  mov     [rsp+arg_8], rbx
0x180023bd5  push    rsi
0x180023bd6  push    rdi
0x180023bd7  push    r14
0x180023bd9  sub     rsp, 40h
0x180023bdd  mov     esi, edx
0x180023bdf  mov     rdi, rcx
0x180023be2  mov     rcx, cs:WPP_GLOBAL_Control
0x180023be9  lea     r14, WPP_GLOBAL_Control
0x180023bf0  cmp     rcx, r14
0x180023bf3  jz      short loc_180023C17
0x180023bf5  test    byte ptr [rcx+1Ch], 10h
0x180023bf9  jz      short loc_180023C17
0x180023bfb  mov     rcx, [rcx+10h]
0x180023bff  lea     r9, aPenserviceCser_31; "PENSERVICE_CServiceModule::OnConsoleCon"...
0x180023c06  mov     edx, 6Ah ; 'j'
0x180023c0b  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180023c12  call    WPP_SF_s
0x180023c17  mov     eax, cs:dword_1800411A8
0x180023c1d  cmp     eax, 5
0x180023c20  jbe     short loc_180023C51
0x180023c22  mov     edx, 4000000h
0x180023c27  lea     rcx, dword_1800411A8
0x180023c2e  call    _tlgKeywordOn
0x180023c33  test    al, al
0x180023c35  jz      short loc_180023C51
0x180023c37  lea     rax, [rsp+58h+arg_0]
0x180023c3c  mov     [rsp+58h+arg_0], esi
0x180023c40  lea     rdx, byte_18003A21F
0x180023c47  mov     [rsp+58h+pBytesReturned], rax
0x180023c4c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180023c51  cmp     dword ptr [rdi+44h], 0
0x180023c55  jz      short loc_180023CCC
0x180023c57  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch> `wil::Feature<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::GetImpl(void)'::`2'::impl
0x180023c5e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::__private_IsEnabled(void)
0x180023c63  test    al, al
0x180023c65  jz      short loc_180023C73
0x180023c67  mov     edx, esi; unsigned int
0x180023c69  mov     rcx, rdi; this
0x180023c6c  call    ?_StopOobeProcesses@CServiceModule@@AEAAXK@Z; CServiceModule::_StopOobeProcesses(ulong)
0x180023c71  jmp     short loc_180023CCC
0x180023c73  mov     dword ptr [rdi+44h], 0
0x180023c7a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController> `wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl(void)'::`2'::impl
0x180023c81  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(void)
0x180023c86  mov     ebx, 1
0x180023c8b  test    al, al
0x180023c8d  jz      short loc_180023CA3
0x180023c8f  cmp     byte ptr [rdi+40h], 0
0x180023c93  jnz     short loc_180023C9F
0x180023c95  cmp     byte ptr [rdi+41h], 0
0x180023c99  jnz     short loc_180023C9F
0x180023c9b  xor     edx, edx
0x180023c9d  jmp     short loc_180023CA7
0x180023c9f  mov     edx, ebx
0x180023ca1  jmp     short loc_180023CA7
0x180023ca3  movzx   edx, byte ptr [rdi+40h]; int
0x180023ca7  mov     rcx, rdi; this
0x180023caa  call    ?_EnableDisablePenProcessTypes@CServiceModule@@AEAAHH@Z; CServiceModule::_EnableDisablePenProcessTypes(int)
0x180023caf  mov     edx, eax; int
0x180023cb1  mov     rcx, rdi; this
0x180023cb4  call    ?_CheckLicense@CServiceModule@@AEAAHH@Z; CServiceModule::_CheckLicense(int)
0x180023cb9  mov     r9d, esi; unsigned int
0x180023cbc  mov     r8d, 18h; unsigned int
0x180023cc2  mov     edx, ebx; unsigned int
0x180023cc4  mov     rcx, rdi; this
0x180023cc7  call    ?_RemovePenProcessesWorker@CServiceModule@@AEAAXKKK@Z; CServiceModule::_RemovePenProcessesWorker(ulong,ulong,ulong)
0x180023ccc  xor     r8d, r8d; unsigned int
0x180023ccf  mov     r9d, esi; unsigned int
0x180023cd2  mov     rcx, rdi; this
0x180023cd5  lea     edx, [r8+2]; unsigned int
0x180023cd9  call    ?_RemovePenProcessesWorker@CServiceModule@@AEAAXKKK@Z; CServiceModule::_RemovePenProcessesWorker(ulong,ulong,ulong)
0x180023cde  lea     rax, [rsp+58h+arg_0]
0x180023ce3  mov     [rsp+58h+ppBuffer], 0
0x180023cec  lea     r9, [rsp+58h+ppBuffer]; ppBuffer
0x180023cf1  mov     [rsp+58h+pBytesReturned], rax; int
0x180023cf6  mov     r8d, 8; WTSInfoClass
0x180023cfc  mov     [rsp+58h+arg_0], 0
0x180023d04  mov     edx, esi; SessionId
0x180023d06  xor     ecx, ecx; hServer
0x180023d08  call    cs:__imp_WTSQuerySessionInformationW
0x180023d0e  test    eax, eax
0x180023d10  jz      short loc_180023D7F
0x180023d12  mov     r8d, [rsp+58h+arg_0]
0x180023d17  mov     rcx, [rsp+58h+ppBuffer]; pMemory
0x180023d1c  cmp     r8d, 4
0x180023d20  jnz     loc_180023DCC
0x180023d26  test    rcx, rcx
0x180023d29  jz      loc_180023DCC
0x180023d2f  mov     ebx, [rcx]
0x180023d31  call    cs:__imp_WTSFreeMemory
0x180023d37  xor     r9d, r9d; int
0x180023d3a  mov     [rsp+58h+var_30], 0; int
0x180023d42  mov     r8d, ebx; enum _WTS_CONNECTSTATE_CLASS
0x180023d45  mov     edx, esi; unsigned int
0x180023d47  mov     rcx, rdi; Context
0x180023d4a  call    ?_StartPenProcessesWorker@CServiceModule@@AEAAXKW4_WTS_CONNECTSTATE_CLASS@@HHHH@Z; CServiceModule::_StartPenProcessesWorker(ulong,_WTS_CONNECTSTATE_CLASS,int,int,int,int)
0x180023d4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d56  cmp     rcx, r14
0x180023d59  jz      short loc_180023DBE
0x180023d5b  test    byte ptr [rcx+1Ch], 10h
0x180023d5f  jz      short loc_180023DBE
0x180023d61  mov     rcx, [rcx+10h]
0x180023d65  lea     r9, aPenserviceCser_31; "PENSERVICE_CServiceModule::OnConsoleCon"...
0x180023d6c  mov     edx, 6Dh ; 'm'
0x180023d71  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180023d78  call    WPP_SF_s
0x180023d7d  jmp     short loc_180023DBE
0x180023d7f  mov     rax, cs:WPP_GLOBAL_Control
0x180023d86  cmp     rax, r14
0x180023d89  jz      short loc_180023DBE
0x180023d8b  test    byte ptr [rax+1Ch], 4
0x180023d8f  jz      short loc_180023DBE
0x180023d91  call    cs:__imp_GetLastError
0x180023d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d9e  lea     r9, aPenserviceCser_31; "PENSERVICE_CServiceModule::OnConsoleCon"...
0x180023da5  mov     edx, 6Ch ; 'l'
0x180023daa  mov     dword ptr [rsp+58h+pBytesReturned], eax
0x180023dae  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180023db5  mov     rcx, [rcx+10h]
0x180023db9  call    WPP_SF_sd
0x180023dbe  mov     rbx, [rsp+58h+arg_8]
0x180023dc3  add     rsp, 40h
0x180023dc7  pop     r14
0x180023dc9  pop     rdi
0x180023dca  pop     rsi
0x180023dcb  retn
0x180023dcc  mov     rax, cs:WPP_GLOBAL_Control
0x180023dd3  cmp     rax, r14
0x180023dd6  jz      short loc_180023E04
0x180023dd8  test    byte ptr [rax+1Ch], 4
0x180023ddc  jz      short loc_180023E04
0x180023dde  mov     rcx, [rax+10h]
0x180023de2  lea     r9, aPenserviceCser_31; "PENSERVICE_CServiceModule::OnConsoleCon"...
0x180023de9  mov     dword ptr [rsp+58h+pBytesReturned], r8d; char *
0x180023dee  mov     edx, 6Bh ; 'k'
0x180023df3  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180023dfa  call    WPP_SF_sd
0x180023dff  mov     rcx, [rsp+58h+ppBuffer]; pMemory
0x180023e04  call    cs:__imp_WTSFreeMemory
0x180023e0a  mov     rcx, [rsp+58h]; this
0x180023e0f  lea     r9, aUnexpectedRetu; "unexpected return from WTSQuerySessionI"...
0x180023e16  lea     r8, aDriversTabletP_1; "drivers\\tablet\\platform\\pen\\penserv"...
0x180023e1d  mov     edx, 919h; void *
0x180023e22  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
```
