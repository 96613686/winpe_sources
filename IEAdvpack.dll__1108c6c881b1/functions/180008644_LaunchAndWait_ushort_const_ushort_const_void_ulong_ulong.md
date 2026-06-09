# LaunchAndWait(ushort const *,ushort const *,void * *,ulong,ulong)

- ea: `0x180008644`
- end: `0x180008851`
- name: `?LaunchAndWait@@YAJPEBG0PEAPEAXKK@Z`
- size: `525`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpCurrentDirectory, void **, DWORD, char)`
- caller_count: `6`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180004880`
- `0x1800079c0`
- `0x180009c14`
- `0x18000bdb0`
- `0x1800115b0`
- `0x180011940`

## callees

- `0x180002268`
- `0x180008644`
- `0x18000c574`
- `0x18001b94e`

## import_xrefs

- `USER32!PeekMessageW` at `0x1800087f3`
- `USER32!PeekMessageW` at `0x1800087f3`
- `USER32!MsgWaitForMultipleObjects` at `0x1800087a6`
- `USER32!MsgWaitForMultipleObjects` at `0x1800087a6`
- `USER32!DispatchMessageW` at `0x1800087db`
- `USER32!DispatchMessageW` at `0x1800087db`
- `KERNEL32!LocalFree` at `0x180008835`
- `KERNEL32!LocalFree` at `0x180008835`
- `KERNEL32!CloseHandle` at `0x18000875b`
- `KERNEL32!CloseHandle` at `0x180008816`
- `KERNEL32!CloseHandle` at `0x18000875b`
- `KERNEL32!CloseHandle` at `0x180008816`
- `KERNEL32!LocalAlloc` at `0x1800086b7`
- `KERNEL32!LocalAlloc` at `0x1800086b7`
- `KERNEL32!CreateProcessW` at `0x180008745`
- `KERNEL32!CreateProcessW` at `0x180008745`

## pseudocode

```c
__int64 __fastcall LaunchAndWait(const unsigned __int16 *a1, LPCWSTR lpCurrentDirectory, void **a3, DWORD a4, char a5)
{
  WCHAR *v9; // rdi
  __int64 v10; // rbx
  unsigned __int16 *v11; // rax
  unsigned int v12; // ebx
  int v13; // esi
  DWORD v14; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  MSG Msg; // [rsp+68h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE pHandles; // [rsp+160h] [rbp+60h] BYREF

  v9 = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( a3 )
    *a3 = 0;
  if ( a1 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a1[v10] );
    v11 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * (unsigned int)(v10 + 1));
    v9 = v11;
    if ( !v11 )
      goto LABEL_11;
    StringCchCopyNW(v11, (unsigned int)(v10 + 1), a1, (unsigned int)v10);
  }
  AdvWriteToLog(L"LaunchAndWait: Cmd=%1\r\n", v9);
  StartupInfo.cb = 104;
  StartupInfo.dwFlags |= 1u;
  StartupInfo.wShowWindow = (a5 & 1) == 0;
  if ( !CreateProcessW(0, v9, 0, 0, 0, 0x4000020u, 0, lpCurrentDirectory, &StartupInfo, &ProcessInformation) )
  {
LABEL_11:
    v12 = -2147467259;
    goto LABEL_25;
  }
  v12 = 0;
  pHandles = 0;
  CloseHandle(ProcessInformation.hThread);
  pHandles = ProcessInformation.hProcess;
  if ( a3 )
  {
    *a3 = ProcessInformation.hProcess;
  }
  else if ( (a5 & 2) == 0 )
  {
    v13 = 0;
    do
    {
      v14 = MsgWaitForMultipleObjects(1u, &pHandles, 0, a4, 0x1CFFu);
      if ( !v14 )
        break;
      if ( v14 == 258 )
      {
        AdvWriteToLog(L"LaunchAndWait: %1: TimedOut.\r\n", v9);
        break;
      }
      memset(&Msg, 0, sizeof(Msg));
      while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      {
        if ( Msg.message == 18 )
          v13 = 1;
        else
          DispatchMessageW(&Msg);
      }
    }
    while ( !v13 );
    CloseHandle(pHandles);
  }
LABEL_25:
  AdvWriteToLog(L"LaunchAndWait: End hr=0x%1!x!, %2\r\n", v12, v9);
  if ( v9 )
    LocalFree(v9);
  return v12;
}

```

## disassembly

```asm
0x180008644  push    rbp
0x180008646  push    rbx
0x180008647  push    rsi
0x180008648  push    rdi
0x180008649  push    r12
0x18000864b  push    r13
0x18000864d  push    r14
0x18000864f  push    r15
0x180008651  lea     rbp, [rsp-18h]
0x180008656  sub     rsp, 118h
0x18000865d  xor     r15d, r15d
0x180008660  mov     rsi, r8
0x180008663  mov     r12, rdx
0x180008666  mov     r14, rcx
0x180008669  xor     edx, edx; Val
0x18000866b  lea     rcx, [rbp+50h+StartupInfo]; void *
0x18000866f  mov     r13d, r9d
0x180008672  mov     edi, r15d
0x180008675  lea     r8d, [r15+68h]; Size
0x180008679  call    memset_0
0x18000867e  xor     eax, eax
0x180008680  xorps   xmm0, xmm0
0x180008683  mov     qword ptr [rsp+150h+ProcessInformation.dwProcessId], rax
0x180008688  movups  xmmword ptr [rsp+150h+ProcessInformation.hProcess], xmm0
0x18000868d  test    rsi, rsi
0x180008690  jz      short loc_180008695
0x180008692  mov     [rsi], r15
0x180008695  test    r14, r14
0x180008698  jz      short loc_1800086DD
0x18000869a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000869e  inc     rbx
0x1800086a1  cmp     [r14+rbx*2], r15w
0x1800086a6  jnz     short loc_18000869E
0x1800086a8  lea     eax, [rbx+1]
0x1800086ab  mov     ecx, 40h ; '@'; uFlags
0x1800086b0  lea     rdx, [rax+rax]; uBytes
0x1800086b4  mov     r15d, eax
0x1800086b7  call    cs:__imp_LocalAlloc
0x1800086bd  mov     rdi, rax
0x1800086c0  test    rax, rax
0x1800086c3  jz      loc_180008777
0x1800086c9  mov     r9d, ebx; unsigned __int64
0x1800086cc  mov     r8, r14; unsigned __int16 *
0x1800086cf  mov     edx, r15d; unsigned __int64
0x1800086d2  mov     rcx, rax; unsigned __int16 *
0x1800086d5  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800086da  xor     r15d, r15d
0x1800086dd  mov     rdx, rdi
0x1800086e0  lea     rcx, aLaunchandwaitC; "LaunchAndWait: Cmd=%1\r\n"
0x1800086e7  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x1800086ec  mov     r14d, 1
0x1800086f2  mov     [rbp+50h+StartupInfo.cb], 68h ; 'h'
0x1800086f9  or      [rbp+50h+StartupInfo.dwFlags], r14d
0x1800086fd  mov     [rbp+50h+StartupInfo.wShowWindow], r15w
0x180008702  test    byte ptr [rbp+50h+arg_20], r14b
0x180008709  jnz     short loc_180008710
0x18000870b  mov     [rbp+50h+StartupInfo.wShowWindow], r14w
0x180008710  lea     rax, [rsp+150h+ProcessInformation]
0x180008715  xor     r9d, r9d; lpThreadAttributes
0x180008718  mov     [rsp+150h+lpProcessInformation], rax; lpProcessInformation
0x18000871d  xor     r8d, r8d; lpProcessAttributes
0x180008720  lea     rax, [rbp+50h+StartupInfo]
0x180008724  mov     rdx, rdi; lpCommandLine
0x180008727  mov     [rsp+150h+lpStartupInfo], rax; lpStartupInfo
0x18000872c  xor     ecx, ecx; lpApplicationName
0x18000872e  mov     [rsp+150h+lpCurrentDirectory], r12; lpCurrentDirectory
0x180008733  mov     [rsp+150h+lpEnvironment], r15; lpEnvironment
0x180008738  mov     [rsp+150h+dwCreationFlags], 4000020h; dwCreationFlags
0x180008740  mov     [rsp+150h+bInheritHandles], r15d; bInheritHandles
0x180008745  call    cs:__imp_CreateProcessW
0x18000874b  test    eax, eax
0x18000874d  jz      short loc_180008777
0x18000874f  mov     rcx, [rsp+150h+ProcessInformation.hThread]; hObject
0x180008754  mov     ebx, r15d
0x180008757  mov     [rbp+50h+pHandles], r15
0x18000875b  call    cs:__imp_CloseHandle
0x180008761  mov     rax, [rsp+150h+ProcessInformation.hProcess]
0x180008766  mov     [rbp+50h+pHandles], rax
0x18000876a  test    rsi, rsi
0x18000876d  jz      short loc_180008781
0x18000876f  mov     [rsi], rax
0x180008772  jmp     loc_18000881C
0x180008777  mov     ebx, 80004005h
0x18000877c  jmp     loc_18000881C
0x180008781  test    byte ptr [rbp+50h+arg_20], 2
0x180008788  jnz     loc_18000881C
0x18000878e  mov     esi, r15d
0x180008791  mov     r9d, r13d; dwMilliseconds
0x180008794  mov     [rsp+150h+bInheritHandles], 1CFFh; dwWakeMask
0x18000879c  xor     r8d, r8d; fWaitAll
0x18000879f  lea     rdx, [rbp+50h+pHandles]; pHandles
0x1800087a3  mov     ecx, r14d; nCount
0x1800087a6  call    cs:__imp_MsgWaitForMultipleObjects
0x1800087ac  test    eax, eax
0x1800087ae  jz      short loc_180008812
0x1800087b0  cmp     eax, 102h
0x1800087b5  jz      short loc_180008803
0x1800087b7  xorps   xmm0, xmm0
0x1800087ba  movups  xmmword ptr [rsp+150h+Msg.hwnd], xmm0
0x1800087bf  movups  xmmword ptr [rsp+150h+Msg.wParam], xmm0
0x1800087c4  movups  xmmword ptr [rbp+50h+Msg.time], xmm0
0x1800087c8  jmp     short loc_1800087E1
0x1800087ca  cmp     [rsp+150h+Msg.message], 12h
0x1800087cf  jnz     short loc_1800087D6
0x1800087d1  mov     esi, r14d
0x1800087d4  jmp     short loc_1800087E1
0x1800087d6  lea     rcx, [rsp+150h+Msg]; lpMsg
0x1800087db  call    cs:__imp_DispatchMessageW
0x1800087e1  xor     r9d, r9d; wMsgFilterMax
0x1800087e4  mov     [rsp+150h+bInheritHandles], r14d; wRemoveMsg
0x1800087e9  xor     r8d, r8d; wMsgFilterMin
0x1800087ec  lea     rcx, [rsp+150h+Msg]; lpMsg
0x1800087f1  xor     edx, edx; hWnd
0x1800087f3  call    cs:__imp_PeekMessageW
0x1800087f9  test    eax, eax
0x1800087fb  jnz     short loc_1800087CA
0x1800087fd  test    esi, esi
0x1800087ff  jz      short loc_180008791
0x180008801  jmp     short loc_180008812
0x180008803  mov     rdx, rdi
0x180008806  lea     rcx, aLaunchandwait1; "LaunchAndWait: %1: TimedOut.\r\n"
0x18000880d  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180008812  mov     rcx, [rbp+50h+pHandles]; hObject
0x180008816  call    cs:__imp_CloseHandle
0x18000881c  mov     r8, rdi
0x18000881f  lea     rcx, aLaunchandwaitE; "LaunchAndWait: End hr=0x%1!x!, %2\r\n"
0x180008826  mov     edx, ebx
0x180008828  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000882d  test    rdi, rdi
0x180008830  jz      short loc_18000883B
0x180008832  mov     rcx, rdi; hMem
0x180008835  call    cs:__imp_LocalFree
0x18000883b  mov     eax, ebx
0x18000883d  add     rsp, 118h
0x180008844  pop     r15
0x180008846  pop     r14
0x180008848  pop     r13
0x18000884a  pop     r12
0x18000884c  pop     rdi
0x18000884d  pop     rsi
0x18000884e  pop     rbx
0x18000884f  pop     rbp
0x180008850  retn
```
