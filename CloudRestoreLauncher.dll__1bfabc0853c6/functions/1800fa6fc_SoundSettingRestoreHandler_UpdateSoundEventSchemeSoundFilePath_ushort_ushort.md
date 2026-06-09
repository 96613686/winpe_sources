# SoundSettingRestoreHandler::UpdateSoundEventSchemeSoundFilePath(ushort *,ushort *)

- ea: `0x1800fa6fc`
- end: `0x1800fa8ad`
- name: `?UpdateSoundEventSchemeSoundFilePath@SoundSettingRestoreHandler@@AEAAXPEAG0@Z`
- size: `433`
- prototype: `void(SoundSettingRestoreHandler *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800f9cc4`

## callees

- `0x18000c6e0`
- `0x18000d688`
- `0x1800977e8`
- `0x1800f8ff0`
- `0x1800f9328`
- `0x1800f9510`
- `0x1800fa018`
- `0x1800fa6fc`
- `0x1800fa8b4`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800fa775`
- `KERNEL32!CompareStringOrdinal` at `0x1800fa775`
- `SHLWAPI!PathFileExistsW` at `0x1800fa789`
- `SHLWAPI!PathFileExistsW` at `0x1800fa789`

## pseudocode

```c
void __fastcall SoundSettingRestoreHandler::UpdateSoundEventSchemeSoundFilePath(
        SoundSettingRestoreHandler *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  SoundSettingRestoreHandler *v5; // rcx
  int SystemSoundSchemeSetting; // eax
  int v7; // edx
  __int64 v8; // rcx
  SoundSettingRestoreHandler *v9; // rcx
  SoundSettingRestoreHandler *v10; // rcx
  int v11; // eax
  int v12; // edx
  int v13; // ecx
  const wchar_t *v14; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v17; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR *v18; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR String1[264]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v20[264]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(String1, 0, 0x208u);
  SystemSoundSchemeSetting = SoundSettingRestoreHandler::GetSystemSoundSchemeSetting(v5, a2, a3, String1, bIgnoreCase);
  LODWORD(v17) = SystemSoundSchemeSetting;
  if ( SystemSoundSchemeSetting < 0 )
    goto LABEL_11;
  if ( CompareStringOrdinal(String1, -1, &word_1801382A0, -1, 1) == 2 || PathFileExistsW(String1) )
    return;
  memset_0(v20, 0, 0x208u);
  SystemSoundSchemeSetting = SoundSettingRestoreHandler::GetSystemSoundSchemeSetting(
                               v9,
                               a2,
                               L".default",
                               v20,
                               bIgnoreCasea);
  LODWORD(v17) = SystemSoundSchemeSetting;
  if ( SystemSoundSchemeSetting < 0 )
  {
LABEL_11:
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 1) != 0 )
      McTemplateU0zzd_EventWriteTransfer(
        v8,
        v7,
        (unsigned int)L"GetSystemSoundSchemeSetting method failed",
        (_DWORD)a2,
        SystemSoundSchemeSetting);
    v14 = L"GetSystemSoundSchemeSetting method failed";
    goto LABEL_14;
  }
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    McTemplateU0zz_EventWriteTransfer(v8, AssociatedSoundSettingRestoreHandlerData, String1, v20);
  v17 = v20;
  v18 = String1;
  CloudRestoreLauncherTelemetry::SoundSettingActivity::SoundSettingActivityData<unsigned short const *,unsigned short const *>(
    &v18,
    &v17);
  v11 = SoundSettingRestoreHandler::SetSystemSoundSchemeSetting(v10, a2, a3, v20);
  LODWORD(v17) = v11;
  if ( v11 < 0 )
  {
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 1) != 0 )
      McTemplateU0zzd_EventWriteTransfer(
        v13,
        v12,
        (unsigned int)L"SetSystemSoundSchemeSetting method failed",
        (_DWORD)a2,
        v11);
    v14 = L"SetSystemSoundSchemeSetting method failed";
LABEL_14:
    v18 = a2;
    CloudRestoreLauncherTelemetry::SoundSettingActivity::SoundSettingActivityError<unsigned short const (&)[42],unsigned short const *,long &>(
      v14,
      &v18,
      &v17);
  }
}

```

## disassembly

```asm
0x1800fa6fc  mov     [rsp-8+arg_0], rbx
0x1800fa701  mov     [rsp-8+arg_18], rdi
0x1800fa706  push    rbp
0x1800fa707  lea     rbp, [rsp-370h]
0x1800fa70f  sub     rsp, 470h
0x1800fa716  mov     rax, cs:__security_cookie
0x1800fa71d  xor     rax, rsp
0x1800fa720  mov     [rbp+370h+var_10], rax
0x1800fa727  mov     rdi, r8
0x1800fa72a  lea     rcx, [rsp+470h+String1]; void *
0x1800fa72f  mov     rbx, rdx
0x1800fa732  mov     r8d, 208h; Size
0x1800fa738  xor     edx, edx; Val
0x1800fa73a  call    memset_0
0x1800fa73f  lea     r9, [rsp+470h+String1]; unsigned __int16 *
0x1800fa744  mov     r8, rdi; unsigned __int16 *
0x1800fa747  mov     rdx, rbx; unsigned __int16 *
0x1800fa74a  call    ?GetSystemSoundSchemeSetting@SoundSettingRestoreHandler@@AEAAJPEBG0PEAGI@Z; SoundSettingRestoreHandler::GetSystemSoundSchemeSetting(ushort const *,ushort const *,ushort *,uint)
0x1800fa74f  mov     dword ptr [rsp+470h+var_440], eax
0x1800fa753  test    eax, eax
0x1800fa755  js      loc_1800FA852
0x1800fa75b  or      edx, 0FFFFFFFFh; cchCount1
0x1800fa75e  mov     [rsp+470h+bIgnoreCase], 1; unsigned int
0x1800fa766  mov     r9d, edx; cchCount2
0x1800fa769  lea     r8, word_1801382A0; lpString2
0x1800fa770  lea     rcx, [rsp+470h+String1]; lpString1
0x1800fa775  call    cs:__imp_CompareStringOrdinal
0x1800fa77b  cmp     eax, 2
0x1800fa77e  jz      loc_1800FA889
0x1800fa784  lea     rcx, [rsp+470h+String1]; pszPath
0x1800fa789  call    cs:__imp_PathFileExistsW
0x1800fa78f  test    eax, eax
0x1800fa791  jnz     loc_1800FA889
0x1800fa797  xor     edx, edx; Val
0x1800fa799  lea     rcx, [rbp+370h+var_220]; void *
0x1800fa7a0  mov     r8d, 208h; Size
0x1800fa7a6  call    memset_0
0x1800fa7ab  lea     r9, [rbp+370h+var_220]; unsigned __int16 *
0x1800fa7b2  mov     rdx, rbx; unsigned __int16 *
0x1800fa7b5  lea     r8, aDefault_0; ".default"
0x1800fa7bc  call    ?GetSystemSoundSchemeSetting@SoundSettingRestoreHandler@@AEAAJPEBG0PEAGI@Z; SoundSettingRestoreHandler::GetSystemSoundSchemeSetting(ushort const *,ushort const *,ushort *,uint)
0x1800fa7c1  mov     dword ptr [rsp+470h+var_440], eax
0x1800fa7c5  test    eax, eax
0x1800fa7c7  js      loc_1800FA852
0x1800fa7cd  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800fa7d4  jz      short loc_1800FA7EE
0x1800fa7d6  lea     r9, [rbp+370h+var_220]
0x1800fa7dd  lea     r8, [rsp+470h+String1]
0x1800fa7e2  lea     rdx, AssociatedSoundSettingRestoreHandlerData
0x1800fa7e9  call    McTemplateU0zz_EventWriteTransfer
0x1800fa7ee  lea     rax, [rbp+370h+var_220]
0x1800fa7f5  mov     [rsp+470h+var_440], rax
0x1800fa7fa  lea     rdx, [rsp+470h+var_440]
0x1800fa7ff  lea     rax, [rsp+470h+String1]
0x1800fa804  lea     rcx, [rsp+470h+var_438]
0x1800fa809  mov     [rsp+470h+var_438], rax
0x1800fa80e  call    ??$SoundSettingActivityData@PEBGPEBG@SoundSettingActivity@CloudRestoreLauncherTelemetry@@SAX$$QEAPEBG0@Z; CloudRestoreLauncherTelemetry::SoundSettingActivity::SoundSettingActivityData<ushort const *,ushort const *>(ushort const * &&,ushort const * &&)
0x1800fa813  lea     r9, [rbp+370h+var_220]; unsigned __int16 *
0x1800fa81a  mov     r8, rdi; unsigned __int16 *
0x1800fa81d  mov     rdx, rbx; unsigned __int16 *
0x1800fa820  call    ?SetSystemSoundSchemeSetting@SoundSettingRestoreHandler@@AEAAJPEBG00@Z; SoundSettingRestoreHandler::SetSystemSoundSchemeSetting(ushort const *,ushort const *,ushort const *)
0x1800fa825  mov     dword ptr [rsp+470h+var_440], eax
0x1800fa829  test    eax, eax
0x1800fa82b  jns     short loc_1800FA889
0x1800fa82d  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 1
0x1800fa834  jz      short loc_1800FA849
0x1800fa836  mov     r9, rbx
0x1800fa839  mov     [rsp+470h+bIgnoreCase], eax
0x1800fa83d  lea     r8, aSetsystemsound; "SetSystemSoundSchemeSetting method fail"...
0x1800fa844  call    McTemplateU0zzd_EventWriteTransfer
0x1800fa849  lea     rcx, aSetsystemsound; "SetSystemSoundSchemeSetting method fail"...
0x1800fa850  jmp     short loc_1800FA875
0x1800fa852  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 1
0x1800fa859  jz      short loc_1800FA86E
0x1800fa85b  mov     r9, rbx
0x1800fa85e  mov     [rsp+470h+bIgnoreCase], eax
0x1800fa862  lea     r8, aGetsystemsound; "GetSystemSoundSchemeSetting method fail"...
0x1800fa869  call    McTemplateU0zzd_EventWriteTransfer
0x1800fa86e  lea     rcx, aGetsystemsound; "GetSystemSoundSchemeSetting method fail"...
0x1800fa875  lea     r8, [rsp+470h+var_440]
0x1800fa87a  mov     [rsp+470h+var_438], rbx
0x1800fa87f  lea     rdx, [rsp+470h+var_438]
0x1800fa884  call    ??$SoundSettingActivityError@AEAY0CK@$$CBGPEBGAEAJ@SoundSettingActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0CK@$$CBG$$QEAPEBGAEAJ@Z; CloudRestoreLauncherTelemetry::SoundSettingActivity::SoundSettingActivityError<ushort const (&)[42],ushort const *,long &>(ushort const (&)[42],ushort const * &&,long &)
0x1800fa889  mov     rcx, [rbp+370h+var_10]
0x1800fa890  xor     rcx, rsp; StackCookie
0x1800fa893  call    __security_check_cookie
0x1800fa898  lea     r11, [rsp+470h+var_s0]
0x1800fa8a0  mov     rbx, [r11+10h]
0x1800fa8a4  mov     rdi, [r11+28h]
0x1800fa8a8  mov     rsp, r11
0x1800fa8ab  pop     rbp
0x1800fa8ac  retn
```
