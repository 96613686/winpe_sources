# SnapshotCaptureMain(int,wchar_t const * * const)

- ea: `0x140048410`
- end: `0x14004871a`
- name: `?SnapshotCaptureMain@@YAHHQEAPEB_W@Z`
- size: `778`
- prototype: `__int64 __fastcall(int, const wchar_t **const)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000ddb8`

## callees

- `0x1400088e8`
- `0x14000bee0`
- `0x140047b58`
- `0x1400480b0`
- `0x140048410`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140048497`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400484fe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140048541`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140048497`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400484fe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140048541`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140048513`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140048556`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140048513`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140048556`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1400484ac`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1400484ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400486d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400486f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400486d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400486f3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140048599`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400485c9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140048609`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140048638`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140048599`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400485c9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140048609`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140048638`

## string_xrefs

- `0x140048444`: `Invalid number of command line params. Params expected %d, passed: %d`
- `0x14004867a`: `Open process failed for pid: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SnapshotCaptureMain(int a1, const wchar_t **const a2)
{
  char *v3; // r13
  char *v4; // rdi
  DWORD v6; // ebx
  DWORD v7; // r14d
  void *v8; // r12
  __int64 v9; // r8
  unsigned int i; // r15d
  __int64 v11; // r8
  __int64 v12; // r8
  const char *v13; // rax
  __int64 v14; // rdx
  unsigned int v15; // esi
  char *v16; // rax
  __int64 v17; // rdx
  char *v18; // [rsp+28h] [rbp-50h]
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
      if ( (unsigned int)_o__wcsicmp(a2[i], L"-s", v9) )
      {
        if ( (unsigned int)_o__wcsicmp(a2[i], L"-p", v11) )
        {
          if ( !(unsigned int)_o__wcsicmp(a2[i], L"-ip", v12) )
          {
            v7 = _o__wtoi(a2[i + 1]);
            if ( !v7 )
            {
              v13 = "Invalid initiating process id was passed";
              v14 = 420;
              goto LABEL_31;
            }
          }
        }
        else
        {
          v6 = _o__wtoi(a2[i + 1]);
          if ( !v6 )
          {
            v13 = "Invalid process id was passed";
            v14 = 406;
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
            v18);
          return 2147942487LL;
        }
      }
    }
    if ( !v8 || !v6 )
    {
      v13 = "No shared mem handle or process id was passed";
      v14 = 429;
LABEL_31:
      v15 = -2147024809;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\snapshot.cpp",
        (const char *)0x80070057LL,
        (int)v13,
        v18);
      goto LABEL_32;
    }
    v15 = 0;
    v3 = (char *)OpenProcess(0x1FFFFFu, 0, v6);
    if ( v3 == (char *)-1LL || v3 + 1 == (char *)1 )
    {
      v17 = 439;
    }
    else
    {
      if ( v7 )
      {
        v4 = (char *)OpenProcess(0x1FFFFFu, 0, v7);
        if ( v4 == (char *)-1LL || v4 + 1 == (char *)1 )
        {
          v16 = (char *)OpenProcess(0x400u, 0, v7);
          v4 = v16;
        }
        else
        {
          v16 = v4;
        }
        if ( v16 == (char *)-1LL || v16 + 1 == (char *)1 )
        {
          LODWORD(v18) = v7;
          v17 = 458;
LABEL_29:
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)v17,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\snapshot.cpp",
            (const char *)0x80000000LL,
            (int)"Open process failed for pid: %d",
            v18);
LABEL_32:
          if ( (unsigned __int64)(v4 + 1) > 1 )
            CloseHandle(v4);
          if ( (unsigned __int64)(v3 + 1) > 1 )
            CloseHandle(v3);
          return v15;
        }
LABEL_25:
        v15 = CaptureSnapshot(v8);
        goto LABEL_32;
      }
      v4 = (char *)OpenProcess(0x1FFFFFu, 0, v6);
      if ( v4 != (char *)-1LL && v4 + 1 != (char *)1 )
        goto LABEL_25;
      v17 = 474;
    }
    LODWORD(v18) = v6;
    goto LABEL_29;
  }
  LODWORD(v18) = 8;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x172,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\snapshot.cpp",
    (const char *)0x80070057LL,
    (int)"Invalid number of command line params. Params expected %d, passed: %d",
    v18,
    a1);
  return 2147942487LL;
}

```

## disassembly

```asm
0x140048410  mov     [rsp+arg_0], rbx
0x140048415  push    rbp
0x140048416  push    rsi
0x140048417  push    rdi
0x140048418  push    r12
0x14004841a  push    r13
0x14004841c  push    r14
0x14004841e  push    r15
0x140048420  sub     rsp, 40h
0x140048424  mov     rsi, rdx
0x140048427  mov     eax, ecx
0x140048429  xor     r13d, r13d
0x14004842c  xor     edi, edi
0x14004842e  cmp     ecx, 8
0x140048431  jz      short loc_140048471
0x140048433  mov     rcx, [rsp+78h]; this
0x140048438  mov     [rsp+78h+var_48], eax
0x14004843c  mov     dword ptr [rsp+78h+var_50], 8; char *
0x140048444  lea     rax, aInvalidNumberO_0; "Invalid number of command line params. "...
0x14004844b  mov     qword ptr [rsp+78h+var_58], rax; int
0x140048450  mov     ebx, 80070057h
0x140048455  mov     r9d, ebx; char *
0x140048458  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x14004845f  mov     edx, 172h; void *
0x140048464  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x140048469  nop
0x14004846a  mov     eax, ebx
0x14004846c  jmp     loc_140048701
0x140048471  xor     ebx, ebx
0x140048473  xor     r14d, r14d
0x140048476  xor     r12d, r12d
0x140048479  lea     rcx, aWaitonsnapshot; "WaitOnSnapshot"
0x140048480  call    ?UtilCheckDebugWait@@YAXPEB_W@Z; UtilCheckDebugWait(wchar_t const *)
0x140048485  lea     r15d, [rbx+1]
0x140048489  mov     ebp, r15d
0x14004848c  lea     rdx, aS_2; "-s"
0x140048493  mov     rcx, [rsi+rbp*8]
0x140048497  call    cs:__imp__o__wcsicmp
0x14004849e  nop     dword ptr [rax+rax+00h]
0x1400484a3  test    eax, eax
0x1400484a5  jnz     short loc_1400484F3
0x1400484a7  mov     rcx, [rsi+rbp*8+8]; String
0x1400484ac  call    cs:__imp__wtoi64
0x1400484b3  nop     dword ptr [rax+rax+00h]
0x1400484b8  mov     r12, rax
0x1400484bb  test    rax, rax
0x1400484be  jnz     loc_14004856D
0x1400484c4  mov     rcx, [rsp+78h]; this
0x1400484c9  lea     rax, aNoSharedMemHan_0; "No shared mem handle passed"
0x1400484d0  mov     qword ptr [rsp+78h+var_58], rax; int
0x1400484d5  mov     ebx, 80070057h
0x1400484da  mov     r9d, ebx; char *
0x1400484dd  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x1400484e4  mov     edx, 188h; void *
0x1400484e9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400484ee  jmp     loc_14004846A
0x1400484f3  lea     rdx, aP; "-p"
0x1400484fa  mov     rcx, [rsi+rbp*8]
0x1400484fe  call    cs:__imp__o__wcsicmp
0x140048505  nop     dword ptr [rax+rax+00h]
0x14004850a  test    eax, eax
0x14004850c  jnz     short loc_140048536
0x14004850e  mov     rcx, [rsi+rbp*8+8]
0x140048513  call    cs:__imp__o__wtoi
0x14004851a  nop     dword ptr [rax+rax+00h]
0x14004851f  mov     ebx, eax
0x140048521  test    eax, eax
0x140048523  jnz     short loc_14004856D
0x140048525  lea     rax, aInvalidProcess; "Invalid process id was passed"
0x14004852c  mov     edx, 196h
0x140048531  jmp     loc_1400486AB
0x140048536  lea     rdx, aIp; "-ip"
0x14004853d  mov     rcx, [rsi+rbp*8]
0x140048541  call    cs:__imp__o__wcsicmp
0x140048548  nop     dword ptr [rax+rax+00h]
0x14004854d  test    eax, eax
0x14004854f  jnz     short loc_14004856D
0x140048551  mov     rcx, [rsi+rbp*8+8]
0x140048556  call    cs:__imp__o__wtoi
0x14004855d  nop     dword ptr [rax+rax+00h]
0x140048562  mov     r14d, eax
0x140048565  test    eax, eax
0x140048567  jz      loc_1400485EE
0x14004856d  inc     r15d
0x140048570  cmp     r15d, 7
0x140048574  jl      loc_140048489
0x14004857a  test    r12, r12
0x14004857d  jz      loc_14004869F
0x140048583  test    ebx, ebx
0x140048585  jz      loc_14004869F
0x14004858b  xor     esi, esi
0x14004858d  mov     r8d, ebx; dwProcessId
0x140048590  xor     edx, edx; bInheritHandle
0x140048592  mov     ebp, 1FFFFFh
0x140048597  mov     ecx, ebp; dwDesiredAccess
0x140048599  call    cs:__imp_OpenProcess
0x1400485a0  nop     dword ptr [rax+rax+00h]
0x1400485a5  mov     r13, rax
0x1400485a8  mov     [rsp+78h+arg_18], rax
0x1400485b0  inc     rax
0x1400485b3  cmp     rax, 1
0x1400485b7  jbe     loc_140048671
0x1400485bd  xor     edx, edx; bInheritHandle
0x1400485bf  mov     ecx, ebp; dwDesiredAccess
0x1400485c1  test    r14d, r14d
0x1400485c4  jz      short loc_140048635
0x1400485c6  mov     r8d, r14d; dwProcessId
0x1400485c9  call    cs:__imp_OpenProcess
0x1400485d0  nop     dword ptr [rax+rax+00h]
0x1400485d5  mov     rdi, rax
0x1400485d8  mov     [rsp+78h+arg_10], rax
0x1400485e0  inc     rax
0x1400485e3  cmp     rax, 1
0x1400485e7  jbe     short loc_1400485FF
0x1400485e9  mov     rax, rdi
0x1400485ec  jmp     short loc_140048620
0x1400485ee  lea     rax, aInvalidInitiat; "Invalid initiating process id was passe"...
0x1400485f5  mov     edx, 1A4h
0x1400485fa  jmp     loc_1400486AB
0x1400485ff  mov     r8d, r14d; dwProcessId
0x140048602  xor     edx, edx; bInheritHandle
0x140048604  mov     ecx, 400h; dwDesiredAccess
0x140048609  call    cs:__imp_OpenProcess
0x140048610  nop     dword ptr [rax+rax+00h]
0x140048615  mov     rdi, rax
0x140048618  mov     [rsp+78h+arg_10], rax
0x140048620  inc     rax
0x140048623  cmp     rax, 1
0x140048627  ja      short loc_140048658
0x140048629  mov     dword ptr [rsp+78h+var_50], r14d
0x14004862e  mov     edx, 1CAh
0x140048633  jmp     short loc_14004867A
0x140048635  mov     r8d, ebx; dwProcessId
0x140048638  call    cs:__imp_OpenProcess
0x14004863f  nop     dword ptr [rax+rax+00h]
0x140048644  mov     rdi, rax
0x140048647  mov     [rsp+78h+arg_10], rax
0x14004864f  inc     rax
0x140048652  cmp     rax, 1
0x140048656  jbe     short loc_14004866A
0x140048658  mov     r8d, ebx
0x14004865b  mov     rdx, rdi
0x14004865e  mov     rcx, r12; hFileMappingObject
0x140048661  call    CaptureSnapshot
0x140048666  mov     esi, eax
0x140048668  jmp     short loc_1400486CC
0x14004866a  mov     edx, 1DAh
0x14004866f  jmp     short loc_140048676
0x140048671  mov     edx, 1B7h; void *
0x140048676  mov     dword ptr [rsp+78h+var_50], ebx; char *
0x14004867a  lea     rax, aOpenProcessFai_0; "Open process failed for pid: %d"
0x140048681  mov     rcx, [rsp+78h]; this
0x140048686  mov     qword ptr [rsp+78h+var_58], rax; int
0x14004868b  mov     r9d, 80000000h; char *
0x140048691  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x140048698  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x14004869d  jmp     short loc_1400486CC
0x14004869f  lea     rax, aNoSharedMemHan; "No shared mem handle or process id was "...
0x1400486a6  mov     edx, 1ADh; void *
0x1400486ab  mov     ebx, 80070057h
0x1400486b0  mov     esi, ebx
0x1400486b2  mov     qword ptr [rsp+78h+var_58], rax; int
0x1400486b7  mov     r9d, ebx; char *
0x1400486ba  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werfa"...
0x1400486c1  mov     rcx, [rsp+78h]; this
0x1400486c6  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400486cb  nop
0x1400486cc  lea     rax, [rdi+1]
0x1400486d0  cmp     rax, 1
0x1400486d4  jbe     short loc_1400486E6
0x1400486d6  mov     rcx, rdi; hObject
0x1400486d9  call    cs:__imp_CloseHandle
0x1400486e0  nop     dword ptr [rax+rax+00h]
0x1400486e5  nop
0x1400486e6  lea     rax, [r13+1]
0x1400486ea  cmp     rax, 1
0x1400486ee  jbe     short loc_1400486FF
0x1400486f0  mov     rcx, r13; hObject
0x1400486f3  call    cs:__imp_CloseHandle
0x1400486fa  nop     dword ptr [rax+rax+00h]
0x1400486ff  mov     eax, esi
0x140048701  mov     rbx, [rsp+78h+arg_0]
0x140048709  add     rsp, 40h
0x14004870d  pop     r15
0x14004870f  pop     r14
0x140048711  pop     r13
0x140048713  pop     r12
0x140048715  pop     rdi
0x140048716  pop     rsi
0x140048717  pop     rbp
0x140048718  retn
```
