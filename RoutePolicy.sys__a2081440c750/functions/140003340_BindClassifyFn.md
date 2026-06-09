# BindClassifyFn

- ea: `0x140003340`
- end: `0x14000379b`
- name: `BindClassifyFn`
- size: `1115`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400063e0`

## callees

- `0x140001008`
- `0x1400030dc`
- `0x140003340`
- `0x140007d28`
- `0x140007d7c`
- `0x14000a680`
- `0x14000a6c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140003591`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003684`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400036f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003591`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003684`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400036f8`
- `ntoskrnl!ExAllocatePool2` at `0x1400034ba`
- `ntoskrnl!ExAllocatePool2` at `0x1400034ba`
- `fwpkclnt!FwpsApplyModifiedLayerData0` at `0x140003514`
- `fwpkclnt!FwpsApplyModifiedLayerData0` at `0x140003514`
- `fwpkclnt!FwpsPendClassify0` at `0x1400036a9`
- `fwpkclnt!FwpsPendClassify0` at `0x1400036a9`
- `fwpkclnt!FwpsAcquireClassifyHandle0` at `0x140003394`
- `fwpkclnt!FwpsAcquireClassifyHandle0` at `0x140003394`
- `fwpkclnt!FwpsReleaseClassifyHandle0` at `0x14000344b`
- `fwpkclnt!FwpsReleaseClassifyHandle0` at `0x14000344b`
- `fwpkclnt!FwpsAcquireWritableLayerDataPointer0` at `0x140003400`
- `fwpkclnt!FwpsAcquireWritableLayerDataPointer0` at `0x140003400`

## string_xrefs

- `0x140003567`: `WdfWorkItemCreate for RoutePolicyAsyncRedirectRoutine failed`

## pseudocode

```c
void __fastcall BindClassifyFn(__int64 a1, void *a2, UINT64 *a3, __int64 a4)
{
  NTSTATUS v7; // eax
  int v8; // r8d
  int v9; // r9d
  UINT64 v10; // rdx
  NTSTATUS v11; // eax
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rcx
  __int64 Pool2; // rax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  _QWORD *v19; // rsi
  _QWORD *v20; // r14
  int v21; // eax
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // rax
  char v25; // bl
  __int16 v26; // di
  __int64 v27; // rax
  PVOID *v28; // rbx
  __int64 v29; // rdx
  int v30; // eax
  int v31; // r8d
  int v32; // r9d
  NTSTATUS v33; // eax
  int v34; // r8d
  int v35; // r9d
  char *v36; // rax
  PVOID *v37; // rcx
  _DWORD v38[4]; // [rsp+30h] [rbp-69h] BYREF
  __int128 v39; // [rsp+40h] [rbp-59h] BYREF
  PVOID writableLayerData; // [rsp+50h] [rbp-49h] BYREF
  __int128 v41; // [rsp+58h] [rbp-41h] BYREF
  __int64 v42; // [rsp+68h] [rbp-31h]
  __int64 v43; // [rsp+70h] [rbp-29h]
  __int128 v44; // [rsp+78h] [rbp-21h]
  __int64 *v45; // [rsp+88h] [rbp-11h]
  UINT64 classifyHandle; // [rsp+98h] [rbp-1h] BYREF
  _QWORD v47[3]; // [rsp+A0h] [rbp+7h] BYREF

  if ( (*(_DWORD *)(a4 + 24) & 1) != 0 )
  {
    classifyHandle = 0;
    v7 = FwpsAcquireClassifyHandle0(a2, 0, &classifyHandle);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v38[0] = v7;
        *(_QWORD *)&v39 = "FwpsAcquireClassifyHandle failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          dword_140012050,
          (unsigned int)byte_14000EE41,
          v8,
          v9,
          (__int64)&v39,
          (__int64)v38);
      }
      return;
    }
    v10 = *a3;
    writableLayerData = 0;
    v11 = FwpsAcquireWritableLayerDataPointer0(classifyHandle, v10, 0, &writableLayerData, (FWPS_CLASSIFY_OUT0 *)a4);
    if ( v11 < 0 )
    {
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v38[0] = v11;
        *(_QWORD *)&v39 = "FwpsAcquireWritableLayerDataPointer failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          dword_140012050,
          (unsigned int)byte_14000FA13,
          v12,
          v13,
          (__int64)&v39,
          (__int64)v38);
      }
      goto LABEL_8;
    }
    v45 = off_140012040;
    v42 = 0;
    v43 = 0x100000001LL;
    v41 = 0;
    LODWORD(v41) = 56;
    v44 = 0;
    v14 = *((_QWORD *)RoutePolicyCallout::g_pCalloutContext + 3);
    v47[2] = 0;
    *(_QWORD *)&v44 = v14;
    v47[0] = 24;
    v47[1] = RoutePolicyAsyncRedirectRoutine;
    Pool2 = ExAllocatePool2(64, 24, 1684435058);
    v19 = (_QWORD *)Pool2;
    if ( !Pool2 )
    {
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v38[0] = -1073741670;
        *(_QWORD *)&v39 = "Failed to allocate work item list entry";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v16,
          (unsigned int)&word_14000FB5E,
          v17,
          v18,
          (__int64)&v39,
          (__int64)v38);
      }
      goto LABEL_12;
    }
    v20 = (_QWORD *)(Pool2 + 16);
    v21 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD *, __int128 *, __int64))(WdfFunctions_01015 + 3032))(
            WdfDriverGlobals,
            v47,
            &v41,
            Pool2 + 16);
    if ( v21 < 0 )
    {
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v38[0] = v21;
        *(_QWORD *)&v39 = "WdfWorkItemCreate for RoutePolicyAsyncRedirectRoutine failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          dword_140012050,
          (unsigned int)&word_14000F196,
          v22,
          v23,
          (__int64)&v39,
          (__int64)v38);
      }
      ExFreePoolWithTag(v19, 0x64667072u);
      goto LABEL_12;
    }
    v24 = *(_QWORD *)(a1 + 8);
    v25 = *(_BYTE *)(v24 + 88);
    v26 = __ROR2__(*(_WORD *)(v24 + 72), 8);
    v27 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01015 + 1616))(
            WdfDriverGlobals,
            *v20,
            off_140012040);
    *(_QWORD *)v27 = classifyHandle;
    *(_OWORD *)(v27 + 8) = *(_OWORD *)a4;
    *(_OWORD *)(v27 + 24) = *(_OWORD *)(a4 + 16);
    *(_QWORD *)(v27 + 40) = *(_QWORD *)(a4 + 32);
    *(_QWORD *)(v27 + 48) = *a3;
    *(_QWORD *)(v27 + 72) = writableLayerData;
    *(_BYTE *)(v27 + 64) = v25;
    v28 = (PVOID *)(v27 + 56);
    *(_WORD *)(v27 + 66) = v26;
    v30 = AppIdFromFilter(a3, v29, 7, v27 + 56);
    if ( v30 < 0 )
    {
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v38[0] = v30;
        *(_QWORD *)&v39 = "AppIdFromFilter failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          dword_140012050,
          (unsigned int)&word_140010366,
          v31,
          v32,
          (__int64)&v39,
          (__int64)v38);
      }
LABEL_20:
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, *v20);
      ExFreePoolWithTag(v19, 0x64667072u);
LABEL_12:
      FwpsApplyModifiedLayerData0(classifyHandle, writableLayerData, 1u);
LABEL_8:
      FwpsReleaseClassifyHandle0(classifyHandle);
      return;
    }
    v33 = FwpsPendClassify0(classifyHandle, *a3, 0, (FWPS_CLASSIFY_OUT0 *)a4);
    if ( v33 < 0 )
    {
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v38[0] = v33;
        *(_QWORD *)&v39 = "FwpsPendClassify failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          dword_140012050,
          (unsigned int)word_140010302,
          v34,
          v35,
          (__int64)&v39,
          (__int64)v38);
      }
      ExFreePoolWithTag(*v28, 0x64667072u);
      goto LABEL_20;
    }
    AcquireSpinLock(&v39, (char *)RoutePolicyCallout::g_pCalloutContext + 40);
    v36 = (char *)RoutePolicyCallout::g_pCalloutContext + 64;
    v37 = (PVOID *)*((_QWORD *)RoutePolicyCallout::g_pCalloutContext + 9);
    if ( *v37 != (char *)RoutePolicyCallout::g_pCalloutContext + 64 )
      __fastfail(3u);
    *v19 = v36;
    v19[1] = v37;
    *v37 = v19;
    *((_QWORD *)v36 + 1) = v19;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 3040))(WdfDriverGlobals, *v20);
    if ( (_QWORD)v39 )
      SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v39);
  }
}

```

## disassembly

```asm
0x140003340  push    rbp
0x140003342  push    rbx
0x140003343  push    rsi
0x140003344  push    rdi
0x140003345  push    r12
0x140003347  push    r14
0x140003349  push    r15
0x14000334b  lea     rbp, [rsp-27h]
0x140003350  sub     rsp, 0C0h
0x140003357  mov     rax, cs:__security_cookie
0x14000335e  xor     rax, rsp
0x140003361  mov     [rbp+57h+var_38], rax
0x140003365  mov     r15, r9
0x140003368  mov     edi, 1
0x14000336d  mov     r12, r8
0x140003370  mov     r9, rdx
0x140003373  mov     rbx, rcx
0x140003376  mov     eax, [r15+18h]
0x14000337a  test    dil, al
0x14000337d  jz      loc_14000377C
0x140003383  lea     r8, [rbp+57h+classifyHandle]; classifyHandle
0x140003387  mov     [rbp+57h+classifyHandle], 0
0x14000338f  xor     edx, edx; flags
0x140003391  mov     rcx, r9; classifyContext
0x140003394  call    cs:__imp_FwpsAcquireClassifyHandle0
0x14000339b  nop     dword ptr [rax+rax+00h]
0x1400033a0  test    eax, eax
0x1400033a2  jns     short loc_1400033E4
0x1400033a4  mov     ecx, cs:dword_140012050
0x1400033aa  cmp     ecx, 2
0x1400033ad  jbe     loc_14000377C
0x1400033b3  mov     [rbp+57h+var_C0], eax
0x1400033b6  lea     rdx, byte_14000EE41
0x1400033bd  lea     rax, aFwpsacquirecla; "FwpsAcquireClassifyHandle failed"
0x1400033c4  mov     qword ptr [rbp+57h+var_B0], rax
0x1400033c8  lea     rax, [rbp+57h+var_C0]
0x1400033cc  mov     [rsp+0F0h+var_C8], rax
0x1400033d1  lea     rax, [rbp+57h+var_B0]
0x1400033d5  mov     [rsp+0F0h+classifyOut], rax
0x1400033da  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400033df  jmp     loc_14000377C
0x1400033e4  mov     rdx, [r12]; filterId
0x1400033e8  lea     r9, [rbp+57h+writableLayerData]; writableLayerData
0x1400033ec  mov     rcx, [rbp+57h+classifyHandle]; classifyHandle
0x1400033f0  xor     r8d, r8d; flags
0x1400033f3  mov     [rbp+57h+writableLayerData], 0
0x1400033fb  mov     [rsp+0F0h+classifyOut], r15; classifyOut
0x140003400  call    cs:__imp_FwpsAcquireWritableLayerDataPointer0
0x140003407  nop     dword ptr [rax+rax+00h]
0x14000340c  test    eax, eax
0x14000340e  jns     short loc_14000345C
0x140003410  mov     ecx, cs:dword_140012050
0x140003416  cmp     ecx, 2
0x140003419  jbe     short loc_140003447
0x14000341b  mov     [rbp+57h+var_C0], eax
0x14000341e  lea     rdx, byte_14000FA13
0x140003425  lea     rax, aFwpsacquirewri; "FwpsAcquireWritableLayerDataPointer fai"...
0x14000342c  mov     qword ptr [rbp+57h+var_B0], rax
0x140003430  lea     rax, [rbp+57h+var_C0]
0x140003434  mov     [rsp+0F0h+var_C8], rax
0x140003439  lea     rax, [rbp+57h+var_B0]
0x14000343d  mov     [rsp+0F0h+classifyOut], rax
0x140003442  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003447  mov     rcx, [rbp+57h+classifyHandle]; classifyHandle
0x14000344b  call    cs:__imp_FwpsReleaseClassifyHandle0
0x140003452  nop     dword ptr [rax+rax+00h]
0x140003457  jmp     loc_14000377C
0x14000345c  mov     rax, cs:off_140012040
0x140003463  xorps   xmm0, xmm0
0x140003466  mov     [rbp+57h+var_68], rax
0x14000346a  mov     r8d, 64667072h
0x140003470  mov     rax, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140003477  movups  [rbp+57h+var_88], xmm0
0x14000347b  mov     dword ptr [rbp+57h+var_88+8], edi
0x14000347e  movups  [rbp+57h+var_98], xmm0
0x140003482  mov     dword ptr [rbp+57h+var_98], 38h ; '8'
0x140003489  movups  [rbp+57h+var_78], xmm0
0x14000348d  mov     dword ptr [rbp+57h+var_88+0Ch], edi
0x140003490  mov     rcx, [rax+18h]
0x140003494  xor     eax, eax
0x140003496  mov     [rbp+57h+var_40], rax
0x14000349a  movups  [rbp+57h+var_50], xmm0
0x14000349e  mov     qword ptr [rbp+57h+var_78], rcx
0x1400034a2  lea     edx, [rax+18h]
0x1400034a5  mov     byte ptr [rbp+57h+var_40], 0
0x1400034a9  lea     rax, RoutePolicyAsyncRedirectRoutine
0x1400034b0  mov     dword ptr [rbp+57h+var_50], edx
0x1400034b3  lea     ecx, [rdx+28h]
0x1400034b6  mov     qword ptr [rbp+57h+var_50+8], rax
0x1400034ba  call    cs:__imp_ExAllocatePool2
0x1400034c1  nop     dword ptr [rax+rax+00h]
0x1400034c6  mov     rsi, rax
0x1400034c9  test    rax, rax
0x1400034cc  jnz     short loc_140003525
0x1400034ce  mov     eax, cs:dword_140012050
0x1400034d4  cmp     eax, 2
0x1400034d7  jbe     short loc_140003509
0x1400034d9  lea     rax, aFailedToAlloca_5; "Failed to allocate work item list entry"
0x1400034e0  mov     [rbp+57h+var_C0], 0C000009Ah
0x1400034e7  mov     qword ptr [rbp+57h+var_B0], rax
0x1400034eb  lea     rdx, word_14000FB5E
0x1400034f2  lea     rax, [rbp+57h+var_C0]
0x1400034f6  mov     [rsp+0F0h+var_C8], rax
0x1400034fb  lea     rax, [rbp+57h+var_B0]
0x1400034ff  mov     [rsp+0F0h+classifyOut], rax
0x140003504  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003509  mov     r8d, edi; flags
0x14000350c  mov     rdx, [rbp+57h+writableLayerData]; modifiedLayerData
0x140003510  mov     rcx, [rbp+57h+classifyHandle]; classifyHandle
0x140003514  call    cs:__imp_FwpsApplyModifiedLayerData0
0x14000351b  nop     dword ptr [rax+rax+00h]
0x140003520  jmp     loc_140003447
0x140003525  mov     rcx, cs:WdfDriverGlobals
0x14000352c  lea     r14, [rax+10h]
0x140003530  mov     rax, cs:WdfFunctions_01015
0x140003537  lea     r8, [rbp+57h+var_98]
0x14000353b  mov     r9, r14
0x14000353e  lea     rdx, [rbp+57h+var_50]
0x140003542  mov     rax, [rax+0BD8h]
0x140003549  call    _guard_dispatch_icall
0x14000354e  test    eax, eax
0x140003550  jns     short loc_1400035A2
0x140003552  mov     ecx, cs:dword_140012050
0x140003558  cmp     ecx, 2
0x14000355b  jbe     short loc_140003589
0x14000355d  mov     [rbp+57h+var_C0], eax
0x140003560  lea     rdx, word_14000F196
0x140003567  lea     rax, aWdfworkitemcre_0; "WdfWorkItemCreate for RoutePolicyAsyncR"...
0x14000356e  mov     qword ptr [rbp+57h+var_B0], rax
0x140003572  lea     rax, [rbp+57h+var_C0]
0x140003576  mov     [rsp+0F0h+var_C8], rax
0x14000357b  lea     rax, [rbp+57h+var_B0]
0x14000357f  mov     [rsp+0F0h+classifyOut], rax
0x140003584  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003589  mov     edx, 64667072h; Tag
0x14000358e  mov     rcx, rsi; P
0x140003591  call    cs:__imp_ExFreePoolWithTag
0x140003598  nop     dword ptr [rax+rax+00h]
0x14000359d  jmp     loc_140003509
0x1400035a2  mov     rax, [rbx+8]
0x1400035a6  mov     r8, cs:off_140012040
0x1400035ad  mov     rdx, [r14]
0x1400035b0  mov     rcx, cs:WdfDriverGlobals
0x1400035b7  movzx   edi, word ptr [rax+48h]
0x1400035bb  mov     bl, [rax+58h]
0x1400035be  mov     rax, cs:WdfFunctions_01015
0x1400035c5  ror     di, 8
0x1400035c9  mov     rax, [rax+650h]
0x1400035d0  call    _guard_dispatch_icall
0x1400035d5  mov     rcx, [rbp+57h+classifyHandle]
0x1400035d9  mov     r8d, 7
0x1400035df  mov     [rax], rcx
0x1400035e2  movups  xmm0, xmmword ptr [r15]
0x1400035e6  movups  xmmword ptr [rax+8], xmm0
0x1400035ea  movups  xmm1, xmmword ptr [r15+10h]
0x1400035ef  movups  xmmword ptr [rax+18h], xmm1
0x1400035f3  movsd   xmm0, qword ptr [r15+20h]
0x1400035f9  movsd   qword ptr [rax+28h], xmm0
0x1400035fe  mov     rcx, [r12]
0x140003602  mov     [rax+30h], rcx
0x140003606  mov     rcx, [rbp+57h+writableLayerData]
0x14000360a  mov     [rax+48h], rcx
0x14000360e  mov     rcx, r12
0x140003611  mov     [rax+40h], bl
0x140003614  lea     rbx, [rax+38h]
0x140003618  mov     r9, rbx
0x14000361b  mov     [rax+42h], di
0x14000361f  call    AppIdFromFilter
0x140003624  test    eax, eax
0x140003626  jns     short loc_14000369B
0x140003628  mov     ecx, cs:dword_140012050
0x14000362e  cmp     ecx, 2
0x140003631  jbe     short loc_14000365F
0x140003633  mov     [rbp+57h+var_C0], eax
0x140003636  lea     rdx, word_140010366
0x14000363d  lea     rax, aAppidfromfilte; "AppIdFromFilter failed"
0x140003644  mov     qword ptr [rbp+57h+var_B0], rax
0x140003648  lea     rax, [rbp+57h+var_C0]
0x14000364c  mov     [rsp+0F0h+var_C8], rax
0x140003651  lea     rax, [rbp+57h+var_B0]
0x140003655  mov     [rsp+0F0h+classifyOut], rax
0x14000365a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14000365f  mov     rax, cs:WdfFunctions_01015
0x140003666  mov     rdx, [r14]
0x140003669  mov     rcx, cs:WdfDriverGlobals
0x140003670  mov     rax, [rax+680h]
0x140003677  call    _guard_dispatch_icall
0x14000367c  mov     edx, 64667072h; Tag
0x140003681  mov     rcx, rsi; P
0x140003684  call    cs:__imp_ExFreePoolWithTag
0x14000368b  nop     dword ptr [rax+rax+00h]
0x140003690  mov     r8d, 1
0x140003696  jmp     loc_14000350C
0x14000369b  mov     rdx, [r12]; filterId
0x14000369f  mov     r9, r15; classifyOut
0x1400036a2  mov     rcx, [rbp+57h+classifyHandle]; classifyHandle
0x1400036a6  xor     r8d, r8d; flags
0x1400036a9  call    cs:__imp_FwpsPendClassify0
0x1400036b0  nop     dword ptr [rax+rax+00h]
0x1400036b5  test    eax, eax
0x1400036b7  jns     short loc_140003709
0x1400036b9  mov     ecx, cs:dword_140012050
0x1400036bf  cmp     ecx, 2
0x1400036c2  jbe     short loc_1400036F0
0x1400036c4  mov     [rbp+57h+var_C0], eax
0x1400036c7  lea     rdx, word_140010302
0x1400036ce  lea     rax, aFwpspendclassi; "FwpsPendClassify failed"
0x1400036d5  mov     qword ptr [rbp+57h+var_B0], rax
0x1400036d9  lea     rax, [rbp+57h+var_C0]
0x1400036dd  mov     [rsp+0F0h+var_C8], rax
0x1400036e2  lea     rax, [rbp+57h+var_B0]
0x1400036e6  mov     [rsp+0F0h+classifyOut], rax
0x1400036eb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400036f0  mov     rcx, [rbx]; P
0x1400036f3  mov     edx, 64667072h; Tag
0x1400036f8  call    cs:__imp_ExFreePoolWithTag
0x1400036ff  nop     dword ptr [rax+rax+00h]
0x140003704  jmp     loc_14000365F
0x140003709  mov     rdx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140003710  lea     rcx, [rbp+57h+var_B0]
0x140003714  add     rdx, 28h ; '('
0x140003718  call    ?AcquireSpinLock@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUSpinLockAndSavedIrql@@@Z$1?Release@1@SAX0@ZU?$integral_constant@_K$01@wistd@@U1@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_K@Z; AcquireSpinLock(unsigned __int64 *)
0x14000371d  mov     rax, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140003724  add     rax, 40h ; '@'
0x140003728  mov     rcx, [rax+8]
0x14000372c  cmp     [rcx], rax
0x14000372f  jz      short loc_140003738
0x140003731  mov     ecx, 3
0x140003736  int     29h; Win8: RtlFailFast(ecx)
0x140003738  mov     [rsi], rax
0x14000373b  mov     [rsi+8], rcx
0x14000373f  mov     [rcx], rsi
0x140003742  mov     [rax+8], rsi
0x140003746  mov     rax, cs:WdfFunctions_01015
0x14000374d  mov     rdx, [r14]
0x140003750  mov     rcx, cs:WdfDriverGlobals
0x140003757  mov     rax, [rax+0BE0h]
0x14000375e  call    _guard_dispatch_icall
0x140003763  cmp     qword ptr [rbp+57h+var_B0], 0
0x140003768  jz      short loc_14000377C
0x14000376a  movaps  xmm0, [rbp+57h+var_B0]
0x14000376e  lea     rcx, [rbp+57h+var_B0]; struct SpinLockAndSavedIrql *
0x140003772  movdqa  [rbp+57h+var_B0], xmm0
0x140003777  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x14000377c  mov     rcx, [rbp+57h+var_38]
0x140003780  xor     rcx, rsp; StackCookie
0x140003783  call    __security_check_cookie
0x140003788  add     rsp, 0C0h
0x14000378f  pop     r15
0x140003791  pop     r14
0x140003793  pop     r12
0x140003795  pop     rdi
0x140003796  pop     rsi
0x140003797  pop     rbx
0x140003798  pop     rbp
0x140003799  retn
```
