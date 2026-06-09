# CMiscHelpersT<CEmptyType>::LaunchProcessInternal(ushort const *,ushort const *,_STARTUPINFOW *,ulong,int,uint,ulong *)

- ea: `0x140012f84`
- end: `0x14001316e`
- name: `?LaunchProcessInternal@?$CMiscHelpersT@VCEmptyType@@@@CAJPEBG0PEAU_STARTUPINFOW@@KHIPEAK@Z`
- size: `490`
- prototype: `__int64 __fastcall(__int64, __int64, struct _STARTUPINFOW *, DWORD, DWORD ExitCode, __int64, DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007494`
- `0x140011f98`

## callees

- `0x1400076c8`
- `0x140012f84`
- `0x1400135b8`
- `0x14001d4ac`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140013131`
- `KERNEL32!CloseHandle` at `0x140013145`
- `KERNEL32!CloseHandle` at `0x140013131`
- `KERNEL32!CloseHandle` at `0x140013145`
- `KERNEL32!CreateProcessW` at `0x14001305a`
- `KERNEL32!CreateProcessW` at `0x14001305a`
- `KERNEL32!GetExitCodeProcess` at `0x1400130d6`
- `KERNEL32!GetExitCodeProcess` at `0x1400130d6`
- `KERNEL32!HeapFree` at `0x140013116`
- `KERNEL32!HeapFree` at `0x140013116`
- `KERNEL32!GetProcessHeap` at `0x140013101`
- `KERNEL32!GetProcessHeap` at `0x140013101`
- `KERNEL32!GetLastError` at `0x14001306a`
- `KERNEL32!GetLastError` at `0x14001306a`
- `KERNEL32!WaitForSingleObject` at `0x1400130ac`
- `KERNEL32!WaitForSingleObject` at `0x1400130ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMiscHelpersT<CEmptyType>::LaunchProcessInternal(
        __int64 a1,
        __int64 a2,
        struct _STARTUPINFOW *a3,
        DWORD a4,
        DWORD ExitCode,
        __int64 a6,
        DWORD *a7)
{
  LPWSTR v7; // rsi
  HANDLE hProcess; // rbx
  HANDLE hThread; // rdi
  int v12; // eax
  unsigned int v13; // r14d
  signed int LastError; // eax
  DWORD v15; // eax
  HANDLE ProcessHeap; // rax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-20h] BYREF
  LPWSTR lpCommandLine; // [rsp+A0h] [rbp+30h] BYREF

  v7 = 0;
  ExitCode = 0;
  lpCommandLine = 0;
  hProcess = 0;
  hThread = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( a1 )
  {
    v12 = STRAPI_Format(&lpCommandLine, L"\"%s\" %s", a1, a2);
  }
  else
  {
    if ( !a2 )
    {
      v13 = -2147024809;
LABEL_7:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
      goto LABEL_20;
    }
    v12 = STRAPI_Format(&lpCommandLine, L"%s", a2);
  }
  v13 = v12;
  if ( v12 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v12);
    v7 = lpCommandLine;
    goto LABEL_20;
  }
  v7 = lpCommandLine;
  if ( !CreateProcessW(0, lpCommandLine, 0, 0, (a3->dwFlags >> 8) & 1, a4, 0, 0, a3, &ProcessInformation) )
    goto LABEL_10;
  hProcess = ProcessInformation.hProcess;
  hThread = ProcessInformation.hThread;
  v15 = WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
  if ( v15 )
  {
    if ( v15 == 258 )
    {
      v13 = -2147023436;
      goto LABEL_7;
    }
    goto LABEL_11;
  }
  if ( !GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
  {
LABEL_10:
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_7;
    }
LABEL_11:
    v13 = -2147467259;
    goto LABEL_7;
  }
  if ( a7 )
    *a7 = ExitCode;
LABEL_20:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( hThread )
    CloseHandle(hThread);
  if ( hProcess )
    CloseHandle(hProcess);
  return v13;
}

```

## disassembly

```asm
0x140012f84  mov     [rsp-28h+arg_8], rbx
0x140012f89  mov     [rsp-28h+arg_10], rsi
0x140012f8e  push    rbp
0x140012f8f  push    rdi
0x140012f90  push    r12
0x140012f92  push    r14
0x140012f94  push    r15
0x140012f96  mov     rbp, rsp
0x140012f99  sub     rsp, 70h
0x140012f9d  xor     esi, esi
0x140012f9f  mov     [rbp+ExitCode], 0
0x140012fa6  xor     eax, eax
0x140012fa8  mov     [rbp+lpCommandLine], rsi
0x140012fac  xor     ebx, ebx
0x140012fae  mov     qword ptr [rbp+ProcessInformation.dwProcessId], rax
0x140012fb2  xor     edi, edi
0x140012fb4  xorps   xmm0, xmm0
0x140012fb7  mov     r12d, r9d
0x140012fba  mov     r15, r8
0x140012fbd  movups  xmmword ptr [rbp+ProcessInformation.hProcess], xmm0
0x140012fc1  test    rcx, rcx
0x140012fc4  jz      short loc_140012FF3
0x140012fc6  mov     r9, rdx
0x140012fc9  mov     r8, rcx
0x140012fcc  lea     rdx, aSS_6; "\"%s\" %s"
0x140012fd3  lea     rcx, [rbp+lpCommandLine]; unsigned __int16 **
0x140012fd7  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x140012fdc  mov     r14d, eax
0x140012fdf  test    eax, eax
0x140012fe1  jns     short loc_140013020
0x140012fe3  mov     ecx, eax
0x140012fe5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140012fea  mov     rsi, [rbp+lpCommandLine]
0x140012fee  jmp     loc_1400130F4
0x140012ff3  test    rdx, rdx
0x140012ff6  jnz     short loc_14001300B
0x140012ff8  mov     r14d, 80070057h
0x140012ffe  mov     ecx, r14d
0x140013001  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140013006  jmp     loc_1400130F4
0x14001300b  mov     r8, rdx
0x14001300e  lea     rcx, [rbp+lpCommandLine]; unsigned __int16 **
0x140013012  lea     rdx, aS_2; "%s"
0x140013019  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x14001301e  jmp     short loc_140012FDC
0x140013020  mov     eax, [r15+3Ch]
0x140013024  lea     rcx, [rbp+ProcessInformation]
0x140013028  mov     rsi, [rbp+lpCommandLine]
0x14001302c  xor     r9d, r9d; lpThreadAttributes
0x14001302f  mov     [rsp+70h+lpProcessInformation], rcx; lpProcessInformation
0x140013034  xor     r8d, r8d; lpProcessAttributes
0x140013037  mov     [rsp+70h+lpStartupInfo], r15; lpStartupInfo
0x14001303c  mov     rdx, rsi; lpCommandLine
0x14001303f  mov     [rsp+70h+lpCurrentDirectory], rbx; lpCurrentDirectory
0x140013044  xor     ecx, ecx; lpApplicationName
0x140013046  shr     eax, 8
0x140013049  mov     [rsp+70h+lpEnvironment], rbx; lpEnvironment
0x14001304e  and     eax, 1
0x140013051  mov     [rsp+70h+dwCreationFlags], r12d; dwCreationFlags
0x140013056  mov     [rsp+70h+bInheritHandles], eax; bInheritHandles
0x14001305a  call    cs:__imp_CreateProcessW
0x140013061  nop     dword ptr [rax+rax+00h]
0x140013066  test    eax, eax
0x140013068  jnz     short loc_14001309E
0x14001306a  call    cs:__imp_GetLastError
0x140013071  nop     dword ptr [rax+rax+00h]
0x140013076  mov     r14d, eax
0x140013079  test    eax, eax
0x14001307b  jnz     short loc_140013088
0x14001307d  mov     r14d, 80004005h
0x140013083  jmp     loc_140012FFE
0x140013088  jle     loc_140012FFE
0x14001308e  movzx   r14d, ax
0x140013092  or      r14d, 80070000h
0x140013099  jmp     loc_140012FFE
0x14001309e  mov     rbx, [rbp+ProcessInformation.hProcess]
0x1400130a2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400130a5  mov     rdi, [rbp+ProcessInformation.hThread]
0x1400130a9  mov     rcx, rbx; hHandle
0x1400130ac  call    cs:__imp_WaitForSingleObject
0x1400130b3  nop     dword ptr [rax+rax+00h]
0x1400130b8  test    eax, eax
0x1400130ba  jz      short loc_1400130CE
0x1400130bc  cmp     eax, 102h
0x1400130c1  jnz     short loc_14001307D
0x1400130c3  mov     r14d, 800705B4h
0x1400130c9  jmp     loc_140012FFE
0x1400130ce  mov     rcx, [rbp+ProcessInformation.hProcess]; hProcess
0x1400130d2  lea     rdx, [rbp+ExitCode]; lpExitCode
0x1400130d6  call    cs:__imp_GetExitCodeProcess
0x1400130dd  nop     dword ptr [rax+rax+00h]
0x1400130e2  test    eax, eax
0x1400130e4  jz      short loc_14001306A
0x1400130e6  mov     rcx, [rbp+arg_30]
0x1400130ea  test    rcx, rcx
0x1400130ed  jz      short loc_1400130F4
0x1400130ef  mov     eax, [rbp+ExitCode]
0x1400130f2  mov     [rcx], eax
0x1400130f4  mov     ecx, r14d
0x1400130f7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400130fc  test    rsi, rsi
0x1400130ff  jz      short loc_140013129
0x140013101  call    cs:__imp_GetProcessHeap
0x140013108  nop     dword ptr [rax+rax+00h]
0x14001310d  lea     r8, [rsi-4]; lpMem
0x140013111  xor     edx, edx; dwFlags
0x140013113  mov     rcx, rax; hHeap
0x140013116  call    cs:__imp_HeapFree
0x14001311d  nop     dword ptr [rax+rax+00h]
0x140013122  xor     ecx, ecx
0x140013124  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140013129  test    rdi, rdi
0x14001312c  jz      short loc_14001313D
0x14001312e  mov     rcx, rdi; hObject
0x140013131  call    cs:__imp_CloseHandle
0x140013138  nop     dword ptr [rax+rax+00h]
0x14001313d  test    rbx, rbx
0x140013140  jz      short loc_140013151
0x140013142  mov     rcx, rbx; hObject
0x140013145  call    cs:__imp_CloseHandle
0x14001314c  nop     dword ptr [rax+rax+00h]
0x140013151  lea     r11, [rsp+70h+var_s0]
0x140013156  mov     eax, r14d
0x140013159  mov     rbx, [r11+38h]
0x14001315d  mov     rsi, [r11+40h]
0x140013161  mov     rsp, r11
0x140013164  pop     r15
0x140013166  pop     r14
0x140013168  pop     r12
0x14001316a  pop     rdi
0x14001316b  pop     rbp
0x14001316c  retn
```
