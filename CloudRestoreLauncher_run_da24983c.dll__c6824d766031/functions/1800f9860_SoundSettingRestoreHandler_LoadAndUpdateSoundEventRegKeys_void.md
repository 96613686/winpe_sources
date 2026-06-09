# SoundSettingRestoreHandler::LoadAndUpdateSoundEventRegKeys(void)

- ea: `0x1800f9860`
- end: `0x1800f9a5f`
- name: `?LoadAndUpdateSoundEventRegKeys@SoundSettingRestoreHandler@@AEAAXXZ`
- size: `511`
- prototype: `void __fastcall(SoundSettingRestoreHandler *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800f9f40`

## callees

- `0x18000c6e0`
- `0x1800123f4`
- `0x180012470`
- `0x18001cfa4`
- `0x1800284d0`
- `0x1800f91d8`
- `0x1800f9860`
- `0x1800f9a68`
- `0x1800fa8b4`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x1800f99ba`
- `ADVAPI32!RegEnumKeyExW` at `0x1800f99ba`
- `ADVAPI32!RegOpenKeyExW` at `0x1800f98b6`
- `ADVAPI32!RegOpenKeyExW` at `0x1800f98b6`
- `ADVAPI32!RegCloseKey` at `0x1800f9a1e`
- `ADVAPI32!RegCloseKey` at `0x1800f9a1e`

## pseudocode

```c
void __fastcall SoundSettingRestoreHandler::LoadAndUpdateSoundEventRegKeys(SoundSettingRestoreHandler *this)
{
  int v1; // eax
  bool v2; // sf
  DWORD v3; // esi
  DWORD i; // edx
  signed int v5; // eax
  int v6; // eax
  unsigned __int64 v7; // rdx
  int v8; // eax
  SoundSettingRestoreHandler *v9; // rcx
  int v10; // edx
  __int64 v11; // rcx
  int v12; // ebx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  int v17; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v18; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v19[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  hKey = 0;
  v1 = RegOpenKeyExW(HKEY_CURRENT_USER, L"AppEvents\\Schemes\\Apps", 0, 0x20019u, &hKey);
  v2 = v1 < 0;
  if ( v1 > 0 )
  {
    v1 = (unsigned __int16)v1 | 0x80070000;
    v2 = v1 < 0;
  }
  if ( v2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\soundsettingrestorehandler.cpp",
      (const char *)(unsigned int)v1,
      phkResult);
  v3 = 0;
  for ( i = 0; ; i = v3 )
  {
    cchName = 260;
    v12 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
    if ( v12 == 259 )
      break;
    if ( v12 > 0 )
      v5 = (unsigned __int16)v12 | 0x80070000;
    else
      v5 = v12;
    if ( v5 < 0 )
    {
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 1) != 0 )
        McTemplateU0zzd_EventWriteTransfer(
          v11,
          v10,
          (unsigned int)L"Failed To Enumerate Reg Keys",
          (unsigned int)L"AppEvents\\Schemes\\Apps",
          v12);
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      v17 = v12;
      v18 = L"AppEvents\\Schemes\\Apps";
      CloudRestoreLauncherTelemetry::SoundSettingActivity::SoundSettingActivityError<unsigned short const (&)[29],unsigned short const *,long>(
        v11,
        &v18,
        &v17);
      break;
    }
    v6 = StringCchCopyW(v19, 0x104u, L"AppEvents\\Schemes\\Apps\\");
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\soundsettingrestorehandler.cpp",
        (const char *)(unsigned int)v6,
        phkResulta);
    v8 = StringCchCatW(v19, v7, Name);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\soundsettingrestorehandler.cpp",
        (const char *)(unsigned int)v8,
        phkResulta);
    SoundSettingRestoreHandler::LoadSoundEvents(v9, v19);
    ++v3;
  }
  RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1800f9860  push    rbp
0x1800f9862  push    rbx
0x1800f9863  push    rsi
0x1800f9864  push    rdi
0x1800f9865  push    r12
0x1800f9867  push    r15
0x1800f9869  lea     rbp, [rsp-398h]
0x1800f9871  sub     rsp, 498h
0x1800f9878  mov     rax, cs:__security_cookie
0x1800f987f  xor     rax, rsp
0x1800f9882  mov     [rbp+3C0h+var_40], rax
0x1800f9889  lea     rax, [rsp+4C0h+hKey]
0x1800f988e  mov     [rsp+4C0h+hKey], 0
0x1800f9897  lea     r12, aAppeventsSchem_0; "AppEvents\\Schemes\\Apps"
0x1800f989e  mov     [rsp+4C0h+phkResult], rax; int
0x1800f98a3  mov     rdx, r12; lpSubKey
0x1800f98a6  mov     r9d, 20019h; samDesired
0x1800f98ac  xor     r8d, r8d; ulOptions
0x1800f98af  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800f98b6  call    cs:__imp_RegOpenKeyExW
0x1800f98bc  mov     r15d, 80070000h
0x1800f98c2  test    eax, eax
0x1800f98c4  jle     short loc_1800F98CE
0x1800f98c6  movzx   eax, ax
0x1800f98c9  or      eax, r15d
0x1800f98cc  test    eax, eax
0x1800f98ce  js      loc_1800F9A43
0x1800f98d4  xor     esi, esi
0x1800f98d6  mov     [rsp+4C0h+lpftLastWriteTime], rsi
0x1800f98db  xor     edx, edx
0x1800f98dd  mov     [rsp+4C0h+lpcchClass], rsi
0x1800f98e2  mov     [rsp+4C0h+lpClass], rsi
0x1800f98e7  mov     [rsp+4C0h+phkResult], rsi
0x1800f98ec  jmp     loc_1800F99A1
0x1800f98f1  test    ebx, ebx
0x1800f98f3  jg      short loc_1800F98F9
0x1800f98f5  mov     eax, ebx
0x1800f98f7  jmp     short loc_1800F98FF
0x1800f98f9  movzx   eax, bx
0x1800f98fc  or      eax, r15d
0x1800f98ff  movzx   edi, bx
0x1800f9902  test    eax, eax
0x1800f9904  js      loc_1800F99CF
0x1800f990a  lea     r8, aAppeventsSchem; "AppEvents\\Schemes\\Apps\\"
0x1800f9911  mov     edx, 104h; unsigned __int64
0x1800f9916  lea     rcx, [rsp+4C0h+var_460]; unsigned __int16 *
0x1800f991b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f9920  test    eax, eax
0x1800f9922  jns     short loc_1800F993F
0x1800f9924  mov     rcx, [rbp+3C8h]; this
0x1800f992b  lea     r8, aPcshellShellCl_25; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800f9932  mov     r9d, eax; char *
0x1800f9935  mov     edx, 5Ch ; '\'; void *
0x1800f993a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f993f  lea     r8, [rbp+3C0h+Name]; unsigned __int16 *
0x1800f9946  lea     rcx, [rsp+4C0h+var_460]; unsigned __int16 *
0x1800f994b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f9950  test    eax, eax
0x1800f9952  jns     short loc_1800F996F
0x1800f9954  mov     rcx, [rbp+3C8h]; this
0x1800f995b  lea     r8, aPcshellShellCl_25; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800f9962  mov     r9d, eax; char *
0x1800f9965  mov     edx, 5Dh ; ']'; void *
0x1800f996a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f996f  lea     rdx, [rsp+4C0h+var_460]; unsigned __int16 *
0x1800f9974  call    ?LoadSoundEvents@SoundSettingRestoreHandler@@AEAAXPEAG@Z; SoundSettingRestoreHandler::LoadSoundEvents(ushort *)
0x1800f9979  mov     [rsp+4C0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800f9982  inc     esi
0x1800f9984  mov     [rsp+4C0h+lpcchClass], 0; lpcchClass
0x1800f998d  mov     edx, esi; dwIndex
0x1800f998f  mov     [rsp+4C0h+lpClass], 0; lpClass
0x1800f9998  mov     [rsp+4C0h+phkResult], 0; int
0x1800f99a1  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800f99a6  lea     r9, [rsp+4C0h+cchName]; lpcchName
0x1800f99ab  lea     r8, [rbp+3C0h+Name]; lpName
0x1800f99b2  mov     [rsp+4C0h+cchName], 104h
0x1800f99ba  call    cs:__imp_RegEnumKeyExW
0x1800f99c0  mov     ebx, eax
0x1800f99c2  cmp     eax, 103h
0x1800f99c7  jnz     loc_1800F98F1
0x1800f99cd  jmp     short loc_1800F9A19
0x1800f99cf  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 1
0x1800f99d6  jz      short loc_1800F99F8
0x1800f99d8  test    ebx, ebx
0x1800f99da  jg      short loc_1800F99E0
0x1800f99dc  mov     eax, ebx
0x1800f99de  jmp     short loc_1800F99E5
0x1800f99e0  mov     eax, edi
0x1800f99e2  or      eax, r15d
0x1800f99e5  mov     r9, r12
0x1800f99e8  mov     dword ptr [rsp+4C0h+phkResult], eax
0x1800f99ec  lea     r8, aFailedToEnumer; "Failed To Enumerate Reg Keys"
0x1800f99f3  call    McTemplateU0zzd_EventWriteTransfer
0x1800f99f8  test    ebx, ebx
0x1800f99fa  jle     short loc_1800F9A01
0x1800f99fc  mov     ebx, edi
0x1800f99fe  or      ebx, r15d
0x1800f9a01  lea     r8, [rsp+4C0h+var_470]
0x1800f9a06  mov     [rsp+4C0h+var_470], ebx
0x1800f9a0a  lea     rdx, [rsp+4C0h+var_468]
0x1800f9a0f  mov     [rsp+4C0h+var_468], r12
0x1800f9a14  call    ??$SoundSettingActivityError@AEAY0BN@$$CBGPEBGJ@SoundSettingActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0BN@$$CBG$$QEAPEBG$$QEAJ@Z; CloudRestoreLauncherTelemetry::SoundSettingActivity::SoundSettingActivityError<ushort const (&)[29],ushort const *,long>(ushort const (&)[29],ushort const * &&,long &&)
0x1800f9a19  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800f9a1e  call    cs:__imp_RegCloseKey
0x1800f9a24  mov     rcx, [rbp+3C0h+var_40]
0x1800f9a2b  xor     rcx, rsp; StackCookie
0x1800f9a2e  call    __security_check_cookie
0x1800f9a33  add     rsp, 498h
0x1800f9a3a  pop     r15
0x1800f9a3c  pop     r12
0x1800f9a3e  pop     rdi
0x1800f9a3f  pop     rsi
0x1800f9a40  pop     rbx
0x1800f9a41  pop     rbp
0x1800f9a42  retn
0x1800f9a43  mov     rcx, [rbp+3C8h]; this
0x1800f9a4a  lea     r8, aPcshellShellCl_25; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800f9a51  mov     r9d, eax; char *
0x1800f9a54  mov     edx, 4Fh ; 'O'; void *
0x1800f9a59  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
