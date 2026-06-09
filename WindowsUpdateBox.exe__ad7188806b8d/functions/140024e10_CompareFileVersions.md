# CompareFileVersions

- ea: `0x140024e10`
- end: `0x14002527e`
- name: `CompareFileVersions`
- size: `1134`
- prototype: `__int64 __fastcall(LPCWSTR lpwstrFilename, LPCWSTR)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400553f0`

## callees

- `0x140022960`
- `0x1400245e4`
- `0x140024e10`
- `0x140025374`
- `0x140025550`
- `0x140025694`
- `0x140080d70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140024f7e`
- `KERNEL32!HeapFree` at `0x140024fa3`
- `KERNEL32!HeapFree` at `0x140024fef`
- `KERNEL32!HeapFree` at `0x140025014`
- `KERNEL32!HeapFree` at `0x140024f7e`
- `KERNEL32!HeapFree` at `0x140024fa3`
- `KERNEL32!HeapFree` at `0x140024fef`
- `KERNEL32!HeapFree` at `0x140025014`
- `KERNEL32!GetProcessHeap` at `0x140024f6a`
- `KERNEL32!GetProcessHeap` at `0x140024f8f`
- `KERNEL32!GetProcessHeap` at `0x140024fdb`
- `KERNEL32!GetProcessHeap` at `0x140025000`
- `KERNEL32!GetProcessHeap` at `0x140024f6a`
- `KERNEL32!GetProcessHeap` at `0x140024f8f`
- `KERNEL32!GetProcessHeap` at `0x140024fdb`
- `KERNEL32!GetProcessHeap` at `0x140025000`
- `KERNEL32!FileTimeToSystemTime` at `0x14002509e`
- `KERNEL32!FileTimeToSystemTime` at `0x1400250ba`
- `KERNEL32!FileTimeToSystemTime` at `0x14002509e`
- `KERNEL32!FileTimeToSystemTime` at `0x1400250ba`
- `KERNEL32!CompareFileTime` at `0x1400251c3`
- `KERNEL32!CompareFileTime` at `0x1400251c3`
- `KERNEL32!GetLastError` at `0x1400251ed`
- `KERNEL32!GetLastError` at `0x14002521d`
- `KERNEL32!GetLastError` at `0x1400251ed`
- `KERNEL32!GetLastError` at `0x14002521d`
- `KERNEL32!SetLastError` at `0x140025232`
- `KERNEL32!SetLastError` at `0x140025248`
- `KERNEL32!SetLastError` at `0x140025232`
- `KERNEL32!SetLastError` at `0x140025248`

## string_xrefs

- `0x140024ee9`: `Comparing file versions:`
- `0x140025079`: `Comparing file modification times:`
- `0x140025200`: `CompareFileVersions: Couldn't get last modification time of [%s] and/or [%s]. GLE = %u`

## pseudocode

```c
__int64 __fastcall CompareFileVersions(LPCWSTR lpwstrFilename, LPCWSTR a2, int a3, int *a4)
{
  LONG v6; // ebx
  int v7; // r13d
  _DWORD *FixedFileInfo; // r14
  __int64 v9; // rax
  _DWORD *v10; // rsi
  int v11; // r12d
  int *FileVersionInformationValue; // r13
  const int *v13; // rbx
  const int *v14; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v18; // rax
  __int64 result; // rax
  __int64 v20; // [rsp+20h] [rbp-69h]
  __int64 v21; // [rsp+20h] [rbp-69h]
  __int64 v22; // [rsp+20h] [rbp-69h]
  __int64 v23; // [rsp+28h] [rbp-61h]
  __int64 v24; // [rsp+28h] [rbp-61h]
  DWORD LastError; // [rsp+28h] [rbp-61h]
  __int64 v26; // [rsp+30h] [rbp-59h]
  __int64 v27; // [rsp+38h] [rbp-51h]
  __int64 v28; // [rsp+40h] [rbp-49h]
  __int64 v29; // [rsp+48h] [rbp-41h]
  __int64 v30; // [rsp+50h] [rbp-39h]
  LPVOID lpMem; // [rsp+60h] [rbp-29h] BYREF
  int v32; // [rsp+68h] [rbp-21h]
  unsigned int v33; // [rsp+6Ch] [rbp-1Dh]
  FILETIME FileTime; // [rsp+70h] [rbp-19h] BYREF
  int *v35; // [rsp+78h] [rbp-11h]
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp-9h] BYREF
  struct _SYSTEMTIME v37; // [rsp+90h] [rbp+7h] BYREF

  v32 = a3;
  v33 = 0;
  v35 = a4;
  v6 = 0;
  v7 = 0;
  if ( !lpwstrFilename || !*lpwstrFilename || !a2 || !*a2 || !a4 )
  {
    SetLastError(0x57u);
    return 0;
  }
  if ( !(unsigned int)FileExists(lpwstrFilename) || !(unsigned int)FileExists(a2) )
    return 0;
  FixedFileInfo = (_DWORD *)GetFixedFileInfo(lpwstrFilename);
  v9 = GetFixedFileInfo(a2);
  v10 = (_DWORD *)v9;
  v11 = 1;
  if ( !FixedFileInfo )
  {
    if ( !v9 )
      goto LABEL_28;
LABEL_25:
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
    if ( !FixedFileInfo )
      goto LABEL_27;
    goto LABEL_26;
  }
  if ( v9 )
  {
    if ( v32 )
    {
      FileVersionInformationValue = (int *)GetFileVersionInformationValue(lpwstrFilename);
      lpMem = (LPVOID)GetFileVersionInformationValue(a2);
      LibLog(&g_WdsLibLog, 0x4000000, L"Comparing file versions:");
      v13 = &dword_1400860C4;
      v14 = &dword_1400860C4;
      if ( FileVersionInformationValue )
        v14 = FileVersionInformationValue;
      LibLog(&g_WdsLibLog, 0x4000000, L"  %s: %s", lpwstrFilename, v14);
      if ( lpMem )
        v13 = (const int *)lpMem;
      LibLog(&g_WdsLibLog, 0x4000000, L"  %s: %s", a2, v13);
      if ( lpMem )
      {
        v15 = GetProcessHeap();
        HeapFree(v15, 0, lpMem);
      }
      if ( FileVersionInformationValue )
      {
        v16 = GetProcessHeap();
        HeapFree(v16, 0, FileVersionInformationValue);
      }
    }
    v6 = FixedFileInfo[4] - v10[4];
    if ( !v6 )
    {
      v6 = FixedFileInfo[5] - v10[5];
      if ( !v6 )
      {
        v6 = FixedFileInfo[2] - v10[2];
        if ( !v6 )
          v6 = FixedFileInfo[3] - v10[3];
      }
    }
    v7 = 1;
    goto LABEL_25;
  }
LABEL_26:
  v18 = GetProcessHeap();
  HeapFree(v18, 0, FixedFileInfo);
LABEL_27:
  if ( v7 )
  {
LABEL_36:
    result = 1;
    if ( v6 <= 0 )
    {
      v11 = v6;
      if ( v6 < 0 )
        v11 = -1;
    }
    *v35 = v11;
    return result;
  }
LABEL_28:
  lpMem = 0;
  FileTime = 0;
  if ( (unsigned int)GetLastModificationTime(lpwstrFilename, &lpMem)
    && (unsigned int)GetLastModificationTime(a2, &FileTime) )
  {
    if ( v32 )
    {
      LibLog(&g_WdsLibLog, 0x4000000, L"Comparing file modification times:");
      SystemTime = 0;
      v37 = 0;
      if ( FileTimeToSystemTime((const FILETIME *)&lpMem, &SystemTime) && FileTimeToSystemTime(&FileTime, &v37) )
      {
        LODWORD(v20) = SystemTime.wYear;
        LibLog(
          &g_WdsLibLog,
          0x4000000,
          L"  %s: %u-%02u-%02u %02u:%02u:%02u.%03u",
          lpwstrFilename,
          v20,
          SystemTime.wMonth,
          SystemTime.wDay,
          SystemTime.wHour,
          SystemTime.wMinute,
          SystemTime.wSecond,
          SystemTime.wMilliseconds);
        LODWORD(v30) = v37.wMilliseconds;
        LODWORD(v29) = v37.wSecond;
        LODWORD(v28) = v37.wMinute;
        LODWORD(v27) = v37.wHour;
        LODWORD(v26) = v37.wDay;
        LODWORD(v23) = v37.wMonth;
        LODWORD(v21) = v37.wYear;
        LibLog(
          &g_WdsLibLog,
          0x4000000,
          L"  %s: %u-%02u-%02u %02u:%02u:%02u.%03u",
          a2,
          v21,
          v23,
          v26,
          v27,
          v28,
          v29,
          v30);
      }
      else
      {
        LODWORD(v20) = HIDWORD(lpMem);
        LibLog(&g_WdsLibLog, 0x4000000, L"  %s: %08x:%08x", lpwstrFilename, v20, (_DWORD)lpMem);
        LODWORD(v24) = FileTime.dwLowDateTime;
        LODWORD(v22) = FileTime.dwHighDateTime;
        LibLog(&g_WdsLibLog, 0x4000000, L"  %s: %08x:%08x", a2, v22, v24);
      }
    }
    v6 = CompareFileTime((const FILETIME *)&lpMem, &FileTime);
    goto LABEL_36;
  }
  LastError = GetLastError();
  LibLog(
    &g_WdsLibLog,
    50331648,
    L"CompareFileVersions: Couldn't get last modification time of [%s] and/or [%s]. GLE = %u",
    lpwstrFilename,
    a2,
    LastError);
  if ( !GetLastError() )
    SetLastError(0x309u);
  return v33;
}

```

## disassembly

```asm
0x140024e10  mov     [rsp-8+arg_10], rbx
0x140024e15  push    rbp
0x140024e16  push    rsi
0x140024e17  push    rdi
0x140024e18  push    r12
0x140024e1a  push    r13
0x140024e1c  push    r14
0x140024e1e  push    r15
0x140024e20  lea     rbp, [rsp-27h]
0x140024e25  sub     rsp, 0B0h
0x140024e2c  mov     rax, cs:__security_cookie
0x140024e33  xor     rax, rsp
0x140024e36  mov     [rbp+57h+var_40], rax
0x140024e3a  xor     esi, esi
0x140024e3c  mov     [rbp+57h+var_78], r8d
0x140024e40  mov     [rbp+57h+var_74], esi
0x140024e43  mov     rax, r9
0x140024e46  mov     [rbp+57h+var_68], rax
0x140024e4a  mov     r15, rdx
0x140024e4d  mov     rdi, rcx
0x140024e50  mov     ebx, esi
0x140024e52  mov     r13d, esi
0x140024e55  test    rcx, rcx
0x140024e58  jz      loc_140025243
0x140024e5e  cmp     [rcx], si
0x140024e61  jz      loc_140025243
0x140024e67  test    rdx, rdx
0x140024e6a  jz      loc_140025243
0x140024e70  cmp     [rdx], si
0x140024e73  jz      loc_140025243
0x140024e79  test    rax, rax
0x140024e7c  jz      loc_140025243
0x140024e82  call    FileExists
0x140024e87  test    eax, eax
0x140024e89  jz      loc_140025254
0x140024e8f  mov     rcx, r15
0x140024e92  call    FileExists
0x140024e97  test    eax, eax
0x140024e99  jz      loc_140025254
0x140024e9f  mov     rcx, rdi; lpwstrFilename
0x140024ea2  call    GetFixedFileInfo
0x140024ea7  mov     rcx, r15; lpwstrFilename
0x140024eaa  mov     r14, rax
0x140024ead  call    GetFixedFileInfo
0x140024eb2  mov     rsi, rax
0x140024eb5  mov     r12d, 1
0x140024ebb  test    r14, r14
0x140024ebe  jz      loc_140024FD6
0x140024ec4  test    rax, rax
0x140024ec7  jz      loc_140025000
0x140024ecd  cmp     [rbp+57h+var_78], ebx
0x140024ed0  jz      loc_140024FAF
0x140024ed6  mov     rcx, rdi; lpwstrFilename
0x140024ed9  call    GetFileVersionInformationValue
0x140024ede  mov     rcx, r15; lpwstrFilename
0x140024ee1  mov     r13, rax
0x140024ee4  call    GetFileVersionInformationValue
0x140024ee9  lea     r8, aComparingFileV; "Comparing file versions:"
0x140024ef0  mov     [rbp+57h+lpMem], rax
0x140024ef4  mov     edx, 4000000h
0x140024ef9  lea     rcx, g_WdsLibLog
0x140024f00  call    LibLog
0x140024f05  lea     rbx, dword_1400860C4
0x140024f0c  test    r13, r13
0x140024f0f  mov     rax, rbx
0x140024f12  lea     r8, aSS_7; "  %s: %s"
0x140024f19  cmovnz  rax, r13
0x140024f1d  lea     rcx, g_WdsLibLog
0x140024f24  mov     r9, rdi
0x140024f27  mov     [rsp+0E0h+var_C0], rax
0x140024f2c  mov     edx, 4000000h
0x140024f31  call    LibLog
0x140024f36  mov     rax, [rbp+57h+lpMem]
0x140024f3a  lea     r8, aSS_7; "  %s: %s"
0x140024f41  test    rax, rax
0x140024f44  lea     rcx, g_WdsLibLog
0x140024f4b  mov     r9, r15
0x140024f4e  mov     edx, 4000000h
0x140024f53  cmovnz  rbx, rax
0x140024f57  mov     [rsp+0E0h+var_C0], rbx
0x140024f5c  call    LibLog
0x140024f61  mov     rbx, [rbp+57h+lpMem]
0x140024f65  test    rbx, rbx
0x140024f68  jz      short loc_140024F8A
0x140024f6a  call    cs:__imp_GetProcessHeap
0x140024f71  nop     dword ptr [rax+rax+00h]
0x140024f76  mov     r8, rbx; lpMem
0x140024f79  xor     edx, edx; dwFlags
0x140024f7b  mov     rcx, rax; hHeap
0x140024f7e  call    cs:__imp_HeapFree
0x140024f85  nop     dword ptr [rax+rax+00h]
0x140024f8a  test    r13, r13
0x140024f8d  jz      short loc_140024FAF
0x140024f8f  call    cs:__imp_GetProcessHeap
0x140024f96  nop     dword ptr [rax+rax+00h]
0x140024f9b  mov     r8, r13; lpMem
0x140024f9e  xor     edx, edx; dwFlags
0x140024fa0  mov     rcx, rax; hHeap
0x140024fa3  call    cs:__imp_HeapFree
0x140024faa  nop     dword ptr [rax+rax+00h]
0x140024faf  mov     ebx, [r14+10h]
0x140024fb3  sub     ebx, [rsi+10h]
0x140024fb6  jnz     short loc_140024FD1
0x140024fb8  mov     ebx, [r14+14h]
0x140024fbc  sub     ebx, [rsi+14h]
0x140024fbf  jnz     short loc_140024FD1
0x140024fc1  mov     ebx, [r14+8]
0x140024fc5  sub     ebx, [rsi+8]
0x140024fc8  jnz     short loc_140024FD1
0x140024fca  mov     ebx, [r14+0Ch]
0x140024fce  sub     ebx, [rsi+0Ch]
0x140024fd1  mov     r13d, r12d
0x140024fd4  jmp     short loc_140024FDB
0x140024fd6  test    rsi, rsi
0x140024fd9  jz      short loc_140025029
0x140024fdb  call    cs:__imp_GetProcessHeap
0x140024fe2  nop     dword ptr [rax+rax+00h]
0x140024fe7  mov     r8, rsi; lpMem
0x140024fea  xor     edx, edx; dwFlags
0x140024fec  mov     rcx, rax; hHeap
0x140024fef  call    cs:__imp_HeapFree
0x140024ff6  nop     dword ptr [rax+rax+00h]
0x140024ffb  test    r14, r14
0x140024ffe  jz      short loc_140025020
0x140025000  call    cs:__imp_GetProcessHeap
0x140025007  nop     dword ptr [rax+rax+00h]
0x14002500c  mov     r8, r14; lpMem
0x14002500f  xor     edx, edx; dwFlags
0x140025011  mov     rcx, rax; hHeap
0x140025014  call    cs:__imp_HeapFree
0x14002501b  nop     dword ptr [rax+rax+00h]
0x140025020  test    r13d, r13d
0x140025023  jnz     loc_1400251D1
0x140025029  lea     rdx, [rbp+57h+lpMem]
0x14002502d  mov     [rbp+57h+lpMem], 0
0x140025035  mov     rcx, rdi
0x140025038  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], 0
0x140025040  call    GetLastModificationTime
0x140025045  test    eax, eax
0x140025047  jz      loc_1400251ED
0x14002504d  lea     rdx, [rbp+57h+FileTime]
0x140025051  mov     rcx, r15
0x140025054  call    GetLastModificationTime
0x140025059  test    eax, eax
0x14002505b  jz      loc_1400251ED
0x140025061  cmp     [rbp+57h+var_78], 0
0x140025065  jz      loc_1400251BB
0x14002506b  mov     esi, 4000000h
0x140025070  lea     r13, g_WdsLibLog
0x140025077  mov     edx, esi
0x140025079  lea     r8, aComparingFileM; "Comparing file modification times:"
0x140025080  mov     rcx, r13
0x140025083  call    LibLog
0x140025088  xorps   xmm0, xmm0
0x14002508b  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x14002508f  xorps   xmm1, xmm1
0x140025092  lea     rcx, [rbp+57h+lpMem]; lpFileTime
0x140025096  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x14002509a  movups  xmmword ptr [rbp+57h+var_50.wYear], xmm1
0x14002509e  call    cs:__imp_FileTimeToSystemTime
0x1400250a5  nop     dword ptr [rax+rax+00h]
0x1400250aa  test    eax, eax
0x1400250ac  jz      loc_140025177
0x1400250b2  lea     rdx, [rbp+57h+var_50]; lpSystemTime
0x1400250b6  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x1400250ba  call    cs:__imp_FileTimeToSystemTime
0x1400250c1  nop     dword ptr [rax+rax+00h]
0x1400250c6  test    eax, eax
0x1400250c8  jz      loc_140025177
0x1400250ce  movzx   ecx, [rbp+57h+SystemTime.wSecond]
0x1400250d2  mov     r9, rdi
0x1400250d5  movzx   edx, [rbp+57h+SystemTime.wMinute]
0x1400250d9  movzx   r8d, [rbp+57h+SystemTime.wHour]
0x1400250de  movzx   eax, [rbp+57h+SystemTime.wMilliseconds]
0x1400250e2  movzx   r10d, [rbp+57h+SystemTime.wDay]
0x1400250e7  movzx   r11d, [rbp+57h+SystemTime.wMonth]
0x1400250ec  movzx   ebx, [rbp+57h+SystemTime.wYear]
0x1400250f0  mov     [rsp+0E0h+var_90], eax
0x1400250f4  mov     dword ptr [rsp+0E0h+var_98], ecx
0x1400250f8  mov     rcx, r13
0x1400250fb  mov     dword ptr [rsp+0E0h+var_A0], edx
0x1400250ff  mov     edx, esi
0x140025101  mov     dword ptr [rsp+0E0h+var_A8], r8d
0x140025106  lea     r8, aSU02u02u02u02u; "  %s: %u-%02u-%02u %02u:%02u:%02u.%03u"
0x14002510d  mov     dword ptr [rsp+0E0h+var_B0], r10d
0x140025112  mov     dword ptr [rsp+0E0h+var_B8], r11d
0x140025117  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x14002511b  call    LibLog
0x140025120  movzx   eax, [rbp+57h+var_50.wMilliseconds]
0x140025124  lea     r8, aSU02u02u02u02u; "  %s: %u-%02u-%02u %02u:%02u:%02u.%03u"
0x14002512b  movzx   r10d, [rbp+57h+var_50.wSecond]
0x140025130  mov     r9, r15
0x140025133  movzx   r11d, [rbp+57h+var_50.wMinute]
0x140025138  mov     edx, 4000000h
0x14002513d  movzx   ebx, [rbp+57h+var_50.wHour]
0x140025141  mov     rcx, r13
0x140025144  movzx   edi, [rbp+57h+var_50.wDay]
0x140025148  movzx   esi, [rbp+57h+var_50.wMonth]
0x14002514c  movzx   r14d, [rbp+57h+var_50.wYear]
0x140025151  mov     [rsp+0E0h+var_90], eax
0x140025155  mov     dword ptr [rsp+0E0h+var_98], r10d
0x14002515a  mov     dword ptr [rsp+0E0h+var_A0], r11d
0x14002515f  mov     dword ptr [rsp+0E0h+var_A8], ebx
0x140025163  mov     dword ptr [rsp+0E0h+var_B0], edi
0x140025167  mov     dword ptr [rsp+0E0h+var_B8], esi
0x14002516b  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x140025170  call    LibLog
0x140025175  jmp     short loc_1400251BB
0x140025177  mov     eax, dword ptr [rbp+57h+lpMem]
0x14002517a  lea     r8, aS08x08x; "  %s: %08x:%08x"
0x140025181  mov     dword ptr [rsp+0E0h+var_B8], eax
0x140025185  mov     r9, rdi
0x140025188  mov     eax, dword ptr [rbp+57h+lpMem+4]
0x14002518b  mov     edx, esi
0x14002518d  mov     rcx, r13
0x140025190  mov     dword ptr [rsp+0E0h+var_C0], eax
0x140025194  call    LibLog
0x140025199  mov     eax, [rbp+57h+FileTime.dwLowDateTime]
0x14002519c  lea     r8, aS08x08x; "  %s: %08x:%08x"
0x1400251a3  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1400251a7  mov     r9, r15
0x1400251aa  mov     eax, [rbp+57h+FileTime.dwHighDateTime]
0x1400251ad  mov     edx, esi
0x1400251af  mov     rcx, r13
0x1400251b2  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1400251b6  call    LibLog
0x1400251bb  lea     rdx, [rbp+57h+FileTime]; lpFileTime2
0x1400251bf  lea     rcx, [rbp+57h+lpMem]; lpFileTime1
0x1400251c3  call    cs:__imp_CompareFileTime
0x1400251ca  nop     dword ptr [rax+rax+00h]
0x1400251cf  mov     ebx, eax
0x1400251d1  mov     eax, r12d
0x1400251d4  test    ebx, ebx
0x1400251d6  jg      short loc_1400251E4
0x1400251d8  or      ecx, 0FFFFFFFFh
0x1400251db  mov     r12d, ebx
0x1400251de  test    ebx, ebx
0x1400251e0  cmovs   r12d, ecx
0x1400251e4  mov     rcx, [rbp+57h+var_68]
0x1400251e8  mov     [rcx], r12d
0x1400251eb  jmp     short loc_140025256
0x1400251ed  call    cs:__imp_GetLastError
0x1400251f4  nop     dword ptr [rax+rax+00h]
0x1400251f9  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1400251fd  mov     r9, rdi
0x140025200  lea     r8, aComparefilever; "CompareFileVersions: Couldn't get last "...
0x140025207  mov     [rsp+0E0h+var_C0], r15
0x14002520c  mov     edx, 3000000h
0x140025211  lea     rcx, g_WdsLibLog
0x140025218  call    LibLog
0x14002521d  call    cs:__imp_GetLastError
0x140025224  nop     dword ptr [rax+rax+00h]
0x140025229  test    eax, eax
0x14002522b  jnz     short loc_14002523E
0x14002522d  mov     ecx, 309h; dwErrCode
0x140025232  call    cs:__imp_SetLastError
0x140025239  nop     dword ptr [rax+rax+00h]
0x14002523e  mov     eax, [rbp+57h+var_74]
0x140025241  jmp     short loc_140025256
0x140025243  mov     ecx, 57h ; 'W'; dwErrCode
0x140025248  call    cs:__imp_SetLastError
0x14002524f  nop     dword ptr [rax+rax+00h]
0x140025254  xor     eax, eax
0x140025256  mov     rcx, [rbp+57h+var_40]
0x14002525a  xor     rcx, rsp; StackCookie
0x14002525d  call    __security_check_cookie
0x140025262  mov     rbx, [rsp+0E0h+arg_10]
0x14002526a  add     rsp, 0B0h
0x140025271  pop     r15
0x140025273  pop     r14
0x140025275  pop     r13
0x140025277  pop     r12
0x140025279  pop     rdi
0x14002527a  pop     rsi
0x14002527b  pop     rbp
0x14002527c  retn
```
