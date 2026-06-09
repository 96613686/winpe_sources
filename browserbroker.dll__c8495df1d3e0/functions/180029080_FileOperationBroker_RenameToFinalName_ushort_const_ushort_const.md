# FileOperationBroker::RenameToFinalName(ushort const *,ushort const *)

- ea: `0x180029080`
- end: `0x1800290ee`
- name: `?RenameToFinalName@FileOperationBroker@@UEAAJPEBG0@Z`
- size: `110`
- prototype: `__int64 __fastcall(FileOperationBroker *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000e428`
- `0x180029080`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800290c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800290c7`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800290bd`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800290bd`

## pseudocode

```c
__int64 __fastcall FileOperationBroker::RenameToFinalName(
        FileOperationBroker *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int PIC; // ebx
  signed int LastError; // eax
  unsigned int v8; // [rsp+48h] [rbp+20h] BYREF

  v8 = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, &v8);
  if ( PIC >= 0 && !MoveFileExW(a2, a3, 1u) )
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
0x180029080  mov     rax, rsp
0x180029083  mov     [rax+8], rbx
0x180029087  mov     [rax+10h], rsi
0x18002908b  push    rdi
0x18002908c  sub     rsp, 20h
0x180029090  mov     rsi, rdx
0x180029093  mov     dword ptr [rax+20h], 0
0x18002909a  lea     rdx, [rax+20h]; unsigned int *
0x18002909e  mov     ecx, 1; unsigned int
0x1800290a3  mov     rdi, r8
0x1800290a6  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x1800290ab  mov     ebx, eax
0x1800290ad  test    eax, eax
0x1800290af  js      short loc_1800290DC
0x1800290b1  mov     r8d, 1; dwFlags
0x1800290b7  mov     rdx, rdi; lpNewFileName
0x1800290ba  mov     rcx, rsi; lpExistingFileName
0x1800290bd  call    cs:__imp_MoveFileExW
0x1800290c3  test    eax, eax
0x1800290c5  jnz     short loc_1800290DC
0x1800290c7  call    cs:__imp_GetLastError
0x1800290cd  mov     ebx, eax
0x1800290cf  test    eax, eax
0x1800290d1  jle     short loc_1800290DC
0x1800290d3  movzx   ebx, ax
0x1800290d6  or      ebx, 80070000h
0x1800290dc  mov     rsi, [rsp+28h+arg_8]
0x1800290e1  mov     eax, ebx
0x1800290e3  mov     rbx, [rsp+28h+arg_0]
0x1800290e8  add     rsp, 20h
0x1800290ec  pop     rdi
0x1800290ed  retn
```
