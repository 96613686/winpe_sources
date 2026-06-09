# UserCrashMain(int,wchar_t const * * const)

- ea: `0x1400445fc`
- end: `0x14004492d`
- name: `?UserCrashMain@@YAHHQEAPEB_W@Z`
- size: `817`
- prototype: `__int64 __fastcall(char *, const wchar_t **const)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000bcd0`

## callees

- `0x140003b14`
- `0x140008970`
- `0x14000bcf8`
- `0x140030450`
- `0x1400445fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004467b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400446b3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400446e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004467b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400446b3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400446e8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1400446c2`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1400446f7`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1400446c2`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1400446f7`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x14004468a`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x14004468a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004484c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400448ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004484c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400448ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004489b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400448a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004489b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400448a4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140044730`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140044752`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14004476e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400447c5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140044730`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140044752`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14004476e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400447c5`
- `faultrep!WerpInitiateCrashReporting` at `0x140044816`
- `faultrep!WerpInitiateCrashReporting` at `0x140044816`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyComplete` at `0x14004482a`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyComplete` at `0x14004482a`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyStart` at `0x1400447e3`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyStart` at `0x1400447e3`

## string_xrefs

- `0x14004461a`: `Invalid number of command line params passed. Params passed: %d`
- `0x1400448c6`: `OpenProcess failed for faulting pid %d (0x%x)`
- `0x14004479b`: `OpenProcess failed for initiating pid %d (0x%x)`
- `0x140044865`: `OpenProcess failed for self, pid %d (0x%x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserCrashMain(char *a1, const wchar_t **const a2)
{
  int v3; // ebx
  __int64 v5; // r15
  DWORD v6; // ebp
  DWORD v7; // r14d
  unsigned int v8; // esi
  const char *v9; // rax
  __int64 v10; // rdx
  char *v11; // rdi
  char *v12; // rbx
  signed int v13; // eax
  unsigned int v14; // esi
  const char *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  signed int v18; // eax
  signed int LastError; // eax
  char *v20; // [rsp+28h] [rbp-50h]
  DWORD v21; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v3 = (int)a1;
  if ( (int)a1 < 6 )
  {
    LODWORD(v20) = (_DWORD)a1;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\userfault.cpp",
      (const char *)0x80070057LL,
      (int)"Invalid number of command line params passed. Params passed: %d",
      v20);
    return 2147942487LL;
  }
  v5 = 0;
  v6 = 0;
  v7 = 0;
  UtilCheckDebugWait(L"WaitOnStart");
  v8 = 1;
  if ( v3 - 1 <= 1 )
    goto LABEL_41;
  do
  {
    if ( (unsigned int)_o__wcsicmp(a2[v8], L"-s") )
    {
      if ( (unsigned int)_o__wcsicmp(a2[v8], L"-p") )
      {
        if ( !(unsigned int)_o__wcsicmp(a2[v8], L"-ip") )
        {
          v7 = _o__wtoi(a2[v8 + 1]);
          if ( !v7 )
          {
            v9 = "Invalid initiating process id was passed";
            v10 = 115;
            goto LABEL_42;
          }
        }
      }
      else
      {
        v6 = _o__wtoi(a2[v8 + 1]);
        if ( !v6 )
        {
          v9 = "Invalid process id was passed";
          v10 = 101;
          goto LABEL_42;
        }
      }
    }
    else
    {
      v5 = _wtoi64(a2[v8 + 1]);
      if ( !v5 )
      {
        v9 = "No shared mem handle passed";
        v10 = 87;
        goto LABEL_42;
      }
    }
    ++v8;
  }
  while ( (int)v8 < v3 - 1 );
  if ( !v5 || !v6 )
  {
LABEL_41:
    v9 = "No shared mem handle or process id was passed";
    v10 = 124;
LABEL_42:
    v14 = -2147024809;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\userfault.cpp",
      (const char *)0x80070057LL,
      (int)v9,
      v20);
    return v14;
  }
  v11 = (char *)OpenProcess(0x1FFFFFu, 0, v6);
  if ( v11 == (char *)-1LL || v11 + 1 == (char *)1 )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    LODWORD(v20) = v6;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\userfault.cpp",
      (const char *)v14,
      (int)"OpenProcess failed for faulting pid %d (0x%x)",
      v20,
      v6);
    return v14;
  }
  if ( !v7 )
  {
    v12 = (char *)OpenProcess(0x1FFFFFu, 0, v6);
    if ( v12 == (char *)-1LL || v12 + 1 == (char *)1 )
    {
      v18 = GetLastError();
      v14 = v18;
      if ( v18 > 0 )
        v14 = (unsigned __int16)v18 | 0x80070000;
      v21 = v6;
      v15 = "OpenProcess failed for self, pid %d (0x%x)";
      LODWORD(v20) = v6;
      v16 = 171;
      goto LABEL_34;
    }
LABEL_25:
    if ( (unsigned __int8)IsXerDumpNotifyStartPresent() )
      XerDumpNotifyStart(v11);
    v14 = WerpInitiateCrashReporting(v11, v12, v5, 0, 0, 0, 0, 0);
    if ( (unsigned __int8)IsXerDumpNotifyStartPresent() )
      XerDumpNotifyComplete(v11);
    if ( v14 == -2147024739 )
      UtilFireWerVerticalDisabledEvent(v17, L"Crash", 2);
    goto LABEL_35;
  }
  v12 = (char *)OpenProcess(0x1FFFFFu, 0, v7);
  if ( v12 == (char *)-1LL || v12 + 1 == (char *)1 )
    v12 = (char *)OpenProcess(0x400u, 0, v7);
  if ( (unsigned __int64)(v12 + 1) > 1 )
    goto LABEL_25;
  v13 = GetLastError();
  v14 = v13;
  if ( v13 > 0 )
    v14 = (unsigned __int16)v13 | 0x80070000;
  v21 = v7;
  v15 = "OpenProcess failed for initiating pid %d (0x%x)";
  LODWORD(v20) = v7;
  v16 = 155;
LABEL_34:
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)v16,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\userfault.cpp",
    (const char *)v14,
    (int)v15,
    v20,
    v21);
LABEL_35:
  if ( (unsigned __int64)(v12 + 1) > 1 )
    CloseHandle(v12);
  CloseHandle(v11);
  return v14;
}

```

## disassembly

```asm
0x1400445fc  push    rbx
0x1400445fe  push    rbp
0x1400445ff  push    rsi
0x140044600  push    rdi
0x140044601  push    r12
0x140044603  push    r14
0x140044605  push    r15
0x140044607  sub     rsp, 40h
0x14004460b  mov     rdi, rdx
0x14004460e  mov     ebx, ecx
0x140044610  cmp     ecx, 6
0x140044613  jge     short loc_14004464A
0x140044615  mov     rcx, [rsp+78h]; this
0x14004461a  lea     rax, aInvalidNumberO_1; "Invalid number of command line params p"...
0x140044621  mov     dword ptr [rsp+78h+var_50], ebx; char *
0x140044625  lea     r8, aOnecoreWindows_10; "onecore\\windows\\feedback\\core\\werfa"...
0x14004462c  mov     ebx, 80070057h
0x140044631  mov     qword ptr [rsp+78h+var_58], rax; int
0x140044636  mov     r9d, ebx; char *
0x140044639  mov     edx, 3Fh ; '?'; void *
0x14004463e  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x140044643  mov     eax, ebx
0x140044645  jmp     loc_14004491E
0x14004464a  lea     rcx, aWaitonstart; "WaitOnStart"
0x140044651  xor     r15d, r15d
0x140044654  xor     ebp, ebp
0x140044656  xor     r14d, r14d
0x140044659  call    ?UtilCheckDebugWait@@YAXPEB_W@Z; UtilCheckDebugWait(wchar_t const *)
0x14004465e  lea     esi, [rbp+1]
0x140044661  lea     r12d, [rbx-1]
0x140044665  cmp     r12d, esi
0x140044668  jle     loc_1400448F0
0x14004466e  mov     ebx, esi
0x140044670  lea     rdx, aS_2; "-s"
0x140044677  mov     rcx, [rdi+rbx*8]
0x14004467b  call    cs:__imp__o__wcsicmp
0x140044681  test    eax, eax
0x140044683  jnz     short loc_1400446A8
0x140044685  mov     rcx, [rdi+rbx*8+8]; String
0x14004468a  call    cs:__imp__wtoi64
0x140044690  mov     r15, rax
0x140044693  test    rax, rax
0x140044696  jnz     short loc_140044708
0x140044698  lea     rax, aNoSharedMemHan_0; "No shared mem handle passed"
0x14004469f  lea     edx, [r15+57h]
0x1400446a3  jmp     loc_1400448FC
0x1400446a8  mov     rcx, [rdi+rbx*8]
0x1400446ac  lea     rdx, aP; "-p"
0x1400446b3  call    cs:__imp__o__wcsicmp
0x1400446b9  test    eax, eax
0x1400446bb  jnz     short loc_1400446DD
0x1400446bd  mov     rcx, [rdi+rbx*8+8]
0x1400446c2  call    cs:__imp__o__wtoi
0x1400446c8  mov     ebp, eax
0x1400446ca  test    eax, eax
0x1400446cc  jnz     short loc_140044708
0x1400446ce  lea     rax, aInvalidProcess; "Invalid process id was passed"
0x1400446d5  lea     edx, [rbp+65h]
0x1400446d8  jmp     loc_1400448FC
0x1400446dd  mov     rcx, [rdi+rbx*8]
0x1400446e1  lea     rdx, aIp; "-ip"
0x1400446e8  call    cs:__imp__o__wcsicmp
0x1400446ee  test    eax, eax
0x1400446f0  jnz     short loc_140044708
0x1400446f2  mov     rcx, [rdi+rbx*8+8]
0x1400446f7  call    cs:__imp__o__wtoi
0x1400446fd  mov     r14d, eax
0x140044700  test    eax, eax
0x140044702  jz      loc_1400447B1
0x140044708  inc     esi
0x14004470a  cmp     esi, r12d
0x14004470d  jl      loc_14004466E
0x140044713  test    r15, r15
0x140044716  jz      loc_1400448F0
0x14004471c  test    ebp, ebp
0x14004471e  jz      loc_1400448F0
0x140044724  mov     ebx, 1FFFFFh
0x140044729  mov     r8d, ebp; dwProcessId
0x14004472c  mov     ecx, ebx; dwDesiredAccess
0x14004472e  xor     edx, edx; bInheritHandle
0x140044730  call    cs:__imp_OpenProcess
0x140044736  mov     rdi, rax
0x140044739  inc     rax
0x14004473c  cmp     rax, 1
0x140044740  jbe     loc_1400448AC
0x140044746  xor     edx, edx; bInheritHandle
0x140044748  mov     ecx, ebx; dwDesiredAccess
0x14004474a  test    r14d, r14d
0x14004474d  jz      short loc_1400447C2
0x14004474f  mov     r8d, r14d; dwProcessId
0x140044752  call    cs:__imp_OpenProcess
0x140044758  mov     rbx, rax
0x14004475b  inc     rax
0x14004475e  cmp     rax, 1
0x140044762  ja      short loc_140044777
0x140044764  mov     r8d, r14d; dwProcessId
0x140044767  xor     edx, edx; bInheritHandle
0x140044769  mov     ecx, 400h; dwDesiredAccess
0x14004476e  call    cs:__imp_OpenProcess
0x140044774  mov     rbx, rax
0x140044777  lea     rax, [rbx+1]
0x14004477b  cmp     rax, 1
0x14004477f  ja      short loc_1400447D7
0x140044781  call    cs:__imp_GetLastError
0x140044787  mov     esi, eax
0x140044789  test    eax, eax
0x14004478b  jle     short loc_140044796
0x14004478d  movzx   esi, ax
0x140044790  or      esi, 80070000h
0x140044796  mov     [rsp+78h+var_48], r14d
0x14004479b  lea     rax, aOpenprocessFai; "OpenProcess failed for initiating pid %"...
0x1400447a2  mov     dword ptr [rsp+78h+var_50], r14d
0x1400447a7  mov     edx, 9Bh
0x1400447ac  jmp     loc_140044875
0x1400447b1  lea     rax, aInvalidInitiat; "Invalid initiating process id was passe"...
0x1400447b8  mov     edx, 73h ; 's'
0x1400447bd  jmp     loc_1400448FC
0x1400447c2  mov     r8d, ebp; dwProcessId
0x1400447c5  call    cs:__imp_OpenProcess
0x1400447cb  mov     rbx, rax
0x1400447ce  inc     rax
0x1400447d1  cmp     rax, 1
0x1400447d5  jbe     short loc_14004484C
0x1400447d7  call    IsXerDumpNotifyStartPresent
0x1400447dc  test    al, al
0x1400447de  jz      short loc_1400447E9
0x1400447e0  mov     rcx, rdi
0x1400447e3  call    cs:__imp_XerDumpNotifyStart
0x1400447e9  mov     [rsp+78h+var_40], 0
0x1400447f2  xor     r9d, r9d
0x1400447f5  mov     [rsp+78h+var_48], 0
0x1400447fd  mov     r8, r15
0x140044800  mov     dword ptr [rsp+78h+var_50], 0
0x140044808  mov     rdx, rbx
0x14004480b  mov     rcx, rdi
0x14004480e  mov     [rsp+78h+var_58], 0
0x140044816  call    cs:__imp_WerpInitiateCrashReporting
0x14004481c  mov     esi, eax
0x14004481e  call    IsXerDumpNotifyStartPresent
0x140044823  test    al, al
0x140044825  jz      short loc_140044830
0x140044827  mov     rcx, rdi
0x14004482a  call    cs:__imp_XerDumpNotifyComplete
0x140044830  cmp     esi, 8007009Dh
0x140044836  jnz     short loc_14004488E
0x140044838  mov     r8d, 2
0x14004483e  lea     rdx, aCrash; "Crash"
0x140044845  call    ?UtilFireWerVerticalDisabledEvent@@YAXQEBU_tlgProvider_t@@PEB_WW4_VERTICAL_DISABLED_REASON@@@Z; UtilFireWerVerticalDisabledEvent(_tlgProvider_t const * const,wchar_t const *,_VERTICAL_DISABLED_REASON)
0x14004484a  jmp     short loc_14004488E
0x14004484c  call    cs:__imp_GetLastError
0x140044852  mov     esi, eax
0x140044854  test    eax, eax
0x140044856  jle     short loc_140044861
0x140044858  movzx   esi, ax
0x14004485b  or      esi, 80070000h
0x140044861  mov     [rsp+78h+var_48], ebp
0x140044865  lea     rax, aOpenprocessFai_0; "OpenProcess failed for self, pid %d (0x"...
0x14004486c  mov     dword ptr [rsp+78h+var_50], ebp; char *
0x140044870  mov     edx, 0ABh; void *
0x140044875  mov     rcx, [rsp+78h]; this
0x14004487a  lea     r8, aOnecoreWindows_10; "onecore\\windows\\feedback\\core\\werfa"...
0x140044881  mov     r9d, esi; char *
0x140044884  mov     qword ptr [rsp+78h+var_58], rax; int
0x140044889  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x14004488e  lea     rax, [rbx+1]
0x140044892  cmp     rax, 1
0x140044896  jbe     short loc_1400448A1
0x140044898  mov     rcx, rbx; hObject
0x14004489b  call    cs:__imp_CloseHandle
0x1400448a1  mov     rcx, rdi; hObject
0x1400448a4  call    cs:__imp_CloseHandle
0x1400448aa  jmp     short loc_14004491C
0x1400448ac  call    cs:__imp_GetLastError
0x1400448b2  mov     esi, eax
0x1400448b4  test    eax, eax
0x1400448b6  jle     short loc_1400448C1
0x1400448b8  movzx   esi, ax
0x1400448bb  or      esi, 80070000h
0x1400448c1  mov     rcx, [rsp+78h]; this
0x1400448c6  lea     rax, aOpenprocessFai_1; "OpenProcess failed for faulting pid %d "...
0x1400448cd  mov     [rsp+78h+var_48], ebp
0x1400448d1  lea     r8, aOnecoreWindows_10; "onecore\\windows\\feedback\\core\\werfa"...
0x1400448d8  mov     dword ptr [rsp+78h+var_50], ebp; char *
0x1400448dc  mov     r9d, esi; char *
0x1400448df  mov     edx, 87h; void *
0x1400448e4  mov     qword ptr [rsp+78h+var_58], rax; int
0x1400448e9  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400448ee  jmp     short loc_14004491C
0x1400448f0  lea     rax, aNoSharedMemHan; "No shared mem handle or process id was "...
0x1400448f7  mov     edx, 7Ch ; '|'; void *
0x1400448fc  mov     rcx, [rsp+78h]; this
0x140044901  lea     r8, aOnecoreWindows_10; "onecore\\windows\\feedback\\core\\werfa"...
0x140044908  mov     ebx, 80070057h
0x14004490d  mov     qword ptr [rsp+78h+var_58], rax; int
0x140044912  mov     r9d, ebx; char *
0x140044915  mov     esi, ebx
0x140044917  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x14004491c  mov     eax, esi
0x14004491e  add     rsp, 40h
0x140044922  pop     r15
0x140044924  pop     r14
0x140044926  pop     r12
0x140044928  pop     rdi
0x140044929  pop     rsi
0x14004492a  pop     rbp
0x14004492b  pop     rbx
0x14004492c  retn
```
