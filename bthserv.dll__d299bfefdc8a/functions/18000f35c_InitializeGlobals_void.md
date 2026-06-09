# InitializeGlobals(void)

- ea: `0x18000f35c`
- end: `0x18000f758`
- name: `?InitializeGlobals@@YAXXZ`
- size: `1020`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800100c0`

## callees

- `0x180001b60`
- `0x18000a384`
- `0x18000a3e4`
- `0x18000f35c`
- `0x1800110fc`
- `0x180011194`
- `0x18001d324`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000f5b1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000f5d1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000f5b1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000f5d1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f449`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f449`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f48b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f48b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f637`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f637`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f701`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f701`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f5fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f5fe`

## string_xrefs

- `0x18000f5e7`: `SYSTEM\CurrentControlSet\Services\BthServ\Parameters`

## pseudocode

```c
void InitializeGlobals(void)
{
  char v0; // bl
  char v1; // dl
  HANDLE EventW; // rax
  struct _TP_TIMER *ThreadpoolTimer; // rax
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *v4; // rcx
  char v5; // dl
  Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher *v6; // rdi
  char v7; // dl
  HANDLE MutexW; // rax
  int v9; // edx
  int v10; // r8d
  unsigned int v11; // eax
  _BYTE *v12; // rcx
  char v13; // dl
  int phkResult; // [rsp+20h] [rbp-48h]
  int lpcbData; // [rsp+28h] [rbp-40h]
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF
  int *v17; // [rsp+58h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+38h] BYREF
  int v19; // [rsp+A8h] [rbp+40h] BYREF
  DWORD Type; // [rsp+B0h] [rbp+48h] BYREF
  unsigned int Data; // [rsp+B8h] [rbp+50h] BYREF

  Type = 4;
  hKey = 0;
  Data = 0;
  cbData = 4;
  v0 = 1;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v1 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
    v1 = 0;
  if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v1,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  hModule = 0;
  dword_180044A80 = 32;
  dword_180044A8C = 32;
  dword_180044A98 = 32;
  *(_OWORD *)&pv = 0;
  qword_180044A70 = 0;
  qword_180044A78 = 0;
  qword_180044A84 = 8;
  dword_180044A90 = 1;
  dword_180044A94 = 10;
  qword_180044AD8 = 0;
  hServiceStatus = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  hEvent = 0;
  Globals = EventW;
  *(_OWORD *)&ServiceStatus.dwServiceType = 0;
  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  xmmword_180044B08 = 0;
  *(_OWORD *)&hObject = 0;
  ThreadpoolTimer = CreateThreadpoolTimer(PolicyTimerCallback, 0, 0);
  v4 = qword_180044BA8;
  pti = ThreadpoolTimer;
  v19 = 0;
  qword_180044BA8 = 0;
  if ( v4 )
    (**(void (__fastcall ***)(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *, __int64))v4)(
      v4,
      1);
  v17 = &v19;
  v19 = wil::ResultFromException__lambda_c16bf91101c9118b5e2e61d840e8728a___(&v17);
  if ( v19 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v5 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
      v5 = 0;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
  v6 = (Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher *)qword_180044BC0;
  qword_180044BC0 = 0;
  if ( v6 )
  {
    Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::~BthServDeviceRefresher(v6);
    operator delete(v6, (const struct std::nothrow_t *)0x28);
  }
  if ( (int)wil::ResultFromException__lambda_55b676508b23d6fc517a7e1a7ea2e59f___() < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v7 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
      v7 = 0;
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
  qword_180044B38 = 0;
  qword_180044B40 = 0;
  MutexW = CreateMutexW(0, 0, 0);
  dword_180044B58 = 1;
  hMutex = MutexW;
  dword_180044B5C = 1;
  qword_180044B50 = CreateMutexW(0, 0, 0);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BthServ\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"ChannelAvoidanceRange", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
    {
      v11 = Data;
      *(_DWORD *)&dword_180044B94 = Data;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v9) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
      {
        LOBYTE(v9) = 0;
      }
      if ( !(_BYTE)v9 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_37;
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        v10,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        phkResult,
        lpcbData,
        23,
        (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
      v11 = *(_DWORD *)&dword_180044B94;
    }
    else
    {
      v11 = 0;
      *(_DWORD *)&dword_180044B94 = 0;
    }
    v12 = WPP_GLOBAL_Control;
LABEL_37:
    if ( v11 > 0x3B )
    {
      if ( v12 == (_BYTE *)&WPP_GLOBAL_Control || (v13 = 1, v12[25] < 3u) )
        v13 = 0;
      if ( v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_s(
          *((_QWORD *)v12 + 2),
          v13,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *((_QWORD *)v12 + 5));
      *(_DWORD *)&dword_180044B94 = 0;
    }
    RegCloseKey(hKey);
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    v0 = 0;
  if ( v0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v0,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
}

```

## disassembly

```asm
0x18000f35c  push    rbp
0x18000f35e  push    rbx
0x18000f35f  push    rsi
0x18000f360  push    rdi
0x18000f361  push    r12
0x18000f363  push    r15
0x18000f365  mov     rbp, rsp
0x18000f368  sub     rsp, 68h
0x18000f36c  xor     esi, esi
0x18000f36e  mov     [rbp+Type], 4
0x18000f375  mov     [rbp+hKey], rsi
0x18000f379  mov     [rbp+Data], esi
0x18000f37c  mov     [rbp+cbData], 4
0x18000f383  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f38a  lea     r15, WPP_GLOBAL_Control
0x18000f391  lea     ebx, [rsi+1]
0x18000f394  cmp     rcx, r15
0x18000f397  jz      short loc_18000F3A1
0x18000f399  cmp     byte ptr [rcx+19h], 5
0x18000f39d  mov     dl, bl
0x18000f39f  jnb     short loc_18000F3A4
0x18000f3a1  mov     dl, sil
0x18000f3a4  lea     r12, WPP_RECORDER_INITIALIZED
0x18000f3ab  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000f3b2  lea     rdi, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000f3b9  setnz   r8b
0x18000f3bd  test    dl, dl
0x18000f3bf  jnz     short loc_18000F3C6
0x18000f3c1  test    r8b, r8b
0x18000f3c4  jz      short loc_18000F3DF
0x18000f3c6  mov     r9, [rcx+28h]
0x18000f3ca  mov     rcx, [rcx+10h]
0x18000f3ce  mov     [rsp+68h+var_30], rdi
0x18000f3d3  mov     [rsp+68h+var_38], 14h
0x18000f3da  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000f3df  mov     eax, 20h ; ' '
0x18000f3e4  mov     cs:hModule, rsi
0x18000f3eb  xorps   xmm0, xmm0
0x18000f3ee  mov     cs:dword_180044A80, eax
0x18000f3f4  xor     r9d, r9d; lpName
0x18000f3f7  mov     cs:dword_180044A8C, eax
0x18000f3fd  xor     r8d, r8d; bInitialState
0x18000f400  mov     cs:dword_180044A98, eax
0x18000f406  mov     edx, ebx; bManualReset
0x18000f408  movdqa  cs:pv, xmm0
0x18000f410  xor     ecx, ecx; lpEventAttributes
0x18000f412  mov     cs:qword_180044A70, rsi
0x18000f419  mov     cs:qword_180044A78, rsi
0x18000f420  mov     cs:qword_180044A84, 8
0x18000f42b  mov     cs:dword_180044A90, ebx
0x18000f431  mov     cs:dword_180044A94, 0Ah
0x18000f43b  mov     cs:qword_180044AD8, rsi
0x18000f442  mov     cs:hServiceStatus, rsi
0x18000f449  call    cs:__imp_CreateEventW
0x18000f44f  xorps   xmm0, xmm0
0x18000f452  mov     cs:hEvent, rsi
0x18000f459  xorps   xmm1, xmm1
0x18000f45c  mov     cs:?Globals@@3VBthServGlobals@@A, rax; BthServGlobals Globals
0x18000f463  movups  xmmword ptr cs:ServiceStatus.dwServiceType, xmm0
0x18000f46a  xor     r8d, r8d; pcbe
0x18000f46d  lea     rcx, ?PolicyTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000f474  xor     edx, edx; pv
0x18000f476  movups  xmmword ptr cs:ServiceStatus.dwWin32ExitCode, xmm0
0x18000f47d  movups  cs:xmmword_180044B08, xmm0
0x18000f484  movups  cs:hObject, xmm1
0x18000f48b  call    cs:__imp_CreateThreadpoolTimer
0x18000f491  mov     rcx, cs:qword_180044BA8
0x18000f498  mov     cs:pti, rax
0x18000f49f  mov     [rbp+arg_8], esi
0x18000f4a2  mov     cs:qword_180044BA8, rsi
0x18000f4a9  test    rcx, rcx
0x18000f4ac  jz      short loc_18000F4BB
0x18000f4ae  mov     rax, [rcx]
0x18000f4b1  mov     edx, ebx
0x18000f4b3  mov     rax, [rax]
0x18000f4b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4bb  lea     rax, [rbp+arg_8]
0x18000f4bf  lea     rcx, [rbp+var_10]
0x18000f4c3  mov     [rbp+var_10], rax
0x18000f4c7  call    wil__ResultFromException__lambda_c16bf91101c9118b5e2e61d840e8728a___
0x18000f4cc  mov     [rbp+arg_8], eax
0x18000f4cf  test    eax, eax
0x18000f4d1  jns     short loc_18000F517
0x18000f4d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4da  cmp     rcx, r15
0x18000f4dd  jz      short loc_18000F4E7
0x18000f4df  cmp     byte ptr [rcx+19h], 3
0x18000f4e3  mov     dl, bl
0x18000f4e5  jnb     short loc_18000F4EA
0x18000f4e7  mov     dl, sil
0x18000f4ea  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000f4f1  setnz   r8b
0x18000f4f5  test    dl, dl
0x18000f4f7  jnz     short loc_18000F4FE
0x18000f4f9  test    r8b, r8b
0x18000f4fc  jz      short loc_18000F517
0x18000f4fe  mov     r9, [rcx+28h]
0x18000f502  mov     rcx, [rcx+10h]
0x18000f506  mov     [rsp+68h+var_30], rdi
0x18000f50b  mov     [rsp+68h+var_38], 15h
0x18000f512  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000f517  mov     rdi, cs:qword_180044BC0
0x18000f51e  mov     cs:qword_180044BC0, rsi
0x18000f525  test    rdi, rdi
0x18000f528  jz      short loc_18000F53F
0x18000f52a  mov     rcx, rdi; this
0x18000f52d  call    ??1BthServDeviceRefresher@BthServ@Services@Bluetooth@Microsoft@@QEAA@XZ; Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::~BthServDeviceRefresher(void)
0x18000f532  mov     edx, 28h ; '('; struct std::nothrow_t *
0x18000f537  mov     rcx, rdi; void *
0x18000f53a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f53f  call    wil__ResultFromException__lambda_55b676508b23d6fc517a7e1a7ea2e59f___
0x18000f544  test    eax, eax
0x18000f546  jns     short loc_18000F595
0x18000f548  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f54f  cmp     rcx, r15
0x18000f552  jz      short loc_18000F55C
0x18000f554  cmp     byte ptr [rcx+19h], 3
0x18000f558  mov     dl, bl
0x18000f55a  jnb     short loc_18000F55F
0x18000f55c  mov     dl, sil
0x18000f55f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000f566  setnz   r8b
0x18000f56a  test    dl, dl
0x18000f56c  jnz     short loc_18000F573
0x18000f56e  test    r8b, r8b
0x18000f571  jz      short loc_18000F595
0x18000f573  mov     r9, [rcx+28h]
0x18000f577  lea     rdi, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000f57e  mov     rcx, [rcx+10h]
0x18000f582  mov     [rsp+68h+var_30], rdi
0x18000f587  mov     [rsp+68h+var_38], 16h
0x18000f58e  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000f593  jmp     short loc_18000F59C
0x18000f595  lea     rdi, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000f59c  xor     r8d, r8d; lpName
0x18000f59f  mov     cs:qword_180044B38, rsi
0x18000f5a6  xor     edx, edx; bInitialOwner
0x18000f5a8  mov     cs:qword_180044B40, rsi
0x18000f5af  xor     ecx, ecx; lpMutexAttributes
0x18000f5b1  call    cs:__imp_CreateMutexW
0x18000f5b7  xor     r8d, r8d; lpName
0x18000f5ba  mov     cs:dword_180044B58, ebx
0x18000f5c0  xor     edx, edx; bInitialOwner
0x18000f5c2  mov     cs:hMutex, rax
0x18000f5c9  xor     ecx, ecx; lpMutexAttributes
0x18000f5cb  mov     cs:dword_180044B5C, ebx
0x18000f5d1  call    cs:__imp_CreateMutexW
0x18000f5d7  mov     cs:qword_180044B50, rax
0x18000f5de  mov     r9d, 20019h; samDesired
0x18000f5e4  xor     r8d, r8d; ulOptions
0x18000f5e7  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Bt"...
0x18000f5ee  lea     rax, [rbp+hKey]
0x18000f5f2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f5f9  mov     [rsp+68h+phkResult], rax; phkResult
0x18000f5fe  call    cs:__imp_RegOpenKeyExW
0x18000f604  test    eax, eax
0x18000f606  jnz     loc_18000F707
0x18000f60c  mov     rcx, [rbp+hKey]; hKey
0x18000f610  lea     rax, [rbp+cbData]
0x18000f614  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18000f619  lea     r9, [rbp+Type]; lpType
0x18000f61d  lea     rax, [rbp+Data]
0x18000f621  mov     [rbp+cbData], 4
0x18000f628  xor     r8d, r8d; lpReserved
0x18000f62b  mov     [rsp+68h+phkResult], rax; lpData
0x18000f630  lea     rdx, aChannelavoidan; "ChannelAvoidanceRange"
0x18000f637  call    cs:__imp_RegQueryValueExW
0x18000f63d  test    eax, eax
0x18000f63f  jnz     short loc_18000F6A6
0x18000f641  cmp     [rbp+Type], 4
0x18000f645  jnz     short loc_18000F6A6
0x18000f647  cmp     [rbp+cbData], 4
0x18000f64b  jnz     short loc_18000F6A6
0x18000f64d  mov     eax, [rbp+Data]
0x18000f650  mov     cs:dword_180044B94, eax
0x18000f656  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f65d  cmp     rcx, r15
0x18000f660  jz      short loc_18000F66A
0x18000f662  cmp     byte ptr [rcx+19h], 4
0x18000f666  mov     dl, bl
0x18000f668  jnb     short loc_18000F66D
0x18000f66a  mov     dl, sil
0x18000f66d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000f674  setnz   r8b
0x18000f678  test    dl, dl
0x18000f67a  jnz     short loc_18000F681
0x18000f67c  test    r8b, r8b
0x18000f67f  jz      short loc_18000F6B5
0x18000f681  mov     r9, [rcx+28h]
0x18000f685  mov     rcx, [rcx+10h]
0x18000f689  mov     [rsp+68h+var_20], eax
0x18000f68d  mov     [rsp+68h+var_30], rdi
0x18000f692  mov     [rsp+68h+var_38], 17h
0x18000f699  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18000f69e  mov     eax, cs:dword_180044B94
0x18000f6a4  jmp     short loc_18000F6AE
0x18000f6a6  mov     eax, esi
0x18000f6a8  mov     cs:dword_180044B94, eax
0x18000f6ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6b5  cmp     eax, 3Bh ; ';'
0x18000f6b8  jbe     short loc_18000F6FD
0x18000f6ba  cmp     rcx, r15
0x18000f6bd  jz      short loc_18000F6C7
0x18000f6bf  cmp     byte ptr [rcx+19h], 3
0x18000f6c3  mov     dl, bl
0x18000f6c5  jnb     short loc_18000F6CA
0x18000f6c7  mov     dl, sil
0x18000f6ca  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000f6d1  setnz   r8b
0x18000f6d5  test    dl, dl
0x18000f6d7  jnz     short loc_18000F6DE
0x18000f6d9  test    r8b, r8b
0x18000f6dc  jz      short loc_18000F6F7
0x18000f6de  mov     r9, [rcx+28h]
0x18000f6e2  mov     rcx, [rcx+10h]
0x18000f6e6  mov     [rsp+68h+var_30], rdi
0x18000f6eb  mov     [rsp+68h+var_38], 18h
0x18000f6f2  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000f6f7  mov     cs:dword_180044B94, esi
0x18000f6fd  mov     rcx, [rbp+hKey]; hKey
0x18000f701  call    cs:__imp_RegCloseKey
0x18000f707  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f70e  cmp     rcx, r15
0x18000f711  jz      short loc_18000F719
0x18000f713  cmp     byte ptr [rcx+19h], 5
0x18000f717  jnb     short loc_18000F71C
0x18000f719  mov     bl, sil
0x18000f71c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000f723  setnz   r8b
0x18000f727  test    bl, bl
0x18000f729  jnz     short loc_18000F730
0x18000f72b  test    r8b, r8b
0x18000f72e  jz      short loc_18000F74B
0x18000f730  mov     r9, [rcx+28h]
0x18000f734  mov     dl, bl
0x18000f736  mov     rcx, [rcx+10h]
0x18000f73a  mov     [rsp+68h+var_30], rdi
0x18000f73f  mov     [rsp+68h+var_38], 19h
0x18000f746  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000f74b  add     rsp, 68h
0x18000f74f  pop     r15
0x18000f751  pop     r12
0x18000f753  pop     rdi
0x18000f754  pop     rsi
0x18000f755  pop     rbx
0x18000f756  pop     rbp
0x18000f757  retn
```
