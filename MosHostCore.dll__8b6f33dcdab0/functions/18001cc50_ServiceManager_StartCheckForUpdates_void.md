# ServiceManager::StartCheckForUpdates(void)

- ea: `0x18001cc50`
- end: `0x18001cf58`
- name: `?StartCheckForUpdates@ServiceManager@@UEAAJXZ`
- size: `776`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180003410`
- `0x18000381c`
- `0x180003f7c`
- `0x1800043e4`
- `0x18000e57c`
- `0x18000e6a0`
- `0x18000f67c`
- `0x18000f6a8`
- `0x18000f6d4`
- `0x1800117f0`
- `0x180012198`
- `0x180015ed0`
- `0x18001cc50`
- `0x18001edb0`
- `0x18001eec4`
- `0x18001f3c4`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001cd15`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001cd15`
- `MapsStore!MapsStore_CheckUpdateAsync` at `0x18001cddc`
- `MapsStore!MapsStore_CheckUpdateAsync` at `0x18001cddc`
- `MosStorage!MosStorageGetCurrentLocation` at `0x18001ce39`
- `MosStorage!MosStorageGetCurrentLocation` at `0x18001ce39`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ce55`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ce55`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001cdd4`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001cdd4`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001ce07`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001ce07`

## string_xrefs

- `0x18001cdcb`: `ServiceManager::StartCheckForUpdates`
- `0x18001ce00`: `ServiceManager::StartCheckForUpdates`
- `0x18001ce4c`: `ServiceManager::StartCheckForUpdates`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceManager::StartCheckForUpdates(ServiceManager *this)
{
  unsigned int v2; // r14d
  char v3; // bl
  int v4; // r8d
  int v5; // ecx
  bool v6; // bl
  struct _TP_CALLBACK_ENVIRON_V3 *v7; // rdi
  _QWORD *v8; // rbx
  _QWORD *v9; // rax
  int v10; // eax
  int v11; // r8d
  int v12; // eax
  int CurrentLocation; // eax
  PackageManager *v14; // rcx
  PackageManager *v15; // rcx
  bool v17; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+54h] [rbp-ACh] BYREF
  int CurrentOperationTrigger; // [rsp+58h] [rbp-A8h] BYREF
  int CurrentOperationInfo; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v21[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+70h] [rbp-90h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v24[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[4]; // [rsp+90h] [rbp-70h] BYREF
  int v26; // [rsp+94h] [rbp-6Ch]
  unsigned int v27[275]; // [rsp+2A4h] [rbp+1A4h] BYREF
  unsigned int v28[4]; // [rsp+6F0h] [rbp+5F0h] BYREF

  v2 = 0;
  v3 = 0;
  CriticalSectionWithConditionVariable::Lock((struct _RTL_CRITICAL_SECTION *)this + 85, (__int64)v24);
  if ( (unsigned int)(*((_DWORD *)this + 882) - 4) > 1 )
  {
    v4 = 724;
    v5 = -2147024875;
LABEL_14:
    v12 = ZTraceReportOrigination(v5, "ServiceManager::StartCheckForUpdates", v4, this);
    goto LABEL_15;
  }
  if ( *((_DWORD *)this + 880) || *((_DWORD *)this + 881) )
  {
    v4 = 725;
    v5 = -2147024567;
    goto LABEL_14;
  }
  *((_QWORD *)this + 442) = 2;
  ServiceManager::FireOdmlStateChange(this);
  *((_BYTE *)this + 4314) = *((_DWORD *)this + 1082) == 5;
  *((_DWORD *)this + 880) = 4;
  *((_DWORD *)this + 881) = 8;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( *((_BYTE *)this + 4314) )
  {
    ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
      (__int64)v21,
      (struct _RTL_CRITICAL_SECTION *)((char *)this + 3568));
    v6 = *((_QWORD *)this + 470) != *((_QWORD *)this + 471);
    ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>((__int64)v21);
    if ( !v6 )
    {
      v7 = (struct _TP_CALLBACK_ENVIRON_V3 *)*((_QWORD *)this + 424);
      v8 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
             &v22,
             (__int64)this);
      v9 = operator new(8u);
      *v9 = *v8;
      Threadpool::QueueWorkItem(v7, lambda_f6107d3809f93926dc3649566c190a4e_::_lambda_invoker_cdecl_, v9);
      *(_QWORD *)v21 = 0;
      std::unique_ptr__lambda_e0151e82603ed25fc2b10ac46ee2682c__std::default_delete__lambda_e0151e82603ed25fc2b10ac46ee2682c_____::_unique_ptr__lambda_e0151e82603ed25fc2b10ac46ee2682c__std::default_delete__lambda_e0151e82603ed25fc2b10ac46ee2682c_____(v21);
      goto LABEL_20;
    }
  }
  v3 = 1;
  v10 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))ServiceWatchdog::Start)(
          (char *)this + 3944,
          2,
          SystemTimeAsFileTime);
  if ( v10 >= 0 )
  {
    v10 = MapsStore_CheckUpdateAsync();
    if ( v10 >= 0 )
      goto LABEL_20;
    v11 = 744;
  }
  else
  {
    v11 = 742;
  }
  v12 = ZTraceReportPropagation(v10, "ServiceManager::StartCheckForUpdates", v11, this);
LABEL_15:
  v2 = v12;
  v18 = v12;
  if ( v12 < 0 && v3 )
  {
    memset_0(v25, 0, 0x670u);
    CurrentLocation = MosStorageGetCurrentLocation((struct _STORAGE_DEVICE_DATA *)v25);
    if ( CurrentLocation < 0 )
      ZTraceReportIgnore(CurrentLocation, "ServiceManager::StartCheckForUpdates", 761, this);
    ServiceWatchdog::Stop((ServiceManager *)((char *)this + 3944));
    v17 = v26 != 0;
    CurrentOperationTrigger = PackageManager::GetCurrentOperationTrigger((char *)this + 3568);
    CurrentOperationInfo = PackageManager::GetCurrentOperationInfo(v14);
    LODWORD(v22) = PackageManager::GetCurrentPackageSizeInKB(v15);
    v21[0] = *((_DWORD *)this + 952);
    OfflineMapsTelemetry::OfflineMapCheckForUpdatesFailed<unsigned int,unsigned int,unsigned long,int,_FILETIME &,unsigned __int64 &,bool,enum _STORAGE_DEVICE_TYPE &,unsigned long &,long &>(
      v21,
      (unsigned int *)&v22,
      &CurrentOperationInfo,
      &CurrentOperationTrigger,
      (struct _FILETIME *)((char *)this + 4332),
      (unsigned __int64 *)this + 543,
      &v17,
      v27,
      v28,
      &v18);
    *((_BYTE *)this + 4314) = 0;
    *((_QWORD *)this + 440) = 0;
    *((_DWORD *)this + 884) = 1;
    *((_DWORD *)this + 885) = v2;
    ServiceManager::FireOdmlStateChange(this);
  }
LABEL_20:
  RelockableGate::~RelockableGate((RelockableGate *)v24);
  return v2;
}

```

## disassembly

```asm
0x18001cc50  mov     [rsp-8+arg_8], rbx
0x18001cc55  mov     [rsp-8+arg_10], rsi
0x18001cc5a  push    rbp
0x18001cc5b  push    rdi
0x18001cc5c  push    r14
0x18001cc5e  lea     rbp, [rsp-610h]
0x18001cc66  sub     rsp, 710h
0x18001cc6d  mov     rax, cs:__security_cookie
0x18001cc74  xor     rax, rsp
0x18001cc77  mov     [rbp+620h+var_20], rax
0x18001cc7e  mov     rsi, rcx
0x18001cc81  xor     r14d, r14d
0x18001cc84  xor     bl, bl
0x18001cc86  add     rcx, 0D48h
0x18001cc8d  lea     rdx, [rbp+620h+var_6A0]
0x18001cc91  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x18001cc96  nop
0x18001cc97  mov     eax, [rsi+0DC8h]
0x18001cc9d  sub     eax, 4
0x18001cca0  cmp     eax, 1
0x18001cca3  jbe     short loc_18001CCB5
0x18001cca5  mov     r8d, 2D4h
0x18001ccab  mov     ecx, 80070015h
0x18001ccb0  jmp     loc_18001CDFD
0x18001ccb5  cmp     dword ptr [rsi+0DC0h], 0
0x18001ccbc  jnz     loc_18001CDF2
0x18001ccc2  cmp     dword ptr [rsi+0DC4h], 0
0x18001ccc9  jnz     loc_18001CDF2
0x18001cccf  mov     edi, 2
0x18001ccd4  mov     [rsi+0DD0h], rdi
0x18001ccdb  mov     rcx, rsi; this
0x18001ccde  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x18001cce3  cmp     dword ptr [rsi+10E8h], 5
0x18001ccea  setz    al
0x18001cced  mov     [rsi+10DAh], al
0x18001ccf3  mov     dword ptr [rsi+0DC0h], 4
0x18001ccfd  mov     dword ptr [rsi+0DC4h], 8
0x18001cd07  mov     qword ptr [rsp+720h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001cd10  lea     rcx, [rsp+720h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001cd15  call    cs:__imp_GetSystemTimeAsFileTime
0x18001cd1b  cmp     byte ptr [rsi+10DAh], 0
0x18001cd22  jz      loc_18001CDA9
0x18001cd28  lea     rdx, [rsi+0DF0h]
0x18001cd2f  lea     rcx, [rsp+720h+var_6C0]
0x18001cd34  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18001cd39  mov     rax, [rsi+0EB8h]
0x18001cd40  cmp     [rsi+0EB0h], rax
0x18001cd47  setnz   bl
0x18001cd4a  lea     rcx, [rsp+720h+var_6C0]
0x18001cd4f  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x18001cd54  test    bl, bl
0x18001cd56  jnz     short loc_18001CDA9
0x18001cd58  mov     rdi, [rsi+0D40h]
0x18001cd5f  mov     rdx, rsi
0x18001cd62  lea     rcx, [rsp+720h+var_6B0]
0x18001cd67  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18001cd6c  mov     rbx, rax
0x18001cd6f  mov     ecx, 8; Size
0x18001cd74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cd79  mov     rdx, [rbx]
0x18001cd7c  mov     [rax], rdx
0x18001cd7f  mov     r8, rax; pv
0x18001cd82  lea     rdx, _lambda_f6107d3809f93926dc3649566c190a4e____lambda_invoker_cdecl_; pfnwk
0x18001cd89  mov     rcx, rdi; pcbe
0x18001cd8c  call    ?QueueWorkItem@Threadpool@@AEAAXP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1@Z; Threadpool::QueueWorkItem(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)
0x18001cd91  mov     qword ptr [rsp+720h+var_6C0], 0
0x18001cd9a  lea     rcx, [rsp+720h+var_6C0]
0x18001cd9f  call    std__unique_ptr__lambda_e0151e82603ed25fc2b10ac46ee2682c__std__default_delete__lambda_e0151e82603ed25fc2b10ac46ee2682c________unique_ptr__lambda_e0151e82603ed25fc2b10ac46ee2682c__std__default_delete__lambda_e0151e82603ed25fc2b10ac46ee2682c_____
0x18001cda4  jmp     loc_18001CF25
0x18001cda9  mov     bl, 1
0x18001cdab  lea     rcx, [rsi+0F68h]
0x18001cdb2  mov     r8, qword ptr [rsp+720h+SystemTimeAsFileTime.dwLowDateTime]
0x18001cdb7  mov     edx, edi
0x18001cdb9  call    ?Start@ServiceWatchdog@@QEAAJW4StartReason@1@U_FILETIME@@@Z; ServiceWatchdog::Start(ServiceWatchdog::StartReason,_FILETIME)
0x18001cdbe  test    eax, eax
0x18001cdc0  jns     short loc_18001CDDC
0x18001cdc2  mov     r8d, 2E6h
0x18001cdc8  mov     r9, rsi
0x18001cdcb  lea     rdx, aServicemanager_46; "ServiceManager::StartCheckForUpdates"
0x18001cdd2  mov     ecx, eax
0x18001cdd4  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001cdda  jmp     short loc_18001CE0D
0x18001cddc  call    cs:__imp_?MapsStore_CheckUpdateAsync@@YAJXZ; MapsStore_CheckUpdateAsync(void)
0x18001cde2  test    eax, eax
0x18001cde4  jns     loc_18001CF25
0x18001cdea  mov     r8d, 2E8h
0x18001cdf0  jmp     short loc_18001CDC8
0x18001cdf2  mov     r8d, 2D5h
0x18001cdf8  mov     ecx, 80070149h
0x18001cdfd  mov     r9, rsi
0x18001ce00  lea     rdx, aServicemanager_46; "ServiceManager::StartCheckForUpdates"
0x18001ce07  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001ce0d  mov     r14d, eax
0x18001ce10  mov     [rsp+720h+var_6CC], eax
0x18001ce14  test    eax, eax
0x18001ce16  jns     loc_18001CF25
0x18001ce1c  test    bl, bl
0x18001ce1e  jz      loc_18001CF25
0x18001ce24  xor     edx, edx; Val
0x18001ce26  mov     r8d, 670h; Size
0x18001ce2c  lea     rcx, [rbp+620h+var_690]; void *
0x18001ce30  call    memset_0
0x18001ce35  lea     rcx, [rbp+620h+var_690]
0x18001ce39  call    cs:__imp_?MosStorageGetCurrentLocation@@YAJPEAU_STORAGE_DEVICE_DATA@@@Z; MosStorageGetCurrentLocation(_STORAGE_DEVICE_DATA *)
0x18001ce3f  test    eax, eax
0x18001ce41  jns     short loc_18001CE5B
0x18001ce43  mov     r9, rsi
0x18001ce46  mov     r8d, 2F9h
0x18001ce4c  lea     rdx, aServicemanager_46; "ServiceManager::StartCheckForUpdates"
0x18001ce53  mov     ecx, eax
0x18001ce55  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001ce5b  lea     rcx, [rsi+0F68h]; this
0x18001ce62  call    ?Stop@ServiceWatchdog@@QEAAXXZ; ServiceWatchdog::Stop(void)
0x18001ce67  cmp     [rbp+620h+var_68C], 0
0x18001ce6b  setnz   [rsp+720h+var_6D0]
0x18001ce70  lea     rcx, [rsi+0DF0h]
0x18001ce77  call    ?GetCurrentOperationTrigger@PackageManager@@QEAA?AW4MapsOperationTrigger@@XZ; PackageManager::GetCurrentOperationTrigger(void)
0x18001ce7c  mov     [rsp+720h+var_6C8], eax
0x18001ce80  call    ?GetCurrentOperationInfo@PackageManager@@QEAAKXZ; PackageManager::GetCurrentOperationInfo(void)
0x18001ce85  mov     [rsp+720h+var_6C4], eax
0x18001ce89  call    ?GetCurrentPackageSizeInKB@PackageManager@@QEAAIXZ; PackageManager::GetCurrentPackageSizeInKB(void)
0x18001ce8e  mov     dword ptr [rsp+720h+var_6B0], eax
0x18001ce92  mov     eax, [rsi+0EE0h]
0x18001ce98  mov     [rsp+720h+var_6C0], eax
0x18001ce9c  lea     rax, [rsi+10F8h]
0x18001cea3  lea     rcx, [rsi+10ECh]
0x18001ceaa  lea     rdx, [rsp+720h+var_6CC]
0x18001ceaf  mov     [rsp+720h+var_6D8], rdx
0x18001ceb4  lea     rdx, [rbp+620h+var_30]
0x18001cebb  mov     [rsp+720h+var_6E0], rdx
0x18001cec0  lea     rdx, [rbp+620h+var_47C]
0x18001cec7  mov     [rsp+720h+var_6E8], rdx
0x18001cecc  lea     rdx, [rsp+720h+var_6D0]
0x18001ced1  mov     [rsp+720h+var_6F0], rdx
0x18001ced6  mov     [rsp+720h+var_6F8], rax
0x18001cedb  mov     [rsp+720h+var_700], rcx
0x18001cee0  lea     r9, [rsp+720h+var_6C8]
0x18001cee5  lea     r8, [rsp+720h+var_6C4]
0x18001ceea  lea     rdx, [rsp+720h+var_6B0]
0x18001ceef  lea     rcx, [rsp+720h+var_6C0]
0x18001cef4  call    ??$OfflineMapCheckForUpdatesFailed@IIKHAEAU_FILETIME@@AEA_K_NAEAW4_STORAGE_DEVICE_TYPE@@AEAKAEAJ@OfflineMapsTelemetry@@SAX$$QEAI0$$QEAK$$QEAHAEAU_FILETIME@@AEA_K$$QEA_NAEAW4_STORAGE_DEVICE_TYPE@@AEAKAEAJ@Z; OfflineMapsTelemetry::OfflineMapCheckForUpdatesFailed<uint,uint,ulong,int,_FILETIME &,unsigned __int64 &,bool,_STORAGE_DEVICE_TYPE &,ulong &,long &>(uint &&,uint &&,ulong &&,int &&,_FILETIME &,unsigned __int64 &,bool &&,_STORAGE_DEVICE_TYPE &,ulong &,long &)
0x18001cef9  mov     byte ptr [rsi+10DAh], 0
0x18001cf00  mov     qword ptr [rsi+0DC0h], 0
0x18001cf0b  mov     dword ptr [rsi+0DD0h], 1
0x18001cf15  mov     [rsi+0DD4h], r14d
0x18001cf1c  mov     rcx, rsi; this
0x18001cf1f  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x18001cf24  nop
0x18001cf25  lea     rcx, [rbp+620h+var_6A0]; this
0x18001cf29  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001cf2e  mov     eax, r14d
0x18001cf31  mov     rcx, [rbp+620h+var_20]
0x18001cf38  xor     rcx, rsp; StackCookie
0x18001cf3b  call    __security_check_cookie
0x18001cf40  lea     r11, [rsp+720h+var_10]
0x18001cf48  mov     rbx, [r11+28h]
0x18001cf4c  mov     rsi, [r11+30h]
0x18001cf50  mov     rsp, r11
0x18001cf53  pop     r14
0x18001cf55  pop     rdi
0x18001cf56  pop     rbp
0x18001cf57  retn
```
