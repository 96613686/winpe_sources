# SoundSettingRestoreHandler::LoadSoundEvents(ushort *)

- ea: `0x1800f9a68`
- end: `0x1800f9cbd`
- name: `?LoadSoundEvents@SoundSettingRestoreHandler@@AEAAXPEAG@Z`
- size: `597`
- prototype: `void(SoundSettingRestoreHandler *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f9860`

## callees

- `0x18000c6e0`
- `0x1800123f4`
- `0x180012470`
- `0x1800284d0`
- `0x1800f9080`
- `0x1800f91d8`
- `0x1800f9670`
- `0x1800f9a68`
- `0x1800f9cc4`
- `0x1800fa8b4`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x1800f9c02`
- `ADVAPI32!RegEnumKeyExW` at `0x1800f9c02`
- `ADVAPI32!RegOpenKeyExW` at `0x1800f9ab7`
- `ADVAPI32!RegOpenKeyExW` at `0x1800f9ab7`
- `ADVAPI32!RegCloseKey` at `0x1800f9c98`
- `ADVAPI32!RegCloseKey` at `0x1800f9c98`

## string_xrefs

- `0x1800f9c73`: `RegOpenKeyEx API failed`

## pseudocode

```c
void __fastcall SoundSettingRestoreHandler::LoadSoundEvents(SoundSettingRestoreHandler *this, unsigned __int16 *a2)
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
  SoundSettingRestoreHandler *v16; // rcx
  int v17; // ebx
  int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v23[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+270h] [rbp+170h] BYREF
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
      v17 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      if ( v17 == 259 )
        break;
      if ( v17 > 0 )
        v8 = (unsigned __int16)v17 | 0x80070000;
      else
        v8 = v17;
      if ( v8 < 0 )
      {
        if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 1) != 0 )
          McTemplateU0zzd_EventWriteTransfer(
            (_DWORD)v16,
            v15,
            (unsigned int)L"Failed To Enumerate Reg Keys",
            (_DWORD)a2,
            v17);
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
      if ( !SoundSettingRestoreHandler::IsCPLExclude(v16, Name) )
      {
        v9 = StringCchCopyW(v23, 0x104u, a2);
        if ( v9 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x7F,
            (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\soundsettingrestorehandler.cpp",
            (const char *)(unsigned int)v9,
            phkResult);
        v11 = StringCchCatW(v23, v10, L"\\");
        if ( v11 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x80,
            (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\soundsettingrestorehandler.cpp",
            (const char *)(unsigned int)v11,
            phkResult);
        v13 = StringCchCatW(v23, v12, Name);
        if ( v13 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x81,
            (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\soundsettingrestorehandler.cpp",
            (const char *)(unsigned int)v13,
            phkResult);
        SoundSettingRestoreHandler::LoadSoundEventsScheme(v14, v23);
      }
      ++v6;
    }
  }
  RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1800f9a68  push    rbp
0x1800f9a6a  push    rbx
0x1800f9a6b  push    rsi
0x1800f9a6c  push    rdi
0x1800f9a6d  push    r12
0x1800f9a6f  push    r14
0x1800f9a71  lea     rbp, [rsp-398h]
0x1800f9a79  sub     rsp, 498h
0x1800f9a80  mov     rax, cs:__security_cookie
0x1800f9a87  xor     rax, rsp
0x1800f9a8a  mov     [rbp+3C0h+var_40], rax
0x1800f9a91  lea     rax, [rsp+4C0h+hKey]
0x1800f9a96  mov     [rsp+4C0h+hKey], 0
0x1800f9a9f  mov     r9d, 20019h; samDesired
0x1800f9aa5  mov     [rsp+4C0h+phkResult], rax; phkResult
0x1800f9aaa  xor     r8d, r8d; ulOptions
0x1800f9aad  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800f9ab4  mov     rdi, rdx
0x1800f9ab7  call    cs:__imp_RegOpenKeyExW
0x1800f9abd  mov     r12d, 80070000h
0x1800f9ac3  test    eax, eax
0x1800f9ac5  jle     short loc_1800F9ACD
0x1800f9ac7  movzx   eax, ax
0x1800f9aca  or      eax, r12d
0x1800f9acd  mov     [rsp+4C0h+var_47C], eax
0x1800f9ad1  test    eax, eax
0x1800f9ad3  js      loc_1800F9C63
0x1800f9ad9  xor     r14d, r14d
0x1800f9adc  mov     [rsp+4C0h+lpftLastWriteTime], r14
0x1800f9ae1  xor     edx, edx
0x1800f9ae3  mov     [rsp+4C0h+lpcchClass], r14
0x1800f9ae8  mov     [rsp+4C0h+lpClass], r14
0x1800f9aed  mov     [rsp+4C0h+phkResult], r14
0x1800f9af2  jmp     loc_1800F9BE9
0x1800f9af7  test    ebx, ebx
0x1800f9af9  jg      short loc_1800F9AFF
0x1800f9afb  mov     eax, ebx
0x1800f9afd  jmp     short loc_1800F9B05
0x1800f9aff  movzx   eax, bx
0x1800f9b02  or      eax, r12d
0x1800f9b05  movzx   esi, bx
0x1800f9b08  test    eax, eax
0x1800f9b0a  js      loc_1800F9C17
0x1800f9b10  lea     rdx, [rbp+3C0h+Name]; unsigned __int16 *
0x1800f9b17  call    ?IsCPLExclude@SoundSettingRestoreHandler@@AEAA_NPEAG@Z; SoundSettingRestoreHandler::IsCPLExclude(ushort *)
0x1800f9b1c  test    al, al
0x1800f9b1e  jnz     loc_1800F9BBF
0x1800f9b24  mov     r8, rdi; unsigned __int16 *
0x1800f9b27  lea     rcx, [rsp+4C0h+var_460]; unsigned __int16 *
0x1800f9b2c  mov     edx, 104h; unsigned __int64
0x1800f9b31  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f9b36  test    eax, eax
0x1800f9b38  jns     short loc_1800F9B55
0x1800f9b3a  mov     rcx, [rbp+3C8h]; this
0x1800f9b41  lea     r8, aPcshellShellCl_25; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800f9b48  mov     r9d, eax; char *
0x1800f9b4b  mov     edx, 7Fh; void *
0x1800f9b50  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f9b55  lea     r8, StringValue; "\\"
0x1800f9b5c  lea     rcx, [rsp+4C0h+var_460]; unsigned __int16 *
0x1800f9b61  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f9b66  test    eax, eax
0x1800f9b68  jns     short loc_1800F9B85
0x1800f9b6a  mov     rcx, [rbp+3C8h]; this
0x1800f9b71  lea     r8, aPcshellShellCl_25; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800f9b78  mov     r9d, eax; char *
0x1800f9b7b  mov     edx, 80h; void *
0x1800f9b80  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f9b85  lea     r8, [rbp+3C0h+Name]; unsigned __int16 *
0x1800f9b8c  lea     rcx, [rsp+4C0h+var_460]; unsigned __int16 *
0x1800f9b91  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f9b96  test    eax, eax
0x1800f9b98  jns     short loc_1800F9BB5
0x1800f9b9a  mov     rcx, [rbp+3C8h]; this
0x1800f9ba1  lea     r8, aPcshellShellCl_25; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800f9ba8  mov     r9d, eax; char *
0x1800f9bab  mov     edx, 81h; void *
0x1800f9bb0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f9bb5  lea     rdx, [rsp+4C0h+var_460]; unsigned __int16 *
0x1800f9bba  call    ?LoadSoundEventsScheme@SoundSettingRestoreHandler@@AEAAXPEAG@Z; SoundSettingRestoreHandler::LoadSoundEventsScheme(ushort *)
0x1800f9bbf  mov     [rsp+4C0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800f9bc8  inc     r14d
0x1800f9bcb  mov     [rsp+4C0h+lpcchClass], 0; lpcchClass
0x1800f9bd4  mov     edx, r14d; dwIndex
0x1800f9bd7  mov     [rsp+4C0h+lpClass], 0; lpClass
0x1800f9be0  mov     [rsp+4C0h+phkResult], 0; int
0x1800f9be9  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800f9bee  lea     r9, [rsp+4C0h+cchName]; lpcchName
0x1800f9bf3  lea     r8, [rbp+3C0h+Name]; lpName
0x1800f9bfa  mov     [rsp+4C0h+cchName], 104h
0x1800f9c02  call    cs:__imp_RegEnumKeyExW
0x1800f9c08  mov     ebx, eax
0x1800f9c0a  cmp     eax, 103h
0x1800f9c0f  jnz     loc_1800F9AF7
0x1800f9c15  jmp     short loc_1800F9C93
0x1800f9c17  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 1
0x1800f9c1e  jz      short loc_1800F9C40
0x1800f9c20  test    ebx, ebx
0x1800f9c22  jg      short loc_1800F9C28
0x1800f9c24  mov     eax, ebx
0x1800f9c26  jmp     short loc_1800F9C2D
0x1800f9c28  mov     eax, esi
0x1800f9c2a  or      eax, r12d
0x1800f9c2d  mov     r9, rdi
0x1800f9c30  mov     dword ptr [rsp+4C0h+phkResult], eax
0x1800f9c34  lea     r8, aFailedToEnumer; "Failed To Enumerate Reg Keys"
0x1800f9c3b  call    McTemplateU0zzd_EventWriteTransfer
0x1800f9c40  test    ebx, ebx
0x1800f9c42  jle     short loc_1800F9C49
0x1800f9c44  mov     ebx, esi
0x1800f9c46  or      ebx, r12d
0x1800f9c49  lea     r8, [rsp+4C0h+var_47C]
0x1800f9c4e  mov     [rsp+4C0h+var_47C], ebx
0x1800f9c52  lea     rdx, [rsp+4C0h+var_470]
0x1800f9c57  mov     [rsp+4C0h+var_470], rdi
0x1800f9c5c  call    ??$SoundSettingActivityError@AEAY0BN@$$CBGPEBGJ@SoundSettingActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0BN@$$CBG$$QEAPEBG$$QEAJ@Z; CloudRestoreLauncherTelemetry::SoundSettingActivity::SoundSettingActivityError<ushort const (&)[29],ushort const *,long>(ushort const (&)[29],ushort const * &&,long &&)
0x1800f9c61  jmp     short loc_1800F9C93
0x1800f9c63  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 1
0x1800f9c6a  jz      short loc_1800F9C7F
0x1800f9c6c  mov     r9, rdi
0x1800f9c6f  mov     dword ptr [rsp+4C0h+phkResult], eax
0x1800f9c73  lea     r8, aRegopenkeyexAp; "RegOpenKeyEx API failed"
0x1800f9c7a  call    McTemplateU0zzd_EventWriteTransfer
0x1800f9c7f  lea     r8, [rsp+4C0h+var_47C]
0x1800f9c84  mov     [rsp+4C0h+var_470], rdi
0x1800f9c89  lea     rdx, [rsp+4C0h+var_470]
0x1800f9c8e  call    ??$SoundSettingActivityError@AEAY0BI@$$CBGPEBGAEAJ@SoundSettingActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0BI@$$CBG$$QEAPEBGAEAJ@Z; CloudRestoreLauncherTelemetry::SoundSettingActivity::SoundSettingActivityError<ushort const (&)[24],ushort const *,long &>(ushort const (&)[24],ushort const * &&,long &)
0x1800f9c93  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800f9c98  call    cs:__imp_RegCloseKey
0x1800f9c9e  mov     rcx, [rbp+3C0h+var_40]
0x1800f9ca5  xor     rcx, rsp; StackCookie
0x1800f9ca8  call    __security_check_cookie
0x1800f9cad  add     rsp, 498h
0x1800f9cb4  pop     r14
0x1800f9cb6  pop     r12
0x1800f9cb8  pop     rdi
0x1800f9cb9  pop     rsi
0x1800f9cba  pop     rbx
0x1800f9cbb  pop     rbp
0x1800f9cbc  retn
```
