# OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsDirectly(ushort const *,ushort const *)

- ea: `0x18001acb4`
- end: `0x18001ae73`
- name: `?DownloadSettingsDirectly@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG0@Z`
- size: `447`
- prototype: `__int64 __fastcall(void **this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001f3f4`

## callees

- `0x18001acb4`
- `0x18001b524`
- `0x18001e200`
- `0x18001eac8`
- `0x180021ca8`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x18001ae14`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x18001ae44`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x18001ae14`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x18001ae44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae3c`
- `WINHTTP!WinHttpSetCredentials` at `0x18001adc0`
- `WINHTTP!WinHttpSetCredentials` at `0x18001adc0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001ad4e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001ad4e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001addf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001ae02`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001addf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001ae02`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsDirectly(
        void **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  OneCore::Base::Telemetry::OneSettingsQuery *v5; // rcx
  bool v7; // si
  __int64 v8; // rdi
  signed int UserSession; // ebx
  const unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // rdx
  UINT v12; // eax
  signed int v13; // eax
  UINT LastError; // eax
  LPCWSTR pwszPassword; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v16; // [rsp+30h] [rbp-D0h]
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hToken; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pwszUserName[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR v20[264]; // [rsp+260h] [rbp+160h] BYREF

  hToken = 0;
  v20[0] = 0;
  pwszUserName[0] = 0;
  v17 = 0;
  if ( IsWindowsVersionOrGreaterEx((unsigned __int16)this, (unsigned __int16)a2, (unsigned __int16)a3, 0x4F7Cu) )
    return 2147500037LL;
  v7 = 0;
  v8 = 0;
  while ( 1 )
  {
    if ( v8 == 1 )
    {
      UserSession = OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(v5, &hToken, &v17);
      if ( UserSession < 0 )
        goto LABEL_19;
      if ( v17 )
        break;
    }
LABEL_9:
    UserSession = OneCore::Base::Telemetry::OneSettingsQuery::OpenWebRequest(
                    this,
                    a2,
                    v7,
                    pwszUserName,
                    (unsigned __int64)pwszPassword,
                    v20,
                    v16);
    if ( UserSession >= 0 )
    {
      UserSession = OneCore::Base::Telemetry::OneSettingsQuery::RetrieveOneSettingsFromWeb(
                      (OneCore::Base::Telemetry::OneSettingsQuery *)this,
                      v10);
      if ( UserSession == -2147024891 && pwszUserName[0] && WinHttpSetCredentials(this[2], 1u, 1u, pwszUserName, v20, 0) )
        UserSession = OneCore::Base::Telemetry::OneSettingsQuery::RetrieveOneSettingsFromWeb(
                        (OneCore::Base::Telemetry::OneSettingsQuery *)this,
                        v11);
    }
    if ( v8 == 1 && v7 )
    {
      if ( !RevertToSelf() )
      {
        LastError = GetLastError();
        ExitProcess(LastError);
      }
      v7 = 0;
    }
    if ( UserSession >= 0 )
      goto LABEL_20;
LABEL_19:
    if ( (unsigned __int64)++v8 >= 2 )
      goto LABEL_20;
  }
  if ( ImpersonateLoggedOnUser(hToken) )
  {
    v7 = 1;
    goto LABEL_9;
  }
  v13 = GetLastError();
  UserSession = v13;
  if ( v13 > 0 )
    UserSession = (unsigned __int16)v13 | 0x80070000;
  if ( UserSession >= 0 )
    UserSession = -2147467259;
LABEL_20:
  if ( v7 && !RevertToSelf() )
  {
    v12 = GetLastError();
    ExitProcess(v12);
  }
  return (unsigned int)UserSession;
}

```

## disassembly

```asm
0x18001acb4  mov     [rsp-8+arg_10], rbx
0x18001acb9  push    rbp
0x18001acba  push    rsi
0x18001acbb  push    rdi
0x18001acbc  push    r14
0x18001acbe  push    r15
0x18001acc0  lea     rbp, [rsp-380h]
0x18001acc8  sub     rsp, 480h
0x18001accf  mov     rax, cs:__security_cookie
0x18001acd6  xor     rax, rsp
0x18001acd9  mov     [rbp+3A0h+var_30], rax
0x18001ace0  xor     eax, eax
0x18001ace2  mov     [rsp+4A0h+hToken], 0
0x18001aceb  mov     r9d, 4F7Ch; unsigned __int16
0x18001acf1  mov     [rbp+3A0h+var_240], ax
0x18001acf8  mov     [rsp+4A0h+pwszUserName], ax
0x18001acfd  mov     r15, rdx
0x18001ad00  mov     r14, rcx
0x18001ad03  mov     [rsp+4A0h+var_460], 0
0x18001ad0b  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x18001ad10  test    al, al
0x18001ad12  jz      short loc_18001AD1E
0x18001ad14  mov     eax, 80004005h
0x18001ad19  jmp     loc_18001AE4D
0x18001ad1e  xor     sil, sil
0x18001ad21  xor     edi, edi
0x18001ad23  cmp     rdi, 1
0x18001ad27  jnz     short loc_18001AD5F
0x18001ad29  lea     r8, [rsp+4A0h+var_460]; int *
0x18001ad2e  lea     rdx, [rsp+4A0h+hToken]; void **
0x18001ad33  call    ?FindUserSession@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAPEAXPEAH@Z; OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(void * *,int *)
0x18001ad38  mov     ebx, eax
0x18001ad3a  test    eax, eax
0x18001ad3c  js      loc_18001ADF0
0x18001ad42  cmp     [rsp+4A0h+var_460], 0
0x18001ad47  jz      short loc_18001AD5F
0x18001ad49  mov     rcx, [rsp+4A0h+hToken]; hToken
0x18001ad4e  call    cs:__imp_ImpersonateLoggedOnUser
0x18001ad54  test    eax, eax
0x18001ad56  jz      loc_18001AE1B
0x18001ad5c  mov     sil, dil
0x18001ad5f  lea     rax, [rbp+3A0h+var_240]
0x18001ad66  mov     r8b, sil; bool
0x18001ad69  lea     r9, [rsp+4A0h+pwszUserName]; unsigned __int16 *
0x18001ad6e  mov     [rsp+4A0h+pAuthParams], rax; unsigned __int16 *
0x18001ad73  mov     rdx, r15; unsigned __int16 *
0x18001ad76  mov     rcx, r14; this
0x18001ad79  call    ?OpenWebRequest@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG_NPEAG_K23@Z; OneCore::Base::Telemetry::OneSettingsQuery::OpenWebRequest(ushort const *,bool,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x18001ad7e  mov     ebx, eax
0x18001ad80  test    eax, eax
0x18001ad82  js      short loc_18001ADD4
0x18001ad84  mov     rcx, r14; this
0x18001ad87  call    ?RetrieveOneSettingsFromWeb@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG@Z; OneCore::Base::Telemetry::OneSettingsQuery::RetrieveOneSettingsFromWeb(ushort const *)
0x18001ad8c  mov     ebx, eax
0x18001ad8e  cmp     eax, 80070005h
0x18001ad93  jnz     short loc_18001ADD4
0x18001ad95  xor     eax, eax
0x18001ad97  cmp     ax, [rsp+4A0h+pwszUserName]
0x18001ad9c  jz      short loc_18001ADD4
0x18001ad9e  mov     rcx, [r14+10h]; hRequest
0x18001ada2  lea     r9, [rsp+4A0h+pwszUserName]; pwszUserName
0x18001ada7  mov     [rsp+4A0h+pAuthParams], rax; pAuthParams
0x18001adac  mov     edx, 1; AuthTargets
0x18001adb1  lea     rax, [rbp+3A0h+var_240]
0x18001adb8  mov     r8d, edx; AuthScheme
0x18001adbb  mov     [rsp+4A0h+pwszPassword], rax; pwszPassword
0x18001adc0  call    cs:__imp_WinHttpSetCredentials
0x18001adc6  test    eax, eax
0x18001adc8  jz      short loc_18001ADD4
0x18001adca  mov     rcx, r14; this
0x18001adcd  call    ?RetrieveOneSettingsFromWeb@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG@Z; OneCore::Base::Telemetry::OneSettingsQuery::RetrieveOneSettingsFromWeb(ushort const *)
0x18001add2  mov     ebx, eax
0x18001add4  cmp     rdi, 1
0x18001add8  jnz     short loc_18001ADEC
0x18001adda  test    sil, sil
0x18001addd  jz      short loc_18001ADEC
0x18001addf  call    cs:__imp_RevertToSelf
0x18001ade5  test    eax, eax
0x18001ade7  jz      short loc_18001AE3C
0x18001ade9  xor     sil, sil
0x18001adec  test    ebx, ebx
0x18001adee  jns     short loc_18001ADFD
0x18001adf0  inc     rdi
0x18001adf3  cmp     rdi, 2
0x18001adf7  jb      loc_18001AD23
0x18001adfd  test    sil, sil
0x18001ae00  jz      short loc_18001AE4B
0x18001ae02  call    cs:__imp_RevertToSelf
0x18001ae08  test    eax, eax
0x18001ae0a  jnz     short loc_18001AE4B
0x18001ae0c  call    cs:__imp_GetLastError
0x18001ae12  mov     ecx, eax; uExitCode
0x18001ae14  call    cs:__imp_ExitProcess
0x18001ae1b  call    cs:__imp_GetLastError
0x18001ae21  mov     ebx, eax
0x18001ae23  test    eax, eax
0x18001ae25  jle     short loc_18001AE30
0x18001ae27  movzx   ebx, ax
0x18001ae2a  or      ebx, 80070000h
0x18001ae30  test    ebx, ebx
0x18001ae32  mov     eax, 80004005h
0x18001ae37  cmovns  ebx, eax
0x18001ae3a  jmp     short loc_18001ADFD
0x18001ae3c  call    cs:__imp_GetLastError
0x18001ae42  mov     ecx, eax; uExitCode
0x18001ae44  call    cs:__imp_ExitProcess
0x18001ae4b  mov     eax, ebx
0x18001ae4d  mov     rcx, [rbp+3A0h+var_30]
0x18001ae54  xor     rcx, rsp; StackCookie
0x18001ae57  call    __security_check_cookie
0x18001ae5c  mov     rbx, [rsp+4A0h+arg_10]
0x18001ae64  add     rsp, 480h
0x18001ae6b  pop     r15
0x18001ae6d  pop     r14
0x18001ae6f  pop     rdi
0x18001ae70  pop     rsi
0x18001ae71  pop     rbp
0x18001ae72  retn
```
