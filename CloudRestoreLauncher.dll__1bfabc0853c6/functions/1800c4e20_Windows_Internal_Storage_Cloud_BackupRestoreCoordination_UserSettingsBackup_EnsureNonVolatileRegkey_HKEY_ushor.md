# Windows::Internal::Storage::Cloud::BackupRestoreCoordination::UserSettingsBackup::EnsureNonVolatileRegkey(HKEY__ *,ushort const *)

- ea: `0x1800c4e20`
- end: `0x1800c4ea2`
- name: `?EnsureNonVolatileRegkey@UserSettingsBackup@BackupRestoreCoordination@Cloud@Storage@Internal@Windows@@YAXPEAUHKEY__@@PEBG@Z`
- size: `130`
- prototype: `void __fastcall(Windows::Internal::Storage::Cloud::BackupRestoreCoordination::UserSettingsBackup *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800c57e0`

## callees

- `0x18002498c`
- `0x1800821ac`
- `0x1800c4e20`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x1800c4e70`
- `ADVAPI32!RegCreateKeyExW` at `0x1800c4e70`

## string_xrefs

- `0x1800c4e7f`: `pcshell\shell\cloudrestorelauncher\cloudbackuprestore\manifestdrivenbackuprestorehandler.cpp`

## pseudocode

```c
void __fastcall Windows::Internal::Storage::Cloud::BackupRestoreCoordination::UserSettingsBackup::EnsureNonVolatileRegkey(
        Windows::Internal::Storage::Cloud::BackupRestoreCoordination::UserSettingsBackup *this,
        const WCHAR *a2,
        const unsigned __int16 *a3)
{
  unsigned int v3; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD v6; // [rsp+60h] [rbp+8h] BYREF
  int v7; // [rsp+64h] [rbp+Ch]
  HKEY v8; // [rsp+70h] [rbp+18h] BYREF

  v7 = HIDWORD(this);
  v6 = 0;
  v8 = 0;
  v3 = RegCreateKeyExW(HKEY_CURRENT_USER, a2, 0, 0, 0, 0xF003Fu, 0, &v8, &v6);
  if ( v3 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x128,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\manifestdrivenbackuprestorehandler.cpp",
      (const char *)v3,
      dwOptions);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v8);
}

```

## disassembly

```asm
0x1800c4e20  mov     r11, rsp
0x1800c4e23  mov     [r11+8], rcx
0x1800c4e27  sub     rsp, 58h
0x1800c4e2b  lea     rax, [r11+8]
0x1800c4e2f  mov     [rsp+58h+arg_0], 0
0x1800c4e37  mov     [r11-18h], rax
0x1800c4e3b  xor     r9d, r9d; lpClass
0x1800c4e3e  lea     rax, [r11+18h]
0x1800c4e42  mov     qword ptr [r11+18h], 0
0x1800c4e4a  mov     [r11-20h], rax
0x1800c4e4e  xor     r8d, r8d; Reserved
0x1800c4e51  mov     qword ptr [r11-28h], 0
0x1800c4e59  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800c4e60  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x1800c4e68  mov     [rsp+58h+dwOptions], 0; unsigned int
0x1800c4e70  call    cs:__imp_RegCreateKeyExW
0x1800c4e76  test    eax, eax
0x1800c4e78  jz      short loc_1800C4E93
0x1800c4e7a  mov     rcx, [rsp+58h]; this
0x1800c4e7f  lea     r8, aPcshellShellCl_3; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800c4e86  mov     r9d, eax; char *
0x1800c4e89  mov     edx, 128h; void *
0x1800c4e8e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800c4e93  lea     rcx, [rsp+58h+arg_10]
0x1800c4e98  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c4e9d  add     rsp, 58h
0x1800c4ea1  retn
```
