# ShieldProvider::ShieldProcessLauncher::LaunchCommand(ushort const *,ushort const *,ulong)

- ea: `0x18007d0b8`
- end: `0x18007d636`
- name: `?LaunchCommand@ShieldProcessLauncher@ShieldProvider@@AEAAJPEBG0K@Z`
- size: `1406`
- prototype: `__int64 __fastcall(ShieldProvider::ShieldProcessLauncher *this, void **, const unsigned __int16 *, void *)`
- caller_count: `9`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007cd60`
- `0x18007cf50`
- `0x18007d640`
- `0x18007d740`
- `0x18007d8a0`
- `0x18007da90`
- `0x18007dbf0`
- `0x18007de90`
- `0x18007e4b0`

## callees

- `0x180004710`
- `0x18000517c`
- `0x18000af6c`
- `0x18000ccb0`
- `0x18000d7fc`
- `0x18007c000`
- `0x18007d0b8`
- `0x1800ceb24`
- `0x1800ceb60`
- `0x1800da4ac`
- `0x1800df118`
- `0x1800e1008`
- `0x1800e16e4`
- `0x1800e7010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007d20b`
- `KERNEL32!GetLastError` at `0x18007d428`
- `KERNEL32!GetLastError` at `0x18007d591`
- `KERNEL32!GetLastError` at `0x18007d20b`
- `KERNEL32!GetLastError` at `0x18007d428`
- `KERNEL32!GetLastError` at `0x18007d591`
- `KERNEL32!CloseHandle` at `0x18007d264`
- `KERNEL32!CloseHandle` at `0x18007d328`
- `KERNEL32!CloseHandle` at `0x18007d480`
- `KERNEL32!CloseHandle` at `0x18007d5f2`
- `KERNEL32!CloseHandle` at `0x18007d603`
- `KERNEL32!CloseHandle` at `0x18007d264`
- `KERNEL32!CloseHandle` at `0x18007d328`
- `KERNEL32!CloseHandle` at `0x18007d480`
- `KERNEL32!CloseHandle` at `0x18007d5f2`
- `KERNEL32!CloseHandle` at `0x18007d603`
- `KERNEL32!GetCurrentThread` at `0x18007d1eb`
- `KERNEL32!GetCurrentThread` at `0x18007d1eb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007d201`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007d201`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18007d587`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18007d587`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18007d41e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18007d41e`

## string_xrefs

- `0x18007d494`: `SeAssignPrimaryTokenPrivilege`
- `0x18007d4cb`: `SeIncreaseQuotaPrivilege`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ShieldProcessLauncher::LaunchCommand(
        ShieldProvider::ShieldProcessLauncher *this,
        void **a2,
        const unsigned __int16 *a3,
        void *a4)
{
  char v4; // di
  int v7; // esi
  signed int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  ShieldProvider *v12; // rcx
  BOOL IsOSWcos; // ebx
  HANDLE CurrentThread; // rax
  void *v15; // r8
  unsigned int v16; // r9d
  signed int LastError; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  ShieldProvider *v20; // rcx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  ShieldProvider::ShieldProcessLauncher *v25; // rcx
  signed int v26; // eax
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  ShieldProvider::ShieldProcessLauncher *v29; // rcx
  void *v30; // rdx
  signed int v31; // eax
  void *v32; // rdx
  unsigned int TokenType; // [rsp+20h] [rbp-E0h]
  unsigned int TokenTypea; // [rsp+20h] [rbp-E0h]
  struct IUnknown *phNewToken; // [rsp+28h] [rbp-D8h]
  _BYTE v36[8]; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+78h] [rbp-88h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  WCHAR CommandLine[520]; // [rsp+100h] [rbp+0h] BYREF

  v4 = (char)a4;
  v7 = (unsigned __int8)a4 & 4;
  if ( ((unsigned __int8)a4 & 4) != 0 && ((unsigned __int8)a4 & 1) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids, 2147942405LL);
    return 2147942405LL;
  }
  if ( ((unsigned __int8)a4 & 8) != 0 )
  {
    v8 = CommonUtil::MpUtilMicrosoftCertCheck(a2, (const unsigned __int16 *)4, (unsigned int)a3, a4);
    if ( v8 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)v8;
      v10 = 13;
LABEL_11:
      WPP_SF_d(v9[2], v10, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids, (unsigned int)v8);
      return (unsigned int)v8;
    }
  }
  v8 = StringCchPrintfW(CommandLine, 0x208u, L"\"%s\" %s", a2, a3);
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)v8;
    v10 = 14;
    goto LABEL_11;
  }
  TokenHandle = 0;
  IsOSWcos = ShieldProvider::IsOSWcos(v12);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xAu, IsOSWcos, &TokenHandle) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v19 = 15;
LABEL_24:
        WPP_SF_d(v18[2], v19, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids, (unsigned int)v8);
        goto LABEL_25;
      }
      goto LABEL_25;
    }
  }
  v36[0] = 0;
  v8 = CommonUtil::UtilCheckTokenMembershipByRid((CommonUtil *)v36, (bool *)TokenHandle, v15, v16, TokenType);
  if ( v8 < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v19 = 16;
      goto LABEL_24;
    }
LABEL_25:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return (unsigned int)v8;
  }
  if ( (v4 & 1) != 0 && !v36[0] )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v22 = 17;
LABEL_42:
      WPP_SF_d(v21[2], v22, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids, 2147942405LL);
      goto LABEL_43;
    }
    goto LABEL_43;
  }
  if ( (v4 & 2) != 0 && v36[0] && !ShieldProvider::IsOSWcosGuest(v20) )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v22 = 18;
      goto LABEL_42;
    }
LABEL_43:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return 2147942405LL;
  }
  hObject = 0;
  if ( (v4 & 0x10) == 0 )
  {
    if ( !DuplicateTokenEx(TokenHandle, 0xABu, 0, SecurityImpersonation, TokenPrimary, &hObject) )
    {
      v26 = GetLastError();
      v8 = v26;
      if ( v26 > 0 )
        v8 = (unsigned __int16)v26 | 0x80070000;
      if ( v8 < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v28 = 21;
LABEL_65:
          WPP_SF_d(v27[2], v28, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids, (unsigned int)v8);
          goto LABEL_66;
        }
        goto LABEL_66;
      }
    }
    if ( v7 )
    {
      v8 = ShieldProvider::ShieldProcessLauncher::EnableSinglePrivilege(v25, L"SeAssignPrimaryTokenPrivilege", hObject);
      if ( v8 < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v28 = 22;
          goto LABEL_65;
        }
LABEL_66:
        if ( hObject )
          CloseHandle(hObject);
        goto LABEL_25;
      }
      v8 = ShieldProvider::ShieldProcessLauncher::EnableSinglePrivilege(v29, L"SeIncreaseQuotaPrivilege", hObject);
      if ( v8 < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v28 = 23;
          goto LABEL_65;
        }
        goto LABEL_66;
      }
    }
    *(_QWORD *)&ProcessInformation.dwProcessId = 0;
    *(__m128i *)&ProcessInformation.hProcess = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    memset_0(&StartupInfo, 0, sizeof(StartupInfo));
    StartupInfo.cb = 104;
    StartupInfo.lpDesktop = L"winsta0\\default";
    if ( CreateProcessAsUserW(hObject, 0, CommandLine, 0, 0, 0, 0x20u, 0, 0, &StartupInfo, &ProcessInformation) )
      goto LABEL_84;
    v31 = GetLastError();
    v8 = v31;
    if ( v31 > 0 )
      v8 = (unsigned __int16)v31 | 0x80070000;
    if ( v8 >= 0 )
    {
LABEL_84:
      CommonUtil::UtilCloseHandle((CommonUtil *)ProcessInformation.hProcess, v30);
      CommonUtil::UtilCloseHandle((CommonUtil *)ProcessInformation.hThread, v32);
      if ( hObject )
        CloseHandle(hObject);
      goto LABEL_86;
    }
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v28 = 24;
      goto LABEL_65;
    }
    goto LABEL_66;
  }
  v8 = CommonUtil::UtilCoCreateInstanceImpl(
         &hObject,
         &CLSID_ShieldProviderUserSessionAgent,
         &GUID_63436228_bafc_4acd_a2ae_75e4f5108ab1,
         4u,
         TokenTypea,
         phNewToken);
  if ( v8 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_52;
    v24 = 19;
LABEL_51:
    WPP_SF_d(v23[2], v24, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids, (unsigned int)v8);
LABEL_52:
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&hObject);
    goto LABEL_25;
  }
  v8 = (*(__int64 (__fastcall **)(HANDLE, void **, const unsigned __int16 *))(*(_QWORD *)hObject + 56LL))(
         hObject,
         a2,
         a3);
  if ( v8 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_52;
    v24 = 20;
    goto LABEL_51;
  }
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&hObject);
LABEL_86:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x18007d0b8  mov     [rsp-8+arg_0], rbx
0x18007d0bd  mov     [rsp-8+arg_18], rsi
0x18007d0c2  push    rbp
0x18007d0c3  push    rdi
0x18007d0c4  push    r13
0x18007d0c6  push    r14
0x18007d0c8  push    r15
0x18007d0ca  lea     rbp, [rsp-420h]
0x18007d0d2  sub     rsp, 520h
0x18007d0d9  mov     rax, cs:__security_cookie
0x18007d0e0  xor     rax, rsp
0x18007d0e3  mov     [rbp+440h+var_30], rax
0x18007d0ea  mov     edi, r9d
0x18007d0ed  mov     r15, r8
0x18007d0f0  mov     r14, rdx
0x18007d0f3  mov     esi, r9d
0x18007d0f6  mov     r13d, 1
0x18007d0fc  and     esi, 4
0x18007d0ff  jz      short loc_18007D146
0x18007d101  test    r13b, dil
0x18007d104  jnz     short loc_18007D146
0x18007d106  lea     rax, WPP_GLOBAL_Control
0x18007d10d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d114  cmp     rcx, rax
0x18007d117  jz      loc_18007D32E
0x18007d11d  test    [rcx+1Ch], r13b
0x18007d121  jz      loc_18007D32E
0x18007d127  lea     edx, [r13+0Bh]
0x18007d12b  mov     r9d, 80070005h
0x18007d131  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007d138  mov     rcx, [rcx+10h]
0x18007d13c  call    WPP_SF_d
0x18007d141  jmp     loc_18007D32E
0x18007d146  test    dil, 8
0x18007d14a  jz      short loc_18007D197
0x18007d14c  mov     edx, 4; unsigned __int16 *
0x18007d151  mov     rcx, r14; this
0x18007d154  call    ?MpUtilMicrosoftCertCheck@CommonUtil@@YAJPEBGKPEAX@Z; CommonUtil::MpUtilMicrosoftCertCheck(ushort const *,ulong,void *)
0x18007d159  mov     ebx, eax
0x18007d15b  test    eax, eax
0x18007d15d  jns     short loc_18007D197
0x18007d15f  lea     rax, WPP_GLOBAL_Control
0x18007d166  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d16d  cmp     rcx, rax
0x18007d170  jz      short loc_18007D190
0x18007d172  test    [rcx+1Ch], r13b
0x18007d176  jz      short loc_18007D190
0x18007d178  mov     edx, 0Dh
0x18007d17d  mov     r9d, ebx
0x18007d180  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007d187  mov     rcx, [rcx+10h]
0x18007d18b  call    WPP_SF_d
0x18007d190  mov     eax, ebx
0x18007d192  jmp     loc_18007D60B
0x18007d197  mov     qword ptr [rsp+540h+TokenType], r15; unsigned int
0x18007d19c  mov     r9, r14
0x18007d19f  lea     r8, aSS_0; "\"%s\" %s"
0x18007d1a6  mov     edx, 208h; unsigned __int64
0x18007d1ab  lea     rcx, [rbp+440h+CommandLine]; unsigned __int16 *
0x18007d1af  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007d1b4  mov     ebx, eax
0x18007d1b6  test    eax, eax
0x18007d1b8  jns     short loc_18007D1DA
0x18007d1ba  lea     rax, WPP_GLOBAL_Control
0x18007d1c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d1c8  cmp     rcx, rax
0x18007d1cb  jz      short loc_18007D190
0x18007d1cd  test    [rcx+1Ch], r13b
0x18007d1d1  jz      short loc_18007D190
0x18007d1d3  mov     edx, 0Eh
0x18007d1d8  jmp     short loc_18007D17D
0x18007d1da  mov     [rsp+540h+TokenHandle], 0
0x18007d1e3  call    ?IsOSWcos@ShieldProvider@@YA_NXZ; ShieldProvider::IsOSWcos(void)
0x18007d1e8  movzx   ebx, al
0x18007d1eb  call    cs:__imp_GetCurrentThread
0x18007d1f1  lea     r9, [rsp+540h+TokenHandle]; TokenHandle
0x18007d1f6  mov     r8d, ebx; OpenAsSelf
0x18007d1f9  mov     edx, 0Ah; DesiredAccess
0x18007d1fe  mov     rcx, rax; ThreadHandle
0x18007d201  call    cs:__imp_OpenThreadToken
0x18007d207  test    eax, eax
0x18007d209  jnz     short loc_18007D26F
0x18007d20b  call    cs:__imp_GetLastError
0x18007d211  mov     ebx, eax
0x18007d213  test    eax, eax
0x18007d215  jle     short loc_18007D220
0x18007d217  movzx   ebx, ax
0x18007d21a  or      ebx, 80070000h
0x18007d220  test    ebx, ebx
0x18007d222  jns     short loc_18007D26F
0x18007d224  lea     rax, WPP_GLOBAL_Control
0x18007d22b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d232  cmp     rcx, rax
0x18007d235  jz      short loc_18007D256
0x18007d237  test    [rcx+1Ch], r13b
0x18007d23b  jz      short loc_18007D256
0x18007d23d  mov     edx, 0Fh
0x18007d242  mov     r9d, ebx
0x18007d245  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007d24c  mov     rcx, [rcx+10h]
0x18007d250  call    WPP_SF_d
0x18007d255  nop
0x18007d256  mov     rcx, [rsp+540h+TokenHandle]; hObject
0x18007d25b  test    rcx, rcx
0x18007d25e  jz      loc_18007D190
0x18007d264  call    cs:__imp_CloseHandle
0x18007d26a  jmp     loc_18007D190
0x18007d26f  mov     [rsp+540h+var_4E0], 0
0x18007d274  mov     rdx, [rsp+540h+TokenHandle]; bool *
0x18007d279  lea     rcx, [rsp+540h+var_4E0]; this
0x18007d27e  call    ?UtilCheckTokenMembershipByRid@CommonUtil@@YAJPEA_NPEAXKK@Z; CommonUtil::UtilCheckTokenMembershipByRid(bool *,void *,ulong,ulong)
0x18007d283  mov     ebx, eax
0x18007d285  test    eax, eax
0x18007d287  jns     short loc_18007D2A9
0x18007d289  lea     rax, WPP_GLOBAL_Control
0x18007d290  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d297  cmp     rcx, rax
0x18007d29a  jz      short loc_18007D256
0x18007d29c  test    [rcx+1Ch], r13b
0x18007d2a0  jz      short loc_18007D256
0x18007d2a2  mov     edx, 10h
0x18007d2a7  jmp     short loc_18007D242
0x18007d2a9  mov     al, [rsp+540h+var_4E0]
0x18007d2ad  test    r13b, dil
0x18007d2b0  jz      short loc_18007D2D6
0x18007d2b2  test    al, al
0x18007d2b4  jnz     short loc_18007D2D6
0x18007d2b6  lea     rax, WPP_GLOBAL_Control
0x18007d2bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d2c4  cmp     rcx, rax
0x18007d2c7  jz      short loc_18007D31E
0x18007d2c9  test    [rcx+1Ch], r13b
0x18007d2cd  jz      short loc_18007D31E
0x18007d2cf  mov     edx, 11h
0x18007d2d4  jmp     short loc_18007D307
0x18007d2d6  test    dil, 2
0x18007d2da  jz      short loc_18007D338
0x18007d2dc  test    al, al
0x18007d2de  jz      short loc_18007D338
0x18007d2e0  call    ?IsOSWcosGuest@ShieldProvider@@YA_NXZ; ShieldProvider::IsOSWcosGuest(void)
0x18007d2e5  test    al, al
0x18007d2e7  jnz     short loc_18007D338
0x18007d2e9  lea     rax, WPP_GLOBAL_Control
0x18007d2f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d2f7  cmp     rcx, rax
0x18007d2fa  jz      short loc_18007D31E
0x18007d2fc  test    [rcx+1Ch], r13b
0x18007d300  jz      short loc_18007D31E
0x18007d302  mov     edx, 12h
0x18007d307  mov     r9d, 80070005h
0x18007d30d  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007d314  mov     rcx, [rcx+10h]
0x18007d318  call    WPP_SF_d
0x18007d31d  nop
0x18007d31e  mov     rcx, [rsp+540h+TokenHandle]; hObject
0x18007d323  test    rcx, rcx
0x18007d326  jz      short loc_18007D32E
0x18007d328  call    cs:__imp_CloseHandle
0x18007d32e  mov     eax, 80070005h
0x18007d333  jmp     loc_18007D60B
0x18007d338  mov     [rsp+540h+hObject], 0
0x18007d341  test    dil, 10h
0x18007d345  jz      loc_18007D3FC
0x18007d34b  mov     r9d, 4; dwClsContext
0x18007d351  lea     r8, _GUID_63436228_bafc_4acd_a2ae_75e4f5108ab1; riid
0x18007d358  lea     rdx, CLSID_ShieldProviderUserSessionAgent; rclsid
0x18007d35f  lea     rcx, [rsp+540h+hObject]; ppv
0x18007d364  call    ?UtilCoCreateInstanceImpl@CommonUtil@@YAJPEAPEAXAEBU_GUID@@1KPEAUIUnknown@@@Z; CommonUtil::UtilCoCreateInstanceImpl(void * *,_GUID const &,_GUID const &,ulong,IUnknown *)
0x18007d369  mov     ebx, eax
0x18007d36b  test    eax, eax
0x18007d36d  jns     short loc_18007D3B0
0x18007d36f  lea     rax, WPP_GLOBAL_Control
0x18007d376  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d37d  cmp     rcx, rax
0x18007d380  jz      short loc_18007D3A1
0x18007d382  test    [rcx+1Ch], r13b
0x18007d386  jz      short loc_18007D3A1
0x18007d388  mov     edx, 13h
0x18007d38d  mov     r9d, ebx
0x18007d390  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007d397  mov     rcx, [rcx+10h]
0x18007d39b  call    WPP_SF_d
0x18007d3a0  nop
0x18007d3a1  lea     rcx, [rsp+540h+hObject]
0x18007d3a6  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x18007d3ab  jmp     loc_18007D256
0x18007d3b0  mov     rcx, [rsp+540h+hObject]
0x18007d3b5  mov     rax, [rcx]
0x18007d3b8  mov     r8, r15
0x18007d3bb  mov     rdx, r14
0x18007d3be  mov     rax, [rax+38h]
0x18007d3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d3c7  mov     ebx, eax
0x18007d3c9  test    eax, eax
0x18007d3cb  jns     short loc_18007D3ED
0x18007d3cd  lea     rax, WPP_GLOBAL_Control
0x18007d3d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d3db  cmp     rcx, rax
0x18007d3de  jz      short loc_18007D3A1
0x18007d3e0  test    [rcx+1Ch], r13b
0x18007d3e4  jz      short loc_18007D3A1
0x18007d3e6  mov     edx, 14h
0x18007d3eb  jmp     short loc_18007D38D
0x18007d3ed  lea     rcx, [rsp+540h+hObject]
0x18007d3f2  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x18007d3f7  jmp     loc_18007D5F9
0x18007d3fc  lea     rax, [rsp+540h+hObject]
0x18007d401  mov     [rsp+540h+phNewToken], rax; phNewToken
0x18007d406  mov     [rsp+540h+TokenType], r13d; TokenType
0x18007d40b  mov     r9d, 2; ImpersonationLevel
0x18007d411  xor     r8d, r8d; lpTokenAttributes
0x18007d414  mov     edx, 0ABh; dwDesiredAccess
0x18007d419  mov     rcx, [rsp+540h+TokenHandle]; hExistingToken
0x18007d41e  call    cs:__imp_DuplicateTokenEx
0x18007d424  test    eax, eax
0x18007d426  jnz     short loc_18007D48B
0x18007d428  call    cs:__imp_GetLastError
0x18007d42e  mov     ebx, eax
0x18007d430  test    eax, eax
0x18007d432  jle     short loc_18007D43D
0x18007d434  movzx   ebx, ax
0x18007d437  or      ebx, 80070000h
0x18007d43d  test    ebx, ebx
0x18007d43f  jns     short loc_18007D48B
0x18007d441  lea     rax, WPP_GLOBAL_Control
0x18007d448  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d44f  cmp     rcx, rax
0x18007d452  jz      short loc_18007D472
0x18007d454  test    [rcx+1Ch], r13b
0x18007d458  jz      short loc_18007D472
0x18007d45a  mov     edx, 15h
0x18007d45f  mov     r9d, ebx
0x18007d462  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007d469  mov     rcx, [rcx+10h]
0x18007d46d  call    WPP_SF_d
0x18007d472  mov     rcx, [rsp+540h+hObject]; hObject
0x18007d477  test    rcx, rcx
0x18007d47a  jz      loc_18007D256
0x18007d480  call    cs:__imp_CloseHandle
0x18007d486  jmp     loc_18007D256
0x18007d48b  test    esi, esi
0x18007d48d  jz      short loc_18007D504
0x18007d48f  mov     r8, [rsp+540h+hObject]; void *
0x18007d494  lea     rdx, aSeassignprimar; "SeAssignPrimaryTokenPrivilege"
0x18007d49b  call    ?EnableSinglePrivilege@ShieldProcessLauncher@ShieldProvider@@AEAAJPEBGPEAX@Z; ShieldProvider::ShieldProcessLauncher::EnableSinglePrivilege(ushort const *,void *)
0x18007d4a0  mov     ebx, eax
0x18007d4a2  test    eax, eax
0x18007d4a4  jns     short loc_18007D4C6
0x18007d4a6  lea     rax, WPP_GLOBAL_Control
0x18007d4ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d4b4  cmp     rcx, rax
0x18007d4b7  jz      short loc_18007D472
0x18007d4b9  test    [rcx+1Ch], r13b
0x18007d4bd  jz      short loc_18007D472
0x18007d4bf  mov     edx, 16h
0x18007d4c4  jmp     short loc_18007D45F
0x18007d4c6  mov     r8, [rsp+540h+hObject]; void *
0x18007d4cb  lea     rdx, aSeincreasequot; "SeIncreaseQuotaPrivilege"
0x18007d4d2  call    ?EnableSinglePrivilege@ShieldProcessLauncher@ShieldProvider@@AEAAJPEBGPEAX@Z; ShieldProvider::ShieldProcessLauncher::EnableSinglePrivilege(ushort const *,void *)
0x18007d4d7  mov     ebx, eax
0x18007d4d9  test    eax, eax
0x18007d4db  jns     short loc_18007D504
0x18007d4dd  lea     rax, WPP_GLOBAL_Control
0x18007d4e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d4eb  cmp     rcx, rax
0x18007d4ee  jz      short loc_18007D472
0x18007d4f0  test    [rcx+1Ch], r13b
0x18007d4f4  jz      loc_18007D472
0x18007d4fa  mov     edx, 17h
0x18007d4ff  jmp     loc_18007D45F
0x18007d504  mov     qword ptr [rbp+440h+ProcessInformation.dwProcessId], 0
0x18007d50c  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18007d514  movdqu  xmmword ptr [rsp+540h+ProcessInformation.hProcess], xmm0
0x18007d51a  mov     ebx, 68h ; 'h'
0x18007d51f  mov     r8d, ebx; Size
0x18007d522  xor     edx, edx; Val
0x18007d524  lea     rcx, [rbp+440h+StartupInfo]; void *
0x18007d528  call    memset_0
0x18007d52d  mov     [rbp+440h+StartupInfo.cb], ebx
0x18007d530  lea     rax, aWinsta0Default; "winsta0\\default"
0x18007d537  mov     [rbp+440h+StartupInfo.lpDesktop], rax
0x18007d53b  lea     rax, [rsp+540h+ProcessInformation]
0x18007d540  mov     [rsp+540h+lpProcessInformation], rax; lpProcessInformation
0x18007d545  lea     rax, [rbp+440h+StartupInfo]
0x18007d549  mov     [rsp+540h+lpStartupInfo], rax; lpStartupInfo
0x18007d54e  mov     [rsp+540h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18007d557  mov     [rsp+540h+lpEnvironment], 0; lpEnvironment
0x18007d560  mov     [rsp+540h+dwCreationFlags], 20h ; ' '; dwCreationFlags
0x18007d568  mov     dword ptr [rsp+540h+phNewToken], 0; bInheritHandles
0x18007d570  mov     qword ptr [rsp+540h+TokenType], 0; lpThreadAttributes
0x18007d579  xor     r9d, r9d; lpProcessAttributes
0x18007d57c  lea     r8, [rbp+440h+CommandLine]; lpCommandLine
0x18007d580  xor     edx, edx; lpApplicationName
0x18007d582  mov     rcx, [rsp+540h+hObject]; hToken
0x18007d587  call    cs:__imp_CreateProcessAsUserW
0x18007d58d  test    eax, eax
0x18007d58f  jnz     short loc_18007D5D5
0x18007d591  call    cs:__imp_GetLastError
0x18007d597  mov     ebx, eax
0x18007d599  test    eax, eax
  ... truncated ...
```
