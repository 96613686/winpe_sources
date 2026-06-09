# OpenOrCreatePrivateMutex(void)

- ea: `0x18000fd5c`
- end: `0x180010156`
- name: `?OpenOrCreatePrivateMutex@@YAKXZ`
- size: `1018`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004320`

## callees

- `0x180002f2c`
- `0x18000f6bc`
- `0x18000f94c`
- `0x18000fbdc`
- `0x18000fd5c`
- `0x18001015c`
- `0x1800135cc`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000fee5`
- `KERNEL32!HeapAlloc` at `0x18000ff85`
- `KERNEL32!HeapAlloc` at `0x18000fee5`
- `KERNEL32!HeapAlloc` at `0x18000ff85`
- `KERNEL32!GetProcessHeap` at `0x18000fed7`
- `KERNEL32!GetProcessHeap` at `0x18000ff77`
- `KERNEL32!GetProcessHeap` at `0x1800100ea`
- `KERNEL32!GetProcessHeap` at `0x180010116`
- `KERNEL32!GetProcessHeap` at `0x18001012f`
- `KERNEL32!GetProcessHeap` at `0x18000fed7`
- `KERNEL32!GetProcessHeap` at `0x18000ff77`
- `KERNEL32!GetProcessHeap` at `0x1800100ea`
- `KERNEL32!GetProcessHeap` at `0x180010116`
- `KERNEL32!GetProcessHeap` at `0x18001012f`
- `KERNEL32!SetLastError` at `0x18000fe29`
- `KERNEL32!SetLastError` at `0x18000fe29`
- `KERNEL32!HeapFree` at `0x1800100f8`
- `KERNEL32!HeapFree` at `0x180010124`
- `KERNEL32!HeapFree` at `0x18001013d`
- `KERNEL32!HeapFree` at `0x1800100f8`
- `KERNEL32!HeapFree` at `0x180010124`
- `KERNEL32!HeapFree` at `0x18001013d`
- `KERNEL32!GetLastError` at `0x18000fdb1`
- `KERNEL32!GetLastError` at `0x18000fdd9`
- `KERNEL32!GetLastError` at `0x18000fe10`
- `KERNEL32!GetLastError` at `0x18000fe34`
- `KERNEL32!GetLastError` at `0x18000fffe`
- `KERNEL32!GetLastError` at `0x180010055`
- `KERNEL32!GetLastError` at `0x18000fdb1`
- `KERNEL32!GetLastError` at `0x18000fdd9`
- `KERNEL32!GetLastError` at `0x18000fe10`
- `KERNEL32!GetLastError` at `0x18000fe34`
- `KERNEL32!GetLastError` at `0x18000fffe`
- `KERNEL32!GetLastError` at `0x180010055`
- `KERNEL32!CloseHandle` at `0x18000fe21`
- `KERNEL32!CloseHandle` at `0x1800100ca`
- `KERNEL32!CloseHandle` at `0x18000fe21`
- `KERNEL32!CloseHandle` at `0x1800100ca`
- `KERNEL32!LocalFree` at `0x180010107`
- `KERNEL32!LocalFree` at `0x180010107`
- `KERNEL32!GetCurrentProcess` at `0x18000fdc0`
- `KERNEL32!GetCurrentProcess` at `0x18000fdc0`
- `KERNEL32!ClosePrivateNamespace` at `0x1800100b1`
- `KERNEL32!ClosePrivateNamespace` at `0x1800100b1`
- `KERNEL32!OpenPrivateNamespaceW` at `0x18000ffec`
- `KERNEL32!OpenPrivateNamespaceW` at `0x18000ffec`
- `KERNEL32!OpenMutexW` at `0x180010043`
- `KERNEL32!OpenMutexW` at `0x180010043`
- `KERNEL32!DeleteBoundaryDescriptor` at `0x1800100df`
- `KERNEL32!DeleteBoundaryDescriptor` at `0x1800100df`
- `KERNEL32!GetCurrentThread` at `0x18000fd8f`
- `KERNEL32!GetCurrentThread` at `0x18000fd8f`
- `ADVAPI32!OpenProcessToken` at `0x18000fdcf`
- `ADVAPI32!OpenProcessToken` at `0x18000fdcf`
- `ADVAPI32!OpenThreadToken` at `0x18000fda7`
- `ADVAPI32!OpenThreadToken` at `0x18000fda7`
- `ADVAPI32!ConvertSidToStringSidW` at `0x18000fe48`
- `ADVAPI32!ConvertSidToStringSidW` at `0x18000fe48`

## pseudocode

```c
__int64 OpenOrCreatePrivateMutex(void)
{
  void *v0; // r12
  unsigned __int16 *v1; // r13
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  __int64 v4; // rdx
  HANDLE CurrentProcess; // rax
  void *UserSid; // rdi
  HANDLE v7; // rcx
  DWORD SecurePrivateNamespace; // ebx
  const wchar_t *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r15
  LPWSTR v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r14
  SIZE_T v15; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v17; // rcx
  const wchar_t *v18; // rax
  __int64 v19; // r14
  __int64 v20; // r15
  SIZE_T v21; // rbx
  HANDLE v22; // rax
  const WCHAR *v23; // rsi
  void *UserBoundaryDescriptor; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  void **v27; // r9
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  void **v34; // r8
  HANDLE v35; // rax
  void *v36; // rdi
  HANDLE v37; // rax
  HANDLE v38; // rax
  HANDLE TokenHandle; // [rsp+80h] [rbp+48h] BYREF
  LPWSTR StringSid; // [rsp+88h] [rbp+50h] BYREF
  LPVOID lpMem; // [rsp+90h] [rbp+58h]
  __int64 v43; // [rsp+98h] [rbp+60h]

  v0 = 0;
  lpMem = 0;
  v1 = 0;
  StringSid = 0;
  g_hDmrcPrivateMutex = 0;
  LastError = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000000u, 1, &TokenHandle) )
    goto LABEL_8;
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x2000000u, &TokenHandle) )
    {
      LastError = 0;
      goto LABEL_8;
    }
    LastError = GetLastError();
  }
  if ( !LastError )
  {
LABEL_8:
    v7 = TokenHandle;
    if ( !TokenHandle )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(0, v4);
      v7 = TokenHandle;
    }
    UserSid = _GetUserSid(v7);
    if ( !UserSid )
      LastError = GetLastError();
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    goto LABEL_14;
  }
  UserSid = 0;
  TokenHandle = 0;
LABEL_14:
  SetLastError(LastError);
  if ( !UserSid || !ConvertSidToStringSidW(UserSid, &StringSid) )
    goto LABEL_15;
  v9 = L"Dmrc_ns_0466814c-52a3-42bf-bbc1-441ebf9b9967";
  v10 = 0x7FFFFFFF;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v10;
  }
  while ( v10 );
  v11 = (0x7FFFFFFF - v10) & -(__int64)(v10 != 0);
  if ( !v10 )
    goto LABEL_53;
  v12 = StringSid;
  if ( !StringSid )
    goto LABEL_53;
  v13 = 0x7FFFFFFF;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v13;
  }
  while ( v13 );
  v14 = (0x7FFFFFFF - v13) & -(__int64)(v13 != 0);
  if ( !v13 )
    goto LABEL_53;
  v43 = v14 + v11 + 1;
  v15 = 2LL * (unsigned int)(v43 + 1);
  ProcessHeap = GetProcessHeap();
  v1 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, v15);
  if ( !v1 )
  {
LABEL_27:
    SecurePrivateNamespace = 8;
    goto LABEL_54;
  }
  if ( (int)StringCchPrintfW(v1, v11 + v14 + 2, L"%ws_%ws", L"Dmrc_ns_0466814c-52a3-42bf-bbc1-441ebf9b9967", StringSid) < 0 )
  {
LABEL_29:
    SecurePrivateNamespace = 8;
    goto LABEL_54;
  }
  v17 = 0x7FFFFFFF;
  v18 = L"Dmrc_mtx_409a9db1-a045-4296-8d2c-9d71016c846b";
  do
  {
    if ( !*v18 )
      break;
    ++v18;
    --v17;
  }
  while ( v17 );
  v19 = (0x7FFFFFFF - v17) & -(__int64)(v17 != 0);
  if ( !v17 )
  {
LABEL_53:
    SecurePrivateNamespace = 87;
    goto LABEL_54;
  }
  v20 = v43;
  v21 = 2LL * (unsigned int)(v19 + v43 + 2);
  v22 = GetProcessHeap();
  lpMem = HeapAlloc(v22, 0, v21);
  v23 = (const WCHAR *)lpMem;
  if ( !lpMem )
    goto LABEL_27;
  if ( (int)StringCchPrintfW(
              (unsigned __int16 *)lpMem,
              v19 + v20 + 2,
              L"%ws\\%ws",
              v1,
              L"Dmrc_mtx_409a9db1-a045-4296-8d2c-9d71016c846b") < 0 )
    goto LABEL_29;
  UserBoundaryDescriptor = CreateUserBoundaryDescriptor(UserSid, StringSid);
  v0 = UserBoundaryDescriptor;
  if ( !UserBoundaryDescriptor )
  {
LABEL_15:
    SecurePrivateNamespace = GetLastError();
    goto LABEL_51;
  }
  SecurePrivateNamespace = 0;
  g_hDmrcPrivateNamespace = OpenPrivateNamespaceW(UserBoundaryDescriptor, v1);
  if ( !g_hDmrcPrivateNamespace )
  {
    if ( GetLastError() - 2 > 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v26, v25);
    SecurePrivateNamespace = CreateSecurePrivateNamespace(v0, UserSid, v1, v27);
    if ( SecurePrivateNamespace )
      goto LABEL_54;
    if ( !g_hDmrcPrivateNamespace )
      MicrosoftTelemetryAssertTriggeredNoArgs(v29, v28);
  }
  g_hDmrcPrivateMutex = OpenMutexW(0x10000000u, 1, v23);
  if ( g_hDmrcPrivateMutex )
    goto LABEL_47;
  if ( GetLastError() - 2 > 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v33, v32);
  SecurePrivateNamespace = CreateSecurePrivateMutex(UserSid, v23, v34);
  if ( !SecurePrivateNamespace )
  {
LABEL_47:
    if ( !g_hDmrcPrivateMutex )
      MicrosoftTelemetryAssertTriggeredNoArgs(v31, v30);
    if ( !g_hDmrcPrivateNamespace )
      MicrosoftTelemetryAssertTriggeredNoArgs(v31, v30);
LABEL_51:
    if ( !SecurePrivateNamespace )
      goto LABEL_58;
  }
LABEL_54:
  if ( g_hDmrcPrivateNamespace )
  {
    ClosePrivateNamespace(g_hDmrcPrivateNamespace, 0);
    g_hDmrcPrivateNamespace = 0;
  }
  if ( g_hDmrcPrivateMutex )
  {
    CloseHandle(g_hDmrcPrivateMutex);
    g_hDmrcPrivateMutex = 0;
  }
LABEL_58:
  if ( v0 )
    DeleteBoundaryDescriptor(v0);
  if ( UserSid )
  {
    v35 = GetProcessHeap();
    HeapFree(v35, 0, UserSid);
  }
  if ( StringSid )
    LocalFree(StringSid);
  v36 = lpMem;
  if ( lpMem )
  {
    v37 = GetProcessHeap();
    HeapFree(v37, 0, v36);
  }
  if ( v1 )
  {
    v38 = GetProcessHeap();
    HeapFree(v38, 0, v1);
  }
  return SecurePrivateNamespace;
}

```

## disassembly

```asm
0x18000fd5c  push    rbp
0x18000fd5e  push    rbx
0x18000fd5f  push    rsi
0x18000fd60  push    rdi
0x18000fd61  push    r12
0x18000fd63  push    r13
0x18000fd65  push    r14
0x18000fd67  push    r15
0x18000fd69  mov     rbp, rsp
0x18000fd6c  sub     rsp, 38h
0x18000fd70  xor     r14d, r14d
0x18000fd73  mov     r12d, r14d
0x18000fd76  mov     [rbp+lpMem], r14
0x18000fd7a  mov     r13d, r14d
0x18000fd7d  mov     [rbp+StringSid], r14
0x18000fd81  mov     cs:?g_hDmrcPrivateMutex@@3PEAXEA, r14; void * g_hDmrcPrivateMutex
0x18000fd88  mov     ebx, r14d
0x18000fd8b  mov     [rbp+TokenHandle], r14
0x18000fd8f  call    cs:__imp_GetCurrentThread
0x18000fd95  mov     edi, 2000000h
0x18000fd9a  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000fd9e  mov     rcx, rax; ThreadHandle
0x18000fda1  lea     r8d, [r14+1]; OpenAsSelf
0x18000fda5  mov     edx, edi; DesiredAccess
0x18000fda7  call    cs:__imp_OpenThreadToken
0x18000fdad  test    eax, eax
0x18000fdaf  jnz     short loc_18000FDF1
0x18000fdb1  call    cs:__imp_GetLastError
0x18000fdb7  mov     ebx, eax
0x18000fdb9  cmp     eax, 3F0h
0x18000fdbe  jnz     short loc_18000FDE1
0x18000fdc0  call    cs:__imp_GetCurrentProcess
0x18000fdc6  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000fdca  mov     edx, edi; DesiredAccess
0x18000fdcc  mov     rcx, rax; ProcessHandle
0x18000fdcf  call    cs:__imp_OpenProcessToken
0x18000fdd5  test    eax, eax
0x18000fdd7  jnz     short loc_18000FDEE
0x18000fdd9  call    cs:__imp_GetLastError
0x18000fddf  mov     ebx, eax
0x18000fde1  test    ebx, ebx
0x18000fde3  jz      short loc_18000FDF1
0x18000fde5  mov     rdi, r14
0x18000fde8  mov     [rbp+TokenHandle], r14
0x18000fdec  jmp     short loc_18000FE27
0x18000fdee  mov     ebx, r14d
0x18000fdf1  mov     rcx, [rbp+TokenHandle]
0x18000fdf5  test    rcx, rcx
0x18000fdf8  jnz     short loc_18000FE03
0x18000fdfa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000fdff  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000fe03  call    ?_GetUserSid@@YAPEAXPEAX@Z; _GetUserSid(void *)
0x18000fe08  mov     rdi, rax
0x18000fe0b  test    rax, rax
0x18000fe0e  jnz     short loc_18000FE18
0x18000fe10  call    cs:__imp_GetLastError
0x18000fe16  mov     ebx, eax
0x18000fe18  mov     rcx, [rbp+TokenHandle]; hObject
0x18000fe1c  test    rcx, rcx
0x18000fe1f  jz      short loc_18000FE27
0x18000fe21  call    cs:__imp_CloseHandle
0x18000fe27  mov     ecx, ebx; dwErrCode
0x18000fe29  call    cs:__imp_SetLastError
0x18000fe2f  test    rdi, rdi
0x18000fe32  jnz     short loc_18000FE41
0x18000fe34  call    cs:__imp_GetLastError
0x18000fe3a  mov     ebx, eax
0x18000fe3c  jmp     loc_180010095
0x18000fe41  lea     rdx, [rbp+StringSid]; StringSid
0x18000fe45  mov     rcx, rdi; Sid
0x18000fe48  call    cs:__imp_ConvertSidToStringSidW
0x18000fe4e  test    eax, eax
0x18000fe50  jz      short loc_18000FE34
0x18000fe52  mov     esi, 7FFFFFFFh
0x18000fe57  lea     rax, aDmrcNs0466814c; "Dmrc_ns_0466814c-52a3-42bf-bbc1-441ebf9"...
0x18000fe5e  mov     edx, esi
0x18000fe60  cmp     [rax], r14w
0x18000fe64  jz      short loc_18000FE70
0x18000fe66  add     rax, 2
0x18000fe6a  sub     rdx, 1
0x18000fe6e  jnz     short loc_18000FE60
0x18000fe70  mov     rcx, rsi
0x18000fe73  mov     rax, rdx
0x18000fe76  sub     rcx, rdx
0x18000fe79  neg     rax
0x18000fe7c  sbb     r15, r15
0x18000fe7f  and     r15, rcx
0x18000fe82  test    rdx, rdx
0x18000fe85  jz      loc_18001009E
0x18000fe8b  mov     rax, [rbp+StringSid]
0x18000fe8f  test    rax, rax
0x18000fe92  jz      loc_18001009E
0x18000fe98  mov     rdx, rsi
0x18000fe9b  cmp     [rax], r14w
0x18000fe9f  jz      short loc_18000FEAB
0x18000fea1  add     rax, 2
0x18000fea5  sub     rdx, 1
0x18000fea9  jnz     short loc_18000FE9B
0x18000feab  mov     rcx, rsi
0x18000feae  mov     rax, rdx
0x18000feb1  sub     rcx, rdx
0x18000feb4  neg     rax
0x18000feb7  sbb     r14, r14
0x18000feba  and     r14, rcx
0x18000febd  test    rdx, rdx
0x18000fec0  jz      loc_18001009B
0x18000fec6  lea     rax, [r15+1]
0x18000feca  add     rax, r14
0x18000fecd  mov     [rbp+arg_18], rax
0x18000fed1  lea     ebx, [rax+1]
0x18000fed4  add     rbx, rbx
0x18000fed7  call    cs:__imp_GetProcessHeap
0x18000fedd  mov     r8, rbx; dwBytes
0x18000fee0  xor     edx, edx; dwFlags
0x18000fee2  mov     rcx, rax; hHeap
0x18000fee5  call    cs:__imp_HeapAlloc
0x18000feeb  mov     r13, rax
0x18000feee  test    rax, rax
0x18000fef1  jnz     short loc_18000FF00
0x18000fef3  mov     ebx, 8
0x18000fef8  xor     r14d, r14d
0x18000fefb  jmp     loc_1800100A3
0x18000ff00  mov     rax, [rbp+StringSid]
0x18000ff04  lea     rdx, [r14+2]
0x18000ff08  add     rdx, r15; unsigned __int64
0x18000ff0b  mov     [rsp+38h+var_18], rax
0x18000ff10  lea     r9, aDmrcNs0466814c; "Dmrc_ns_0466814c-52a3-42bf-bbc1-441ebf9"...
0x18000ff17  mov     rcx, r13; unsigned __int16 *
0x18000ff1a  lea     r8, aWsWs; "%ws_%ws"
0x18000ff21  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ff26  xor     r14d, r14d
0x18000ff29  test    eax, eax
0x18000ff2b  jns     short loc_18000FF37
0x18000ff2d  mov     ebx, 8
0x18000ff32  jmp     loc_1800100A3
0x18000ff37  mov     rcx, rsi
0x18000ff3a  lea     rax, aDmrcMtx409a9db; "Dmrc_mtx_409a9db1-a045-4296-8d2c-9d7101"...
0x18000ff41  cmp     [rax], r14w
0x18000ff45  jz      short loc_18000FF51
0x18000ff47  add     rax, 2
0x18000ff4b  sub     rcx, 1
0x18000ff4f  jnz     short loc_18000FF41
0x18000ff51  sub     rsi, rcx
0x18000ff54  mov     rax, rcx
0x18000ff57  neg     rax
0x18000ff5a  sbb     r14, r14
0x18000ff5d  and     r14, rsi
0x18000ff60  test    rcx, rcx
0x18000ff63  jz      loc_18001009B
0x18000ff69  mov     r15, [rbp+arg_18]
0x18000ff6d  lea     ebx, [r14+r15]
0x18000ff71  add     ebx, 2
0x18000ff74  add     rbx, rbx
0x18000ff77  call    cs:__imp_GetProcessHeap
0x18000ff7d  mov     r8, rbx; dwBytes
0x18000ff80  xor     edx, edx; dwFlags
0x18000ff82  mov     rcx, rax; hHeap
0x18000ff85  call    cs:__imp_HeapAlloc
0x18000ff8b  mov     [rbp+lpMem], rax
0x18000ff8f  mov     rsi, rax
0x18000ff92  test    rax, rax
0x18000ff95  jz      loc_18000FEF3
0x18000ff9b  lea     rax, aDmrcMtx409a9db; "Dmrc_mtx_409a9db1-a045-4296-8d2c-9d7101"...
0x18000ffa2  mov     r9, r13
0x18000ffa5  lea     rdx, [r15+2]
0x18000ffa9  mov     [rsp+38h+var_18], rax
0x18000ffae  add     rdx, r14; unsigned __int64
0x18000ffb1  lea     r8, aWsWs_0; "%ws\\%ws"
0x18000ffb8  mov     rcx, rsi; unsigned __int16 *
0x18000ffbb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ffc0  xor     r14d, r14d
0x18000ffc3  test    eax, eax
0x18000ffc5  js      loc_18000FF2D
0x18000ffcb  mov     rdx, [rbp+StringSid]; unsigned __int16 *
0x18000ffcf  mov     rcx, rdi; RequiredSid
0x18000ffd2  call    ?CreateUserBoundaryDescriptor@@YAPEAXPEAXPEBG@Z; CreateUserBoundaryDescriptor(void *,ushort const *)
0x18000ffd7  mov     r12, rax
0x18000ffda  test    rax, rax
0x18000ffdd  jz      loc_18000FE34
0x18000ffe3  mov     rdx, r13; lpAliasPrefix
0x18000ffe6  mov     rcx, rax; lpBoundaryDescriptor
0x18000ffe9  mov     ebx, r14d
0x18000ffec  call    cs:__imp_OpenPrivateNamespaceW
0x18000fff2  mov     cs:?g_hDmrcPrivateNamespace@@3PEAXEA, rax; void * g_hDmrcPrivateNamespace
0x18000fff9  test    rax, rax
0x18000fffc  jnz     short loc_180010036
0x18000fffe  call    cs:__imp_GetLastError
0x180010004  add     eax, 0FFFFFFFEh
0x180010007  cmp     eax, 1
0x18001000a  jbe     short loc_180010011
0x18001000c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010011  mov     r8, r13; lpAliasPrefix
0x180010014  mov     rdx, rdi; pSid
0x180010017  mov     rcx, r12; lpBoundaryDescriptor
0x18001001a  call    ?CreateSecurePrivateNamespace@@YAKPEAX0PEBGPEAPEAX@Z; CreateSecurePrivateNamespace(void *,void *,ushort const *,void * *)
0x18001001f  mov     ebx, eax
0x180010021  test    eax, eax
0x180010023  jnz     short loc_1800100A3
0x180010025  mov     rax, cs:?g_hDmrcPrivateNamespace@@3PEAXEA; void * g_hDmrcPrivateNamespace
0x18001002c  test    rax, rax
0x18001002f  jnz     short loc_180010036
0x180010031  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010036  mov     r8, rsi; lpName
0x180010039  mov     edx, 1; bInheritHandle
0x18001003e  mov     ecx, 10000000h; dwDesiredAccess
0x180010043  call    cs:__imp_OpenMutexW
0x180010049  mov     cs:?g_hDmrcPrivateMutex@@3PEAXEA, rax; void * g_hDmrcPrivateMutex
0x180010050  test    rax, rax
0x180010053  jnz     short loc_180010079
0x180010055  call    cs:__imp_GetLastError
0x18001005b  add     eax, 0FFFFFFFEh
0x18001005e  cmp     eax, 1
0x180010061  jbe     short loc_180010068
0x180010063  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010068  mov     rdx, rsi; lpName
0x18001006b  mov     rcx, rdi; pSid
0x18001006e  call    ?CreateSecurePrivateMutex@@YAKPEAXPEAGPEAPEAX@Z; CreateSecurePrivateMutex(void *,ushort *,void * *)
0x180010073  mov     ebx, eax
0x180010075  test    eax, eax
0x180010077  jnz     short loc_1800100A3
0x180010079  cmp     cs:?g_hDmrcPrivateMutex@@3PEAXEA, r14; void * g_hDmrcPrivateMutex
0x180010080  jnz     short loc_180010087
0x180010082  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010087  cmp     cs:?g_hDmrcPrivateNamespace@@3PEAXEA, r14; void * g_hDmrcPrivateNamespace
0x18001008e  jnz     short loc_180010095
0x180010090  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010095  test    ebx, ebx
0x180010097  jnz     short loc_1800100A3
0x180010099  jmp     short loc_1800100D7
0x18001009b  xor     r14d, r14d
0x18001009e  mov     ebx, 57h ; 'W'
0x1800100a3  mov     rcx, cs:?g_hDmrcPrivateNamespace@@3PEAXEA; Handle
0x1800100aa  test    rcx, rcx
0x1800100ad  jz      short loc_1800100BE
0x1800100af  xor     edx, edx; Flags
0x1800100b1  call    cs:__imp_ClosePrivateNamespace
0x1800100b7  mov     cs:?g_hDmrcPrivateNamespace@@3PEAXEA, r14; void * g_hDmrcPrivateNamespace
0x1800100be  mov     rcx, cs:?g_hDmrcPrivateMutex@@3PEAXEA; hObject
0x1800100c5  test    rcx, rcx
0x1800100c8  jz      short loc_1800100D7
0x1800100ca  call    cs:__imp_CloseHandle
0x1800100d0  mov     cs:?g_hDmrcPrivateMutex@@3PEAXEA, r14; void * g_hDmrcPrivateMutex
0x1800100d7  test    r12, r12
0x1800100da  jz      short loc_1800100E5
0x1800100dc  mov     rcx, r12; BoundaryDescriptor
0x1800100df  call    cs:__imp_DeleteBoundaryDescriptor
0x1800100e5  test    rdi, rdi
0x1800100e8  jz      short loc_1800100FE
0x1800100ea  call    cs:__imp_GetProcessHeap
0x1800100f0  mov     r8, rdi; lpMem
0x1800100f3  xor     edx, edx; dwFlags
0x1800100f5  mov     rcx, rax; hHeap
0x1800100f8  call    cs:__imp_HeapFree
0x1800100fe  mov     rcx, [rbp+StringSid]; hMem
0x180010102  test    rcx, rcx
0x180010105  jz      short loc_18001010D
0x180010107  call    cs:__imp_LocalFree
0x18001010d  mov     rdi, [rbp+lpMem]
0x180010111  test    rdi, rdi
0x180010114  jz      short loc_18001012A
0x180010116  call    cs:__imp_GetProcessHeap
0x18001011c  mov     r8, rdi; lpMem
0x18001011f  xor     edx, edx; dwFlags
0x180010121  mov     rcx, rax; hHeap
0x180010124  call    cs:__imp_HeapFree
0x18001012a  test    r13, r13
0x18001012d  jz      short loc_180010143
0x18001012f  call    cs:__imp_GetProcessHeap
0x180010135  mov     r8, r13; lpMem
0x180010138  xor     edx, edx; dwFlags
0x18001013a  mov     rcx, rax; hHeap
0x18001013d  call    cs:__imp_HeapFree
0x180010143  mov     eax, ebx
0x180010145  add     rsp, 38h
0x180010149  pop     r15
0x18001014b  pop     r14
0x18001014d  pop     r13
0x18001014f  pop     r12
0x180010151  pop     rdi
0x180010152  pop     rsi
0x180010153  pop     rbx
0x180010154  pop     rbp
0x180010155  retn
```
