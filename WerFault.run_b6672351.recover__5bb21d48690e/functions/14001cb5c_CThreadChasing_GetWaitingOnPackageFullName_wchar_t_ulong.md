# CThreadChasing::GetWaitingOnPackageFullName(wchar_t *,ulong)

- ea: `0x14001cb5c`
- end: `0x14001cd34`
- name: `?GetWaitingOnPackageFullName@CThreadChasing@@QEAAJPEA_WK@Z`
- size: `472`
- prototype: `int(CThreadChasing *__hidden this, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14002b5d8`

## callees

- `0x14000353c`
- `0x140003bb8`
- `0x140014f14`
- `0x1400166ec`
- `0x14001cb5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001cbfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001cbfb`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001ccec`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001ccec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001cd12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001cd12`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001cbde`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001cbde`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x14001cc74`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x14001cc74`
- `ext-ms-win-wer-xbox-l1-1-2!XerGetPackageIdentity` at `0x14001ccbc`
- `ext-ms-win-wer-xbox-l1-1-2!XerGetPackageIdentity` at `0x14001ccbc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThreadChasing::GetWaitingOnPackageFullName(DWORD *this, wchar_t *a2, __int64 a3, __int64 a4)
{
  unsigned int PackageIdentity; // ebx
  char *v7; // rbp
  DWORD v8; // r8d
  __int64 v9; // rcx
  signed int LastError; // eax
  __int64 v11; // rcx
  LONG PackageFullName; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  DWORD EnvironmentVariableW; // eax
  UINT32 packageFullNameLength; // [rsp+60h] [rbp+18h] BYREF

  packageFullNameLength = a3;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, 0, a3, a4);
  PackageIdentity = -2147467259;
  v7 = 0;
  packageFullNameLength = 0;
  if ( (this[1132] & 0x1080F0) == 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  if ( !this[1127] )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  if ( (this[1132] & 0x1080F0) != 0 )
  {
    v8 = this[1127];
    if ( v8 )
    {
      v7 = (char *)OpenProcess(0x410u, 0, v8);
      if ( v7 == (char *)-1LL || v7 + 1 == (char *)1 )
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
      if ( !(unsigned __int8)IsGetPackageFullNamePresent(v9) )
      {
        if ( (unsigned __int8)IsXerGetPackageIdentityPresent(v11) )
        {
          PackageIdentity = XerGetPackageIdentity(v7, &packageFullNameLength, a2, 0, 0);
          if ( (PackageIdentity & 0x80000000) != 0 )
            goto LABEL_26;
          if ( !*a2 )
            goto LABEL_24;
        }
        goto LABEL_25;
      }
      PackageFullName = GetPackageFullName(v7, &packageFullNameLength, a2);
      PackageIdentity = PackageFullName;
      if ( !PackageFullName )
      {
        if ( !*a2 )
LABEL_24:
          MicrosoftTelemetryAssertTriggeredNoArgs(v14, v13, v15, v16);
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
  if ( (unsigned __int64)(v7 + 1) > 1 )
    CloseHandle(v7);
  return PackageIdentity;
}

```

## disassembly

```asm
0x14001cb5c  mov     [rsp+arg_8], rbx
0x14001cb61  mov     [rsp+arg_18], rbp
0x14001cb66  mov     [rsp+packageFullNameLength], r8d
0x14001cb6b  push    rsi
0x14001cb6c  push    rdi
0x14001cb6d  push    r14
0x14001cb6f  sub     rsp, 30h
0x14001cb73  mov     rdi, rdx
0x14001cb76  mov     rsi, rcx
0x14001cb79  xor     r14d, r14d
0x14001cb7c  test    rdx, rdx
0x14001cb7f  jnz     short loc_14001CB86
0x14001cb81  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001cb86  mov     ebx, 80004005h
0x14001cb8b  mov     rbp, r14
0x14001cb8e  mov     [rsp+48h+arg_0], r14
0x14001cb93  mov     [rsp+48h+packageFullNameLength], r14d
0x14001cb98  test    dword ptr [rsi+11B0h], 1080F0h
0x14001cba2  jnz     short loc_14001CBA9
0x14001cba4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001cba9  cmp     [rsi+119Ch], r14d
0x14001cbb0  jnz     short loc_14001CBB7
0x14001cbb2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001cbb7  test    dword ptr [rsi+11B0h], 1080F0h
0x14001cbc1  jz      loc_14001CCDC
0x14001cbc7  mov     r8d, [rsi+119Ch]; dwProcessId
0x14001cbce  test    r8d, r8d
0x14001cbd1  jz      loc_14001CCDC
0x14001cbd7  xor     edx, edx; bInheritHandle
0x14001cbd9  mov     ecx, 410h; dwDesiredAccess
0x14001cbde  call    cs:__imp_OpenProcess
0x14001cbe5  nop     dword ptr [rax+rax+00h]
0x14001cbea  mov     rbp, rax
0x14001cbed  mov     [rsp+48h+arg_0], rax
0x14001cbf2  inc     rax
0x14001cbf5  cmp     rax, 1
0x14001cbf9  ja      short loc_14001CC54
0x14001cbfb  call    cs:__imp_GetLastError
0x14001cc02  nop     dword ptr [rax+rax+00h]
0x14001cc07  mov     ebx, eax
0x14001cc09  test    eax, eax
0x14001cc0b  jle     short loc_14001CC16
0x14001cc0d  movzx   ebx, ax
0x14001cc10  or      ebx, 80070000h
0x14001cc16  lea     rax, WPP_GLOBAL_Control
0x14001cc1d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cc24  cmp     rcx, rax
0x14001cc27  jz      loc_14001CCDC
0x14001cc2d  test    byte ptr [rcx+1Ch], 1
0x14001cc31  jz      loc_14001CCDC
0x14001cc37  mov     edx, 40h ; '@'
0x14001cc3c  mov     r9d, ebx
0x14001cc3f  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001cc46  mov     rcx, [rcx+10h]
0x14001cc4a  call    WPP_SF_d
0x14001cc4f  jmp     loc_14001CCDC
0x14001cc54  mov     [rsp+48h+packageFullNameLength], 80h
0x14001cc5c  mov     [rdi], r14w
0x14001cc60  call    IsGetPackageFullNamePresent
0x14001cc65  test    al, al
0x14001cc67  jz      short loc_14001CCA0
0x14001cc69  mov     r8, rdi; packageFullName
0x14001cc6c  lea     rdx, [rsp+48h+packageFullNameLength]; packageFullNameLength
0x14001cc71  mov     rcx, rbp; hProcess
0x14001cc74  call    cs:__imp_GetPackageFullName
0x14001cc7b  nop     dword ptr [rax+rax+00h]
0x14001cc80  mov     ebx, eax
0x14001cc82  test    eax, eax
0x14001cc84  jnz     short loc_14001CC93
0x14001cc86  cmp     [rdi], r14w
0x14001cc8a  jnz     short loc_14001CCD9
0x14001cc8c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001cc91  jmp     short loc_14001CCD9
0x14001cc93  jle     short loc_14001CCDC
0x14001cc95  movzx   ebx, ax
0x14001cc98  or      ebx, 80070000h
0x14001cc9e  jmp     short loc_14001CCDC
0x14001cca0  call    IsXerGetPackageIdentityPresent
0x14001cca5  test    al, al
0x14001cca7  jz      short loc_14001CCD9
0x14001cca9  mov     [rsp+48h+var_28], r14
0x14001ccae  xor     r9d, r9d
0x14001ccb1  mov     r8, rdi
0x14001ccb4  lea     rdx, [rsp+48h+packageFullNameLength]
0x14001ccb9  mov     rcx, rbp
0x14001ccbc  call    cs:__imp_XerGetPackageIdentity
0x14001ccc3  nop     dword ptr [rax+rax+00h]
0x14001ccc8  mov     ebx, eax
0x14001ccca  test    eax, eax
0x14001cccc  js      short loc_14001CCDC
0x14001ccce  cmp     [rdi], r14w
0x14001ccd2  jnz     short loc_14001CCD9
0x14001ccd4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001ccd9  mov     ebx, r14d
0x14001ccdc  mov     r8d, 80h; nSize
0x14001cce2  mov     rdx, rdi; lpBuffer
0x14001cce5  lea     rcx, aHangrepXprocPk; "_HANGREP_XPROC_PKGFULLNAME"
0x14001ccec  call    cs:__imp_GetEnvironmentVariableW
0x14001ccf3  nop     dword ptr [rax+rax+00h]
0x14001ccf8  test    eax, eax
0x14001ccfa  jz      short loc_14001CD05
0x14001ccfc  cmp     eax, 80h
0x14001cd01  cmovb   ebx, r14d
0x14001cd05  lea     rax, [rbp+1]
0x14001cd09  cmp     rax, 1
0x14001cd0d  jbe     short loc_14001CD1E
0x14001cd0f  mov     rcx, rbp; hObject
0x14001cd12  call    cs:__imp_CloseHandle
0x14001cd19  nop     dword ptr [rax+rax+00h]
0x14001cd1e  mov     eax, ebx
0x14001cd20  mov     rbx, [rsp+48h+arg_8]
0x14001cd25  mov     rbp, [rsp+48h+arg_18]
0x14001cd2a  add     rsp, 30h
0x14001cd2e  pop     r14
0x14001cd30  pop     rdi
0x14001cd31  pop     rsi
0x14001cd32  retn
```
