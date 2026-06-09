# OutputMsg(void *,void *,ushort const *,...)

- ea: `0x140016bb4`
- end: `0x140016fa0`
- name: `?OutputMsg@@YAXPEAX0PEBGZZ`
- size: `1004`
- prototype: `void(HANDLE hFile, HANDLE hEvent, const unsigned __int16 *, ...)`
- caller_count: `46`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x140002770`
- `0x140005f7c`
- `0x140006110`
- `0x140006238`
- `0x140006e64`
- `0x140006ffc`
- `0x140007100`
- `0x1400072bc`
- `0x140007494`
- `0x1400076e8`
- `0x140007b94`
- `0x140008624`
- `0x140008de0`
- `0x140008f00`
- `0x140009020`
- `0x14000b1e4`
- `0x14000bccc`
- `0x14000bf54`
- `0x14000c40c`
- `0x14000d650`
- `0x14000e878`
- `0x140011400`
- `0x140011670`
- `0x140011770`
- `0x140011f98`
- `0x140012124`
- `0x140013894`
- `0x1400166d8`
- `0x140016fa8`
- `0x140018ccc`
- `0x1400192b0`
- `0x1400195dc`
- `0x140019830`
- `0x140019db4`
- `0x14001a000`
- `0x14001a41c`
- `0x14001a670`
- `0x14001ac60`
- `0x14001b310`
- `0x14001c624`
- `0x14001e1b0`
- `0x14001e7b0`
- `0x14001ec90`
- `0x140020498`
- `0x14002066c`
- `0x140021744`

## callees

- `0x1400076c8`
- `0x14000e494`
- `0x14000e5d4`
- `0x1400135b8`
- `0x140016bb4`
- `0x14001d4ac`
- `0x140020e78`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x140016c91`
- `KERNEL32!ResetEvent` at `0x140016c91`
- `KERNEL32!GetOverlappedResult` at `0x140016d24`
- `KERNEL32!GetOverlappedResult` at `0x140016d24`
- `KERNEL32!SetFilePointerEx` at `0x140016dae`
- `KERNEL32!SetFilePointerEx` at `0x140016dae`
- `KERNEL32!LockFileEx` at `0x140016cea`
- `KERNEL32!LockFileEx` at `0x140016cea`
- `KERNEL32!FlushFileBuffers` at `0x140016d8c`
- `KERNEL32!FlushFileBuffers` at `0x140016e6e`
- `KERNEL32!FlushFileBuffers` at `0x140016d8c`
- `KERNEL32!FlushFileBuffers` at `0x140016e6e`
- `KERNEL32!HeapFree` at `0x140016ef0`
- `KERNEL32!HeapFree` at `0x140016f24`
- `KERNEL32!HeapFree` at `0x140016f58`
- `KERNEL32!HeapFree` at `0x140016ef0`
- `KERNEL32!HeapFree` at `0x140016f24`
- `KERNEL32!HeapFree` at `0x140016f58`
- `KERNEL32!GetProcessHeap` at `0x140016edb`
- `KERNEL32!GetProcessHeap` at `0x140016f10`
- `KERNEL32!GetProcessHeap` at `0x140016f44`
- `KERNEL32!GetProcessHeap` at `0x140016edb`
- `KERNEL32!GetProcessHeap` at `0x140016f10`
- `KERNEL32!GetProcessHeap` at `0x140016f44`
- `KERNEL32!GetLastError` at `0x140016ca1`
- `KERNEL32!GetLastError` at `0x140016cfa`
- `KERNEL32!GetLastError` at `0x140016e7e`
- `KERNEL32!GetLastError` at `0x140016ca1`
- `KERNEL32!GetLastError` at `0x140016cfa`
- `KERNEL32!GetLastError` at `0x140016e7e`
- `KERNEL32!GetFileSizeEx` at `0x140016d45`
- `KERNEL32!GetFileSizeEx` at `0x140016d45`
- `KERNEL32!UnlockFileEx` at `0x140016ec3`
- `KERNEL32!UnlockFileEx` at `0x140016ec3`
- `KERNEL32!LeaveCriticalSection` at `0x140016f79`
- `KERNEL32!LeaveCriticalSection` at `0x140016f79`
- `KERNEL32!WriteFile` at `0x140016d75`
- `KERNEL32!WriteFile` at `0x140016d75`
- `KERNEL32!EnterCriticalSection` at `0x140016be2`
- `KERNEL32!EnterCriticalSection` at `0x140016be2`

## pseudocode

```c
void OutputMsg(HANDLE hFile, HANDLE hEvent, const unsigned __int16 *a3, ...)
{
  const WCHAR *v5; // r13
  unsigned int v6; // r15d
  int v7; // r12d
  int v8; // ecx
  signed int v9; // edi
  int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  int v13; // eax
  int v14; // esi
  int v15; // eax
  int v16; // ecx
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  void *v19; // rdi
  HANDLE v20; // rax
  unsigned __int16 *v21; // rdi
  HANDLE v22; // rax
  struct _OVERLAPPED *nNumberOfBytesToLockHigh; // [rsp+20h] [rbp-59h]
  __int16 Buffer; // [rsp+30h] [rbp-49h] BYREF
  char v25; // [rsp+32h] [rbp-47h]
  DWORD NumberOfBytesWritten; // [rsp+34h] [rbp-45h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+38h] [rbp-41h] BYREF
  LPCWCH lpWideCharStr; // [rsp+40h] [rbp-39h] BYREF
  __int64 v29; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v30; // [rsp+50h] [rbp-29h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+58h] [rbp-21h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+60h] [rbp-19h] BYREF
  int v33; // [rsp+90h] [rbp+17h]
  va_list va; // [rsp+F8h] [rbp+7Fh] BYREF

  va_start(va, a3);
  EnterCriticalSection(&stru_1400A5E60);
  v5 = 0;
  v33 = 1;
  v6 = 0;
  v30 = 0;
  v7 = 0;
  v29 = 0;
  lpWideCharStr = 0;
  FileSize.QuadPart = 0;
  NumberOfBytesWritten = 0;
  NumberOfBytesTransferred = 0;
  Buffer = -17425;
  v25 = -65;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( !hFile || !a3 )
  {
    v8 = -2147024809;
    v9 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_49;
  }
  v10 = CDlpHelpersT<CEmptyType>::FormatSystemTime(&v30);
  v9 = v10;
  if ( v10 < 0
    || (v10 = CImmutableStringsExT<unsigned short,CImmutableStringsPolicyDefault>::FormatV(&v29, a3, (__int64 *)va),
        v9 = v10,
        v10 < 0) )
  {
    v8 = v10;
    goto LABEL_3;
  }
  if ( !hEvent )
    goto LABEL_19;
  Overlapped.hEvent = hEvent;
  if ( !ResetEvent(hEvent) )
    goto LABEL_10;
  if ( LockFileEx(hFile, 2u, 0, 3u, 0, &Overlapped) )
  {
LABEL_18:
    v7 = 1;
LABEL_19:
    if ( GetFileSizeEx(hFile, &FileSize)
      && (FileSize.QuadPart || WriteFile(hFile, &Buffer, 3u, &NumberOfBytesWritten, 0) && FlushFileBuffers(hFile))
      && SetFilePointerEx(hFile, 0, 0, 2u) )
    {
      v13 = STRAPI_Format((unsigned __int16 **)&lpWideCharStr, L"%s: %s\r\n", v30, v29);
      v9 = v13;
      if ( v13 < 0 )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
        v5 = lpWideCharStr;
        goto LABEL_47;
      }
      v5 = lpWideCharStr;
      if ( lpWideCharStr )
        v14 = *((_DWORD *)lpWideCharStr - 1);
      else
        v14 = 0;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v9 = 0;
      if ( v14 )
      {
        if ( (unsigned int)(2 * v14) >> 1 == v14 )
        {
          v6 = 2 * v14;
        }
        else
        {
          v9 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
        }
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v9);
      if ( v9 < 0 )
        goto LABEL_45;
      v15 = WriteFileMultiByte(hFile, v5, v6, &NumberOfBytesWritten, nNumberOfBytesToLockHigh);
      v9 = v15;
      if ( v15 < 0 )
      {
        v16 = v15;
LABEL_46:
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v16);
LABEL_47:
        if ( v7 )
          UnlockFileEx(hFile, 0, 3u, 0, &Overlapped);
        goto LABEL_49;
      }
      if ( FlushFileBuffers(hFile) )
        goto LABEL_47;
    }
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v9 = -2147467259;
    }
LABEL_45:
    v16 = v9;
    goto LABEL_46;
  }
  v12 = GetLastError();
  v9 = v12;
  if ( v12 == 997 )
  {
    if ( !GetOverlappedResult(hFile, &Overlapped, &NumberOfBytesTransferred, 1) )
    {
LABEL_10:
      v11 = GetLastError();
      v9 = v11;
      if ( v11 )
      {
        if ( v11 > 0 )
          v9 = (unsigned __int16)v11 | 0x80070000;
      }
      else
      {
        v9 = -2147467259;
      }
LABEL_14:
      v8 = v9;
      goto LABEL_3;
    }
    goto LABEL_18;
  }
  if ( v12 > 0 )
    v9 = (unsigned __int16)v12 | 0x80070000;
  if ( v9 < 0 )
    goto LABEL_14;
LABEL_49:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v9);
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v5 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v29 )
  {
    v19 = (void *)(v29 - 4);
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v19);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v30 )
  {
    v21 = v30 - 2;
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v21);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v33 )
    LeaveCriticalSection(&stru_1400A5E60);
}

```

## disassembly

```asm
0x140016bb4  mov     [rsp-8+arg_10], r8
0x140016bb9  mov     [rsp-8+arg_18], r9
0x140016bbe  push    rbp
0x140016bbf  push    rsi
0x140016bc0  push    rdi
0x140016bc1  push    r12
0x140016bc3  push    r13
0x140016bc5  push    r14
0x140016bc7  push    r15
0x140016bc9  lea     rbp, [rsp-27h]
0x140016bce  sub     rsp, 0A0h
0x140016bd5  mov     r14, rcx
0x140016bd8  mov     rsi, rdx
0x140016bdb  lea     rcx, stru_1400A5E60; lpCriticalSection
0x140016be2  call    cs:__imp_EnterCriticalSection
0x140016be9  nop     dword ptr [rax+rax+00h]
0x140016bee  xor     r13d, r13d
0x140016bf1  mov     qword ptr [rbp+57h+FileSize], 0
0x140016bf9  xorps   xmm0, xmm0
0x140016bfc  mov     [rbp+57h+var_40], 1
0x140016c03  xor     r15d, r15d
0x140016c06  mov     [rbp+57h+var_80], 0
0x140016c0e  xor     r12d, r12d
0x140016c11  mov     [rbp+57h+var_88], 0
0x140016c19  mov     [rbp+57h+lpWideCharStr], r13
0x140016c1d  mov     qword ptr [rbp+57h+FileSize], r13
0x140016c21  mov     [rbp+57h+NumberOfBytesWritten], r13d
0x140016c25  mov     [rbp+57h+NumberOfBytesTransferred], r13d
0x140016c29  mov     [rbp+57h+Buffer], 0BBEFh
0x140016c2f  mov     [rbp+57h+var_9E], 0BFh
0x140016c33  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x140016c37  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x140016c3b  test    r14, r14
0x140016c3e  jnz     short loc_140016C51
0x140016c40  mov     ecx, 80070057h
0x140016c45  mov     edi, ecx
0x140016c47  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140016c4c  jmp     loc_140016ECF
0x140016c51  cmp     [rbp+57h+arg_10], r12
0x140016c55  jz      short loc_140016C40
0x140016c57  lea     rcx, [rbp+57h+var_80]; unsigned __int16 **
0x140016c5b  call    ?FormatSystemTime@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z; CDlpHelpersT<CEmptyType>::FormatSystemTime(ushort * *)
0x140016c60  mov     edi, eax
0x140016c62  test    eax, eax
0x140016c64  jns     short loc_140016C6A
0x140016c66  mov     ecx, eax
0x140016c68  jmp     short loc_140016C47
0x140016c6a  mov     rdx, [rbp+57h+arg_10]
0x140016c6e  lea     r8, [rbp+57h+arg_18]
0x140016c72  lea     rcx, [rbp+57h+var_88]
0x140016c76  call    ?FormatV@?$CImmutableStringsExT@GVCImmutableStringsPolicyDefault@@@@SAJPEAPEAGPEBGPEAD@Z; CImmutableStringsExT<ushort,CImmutableStringsPolicyDefault>::FormatV(ushort * *,ushort const *,char *)
0x140016c7b  mov     edi, eax
0x140016c7d  test    eax, eax
0x140016c7f  js      short loc_140016C66
0x140016c81  test    rsi, rsi
0x140016c84  jz      loc_140016D3E
0x140016c8a  mov     rcx, rsi; hEvent
0x140016c8d  mov     [rbp+57h+Overlapped.hEvent], rsi
0x140016c91  call    cs:__imp_ResetEvent
0x140016c98  nop     dword ptr [rax+rax+00h]
0x140016c9d  test    eax, eax
0x140016c9f  jnz     short loc_140016CCC
0x140016ca1  call    cs:__imp_GetLastError
0x140016ca8  nop     dword ptr [rax+rax+00h]
0x140016cad  mov     edi, eax
0x140016caf  test    eax, eax
0x140016cb1  jnz     short loc_140016CBA
0x140016cb3  mov     edi, 80004005h
0x140016cb8  jmp     short loc_140016CC5
0x140016cba  jle     short loc_140016CC5
0x140016cbc  movzx   edi, ax
0x140016cbf  or      edi, 80070000h
0x140016cc5  mov     ecx, edi
0x140016cc7  jmp     loc_140016C47
0x140016ccc  mov     r9d, 3; nNumberOfBytesToLockLow
0x140016cd2  lea     rax, [rbp+57h+Overlapped]
0x140016cd6  mov     [rsp+0D0h+lpOverlapped], rax; lpOverlapped
0x140016cdb  xor     r8d, r8d; dwReserved
0x140016cde  mov     rcx, r14; hFile
0x140016ce1  mov     [rsp+0D0h+nNumberOfBytesToLockHigh], r12d; nNumberOfBytesToLockHigh
0x140016ce6  lea     edx, [r9-1]; dwFlags
0x140016cea  call    cs:__imp_LockFileEx
0x140016cf1  nop     dword ptr [rax+rax+00h]
0x140016cf6  test    eax, eax
0x140016cf8  jnz     short loc_140016D38
0x140016cfa  call    cs:__imp_GetLastError
0x140016d01  nop     dword ptr [rax+rax+00h]
0x140016d06  mov     edi, eax
0x140016d08  cmp     eax, 3E5h
0x140016d0d  jnz     loc_140016DF0
0x140016d13  mov     r9d, 1; bWait
0x140016d19  lea     r8, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x140016d1d  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x140016d21  mov     rcx, r14; hFile
0x140016d24  call    cs:__imp_GetOverlappedResult
0x140016d2b  nop     dword ptr [rax+rax+00h]
0x140016d30  test    eax, eax
0x140016d32  jz      loc_140016CA1
0x140016d38  mov     r12d, 1
0x140016d3e  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x140016d42  mov     rcx, r14; hFile
0x140016d45  call    cs:__imp_GetFileSizeEx
0x140016d4c  nop     dword ptr [rax+rax+00h]
0x140016d51  test    eax, eax
0x140016d53  jz      loc_140016E7E
0x140016d59  cmp     qword ptr [rbp+57h+FileSize], r13
0x140016d5d  jnz     short loc_140016DA0
0x140016d5f  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140016d63  mov     qword ptr [rsp+0D0h+nNumberOfBytesToLockHigh], r13; struct _OVERLAPPED *
0x140016d68  mov     r8d, 3; nNumberOfBytesToWrite
0x140016d6e  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x140016d72  mov     rcx, r14; hFile
0x140016d75  call    cs:__imp_WriteFile
0x140016d7c  nop     dword ptr [rax+rax+00h]
0x140016d81  test    eax, eax
0x140016d83  jz      loc_140016E7E
0x140016d89  mov     rcx, r14; hFile
0x140016d8c  call    cs:__imp_FlushFileBuffers
0x140016d93  nop     dword ptr [rax+rax+00h]
0x140016d98  test    eax, eax
0x140016d9a  jz      loc_140016E7E
0x140016da0  mov     r9d, 2; dwMoveMethod
0x140016da6  xor     r8d, r8d; lpNewFilePointer
0x140016da9  xor     edx, edx; liDistanceToMove
0x140016dab  mov     rcx, r14; hFile
0x140016dae  call    cs:__imp_SetFilePointerEx
0x140016db5  nop     dword ptr [rax+rax+00h]
0x140016dba  test    eax, eax
0x140016dbc  jz      loc_140016E7E
0x140016dc2  mov     r9, [rbp+57h+var_88]
0x140016dc6  lea     rdx, aSS_4; "%s: %s\r\n"
0x140016dcd  mov     r8, [rbp+57h+var_80]
0x140016dd1  lea     rcx, [rbp+57h+lpWideCharStr]; unsigned __int16 **
0x140016dd5  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x140016dda  mov     edi, eax
0x140016ddc  test    eax, eax
0x140016dde  jns     short loc_140016E0A
0x140016de0  mov     ecx, eax
0x140016de2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140016de7  mov     r13, [rbp+57h+lpWideCharStr]
0x140016deb  jmp     loc_140016EA9
0x140016df0  test    eax, eax
0x140016df2  jle     short loc_140016DFD
0x140016df4  movzx   edi, ax
0x140016df7  or      edi, 80070000h
0x140016dfd  test    edi, edi
0x140016dff  jns     loc_140016ECF
0x140016e05  jmp     loc_140016CC5
0x140016e0a  mov     r13, [rbp+57h+lpWideCharStr]
0x140016e0e  test    r13, r13
0x140016e11  jz      short loc_140016E19
0x140016e13  mov     esi, [r13-4]
0x140016e17  jmp     short loc_140016E1B
0x140016e19  xor     esi, esi
0x140016e1b  xor     ecx, ecx
0x140016e1d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140016e22  xor     edi, edi
0x140016e24  test    esi, esi
0x140016e26  jz      short loc_140016E44
0x140016e28  lea     ecx, [rsi+rsi]
0x140016e2b  mov     eax, ecx
0x140016e2d  shr     eax, 1
0x140016e2f  cmp     eax, esi
0x140016e31  jz      short loc_140016E41
0x140016e33  mov     edi, 80070216h
0x140016e38  mov     ecx, edi
0x140016e3a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140016e3f  jmp     short loc_140016E44
0x140016e41  mov     r15d, ecx
0x140016e44  mov     ecx, edi
0x140016e46  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140016e4b  test    edi, edi
0x140016e4d  js      short loc_140016EA2
0x140016e4f  lea     r9, [rbp+57h+NumberOfBytesWritten]; unsigned int *
0x140016e53  mov     r8d, r15d; unsigned int
0x140016e56  mov     rdx, r13; lpWideCharStr
0x140016e59  mov     rcx, r14; hFile
0x140016e5c  call    ?WriteFileMultiByte@@YAJPEAXPEAGKPEAKPEAU_OVERLAPPED@@@Z; WriteFileMultiByte(void *,ushort *,ulong,ulong *,_OVERLAPPED *)
0x140016e61  mov     edi, eax
0x140016e63  test    eax, eax
0x140016e65  jns     short loc_140016E6B
0x140016e67  mov     ecx, eax
0x140016e69  jmp     short loc_140016EA4
0x140016e6b  mov     rcx, r14; hFile
0x140016e6e  call    cs:__imp_FlushFileBuffers
0x140016e75  nop     dword ptr [rax+rax+00h]
0x140016e7a  test    eax, eax
0x140016e7c  jnz     short loc_140016EA9
0x140016e7e  call    cs:__imp_GetLastError
0x140016e85  nop     dword ptr [rax+rax+00h]
0x140016e8a  mov     edi, eax
0x140016e8c  test    eax, eax
0x140016e8e  jnz     short loc_140016E97
0x140016e90  mov     edi, 80004005h
0x140016e95  jmp     short loc_140016EA2
0x140016e97  jle     short loc_140016EA2
0x140016e99  movzx   edi, ax
0x140016e9c  or      edi, 80070000h
0x140016ea2  mov     ecx, edi
0x140016ea4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140016ea9  test    r12d, r12d
0x140016eac  jz      short loc_140016ECF
0x140016eae  xor     r9d, r9d; nNumberOfBytesToUnlockHigh
0x140016eb1  lea     rax, [rbp+57h+Overlapped]
0x140016eb5  xor     edx, edx; dwReserved
0x140016eb7  mov     qword ptr [rsp+0D0h+nNumberOfBytesToLockHigh], rax; lpOverlapped
0x140016ebc  mov     rcx, r14; hFile
0x140016ebf  lea     r8d, [r9+3]; nNumberOfBytesToUnlockLow
0x140016ec3  call    cs:__imp_UnlockFileEx
0x140016eca  nop     dword ptr [rax+rax+00h]
0x140016ecf  mov     ecx, edi
0x140016ed1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140016ed6  test    r13, r13
0x140016ed9  jz      short loc_140016F03
0x140016edb  call    cs:__imp_GetProcessHeap
0x140016ee2  nop     dword ptr [rax+rax+00h]
0x140016ee7  lea     r8, [r13-4]; lpMem
0x140016eeb  xor     edx, edx; dwFlags
0x140016eed  mov     rcx, rax; hHeap
0x140016ef0  call    cs:__imp_HeapFree
0x140016ef7  nop     dword ptr [rax+rax+00h]
0x140016efc  xor     ecx, ecx
0x140016efe  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140016f03  mov     rax, [rbp+57h+var_88]
0x140016f07  test    rax, rax
0x140016f0a  jz      short loc_140016F37
0x140016f0c  lea     rdi, [rax-4]
0x140016f10  call    cs:__imp_GetProcessHeap
0x140016f17  nop     dword ptr [rax+rax+00h]
0x140016f1c  mov     r8, rdi; lpMem
0x140016f1f  xor     edx, edx; dwFlags
0x140016f21  mov     rcx, rax; hHeap
0x140016f24  call    cs:__imp_HeapFree
0x140016f2b  nop     dword ptr [rax+rax+00h]
0x140016f30  xor     ecx, ecx
0x140016f32  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140016f37  mov     rax, [rbp+57h+var_80]
0x140016f3b  test    rax, rax
0x140016f3e  jz      short loc_140016F6B
0x140016f40  lea     rdi, [rax-4]
0x140016f44  call    cs:__imp_GetProcessHeap
0x140016f4b  nop     dword ptr [rax+rax+00h]
0x140016f50  mov     r8, rdi; lpMem
0x140016f53  xor     edx, edx; dwFlags
0x140016f55  mov     rcx, rax; hHeap
0x140016f58  call    cs:__imp_HeapFree
0x140016f5f  nop     dword ptr [rax+rax+00h]
0x140016f64  xor     ecx, ecx
0x140016f66  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140016f6b  mov     eax, [rbp+57h+var_40]
0x140016f6e  test    eax, eax
0x140016f70  jz      short loc_140016F8C
0x140016f72  lea     rcx, stru_1400A5E60; lpCriticalSection
0x140016f79  call    cs:__imp_LeaveCriticalSection
0x140016f80  nop     dword ptr [rax+rax+00h]
0x140016f85  mov     [rbp+57h+var_40], 0
0x140016f8c  add     rsp, 0A0h
0x140016f93  pop     r15
0x140016f95  pop     r14
0x140016f97  pop     r13
0x140016f99  pop     r12
0x140016f9b  pop     rdi
0x140016f9c  pop     rsi
0x140016f9d  pop     rbp
0x140016f9e  retn
```
