# SrSettings::CSrSettings::BackupSettings(void)

- ea: `0x1800469e0`
- end: `0x180046b67`
- name: `?BackupSettings@CSrSettings@SrSettings@@UEAAJXZ`
- size: `391`
- prototype: `__int64 __fastcall(LPCWSTR *this)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config`

## callees

- `0x180005c48`
- `0x180006120`
- `0x1800469e0`
- `0x18004a3bc`
- `0x18004c0e8`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x180046b09`
- `KERNEL32!CopyFileW` at `0x180046b09`
- `KERNEL32!GetLastError` at `0x180046a60`
- `KERNEL32!GetLastError` at `0x180046acb`
- `KERNEL32!GetLastError` at `0x180046b13`
- `KERNEL32!GetLastError` at `0x180046a60`
- `KERNEL32!GetLastError` at `0x180046acb`
- `KERNEL32!GetLastError` at `0x180046b13`
- `KERNEL32!DeleteFileW` at `0x180046ac1`
- `KERNEL32!DeleteFileW` at `0x180046ac1`

## string_xrefs

- `0x180046a1b`: `No backup path, WinRE must be disabled, cannot backup settings`
- `0x180046a42`: `Delete existing backup file`
- `0x180046a66`: `Failed to delete existing backup file. Err = %lu`
- `0x180046aac`: `Delete backup settings file %s`
- `0x180046ae0`: `Failed to delete backup settings file. Error: 0x%08x`
- `0x180046b43`: `Failed to set ACL on backup settings file. Error: 0x%08x`

## pseudocode

```c
__int64 __fastcall SrSettings::CSrSettings::BackupSettings(LPCWSTR *this)
{
  __int64 result; // rax
  const WCHAR *v3; // rcx
  DWORD LastError; // eax
  signed int v5; // eax
  unsigned int v6; // edi
  signed int v7; // eax

  if ( *((_BYTE *)this + 3944) )
  {
    SrSettings::CSrSettings::Trace(this, 2, L"Cannot backup settings in UseInWinRE mode");
    return 2147942405LL;
  }
  v3 = this[9];
  if ( v3 == this[10] )
  {
    SrSettings::CSrSettings::Trace(this, 2, L"No backup path, WinRE must be disabled, cannot backup settings");
    return 2147942450LL;
  }
  if ( (unsigned int)FileExists(v3) )
  {
    SrSettings::CSrSettings::Trace(this, 0, L"Delete existing backup file");
    if ( !(unsigned int)DeleteFileEx2(this[9]) )
    {
      LastError = GetLastError();
      SrSettings::CSrSettings::Trace(this, 1, L"Failed to delete existing backup file. Err = %lu", LastError);
    }
  }
  if ( (unsigned int)FileExists(this[5])
    || (SrSettings::CSrSettings::Trace(this, 0, L"Settings file not found"), !(unsigned int)FileExists(this[9]))
    || (SrSettings::CSrSettings::Trace(this, 0, L"Delete backup settings file %s", this[9]), DeleteFileW(this[9])) )
  {
    SrSettings::CSrSettings::Trace(this, 0, L"Backup settings to %s", this[9]);
    if ( CopyFileW(this[5], this[9], 0) )
    {
      result = SrSettings::CSrSettings::SetACL((SrSettings::CSrSettings *)this, this[9]);
      v6 = result;
      if ( (int)result >= 0 )
        return result;
      SrSettings::CSrSettings::Trace(
        this,
        2,
        L"Failed to set ACL on backup settings file. Error: 0x%08x",
        (unsigned int)result);
    }
    else
    {
      v7 = GetLastError();
      v6 = v7;
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0x80070000;
      SrSettings::CSrSettings::Trace(this, 2, L"Failed to backup settings. Error: 0x%08x", v6);
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    SrSettings::CSrSettings::Trace(this, 2, L"Failed to delete backup settings file. Error: 0x%08x", v6);
  }
  return v6;
}

```

## disassembly

```asm
0x1800469e0  mov     [rsp+arg_0], rbx
0x1800469e5  push    rdi
0x1800469e6  sub     rsp, 20h
0x1800469ea  cmp     byte ptr [rcx+0F68h], 0
0x1800469f1  mov     rbx, rcx
0x1800469f4  jz      short loc_180046A11
0x1800469f6  lea     r8, aCannotBackupSe; "Cannot backup settings in UseInWinRE mo"...
0x1800469fd  mov     edx, 2
0x180046a02  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180046a07  mov     eax, 80070005h
0x180046a0c  jmp     loc_180046B5C
0x180046a11  mov     rcx, [rcx+48h]
0x180046a15  cmp     rcx, [rbx+50h]
0x180046a19  jnz     short loc_180046A39
0x180046a1b  lea     r8, aNoBackupPathWi; "No backup path, WinRE must be disabled,"...
0x180046a22  mov     edx, 2
0x180046a27  mov     rcx, rbx
0x180046a2a  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180046a2f  mov     eax, 80070032h
0x180046a34  jmp     loc_180046B5C
0x180046a39  call    FileExists
0x180046a3e  test    eax, eax
0x180046a40  jz      short loc_180046A7D
0x180046a42  lea     r8, aDeleteExisting_0; "Delete existing backup file"
0x180046a49  xor     edx, edx
0x180046a4b  mov     rcx, rbx
0x180046a4e  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180046a53  mov     rcx, [rbx+48h]
0x180046a57  call    DeleteFileEx2
0x180046a5c  test    eax, eax
0x180046a5e  jnz     short loc_180046A7D
0x180046a60  call    cs:__imp_GetLastError
0x180046a66  lea     r8, aFailedToDelete_4; "Failed to delete existing backup file. "...
0x180046a6d  mov     edx, 1
0x180046a72  mov     r9d, eax
0x180046a75  mov     rcx, rbx
0x180046a78  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180046a7d  mov     rcx, [rbx+28h]
0x180046a81  call    FileExists
0x180046a86  test    eax, eax
0x180046a88  jnz     short loc_180046AE9
0x180046a8a  lea     r8, aSettingsFileNo; "Settings file not found"
0x180046a91  xor     edx, edx
0x180046a93  mov     rcx, rbx
0x180046a96  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180046a9b  mov     rcx, [rbx+48h]
0x180046a9f  call    FileExists
0x180046aa4  test    eax, eax
0x180046aa6  jz      short loc_180046AE9
0x180046aa8  mov     r9, [rbx+48h]
0x180046aac  lea     r8, aDeleteBackupSe; "Delete backup settings file %s"
0x180046ab3  xor     edx, edx
0x180046ab5  mov     rcx, rbx
0x180046ab8  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180046abd  mov     rcx, [rbx+48h]; lpFileName
0x180046ac1  call    cs:__imp_DeleteFileW
0x180046ac7  test    eax, eax
0x180046ac9  jnz     short loc_180046AE9
0x180046acb  call    cs:__imp_GetLastError
0x180046ad1  mov     edi, eax
0x180046ad3  test    eax, eax
0x180046ad5  jle     short loc_180046AE0
0x180046ad7  movzx   edi, ax
0x180046ada  or      edi, 80070000h
0x180046ae0  lea     r8, aFailedToDelete; "Failed to delete backup settings file. "...
0x180046ae7  jmp     short loc_180046B4A
0x180046ae9  mov     r9, [rbx+48h]
0x180046aed  lea     r8, aBackupSettings; "Backup settings to %s"
0x180046af4  xor     edx, edx
0x180046af6  mov     rcx, rbx
0x180046af9  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180046afe  mov     rdx, [rbx+48h]; lpNewFileName
0x180046b02  xor     r8d, r8d; bFailIfExists
0x180046b05  mov     rcx, [rbx+28h]; lpExistingFileName
0x180046b09  call    cs:__imp_CopyFileW
0x180046b0f  test    eax, eax
0x180046b11  jnz     short loc_180046B31
0x180046b13  call    cs:__imp_GetLastError
0x180046b19  mov     edi, eax
0x180046b1b  test    eax, eax
0x180046b1d  jle     short loc_180046B28
0x180046b1f  movzx   edi, ax
0x180046b22  or      edi, 80070000h
0x180046b28  lea     r8, aFailedToBackup_3; "Failed to backup settings. Error: 0x%08"...
0x180046b2f  jmp     short loc_180046B4A
0x180046b31  mov     rdx, [rbx+48h]; lpFileName
0x180046b35  mov     rcx, rbx; this
0x180046b38  call    ?SetACL@CSrSettings@SrSettings@@AEAAJPEBG@Z; SrSettings::CSrSettings::SetACL(ushort const *)
0x180046b3d  mov     edi, eax
0x180046b3f  test    eax, eax
0x180046b41  jns     short loc_180046B5C
0x180046b43  lea     r8, aFailedToSetAcl; "Failed to set ACL on backup settings fi"...
0x180046b4a  mov     r9d, edi
0x180046b4d  mov     edx, 2
0x180046b52  mov     rcx, rbx
0x180046b55  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180046b5a  mov     eax, edi
0x180046b5c  mov     rbx, [rsp+28h+arg_0]
0x180046b61  add     rsp, 20h
0x180046b65  pop     rdi
0x180046b66  retn
```
