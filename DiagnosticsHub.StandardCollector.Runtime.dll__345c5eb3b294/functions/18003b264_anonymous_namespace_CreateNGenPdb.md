# _anonymous_namespace_::CreateNGenPdb

- ea: `0x18003b264`
- end: `0x18003b478`
- name: `_anonymous_namespace_::CreateNGenPdb`
- size: `532`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003ba48`

## callees

- `0x1800021fc`
- `0x180002604`
- `0x18000288c`
- `0x180027bc8`
- `0x18003b264`
- `0x18003d864`
- `0x180049b50`
- `0x18004ad26`
- `0x18004b640`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18003b37c`
- `KERNEL32!WaitForSingleObject` at `0x18003b37c`
- `KERNEL32!CreateProcessW` at `0x18003b34b`
- `KERNEL32!CreateProcessW` at `0x18003b34b`
- `KERNEL32!GetExitCodeProcess` at `0x18003b39d`
- `KERNEL32!GetExitCodeProcess` at `0x18003b39d`
- `KERNEL32!CloseHandle` at `0x18003b3c3`
- `KERNEL32!CloseHandle` at `0x18003b3d1`
- `KERNEL32!CloseHandle` at `0x18003b3c3`
- `KERNEL32!CloseHandle` at `0x18003b3d1`
- `KERNEL32!GetLastError` at `0x18003b355`
- `KERNEL32!GetLastError` at `0x18003b386`
- `KERNEL32!GetLastError` at `0x18003b355`
- `KERNEL32!GetLastError` at `0x18003b386`

## string_xrefs

- `0x18003b2bf`: `"%sngen.exe" createpdb "%s" "%s"`
- `0x18003b414`: `Failed to create NGen PDB: '%s' (HRESULT: %#08x)`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::CreateNGenPdb(__int64 a1, __int64 a2, __int64 a3)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  WCHAR *v7; // rdi
  signed int v8; // eax
  signed int v9; // r14d
  HANDLE hProcess; // rbx
  HANDLE hThread; // rsi
  signed int LastError; // eax
  DiagHubCommon::LogStream *v13; // rbx
  signed __int32 v14; // eax
  bool v15; // cc
  __int64 result; // rax
  BOOL bInheritHandles[2]; // [rsp+20h] [rbp-A9h]
  LPWSTR lpCommandLine; // [rsp+50h] [rbp-79h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-71h] BYREF
  DWORD ExitCode[4]; // [rsp+70h] [rbp-59h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-49h] BYREF

  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  lpCommandLine = (LPWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                         + 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &lpCommandLine,
    L"\"%sngen.exe\" createpdb \"%s\" \"%s\"",
    a1,
    a2,
    a3);
  v7 = lpCommandLine;
  if ( *((int *)lpCommandLine - 2) > 1 )
  {
    ATL::CSimpleStringT<unsigned short,0>::Fork(&lpCommandLine, *((unsigned int *)lpCommandLine - 4));
    v7 = lpCommandLine;
  }
  StartupInfo.cb = 104;
  memset_0(&StartupInfo.lpReserved, 0, 0x60u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( CreateProcessW(0, v7, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    hProcess = ProcessInformation.hProcess;
    hThread = ProcessInformation.hThread;
    if ( WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF)
      || (ExitCode[0] = 0, !GetExitCodeProcess(ProcessInformation.hProcess, ExitCode)) )
    {
      LastError = GetLastError();
    }
    else
    {
      LastError = ExitCode[0];
    }
    v9 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v9 = LastError;
    if ( hThread )
      CloseHandle(hThread);
    if ( hProcess )
      CloseHandle(hProcess);
  }
  else
  {
    v8 = GetLastError();
    v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 <= 0 )
      v9 = v8;
  }
  if ( v9 < 0 )
  {
    v13 = _logger;
    if ( *((_QWORD *)_logger + 21) != *((_QWORD *)_logger + 22) )
    {
      _mm_lfence();
      if ( *((int *)v7 - 2) > 1 )
      {
        ATL::CSimpleStringT<unsigned short,0>::Fork(&lpCommandLine, *((unsigned int *)v7 - 4));
        v7 = lpCommandLine;
      }
      bInheritHandles[0] = v9;
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)v13 + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
        L"Failed to create NGen PDB: '%s' (HRESULT: %#08x)",
        v7,
        *(_QWORD *)bInheritHandles);
    }
  }
  v14 = _InterlockedExchangeAdd((volatile signed __int32 *)v7 - 2, 0xFFFFFFFF);
  v15 = v14 <= 1;
  result = (unsigned int)(v14 - 1);
  if ( v15 )
  {
    _mm_lfence();
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v7 - 3) + 8LL))(*((_QWORD *)v7 - 3));
  }
  return result;
}

```

## disassembly

```asm
0x18003b264  push    rbp
0x18003b266  push    rbx
0x18003b267  push    rsi
0x18003b268  push    rdi
0x18003b269  push    r14
0x18003b26b  lea     rbp, [rsp-37h]
0x18003b270  sub     rsp, 100h
0x18003b277  mov     rax, cs:__security_cookie
0x18003b27e  xor     rax, rsp
0x18003b281  mov     [rbp+57h+var_30], rax
0x18003b285  mov     rsi, r8
0x18003b288  mov     rdi, rdx
0x18003b28b  mov     rbx, rcx
0x18003b28e  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x18003b293  mov     rcx, rax
0x18003b296  test    rax, rax
0x18003b299  jz      loc_18003B46D
0x18003b29f  mov     rax, [rax]
0x18003b2a2  mov     rax, [rax+18h]
0x18003b2a6  call    cs:__guard_dispatch_icall_fptr
0x18003b2ac  add     rax, 18h
0x18003b2b0  mov     [rbp+57h+lpCommandLine], rax
0x18003b2b4  mov     qword ptr [rsp+120h+bInheritHandles], rsi
0x18003b2b9  mov     r9, rdi
0x18003b2bc  mov     r8, rbx
0x18003b2bf  lea     rdx, aSngenExeCreate; "\"%sngen.exe\" createpdb \"%s\" \"%s\""
0x18003b2c6  lea     rcx, [rbp+57h+lpCommandLine]
0x18003b2ca  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18003b2cf  mov     rdi, [rbp+57h+lpCommandLine]
0x18003b2d3  cmp     dword ptr [rdi-8], 1
0x18003b2d7  jle     short loc_18003B2E9
0x18003b2d9  mov     edx, [rdi-10h]
0x18003b2dc  lea     rcx, [rbp+57h+lpCommandLine]
0x18003b2e0  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18003b2e5  mov     rdi, [rbp+57h+lpCommandLine]
0x18003b2e9  mov     [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x18003b2f0  xor     edx, edx; Val
0x18003b2f2  lea     r8d, [rdx+60h]; Size
0x18003b2f6  lea     rcx, [rbp+57h+StartupInfo.lpReserved]; void *
0x18003b2fa  call    memset_0
0x18003b2ff  xorps   xmm0, xmm0
0x18003b302  xor     eax, eax
0x18003b304  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x18003b308  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x18003b30c  lea     rax, [rbp+57h+ProcessInformation]
0x18003b310  mov     [rsp+120h+lpProcessInformation], rax; lpProcessInformation
0x18003b315  lea     rax, [rbp+57h+StartupInfo]
0x18003b319  mov     [rsp+120h+lpStartupInfo], rax; lpStartupInfo
0x18003b31e  mov     [rsp+120h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18003b327  mov     [rsp+120h+lpEnvironment], 0; lpEnvironment
0x18003b330  mov     [rsp+120h+dwCreationFlags], 8000000h; dwCreationFlags
0x18003b338  mov     [rsp+120h+bInheritHandles], 0; bInheritHandles
0x18003b340  xor     r9d, r9d; lpThreadAttributes
0x18003b343  xor     r8d, r8d; lpProcessAttributes
0x18003b346  mov     rdx, rdi; lpCommandLine
0x18003b349  xor     ecx, ecx; lpApplicationName
0x18003b34b  call    cs:__imp_CreateProcessW
0x18003b351  test    eax, eax
0x18003b353  jnz     short loc_18003B36E
0x18003b355  call    cs:__imp_GetLastError
0x18003b35b  movzx   r14d, ax
0x18003b35f  or      r14d, 80070000h
0x18003b366  test    eax, eax
0x18003b368  cmovle  r14d, eax
0x18003b36c  jmp     short loc_18003B3D7
0x18003b36e  mov     rbx, [rbp+57h+ProcessInformation.hProcess]
0x18003b372  mov     rsi, [rbp+57h+ProcessInformation.hThread]
0x18003b376  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003b379  mov     rcx, rbx; hHandle
0x18003b37c  call    cs:__imp_WaitForSingleObject
0x18003b382  test    eax, eax
0x18003b384  jz      short loc_18003B38E
0x18003b386  call    cs:__imp_GetLastError
0x18003b38c  jmp     short loc_18003B3AA
0x18003b38e  mov     [rbp+57h+ExitCode], 0
0x18003b395  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x18003b399  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hProcess
0x18003b39d  call    cs:__imp_GetExitCodeProcess
0x18003b3a3  test    eax, eax
0x18003b3a5  jz      short loc_18003B386
0x18003b3a7  mov     eax, [rbp+57h+ExitCode]
0x18003b3aa  movzx   r14d, ax
0x18003b3ae  or      r14d, 80070000h
0x18003b3b5  test    eax, eax
0x18003b3b7  cmovle  r14d, eax
0x18003b3bb  test    rsi, rsi
0x18003b3be  jz      short loc_18003B3C9
0x18003b3c0  mov     rcx, rsi; hObject
0x18003b3c3  call    cs:__imp_CloseHandle
0x18003b3c9  test    rbx, rbx
0x18003b3cc  jz      short loc_18003B3D7
0x18003b3ce  mov     rcx, rbx; hObject
0x18003b3d1  call    cs:__imp_CloseHandle
0x18003b3d7  test    r14d, r14d
0x18003b3da  jns     short loc_18003B42F
0x18003b3dc  mov     rbx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003b3e3  mov     rax, [rbx+0B0h]
0x18003b3ea  cmp     [rbx+0A8h], rax
0x18003b3f1  jz      short loc_18003B42F
0x18003b3f3  lfence
0x18003b3f6  cmp     dword ptr [rdi-8], 1
0x18003b3fa  jle     short loc_18003B40C
0x18003b3fc  mov     edx, [rdi-10h]
0x18003b3ff  lea     rcx, [rbp+57h+lpCommandLine]
0x18003b403  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18003b408  mov     rdi, [rbp+57h+lpCommandLine]
0x18003b40c  mov     [rsp+120h+bInheritHandles], r14d
0x18003b411  mov     r9, rdi
0x18003b414  lea     r8, aFailedToCreate; "Failed to create NGen PDB: '%s' (HRESUL"...
0x18003b41b  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003b422  lea     rcx, [rbx+0A8h]; this
0x18003b429  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003b42e  nop
0x18003b42f  lea     rdx, [rdi-18h]
0x18003b433  or      eax, 0FFFFFFFFh
0x18003b436  lock xadd [rdx+10h], eax
0x18003b43b  sub     eax, 1
0x18003b43e  jg      short loc_18003B453
0x18003b440  lfence
0x18003b443  mov     rcx, [rdx]
0x18003b446  mov     rax, [rcx]
0x18003b449  mov     rax, [rax+8]
0x18003b44d  call    cs:__guard_dispatch_icall_fptr
0x18003b453  mov     rcx, [rbp+57h+var_30]
0x18003b457  xor     rcx, rsp; StackCookie
0x18003b45a  call    __security_check_cookie
0x18003b45f  add     rsp, 100h
0x18003b466  pop     r14
0x18003b468  pop     rdi
0x18003b469  pop     rsi
0x18003b46a  pop     rbx
0x18003b46b  pop     rbp
0x18003b46c  retn
0x18003b46d  mov     ecx, 80004005h; int
0x18003b472  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
