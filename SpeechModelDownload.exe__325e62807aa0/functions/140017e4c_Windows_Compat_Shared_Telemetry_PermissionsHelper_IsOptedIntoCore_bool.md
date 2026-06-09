# Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)

- ea: `0x140017e4c`
- end: `0x140017f3b`
- name: `?IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z`
- size: `239`
- prototype: `char __fastcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140018a94`

## callees

- `0x140002600`
- `0x1400030dc`
- `0x140017e4c`
- `0x140017f44`

## import_xrefs

- `ntdll!WinSqmIsOptedInEx` at `0x140017f02`
- `ntdll!WinSqmIsOptedInEx` at `0x140017f02`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x140017ea6`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x140017eb7`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x140017ec8`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x140017ea6`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x140017eb7`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x140017ec8`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x140017eec`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x140017eec`

## pseudocode

```c
char __fastcall Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore()
{
  ULONGLONG v0; // rax
  ULONGLONG v1; // rax
  ULONGLONG v2; // rax
  unsigned int v3; // ecx
  char result; // al
  _OSVERSIONINFOEXW VersionInformation; // [rsp+20h] [rbp-138h] BYREF

  if ( `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::AlreadyChecked )
    return `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::IsOptedIn;
  VersionInformation.dwOSVersionInfoSize = 284;
  *(_OWORD *)&VersionInformation.dwMajorVersion = 0;
  memset_0(VersionInformation.szCSDVersion, 0, sizeof(VersionInformation.szCSDVersion));
  *(_QWORD *)&VersionInformation.wServicePackMajor = 0;
  v0 = VerSetConditionMask(0, 2u, 3u);
  v1 = VerSetConditionMask(v0, 1u, 3u);
  v2 = VerSetConditionMask(v1, 0x20u, 3u);
  *(_QWORD *)&VersionInformation.dwMajorVersion = 10;
  VersionInformation.wServicePackMajor = 0;
  if ( VerifyVersionInfoW(&VersionInformation, 0x23u, v2) )
    result = Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(v3);
  else
    result = (unsigned int)WinSqmIsOptedInEx(4) == 1;
  `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::IsOptedIn = result;
  `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::AlreadyChecked = 1;
  return result;
}

```

## disassembly

```asm
0x140017e4c  sub     rsp, 158h
0x140017e53  mov     rax, cs:__security_cookie
0x140017e5a  xor     rax, rsp
0x140017e5d  mov     [rsp+158h+var_18], rax
0x140017e65  cmp     cs:?AlreadyChecked@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, 0; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::AlreadyChecked
0x140017e6c  jnz     loc_140017F1D
0x140017e72  xorps   xmm0, xmm0
0x140017e75  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140017e7d  xor     edx, edx; Val
0x140017e7f  lea     rcx, [rsp+158h+VersionInformation.szCSDVersion]; void *
0x140017e84  mov     r8d, 100h; Size
0x140017e8a  movups  xmmword ptr [rsp+158h+VersionInformation.dwMajorVersion], xmm0
0x140017e8f  call    memset_0
0x140017e94  xor     eax, eax
0x140017e96  mov     r8b, 3; Condition
0x140017e99  xor     ecx, ecx; ConditionMask
0x140017e9b  mov     qword ptr [rsp+158h+VersionInformation.wServicePackMajor], rax
0x140017ea3  lea     edx, [rax+2]; TypeMask
0x140017ea6  call    cs:__imp_VerSetConditionMask
0x140017eac  mov     r8b, 3; Condition
0x140017eaf  mov     edx, 1; TypeMask
0x140017eb4  mov     rcx, rax; ConditionMask
0x140017eb7  call    cs:__imp_VerSetConditionMask
0x140017ebd  mov     r8b, 3; Condition
0x140017ec0  mov     edx, 20h ; ' '; TypeMask
0x140017ec5  mov     rcx, rax; ConditionMask
0x140017ec8  call    cs:__imp_VerSetConditionMask
0x140017ece  xor     ecx, ecx
0x140017ed0  mov     qword ptr [rsp+158h+VersionInformation.dwMajorVersion], 0Ah
0x140017ed9  mov     [rsp+158h+VersionInformation.wServicePackMajor], cx
0x140017ee1  mov     r8, rax; dwlConditionMask
0x140017ee4  lea     edx, [rcx+23h]; dwTypeMask
0x140017ee7  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x140017eec  call    cs:__imp_VerifyVersionInfoW
0x140017ef2  test    eax, eax
0x140017ef4  jz      short loc_140017EFD
0x140017ef6  call    ?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z; Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)
0x140017efb  jmp     short loc_140017F0E
0x140017efd  mov     ecx, 4
0x140017f02  call    cs:__imp_WinSqmIsOptedInEx
0x140017f08  cmp     eax, 1
0x140017f0b  setz    al
0x140017f0e  mov     cs:?IsOptedIn@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, al; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::IsOptedIn
0x140017f14  mov     cs:?AlreadyChecked@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, 1; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::AlreadyChecked
0x140017f1b  jmp     short loc_140017F23
0x140017f1d  mov     al, cs:?IsOptedIn@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::IsOptedIn
0x140017f23  mov     rcx, [rsp+158h+var_18]
0x140017f2b  xor     rcx, rsp; StackCookie
0x140017f2e  call    __security_check_cookie
0x140017f33  add     rsp, 158h
0x140017f3a  retn
```
