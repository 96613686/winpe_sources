# FileOperationBroker::DeleteDownloadedFile(ushort const *)

- ea: `0x180027c40`
- end: `0x180027c99`
- name: `?DeleteDownloadedFile@FileOperationBroker@@UEAAJPEBG@Z`
- size: `89`
- prototype: `__int64 __fastcall(FileOperationBroker *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000e428`
- `0x180027c40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c77`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180027c6d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180027c6d`

## pseudocode

```c
__int64 __fastcall FileOperationBroker::DeleteDownloadedFile(FileOperationBroker *this, const unsigned __int16 *a2)
{
  int PIC; // ebx
  signed int LastError; // eax
  unsigned int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, &v6);
  if ( PIC >= 0 && !DeleteFileW(a2) )
  {
    LastError = GetLastError();
    PIC = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180027c40  mov     [rsp+arg_0], rbx
0x180027c45  push    rdi
0x180027c46  sub     rsp, 20h
0x180027c4a  mov     rdi, rdx
0x180027c4d  mov     [rsp+28h+arg_10], 0
0x180027c55  lea     rdx, [rsp+28h+arg_10]; unsigned int *
0x180027c5a  mov     ecx, 1; unsigned int
0x180027c5f  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180027c64  mov     ebx, eax
0x180027c66  test    eax, eax
0x180027c68  js      short loc_180027C8C
0x180027c6a  mov     rcx, rdi; lpFileName
0x180027c6d  call    cs:__imp_DeleteFileW
0x180027c73  test    eax, eax
0x180027c75  jnz     short loc_180027C8C
0x180027c77  call    cs:__imp_GetLastError
0x180027c7d  mov     ebx, eax
0x180027c7f  test    eax, eax
0x180027c81  jle     short loc_180027C8C
0x180027c83  movzx   ebx, ax
0x180027c86  or      ebx, 80070000h
0x180027c8c  mov     eax, ebx
0x180027c8e  mov     rbx, [rsp+28h+arg_0]
0x180027c93  add     rsp, 20h
0x180027c97  pop     rdi
0x180027c98  retn
```
