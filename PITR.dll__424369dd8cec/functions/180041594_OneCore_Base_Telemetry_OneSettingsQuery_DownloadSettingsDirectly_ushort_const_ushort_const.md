# OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsDirectly(ushort const *,ushort const *)

- ea: `0x180041594`
- end: `0x180041753`
- name: `?DownloadSettingsDirectly@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG0@Z`
- size: `447`
- prototype: `__int64 __fastcall(HINTERNET *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180044ba0`

## callees

- `0x180041594`
- `0x180041980`
- `0x180043fdc`
- `0x180044318`
- `0x180046288`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800416ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800416fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004171c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800416ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800416fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004171c`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1800416f4`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x180041724`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1800416f4`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x180041724`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800416bf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800416e2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800416bf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800416e2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004162e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004162e`
- `WINHTTP!WinHttpSetCredentials` at `0x1800416a0`
- `WINHTTP!WinHttpSetCredentials` at `0x1800416a0`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsDirectly(
        HINTERNET *this,
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
                    (OneCore::Base::Telemetry::OneSettingsQuery *)this,
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
0x180041594  mov     [rsp-8+arg_10], rbx
0x180041599  push    rbp
0x18004159a  push    rsi
0x18004159b  push    rdi
0x18004159c  push    r14
0x18004159e  push    r15
0x1800415a0  lea     rbp, [rsp-380h]
0x1800415a8  sub     rsp, 480h
0x1800415af  mov     rax, cs:__security_cookie
0x1800415b6  xor     rax, rsp
0x1800415b9  mov     [rbp+3A0h+var_30], rax
0x1800415c0  xor     eax, eax
0x1800415c2  mov     [rsp+4A0h+hToken], 0
0x1800415cb  mov     r9d, 4F7Ch; unsigned __int16
0x1800415d1  mov     [rbp+3A0h+var_240], ax
0x1800415d8  mov     [rsp+4A0h+pwszUserName], ax
0x1800415dd  mov     r15, rdx
0x1800415e0  mov     r14, rcx
0x1800415e3  mov     [rsp+4A0h+var_460], 0
0x1800415eb  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x1800415f0  test    al, al
0x1800415f2  jz      short loc_1800415FE
0x1800415f4  mov     eax, 80004005h
0x1800415f9  jmp     loc_18004172D
0x1800415fe  xor     sil, sil
0x180041601  xor     edi, edi
0x180041603  cmp     rdi, 1
0x180041607  jnz     short loc_18004163F
0x180041609  lea     r8, [rsp+4A0h+var_460]; int *
0x18004160e  lea     rdx, [rsp+4A0h+hToken]; void **
0x180041613  call    ?FindUserSession@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAPEAXPEAH@Z; OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(void * *,int *)
0x180041618  mov     ebx, eax
0x18004161a  test    eax, eax
0x18004161c  js      loc_1800416D0
0x180041622  cmp     [rsp+4A0h+var_460], 0
0x180041627  jz      short loc_18004163F
0x180041629  mov     rcx, [rsp+4A0h+hToken]; hToken
0x18004162e  call    cs:__imp_ImpersonateLoggedOnUser
0x180041634  test    eax, eax
0x180041636  jz      loc_1800416FB
0x18004163c  mov     sil, dil
0x18004163f  lea     rax, [rbp+3A0h+var_240]
0x180041646  mov     r8b, sil; bool
0x180041649  lea     r9, [rsp+4A0h+pwszUserName]; unsigned __int16 *
0x18004164e  mov     [rsp+4A0h+pAuthParams], rax; unsigned __int16 *
0x180041653  mov     rdx, r15; unsigned __int16 *
0x180041656  mov     rcx, r14; this
0x180041659  call    ?OpenWebRequest@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG_NPEAG_K23@Z; OneCore::Base::Telemetry::OneSettingsQuery::OpenWebRequest(ushort const *,bool,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x18004165e  mov     ebx, eax
0x180041660  test    eax, eax
0x180041662  js      short loc_1800416B4
0x180041664  mov     rcx, r14; this
0x180041667  call    ?RetrieveOneSettingsFromWeb@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG@Z; OneCore::Base::Telemetry::OneSettingsQuery::RetrieveOneSettingsFromWeb(ushort const *)
0x18004166c  mov     ebx, eax
0x18004166e  cmp     eax, 80070005h
0x180041673  jnz     short loc_1800416B4
0x180041675  xor     eax, eax
0x180041677  cmp     ax, [rsp+4A0h+pwszUserName]
0x18004167c  jz      short loc_1800416B4
0x18004167e  mov     rcx, [r14+10h]; hRequest
0x180041682  lea     r9, [rsp+4A0h+pwszUserName]; pwszUserName
0x180041687  mov     [rsp+4A0h+pAuthParams], rax; pAuthParams
0x18004168c  mov     edx, 1; AuthTargets
0x180041691  lea     rax, [rbp+3A0h+var_240]
0x180041698  mov     r8d, edx; AuthScheme
0x18004169b  mov     [rsp+4A0h+pwszPassword], rax; pwszPassword
0x1800416a0  call    cs:__imp_WinHttpSetCredentials
0x1800416a6  test    eax, eax
0x1800416a8  jz      short loc_1800416B4
0x1800416aa  mov     rcx, r14; this
0x1800416ad  call    ?RetrieveOneSettingsFromWeb@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG@Z; OneCore::Base::Telemetry::OneSettingsQuery::RetrieveOneSettingsFromWeb(ushort const *)
0x1800416b2  mov     ebx, eax
0x1800416b4  cmp     rdi, 1
0x1800416b8  jnz     short loc_1800416CC
0x1800416ba  test    sil, sil
0x1800416bd  jz      short loc_1800416CC
0x1800416bf  call    cs:__imp_RevertToSelf
0x1800416c5  test    eax, eax
0x1800416c7  jz      short loc_18004171C
0x1800416c9  xor     sil, sil
0x1800416cc  test    ebx, ebx
0x1800416ce  jns     short loc_1800416DD
0x1800416d0  inc     rdi
0x1800416d3  cmp     rdi, 2
0x1800416d7  jb      loc_180041603
0x1800416dd  test    sil, sil
0x1800416e0  jz      short loc_18004172B
0x1800416e2  call    cs:__imp_RevertToSelf
0x1800416e8  test    eax, eax
0x1800416ea  jnz     short loc_18004172B
0x1800416ec  call    cs:__imp_GetLastError
0x1800416f2  mov     ecx, eax; uExitCode
0x1800416f4  call    cs:__imp_ExitProcess
0x1800416fb  call    cs:__imp_GetLastError
0x180041701  mov     ebx, eax
0x180041703  test    eax, eax
0x180041705  jle     short loc_180041710
0x180041707  movzx   ebx, ax
0x18004170a  or      ebx, 80070000h
0x180041710  test    ebx, ebx
0x180041712  mov     eax, 80004005h
0x180041717  cmovns  ebx, eax
0x18004171a  jmp     short loc_1800416DD
0x18004171c  call    cs:__imp_GetLastError
0x180041722  mov     ecx, eax; uExitCode
0x180041724  call    cs:__imp_ExitProcess
0x18004172b  mov     eax, ebx
0x18004172d  mov     rcx, [rbp+3A0h+var_30]
0x180041734  xor     rcx, rsp; StackCookie
0x180041737  call    __security_check_cookie
0x18004173c  mov     rbx, [rsp+4A0h+arg_10]
0x180041744  add     rsp, 480h
0x18004174b  pop     r15
0x18004174d  pop     r14
0x18004174f  pop     rdi
0x180041750  pop     rsi
0x180041751  pop     rbp
0x180041752  retn
```
