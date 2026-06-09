# ConvertUtf16ToUtf8(void *)

- ea: `0x140007dd4`
- end: `0x14000842e`
- name: `?ConvertUtf16ToUtf8@@YAJPEAX@Z`
- size: `1626`
- prototype: `__int64 __fastcall(HANDLE hEvent, __int64, __int64, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140021744`

## callees

- `0x1400076c8`
- `0x140007cb0`
- `0x140007dd4`
- `0x14000a074`
- `0x140010d84`
- `0x1400135b8`
- `0x140020e78`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140007f72`
- `KERNEL32!CloseHandle` at `0x140007f8b`
- `KERNEL32!CloseHandle` at `0x1400082d7`
- `KERNEL32!CloseHandle` at `0x140007f72`
- `KERNEL32!CloseHandle` at `0x140007f8b`
- `KERNEL32!CloseHandle` at `0x1400082d7`
- `KERNEL32!ResetEvent` at `0x140007fb5`
- `KERNEL32!ResetEvent` at `0x140007fb5`
- `KERNEL32!GetOverlappedResult` at `0x140008068`
- `KERNEL32!GetOverlappedResult` at `0x140008068`
- `KERNEL32!SetFilePointerEx` at `0x140008164`
- `KERNEL32!SetFilePointerEx` at `0x140008225`
- `KERNEL32!SetFilePointerEx` at `0x140008164`
- `KERNEL32!SetFilePointerEx` at `0x140008225`
- `KERNEL32!ReplaceFileW` at `0x14000838c`
- `KERNEL32!ReplaceFileW` at `0x14000838c`
- `KERNEL32!LockFileEx` at `0x140008025`
- `KERNEL32!LockFileEx` at `0x140008025`
- `KERNEL32!HeapFree` at `0x140007e98`
- `KERNEL32!HeapFree` at `0x140007ec5`
- `KERNEL32!HeapFree` at `0x140007ef9`
- `KERNEL32!HeapFree` at `0x140007f2d`
- `KERNEL32!HeapFree` at `0x140007f59`
- `KERNEL32!HeapFree` at `0x140007e98`
- `KERNEL32!HeapFree` at `0x140007ec5`
- `KERNEL32!HeapFree` at `0x140007ef9`
- `KERNEL32!HeapFree` at `0x140007f2d`
- `KERNEL32!HeapFree` at `0x140007f59`
- `KERNEL32!HeapAlloc` at `0x14000812f`
- `KERNEL32!HeapAlloc` at `0x14000812f`
- `KERNEL32!GetProcessHeap` at `0x140007e83`
- `KERNEL32!GetProcessHeap` at `0x140007eb0`
- `KERNEL32!GetProcessHeap` at `0x140007ee5`
- `KERNEL32!GetProcessHeap` at `0x140007f19`
- `KERNEL32!GetProcessHeap` at `0x140007f45`
- `KERNEL32!GetProcessHeap` at `0x14000811b`
- `KERNEL32!GetProcessHeap` at `0x140007e83`
- `KERNEL32!GetProcessHeap` at `0x140007eb0`
- `KERNEL32!GetProcessHeap` at `0x140007ee5`
- `KERNEL32!GetProcessHeap` at `0x140007f19`
- `KERNEL32!GetProcessHeap` at `0x140007f45`
- `KERNEL32!GetProcessHeap` at `0x14000811b`
- `KERNEL32!GetLastError` at `0x140007fc5`
- `KERNEL32!GetLastError` at `0x140008035`
- `KERNEL32!GetLastError` at `0x1400080a1`
- `KERNEL32!GetLastError` at `0x14000839c`
- `KERNEL32!GetLastError` at `0x140007fc5`
- `KERNEL32!GetLastError` at `0x140008035`
- `KERNEL32!GetLastError` at `0x1400080a1`
- `KERNEL32!GetLastError` at `0x14000839c`
- `KERNEL32!ReadFile` at `0x140008199`
- `KERNEL32!ReadFile` at `0x140008199`
- `KERNEL32!GetFileSizeEx` at `0x140008091`
- `KERNEL32!GetFileSizeEx` at `0x140008091`
- `KERNEL32!UnlockFileEx` at `0x14000841d`
- `KERNEL32!UnlockFileEx` at `0x14000841d`
- `KERNEL32!SetEndOfFile` at `0x1400082b6`
- `KERNEL32!SetEndOfFile` at `0x1400082b6`
- `KERNEL32!WriteFile` at `0x14000825d`
- `KERNEL32!WriteFile` at `0x14000825d`

## pseudocode

```c
__int64 __fastcall ConvertUtf16ToUtf8(HANDLE hEvent, __int64 a2, __int64 a3, struct _SECURITY_ATTRIBUTES *a4)
{
  _BYTE *v4; // rsi
  __int64 v5; // rdi
  LPCWSTR v7; // r13
  int v8; // eax
  unsigned __int64 v9; // r14
  unsigned int v10; // r12d
  int v11; // ecx
  HANDLE v12; // rax
  void *v13; // r15
  HANDLE v14; // rax
  void *v15; // r15
  HANDLE v16; // rax
  HANDLE v17; // rax
  signed int v19; // eax
  void *v20; // rcx
  signed int LastError; // eax
  signed int v22; // eax
  int v23; // ecx
  DWORD LowPart; // esi
  HANDLE ProcessHeap; // rax
  struct _SECURITY_ATTRIBUTES *v26; // r9
  int v27; // eax
  int WindowsPath; // eax
  __int64 v29; // r15
  int v30; // eax
  signed int v31; // eax
  struct _OVERLAPPED *nNumberOfBytesToLockHigh; // [rsp+20h] [rbp-59h]
  unsigned int lpOverlapped; // [rsp+28h] [rbp-51h]
  unsigned int lpOverlappeda; // [rsp+28h] [rbp-51h]
  void *v35; // [rsp+30h] [rbp-49h]
  void *v36; // [rsp+30h] [rbp-49h]
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-31h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-29h] BYREF
  LPCWSTR lpReplacementFileName; // [rsp+58h] [rbp-21h]
  HANDLE v40; // [rsp+60h] [rbp-19h] BYREF
  __int64 v41; // [rsp+68h] [rbp-11h]
  __int64 v42; // [rsp+70h] [rbp-9h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+78h] [rbp-1h] BYREF
  _BYTE Buffer[3]; // [rsp+E8h] [rbp+6Fh] BYREF
  DWORD NumberOfBytesRead; // [rsp+F0h] [rbp+77h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+F8h] [rbp+7Fh] BYREF

  FileSize.QuadPart = 0;
  v4 = 0;
  hObject = (HANDLE)-1LL;
  v5 = -1;
  v40 = (HANDLE)-1LL;
  NumberOfBytesWritten = 0;
  v42 = 0;
  v7 = 0;
  v41 = 0;
  lpReplacementFileName = 0;
  NumberOfBytesRead = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  *(_WORD *)Buffer = -17425;
  Buffer[2] = -65;
  v8 = CreateLogFileInternal(L"BlueBox.log", 0x80000000, 7u, a4, 4u, lpOverlapped, v35, &hObject);
  v9 = (unsigned __int64)hObject;
  v10 = v8;
  if ( v8 < 0 )
  {
    v11 = v8;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
    goto LABEL_4;
  }
  Overlapped.hEvent = hEvent;
  if ( !ResetEvent(hEvent) )
    goto LABEL_18;
  v20 = 0;
  if ( v9 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    v20 = (void *)v9;
  if ( LockFileEx(v20, 2u, 0, 3u, 0, &Overlapped) )
    goto LABEL_28;
  LastError = GetLastError();
  LODWORD(hObject) = 0;
  if ( LastError == 997 )
  {
    if ( !GetOverlappedResult(
            (HANDLE)(v9 & -(__int64)(((v9 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
            &Overlapped,
            (LPDWORD)&hObject,
            1) )
    {
LABEL_18:
      v19 = GetLastError();
      v10 = v19;
      if ( v19 )
      {
        if ( v19 > 0 )
          v10 = (unsigned __int16)v19 | 0x80070000;
      }
      else
      {
        v10 = -2147467259;
      }
      goto LABEL_22;
    }
LABEL_28:
    if ( !GetFileSizeEx((HANDLE)(v9 & -(__int64)(((v9 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)), &FileSize) )
      goto LABEL_29;
    if ( FileSize.QuadPart <= 0 )
    {
      v10 = 0;
      v23 = 0;
      goto LABEL_74;
    }
    if ( FileSize.QuadPart > 4uLL && !FileSize.HighPart )
    {
      LowPart = FileSize.LowPart;
      ProcessHeap = GetProcessHeap();
      v4 = HeapAlloc(ProcessHeap, 0, LowPart);
      if ( !v4 )
      {
        v10 = -2147024882;
LABEL_38:
        v23 = v10;
LABEL_74:
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v23);
        goto LABEL_75;
      }
      if ( !SetFilePointerEx((HANDLE)(v9 & -(__int64)(((v9 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)), 0, 0, 0)
        || !ReadFile(
              (HANDLE)(v9 & -(__int64)(((v9 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
              v4,
              FileSize.LowPart,
              &NumberOfBytesRead,
              0) )
      {
        goto LABEL_29;
      }
      if ( NumberOfBytesRead == FileSize.LowPart )
      {
        if ( *v4 == 0xFF && v4[1] == 0xFE )
        {
          v27 = CreateLogFileInternal(L"BlueBox2.log", 0xC0000000, 0, v26, 2u, lpOverlappeda, v36, &v40);
          v10 = v27;
          if ( v27 < 0 )
          {
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v27);
            v5 = (__int64)v40;
LABEL_75:
            UnlockFileEx((HANDLE)(v9 & -(__int64)(((v9 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)), 0, 3u, 0, &Overlapped);
            goto LABEL_4;
          }
          v5 = (__int64)v40;
          if ( !SetFilePointerEx(
                  (HANDLE)((unsigned __int64)v40 & -(__int64)((((unsigned __int64)v40 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
                  0,
                  0,
                  0)
            || !WriteFile(
                  (HANDLE)(v5 & -(__int64)(((v5 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
                  Buffer,
                  3u,
                  &NumberOfBytesWritten,
                  0) )
          {
            goto LABEL_29;
          }
          WindowsPath = WriteFileMultiByte(
                          (HANDLE)(v5 & -(__int64)(((v5 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
                          (LPCWCH)v4 + 1,
                          FileSize.LowPart - 2,
                          &NumberOfBytesWritten,
                          nNumberOfBytesToLockHigh);
          v10 = WindowsPath;
          if ( WindowsPath < 0 )
          {
LABEL_55:
            v23 = WindowsPath;
            goto LABEL_74;
          }
          if ( SetEndOfFile((HANDLE)(v5 & -(__int64)(((v5 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0))) )
          {
            if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            {
              CloseHandle((HANDLE)v5);
              v5 = -1;
            }
            WindowsPath = CDlpHelpersT<CEmptyType>::GetWindowsPath(&v42);
            v10 = WindowsPath;
            if ( WindowsPath >= 0 )
            {
              WindowsPath = CMiscHelpersT<CEmptyType>::CombinePath(v42, (__int64)L"Logs\\MoSetup", 0);
              v10 = WindowsPath;
              if ( WindowsPath >= 0 )
              {
                v29 = v41;
                v30 = CMiscHelpersT<CEmptyType>::CombinePath(v41, (__int64)L"BlueBox2.log", 0);
                v10 = v30;
                if ( v30 < 0
                  || (v30 = CMiscHelpersT<CEmptyType>::CombinePath(v29, (__int64)L"BlueBox.log", 0), v10 = v30, v30 < 0) )
                {
                  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v30);
                  v7 = lpReplacementFileName;
                }
                else
                {
                  v7 = lpReplacementFileName;
                  if ( !ReplaceFileW(0, lpReplacementFileName, 0, 3u, 0, 0) )
                  {
                    v31 = GetLastError();
                    v10 = v31;
                    if ( v31 )
                    {
                      if ( v31 > 0 )
                        v10 = (unsigned __int16)v31 | 0x80070000;
                    }
                    else
                    {
                      v10 = -2147467259;
                    }
                    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
                  }
                }
                goto LABEL_75;
              }
            }
            goto LABEL_55;
          }
LABEL_29:
          v22 = GetLastError();
          v10 = v22;
          if ( v22 )
          {
            if ( v22 > 0 )
              v10 = (unsigned __int16)v22 | 0x80070000;
          }
          else
          {
            v10 = -2147467259;
          }
          goto LABEL_38;
        }
        if ( FileSize.QuadPart >= 3uLL && *v4 == Buffer[0] && *(_WORD *)(v4 + 1) == *(_WORD *)&Buffer[1] )
          goto LABEL_75;
      }
    }
    v23 = -2147418113;
    v10 = -2147418113;
    goto LABEL_74;
  }
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  else
    v10 = LastError;
  if ( (v10 & 0x80000000) != 0 )
  {
LABEL_22:
    v11 = v10;
    goto LABEL_3;
  }
LABEL_4:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
  if ( v7 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, (LPVOID)(v7 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v41 )
  {
    v13 = (void *)(v41 - 4);
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v13);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v42 )
  {
    v15 = (void *)(v42 - 4);
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v15);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v4 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v4);
  }
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v5);
  if ( v9 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v9);
  return v10;
}

```

## disassembly

```asm
0x140007dd4  push    rbp
0x140007dd6  push    rsi
0x140007dd7  push    rdi
0x140007dd8  push    r12
0x140007dda  push    r13
0x140007ddc  push    r14
0x140007dde  push    r15
0x140007de0  lea     rbp, [rsp-27h]
0x140007de5  sub     rsp, 0A0h
0x140007dec  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007df0  mov     qword ptr [rbp+57h+FileSize], 0
0x140007df8  xor     esi, esi
0x140007dfa  mov     [rbp+57h+hObject], rax
0x140007dfe  mov     rdi, rax
0x140007e01  mov     [rbp+57h+var_70], rax
0x140007e05  xorps   xmm0, xmm0
0x140007e08  mov     [rbp+57h+NumberOfBytesWritten], esi
0x140007e0b  lea     rax, [rbp+57h+hObject]
0x140007e0f  mov     [rbp+57h+var_60], rsi
0x140007e13  mov     r15, rcx
0x140007e16  mov     [rsp+0D0h+var_98], rax; void **
0x140007e1b  xor     r13d, r13d
0x140007e1e  mov     [rbp+57h+var_68], rsi
0x140007e22  lea     r8d, [rdi+8]; unsigned int
0x140007e26  mov     [rbp+57h+lpReplacementFileName], r13
0x140007e2a  mov     edx, 80000000h; unsigned int
0x140007e2f  mov     [rbp+57h+lpReplacedFileName], rsi
0x140007e33  lea     rcx, aBlueboxLog; "BlueBox.log"
0x140007e3a  mov     [rbp+57h+NumberOfBytesRead], esi
0x140007e3d  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x140007e41  mov     word ptr [rbp+57h+Buffer], 0BBEFh
0x140007e47  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x140007e4b  mov     [rbp+57h+Buffer+2], 0BFh
0x140007e4f  mov     [rsp+0D0h+nNumberOfBytesToLockHigh], 4; unsigned int
0x140007e57  call    ?CreateLogFileInternal@@YAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEAPEAX@Z; CreateLogFileInternal(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,void * *)
0x140007e5c  mov     r14, [rbp+57h+hObject]
0x140007e60  mov     r12d, eax
0x140007e63  test    eax, eax
0x140007e65  jns     loc_140007FAE
0x140007e6b  mov     ecx, eax
0x140007e6d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140007e72  mov     r15, [rbp+57h+lpReplacedFileName]
0x140007e76  mov     ecx, r12d
0x140007e79  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140007e7e  test    r15, r15
0x140007e81  jz      short loc_140007EAB
0x140007e83  call    cs:__imp_GetProcessHeap
0x140007e8a  nop     dword ptr [rax+rax+00h]
0x140007e8f  lea     r8, [r15-4]; lpMem
0x140007e93  xor     edx, edx; dwFlags
0x140007e95  mov     rcx, rax; hHeap
0x140007e98  call    cs:__imp_HeapFree
0x140007e9f  nop     dword ptr [rax+rax+00h]
0x140007ea4  xor     ecx, ecx
0x140007ea6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140007eab  test    r13, r13
0x140007eae  jz      short loc_140007ED8
0x140007eb0  call    cs:__imp_GetProcessHeap
0x140007eb7  nop     dword ptr [rax+rax+00h]
0x140007ebc  lea     r8, [r13-4]; lpMem
0x140007ec0  xor     edx, edx; dwFlags
0x140007ec2  mov     rcx, rax; hHeap
0x140007ec5  call    cs:__imp_HeapFree
0x140007ecc  nop     dword ptr [rax+rax+00h]
0x140007ed1  xor     ecx, ecx
0x140007ed3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140007ed8  mov     rax, [rbp+57h+var_68]
0x140007edc  test    rax, rax
0x140007edf  jz      short loc_140007F0C
0x140007ee1  lea     r15, [rax-4]
0x140007ee5  call    cs:__imp_GetProcessHeap
0x140007eec  nop     dword ptr [rax+rax+00h]
0x140007ef1  mov     r8, r15; lpMem
0x140007ef4  xor     edx, edx; dwFlags
0x140007ef6  mov     rcx, rax; hHeap
0x140007ef9  call    cs:__imp_HeapFree
0x140007f00  nop     dword ptr [rax+rax+00h]
0x140007f05  xor     ecx, ecx
0x140007f07  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140007f0c  mov     rax, [rbp+57h+var_60]
0x140007f10  test    rax, rax
0x140007f13  jz      short loc_140007F40
0x140007f15  lea     r15, [rax-4]
0x140007f19  call    cs:__imp_GetProcessHeap
0x140007f20  nop     dword ptr [rax+rax+00h]
0x140007f25  mov     r8, r15; lpMem
0x140007f28  xor     edx, edx; dwFlags
0x140007f2a  mov     rcx, rax; hHeap
0x140007f2d  call    cs:__imp_HeapFree
0x140007f34  nop     dword ptr [rax+rax+00h]
0x140007f39  xor     ecx, ecx
0x140007f3b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140007f40  test    rsi, rsi
0x140007f43  jz      short loc_140007F65
0x140007f45  call    cs:__imp_GetProcessHeap
0x140007f4c  nop     dword ptr [rax+rax+00h]
0x140007f51  mov     r8, rsi; lpMem
0x140007f54  xor     edx, edx; dwFlags
0x140007f56  mov     rcx, rax; hHeap
0x140007f59  call    cs:__imp_HeapFree
0x140007f60  nop     dword ptr [rax+rax+00h]
0x140007f65  lea     rax, [rdi-1]
0x140007f69  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140007f6d  ja      short loc_140007F7E
0x140007f6f  mov     rcx, rdi; hObject
0x140007f72  call    cs:__imp_CloseHandle
0x140007f79  nop     dword ptr [rax+rax+00h]
0x140007f7e  lea     rax, [r14-1]
0x140007f82  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140007f86  ja      short loc_140007F97
0x140007f88  mov     rcx, r14; hObject
0x140007f8b  call    cs:__imp_CloseHandle
0x140007f92  nop     dword ptr [rax+rax+00h]
0x140007f97  mov     eax, r12d
0x140007f9a  add     rsp, 0A0h
0x140007fa1  pop     r15
0x140007fa3  pop     r14
0x140007fa5  pop     r13
0x140007fa7  pop     r12
0x140007fa9  pop     rdi
0x140007faa  pop     rsi
0x140007fab  pop     rbp
0x140007fac  retn
0x140007fae  mov     rcx, r15; hEvent
0x140007fb1  mov     [rbp+57h+Overlapped.hEvent], r15
0x140007fb5  call    cs:__imp_ResetEvent
0x140007fbc  nop     dword ptr [rax+rax+00h]
0x140007fc1  test    eax, eax
0x140007fc3  jnz     short loc_140007FF5
0x140007fc5  call    cs:__imp_GetLastError
0x140007fcc  nop     dword ptr [rax+rax+00h]
0x140007fd1  mov     r12d, eax
0x140007fd4  test    eax, eax
0x140007fd6  jnz     short loc_140007FE0
0x140007fd8  mov     r12d, 80004005h
0x140007fde  jmp     short loc_140007FED
0x140007fe0  jle     short loc_140007FED
0x140007fe2  movzx   r12d, ax
0x140007fe6  or      r12d, 80070000h
0x140007fed  mov     ecx, r12d
0x140007ff0  jmp     loc_140007E6D
0x140007ff5  lea     rax, [r14-1]
0x140007ff9  mov     r9d, 3; nNumberOfBytesToLockLow
0x140007fff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140008003  setnbe  al
0x140008006  xor     ecx, ecx
0x140008008  test    al, al
0x14000800a  lea     r15d, [r9-1]
0x14000800e  lea     rax, [rbp+57h+Overlapped]
0x140008012  mov     edx, r15d; dwFlags
0x140008015  cmovz   rcx, r14; hFile
0x140008019  mov     [rsp+0D0h+lpOverlapped], rax; unsigned int
0x14000801e  xor     r8d, r8d; dwReserved
0x140008021  mov     [rsp+0D0h+nNumberOfBytesToLockHigh], esi; nNumberOfBytesToLockHigh
0x140008025  call    cs:__imp_LockFileEx
0x14000802c  nop     dword ptr [rax+rax+00h]
0x140008031  test    eax, eax
0x140008033  jnz     short loc_14000807C
0x140008035  call    cs:__imp_GetLastError
0x14000803c  nop     dword ptr [rax+rax+00h]
0x140008041  mov     dword ptr [rbp+57h+hObject], esi
0x140008044  cmp     eax, 3E5h
0x140008049  jnz     short loc_1400080BC
0x14000804b  lea     rax, [r14+1]
0x14000804f  and     rax, 0FFFFFFFFFFFFFFFEh
0x140008053  lea     r9d, [r15-1]; bWait
0x140008057  neg     rax
0x14000805a  lea     r8, [rbp+57h+hObject]; lpNumberOfBytesTransferred
0x14000805e  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x140008062  sbb     rcx, rcx
0x140008065  and     rcx, r14; hFile
0x140008068  call    cs:__imp_GetOverlappedResult
0x14000806f  nop     dword ptr [rax+rax+00h]
0x140008074  test    eax, eax
0x140008076  jz      loc_140007FC5
0x14000807c  lea     rax, [r14+1]
0x140008080  and     rax, 0FFFFFFFFFFFFFFFEh
0x140008084  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x140008088  neg     rax
0x14000808b  sbb     rcx, rcx
0x14000808e  and     rcx, r14; hFile
0x140008091  call    cs:__imp_GetFileSizeEx
0x140008098  nop     dword ptr [rax+rax+00h]
0x14000809d  test    eax, eax
0x14000809f  jnz     short loc_1400080F3
0x1400080a1  call    cs:__imp_GetLastError
0x1400080a8  nop     dword ptr [rax+rax+00h]
0x1400080ad  mov     r12d, eax
0x1400080b0  test    eax, eax
0x1400080b2  jnz     short loc_1400080DE
0x1400080b4  mov     r12d, 80004005h
0x1400080ba  jmp     short loc_1400080EB
0x1400080bc  test    eax, eax
0x1400080be  jg      short loc_1400080C5
0x1400080c0  mov     r12d, eax
0x1400080c3  jmp     short loc_1400080D0
0x1400080c5  movzx   r12d, ax
0x1400080c9  or      r12d, 80070000h
0x1400080d0  test    r12d, r12d
0x1400080d3  jns     loc_140007E72
0x1400080d9  jmp     loc_140007FED
0x1400080de  jle     short loc_1400080EB
0x1400080e0  movzx   r12d, ax
0x1400080e4  or      r12d, 80070000h
0x1400080eb  mov     ecx, r12d
0x1400080ee  jmp     loc_1400083F1
0x1400080f3  mov     rax, qword ptr [rbp+57h+FileSize]
0x1400080f7  test    rax, rax
0x1400080fa  jg      short loc_140008106
0x1400080fc  xor     r12d, r12d
0x1400080ff  xor     ecx, ecx
0x140008101  jmp     loc_1400083F1
0x140008106  cmp     rax, 4
0x14000810a  jbe     loc_1400083E9
0x140008110  cmp     dword ptr [rbp+57h+FileSize+4], esi
0x140008113  jnz     loc_1400083E9
0x140008119  mov     esi, eax
0x14000811b  call    cs:__imp_GetProcessHeap
0x140008122  nop     dword ptr [rax+rax+00h]
0x140008127  mov     r8d, esi; dwBytes
0x14000812a  xor     edx, edx; dwFlags
0x14000812c  mov     rcx, rax; hHeap
0x14000812f  call    cs:__imp_HeapAlloc
0x140008136  nop     dword ptr [rax+rax+00h]
0x14000813b  mov     rsi, rax
0x14000813e  test    rax, rax
0x140008141  jnz     short loc_14000814B
0x140008143  mov     r12d, 8007000Eh
0x140008149  jmp     short loc_1400080EB
0x14000814b  lea     rax, [r14+1]
0x14000814f  and     rax, 0FFFFFFFFFFFFFFFEh
0x140008153  neg     rax
0x140008156  sbb     rcx, rcx
0x140008159  xor     r9d, r9d; dwMoveMethod
0x14000815c  and     rcx, r14; hFile
0x14000815f  xor     r8d, r8d; lpNewFilePointer
0x140008162  xor     edx, edx; liDistanceToMove
0x140008164  call    cs:__imp_SetFilePointerEx
0x14000816b  nop     dword ptr [rax+rax+00h]
0x140008170  test    eax, eax
0x140008172  jz      loc_1400080A1
0x140008178  mov     r8d, dword ptr [rbp+57h+FileSize]; nNumberOfBytesToRead
0x14000817c  lea     rax, [r14+1]
0x140008180  and     rax, 0FFFFFFFFFFFFFFFEh
0x140008184  mov     qword ptr [rsp+0D0h+nNumberOfBytesToLockHigh], r13; lpOverlapped
0x140008189  neg     rax
0x14000818c  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140008190  mov     rdx, rsi; lpBuffer
0x140008193  sbb     rcx, rcx
0x140008196  and     rcx, r14; hFile
0x140008199  call    cs:__imp_ReadFile
0x1400081a0  nop     dword ptr [rax+rax+00h]
0x1400081a5  test    eax, eax
0x1400081a7  jz      loc_1400080A1
0x1400081ad  mov     rax, qword ptr [rbp+57h+FileSize]
0x1400081b1  cmp     [rbp+57h+NumberOfBytesRead], eax
0x1400081b4  jnz     loc_1400083E9
0x1400081ba  mov     cl, [rsi]
0x1400081bc  cmp     cl, 0FFh
0x1400081bf  jnz     loc_1400083CE
0x1400081c5  cmp     byte ptr [rsi+1], 0FEh
0x1400081c9  jnz     loc_1400083CE
0x1400081cf  lea     rax, [rbp+57h+var_70]
0x1400081d3  xor     r8d, r8d; unsigned int
0x1400081d6  mov     [rsp+0D0h+var_98], rax; void **
0x1400081db  lea     rcx, aBluebox2Log; "BlueBox2.log"
0x1400081e2  mov     edx, 0C0000000h; unsigned int
0x1400081e7  mov     [rsp+0D0h+nNumberOfBytesToLockHigh], r15d; unsigned int
0x1400081ec  call    ?CreateLogFileInternal@@YAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEAPEAX@Z; CreateLogFileInternal(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,void * *)
0x1400081f1  mov     r12d, eax
0x1400081f4  test    eax, eax
0x1400081f6  jns     short loc_140008208
0x1400081f8  mov     ecx, eax
0x1400081fa  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400081ff  mov     rdi, [rbp+57h+var_70]
0x140008203  jmp     loc_1400083F6
0x140008208  mov     rdi, [rbp+57h+var_70]
0x14000820c  lea     rax, [rdi+1]
0x140008210  and     rax, 0FFFFFFFFFFFFFFFEh
0x140008214  neg     rax
0x140008217  sbb     rcx, rcx
0x14000821a  xor     r9d, r9d; dwMoveMethod
0x14000821d  and     rcx, rdi; hFile
0x140008220  xor     r8d, r8d; lpNewFilePointer
0x140008223  xor     edx, edx; liDistanceToMove
0x140008225  call    cs:__imp_SetFilePointerEx
0x14000822c  nop     dword ptr [rax+rax+00h]
0x140008231  test    eax, eax
0x140008233  jz      loc_1400080A1
0x140008239  lea     rax, [rdi+1]
0x14000823d  mov     qword ptr [rsp+0D0h+nNumberOfBytesToLockHigh], r13; struct _OVERLAPPED *
0x140008242  and     rax, 0FFFFFFFFFFFFFFFEh
0x140008246  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000824a  neg     rax
0x14000824d  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x140008251  mov     r8d, 3; nNumberOfBytesToWrite
0x140008257  sbb     rcx, rcx
0x14000825a  and     rcx, rdi; hFile
0x14000825d  call    cs:__imp_WriteFile
0x140008264  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
