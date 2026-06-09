# ServiceManager::DoUpgradeCheck(void)

- ea: `0x18001546c`
- end: `0x1800155e6`
- name: `?DoUpgradeCheck@ServiceManager@@AEAAJXZ`
- size: `378`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180015898`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x180009d0c`
- `0x180009db4`
- `0x18001546c`
- `0x18001a58c`
- `0x18001dee8`
- `0x18001e0ac`
- `0x18001e1ac`
- `0x1800207d0`
- `0x180020f6c`

## import_xrefs

- `MosStorage!MosStorageGetCurrentLocation` at `0x180015569`
- `MosStorage!MosStorageGetCurrentLocation` at `0x180015569`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180015581`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180015581`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800154c7`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800154c7`

## string_xrefs

- `0x1800154ae`: `ServiceManager::DoUpgradeCheck`

## pseudocode

```c
__int64 __fastcall ServiceManager::DoUpgradeCheck(ServiceManager *this)
{
  int MapsPersistedRegDword; // eax
  __int64 v3; // rcx
  unsigned int v4; // esi
  int v5; // r8d
  unsigned int v6; // edi
  int CurrentLocation; // eax
  unsigned __int64 v8; // rdx
  unsigned __int8 v9; // cl
  bool v10; // si
  OfflineMapsTelemetry *v11; // rax
  unsigned int v13[4]; // [rsp+30h] [rbp-6B8h] BYREF
  _BYTE v14[4]; // [rsp+40h] [rbp-6A8h] BYREF
  int v15; // [rsp+44h] [rbp-6A4h]
  unsigned int v16; // [rsp+254h] [rbp-494h]
  unsigned int v17; // [rsp+6A0h] [rbp-48h]

  v13[0] = 0;
  MapsPersistedRegDword = RegUtils::GetMapsPersistedRegDword((__int64)this, L"UpgradeCheck", 0, v13);
  v4 = v13[0];
  if ( MapsPersistedRegDword < 0 )
  {
    v5 = 3810;
LABEL_3:
    v6 = ZTraceReportPropagation(MapsPersistedRegDword, "ServiceManager::DoUpgradeCheck", v5, this);
    goto LABEL_18;
  }
  if ( v13[0] != 5 )
  {
    if ( v13[0] < 3 )
    {
      MapsPersistedRegDword = ServiceManager::UpgradeRegistryStateSeparation(this);
      if ( MapsPersistedRegDword < 0 )
      {
        v5 = 3817;
        goto LABEL_3;
      }
    }
    if ( *((_BYTE *)this + 4317) )
    {
      if ( v4 < 5 )
      {
        MapsPersistedRegDword = ServiceManager::UpgradeToChinaStack(this);
        if ( MapsPersistedRegDword < 0 )
        {
          v5 = 3831;
          goto LABEL_3;
        }
      }
    }
    else if ( v4 < 2 )
    {
      MapsPersistedRegDword = ServiceManager::UpgradeToUnifiedStack(this);
      if ( MapsPersistedRegDword < 0 )
      {
        v5 = 3824;
        goto LABEL_3;
      }
    }
    MapsPersistedRegDword = RegUtils::SetMapsPersistedRegDword(v3, L"UpgradeCheck", 5);
    if ( MapsPersistedRegDword < 0 )
    {
      v5 = 3836;
      goto LABEL_3;
    }
  }
  v6 = 0;
LABEL_18:
  if ( v4 != 5 )
  {
    memset_0(v14, 0, 0x670u);
    CurrentLocation = MosStorageGetCurrentLocation((struct _STORAGE_DEVICE_DATA *)v14);
    if ( CurrentLocation < 0 )
      ZTraceReportIgnore(CurrentLocation, "ServiceManager::DoUpgradeCheck", 3845, this);
    v10 = v15 != 0;
    if ( OfflineMapsTelemetry::IsEnabled(v9, v8) )
    {
      v11 = OfflineMapsTelemetry::Instance();
      OfflineMapsTelemetry::OfflineMapsUpgradeCheck_(v11, v10, v16, v17, *((_BYTE *)this + 4317), v6);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18001546c  push    rbx
0x18001546e  push    rsi
0x18001546f  push    rdi
0x180015470  push    r15
0x180015472  sub     rsp, 6C8h
0x180015479  mov     rax, cs:__security_cookie
0x180015480  xor     rax, rsp
0x180015483  mov     [rsp+6E8h+var_38], rax
0x18001548b  lea     r9, [rsp+6E8h+var_6B8]
0x180015490  mov     [rsp+6E8h+var_6B8], 0
0x180015498  xor     r8d, r8d
0x18001549b  lea     rdx, aUpgradecheck; "UpgradeCheck"
0x1800154a2  mov     rbx, rcx
0x1800154a5  call    ?GetMapsPersistedRegDword@RegUtils@@SAJW4MapsRegKeys@@PEBGKPEAK@Z; RegUtils::GetMapsPersistedRegDword(MapsRegKeys,ushort const *,ulong,ulong *)
0x1800154aa  mov     esi, [rsp+6E8h+var_6B8]
0x1800154ae  lea     r15, aServicemanager_6; "ServiceManager::DoUpgradeCheck"
0x1800154b5  test    eax, eax
0x1800154b7  jns     short loc_1800154D1
0x1800154b9  mov     r8d, 0EE2h
0x1800154bf  mov     r9, rbx
0x1800154c2  mov     rdx, r15
0x1800154c5  mov     ecx, eax
0x1800154c7  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x1800154cd  mov     edi, eax
0x1800154cf  jmp     short loc_18001554D
0x1800154d1  cmp     esi, 5
0x1800154d4  jz      short loc_18001554B
0x1800154d6  cmp     esi, 3
0x1800154d9  jnb     short loc_1800154EF
0x1800154db  mov     rcx, rbx; this
0x1800154de  call    ?UpgradeRegistryStateSeparation@ServiceManager@@AEAAJXZ; ServiceManager::UpgradeRegistryStateSeparation(void)
0x1800154e3  test    eax, eax
0x1800154e5  jns     short loc_1800154EF
0x1800154e7  mov     r8d, 0EE9h
0x1800154ed  jmp     short loc_1800154BF
0x1800154ef  cmp     byte ptr [rbx+10DDh], 0
0x1800154f6  jnz     short loc_180015511
0x1800154f8  cmp     esi, 2
0x1800154fb  jnb     short loc_18001552A
0x1800154fd  mov     rcx, rbx; this
0x180015500  call    ?UpgradeToUnifiedStack@ServiceManager@@AEAAJXZ; ServiceManager::UpgradeToUnifiedStack(void)
0x180015505  test    eax, eax
0x180015507  jns     short loc_18001552A
0x180015509  mov     r8d, 0EF0h
0x18001550f  jmp     short loc_1800154BF
0x180015511  cmp     esi, 5
0x180015514  jnb     short loc_18001552A
0x180015516  mov     rcx, rbx; this
0x180015519  call    ?UpgradeToChinaStack@ServiceManager@@AEAAJXZ; ServiceManager::UpgradeToChinaStack(void)
0x18001551e  test    eax, eax
0x180015520  jns     short loc_18001552A
0x180015522  mov     r8d, 0EF7h
0x180015528  jmp     short loc_1800154BF
0x18001552a  mov     r8d, 5
0x180015530  lea     rdx, aUpgradecheck; "UpgradeCheck"
0x180015537  call    ?SetMapsPersistedRegDword@RegUtils@@SAJW4MapsRegKeys@@PEBGK@Z; RegUtils::SetMapsPersistedRegDword(MapsRegKeys,ushort const *,ulong)
0x18001553c  test    eax, eax
0x18001553e  jns     short loc_18001554B
0x180015540  mov     r8d, 0EFCh
0x180015546  jmp     loc_1800154BF
0x18001554b  xor     edi, edi
0x18001554d  cmp     esi, 5
0x180015550  jz      short loc_1800155C7
0x180015552  xor     edx, edx; Val
0x180015554  lea     rcx, [rsp+6E8h+var_6A8]; void *
0x180015559  mov     r8d, 670h; Size
0x18001555f  call    memset_0
0x180015564  lea     rcx, [rsp+6E8h+var_6A8]
0x180015569  call    cs:__imp_?MosStorageGetCurrentLocation@@YAJPEAU_STORAGE_DEVICE_DATA@@@Z; MosStorageGetCurrentLocation(_STORAGE_DEVICE_DATA *)
0x18001556f  test    eax, eax
0x180015571  jns     short loc_180015587
0x180015573  mov     r9, rbx
0x180015576  mov     r8d, 0F05h
0x18001557c  mov     rdx, r15
0x18001557f  mov     ecx, eax
0x180015581  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180015587  cmp     [rsp+6E8h+var_6A4], 0
0x18001558c  setnz   sil
0x180015590  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180015595  test    al, al
0x180015597  jz      short loc_1800155C7
0x180015599  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18001559e  mov     cl, [rbx+10DDh]
0x1800155a4  mov     dl, sil; bool
0x1800155a7  mov     r9d, [rsp+6E8h+var_48]; unsigned int
0x1800155af  mov     r8d, [rsp+6E8h+var_494]; unsigned int
0x1800155b7  mov     [rsp+6E8h+var_6C0], edi; int
0x1800155bb  mov     [rsp+6E8h+var_6C8], cl; bool
0x1800155bf  mov     rcx, rax; this
0x1800155c2  call    ?OfflineMapsUpgradeCheck_@OfflineMapsTelemetry@@QEAAX_NII0J@Z; OfflineMapsTelemetry::OfflineMapsUpgradeCheck_(bool,uint,uint,bool,long)
0x1800155c7  mov     eax, edi
0x1800155c9  mov     rcx, [rsp+6E8h+var_38]
0x1800155d1  xor     rcx, rsp; StackCookie
0x1800155d4  call    __security_check_cookie
0x1800155d9  add     rsp, 6C8h
0x1800155e0  pop     r15
0x1800155e2  pop     rdi
0x1800155e3  pop     rsi
0x1800155e4  pop     rbx
0x1800155e5  retn
```
