# ServiceManager::CompleteUpdateCheck(long,bool)

- ea: `0x180014744`
- end: `0x180014975`
- name: `?CompleteUpdateCheck@ServiceManager@@QEAAXJ_N@Z`
- size: `561`
- prototype: `void __fastcall(ServiceManager *this, int, unsigned __int8)`
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180011480`
- `0x1800115e0`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x18000f67c`
- `0x18000f6a8`
- `0x18000f6d4`
- `0x1800117f0`
- `0x180014744`
- `0x180015ed0`
- `0x18001bcc0`
- `0x18001bce4`
- `0x18001ca00`
- `0x18001eec4`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001479e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001479e`
- `MosStorage!MosStorageGetCurrentLocation` at `0x180014826`
- `MosStorage!MosStorageGetCurrentLocation` at `0x180014826`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800147c6`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800147ed`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180014842`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800148fc`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800147c6`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800147ed`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180014842`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800148fc`

## string_xrefs

- `0x1800147a4`: `LastMapUpdateCheck`
- `0x1800147bd`: `ServiceManager::CompleteUpdateCheck`
- `0x1800147e4`: `ServiceManager::CompleteUpdateCheck`
- `0x180014839`: `ServiceManager::CompleteUpdateCheck`
- `0x1800148f3`: `ServiceManager::CompleteUpdateCheck`

## pseudocode

```c
void __fastcall ServiceManager::CompleteUpdateCheck(ServiceManager *this, int a2, unsigned __int8 a3)
{
  int v3; // esi
  ServiceManager *v6; // rcx
  int v7; // eax
  int v8; // eax
  int updated; // eax
  int v10; // r8d
  int CurrentLocation; // eax
  PackageManager *v12; // rcx
  PackageManager *v13; // rcx
  int v14; // [rsp+58h] [rbp-B0h] BYREF
  int CurrentOperationTrigger; // [rsp+5Ch] [rbp-ACh] BYREF
  unsigned int CurrentOperationInfo; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int CurrentPackageSizeInKB; // [rsp+64h] [rbp-A4h] BYREF
  unsigned int v18; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v19[24]; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v20[4]; // [rsp+88h] [rbp-80h] BYREF
  int v21; // [rsp+8Ch] [rbp-7Ch]
  unsigned int v22[275]; // [rsp+29Ch] [rbp+194h] BYREF
  unsigned int v23[4]; // [rsp+6E8h] [rbp+5E0h] BYREF
  int v24; // [rsp+730h] [rbp+628h] BYREF

  v24 = a2;
  v3 = a3;
  CriticalSectionWithConditionVariable::Lock((char *)this + 3400, v19);
  if ( a2 < 0 )
  {
    memset_0(v20, 0, 0x670u);
    CurrentLocation = MosStorageGetCurrentLocation((struct _STORAGE_DEVICE_DATA *)v20);
    if ( CurrentLocation < 0 )
      ZTraceReportIgnore(CurrentLocation, "ServiceManager::CompleteUpdateCheck", 442, this);
    LOBYTE(v14) = v21 != 0;
    CurrentOperationTrigger = PackageManager::GetCurrentOperationTrigger((char *)this + 3568);
    CurrentOperationInfo = PackageManager::GetCurrentOperationInfo(v12);
    CurrentPackageSizeInKB = PackageManager::GetCurrentPackageSizeInKB(v13);
    v18 = *((_DWORD *)this + 952);
    OfflineMapsTelemetry::OfflineMapCheckForUpdatesFailed<unsigned int,unsigned int,unsigned long,int,_FILETIME &,unsigned __int64 &,bool,enum _STORAGE_DEVICE_TYPE &,unsigned long &,long &>(
      &v18,
      &CurrentPackageSizeInKB,
      (int *)&CurrentOperationInfo,
      &CurrentOperationTrigger,
      (struct _FILETIME *)((char *)this + 4332),
      (unsigned __int64 *)this + 543,
      (bool *)&v14,
      v22,
      v23,
      &v24);
    updated = ServiceManager::SetUpdateAvailability(this, 0);
    if ( updated < 0 )
    {
      v10 = 446;
      goto LABEL_12;
    }
  }
  else
  {
    GetSystemTimeAsFileTime((LPFILETIME)this + 444);
    v7 = ServiceManager::SetMapsRegDateToNow(v6, L"LastMapUpdateCheck");
    if ( v7 < 0 )
      ZTraceReportIgnore(v7, "ServiceManager::CompleteUpdateCheck", 430, this);
    v8 = ServiceManager::SetUpdateAvailability(this, (unsigned int)(v3 + 1));
    if ( v8 < 0 )
      ZTraceReportIgnore(v8, "ServiceManager::CompleteUpdateCheck", 433, this);
    updated = ServiceManager::ShowUpdateToast(this, (unsigned int)(v3 + 1));
    if ( updated < 0 )
    {
      v10 = 436;
LABEL_12:
      ZTraceReportIgnore(updated, "ServiceManager::CompleteUpdateCheck", v10, this);
    }
  }
  ServiceWatchdog::Stop((ServiceManager *)((char *)this + 3944));
  *((_BYTE *)this + 4314) = 0;
  *((_QWORD *)this + 440) = 0;
  *((_DWORD *)this + 884) = 1;
  *((_DWORD *)this + 885) = a2;
  *((_DWORD *)this + 886) = v3 + 1;
  ServiceManager::FireOdmlStateChange(this);
  RelockableGate::~RelockableGate((RelockableGate *)v19);
}

```

## disassembly

```asm
0x180014744  mov     rax, rsp
0x180014747  mov     [rax+18h], rbx
0x18001474b  mov     [rax+20h], rsi
0x18001474f  mov     [rax+10h], edx
0x180014752  push    rbp
0x180014753  push    r14
0x180014755  push    r15
0x180014757  lea     rbp, [rax-618h]
0x18001475e  sub     rsp, 700h
0x180014765  mov     rax, cs:__security_cookie
0x18001476c  xor     rax, rsp
0x18001476f  mov     [rbp+610h+var_20], rax
0x180014776  movzx   esi, r8b
0x18001477a  mov     r14d, edx
0x18001477d  mov     rbx, rcx
0x180014780  add     rcx, 0D48h
0x180014787  lea     rdx, [rsp+710h+var_6A8]
0x18001478c  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x180014791  nop
0x180014792  test    r14d, r14d
0x180014795  js      short loc_180014811
0x180014797  lea     rcx, [rbx+0DE0h]; lpSystemTimeAsFileTime
0x18001479e  call    cs:__imp_GetSystemTimeAsFileTime
0x1800147a4  lea     rdx, aLastmapupdatec; "LastMapUpdateCheck"
0x1800147ab  call    ?SetMapsRegDateToNow@ServiceManager@@AEAAJPEBG@Z; ServiceManager::SetMapsRegDateToNow(ushort const *)
0x1800147b0  test    eax, eax
0x1800147b2  jns     short loc_1800147CC
0x1800147b4  mov     r9, rbx
0x1800147b7  mov     r8d, 1AEh
0x1800147bd  lea     rdx, aServicemanager_22; "ServiceManager::CompleteUpdateCheck"
0x1800147c4  mov     ecx, eax
0x1800147c6  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x1800147cc  lea     edx, [rsi+1]
0x1800147cf  mov     rcx, rbx
0x1800147d2  call    ?SetUpdateAvailability@ServiceManager@@AEAAJW4__MIDL_odmlapi_0005@@@Z; ServiceManager::SetUpdateAvailability(__MIDL_odmlapi_0005)
0x1800147d7  test    eax, eax
0x1800147d9  jns     short loc_1800147F3
0x1800147db  mov     r9, rbx
0x1800147de  mov     r8d, 1B1h
0x1800147e4  lea     rdx, aServicemanager_22; "ServiceManager::CompleteUpdateCheck"
0x1800147eb  mov     ecx, eax
0x1800147ed  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x1800147f3  lea     edx, [rsi+1]
0x1800147f6  mov     rcx, rbx
0x1800147f9  call    ?ShowUpdateToast@ServiceManager@@AEAAJW4__MIDL_odmlapi_0005@@@Z; ServiceManager::ShowUpdateToast(__MIDL_odmlapi_0005)
0x1800147fe  test    eax, eax
0x180014800  jns     loc_180014902
0x180014806  mov     r8d, 1B4h
0x18001480c  jmp     loc_1800148F0
0x180014811  xor     edx, edx; Val
0x180014813  mov     r8d, 670h; Size
0x180014819  lea     rcx, [rbp+610h+var_690]; void *
0x18001481d  call    memset_0
0x180014822  lea     rcx, [rbp+610h+var_690]
0x180014826  call    cs:__imp_?MosStorageGetCurrentLocation@@YAJPEAU_STORAGE_DEVICE_DATA@@@Z; MosStorageGetCurrentLocation(_STORAGE_DEVICE_DATA *)
0x18001482c  test    eax, eax
0x18001482e  jns     short loc_180014848
0x180014830  mov     r9, rbx
0x180014833  mov     r8d, 1BAh
0x180014839  lea     rdx, aServicemanager_22; "ServiceManager::CompleteUpdateCheck"
0x180014840  mov     ecx, eax
0x180014842  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180014848  cmp     [rbp+610h+var_68C], 0
0x18001484c  setnz   byte ptr [rsp+710h+var_6C0]
0x180014851  lea     rcx, [rbx+0DF0h]
0x180014858  call    ?GetCurrentOperationTrigger@PackageManager@@QEAA?AW4MapsOperationTrigger@@XZ; PackageManager::GetCurrentOperationTrigger(void)
0x18001485d  mov     [rsp+710h+var_6BC], eax
0x180014861  call    ?GetCurrentOperationInfo@PackageManager@@QEAAKXZ; PackageManager::GetCurrentOperationInfo(void)
0x180014866  mov     [rsp+710h+var_6B8], eax
0x18001486a  call    ?GetCurrentPackageSizeInKB@PackageManager@@QEAAIXZ; PackageManager::GetCurrentPackageSizeInKB(void)
0x18001486f  mov     [rsp+710h+var_6B4], eax
0x180014873  mov     eax, [rbx+0EE0h]
0x180014879  mov     [rsp+710h+var_6B0], eax
0x18001487d  lea     rax, [rbx+10F8h]
0x180014884  lea     rcx, [rbx+10ECh]
0x18001488b  lea     rdx, [rbp+610h+arg_8]
0x180014892  mov     qword ptr [rsp+710h+var_6C8], rdx
0x180014897  lea     rdx, [rbp+610h+var_30]
0x18001489e  mov     [rsp+710h+var_6D0], rdx
0x1800148a3  lea     rdx, [rbp+610h+var_47C]
0x1800148aa  mov     [rsp+710h+var_6D8], rdx
0x1800148af  lea     rdx, [rsp+710h+var_6C0]
0x1800148b4  mov     [rsp+710h+var_6E0], rdx
0x1800148b9  mov     [rsp+710h+var_6E8], rax
0x1800148be  mov     [rsp+710h+var_6F0], rcx
0x1800148c3  lea     r9, [rsp+710h+var_6BC]
0x1800148c8  lea     r8, [rsp+710h+var_6B8]
0x1800148cd  lea     rdx, [rsp+710h+var_6B4]
0x1800148d2  lea     rcx, [rsp+710h+var_6B0]
0x1800148d7  call    ??$OfflineMapCheckForUpdatesFailed@IIKHAEAU_FILETIME@@AEA_K_NAEAW4_STORAGE_DEVICE_TYPE@@AEAKAEAJ@OfflineMapsTelemetry@@SAX$$QEAI0$$QEAK$$QEAHAEAU_FILETIME@@AEA_K$$QEA_NAEAW4_STORAGE_DEVICE_TYPE@@AEAKAEAJ@Z; OfflineMapsTelemetry::OfflineMapCheckForUpdatesFailed<uint,uint,ulong,int,_FILETIME &,unsigned __int64 &,bool,_STORAGE_DEVICE_TYPE &,ulong &,long &>(uint &&,uint &&,ulong &&,int &&,_FILETIME &,unsigned __int64 &,bool &&,_STORAGE_DEVICE_TYPE &,ulong &,long &)
0x1800148dc  xor     edx, edx
0x1800148de  mov     rcx, rbx
0x1800148e1  call    ?SetUpdateAvailability@ServiceManager@@AEAAJW4__MIDL_odmlapi_0005@@@Z; ServiceManager::SetUpdateAvailability(__MIDL_odmlapi_0005)
0x1800148e6  test    eax, eax
0x1800148e8  jns     short loc_180014902
0x1800148ea  mov     r8d, 1BEh
0x1800148f0  mov     r9, rbx
0x1800148f3  lea     rdx, aServicemanager_22; "ServiceManager::CompleteUpdateCheck"
0x1800148fa  mov     ecx, eax
0x1800148fc  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180014902  lea     rcx, [rbx+0F68h]; this
0x180014909  call    ?Stop@ServiceWatchdog@@QEAAXXZ; ServiceWatchdog::Stop(void)
0x18001490e  mov     byte ptr [rbx+10DAh], 0
0x180014915  mov     qword ptr [rbx+0DC0h], 0
0x180014920  mov     dword ptr [rbx+0DD0h], 1
0x18001492a  mov     [rbx+0DD4h], r14d
0x180014931  lea     eax, [rsi+1]
0x180014934  mov     [rbx+0DD8h], eax
0x18001493a  mov     rcx, rbx; this
0x18001493d  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x180014942  nop
0x180014943  lea     rcx, [rsp+710h+var_6A8]; this
0x180014948  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001494d  mov     rcx, [rbp+610h+var_20]
0x180014954  xor     rcx, rsp; StackCookie
0x180014957  call    __security_check_cookie
0x18001495c  lea     r11, [rsp+710h+var_10]
0x180014964  mov     rbx, [r11+30h]
0x180014968  mov     rsi, [r11+38h]
0x18001496c  mov     rsp, r11
0x18001496f  pop     r15
0x180014971  pop     r14
0x180014973  pop     rbp
0x180014974  retn
```
