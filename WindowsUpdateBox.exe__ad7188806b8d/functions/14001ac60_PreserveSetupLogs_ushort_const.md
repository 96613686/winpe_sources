# PreserveSetupLogs(ushort const *)

- ea: `0x14001ac60`
- end: `0x14001b1af`
- name: `?PreserveSetupLogs@@YAJPEBG@Z`
- size: `1359`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14000bccc`

## callees

- `0x140002116`
- `0x140005f7c`
- `0x1400076c8`
- `0x140007cb0`
- `0x1400135b8`
- `0x140016bb4`
- `0x14001ac60`
- `0x14002571c`
- `0x140052ad4`
- `0x140080d70`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x14001af28`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x14001af28`
- `KERNEL32!HeapFree` at `0x14001ae0d`
- `KERNEL32!HeapFree` at `0x14001ae3b`
- `KERNEL32!HeapFree` at `0x14001ae69`
- `KERNEL32!HeapFree` at `0x14001ae97`
- `KERNEL32!HeapFree` at `0x14001aec6`
- `KERNEL32!HeapFree` at `0x14001ae0d`
- `KERNEL32!HeapFree` at `0x14001ae3b`
- `KERNEL32!HeapFree` at `0x14001ae69`
- `KERNEL32!HeapFree` at `0x14001ae97`
- `KERNEL32!HeapFree` at `0x14001aec6`
- `KERNEL32!GetProcessHeap` at `0x14001adf8`
- `KERNEL32!GetProcessHeap` at `0x14001ae26`
- `KERNEL32!GetProcessHeap` at `0x14001ae54`
- `KERNEL32!GetProcessHeap` at `0x14001ae82`
- `KERNEL32!GetProcessHeap` at `0x14001aeb0`
- `KERNEL32!GetProcessHeap` at `0x14001adf8`
- `KERNEL32!GetProcessHeap` at `0x14001ae26`
- `KERNEL32!GetProcessHeap` at `0x14001ae54`
- `KERNEL32!GetProcessHeap` at `0x14001ae82`
- `KERNEL32!GetProcessHeap` at `0x14001aeb0`
- `KERNEL32!GetLastError` at `0x14001b0ae`
- `KERNEL32!GetLastError` at `0x14001b186`
- `KERNEL32!GetLastError` at `0x14001b0ae`
- `KERNEL32!GetLastError` at `0x14001b186`
- `KERNEL32!GetFileAttributesW` at `0x14001ad13`
- `KERNEL32!GetFileAttributesW` at `0x14001ad74`
- `KERNEL32!GetFileAttributesW` at `0x14001af92`
- `KERNEL32!GetFileAttributesW` at `0x14001ad13`
- `KERNEL32!GetFileAttributesW` at `0x14001ad74`
- `KERNEL32!GetFileAttributesW` at `0x14001af92`

## string_xrefs

- `0x14001b04b`: `Creating path: [%s]...`
- `0x14001b113`: `Creating path: [%s]...`
- `0x14001ad46`: `Sources\Rollback`
- `0x14001afde`: `Cleaning path: [%s]...`
- `0x14001b08c`: `Copying [%s] -> [%s]...`
- `0x14001b160`: `Copying [%s] -> [%s]...`
- `0x14001b0da`: `Rollback`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall PreserveSetupLogs(const unsigned __int16 *a1)
{
  LPCWSTR v2; // r12
  LPCWSTR v3; // r13
  const unsigned __int16 *v4; // r15
  LPCWSTR v5; // r14
  unsigned int v6; // edi
  const WCHAR *v7; // rbx
  int v8; // eax
  DWORD FileAttributesW; // ebx
  int v10; // ebx
  int v11; // eax
  DWORD v12; // r14d
  int v13; // r14d
  HANDLE ProcessHeap; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax
  HANDLE v17; // rax
  HANDLE v18; // rax
  int v20; // eax
  __int64 v21; // rcx
  DWORD v22; // esi
  int v23; // esi
  int v24; // eax
  const WCHAR *v25; // rbx
  signed int LastError; // eax
  int v27; // eax
  __int64 v28; // rcx
  signed int v29; // eax
  LPCWSTR v30; // [rsp+38h] [rbp-D0h] BYREF
  LPCWSTR lpPathName; // [rsp+40h] [rbp-C8h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-C0h] BYREF
  LPCWSTR v33; // [rsp+50h] [rbp-B8h] BYREF
  LPCWSTR v34[2]; // [rsp+58h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+68h] [rbp-A0h] BYREF

  v34[1] = (LPCWSTR)-2LL;
  v2 = 0;
  lpFileName = 0;
  v3 = 0;
  v33 = 0;
  v4 = 0;
  v34[0] = 0;
  v5 = 0;
  lpPathName = 0;
  v30 = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942487LL);
LABEL_3:
    v7 = v30;
    goto LABEL_19;
  }
  v8 = CMiscHelpersT<CEmptyType>::CombinePath(a1, L"Sources\\Panther", 0, &lpFileName);
  v6 = v8;
  if ( v8 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v8);
    v2 = lpFileName;
    goto LABEL_3;
  }
  v2 = lpFileName;
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
    v10 = 0;
  else
    v10 = (FileAttributesW >> 4) & 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v11 = CMiscHelpersT<CEmptyType>::CombinePath(a1, L"Sources\\Rollback", 0, &v33);
  v6 = v11;
  if ( v11 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v11);
    v3 = v33;
    goto LABEL_3;
  }
  v3 = v33;
  v12 = GetFileAttributesW(v33);
  if ( v12 == -1 )
    v13 = 0;
  else
    v13 = (v12 >> 4) & 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( !v10 && !v13 )
  {
    OutputMsg(
      (HANDLE)((unsigned __int64)g_shLogFile
             & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
      g_shLogEvent,
      L"Nothing to preserve.");
    v6 = 0;
LABEL_17:
    v7 = v30;
    goto LABEL_18;
  }
  memset_0(Buffer, 0, 0x208u);
  if ( !GetSystemWindowsDirectoryW(Buffer, 0x104u) )
    goto LABEL_48;
  v20 = CMiscHelpersT<CEmptyType>::CombinePath(Buffer, L"Panther\\NewOs", 0, v34);
  v6 = v20;
  if ( v20 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v20);
    v4 = v34[0];
    goto LABEL_17;
  }
  v4 = v34[0];
  v22 = GetFileAttributesW(v34[0]);
  if ( v22 == -1 )
    v23 = 0;
  else
    v23 = (v22 >> 4) & 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v6 = 0;
  if ( v23 )
  {
    OutputMsg(
      (HANDLE)((unsigned __int64)g_shLogFile
             & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
      g_shLogEvent,
      L"Cleaning path: [%s]...",
      v4);
    v24 = BoxDeletePath(v4);
    v6 = v24;
    if ( v24 < 0 )
      goto LABEL_43;
  }
  if ( v10 )
  {
    v24 = CMiscHelpersT<CEmptyType>::CombinePath(v4, L"Panther", 0, &lpPathName);
    v6 = v24;
    if ( v24 < 0
      || (v25 = lpPathName,
          OutputMsg(
            (HANDLE)((unsigned __int64)g_shLogFile
                   & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
            g_shLogEvent,
            L"Creating path: [%s]...",
            lpPathName),
          v24 = DirEnsureExists(v25),
          v6 = v24,
          v24 < 0) )
    {
LABEL_43:
      v21 = (unsigned int)v24;
LABEL_37:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v21);
      goto LABEL_17;
    }
    OutputMsg(
      (HANDLE)((unsigned __int64)g_shLogFile
             & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
      g_shLogEvent,
      L"Copying [%s] -> [%s]...",
      v2,
      v25);
    if ( !(unsigned int)CopyDirectory((__int64)v2, (__int64)v25) )
    {
LABEL_48:
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v6 = -2147467259;
      }
      v21 = v6;
      goto LABEL_37;
    }
  }
  if ( !v13 )
    goto LABEL_17;
  v24 = CMiscHelpersT<CEmptyType>::CombinePath(v4, L"Rollback", 0, &v30);
  v6 = v24;
  if ( v24 < 0 )
    goto LABEL_43;
  v7 = v30;
  OutputMsg(
    (HANDLE)((unsigned __int64)g_shLogFile
           & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
    g_shLogEvent,
    L"Creating path: [%s]...",
    v30);
  v27 = DirEnsureExists(v7);
  v6 = v27;
  if ( v27 >= 0 )
  {
    OutputMsg(
      (HANDLE)((unsigned __int64)g_shLogFile
             & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
      g_shLogEvent,
      L"Copying [%s] -> [%s]...",
      v3,
      v7);
    if ( (unsigned int)CopyDirectory((__int64)v3, (__int64)v7) )
      goto LABEL_18;
    v29 = GetLastError();
    v6 = v29;
    if ( v29 )
    {
      if ( v29 > 0 )
        v6 = (unsigned __int16)v29 | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    v28 = v6;
  }
  else
  {
    v28 = (unsigned int)v27;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v28);
LABEL_18:
  v5 = lpPathName;
LABEL_19:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v7 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v5 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, (LPVOID)(v5 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v4 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, (LPVOID)(v4 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v3 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, (LPVOID)(v3 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v2 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, (LPVOID)(v2 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v6;
}

```

## disassembly

```asm
0x14001ac60  mov     rax, rsp
0x14001ac63  push    rbp
0x14001ac64  push    r12
0x14001ac66  push    r13
0x14001ac68  push    r14
0x14001ac6a  push    r15
0x14001ac6c  lea     rbp, [rax-1A8h]
0x14001ac73  sub     rsp, 280h
0x14001ac7a  mov     qword ptr [rsp+2A0h+var_248], 0FFFFFFFFFFFFFFFEh
0x14001ac83  mov     [rax+10h], rbx
0x14001ac87  mov     [rax+18h], rsi
0x14001ac8b  mov     [rax+20h], rdi
0x14001ac8f  mov     rax, cs:__security_cookie
0x14001ac96  xor     rax, rsp
0x14001ac99  mov     [rbp+1A0h+var_30], rax
0x14001aca0  mov     rsi, rcx
0x14001aca3  xor     r12d, r12d
0x14001aca6  mov     [rsp+2A0h+lpFileName], r12
0x14001acab  xor     r13d, r13d
0x14001acae  mov     [rsp+2A0h+var_258], r13
0x14001acb3  xor     r15d, r15d
0x14001acb6  mov     [rsp+2A0h+var_250], r15
0x14001acbb  xor     r14d, r14d
0x14001acbe  mov     [rsp+2A0h+lpPathName], r14
0x14001acc3  mov     [rsp+2A0h+var_270], r14
0x14001acc8  test    rcx, rcx
0x14001accb  jnz     short loc_14001ACE3
0x14001accd  mov     edi, 80070057h
0x14001acd2  mov     ecx, edi
0x14001acd4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001acd9  mov     rbx, [rsp+2A0h+var_270]
0x14001acde  jmp     loc_14001ADEB
0x14001ace3  lea     r9, [rsp+2A0h+lpFileName]
0x14001ace8  xor     r8d, r8d
0x14001aceb  lea     rdx, aSourcesPanther; "Sources\\Panther"
0x14001acf2  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x14001acf7  mov     edi, eax
0x14001acf9  test    eax, eax
0x14001acfb  jns     short loc_14001AD0B
0x14001acfd  mov     ecx, eax
0x14001acff  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001ad04  mov     r12, [rsp+2A0h+lpFileName]
0x14001ad09  jmp     short loc_14001ACD9
0x14001ad0b  mov     r12, [rsp+2A0h+lpFileName]
0x14001ad10  mov     rcx, r12; lpFileName
0x14001ad13  call    cs:__imp_GetFileAttributesW
0x14001ad1a  nop     dword ptr [rax+rax+00h]
0x14001ad1f  mov     ebx, eax
0x14001ad21  cmp     eax, 0FFFFFFFFh
0x14001ad24  jz      short loc_14001AD2E
0x14001ad26  shr     ebx, 4
0x14001ad29  and     ebx, 1
0x14001ad2c  jmp     short loc_14001AD30
0x14001ad2e  xor     ebx, ebx
0x14001ad30  xor     ecx, ecx
0x14001ad32  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001ad37  xor     ecx, ecx
0x14001ad39  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001ad3e  lea     r9, [rsp+2A0h+var_258]
0x14001ad43  xor     r8d, r8d
0x14001ad46  lea     rdx, aSourcesRollbac; "Sources\\Rollback"
0x14001ad4d  mov     rcx, rsi
0x14001ad50  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x14001ad55  mov     edi, eax
0x14001ad57  test    eax, eax
0x14001ad59  jns     short loc_14001AD6C
0x14001ad5b  mov     ecx, eax
0x14001ad5d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001ad62  mov     r13, [rsp+2A0h+var_258]
0x14001ad67  jmp     loc_14001ACD9
0x14001ad6c  mov     r13, [rsp+2A0h+var_258]
0x14001ad71  mov     rcx, r13; lpFileName
0x14001ad74  call    cs:__imp_GetFileAttributesW
0x14001ad7b  nop     dword ptr [rax+rax+00h]
0x14001ad80  mov     r14d, eax
0x14001ad83  cmp     eax, 0FFFFFFFFh
0x14001ad86  jz      short loc_14001AD92
0x14001ad88  shr     r14d, 4
0x14001ad8c  and     r14d, 1
0x14001ad90  jmp     short loc_14001AD95
0x14001ad92  xor     r14d, r14d
0x14001ad95  xor     ecx, ecx
0x14001ad97  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001ad9c  xor     ecx, ecx
0x14001ad9e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001ada3  test    ebx, ebx
0x14001ada5  jnz     loc_14001AF0C
0x14001adab  test    r14d, r14d
0x14001adae  jnz     loc_14001AF0C
0x14001adb4  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001adbb  lea     rax, [r8+1]
0x14001adbf  and     rax, 0FFFFFFFFFFFFFFFEh
0x14001adc3  neg     rax
0x14001adc6  sbb     rcx, rcx
0x14001adc9  and     rcx, r8; hFile
0x14001adcc  lea     r8, aNothingToPrese; "Nothing to preserve."
0x14001add3  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001adda  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001addf  xor     edi, edi
0x14001ade1  mov     rbx, [rsp+2A0h+var_270]
0x14001ade6  mov     r14, [rsp+2A0h+lpPathName]
0x14001adeb  mov     ecx, edi
0x14001aded  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001adf2  nop
0x14001adf3  test    rbx, rbx
0x14001adf6  jz      short loc_14001AE21
0x14001adf8  call    cs:__imp_GetProcessHeap
0x14001adff  nop     dword ptr [rax+rax+00h]
0x14001ae04  mov     rcx, rax; hHeap
0x14001ae07  lea     r8, [rbx-4]; lpMem
0x14001ae0b  xor     edx, edx; dwFlags
0x14001ae0d  call    cs:__imp_HeapFree
0x14001ae14  nop     dword ptr [rax+rax+00h]
0x14001ae19  xor     ecx, ecx
0x14001ae1b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001ae20  nop
0x14001ae21  test    r14, r14
0x14001ae24  jz      short loc_14001AE4F
0x14001ae26  call    cs:__imp_GetProcessHeap
0x14001ae2d  nop     dword ptr [rax+rax+00h]
0x14001ae32  mov     rcx, rax; hHeap
0x14001ae35  lea     r8, [r14-4]; lpMem
0x14001ae39  xor     edx, edx; dwFlags
0x14001ae3b  call    cs:__imp_HeapFree
0x14001ae42  nop     dword ptr [rax+rax+00h]
0x14001ae47  xor     ecx, ecx
0x14001ae49  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001ae4e  nop
0x14001ae4f  test    r15, r15
0x14001ae52  jz      short loc_14001AE7D
0x14001ae54  call    cs:__imp_GetProcessHeap
0x14001ae5b  nop     dword ptr [rax+rax+00h]
0x14001ae60  mov     rcx, rax; hHeap
0x14001ae63  lea     r8, [r15-4]; lpMem
0x14001ae67  xor     edx, edx; dwFlags
0x14001ae69  call    cs:__imp_HeapFree
0x14001ae70  nop     dword ptr [rax+rax+00h]
0x14001ae75  xor     ecx, ecx
0x14001ae77  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001ae7c  nop
0x14001ae7d  test    r13, r13
0x14001ae80  jz      short loc_14001AEAB
0x14001ae82  call    cs:__imp_GetProcessHeap
0x14001ae89  nop     dword ptr [rax+rax+00h]
0x14001ae8e  mov     rcx, rax; hHeap
0x14001ae91  lea     r8, [r13-4]; lpMem
0x14001ae95  xor     edx, edx; dwFlags
0x14001ae97  call    cs:__imp_HeapFree
0x14001ae9e  nop     dword ptr [rax+rax+00h]
0x14001aea3  xor     ecx, ecx
0x14001aea5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001aeaa  nop
0x14001aeab  test    r12, r12
0x14001aeae  jz      short loc_14001AED9
0x14001aeb0  call    cs:__imp_GetProcessHeap
0x14001aeb7  nop     dword ptr [rax+rax+00h]
0x14001aebc  mov     rcx, rax; hHeap
0x14001aebf  lea     r8, [r12-4]; lpMem
0x14001aec4  xor     edx, edx; dwFlags
0x14001aec6  call    cs:__imp_HeapFree
0x14001aecd  nop     dword ptr [rax+rax+00h]
0x14001aed2  xor     ecx, ecx
0x14001aed4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001aed9  mov     eax, edi
0x14001aedb  mov     rcx, [rbp+1A0h+var_30]
0x14001aee2  xor     rcx, rsp; StackCookie
0x14001aee5  call    __security_check_cookie
0x14001aeea  lea     r11, [rsp+2A0h+var_20]
0x14001aef2  mov     rbx, [r11+38h]
0x14001aef6  mov     rsi, [r11+40h]
0x14001aefa  mov     rdi, [r11+48h]
0x14001aefe  mov     rsp, r11
0x14001af01  pop     r15
0x14001af03  pop     r14
0x14001af05  pop     r13
0x14001af07  pop     r12
0x14001af09  pop     rbp
0x14001af0a  retn
0x14001af0c  xor     edx, edx; Val
0x14001af0e  mov     r8d, 208h; Size
0x14001af14  lea     rcx, [rsp+2A0h+Buffer]; void *
0x14001af19  call    memset_0
0x14001af1e  mov     edx, 104h; uSize
0x14001af23  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x14001af28  call    cs:__imp_GetSystemWindowsDirectoryW
0x14001af2f  nop     dword ptr [rax+rax+00h]
0x14001af34  test    eax, eax
0x14001af36  jz      loc_14001B0AE
0x14001af3c  lea     r9, [rsp+2A0h+var_250]
0x14001af41  xor     r8d, r8d
0x14001af44  lea     rdx, aPantherNewos; "Panther\\NewOs"
0x14001af4b  lea     rcx, [rsp+2A0h+Buffer]
0x14001af50  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x14001af55  mov     edi, eax
0x14001af57  test    eax, eax
0x14001af59  jns     short loc_14001AF8A
0x14001af5b  mov     ecx, eax
0x14001af5d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001af62  mov     r15, [rsp+2A0h+var_250]
0x14001af67  jmp     loc_14001ADE1
0x14001af6c  mov     edi, 80004005h
0x14001af71  jmp     short loc_14001AF7E
0x14001af73  jle     short loc_14001AF7E
0x14001af75  movzx   edi, ax
0x14001af78  or      edi, 80070000h
0x14001af7e  mov     ecx, edi
0x14001af80  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001af85  jmp     loc_14001ADE1
0x14001af8a  mov     r15, [rsp+2A0h+var_250]
0x14001af8f  mov     rcx, r15; lpFileName
0x14001af92  call    cs:__imp_GetFileAttributesW
0x14001af99  nop     dword ptr [rax+rax+00h]
0x14001af9e  mov     esi, eax
0x14001afa0  cmp     eax, 0FFFFFFFFh
0x14001afa3  jz      short loc_14001AFAD
0x14001afa5  shr     esi, 4
0x14001afa8  and     esi, 1
0x14001afab  jmp     short loc_14001AFAF
0x14001afad  xor     esi, esi
0x14001afaf  xor     ecx, ecx
0x14001afb1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001afb6  xor     ecx, ecx
0x14001afb8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001afbd  xor     edi, edi
0x14001afbf  test    esi, esi
0x14001afc1  jz      short loc_14001B006
0x14001afc3  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001afca  lea     rax, [r8+1]
0x14001afce  and     rax, 0FFFFFFFFFFFFFFFEh
0x14001afd2  neg     rax
0x14001afd5  sbb     rcx, rcx
0x14001afd8  and     rcx, r8; hFile
0x14001afdb  mov     r9, r15
0x14001afde  lea     r8, aCleaningPathS; "Cleaning path: [%s]..."
0x14001afe5  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001afec  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001aff1  mov     rcx, r15; unsigned __int16 *
0x14001aff4  call    ?BoxDeletePath@@YAJPEBG@Z; BoxDeletePath(ushort const *)
0x14001aff9  mov     edi, eax
0x14001affb  test    eax, eax
0x14001affd  jns     short loc_14001B006
0x14001afff  mov     ecx, eax
0x14001b001  jmp     loc_14001AF80
0x14001b006  test    ebx, ebx
0x14001b008  jz      loc_14001B0C9
0x14001b00e  lea     r9, [rsp+2A0h+lpPathName]
0x14001b013  xor     r8d, r8d
0x14001b016  lea     rdx, aPanther; "Panther"
0x14001b01d  mov     rcx, r15
0x14001b020  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x14001b025  mov     edi, eax
0x14001b027  test    eax, eax
0x14001b029  js      short loc_14001AFFF
0x14001b02b  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001b032  lea     rax, [r8+1]
0x14001b036  and     rax, 0FFFFFFFFFFFFFFFEh
0x14001b03a  neg     rax
0x14001b03d  sbb     rcx, rcx
0x14001b040  and     rcx, r8; hFile
0x14001b043  mov     rbx, [rsp+2A0h+lpPathName]
0x14001b048  mov     r9, rbx
0x14001b04b  lea     r8, aCreatingPathS; "Creating path: [%s]..."
0x14001b052  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001b059  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001b05e  mov     rcx, rbx; lpPathName
0x14001b061  call    DirEnsureExists
0x14001b066  mov     edi, eax
0x14001b068  test    eax, eax
0x14001b06a  js      short loc_14001AFFF
0x14001b06c  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001b073  lea     rax, [r8+1]
0x14001b077  and     rax, 0FFFFFFFFFFFFFFFEh
0x14001b07b  neg     rax
0x14001b07e  sbb     rcx, rcx
0x14001b081  and     rcx, r8; hFile
0x14001b084  mov     [rsp+2A0h+var_280], rbx
0x14001b089  mov     r9, r12
0x14001b08c  lea     r8, aCopyingSS; "Copying [%s] -> [%s]..."
0x14001b093  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001b09a  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001b09f  mov     rdx, rbx
0x14001b0a2  mov     rcx, r12
0x14001b0a5  call    CopyDirectory
0x14001b0aa  test    eax, eax
0x14001b0ac  jnz     short loc_14001B0C9
0x14001b0ae  call    cs:__imp_GetLastError
0x14001b0b5  nop     dword ptr [rax+rax+00h]
0x14001b0ba  test    eax, eax
0x14001b0bc  mov     edi, eax
0x14001b0be  jz      loc_14001AF6C
0x14001b0c4  jmp     loc_14001AF73
0x14001b0c9  test    r14d, r14d
0x14001b0cc  jz      loc_14001ADE1
0x14001b0d2  lea     r9, [rsp+2A0h+var_270]
0x14001b0d7  xor     r8d, r8d
0x14001b0da  lea     rdx, aRollback; "Rollback"
0x14001b0e1  mov     rcx, r15
0x14001b0e4  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x14001b0e9  mov     edi, eax
0x14001b0eb  test    eax, eax
  ... truncated ...
```
