# FileOperationBroker::EnsurePath(ushort const *)

- ea: `0x180027e50`
- end: `0x180027ebe`
- name: `?EnsurePath@FileOperationBroker@@UEAAJPEBG@Z`
- size: `110`
- prototype: `int(FileOperationBroker *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e428`
- `0x180027e50`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x180027e82`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x180027e82`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x180027e94`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x180027e94`

## pseudocode

```c
__int64 __fastcall FileOperationBroker::EnsurePath(FileOperationBroker *this, const unsigned __int16 *a2)
{
  int PIC; // ebx
  int v4; // eax
  int v5; // eax
  unsigned int v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, &v7);
  if ( PIC >= 0 )
  {
    PIC = 1;
    if ( !PathIsRootW(a2) )
    {
      v4 = SHCreateDirectoryExW(0, a2, 0);
      if ( v4 && (v5 = v4 - 80) != 0 && v5 != 103 )
        return (unsigned int)-2147467259;
      else
        return 0;
    }
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180027e50  mov     [rsp+arg_0], rbx
0x180027e55  push    rdi
0x180027e56  sub     rsp, 20h
0x180027e5a  mov     rdi, rdx
0x180027e5d  mov     [rsp+28h+arg_10], 0
0x180027e65  lea     rdx, [rsp+28h+arg_10]; unsigned int *
0x180027e6a  mov     ecx, 1; unsigned int
0x180027e6f  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180027e74  mov     ebx, eax
0x180027e76  test    eax, eax
0x180027e78  js      short loc_180027EB1
0x180027e7a  mov     rcx, rdi; pszPath
0x180027e7d  mov     ebx, 1
0x180027e82  call    cs:__imp_PathIsRootW
0x180027e88  test    eax, eax
0x180027e8a  jnz     short loc_180027EB1
0x180027e8c  xor     r8d, r8d; psa
0x180027e8f  mov     rdx, rdi; pszPath
0x180027e92  xor     ecx, ecx; hwnd
0x180027e94  call    cs:__imp_SHCreateDirectoryExW
0x180027e9a  test    eax, eax
0x180027e9c  jz      short loc_180027EAF
0x180027e9e  sub     eax, 50h ; 'P'
0x180027ea1  jz      short loc_180027EAF
0x180027ea3  cmp     eax, 67h ; 'g'
0x180027ea6  jz      short loc_180027EAF
0x180027ea8  mov     ebx, 80004005h
0x180027ead  jmp     short loc_180027EB1
0x180027eaf  xor     ebx, ebx
0x180027eb1  mov     eax, ebx
0x180027eb3  mov     rbx, [rsp+28h+arg_0]
0x180027eb8  add     rsp, 20h
0x180027ebc  pop     rdi
0x180027ebd  retn
```
