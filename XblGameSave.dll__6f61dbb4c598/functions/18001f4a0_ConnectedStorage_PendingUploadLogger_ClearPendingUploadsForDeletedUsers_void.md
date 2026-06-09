# ConnectedStorage::PendingUploadLogger::ClearPendingUploadsForDeletedUsers(void)

- ea: `0x18001f4a0`
- end: `0x18001f5ab`
- name: `?ClearPendingUploadsForDeletedUsers@PendingUploadLogger@ConnectedStorage@@SAXXZ`
- size: `267`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180034734`

## callees

- `0x180003c70`
- `0x18000ab18`
- `0x180015f7c`
- `0x18001ef04`
- `0x18001f248`
- `0x18001f4a0`
- `0x18001f8dc`
- `0x18001fa2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001f569`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001f569`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001f504`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001f504`

## string_xrefs

- `0x18001f51c`: `PendingUploadLogger::ClearPendingUploadsForDeletedUsers`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void ConnectedStorage::PendingUploadLogger::ClearPendingUploadsForDeletedUsers(void)
{
  DWORD v0; // edi
  DWORD i; // edx
  int v2; // eax
  const unsigned __int16 *v3; // r8
  const unsigned __int16 *v4; // rdx
  DWORD cchName; // [rsp+40h] [rbp-238h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-230h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-228h] BYREF

  ConnectedStorage::GetRootKey(&hKey);
  if ( !hKey )
    goto LABEL_14;
  v0 = 0;
  for ( i = 0; ; i = v0 )
  {
    cchName = 260;
    if ( RegEnumKeyExW(hKey, i, SubKey, &cchName, 0, 0, 0, 0) )
      break;
    if ( !ConnectedStorage::CheckIfSidExists((ConnectedStorage *)SubKey, v4) )
    {
      v2 = RegDeleteTreeW(hKey, SubKey);
      if ( !v2 )
      {
        v0 = 0;
        continue;
      }
      if ( v2 > 0 )
        v2 = (unsigned __int16)v2 | 0x80070000;
      ConnectedStorage::ReportErrorNoThrow(
        (ConnectedStorage *)(unsigned int)v2,
        (int)L"PendingUploadLogger::ClearPendingUploadsForDeletedUsers",
        v3);
    }
    ++v0;
  }
  if ( !ConnectedStorage::PendingUploadLogger::HasPendingUploads() )
    ConnectedStorage::ChangeServiceStart(0);
LABEL_14:
  ConnectedStorage::HKey::Release((ConnectedStorage::HKey *)&hKey);
}

```

## disassembly

```asm
0x18001f4a0  push    rdi
0x18001f4a2  sub     rsp, 270h
0x18001f4a9  mov     rax, cs:__security_cookie
0x18001f4b0  xor     rax, rsp
0x18001f4b3  mov     [rsp+278h+var_18], rax
0x18001f4bb  lea     rcx, [rsp+278h+hKey]
0x18001f4c0  call    ?GetRootKey@ConnectedStorage@@YA?AVHKey@1@XZ; ConnectedStorage::GetRootKey(void)
0x18001f4c5  nop
0x18001f4c6  cmp     [rsp+278h+hKey], 0
0x18001f4cc  jz      loc_18001F588
0x18001f4d2  xor     edi, edi
0x18001f4d4  mov     [rsp+278h+lpftLastWriteTime], rdi
0x18001f4d9  mov     [rsp+278h+lpcchClass], rdi
0x18001f4de  mov     [rsp+278h+lpClass], rdi
0x18001f4e3  mov     [rsp+278h+lpReserved], rdi
0x18001f4e8  xor     edx, edx
0x18001f4ea  jmp     short loc_18001F552
0x18001f4ec  lea     rcx, [rsp+278h+SubKey]; this
0x18001f4f1  call    ?CheckIfSidExists@ConnectedStorage@@YA_NPEBG@Z; ConnectedStorage::CheckIfSidExists(ushort const *)
0x18001f4f6  test    al, al
0x18001f4f8  jnz     short loc_18001F52A
0x18001f4fa  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x18001f4ff  mov     rcx, [rsp+278h+hKey]; hKey
0x18001f504  call    cs:__imp_RegDeleteTreeW
0x18001f50a  test    eax, eax
0x18001f50c  jnz     short loc_18001F512
0x18001f50e  xor     edi, edi
0x18001f510  jmp     short loc_18001F52C
0x18001f512  jle     short loc_18001F51C
0x18001f514  movzx   eax, ax
0x18001f517  or      eax, 80070000h
0x18001f51c  lea     rdx, aPendinguploadl; "PendingUploadLogger::ClearPendingUpload"...
0x18001f523  mov     ecx, eax; this
0x18001f525  call    ?ReportErrorNoThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorNoThrow(long,ushort const *)
0x18001f52a  inc     edi
0x18001f52c  mov     [rsp+278h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18001f535  mov     [rsp+278h+lpcchClass], 0; lpcchClass
0x18001f53e  mov     [rsp+278h+lpClass], 0; lpClass
0x18001f547  mov     [rsp+278h+lpReserved], 0; lpReserved
0x18001f550  mov     edx, edi; dwIndex
0x18001f552  mov     [rsp+278h+cchName], 104h
0x18001f55a  lea     r9, [rsp+278h+cchName]; lpcchName
0x18001f55f  lea     r8, [rsp+278h+SubKey]; lpName
0x18001f564  mov     rcx, [rsp+278h+hKey]; hKey
0x18001f569  call    cs:__imp_RegEnumKeyExW
0x18001f56f  test    eax, eax
0x18001f571  jz      loc_18001F4EC
0x18001f577  call    ?HasPendingUploads@PendingUploadLogger@ConnectedStorage@@SA_NXZ; ConnectedStorage::PendingUploadLogger::HasPendingUploads(void)
0x18001f57c  test    al, al
0x18001f57e  jnz     short loc_18001F588
0x18001f580  xor     ecx, ecx; this
0x18001f582  call    ?ChangeServiceStart@ConnectedStorage@@YAX_N@Z; ConnectedStorage::ChangeServiceStart(bool)
0x18001f587  nop
0x18001f588  lea     rcx, [rsp+278h+hKey]; this
0x18001f58d  call    ?Release@HKey@ConnectedStorage@@QEAAXXZ; ConnectedStorage::HKey::Release(void)
0x18001f592  mov     rcx, [rsp+278h+var_18]
0x18001f59a  xor     rcx, rsp; StackCookie
0x18001f59d  call    __security_check_cookie
0x18001f5a2  add     rsp, 270h
0x18001f5a9  pop     rdi
0x18001f5aa  retn
```
