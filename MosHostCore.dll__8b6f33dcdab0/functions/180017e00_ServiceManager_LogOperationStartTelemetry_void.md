# ServiceManager::LogOperationStartTelemetry(void)

- ea: `0x180017e00`
- end: `0x180018001`
- name: `?LogOperationStartTelemetry@ServiceManager@@AEAAXXZ`
- size: `513`
- prototype: `void __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x18001d224`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x180009d0c`
- `0x180009db4`
- `0x18000f67c`
- `0x18000f6a8`
- `0x18000f6d4`
- `0x180017e00`
- `0x1800191f8`
- `0x180019f70`
- `0x18001a3e4`

## import_xrefs

- `MosStorage!MosStorageGetCurrentLocation` at `0x180017e3c`
- `MosStorage!MosStorageGetCurrentLocation` at `0x180017e3c`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180017e58`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180017e58`

## string_xrefs

- `0x180017e49`: `ServiceManager::LogOperationStartTelemetry`

## pseudocode

```c
void __fastcall ServiceManager::LogOperationStartTelemetry(ServiceManager *this)
{
  int CurrentLocation; // eax
  bool v3; // di
  OfflineMapsTelemetry *v4; // rax
  bool v5; // di
  int v6; // esi
  PackageManager *v7; // rcx
  int v8; // ebp
  PackageManager *v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // r15d
  unsigned int v12; // r14d
  OfflineMapsTelemetry *v13; // rax
  bool v14; // di
  int CurrentOperationTrigger; // esi
  PackageManager *v16; // rcx
  int CurrentOperationInfo; // ebp
  PackageManager *v18; // rcx
  unsigned int CurrentPackageSizeInKB; // eax
  unsigned int v20; // r15d
  unsigned int v21; // r14d
  OfflineMapsTelemetry *v22; // rax
  _BYTE v23[4]; // [rsp+50h] [rbp-6B8h] BYREF
  int v24; // [rsp+54h] [rbp-6B4h]
  unsigned int v25; // [rsp+264h] [rbp-4A4h]
  unsigned int v26; // [rsp+6B0h] [rbp-58h]

  memset_0(v23, 0, 0x670u);
  CurrentLocation = MosStorageGetCurrentLocation((struct _STORAGE_DEVICE_DATA *)v23);
  if ( CurrentLocation < 0 )
    ZTraceReportIgnore(CurrentLocation, "ServiceManager::LogOperationStartTelemetry", 464, this);
  switch ( *((_DWORD *)this + 880) )
  {
    case 1:
      v14 = v24 != 0;
      CurrentOperationTrigger = PackageManager::GetCurrentOperationTrigger((char *)this + 3568);
      CurrentOperationInfo = PackageManager::GetCurrentOperationInfo(v16);
      CurrentPackageSizeInKB = PackageManager::GetCurrentPackageSizeInKB(v18);
      v20 = *((_DWORD *)this + 952);
      v21 = CurrentPackageSizeInKB;
      if ( OfflineMapsTelemetry::IsEnabled() )
      {
        v22 = OfflineMapsTelemetry::Instance();
        OfflineMapsTelemetry::OfflineMapDownloadStart_(
          v22,
          v20,
          v21,
          CurrentOperationInfo,
          CurrentOperationTrigger,
          *(struct _FILETIME *)((char *)this + 4332),
          *((_QWORD *)this + 543),
          v14,
          v25,
          v26);
      }
      break;
    case 2:
      v5 = v24 != 0;
      v6 = PackageManager::GetCurrentOperationTrigger((char *)this + 3568);
      v8 = PackageManager::GetCurrentOperationInfo(v7);
      v10 = PackageManager::GetCurrentPackageSizeInKB(v9);
      v11 = *((_DWORD *)this + 952);
      v12 = v10;
      if ( OfflineMapsTelemetry::IsEnabled() )
      {
        v13 = OfflineMapsTelemetry::Instance();
        OfflineMapsTelemetry::OfflineDeleteStart_(
          v13,
          v11,
          v12,
          v8,
          v6,
          *(struct _FILETIME *)((char *)this + 4332),
          *((_QWORD *)this + 543),
          v5,
          v25,
          v26);
      }
      break;
    case 3:
      v3 = v24 != 0;
      if ( OfflineMapsTelemetry::IsEnabled() )
      {
        v4 = OfflineMapsTelemetry::Instance();
        OfflineMapsTelemetry::OfflineMapUpdateStart_(
          v4,
          *(struct _FILETIME *)((char *)this + 4332),
          *((_QWORD *)this + 543),
          v3,
          v25,
          v26);
      }
      break;
  }
}

```

## disassembly

```asm
0x180017e00  push    rbx
0x180017e02  push    rbp
0x180017e03  push    rsi
0x180017e04  push    rdi
0x180017e05  push    r14
0x180017e07  push    r15
0x180017e09  sub     rsp, 6D8h
0x180017e10  mov     rax, cs:__security_cookie
0x180017e17  xor     rax, rsp
0x180017e1a  mov     [rsp+708h+var_48], rax
0x180017e22  mov     rbx, rcx
0x180017e25  xor     edx, edx; Val
0x180017e27  lea     rcx, [rsp+708h+var_6B8]; void *
0x180017e2c  mov     r8d, 670h; Size
0x180017e32  call    memset_0
0x180017e37  lea     rcx, [rsp+708h+var_6B8]
0x180017e3c  call    cs:__imp_?MosStorageGetCurrentLocation@@YAJPEAU_STORAGE_DEVICE_DATA@@@Z; MosStorageGetCurrentLocation(_STORAGE_DEVICE_DATA *)
0x180017e42  test    eax, eax
0x180017e44  jns     short loc_180017E5E
0x180017e46  mov     r9, rbx
0x180017e49  lea     rdx, aServicemanager_52; "ServiceManager::LogOperationStartTeleme"...
0x180017e50  mov     r8d, 1D0h
0x180017e56  mov     ecx, eax
0x180017e58  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180017e5e  mov     ecx, [rbx+0DC0h]
0x180017e64  sub     ecx, 1
0x180017e67  jz      loc_180017F5A
0x180017e6d  sub     ecx, 1; unsigned __int8
0x180017e70  jz      short loc_180017ECA
0x180017e72  cmp     ecx, 1
0x180017e75  jnz     loc_180017FE1
0x180017e7b  cmp     [rsp+708h+var_6B4], 0
0x180017e80  setnz   dil
0x180017e84  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180017e89  test    al, al
0x180017e8b  jz      loc_180017FE1
0x180017e91  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180017e96  mov     ecx, [rsp+708h+var_58]
0x180017e9d  mov     r9b, dil; bool
0x180017ea0  mov     r8, [rbx+10F8h]; unsigned __int64
0x180017ea7  mov     rdx, [rbx+10ECh]; struct _FILETIME
0x180017eae  mov     [rsp+708h+var_6E0.dwLowDateTime], ecx; unsigned int
0x180017eb2  mov     ecx, [rsp+708h+var_4A4]
0x180017eb9  mov     [rsp+708h+var_6E8], ecx; unsigned int
0x180017ebd  mov     rcx, rax; this
0x180017ec0  call    ?OfflineMapUpdateStart_@OfflineMapsTelemetry@@QEAAXU_FILETIME@@_K_NII@Z; OfflineMapsTelemetry::OfflineMapUpdateStart_(_FILETIME,unsigned __int64,bool,uint,uint)
0x180017ec5  jmp     loc_180017FE1
0x180017eca  cmp     [rsp+708h+var_6B4], 0
0x180017ecf  lea     rcx, [rbx+0DF0h]
0x180017ed6  setnz   dil
0x180017eda  call    ?GetCurrentOperationTrigger@PackageManager@@QEAA?AW4MapsOperationTrigger@@XZ; PackageManager::GetCurrentOperationTrigger(void)
0x180017edf  mov     esi, eax
0x180017ee1  call    ?GetCurrentOperationInfo@PackageManager@@QEAAKXZ; PackageManager::GetCurrentOperationInfo(void)
0x180017ee6  mov     ebp, eax
0x180017ee8  call    ?GetCurrentPackageSizeInKB@PackageManager@@QEAAIXZ; PackageManager::GetCurrentPackageSizeInKB(void)
0x180017eed  mov     r15d, [rbx+0EE0h]
0x180017ef4  mov     r14d, eax
0x180017ef7  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180017efc  test    al, al
0x180017efe  jz      loc_180017FE1
0x180017f04  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180017f09  mov     r8d, [rsp+708h+var_58]
0x180017f11  mov     r9d, ebp; int
0x180017f14  mov     rcx, [rbx+10ECh]
0x180017f1b  mov     edx, r15d; unsigned int
0x180017f1e  mov     [rsp+708h+var_6C0], r8d; unsigned int
0x180017f23  mov     r8d, [rsp+708h+var_4A4]
0x180017f2b  mov     [rsp+708h+var_6C8], r8d; unsigned int
0x180017f30  mov     r8, [rbx+10F8h]
0x180017f37  mov     [rsp+708h+var_6D0], dil; bool
0x180017f3c  mov     [rsp+708h+var_6D8], r8; unsigned __int64
0x180017f41  mov     r8d, r14d; unsigned int
0x180017f44  mov     qword ptr [rsp+708h+var_6E0.dwLowDateTime], rcx; struct _FILETIME
0x180017f49  mov     rcx, rax; this
0x180017f4c  mov     [rsp+708h+var_6E8], esi; int
0x180017f50  call    ?OfflineDeleteStart_@OfflineMapsTelemetry@@QEAAXIIHHU_FILETIME@@_K_NII@Z; OfflineMapsTelemetry::OfflineDeleteStart_(uint,uint,int,int,_FILETIME,unsigned __int64,bool,uint,uint)
0x180017f55  jmp     loc_180017FE1
0x180017f5a  cmp     [rsp+708h+var_6B4], 0
0x180017f5f  lea     rcx, [rbx+0DF0h]
0x180017f66  setnz   dil
0x180017f6a  call    ?GetCurrentOperationTrigger@PackageManager@@QEAA?AW4MapsOperationTrigger@@XZ; PackageManager::GetCurrentOperationTrigger(void)
0x180017f6f  mov     esi, eax
0x180017f71  call    ?GetCurrentOperationInfo@PackageManager@@QEAAKXZ; PackageManager::GetCurrentOperationInfo(void)
0x180017f76  mov     ebp, eax
0x180017f78  call    ?GetCurrentPackageSizeInKB@PackageManager@@QEAAIXZ; PackageManager::GetCurrentPackageSizeInKB(void)
0x180017f7d  mov     r15d, [rbx+0EE0h]
0x180017f84  mov     r14d, eax
0x180017f87  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180017f8c  test    al, al
0x180017f8e  jz      short loc_180017FE1
0x180017f90  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180017f95  mov     r8d, [rsp+708h+var_58]
0x180017f9d  mov     r9d, ebp; int
0x180017fa0  mov     rcx, [rbx+10ECh]
0x180017fa7  mov     edx, r15d; unsigned int
0x180017faa  mov     [rsp+708h+var_6C0], r8d; unsigned int
0x180017faf  mov     r8d, [rsp+708h+var_4A4]
0x180017fb7  mov     [rsp+708h+var_6C8], r8d; unsigned int
0x180017fbc  mov     r8, [rbx+10F8h]
0x180017fc3  mov     [rsp+708h+var_6D0], dil; bool
0x180017fc8  mov     [rsp+708h+var_6D8], r8; unsigned __int64
0x180017fcd  mov     r8d, r14d; unsigned int
0x180017fd0  mov     qword ptr [rsp+708h+var_6E0.dwLowDateTime], rcx; struct _FILETIME
0x180017fd5  mov     rcx, rax; this
0x180017fd8  mov     [rsp+708h+var_6E8], esi; int
0x180017fdc  call    ?OfflineMapDownloadStart_@OfflineMapsTelemetry@@QEAAXIIHHU_FILETIME@@_K_NII@Z; OfflineMapsTelemetry::OfflineMapDownloadStart_(uint,uint,int,int,_FILETIME,unsigned __int64,bool,uint,uint)
0x180017fe1  mov     rcx, [rsp+708h+var_48]
0x180017fe9  xor     rcx, rsp; StackCookie
0x180017fec  call    __security_check_cookie
0x180017ff1  add     rsp, 6D8h
0x180017ff8  pop     r15
0x180017ffa  pop     r14
0x180017ffc  pop     rdi
0x180017ffd  pop     rsi
0x180017ffe  pop     rbp
0x180017fff  pop     rbx
0x180018000  retn
```
