# PrepareCrashDataPayload

- ea: `0x140005210`
- end: `0x140005589`
- name: `PrepareCrashDataPayload`
- size: `889`
- prototype: `__int64 __fastcall(int, int, int, int, HANDLE hTargetProcessHandle, HANDLE hSourceHandle, HANDLE)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140005590`

## callees

- `0x140005128`
- `0x140005210`
- `0x14000e598`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000525f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400052f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140005386`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000525f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400052f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140005386`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400052a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000533e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400053bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000542a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400052a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000533e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400053bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000542a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140005290`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14000531b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400053b2`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140005290`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14000531b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400053b2`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140005414`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140005414`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140005522`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140005522`

## string_xrefs

- `0x1400052c7`: `DuplicateHandle/hSharedMemTemplate failed`
- `0x1400052de`: `onecore\windows\feedback\core\werfault\exe\secure\protectedbroker.cpp`
- `0x140005333`: `onecore\windows\feedback\core\werfault\exe\secure\protectedbroker.cpp`
- `0x1400053d5`: `DuplicateHandle/hCompletionEvent failed`
- `0x140005445`: `MapViewOfFile/hLocalSharedMemTemplate failed`
- `0x1400054a9`: `hRemoteCompletionEvent: 0x%p`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PrepareCrashDataPayload(
        _DWORD *a1,
        _QWORD *a2,
        HANDLE *a3,
        unsigned int *a4,
        HANDLE hTargetProcessHandle,
        HANDLE hSourceHandle,
        HANDLE a7)
{
  HANDLE CurrentProcess; // rax
  HANDLE v9; // rbx
  signed int v10; // eax
  signed int v11; // ebx
  HANDLE v12; // rax
  signed int LastError; // eax
  bool v14; // sf
  HANDLE v15; // rax
  signed int v16; // eax
  bool v17; // sf
  _QWORD *v18; // rbx
  signed int v19; // eax
  HANDLE v20; // rdx
  HANDLE *v21; // r8
  unsigned int v22; // ebx
  wil::details *dwDesiredAccess; // [rsp+20h] [rbp-40h]
  wil::details *dwDesiredAccessa; // [rsp+20h] [rbp-40h]
  wil::details *dwDesiredAccessb; // [rsp+20h] [rbp-40h]
  wil::details *dwDesiredAccessc; // [rsp+20h] [rbp-40h]
  wil::details *dwDesiredAccessd; // [rsp+20h] [rbp-40h]
  wil::details *dwDesiredAccesse; // [rsp+20h] [rbp-40h]
  const char *dwOptions; // [rsp+30h] [rbp-30h]
  const char *dwOptionsa; // [rsp+30h] [rbp-30h]
  HANDLE v32; // [rsp+40h] [rbp-20h] BYREF
  HANDLE TargetHandle[3]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+98h] [rbp+38h]
  HANDLE v35; // [rsp+A0h] [rbp+40h] BYREF
  _QWORD *v36; // [rsp+A8h] [rbp+48h]
  HANDLE *v37; // [rsp+B0h] [rbp+50h]
  unsigned int *v38; // [rsp+B8h] [rbp+58h]

  v38 = a4;
  v37 = a3;
  v36 = a2;
  TargetHandle[0] = 0;
  v32 = 0;
  v35 = 0;
  *a1 = 0;
  *a2 = 0;
  *a4 = 0;
  CurrentProcess = GetCurrentProcess();
  v9 = hTargetProcessHandle;
  if ( DuplicateHandle(CurrentProcess, hSourceHandle, hTargetProcessHandle, TargetHandle, 2u, 1, 0) )
  {
    v12 = GetCurrentProcess();
    if ( !DuplicateHandle(v12, v9, v9, &v32, 0x1FFFFFu, 1, 0) )
    {
      LastError = GetLastError();
      v14 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v14 = LastError < 0;
      }
      if ( !v14 )
        LastError = -2147467259;
      LODWORD(dwDesiredAccessa) = LastError;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0xAF,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\exe\\secure\\protectedbroker.cpp",
        "PrepareCrashDataPayload",
        dwDesiredAccessa,
        (int)"DuplicateHandle/hFaultingProcess failed",
        dwOptionsa);
      v32 = 0;
    }
    if ( a7 )
    {
      v15 = GetCurrentProcess();
      if ( !DuplicateHandle(v15, a7, v9, &v35, 0x100002u, 1, 0) )
      {
        v16 = GetLastError();
        v17 = v16 < 0;
        if ( v16 > 0 )
        {
          v16 = (unsigned __int16)v16 | 0x80070000;
          v17 = v16 < 0;
        }
        if ( !v17 )
          v16 = -2147467259;
        LODWORD(dwDesiredAccessb) = v16;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0xC3,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\exe\\secure\\protectedbroker.cpp",
          "PrepareCrashDataPayload",
          dwDesiredAccessb,
          (int)"DuplicateHandle/hCompletionEvent failed",
          dwOptionsa);
        v35 = 0;
      }
    }
    v18 = MapViewOfFile(hSourceHandle, 2u, 0, 0, 0);
    if ( v18 )
    {
      LODWORD(dwDesiredAccessc) = 0x80000000;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0xDA,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\exe\\secure\\protectedbroker.cpp",
        "PrepareCrashDataPayload",
        dwDesiredAccessc,
        (int)"hRemoteSharedMem: 0x%p",
        (const char *)TargetHandle[0]);
      LODWORD(dwDesiredAccessd) = 0x80000000;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0xDB,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\exe\\secure\\protectedbroker.cpp",
        "PrepareCrashDataPayload",
        dwDesiredAccessd,
        (int)"hRemoteCompletionEvent: 0x%p",
        (const char *)v35);
      LODWORD(dwDesiredAccesse) = 0x80000000;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0xDC,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\exe\\secure\\protectedbroker.cpp",
        "PrepareCrashDataPayload",
        dwDesiredAccesse,
        (int)"hRemoteFaultingProcess: 0x%p",
        (const char *)v32);
      v18[23] = v32;
      v18[25] = 0;
      v18[26] = v35;
      TargetHandle[1] = 0;
      UnmapViewOfFile(v18);
      v20 = TargetHandle[0];
      v21 = v37;
      *v37 = TargetHandle[0];
      v22 = 1;
      if ( v35 )
      {
        v21[1] = v35;
        v22 = 2;
      }
      if ( v32 )
        v21[v22++] = v32;
      if ( v22 > 5 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v20 = TargetHandle[0];
      }
      *v36 = v20;
      *v38 = v22;
      return 0;
    }
    else
    {
      *a1 = 212;
      v19 = GetLastError();
      v11 = v19;
      if ( v19 > 0 )
        v11 = (unsigned __int16)v19 | 0x80070000;
      if ( v11 >= 0 )
        v11 = -2147467259;
      LODWORD(dwDesiredAccessc) = v11;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0xD6,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\exe\\secure\\protectedbroker.cpp",
        "PrepareCrashDataPayload",
        dwDesiredAccessc,
        (int)"MapViewOfFile/hLocalSharedMemTemplate failed",
        dwOptionsa);
    }
  }
  else
  {
    *a1 = 155;
    v10 = GetLastError();
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    if ( v11 >= 0 )
      v11 = -2147467259;
    LODWORD(dwDesiredAccess) = v11;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\exe\\secure\\protectedbroker.cpp",
      "PrepareCrashDataPayload",
      dwDesiredAccess,
      (int)"DuplicateHandle/hSharedMemTemplate failed",
      dwOptions);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140005210  mov     [rsp-38h+arg_18], r9
0x140005215  mov     [rsp-38h+arg_10], r8
0x14000521a  mov     [rsp-38h+arg_8], rdx
0x14000521f  push    rbp
0x140005220  push    rbx
0x140005221  push    rsi
0x140005222  push    rdi
0x140005223  push    r12
0x140005225  push    r14
0x140005227  push    r15
0x140005229  mov     rbp, rsp
0x14000522c  sub     rsp, 60h
0x140005230  mov     r12, rcx
0x140005233  mov     [rbp+TargetHandle], 0
0x14000523b  mov     [rbp+var_20], 0
0x140005243  mov     [rbp+arg_0], 0
0x14000524b  mov     dword ptr [rcx], 0
0x140005251  mov     qword ptr [rdx], 0
0x140005258  mov     dword ptr [r9], 0
0x14000525f  call    cs:__imp_GetCurrentProcess
0x140005265  mov     rcx, rax; hSourceProcessHandle
0x140005268  mov     [rsp+60h+dwOptions], 0; char *
0x140005270  mov     edi, 1
0x140005275  mov     [rsp+60h+bInheritHandle], edi; bInheritHandle
0x140005279  mov     [rsp+60h+dwDesiredAccess], 2; dwDesiredAccess
0x140005281  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x140005285  mov     rbx, [rbp+hTargetProcessHandle]
0x140005289  mov     r8, rbx; hTargetProcessHandle
0x14000528c  mov     rdx, [rbp+hSourceHandle]; hSourceHandle
0x140005290  call    cs:__imp_DuplicateHandle
0x140005296  test    eax, eax
0x140005298  jnz     short loc_1400052F4
0x14000529a  mov     dword ptr [r12], 9Bh
0x1400052a2  call    cs:__imp_GetLastError
0x1400052a8  mov     ebx, eax
0x1400052aa  test    eax, eax
0x1400052ac  jle     short loc_1400052B7
0x1400052ae  movzx   ebx, ax
0x1400052b1  or      ebx, 80070000h
0x1400052b7  mov     r15d, 80004005h
0x1400052bd  test    ebx, ebx
0x1400052bf  cmovns  ebx, r15d
0x1400052c3  mov     rcx, [rbp+38h]; this
0x1400052c7  lea     rax, aDuplicatehandl_1; "DuplicateHandle/hSharedMemTemplate fail"...
0x1400052ce  mov     qword ptr [rsp+60h+bInheritHandle], rax; int
0x1400052d3  mov     [rsp+60h+dwDesiredAccess], ebx; wil::details *
0x1400052d7  lea     r9, aPreparecrashda; "PrepareCrashDataPayload"
0x1400052de  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x1400052e5  mov     edx, 9Dh; void *
0x1400052ea  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400052ef  jmp     loc_140005578
0x1400052f4  call    cs:__imp_GetCurrentProcess
0x1400052fa  mov     rcx, rax; hSourceProcessHandle
0x1400052fd  mov     [rsp+60h+dwOptions], 0; char *
0x140005305  mov     [rsp+60h+bInheritHandle], edi; bInheritHandle
0x140005309  mov     [rsp+60h+dwDesiredAccess], 1FFFFFh; dwDesiredAccess
0x140005311  lea     r9, [rbp+var_20]; lpTargetHandle
0x140005315  mov     r8, rbx; hTargetProcessHandle
0x140005318  mov     rdx, rbx; hSourceHandle
0x14000531b  call    cs:__imp_DuplicateHandle
0x140005321  mov     edi, 80070000h
0x140005326  mov     r15d, 80004005h
0x14000532c  lea     rsi, aPreparecrashda; "PrepareCrashDataPayload"
0x140005333  lea     r14, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14000533a  test    eax, eax
0x14000533c  jnz     short loc_14000537F
0x14000533e  call    cs:__imp_GetLastError
0x140005344  test    eax, eax
0x140005346  jle     short loc_14000534F
0x140005348  movzx   eax, ax
0x14000534b  or      eax, edi
0x14000534d  test    eax, eax
0x14000534f  cmovns  eax, r15d
0x140005353  mov     rcx, [rbp+38h]; this
0x140005357  lea     rdx, aDuplicatehandl_2; "DuplicateHandle/hFaultingProcess failed"
0x14000535e  mov     qword ptr [rsp+60h+bInheritHandle], rdx; int
0x140005363  mov     [rsp+60h+dwDesiredAccess], eax; wil::details *
0x140005367  mov     r9, rsi; char *
0x14000536a  mov     r8, r14; unsigned int
0x14000536d  mov     edx, 0AFh; void *
0x140005372  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140005377  mov     [rbp+var_20], 0
0x14000537f  cmp     [rbp+arg_30], 0
0x140005384  jz      short loc_1400053FD
0x140005386  call    cs:__imp_GetCurrentProcess
0x14000538c  mov     rcx, rax; hSourceProcessHandle
0x14000538f  mov     [rsp+60h+dwOptions], 0; char *
0x140005397  mov     [rsp+60h+bInheritHandle], 1; bInheritHandle
0x14000539f  mov     [rsp+60h+dwDesiredAccess], 100002h; dwDesiredAccess
0x1400053a7  lea     r9, [rbp+arg_0]; lpTargetHandle
0x1400053ab  mov     r8, rbx; hTargetProcessHandle
0x1400053ae  mov     rdx, [rbp+arg_30]; hSourceHandle
0x1400053b2  call    cs:__imp_DuplicateHandle
0x1400053b8  test    eax, eax
0x1400053ba  jnz     short loc_1400053FD
0x1400053bc  call    cs:__imp_GetLastError
0x1400053c2  test    eax, eax
0x1400053c4  jle     short loc_1400053CD
0x1400053c6  movzx   eax, ax
0x1400053c9  or      eax, edi
0x1400053cb  test    eax, eax
0x1400053cd  cmovns  eax, r15d
0x1400053d1  mov     rcx, [rbp+38h]; this
0x1400053d5  lea     rdx, aDuplicatehandl_7; "DuplicateHandle/hCompletionEvent failed"
0x1400053dc  mov     qword ptr [rsp+60h+bInheritHandle], rdx; int
0x1400053e1  mov     [rsp+60h+dwDesiredAccess], eax; wil::details *
0x1400053e5  mov     r9, rsi; char *
0x1400053e8  mov     r8, r14; unsigned int
0x1400053eb  mov     edx, 0C3h; void *
0x1400053f0  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400053f5  mov     [rbp+arg_0], 0
0x1400053fd  mov     qword ptr [rsp+60h+dwDesiredAccess], 0; dwNumberOfBytesToMap
0x140005406  xor     r9d, r9d; dwFileOffsetLow
0x140005409  xor     r8d, r8d; dwFileOffsetHigh
0x14000540c  lea     edx, [r9+2]; dwDesiredAccess
0x140005410  mov     rcx, [rbp+hSourceHandle]; hFileMappingObject
0x140005414  call    cs:__imp_MapViewOfFile
0x14000541a  mov     rbx, rax
0x14000541d  test    rax, rax
0x140005420  jnz     short loc_14000546A
0x140005422  mov     dword ptr [r12], 0D4h
0x14000542a  call    cs:__imp_GetLastError
0x140005430  mov     ebx, eax
0x140005432  test    eax, eax
0x140005434  jle     short loc_14000543B
0x140005436  movzx   ebx, ax
0x140005439  or      ebx, edi
0x14000543b  test    ebx, ebx
0x14000543d  cmovns  ebx, r15d
0x140005441  mov     rcx, [rbp+38h]; this
0x140005445  lea     rax, aMapviewoffileH; "MapViewOfFile/hLocalSharedMemTemplate f"...
0x14000544c  mov     qword ptr [rsp+60h+bInheritHandle], rax; int
0x140005451  mov     [rsp+60h+dwDesiredAccess], ebx; wil::details *
0x140005455  mov     r9, rsi; char *
0x140005458  mov     r8, r14; unsigned int
0x14000545b  mov     edx, 0D6h; void *
0x140005460  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140005465  jmp     loc_140005578
0x14000546a  mov     rcx, [rbp+38h]; this
0x14000546e  mov     rax, [rbp+TargetHandle]
0x140005472  mov     qword ptr [rsp+60h+dwOptions], rax; char *
0x140005477  lea     rax, aHremotesharedm; "hRemoteSharedMem: 0x%p"
0x14000547e  mov     qword ptr [rsp+60h+bInheritHandle], rax; int
0x140005483  mov     edi, 80000000h
0x140005488  mov     [rsp+60h+dwDesiredAccess], edi; wil::details *
0x14000548c  mov     r9, rsi; char *
0x14000548f  mov     r8, r14; unsigned int
0x140005492  mov     edx, 0DAh; void *
0x140005497  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14000549c  mov     rcx, [rbp+38h]; this
0x1400054a0  mov     rax, [rbp+arg_0]
0x1400054a4  mov     qword ptr [rsp+60h+dwOptions], rax; char *
0x1400054a9  lea     rax, aHremotecomplet; "hRemoteCompletionEvent: 0x%p"
0x1400054b0  mov     qword ptr [rsp+60h+bInheritHandle], rax; int
0x1400054b5  mov     [rsp+60h+dwDesiredAccess], edi; wil::details *
0x1400054b9  mov     r9, rsi; char *
0x1400054bc  mov     r8, r14; unsigned int
0x1400054bf  mov     edx, 0DBh; void *
0x1400054c4  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400054c9  mov     rcx, [rbp+38h]; this
0x1400054cd  mov     rax, [rbp+var_20]
0x1400054d1  mov     qword ptr [rsp+60h+dwOptions], rax; char *
0x1400054d6  lea     rax, aHremotefaultin; "hRemoteFaultingProcess: 0x%p"
0x1400054dd  mov     qword ptr [rsp+60h+bInheritHandle], rax; int
0x1400054e2  mov     [rsp+60h+dwDesiredAccess], edi; wil::details *
0x1400054e6  mov     r9, rsi; char *
0x1400054e9  mov     r8, r14; unsigned int
0x1400054ec  mov     edx, 0DCh; void *
0x1400054f1  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400054f6  mov     rax, [rbp+var_20]
0x1400054fa  mov     [rbx+0B8h], rax
0x140005501  mov     qword ptr [rbx+0C8h], 0
0x14000550c  mov     rax, [rbp+arg_0]
0x140005510  mov     [rbx+0D0h], rax
0x140005517  mov     [rbp+var_10], 0
0x14000551f  mov     rcx, rbx; lpBaseAddress
0x140005522  call    cs:__imp_UnmapViewOfFile
0x140005528  mov     rdx, [rbp+TargetHandle]
0x14000552c  mov     r8, [rbp+arg_10]
0x140005530  mov     [r8], rdx
0x140005533  mov     ebx, 1
0x140005538  mov     rax, [rbp+arg_0]
0x14000553c  test    rax, rax
0x14000553f  jz      short loc_14000554A
0x140005541  mov     [r8+8], rax
0x140005545  mov     ebx, 2
0x14000554a  mov     rcx, [rbp+var_20]
0x14000554e  test    rcx, rcx
0x140005551  jz      short loc_14000555B
0x140005553  mov     eax, ebx
0x140005555  mov     [r8+rax*8], rcx
0x140005559  inc     ebx
0x14000555b  cmp     ebx, 5
0x14000555e  jbe     short loc_140005569
0x140005560  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140005565  mov     rdx, [rbp+TargetHandle]
0x140005569  mov     rax, [rbp+arg_8]
0x14000556d  mov     [rax], rdx
0x140005570  mov     rax, [rbp+arg_18]
0x140005574  mov     [rax], ebx
0x140005576  xor     ebx, ebx
0x140005578  mov     eax, ebx
0x14000557a  add     rsp, 60h
0x14000557e  pop     r15
0x140005580  pop     r14
0x140005582  pop     r12
0x140005584  pop     rdi
0x140005585  pop     rsi
0x140005586  pop     rbx
0x140005587  pop     rbp
0x140005588  retn
```
