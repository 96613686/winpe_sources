# BipEnergyQuotaManagerInitializeAndAllocate

- ea: `0x1800865dc`
- end: `0x180086a21`
- name: `BipEnergyQuotaManagerInitializeAndAllocate`
- size: `1093`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007a320`

## callees

- `0x180002ac4`
- `0x180034fa8`
- `0x180049814`
- `0x18004aedc`
- `0x18004b61c`
- `0x18004d0fc`
- `0x180053100`
- `0x180070e58`
- `0x180080dd4`
- `0x180080e38`
- `0x1800855f0`
- `0x18008598c`
- `0x1800865dc`
- `0x18009467a`
- `0x180095010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800867f0`
- `ntdll!RtlNtStatusToDosError` at `0x1800867f0`
- `ntdll!RtlQueryWnfStateData` at `0x1800867e4`
- `ntdll!RtlQueryWnfStateData` at `0x1800867e4`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180086922`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180086922`
- `ntdll!RtlCreateHashTable` at `0x1800866b4`
- `ntdll!RtlCreateHashTable` at `0x1800866d7`
- `ntdll!RtlCreateHashTable` at `0x1800866ea`
- `ntdll!RtlCreateHashTable` at `0x1800866b4`
- `ntdll!RtlCreateHashTable` at `0x1800866d7`
- `ntdll!RtlCreateHashTable` at `0x1800866ea`
- `ntdll!TpAllocTimer` at `0x1800868a6`
- `ntdll!TpAllocTimer` at `0x1800868a6`
- `ntdll!TpReleaseTimer` at `0x180086913`
- `ntdll!TpReleaseTimer` at `0x180086913`
- `ntdll!TpSetTimer` at `0x1800868e6`
- `ntdll!TpSetTimer` at `0x1800868e6`
- `ntdll!RtlAllocateHeap` at `0x180086659`
- `ntdll!RtlAllocateHeap` at `0x180086659`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180086838`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180086838`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180086728`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180086728`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008692d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008692d`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1800867ba`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1800867ba`
- `ext-ms-win-shell-embeddedmode-l1-1-0!IsEmbeddedModeAllowed` at `0x180086853`
- `ext-ms-win-shell-embeddedmode-l1-1-0!IsEmbeddedModeAllowed` at `0x180086853`

## pseudocode

```c
__int64 __fastcall BipEnergyQuotaManagerInitializeAndAllocate(_QWORD *a1, __int64 a2, __int64 a3)
{
  char *Heap; // rax
  char *v5; // rdi
  int v6; // ebx
  char v7; // r12
  __int64 v8; // r8
  _QWORD *v9; // rsi
  CBackgroundEnergyQuotaManager *v10; // r14
  int v11; // ebx
  CBackgroundEnergyQuotaManager *v12; // rcx
  NTSTATUS v13; // eax
  signed int v14; // eax
  char v15; // al
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  double v19; // xmm0_8
  double v20; // xmm1_8
  int v21; // eax
  unsigned int v23; // [rsp+60h] [rbp-19h] BYREF
  CBackgroundEnergyQuotaManager *v24; // [rsp+68h] [rbp-11h] BYREF
  LPUNKNOWN pUnk; // [rsp+70h] [rbp-9h] BYREF
  DWORD dwRegister; // [rsp+78h] [rbp-1h] BYREF
  int v27; // [rsp+7Ch] [rbp+3h] BYREF
  float v28; // [rsp+80h] [rbp+7h] BYREF
  float v29; // [rsp+84h] [rbp+Bh] BYREF
  int v30; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v31; // [rsp+90h] [rbp+17h] BYREF
  __int64 v32[7]; // [rsp+98h] [rbp+1Fh] BYREF
  __int16 v33; // [rsp+E8h] [rbp+6Fh] BYREF
  __int16 v34; // [rsp+F0h] [rbp+77h] BYREF
  int v35; // [rsp+F8h] [rbp+7Fh] BYREF

  v35 = 0;
  pUnk = 0;
  v24 = 0;
  dwRegister = 0;
  v23 = 0;
  v31 = 0;
  if ( (unsigned int)dword_1800C3098 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 2, a3) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1800C3098,
      &word_1800B52AE);
  Heap = (char *)RtlAllocateHeap(BipHeap, 0, 0xC0u);
  v5 = Heap;
  if ( !Heap )
  {
    v6 = -2147024882;
    goto LABEL_47;
  }
  v7 = 0;
  memset_0(Heap, 0, 0xC0u);
  *((_QWORD *)v5 + 14) = v5 + 104;
  *((_QWORD *)v5 + 13) = v5 + 104;
  *((_QWORD *)v5 + 16) = v5 + 120;
  *((_QWORD *)v5 + 15) = v5 + 120;
  BipSyncInitializeLock(v5, 11);
  *((_DWORD *)v5 + 18) = 30000;
  if ( !(unsigned __int8)RtlCreateHashTable(v5 + 16, 0, 0)
    || (v9 = v5 + 152, !(unsigned __int8)RtlCreateHashTable(v5 + 152, 0, 0))
    || !(unsigned __int8)RtlCreateHashTable(v5 + 24, 0, 0) )
  {
    v6 = -2147024882;
    goto LABEL_38;
  }
  v10 = 0;
  v11 = BipEnergyBudgetAddListToAlwaysImportantAppTable(*v9);
  if ( v11 < 0 || (v11 = BipEnergyBudgetAddRegOverrideImportantPackage(*v9), v11 < 0) )
  {
    v6 = v11 | 0x10000000;
    goto LABEL_35;
  }
  BipEnergyBudgetInitializeParams(v5);
  v6 = CoInitializeEx(0, 0);
  if ( v6 < 0
    || (v7 = 1,
        v6 = ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CBackgroundEnergyQuotaManager>>>::CreateInstance(
               0,
               &IID_IClassFactory,
               &pUnk),
        v6 < 0)
    || (v6 = ((__int64 (__fastcall *)(LPUNKNOWN, _QWORD, GUID *, CBackgroundEnergyQuotaManager **))pUnk->lpVtbl[1].QueryInterface)(
               pUnk,
               0,
               &IID_IBackgroundEnergyQuotaManager,
               &v24),
        v6 < 0) )
  {
LABEL_38:
    if ( *((_QWORD *)v5 + 17) )
      TpReleaseTimer();
    if ( *((_QWORD *)v5 + 7) )
      RtlUnsubscribeWnfStateChangeNotification();
    goto LABEL_42;
  }
  v10 = v24;
  v12 = v24;
  v24 = 0;
  v6 = CBackgroundEnergyQuotaManager::Initialize(v12, (struct _BI_ENERGY_BUDGET_CONTEXT *)v5);
  if ( v6 < 0 || (v6 = CoRegisterClassObject(&CLSID_CBackgroundEnergyQuotaManager, pUnk, 1u, 1u, &dwRegister), v6 < 0) )
  {
LABEL_36:
    if ( v10 )
      (*(void (__fastcall **)(CBackgroundEnergyQuotaManager *))(*(_QWORD *)v10 + 16LL))(v10);
    goto LABEL_38;
  }
  v13 = RtlQueryWnfStateData(&v23, WNF_PO_POWER_STATE_CHANGE, &BipEnergyBudgetBatteryChangedProc, v5, 0);
  if ( v13 < 0
    || (v13 = RtlSubscribeWnfStateChangeNotification(
                v5 + 56,
                WNF_PO_POWER_STATE_CHANGE,
                v23,
                &BipEnergyBudgetBatteryChangedProc,
                v5,
                0,
                0,
                0),
        v13 < 0) )
  {
    v14 = RtlNtStatusToDosError(v13);
    v6 = v14;
    if ( v14 > 0 )
      v6 = (unsigned __int16)v14 | 0x80070000;
  }
  else
  {
    if ( (unsigned __int8)IsIsEmbeddedModeAllowedPresent() )
    {
      v35 = 0;
      v6 = IsEmbeddedModeAllowed(&v35);
      if ( v6 >= 0 )
      {
        if ( v35 )
          v5[176] |= 0x40u;
      }
    }
    v15 = v5[176];
    if ( (v15 & 4) == 0
      && *((_WORD *)v5 + 16)
      && *((_WORD *)v5 + 17)
      && *((_WORD *)v5 + 18) < 0x64u
      && (v15 & 0x40) == 0 )
    {
      if ( (int)TpAllocTimer(v5 + 136, &BipEnergyBudgetRefillPeriodTimerCallback, v5, 0) < 0 )
      {
        v6 = -2147024882;
        goto LABEL_36;
      }
      v31 = -600000000LL * *((unsigned __int16 *)v5 + 16);
      TpSetTimer(*((_QWORD *)v5 + 17), &v31, 60000 * (unsigned int)*((unsigned __int16 *)v5 + 16), 60000);
    }
    *a1 = v5;
  }
LABEL_35:
  if ( v6 < 0 )
    goto LABEL_36;
LABEL_42:
  if ( v7 )
    CoUninitialize();
  if ( (unsigned int)dword_1800C3098 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 0x200000000003LL, v8) )
  {
    v19 = *((double *)v5 + 6);
    v20 = *((double *)v5 + 5);
    v21 = ((unsigned __int8)v5[176] >> 2) & 1;
    v32[0] = 0x1000000;
    v27 = v21;
    v33 = *((_WORD *)v5 + 17);
    v34 = *((_WORD *)v5 + 16);
    v30 = v6;
    v28 = v19;
    v29 = v20;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v16,
      (unsigned int)&unk_1800B5580,
      v17,
      v18,
      (__int64)&v30,
      (__int64)&v34,
      (__int64)&v33,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)v32);
  }
LABEL_47:
  ATL::CComPtrBase<IBackgroundEnergyQuotaManager>::~CComPtrBase<IBackgroundEnergyQuotaManager>(&v24);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pUnk);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800865dc  mov     [rsp-8+arg_0], rbx
0x1800865e1  push    rbp
0x1800865e2  push    rsi
0x1800865e3  push    rdi
0x1800865e4  push    r12
0x1800865e6  push    r13
0x1800865e8  push    r14
0x1800865ea  push    r15
0x1800865ec  lea     rbp, [rsp-27h]
0x1800865f1  sub     rsp, 0A0h
0x1800865f8  mov     eax, cs:dword_1800C3098
0x1800865fe  xor     r13d, r13d
0x180086601  mov     [rbp+57h+arg_18], r13d
0x180086605  mov     r15, rcx
0x180086608  mov     [rbp+57h+pUnk], r13
0x18008660c  mov     [rbp+57h+var_68], r13
0x180086610  mov     [rbp+57h+dwRegister], r13d
0x180086614  mov     [rbp+57h+var_70], r13d
0x180086618  mov     [rbp+57h+var_40], r13
0x18008661c  cmp     eax, 5
0x18008661f  jbe     short loc_180086648
0x180086621  lea     edx, [r13+2]
0x180086625  lea     rcx, dword_1800C3098
0x18008662c  call    _tlgKeywordOn
0x180086631  test    al, al
0x180086633  jz      short loc_180086648
0x180086635  lea     rdx, word_1800B52AE
0x18008663c  lea     rcx, dword_1800C3098
0x180086643  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180086648  mov     rcx, cs:BipHeap; HeapHandle
0x18008664f  mov     ebx, 0C0h
0x180086654  mov     r8d, ebx; Size
0x180086657  xor     edx, edx; Flags
0x180086659  call    cs:__imp_RtlAllocateHeap
0x18008665f  mov     rdi, rax
0x180086662  test    rax, rax
0x180086665  jnz     short loc_180086671
0x180086667  mov     ebx, 8007000Eh
0x18008666c  jmp     loc_1800869F2
0x180086671  mov     r8, rbx; Size
0x180086674  xor     edx, edx; Val
0x180086676  mov     rcx, rdi; void *
0x180086679  mov     r12b, r13b
0x18008667c  call    memset_0
0x180086681  lea     rax, [rdi+68h]
0x180086685  mov     edx, 0Bh
0x18008668a  mov     [rax+8], rax
0x18008668e  mov     rcx, rdi
0x180086691  mov     [rax], rax
0x180086694  lea     rax, [rdi+78h]
0x180086698  mov     [rax+8], rax
0x18008669c  mov     [rax], rax
0x18008669f  call    BipSyncInitializeLock
0x1800866a4  lea     rcx, [rdi+10h]
0x1800866a8  mov     dword ptr [rdi+48h], 7530h
0x1800866af  xor     r8d, r8d
0x1800866b2  xor     edx, edx
0x1800866b4  call    cs:__imp_RtlCreateHashTable
0x1800866ba  test    al, al
0x1800866bc  jnz     short loc_1800866C8
0x1800866be  mov     ebx, 8007000Eh
0x1800866c3  jmp     loc_180086907
0x1800866c8  lea     rsi, [rdi+98h]
0x1800866cf  xor     r8d, r8d
0x1800866d2  mov     rcx, rsi
0x1800866d5  xor     edx, edx
0x1800866d7  call    cs:__imp_RtlCreateHashTable
0x1800866dd  test    al, al
0x1800866df  jz      short loc_1800866BE
0x1800866e1  lea     rcx, [rdi+18h]
0x1800866e5  xor     r8d, r8d
0x1800866e8  xor     edx, edx
0x1800866ea  call    cs:__imp_RtlCreateHashTable
0x1800866f0  test    al, al
0x1800866f2  jz      short loc_1800866BE
0x1800866f4  mov     rcx, [rsi]
0x1800866f7  mov     r14, r13
0x1800866fa  call    BipEnergyBudgetAddListToAlwaysImportantAppTable
0x1800866ff  mov     ebx, eax
0x180086701  test    eax, eax
0x180086703  jns     short loc_18008670E
0x180086705  bts     ebx, 1Ch
0x180086709  jmp     loc_1800868EF
0x18008670e  mov     rcx, [rsi]
0x180086711  call    BipEnergyBudgetAddRegOverrideImportantPackage
0x180086716  mov     ebx, eax
0x180086718  test    eax, eax
0x18008671a  js      short loc_180086705
0x18008671c  mov     rcx, rdi
0x18008671f  call    BipEnergyBudgetInitializeParams
0x180086724  xor     edx, edx; dwCoInit
0x180086726  xor     ecx, ecx; pvReserved
0x180086728  call    cs:__imp_CoInitializeEx
0x18008672e  mov     ebx, eax
0x180086730  test    eax, eax
0x180086732  js      loc_180086907
0x180086738  mov     esi, 1
0x18008673d  lea     r8, [rbp+57h+pUnk]
0x180086741  lea     rdx, IID_IClassFactory
0x180086748  xor     ecx, ecx
0x18008674a  mov     r12b, sil
0x18008674d  call    ?CreateInstance@?$CComCreator@V?$CComObjectNoLock@V?$CComClassFactorySingleton@VCBackgroundEnergyQuotaManager@@@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CBackgroundEnergyQuotaManager>>>::CreateInstance(void *,_GUID const &,void * *)
0x180086752  mov     ebx, eax
0x180086754  test    eax, eax
0x180086756  js      loc_180086907
0x18008675c  mov     rcx, [rbp+57h+pUnk]
0x180086760  lea     r9, [rbp+57h+var_68]
0x180086764  lea     r8, IID_IBackgroundEnergyQuotaManager
0x18008676b  xor     edx, edx
0x18008676d  mov     rax, [rcx]
0x180086770  mov     rax, [rax+18h]
0x180086774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086779  mov     ebx, eax
0x18008677b  test    eax, eax
0x18008677d  js      loc_180086907
0x180086783  mov     r14, [rbp+57h+var_68]
0x180086787  mov     rdx, rdi; struct _BI_ENERGY_BUDGET_CONTEXT *
0x18008678a  mov     rcx, r14; this
0x18008678d  mov     [rbp+57h+var_68], r13
0x180086791  call    ?Initialize@CBackgroundEnergyQuotaManager@@QEAAJPEAU_BI_ENERGY_BUDGET_CONTEXT@@@Z; CBackgroundEnergyQuotaManager::Initialize(_BI_ENERGY_BUDGET_CONTEXT *)
0x180086796  mov     ebx, eax
0x180086798  test    eax, eax
0x18008679a  js      loc_1800868F3
0x1800867a0  mov     rdx, [rbp+57h+pUnk]; pUnk
0x1800867a4  lea     rax, [rbp+57h+dwRegister]
0x1800867a8  mov     r9d, esi; flags
0x1800867ab  mov     [rsp+0D0h+lpdwRegister], rax; lpdwRegister
0x1800867b0  mov     r8d, esi; dwClsContext
0x1800867b3  lea     rcx, CLSID_CBackgroundEnergyQuotaManager; rclsid
0x1800867ba  call    cs:__imp_CoRegisterClassObject
0x1800867c0  mov     ebx, eax
0x1800867c2  test    eax, eax
0x1800867c4  js      loc_1800868F3
0x1800867ca  mov     rdx, cs:WNF_PO_POWER_STATE_CHANGE
0x1800867d1  lea     r8, BipEnergyBudgetBatteryChangedProc
0x1800867d8  mov     r9, rdi
0x1800867db  mov     [rsp+0D0h+lpdwRegister], r13
0x1800867e0  lea     rcx, [rbp+57h+var_70]
0x1800867e4  call    cs:__imp_RtlQueryWnfStateData
0x1800867ea  test    eax, eax
0x1800867ec  jns     short loc_18008680E
0x1800867ee  mov     ecx, eax; Status
0x1800867f0  call    cs:__imp_RtlNtStatusToDosError
0x1800867f6  mov     ebx, eax
0x1800867f8  test    eax, eax
0x1800867fa  jle     loc_1800868EF
0x180086800  movzx   ebx, ax
0x180086803  or      ebx, 80070000h
0x180086809  jmp     loc_1800868EF
0x18008680e  mov     r8d, [rbp+57h+var_70]
0x180086812  lea     rcx, [rdi+38h]
0x180086816  mov     rdx, cs:WNF_PO_POWER_STATE_CHANGE
0x18008681d  lea     r9, BipEnergyBudgetBatteryChangedProc
0x180086824  mov     dword ptr [rsp+0D0h+var_98], r13d
0x180086829  mov     dword ptr [rsp+0D0h+var_A0], r13d
0x18008682e  mov     [rsp+0D0h+var_A8], r13
0x180086833  mov     [rsp+0D0h+lpdwRegister], rdi
0x180086838  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18008683e  test    eax, eax
0x180086840  js      short loc_1800867EE
0x180086842  call    IsIsEmbeddedModeAllowedPresent
0x180086847  test    al, al
0x180086849  jz      short loc_18008686C
0x18008684b  lea     rcx, [rbp+57h+arg_18]
0x18008684f  mov     [rbp+57h+arg_18], r13d
0x180086853  call    cs:__imp_IsEmbeddedModeAllowed
0x180086859  mov     ebx, eax
0x18008685b  test    eax, eax
0x18008685d  js      short loc_18008686C
0x18008685f  cmp     [rbp+57h+arg_18], r13d
0x180086863  jz      short loc_18008686C
0x180086865  or      byte ptr [rdi+0B0h], 40h
0x18008686c  mov     al, [rdi+0B0h]
0x180086872  test    al, 4
0x180086874  jnz     short loc_1800868EC
0x180086876  cmp     [rdi+20h], r13w
0x18008687b  jz      short loc_1800868EC
0x18008687d  cmp     [rdi+22h], r13w
0x180086882  jz      short loc_1800868EC
0x180086884  cmp     word ptr [rdi+24h], 64h ; 'd'
0x180086889  jnb     short loc_1800868EC
0x18008688b  test    al, 40h
0x18008688d  jnz     short loc_1800868EC
0x18008688f  lea     rsi, [rdi+88h]
0x180086896  xor     r9d, r9d
0x180086899  mov     rcx, rsi
0x18008689c  lea     rdx, BipEnergyBudgetRefillPeriodTimerCallback
0x1800868a3  mov     r8, rdi
0x1800868a6  call    cs:__imp_TpAllocTimer
0x1800868ac  test    eax, eax
0x1800868ae  jns     short loc_1800868B7
0x1800868b0  mov     ebx, 8007000Eh
0x1800868b5  jmp     short loc_1800868F3
0x1800868b7  movzx   eax, word ptr [rdi+20h]
0x1800868bb  mov     r9d, 0EA60h
0x1800868c1  imul    eax, 0EA60h
0x1800868c7  cdqe
0x1800868c9  imul    rdx, rax, 0FFFFFFFFFFFFD8F0h
0x1800868d0  mov     [rbp+57h+var_40], rdx
0x1800868d4  lea     rdx, [rbp+57h+var_40]
0x1800868d8  movzx   eax, word ptr [rdi+20h]
0x1800868dc  mov     rcx, [rsi]
0x1800868df  imul    r8d, eax, 0EA60h
0x1800868e6  call    cs:__imp_TpSetTimer
0x1800868ec  mov     [r15], rdi
0x1800868ef  test    ebx, ebx
0x1800868f1  jns     short loc_180086928
0x1800868f3  test    r14, r14
0x1800868f6  jz      short loc_180086907
0x1800868f8  mov     rax, [r14]
0x1800868fb  mov     rcx, r14
0x1800868fe  mov     rax, [rax+10h]
0x180086902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086907  mov     rcx, [rdi+88h]
0x18008690e  test    rcx, rcx
0x180086911  jz      short loc_180086919
0x180086913  call    cs:__imp_TpReleaseTimer
0x180086919  mov     rcx, [rdi+38h]
0x18008691d  test    rcx, rcx
0x180086920  jz      short loc_180086928
0x180086922  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x180086928  test    r12b, r12b
0x18008692b  jz      short loc_180086933
0x18008692d  call    cs:__imp_CoUninitialize
0x180086933  mov     eax, cs:dword_1800C3098
0x180086939  cmp     eax, 4
0x18008693c  jbe     loc_1800869F2
0x180086942  mov     rdx, 200000000003h
0x18008694c  lea     rcx, dword_1800C3098
0x180086953  call    _tlgKeywordOn
0x180086958  test    al, al
0x18008695a  jz      loc_1800869F2
0x180086960  movzx   eax, byte ptr [rdi+0B0h]
0x180086967  lea     rdx, unk_1800B5580
0x18008696e  movsd   xmm0, qword ptr [rdi+30h]
0x180086973  movsd   xmm1, qword ptr [rdi+28h]
0x180086978  shr     eax, 2
0x18008697b  and     eax, 1
0x18008697e  mov     [rbp+57h+var_38], 1000000h
0x180086986  mov     [rbp+57h+var_54], eax
0x180086989  movzx   eax, word ptr [rdi+22h]
0x18008698d  mov     [rbp+57h+arg_8], ax
0x180086991  movzx   eax, word ptr [rdi+20h]
0x180086995  mov     [rbp+57h+arg_10], ax
0x180086999  lea     rax, [rbp+57h+var_38]
0x18008699d  mov     [rsp+0D0h+var_80], rax
0x1800869a2  lea     rax, [rbp+57h+var_54]
0x1800869a6  mov     [rsp+0D0h+var_88], rax
0x1800869ab  lea     rax, [rbp+57h+var_50]
0x1800869af  mov     [rsp+0D0h+var_90], rax
0x1800869b4  lea     rax, [rbp+57h+var_4C]
0x1800869b8  mov     [rsp+0D0h+var_98], rax
0x1800869bd  lea     rax, [rbp+57h+arg_8]
0x1800869c1  mov     [rsp+0D0h+var_A0], rax
0x1800869c6  lea     rax, [rbp+57h+arg_10]
0x1800869ca  mov     [rsp+0D0h+var_A8], rax
0x1800869cf  lea     rax, [rbp+57h+var_48]
0x1800869d3  cvtpd2ps xmm0, xmm0
0x1800869d7  mov     [rsp+0D0h+lpdwRegister], rax
0x1800869dc  mov     [rbp+57h+var_48], ebx
0x1800869df  cvtpd2ps xmm1, xmm1
0x1800869e3  movss   [rbp+57h+var_50], xmm0
0x1800869e8  movss   [rbp+57h+var_4C], xmm1
0x1800869ed  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@U1@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4333AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800869f2  lea     rcx, [rbp+57h+var_68]
0x1800869f6  call    ??1?$CComPtrBase@UIBackgroundEnergyQuotaManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IBackgroundEnergyQuotaManager>::~CComPtrBase<IBackgroundEnergyQuotaManager>(void)
0x1800869fb  lea     rcx, [rbp+57h+pUnk]
0x1800869ff  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180086a04  mov     eax, ebx
0x180086a06  mov     rbx, [rsp+0D0h+arg_0]
0x180086a0e  add     rsp, 0A0h
0x180086a15  pop     r15
0x180086a17  pop     r14
0x180086a19  pop     r13
0x180086a1b  pop     r12
0x180086a1d  pop     rdi
0x180086a1e  pop     rsi
0x180086a1f  pop     rbp
0x180086a20  retn
```
