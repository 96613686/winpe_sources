# DebugFlags::InitRegistry(void)

- ea: `0x180010070`
- end: `0x1800101e2`
- name: `?InitRegistry@DebugFlags@@CAXXZ`
- size: `370`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f654`

## callees

- `0x18000fed8`
- `0x18000ffc0`
- `0x180010070`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800100a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800100cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800100a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800100cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800101cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800101cc`

## string_xrefs

- `0x180010093`: `Software\Microsoft\COM3\Debug`
- `0x1800100bd`: `Software\Microsoft\COM3\Debug`
- `0x180010112`: `DebugBreakOnInitComPlus`
- `0x180010129`: `DebugBreakOnLoadComsvcs`
- `0x18001019c`: `TraceSecurity`
- `0x1800101b3`: `TraceSecurityPM`

## pseudocode

```c
void DebugFlags::InitRegistry(void)
{
  const unsigned __int16 *v0; // rdx
  unsigned int *v1; // r8
  HKEY hKey; // [rsp+40h] [rbp+10h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\COM3\\Debug", 0, 0x2001Bu, &hKey)
    || !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\COM3\\Debug", 0, 0x20019u, &hKey) )
  {
    DebugFlags::InitBoolean(hKey, L"AutoAddTraceToContext", &DebugFlags::sm_fAutoAddTraceToContext);
    DebugFlags::InitBoolean(hKey, L"DebugBreakOnFailFast", &DebugFlags::sm_fDebugBreakOnFailFast);
    DebugFlags::InitBoolean(hKey, L"DebugBreakOnInitComPlus", &DebugFlags::sm_fDebugBreakOnInitComPlus);
    DebugFlags::InitBoolean(hKey, L"DebugBreakOnLoadComsvcs", &DebugFlags::sm_fDebugBreakOnLoadComsvcs);
    DebugFlags::InitBoolean(hKey, L"TraceActivityModule", &DebugFlags::sm_fTraceActivityModule);
    DebugFlags::InitBoolean(hKey, L"TraceContextCreation", &DebugFlags::sm_fTraceContextCreation);
    DebugFlags::InitBoolean(hKey, L"TraceInfrastructureCalls", &DebugFlags::sm_fTraceInfrastructureCalls);
    DebugFlags::InitBoolean(hKey, L"TraceSTAPool", &DebugFlags::sm_fTraceSTAPool);
    DebugFlags::InitBoolean(hKey, L"TraceSecurity", &DebugFlags::sm_fTraceSecurity);
    DebugFlags::InitBoolean(hKey, L"TraceSecurityPM", &DebugFlags::sm_fTraceSecurityPM);
    DebugFlags::InitDWORD(hKey, v0, v1);
    RegCloseKey(hKey);
  }
  DebugFlags::sm_registryInitialized = 1;
}

```

## disassembly

```asm
0x180010070  push    rbp
0x180010072  mov     rbp, rsp
0x180010075  sub     rsp, 30h
0x180010079  lea     rax, [rbp+hKey]
0x18001007d  mov     [rbp+hKey], 0
0x180010085  mov     r9d, 2001Bh; samDesired
0x18001008b  mov     [rsp+30h+phkResult], rax; phkResult
0x180010090  xor     r8d, r8d; ulOptions
0x180010093  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\COM3\\Debug"
0x18001009a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800100a1  call    cs:__imp_RegOpenKeyExW
0x1800100a7  test    eax, eax
0x1800100a9  jz      short loc_1800100D9
0x1800100ab  lea     rax, [rbp+hKey]
0x1800100af  mov     r9d, 20019h; samDesired
0x1800100b5  xor     r8d, r8d; ulOptions
0x1800100b8  mov     [rsp+30h+phkResult], rax; phkResult
0x1800100bd  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\COM3\\Debug"
0x1800100c4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800100cb  call    cs:__imp_RegOpenKeyExW
0x1800100d1  test    eax, eax
0x1800100d3  jnz     loc_1800101D2
0x1800100d9  mov     rcx, [rbp+hKey]; hKey
0x1800100dd  lea     r8, ?sm_fAutoAddTraceToContext@DebugFlags@@0HA; int *
0x1800100e4  lea     rdx, aAutoaddtraceto; "AutoAddTraceToContext"
0x1800100eb  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x1800100f0  mov     rcx, [rbp+hKey]; hKey
0x1800100f4  lea     r8, ?sm_fDebugBreakOnFailFast@DebugFlags@@0HA; int *
0x1800100fb  lea     rdx, aDebugbreakonfa; "DebugBreakOnFailFast"
0x180010102  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180010107  mov     rcx, [rbp+hKey]; hKey
0x18001010b  lea     r8, ?sm_fDebugBreakOnInitComPlus@DebugFlags@@0HA; int *
0x180010112  lea     rdx, aDebugbreakonin; "DebugBreakOnInitComPlus"
0x180010119  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18001011e  mov     rcx, [rbp+hKey]; hKey
0x180010122  lea     r8, ?sm_fDebugBreakOnLoadComsvcs@DebugFlags@@0HA; int *
0x180010129  lea     rdx, aDebugbreakonlo; "DebugBreakOnLoadComsvcs"
0x180010130  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180010135  mov     rcx, [rbp+hKey]; hKey
0x180010139  lea     r8, ?sm_fTraceActivityModule@DebugFlags@@0HA; int *
0x180010140  lea     rdx, aTraceactivitym; "TraceActivityModule"
0x180010147  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18001014c  mov     rcx, [rbp+hKey]; hKey
0x180010150  lea     r8, ?sm_fTraceContextCreation@DebugFlags@@0HA; int *
0x180010157  lea     rdx, aTracecontextcr; "TraceContextCreation"
0x18001015e  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180010163  mov     rcx, [rbp+hKey]; hKey
0x180010167  lea     r8, ?sm_fTraceInfrastructureCalls@DebugFlags@@0HA; int *
0x18001016e  lea     rdx, aTraceinfrastru; "TraceInfrastructureCalls"
0x180010175  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18001017a  mov     rcx, [rbp+hKey]; hKey
0x18001017e  lea     r8, ?sm_fTraceSTAPool@DebugFlags@@0HA; int *
0x180010185  lea     rdx, aTracestapool; "TraceSTAPool"
0x18001018c  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180010191  mov     rcx, [rbp+hKey]; hKey
0x180010195  lea     r8, ?sm_fTraceSecurity@DebugFlags@@0HA; int *
0x18001019c  lea     rdx, aTracesecurity; "TraceSecurity"
0x1800101a3  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x1800101a8  mov     rcx, [rbp+hKey]; hKey
0x1800101ac  lea     r8, ?sm_fTraceSecurityPM@DebugFlags@@0HA; int *
0x1800101b3  lea     rdx, aTracesecurityp; "TraceSecurityPM"
0x1800101ba  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x1800101bf  mov     rcx, [rbp+hKey]; hKey
0x1800101c3  call    ?InitDWORD@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAK@Z; DebugFlags::InitDWORD(HKEY__ *,ushort const *,ulong *)
0x1800101c8  mov     rcx, [rbp+hKey]; hKey
0x1800101cc  call    cs:__imp_RegCloseKey
0x1800101d2  mov     cs:?sm_registryInitialized@DebugFlags@@0HA, 1; int DebugFlags::sm_registryInitialized
0x1800101dc  add     rsp, 30h
0x1800101e0  pop     rbp
0x1800101e1  retn
```
