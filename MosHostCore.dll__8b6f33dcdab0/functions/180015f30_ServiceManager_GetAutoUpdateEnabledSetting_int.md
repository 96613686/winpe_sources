# ServiceManager::GetAutoUpdateEnabledSetting(int *)

- ea: `0x180015f30`
- end: `0x180015f93`
- name: `?GetAutoUpdateEnabledSetting@ServiceManager@@UEAAJPEAH@Z`
- size: `99`
- prototype: `__int64 __fastcall(ServiceManager *this, int *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x18001ca00`

## callees

- `0x180015f30`
- `0x180020720`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x180015f6f`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180015f6f`

## string_xrefs

- `0x180015f42`: `AutoUpdateEnabled`
- `0x180015f60`: `ServiceManager::GetAutoUpdateEnabledSetting`

## pseudocode

```c
__int64 __fastcall ServiceManager::GetAutoUpdateEnabledSetting(ServiceManager *this, int *a2, __int64 a3)
{
  int MapsPersistedRegBoolean; // eax
  unsigned int v6; // ecx
  char v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = 1;
  LOBYTE(a3) = 1;
  MapsPersistedRegBoolean = RegUtils::GetMapsPersistedRegBoolean(this, L"AutoUpdateEnabled", a3, &v8);
  if ( MapsPersistedRegBoolean >= 0 )
  {
    v6 = 0;
    *a2 = v8 != 0;
  }
  else
  {
    return (unsigned int)ZTraceReportPropagation(
                           MapsPersistedRegBoolean,
                           "ServiceManager::GetAutoUpdateEnabledSetting",
                           3025,
                           this);
  }
  return v6;
}

```

## disassembly

```asm
0x180015f30  mov     [rsp+arg_0], rbx
0x180015f35  push    rdi
0x180015f36  sub     rsp, 20h
0x180015f3a  mov     rbx, rdx
0x180015f3d  mov     [rsp+28h+arg_10], 1
0x180015f42  lea     rdx, aAutoupdateenab; "AutoUpdateEnabled"
0x180015f49  mov     r8b, 1
0x180015f4c  lea     r9, [rsp+28h+arg_10]
0x180015f51  mov     rdi, rcx
0x180015f54  call    ?GetMapsPersistedRegBoolean@RegUtils@@SAJW4MapsRegKeys@@PEBG_NPEA_N@Z; RegUtils::GetMapsPersistedRegBoolean(MapsRegKeys,ushort const *,bool,bool *)
0x180015f59  test    eax, eax
0x180015f5b  jns     short loc_180015F79
0x180015f5d  mov     r9, rdi
0x180015f60  lea     rdx, aServicemanager_40; "ServiceManager::GetAutoUpdateEnabledSet"...
0x180015f67  mov     r8d, 0BD1h
0x180015f6d  mov     ecx, eax
0x180015f6f  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180015f75  mov     ecx, eax
0x180015f77  jmp     short loc_180015F86
0x180015f79  xor     eax, eax
0x180015f7b  xor     ecx, ecx
0x180015f7d  cmp     [rsp+28h+arg_10], al
0x180015f81  setnz   al
0x180015f84  mov     [rbx], eax
0x180015f86  mov     rbx, [rsp+28h+arg_0]
0x180015f8b  mov     eax, ecx
0x180015f8d  add     rsp, 20h
0x180015f91  pop     rdi
0x180015f92  retn
```
