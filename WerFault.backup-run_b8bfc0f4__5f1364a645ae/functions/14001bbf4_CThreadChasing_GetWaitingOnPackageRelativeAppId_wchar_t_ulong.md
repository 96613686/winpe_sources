# CThreadChasing::GetWaitingOnPackageRelativeAppId(wchar_t *,ulong)

- ea: `0x14001bbf4`
- end: `0x14001bdb3`
- name: `?GetWaitingOnPackageRelativeAppId@CThreadChasing@@QEAAJPEA_WK@Z`
- size: `447`
- prototype: `int(CThreadChasing *__hidden this, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140029a14`

## callees

- `0x140002728`
- `0x14000b4cc`
- `0x140014474`
- `0x140015b40`
- `0x14001bbf4`
- `0x140032628`
- `0x140032a48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bcac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bcac`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001bd43`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001bd43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001bd96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001bd96`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001bc96`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001bc96`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CThreadChasing::GetWaitingOnPackageRelativeAppId(DWORD *this, wchar_t *a2)
{
  signed int ProcessApplicationId; // ebx
  char *v5; // rsi
  DWORD v6; // r8d
  signed int LastError; // eax
  __int64 v8; // rdx
  DWORD EnvironmentVariableW; // eax
  wchar_t *v11[2]; // [rsp+20h] [rbp-40h] BYREF
  _WORD v12[8]; // [rsp+30h] [rbp-30h] BYREF
  void *v13; // [rsp+40h] [rbp-20h]
  _WORD *v14; // [rsp+48h] [rbp-18h]
  _WORD v15[8]; // [rsp+50h] [rbp-10h] BYREF

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  ProcessApplicationId = -2147467259;
  v5 = 0;
  v13 = v15;
  v14 = v15;
  v15[0] = 0;
  v11[0] = v12;
  v11[1] = v12;
  v12[0] = 0;
  if ( (this[1132] & 0x1080F0) == 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( !this[1127] )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( (this[1132] & 0x1080F0) != 0 )
  {
    v6 = this[1127];
    if ( v6 )
    {
      v5 = (char *)OpenProcess(0x400u, 0, v6);
      if ( v5 == (char *)-1LL || v5 + 1 == (char *)1 )
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
        ProcessApplicationId = PackageUtility::GetProcessApplicationId(v5);
        if ( ProcessApplicationId >= 0 )
        {
          ProcessApplicationId = PackageUtility::ParseApplicationId(v13, v8, v11);
          if ( ProcessApplicationId >= 0 )
          {
            ProcessApplicationId = StringCchCopyW(a2, 0x42u, v11[0]);
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
  if ( v11[0] != v12 )
    operator delete(v11[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v13 != v15 )
    operator delete(v13, (const struct std::nothrow_t *)&std::nothrow);
  if ( (unsigned __int64)(v5 + 1) > 1 )
    CloseHandle(v5);
  return (unsigned int)ProcessApplicationId;
}

```

## disassembly

```asm
0x14001bbf4  mov     [rsp-18h+arg_8], rbx
0x14001bbf9  mov     [rsp-18h+arg_10], rsi
0x14001bbfe  push    rbp
0x14001bbff  push    rdi
0x14001bc00  push    r14
0x14001bc02  mov     rbp, rsp
0x14001bc05  sub     rsp, 60h
0x14001bc09  mov     r14, rdx
0x14001bc0c  mov     rdi, rcx
0x14001bc0f  test    rdx, rdx
0x14001bc12  jnz     short loc_14001BC19
0x14001bc14  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001bc19  mov     ebx, 80004005h
0x14001bc1e  xor     esi, esi
0x14001bc20  mov     [rbp+arg_0], rsi
0x14001bc24  lea     rax, [rbp+var_10]
0x14001bc28  mov     [rbp+var_20], rax
0x14001bc2c  lea     rax, [rbp+var_10]
0x14001bc30  mov     [rbp+var_18], rax
0x14001bc34  xor     eax, eax
0x14001bc36  mov     [rbp+var_10], ax
0x14001bc3a  lea     rax, [rbp+var_30]
0x14001bc3e  mov     [rbp+var_40], rax
0x14001bc42  lea     rax, [rbp+var_30]
0x14001bc46  mov     [rbp+var_38], rax
0x14001bc4a  xor     eax, eax
0x14001bc4c  mov     [rbp+var_30], ax
0x14001bc50  test    dword ptr [rdi+11B0h], 1080F0h
0x14001bc5a  jnz     short loc_14001BC61
0x14001bc5c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001bc61  cmp     dword ptr [rdi+119Ch], 0
0x14001bc68  jnz     short loc_14001BC6F
0x14001bc6a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001bc6f  test    dword ptr [rdi+11B0h], 1080F0h
0x14001bc79  jz      loc_14001BD33
0x14001bc7f  mov     r8d, [rdi+119Ch]; dwProcessId
0x14001bc86  test    r8d, r8d
0x14001bc89  jz      loc_14001BD33
0x14001bc8f  xor     edx, edx; bInheritHandle
0x14001bc91  mov     ecx, 400h; dwDesiredAccess
0x14001bc96  call    cs:__imp_OpenProcess
0x14001bc9c  mov     rsi, rax
0x14001bc9f  mov     [rbp+arg_0], rax
0x14001bca3  inc     rax
0x14001bca6  cmp     rax, 1
0x14001bcaa  ja      short loc_14001BCF4
0x14001bcac  call    cs:__imp_GetLastError
0x14001bcb2  mov     ebx, eax
0x14001bcb4  test    eax, eax
0x14001bcb6  jle     short loc_14001BCC1
0x14001bcb8  movzx   ebx, ax
0x14001bcbb  or      ebx, 80070000h
0x14001bcc1  lea     rax, WPP_GLOBAL_Control
0x14001bcc8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bccf  cmp     rcx, rax
0x14001bcd2  jz      short loc_14001BD33
0x14001bcd4  test    byte ptr [rcx+1Ch], 1
0x14001bcd8  jz      short loc_14001BD33
0x14001bcda  mov     edx, 41h ; 'A'
0x14001bcdf  mov     r9d, ebx
0x14001bce2  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001bce9  mov     rcx, [rcx+10h]
0x14001bced  call    WPP_SF_d
0x14001bcf2  jmp     short loc_14001BD33
0x14001bcf4  lea     rdx, [rbp+var_20]
0x14001bcf8  mov     rcx, rsi; ProcessHandle
0x14001bcfb  call    ?GetProcessApplicationId@PackageUtility@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PackageUtility::GetProcessApplicationId(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14001bd00  mov     ebx, eax
0x14001bd02  test    eax, eax
0x14001bd04  js      short loc_14001BD33
0x14001bd06  lea     r8, [rbp+var_40]
0x14001bd0a  mov     rcx, [rbp+var_20]
0x14001bd0e  call    ?ParseApplicationId@PackageUtility@@SAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; PackageUtility::ParseApplicationId(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14001bd13  mov     ebx, eax
0x14001bd15  test    eax, eax
0x14001bd17  js      short loc_14001BD33
0x14001bd19  mov     r8, [rbp+var_40]; wchar_t *
0x14001bd1d  mov     edx, 42h ; 'B'; unsigned __int64
0x14001bd22  mov     rcx, r14; wchar_t *
0x14001bd25  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001bd2a  mov     ebx, eax
0x14001bd2c  xor     eax, eax
0x14001bd2e  test    ebx, ebx
0x14001bd30  cmovns  ebx, eax
0x14001bd33  mov     r8d, 42h ; 'B'; nSize
0x14001bd39  mov     rdx, r14; lpBuffer
0x14001bd3c  lea     rcx, aHangrepXprocPk_0; "_HANGREP_XPROC_PKGRELAPPID"
0x14001bd43  call    cs:__imp_GetEnvironmentVariableW
0x14001bd49  test    eax, eax
0x14001bd4b  jz      short loc_14001BD55
0x14001bd4d  xor     ecx, ecx
0x14001bd4f  cmp     eax, 42h ; 'B'
0x14001bd52  cmovb   ebx, ecx
0x14001bd55  lea     rax, [rbp+var_30]
0x14001bd59  mov     rcx, [rbp+var_40]; void *
0x14001bd5d  cmp     rcx, rax
0x14001bd60  jz      short loc_14001BD6F
0x14001bd62  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001bd69  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001bd6e  nop
0x14001bd6f  lea     rax, [rbp+var_10]
0x14001bd73  mov     rcx, [rbp+var_20]; void *
0x14001bd77  cmp     rcx, rax
0x14001bd7a  jz      short loc_14001BD89
0x14001bd7c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001bd83  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001bd88  nop
0x14001bd89  lea     rax, [rsi+1]
0x14001bd8d  cmp     rax, 1
0x14001bd91  jbe     short loc_14001BD9C
0x14001bd93  mov     rcx, rsi; hObject
0x14001bd96  call    cs:__imp_CloseHandle
0x14001bd9c  mov     eax, ebx
0x14001bd9e  lea     r11, [rsp+60h+var_s0]
0x14001bda3  mov     rbx, [r11+28h]
0x14001bda7  mov     rsi, [r11+30h]
0x14001bdab  mov     rsp, r11
0x14001bdae  pop     r14
0x14001bdb0  pop     rdi
0x14001bdb1  pop     rbp
0x14001bdb2  retn
```
