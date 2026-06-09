# FileOperationBroker::DoesBackupFolderExist(void)

- ea: `0x180027cc0`
- end: `0x180027d70`
- name: `?DoesBackupFolderExist@FileOperationBroker@@UEAAJXZ`
- size: `176`
- prototype: `__int64 __fastcall(FileOperationBroker *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180002ce0`
- `0x18000e428`
- `0x180027cc0`
- `0x180027d80`
- `0x180028be0`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180027d25`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180027d40`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180027d25`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180027d40`

## pseudocode

```c
int __fastcall FileOperationBroker::DoesBackupFolderExist(FileOperationBroker *this)
{
  int result; // eax
  FileOperationBroker *v3; // rcx
  unsigned int v4[4]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR pszPath[264]; // [rsp+30h] [rbp-228h] BYREF

  v4[0] = 0;
  result = BrokerAuthenticateAttachedCallerGetPIC(1, v4);
  if ( result >= 0 )
  {
    v4[0] = 260;
    result = FileOperationBroker::GetUserProfilePath(v3, pszPath, v4);
    if ( result >= 0 )
    {
      result = PathCchAppend(pszPath, 0x104u, L"MicrosoftEdgeBackups");
      if ( result >= 0 )
      {
        result = PathCchAppend(pszPath, 0x104u, L"backups");
        if ( result >= 0 )
          return FileOperationBroker::DoesFolderExist(this, pszPath);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180027cc0  push    rbx
0x180027cc2  sub     rsp, 250h
0x180027cc9  mov     rax, cs:__security_cookie
0x180027cd0  xor     rax, rsp
0x180027cd3  mov     [rsp+258h+var_18], rax
0x180027cdb  mov     rbx, rcx
0x180027cde  mov     [rsp+258h+var_238], 0
0x180027ce6  mov     ecx, 1; unsigned int
0x180027ceb  lea     rdx, [rsp+258h+var_238]; unsigned int *
0x180027cf0  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180027cf5  test    eax, eax
0x180027cf7  js      short loc_180027D57
0x180027cf9  lea     r8, [rsp+258h+var_238]; unsigned int *
0x180027cfe  mov     [rsp+258h+var_238], 104h
0x180027d06  lea     rdx, [rsp+258h+pszPath]; unsigned __int16 *
0x180027d0b  call    ?GetUserProfilePath@FileOperationBroker@@AEAAJPEAGPEAK@Z; FileOperationBroker::GetUserProfilePath(ushort *,ulong *)
0x180027d10  test    eax, eax
0x180027d12  js      short loc_180027D57
0x180027d14  lea     r8, aMicrosoftedgeb_0; "MicrosoftEdgeBackups"
0x180027d1b  mov     edx, 104h; cchPath
0x180027d20  lea     rcx, [rsp+258h+pszPath]; pszPath
0x180027d25  call    cs:__imp_PathCchAppend
0x180027d2b  test    eax, eax
0x180027d2d  js      short loc_180027D57
0x180027d2f  lea     r8, aBackups; "backups"
0x180027d36  mov     edx, 104h; cchPath
0x180027d3b  lea     rcx, [rsp+258h+pszPath]; pszPath
0x180027d40  call    cs:__imp_PathCchAppend
0x180027d46  test    eax, eax
0x180027d48  js      short loc_180027D57
0x180027d4a  lea     rdx, [rsp+258h+pszPath]; unsigned __int16 *
0x180027d4f  mov     rcx, rbx; this
0x180027d52  call    ?DoesFolderExist@FileOperationBroker@@UEAAJPEBG@Z; FileOperationBroker::DoesFolderExist(ushort const *)
0x180027d57  mov     rcx, [rsp+258h+var_18]
0x180027d5f  xor     rcx, rsp; StackCookie
0x180027d62  call    __security_check_cookie
0x180027d67  add     rsp, 250h
0x180027d6e  pop     rbx
0x180027d6f  retn
```
