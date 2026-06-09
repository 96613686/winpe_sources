# CGeofenceStoreFileOperationsHelper::ReadAtFileOffset(void *,ulong,ulong,void *)

- ea: `0x18005ba68`
- end: `0x18005bb7b`
- name: `?ReadAtFileOffset@CGeofenceStoreFileOperationsHelper@@SAJPEAXKK0@Z`
- size: `275`
- prototype: `__int64 __fastcall(HANDLE hFile, LARGE_INTEGER liDistanceToMove, DWORD nNumberOfBytesToRead, void *lpBuffer)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180049e94`
- `0x180071a74`
- `0x1800ff2e0`
- `0x1800ff8d0`
- `0x1801000f8`
- `0x180100bbc`

## callees

- `0x18005ba68`
- `0x1800a98c0`
- `0x1801004ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005baa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bafe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005baa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bafe`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18005ba97`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18005ba97`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005baf4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005baf4`

## string_xrefs

- `0x18005bac2`: `ReadAtFileOffset:SetFilePointerEx failed`
- `0x18005bb1f`: `ReadFile failed`
- `0x18005bb4b`: `Mismatch in number of bytes read`

## pseudocode

```c
__int64 __fastcall CGeofenceStoreFileOperationsHelper::ReadAtFileOffset(
        HANDLE hFile,
        LARGE_INTEGER liDistanceToMove,
        DWORD nNumberOfBytesToRead,
        void *lpBuffer)
{
  signed int v6; // ebx
  signed int LastError; // eax
  __int64 v9; // rcx
  __int64 v10; // rcx
  signed int v11; // eax
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-38h] BYREF

  v6 = 0;
  NumberOfBytesRead = 0;
  if ( !SetFilePointerEx(hFile, (LARGE_INTEGER)liDistanceToMove.LowPart, 0, 0) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (byte_1801E39C4 & 0x10) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v9,
        GeofenceStoreInternalError,
        L"ReadAtFileOffset:SetFilePointerEx failed",
        (unsigned int)v6);
    if ( v6 < 0 )
      return (unsigned int)-2147023504;
  }
  if ( !ReadFile(hFile, lpBuffer, nNumberOfBytesToRead, &NumberOfBytesRead, 0) )
  {
    v11 = GetLastError();
    v6 = v11;
    if ( v11 > 0 )
      v6 = (unsigned __int16)v11 | 0x80070000;
    if ( (byte_1801E39C4 & 0x10) != 0 )
      McTemplateU0zq_EventWriteTransfer(v10, GeofenceStoreInternalError, L"ReadFile failed", (unsigned int)v6);
    if ( v6 < 0 )
      return (unsigned int)-2147023504;
  }
  if ( NumberOfBytesRead != nNumberOfBytesToRead )
  {
    if ( (byte_1801E39C4 & 0x10) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v10,
        GeofenceStoreInternalError,
        L"Mismatch in number of bytes read",
        2147549183LL);
    return (unsigned int)-2147023504;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005ba68  push    rbx
0x18005ba6a  push    rbp
0x18005ba6b  push    rsi
0x18005ba6c  push    rdi
0x18005ba6d  sub     rsp, 48h
0x18005ba71  mov     rax, cs:__security_cookie
0x18005ba78  xor     rax, rsp
0x18005ba7b  mov     [rsp+68h+var_30], rax
0x18005ba80  mov     rbp, r9
0x18005ba83  mov     edx, edx; liDistanceToMove
0x18005ba85  mov     edi, r8d
0x18005ba88  xor     ebx, ebx
0x18005ba8a  xor     r9d, r9d; dwMoveMethod
0x18005ba8d  mov     [rsp+68h+NumberOfBytesRead], ebx
0x18005ba91  xor     r8d, r8d; lpNewFilePointer
0x18005ba94  mov     rsi, rcx
0x18005ba97  call    cs:__imp_SetFilePointerEx
0x18005ba9d  test    eax, eax
0x18005ba9f  jnz     short loc_18005BADD
0x18005baa1  call    cs:__imp_GetLastError
0x18005baa7  mov     ebx, eax
0x18005baa9  test    eax, eax
0x18005baab  jle     short loc_18005BAB6
0x18005baad  movzx   ebx, ax
0x18005bab0  or      ebx, 80070000h
0x18005bab6  test    cs:byte_1801E39C4, 10h
0x18005babd  jz      short loc_18005BAD5
0x18005babf  mov     r9d, ebx
0x18005bac2  lea     r8, aReadatfileoffs; "ReadAtFileOffset:SetFilePointerEx faile"...
0x18005bac9  lea     rdx, GeofenceStoreInternalError
0x18005bad0  call    McTemplateU0zq_EventWriteTransfer
0x18005bad5  test    ebx, ebx
0x18005bad7  js      loc_18005BB5E
0x18005badd  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005bae2  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18005baeb  mov     r8d, edi; nNumberOfBytesToRead
0x18005baee  mov     rdx, rbp; lpBuffer
0x18005baf1  mov     rcx, rsi; hFile
0x18005baf4  call    cs:__imp_ReadFile
0x18005bafa  test    eax, eax
0x18005bafc  jnz     short loc_18005BB36
0x18005bafe  call    cs:__imp_GetLastError
0x18005bb04  mov     ebx, eax
0x18005bb06  test    eax, eax
0x18005bb08  jle     short loc_18005BB13
0x18005bb0a  movzx   ebx, ax
0x18005bb0d  or      ebx, 80070000h
0x18005bb13  test    cs:byte_1801E39C4, 10h
0x18005bb1a  jz      short loc_18005BB32
0x18005bb1c  mov     r9d, ebx
0x18005bb1f  lea     r8, aReadfileFailed; "ReadFile failed"
0x18005bb26  lea     rdx, GeofenceStoreInternalError
0x18005bb2d  call    McTemplateU0zq_EventWriteTransfer
0x18005bb32  test    ebx, ebx
0x18005bb34  js      short loc_18005BB5E
0x18005bb36  cmp     [rsp+68h+NumberOfBytesRead], edi
0x18005bb3a  jz      short loc_18005BB63
0x18005bb3c  test    cs:byte_1801E39C4, 10h
0x18005bb43  jz      short loc_18005BB5E
0x18005bb45  mov     r9d, 8000FFFFh
0x18005bb4b  lea     r8, aMismatchInNumb_0; "Mismatch in number of bytes read"
0x18005bb52  lea     rdx, GeofenceStoreInternalError
0x18005bb59  call    McTemplateU0zq_EventWriteTransfer
0x18005bb5e  mov     ebx, 80070570h
0x18005bb63  mov     eax, ebx
0x18005bb65  mov     rcx, [rsp+68h+var_30]
0x18005bb6a  xor     rcx, rsp; StackCookie
0x18005bb6d  call    __security_check_cookie
0x18005bb72  add     rsp, 48h
0x18005bb76  pop     rdi
0x18005bb77  pop     rsi
0x18005bb78  pop     rbp
0x18005bb79  pop     rbx
0x18005bb7a  retn
```
