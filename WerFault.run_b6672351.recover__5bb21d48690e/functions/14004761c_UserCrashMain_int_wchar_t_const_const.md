# UserCrashMain(int,wchar_t const * * const)

- ea: `0x14004761c`
- end: `0x1400479c6`
- name: `?UserCrashMain@@YAHHQEAPEB_W@Z`
- size: `938`
- prototype: `__int64 __fastcall(char *, const wchar_t **const)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000beb8`

## callees

- `0x140003b64`
- `0x1400088e8`
- `0x14000bee0`
- `0x140032600`
- `0x14004761c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004769b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400476e3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140047724`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004769b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400476e3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140047724`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1400476f8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140047739`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1400476f8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140047739`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1400476b0`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1400476b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400477df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400478cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004793e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400477df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400478cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004793e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047921`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047930`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047921`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140047930`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140047778`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400477a4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400477c6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140047829`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140047778`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400477a4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400477c6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140047829`
- `faultrep!WerpInitiateCrashReporting` at `0x14004788a`
- `faultrep!WerpInitiateCrashReporting` at `0x14004788a`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyComplete` at `0x1400478a4`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyComplete` at `0x1400478a4`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyStart` at `0x140047851`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyStart` at `0x140047851`

## string_xrefs

- `0x14004763a`: `Invalid number of command line params passed. Params passed: %d`
- `0x14004795e`: `OpenProcess failed for faulting pid %d (0x%x)`
- `0x1400477ff`: `OpenProcess failed for initiating pid %d (0x%x)`
- `0x1400478eb`: `OpenProcess failed for self, pid %d (0x%x)`

## pseudocode

```c
__int64 __fastcall UserCrashMain(char *a1, const wchar_t **const a2)
{
  int v3; // ebx
  __int64 v5; // r15
  DWORD v6; // ebp
  DWORD v7; // r14d
  __int64 v8; // r8
  unsigned int v9; // esi
  __int64 v10; // r8
  const char *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  char *v14; // rdi
  char *v15; // rbx
  signed int v16; // eax
  unsigned int v17; // esi
  const char *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  signed int v21; // eax
  signed int LastError; // eax
  char *v23; // [rsp+28h] [rbp-50h]
  DWORD v24; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v3 = (int)a1;
  if ( (int)a1 < 6 )
  {
    LODWORD(v23) = (_DWORD)a1;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\userfault.cpp",
      (const char *)0x80070057LL,
      (int)"Invalid number of command line params passed. Params passed: %d",
      v23);
    return 2147942487LL;
  }
  v5 = 0;
  v6 = 0;
  v7 = 0;
  UtilCheckDebugWait(L"WaitOnStart");
  v9 = 1;
  if ( v3 - 1 <= 1 )
    goto LABEL_41;
  do
  {
    if ( (unsigned int)_o__wcsicmp(a2[v9], L"-s", v8) )
    {
      if ( (unsigned int)_o__wcsicmp(a2[v9], L"-p", v10) )
      {
        if ( !(unsigned int)_o__wcsicmp(a2[v9], L"-ip", v13) )
        {
          v7 = _o__wtoi(a2[v9 + 1]);
          if ( !v7 )
          {
            v11 = "Invalid initiating process id was passed";
            v12 = 115;
            goto LABEL_42;
          }
        }
      }
      else
      {
        v6 = _o__wtoi(a2[v9 + 1]);
        if ( !v6 )
        {
          v11 = "Invalid process id was passed";
          v12 = 101;
          goto LABEL_42;
        }
      }
    }
    else
    {
      v5 = _wtoi64(a2[v9 + 1]);
      if ( !v5 )
      {
        v11 = "No shared mem handle passed";
        v12 = 87;
        goto LABEL_42;
      }
    }
    ++v9;
  }
  while ( (int)v9 < v3 - 1 );
  if ( !v5 || !v6 )
  {
LABEL_41:
    v11 = "No shared mem handle or process id was passed";
    v12 = 124;
LABEL_42:
    v17 = -2147024809;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\userfault.cpp",
      (const char *)0x80070057LL,
      (int)v11,
      v23);
    return v17;
  }
  v14 = (char *)OpenProcess(0x1FFFFFu, 0, v6);
  if ( v14 == (char *)-1LL || v14 + 1 == (char *)1 )
  {
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    LODWORD(v23) = v6;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\userfault.cpp",
      (const char *)v17,
      (int)"OpenProcess failed for faulting pid %d (0x%x)",
      v23,
      v6);
    return v17;
  }
  if ( !v7 )
  {
    v15 = (char *)OpenProcess(0x1FFFFFu, 0, v6);
    if ( v15 == (char *)-1LL || v15 + 1 == (char *)1 )
    {
      v21 = GetLastError();
      v17 = v21;
      if ( v21 > 0 )
        v17 = (unsigned __int16)v21 | 0x80070000;
      v24 = v6;
      v18 = "OpenProcess failed for self, pid %d (0x%x)";
      LODWORD(v23) = v6;
      v19 = 171;
      goto LABEL_34;
    }
LABEL_25:
    if ( (unsigned __int8)IsXerDumpNotifyStartPresent() )
      XerDumpNotifyStart(v14);
    v17 = WerpInitiateCrashReporting(v14, v15, v5, 0, 0, 0, 0, 0);
    if ( (unsigned __int8)IsXerDumpNotifyStartPresent() )
      XerDumpNotifyComplete(v14);
    if ( v17 == -2147024739 )
      UtilFireWerVerticalDisabledEvent(v20, L"Crash", 2);
    goto LABEL_35;
  }
  v15 = (char *)OpenProcess(0x1FFFFFu, 0, v7);
  if ( v15 == (char *)-1LL || v15 + 1 == (char *)1 )
    v15 = (char *)OpenProcess(0x400u, 0, v7);
  if ( (unsigned __int64)(v15 + 1) > 1 )
    goto LABEL_25;
  v16 = GetLastError();
  v17 = v16;
  if ( v16 > 0 )
    v17 = (unsigned __int16)v16 | 0x80070000;
  v24 = v7;
  v18 = "OpenProcess failed for initiating pid %d (0x%x)";
  LODWORD(v23) = v7;
  v19 = 155;
LABEL_34:
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)v19,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\user\\userfault.cpp",
    (const char *)v17,
    (int)v18,
    v23,
    v24);
LABEL_35:
  if ( (unsigned __int64)(v15 + 1) > 1 )
    CloseHandle(v15);
  CloseHandle(v14);
  return v17;
}

```

## disassembly

```asm
0x14004761c  push    rbx
0x14004761e  push    rbp
0x14004761f  push    rsi
0x140047620  push    rdi
0x140047621  push    r12
0x140047623  push    r14
0x140047625  push    r15
0x140047627  sub     rsp, 40h
0x14004762b  mov     rdi, rdx
0x14004762e  mov     ebx, ecx
0x140047630  cmp     ecx, 6
0x140047633  jge     short loc_14004766A
0x140047635  mov     rcx, [rsp+78h]; this
0x14004763a  lea     rax, aInvalidNumberO_1; "Invalid number of command line params p"...
0x140047641  mov     dword ptr [rsp+78h+var_50], ebx; char *
0x140047645  lea     r8, aOnecoreWindows_10; "onecore\\windows\\feedback\\core\\werfa"...
0x14004764c  mov     ebx, 80070057h
0x140047651  mov     qword ptr [rsp+78h+var_58], rax; int
0x140047656  mov     r9d, ebx; char *
0x140047659  mov     edx, 3Fh ; '?'; void *
0x14004765e  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x140047663  mov     eax, ebx
0x140047665  jmp     loc_1400479B6
0x14004766a  lea     rcx, aWaitonstart; "WaitOnStart"
0x140047671  xor     r15d, r15d
0x140047674  xor     ebp, ebp
0x140047676  xor     r14d, r14d
0x140047679  call    ?UtilCheckDebugWait@@YAXPEB_W@Z; UtilCheckDebugWait(wchar_t const *)
0x14004767e  lea     esi, [rbp+1]
0x140047681  lea     r12d, [rbx-1]
0x140047685  cmp     r12d, esi
0x140047688  jle     loc_140047988
0x14004768e  mov     ebx, esi
0x140047690  lea     rdx, aS_2; "-s"
0x140047697  mov     rcx, [rdi+rbx*8]
0x14004769b  call    cs:__imp__o__wcsicmp
0x1400476a2  nop     dword ptr [rax+rax+00h]
0x1400476a7  test    eax, eax
0x1400476a9  jnz     short loc_1400476D8
0x1400476ab  mov     rcx, [rdi+rbx*8+8]; String
0x1400476b0  call    cs:__imp__wtoi64
0x1400476b7  nop     dword ptr [rax+rax+00h]
0x1400476bc  mov     r15, rax
0x1400476bf  test    rax, rax
0x1400476c2  jnz     loc_140047750
0x1400476c8  lea     rax, aNoSharedMemHan_0; "No shared mem handle passed"
0x1400476cf  lea     edx, [r15+57h]
0x1400476d3  jmp     loc_140047994
0x1400476d8  mov     rcx, [rdi+rbx*8]
0x1400476dc  lea     rdx, aP; "-p"
0x1400476e3  call    cs:__imp__o__wcsicmp
0x1400476ea  nop     dword ptr [rax+rax+00h]
0x1400476ef  test    eax, eax
0x1400476f1  jnz     short loc_140047719
0x1400476f3  mov     rcx, [rdi+rbx*8+8]
0x1400476f8  call    cs:__imp__o__wtoi
0x1400476ff  nop     dword ptr [rax+rax+00h]
0x140047704  mov     ebp, eax
0x140047706  test    eax, eax
0x140047708  jnz     short loc_140047750
0x14004770a  lea     rax, aInvalidProcess; "Invalid process id was passed"
0x140047711  lea     edx, [rbp+65h]
0x140047714  jmp     loc_140047994
0x140047719  mov     rcx, [rdi+rbx*8]
0x14004771d  lea     rdx, aIp; "-ip"
0x140047724  call    cs:__imp__o__wcsicmp
0x14004772b  nop     dword ptr [rax+rax+00h]
0x140047730  test    eax, eax
0x140047732  jnz     short loc_140047750
0x140047734  mov     rcx, [rdi+rbx*8+8]
0x140047739  call    cs:__imp__o__wtoi
0x140047740  nop     dword ptr [rax+rax+00h]
0x140047745  mov     r14d, eax
0x140047748  test    eax, eax
0x14004774a  jz      loc_140047815
0x140047750  inc     esi
0x140047752  cmp     esi, r12d
0x140047755  jl      loc_14004768E
0x14004775b  test    r15, r15
0x14004775e  jz      loc_140047988
0x140047764  test    ebp, ebp
0x140047766  jz      loc_140047988
0x14004776c  mov     ebx, 1FFFFFh
0x140047771  mov     r8d, ebp; dwProcessId
0x140047774  mov     ecx, ebx; dwDesiredAccess
0x140047776  xor     edx, edx; bInheritHandle
0x140047778  call    cs:__imp_OpenProcess
0x14004777f  nop     dword ptr [rax+rax+00h]
0x140047784  mov     rdi, rax
0x140047787  inc     rax
0x14004778a  cmp     rax, 1
0x14004778e  jbe     loc_14004793E
0x140047794  xor     edx, edx; bInheritHandle
0x140047796  mov     ecx, ebx; dwDesiredAccess
0x140047798  test    r14d, r14d
0x14004779b  jz      loc_140047826
0x1400477a1  mov     r8d, r14d; dwProcessId
0x1400477a4  call    cs:__imp_OpenProcess
0x1400477ab  nop     dword ptr [rax+rax+00h]
0x1400477b0  mov     rbx, rax
0x1400477b3  inc     rax
0x1400477b6  cmp     rax, 1
0x1400477ba  ja      short loc_1400477D5
0x1400477bc  mov     r8d, r14d; dwProcessId
0x1400477bf  xor     edx, edx; bInheritHandle
0x1400477c1  mov     ecx, 400h; dwDesiredAccess
0x1400477c6  call    cs:__imp_OpenProcess
0x1400477cd  nop     dword ptr [rax+rax+00h]
0x1400477d2  mov     rbx, rax
0x1400477d5  lea     rax, [rbx+1]
0x1400477d9  cmp     rax, 1
0x1400477dd  ja      short loc_140047845
0x1400477df  call    cs:__imp_GetLastError
0x1400477e6  nop     dword ptr [rax+rax+00h]
0x1400477eb  mov     esi, eax
0x1400477ed  test    eax, eax
0x1400477ef  jle     short loc_1400477FA
0x1400477f1  movzx   esi, ax
0x1400477f4  or      esi, 80070000h
0x1400477fa  mov     [rsp+78h+var_48], r14d
0x1400477ff  lea     rax, aOpenprocessFai; "OpenProcess failed for initiating pid %"...
0x140047806  mov     dword ptr [rsp+78h+var_50], r14d
0x14004780b  mov     edx, 9Bh
0x140047810  jmp     loc_1400478FB
0x140047815  lea     rax, aInvalidInitiat; "Invalid initiating process id was passe"...
0x14004781c  mov     edx, 73h ; 's'
0x140047821  jmp     loc_140047994
0x140047826  mov     r8d, ebp; dwProcessId
0x140047829  call    cs:__imp_OpenProcess
0x140047830  nop     dword ptr [rax+rax+00h]
0x140047835  mov     rbx, rax
0x140047838  inc     rax
0x14004783b  cmp     rax, 1
0x14004783f  jbe     loc_1400478CC
0x140047845  call    IsXerDumpNotifyStartPresent
0x14004784a  test    al, al
0x14004784c  jz      short loc_14004785D
0x14004784e  mov     rcx, rdi
0x140047851  call    cs:__imp_XerDumpNotifyStart
0x140047858  nop     dword ptr [rax+rax+00h]
0x14004785d  mov     [rsp+78h+var_40], 0
0x140047866  xor     r9d, r9d
0x140047869  mov     [rsp+78h+var_48], 0
0x140047871  mov     r8, r15
0x140047874  mov     dword ptr [rsp+78h+var_50], 0
0x14004787c  mov     rdx, rbx
0x14004787f  mov     rcx, rdi
0x140047882  mov     [rsp+78h+var_58], 0
0x14004788a  call    cs:__imp_WerpInitiateCrashReporting
0x140047891  nop     dword ptr [rax+rax+00h]
0x140047896  mov     esi, eax
0x140047898  call    IsXerDumpNotifyStartPresent
0x14004789d  test    al, al
0x14004789f  jz      short loc_1400478B0
0x1400478a1  mov     rcx, rdi
0x1400478a4  call    cs:__imp_XerDumpNotifyComplete
0x1400478ab  nop     dword ptr [rax+rax+00h]
0x1400478b0  cmp     esi, 8007009Dh
0x1400478b6  jnz     short loc_140047914
0x1400478b8  mov     r8d, 2
0x1400478be  lea     rdx, aCrash; "Crash"
0x1400478c5  call    ?UtilFireWerVerticalDisabledEvent@@YAXQEBU_tlgProvider_t@@PEB_WW4_VERTICAL_DISABLED_REASON@@@Z; UtilFireWerVerticalDisabledEvent(_tlgProvider_t const * const,wchar_t const *,_VERTICAL_DISABLED_REASON)
0x1400478ca  jmp     short loc_140047914
0x1400478cc  call    cs:__imp_GetLastError
0x1400478d3  nop     dword ptr [rax+rax+00h]
0x1400478d8  mov     esi, eax
0x1400478da  test    eax, eax
0x1400478dc  jle     short loc_1400478E7
0x1400478de  movzx   esi, ax
0x1400478e1  or      esi, 80070000h
0x1400478e7  mov     [rsp+78h+var_48], ebp
0x1400478eb  lea     rax, aOpenprocessFai_0; "OpenProcess failed for self, pid %d (0x"...
0x1400478f2  mov     dword ptr [rsp+78h+var_50], ebp; char *
0x1400478f6  mov     edx, 0ABh; void *
0x1400478fb  mov     rcx, [rsp+78h]; this
0x140047900  lea     r8, aOnecoreWindows_10; "onecore\\windows\\feedback\\core\\werfa"...
0x140047907  mov     r9d, esi; char *
0x14004790a  mov     qword ptr [rsp+78h+var_58], rax; int
0x14004790f  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x140047914  lea     rax, [rbx+1]
0x140047918  cmp     rax, 1
0x14004791c  jbe     short loc_14004792D
0x14004791e  mov     rcx, rbx; hObject
0x140047921  call    cs:__imp_CloseHandle
0x140047928  nop     dword ptr [rax+rax+00h]
0x14004792d  mov     rcx, rdi; hObject
0x140047930  call    cs:__imp_CloseHandle
0x140047937  nop     dword ptr [rax+rax+00h]
0x14004793c  jmp     short loc_1400479B4
0x14004793e  call    cs:__imp_GetLastError
0x140047945  nop     dword ptr [rax+rax+00h]
0x14004794a  mov     esi, eax
0x14004794c  test    eax, eax
0x14004794e  jle     short loc_140047959
0x140047950  movzx   esi, ax
0x140047953  or      esi, 80070000h
0x140047959  mov     rcx, [rsp+78h]; this
0x14004795e  lea     rax, aOpenprocessFai_1; "OpenProcess failed for faulting pid %d "...
0x140047965  mov     [rsp+78h+var_48], ebp
0x140047969  lea     r8, aOnecoreWindows_10; "onecore\\windows\\feedback\\core\\werfa"...
0x140047970  mov     dword ptr [rsp+78h+var_50], ebp; char *
0x140047974  mov     r9d, esi; char *
0x140047977  mov     edx, 87h; void *
0x14004797c  mov     qword ptr [rsp+78h+var_58], rax; int
0x140047981  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x140047986  jmp     short loc_1400479B4
0x140047988  lea     rax, aNoSharedMemHan; "No shared mem handle or process id was "...
0x14004798f  mov     edx, 7Ch ; '|'; void *
0x140047994  mov     rcx, [rsp+78h]; this
0x140047999  lea     r8, aOnecoreWindows_10; "onecore\\windows\\feedback\\core\\werfa"...
0x1400479a0  mov     ebx, 80070057h
0x1400479a5  mov     qword ptr [rsp+78h+var_58], rax; int
0x1400479aa  mov     r9d, ebx; char *
0x1400479ad  mov     esi, ebx
0x1400479af  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400479b4  mov     eax, esi
0x1400479b6  add     rsp, 40h
0x1400479ba  pop     r15
0x1400479bc  pop     r14
0x1400479be  pop     r12
0x1400479c0  pop     rdi
0x1400479c1  pop     rsi
0x1400479c2  pop     rbp
0x1400479c3  pop     rbx
0x1400479c4  retn
```
