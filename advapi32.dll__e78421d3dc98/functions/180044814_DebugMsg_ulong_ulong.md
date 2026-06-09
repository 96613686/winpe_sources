# _DebugMsg(ulong,ulong,...)

- ea: `0x180044814`
- end: `0x180044ac0`
- name: `?_DebugMsg@@YAXKKZZ`
- size: `684`
- prototype: `void(unsigned int, unsigned int, ...)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callers

- `0x18002ec80`
- `0x1800367f0`
- `0x180044c20`

## callees

- `0x1800175c8`
- `0x18003702c`
- `0x180043350`
- `0x180043510`
- `0x180043b14`
- `0x180043b4c`
- `0x180043dc8`
- `0x180044604`
- `0x180044814`
- `0x180044c20`
- `0x180065090`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x1800449a6`
- `KERNELBASE!LocalAlloc` at `0x1800449a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044913`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044913`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004491b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004491b`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18004490d`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18004490d`
- `KERNEL32!LocalFree` at `0x180044a5e`
- `KERNEL32!LocalFree` at `0x180044a9c`
- `KERNEL32!LocalFree` at `0x180044a5e`
- `KERNEL32!LocalFree` at `0x180044a9c`
- `KERNEL32!CloseHandle` at `0x180044a55`
- `KERNEL32!CloseHandle` at `0x180044a55`
- `KERNEL32!WriteFile` at `0x180044a25`
- `KERNEL32!WriteFile` at `0x180044a4c`
- `KERNEL32!WriteFile` at `0x180044a25`
- `KERNEL32!WriteFile` at `0x180044a4c`
- `KERNEL32!SetFilePointer` at `0x1800449e8`
- `KERNEL32!SetFilePointer` at `0x1800449e8`
- `KERNEL32!FormatMessageW` at `0x1800448f1`
- `KERNEL32!FormatMessageW` at `0x1800448f1`
- `KERNEL32!OutputDebugStringW` at `0x180044973`
- `KERNEL32!OutputDebugStringW` at `0x18004497e`
- `KERNEL32!OutputDebugStringW` at `0x18004498b`
- `KERNEL32!OutputDebugStringW` at `0x180044973`
- `KERNEL32!OutputDebugStringW` at `0x18004497e`
- `KERNEL32!OutputDebugStringW` at `0x18004498b`

## pseudocode

```c
void _DebugMsg(unsigned int a1, DWORD a2, ...)
{
  DWORD v3; // eax
  HINSTANCE HandleForCallingDll; // rax
  int v5; // r14d
  DWORD CurrentThreadId; // ebx
  DWORD CurrentProcessId; // eax
  BYTE v8; // al
  WCHAR *v9; // rax
  int v10; // edx
  WCHAR *v11; // rdi
  void *v12; // rax
  __int64 v13; // rbx
  void *v14; // rsi
  DWORD v15; // eax
  DWORD v16; // eax
  LPWSTR lpBuffer; // [rsp+28h] [rbp-E0h]
  DWORD nSize[2]; // [rsp+30h] [rbp-D8h]
  va_list *Arguments; // [rsp+38h] [rbp-D0h]
  WCHAR Buffer[4]; // [rsp+58h] [rbp-B0h] BYREF
  DWORD NumberOfBytesWritten[2]; // [rsp+60h] [rbp-A8h] BYREF
  va_list v22[4]; // [rsp+68h] [rbp-A0h] BYREF
  WCHAR OutputString[64]; // [rsp+88h] [rbp-80h] BYREF
  va_list va; // [rsp+168h] [rbp+60h] BYREF

  va_start(va, a2);
  *(_QWORD *)Buffer = 0;
  memset(v22, 0, 24);
  if ( gDebugEnabled != 1 || gDebugInitialized || (ApplyDebugSettings(), gDebugEnabled == 1) && gDebugInitialized == 1 )
  {
    if ( (unsigned int)DebugLevelOn(a1) && (unsigned int)LoadLoadString() )
    {
      va_copy((va_list)v22, va);
      v3 = 0;
      if ( a2 < 0x3E8 )
      {
        HandleForCallingDll = AppmgmtGetHandleForCallingDll();
        v3 = FormatMessageW(0x900u, HandleForCallingDll, a2, 0, Buffer, 0, v22);
      }
      v22[0] = 0;
      if ( v3 )
      {
        v5 = a1 & 8;
        GetLocalTime((LPSYSTEMTIME)&v22[1]);
        CurrentThreadId = GetCurrentThreadId();
        CurrentProcessId = GetCurrentProcessId();
        LODWORD(Arguments) = WORD1(v22[2]);
        nSize[0] = LOWORD(v22[2]);
        LODWORD(lpBuffer) = CurrentThreadId;
        StringCchPrintfW(
          OutputString,
          0x40u,
          L"APPMGMT (%x.%x) %02d:%02d:%02d:%03d ",
          CurrentProcessId,
          lpBuffer,
          *(_QWORD *)nSize,
          Arguments,
          WORD2(v22[2]),
          HIWORD(v22[2]));
        v8 = gDebugLevel;
        if ( (gDebugLevel & 0x40) == 0 )
        {
          OutputDebugStringW(OutputString);
          OutputDebugStringW(*(LPCWSTR *)Buffer);
          OutputDebugStringW(L"\r\n");
          v8 = gDebugLevel;
        }
        if ( (v8 & 8) != 0 )
        {
          v9 = (WCHAR *)LocalAlloc(0, 0x208u);
          v11 = v9;
          if ( v9 && (unsigned int)GetDebugLogFileName(v9, v10) )
          {
            v12 = OpenUnicodeLogFile(v11);
            v13 = -1;
            v14 = v12;
            if ( v12 != (void *)-1LL && SetFilePointer(v12, 0, 0, 2u) != -1 )
            {
              NumberOfBytesWritten[0] = 0;
              do
                ++v13;
              while ( *(_WORD *)(*(_QWORD *)Buffer + 2 * v13) );
              v15 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(2 * v13);
              WriteFile(v14, *(LPCVOID *)Buffer, v15, NumberOfBytesWritten, 0);
              v16 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(4);
              WriteFile(v14, L"\r\n", v16, NumberOfBytesWritten, 0);
            }
            CloseHandle(v14);
          }
          LocalFree(v11);
          v8 = gDebugLevel;
        }
        if ( !v5 && (v8 & 4) != 0 )
        {
          *(_QWORD *)NumberOfBytesWritten = 0;
          CEventsBase::Report((CEventsBase *)NumberOfBytesWritten, 0x191u, 0, 1u, *(_QWORD *)Buffer);
        }
        LocalFree(*(HLOCAL *)Buffer);
      }
    }
  }
}

```

## disassembly

```asm
0x180044814  mov     rax, rsp
0x180044817  mov     [rax+10h], edx
0x18004481a  mov     [rax+18h], r8
0x18004481e  mov     [rax+20h], r9
0x180044822  push    rbp
0x180044823  push    rbx
0x180044824  push    rsi
0x180044825  push    rdi
0x180044826  push    r12
0x180044828  push    r14
0x18004482a  push    r15
0x18004482c  lea     rbp, [rax-48h]
0x180044830  sub     rsp, 110h
0x180044837  mov     rax, cs:__security_cookie
0x18004483e  xor     rax, rsp
0x180044841  mov     [rbp+40h+var_40], rax
0x180044845  xor     r15d, r15d
0x180044848  xorps   xmm0, xmm0
0x18004484b  mov     r14d, ecx
0x18004484e  mov     qword ptr [rsp+140h+Buffer], r15
0x180044853  mov     qword ptr [rsp+140h+var_E0], r15
0x180044858  movups  xmmword ptr [rsp+140h+var_E0+8], xmm0
0x18004485d  lea     r12d, [r15+1]
0x180044861  cmp     cs:?gDebugEnabled@@3KA, r12d; ulong gDebugEnabled
0x180044868  jnz     short loc_180044892
0x18004486a  cmp     cs:?gDebugInitialized@@3KA, r15d; ulong gDebugInitialized
0x180044871  jnz     short loc_180044892
0x180044873  call    ?ApplyDebugSettings@@YAXXZ; ApplyDebugSettings(void)
0x180044878  cmp     cs:?gDebugEnabled@@3KA, r12d; ulong gDebugEnabled
0x18004487f  jnz     loc_180044AA2
0x180044885  cmp     cs:?gDebugInitialized@@3KA, r12d; ulong gDebugInitialized
0x18004488c  jnz     loc_180044AA2
0x180044892  mov     ecx, r14d; unsigned int
0x180044895  call    ?DebugLevelOn@@YAHK@Z; DebugLevelOn(ulong)
0x18004489a  test    eax, eax
0x18004489c  jz      loc_180044AA2
0x1800448a2  call    ?LoadLoadString@@YAHXZ; LoadLoadString(void)
0x1800448a7  test    eax, eax
0x1800448a9  jz      loc_180044AA2
0x1800448af  cmp     [rbp+40h+dwMessageId], 3E8h
0x1800448b6  lea     rax, [rbp+40h+arg_10]
0x1800448ba  mov     qword ptr [rsp+140h+var_E0], rax
0x1800448bf  mov     eax, r15d
0x1800448c2  jnb     short loc_1800448F7
0x1800448c4  call    ?AppmgmtGetHandleForCallingDll@@YAPEAUHINSTANCE__@@XZ; AppmgmtGetHandleForCallingDll(void)
0x1800448c9  mov     r8d, [rbp+40h+dwMessageId]; dwMessageId
0x1800448cd  mov     rdx, rax; lpSource
0x1800448d0  lea     rax, [rsp+140h+var_E0]
0x1800448d5  xor     r9d, r9d; dwLanguageId
0x1800448d8  mov     [rsp+140h+Arguments], rax; Arguments
0x1800448dd  mov     ecx, 900h; dwFlags
0x1800448e2  lea     rax, [rsp+140h+Buffer]
0x1800448e7  mov     [rsp+140h+nSize], r15d; nSize
0x1800448ec  mov     [rsp+140h+lpBuffer], rax; lpBuffer
0x1800448f1  call    cs:__imp_FormatMessageW
0x1800448f7  mov     qword ptr [rsp+140h+var_E0], r15
0x1800448fc  test    eax, eax
0x1800448fe  jz      loc_180044AA2
0x180044904  lea     rcx, [rsp+140h+var_E0+8]; lpSystemTime
0x180044909  and     r14d, 8
0x18004490d  call    cs:__imp_GetLocalTime
0x180044913  call    cs:__imp_GetCurrentThreadId
0x180044919  mov     ebx, eax
0x18004491b  call    cs:__imp_GetCurrentProcessId
0x180044921  movzx   ecx, word ptr [rsp+140h+var_E0+16h]
0x180044926  movzx   edx, word ptr [rsp+140h+var_E0+14h]
0x18004492b  movzx   r8d, word ptr [rsp+140h+var_E0+12h]
0x180044931  movzx   r9d, word ptr [rsp+140h+var_E0+10h]
0x180044937  mov     [rsp+40h], ecx
0x18004493b  lea     rcx, [rbp+40h+OutputString]; unsigned __int16 *
0x18004493f  mov     [rsp+140h+var_108], edx
0x180044943  mov     edx, 40h ; '@'; unsigned __int64
0x180044948  mov     dword ptr [rsp+140h+Arguments], r8d
0x18004494d  lea     r8, aAppmgmtXX02d02; "APPMGMT (%x.%x) %02d:%02d:%02d:%03d "
0x180044954  mov     [rsp+140h+nSize], r9d
0x180044959  mov     r9d, eax
0x18004495c  mov     dword ptr [rsp+140h+lpBuffer], ebx
0x180044960  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180044965  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x18004496b  test    al, 40h
0x18004496d  jnz     short loc_180044997
0x18004496f  lea     rcx, [rbp+40h+OutputString]; lpOutputString
0x180044973  call    cs:__imp_OutputDebugStringW
0x180044979  mov     rcx, qword ptr [rsp+140h+Buffer]; lpOutputString
0x18004497e  call    cs:__imp_OutputDebugStringW
0x180044984  lea     rcx, OutputString; "\r\n"
0x18004498b  call    cs:__imp_OutputDebugStringW
0x180044991  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x180044997  test    al, 8
0x180044999  jz      loc_180044A6A
0x18004499f  mov     edx, 208h; uBytes
0x1800449a4  xor     ecx, ecx; uFlags
0x1800449a6  call    cs:__imp_LocalAlloc
0x1800449ac  mov     rdi, rax
0x1800449af  test    rax, rax
0x1800449b2  jz      loc_180044A5B
0x1800449b8  mov     rcx, rax; lpDst
0x1800449bb  call    ?GetDebugLogFileName@@YAHPEAGJ@Z; GetDebugLogFileName(ushort *,long)
0x1800449c0  test    eax, eax
0x1800449c2  jz      loc_180044A5B
0x1800449c8  mov     rcx, rdi; lpFileName
0x1800449cb  call    ?OpenUnicodeLogFile@@YAPEAXPEBG@Z; OpenUnicodeLogFile(ushort const *)
0x1800449d0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800449d4  mov     rsi, rax
0x1800449d7  cmp     rax, rbx
0x1800449da  jz      short loc_180044A52
0x1800449dc  lea     r9d, [rbx+3]; dwMoveMethod
0x1800449e0  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800449e3  xor     edx, edx; lDistanceToMove
0x1800449e5  mov     rcx, rax; hFile
0x1800449e8  call    cs:__imp_SetFilePointer
0x1800449ee  cmp     eax, 0FFFFFFFFh
0x1800449f1  jz      short loc_180044A52
0x1800449f3  mov     rax, qword ptr [rsp+140h+Buffer]
0x1800449f8  mov     [rsp+140h+NumberOfBytesWritten], r15d
0x1800449fd  inc     rbx
0x180044a00  cmp     [rax+rbx*2], r15w
0x180044a05  jnz     short loc_1800449FD
0x180044a07  lea     rcx, [rbx+rbx]
0x180044a0b  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180044a10  mov     rdx, qword ptr [rsp+140h+Buffer]; lpBuffer
0x180044a15  lea     r9, [rsp+140h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180044a1a  mov     r8d, eax; nNumberOfBytesToWrite
0x180044a1d  mov     [rsp+140h+lpBuffer], r15; lpOverlapped
0x180044a22  mov     rcx, rsi; hFile
0x180044a25  call    cs:__imp_WriteFile
0x180044a2b  mov     ecx, 4
0x180044a30  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180044a35  mov     r8d, eax; nNumberOfBytesToWrite
0x180044a38  mov     [rsp+140h+lpBuffer], r15; lpOverlapped
0x180044a3d  lea     r9, [rsp+140h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180044a42  mov     rcx, rsi; hFile
0x180044a45  lea     rdx, OutputString; "\r\n"
0x180044a4c  call    cs:__imp_WriteFile
0x180044a52  mov     rcx, rsi; hObject
0x180044a55  call    cs:__imp_CloseHandle
0x180044a5b  mov     rcx, rdi; hMem
0x180044a5e  call    cs:__imp_LocalFree
0x180044a64  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x180044a6a  test    r14d, r14d
0x180044a6d  jnz     short loc_180044A97
0x180044a6f  test    al, 4
0x180044a71  jz      short loc_180044A97
0x180044a73  mov     rax, qword ptr [rsp+140h+Buffer]
0x180044a78  lea     rcx, [rsp+140h+NumberOfBytesWritten]; this
0x180044a7d  mov     r9d, r12d; unsigned __int16
0x180044a80  mov     [rsp+140h+lpBuffer], rax
0x180044a85  xor     r8d, r8d; int
0x180044a88  mov     qword ptr [rsp+140h+NumberOfBytesWritten], r15
0x180044a8d  mov     edx, 191h; unsigned int
0x180044a92  call    ?Report@CEventsBase@@QEAAXKHGZZ; CEventsBase::Report(ulong,int,ushort,...)
0x180044a97  mov     rcx, qword ptr [rsp+140h+Buffer]; hMem
0x180044a9c  call    cs:__imp_LocalFree
0x180044aa2  mov     rcx, [rbp+40h+var_40]
0x180044aa6  xor     rcx, rsp; StackCookie
0x180044aa9  call    __security_check_cookie
0x180044aae  add     rsp, 110h
0x180044ab5  pop     r15
0x180044ab7  pop     r14
0x180044ab9  pop     r12
0x180044abb  pop     rdi
0x180044abc  pop     rsi
0x180044abd  pop     rbx
0x180044abe  pop     rbp
0x180044abf  retn
```
