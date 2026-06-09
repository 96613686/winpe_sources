# IO::InputFile::Peek(void)

- ea: `0x18005a800`
- end: `0x18005a91e`
- name: `?Peek@InputFile@IO@@UEBADXZ`
- size: `286`
- prototype: `char __fastcall(IO::InputFile *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180006ee0`
- `0x18000ecc0`
- `0x180035e0c`
- `0x18005a800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a8ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a8ba`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18005a842`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18005a842`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005a827`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005a827`

## pseudocode

```c
char __fastcall IO::InputFile::Peek(HANDLE *this)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  signed int v5; // eax
  unsigned int v6; // ebx
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF
  char Buffer; // [rsp+70h] [rbp+8h] BYREF

  Buffer = 0;
  if ( !ReadFile(this[2], &Buffer, 1u, 0, 0) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_fc52131781a63b563a504d48059c77ca_Traceguids, v4);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v4);
    throw (ErrorCodeException *)pExceptionObject;
  }
  if ( !SetFilePointerEx(this[2], (LARGE_INTEGER)-1LL, 0, 1u) )
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_fc52131781a63b563a504d48059c77ca_Traceguids, v6);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v6);
    throw (ErrorCodeException *)pExceptionObject;
  }
  return Buffer;
}

```

## disassembly

```asm
0x18005a800  push    rbx
0x18005a802  sub     rsp, 60h
0x18005a806  xor     r9d, r9d; lpNumberOfBytesRead
0x18005a809  mov     [rsp+68h+Buffer], 0
0x18005a80e  mov     rbx, rcx
0x18005a811  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18005a81a  mov     rcx, [rcx+10h]; hFile
0x18005a81e  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x18005a823  lea     r8d, [r9+1]; nNumberOfBytesToRead
0x18005a827  call    cs:__imp_ReadFile
0x18005a82d  test    eax, eax
0x18005a82f  jz      short loc_18005A856
0x18005a831  mov     rcx, [rbx+10h]; hFile
0x18005a835  mov     r9d, 1; dwMoveMethod
0x18005a83b  xor     r8d, r8d; lpNewFilePointer
0x18005a83e  or      rdx, 0FFFFFFFFFFFFFFFFh; liDistanceToMove
0x18005a842  call    cs:__imp_SetFilePointerEx
0x18005a848  test    eax, eax
0x18005a84a  jz      short loc_18005A8BA
0x18005a84c  mov     al, [rsp+68h+Buffer]
0x18005a850  add     rsp, 60h
0x18005a854  pop     rbx
0x18005a855  retn
0x18005a856  call    cs:__imp_GetLastError
0x18005a85c  mov     ebx, eax
0x18005a85e  test    eax, eax
0x18005a860  jle     short loc_18005A86B
0x18005a862  movzx   ebx, ax
0x18005a865  or      ebx, 80070000h
0x18005a86b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a872  lea     rax, WPP_GLOBAL_Control
0x18005a879  cmp     rcx, rax
0x18005a87c  jz      short loc_18005A89C
0x18005a87e  test    byte ptr [rcx+1Ch], 1
0x18005a882  jz      short loc_18005A89C
0x18005a884  mov     rcx, [rcx+10h]
0x18005a888  lea     r8, WPP_fc52131781a63b563a504d48059c77ca_Traceguids
0x18005a88f  mov     edx, 0Ch
0x18005a894  mov     r9d, ebx
0x18005a897  call    WPP_SF_d
0x18005a89c  mov     edx, ebx; int
0x18005a89e  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18005a8a3  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18005a8a8  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18005a8af  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18005a8b4  call    _CxxThrowException_0
0x18005a8ba  call    cs:__imp_GetLastError
0x18005a8c0  mov     ebx, eax
0x18005a8c2  test    eax, eax
0x18005a8c4  jle     short loc_18005A8CF
0x18005a8c6  movzx   ebx, ax
0x18005a8c9  or      ebx, 80070000h
0x18005a8cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a8d6  lea     rax, WPP_GLOBAL_Control
0x18005a8dd  cmp     rcx, rax
0x18005a8e0  jz      short loc_18005A900
0x18005a8e2  test    byte ptr [rcx+1Ch], 1
0x18005a8e6  jz      short loc_18005A900
0x18005a8e8  mov     rcx, [rcx+10h]
0x18005a8ec  lea     r8, WPP_fc52131781a63b563a504d48059c77ca_Traceguids
0x18005a8f3  mov     edx, 0Dh
0x18005a8f8  mov     r9d, ebx
0x18005a8fb  call    WPP_SF_d
0x18005a900  mov     edx, ebx; int
0x18005a902  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18005a907  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18005a90c  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18005a913  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18005a918  call    _CxxThrowException_0
```
