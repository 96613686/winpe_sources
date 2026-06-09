# ServiceManager::UpgradeToUnifiedStack(void)

- ea: `0x18001e1ac`
- end: `0x18001e280`
- name: `?UpgradeToUnifiedStack@ServiceManager@@AEAAJXZ`
- size: `212`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001546c`

## callees

- `0x180018508`
- `0x18001e1ac`
- `0x1800203f0`
- `0x180020720`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001e1f4`
- `ZTrace_Maps!ZTraceHelper` at `0x18001e220`
- `ZTrace_Maps!ZTraceHelper` at `0x18001e254`
- `ZTrace_Maps!ZTraceHelper` at `0x18001e220`
- `ZTrace_Maps!ZTraceHelper` at `0x18001e254`

## string_xrefs

- `0x18001e1e6`: `ServiceManager::UpgradeToUnifiedStack`
- `0x18001e200`: `ServiceManager::UpgradeToUnifiedStack`
- `0x18001e242`: `Device is already in the Unified stack. Nothing to do.`

## pseudocode

```c
int __fastcall ServiceManager::UpgradeToUnifiedStack(ServiceManager *this, __int64 a2, __int64 a3)
{
  bool v3; // zf
  int MapsPersistedRegBoolean; // eax
  ServiceManager *v6; // r9
  int v7; // r8d
  __int64 v9; // rcx
  char v10; // [rsp+40h] [rbp+8h] BYREF

  v3 = *((_DWORD *)this + 1080) == 3;
  v10 = 1;
  if ( !v3 )
    __int2c();
  LOBYTE(a3) = 1;
  MapsPersistedRegBoolean = RegUtils::GetMapsPersistedRegBoolean(this, L"UseMOSStack", a3, &v10);
  v6 = this;
  if ( MapsPersistedRegBoolean < 0 )
  {
    v7 = 3913;
    return ZTraceReportPropagation(MapsPersistedRegBoolean, "ServiceManager::UpgradeToUnifiedStack", v7, v6);
  }
  if ( v10 )
  {
    ZTraceHelper(
      3,
      "ServiceManager::UpgradeToUnifiedStack",
      3917,
      this,
      "Device is in the MOS stack. Migrating map data to the Unified stack.");
    MapsPersistedRegBoolean = ServiceManager::MigrateData(this, 1u);
    if ( MapsPersistedRegBoolean < 0 )
    {
      v6 = this;
      v7 = 3918;
      return ZTraceReportPropagation(MapsPersistedRegBoolean, "ServiceManager::UpgradeToUnifiedStack", v7, v6);
    }
  }
  else
  {
    ZTraceHelper(
      3,
      "ServiceManager::UpgradeToUnifiedStack",
      3922,
      this,
      "Device is already in the Unified stack. Nothing to do.");
    MapsPersistedRegBoolean = RegUtils::DeleteMapsPersistedRegValue(v9, L"UseMOSStack");
    if ( MapsPersistedRegBoolean < 0 )
    {
      v6 = this;
      v7 = 3925;
      return ZTraceReportPropagation(MapsPersistedRegBoolean, "ServiceManager::UpgradeToUnifiedStack", v7, v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001e1ac  push    rbx
0x18001e1ae  sub     rsp, 30h
0x18001e1b2  cmp     dword ptr [rcx+10E0h], 3
0x18001e1b9  mov     rbx, rcx
0x18001e1bc  mov     [rsp+38h+arg_0], 1
0x18001e1c1  jz      short loc_18001E1C5
0x18001e1c3  int     2Ch; Windows NT - assertion failure
0x18001e1c5  lea     r9, [rsp+38h+arg_0]
0x18001e1ca  mov     r8b, 1
0x18001e1cd  lea     rdx, aUsemosstack; "UseMOSStack"
0x18001e1d4  call    ?GetMapsPersistedRegBoolean@RegUtils@@SAJW4MapsRegKeys@@PEBG_NPEA_N@Z; RegUtils::GetMapsPersistedRegBoolean(MapsRegKeys,ushort const *,bool,bool *)
0x18001e1d9  mov     r9, rbx
0x18001e1dc  test    eax, eax
0x18001e1de  jns     short loc_18001E1FB
0x18001e1e0  mov     r8d, 0F49h
0x18001e1e6  lea     rdx, aServicemanager_35; "ServiceManager::UpgradeToUnifiedStack"
0x18001e1ed  mov     ecx, eax
0x18001e1ef  add     rsp, 30h
0x18001e1f3  pop     rbx
0x18001e1f4  jmp     cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001e1fb  cmp     [rsp+38h+arg_0], 0
0x18001e200  lea     rdx, aServicemanager_35; "ServiceManager::UpgradeToUnifiedStack"
0x18001e207  mov     ecx, 3
0x18001e20c  jz      short loc_18001E242
0x18001e20e  lea     rax, aDeviceIsInTheM; "Device is in the MOS stack. Migrating m"...
0x18001e215  mov     r8d, 0F4Dh
0x18001e21b  mov     [rsp+38h+var_18], rax
0x18001e220  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18001e226  mov     edx, 1
0x18001e22b  mov     rcx, rbx
0x18001e22e  call    ?MigrateData@ServiceManager@@AEAAJW4StackMode@@@Z; ServiceManager::MigrateData(StackMode)
0x18001e233  test    eax, eax
0x18001e235  jns     short loc_18001E278
0x18001e237  mov     r9, rbx
0x18001e23a  mov     r8d, 0F4Eh
0x18001e240  jmp     short loc_18001E1E6
0x18001e242  lea     rax, aDeviceIsAlread; "Device is already in the Unified stack."...
0x18001e249  mov     r8d, 0F52h
0x18001e24f  mov     [rsp+38h+var_18], rax
0x18001e254  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18001e25a  lea     rdx, aUsemosstack; "UseMOSStack"
0x18001e261  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x18001e266  test    eax, eax
0x18001e268  jns     short loc_18001E278
0x18001e26a  mov     r9, rbx
0x18001e26d  mov     r8d, 0F55h
0x18001e273  jmp     loc_18001E1E6
0x18001e278  xor     eax, eax
0x18001e27a  add     rsp, 30h
0x18001e27e  pop     rbx
0x18001e27f  retn
```
