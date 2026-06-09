# wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x1800187a0`
- end: `0x180018f8d`
- name: `?ReportStopActivity@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `2029`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007d60`
- `0x1800082b4`
- `0x180008374`
- `0x180008780`
- `0x180008cc0`
- `0x180009250`
- `0x1800099f0`
- `0x18000a2a0`
- `0x18000de40`
- `0x18000e010`
- `0x18000fb20`

## callees

- `0x1800187a0`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018e01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018e01`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180018c8b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180018f33`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180018c8b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180018f33`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800188f8`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180018d7d`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800188f8`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180018d7d`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800188dd`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180018d62`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800188dd`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180018d62`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180018834`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180018cb9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180018834`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180018cb9`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180018927`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180018dac`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180018927`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180018dac`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        _QWORD *a1,
        int a2)
{
  _QWORD *v3; // r12
  __int64 v4; // rdi
  int v5; // eax
  __int64 v6; // rdi
  _QWORD *v7; // rsi
  ULONGLONG *v8; // r9
  _QWORD *v9; // rdx
  int *v10; // rdx
  const unsigned __int16 *v11; // r8
  int *v12; // r9
  const unsigned __int16 *v13; // r10
  const unsigned __int16 *v14; // r11
  int *v15; // r14
  const unsigned __int16 *v16; // r15
  const unsigned __int16 *v17; // r12
  __int64 v18; // rax
  __int64 v19; // rcx
  bool v20; // zf
  int v21; // ecx
  __int64 v22; // rcx
  int v23; // ecx
  __int64 v24; // rcx
  int v25; // ecx
  __int64 v26; // rcx
  int v27; // ecx
  __int64 v28; // rcx
  int v29; // ecx
  __int64 v30; // rcx
  int v31; // ecx
  __int64 v32; // rcx
  int v33; // ecx
  int v34; // eax
  _QWORD *v35; // rcx
  _QWORD *v36; // rdi
  ULONGLONG *v37; // r9
  __int64 v38; // r14
  __int64 v39; // rax
  int *v40; // rsi
  const unsigned __int16 *v41; // rdi
  DWORD CurrentThreadId; // eax
  const GUID *v43; // r8
  __int64 v44; // rax
  __int64 v45; // rcx
  int v46; // ecx
  int v47; // eax
  WINBOOL fPending[2]; // [rsp+38h] [rbp-D0h] BYREF
  LPVOID Context; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v51; // [rsp+48h] [rbp-C0h] BYREF
  int v52; // [rsp+4Ch] [rbp-BCh] BYREF
  int v53; // [rsp+50h] [rbp-B8h] BYREF
  int v54; // [rsp+54h] [rbp-B4h] BYREF
  __int64 v55; // [rsp+58h] [rbp-B0h] BYREF
  LPCGUID ActivityId; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD *v57; // [rsp+68h] [rbp-A0h]
  _QWORD ProviderId[3]; // [rsp+70h] [rbp-98h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v59; // [rsp+88h] [rbp-80h] BYREF
  int *v60; // [rsp+98h] [rbp-70h]
  int v61; // [rsp+A0h] [rbp-68h]
  int v62; // [rsp+A4h] [rbp-64h]
  LPCGUID *p_ActivityId; // [rsp+A8h] [rbp-60h]
  __int64 v64; // [rsp+B0h] [rbp-58h]
  int *v65; // [rsp+B8h] [rbp-50h]
  __int64 v66; // [rsp+C0h] [rbp-48h]
  LPVOID *p_Context; // [rsp+C8h] [rbp-40h]
  __int64 v68; // [rsp+D0h] [rbp-38h]
  const unsigned __int16 *v69; // [rsp+D8h] [rbp-30h]
  int v70; // [rsp+E0h] [rbp-28h]
  int v71; // [rsp+E4h] [rbp-24h]
  int *v72; // [rsp+E8h] [rbp-20h]
  int v73; // [rsp+F0h] [rbp-18h]
  int v74; // [rsp+F4h] [rbp-14h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+F8h] [rbp-10h] BYREF
  char *v76; // [rsp+108h] [rbp+0h]
  int v77; // [rsp+110h] [rbp+8h]
  int v78; // [rsp+114h] [rbp+Ch]
  _QWORD *v79; // [rsp+118h] [rbp+10h]
  __int64 v80; // [rsp+120h] [rbp+18h]
  int *v81; // [rsp+128h] [rbp+20h]
  __int64 v82; // [rsp+130h] [rbp+28h]
  const unsigned __int16 *v83; // [rsp+138h] [rbp+30h]
  int v84; // [rsp+140h] [rbp+38h]
  int v85; // [rsp+144h] [rbp+3Ch]
  unsigned int *v86; // [rsp+148h] [rbp+40h]
  __int64 v87; // [rsp+150h] [rbp+48h]
  const unsigned __int16 *v88; // [rsp+158h] [rbp+50h]
  int v89; // [rsp+160h] [rbp+58h]
  int v90; // [rsp+164h] [rbp+5Ch]
  __int64 *v91; // [rsp+168h] [rbp+60h]
  __int64 v92; // [rsp+170h] [rbp+68h]
  int *v93; // [rsp+178h] [rbp+70h]
  int v94; // [rsp+180h] [rbp+78h]
  int v95; // [rsp+184h] [rbp+7Ch]
  int *v96; // [rsp+188h] [rbp+80h]
  __int64 v97; // [rsp+190h] [rbp+88h]
  const unsigned __int16 *v98; // [rsp+198h] [rbp+90h]
  int v99; // [rsp+1A0h] [rbp+98h]
  int v100; // [rsp+1A4h] [rbp+9Ch]
  int *v101; // [rsp+1A8h] [rbp+A0h]
  __int64 v102; // [rsp+1B0h] [rbp+A8h]
  const unsigned __int16 *v103; // [rsp+1B8h] [rbp+B0h]
  int v104; // [rsp+1C0h] [rbp+B8h]
  int v105; // [rsp+1C4h] [rbp+BCh]
  int *v106; // [rsp+1C8h] [rbp+C0h]
  int v107; // [rsp+1D0h] [rbp+C8h]
  int v108; // [rsp+1D4h] [rbp+CCh]
  WINBOOL *v109; // [rsp+1D8h] [rbp+D0h]
  __int64 v110; // [rsp+1E0h] [rbp+D8h]
  const unsigned __int16 *v111; // [rsp+1E8h] [rbp+E0h]
  int v112; // [rsp+1F0h] [rbp+E8h]
  int v113; // [rsp+1F4h] [rbp+ECh]
  int *v114; // [rsp+1F8h] [rbp+F0h]
  int v115; // [rsp+200h] [rbp+F8h]
  int v116; // [rsp+204h] [rbp+FCh]

  v57 = a1;
  v3 = a1;
  if ( a2 < 0 )
  {
    v4 = a1[34];
    v5 = *(_DWORD *)(v4 + 72);
    if ( v5 < 0 && (v6 = v4 + 80, v5 == *(_DWORD *)(v6 + 8)) && v6 )
    {
      Context = 0;
      fPending[0] = 0;
      if ( InitOnceBeginInitialize(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, fPending, &Context) && fPending[0] )
      {
        qword_18004A768 = 0;
        Context = &qword_18004A760;
        qword_18004A760 = (__int64)&wil::details::FeatureLogging::`vftable';
        byte_18004A770 = 0;
        dword_18004A774 = 0;
        CallbackContext = &`WnsCPTracelogger::StaticHandle::StaticHandle'::`2'::__hInner;
        atexit(_lambda_633a74d489e420a2ff0e92495a1626f6_::_lambda_invoker_cdecl_);
        v7 = CallbackContext;
        qword_18004A768 = (__int64)CallbackContext;
        byte_18004A770 = 1;
        *(_OWORD *)&ProviderId[1] = *(_OWORD *)(*((_QWORD *)CallbackContext + 1) - 16LL);
        if ( *((_QWORD *)CallbackContext + 4) )
          __fastfail(5u);
        v8 = (ULONGLONG *)((char *)CallbackContext + 32);
        *((_QWORD *)CallbackContext + 5) = 0;
        v7[6] = 0;
        if ( !EventRegister((LPCGUID)&ProviderId[1], tlgEnableCallback, v7, v8) )
          EventSetInformation(v7[4], 2, v7[1], *(unsigned __int16 *)v7[1]);
        dword_18004A774 = 1;
        (*(void (__fastcall **)(__int64 *))(qword_18004A760 + 8))(&qword_18004A760);
        InitOnceComplete(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &qword_18004A760);
      }
      v9 = (_QWORD *)*((_QWORD *)Context + 1);
      Context = v9;
      if ( *(_DWORD *)v9 > 2u && (v9[2] & 0x200000000000LL) != 0 && (v9[3] & 0x200000000000LL) == v9[3] )
      {
        v10 = *(int **)(v6 + 120);
        v11 = *(const unsigned __int16 **)(v6 + 112);
        v12 = *(int **)(v6 + 96);
        v13 = *(const unsigned __int16 **)(v6 + 88);
        v14 = *(const unsigned __int16 **)(v6 + 72);
        v15 = *(int **)(v6 + 24);
        v16 = *(const unsigned __int16 **)(v6 + 128);
        v17 = *(const unsigned __int16 **)(v6 + 56);
        fPending[0] = *(_DWORD *)(v6 + 104);
        v53 = *(_DWORD *)(v6 + 80);
        v54 = *(_DWORD *)(v6 + 32);
        LODWORD(v55) = *(_DWORD *)v6;
        v51 = *(_DWORD *)(v6 + 64);
        v52 = *(_DWORD *)(v6 + 8);
        ProviderId[0] = 0x1000000;
        ActivityId = (LPCGUID)(v57[34] + 8LL);
        v18 = -1;
        if ( v10 )
        {
          v19 = -1;
          do
            v20 = *((_WORD *)v10 + ++v19) == 0;
          while ( !v20 );
          v21 = 2 * v19 + 2;
        }
        else
        {
          v10 = &dword_18003A074;
          v21 = 2;
        }
        v114 = v10;
        v115 = v21;
        v116 = 0;
        if ( v11 )
        {
          v22 = -1;
          do
            ++v22;
          while ( *((_BYTE *)v11 + v22) );
          v23 = v22 + 1;
        }
        else
        {
          v11 = &byte_18003A073;
          v23 = 1;
        }
        v112 = v23;
        v109 = fPending;
        v111 = v11;
        v113 = 0;
        v110 = 4;
        if ( v12 )
        {
          v24 = -1;
          do
            v20 = *((_WORD *)v12 + ++v24) == 0;
          while ( !v20 );
          v25 = 2 * v24 + 2;
        }
        else
        {
          v12 = &dword_18003A074;
          v25 = 2;
        }
        v106 = v12;
        v107 = v25;
        v108 = 0;
        if ( v13 )
        {
          v26 = -1;
          do
            ++v26;
          while ( *((_BYTE *)v13 + v26) );
          v27 = v26 + 1;
        }
        else
        {
          v13 = &byte_18003A073;
          v27 = 1;
        }
        v104 = v27;
        v101 = &v53;
        v103 = v13;
        v105 = 0;
        v102 = 4;
        if ( v14 )
        {
          v28 = -1;
          do
            ++v28;
          while ( *((_BYTE *)v14 + v28) );
          v29 = v28 + 1;
        }
        else
        {
          v14 = &byte_18003A073;
          v29 = 1;
        }
        v99 = v29;
        v96 = &v54;
        v98 = v14;
        v100 = 0;
        v97 = 4;
        if ( v15 )
        {
          v30 = -1;
          do
            v20 = *((_WORD *)v15 + ++v30) == 0;
          while ( !v20 );
          v31 = 2 * v30 + 2;
        }
        else
        {
          v15 = &dword_18003A074;
          v31 = 2;
        }
        v94 = v31;
        v91 = &v55;
        v93 = v15;
        v95 = 0;
        v92 = 4;
        if ( v16 )
        {
          v32 = -1;
          do
            ++v32;
          while ( *((_BYTE *)v16 + v32) );
          v33 = v32 + 1;
        }
        else
        {
          v16 = &byte_18003A073;
          v33 = 1;
        }
        v89 = v33;
        v86 = &v51;
        v88 = v16;
        v90 = 0;
        v87 = 4;
        if ( v17 )
        {
          do
            ++v18;
          while ( *((_BYTE *)v17 + v18) );
          v34 = v18 + 1;
        }
        else
        {
          v17 = &byte_18003A073;
          v34 = 1;
        }
        v35 = Context;
        v84 = v34;
        v83 = v17;
        v81 = &v52;
        v79 = ProviderId;
        UserData.Ptr = *((_QWORD *)Context + 1);
        v85 = 0;
        v82 = 4;
        v80 = 8;
        ProviderId[1] = 0x20B000000LL;
        ProviderId[2] = 0x200000000000LL;
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        v76 = &byte_18003D85F;
        UserData.Reserved = 2;
        v77 = 267;
        v78 = 1;
        LODWORD(Context) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(v35[4], (PCEVENT_DESCRIPTOR)&ProviderId[1], ActivityId, 0, 0x11u, &UserData);
        v3 = v57;
      }
    }
    else
    {
      Context = 0;
      fPending[0] = 0;
      if ( InitOnceBeginInitialize(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, fPending, &Context) && fPending[0] )
      {
        qword_18004A768 = 0;
        Context = &qword_18004A760;
        qword_18004A760 = (__int64)&wil::details::FeatureLogging::`vftable';
        byte_18004A770 = 0;
        dword_18004A774 = 0;
        CallbackContext = &`WnsCPTracelogger::StaticHandle::StaticHandle'::`2'::__hInner;
        atexit(_lambda_633a74d489e420a2ff0e92495a1626f6_::_lambda_invoker_cdecl_);
        v36 = CallbackContext;
        qword_18004A768 = (__int64)CallbackContext;
        byte_18004A770 = 1;
        *(_OWORD *)&ProviderId[1] = *(_OWORD *)(*((_QWORD *)CallbackContext + 1) - 16LL);
        if ( *((_QWORD *)CallbackContext + 4) )
          __fastfail(5u);
        v37 = (ULONGLONG *)((char *)CallbackContext + 32);
        *((_QWORD *)CallbackContext + 5) = 0;
        v36[6] = 0;
        if ( !EventRegister((LPCGUID)&ProviderId[1], tlgEnableCallback, v36, v37) )
          EventSetInformation(v36[4], 2, v36[1], *(unsigned __int16 *)v36[1]);
        dword_18004A774 = 1;
        (*(void (__fastcall **)(__int64 *))(qword_18004A760 + 8))(&qword_18004A760);
        InitOnceComplete(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &qword_18004A760);
      }
      v38 = *((_QWORD *)Context + 1);
      if ( *(_DWORD *)v38 > 2u
        && (*(_QWORD *)(v38 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(v38 + 24) & 0x200000000000LL) == *(_QWORD *)(v38 + 24) )
      {
        v39 = v3[34];
        v40 = *(int **)(v39 + 56);
        v41 = *(const unsigned __int16 **)(v39 + 48);
        CurrentThreadId = GetCurrentThreadId();
        v43 = (const GUID *)(v3[34] + 8LL);
        LODWORD(Context) = CurrentThreadId;
        v52 = a2;
        v44 = -1;
        ActivityId = (LPCGUID)0x1000000;
        if ( v40 )
        {
          v45 = -1;
          do
            v20 = *((_WORD *)v40 + ++v45) == 0;
          while ( !v20 );
          v46 = 2 * v45 + 2;
        }
        else
        {
          v40 = &dword_18003A074;
          v46 = 2;
        }
        v72 = v40;
        v73 = v46;
        v74 = 0;
        if ( v41 )
        {
          do
            ++v44;
          while ( *((_BYTE *)v41 + v44) );
          v47 = v44 + 1;
        }
        else
        {
          v41 = &byte_18003A073;
          v47 = 1;
        }
        v70 = v47;
        v69 = v41;
        p_Context = &Context;
        v71 = 0;
        v65 = &v52;
        p_ActivityId = &ActivityId;
        v59.Ptr = *(_QWORD *)(v38 + 8);
        v68 = 4;
        v66 = 4;
        v64 = 8;
        ProviderId[1] = 0x20B000000LL;
        ProviderId[2] = 0x200000000000LL;
        v59.Size = *(unsigned __int16 *)v59.Ptr;
        v60 = &dword_18003D7E4;
        v59.Reserved = 2;
        v61 = 111;
        v62 = 1;
        v51 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(*(_QWORD *)(v38 + 32), (PCEVENT_DESCRIPTOR)&ProviderId[1], v43, 0, 7u, &v59);
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*v3 + 8LL))(v3);
}

```

## disassembly

```asm
0x1800187a0  mov     r11, rsp
0x1800187a3  push    rbp
0x1800187a4  push    r12
0x1800187a6  push    r15
0x1800187a8  lea     rbp, [r11-138h]
0x1800187af  sub     rsp, 220h
0x1800187b6  mov     rax, cs:__security_cookie
0x1800187bd  xor     rax, rsp
0x1800187c0  mov     [rbp+130h+var_30], rax
0x1800187c7  mov     [rsp+230h+var_1D0], rcx
0x1800187cc  mov     r15d, edx
0x1800187cf  mov     r12, rcx
0x1800187d2  test    edx, edx
0x1800187d4  jns     loc_180018F61
0x1800187da  mov     [r11+20h], rdi
0x1800187de  mov     rdi, [rcx+110h]
0x1800187e5  mov     [r11+10h], rbx
0x1800187e9  mov     [r11+18h], rsi
0x1800187ed  mov     [r11-20h], r13
0x1800187f1  mov     eax, [rdi+48h]
0x1800187f4  mov     [r11-28h], r14
0x1800187f8  test    eax, eax
0x1800187fa  jns     loc_180018C9B
0x180018800  add     rdi, 50h ; 'P'
0x180018804  cmp     eax, [rdi+8]
0x180018807  jnz     loc_180018C9B
0x18001880d  test    rdi, rdi
0x180018810  jz      loc_180018C9B
0x180018816  xor     ebx, ebx
0x180018818  lea     r9, [rsp+230h+Context]; lpContext
0x18001881d  lea     r8, [rsp+230h+fPending]; fPending
0x180018822  mov     [rsp+230h+Context], rbx
0x180018827  xor     edx, edx; dwFlags
0x180018829  mov     [rsp+230h+fPending], ebx
0x18001882d  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x180018834  call    cs:__imp_InitOnceBeginInitialize
0x18001883a  test    eax, eax
0x18001883c  jz      loc_18001892D
0x180018842  cmp     [rsp+230h+fPending], ebx
0x180018846  jz      loc_18001892D
0x18001884c  lea     r14, qword_18004A760
0x180018853  mov     cs:qword_18004A768, rbx
0x18001885a  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180018861  mov     [rsp+230h+Context], r14
0x180018866  mov     cs:qword_18004A760, rax
0x18001886d  mov     cs:byte_18004A770, bl
0x180018873  mov     cs:dword_18004A774, ebx
0x180018879  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WnsCPTracelogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180018880  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x180018887  mov     cs:CallbackContext, rax
0x18001888e  call    atexit
0x180018893  mov     rsi, cs:CallbackContext
0x18001889a  mov     cs:qword_18004A768, rsi
0x1800188a1  mov     cs:byte_18004A770, 1
0x1800188a8  mov     rax, [rsi+8]
0x1800188ac  movups  xmm0, xmmword ptr [rax-10h]
0x1800188b0  movups  xmmword ptr [rsp+230h+ProviderId+8], xmm0
0x1800188b5  cmp     [rsi+20h], rbx
0x1800188b9  jz      short loc_1800188C2
0x1800188bb  mov     ecx, 5
0x1800188c0  int     29h; Win8: RtlFailFast(ecx)
0x1800188c2  lea     r9, [rsi+20h]; RegHandle
0x1800188c6  mov     [rsi+28h], rbx
0x1800188ca  mov     r8, rsi; CallbackContext
0x1800188cd  mov     [rsi+30h], rbx
0x1800188d1  lea     rdx, _tlgEnableCallback; EnableCallback
0x1800188d8  lea     rcx, [rsp+230h+ProviderId+8]; ProviderId
0x1800188dd  call    cs:__imp_EventRegister
0x1800188e3  test    eax, eax
0x1800188e5  jnz     short loc_1800188FE
0x1800188e7  mov     r8, [rsi+8]
0x1800188eb  mov     edx, 2
0x1800188f0  mov     rcx, [rsi+20h]
0x1800188f4  movzx   r9d, word ptr [r8]
0x1800188f8  call    cs:__imp_EventSetInformation
0x1800188fe  mov     rax, cs:qword_18004A760
0x180018905  mov     rcx, r14
0x180018908  mov     cs:dword_18004A774, 1
0x180018912  mov     rax, [rax+8]
0x180018916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001891b  mov     r8, r14; lpContext
0x18001891e  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x180018925  xor     edx, edx; dwFlags
0x180018927  call    cs:__imp_InitOnceComplete
0x18001892d  mov     rax, [rsp+230h+Context]
0x180018932  mov     rdx, [rax+8]
0x180018936  mov     [rsp+230h+Context], rdx
0x18001893b  mov     eax, [rdx]
0x18001893d  cmp     eax, 2
0x180018940  jbe     loc_180018F39
0x180018946  mov     rcx, [rdx+18h]
0x18001894a  mov     r13, 200000000000h
0x180018954  mov     rax, [rdx+10h]
0x180018958  test    r13, rax
0x18001895b  jz      loc_180018F39
0x180018961  mov     rax, rcx
0x180018964  and     rax, r13
0x180018967  cmp     rax, rcx
0x18001896a  jnz     loc_180018F39
0x180018970  mov     eax, [rdi+68h]
0x180018973  lea     rsi, dword_18003A074
0x18001897a  mov     rdx, [rdi+78h]
0x18001897e  mov     r8, [rdi+70h]
0x180018982  mov     r9, [rdi+60h]
0x180018986  mov     r10, [rdi+58h]
0x18001898a  mov     r11, [rdi+48h]
0x18001898e  mov     r14, [rdi+18h]
0x180018992  mov     r15, [rdi+80h]
0x180018999  mov     r12, [rdi+38h]
0x18001899d  mov     [rsp+230h+fPending], eax
0x1800189a1  mov     eax, [rdi+50h]
0x1800189a4  mov     [rsp+230h+var_1E8], eax
0x1800189a8  mov     eax, [rdi+20h]
0x1800189ab  mov     [rsp+230h+var_1E4], eax
0x1800189af  mov     eax, [rdi]
0x1800189b1  mov     dword ptr [rsp+230h+var_1E0], eax
0x1800189b5  mov     eax, [rdi+40h]
0x1800189b8  mov     [rsp+230h+var_1F0], eax
0x1800189bc  mov     eax, [rdi+8]
0x1800189bf  mov     [rsp+230h+var_1EC], eax
0x1800189c3  mov     rax, [rsp+230h+var_1D0]
0x1800189c8  mov     qword ptr [rsp+230h+ProviderId], 1000000h
0x1800189d1  mov     rax, [rax+110h]
0x1800189d8  add     rax, 8
0x1800189dc  mov     [rsp+230h+ActivityId], rax
0x1800189e1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800189e8  test    rdx, rdx
0x1800189eb  jz      short loc_180018A04
0x1800189ed  mov     rcx, rax
0x1800189f0  cmp     [rdx+rcx*2+2], bx
0x1800189f5  lea     rcx, [rcx+1]
0x1800189f9  jnz     short loc_1800189F0
0x1800189fb  lea     ecx, ds:2[rcx*2]
0x180018a02  jmp     short loc_180018A0C
0x180018a04  mov     rdx, rsi
0x180018a07  mov     ecx, 2
0x180018a0c  mov     [rbp+130h+var_40], rdx
0x180018a13  lea     rdi, byte_18003A073
0x180018a1a  mov     [rbp+130h+var_38], ecx
0x180018a20  mov     [rbp+130h+var_34], ebx
0x180018a26  test    r8, r8
0x180018a29  jz      short loc_180018A3D
0x180018a2b  mov     rcx, rax
0x180018a2e  xchg    ax, ax
0x180018a30  inc     rcx
0x180018a33  cmp     [r8+rcx], bl
0x180018a37  jnz     short loc_180018A30
0x180018a39  inc     ecx
0x180018a3b  jmp     short loc_180018A45
0x180018a3d  mov     r8, rdi
0x180018a40  mov     ecx, 1
0x180018a45  mov     [rbp+130h+var_48], ecx
0x180018a4b  lea     rcx, [rsp+230h+fPending]
0x180018a50  mov     [rbp+130h+var_60], rcx
0x180018a57  mov     [rbp+130h+var_50], r8
0x180018a5e  mov     [rbp+130h+var_44], ebx
0x180018a64  mov     [rbp+130h+var_58], 4
0x180018a6f  test    r9, r9
0x180018a72  jz      short loc_180018A95
0x180018a74  mov     rcx, rax
0x180018a77  nop     word ptr [rax+rax+00000000h]
0x180018a80  cmp     [r9+rcx*2+2], bx
0x180018a86  lea     rcx, [rcx+1]
0x180018a8a  jnz     short loc_180018A80
0x180018a8c  lea     ecx, ds:2[rcx*2]
0x180018a93  jmp     short loc_180018A9D
0x180018a95  mov     r9, rsi
0x180018a98  mov     ecx, 2
0x180018a9d  mov     [rbp+130h+var_70], r9
0x180018aa4  mov     [rbp+130h+var_68], ecx
0x180018aaa  mov     [rbp+130h+var_64], ebx
0x180018ab0  test    r10, r10
0x180018ab3  jz      short loc_180018ACD
0x180018ab5  mov     rcx, rax
0x180018ab8  nop     dword ptr [rax+rax+00000000h]
0x180018ac0  inc     rcx
0x180018ac3  cmp     [r10+rcx], bl
0x180018ac7  jnz     short loc_180018AC0
0x180018ac9  inc     ecx
0x180018acb  jmp     short loc_180018AD5
0x180018acd  mov     r10, rdi
0x180018ad0  mov     ecx, 1
0x180018ad5  mov     [rbp+130h+var_78], ecx
0x180018adb  lea     rcx, [rsp+230h+var_1E8]
0x180018ae0  mov     [rbp+130h+var_90], rcx
0x180018ae7  mov     [rbp+130h+var_80], r10
0x180018aee  mov     [rbp+130h+var_74], ebx
0x180018af4  mov     [rbp+130h+var_88], 4
0x180018aff  test    r11, r11
0x180018b02  jz      short loc_180018B14
0x180018b04  mov     rcx, rax
0x180018b07  inc     rcx
0x180018b0a  cmp     [r11+rcx], bl
0x180018b0e  jnz     short loc_180018B07
0x180018b10  inc     ecx
0x180018b12  jmp     short loc_180018B1C
0x180018b14  mov     r11, rdi
0x180018b17  mov     ecx, 1
0x180018b1c  mov     [rbp+130h+var_98], ecx
0x180018b22  lea     rcx, [rsp+230h+var_1E4]
0x180018b27  mov     [rbp+130h+var_B0], rcx
0x180018b2e  mov     [rbp+130h+var_A0], r11
0x180018b35  mov     [rbp+130h+var_94], ebx
0x180018b3b  mov     [rbp+130h+var_A8], 4
0x180018b46  test    r14, r14
0x180018b49  jz      short loc_180018B65
0x180018b4b  mov     rcx, rax
0x180018b4e  xchg    ax, ax
0x180018b50  cmp     [r14+rcx*2+2], bx
0x180018b56  lea     rcx, [rcx+1]
0x180018b5a  jnz     short loc_180018B50
0x180018b5c  lea     ecx, ds:2[rcx*2]
0x180018b63  jmp     short loc_180018B6D
0x180018b65  mov     r14, rsi
0x180018b68  mov     ecx, 2
0x180018b6d  mov     [rbp+130h+var_B8], ecx
0x180018b70  lea     rcx, [rsp+230h+var_1E0]
0x180018b75  mov     [rbp+130h+var_D0], rcx
0x180018b79  mov     [rbp+130h+var_C0], r14
0x180018b7d  mov     [rbp+130h+var_B4], ebx
0x180018b80  mov     [rbp+130h+var_C8], 4
0x180018b88  test    r15, r15
0x180018b8b  jz      short loc_180018B9D
0x180018b8d  mov     rcx, rax
0x180018b90  inc     rcx
0x180018b93  cmp     [r15+rcx], bl
0x180018b97  jnz     short loc_180018B90
0x180018b99  inc     ecx
0x180018b9b  jmp     short loc_180018BA5
0x180018b9d  mov     r15, rdi
0x180018ba0  mov     ecx, 1
0x180018ba5  mov     [rbp+130h+var_D8], ecx
0x180018ba8  lea     rcx, [rsp+230h+var_1F0]
0x180018bad  mov     [rbp+130h+var_F0], rcx
0x180018bb1  mov     [rbp+130h+var_E0], r15
0x180018bb5  mov     [rbp+130h+var_D4], ebx
0x180018bb8  mov     [rbp+130h+var_E8], 4
0x180018bc0  test    r12, r12
0x180018bc3  jz      short loc_180018BD2
0x180018bc5  inc     rax
0x180018bc8  cmp     [r12+rax], bl
0x180018bcc  jnz     short loc_180018BC5
0x180018bce  inc     eax
0x180018bd0  jmp     short loc_180018BDA
0x180018bd2  mov     r12, rdi
0x180018bd5  mov     eax, 1
0x180018bda  mov     rcx, [rsp+230h+Context]
0x180018bdf  lea     rdx, _TraceLoggingMetadata
0x180018be6  mov     [rbp+130h+var_F8], eax
0x180018be9  xor     r9d, r9d; RelatedActivityId
0x180018bec  mov     [rbp+130h+var_100], r12
0x180018bf0  lea     rax, [rsp+230h+var_1EC]
0x180018bf5  mov     [rbp+130h+var_110], rax
0x180018bf9  lea     rax, [rsp+230h+ProviderId]
0x180018bfe  mov     [rbp+130h+var_120], rax
0x180018c02  movzx   eax, cs:word_18003D855
0x180018c09  mov     dword ptr [rsp+230h+ProviderId+0Ch], eax
0x180018c0d  mov     rax, [rcx+8]
0x180018c11  mov     [rbp+130h+var_140.Ptr], rax
0x180018c15  mov     [rbp+130h+var_F4], ebx
0x180018c18  mov     [rbp+130h+var_108], 4
0x180018c20  mov     [rbp+130h+var_118], 8
0x180018c28  mov     dword ptr [rsp+230h+ProviderId+8], 0B000000h
0x180018c30  mov     qword ptr [rsp+230h+ProviderId+10h], r13
0x180018c35  movzx   eax, word ptr [rax]
0x180018c38  mov     [rbp+130h+var_140.Size], eax
0x180018c3b  lea     rax, byte_18003D85F
0x180018c42  mov     [rbp+130h+var_130], rax
0x180018c46  lea     rax, _TraceLoggingMetadataEnd
0x180018c4d  sub     eax, edx
0x180018c4f  mov     dword ptr [rbp+130h+var_140.0Ch], 2
0x180018c56  mov     [rbp+130h+var_128], 10Bh
0x180018c5d  lea     rdx, [rsp+230h+ProviderId+8]; EventDescriptor
0x180018c62  mov     [rbp+130h+var_124], 1
0x180018c69  mov     dword ptr [rsp+230h+Context], eax
0x180018c6d  mov     eax, dword ptr [rsp+230h+Context]
0x180018c71  mov     r8, [rsp+230h+ActivityId]; ActivityId
0x180018c76  lea     rax, [rbp+130h+var_140]
0x180018c7a  mov     rcx, [rcx+20h]; RegHandle
0x180018c7e  mov     [rsp+230h+UserData], rax; UserData
0x180018c83  mov     [rsp+230h+UserDataCount], 11h; UserDataCount
0x180018c8b  call    cs:__imp_EventWriteTransfer
0x180018c91  mov     r12, [rsp+230h+var_1D0]
0x180018c96  jmp     loc_180018F39
0x180018c9b  xor     ebx, ebx
0x180018c9d  lea     r9, [rsp+230h+Context]; lpContext
0x180018ca2  lea     r8, [rsp+230h+fPending]; fPending
0x180018ca7  mov     [rsp+230h+Context], rbx
0x180018cac  xor     edx, edx; dwFlags
0x180018cae  mov     [rsp+230h+fPending], ebx
0x180018cb2  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x180018cb9  call    cs:__imp_InitOnceBeginInitialize
0x180018cbf  test    eax, eax
0x180018cc1  jz      loc_180018DB2
0x180018cc7  cmp     [rsp+230h+fPending], ebx
0x180018ccb  jz      loc_180018DB2
0x180018cd1  lea     r14, qword_18004A760
0x180018cd8  mov     cs:qword_18004A768, rbx
0x180018cdf  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180018ce6  mov     [rsp+230h+Context], r14
  ... truncated ...
```
