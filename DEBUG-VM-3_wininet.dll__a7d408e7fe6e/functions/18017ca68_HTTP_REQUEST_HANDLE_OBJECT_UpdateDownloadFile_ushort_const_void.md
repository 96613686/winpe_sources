# HTTP_REQUEST_HANDLE_OBJECT::UpdateDownloadFile(ushort const *,void *)

- ea: `0x18017ca68`
- end: `0x18017cf40`
- name: `?UpdateDownloadFile@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKPEBGPEAX@Z`
- size: `1240`
- prototype: `unsigned int __fastcall(HTTP_REQUEST_HANDLE_OBJECT *__hidden this, const unsigned __int16 *Src, HANDLE hSourceHandle)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800d1e00`

## callees

- `0x1800701d0`
- `0x18007613c`
- `0x180076574`
- `0x18007a91c`
- `0x1800a4900`
- `0x1800a4d40`
- `0x1800d0550`
- `0x1800d058c`
- `0x18010bb84`
- `0x18010fd28`
- `0x18013284c`
- `0x1801379b0`
- `0x18014a7a0`
- `0x18017ca68`
- `0x1801e1790`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18017cb14`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18017cb14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18017cf11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18017cf11`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18017cbcd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18017cbcd`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18017cc5c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18017cc5c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18017ce1f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18017ce1f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18017cc86`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18017cc86`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18017cbeb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18017cc36`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18017cbeb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18017cc36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18017cb3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18017cb48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18017cb3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18017cb48`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18017cb6d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18017cb6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017cd11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017cee0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017cef6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017cd11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017cee0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017cef6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18017cd04`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18017cd1b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18017cd04`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18017cd1b`

## pseudocode

```c
__int64 __fastcall HTTP_REQUEST_HANDLE_OBJECT::UpdateDownloadFile(
        HTTP_REQUEST_HANDLE_OBJECT *this,
        unsigned __int16 *Src,
        HANDLE hSourceHandle)
{
  unsigned __int16 *v6; // rsi
  unsigned int v7; // ebx
  LPVOID v8; // rax
  void *Handle; // r14
  HANDLE CurrentProcess; // rbx
  HANDLE v11; // rax
  unsigned int LastError; // eax
  HANDLE FileW; // rax
  DWORD v14; // eax
  __int64 v15; // rbx
  unsigned int ThreadInfoUIType; // eax
  unsigned int v17; // ebx
  int v18; // ecx
  bool v19; // zf
  __int64 v20; // rcx
  __int64 v21; // rax
  void *v22; // rcx
  const unsigned __int16 **v23; // rbx
  int v24; // eax
  void *v25; // rcx
  HANDLE TargetHandle; // [rsp+60h] [rbp-9h] BYREF
  LONG DistanceToMoveHigh; // [rsp+68h] [rbp-1h] BYREF
  DWORD NumberOfBytesRead; // [rsp+6Ch] [rbp+3h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp+7h] BYREF
  LARGE_INTEGER v31; // [rsp+78h] [rbp+Fh] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+80h] [rbp+17h] BYREF

  TargetHandle = (HANDLE)-1LL;
  NumberOfBytesRead = 0;
  NumberOfBytesWritten = 0;
  DistanceToMoveHigh = 0;
  PerformanceCount.QuadPart = 0;
  v31.QuadPart = 0;
  if ( !*((_QWORD *)this + 89) && !*((_DWORD *)this + 1348) )
  {
    v6 = 0;
LABEL_4:
    v7 = 12019;
    goto LABEL_55;
  }
  v6 = (unsigned __int16 *)NewStringW(Src);
  if ( !v6 )
    goto LABEL_6;
  if ( *((_QWORD *)this + 94) )
    goto LABEL_4;
  v8 = HeapAlloc(g_hWxProcessHeap, 0, 0x100000u);
  *((_QWORD *)this + 94) = v8;
  if ( !v8 )
  {
LABEL_6:
    v7 = 8;
    goto LABEL_55;
  }
  Handle = HTTP_REQUEST_HANDLE_OBJECT::GetDownloadFileReadHandle(this);
  if ( Handle == (void *)-1LL )
    goto LABEL_18;
  if ( hSourceHandle != (HANDLE)-1LL )
  {
    CurrentProcess = GetCurrentProcess();
    v11 = GetCurrentProcess();
    if ( !DuplicateHandle(v11, hSourceHandle, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    {
      LastError = WxGetLastError();
      v7 = LastError;
      if ( (xmmword_180266B50 & 2) != 0 )
        WPP_SF_d(513, 39, &WPP_f57f0d52a59033179f5677a89e61f04c_Traceguids, LastError);
LABEL_19:
      if ( !v7 )
        goto LABEL_57;
      goto LABEL_55;
    }
    FileW = TargetHandle;
    goto LABEL_16;
  }
  FileW = CreateFileW(Src, 0x40000000u, 7u, 0, 3u, 0, 0);
  TargetHandle = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
LABEL_18:
    v7 = WxGetLastError();
    goto LABEL_19;
  }
LABEL_16:
  v14 = SetFilePointer(FileW, 0, &DistanceToMoveHigh, 2u);
  if ( v14 == -1 )
  {
    if ( (unsigned int)WxGetLastError() )
      goto LABEL_18;
  }
  else if ( !v14 && !DistanceToMoveHigh )
  {
    if ( SetFilePointer(Handle, 0, 0, 0) != -1 )
    {
      v15 = 0;
      while ( ReadFile(Handle, *((LPVOID *)this + 94), 0x100000u, &NumberOfBytesRead, 0) )
      {
        v15 += NumberOfBytesRead;
        if ( !NumberOfBytesRead )
        {
          if ( *((_QWORD *)this + 93) != v15 )
          {
            v7 = 1006;
            goto LABEL_55;
          }
          if ( *((_QWORD *)this + 90) != -1 )
          {
            ThreadInfoUIType = GetThreadInfoUIType();
            v17 = ThreadInfoUIType;
            if ( (Microsoft_Windows_WinINetEnableBits & 0x800000) != 0 )
              McTemplateU0pqqqt_EventWriteTransfer(
                GlobalClientType,
                (unsigned int)&WININET_FILE_IO_START,
                *((_QWORD *)this + 16),
                4,
                GlobalClientType,
                ThreadInfoUIType,
                *((_QWORD *)this + 78) != 0);
            QueryPerformanceCounter(&PerformanceCount);
            CloseHandle(*((HANDLE *)this + 90));
            QueryPerformanceCounter(&v31);
            if ( (Microsoft_Windows_WinINetEnableBits & 0x800000) != 0 )
              McTemplateU0pqqqt_EventWriteTransfer(
                v18,
                (unsigned int)&WININET_FILE_IO_STOP,
                *((_QWORD *)this + 16),
                4,
                GlobalClientType,
                v17,
                *((_QWORD *)this + 78) != 0);
            (*(void (__fastcall **)(HTTP_REQUEST_HANDLE_OBJECT *, __int64, LONGLONG, _QWORD))(*(_QWORD *)this + 216LL))(
              this,
              4,
              v31.QuadPart - PerformanceCount.QuadPart,
              v17);
            *((_QWORD *)this + 90) = -1;
          }
          *(_QWORD *)((char *)this + 1260) = 0;
          *((_QWORD *)this + 66) = 0;
          if ( *((_DWORD *)this + 178) )
          {
            *((_QWORD *)this + 98) = *((_QWORD *)this + 93);
            *((_QWORD *)this + 617) = 0;
          }
          else if ( (unsigned int)HTTP_REQUEST_HANDLE_OBJECT::IsReadRequest(this) )
          {
            v19 = (*((_DWORD *)this + 1291) & 0x800) == 0;
            v20 = *((_QWORD *)this + 93);
            v21 = *((_QWORD *)this + 98);
            *((_QWORD *)this + 98) = v20;
            if ( !v19 )
              *((_QWORD *)this + 617) += v21 - v20;
          }
          v22 = (void *)*((_QWORD *)this + 102);
          if ( v22 )
          {
            InternetUnlockRequestFile(v22);
            *((_QWORD *)this + 102) = 0;
          }
          if ( *((_DWORD *)this + 1348) || *((_DWORD *)this + 178) )
          {
            DeleteUrlCacheEntryA(*((LPCSTR *)this + 84));
            v23 = (const unsigned __int16 **)((char *)this + 696);
          }
          else
          {
            v23 = (const unsigned __int16 **)((char *)this + 696);
            if ( !DeleteFileW(*((LPCWSTR *)this + 87)) )
            {
              v24 = WxGetLastError();
              if ( v24 == 5 || v24 == 32 )
                UrlCacheAddLeakFile(*v23);
            }
          }
          INTERNET_CONNECT_HANDLE_OBJECT::FreeCacheFileName(this);
          *v23 = v6;
          v6 = 0;
          if ( *((_DWORD *)this + 179) )
          {
            *((_QWORD *)this + 90) = TargetHandle;
            TargetHandle = (HANDLE)-1LL;
          }
          v7 = 0;
          goto LABEL_57;
        }
        if ( !WriteFile(TargetHandle, *((LPCVOID *)this + 94), NumberOfBytesRead, &NumberOfBytesWritten, 0) )
          goto LABEL_18;
      }
    }
    goto LABEL_18;
  }
  v7 = 87;
LABEL_55:
  HTTP_REQUEST_HANDLE_OBJECT::SetState(this, 49157);
  if ( *((_DWORD *)this + 179) )
    INTERNET_CONNECT_HANDLE_OBJECT::EndCacheWrite(this, 0, 0, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0, 0);
LABEL_57:
  v25 = (void *)*((_QWORD *)this + 91);
  if ( v25 != (void *)-1LL )
  {
    CloseHandle(v25);
    *((_QWORD *)this + 91) = -1;
  }
  if ( TargetHandle != (HANDLE)-1LL )
  {
    CloseHandle(TargetHandle);
    TargetHandle = (HANDLE)-1LL;
  }
  if ( v6 )
    HeapFree(g_hWxProcessHeap, 0, v6);
  return v7;
}

```

## disassembly

```asm
0x18017ca68  mov     [rsp-8+arg_18], rbx
0x18017ca6d  push    rbp
0x18017ca6e  push    rsi
0x18017ca6f  push    rdi
0x18017ca70  push    r12
0x18017ca72  push    r13
0x18017ca74  push    r14
0x18017ca76  push    r15
0x18017ca78  lea     rbp, [rsp-27h]
0x18017ca7d  sub     rsp, 90h
0x18017ca84  mov     rax, cs:__security_cookie
0x18017ca8b  xor     rax, rsp
0x18017ca8e  mov     [rbp+57h+var_38], rax
0x18017ca92  xor     r12d, r12d
0x18017ca95  or      r13, 0FFFFFFFFFFFFFFFFh
0x18017ca99  mov     r15, r8
0x18017ca9c  mov     rbx, rdx
0x18017ca9f  mov     rdi, rcx
0x18017caa2  mov     [rbp+57h+TargetHandle], r13
0x18017caa6  mov     [rbp+57h+NumberOfBytesRead], r12d
0x18017caaa  mov     [rbp+57h+NumberOfBytesWritten], r12d
0x18017caae  mov     [rbp+57h+DistanceToMoveHigh], r12d
0x18017cab2  mov     qword ptr [rbp+57h+PerformanceCount], r12
0x18017cab6  mov     qword ptr [rbp+57h+var_48], r12
0x18017caba  cmp     [rcx+2C8h], r12d
0x18017cac1  jnz     short loc_18017CAE2
0x18017cac3  cmp     [rcx+2CCh], r12d
0x18017caca  jnz     short loc_18017CAE2
0x18017cacc  cmp     [rcx+1510h], r12d
0x18017cad3  jnz     short loc_18017CAE2
0x18017cad5  mov     esi, r12d
0x18017cad8  mov     ebx, 2EF3h
0x18017cadd  jmp     loc_18017CE85
0x18017cae2  mov     rcx, rbx; Src
0x18017cae5  call    NewStringW
0x18017caea  mov     rsi, rax
0x18017caed  test    rax, rax
0x18017caf0  jnz     short loc_18017CAFC
0x18017caf2  mov     ebx, 8
0x18017caf7  jmp     loc_18017CE85
0x18017cafc  cmp     [rdi+2F0h], r12
0x18017cb03  jnz     short loc_18017CAD8
0x18017cb05  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18017cb0c  xor     edx, edx; dwFlags
0x18017cb0e  mov     r8d, 100000h; dwBytes
0x18017cb14  call    cs:__imp_HeapAlloc
0x18017cb1a  mov     [rdi+2F0h], rax
0x18017cb21  test    rax, rax
0x18017cb24  jz      short loc_18017CAF2
0x18017cb26  mov     rcx, rdi; this
0x18017cb29  call    ?GetDownloadFileReadHandle@HTTP_REQUEST_HANDLE_OBJECT@@AEAAPEAXXZ; HTTP_REQUEST_HANDLE_OBJECT::GetDownloadFileReadHandle(void)
0x18017cb2e  mov     r14, rax
0x18017cb31  cmp     rax, r13
0x18017cb34  jz      loc_18017CC05
0x18017cb3a  cmp     r15, r13
0x18017cb3d  jz      short loc_18017CBAC
0x18017cb3f  call    cs:__imp_GetCurrentProcess
0x18017cb45  mov     rbx, rax
0x18017cb48  call    cs:__imp_GetCurrentProcess
0x18017cb4e  mov     [rsp+0C0h+dwOptions], 2; dwOptions
0x18017cb56  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x18017cb5a  mov     rcx, rax; hSourceProcessHandle
0x18017cb5d  mov     [rsp+0C0h+bInheritHandle], r12d; bInheritHandle
0x18017cb62  mov     r8, rbx; hTargetProcessHandle
0x18017cb65  mov     [rsp+0C0h+dwDesiredAccess], r12d; dwDesiredAccess
0x18017cb6a  mov     rdx, r15; hSourceHandle
0x18017cb6d  call    cs:__imp_DuplicateHandle
0x18017cb73  test    eax, eax
0x18017cb75  jnz     short loc_18017CBA6
0x18017cb77  call    WxGetLastError
0x18017cb7c  mov     ebx, eax
0x18017cb7e  test    byte ptr cs:xmmword_180266B50, 2
0x18017cb85  jz      loc_18017CC0C
0x18017cb8b  mov     edx, 27h ; '''
0x18017cb90  lea     r8, WPP_f57f0d52a59033179f5677a89e61f04c_Traceguids
0x18017cb97  mov     ecx, 201h
0x18017cb9c  mov     r9d, eax
0x18017cb9f  call    WPP_SF_d
0x18017cba4  jmp     short loc_18017CC0C
0x18017cba6  mov     rax, [rbp+57h+TargetHandle]
0x18017cbaa  jmp     short loc_18017CBDC
0x18017cbac  xor     r9d, r9d; lpSecurityAttributes
0x18017cbaf  mov     qword ptr [rsp+0C0h+dwOptions], r12; hTemplateFile
0x18017cbb4  mov     [rsp+0C0h+bInheritHandle], r12d; dwFlagsAndAttributes
0x18017cbb9  mov     edx, 40000000h; dwDesiredAccess
0x18017cbbe  mov     rcx, rbx; lpFileName
0x18017cbc1  mov     [rsp+0C0h+dwDesiredAccess], 3; dwCreationDisposition
0x18017cbc9  lea     r8d, [r9+7]; dwShareMode
0x18017cbcd  call    cs:__imp_CreateFileW
0x18017cbd3  mov     [rbp+57h+TargetHandle], rax
0x18017cbd7  cmp     rax, r13
0x18017cbda  jz      short loc_18017CC05
0x18017cbdc  mov     r9d, 2; dwMoveMethod
0x18017cbe2  lea     r8, [rbp+57h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18017cbe6  xor     edx, edx; lDistanceToMove
0x18017cbe8  mov     rcx, rax; hFile
0x18017cbeb  call    cs:__imp_SetFilePointer
0x18017cbf1  or      ebx, 0FFFFFFFFh
0x18017cbf4  cmp     eax, ebx
0x18017cbf6  jnz     short loc_18017CC19
0x18017cbf8  call    WxGetLastError
0x18017cbfd  test    eax, eax
0x18017cbff  jz      loc_18017CE80
0x18017cc05  call    WxGetLastError
0x18017cc0a  mov     ebx, eax
0x18017cc0c  test    ebx, ebx
0x18017cc0e  jz      loc_18017CED4
0x18017cc14  jmp     loc_18017CE85
0x18017cc19  test    eax, eax
0x18017cc1b  jnz     loc_18017CE80
0x18017cc21  cmp     [rbp+57h+DistanceToMoveHigh], r12d
0x18017cc25  jnz     loc_18017CE80
0x18017cc2b  xor     r9d, r9d; dwMoveMethod
0x18017cc2e  xor     r8d, r8d; lpDistanceToMoveHigh
0x18017cc31  xor     edx, edx; lDistanceToMove
0x18017cc33  mov     rcx, r14; hFile
0x18017cc36  call    cs:__imp_SetFilePointer
0x18017cc3c  cmp     eax, ebx
0x18017cc3e  jz      short loc_18017CC05
0x18017cc40  mov     rbx, r12
0x18017cc43  mov     rdx, [rdi+2F0h]; lpBuffer
0x18017cc4a  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18017cc4e  mov     r8d, 100000h; nNumberOfBytesToRead
0x18017cc54  mov     qword ptr [rsp+0C0h+dwDesiredAccess], r12; lpOverlapped
0x18017cc59  mov     rcx, r14; hFile
0x18017cc5c  call    cs:__imp_ReadFile
0x18017cc62  test    eax, eax
0x18017cc64  jz      short loc_18017CC05
0x18017cc66  mov     r8d, [rbp+57h+NumberOfBytesRead]; nNumberOfBytesToWrite
0x18017cc6a  add     rbx, r8
0x18017cc6d  test    r8d, r8d
0x18017cc70  jz      short loc_18017CC95
0x18017cc72  mov     rdx, [rdi+2F0h]; lpBuffer
0x18017cc79  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18017cc7d  mov     rcx, [rbp+57h+TargetHandle]; hFile
0x18017cc81  mov     qword ptr [rsp+0C0h+dwDesiredAccess], r12; lpOverlapped
0x18017cc86  call    cs:__imp_WriteFile
0x18017cc8c  test    eax, eax
0x18017cc8e  jnz     short loc_18017CC43
0x18017cc90  jmp     loc_18017CC05
0x18017cc95  cmp     [rdi+2E8h], rbx
0x18017cc9c  jz      short loc_18017CCA8
0x18017cc9e  mov     ebx, 3EEh
0x18017cca3  jmp     loc_18017CE85
0x18017cca8  cmp     [rdi+2D0h], r13
0x18017ccaf  jz      loc_18017CD86
0x18017ccb5  call    GetThreadInfoUIType
0x18017ccba  cmp     byte ptr cs:Microsoft_Windows_WinINetEnableBits+2, r12b
0x18017ccc1  mov     ebx, eax
0x18017ccc3  mov     r14d, 4
0x18017ccc9  jge     short loc_18017CD00
0x18017cccb  cmp     [rdi+270h], r12
0x18017ccd2  lea     rdx, WININET_FILE_IO_START
0x18017ccd9  mov     r8, [rdi+80h]
0x18017cce0  mov     ecx, r12d
0x18017cce3  setnz   cl
0x18017cce6  mov     r9d, r14d
0x18017cce9  mov     [rsp+0C0h+dwOptions], ecx
0x18017cced  mov     ecx, cs:GlobalClientType
0x18017ccf3  mov     [rsp+0C0h+bInheritHandle], eax
0x18017ccf7  mov     [rsp+0C0h+dwDesiredAccess], ecx
0x18017ccfb  call    McTemplateU0pqqqt_EventWriteTransfer
0x18017cd00  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x18017cd04  call    cs:__imp_QueryPerformanceCounter
0x18017cd0a  mov     rcx, [rdi+2D0h]; hObject
0x18017cd11  call    cs:__imp_CloseHandle
0x18017cd17  lea     rcx, [rbp+57h+var_48]; lpPerformanceCount
0x18017cd1b  call    cs:__imp_QueryPerformanceCounter
0x18017cd21  cmp     byte ptr cs:Microsoft_Windows_WinINetEnableBits+2, r12b
0x18017cd28  jge     short loc_18017CD5F
0x18017cd2a  cmp     [rdi+270h], r12
0x18017cd31  lea     rdx, WININET_FILE_IO_STOP
0x18017cd38  mov     r8, [rdi+80h]
0x18017cd3f  mov     eax, r12d
0x18017cd42  setnz   al
0x18017cd45  mov     r9d, r14d
0x18017cd48  mov     [rsp+0C0h+dwOptions], eax
0x18017cd4c  mov     eax, cs:GlobalClientType
0x18017cd52  mov     [rsp+0C0h+bInheritHandle], ebx
0x18017cd56  mov     [rsp+0C0h+dwDesiredAccess], eax
0x18017cd5a  call    McTemplateU0pqqqt_EventWriteTransfer
0x18017cd5f  mov     rax, [rdi]
0x18017cd62  mov     r9d, ebx
0x18017cd65  mov     r8, qword ptr [rbp+57h+var_48]
0x18017cd69  mov     edx, r14d
0x18017cd6c  sub     r8, qword ptr [rbp+57h+PerformanceCount]
0x18017cd70  mov     rcx, rdi
0x18017cd73  mov     rax, [rax+0D8h]
0x18017cd7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017cd7f  mov     [rdi+2D0h], r13
0x18017cd86  mov     [rdi+4ECh], r12
0x18017cd8d  mov     [rdi+210h], r12
0x18017cd94  cmp     [rdi+2C8h], r12d
0x18017cd9b  jz      short loc_18017CDB4
0x18017cd9d  mov     rax, [rdi+2E8h]
0x18017cda4  mov     [rdi+310h], rax
0x18017cdab  mov     [rdi+1348h], r12
0x18017cdb2  jmp     short loc_18017CDEB
0x18017cdb4  mov     rcx, rdi; this
0x18017cdb7  call    ?IsReadRequest@HTTP_REQUEST_HANDLE_OBJECT@@QEAAHXZ; HTTP_REQUEST_HANDLE_OBJECT::IsReadRequest(void)
0x18017cdbc  test    eax, eax
0x18017cdbe  jz      short loc_18017CDEB
0x18017cdc0  test    dword ptr [rdi+142Ch], 800h
0x18017cdca  mov     rcx, [rdi+2E8h]
0x18017cdd1  mov     rax, [rdi+310h]
0x18017cdd8  mov     [rdi+310h], rcx
0x18017cddf  jz      short loc_18017CDEB
0x18017cde1  sub     rax, rcx
0x18017cde4  add     [rdi+1348h], rax
0x18017cdeb  mov     rcx, [rdi+330h]; hLockRequestInfo
0x18017cdf2  test    rcx, rcx
0x18017cdf5  jz      short loc_18017CE03
0x18017cdf7  call    InternetUnlockRequestFile
0x18017cdfc  mov     [rdi+330h], r12
0x18017ce03  cmp     [rdi+1510h], r12d
0x18017ce0a  jnz     short loc_18017CE42
0x18017ce0c  cmp     [rdi+2C8h], r12d
0x18017ce13  jnz     short loc_18017CE42
0x18017ce15  lea     rbx, [rdi+2B8h]
0x18017ce1c  mov     rcx, [rbx]; lpFileName
0x18017ce1f  call    cs:__imp_DeleteFileW
0x18017ce25  test    eax, eax
0x18017ce27  jnz     short loc_18017CE55
0x18017ce29  call    WxGetLastError
0x18017ce2e  cmp     eax, 5
0x18017ce31  jz      short loc_18017CE38
0x18017ce33  cmp     eax, 20h ; ' '
0x18017ce36  jnz     short loc_18017CE55
0x18017ce38  mov     rcx, [rbx]; unsigned __int16 *
0x18017ce3b  call    ?UrlCacheAddLeakFile@@YAKPEBG@Z; UrlCacheAddLeakFile(ushort const *)
0x18017ce40  jmp     short loc_18017CE55
0x18017ce42  mov     rcx, [rdi+2A0h]; lpszUrlName
0x18017ce49  call    DeleteUrlCacheEntryA
0x18017ce4e  lea     rbx, [rdi+2B8h]
0x18017ce55  mov     rcx, rdi; this
0x18017ce58  call    ?FreeCacheFileName@INTERNET_CONNECT_HANDLE_OBJECT@@QEAAXXZ; INTERNET_CONNECT_HANDLE_OBJECT::FreeCacheFileName(void)
0x18017ce5d  mov     [rbx], rsi
0x18017ce60  mov     rsi, r12
0x18017ce63  cmp     [rdi+2CCh], r12d
0x18017ce6a  jz      short loc_18017CE7B
0x18017ce6c  mov     rax, [rbp+57h+TargetHandle]
0x18017ce70  mov     [rdi+2D0h], rax
0x18017ce77  mov     [rbp+57h+TargetHandle], r13
0x18017ce7b  mov     ebx, r12d
0x18017ce7e  jmp     short loc_18017CED4
0x18017ce80  mov     ebx, 57h ; 'W'
0x18017ce85  mov     edx, 0C005h
0x18017ce8a  mov     rcx, rdi
0x18017ce8d  call    ?SetState@HTTP_REQUEST_HANDLE_OBJECT@@QEAAXW4HTTPREQ_STATE@@@Z; HTTP_REQUEST_HANDLE_OBJECT::SetState(HTTPREQ_STATE)
0x18017ce92  cmp     [rdi+2CCh], r12d
0x18017ce99  jz      short loc_18017CED4
0x18017ce9b  mov     [rsp+0C0h+var_68], r12d; int
0x18017cea0  or      r9d, 0FFFFFFFFh; unsigned int
0x18017cea4  mov     [rsp+0C0h+var_70], r12; struct CAppCacheHandle *
0x18017cea9  xor     r8d, r8d; struct _FILETIME *
0x18017ceac  mov     [rsp+0C0h+var_78], r12; char *
0x18017ceb1  xor     edx, edx; struct _FILETIME *
0x18017ceb3  mov     [rsp+0C0h+var_80], r12; unsigned __int8 *
0x18017ceb8  mov     rcx, rdi; this
0x18017cebb  mov     [rsp+0C0h+var_88], r12d; unsigned int
0x18017cec0  mov     qword ptr [rsp+0C0h+dwOptions], r12; unsigned __int8 *
0x18017cec5  mov     [rsp+0C0h+bInheritHandle], r12d; unsigned int
0x18017ceca  mov     [rsp+0C0h+dwDesiredAccess], r12d; unsigned int
0x18017cecf  call    ?EndCacheWrite@INTERNET_CONNECT_HANDLE_OBJECT@@QEAAKPEAU_FILETIME@@0KKKPEBEK1PEBDPEAVCAppCacheHandle@@H@Z; INTERNET_CONNECT_HANDLE_OBJECT::EndCacheWrite(_FILETIME *,_FILETIME *,ulong,ulong,ulong,uchar const *,ulong,uchar const *,char const *,CAppCacheHandle *,int)
0x18017ced4  mov     rcx, [rdi+2D8h]; hObject
0x18017cedb  cmp     rcx, r13
0x18017cede  jz      short loc_18017CEED
0x18017cee0  call    cs:__imp_CloseHandle
0x18017cee6  mov     [rdi+2D8h], r13
0x18017ceed  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x18017cef1  cmp     rcx, r13
0x18017cef4  jz      short loc_18017CF00
0x18017cef6  call    cs:__imp_CloseHandle
0x18017cefc  mov     [rbp+57h+TargetHandle], r13
0x18017cf00  test    rsi, rsi
0x18017cf03  jz      short loc_18017CF17
0x18017cf05  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18017cf0c  mov     r8, rsi; lpMem
0x18017cf0f  xor     edx, edx; dwFlags
0x18017cf11  call    cs:__imp_HeapFree
0x18017cf17  mov     eax, ebx
0x18017cf19  mov     rcx, [rbp+57h+var_38]
0x18017cf1d  xor     rcx, rsp; StackCookie
0x18017cf20  call    __security_check_cookie
0x18017cf25  mov     rbx, [rsp+0C0h+arg_18]
0x18017cf2d  add     rsp, 90h
0x18017cf34  pop     r15
0x18017cf36  pop     r14
0x18017cf38  pop     r13
0x18017cf3a  pop     r12
0x18017cf3c  pop     rdi
0x18017cf3d  pop     rsi
0x18017cf3e  pop     rbp
0x18017cf3f  retn
```
