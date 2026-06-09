# RegisterToRecoveryBCD(void)

- ea: `0x18000d394`
- end: `0x18000d531`
- name: `?RegisterToRecoveryBCD@@YAJXZ`
- size: `413`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18000f254`
- `0x180011118`

## callees

- `0x180005c00`
- `0x18000d394`
- `0x18000d900`
- `0x18003717c`
- `0x180037344`
- `0x18006f010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18000d3af`
- `KERNEL32!LoadLibraryExW` at `0x18000d3af`
- `KERNEL32!GetProcAddress` at `0x18000d44d`
- `KERNEL32!GetProcAddress` at `0x18000d44d`
- `KERNEL32!GetLastError` at `0x18000d3d4`
- `KERNEL32!GetLastError` at `0x18000d416`
- `KERNEL32!GetLastError` at `0x18000d45b`
- `KERNEL32!GetLastError` at `0x18000d49d`
- `KERNEL32!GetLastError` at `0x18000d4cc`
- `KERNEL32!GetLastError` at `0x18000d3d4`
- `KERNEL32!GetLastError` at `0x18000d416`
- `KERNEL32!GetLastError` at `0x18000d45b`
- `KERNEL32!GetLastError` at `0x18000d49d`
- `KERNEL32!GetLastError` at `0x18000d4cc`

## string_xrefs

- `0x18000d3fc`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000d483`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000d4f5`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000d3a8`: `ReAgent.dll`
- `0x18000d3e8`: `Failed to load ReAgent.dll`
- `0x18000d46f`: `Failed to load function from DLL`
- `0x18000d4b2`: `Register installed WinRE to Recovery BCD`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 RegisterToRecoveryBCD(void)
{
  signed int LastError; // eax
  signed int v1; // eax
  unsigned int v2; // ebx
  HMODULE v3; // rax
  unsigned int (*ProcAddress)(void); // rdi
  signed int v5; // eax
  signed int v6; // eax
  signed int v7; // eax
  _QWORD v9[3]; // [rsp+30h] [rbp-18h] BYREF

  v9[1] = LoadLibraryExW(L"ReAgent.dll", 0, 0);
  v9[0] = &RAII::CAutoFreeLibrary::`vftable';
  if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(v9) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LastError,
      "RegisterToRecoveryBCD",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      333,
      L"Failed to load ReAgent.dll");
    v1 = GetLastError();
    v2 = v1;
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
  }
  else
  {
    v3 = (HMODULE)(*(__int64 (__fastcall **)(_QWORD *))(v9[0] + 32LL))(v9);
    ProcAddress = (unsigned int (*)(void))GetProcAddress(v3, "WinReRegisterRecoveryBoot");
    if ( ProcAddress )
    {
      v2 = 0;
      PushButtonReset::Logging::Trace(0, L"Register installed WinRE to Recovery BCD");
      if ( !ProcAddress() )
      {
        v7 = GetLastError();
        v2 = v7;
        if ( v7 > 0 )
          v2 = (unsigned __int16)v7 | 0x80070000;
        PushButtonReset::Logging::TraceErr(
          1,
          v2,
          "RegisterToRecoveryBCD",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          351,
          L"Failed to Register WinRE to Recovery BCD");
      }
    }
    else
    {
      v5 = GetLastError();
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v5,
        "RegisterToRecoveryBCD",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        343,
        L"Failed to load function from DLL");
      v6 = GetLastError();
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      v2 = v6;
    }
  }
  v9[0] = &RAII::CAutoFreeLibrary::`vftable';
  RAII::CAutoFreeLibrary::Release((RAII::CAutoFreeLibrary *)v9);
  return v2;
}

```

## disassembly

```asm
0x18000d394  mov     [rsp+arg_0], rbx
0x18000d399  mov     [rsp+arg_8], rsi
0x18000d39e  push    rdi
0x18000d39f  sub     rsp, 40h
0x18000d3a3  xor     r8d, r8d; dwFlags
0x18000d3a6  xor     edx, edx; hFile
0x18000d3a8  lea     rcx, LibFileName; "ReAgent.dll"
0x18000d3af  call    cs:__imp_LoadLibraryExW
0x18000d3b5  mov     [rsp+48h+var_10], rax
0x18000d3ba  lea     rsi, ??_7CAutoFreeLibrary@RAII@@6B@; const RAII::CAutoFreeLibrary::`vftable'
0x18000d3c1  mov     [rsp+48h+var_18], rsi
0x18000d3c6  lea     rcx, [rsp+48h+var_18]
0x18000d3cb  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x18000d3d0  test    al, al
0x18000d3d2  jz      short loc_18000D430
0x18000d3d4  call    cs:__imp_GetLastError
0x18000d3da  mov     edi, 80070000h
0x18000d3df  test    eax, eax
0x18000d3e1  jle     short loc_18000D3E8
0x18000d3e3  movzx   eax, ax
0x18000d3e6  or      eax, edi
0x18000d3e8  lea     rcx, aFailedToLoadRe; "Failed to load ReAgent.dll"
0x18000d3ef  mov     [rsp+48h+var_20], rcx
0x18000d3f4  mov     [rsp+48h+var_28], 14Dh
0x18000d3fc  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000d403  lea     r8, aRegistertoreco; "RegisterToRecoveryBCD"
0x18000d40a  mov     edx, eax
0x18000d40c  mov     ecx, 2
0x18000d411  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000d416  call    cs:__imp_GetLastError
0x18000d41c  mov     ebx, eax
0x18000d41e  test    eax, eax
0x18000d420  jle     loc_18000D510
0x18000d426  movzx   ebx, ax
0x18000d429  or      ebx, edi
0x18000d42b  jmp     loc_18000D510
0x18000d430  mov     rax, [rsp+48h+var_18]
0x18000d435  lea     rcx, [rsp+48h+var_18]
0x18000d43a  mov     rax, [rax+20h]
0x18000d43e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d443  mov     rcx, rax; hModule
0x18000d446  lea     rdx, aWinreregisterr; "WinReRegisterRecoveryBoot"
0x18000d44d  call    cs:__imp_GetProcAddress
0x18000d453  mov     rdi, rax
0x18000d456  test    rax, rax
0x18000d459  jnz     short loc_18000D4B0
0x18000d45b  call    cs:__imp_GetLastError
0x18000d461  mov     edi, 80070000h
0x18000d466  test    eax, eax
0x18000d468  jle     short loc_18000D46F
0x18000d46a  movzx   eax, ax
0x18000d46d  or      eax, edi
0x18000d46f  lea     rcx, aFailedToLoadFu; "Failed to load function from DLL"
0x18000d476  mov     [rsp+48h+var_20], rcx
0x18000d47b  mov     [rsp+48h+var_28], 157h
0x18000d483  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000d48a  lea     r8, aRegistertoreco; "RegisterToRecoveryBCD"
0x18000d491  mov     edx, eax
0x18000d493  mov     ecx, 2
0x18000d498  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000d49d  call    cs:__imp_GetLastError
0x18000d4a3  test    eax, eax
0x18000d4a5  jle     short loc_18000D4AC
0x18000d4a7  movzx   eax, ax
0x18000d4aa  or      eax, edi
0x18000d4ac  mov     ebx, eax
0x18000d4ae  jmp     short loc_18000D510
0x18000d4b0  xor     ebx, ebx
0x18000d4b2  lea     rdx, aRegisterInstal; "Register installed WinRE to Recovery BC"...
0x18000d4b9  xor     ecx, ecx
0x18000d4bb  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18000d4c0  mov     rax, rdi
0x18000d4c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4c8  test    eax, eax
0x18000d4ca  jnz     short loc_18000D510
0x18000d4cc  call    cs:__imp_GetLastError
0x18000d4d2  mov     ebx, eax
0x18000d4d4  test    eax, eax
0x18000d4d6  jle     short loc_18000D4E1
0x18000d4d8  movzx   ebx, ax
0x18000d4db  or      ebx, 80070000h
0x18000d4e1  lea     rax, aFailedToRegist; "Failed to Register WinRE to Recovery BC"...
0x18000d4e8  mov     [rsp+48h+var_20], rax
0x18000d4ed  mov     [rsp+48h+var_28], 15Fh
0x18000d4f5  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000d4fc  lea     r8, aRegistertoreco; "RegisterToRecoveryBCD"
0x18000d503  mov     edx, ebx
0x18000d505  mov     ecx, 1
0x18000d50a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000d50f  nop
0x18000d510  mov     [rsp+48h+var_18], rsi
0x18000d515  lea     rcx, [rsp+48h+var_18]; this
0x18000d51a  call    ?Release@CAutoFreeLibrary@RAII@@UEAAXXZ; RAII::CAutoFreeLibrary::Release(void)
0x18000d51f  mov     eax, ebx
0x18000d521  mov     rbx, [rsp+48h+arg_0]
0x18000d526  mov     rsi, [rsp+48h+arg_8]
0x18000d52b  add     rsp, 40h
0x18000d52f  pop     rdi
0x18000d530  retn
```
