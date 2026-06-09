# FileOperationBroker::GetBackupStorageFolder(IUnknown * *)

- ea: `0x1800280a0`
- end: `0x1800281ef`
- name: `?GetBackupStorageFolder@FileOperationBroker@@UEAAJPEAPEAUIUnknown@@@Z`
- size: `335`
- prototype: `__int64 __fastcall(FileOperationBroker *__hidden this, struct IUnknown **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, reparse_path, broker_com_uri`

## callees

- `0x180002ce0`
- `0x18000e428`
- `0x1800280a0`
- `0x180028a30`
- `0x180028be0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002813a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002819b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800281a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002813a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002819b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800281a8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180028130`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180028191`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180028130`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180028191`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180028169`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180028169`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002811b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180028180`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002811b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180028180`

## pseudocode

```c
int __fastcall FileOperationBroker::GetBackupStorageFolder(FileOperationBroker *this, struct IUnknown **a2)
{
  int result; // eax
  FileOperationBroker *v5; // rcx
  bool v6; // sf
  bool v7; // sf
  unsigned int v8[4]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR pszPath[264]; // [rsp+30h] [rbp-228h] BYREF

  *a2 = 0;
  v8[0] = 0;
  result = BrokerAuthenticateAttachedCallerGetPIC(1, v8);
  if ( result < 0 )
    return result;
  v8[0] = 260;
  result = FileOperationBroker::GetUserProfilePath(v5, pszPath, v8);
  if ( result < 0 )
    return result;
  result = PathCchAppend(pszPath, 0x104u, L"MicrosoftEdgeBackups");
  if ( result < 0 )
    return result;
  if ( CreateDirectoryW(pszPath, 0) )
  {
    SetFileAttributesW(pszPath, 2u);
LABEL_11:
    result = PathCchAppend(pszPath, 0x104u, L"backups");
    if ( result >= 0 )
    {
      if ( CreateDirectoryW(pszPath, 0) || GetLastError() == 183 )
        return FileOperationBroker::GetStorageFolder(this, pszPath, a2);
      result = GetLastError();
      v7 = result < 0;
      if ( result > 0 )
      {
        result = (unsigned __int16)result | 0x80070000;
        v7 = result < 0;
      }
      if ( !v7 )
        return FileOperationBroker::GetStorageFolder(this, pszPath, a2);
    }
    return result;
  }
  if ( GetLastError() == 183 )
    goto LABEL_11;
  result = GetLastError();
  v6 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v6 = result < 0;
  }
  if ( !v6 )
    goto LABEL_11;
  return result;
}

```

## disassembly

```asm
0x1800280a0  mov     [rsp+arg_0], rbx
0x1800280a5  push    rdi
0x1800280a6  sub     rsp, 250h
0x1800280ad  mov     rax, cs:__security_cookie
0x1800280b4  xor     rax, rsp
0x1800280b7  mov     [rsp+258h+var_18], rax
0x1800280bf  mov     rbx, rdx
0x1800280c2  mov     qword ptr [rdx], 0
0x1800280c9  mov     rdi, rcx
0x1800280cc  mov     [rsp+258h+var_238], 0
0x1800280d4  lea     rdx, [rsp+258h+var_238]; unsigned int *
0x1800280d9  mov     ecx, 1; unsigned int
0x1800280de  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x1800280e3  test    eax, eax
0x1800280e5  js      loc_1800281CE
0x1800280eb  lea     r8, [rsp+258h+var_238]; unsigned int *
0x1800280f0  mov     [rsp+258h+var_238], 104h
0x1800280f8  lea     rdx, [rsp+258h+pszPath]; unsigned __int16 *
0x1800280fd  call    ?GetUserProfilePath@FileOperationBroker@@AEAAJPEAGPEAK@Z; FileOperationBroker::GetUserProfilePath(ushort *,ulong *)
0x180028102  test    eax, eax
0x180028104  js      loc_1800281CE
0x18002810a  lea     r8, aMicrosoftedgeb_0; "MicrosoftEdgeBackups"
0x180028111  mov     edx, 104h; cchPath
0x180028116  lea     rcx, [rsp+258h+pszPath]; pszPath
0x18002811b  call    cs:__imp_PathCchAppend
0x180028121  test    eax, eax
0x180028123  js      loc_1800281CE
0x180028129  xor     edx, edx; lpSecurityAttributes
0x18002812b  lea     rcx, [rsp+258h+pszPath]; lpPathName
0x180028130  call    cs:__imp_CreateDirectoryW
0x180028136  test    eax, eax
0x180028138  jnz     short loc_18002815F
0x18002813a  call    cs:__imp_GetLastError
0x180028140  cmp     eax, 0B7h
0x180028145  jz      short loc_18002816F
0x180028147  call    cs:__imp_GetLastError
0x18002814d  test    eax, eax
0x18002814f  jle     short loc_18002815B
0x180028151  movzx   eax, ax
0x180028154  or      eax, 80070000h
0x180028159  test    eax, eax
0x18002815b  jns     short loc_18002816F
0x18002815d  jmp     short loc_1800281CE
0x18002815f  mov     edx, 2; dwFileAttributes
0x180028164  lea     rcx, [rsp+258h+pszPath]; lpFileName
0x180028169  call    cs:__imp_SetFileAttributesW
0x18002816f  lea     r8, aBackups; "backups"
0x180028176  mov     edx, 104h; cchPath
0x18002817b  lea     rcx, [rsp+258h+pszPath]; pszPath
0x180028180  call    cs:__imp_PathCchAppend
0x180028186  test    eax, eax
0x180028188  js      short loc_1800281CE
0x18002818a  xor     edx, edx; lpSecurityAttributes
0x18002818c  lea     rcx, [rsp+258h+pszPath]; lpPathName
0x180028191  call    cs:__imp_CreateDirectoryW
0x180028197  test    eax, eax
0x180028199  jnz     short loc_1800281BE
0x18002819b  call    cs:__imp_GetLastError
0x1800281a1  cmp     eax, 0B7h
0x1800281a6  jz      short loc_1800281BE
0x1800281a8  call    cs:__imp_GetLastError
0x1800281ae  test    eax, eax
0x1800281b0  jle     short loc_1800281BC
0x1800281b2  movzx   eax, ax
0x1800281b5  or      eax, 80070000h
0x1800281ba  test    eax, eax
0x1800281bc  js      short loc_1800281CE
0x1800281be  mov     r8, rbx; struct IUnknown **
0x1800281c1  lea     rdx, [rsp+258h+pszPath]; unsigned __int16 *
0x1800281c6  mov     rcx, rdi; this
0x1800281c9  call    ?GetStorageFolder@FileOperationBroker@@UEAAJPEBGPEAPEAUIUnknown@@@Z; FileOperationBroker::GetStorageFolder(ushort const *,IUnknown * *)
0x1800281ce  mov     rcx, [rsp+258h+var_18]
0x1800281d6  xor     rcx, rsp; StackCookie
0x1800281d9  call    __security_check_cookie
0x1800281de  mov     rbx, [rsp+258h+arg_0]
0x1800281e6  add     rsp, 250h
0x1800281ed  pop     rdi
0x1800281ee  retn
```
