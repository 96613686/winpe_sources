# ConnectedStorage::File::Read(ulong,void *)

- ea: `0x18004f85c`
- end: `0x18004f8f2`
- name: `?Read@File@ConnectedStorage@@QEAAXKPEAX@Z`
- size: `150`
- prototype: `void __fastcall(void **this, DWORD, void *)`
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180064d14`
- `0x180064f00`
- `0x180064fdc`
- `0x180071e60`
- `0x180076358`
- `0x180077a54`
- `0x180079fbc`

## callees

- `0x180004760`
- `0x180007dbc`
- `0x18000aae4`
- `0x18004f85c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f890`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004f886`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004f886`

## string_xrefs

- `0x18004f8a2`: `File::Read`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ConnectedStorage::File::Read(void **this, DWORD a2, void *a3)
{
  void *v3; // rcx
  signed int LastError; // eax
  const unsigned __int16 *v6; // r8
  _QWORD pExceptionObject[5]; // [rsp+30h] [rbp-28h] BYREF
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+8h] BYREF

  v3 = *this;
  NumberOfBytesRead = 0;
  if ( !ReadFile(v3, a3, a2, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)LastError, (int)L"File::Read", v6);
  }
  if ( NumberOfBytesRead != a2 )
  {
    std::exception::exception((std::exception *)pExceptionObject, "File::EofException", 1);
    pExceptionObject[0] = &ConnectedStorage::CorruptContainerException::`vftable';
    throw (ConnectedStorage::File::EofException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18004f85c  push    rbx
0x18004f85e  sub     rsp, 50h
0x18004f862  mov     rcx, [rcx]; hFile
0x18004f865  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18004f86a  mov     rax, r8
0x18004f86d  mov     [rsp+58h+NumberOfBytesRead], 0
0x18004f875  mov     r8d, edx; nNumberOfBytesToRead
0x18004f878  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x18004f881  mov     ebx, edx
0x18004f883  mov     rdx, rax; lpBuffer
0x18004f886  call    cs:__imp_ReadFile
0x18004f88c  test    eax, eax
0x18004f88e  jnz     short loc_18004F8B1
0x18004f890  call    cs:__imp_GetLastError
0x18004f896  test    eax, eax
0x18004f898  jle     short loc_18004F8A2
0x18004f89a  movzx   eax, ax
0x18004f89d  or      eax, 80070000h
0x18004f8a2  lea     rdx, aFileRead; "File::Read"
0x18004f8a9  mov     ecx, eax; this
0x18004f8ab  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18004f8b1  cmp     [rsp+58h+NumberOfBytesRead], ebx
0x18004f8b5  jz      short loc_18004F8EC
0x18004f8b7  mov     r8d, 1; int
0x18004f8bd  lea     rdx, aFileEofexcepti; "File::EofException"
0x18004f8c4  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18004f8c9  call    ??0exception@std@@QEAA@QEBDH@Z; std::exception::exception(char const * const,int)
0x18004f8ce  lea     rax, ??_7CorruptContainerException@ConnectedStorage@@6B@; const ConnectedStorage::CorruptContainerException::`vftable'
0x18004f8d5  lea     rdx, _TI2?AVEofException@File@ConnectedStorage@@; pThrowInfo
0x18004f8dc  mov     [rsp+58h+pExceptionObject], rax
0x18004f8e1  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18004f8e6  call    _CxxThrowException_0
0x18004f8ec  add     rsp, 50h
0x18004f8f0  pop     rbx
0x18004f8f1  retn
```
