# CGeofenceStoreFileOperationsHelper::WriteAtFileOffset(void *,ulong,ulong,void const *)

- ea: `0x180062708`
- end: `0x18006281a`
- name: `?WriteAtFileOffset@CGeofenceStoreFileOperationsHelper@@SAJPEAXKKPEBX@Z`
- size: `274`
- prototype: `__int64 __fastcall(HANDLE hFile, LARGE_INTEGER liDistanceToMove, DWORD nNumberOfBytesToWrite, LPCVOID lpBuffer)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180049e94`
- `0x18004a298`
- `0x1800819f8`
- `0x1800ff2e0`
- `0x1800ff8d0`
- `0x1801000f8`
- `0x1801008f0`

## callees

- `0x180062708`
- `0x1800a98c0`
- `0x1801004ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006279d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006279d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180062739`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180062739`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180062793`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180062793`

## string_xrefs

- `0x180062761`: `WriteAtFileOffset:SetFilePointerEx failed`
- `0x1800627be`: `WriteFile failed`

## pseudocode

```c
__int64 __fastcall CGeofenceStoreFileOperationsHelper::WriteAtFileOffset(
        HANDLE hFile,
        LARGE_INTEGER liDistanceToMove,
        DWORD nNumberOfBytesToWrite,
        LPCVOID lpBuffer)
{
  signed int v7; // eax
  __int64 v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rcx
  signed int LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-38h] BYREF

  NumberOfBytesWritten = 0;
  if ( SetFilePointerEx(hFile, (LARGE_INTEGER)liDistanceToMove.LowPart, 0, 0) )
  {
    v9 = 0;
    if ( WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
      goto LABEL_19;
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (byte_1801E39C4 & 0x10) != 0 )
      McTemplateU0zq_EventWriteTransfer(v10, GeofenceStoreInternalError, L"WriteFile failed", v9);
    if ( (v9 & 0x80000000) == 0 )
    {
LABEL_19:
      if ( NumberOfBytesWritten != nNumberOfBytesToWrite )
      {
        v9 = -2147418113;
        if ( (byte_1801E39C4 & 0x10) != 0 )
          McTemplateU0zq_EventWriteTransfer(
            v10,
            GeofenceStoreInternalError,
            L"Mismatch in number of bytes written",
            2147549183LL);
      }
    }
  }
  else
  {
    v7 = GetLastError();
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    if ( (byte_1801E39C4 & 0x10) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v8,
        GeofenceStoreInternalError,
        L"WriteAtFileOffset:SetFilePointerEx failed",
        (unsigned int)v7);
    return (unsigned int)-2147023504;
  }
  return v9;
}

```

## disassembly

```asm
0x180062708  push    rbx
0x18006270a  push    rbp
0x18006270b  push    rsi
0x18006270c  push    rdi
0x18006270d  sub     rsp, 48h
0x180062711  mov     rax, cs:__security_cookie
0x180062718  xor     rax, rsp
0x18006271b  mov     [rsp+68h+var_30], rax
0x180062720  mov     rbp, r9
0x180062723  mov     edx, edx; liDistanceToMove
0x180062725  mov     edi, r8d
0x180062728  mov     [rsp+68h+NumberOfBytesWritten], 0
0x180062730  xor     r9d, r9d; dwMoveMethod
0x180062733  xor     r8d, r8d; lpNewFilePointer
0x180062736  mov     rsi, rcx
0x180062739  call    cs:__imp_SetFilePointerEx
0x18006273f  test    eax, eax
0x180062741  jnz     short loc_18006277E
0x180062743  call    cs:__imp_GetLastError
0x180062749  test    eax, eax
0x18006274b  jle     short loc_180062755
0x18006274d  movzx   eax, ax
0x180062750  or      eax, 80070000h
0x180062755  test    cs:byte_1801E39C4, 10h
0x18006275c  jz      short loc_180062774
0x18006275e  mov     r9d, eax
0x180062761  lea     r8, aWriteatfileoff; "WriteAtFileOffset:SetFilePointerEx fail"...
0x180062768  lea     rdx, GeofenceStoreInternalError
0x18006276f  call    McTemplateU0zq_EventWriteTransfer
0x180062774  mov     ebx, 80070570h
0x180062779  jmp     loc_180062802
0x18006277e  xor     ebx, ebx
0x180062780  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180062785  mov     r8d, edi; nNumberOfBytesToWrite
0x180062788  mov     [rsp+68h+lpOverlapped], rbx; lpOverlapped
0x18006278d  mov     rdx, rbp; lpBuffer
0x180062790  mov     rcx, rsi; hFile
0x180062793  call    cs:__imp_WriteFile
0x180062799  test    eax, eax
0x18006279b  jnz     short loc_1800627D5
0x18006279d  call    cs:__imp_GetLastError
0x1800627a3  mov     ebx, eax
0x1800627a5  test    eax, eax
0x1800627a7  jle     short loc_1800627B2
0x1800627a9  movzx   ebx, ax
0x1800627ac  or      ebx, 80070000h
0x1800627b2  test    cs:byte_1801E39C4, 10h
0x1800627b9  jz      short loc_1800627D1
0x1800627bb  mov     r9d, ebx
0x1800627be  lea     r8, aWritefileFaile; "WriteFile failed"
0x1800627c5  lea     rdx, GeofenceStoreInternalError
0x1800627cc  call    McTemplateU0zq_EventWriteTransfer
0x1800627d1  test    ebx, ebx
0x1800627d3  js      short loc_180062802
0x1800627d5  cmp     [rsp+68h+NumberOfBytesWritten], edi
0x1800627d9  jz      short loc_180062802
0x1800627db  test    cs:byte_1801E39C4, 10h
0x1800627e2  mov     ebx, 8000FFFFh
0x1800627e7  jz      short loc_180062802
0x1800627e9  mov     r9d, 8000FFFFh
0x1800627ef  lea     r8, aMismatchInNumb; "Mismatch in number of bytes written"
0x1800627f6  lea     rdx, GeofenceStoreInternalError
0x1800627fd  call    McTemplateU0zq_EventWriteTransfer
0x180062802  mov     eax, ebx
0x180062804  mov     rcx, [rsp+68h+var_30]
0x180062809  xor     rcx, rsp; StackCookie
0x18006280c  call    __security_check_cookie
0x180062811  add     rsp, 48h
0x180062815  pop     rdi
0x180062816  pop     rsi
0x180062817  pop     rbp
0x180062818  pop     rbx
0x180062819  retn
```
