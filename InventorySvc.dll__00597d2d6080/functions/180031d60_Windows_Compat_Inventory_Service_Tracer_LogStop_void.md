# Windows::Compat::Inventory::Service::Tracer::LogStop(void)

- ea: `0x180031d60`
- end: `0x180031eb5`
- name: `?LogStop@Tracer@Service@Inventory@Compat@Windows@@IEAAJXZ`
- size: `341`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::Service::Tracer *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c6e80`
- `0x1800ca030`
- `0x1800cd160`
- `0x1800cd7b0`

## callees

- `0x1800152d0`
- `0x180031d60`
- `0x180031ebc`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031e56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031e56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031e4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031e4e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031dfb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031dfb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180031dc5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180031dc5`

## string_xrefs

- `0x180031e11`: `RegSetValueExW failed [%d]`
- `0x180031d97`: `Windows::Compat::Inventory::Service::Tracer::LogStop`
- `0x180031e18`: `Windows::Compat::Inventory::Service::Tracer::LogStop`
- `0x180031e8e`: `Windows::Compat::Inventory::Service::Tracer::LogStop`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::Service::Tracer::LogStop(
        Windows::Compat::Inventory::Service::Tracer *this)
{
  const wchar_t *v2; // rax
  unsigned int v3; // ebx
  HKEY v5; // rcx
  LSTATUS v6; // eax
  HKEY v7; // rsi
  DWORD LastError; // ebx
  struct _FILETIME v9; // r8
  int v10; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+8h] BYREF
  struct _FILETIME Data; // [rsp+48h] [rbp+10h] BYREF

  if ( !*((_QWORD *)this + 2) )
  {
    v2 = (const wchar_t *)(*(__int64 (__fastcall **)(Windows::Compat::Inventory::Service::Tracer *))(*(_QWORD *)this + 48LL))(this);
    v3 = -2147418113;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::Service::Tracer::LogStop",
      75,
      "Tracer %ls has not been started [%#x]",
      v2,
      -2147418113);
    return v3;
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v5 = (HKEY)*((_QWORD *)this + 2);
  Data = SystemTimeAsFileTime;
  v6 = RegSetValueExW(v5, L"EndTime", 0, 0xBu, (const BYTE *)&Data, 8u);
  v3 = v6;
  if ( v6 )
  {
    AslLogCallPrintf(1, "Windows::Compat::Inventory::Service::Tracer::LogStop", 89, "RegSetValueExW failed [%d]", v6);
    if ( (int)v3 > 0 )
      return (unsigned __int16)v3 | 0x80070000;
    return v3;
  }
  v7 = (HKEY)*((_QWORD *)this + 2);
  if ( v7 )
  {
    LastError = GetLastError();
    RegCloseKey(v7);
    SetLastError(LastError);
  }
  v9 = Data;
  *((_QWORD *)this + 2) = 0;
  v10 = Windows::Compat::Inventory::Service::Tracer::SendRunTelemetry(this, 0, *(_QWORD *)&v9 - *((_QWORD *)this + 1));
  v3 = v10;
  if ( v10 < 0 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::Service::Tracer::LogStop",
      97,
      "SendRunTelemetry failed [%#x]",
      v10);
    return v3;
  }
  return 0;
}

```

## disassembly

```asm
0x180031d60  mov     [rsp+arg_10], rbx
0x180031d65  mov     [rsp+arg_18], rsi
0x180031d6a  push    rdi
0x180031d6b  sub     rsp, 30h
0x180031d6f  cmp     qword ptr [rcx+10h], 0
0x180031d74  mov     rdi, rcx
0x180031d77  jnz     short loc_180031DB7
0x180031d79  mov     rax, [rcx]
0x180031d7c  mov     rax, [rax+30h]
0x180031d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d85  mov     r8d, 4Bh ; 'K'
0x180031d8b  lea     r9, aTracerLsHasNot; "Tracer %ls has not been started [%#x]"
0x180031d92  mov     ebx, 8000FFFFh
0x180031d97  lea     rdx, aWindowsCompatI_44; "Windows::Compat::Inventory::Service::Tr"...
0x180031d9e  mov     [rsp+38h+cbData], ebx
0x180031da2  mov     [rsp+38h+lpData], rax
0x180031da7  lea     ecx, [r8-4Ah]
0x180031dab  call    AslLogCallPrintf
0x180031db0  mov     eax, ebx
0x180031db2  jmp     loc_180031EA5
0x180031db7  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180031dbc  mov     qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180031dc5  call    cs:__imp_GetSystemTimeAsFileTime
0x180031dcb  mov     rax, qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime]
0x180031dd0  lea     rdx, aEndtime; "EndTime"
0x180031dd7  mov     rcx, [rdi+10h]; hKey
0x180031ddb  mov     r9d, 0Bh; dwType
0x180031de1  mov     [rsp+38h+Data], rax
0x180031de6  xor     r8d, r8d; Reserved
0x180031de9  lea     rax, [rsp+38h+Data]
0x180031dee  mov     [rsp+38h+cbData], 8; cbData
0x180031df6  mov     [rsp+38h+lpData], rax; lpData
0x180031dfb  call    cs:__imp_RegSetValueExW
0x180031e01  mov     ebx, eax
0x180031e03  test    eax, eax
0x180031e05  jz      short loc_180031E3A
0x180031e07  mov     r8d, 59h ; 'Y'
0x180031e0d  mov     dword ptr [rsp+38h+lpData], eax
0x180031e11  lea     r9, aRegsetvalueexw_0; "RegSetValueExW failed [%d]"
0x180031e18  lea     rdx, aWindowsCompatI_44; "Windows::Compat::Inventory::Service::Tr"...
0x180031e1f  lea     ecx, [r8-58h]
0x180031e23  call    AslLogCallPrintf
0x180031e28  test    ebx, ebx
0x180031e2a  jle     short loc_180031DB0
0x180031e2c  movzx   ebx, bx
0x180031e2f  or      ebx, 80070000h
0x180031e35  jmp     loc_180031DB0
0x180031e3a  mov     rsi, [rdi+10h]
0x180031e3e  test    rsi, rsi
0x180031e41  jz      short loc_180031E5C
0x180031e43  call    cs:__imp_GetLastError
0x180031e49  mov     rcx, rsi; hKey
0x180031e4c  mov     ebx, eax
0x180031e4e  call    cs:__imp_RegCloseKey
0x180031e54  mov     ecx, ebx; dwErrCode
0x180031e56  call    cs:__imp_SetLastError
0x180031e5c  mov     r8, [rsp+38h+Data]
0x180031e61  xor     edx, edx; int
0x180031e63  mov     qword ptr [rdi+10h], 0
0x180031e6b  mov     rcx, rdi; this
0x180031e6e  sub     r8, [rdi+8]; unsigned __int64
0x180031e72  call    ?SendRunTelemetry@Tracer@Service@Inventory@Compat@Windows@@AEAAJJ_K@Z; Windows::Compat::Inventory::Service::Tracer::SendRunTelemetry(long,unsigned __int64)
0x180031e77  mov     ebx, eax
0x180031e79  test    eax, eax
0x180031e7b  jns     short loc_180031EA3
0x180031e7d  mov     r8d, 61h ; 'a'
0x180031e83  mov     dword ptr [rsp+38h+lpData], eax
0x180031e87  lea     r9, aSendruntelemet; "SendRunTelemetry failed [%#x]"
0x180031e8e  lea     rdx, aWindowsCompatI_44; "Windows::Compat::Inventory::Service::Tr"...
0x180031e95  lea     ecx, [r8-60h]
0x180031e99  call    AslLogCallPrintf
0x180031e9e  jmp     loc_180031DB0
0x180031ea3  xor     eax, eax
0x180031ea5  mov     rbx, [rsp+38h+arg_10]
0x180031eaa  mov     rsi, [rsp+38h+arg_18]
0x180031eaf  add     rsp, 30h
0x180031eb3  pop     rdi
0x180031eb4  retn
```
