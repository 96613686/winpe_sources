# ServiceManager::GetDownloadOnlyOnWifiSetting(int *)

- ea: `0x1800163e0`
- end: `0x180016443`
- name: `?GetDownloadOnlyOnWifiSetting@ServiceManager@@UEAAJPEAH@Z`
- size: `99`
- prototype: `__int64 __fastcall(ServiceManager *this, int *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x18001bbd0`
- `0x18001db8c`

## callees

- `0x1800163e0`
- `0x180020720`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001641f`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001641f`

## string_xrefs

- `0x1800163f2`: `UpdateOnlyOnWifi`
- `0x180016410`: `ServiceManager::GetDownloadOnlyOnWifiSetting`

## pseudocode

```c
__int64 __fastcall ServiceManager::GetDownloadOnlyOnWifiSetting(ServiceManager *this, int *a2, __int64 a3)
{
  int MapsPersistedRegBoolean; // eax
  unsigned int v6; // ecx
  char v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = 1;
  LOBYTE(a3) = 1;
  MapsPersistedRegBoolean = RegUtils::GetMapsPersistedRegBoolean(this, L"UpdateOnlyOnWifi", a3, &v8);
  if ( MapsPersistedRegBoolean >= 0 )
  {
    v6 = 0;
    *a2 = v8 != 0;
  }
  else
  {
    return (unsigned int)ZTraceReportPropagation(
                           MapsPersistedRegBoolean,
                           "ServiceManager::GetDownloadOnlyOnWifiSetting",
                           3043,
                           this);
  }
  return v6;
}

```

## disassembly

```asm
0x1800163e0  mov     [rsp+arg_0], rbx
0x1800163e5  push    rdi
0x1800163e6  sub     rsp, 20h
0x1800163ea  mov     rbx, rdx
0x1800163ed  mov     [rsp+28h+arg_10], 1
0x1800163f2  lea     rdx, aUpdateonlyonwi; "UpdateOnlyOnWifi"
0x1800163f9  mov     r8b, 1
0x1800163fc  lea     r9, [rsp+28h+arg_10]
0x180016401  mov     rdi, rcx
0x180016404  call    ?GetMapsPersistedRegBoolean@RegUtils@@SAJW4MapsRegKeys@@PEBG_NPEA_N@Z; RegUtils::GetMapsPersistedRegBoolean(MapsRegKeys,ushort const *,bool,bool *)
0x180016409  test    eax, eax
0x18001640b  jns     short loc_180016429
0x18001640d  mov     r9, rdi
0x180016410  lea     rdx, aServicemanager_31; "ServiceManager::GetDownloadOnlyOnWifiSe"...
0x180016417  mov     r8d, 0BE3h
0x18001641d  mov     ecx, eax
0x18001641f  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180016425  mov     ecx, eax
0x180016427  jmp     short loc_180016436
0x180016429  xor     eax, eax
0x18001642b  xor     ecx, ecx
0x18001642d  cmp     [rsp+28h+arg_10], al
0x180016431  setnz   al
0x180016434  mov     [rbx], eax
0x180016436  mov     rbx, [rsp+28h+arg_0]
0x18001643b  mov     eax, ecx
0x18001643d  add     rsp, 20h
0x180016441  pop     rdi
0x180016442  retn
```
