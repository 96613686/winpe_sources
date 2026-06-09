# ServiceManager::AddPackages(ulong,uint const *,MapsOperationTrigger)

- ea: `0x180012a40`
- end: `0x180012c01`
- name: `?AddPackages@ServiceManager@@UEAAJKPEBIW4MapsOperationTrigger@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(__int64, unsigned int, _DWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update`

## callers

- `0x1800128d0`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x180009d0c`
- `0x180009db4`
- `0x18000ea5c`
- `0x18000f67c`
- `0x18000f6a8`
- `0x18000f6d4`
- `0x180012a40`
- `0x180019e58`
- `0x18001af8c`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `MosStorage!MosStorageGetCurrentLocation` at `0x180012b37`
- `MosStorage!MosStorageGetCurrentLocation` at `0x180012b37`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180012b53`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180012b53`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180012aae`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180012aed`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180012aae`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180012aed`

## string_xrefs

- `0x180012aa5`: `ServiceManager::AddPackages`
- `0x180012ae4`: `ServiceManager::AddPackages`
- `0x180012b4a`: `ServiceManager::AddPackages`

## pseudocode

```c
__int64 __fastcall ServiceManager::AddPackages(__int64 a1, unsigned int a2, _DWORD *a3, unsigned int a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  int Operation; // eax
  int CurrentLocation; // eax
  bool v12; // si
  int CurrentOperationTrigger; // r14d
  PackageManager *v14; // rcx
  int CurrentOperationInfo; // r15d
  PackageManager *v16; // rcx
  unsigned int CurrentPackageSizeInKB; // ebp
  unsigned int v18; // r12d
  unsigned __int64 v19; // rdx
  unsigned __int8 v20; // cl
  OfflineMapsTelemetry *v21; // rax
  _BYTE v23[16]; // [rsp+50h] [rbp-6C8h] BYREF
  _BYTE v24[4]; // [rsp+60h] [rbp-6B8h] BYREF
  int v25; // [rsp+64h] [rbp-6B4h]
  unsigned int v26; // [rsp+274h] [rbp-4A4h]
  unsigned int v27; // [rsp+6C0h] [rbp-58h]

  CriticalSectionWithConditionVariable::Lock(a1 + 3400, v23);
  v8 = PackageManager::AddPackagesToInstall(a1 + 3568, a2, a3, a4);
  if ( v8 >= 0 )
  {
    RelockableGate::~RelockableGate((RelockableGate *)v23);
    Operation = ServiceManager::ProcessNextOperation((ServiceManager *)a1);
    if ( Operation >= 0 )
    {
      v9 = 0;
      if ( a2 && *(_DWORD *)(a1 + 3524) == 1 && *a3 == *(_DWORD *)(a1 + 3808) )
      {
        memset_0(v24, 0, 0x670u);
        CurrentLocation = MosStorageGetCurrentLocation((struct _STORAGE_DEVICE_DATA *)v24);
        if ( CurrentLocation < 0 )
          ZTraceReportIgnore(CurrentLocation, "ServiceManager::AddPackages", 798, (const void *)a1);
        v12 = v25 != 0;
        CurrentOperationTrigger = PackageManager::GetCurrentOperationTrigger(a1 + 3568);
        CurrentOperationInfo = PackageManager::GetCurrentOperationInfo(v14);
        CurrentPackageSizeInKB = PackageManager::GetCurrentPackageSizeInKB(v16);
        v18 = *(_DWORD *)(a1 + 3808);
        if ( OfflineMapsTelemetry::IsEnabled(v20, v19) )
        {
          v21 = OfflineMapsTelemetry::Instance();
          OfflineMapsTelemetry::OfflineMapDownloadStartPaused_(
            v21,
            v18,
            CurrentPackageSizeInKB,
            CurrentOperationInfo,
            CurrentOperationTrigger,
            *(struct _FILETIME *)(a1 + 4332),
            *(_QWORD *)(a1 + 4344),
            v12,
            v26,
            v27);
        }
      }
    }
    else
    {
      return (unsigned int)ZTraceReportPropagation(Operation, "ServiceManager::AddPackages", 789, (const void *)a1);
    }
  }
  else
  {
    v9 = ZTraceReportPropagation(v8, "ServiceManager::AddPackages", 786, (const void *)a1);
    RelockableGate::~RelockableGate((RelockableGate *)v23);
  }
  return v9;
}

```

## disassembly

```asm
0x180012a40  push    rbx
0x180012a42  push    rbp
0x180012a43  push    rsi
0x180012a44  push    rdi
0x180012a45  push    r12
0x180012a47  push    r14
0x180012a49  push    r15
0x180012a4b  sub     rsp, 6E0h
0x180012a52  mov     rax, cs:__security_cookie
0x180012a59  xor     rax, rsp
0x180012a5c  mov     [rsp+718h+var_48], rax
0x180012a64  mov     ebx, r9d
0x180012a67  mov     r14, r8
0x180012a6a  mov     esi, edx
0x180012a6c  mov     rdi, rcx
0x180012a6f  add     rcx, 0D48h
0x180012a76  lea     rdx, [rsp+718h+var_6C8]
0x180012a7b  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x180012a80  nop
0x180012a81  lea     rbp, [rdi+0DF0h]
0x180012a88  mov     r9d, ebx
0x180012a8b  mov     r8, r14
0x180012a8e  mov     edx, esi
0x180012a90  mov     rcx, rbp
0x180012a93  call    ?AddPackagesToInstall@PackageManager@@QEAAJKPEBIW4MapsOperationTrigger@@@Z; PackageManager::AddPackagesToInstall(ulong,uint const *,MapsOperationTrigger)
0x180012a98  test    eax, eax
0x180012a9a  jns     short loc_180012AC5
0x180012a9c  mov     r9, rdi
0x180012a9f  mov     r8d, 312h
0x180012aa5  lea     rdx, aServicemanager_76; "ServiceManager::AddPackages"
0x180012aac  mov     ecx, eax
0x180012aae  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180012ab4  mov     ebx, eax
0x180012ab6  lea     rcx, [rsp+718h+var_6C8]; this
0x180012abb  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180012ac0  jmp     loc_180012BDD
0x180012ac5  lea     rcx, [rsp+718h+var_6C8]; this
0x180012aca  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180012acf  mov     rcx, rdi; this
0x180012ad2  call    ?ProcessNextOperation@ServiceManager@@AEAAJXZ; ServiceManager::ProcessNextOperation(void)
0x180012ad7  test    eax, eax
0x180012ad9  jns     short loc_180012AFA
0x180012adb  mov     r9, rdi
0x180012ade  mov     r8d, 315h
0x180012ae4  lea     rdx, aServicemanager_76; "ServiceManager::AddPackages"
0x180012aeb  mov     ecx, eax
0x180012aed  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180012af3  mov     ebx, eax
0x180012af5  jmp     loc_180012BDD
0x180012afa  xor     ebx, ebx
0x180012afc  test    esi, esi
0x180012afe  jz      loc_180012BDD
0x180012b04  cmp     dword ptr [rdi+0DC4h], 1
0x180012b0b  jnz     loc_180012BDD
0x180012b11  mov     eax, [rdi+0EE0h]
0x180012b17  cmp     [r14], eax
0x180012b1a  jnz     loc_180012BDD
0x180012b20  xor     edx, edx; Val
0x180012b22  mov     r8d, 670h; Size
0x180012b28  lea     rcx, [rsp+718h+var_6B8]; void *
0x180012b2d  call    memset_0
0x180012b32  lea     rcx, [rsp+718h+var_6B8]
0x180012b37  call    cs:__imp_?MosStorageGetCurrentLocation@@YAJPEAU_STORAGE_DEVICE_DATA@@@Z; MosStorageGetCurrentLocation(_STORAGE_DEVICE_DATA *)
0x180012b3d  test    eax, eax
0x180012b3f  jns     short loc_180012B59
0x180012b41  mov     r9, rdi
0x180012b44  mov     r8d, 31Eh
0x180012b4a  lea     rdx, aServicemanager_76; "ServiceManager::AddPackages"
0x180012b51  mov     ecx, eax
0x180012b53  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180012b59  cmp     [rsp+718h+var_6B4], ebx
0x180012b5d  setnz   sil
0x180012b61  mov     rcx, rbp
0x180012b64  call    ?GetCurrentOperationTrigger@PackageManager@@QEAA?AW4MapsOperationTrigger@@XZ; PackageManager::GetCurrentOperationTrigger(void)
0x180012b69  mov     r14d, eax
0x180012b6c  call    ?GetCurrentOperationInfo@PackageManager@@QEAAKXZ; PackageManager::GetCurrentOperationInfo(void)
0x180012b71  mov     r15d, eax
0x180012b74  call    ?GetCurrentPackageSizeInKB@PackageManager@@QEAAIXZ; PackageManager::GetCurrentPackageSizeInKB(void)
0x180012b79  mov     ebp, eax
0x180012b7b  mov     r12d, [rdi+0EE0h]
0x180012b82  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180012b87  test    al, al
0x180012b89  jz      short loc_180012BDD
0x180012b8b  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180012b90  mov     rcx, [rdi+10ECh]
0x180012b97  mov     r8d, [rsp+718h+var_58]
0x180012b9f  mov     [rsp+718h+var_6D0], r8d; unsigned int
0x180012ba4  mov     r8d, [rsp+718h+var_4A4]
0x180012bac  mov     [rsp+718h+var_6D8], r8d; unsigned int
0x180012bb1  mov     [rsp+718h+var_6E0], sil; bool
0x180012bb6  mov     r8, [rdi+10F8h]
0x180012bbd  mov     [rsp+718h+var_6E8], r8; unsigned __int64
0x180012bc2  mov     qword ptr [rsp+718h+var_6F0.dwLowDateTime], rcx; struct _FILETIME
0x180012bc7  mov     [rsp+718h+var_6F8], r14d; int
0x180012bcc  mov     r9d, r15d; int
0x180012bcf  mov     r8d, ebp; unsigned int
0x180012bd2  mov     edx, r12d; unsigned int
0x180012bd5  mov     rcx, rax; this
0x180012bd8  call    ?OfflineMapDownloadStartPaused_@OfflineMapsTelemetry@@QEAAXIIHHU_FILETIME@@_K_NII@Z; OfflineMapsTelemetry::OfflineMapDownloadStartPaused_(uint,uint,int,int,_FILETIME,unsigned __int64,bool,uint,uint)
0x180012bdd  mov     eax, ebx
0x180012bdf  mov     rcx, [rsp+718h+var_48]
0x180012be7  xor     rcx, rsp; StackCookie
0x180012bea  call    __security_check_cookie
0x180012bef  add     rsp, 6E0h
0x180012bf6  pop     r15
0x180012bf8  pop     r14
0x180012bfa  pop     r12
0x180012bfc  pop     rdi
0x180012bfd  pop     rsi
0x180012bfe  pop     rbp
0x180012bff  pop     rbx
0x180012c00  retn
```
