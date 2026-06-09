# RdpIdEvtFileCreate(WDFDEVICE__ *,WDFREQUEST__ *,WDFFILEOBJECT__ *)

- ea: `0x18000ffb0`
- end: `0x18001029e`
- name: `?RdpIdEvtFileCreate@@YAXPEAUWDFDEVICE__@@PEAUWDFREQUEST__@@PEAUWDFFILEOBJECT__@@@Z`
- size: `750`
- prototype: `void __fastcall(struct WDFDEVICE__ *, struct WDFREQUEST__ *, struct WDFFILEOBJECT__ *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x180001bc4`
- `0x180006f60`
- `0x18000d614`
- `0x18000dbd8`
- `0x18000e978`
- `0x18000ffb0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001002a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010225`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001002a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010225`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001026a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001026a`

## string_xrefs

- `0x18001016b`: `Failed to impersonate requestor process`
- `0x180010179`: `RdpIdEvtFileCreate`

## pseudocode

```c
void __fastcall RdpIdEvtFileCreate(struct WDFDEVICE__ *a1, struct WDFREQUEST__ *a2, struct WDFFILEOBJECT__ *a3)
{
  char v6; // bl
  bool v7; // di
  bool v8; // si
  char CurrentThreadId; // al
  int v10; // r8d
  int v11; // edx
  int v12; // edi
  __int64 v13; // rsi
  int v14; // edi
  _DWORD *v15; // r8
  int v16; // r9d
  bool v17; // di
  char v18; // al
  int v19; // r8d
  int v20; // edx
  int v21; // [rsp+20h] [rbp-49h]
  int v22; // [rsp+28h] [rbp-41h]
  int v23; // [rsp+50h] [rbp-19h] BYREF
  int v24; // [rsp+54h] [rbp-15h] BYREF
  int v25; // [rsp+58h] [rbp-11h] BYREF
  const char *v26; // [rsp+60h] [rbp-9h] BYREF
  const char *v27; // [rsp+68h] [rbp-1h] BYREF
  int v28[2]; // [rsp+70h] [rbp+7h] BYREF
  GUID ActivityId; // [rsp+78h] [rbp+Fh] BYREF

  v6 = 1;
  v7 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v8 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v10) = v8;
    LOBYTE(v11) = v7;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      v10,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v21,
      v22,
      16,
      &WPP_bf700344ce113c4bc67df149a6a70839_Traceguids,
      CurrentThreadId);
  }
  CAutoSetThreadActivityId::CAutoSetThreadActivityId(
    &ActivityId,
    &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId);
  v12 = (*(__int64 (__fastcall **)(__int64, struct WDFDEVICE__ *, __int64 *))(WdfFunctions_02025 + 984))(
          WdfDriverGlobals,
          a1,
          off_180057078);
  v13 = (*(__int64 (__fastcall **)(__int64, struct WDFFILEOBJECT__ *, __int64 *))(WdfFunctions_02025 + 984))(
          WdfDriverGlobals,
          a3,
          off_180057020);
  *(_BYTE *)(v13 + 44) = 0;
  *(_DWORD *)(v13 + 40) = (*(__int64 (__fastcall **)(__int64, struct WDFREQUEST__ *))(WdfFunctions_02025 + 1432))(
                            WdfDriverGlobals,
                            a2);
  if ( (*(unsigned __int8 (__fastcall **)(__int64, struct WDFREQUEST__ *))(WdfFunctions_02025 + 1384))(
         WdfDriverGlobals,
         a2) != 1
    || *(_DWORD *)(v13 + 40) != 4 )
  {
    v21 = v12;
    v14 = (*(__int64 (__fastcall **)(__int64, struct WDFREQUEST__ *, __int64, void (__fastcall *)(struct WDFREQUEST__ *, void *)))(WdfFunctions_02025 + 1424))(
            WdfDriverGlobals,
            a2,
            1,
            RdpIdEvtRequestImpersonate);
    if ( v14 < 0 )
    {
      v15 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v15 > 3u )
      {
        v24 = *(_DWORD *)(v13 + 40);
        v23 = v14;
        v26 = "Failed to impersonate requestor process";
        v27 = "RdpIdEvtFileCreate";
        *(_QWORD *)v28 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\device.cpp";
        v25 = 346;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v15,
          (unsigned int)&word_18004C426,
          (_DWORD)v15,
          v16,
          (__int64)v28,
          (__int64)&v25,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&v24,
          (__int64)&v23);
      }
    }
  }
  (*(void (__fastcall **)(__int64, struct WDFREQUEST__ *, _QWORD))(WdfFunctions_02025 + 1304))(WdfDriverGlobals, a2, 0);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v6 = 0;
  }
  v17 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v18 = GetCurrentThreadId();
    LOBYTE(v19) = v17;
    LOBYTE(v20) = v6;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v20,
      v19,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v21,
      v22,
      17,
      &WPP_bf700344ce113c4bc67df149a6a70839_Traceguids,
      v18);
  }
  EventActivityIdControl(2u, &ActivityId);
}

```

## disassembly

```asm
0x18000ffb0  mov     [rsp-8+arg_18], rbx
0x18000ffb5  push    rbp
0x18000ffb6  push    rsi
0x18000ffb7  push    rdi
0x18000ffb8  push    r12
0x18000ffba  push    r13
0x18000ffbc  push    r14
0x18000ffbe  push    r15
0x18000ffc0  lea     rbp, [rsp-27h]
0x18000ffc5  sub     rsp, 90h
0x18000ffcc  mov     rax, cs:__security_cookie
0x18000ffd3  xor     rax, rsp
0x18000ffd6  mov     [rbp+57h+var_38], rax
0x18000ffda  mov     r12, r8
0x18000ffdd  mov     r14, rdx
0x18000ffe0  mov     r15, rcx
0x18000ffe3  mov     rax, cs:WPP_GLOBAL_Control
0x18000ffea  lea     rcx, WPP_GLOBAL_Control
0x18000fff1  mov     ebx, 1
0x18000fff6  cmp     rax, rcx
0x18000fff9  jz      short loc_18001000B
0x18000fffb  test    [rax+1Ch], bl
0x18000fffe  jz      short loc_18001000B
0x180010000  cmp     byte ptr [rax+19h], 4
0x180010004  jb      short loc_18001000B
0x180010006  mov     dil, bl
0x180010009  jmp     short loc_18001000E
0x18001000b  xor     dil, dil
0x18001000e  lea     r13, WPP_RECORDER_INITIALIZED
0x180010015  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001001c  setnz   sil
0x180010020  test    dil, dil
0x180010023  jnz     short loc_18001002A
0x180010025  test    sil, sil
0x180010028  jz      short loc_180010067
0x18001002a  call    cs:__imp_GetCurrentThreadId
0x180010031  nop     dword ptr [rax+rax+00h]
0x180010036  mov     rcx, cs:WPP_GLOBAL_Control
0x18001003d  mov     r8b, sil; int
0x180010040  mov     dword ptr [rsp+0C0h+var_80], eax; char
0x180010044  mov     dl, dil; int
0x180010047  lea     rax, WPP_bf700344ce113c4bc67df149a6a70839_Traceguids
0x18001004e  mov     [rsp+0C0h+MessageGuid], rax; MessageGuid
0x180010053  mov     r9, [rcx+28h]; int
0x180010057  mov     rcx, [rcx+10h]; int
0x18001005b  mov     [rsp+0C0h+var_90], 10h; __int16
0x180010062  call    WPP_RECORDER_AND_TRACE_SF_D
0x180010067  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x18001006e  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x180010072  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x180010077  mov     rax, cs:WdfFunctions_02025
0x18001007e  mov     rdx, r15
0x180010081  mov     r8, cs:off_180057078
0x180010088  mov     rcx, cs:WdfDriverGlobals
0x18001008f  mov     rax, [rax+3D8h]
0x180010096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001009b  mov     rcx, cs:WdfFunctions_02025
0x1800100a2  mov     rdi, rax
0x1800100a5  mov     r8, cs:off_180057020
0x1800100ac  mov     rdx, r12
0x1800100af  mov     rax, [rcx+3D8h]
0x1800100b6  mov     rcx, cs:WdfDriverGlobals
0x1800100bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100c2  mov     rsi, rax
0x1800100c5  mov     rdx, r14
0x1800100c8  mov     byte ptr [rax+2Ch], 0
0x1800100cc  mov     rcx, cs:WdfFunctions_02025
0x1800100d3  mov     rax, [rcx+598h]
0x1800100da  mov     rcx, cs:WdfDriverGlobals
0x1800100e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100e6  mov     [rsi+28h], eax
0x1800100e9  mov     rdx, r14
0x1800100ec  mov     rcx, cs:WdfFunctions_02025
0x1800100f3  mov     rax, [rcx+568h]
0x1800100fa  mov     rcx, cs:WdfDriverGlobals
0x180010101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010106  cmp     al, bl
0x180010108  jnz     short loc_180010114
0x18001010a  cmp     dword ptr [rsi+28h], 4
0x18001010e  jz      loc_1800101D1
0x180010114  mov     rax, cs:WdfFunctions_02025
0x18001011b  lea     r9, ?RdpIdEvtRequestImpersonate@@YAXPEAUWDFREQUEST__@@PEAX@Z; RdpIdEvtRequestImpersonate(WDFREQUEST__ *,void *)
0x180010122  mov     rcx, cs:WdfDriverGlobals
0x180010129  mov     r8d, ebx
0x18001012c  mov     rdx, r14
0x18001012f  mov     qword ptr [rsp+0C0h+var_A0], rdi
0x180010134  mov     rax, [rax+590h]
0x18001013b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010140  mov     edi, eax
0x180010142  test    eax, eax
0x180010144  jns     loc_1800101D1
0x18001014a  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001014f  mov     r8, [rax+8]
0x180010153  mov     ecx, [r8]
0x180010156  cmp     ecx, 3
0x180010159  jbe     short loc_1800101D1
0x18001015b  mov     eax, [rsi+28h]
0x18001015e  lea     rdx, word_18004C426
0x180010165  mov     [rbp+57h+var_6C], eax
0x180010168  mov     rcx, r8
0x18001016b  lea     rax, aFailedToImpers; "Failed to impersonate requestor process"
0x180010172  mov     [rbp+57h+var_70], edi
0x180010175  mov     [rbp+57h+var_60], rax
0x180010179  lea     rax, aRdpidevtfilecr; "RdpIdEvtFileCreate"
0x180010180  mov     [rbp+57h+var_58], rax
0x180010184  lea     rax, aOnecoreuapTerm_5; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001018b  mov     qword ptr [rbp+57h+var_50], rax
0x18001018f  lea     rax, [rbp+57h+var_70]
0x180010193  mov     [rsp+0C0h+var_78], rax
0x180010198  lea     rax, [rbp+57h+var_6C]
0x18001019c  mov     qword ptr [rsp+0C0h+var_80], rax
0x1800101a1  lea     rax, [rbp+57h+var_60]
0x1800101a5  mov     [rsp+0C0h+MessageGuid], rax
0x1800101aa  lea     rax, [rbp+57h+var_58]
0x1800101ae  mov     qword ptr [rsp+0C0h+var_90], rax
0x1800101b3  lea     rax, [rbp+57h+var_68]
0x1800101b7  mov     qword ptr [rsp+0C0h+var_98], rax; int
0x1800101bc  lea     rax, [rbp+57h+var_50]
0x1800101c0  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x1800101c5  mov     [rbp+57h+var_68], 15Ah
0x1800101cc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800101d1  mov     rax, cs:WdfFunctions_02025
0x1800101d8  xor     r8d, r8d
0x1800101db  mov     rcx, cs:WdfDriverGlobals
0x1800101e2  mov     rdx, r14
0x1800101e5  mov     rax, [rax+518h]
0x1800101ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101f1  mov     rax, cs:WPP_GLOBAL_Control
0x1800101f8  lea     rcx, WPP_GLOBAL_Control
0x1800101ff  cmp     rax, rcx
0x180010202  jz      short loc_18001020F
0x180010204  test    [rax+1Ch], bl
0x180010207  jz      short loc_18001020F
0x180010209  cmp     byte ptr [rax+19h], 4
0x18001020d  jnb     short loc_180010211
0x18001020f  xor     bl, bl
0x180010211  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180010218  setnz   dil
0x18001021c  test    bl, bl
0x18001021e  jnz     short loc_180010225
0x180010220  test    dil, dil
0x180010223  jz      short loc_180010261
0x180010225  call    cs:__imp_GetCurrentThreadId
0x18001022c  nop     dword ptr [rax+rax+00h]
0x180010231  mov     rcx, cs:WPP_GLOBAL_Control
0x180010238  mov     r8b, dil; int
0x18001023b  mov     dword ptr [rsp+0C0h+var_80], eax; char
0x18001023f  mov     dl, bl; int
0x180010241  lea     rax, WPP_bf700344ce113c4bc67df149a6a70839_Traceguids
0x180010248  mov     [rsp+0C0h+MessageGuid], rax; MessageGuid
0x18001024d  mov     r9, [rcx+28h]; int
0x180010251  mov     rcx, [rcx+10h]; int
0x180010255  mov     [rsp+0C0h+var_90], 11h; __int16
0x18001025c  call    WPP_RECORDER_AND_TRACE_SF_D
0x180010261  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180010265  mov     ecx, 2; ControlCode
0x18001026a  call    cs:__imp_EventActivityIdControl
0x180010271  nop     dword ptr [rax+rax+00h]
0x180010276  mov     rcx, [rbp+57h+var_38]
0x18001027a  xor     rcx, rsp; StackCookie
0x18001027d  call    __security_check_cookie
0x180010282  mov     rbx, [rsp+0C0h+arg_18]
0x18001028a  add     rsp, 90h
0x180010291  pop     r15
0x180010293  pop     r14
0x180010295  pop     r13
0x180010297  pop     r12
0x180010299  pop     rdi
0x18001029a  pop     rsi
0x18001029b  pop     rbp
0x18001029c  retn
```
