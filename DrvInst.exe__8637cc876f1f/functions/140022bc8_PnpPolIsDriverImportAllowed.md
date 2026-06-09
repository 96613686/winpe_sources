# PnpPolIsDriverImportAllowed

- ea: `0x140022bc8`
- end: `0x140022e15`
- name: `PnpPolIsDriverImportAllowed`
- size: `589`
- prototype: `_BOOL8 __fastcall(HANDLE TokenHandle, _WORD *, WORD wProcessorArchitecture)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x1400161bc`

## callees

- `0x14000ad64`
- `0x14000ebf4`
- `0x140021850`
- `0x140022bc8`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022d05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022d05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022d2c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140022ddd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140022ddd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x140022cd5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x140022cd5`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022c92`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022d52`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022d88`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022dd5`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022c92`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022d52`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022d88`
- `DEVRTL!DevRtlWriteTextLog` at `0x140022dd5`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140022c1a`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140022c1a`
- `DEVRTL!DevRtlCreateTextLogSectionW` at `0x140022c64`
- `DEVRTL!DevRtlCreateTextLogSectionW` at `0x140022c64`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x140022c72`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x140022daf`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x140022c72`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x140022daf`
- `drvstore!DriverPackageClose` at `0x140022d91`
- `drvstore!DriverPackageClose` at `0x140022d91`
- `drvstore!DriverPackageOpenW` at `0x140022cf7`
- `drvstore!DriverPackageOpenW` at `0x140022cf7`
- `drvstore!DriverPackageGetVersionInfoW` at `0x140022d22`
- `drvstore!DriverPackageGetVersionInfoW` at `0x140022d22`

## string_xrefs

- `0x140022d75`: `Installation of driver is not allowed for this user`
- `0x140022d7e`: `Installation of driver by limited User is allowed`

## pseudocode

```c
_BOOL8 __fastcall PnpPolIsDriverImportAllowed(HANDLE TokenHandle, _WORD *a2, WORD wProcessorArchitecture)
{
  DWORD LastError; // ebx
  __int64 v7; // rdi
  int v8; // r15d
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 ThreadLogToken; // [rsp+30h] [rbp-D0h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v14[178]; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID v15; // [rsp+338h] [rbp+238h] BYREF

  LastError = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  ThreadLogToken = DevRtlGetThreadLogToken();
  v7 = ThreadLogToken;
  memset_0(v14, 0, 0x6F0u);
  if ( !a2 || !*a2 )
    goto LABEL_22;
  if ( ThreadLogToken )
  {
    v8 = 0;
    DevRtlWriteTextLog(ThreadLogToken, 0x800000, 196612, "{Driver package policy check}");
  }
  else
  {
    v8 = DevRtlCreateTextLogSectionW(a2, 1, L"Driver package policy check", &ThreadLogToken);
    DevRtlSetThreadLogToken(ThreadLogToken);
  }
  if ( !(unsigned int)pSetupTokenHasBuiltinGroup(TokenHandle, 0x220u) )
  {
    if ( (unsigned int)pSetupTokenHasBuiltinGroup(TokenHandle, 0x221u) )
    {
      if ( wProcessorArchitecture == 0xFFFF )
      {
        GetSystemInfo(&SystemInfo);
        wProcessorArchitecture = SystemInfo.wProcessorArchitecture;
      }
      v9 = DriverPackageOpenW(a2, wProcessorArchitecture, 0, 1, 0);
      v10 = v9;
      if ( v9 )
      {
        v14[0] = 1776;
        if ( (unsigned int)DriverPackageGetVersionInfoW(v9, v14) )
        {
          DevRtlWriteTextLog(ThreadLogToken, 0x800000, 4, "Driver package import is subject to policy");
          if ( (unsigned int)PnpPolIsClassInUserDriverAllowList(&v15) )
          {
            DevRtlWriteTextLog(ThreadLogToken, 0x800000, 4, "Installation of driver by limited User is allowed");
          }
          else
          {
            LastError = 5;
            DevRtlWriteTextLog(ThreadLogToken, 0x800000, 1, "Installation of driver is not allowed for this user");
          }
        }
        else
        {
          LastError = GetLastError();
        }
        DriverPackageClose(v10);
      }
      else
      {
        LastError = GetLastError();
      }
    }
    else
    {
      LastError = 5;
    }
  }
  if ( !v8 )
  {
    v7 = ThreadLogToken;
LABEL_22:
    DevRtlWriteTextLog(v7, 0x800000, 327684, "{Driver package policy check - exit(0x%08x)}", LastError);
    goto LABEL_23;
  }
  pSetupCloseTextLogSection(ThreadLogToken, LastError);
  ThreadLogToken = 0;
  DevRtlSetThreadLogToken(0);
LABEL_23:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x140022bc8  mov     [rsp-8+arg_18], rbx
0x140022bcd  push    rbp
0x140022bce  push    rsi
0x140022bcf  push    rdi
0x140022bd0  push    r12
0x140022bd2  push    r13
0x140022bd4  push    r14
0x140022bd6  push    r15
0x140022bd8  lea     rbp, [rsp-670h]
0x140022be0  sub     rsp, 770h
0x140022be7  mov     rax, cs:__security_cookie
0x140022bee  xor     rax, rsp
0x140022bf1  mov     [rbp+6A0h+var_40], rax
0x140022bf8  xorps   xmm0, xmm0
0x140022bfb  xor     r13d, r13d
0x140022bfe  mov     ebx, r13d
0x140022c01  movzx   esi, r8w
0x140022c05  movups  xmmword ptr [rsp+7A0h+SystemInfo], xmm0
0x140022c0a  mov     r14, rdx
0x140022c0d  mov     r12, rcx
0x140022c10  movups  xmmword ptr [rsp+7A0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x140022c15  movups  xmmword ptr [rsp+7A0h+SystemInfo.dwNumberOfProcessors], xmm0
0x140022c1a  call    cs:__imp_DevRtlGetThreadLogToken
0x140022c20  xor     edx, edx; Val
0x140022c22  lea     rcx, [rsp+7A0h+var_730]; void *
0x140022c27  mov     r8d, 6F0h; Size
0x140022c2d  mov     [rsp+7A0h+var_770], rax
0x140022c32  mov     rdi, rax
0x140022c35  call    memset_0
0x140022c3a  test    r14, r14
0x140022c3d  jz      loc_140022DBC
0x140022c43  cmp     [r14], r13w
0x140022c47  jz      loc_140022DBC
0x140022c4d  test    rdi, rdi
0x140022c50  jnz     short loc_140022C7A
0x140022c52  lea     r9, [rsp+7A0h+var_770]
0x140022c57  mov     rcx, r14
0x140022c5a  lea     r8, aDriverPackageP; "Driver package policy check"
0x140022c61  lea     edx, [rdi+1]
0x140022c64  call    cs:__imp_DevRtlCreateTextLogSectionW
0x140022c6a  mov     rcx, [rsp+7A0h+var_770]
0x140022c6f  mov     r15d, eax
0x140022c72  call    cs:__imp_DevRtlSetThreadLogToken
0x140022c78  jmp     short loc_140022C98
0x140022c7a  lea     r9, aDriverPackageP_1; "{Driver package policy check}"
0x140022c81  mov     edx, 800000h
0x140022c86  mov     r8d, 30004h
0x140022c8c  mov     rcx, rdi
0x140022c8f  mov     r15d, r13d
0x140022c92  call    cs:__imp_DevRtlWriteTextLog
0x140022c98  mov     edx, 220h; nSubAuthority1
0x140022c9d  mov     rcx, r12; TokenHandle
0x140022ca0  call    pSetupTokenHasBuiltinGroup
0x140022ca5  test    eax, eax
0x140022ca7  jnz     loc_140022D97
0x140022cad  mov     edx, 221h; nSubAuthority1
0x140022cb2  mov     rcx, r12; TokenHandle
0x140022cb5  call    pSetupTokenHasBuiltinGroup
0x140022cba  test    eax, eax
0x140022cbc  jnz     short loc_140022CC6
0x140022cbe  lea     ebx, [rax+5]
0x140022cc1  jmp     loc_140022D97
0x140022cc6  mov     eax, 0FFFFh
0x140022ccb  cmp     si, ax
0x140022cce  jnz     short loc_140022CE0
0x140022cd0  lea     rcx, [rsp+7A0h+SystemInfo]; lpSystemInfo
0x140022cd5  call    cs:__imp_GetSystemInfo
0x140022cdb  movzx   esi, word ptr [rsp+7A0h+SystemInfo]
0x140022ce0  mov     r12d, 1
0x140022ce6  mov     [rsp+7A0h+var_780], r13
0x140022ceb  mov     r9d, r12d
0x140022cee  xor     r8d, r8d
0x140022cf1  movzx   edx, si
0x140022cf4  mov     rcx, r14
0x140022cf7  call    cs:__imp_DriverPackageOpenW
0x140022cfd  mov     rdi, rax
0x140022d00  test    rax, rax
0x140022d03  jnz     short loc_140022D12
0x140022d05  call    cs:__imp_GetLastError
0x140022d0b  mov     ebx, eax
0x140022d0d  jmp     loc_140022D97
0x140022d12  lea     rdx, [rsp+7A0h+var_730]
0x140022d17  mov     [rsp+7A0h+var_730], 6F0h
0x140022d1f  mov     rcx, rdi
0x140022d22  call    cs:__imp_DriverPackageGetVersionInfoW
0x140022d28  test    eax, eax
0x140022d2a  jnz     short loc_140022D36
0x140022d2c  call    cs:__imp_GetLastError
0x140022d32  mov     ebx, eax
0x140022d34  jmp     short loc_140022D8E
0x140022d36  mov     rcx, [rsp+7A0h+var_770]
0x140022d3b  lea     r9, aDriverPackageI_8; "Driver package import is subject to pol"...
0x140022d42  mov     r14d, 4
0x140022d48  mov     esi, 800000h
0x140022d4d  mov     r8d, r14d
0x140022d50  mov     edx, esi
0x140022d52  call    cs:__imp_DevRtlWriteTextLog
0x140022d58  lea     rcx, [rbp+6A0h+var_468]; struct _GUID *
0x140022d5f  call    ?PnpPolIsClassInUserDriverAllowList@@YAHPEAU_GUID@@@Z; PnpPolIsClassInUserDriverAllowList(_GUID *)
0x140022d64  mov     rcx, [rsp+7A0h+var_770]
0x140022d69  mov     edx, esi
0x140022d6b  test    eax, eax
0x140022d6d  jnz     short loc_140022D7E
0x140022d6f  lea     ebx, [rax+5]
0x140022d72  mov     r8d, r12d
0x140022d75  lea     r9, aInstallationOf_4; "Installation of driver is not allowed f"...
0x140022d7c  jmp     short loc_140022D88
0x140022d7e  lea     r9, aInstallationOf_1; "Installation of driver by limited User "...
0x140022d85  mov     r8d, r14d
0x140022d88  call    cs:__imp_DevRtlWriteTextLog
0x140022d8e  mov     rcx, rdi
0x140022d91  call    cs:__imp_DriverPackageClose
0x140022d97  test    r15d, r15d
0x140022d9a  jz      short loc_140022DB7
0x140022d9c  mov     rcx, [rsp+7A0h+var_770]
0x140022da1  mov     edx, ebx
0x140022da3  call    pSetupCloseTextLogSection
0x140022da8  xor     ecx, ecx
0x140022daa  mov     [rsp+7A0h+var_770], r13
0x140022daf  call    cs:__imp_DevRtlSetThreadLogToken
0x140022db5  jmp     short loc_140022DDB
0x140022db7  mov     rdi, [rsp+7A0h+var_770]
0x140022dbc  lea     r9, aDriverPackageP_0; "{Driver package policy check - exit(0x%"...
0x140022dc3  mov     dword ptr [rsp+7A0h+var_780], ebx
0x140022dc7  mov     edx, 800000h
0x140022dcc  mov     r8d, 50004h
0x140022dd2  mov     rcx, rdi
0x140022dd5  call    cs:__imp_DevRtlWriteTextLog
0x140022ddb  mov     ecx, ebx; dwErrCode
0x140022ddd  call    cs:__imp_SetLastError
0x140022de3  test    ebx, ebx
0x140022de5  mov     eax, r13d
0x140022de8  setz    al
0x140022deb  mov     rcx, [rbp+6A0h+var_40]
0x140022df2  xor     rcx, rsp; StackCookie
0x140022df5  call    __security_check_cookie
0x140022dfa  mov     rbx, [rsp+7A0h+arg_18]
0x140022e02  add     rsp, 770h
0x140022e09  pop     r15
0x140022e0b  pop     r14
0x140022e0d  pop     r13
0x140022e0f  pop     r12
0x140022e11  pop     rdi
0x140022e12  pop     rsi
0x140022e13  pop     rbp
0x140022e14  retn
```
