# StorageService::CompleteInit(void)

- ea: `0x180020140`
- end: `0x18002032d`
- name: `?CompleteInit@StorageService@@QEAAJXZ`
- size: `493`
- prototype: `__int64 __fastcall(StorageService *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002b090`

## callees

- `0x180001010`
- `0x180001148`
- `0x18000d560`
- `0x18001a70c`
- `0x180020140`
- `0x180027080`
- `0x180028064`
- `0x1800281ec`
- `0x18002b474`
- `0x18002d008`
- `0x18006c0bc`
- `0x18006d954`
- `0x18006f944`
- `0x180070550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800202ad`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800202ad`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180020231`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180020231`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800202a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800202a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002015d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800201ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800202e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002015d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800201ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800202e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180020258`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180020258`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StorageService::CompleteInit(StorageService *this)
{
  ULONGLONG TickCount64; // r15
  int LastHr; // edi
  __int64 v4; // rdx
  DiskMonitor *v5; // rax
  ULONGLONG v6; // r14
  PTP_TIMER ThreadpoolTimer; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  NVMeStorageHealthMonitor *v12; // [rsp+70h] [rbp+30h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp+38h] BYREF
  struct _FILETIME pftDueTime; // [rsp+80h] [rbp+40h] BYREF

  *((_DWORD *)this + 5) = 0;
  TickCount64 = GetTickCount64();
  StorageService::UpdateAppPairingState((__int64)this, 0, 0, 40);
  LastHr = StorageService::RegisterHostControllerHandler(this);
  if ( LastHr >= 0 )
  {
    LastHr = StorageService::RegisterVolumeHandler(this);
    if ( LastHr >= 0 )
    {
      StorageService::ProcessVolumeChange(this);
      McGenEventRegister_EventRegister(
        Microsoft_Windows_Storsvc,
        v4,
        Microsoft_Windows_Storsvc_Context,
        Microsoft_Windows_Storsvc_Context);
      v12 = (NVMeStorageHealthMonitor *)operator new(0xF0u);
      v5 = DiskMonitor::DiskMonitor(v12);
      *((_QWORD *)this + 239) = v5;
      DiskMonitor::StartMonitoringDisks(v5);
      if ( RegistryHelpers::IsStorageHealthMonitorEnabled() )
      {
        v6 = GetTickCount64();
        if ( v6 <= 0x927C0 )
        {
          ThreadpoolTimer = CreateThreadpoolTimer(StorageService::NVMeStorageHealthMonitorInitCallback, this, 0);
          *((_QWORD *)this + 242) = ThreadpoolTimer;
          if ( ThreadpoolTimer )
          {
            SystemTimeAsFileTime = 0;
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            v12 = (NVMeStorageHealthMonitor *)(10000 * (600000 - v6) + *(_QWORD *)&SystemTimeAsFileTime);
            pftDueTime = (struct _FILETIME)v12;
            SetThreadpoolTimer(*((PTP_TIMER *)this + 242), &pftDueTime, 0, 0xEA60u);
          }
          else
          {
            LastHr = GetLastHr();
          }
        }
        else
        {
          v12 = (NVMeStorageHealthMonitor *)operator new(8u);
          *((_QWORD *)this + 241) = NVMeStorageHealthMonitor::NVMeStorageHealthMonitor(v12);
        }
      }
    }
  }
  SetEvent(*((HANDLE *)this + 208));
  if ( (unsigned int)dword_1800BF000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
  {
    SystemTimeAsFileTime = (struct _FILETIME)0x1000000LL;
    LODWORD(v12) = LastHr;
    pftDueTime = (struct _FILETIME)(GetTickCount64() - TickCount64);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v8,
      (__int64)&word_1800A6856,
      v9,
      v10,
      (__int64)&pftDueTime,
      (__int64)&v12,
      (__int64)&SystemTimeAsFileTime);
  }
  return (unsigned int)LastHr;
}

```

## disassembly

```asm
0x180020140  mov     [rsp-28h+arg_18], rbx
0x180020145  push    rbp
0x180020146  push    rsi
0x180020147  push    rdi
0x180020148  push    r14
0x18002014a  push    r15
0x18002014c  mov     rbp, rsp
0x18002014f  sub     rsp, 40h
0x180020153  mov     rbx, rcx
0x180020156  mov     dword ptr [rcx+14h], 0
0x18002015d  call    cs:__imp_GetTickCount64
0x180020163  mov     r15, rax
0x180020166  mov     r9d, 28h ; '('
0x18002016c  xor     r8d, r8d
0x18002016f  xor     edx, edx
0x180020171  mov     rcx, rbx
0x180020174  call    ?UpdateAppPairingState@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::UpdateAppPairingState(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x180020179  mov     rcx, rbx; this
0x18002017c  call    ?RegisterHostControllerHandler@StorageService@@IEAAJXZ; StorageService::RegisterHostControllerHandler(void)
0x180020181  mov     edi, eax
0x180020183  test    eax, eax
0x180020185  js      loc_1800202A6
0x18002018b  mov     rcx, rbx; this
0x18002018e  call    ?RegisterVolumeHandler@StorageService@@IEAAJXZ; StorageService::RegisterVolumeHandler(void)
0x180020193  mov     edi, eax
0x180020195  test    eax, eax
0x180020197  js      loc_1800202A6
0x18002019d  mov     rcx, rbx; this
0x1800201a0  call    ?ProcessVolumeChange@StorageService@@QEAAJXZ; StorageService::ProcessVolumeChange(void)
0x1800201a5  lea     r8, Microsoft_Windows_Storsvc_Context
0x1800201ac  mov     r9, r8
0x1800201af  lea     rcx, Microsoft_Windows_Storsvc
0x1800201b6  call    McGenEventRegister_EventRegister
0x1800201bb  mov     ecx, 0F0h; Size
0x1800201c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800201c5  mov     [rbp+arg_0], rax
0x1800201c9  mov     rcx, rax; this
0x1800201cc  call    ??0DiskMonitor@@QEAA@XZ; DiskMonitor::DiskMonitor(void)
0x1800201d1  nop
0x1800201d2  mov     [rbx+778h], rax
0x1800201d9  mov     rcx, rax; this
0x1800201dc  call    ?StartMonitoringDisks@DiskMonitor@@QEAAX_NKKP6AXHAEBUDiskSummaryInfo@@1AEBV?$list@UDiskAnalysisResult@@V?$allocator@UDiskAnalysisResult@@@std@@@std@@@ZP6AXUDiskAnalysisResult@@@ZP6AXXZ6@Z; DiskMonitor::StartMonitoringDisks(bool,ulong,ulong,void (*)(int,DiskSummaryInfo const &,DiskSummaryInfo const &,std::list<DiskAnalysisResult> const &),void (*)(DiskAnalysisResult),void (*)(void),void (*)(void))
0x1800201e1  call    ?IsStorageHealthMonitorEnabled@RegistryHelpers@@SAEXZ; RegistryHelpers::IsStorageHealthMonitorEnabled(void)
0x1800201e6  test    al, al
0x1800201e8  jz      loc_1800202A6
0x1800201ee  call    cs:__imp_GetTickCount64
0x1800201f4  mov     r14, rax
0x1800201f7  mov     esi, 927C0h
0x1800201fc  cmp     rax, rsi
0x1800201ff  jbe     short loc_180020224
0x180020201  mov     ecx, 8; Size
0x180020206  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002020b  mov     [rbp+arg_0], rax
0x18002020f  mov     rcx, rax; this
0x180020212  call    ??0NVMeStorageHealthMonitor@@QEAA@XZ; NVMeStorageHealthMonitor::NVMeStorageHealthMonitor(void)
0x180020217  nop
0x180020218  mov     [rbx+788h], rax
0x18002021f  jmp     loc_1800202A6
0x180020224  xor     r8d, r8d; pcbe
0x180020227  mov     rdx, rbx; pv
0x18002022a  lea     rcx, ?NVMeStorageHealthMonitorInitCallback@StorageService@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180020231  call    cs:__imp_CreateThreadpoolTimer
0x180020237  mov     [rbx+790h], rax
0x18002023e  test    rax, rax
0x180020241  jnz     short loc_18002024C
0x180020243  call    ?GetLastHr@@YAJXZ; GetLastHr(void)
0x180020248  mov     edi, eax
0x18002024a  jmp     short loc_1800202A6
0x18002024c  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180020254  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180020258  call    cs:__imp_GetSystemTimeAsFileTime
0x18002025e  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x180020261  mov     dword ptr [rbp+arg_0+4], eax
0x180020264  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180020267  mov     dword ptr [rbp+arg_0], eax
0x18002026a  sub     rsi, r14
0x18002026d  imul    rcx, rsi, 2710h
0x180020274  mov     rax, [rbp+arg_0]
0x180020278  add     rax, rcx
0x18002027b  mov     [rbp+arg_0], rax
0x18002027f  shr     rax, 20h
0x180020283  mov     [rbp+pftDueTime.dwHighDateTime], eax
0x180020286  mov     eax, dword ptr [rbp+arg_0]
0x180020289  mov     [rbp+pftDueTime.dwLowDateTime], eax
0x18002028c  mov     r9d, 0EA60h; msWindowLength
0x180020292  xor     r8d, r8d; msPeriod
0x180020295  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x180020299  mov     rcx, [rbx+790h]; pti
0x1800202a0  call    cs:__imp_SetThreadpoolTimer
0x1800202a6  mov     rcx, [rbx+680h]; hEvent
0x1800202ad  call    cs:__imp_SetEvent
0x1800202b3  mov     eax, cs:dword_1800BF000
0x1800202b9  cmp     eax, 5
0x1800202bc  jbe     short loc_180020317
0x1800202be  mov     rdx, 400000000000h
0x1800202c8  lea     rcx, dword_1800BF000
0x1800202cf  call    _tlgKeywordOn
0x1800202d4  test    al, al
0x1800202d6  jz      short loc_180020317
0x1800202d8  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 1000000h
0x1800202e0  mov     dword ptr [rbp+arg_0], edi
0x1800202e3  call    cs:__imp_GetTickCount64
0x1800202e9  sub     rax, r15
0x1800202ec  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rax
0x1800202f0  lea     rax, [rbp+SystemTimeAsFileTime]
0x1800202f4  mov     [rsp+40h+var_10], rax
0x1800202f9  lea     rax, [rbp+arg_0]
0x1800202fd  mov     [rsp+40h+var_18], rax
0x180020302  lea     rax, [rbp+pftDueTime]
0x180020306  mov     [rsp+40h+var_20], rax
0x18002030b  lea     rdx, word_1800A6856
0x180020312  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180020317  mov     eax, edi
0x180020319  mov     rbx, [rsp+40h+arg_18]
0x180020321  add     rsp, 40h
0x180020325  pop     r15
0x180020327  pop     r14
0x180020329  pop     rdi
0x18002032a  pop     rsi
0x18002032b  pop     rbp
0x18002032c  retn
```
