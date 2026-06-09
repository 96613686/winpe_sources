# _DebugMsg(ulong,ulong,...)

- ea: `0x180049e60`
- end: `0x18004a165`
- name: `?_DebugMsg@@YAXKKZZ`
- size: `773`
- prototype: `void(unsigned int, unsigned int, ...)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callers

- `0x180032b10`
- `0x18003a788`
- `0x18004a2d0`

## callees

- `0x1800028d8`
- `0x18003b024`
- `0x180048850`
- `0x180048a84`
- `0x1800490c0`
- `0x1800490f8`
- `0x1800493b4`
- `0x180049c20`
- `0x180049e60`
- `0x18004a2d0`
- `0x1800720b0`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18004a01c`
- `KERNELBASE!LocalAlloc` at `0x18004a01c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049f6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049f6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180049f79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180049f79`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180049f5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180049f5f`
- `KERNEL32!LocalFree` at `0x18004a0f6`
- `KERNEL32!LocalFree` at `0x18004a13a`
- `KERNEL32!LocalFree` at `0x18004a0f6`
- `KERNEL32!LocalFree` at `0x18004a13a`
- `KERNEL32!CloseHandle` at `0x18004a0e7`
- `KERNEL32!CloseHandle` at `0x18004a0e7`
- `KERNEL32!WriteFile` at `0x18004a0ab`
- `KERNEL32!WriteFile` at `0x18004a0d8`
- `KERNEL32!WriteFile` at `0x18004a0ab`
- `KERNEL32!WriteFile` at `0x18004a0d8`
- `KERNEL32!SetFilePointer` at `0x18004a068`
- `KERNEL32!SetFilePointer` at `0x18004a068`
- `KERNEL32!FormatMessageW` at `0x180049f3d`
- `KERNEL32!FormatMessageW` at `0x180049f3d`
- `KERNEL32!OutputDebugStringW` at `0x180049fd7`
- `KERNEL32!OutputDebugStringW` at `0x180049fe8`
- `KERNEL32!OutputDebugStringW` at `0x180049ffb`
- `KERNEL32!OutputDebugStringW` at `0x180049fd7`
- `KERNEL32!OutputDebugStringW` at `0x180049fe8`
- `KERNEL32!OutputDebugStringW` at `0x180049ffb`

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
0x180049e60  mov     rax, rsp
0x180049e63  mov     [rax+10h], edx
0x180049e66  mov     [rax+18h], r8
0x180049e6a  mov     [rax+20h], r9
0x180049e6e  push    rbp
0x180049e6f  push    rbx
0x180049e70  push    rsi
0x180049e71  push    rdi
0x180049e72  push    r12
0x180049e74  push    r14
0x180049e76  push    r15
0x180049e78  lea     rbp, [rax-48h]
0x180049e7c  sub     rsp, 110h
0x180049e83  mov     rax, cs:__security_cookie
0x180049e8a  xor     rax, rsp
0x180049e8d  mov     [rbp+40h+var_40], rax
0x180049e91  xor     r15d, r15d
0x180049e94  xorps   xmm0, xmm0
0x180049e97  mov     r14d, ecx
0x180049e9a  mov     qword ptr [rsp+140h+Buffer], r15
0x180049e9f  mov     qword ptr [rsp+140h+var_E0], r15
0x180049ea4  movups  xmmword ptr [rsp+140h+var_E0+8], xmm0
0x180049ea9  lea     r12d, [r15+1]
0x180049ead  cmp     cs:?gDebugEnabled@@3KA, r12d; ulong gDebugEnabled
0x180049eb4  jnz     short loc_180049EDE
0x180049eb6  cmp     cs:?gDebugInitialized@@3KA, r15d; ulong gDebugInitialized
0x180049ebd  jnz     short loc_180049EDE
0x180049ebf  call    ?ApplyDebugSettings@@YAXXZ; ApplyDebugSettings(void)
0x180049ec4  cmp     cs:?gDebugEnabled@@3KA, r12d; ulong gDebugEnabled
0x180049ecb  jnz     loc_18004A146
0x180049ed1  cmp     cs:?gDebugInitialized@@3KA, r12d; ulong gDebugInitialized
0x180049ed8  jnz     loc_18004A146
0x180049ede  mov     ecx, r14d; unsigned int
0x180049ee1  call    ?DebugLevelOn@@YAHK@Z; DebugLevelOn(ulong)
0x180049ee6  test    eax, eax
0x180049ee8  jz      loc_18004A146
0x180049eee  call    ?LoadLoadString@@YAHXZ; LoadLoadString(void)
0x180049ef3  test    eax, eax
0x180049ef5  jz      loc_18004A146
0x180049efb  cmp     [rbp+40h+dwMessageId], 3E8h
0x180049f02  lea     rax, [rbp+40h+arg_10]
0x180049f06  mov     qword ptr [rsp+140h+var_E0], rax
0x180049f0b  mov     eax, r15d
0x180049f0e  jnb     short loc_180049F49
0x180049f10  call    ?AppmgmtGetHandleForCallingDll@@YAPEAUHINSTANCE__@@XZ; AppmgmtGetHandleForCallingDll(void)
0x180049f15  mov     r8d, [rbp+40h+dwMessageId]; dwMessageId
0x180049f19  mov     rdx, rax; lpSource
0x180049f1c  lea     rax, [rsp+140h+var_E0]
0x180049f21  xor     r9d, r9d; dwLanguageId
0x180049f24  mov     [rsp+140h+Arguments], rax; Arguments
0x180049f29  mov     ecx, 900h; dwFlags
0x180049f2e  lea     rax, [rsp+140h+Buffer]
0x180049f33  mov     [rsp+140h+nSize], r15d; nSize
0x180049f38  mov     [rsp+140h+lpBuffer], rax; lpBuffer
0x180049f3d  call    cs:__imp_FormatMessageW
0x180049f44  nop     dword ptr [rax+rax+00h]
0x180049f49  mov     qword ptr [rsp+140h+var_E0], r15
0x180049f4e  test    eax, eax
0x180049f50  jz      loc_18004A146
0x180049f56  lea     rcx, [rsp+140h+var_E0+8]; lpSystemTime
0x180049f5b  and     r14d, 8
0x180049f5f  call    cs:__imp_GetLocalTime
0x180049f66  nop     dword ptr [rax+rax+00h]
0x180049f6b  call    cs:__imp_GetCurrentThreadId
0x180049f72  nop     dword ptr [rax+rax+00h]
0x180049f77  mov     ebx, eax
0x180049f79  call    cs:__imp_GetCurrentProcessId
0x180049f80  nop     dword ptr [rax+rax+00h]
0x180049f85  movzx   ecx, word ptr [rsp+140h+var_E0+16h]
0x180049f8a  movzx   edx, word ptr [rsp+140h+var_E0+14h]
0x180049f8f  movzx   r8d, word ptr [rsp+140h+var_E0+12h]
0x180049f95  movzx   r9d, word ptr [rsp+140h+var_E0+10h]
0x180049f9b  mov     [rsp+40h], ecx
0x180049f9f  lea     rcx, [rbp+40h+OutputString]; unsigned __int16 *
0x180049fa3  mov     [rsp+140h+var_108], edx
0x180049fa7  mov     edx, 40h ; '@'; unsigned __int64
0x180049fac  mov     dword ptr [rsp+140h+Arguments], r8d
0x180049fb1  lea     r8, aAppmgmtXX02d02; "APPMGMT (%x.%x) %02d:%02d:%02d:%03d "
0x180049fb8  mov     [rsp+140h+nSize], r9d
0x180049fbd  mov     r9d, eax
0x180049fc0  mov     dword ptr [rsp+140h+lpBuffer], ebx
0x180049fc4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180049fc9  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x180049fcf  test    al, 40h
0x180049fd1  jnz     short loc_18004A00D
0x180049fd3  lea     rcx, [rbp+40h+OutputString]; lpOutputString
0x180049fd7  call    cs:__imp_OutputDebugStringW
0x180049fde  nop     dword ptr [rax+rax+00h]
0x180049fe3  mov     rcx, qword ptr [rsp+140h+Buffer]; lpOutputString
0x180049fe8  call    cs:__imp_OutputDebugStringW
0x180049fef  nop     dword ptr [rax+rax+00h]
0x180049ff4  lea     rcx, OutputString; "\r\n"
0x180049ffb  call    cs:__imp_OutputDebugStringW
0x18004a002  nop     dword ptr [rax+rax+00h]
0x18004a007  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x18004a00d  test    al, 8
0x18004a00f  jz      loc_18004A108
0x18004a015  mov     edx, 208h; uBytes
0x18004a01a  xor     ecx, ecx; uFlags
0x18004a01c  call    cs:__imp_LocalAlloc
0x18004a023  nop     dword ptr [rax+rax+00h]
0x18004a028  mov     rdi, rax
0x18004a02b  test    rax, rax
0x18004a02e  jz      loc_18004A0F3
0x18004a034  mov     rcx, rax; lpDst
0x18004a037  call    ?GetDebugLogFileName@@YAHPEAGJ@Z; GetDebugLogFileName(ushort *,long)
0x18004a03c  test    eax, eax
0x18004a03e  jz      loc_18004A0F3
0x18004a044  mov     rcx, rdi; lpFileName
0x18004a047  call    ?OpenUnicodeLogFile@@YAPEAXPEBG@Z; OpenUnicodeLogFile(ushort const *)
0x18004a04c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004a050  mov     rsi, rax
0x18004a053  cmp     rax, rbx
0x18004a056  jz      loc_18004A0E4
0x18004a05c  lea     r9d, [rbx+3]; dwMoveMethod
0x18004a060  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004a063  xor     edx, edx; lDistanceToMove
0x18004a065  mov     rcx, rax; hFile
0x18004a068  call    cs:__imp_SetFilePointer
0x18004a06f  nop     dword ptr [rax+rax+00h]
0x18004a074  cmp     eax, 0FFFFFFFFh
0x18004a077  jz      short loc_18004A0E4
0x18004a079  mov     rax, qword ptr [rsp+140h+Buffer]
0x18004a07e  mov     [rsp+140h+NumberOfBytesWritten], r15d
0x18004a083  inc     rbx
0x18004a086  cmp     [rax+rbx*2], r15w
0x18004a08b  jnz     short loc_18004A083
0x18004a08d  lea     rcx, [rbx+rbx]
0x18004a091  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18004a096  mov     rdx, qword ptr [rsp+140h+Buffer]; lpBuffer
0x18004a09b  lea     r9, [rsp+140h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18004a0a0  mov     r8d, eax; nNumberOfBytesToWrite
0x18004a0a3  mov     [rsp+140h+lpBuffer], r15; lpOverlapped
0x18004a0a8  mov     rcx, rsi; hFile
0x18004a0ab  call    cs:__imp_WriteFile
0x18004a0b2  nop     dword ptr [rax+rax+00h]
0x18004a0b7  mov     ecx, 4
0x18004a0bc  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18004a0c1  mov     r8d, eax; nNumberOfBytesToWrite
0x18004a0c4  mov     [rsp+140h+lpBuffer], r15; lpOverlapped
0x18004a0c9  lea     r9, [rsp+140h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18004a0ce  mov     rcx, rsi; hFile
0x18004a0d1  lea     rdx, OutputString; "\r\n"
0x18004a0d8  call    cs:__imp_WriteFile
0x18004a0df  nop     dword ptr [rax+rax+00h]
0x18004a0e4  mov     rcx, rsi; hObject
0x18004a0e7  call    cs:__imp_CloseHandle
0x18004a0ee  nop     dword ptr [rax+rax+00h]
0x18004a0f3  mov     rcx, rdi; hMem
0x18004a0f6  call    cs:__imp_LocalFree
0x18004a0fd  nop     dword ptr [rax+rax+00h]
0x18004a102  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x18004a108  test    r14d, r14d
0x18004a10b  jnz     short loc_18004A135
0x18004a10d  test    al, 4
0x18004a10f  jz      short loc_18004A135
0x18004a111  mov     rax, qword ptr [rsp+140h+Buffer]
0x18004a116  lea     rcx, [rsp+140h+NumberOfBytesWritten]; this
0x18004a11b  mov     r9d, r12d; unsigned __int16
0x18004a11e  mov     [rsp+140h+lpBuffer], rax
0x18004a123  xor     r8d, r8d; int
0x18004a126  mov     qword ptr [rsp+140h+NumberOfBytesWritten], r15
0x18004a12b  mov     edx, 191h; unsigned int
0x18004a130  call    ?Report@CEventsBase@@QEAAXKHGZZ; CEventsBase::Report(ulong,int,ushort,...)
0x18004a135  mov     rcx, qword ptr [rsp+140h+Buffer]; hMem
0x18004a13a  call    cs:__imp_LocalFree
0x18004a141  nop     dword ptr [rax+rax+00h]
0x18004a146  mov     rcx, [rbp+40h+var_40]
0x18004a14a  xor     rcx, rsp; StackCookie
0x18004a14d  call    __security_check_cookie
0x18004a152  add     rsp, 110h
0x18004a159  pop     r15
0x18004a15b  pop     r14
0x18004a15d  pop     r12
0x18004a15f  pop     rdi
0x18004a160  pop     rsi
0x18004a161  pop     rbx
0x18004a162  pop     rbp
0x18004a163  retn
```
