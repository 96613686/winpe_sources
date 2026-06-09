# MbbUtilWwanDeleteMPDP(_MBB_REQUEST_CONTEXT *)

- ea: `0x1400212ec`
- end: `0x1400216cb`
- name: `?MbbUtilWwanDeleteMPDP@@YAHPEAU_MBB_REQUEST_CONTEXT@@@Z`
- size: `991`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140014b10`

## callees

- `0x140001300`
- `0x1400018f0`
- `0x140001980`
- `0x140001b34`
- `0x140001cf8`
- `0x140001db8`
- `0x14000d9cc`
- `0x14001ea18`
- `0x14001f25c`
- `0x1400212ec`
- `0x140047e90`

## string_xrefs

- `0x1400214d7`: `AttemptToDeletePrimaryInterface`
- `0x140021658`: `MbbCxcompleted`

## pseudocode

```c
__int64 __fastcall MbbUtilWwanDeleteMPDP(struct _MBB_REQUEST_CONTEXT *a1)
{
  __int64 v2; // r14
  struct _GUID *v3; // r12
  struct _MINIPORT_INTERFACE_CONTEXT *v4; // rax
  int v5; // edx
  int v6; // r9d
  struct _MINIPORT_INTERFACE_CONTEXT *v7; // rsi
  unsigned int v8; // r15d
  __int64 *v9; // rax
  __int64 v10; // rcx
  int v11; // r8d
  __int64 *v12; // rax
  __int64 v13; // rcx
  const wchar_t *v14; // rax
  int *v15; // rdx
  int v16; // eax
  int v17; // edx
  int v18; // r15d
  int v19; // r13d
  int v20; // edx
  __int64 *v21; // rax
  const wchar_t *v23; // [rsp+50h] [rbp-18h] BYREF
  _QWORD v24[2]; // [rsp+58h] [rbp-10h] BYREF
  int v25; // [rsp+B0h] [rbp+48h] BYREF
  int v26; // [rsp+B8h] [rbp+50h] BYREF
  int v27; // [rsp+C0h] [rbp+58h] BYREF
  struct _GUID *v28; // [rsp+C8h] [rbp+60h] BYREF

  v2 = **((_QWORD **)a1 + 6);
  v3 = (struct _GUID *)(*(_QWORD *)(*((_QWORD *)a1 + 53) + 40LL) + 8LL);
  v4 = MbbWwanReferenceSessionForIfGuid((PKSPIN_LOCK)v2, v3);
  v7 = v4;
  if ( v4 )
  {
    if ( *((_DWORD *)v4 + 17) )
    {
      v16 = MbbUtilDisconnectOnDeleteMPDP((PKSPIN_LOCK)v2, v4);
      v18 = v16;
      if ( v16 == 259 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v17) = 3;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v17,
            3,
            103,
            (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids);
        }
        v18 = 0;
      }
      else if ( v16 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = 3;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v17,
          3,
          104,
          (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
          v16);
      }
      MbbUtilIndicateMPDPState(a1, v18, v7);
      ((void (__fastcall *)(PNET_DRIVER_GLOBALS, _QWORD))qword_14005F548)(NetDriverGlobals, *((_QWORD *)v7 + 1));
      v19 = *((_DWORD *)v7 + 17);
      if ( MbbWwanRemoveSessionFromAdapterList((PKSPIN_LOCK)v2, v7) )
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 1664))(
          WdfDriverGlobals,
          *((_QWORD *)v7 + 1));
      v8 = 65537;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v20) = 4;
        WPP_RECORDER_SF__guid_(
          WPP_GLOBAL_Control->DeviceExtension,
          v20,
          3,
          105,
          (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
          (__int64)v3);
      }
      if ( (unsigned int)dword_14005E0C8 <= 5
        || (qword_14005E0D8 & 0x400000000000LL) == 0
        || (qword_14005E0E0 & 0x400000000000LL) != qword_14005E0E0 )
      {
        goto LABEL_31;
      }
      v15 = &dword_140058A6C;
      v26 = *(_DWORD *)(v2 + 1136);
      v21 = *(__int64 **)(v2 + 1144);
      v25 = v19;
      v13 = *v21;
      v14 = L"MbbCxcompleted";
      v27 = 65537;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v5) = 2;
        WPP_RECORDER_SF__guid_(
          WPP_GLOBAL_Control->DeviceExtension,
          v5,
          3,
          102,
          (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
          (__int64)v3);
      }
      v8 = -1073676267;
      if ( (unsigned int)dword_14005E0C8 <= 5 )
        goto LABEL_31;
      v11 = qword_14005E0E0;
      if ( (qword_14005E0D8 & 0x400000000000LL) == 0 || (qword_14005E0E0 & 0x400000000000LL) != qword_14005E0E0 )
        goto LABEL_31;
      v26 = *(_DWORD *)(v2 + 1136);
      v12 = *(__int64 **)(v2 + 1144);
      v25 = 0;
      v13 = *v12;
      v14 = L"AttemptToDeletePrimaryInterface";
      v27 = -1073676267;
      v15 = (int *)byte_140058BE9;
    }
    v23 = v14;
    v28 = v3;
    v24[0] = v13 + 40;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v13 + 40,
      (_DWORD)v15,
      v11,
      v6,
      (__int64)&v27,
      (__int64)&v23,
      (__int64)v24,
      (__int64)&v28,
      (__int64)&v26,
      (__int64)&v25);
LABEL_31:
    DereferenceSession(v7);
    return v8;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF__guid_(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      3,
      101,
      (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
      (__int64)v3);
  }
  v8 = -1073676267;
  if ( (unsigned int)dword_14005E0C8 > 5
    && (qword_14005E0D8 & 0x400000000000LL) != 0
    && (qword_14005E0E0 & 0x400000000000LL) == qword_14005E0E0 )
  {
    v26 = *(_DWORD *)(v2 + 1136);
    v9 = *(__int64 **)(v2 + 1144);
    v25 = 0;
    v28 = v3;
    v10 = *v9;
    v24[0] = L"SecondaryInterfaceGuidInvalid";
    v27 = -1073676267;
    v23 = (const wchar_t *)(v10 + 40);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v10 + 40,
      (unsigned int)byte_140058AEB,
      qword_14005E0E0,
      v6,
      (__int64)&v27,
      (__int64)v24,
      (__int64)&v23,
      (__int64)&v28,
      (__int64)&v26,
      (__int64)&v25);
  }
  return v8;
}

```

## disassembly

```asm
0x1400212ec  push    rbp
0x1400212ee  push    rbx
0x1400212ef  push    rsi
0x1400212f0  push    rdi
0x1400212f1  push    r12
0x1400212f3  push    r13
0x1400212f5  push    r14
0x1400212f7  push    r15
0x1400212f9  mov     rbp, rsp
0x1400212fc  sub     rsp, 68h
0x140021300  mov     rax, [rcx+30h]
0x140021304  mov     r13, rcx
0x140021307  mov     r14, [rax]
0x14002130a  mov     rax, [rcx+1A8h]
0x140021311  mov     rcx, r14; SpinLock
0x140021314  mov     r12, [rax+28h]
0x140021318  add     r12, 8
0x14002131c  mov     rdx, r12; struct _GUID *
0x14002131f  call    ?MbbWwanReferenceSessionForIfGuid@@YAPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_MINIPORT_ADAPTER_CONTEXT@@AEAU_GUID@@@Z; MbbWwanReferenceSessionForIfGuid(_MINIPORT_ADAPTER_CONTEXT *,_GUID &)
0x140021324  mov     rsi, rax
0x140021327  test    rax, rax
0x14002132a  jnz     loc_14002142E
0x140021330  lea     rbx, WPP_RECORDER_INITIALIZED
0x140021337  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14002133e  jz      short loc_14002136B
0x140021340  mov     rcx, cs:WPP_GLOBAL_Control
0x140021347  lea     rdi, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14002134e  lea     r9d, [rax+65h]
0x140021352  mov     [rsp+68h+var_40], r12
0x140021357  lea     r8d, [rax+3]
0x14002135b  mov     [rsp+68h+var_48], rdi
0x140021360  mov     dl, 2
0x140021362  mov     rcx, [rcx+40h]
0x140021366  call    WPP_RECORDER_SF__guid_
0x14002136b  mov     eax, cs:dword_14005E0C8
0x140021371  mov     edx, 0C0010015h
0x140021376  mov     r15d, edx
0x140021379  cmp     eax, 5
0x14002137c  jbe     loc_1400216B6
0x140021382  mov     r8, cs:qword_14005E0E0
0x140021389  mov     rcx, 400000000000h
0x140021393  mov     rax, cs:qword_14005E0D8
0x14002139a  test    rcx, rax
0x14002139d  jz      loc_1400216B6
0x1400213a3  mov     rax, r8
0x1400213a6  and     rax, rcx
0x1400213a9  cmp     rax, r8
0x1400213ac  jnz     loc_1400216B6
0x1400213b2  mov     eax, [r14+470h]
0x1400213b9  mov     [rbp+arg_8], eax
0x1400213bc  mov     rax, [r14+478h]
0x1400213c3  mov     [rbp+arg_0], 0
0x1400213ca  mov     [rbp+arg_18], r12
0x1400213ce  mov     rcx, [rax]
0x1400213d1  lea     rax, aSecondaryinter; "SecondaryInterfaceGuidInvalid"
0x1400213d8  mov     [rbp+var_10], rax
0x1400213dc  add     rcx, 28h ; '('
0x1400213e0  lea     rax, [rbp+arg_0]
0x1400213e4  mov     [rbp+arg_10], edx
0x1400213e7  mov     [rsp+68h+var_20], rax
0x1400213ec  lea     rdx, byte_140058AEB
0x1400213f3  lea     rax, [rbp+arg_8]
0x1400213f7  mov     [rbp+var_18], rcx
0x1400213fb  mov     [rsp+68h+var_28], rax
0x140021400  lea     rax, [rbp+arg_18]
0x140021404  mov     [rsp+68h+var_30], rax
0x140021409  lea     rax, [rbp+var_18]
0x14002140d  mov     [rsp+68h+var_38], rax
0x140021412  lea     rax, [rbp+var_10]
0x140021416  mov     [rsp+68h+var_40], rax
0x14002141b  lea     rax, [rbp+arg_10]
0x14002141f  mov     [rsp+68h+var_48], rax
0x140021424  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U3@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@533@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140021429  jmp     loc_1400216B6
0x14002142e  cmp     dword ptr [rax+44h], 0
0x140021432  jnz     loc_1400214ED
0x140021438  lea     rbx, WPP_RECORDER_INITIALIZED
0x14002143f  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140021446  jz      short loc_140021475
0x140021448  mov     rcx, cs:WPP_GLOBAL_Control
0x14002144f  lea     rdi, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x140021456  mov     r9d, 66h ; 'f'
0x14002145c  mov     [rsp+68h+var_40], r12
0x140021461  mov     dl, 2
0x140021463  mov     [rsp+68h+var_48], rdi
0x140021468  mov     rcx, [rcx+40h]
0x14002146c  lea     r8d, [r9-63h]
0x140021470  call    WPP_RECORDER_SF__guid_
0x140021475  mov     eax, cs:dword_14005E0C8
0x14002147b  mov     edx, 0C0010015h
0x140021480  mov     r15d, edx
0x140021483  cmp     eax, 5
0x140021486  jbe     loc_1400216AE
0x14002148c  mov     r8, cs:qword_14005E0E0
0x140021493  mov     rcx, 400000000000h
0x14002149d  mov     rax, cs:qword_14005E0D8
0x1400214a4  test    rcx, rax
0x1400214a7  jz      loc_1400216AE
0x1400214ad  mov     rax, r8
0x1400214b0  and     rax, rcx
0x1400214b3  cmp     rax, r8
0x1400214b6  jnz     loc_1400216AE
0x1400214bc  mov     eax, [r14+470h]
0x1400214c3  mov     [rbp+arg_8], eax
0x1400214c6  mov     rax, [r14+478h]
0x1400214cd  mov     [rbp+arg_0], 0
0x1400214d4  mov     rcx, [rax]
0x1400214d7  lea     rax, aAttempttodelet; "AttemptToDeletePrimaryInterface"
0x1400214de  mov     [rbp+arg_10], edx
0x1400214e1  lea     rdx, byte_140058BE9
0x1400214e8  jmp     loc_140021663
0x1400214ed  mov     rdx, rsi; struct _MINIPORT_INTERFACE_CONTEXT *
0x1400214f0  mov     rcx, r14; SpinLock
0x1400214f3  call    ?MbbUtilDisconnectOnDeleteMPDP@@YAHPEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_MINIPORT_INTERFACE_CONTEXT@@@Z; MbbUtilDisconnectOnDeleteMPDP(_MINIPORT_ADAPTER_CONTEXT *,_MINIPORT_INTERFACE_CONTEXT *)
0x1400214f8  lea     rdi, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x1400214ff  mov     r15d, eax
0x140021502  lea     rbx, WPP_RECORDER_INITIALIZED
0x140021509  cmp     eax, 103h
0x14002150e  jnz     short loc_140021540
0x140021510  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140021517  jz      short loc_14002153B
0x140021519  mov     rcx, cs:WPP_GLOBAL_Control
0x140021520  mov     r9d, 67h ; 'g'
0x140021526  mov     [rsp+68h+var_48], rdi
0x14002152b  mov     rcx, [rcx+40h]
0x14002152f  lea     r8d, [r9-64h]
0x140021533  mov     dl, r8b
0x140021536  call    WPP_RECORDER_SF_
0x14002153b  xor     r15d, r15d
0x14002153e  jmp     short loc_140021573
0x140021540  test    eax, eax
0x140021542  jz      short loc_140021573
0x140021544  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14002154b  jz      short loc_140021573
0x14002154d  mov     rcx, cs:WPP_GLOBAL_Control
0x140021554  mov     r9d, 68h ; 'h'
0x14002155a  mov     dword ptr [rsp+68h+var_40], eax
0x14002155e  mov     [rsp+68h+var_48], rdi
0x140021563  mov     rcx, [rcx+40h]
0x140021567  lea     r8d, [r9-65h]
0x14002156b  mov     dl, r8b
0x14002156e  call    WPP_RECORDER_SF_d
0x140021573  mov     r8, rsi; struct _MINIPORT_INTERFACE_CONTEXT *
0x140021576  mov     edx, r15d; int
0x140021579  mov     rcx, r13; struct _MBB_REQUEST_CONTEXT *
0x14002157c  call    ?MbbUtilIndicateMPDPState@@YAXPEAU_MBB_REQUEST_CONTEXT@@HPEAU_MINIPORT_INTERFACE_CONTEXT@@@Z; MbbUtilIndicateMPDPState(_MBB_REQUEST_CONTEXT *,int,_MINIPORT_INTERFACE_CONTEXT *)
0x140021581  mov     rax, cs:qword_14005F548
0x140021588  mov     rdx, [rsi+8]
0x14002158c  mov     rcx, cs:NetDriverGlobals
0x140021593  call    _guard_dispatch_icall
0x140021598  mov     r13d, [rsi+44h]
0x14002159c  mov     rdx, rsi; struct _MINIPORT_INTERFACE_CONTEXT *
0x14002159f  mov     rcx, r14; SpinLock
0x1400215a2  call    ?MbbWwanRemoveSessionFromAdapterList@@YA_NPEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_MINIPORT_INTERFACE_CONTEXT@@@Z; MbbWwanRemoveSessionFromAdapterList(_MINIPORT_ADAPTER_CONTEXT *,_MINIPORT_INTERFACE_CONTEXT *)
0x1400215a7  test    al, al
0x1400215a9  jz      short loc_1400215C9
0x1400215ab  mov     rax, cs:WdfFunctions_01031
0x1400215b2  mov     rdx, [rsi+8]
0x1400215b6  mov     rcx, cs:WdfDriverGlobals
0x1400215bd  mov     rax, [rax+680h]
0x1400215c4  call    _guard_dispatch_icall
0x1400215c9  mov     r15d, 10001h
0x1400215cf  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400215d6  jz      short loc_1400215FE
0x1400215d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400215df  mov     r9d, 69h ; 'i'
0x1400215e5  mov     [rsp+68h+var_40], r12
0x1400215ea  mov     dl, 4
0x1400215ec  mov     [rsp+68h+var_48], rdi
0x1400215f1  mov     rcx, [rcx+40h]
0x1400215f5  lea     r8d, [r9-66h]
0x1400215f9  call    WPP_RECORDER_SF__guid_
0x1400215fe  mov     eax, cs:dword_14005E0C8
0x140021604  cmp     eax, 5
0x140021607  jbe     loc_1400216AE
0x14002160d  mov     rdx, cs:qword_14005E0E0
0x140021614  mov     rcx, 400000000000h
0x14002161e  mov     rax, cs:qword_14005E0D8
0x140021625  test    rcx, rax
0x140021628  jz      loc_1400216AE
0x14002162e  mov     rax, rdx
0x140021631  and     rax, rcx
0x140021634  cmp     rax, rdx
0x140021637  jnz     short loc_1400216AE
0x140021639  mov     eax, [r14+470h]
0x140021640  lea     rdx, dword_140058A6C
0x140021647  mov     [rbp+arg_8], eax
0x14002164a  mov     rax, [r14+478h]
0x140021651  mov     [rbp+arg_0], r13d
0x140021655  mov     rcx, [rax]
0x140021658  lea     rax, aMbbcxcompleted_0; "MbbCxcompleted"
0x14002165f  mov     [rbp+arg_10], r15d
0x140021663  mov     [rbp+var_18], rax
0x140021667  add     rcx, 28h ; '('
0x14002166b  lea     rax, [rbp+arg_0]
0x14002166f  mov     [rbp+arg_18], r12
0x140021673  mov     [rsp+68h+var_20], rax
0x140021678  lea     rax, [rbp+arg_8]
0x14002167c  mov     [rsp+68h+var_28], rax
0x140021681  lea     rax, [rbp+arg_18]
0x140021685  mov     [rsp+68h+var_30], rax
0x14002168a  lea     rax, [rbp+var_10]
0x14002168e  mov     [rsp+68h+var_38], rax
0x140021693  lea     rax, [rbp+var_18]
0x140021697  mov     [rsp+68h+var_40], rax
0x14002169c  lea     rax, [rbp+arg_10]
0x1400216a0  mov     [rsp+68h+var_48], rax
0x1400216a5  mov     [rbp+var_10], rcx
0x1400216a9  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U3@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@533@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400216ae  mov     rcx, rsi; struct _MINIPORT_INTERFACE_CONTEXT *
0x1400216b1  call    ?DereferenceSession@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@@Z; DereferenceSession(_MINIPORT_INTERFACE_CONTEXT *)
0x1400216b6  mov     eax, r15d
0x1400216b9  add     rsp, 68h
0x1400216bd  pop     r15
0x1400216bf  pop     r14
0x1400216c1  pop     r13
0x1400216c3  pop     r12
0x1400216c5  pop     rdi
0x1400216c6  pop     rsi
0x1400216c7  pop     rbx
0x1400216c8  pop     rbp
0x1400216c9  retn
```
