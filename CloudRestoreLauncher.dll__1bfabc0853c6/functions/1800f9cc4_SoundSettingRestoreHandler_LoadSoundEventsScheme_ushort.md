# SoundSettingRestoreHandler::LoadSoundEventsScheme(ushort *)

- ea: `0x1800f9cc4`
- end: `0x1800f9f31`
- name: `?LoadSoundEventsScheme@SoundSettingRestoreHandler@@AEAAXPEAG@Z`
- size: `621`
- prototype: `void(SoundSettingRestoreHandler *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800f9a68`

## callees

- `0x18000c6e0`
- `0x1800123f4`
- `0x180012470`
- `0x1800284d0`
- `0x1800f9080`
- `0x1800f91d8`
- `0x1800f9cc4`
- `0x1800fa6fc`
- `0x1800fa8b4`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800f9e1d`
- `KERNEL32!CompareStringOrdinal` at `0x1800f9e1d`
- `ADVAPI32!RegEnumKeyExW` at `0x1800f9e76`
- `ADVAPI32!RegEnumKeyExW` at `0x1800f9e76`
- `ADVAPI32!RegOpenKeyExW` at `0x1800f9d13`
- `ADVAPI32!RegOpenKeyExW` at `0x1800f9d13`
- `ADVAPI32!RegCloseKey` at `0x1800f9f0c`
- `ADVAPI32!RegCloseKey` at `0x1800f9f0c`

## string_xrefs

- `0x1800f9ee7`: `RegOpenKeyEx API failed`

## pseudocode

```c
void __fastcall SoundSettingRestoreHandler::LoadSoundEventsScheme(
        SoundSettingRestoreHandler *this,
        unsigned __int16 *a2)
{
  int v3; // eax
  int v4; // edx
  __int64 v5; // rcx
  DWORD v6; // r14d
  DWORD i; // edx
  signed int v8; // eax
  int v9; // eax
  unsigned __int64 v10; // rdx
  int v11; // eax
  unsigned __int64 v12; // rdx
  int v13; // eax
  SoundSettingRestoreHandler *v14; // rcx
  int v15; // edx
  __int64 v16; // rcx
  int v17; // ebx
  int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR String1[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v24[264]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_CURRENT_USER, a2, 0, 0x20019u, &hKey);
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  v20 = v3;
  if ( v3 < 0 )
  {
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 1) != 0 )
      McTemplateU0zzd_EventWriteTransfer(v5, v4, (unsigned int)L"RegOpenKeyEx API failed", (_DWORD)a2, v3);
    v22[0] = a2;
    CloudRestoreLauncherTelemetry::SoundSettingActivity::SoundSettingActivityError<unsigned short const (&)[24],unsigned short const *,long &>(
      v5,
      v22,
      &v20);
  }
  else
  {
    v6 = 0;
    for ( i = 0; ; i = v6 )
    {
      cchName = 260;
      v17 = RegEnumKeyExW(hKey, i, String1, &cchName, 0, 0, 0, 0);
      if ( v17 == 259 )
        break;
      if ( v17 > 0 )
        v8 = (unsigned __int16)v17 | 0x80070000;
      else
        v8 = v17;
      if ( v8 < 0 )
      {
        if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 1) != 0 )
          McTemplateU0zzd_EventWriteTransfer(v16, v15, (unsigned int)L"Failed To Enumerate Reg Keys", (_DWORD)a2, v17);
        if ( v17 > 0 )
          v17 = (unsigned __int16)v17 | 0x80070000;
        v20 = v17;
        v22[0] = a2;
        CloudRestoreLauncherTelemetry::SoundSettingActivity::SoundSettingActivityError<unsigned short const (&)[29],unsigned short const *,long>(
          v16,
          v22,
          &v20);
        break;
      }
      v9 = StringCchCopyW(v24, 0x104u, a2);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xA8,
          (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\soundsettingrestorehandler.cpp",
          (const char *)(unsigned int)v9,
          phkResult);
      v11 = StringCchCatW(v24, v10, L"\\");
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xA9,
          (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\soundsettingrestorehandler.cpp",
          (const char *)(unsigned int)v11,
          phkResult);
      v13 = StringCchCatW(v24, v12, String1);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\soundsettingrestorehandler.cpp",
          (const char *)(unsigned int)v13,
          phkResult);
      if ( CompareStringOrdinal(String1, -1, L".Default", -1, 1) != 2 )
        SoundSettingRestoreHandler::UpdateSoundEventSchemeSoundFilePath(v14, a2, String1);
      ++v6;
    }
  }
  RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1800f9cc4  push    rbp
0x1800f9cc6  push    rbx
0x1800f9cc7  push    rsi
0x1800f9cc8  push    rdi
0x1800f9cc9  push    r12
0x1800f9ccb  push    r14
0x1800f9ccd  lea     rbp, [rsp-398h]
0x1800f9cd5  sub     rsp, 498h
0x1800f9cdc  mov     rax, cs:__security_cookie
0x1800f9ce3  xor     rax, rsp
0x1800f9ce6  mov     [rbp+3C0h+var_40], rax
0x1800f9ced  lea     rax, [rsp+4C0h+hKey]
0x1800f9cf2  mov     [rsp+4C0h+hKey], 0
0x1800f9cfb  mov     r9d, 20019h; samDesired
0x1800f9d01  mov     [rsp+4C0h+phkResult], rax; phkResult
0x1800f9d06  xor     r8d, r8d; ulOptions
0x1800f9d09  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800f9d10  mov     rdi, rdx
0x1800f9d13  call    cs:__imp_RegOpenKeyExW
0x1800f9d19  mov     r12d, 80070000h
0x1800f9d1f  test    eax, eax
0x1800f9d21  jle     short loc_1800F9D29
0x1800f9d23  movzx   eax, ax
0x1800f9d26  or      eax, r12d
0x1800f9d29  mov     [rsp+4C0h+var_47C], eax
0x1800f9d2d  test    eax, eax
0x1800f9d2f  js      loc_1800F9ED7
0x1800f9d35  xor     r14d, r14d
0x1800f9d38  mov     [rsp+4C0h+lpftLastWriteTime], r14
0x1800f9d3d  xor     edx, edx
0x1800f9d3f  mov     [rsp+4C0h+lpcchClass], r14
0x1800f9d44  mov     [rsp+4C0h+lpClass], r14
0x1800f9d49  mov     [rsp+4C0h+phkResult], r14
0x1800f9d4e  jmp     loc_1800F9E5F
0x1800f9d53  test    ebx, ebx
0x1800f9d55  jg      short loc_1800F9D5B
0x1800f9d57  mov     eax, ebx
0x1800f9d59  jmp     short loc_1800F9D61
0x1800f9d5b  movzx   eax, bx
0x1800f9d5e  or      eax, r12d
0x1800f9d61  movzx   esi, bx
0x1800f9d64  test    eax, eax
0x1800f9d66  js      loc_1800F9E8B
0x1800f9d6c  mov     r8, rdi; unsigned __int16 *
0x1800f9d6f  lea     rcx, [rbp+3C0h+var_250]; unsigned __int16 *
0x1800f9d76  mov     edx, 104h; unsigned __int64
0x1800f9d7b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f9d80  test    eax, eax
0x1800f9d82  jns     short loc_1800F9D9F
0x1800f9d84  mov     rcx, [rbp+3C8h]; this
0x1800f9d8b  lea     r8, aPcshellShellCl_25; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800f9d92  mov     r9d, eax; char *
0x1800f9d95  mov     edx, 0A8h; void *
0x1800f9d9a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f9d9f  lea     r8, StringValue; "\\"
0x1800f9da6  lea     rcx, [rbp+3C0h+var_250]; unsigned __int16 *
0x1800f9dad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f9db2  test    eax, eax
0x1800f9db4  jns     short loc_1800F9DD1
0x1800f9db6  mov     rcx, [rbp+3C8h]; this
0x1800f9dbd  lea     r8, aPcshellShellCl_25; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800f9dc4  mov     r9d, eax; char *
0x1800f9dc7  mov     edx, 0A9h; void *
0x1800f9dcc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f9dd1  lea     r8, [rsp+4C0h+String1]; unsigned __int16 *
0x1800f9dd6  lea     rcx, [rbp+3C0h+var_250]; unsigned __int16 *
0x1800f9ddd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f9de2  test    eax, eax
0x1800f9de4  jns     short loc_1800F9E01
0x1800f9de6  mov     rcx, [rbp+3C8h]; this
0x1800f9ded  lea     r8, aPcshellShellCl_25; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800f9df4  mov     r9d, eax; char *
0x1800f9df7  mov     edx, 0AAh; void *
0x1800f9dfc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f9e01  or      esi, 0FFFFFFFFh
0x1800f9e04  mov     dword ptr [rsp+4C0h+phkResult], 1; bIgnoreCase
0x1800f9e0c  mov     r9d, esi; cchCount2
0x1800f9e0f  lea     r8, aDefault; ".Default"
0x1800f9e16  mov     edx, esi; cchCount1
0x1800f9e18  lea     rcx, [rsp+4C0h+String1]; lpString1
0x1800f9e1d  call    cs:__imp_CompareStringOrdinal
0x1800f9e23  cmp     eax, 2
0x1800f9e26  jz      short loc_1800F9E35
0x1800f9e28  lea     r8, [rsp+4C0h+String1]; unsigned __int16 *
0x1800f9e2d  mov     rdx, rdi; unsigned __int16 *
0x1800f9e30  call    ?UpdateSoundEventSchemeSoundFilePath@SoundSettingRestoreHandler@@AEAAXPEAG0@Z; SoundSettingRestoreHandler::UpdateSoundEventSchemeSoundFilePath(ushort *,ushort *)
0x1800f9e35  mov     [rsp+4C0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800f9e3e  inc     r14d
0x1800f9e41  mov     [rsp+4C0h+lpcchClass], 0; lpcchClass
0x1800f9e4a  mov     edx, r14d; dwIndex
0x1800f9e4d  mov     [rsp+4C0h+lpClass], 0; lpClass
0x1800f9e56  mov     [rsp+4C0h+phkResult], 0; int
0x1800f9e5f  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800f9e64  lea     r9, [rsp+4C0h+cchName]; lpcchName
0x1800f9e69  lea     r8, [rsp+4C0h+String1]; lpName
0x1800f9e6e  mov     [rsp+4C0h+cchName], 104h
0x1800f9e76  call    cs:__imp_RegEnumKeyExW
0x1800f9e7c  mov     ebx, eax
0x1800f9e7e  cmp     eax, 103h
0x1800f9e83  jnz     loc_1800F9D53
0x1800f9e89  jmp     short loc_1800F9F07
0x1800f9e8b  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 1
0x1800f9e92  jz      short loc_1800F9EB4
0x1800f9e94  test    ebx, ebx
0x1800f9e96  jg      short loc_1800F9E9C
0x1800f9e98  mov     eax, ebx
0x1800f9e9a  jmp     short loc_1800F9EA1
0x1800f9e9c  mov     eax, esi
0x1800f9e9e  or      eax, r12d
0x1800f9ea1  mov     r9, rdi
0x1800f9ea4  mov     dword ptr [rsp+4C0h+phkResult], eax
0x1800f9ea8  lea     r8, aFailedToEnumer; "Failed To Enumerate Reg Keys"
0x1800f9eaf  call    McTemplateU0zzd_EventWriteTransfer
0x1800f9eb4  test    ebx, ebx
0x1800f9eb6  jle     short loc_1800F9EBD
0x1800f9eb8  mov     ebx, esi
0x1800f9eba  or      ebx, r12d
0x1800f9ebd  lea     r8, [rsp+4C0h+var_47C]
0x1800f9ec2  mov     [rsp+4C0h+var_47C], ebx
0x1800f9ec6  lea     rdx, [rsp+4C0h+var_470]
0x1800f9ecb  mov     [rsp+4C0h+var_470], rdi
0x1800f9ed0  call    ??$SoundSettingActivityError@AEAY0BN@$$CBGPEBGJ@SoundSettingActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0BN@$$CBG$$QEAPEBG$$QEAJ@Z; CloudRestoreLauncherTelemetry::SoundSettingActivity::SoundSettingActivityError<ushort const (&)[29],ushort const *,long>(ushort const (&)[29],ushort const * &&,long &&)
0x1800f9ed5  jmp     short loc_1800F9F07
0x1800f9ed7  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 1
0x1800f9ede  jz      short loc_1800F9EF3
0x1800f9ee0  mov     r9, rdi
0x1800f9ee3  mov     dword ptr [rsp+4C0h+phkResult], eax
0x1800f9ee7  lea     r8, aRegopenkeyexAp; "RegOpenKeyEx API failed"
0x1800f9eee  call    McTemplateU0zzd_EventWriteTransfer
0x1800f9ef3  lea     r8, [rsp+4C0h+var_47C]
0x1800f9ef8  mov     [rsp+4C0h+var_470], rdi
0x1800f9efd  lea     rdx, [rsp+4C0h+var_470]
0x1800f9f02  call    ??$SoundSettingActivityError@AEAY0BI@$$CBGPEBGAEAJ@SoundSettingActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0BI@$$CBG$$QEAPEBGAEAJ@Z; CloudRestoreLauncherTelemetry::SoundSettingActivity::SoundSettingActivityError<ushort const (&)[24],ushort const *,long &>(ushort const (&)[24],ushort const * &&,long &)
0x1800f9f07  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800f9f0c  call    cs:__imp_RegCloseKey
0x1800f9f12  mov     rcx, [rbp+3C0h+var_40]
0x1800f9f19  xor     rcx, rsp; StackCookie
0x1800f9f1c  call    __security_check_cookie
0x1800f9f21  add     rsp, 498h
0x1800f9f28  pop     r14
0x1800f9f2a  pop     r12
0x1800f9f2c  pop     rdi
0x1800f9f2d  pop     rsi
0x1800f9f2e  pop     rbx
0x1800f9f2f  pop     rbp
0x1800f9f30  retn
```
