# CThreadChasing::GetWaitingOnPackageFullName(wchar_t *,ulong)

- ea: `0x14001ba3c`
- end: `0x14001bbec`
- name: `?GetWaitingOnPackageFullName@CThreadChasing@@QEAAJPEA_WK@Z`
- size: `432`
- prototype: `__int64 __fastcall(DWORD *this, wchar_t *, UINT32)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140029a14`

## callees

- `0x1400034ec`
- `0x140003b68`
- `0x140014474`
- `0x140015b40`
- `0x14001ba3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bad5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bad5`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001bbb1`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001bbb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001bbd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001bbd1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001babe`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001babe`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x14001bb45`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x14001bb45`
- `ext-ms-win-wer-xbox-l1-1-2!XerGetPackageIdentity` at `0x14001bb87`
- `ext-ms-win-wer-xbox-l1-1-2!XerGetPackageIdentity` at `0x14001bb87`

## pseudocode

```c
__int64 __fastcall CThreadChasing::GetWaitingOnPackageFullName(DWORD *this, wchar_t *a2, UINT32 a3)
{
  unsigned int PackageIdentity; // ebx
  char *v6; // rbp
  DWORD v7; // r8d
  signed int LastError; // eax
  LONG PackageFullName; // eax
  __int64 v10; // rcx
  DWORD EnvironmentVariableW; // eax
  UINT32 packageFullNameLength; // [rsp+60h] [rbp+18h] BYREF

  packageFullNameLength = a3;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  PackageIdentity = -2147467259;
  v6 = 0;
  packageFullNameLength = 0;
  if ( (this[1132] & 0x1080F0) == 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( !this[1127] )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( (this[1132] & 0x1080F0) != 0 )
  {
    v7 = this[1127];
    if ( v7 )
    {
      v6 = (char *)OpenProcess(0x410u, 0, v7);
      if ( v6 == (char *)-1LL || v6 + 1 == (char *)1 )
      {
        LastError = GetLastError();
        PackageIdentity = LastError;
        if ( LastError > 0 )
          PackageIdentity = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            64,
            WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
            PackageIdentity);
        }
        goto LABEL_26;
      }
      packageFullNameLength = 128;
      *a2 = 0;
      if ( !(unsigned __int8)IsGetPackageFullNamePresent() )
      {
        if ( (unsigned __int8)IsXerGetPackageIdentityPresent() )
        {
          PackageIdentity = XerGetPackageIdentity(v6, &packageFullNameLength, a2, 0, 0);
          if ( (PackageIdentity & 0x80000000) != 0 )
            goto LABEL_26;
          if ( !*a2 )
            goto LABEL_24;
        }
        goto LABEL_25;
      }
      PackageFullName = GetPackageFullName(v6, &packageFullNameLength, a2);
      PackageIdentity = PackageFullName;
      if ( !PackageFullName )
      {
        if ( !*a2 )
LABEL_24:
          MicrosoftTelemetryAssertTriggeredNoArgs(v10);
LABEL_25:
        PackageIdentity = 0;
        goto LABEL_26;
      }
      if ( PackageFullName > 0 )
        PackageIdentity = (unsigned __int16)PackageFullName | 0x80070000;
    }
  }
LABEL_26:
  EnvironmentVariableW = GetEnvironmentVariableW(L"_HANGREP_XPROC_PKGFULLNAME", a2, 0x80u);
  if ( EnvironmentVariableW && EnvironmentVariableW < 0x80 )
    PackageIdentity = 0;
  if ( (unsigned __int64)(v6 + 1) > 1 )
    CloseHandle(v6);
  return PackageIdentity;
}

```

## disassembly

```asm
0x14001ba3c  mov     [rsp+arg_8], rbx
0x14001ba41  mov     [rsp+arg_18], rbp
0x14001ba46  mov     [rsp+packageFullNameLength], r8d
0x14001ba4b  push    rsi
0x14001ba4c  push    rdi
0x14001ba4d  push    r14
0x14001ba4f  sub     rsp, 30h
0x14001ba53  mov     rdi, rdx
0x14001ba56  mov     rsi, rcx
0x14001ba59  xor     r14d, r14d
0x14001ba5c  test    rdx, rdx
0x14001ba5f  jnz     short loc_14001BA66
0x14001ba61  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001ba66  mov     ebx, 80004005h
0x14001ba6b  mov     rbp, r14
0x14001ba6e  mov     [rsp+48h+arg_0], r14
0x14001ba73  mov     [rsp+48h+packageFullNameLength], r14d
0x14001ba78  test    dword ptr [rsi+11B0h], 1080F0h
0x14001ba82  jnz     short loc_14001BA89
0x14001ba84  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001ba89  cmp     [rsi+119Ch], r14d
0x14001ba90  jnz     short loc_14001BA97
0x14001ba92  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001ba97  test    dword ptr [rsi+11B0h], 1080F0h
0x14001baa1  jz      loc_14001BBA1
0x14001baa7  mov     r8d, [rsi+119Ch]; dwProcessId
0x14001baae  test    r8d, r8d
0x14001bab1  jz      loc_14001BBA1
0x14001bab7  xor     edx, edx; bInheritHandle
0x14001bab9  mov     ecx, 410h; dwDesiredAccess
0x14001babe  call    cs:__imp_OpenProcess
0x14001bac4  mov     rbp, rax
0x14001bac7  mov     [rsp+48h+arg_0], rax
0x14001bacc  inc     rax
0x14001bacf  cmp     rax, 1
0x14001bad3  ja      short loc_14001BB25
0x14001bad5  call    cs:__imp_GetLastError
0x14001badb  mov     ebx, eax
0x14001badd  test    eax, eax
0x14001badf  jle     short loc_14001BAEA
0x14001bae1  movzx   ebx, ax
0x14001bae4  or      ebx, 80070000h
0x14001baea  lea     rax, WPP_GLOBAL_Control
0x14001baf1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001baf8  cmp     rcx, rax
0x14001bafb  jz      loc_14001BBA1
0x14001bb01  test    byte ptr [rcx+1Ch], 1
0x14001bb05  jz      loc_14001BBA1
0x14001bb0b  mov     edx, 40h ; '@'
0x14001bb10  mov     r9d, ebx
0x14001bb13  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001bb1a  mov     rcx, [rcx+10h]
0x14001bb1e  call    WPP_SF_d
0x14001bb23  jmp     short loc_14001BBA1
0x14001bb25  mov     [rsp+48h+packageFullNameLength], 80h
0x14001bb2d  mov     [rdi], r14w
0x14001bb31  call    IsGetPackageFullNamePresent
0x14001bb36  test    al, al
0x14001bb38  jz      short loc_14001BB6B
0x14001bb3a  mov     r8, rdi; packageFullName
0x14001bb3d  lea     rdx, [rsp+48h+packageFullNameLength]; packageFullNameLength
0x14001bb42  mov     rcx, rbp; hProcess
0x14001bb45  call    cs:__imp_GetPackageFullName
0x14001bb4b  mov     ebx, eax
0x14001bb4d  test    eax, eax
0x14001bb4f  jnz     short loc_14001BB5E
0x14001bb51  cmp     [rdi], r14w
0x14001bb55  jnz     short loc_14001BB9E
0x14001bb57  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001bb5c  jmp     short loc_14001BB9E
0x14001bb5e  jle     short loc_14001BBA1
0x14001bb60  movzx   ebx, ax
0x14001bb63  or      ebx, 80070000h
0x14001bb69  jmp     short loc_14001BBA1
0x14001bb6b  call    IsXerGetPackageIdentityPresent
0x14001bb70  test    al, al
0x14001bb72  jz      short loc_14001BB9E
0x14001bb74  mov     [rsp+48h+var_28], r14
0x14001bb79  xor     r9d, r9d
0x14001bb7c  mov     r8, rdi
0x14001bb7f  lea     rdx, [rsp+48h+packageFullNameLength]
0x14001bb84  mov     rcx, rbp
0x14001bb87  call    cs:__imp_XerGetPackageIdentity
0x14001bb8d  mov     ebx, eax
0x14001bb8f  test    eax, eax
0x14001bb91  js      short loc_14001BBA1
0x14001bb93  cmp     [rdi], r14w
0x14001bb97  jnz     short loc_14001BB9E
0x14001bb99  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001bb9e  mov     ebx, r14d
0x14001bba1  mov     r8d, 80h; nSize
0x14001bba7  mov     rdx, rdi; lpBuffer
0x14001bbaa  lea     rcx, aHangrepXprocPk; "_HANGREP_XPROC_PKGFULLNAME"
0x14001bbb1  call    cs:__imp_GetEnvironmentVariableW
0x14001bbb7  test    eax, eax
0x14001bbb9  jz      short loc_14001BBC4
0x14001bbbb  cmp     eax, 80h
0x14001bbc0  cmovb   ebx, r14d
0x14001bbc4  lea     rax, [rbp+1]
0x14001bbc8  cmp     rax, 1
0x14001bbcc  jbe     short loc_14001BBD7
0x14001bbce  mov     rcx, rbp; hObject
0x14001bbd1  call    cs:__imp_CloseHandle
0x14001bbd7  mov     eax, ebx
0x14001bbd9  mov     rbx, [rsp+48h+arg_8]
0x14001bbde  mov     rbp, [rsp+48h+arg_18]
0x14001bbe3  add     rsp, 30h
0x14001bbe7  pop     r14
0x14001bbe9  pop     rdi
0x14001bbea  pop     rsi
0x14001bbeb  retn
```
