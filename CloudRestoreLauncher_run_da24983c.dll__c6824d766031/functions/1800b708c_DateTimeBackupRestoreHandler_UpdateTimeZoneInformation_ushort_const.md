# DateTimeBackupRestoreHandler::UpdateTimeZoneInformation(ushort const *)

- ea: `0x1800b708c`
- end: `0x1800b71c9`
- name: `?UpdateTimeZoneInformation@DateTimeBackupRestoreHandler@@AEAA_NPEBG@Z`
- size: `317`
- prototype: `bool(DateTimeBackupRestoreHandler *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800b6140`

## callees

- `0x18000c6e0`
- `0x18000d688`
- `0x18001c180`
- `0x180046134`
- `0x1800b708c`
- `0x1800b7284`
- `0x1801102cc`
- `0x18011038c`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800b70eb`
- `KERNEL32!CompareStringOrdinal` at `0x1800b70eb`
- `KERNEL32!SetDynamicTimeZoneInformation` at `0x1800b714b`
- `KERNEL32!SetDynamicTimeZoneInformation` at `0x1800b7160`
- `KERNEL32!SetDynamicTimeZoneInformation` at `0x1800b714b`
- `KERNEL32!SetDynamicTimeZoneInformation` at `0x1800b7160`
- `KERNEL32!GetLastError` at `0x1800b718d`
- `KERNEL32!GetLastError` at `0x1800b718d`
- `ADVAPI32!EnumDynamicTimeZoneInformation` at `0x1800b70ff`
- `ADVAPI32!EnumDynamicTimeZoneInformation` at `0x1800b70ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall DateTimeBackupRestoreHandler::UpdateTimeZoneInformation(
        DateTimeBackupRestoreHandler *this,
        const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  __int64 i; // rcx
  const char *v6; // r9
  __int64 v7; // rcx
  const char *v8; // r9
  _BYTE v9[32]; // [rsp+30h] [rbp-1E8h] BYREF
  DYNAMIC_TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+50h] [rbp-1C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  CAutoPrivilegeEnable::CAutoPrivilegeEnable((CAutoPrivilegeEnable *)v9, a2);
  memset_0(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
  v3 = 0;
  for ( i = 0; ; i = v3 )
  {
    if ( (unsigned int)EnumDynamicTimeZoneInformation(i, &TimeZoneInformation) )
    {
      CAutoPrivilegeEnable::~CAutoPrivilegeEnable((CAutoPrivilegeEnable *)v9);
      return 0;
    }
    if ( CompareStringOrdinal(TimeZoneInformation.TimeZoneKeyName, -1, a2, -1, 1) == 2 )
      break;
    ++v3;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupRestoreLogImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_BackupRestoreLogImprovements>::GetImpl'::`2'::impl) )
  {
    if ( !SetDynamicTimeZoneInformation(&TimeZoneInformation) )
    {
      if ( GetLastError() == 1314 && (Microsoft_Windows_CloudRestoreLauncherEnableBits & 8) != 0 )
        McTemplateU0_EventWriteTransfer(v7, &PrivilegeNotHeldOnSetTimeZone);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xB1,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\datetimebackuprestorehandler.cpp",
        v8);
    }
  }
  else if ( !SetDynamicTimeZoneInformation(&TimeZoneInformation) )
  {
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xB6,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\datetimebackuprestorehandler.cpp",
      v6);
  }
  CAutoPrivilegeEnable::~CAutoPrivilegeEnable((CAutoPrivilegeEnable *)v9);
  return 1;
}

```

## disassembly

```asm
0x1800b708c  mov     [rsp+arg_0], rbx
0x1800b7091  push    rdi
0x1800b7092  sub     rsp, 210h
0x1800b7099  mov     rax, cs:__security_cookie
0x1800b70a0  xor     rax, rsp
0x1800b70a3  mov     [rsp+218h+var_18], rax
0x1800b70ab  mov     rdi, rdx
0x1800b70ae  lea     rcx, [rsp+218h+var_1E8]; this
0x1800b70b3  call    ??0CAutoPrivilegeEnable@@QEAA@PEBG@Z; CAutoPrivilegeEnable::CAutoPrivilegeEnable(ushort const *)
0x1800b70b8  nop
0x1800b70b9  xor     edx, edx; Val
0x1800b70bb  mov     r8d, 1B0h; Size
0x1800b70c1  lea     rcx, [rsp+218h+TimeZoneInformation]; void *
0x1800b70c6  call    memset_0
0x1800b70cb  xor     ebx, ebx
0x1800b70cd  xor     ecx, ecx
0x1800b70cf  jmp     short loc_1800B70FA
0x1800b70d1  mov     [rsp+218h+bIgnoreCase], 1; bIgnoreCase
0x1800b70d9  or      r9d, 0FFFFFFFFh; cchCount2
0x1800b70dd  mov     r8, rdi; lpString2
0x1800b70e0  or      edx, r9d; cchCount1
0x1800b70e3  lea     rcx, [rsp+218h+TimeZoneInformation.TimeZoneKeyName]; lpString1
0x1800b70eb  call    cs:__imp_CompareStringOrdinal
0x1800b70f1  cmp     eax, 2
0x1800b70f4  jz      short loc_1800B7136
0x1800b70f6  inc     ebx
0x1800b70f8  mov     ecx, ebx
0x1800b70fa  lea     rdx, [rsp+218h+TimeZoneInformation]
0x1800b70ff  call    cs:__imp_EnumDynamicTimeZoneInformation
0x1800b7105  test    eax, eax
0x1800b7107  jz      short loc_1800B70D1
0x1800b7109  lea     rcx, [rsp+218h+var_1E8]; this
0x1800b710e  call    ??1CAutoPrivilegeEnable@@QEAA@XZ; CAutoPrivilegeEnable::~CAutoPrivilegeEnable(void)
0x1800b7113  xor     al, al
0x1800b7115  mov     rcx, [rsp+218h+var_18]
0x1800b711d  xor     rcx, rsp; StackCookie
0x1800b7120  call    __security_check_cookie
0x1800b7125  mov     rbx, [rsp+218h+arg_0]
0x1800b712d  add     rsp, 210h
0x1800b7134  pop     rdi
0x1800b7135  retn
0x1800b7136  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BackupRestoreLogImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BackupRestoreLogImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupRestoreLogImprovements> `wil::Feature<__WilFeatureTraits_Feature_BackupRestoreLogImprovements>::GetImpl(void)'::`2'::impl
0x1800b713d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BackupRestoreLogImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupRestoreLogImprovements>::__private_IsEnabled(void)
0x1800b7142  lea     rcx, [rsp+218h+TimeZoneInformation]; lpTimeZoneInformation
0x1800b7147  test    al, al
0x1800b7149  jz      short loc_1800B7158
0x1800b714b  call    cs:__imp_SetDynamicTimeZoneInformation
0x1800b7151  cmp     eax, 1
0x1800b7154  jnz     short loc_1800B718D
0x1800b7156  jmp     short loc_1800B716A
0x1800b7158  mov     rbx, [rsp+218h]
0x1800b7160  call    cs:__imp_SetDynamicTimeZoneInformation
0x1800b7166  test    eax, eax
0x1800b7168  jz      short loc_1800B7178
0x1800b716a  lea     rcx, [rsp+218h+var_1E8]; this
0x1800b716f  call    ??1CAutoPrivilegeEnable@@QEAA@XZ; CAutoPrivilegeEnable::~CAutoPrivilegeEnable(void)
0x1800b7174  mov     al, 1
0x1800b7176  jmp     short loc_1800B7115
0x1800b7178  lea     r8, aPcshellShellCl_0; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800b717f  mov     edx, 0B6h; void *
0x1800b7184  mov     rcx, rbx; this
0x1800b7187  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800b718d  call    cs:__imp_GetLastError
0x1800b7193  cmp     eax, 522h
0x1800b7198  jnz     short loc_1800B71AF
0x1800b719a  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 8
0x1800b71a1  jz      short loc_1800B71AF
0x1800b71a3  lea     rdx, PrivilegeNotHeldOnSetTimeZone
0x1800b71aa  call    McTemplateU0_EventWriteTransfer
0x1800b71af  mov     rcx, [rsp+218h]; this
0x1800b71b7  lea     r8, aPcshellShellCl_0; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800b71be  mov     edx, 0B1h; void *
0x1800b71c3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
