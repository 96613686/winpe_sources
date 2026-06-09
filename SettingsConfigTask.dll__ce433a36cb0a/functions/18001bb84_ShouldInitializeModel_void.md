# ShouldInitializeModel(void)

- ea: `0x18001bb84`
- end: `0x18001bce4`
- name: `?ShouldInitializeModel@@YA_NXZ`
- size: `352`
- prototype: `char(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001c380`

## callees

- `0x1800021d0`
- `0x18001850c`
- `0x180018564`
- `0x1800185bc`
- `0x18001bb84`
- `0x18001c8d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001bbdd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001bc6c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001bbdd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001bc6c`

## string_xrefs

- `0x18001bc55`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsAI\SettingsLastConfiguration`
- `0x18001bc0e`: `pcshell\shell\settings\settingsconfigtask\lib\settingsconfigtaskhandler.cpp`

## pseudocode

```c
char ShouldInitializeModel(void)
{
  LSTATUS ValueW; // eax
  unsigned __int64 v1; // r9
  bool v2; // sf
  LSTATUS v3; // eax
  bool v4; // sf
  unsigned __int16 *v5; // rax
  int v6; // r8d
  int v7; // ecx
  int pdwType; // [rsp+20h] [rbp-C8h]
  DWORD pcbData[4]; // [rsp+40h] [rbp-A8h] BYREF
  _WORD pvData[32]; // [rsp+50h] [rbp-98h] BYREF
  _WORD v12[32]; // [rsp+90h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  pcbData[0] = 64;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
             L"LCUVer",
             2u,
             0,
             pvData,
             pcbData);
  v1 = (unsigned int)ValueW;
  if ( ValueW )
  {
    pvData[0] = 0;
    v2 = ValueW < 0;
    if ( ValueW <= 0 )
      goto LABEL_5;
    v1 = (unsigned __int16)ValueW | 0x80070000;
  }
  v2 = (v1 & 0x80000000) != 0LL;
LABEL_5:
  if ( v2 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"pcshell\\shell\\settings\\settingsconfigtask\\lib\\settingsconfigtaskhandler.cpp",
      (const char *)v1,
      pdwType);
    SettingsDownloadTelemetry::InitialTask_RunwithUnableGetSystemOSBuild();
  }
  else
  {
    pcbData[0] = 64;
    v3 = RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsAI\\SettingsLastConfiguration",
           L"LastLCUVersion",
           2u,
           0,
           v12,
           pcbData);
    v4 = v3 < 0;
    if ( v3 )
    {
      v12[0] = 0;
      v4 = v3 < 0;
      if ( v3 > 0 )
        v4 = 1;
    }
    if ( v4 )
    {
      SettingsDownloadTelemetry::InitialTask_RunwithNotFoundRegKey();
    }
    else
    {
      v5 = pvData;
      do
      {
        v6 = *(unsigned __int16 *)((char *)v5 + (char *)v12 - (char *)pvData);
        v7 = *v5 - v6;
        if ( v7 )
          break;
        ++v5;
      }
      while ( v6 );
      if ( !v7 )
        return 0;
      SettingsDownloadTelemetry::InitialTask_RunforNewReleaseDetected();
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18001bb84  sub     rsp, 0E8h
0x18001bb8b  mov     rax, cs:__security_cookie
0x18001bb92  xor     rax, rsp
0x18001bb95  mov     [rsp+0E8h+var_18], rax
0x18001bb9d  lea     rax, [rsp+0E8h+var_A8]
0x18001bba2  mov     [rsp+0E8h+var_A8], 40h ; '@'
0x18001bbaa  mov     [rsp+0E8h+pcbData], rax; pcbData
0x18001bbaf  lea     r8, aLcuver; "LCUVer"
0x18001bbb6  lea     rax, [rsp+0E8h+var_98]
0x18001bbbb  mov     r9d, 2; dwFlags
0x18001bbc1  mov     [rsp+0E8h+pvData], rax; pvData
0x18001bbc6  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001bbcd  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001bbd4  mov     [rsp+0E8h+pdwType], 0; int
0x18001bbdd  call    cs:__imp_RegGetValueW
0x18001bbe3  mov     r9d, eax
0x18001bbe6  test    eax, eax
0x18001bbe8  jz      short loc_18001BC01
0x18001bbea  xor     eax, eax
0x18001bbec  mov     [rsp+0E8h+var_98], ax
0x18001bbf1  test    r9d, r9d
0x18001bbf4  jle     short loc_18001BC04
0x18001bbf6  movzx   r9d, r9w
0x18001bbfa  or      r9d, 80070000h; char *
0x18001bc01  test    r9d, r9d
0x18001bc04  jns     short loc_18001BC29
0x18001bc06  mov     rcx, [rsp+0E8h]; this
0x18001bc0e  lea     r8, aPcshellShellSe; "pcshell\\shell\\settings\\settingsconfi"...
0x18001bc15  mov     edx, 29h ; ')'; void *
0x18001bc1a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001bc1f  call    ?InitialTask_RunwithUnableGetSystemOSBuild@SettingsDownloadTelemetry@@SAXXZ; SettingsDownloadTelemetry::InitialTask_RunwithUnableGetSystemOSBuild(void)
0x18001bc24  jmp     loc_18001BCCA
0x18001bc29  lea     rax, [rsp+0E8h+var_A8]
0x18001bc2e  mov     [rsp+0E8h+var_A8], 40h ; '@'
0x18001bc36  mov     [rsp+0E8h+pcbData], rax; pcbData
0x18001bc3b  lea     r8, aLastlcuversion; "LastLCUVersion"
0x18001bc42  lea     rax, [rsp+0E8h+var_58]
0x18001bc4a  mov     r9d, 2; dwFlags
0x18001bc50  mov     [rsp+0E8h+pvData], rax; pvData
0x18001bc55  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001bc5c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001bc63  mov     [rsp+0E8h+pdwType], 0; pdwType
0x18001bc6c  call    cs:__imp_RegGetValueW
0x18001bc72  test    eax, eax
0x18001bc74  jz      short loc_18001BC8E
0x18001bc76  xor     ecx, ecx
0x18001bc78  mov     [rsp+0E8h+var_58], cx
0x18001bc80  test    eax, eax
0x18001bc82  jle     short loc_18001BC8E
0x18001bc84  movzx   eax, ax
0x18001bc87  or      eax, 80070000h
0x18001bc8c  test    eax, eax
0x18001bc8e  js      short loc_18001BCC5
0x18001bc90  lea     rax, [rsp+0E8h+var_98]
0x18001bc95  lea     rdx, [rsp+0E8h+var_58]
0x18001bc9d  sub     rdx, rax
0x18001bca0  movzx   ecx, word ptr [rax]
0x18001bca3  movzx   r8d, word ptr [rax+rdx]
0x18001bca8  sub     ecx, r8d
0x18001bcab  jnz     short loc_18001BCB6
0x18001bcad  add     rax, 2
0x18001bcb1  test    r8d, r8d
0x18001bcb4  jnz     short loc_18001BCA0
0x18001bcb6  test    ecx, ecx
0x18001bcb8  jnz     short loc_18001BCBE
0x18001bcba  xor     al, al
0x18001bcbc  jmp     short loc_18001BCCC
0x18001bcbe  call    ?InitialTask_RunforNewReleaseDetected@SettingsDownloadTelemetry@@SAXXZ; SettingsDownloadTelemetry::InitialTask_RunforNewReleaseDetected(void)
0x18001bcc3  jmp     short loc_18001BCCA
0x18001bcc5  call    ?InitialTask_RunwithNotFoundRegKey@SettingsDownloadTelemetry@@SAXXZ; SettingsDownloadTelemetry::InitialTask_RunwithNotFoundRegKey(void)
0x18001bcca  mov     al, 1
0x18001bccc  mov     rcx, [rsp+0E8h+var_18]
0x18001bcd4  xor     rcx, rsp; StackCookie
0x18001bcd7  call    __security_check_cookie
0x18001bcdc  add     rsp, 0E8h
0x18001bce3  retn
```
