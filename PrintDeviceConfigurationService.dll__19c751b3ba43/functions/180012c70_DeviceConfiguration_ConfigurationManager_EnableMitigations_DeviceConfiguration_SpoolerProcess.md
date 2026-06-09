# DeviceConfiguration::ConfigurationManager::_EnableMitigations(DeviceConfiguration::SpoolerProcess)

- ea: `0x180012c70`
- end: `0x180012def`
- name: `?_EnableMitigations@ConfigurationManager@DeviceConfiguration@@AEAAXW4SpoolerProcess@2@@Z`
- size: `383`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180013c3c`

## callees

- `0x1800020c0`
- `0x18000d578`
- `0x18000d9c8`
- `0x180012574`
- `0x180012c70`

## import_xrefs

- `ntdll!RtlSetImageMitigationPolicy` at `0x180012cd0`
- `ntdll!RtlSetImageMitigationPolicy` at `0x180012d4e`
- `ntdll!RtlSetImageMitigationPolicy` at `0x180012da3`
- `ntdll!RtlSetImageMitigationPolicy` at `0x180012cd0`
- `ntdll!RtlSetImageMitigationPolicy` at `0x180012d4e`
- `ntdll!RtlSetImageMitigationPolicy` at `0x180012da3`

## string_xrefs

- `0x180012cda`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180012d58`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180012dad`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::ConfigurationManager::_EnableMitigations(__int64 a1, int a2)
{
  const char *v2; // rbx
  unsigned int v3; // eax
  const unsigned __int16 *v4; // rdx
  __int64 result; // rax
  unsigned int v6; // eax
  unsigned int v7; // eax
  HKEY v8[2]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v9[3]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v10; // [rsp+58h] [rbp-28h] BYREF
  __int128 v11; // [rsp+60h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v9[0] = 0;
  v9[1] = 0;
  v2 = (const char *)L"spoolsv.exe";
  v9[2] = 5;
  if ( a2 )
    v2 = L"spoolsvworker.exe";
  v3 = RtlSetImageMitigationPolicy(v2, 1, 0, v9, 24);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x1D2,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    (const char *)v3,
    (int)"RtlSetImageMitigationPolicy for ImageAslrPolicy (enable) for process %ws failed!",
    v2);
  if ( !PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled()
    || (v8[0] = HKEY_LOCAL_MACHINE,
        result = PrintCore::WindowsProtectedPrintHelpers::_GetRegDwordValueNoThrow(
                   v8,
                   v4,
                   L"WindowsProtectedPrintDebugMode"),
        !(_DWORD)result) )
  {
    v8[1] = 0;
    v8[0] = (HKEY)13;
    v6 = RtlSetImageMitigationPolicy(v2, 7, 0, v8, 16);
    wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
      retaddr,
      (void *)0x1DB,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v6,
      (int)"RtlSetImageMitigationPolicy for ImageControlFlowGuardPolicy (enable) for process %ws failed!",
      v2);
    v10 = 5;
    v11 = 0;
    v7 = RtlSetImageMitigationPolicy(v2, 15, 0, &v10, 24);
    return wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
             retaddr,
             (void *)0x1E3,
             (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
             (const char *)v7,
             (int)"RtlSetImageMitigationPolicy for ImageUserShadowStackPolicy (enable) for process %ws failed!",
             v2);
  }
  return result;
}

```

## disassembly

```asm
0x180012c70  mov     [rsp-8+arg_0], rbx
0x180012c75  push    rbp
0x180012c76  mov     rbp, rsp
0x180012c79  sub     rsp, 80h
0x180012c80  mov     rax, cs:__security_cookie
0x180012c87  xor     rax, rsp
0x180012c8a  mov     [rbp+var_10], rax
0x180012c8e  test    edx, edx
0x180012c90  mov     [rbp+var_40], 0
0x180012c98  lea     rax, aSpoolsvworkerE; "spoolsvworker.exe"
0x180012c9f  mov     [rbp+var_38], 0
0x180012ca7  lea     rbx, aSpoolsvExe; "spoolsv.exe"
0x180012cae  mov     [rbp+var_30], 5
0x180012cb6  cmovnz  rbx, rax
0x180012cba  mov     [rsp+80h+var_60], 18h
0x180012cc2  xor     r8d, r8d
0x180012cc5  lea     r9, [rbp+var_40]
0x180012cc9  mov     rcx, rbx
0x180012ccc  lea     edx, [r8+1]
0x180012cd0  call    cs:__imp_RtlSetImageMitigationPolicy
0x180012cd6  mov     rcx, [rbp+8]; this
0x180012cda  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180012ce1  mov     r9d, eax; char *
0x180012ce4  mov     [rsp+80h+var_58], rbx; char *
0x180012ce9  lea     rax, aRtlsetimagemit_2; "RtlSetImageMitigationPolicy for ImageAs"...
0x180012cf0  mov     edx, 1D2h; void *
0x180012cf5  mov     qword ptr [rsp+80h+var_60], rax; int
0x180012cfa  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180012cff  call    ?IsWindowsProtectedPrintEnabled@WindowsProtectedPrintHelpers@PrintCore@@SA_NXZ; PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled(void)
0x180012d04  test    al, al
0x180012d06  jz      short loc_180012D28
0x180012d08  lea     r8, aWindowsprotect_0; "WindowsProtectedPrintDebugMode"
0x180012d0f  mov     [rbp+var_50], 0FFFFFFFF80000002h
0x180012d17  lea     rcx, [rbp+var_50]; HKEY *
0x180012d1b  call    ?_GetRegDwordValueNoThrow@WindowsProtectedPrintHelpers@PrintCore@@CAKAEBQEAUHKEY__@@PEBG1@Z; PrintCore::WindowsProtectedPrintHelpers::_GetRegDwordValueNoThrow(HKEY__ * const &,ushort const *,ushort const *)
0x180012d20  test    eax, eax
0x180012d22  jnz     loc_180012DD2
0x180012d28  xor     r8d, r8d
0x180012d2b  mov     [rbp+var_48], 0
0x180012d33  lea     r9, [rbp+var_50]
0x180012d37  mov     [rbp+var_50], 0Dh
0x180012d3f  mov     rcx, rbx
0x180012d42  mov     [rsp+80h+var_60], 10h
0x180012d4a  lea     edx, [r8+7]
0x180012d4e  call    cs:__imp_RtlSetImageMitigationPolicy
0x180012d54  mov     rcx, [rbp+8]; this
0x180012d58  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180012d5f  mov     r9d, eax; char *
0x180012d62  mov     [rsp+80h+var_58], rbx; char *
0x180012d67  lea     rax, aRtlsetimagemit_1; "RtlSetImageMitigationPolicy for ImageCo"...
0x180012d6e  mov     edx, 1DBh; void *
0x180012d73  mov     qword ptr [rsp+80h+var_60], rax; int
0x180012d78  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180012d7d  xor     r8d, r8d
0x180012d80  mov     [rbp+var_28], 5
0x180012d88  xorps   xmm0, xmm0
0x180012d8b  mov     [rsp+80h+var_60], 18h
0x180012d93  lea     r9, [rbp+var_28]
0x180012d97  mov     rcx, rbx
0x180012d9a  movdqu  [rbp+var_20], xmm0
0x180012d9f  lea     edx, [r8+0Fh]
0x180012da3  call    cs:__imp_RtlSetImageMitigationPolicy
0x180012da9  mov     rcx, [rbp+8]; this
0x180012dad  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180012db4  mov     r9d, eax; char *
0x180012db7  mov     [rsp+80h+var_58], rbx; char *
0x180012dbc  lea     rax, aRtlsetimagemit_3; "RtlSetImageMitigationPolicy for ImageUs"...
0x180012dc3  mov     edx, 1E3h; void *
0x180012dc8  mov     qword ptr [rsp+80h+var_60], rax; int
0x180012dcd  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180012dd2  mov     rcx, [rbp+var_10]
0x180012dd6  xor     rcx, rsp; StackCookie
0x180012dd9  call    __security_check_cookie
0x180012dde  mov     rbx, [rsp+80h+arg_0]
0x180012de6  add     rsp, 80h
0x180012ded  pop     rbp
0x180012dee  retn
```
