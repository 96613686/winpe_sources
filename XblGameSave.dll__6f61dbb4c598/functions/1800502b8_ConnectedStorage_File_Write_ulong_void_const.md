# ConnectedStorage::File::Write(ulong,void const *)

- ea: `0x1800502b8`
- end: `0x180050340`
- name: `?Write@File@ConnectedStorage@@QEAAXKPEBX@Z`
- size: `136`
- prototype: `void __fastcall(ConnectedStorage::File *this, DWORD, const void *)`
- caller_count: `9`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180047250`
- `0x18004a8c8`
- `0x180065a04`
- `0x180065c10`
- `0x180069ee0`
- `0x180072068`
- `0x1800768d8`
- `0x180077e58`
- `0x18007a9b4`

## callees

- `0x18000aae4`
- `0x1800502b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800502fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800502fc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800502e9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800502e9`

## string_xrefs

- `0x18005030e`: `File::Write`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ConnectedStorage::File::Write(ConnectedStorage::File *this, DWORD a2, const void *a3)
{
  const unsigned __int16 *v5; // r8
  signed int LastError; // eax
  const unsigned __int16 *v7; // r8
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  if ( !WriteFile(*(HANDLE *)this, a3, a2, &NumberOfBytesWritten, 0) )
  {
    if ( *((_DWORD *)this + 2) == 1 )
      *((_DWORD *)this + 2) = 0;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)LastError, (int)L"File::Write", v7);
  }
  if ( NumberOfBytesWritten != a2 )
    ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x8000FFFFLL, (int)L"E_UNEXPECTED", v5);
}

```

## disassembly

```asm
0x1800502b8  mov     [rsp+arg_8], rbx
0x1800502bd  push    rdi
0x1800502be  sub     rsp, 30h
0x1800502c2  mov     rax, r8
0x1800502c5  mov     [rsp+38h+NumberOfBytesWritten], 0
0x1800502cd  mov     r8d, edx; nNumberOfBytesToWrite
0x1800502d0  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1800502d9  mov     edi, edx
0x1800502db  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800502e0  mov     rbx, rcx
0x1800502e3  mov     rdx, rax; lpBuffer
0x1800502e6  mov     rcx, [rcx]; hFile
0x1800502e9  call    cs:__imp_WriteFile
0x1800502ef  test    eax, eax
0x1800502f1  jnz     short loc_18005031D
0x1800502f3  cmp     dword ptr [rbx+8], 1
0x1800502f7  jnz     short loc_1800502FC
0x1800502f9  mov     [rbx+8], eax
0x1800502fc  call    cs:__imp_GetLastError
0x180050302  test    eax, eax
0x180050304  jle     short loc_18005030E
0x180050306  movzx   eax, ax
0x180050309  or      eax, 80070000h
0x18005030e  lea     rdx, aFileWrite; "File::Write"
0x180050315  mov     ecx, eax; this
0x180050317  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18005031d  cmp     [rsp+38h+NumberOfBytesWritten], edi
0x180050321  jz      short loc_180050335
0x180050323  lea     rdx, aEUnexpected; "E_UNEXPECTED"
0x18005032a  mov     ecx, 8000FFFFh; this
0x18005032f  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180050335  mov     rbx, [rsp+38h+arg_8]
0x18005033a  add     rsp, 30h
0x18005033e  pop     rdi
0x18005033f  retn
```
