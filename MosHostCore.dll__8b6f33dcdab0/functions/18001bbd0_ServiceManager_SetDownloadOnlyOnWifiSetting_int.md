# ServiceManager::SetDownloadOnlyOnWifiSetting(int)

- ea: `0x18001bbd0`
- end: `0x18001bc54`
- name: `?SetDownloadOnlyOnWifiSetting@ServiceManager@@UEAAJH@Z`
- size: `132`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update`

## callees

- `0x1800163e0`
- `0x18001bbd0`
- `0x18001db8c`
- `0x180020ec8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001bc07`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001bc07`

## string_xrefs

- `0x18001bc17`: `UpdateOnlyOnWifi`
- `0x18001bbfe`: `ServiceManager::SetDownloadOnlyOnWifiSetting`

## pseudocode

```c
int __fastcall ServiceManager::SetDownloadOnlyOnWifiSetting(ServiceManager *this, int a2, __int64 a3)
{
  int DownloadOnlyOnWifiSetting; // eax
  __int64 v6; // rcx
  __int64 v7; // r8
  int v8; // r8d
  int v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = 1;
  DownloadOnlyOnWifiSetting = ServiceManager::GetDownloadOnlyOnWifiSetting(this, &v10, a3);
  if ( DownloadOnlyOnWifiSetting < 0 )
  {
    v8 = 3002;
    return ZTraceReportPropagation(DownloadOnlyOnWifiSetting, "ServiceManager::SetDownloadOnlyOnWifiSetting", v8, this);
  }
  if ( a2 != v10 )
  {
    LOBYTE(v7) = a2 != 0;
    DownloadOnlyOnWifiSetting = RegUtils::SetMapsPersistedRegBoolean(v6, L"UpdateOnlyOnWifi", v7);
    if ( DownloadOnlyOnWifiSetting < 0 )
    {
      v8 = 3006;
      return ZTraceReportPropagation(
               DownloadOnlyOnWifiSetting,
               "ServiceManager::SetDownloadOnlyOnWifiSetting",
               v8,
               this);
    }
    DownloadOnlyOnWifiSetting = ServiceManager::UpdateTransferPolicies((struct _RTL_CRITICAL_SECTION *)this);
    if ( DownloadOnlyOnWifiSetting < 0 )
    {
      v8 = 3009;
      return ZTraceReportPropagation(
               DownloadOnlyOnWifiSetting,
               "ServiceManager::SetDownloadOnlyOnWifiSetting",
               v8,
               this);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001bbd0  mov     [rsp+arg_0], rbx
0x18001bbd5  push    rdi
0x18001bbd6  sub     rsp, 20h
0x18001bbda  mov     edi, edx
0x18001bbdc  mov     [rsp+28h+arg_10], 1
0x18001bbe4  lea     rdx, [rsp+28h+arg_10]; int *
0x18001bbe9  mov     rbx, rcx
0x18001bbec  call    ?GetDownloadOnlyOnWifiSetting@ServiceManager@@UEAAJPEAH@Z; ServiceManager::GetDownloadOnlyOnWifiSetting(int *)
0x18001bbf1  test    eax, eax
0x18001bbf3  jns     short loc_18001BC0F
0x18001bbf5  mov     r8d, 0BBAh
0x18001bbfb  mov     r9, rbx
0x18001bbfe  lea     rdx, aServicemanager_10; "ServiceManager::SetDownloadOnlyOnWifiSe"...
0x18001bc05  mov     ecx, eax
0x18001bc07  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001bc0d  jmp     short loc_18001BC49
0x18001bc0f  cmp     edi, [rsp+28h+arg_10]
0x18001bc13  jz      short loc_18001BC47
0x18001bc15  test    edi, edi
0x18001bc17  lea     rdx, aUpdateonlyonwi; "UpdateOnlyOnWifi"
0x18001bc1e  setnz   r8b
0x18001bc22  call    ?SetMapsPersistedRegBoolean@RegUtils@@SAJW4MapsRegKeys@@PEBG_N@Z; RegUtils::SetMapsPersistedRegBoolean(MapsRegKeys,ushort const *,bool)
0x18001bc27  test    eax, eax
0x18001bc29  jns     short loc_18001BC33
0x18001bc2b  mov     r8d, 0BBEh
0x18001bc31  jmp     short loc_18001BBFB
0x18001bc33  mov     rcx, rbx; this
0x18001bc36  call    ?UpdateTransferPolicies@ServiceManager@@AEAAJXZ; ServiceManager::UpdateTransferPolicies(void)
0x18001bc3b  test    eax, eax
0x18001bc3d  jns     short loc_18001BC47
0x18001bc3f  mov     r8d, 0BC1h
0x18001bc45  jmp     short loc_18001BBFB
0x18001bc47  xor     eax, eax
0x18001bc49  mov     rbx, [rsp+28h+arg_0]
0x18001bc4e  add     rsp, 20h
0x18001bc52  pop     rdi
0x18001bc53  retn
```
