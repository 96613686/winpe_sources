# UserOOBEController::s_RestoreProvisioningCredential(void)

- ea: `0x180029a78`
- end: `0x180029b61`
- name: `?s_RestoreProvisioningCredential@UserOOBEController@@CAJXZ`
- size: `233`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a480`

## callees

- `0x18000e270`
- `0x180026084`
- `0x180029a78`
- `0x18002c4f8`
- `0x18002ca58`
- `0x180047bd0`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x180029b31`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x180029b31`

## string_xrefs

- `0x180029ab2`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180029b08`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180029b40`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
__int64 UserOOBEController::s_RestoreProvisioningCredential(void)
{
  int v0; // eax
  bool IsStateSeparationEnabled; // al
  HKEY v2; // r8
  const WCHAR *v3; // rbx
  const unsigned __int16 *v4; // rdx
  int v5; // eax
  LSTATUS v6; // eax
  int v8; // [rsp+20h] [rbp-18h]
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  UnattendLogW(0, L"UserOOBEController::s_RestoreProvisioningCredential() starts un-shelving auto logon settings.");
  v0 = SetAutologonDetails(0, 0, 0, 0, 0, 0);
  if ( v0 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x368,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v0,
      v8);
  IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
  v3 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\Winlogon";
  v4 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\Winlogon";
  if ( !IsStateSeparationEnabled )
    v4 = L"SOFTWARE\\Microsoft\\Provisioning\\Winlogon";
  v5 = TransferUnattendXmlAutologonValues(
         HKEY_LOCAL_MACHINE,
         v4,
         v2,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
         1,
         1);
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x36B,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v5,
      v9);
  if ( !ProvIsStateSeparationEnabled() )
    v3 = L"SOFTWARE\\Microsoft\\Provisioning\\Winlogon";
  v6 = SHDeleteKeyW(HKEY_LOCAL_MACHINE, v3);
  if ( v6 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x36E,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v6,
      v9);
  return 0;
}

```

## disassembly

```asm
0x180029a78  mov     [rsp+arg_0], rbx
0x180029a7d  push    rbp
0x180029a7e  sub     rsp, 30h
0x180029a82  lea     rdx, aUseroobecontro_0; "UserOOBEController::s_RestoreProvisioni"...
0x180029a89  xor     ecx, ecx
0x180029a8b  call    UnattendLogW
0x180029a90  xor     r9d, r9d; unsigned int
0x180029a93  mov     [rsp+38h+var_10], 0; bool
0x180029a98  xor     r8d, r8d; unsigned __int8 *
0x180029a9b  mov     [rsp+38h+var_18], 0; int
0x180029aa0  xor     edx, edx; unsigned __int16 *
0x180029aa2  xor     ecx, ecx; unsigned __int16 *
0x180029aa4  call    ?SetAutologonDetails@@YAJPEBG0PEBEK_N2@Z; SetAutologonDetails(ushort const *,ushort const *,uchar const *,ulong,bool,bool)
0x180029aa9  test    eax, eax
0x180029aab  jns     short loc_180029AC6
0x180029aad  mov     rcx, [rsp+38h]; this
0x180029ab2  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180029ab9  mov     r9d, eax; char *
0x180029abc  mov     edx, 368h; void *
0x180029ac1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029ac6  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x180029acb  test    al, al
0x180029acd  mov     [rsp+38h+var_10], 1; bool
0x180029ad2  lea     rbx, aOsdataSoftware; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x180029ad9  mov     [rsp+38h+var_18], 1; int
0x180029ade  mov     rdx, rbx
0x180029ae1  lea     rbp, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Provisioning\\Winl"...
0x180029ae8  cmovz   rdx, rbp; unsigned __int16 *
0x180029aec  lea     r9, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180029af3  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180029afa  call    ?TransferUnattendXmlAutologonValues@@YAJPEAUHKEY__@@PEBG01_N2@Z; TransferUnattendXmlAutologonValues(HKEY__ *,ushort const *,HKEY__ *,ushort const *,bool,bool)
0x180029aff  test    eax, eax
0x180029b01  jns     short loc_180029B1C
0x180029b03  mov     rcx, [rsp+38h]; this
0x180029b08  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180029b0f  mov     r9d, eax; char *
0x180029b12  mov     edx, 36Bh; void *
0x180029b17  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029b1c  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x180029b21  test    al, al
0x180029b23  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180029b2a  cmovz   rbx, rbp
0x180029b2e  mov     rdx, rbx; pszSubKey
0x180029b31  call    cs:__imp_SHDeleteKeyW
0x180029b37  test    eax, eax
0x180029b39  jns     short loc_180029B54
0x180029b3b  mov     rcx, [rsp+38h]; this
0x180029b40  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180029b47  mov     r9d, eax; char *
0x180029b4a  mov     edx, 36Eh; void *
0x180029b4f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029b54  mov     rbx, [rsp+38h+arg_0]
0x180029b59  xor     eax, eax
0x180029b5b  add     rsp, 30h
0x180029b5f  pop     rbp
0x180029b60  retn
```
