# FileOperationBroker::SetReadOnly(ushort const *)

- ea: `0x180029830`
- end: `0x180029883`
- name: `?SetReadOnly@FileOperationBroker@@UEAAJPEBG@Z`
- size: `83`
- prototype: `int(FileOperationBroker *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000e428`
- `0x180029830`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002985d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002985d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180029870`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180029870`

## pseudocode

```c
__int64 __fastcall FileOperationBroker::SetReadOnly(FileOperationBroker *this, const unsigned __int16 *a2)
{
  int PIC; // ebx
  DWORD FileAttributesW; // eax
  unsigned int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, &v6);
  if ( PIC >= 0 )
  {
    FileAttributesW = GetFileAttributesW(a2);
    if ( FileAttributesW != -1 )
      SetFileAttributesW(a2, FileAttributesW | 1);
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180029830  mov     [rsp+arg_0], rbx
0x180029835  push    rdi
0x180029836  sub     rsp, 20h
0x18002983a  mov     rdi, rdx
0x18002983d  mov     [rsp+28h+arg_10], 0
0x180029845  lea     rdx, [rsp+28h+arg_10]; unsigned int *
0x18002984a  mov     ecx, 1; unsigned int
0x18002984f  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180029854  mov     ebx, eax
0x180029856  test    eax, eax
0x180029858  js      short loc_180029876
0x18002985a  mov     rcx, rdi; lpFileName
0x18002985d  call    cs:__imp_GetFileAttributesW
0x180029863  cmp     eax, 0FFFFFFFFh
0x180029866  jz      short loc_180029876
0x180029868  or      eax, 1
0x18002986b  mov     rcx, rdi; lpFileName
0x18002986e  mov     edx, eax; dwFileAttributes
0x180029870  call    cs:__imp_SetFileAttributesW
0x180029876  mov     eax, ebx
0x180029878  mov     rbx, [rsp+28h+arg_0]
0x18002987d  add     rsp, 20h
0x180029881  pop     rdi
0x180029882  retn
```
