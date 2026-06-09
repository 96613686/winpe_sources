# CThreadChasing::GetWaitingOnPackageRelativeAppId(wchar_t *,ulong)

- ea: `0x14001cd3c`
- end: `0x14001cf14`
- name: `?GetWaitingOnPackageRelativeAppId@CThreadChasing@@QEAAJPEA_WK@Z`
- size: `472`
- prototype: `int(CThreadChasing *__hidden this, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002b5d8`

## callees

- `0x140002748`
- `0x14000b50c`
- `0x140014f14`
- `0x1400166ec`
- `0x14001cd3c`
- `0x140034968`
- `0x140034da8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001cdfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001cdfa`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001ce97`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001ce97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001cef0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001cef0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001cdde`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001cdde`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CThreadChasing::GetWaitingOnPackageRelativeAppId(DWORD *this, wchar_t *a2, __int64 a3, __int64 a4)
{
  signed int ProcessApplicationId; // ebx
  char *v7; // rsi
  DWORD v8; // r8d
  signed int LastError; // eax
  __int64 v10; // rdx
  DWORD EnvironmentVariableW; // eax
  wchar_t *v13[2]; // [rsp+20h] [rbp-40h] BYREF
  _WORD v14[8]; // [rsp+30h] [rbp-30h] BYREF
  void *v15; // [rsp+40h] [rbp-20h]
  _WORD *v16; // [rsp+48h] [rbp-18h]
  _WORD v17[8]; // [rsp+50h] [rbp-10h] BYREF

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, 0, a3, a4);
  ProcessApplicationId = -2147467259;
  v7 = 0;
  v15 = v17;
  v16 = v17;
  v17[0] = 0;
  v13[0] = v14;
  v13[1] = v14;
  v14[0] = 0;
  if ( (this[1132] & 0x1080F0) == 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  if ( !this[1127] )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  if ( (this[1132] & 0x1080F0) != 0 )
  {
    v8 = this[1127];
    if ( v8 )
    {
      v7 = (char *)OpenProcess(0x400u, 0, v8);
      if ( v7 == (char *)-1LL || v7 + 1 == (char *)1 )
      {
        LastError = GetLastError();
        ProcessApplicationId = LastError;
        if ( LastError > 0 )
          ProcessApplicationId = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            65,
            WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
            (unsigned int)ProcessApplicationId);
        }
      }
      else
      {
        ProcessApplicationId = PackageUtility::GetProcessApplicationId(v7);
        if ( ProcessApplicationId >= 0 )
        {
          ProcessApplicationId = PackageUtility::ParseApplicationId(v15, v10, v13);
          if ( ProcessApplicationId >= 0 )
          {
            ProcessApplicationId = StringCchCopyW(a2, 0x42u, v13[0]);
            if ( ProcessApplicationId >= 0 )
              ProcessApplicationId = 0;
          }
        }
      }
    }
  }
  EnvironmentVariableW = GetEnvironmentVariableW(L"_HANGREP_XPROC_PKGRELAPPID", a2, 0x42u);
  if ( EnvironmentVariableW && EnvironmentVariableW < 0x42 )
    ProcessApplicationId = 0;
  if ( v13[0] != v14 )
    operator delete(v13[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v15 != v17 )
    operator delete(v15, (const struct std::nothrow_t *)&std::nothrow);
  if ( (unsigned __int64)(v7 + 1) > 1 )
    CloseHandle(v7);
  return (unsigned int)ProcessApplicationId;
}

```

## disassembly

```asm
0x14001cd3c  mov     [rsp-18h+arg_8], rbx
0x14001cd41  mov     [rsp-18h+arg_10], rsi
0x14001cd46  push    rbp
0x14001cd47  push    rdi
0x14001cd48  push    r14
0x14001cd4a  mov     rbp, rsp
0x14001cd4d  sub     rsp, 60h
0x14001cd51  mov     r14, rdx
0x14001cd54  mov     rdi, rcx
0x14001cd57  test    rdx, rdx
0x14001cd5a  jnz     short loc_14001CD61
0x14001cd5c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001cd61  mov     ebx, 80004005h
0x14001cd66  xor     esi, esi
0x14001cd68  mov     [rbp+arg_0], rsi
0x14001cd6c  lea     rax, [rbp+var_10]
0x14001cd70  mov     [rbp+var_20], rax
0x14001cd74  lea     rax, [rbp+var_10]
0x14001cd78  mov     [rbp+var_18], rax
0x14001cd7c  xor     eax, eax
0x14001cd7e  mov     [rbp+var_10], ax
0x14001cd82  lea     rax, [rbp+var_30]
0x14001cd86  mov     [rbp+var_40], rax
0x14001cd8a  lea     rax, [rbp+var_30]
0x14001cd8e  mov     [rbp+var_38], rax
0x14001cd92  xor     eax, eax
0x14001cd94  mov     [rbp+var_30], ax
0x14001cd98  test    dword ptr [rdi+11B0h], 1080F0h
0x14001cda2  jnz     short loc_14001CDA9
0x14001cda4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001cda9  cmp     dword ptr [rdi+119Ch], 0
0x14001cdb0  jnz     short loc_14001CDB7
0x14001cdb2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001cdb7  test    dword ptr [rdi+11B0h], 1080F0h
0x14001cdc1  jz      loc_14001CE87
0x14001cdc7  mov     r8d, [rdi+119Ch]; dwProcessId
0x14001cdce  test    r8d, r8d
0x14001cdd1  jz      loc_14001CE87
0x14001cdd7  xor     edx, edx; bInheritHandle
0x14001cdd9  mov     ecx, 400h; dwDesiredAccess
0x14001cdde  call    cs:__imp_OpenProcess
0x14001cde5  nop     dword ptr [rax+rax+00h]
0x14001cdea  mov     rsi, rax
0x14001cded  mov     [rbp+arg_0], rax
0x14001cdf1  inc     rax
0x14001cdf4  cmp     rax, 1
0x14001cdf8  ja      short loc_14001CE48
0x14001cdfa  call    cs:__imp_GetLastError
0x14001ce01  nop     dword ptr [rax+rax+00h]
0x14001ce06  mov     ebx, eax
0x14001ce08  test    eax, eax
0x14001ce0a  jle     short loc_14001CE15
0x14001ce0c  movzx   ebx, ax
0x14001ce0f  or      ebx, 80070000h
0x14001ce15  lea     rax, WPP_GLOBAL_Control
0x14001ce1c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ce23  cmp     rcx, rax
0x14001ce26  jz      short loc_14001CE87
0x14001ce28  test    byte ptr [rcx+1Ch], 1
0x14001ce2c  jz      short loc_14001CE87
0x14001ce2e  mov     edx, 41h ; 'A'
0x14001ce33  mov     r9d, ebx
0x14001ce36  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001ce3d  mov     rcx, [rcx+10h]
0x14001ce41  call    WPP_SF_d
0x14001ce46  jmp     short loc_14001CE87
0x14001ce48  lea     rdx, [rbp+var_20]
0x14001ce4c  mov     rcx, rsi; ProcessHandle
0x14001ce4f  call    ?GetProcessApplicationId@PackageUtility@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PackageUtility::GetProcessApplicationId(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14001ce54  mov     ebx, eax
0x14001ce56  test    eax, eax
0x14001ce58  js      short loc_14001CE87
0x14001ce5a  lea     r8, [rbp+var_40]
0x14001ce5e  mov     rcx, [rbp+var_20]
0x14001ce62  call    ?ParseApplicationId@PackageUtility@@SAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; PackageUtility::ParseApplicationId(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14001ce67  mov     ebx, eax
0x14001ce69  test    eax, eax
0x14001ce6b  js      short loc_14001CE87
0x14001ce6d  mov     r8, [rbp+var_40]; wchar_t *
0x14001ce71  mov     edx, 42h ; 'B'; unsigned __int64
0x14001ce76  mov     rcx, r14; wchar_t *
0x14001ce79  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001ce7e  mov     ebx, eax
0x14001ce80  xor     eax, eax
0x14001ce82  test    ebx, ebx
0x14001ce84  cmovns  ebx, eax
0x14001ce87  mov     r8d, 42h ; 'B'; nSize
0x14001ce8d  mov     rdx, r14; lpBuffer
0x14001ce90  lea     rcx, aHangrepXprocPk_0; "_HANGREP_XPROC_PKGRELAPPID"
0x14001ce97  call    cs:__imp_GetEnvironmentVariableW
0x14001ce9e  nop     dword ptr [rax+rax+00h]
0x14001cea3  test    eax, eax
0x14001cea5  jz      short loc_14001CEAF
0x14001cea7  xor     ecx, ecx
0x14001cea9  cmp     eax, 42h ; 'B'
0x14001ceac  cmovb   ebx, ecx
0x14001ceaf  lea     rax, [rbp+var_30]
0x14001ceb3  mov     rcx, [rbp+var_40]; void *
0x14001ceb7  cmp     rcx, rax
0x14001ceba  jz      short loc_14001CEC9
0x14001cebc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001cec3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001cec8  nop
0x14001cec9  lea     rax, [rbp+var_10]
0x14001cecd  mov     rcx, [rbp+var_20]; void *
0x14001ced1  cmp     rcx, rax
0x14001ced4  jz      short loc_14001CEE3
0x14001ced6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001cedd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001cee2  nop
0x14001cee3  lea     rax, [rsi+1]
0x14001cee7  cmp     rax, 1
0x14001ceeb  jbe     short loc_14001CEFC
0x14001ceed  mov     rcx, rsi; hObject
0x14001cef0  call    cs:__imp_CloseHandle
0x14001cef7  nop     dword ptr [rax+rax+00h]
0x14001cefc  mov     eax, ebx
0x14001cefe  lea     r11, [rsp+60h+var_s0]
0x14001cf03  mov     rbx, [r11+28h]
0x14001cf07  mov     rsi, [r11+30h]
0x14001cf0b  mov     rsp, r11
0x14001cf0e  pop     r14
0x14001cf10  pop     rdi
0x14001cf11  pop     rbp
0x14001cf12  retn
```
