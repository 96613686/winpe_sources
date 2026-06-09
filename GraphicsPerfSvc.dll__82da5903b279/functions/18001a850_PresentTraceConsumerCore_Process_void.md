# PresentTraceConsumerCore::Process(void)

- ea: `0x18001a850`
- end: `0x18001aa3f`
- name: `?Process@PresentTraceConsumerCore@@QEAAXXZ`
- size: `495`
- prototype: `void __fastcall(PresentTraceConsumerCore *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180010070`

## callees

- `0x18000fbbc`
- `0x18000fc54`
- `0x1800191e0`
- `0x18001a850`
- `0x18001b044`
- `0x18001c068`
- `0x180026ebc`

## import_xrefs

- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18001a86b`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18001a86b`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18001a953`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18001a953`

## string_xrefs

- `0x18001a876`: `onecore\windows\directx\dxg\common\etwtracesession\tracesession.cpp`
- `0x18001a971`: `onecore\windows\directx\dxg\common\etwtracesession\tracesession.cpp`

## pseudocode

```c
void __fastcall PresentTraceConsumerCore::Process(ULONG64 *this)
{
  ULONG v2; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  unsigned int v5; // eax
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  ULONG v13; // eax
  unsigned int v14; // [rsp+20h] [rbp-18h]
  const char *v15; // [rsp+28h] [rbp-10h]
  const char *v16; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = ProcessTrace(this + 13, 1u, 0, 0);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0xDA,
    (unsigned int)"onecore\\windows\\directx\\dxg\\common\\etwtracesession\\tracesession.cpp",
    (const char *)v2,
    (unsigned int)"Error occured while processing trace.",
    v15);
  if ( !*((_BYTE *)this + 152) )
  {
    LOBYTE(v4) = 3;
    LOBYTE(v3) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::GetImpl'::`2'::impl,
      v3,
      v4);
    v5 = PresentTraceConsumerCore::DisableProvider((PresentTraceConsumerCore *)this, &stru_180034D70);
    if ( v5 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x1D0,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\lib\\presenttraceconsumercore.cpp",
        (const char *)v5,
        v14);
    v6 = PresentTraceConsumerCore::DisableProvider((PresentTraceConsumerCore *)this, &stru_180034D90);
    if ( v6 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x1D1,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\lib\\presenttraceconsumercore.cpp",
        (const char *)v6,
        v14);
    LOBYTE(v8) = 3;
    LOBYTE(v7) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::GetImpl'::`2'::impl,
      v7,
      v8);
    v9 = PresentTraceConsumerCore::DisableProvider((PresentTraceConsumerCore *)this, &stru_180034DB0);
    if ( v9 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x1D5,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\lib\\presenttraceconsumercore.cpp",
        (const char *)v9,
        v14);
    v10 = PresentTraceConsumerCore::DisableProvider((PresentTraceConsumerCore *)this, &stru_180034D80);
    if ( v10 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x1D8,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\lib\\presenttraceconsumercore.cpp",
        (const char *)v10,
        v14);
    v11 = PresentTraceConsumerCore::DisableProvider((PresentTraceConsumerCore *)this, &stru_180034DC0);
    if ( v11 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x1D9,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\lib\\presenttraceconsumercore.cpp",
        (const char *)v11,
        v14);
    v12 = PresentTraceConsumerCore::DisableProvider((PresentTraceConsumerCore *)this, &ProviderId);
    if ( v12 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x1DA,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\lib\\presenttraceconsumercore.cpp",
        (const char *)v12,
        v14);
  }
  v13 = CloseTrace(this[13]);
  if ( v13 != 7007 )
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecore\\windows\\directx\\dxg\\common\\etwtracesession\\tracesession.cpp",
      (const char *)v13,
      (unsigned int)"Error occured while closing trace.",
      v16);
  TraceSession::Stop((TraceSession *)(this + 2));
  *((_DWORD *)this + 100) = 2;
}

```

## disassembly

```asm
0x18001a850  mov     [rsp+arg_0], rbx
0x18001a855  push    rdi
0x18001a856  sub     rsp, 30h
0x18001a85a  xor     r9d, r9d; EndTime
0x18001a85d  mov     rbx, rcx
0x18001a860  add     rcx, 68h ; 'h'; HandleArray
0x18001a864  xor     r8d, r8d; StartTime
0x18001a867  lea     edx, [r9+1]; HandleCount
0x18001a86b  call    cs:__imp_ProcessTrace
0x18001a871  mov     rcx, [rsp+38h]; this
0x18001a876  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\dxg\\common"...
0x18001a87d  mov     r9d, eax; char *
0x18001a880  mov     edx, 0DAh; void *
0x18001a885  lea     rax, aErrorOccuredWh_0; "Error occured while processing trace."
0x18001a88c  mov     qword ptr [rsp+38h+var_18], rax; unsigned int
0x18001a891  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18001a896  cmp     byte ptr [rbx+98h], 0
0x18001a89d  jnz     loc_18001A94F
0x18001a8a3  mov     r8b, 3
0x18001a8a6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking> `wil::Feature<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::GetImpl(void)'::`2'::impl
0x18001a8ad  mov     dl, 1
0x18001a8af  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001a8b4  lea     rdx, stru_180034D70; struct _GUID *
0x18001a8bb  mov     rcx, rbx; this
0x18001a8be  call    ?DisableProvider@PresentTraceConsumerCore@@AEAAKAEBU_GUID@@@Z; PresentTraceConsumerCore::DisableProvider(_GUID const &)
0x18001a8c3  test    eax, eax
0x18001a8c5  jnz     loc_18001A9A3
0x18001a8cb  lea     rdx, stru_180034D90; struct _GUID *
0x18001a8d2  mov     rcx, rbx; this
0x18001a8d5  call    ?DisableProvider@PresentTraceConsumerCore@@AEAAKAEBU_GUID@@@Z; PresentTraceConsumerCore::DisableProvider(_GUID const &)
0x18001a8da  test    eax, eax
0x18001a8dc  jnz     loc_18001A9BD
0x18001a8e2  mov     r8b, 3
0x18001a8e5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking> `wil::Feature<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::GetImpl(void)'::`2'::impl
0x18001a8ec  mov     dl, 1
0x18001a8ee  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001a8f3  lea     rdx, stru_180034DB0; struct _GUID *
0x18001a8fa  mov     rcx, rbx; this
0x18001a8fd  call    ?DisableProvider@PresentTraceConsumerCore@@AEAAKAEBU_GUID@@@Z; PresentTraceConsumerCore::DisableProvider(_GUID const &)
0x18001a902  test    eax, eax
0x18001a904  jnz     loc_18001A9D7
0x18001a90a  lea     rdx, stru_180034D80; struct _GUID *
0x18001a911  mov     rcx, rbx; this
0x18001a914  call    ?DisableProvider@PresentTraceConsumerCore@@AEAAKAEBU_GUID@@@Z; PresentTraceConsumerCore::DisableProvider(_GUID const &)
0x18001a919  test    eax, eax
0x18001a91b  jnz     loc_18001A9F1
0x18001a921  lea     rdx, stru_180034DC0; struct _GUID *
0x18001a928  mov     rcx, rbx; this
0x18001a92b  call    ?DisableProvider@PresentTraceConsumerCore@@AEAAKAEBU_GUID@@@Z; PresentTraceConsumerCore::DisableProvider(_GUID const &)
0x18001a930  test    eax, eax
0x18001a932  jnz     loc_18001AA0B
0x18001a938  lea     rdx, ProviderId; struct _GUID *
0x18001a93f  mov     rcx, rbx; this
0x18001a942  call    ?DisableProvider@PresentTraceConsumerCore@@AEAAKAEBU_GUID@@@Z; PresentTraceConsumerCore::DisableProvider(_GUID const &)
0x18001a947  test    eax, eax
0x18001a949  jnz     loc_18001AA25
0x18001a94f  mov     rcx, [rbx+68h]; TraceHandle
0x18001a953  call    cs:__imp_CloseTrace
0x18001a959  cmp     eax, 1B5Fh
0x18001a95e  jz      short loc_18001A985
0x18001a960  mov     rcx, [rsp+38h]; this
0x18001a965  lea     rdx, aErrorOccuredWh_2; "Error occured while closing trace."
0x18001a96c  mov     qword ptr [rsp+38h+var_18], rdx; unsigned int
0x18001a971  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\dxg\\common"...
0x18001a978  mov     edx, 0E7h; void *
0x18001a97d  mov     r9d, eax; char *
0x18001a980  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18001a985  lea     rcx, [rbx+10h]; this
0x18001a989  call    ?Stop@TraceSession@@QEAAXXZ; TraceSession::Stop(void)
0x18001a98e  mov     dword ptr [rbx+190h], 2
0x18001a998  mov     rbx, [rsp+38h+arg_0]
0x18001a99d  add     rsp, 30h
0x18001a9a1  pop     rdi
0x18001a9a2  retn
0x18001a9a3  mov     rcx, [rsp+38h]; this
0x18001a9a8  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\directx\\dxg\\gpm"...
0x18001a9af  mov     r9d, eax; char *
0x18001a9b2  mov     edx, 1D0h; void *
0x18001a9b7  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001a9bd  mov     rcx, [rsp+38h]; this
0x18001a9c2  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\directx\\dxg\\gpm"...
0x18001a9c9  mov     r9d, eax; char *
0x18001a9cc  mov     edx, 1D1h; void *
0x18001a9d1  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001a9d7  mov     rcx, [rsp+38h]; this
0x18001a9dc  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\directx\\dxg\\gpm"...
0x18001a9e3  mov     r9d, eax; char *
0x18001a9e6  mov     edx, 1D5h; void *
0x18001a9eb  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001a9f1  mov     rcx, [rsp+38h]; this
0x18001a9f6  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\directx\\dxg\\gpm"...
0x18001a9fd  mov     r9d, eax; char *
0x18001aa00  mov     edx, 1D8h; void *
0x18001aa05  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001aa0b  mov     rcx, [rsp+38h]; this
0x18001aa10  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\directx\\dxg\\gpm"...
0x18001aa17  mov     r9d, eax; char *
0x18001aa1a  mov     edx, 1D9h; void *
0x18001aa1f  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001aa25  mov     rcx, [rsp+38h]; this
0x18001aa2a  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\directx\\dxg\\gpm"...
0x18001aa31  mov     r9d, eax; char *
0x18001aa34  mov     edx, 1DAh; void *
0x18001aa39  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
