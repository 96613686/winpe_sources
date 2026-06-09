# winreDeleteBackupSettingFile

- ea: `0x1800296ec`
- end: `0x1800297c5`
- name: `winreDeleteBackupSettingFile`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18001fd7c`

## callees

- `0x180001f94`
- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x1800296ec`
- `0x180047350`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180029762`
- `KERNEL32!GetLastError` at `0x180029762`
- `KERNEL32!SetLastError` at `0x1800297b2`
- `KERNEL32!SetLastError` at `0x1800297b2`
- `KERNEL32!DeleteFileW` at `0x180029758`
- `KERNEL32!DeleteFileW` at `0x180029758`

## string_xrefs

- `0x180029707`: `Enter winreDeleteBackupSettingFile`
- `0x18002972c`: `Failed to get backup setting file path. Error: 0x%x`
- `0x180029768`: `Failed to delete backup setting file. Error: 0x%x`
- `0x18002979a`: `Exit winreDeleteBackupSettingFile return value: %d, last error: 0x%x`

## pseudocode

```c
__int64 __fastcall winreDeleteBackupSettingFile(__int64 LastError)
{
  unsigned int v1; // esi
  unsigned __int16 **v2; // r8
  int BackupFilePath; // eax
  LPCWSTR lpFileName; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  lpFileName = 0;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter winreDeleteBackupSettingFile");
  BackupFilePath = SrSettings::GetBackupFilePath((SrSettings *)(LastError + 16), (void **)&lpFileName, v2);
  LOWORD(LastError) = BackupFilePath;
  if ( BackupFilePath >= 0 )
  {
    UnattendLogW(0, L"Deleting backup setting file: %s", lpFileName);
    if ( DeleteFileW(lpFileName) )
    {
      LODWORD(LastError) = 0;
      v1 = 1;
    }
    else
    {
      LastError = GetLastError();
      UnattendLogW(1, L"Failed to delete backup setting file. Error: 0x%x", LastError);
    }
  }
  else
  {
    UnattendLogW(1, L"Failed to get backup setting file path. Error: 0x%x", (unsigned int)BackupFilePath);
    LODWORD(LastError) = (unsigned __int16)LastError;
  }
  if ( lpFileName )
    operator delete((void *)lpFileName);
  UnattendLogW(0, L"Exit winreDeleteBackupSettingFile return value: %d, last error: 0x%x", v1, (unsigned int)LastError);
  UnattendFinalizeLog();
  SetLastError(LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800296ec  mov     [rsp+arg_8], rbx
0x1800296f1  push    rsi
0x1800296f2  sub     rsp, 20h
0x1800296f6  mov     rbx, rcx
0x1800296f9  xor     esi, esi
0x1800296fb  xor     ecx, ecx
0x1800296fd  mov     [rsp+28h+lpFileName], rsi
0x180029702  call    UnattendInitializeLogEx2
0x180029707  lea     rdx, aEnterWinredele_0; "Enter winreDeleteBackupSettingFile"
0x18002970e  xor     ecx, ecx
0x180029710  call    UnattendLogW
0x180029715  lea     rcx, [rbx+10h]; this
0x180029719  lea     rdx, [rsp+28h+lpFileName]; unsigned __int16 *
0x18002971e  call    ?GetBackupFilePath@SrSettings@@YAJPEBGPEAPEAG@Z; SrSettings::GetBackupFilePath(ushort const *,ushort * *)
0x180029723  mov     ebx, eax
0x180029725  test    eax, eax
0x180029727  jns     short loc_180029740
0x180029729  mov     r8d, eax
0x18002972c  lea     rdx, aFailedToGetBac; "Failed to get backup setting file path."...
0x180029733  lea     ecx, [rsi+1]
0x180029736  call    UnattendLogW
0x18002973b  movzx   ebx, bx
0x18002973e  jmp     short loc_180029785
0x180029740  mov     r8, [rsp+28h+lpFileName]
0x180029745  lea     rdx, aDeletingBackup; "Deleting backup setting file: %s"
0x18002974c  xor     ecx, ecx
0x18002974e  call    UnattendLogW
0x180029753  mov     rcx, [rsp+28h+lpFileName]; lpFileName
0x180029758  call    cs:__imp_DeleteFileW
0x18002975e  test    eax, eax
0x180029760  jnz     short loc_180029780
0x180029762  call    cs:__imp_GetLastError
0x180029768  lea     rdx, aFailedToDelete_11; "Failed to delete backup setting file. E"...
0x18002976f  mov     ecx, 1
0x180029774  mov     r8d, eax
0x180029777  mov     ebx, eax
0x180029779  call    UnattendLogW
0x18002977e  jmp     short loc_180029785
0x180029780  xor     ebx, ebx
0x180029782  lea     esi, [rbx+1]
0x180029785  cmp     [rsp+28h+lpFileName], 0
0x18002978b  jz      short loc_180029797
0x18002978d  mov     rcx, [rsp+28h+lpFileName]; Block
0x180029792  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029797  mov     r9d, ebx
0x18002979a  lea     rdx, aExitWinredelet_0; "Exit winreDeleteBackupSettingFile retur"...
0x1800297a1  mov     r8d, esi
0x1800297a4  xor     ecx, ecx
0x1800297a6  call    UnattendLogW
0x1800297ab  call    UnattendFinalizeLog
0x1800297b0  mov     ecx, ebx; dwErrCode
0x1800297b2  call    cs:__imp_SetLastError
0x1800297b8  mov     eax, ebx
0x1800297ba  mov     rbx, [rsp+28h+arg_8]
0x1800297bf  add     rsp, 20h
0x1800297c3  pop     rsi
0x1800297c4  retn
```
