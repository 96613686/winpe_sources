# ConnectedStorage::File::Read(ulong,void *,ulong *)

- ea: `0x18004f8f8`
- end: `0x18004f941`
- name: `?Read@File@ConnectedStorage@@QEAAXKPEAXPEAK@Z`
- size: `73`
- prototype: `void(ConnectedStorage::File *__hidden this, unsigned int, void *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180044340`
- `0x1800443d0`

## callees

- `0x18000aae4`
- `0x18004f8f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f91b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f91b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004f911`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004f911`

## string_xrefs

- `0x18004f92d`: `File::Read`

## pseudocode

```c
void __fastcall ConnectedStorage::File::Read(HANDLE *this, DWORD a2, void *a3, unsigned int *a4)
{
  signed int LastError; // eax
  const unsigned __int16 *v5; // r8

  if ( !ReadFile(*this, a3, a2, a4, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)LastError, (int)L"File::Read", v5);
  }
}

```

## disassembly

```asm
0x18004f8f8  sub     rsp, 38h
0x18004f8fc  mov     rcx, [rcx]; hFile
0x18004f8ff  mov     rax, r8
0x18004f902  mov     r8d, edx; nNumberOfBytesToRead
0x18004f905  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18004f90e  mov     rdx, rax; lpBuffer
0x18004f911  call    cs:__imp_ReadFile
0x18004f917  test    eax, eax
0x18004f919  jnz     short loc_18004F93C
0x18004f91b  call    cs:__imp_GetLastError
0x18004f921  test    eax, eax
0x18004f923  jle     short loc_18004F92D
0x18004f925  movzx   eax, ax
0x18004f928  or      eax, 80070000h
0x18004f92d  lea     rdx, aFileRead; "File::Read"
0x18004f934  mov     ecx, eax; this
0x18004f936  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18004f93c  add     rsp, 38h
0x18004f940  retn
```
