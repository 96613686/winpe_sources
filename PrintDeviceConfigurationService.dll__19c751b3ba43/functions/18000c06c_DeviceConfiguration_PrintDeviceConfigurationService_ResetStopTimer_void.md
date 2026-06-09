# DeviceConfiguration::PrintDeviceConfigurationService::ResetStopTimer(void)

- ea: `0x18000c06c`
- end: `0x18000c0e7`
- name: `?ResetStopTimer@PrintDeviceConfigurationService@DeviceConfiguration@@QEAAXXZ`
- size: `123`
- prototype: `void __fastcall(DeviceConfiguration::PrintDeviceConfigurationService *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000bac8`
- `0x18000ed18`
- `0x180011c38`
- `0x1800121c0`

## callees

- `0x180004e44`
- `0x18000aeac`
- `0x18000c06c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c093`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c093`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c0cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c0cc`

## string_xrefs

- `0x18000c080`: `DeviceConfiguration::PrintDeviceConfigurationService::ResetStopTimer`

## pseudocode

```c
void __fastcall DeviceConfiguration::PrintDeviceConfigurationService::ResetStopTimer(
        DeviceConfiguration::PrintDeviceConfigurationService *this)
{
  bool v2; // zf
  __int64 v3; // rax
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v5; // [rsp+38h] [rbp+10h] BYREF

  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::PrintDeviceConfigurationService::ResetStopTimer",
    L"Setting stop timer...");
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v2 = *((_BYTE *)this + 36) == 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
  if ( v2 )
  {
    v3 = -10000LL * *((unsigned int *)this + 8);
    pftDueTime.dwLowDateTime = -10000 * *((_DWORD *)this + 8);
    pftDueTime.dwHighDateTime = HIDWORD(v3);
    SetThreadpoolTimer(*((PTP_TIMER *)this + 3), &pftDueTime, 0, 0);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v5);
}

```

## disassembly

```asm
0x18000c06c  mov     [rsp+arg_10], rbx
0x18000c071  push    rdi
0x18000c072  sub     rsp, 20h
0x18000c076  mov     rdi, rcx
0x18000c079  lea     rdx, aSettingStopTim; "Setting stop timer..."
0x18000c080  lea     rcx, aDeviceconfigur_8; "DeviceConfiguration::PrintDeviceConfigu"...
0x18000c087  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000c08c  lea     rbx, [rdi+28h]
0x18000c090  mov     rcx, rbx; lpCriticalSection
0x18000c093  call    cs:__imp_EnterCriticalSection
0x18000c099  cmp     byte ptr [rdi+24h], 0
0x18000c09d  mov     [rsp+28h+arg_8], rbx
0x18000c0a2  jnz     short loc_18000C0D2
0x18000c0a4  mov     eax, [rdi+20h]
0x18000c0a7  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000c0ac  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18000c0b3  xor     r9d, r9d; msWindowLength
0x18000c0b6  xor     r8d, r8d; msPeriod
0x18000c0b9  mov     rcx, rax
0x18000c0bc  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18000c0c0  shr     rcx, 20h
0x18000c0c4  mov     [rsp+28h+pftDueTime.dwHighDateTime], ecx
0x18000c0c8  mov     rcx, [rdi+18h]; pti
0x18000c0cc  call    cs:__imp_SetThreadpoolTimer
0x18000c0d2  lea     rcx, [rsp+28h+arg_8]
0x18000c0d7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000c0dc  mov     rbx, [rsp+28h+arg_10]
0x18000c0e1  add     rsp, 20h
0x18000c0e5  pop     rdi
0x18000c0e6  retn
```
