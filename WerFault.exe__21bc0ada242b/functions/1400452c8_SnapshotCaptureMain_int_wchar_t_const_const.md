# SnapshotCaptureMain(int,wchar_t const * * const)

- ea: `0x1400452c8`
- end: `0x140045582`
- name: `?SnapshotCaptureMain@@YAHHQEAPEB_W@Z`
- size: `698`
- prototype: `__int64 __fastcall(int, const wchar_t **const)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000d9f0`

## callees

- `0x140008970`
- `0x14000bcf8`
- `0x140044abc`
- `0x140044f94`
- `0x1400452c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004534f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400453a7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400453de`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004534f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400453a7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400453de`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1400453b6`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1400453ed`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1400453b6`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1400453ed`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x14004535e`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x14004535e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004554e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140045562`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004554e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140045562`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140045426`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140045450`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14004548a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400454b3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140045426`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140045450`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14004548a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400454b3`

## string_xrefs

- `0x1400452fc`: `Invalid number of command line params. Params expected %d, passed: %d`
- `0x1400454ef`: `Open process failed for pid: %d`

## pseudocode

```c
__int64 __fastcall SnapshotCaptureMain(int a1, const wchar_t **const a2)
{
  char *v3; // r13
  char *v4; // rdi
  DWORD v6; // ebx
  DWORD v7; // r14d
  void *v8; // r12
  unsigned int i; // r15d
  const char *v10; // rax
  __int64 v11; // rdx
  unsigned int v12; // esi
  char *v13; // rax
  __int64 v14; // rdx
  char *v15; // [rsp+28h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v3 = 0;
  v4 = 0;
  if ( a1 == 8 )
  {
    v6 = 0;
    v7 = 0;
    v8 = 0;
    UtilCheckDebugWait(L"WaitOnSnapshot");
    for ( i = 1; (int)i < 7; ++i )
    {
      if ( (unsigned int)_o__wcsicmp(a2[i], L"-s") )
      {
        if ( (unsigned int)_o__wcsicmp(a2[i], L"-p") )
        {
          if ( !(unsigned int)_o__wcsicmp(a2[i], L"-ip") )
          {
            v7 = _o__wtoi(a2[i + 1]);
            if ( !v7 )
            {
              v10 = "Invalid initiating process id was passed";
              v11 = 420;
              goto LABEL_31;
            }
          }
        }
        else
        {
          v6 = _o__wtoi(a2[i + 1]);
          if ( !v6 )
          {
            v10 = "Invalid process id was passed";
            v11 = 406;
            goto LABEL_31;
          }
        }
      }
      else
      {
        v8 = (void *)_wtoi64(a2[i + 1]);
        if ( !v8 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x188,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\snapshot.cpp",
            (const char *)0x80070057LL,
            (int)"No shared mem handle passed",
            v15);
          return 2147942487LL;
        }
      }
    }
    if ( !v8 || !v6 )
    {
      v10 = "No shared mem handle or process id was passed";
      v11 = 429;
LABEL_31:
      v12 = -2147024809;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\snapshot.cpp",
        (const char *)0x80070057LL,
        (int)v10,
        v15);
      goto LABEL_32;
    }
    v12 = 0;
    v3 = (char *)OpenProcess(0x1FFFFFu, 0, v6);
    if ( v3 == (char *)-1LL || v3 + 1 == (char *)1 )
    {
      v14 = 439;
    }
    else
    {
      if ( v7 )
      {
        v4 = (char *)OpenProcess(0x1FFFFFu, 0, v7);
        if ( v4 == (char *)-1LL || v4 + 1 == (char *)1 )
        {
          v13 = (char *)OpenProcess(0x400u, 0, v7);
          v4 = v13;
        }
        else
        {
          v13 = v4;
        }
        if ( v13 == (char *)-1LL || v13 + 1 == (char *)1 )
        {
          LODWORD(v15) = v7;
          v14 = 458;
LABEL_29:
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)v14,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\snapshot.cpp",
            (const char *)0x80000000LL,
            (int)"Open process failed for pid: %d",
            v15);
LABEL_32:
          if ( (unsigned __int64)(v4 + 1) > 1 )
            CloseHandle(v4);
          if ( (unsigned __int64)(v3 + 1) > 1 )
            CloseHandle(v3);
          return v12;
        }
LABEL_25:
        v12 = CaptureSnapshot(v8);
        goto LABEL_32;
      }
      v4 = (char *)OpenProcess(0x1FFFFFu, 0, v6);
      if ( v4 != (char *)-1LL && v4 + 1 != (char *)1 )
        goto LABEL_25;
      v14 = 474;
    }
    LODWORD(v15) = v6;
    goto LABEL_29;
  }
  LODWORD(v15) = 8;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x172,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\snapshot.cpp",
    (const char *)0x80070057LL,
    (int)"Invalid number of command line params. Params expected %d, passed: %d",
    v15,
    a1);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1400452c8  mov     [rsp+arg_0], rbx
0x1400452cd  push    rbp
0x1400452ce  push    rsi
0x1400452cf  push    rdi
0x1400452d0  push    r12
0x1400452d2  push    r13
0x1400452d4  push    r14
0x1400452d6  push    r15
0x1400452d8  sub     rsp, 40h
0x1400452dc  mov     rsi, rdx
0x1400452df  mov     eax, ecx
0x1400452e1  xor     r13d, r13d
0x1400452e4  xor     edi, edi
0x1400452e6  cmp     ecx, 8
0x1400452e9  jz      short loc_140045329
0x1400452eb  mov     rcx, [rsp+78h]; this
0x1400452f0  mov     [rsp+78h+var_48], eax
0x1400452f4  mov     dword ptr [rsp+78h+var_50], 8; char *
0x1400452fc  lea     rax, aInvalidNumberO_0; "Invalid number of command line params. "...
0x140045303  mov     qword ptr [rsp+78h+var_58], rax; int
0x140045308  mov     ebx, 80070057h
0x14004530d  mov     r9d, ebx; char *
0x140045310  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140045317  mov     edx, 172h; void *
0x14004531c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x140045321  nop
0x140045322  mov     eax, ebx
0x140045324  jmp     loc_14004556A
0x140045329  xor     ebx, ebx
0x14004532b  xor     r14d, r14d
0x14004532e  xor     r12d, r12d
0x140045331  lea     rcx, aWaitonsnapshot; "WaitOnSnapshot"
0x140045338  call    ?UtilCheckDebugWait@@YAXPEB_W@Z; UtilCheckDebugWait(wchar_t const *)
0x14004533d  lea     r15d, [rbx+1]
0x140045341  mov     ebp, r15d
0x140045344  lea     rdx, aS_2; "-s"
0x14004534b  mov     rcx, [rsi+rbp*8]
0x14004534f  call    cs:__imp__o__wcsicmp
0x140045355  test    eax, eax
0x140045357  jnz     short loc_14004539C
0x140045359  mov     rcx, [rsi+rbp*8+8]; String
0x14004535e  call    cs:__imp__wtoi64
0x140045364  mov     r12, rax
0x140045367  test    rax, rax
0x14004536a  jnz     loc_1400453FA
0x140045370  mov     rcx, [rsp+78h]; this
0x140045375  lea     rax, aNoSharedMemHan_0; "No shared mem handle passed"
0x14004537c  mov     qword ptr [rsp+78h+var_58], rax; int
0x140045381  mov     ebx, 80070057h
0x140045386  mov     r9d, ebx; char *
0x140045389  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140045390  mov     edx, 188h; void *
0x140045395  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14004539a  jmp     short loc_140045322
0x14004539c  lea     rdx, aP; "-p"
0x1400453a3  mov     rcx, [rsi+rbp*8]
0x1400453a7  call    cs:__imp__o__wcsicmp
0x1400453ad  test    eax, eax
0x1400453af  jnz     short loc_1400453D3
0x1400453b1  mov     rcx, [rsi+rbp*8+8]
0x1400453b6  call    cs:__imp__o__wtoi
0x1400453bc  mov     ebx, eax
0x1400453be  test    eax, eax
0x1400453c0  jnz     short loc_1400453FA
0x1400453c2  lea     rax, aInvalidProcess; "Invalid process id was passed"
0x1400453c9  mov     edx, 196h
0x1400453ce  jmp     loc_140045520
0x1400453d3  lea     rdx, aIp; "-ip"
0x1400453da  mov     rcx, [rsi+rbp*8]
0x1400453de  call    cs:__imp__o__wcsicmp
0x1400453e4  test    eax, eax
0x1400453e6  jnz     short loc_1400453FA
0x1400453e8  mov     rcx, [rsi+rbp*8+8]
0x1400453ed  call    cs:__imp__o__wtoi
0x1400453f3  mov     r14d, eax
0x1400453f6  test    eax, eax
0x1400453f8  jz      short loc_14004546F
0x1400453fa  inc     r15d
0x1400453fd  cmp     r15d, 7
0x140045401  jl      loc_140045341
0x140045407  test    r12, r12
0x14004540a  jz      loc_140045514
0x140045410  test    ebx, ebx
0x140045412  jz      loc_140045514
0x140045418  xor     esi, esi
0x14004541a  mov     r8d, ebx; dwProcessId
0x14004541d  xor     edx, edx; bInheritHandle
0x14004541f  mov     ebp, 1FFFFFh
0x140045424  mov     ecx, ebp; dwDesiredAccess
0x140045426  call    cs:__imp_OpenProcess
0x14004542c  mov     r13, rax
0x14004542f  mov     [rsp+78h+arg_18], rax
0x140045437  inc     rax
0x14004543a  cmp     rax, 1
0x14004543e  jbe     loc_1400454E6
0x140045444  xor     edx, edx; bInheritHandle
0x140045446  mov     ecx, ebp; dwDesiredAccess
0x140045448  test    r14d, r14d
0x14004544b  jz      short loc_1400454B0
0x14004544d  mov     r8d, r14d; dwProcessId
0x140045450  call    cs:__imp_OpenProcess
0x140045456  mov     rdi, rax
0x140045459  mov     [rsp+78h+arg_10], rax
0x140045461  inc     rax
0x140045464  cmp     rax, 1
0x140045468  jbe     short loc_140045480
0x14004546a  mov     rax, rdi
0x14004546d  jmp     short loc_14004549B
0x14004546f  lea     rax, aInvalidInitiat; "Invalid initiating process id was passe"...
0x140045476  mov     edx, 1A4h
0x14004547b  jmp     loc_140045520
0x140045480  mov     r8d, r14d; dwProcessId
0x140045483  xor     edx, edx; bInheritHandle
0x140045485  mov     ecx, 400h; dwDesiredAccess
0x14004548a  call    cs:__imp_OpenProcess
0x140045490  mov     rdi, rax
0x140045493  mov     [rsp+78h+arg_10], rax
0x14004549b  inc     rax
0x14004549e  cmp     rax, 1
0x1400454a2  ja      short loc_1400454CD
0x1400454a4  mov     dword ptr [rsp+78h+var_50], r14d
0x1400454a9  mov     edx, 1CAh
0x1400454ae  jmp     short loc_1400454EF
0x1400454b0  mov     r8d, ebx; dwProcessId
0x1400454b3  call    cs:__imp_OpenProcess
0x1400454b9  mov     rdi, rax
0x1400454bc  mov     [rsp+78h+arg_10], rax
0x1400454c4  inc     rax
0x1400454c7  cmp     rax, 1
0x1400454cb  jbe     short loc_1400454DF
0x1400454cd  mov     r8d, ebx
0x1400454d0  mov     rdx, rdi
0x1400454d3  mov     rcx, r12; hFileMappingObject
0x1400454d6  call    CaptureSnapshot
0x1400454db  mov     esi, eax
0x1400454dd  jmp     short loc_140045541
0x1400454df  mov     edx, 1DAh
0x1400454e4  jmp     short loc_1400454EB
0x1400454e6  mov     edx, 1B7h; void *
0x1400454eb  mov     dword ptr [rsp+78h+var_50], ebx; char *
0x1400454ef  lea     rax, aOpenProcessFai_0; "Open process failed for pid: %d"
0x1400454f6  mov     rcx, [rsp+78h]; this
0x1400454fb  mov     qword ptr [rsp+78h+var_58], rax; int
0x140045500  mov     r9d, 80000000h; char *
0x140045506  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x14004550d  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x140045512  jmp     short loc_140045541
0x140045514  lea     rax, aNoSharedMemHan; "No shared mem handle or process id was "...
0x14004551b  mov     edx, 1ADh; void *
0x140045520  mov     ebx, 80070057h
0x140045525  mov     esi, ebx
0x140045527  mov     qword ptr [rsp+78h+var_58], rax; int
0x14004552c  mov     r9d, ebx; char *
0x14004552f  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140045536  mov     rcx, [rsp+78h]; this
0x14004553b  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x140045540  nop
0x140045541  lea     rax, [rdi+1]
0x140045545  cmp     rax, 1
0x140045549  jbe     short loc_140045555
0x14004554b  mov     rcx, rdi; hObject
0x14004554e  call    cs:__imp_CloseHandle
0x140045554  nop
0x140045555  lea     rax, [r13+1]
0x140045559  cmp     rax, 1
0x14004555d  jbe     short loc_140045568
0x14004555f  mov     rcx, r13; hObject
0x140045562  call    cs:__imp_CloseHandle
0x140045568  mov     eax, esi
0x14004556a  mov     rbx, [rsp+78h+arg_0]
0x140045572  add     rsp, 40h
0x140045576  pop     r15
0x140045578  pop     r14
0x14004557a  pop     r13
0x14004557c  pop     r12
0x14004557e  pop     rdi
0x14004557f  pop     rsi
0x140045580  pop     rbp
0x140045581  retn
```
