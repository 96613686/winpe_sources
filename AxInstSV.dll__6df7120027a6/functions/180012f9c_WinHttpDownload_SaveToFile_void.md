# WinHttpDownload::SaveToFile(void *)

- ea: `0x180012f9c`
- end: `0x1800130cd`
- name: `?SaveToFile@WinHttpDownload@@AEAAJPEAX@Z`
- size: `305`
- prototype: `__int64 __fastcall(WinHttpDownload *this, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180012408`

## callees

- `0x180012f9c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001302d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001302d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001301e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800130ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001301e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800130ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013086`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001309d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013086`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001309d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001306e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001306e`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180012ffa`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180012ffa`
- `WINHTTP!WinHttpReadData` at `0x18001304d`
- `WINHTTP!WinHttpReadData` at `0x18001304d`
- `WINHTTP!WinHttpQueryHeaders` at `0x180012fe5`
- `WINHTTP!WinHttpQueryHeaders` at `0x180012fe5`

## pseudocode

```c
__int64 __fastcall WinHttpDownload::SaveToFile(WinHttpDownload *this, void *a2)
{
  HLOCAL v2; // rdi
  DWORD v3; // ebx
  void *v6; // rcx
  void *v7; // rcx
  DWORD v8; // r8d
  unsigned int v9; // ebx
  signed int v10; // eax
  signed int LastError; // eax
  int Buffer; // [rsp+30h] [rbp-10h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+34h] [rbp-Ch] BYREF
  DWORD dwNumberOfBytesAvailable; // [rsp+70h] [rbp+30h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+80h] [rbp+40h] BYREF
  DWORD dwBufferLength; // [rsp+88h] [rbp+48h] BYREF

  v2 = 0;
  dwBufferLength = 4;
  v3 = 0;
  Buffer = 0;
  dwNumberOfBytesAvailable = 0;
  v6 = (void *)*((_QWORD *)this + 9);
  dwNumberOfBytesRead = 0;
  NumberOfBytesWritten = 0;
  WinHttpQueryHeaders(v6, 0x20000005u, 0, &Buffer, &dwBufferLength, 0);
  while ( 1 )
  {
    v7 = (void *)*((_QWORD *)this + 9);
    dwNumberOfBytesAvailable = 0;
    if ( !WinHttpQueryDataAvailable(v7, &dwNumberOfBytesAvailable) )
    {
LABEL_15:
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_17;
    }
    v8 = dwNumberOfBytesAvailable;
    if ( !dwNumberOfBytesAvailable )
      goto LABEL_12;
    if ( dwNumberOfBytesAvailable > v3 )
      break;
LABEL_9:
    if ( !WinHttpReadData(*((HINTERNET *)this + 9), v2, v8, &dwNumberOfBytesRead)
      || !WriteFile(a2, v2, dwNumberOfBytesRead, &NumberOfBytesWritten, 0) )
    {
      goto LABEL_15;
    }
    if ( !dwNumberOfBytesAvailable )
    {
LABEL_12:
      v9 = 0;
LABEL_17:
      if ( v2 )
        LocalFree(v2);
      return v9;
    }
  }
  if ( v2 )
  {
    LocalFree(v2);
    v8 = dwNumberOfBytesAvailable;
  }
  v2 = LocalAlloc(0, v8);
  if ( v2 )
  {
    v8 = dwNumberOfBytesAvailable;
    v3 = dwNumberOfBytesAvailable;
    goto LABEL_9;
  }
  v10 = GetLastError();
  v9 = v10;
  if ( v10 > 0 )
    return (unsigned __int16)v10 | 0x80070000;
  return v9;
}

```

## disassembly

```asm
0x180012f9c  push    rbp
0x180012f9e  push    rbx
0x180012f9f  push    rsi
0x180012fa0  push    rdi
0x180012fa1  push    r14
0x180012fa3  mov     rbp, rsp
0x180012fa6  sub     rsp, 40h
0x180012faa  xor     edi, edi
0x180012fac  mov     [rbp+dwBufferLength], 4
0x180012fb3  xor     ebx, ebx
0x180012fb5  mov     [rbp+Buffer], edi
0x180012fb8  mov     r14, rdx
0x180012fbb  mov     [rsp+40h+lpdwIndex], rbx; lpdwIndex
0x180012fc0  mov     rsi, rcx
0x180012fc3  mov     [rbp+dwNumberOfBytesAvailable], edi
0x180012fc6  mov     rcx, [rcx+48h]; hRequest
0x180012fca  lea     rax, [rbp+dwBufferLength]
0x180012fce  lea     r9, [rbp+Buffer]; lpBuffer
0x180012fd2  mov     [rsp+40h+lpdwBufferLength], rax; lpdwBufferLength
0x180012fd7  xor     r8d, r8d; pwszName
0x180012fda  mov     [rbp+dwNumberOfBytesRead], edi
0x180012fdd  mov     edx, 20000005h; dwInfoLevel
0x180012fe2  mov     [rbp+NumberOfBytesWritten], edi
0x180012fe5  call    cs:__imp_WinHttpQueryHeaders
0x180012feb  mov     rcx, [rsi+48h]; hRequest
0x180012fef  lea     rdx, [rbp+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x180012ff3  mov     [rbp+dwNumberOfBytesAvailable], 0
0x180012ffa  call    cs:__imp_WinHttpQueryDataAvailable
0x180013000  test    eax, eax
0x180013002  jz      loc_18001309D
0x180013008  mov     r8d, [rbp+dwNumberOfBytesAvailable]
0x18001300c  test    r8d, r8d
0x18001300f  jz      short loc_180013082
0x180013011  cmp     r8d, ebx
0x180013014  jbe     short loc_180013042
0x180013016  test    rdi, rdi
0x180013019  jz      short loc_180013028
0x18001301b  mov     rcx, rdi; hMem
0x18001301e  call    cs:__imp_LocalFree
0x180013024  mov     r8d, [rbp+dwNumberOfBytesAvailable]
0x180013028  mov     edx, r8d; uBytes
0x18001302b  xor     ecx, ecx; uFlags
0x18001302d  call    cs:__imp_LocalAlloc
0x180013033  mov     rdi, rax
0x180013036  test    rax, rax
0x180013039  jz      short loc_180013086
0x18001303b  mov     r8d, [rbp+dwNumberOfBytesAvailable]; dwNumberOfBytesToRead
0x18001303f  mov     ebx, r8d
0x180013042  mov     rcx, [rsi+48h]; hRequest
0x180013046  lea     r9, [rbp+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18001304a  mov     rdx, rdi; lpBuffer
0x18001304d  call    cs:__imp_WinHttpReadData
0x180013053  test    eax, eax
0x180013055  jz      short loc_18001309D
0x180013057  mov     r8d, [rbp+dwNumberOfBytesRead]; nNumberOfBytesToWrite
0x18001305b  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001305f  mov     rdx, rdi; lpBuffer
0x180013062  mov     [rsp+40h+lpdwBufferLength], 0; lpOverlapped
0x18001306b  mov     rcx, r14; hFile
0x18001306e  call    cs:__imp_WriteFile
0x180013074  test    eax, eax
0x180013076  jz      short loc_18001309D
0x180013078  cmp     [rbp+dwNumberOfBytesAvailable], 0
0x18001307c  ja      loc_180012FEB
0x180013082  xor     ebx, ebx
0x180013084  jmp     short loc_1800130B2
0x180013086  call    cs:__imp_GetLastError
0x18001308c  mov     ebx, eax
0x18001308e  test    eax, eax
0x180013090  jle     short loc_1800130C0
0x180013092  movzx   ebx, ax
0x180013095  or      ebx, 80070000h
0x18001309b  jmp     short loc_1800130C0
0x18001309d  call    cs:__imp_GetLastError
0x1800130a3  mov     ebx, eax
0x1800130a5  test    eax, eax
0x1800130a7  jle     short loc_1800130B2
0x1800130a9  movzx   ebx, ax
0x1800130ac  or      ebx, 80070000h
0x1800130b2  test    rdi, rdi
0x1800130b5  jz      short loc_1800130C0
0x1800130b7  mov     rcx, rdi; hMem
0x1800130ba  call    cs:__imp_LocalFree
0x1800130c0  mov     eax, ebx
0x1800130c2  add     rsp, 40h
0x1800130c6  pop     r14
0x1800130c8  pop     rdi
0x1800130c9  pop     rsi
0x1800130ca  pop     rbx
0x1800130cb  pop     rbp
0x1800130cc  retn
```
