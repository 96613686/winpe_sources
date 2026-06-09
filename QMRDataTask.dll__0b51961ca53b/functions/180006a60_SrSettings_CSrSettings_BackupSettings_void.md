# SrSettings::CSrSettings::BackupSettings(void)

- ea: `0x180006a60`
- end: `0x180006be7`
- name: `?BackupSettings@CSrSettings@SrSettings@@UEAAJXZ`
- size: `391`
- prototype: `__int64 __fastcall(SrSettings::CSrSettings *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config`

## callees

- `0x180006a60`
- `0x18000e074`
- `0x180010a0c`
- `0x1800128a0`
- `0x180012d7c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006ae0`
- `KERNEL32!GetLastError` at `0x180006b4b`
- `KERNEL32!GetLastError` at `0x180006b93`
- `KERNEL32!GetLastError` at `0x180006ae0`
- `KERNEL32!GetLastError` at `0x180006b4b`
- `KERNEL32!GetLastError` at `0x180006b93`
- `KERNEL32!CopyFileW` at `0x180006b89`
- `KERNEL32!CopyFileW` at `0x180006b89`
- `KERNEL32!DeleteFileW` at `0x180006b41`
- `KERNEL32!DeleteFileW` at `0x180006b41`

## string_xrefs

- `0x180006a9b`: `No backup path, WinRE must be disabled, cannot backup settings`
- `0x180006ac2`: `Delete existing backup file`
- `0x180006ae6`: `Failed to delete existing backup file. Err = %lu`
- `0x180006b2c`: `Delete backup settings file %s`
- `0x180006b60`: `Failed to delete backup settings file. Error: 0x%08x`
- `0x180006bc3`: `Failed to set ACL on backup settings file. Error: 0x%08x`

## pseudocode

```c
__int64 __fastcall SrSettings::CSrSettings::BackupSettings(SrSettings::CSrSettings *this)
{
  __int64 result; // rax
  DWORD LastError; // eax
  signed int v4; // eax
  unsigned int v5; // edi
  signed int v6; // eax

  if ( *((_BYTE *)this + 3944) )
  {
    SrSettings::CSrSettings::Trace(this, 2, L"Cannot backup settings in UseInWinRE mode");
    return 2147942405LL;
  }
  if ( *((_QWORD *)this + 9) == *((_QWORD *)this + 10) )
  {
    SrSettings::CSrSettings::Trace(this, 2, L"No backup path, WinRE must be disabled, cannot backup settings");
    return 2147942450LL;
  }
  if ( (unsigned int)((__int64 (*)(void))FileExists)() )
  {
    SrSettings::CSrSettings::Trace(this, 0, L"Delete existing backup file");
    if ( !DeleteFileEx2(*((_QWORD *)this + 9)) )
    {
      LastError = GetLastError();
      SrSettings::CSrSettings::Trace(this, 1, L"Failed to delete existing backup file. Err = %lu", LastError);
    }
  }
  if ( (unsigned int)FileExists(*((_QWORD *)this + 5))
    || (SrSettings::CSrSettings::Trace(this, 0, L"Settings file not found"),
        !(unsigned int)FileExists(*((_QWORD *)this + 9)))
    || (SrSettings::CSrSettings::Trace(this, 0, L"Delete backup settings file %s", *((_QWORD *)this + 9)),
        DeleteFileW(*((LPCWSTR *)this + 9))) )
  {
    SrSettings::CSrSettings::Trace(this, 0, L"Backup settings to %s", *((_QWORD *)this + 9));
    if ( CopyFileW(*((LPCWSTR *)this + 5), *((LPCWSTR *)this + 9), 0) )
    {
      result = SrSettings::CSrSettings::SetACL(this, *((LPCWSTR *)this + 9));
      v5 = result;
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
      v6 = GetLastError();
      v5 = v6;
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      SrSettings::CSrSettings::Trace(this, 2, L"Failed to backup settings. Error: 0x%08x", v5);
    }
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    SrSettings::CSrSettings::Trace(this, 2, L"Failed to delete backup settings file. Error: 0x%08x", v5);
  }
  return v5;
}

```

## disassembly

```asm
0x180006a60  mov     [rsp+arg_0], rbx
0x180006a65  push    rdi
0x180006a66  sub     rsp, 20h
0x180006a6a  cmp     byte ptr [rcx+0F68h], 0
0x180006a71  mov     rbx, rcx
0x180006a74  jz      short loc_180006A91
0x180006a76  lea     r8, aCannotBackupSe; "Cannot backup settings in UseInWinRE mo"...
0x180006a7d  mov     edx, 2
0x180006a82  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180006a87  mov     eax, 80070005h
0x180006a8c  jmp     loc_180006BDC
0x180006a91  mov     rcx, [rcx+48h]
0x180006a95  cmp     rcx, [rbx+50h]
0x180006a99  jnz     short loc_180006AB9
0x180006a9b  lea     r8, aNoBackupPathWi; "No backup path, WinRE must be disabled,"...
0x180006aa2  mov     edx, 2
0x180006aa7  mov     rcx, rbx
0x180006aaa  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180006aaf  mov     eax, 80070032h
0x180006ab4  jmp     loc_180006BDC
0x180006ab9  call    FileExists
0x180006abe  test    eax, eax
0x180006ac0  jz      short loc_180006AFD
0x180006ac2  lea     r8, aDeleteExisting; "Delete existing backup file"
0x180006ac9  xor     edx, edx
0x180006acb  mov     rcx, rbx
0x180006ace  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180006ad3  mov     rcx, [rbx+48h]
0x180006ad7  call    DeleteFileEx2
0x180006adc  test    eax, eax
0x180006ade  jnz     short loc_180006AFD
0x180006ae0  call    cs:__imp_GetLastError
0x180006ae6  lea     r8, aFailedToDelete_1; "Failed to delete existing backup file. "...
0x180006aed  mov     edx, 1
0x180006af2  mov     r9d, eax
0x180006af5  mov     rcx, rbx
0x180006af8  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180006afd  mov     rcx, [rbx+28h]
0x180006b01  call    FileExists
0x180006b06  test    eax, eax
0x180006b08  jnz     short loc_180006B69
0x180006b0a  lea     r8, aSettingsFileNo; "Settings file not found"
0x180006b11  xor     edx, edx
0x180006b13  mov     rcx, rbx
0x180006b16  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180006b1b  mov     rcx, [rbx+48h]
0x180006b1f  call    FileExists
0x180006b24  test    eax, eax
0x180006b26  jz      short loc_180006B69
0x180006b28  mov     r9, [rbx+48h]
0x180006b2c  lea     r8, aDeleteBackupSe; "Delete backup settings file %s"
0x180006b33  xor     edx, edx
0x180006b35  mov     rcx, rbx
0x180006b38  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180006b3d  mov     rcx, [rbx+48h]; lpFileName
0x180006b41  call    cs:__imp_DeleteFileW
0x180006b47  test    eax, eax
0x180006b49  jnz     short loc_180006B69
0x180006b4b  call    cs:__imp_GetLastError
0x180006b51  mov     edi, eax
0x180006b53  test    eax, eax
0x180006b55  jle     short loc_180006B60
0x180006b57  movzx   edi, ax
0x180006b5a  or      edi, 80070000h
0x180006b60  lea     r8, aFailedToDelete; "Failed to delete backup settings file. "...
0x180006b67  jmp     short loc_180006BCA
0x180006b69  mov     r9, [rbx+48h]
0x180006b6d  lea     r8, aBackupSettings; "Backup settings to %s"
0x180006b74  xor     edx, edx
0x180006b76  mov     rcx, rbx
0x180006b79  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180006b7e  mov     rdx, [rbx+48h]; lpNewFileName
0x180006b82  xor     r8d, r8d; bFailIfExists
0x180006b85  mov     rcx, [rbx+28h]; lpExistingFileName
0x180006b89  call    cs:__imp_CopyFileW
0x180006b8f  test    eax, eax
0x180006b91  jnz     short loc_180006BB1
0x180006b93  call    cs:__imp_GetLastError
0x180006b99  mov     edi, eax
0x180006b9b  test    eax, eax
0x180006b9d  jle     short loc_180006BA8
0x180006b9f  movzx   edi, ax
0x180006ba2  or      edi, 80070000h
0x180006ba8  lea     r8, aFailedToBackup; "Failed to backup settings. Error: 0x%08"...
0x180006baf  jmp     short loc_180006BCA
0x180006bb1  mov     rdx, [rbx+48h]; lpFileName
0x180006bb5  mov     rcx, rbx; this
0x180006bb8  call    ?SetACL@CSrSettings@SrSettings@@AEAAJPEBG@Z; SrSettings::CSrSettings::SetACL(ushort const *)
0x180006bbd  mov     edi, eax
0x180006bbf  test    eax, eax
0x180006bc1  jns     short loc_180006BDC
0x180006bc3  lea     r8, aFailedToSetAcl; "Failed to set ACL on backup settings fi"...
0x180006bca  mov     r9d, edi
0x180006bcd  mov     edx, 2
0x180006bd2  mov     rcx, rbx
0x180006bd5  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180006bda  mov     eax, edi
0x180006bdc  mov     rbx, [rsp+28h+arg_0]
0x180006be1  add     rsp, 20h
0x180006be5  pop     rdi
0x180006be6  retn
```
