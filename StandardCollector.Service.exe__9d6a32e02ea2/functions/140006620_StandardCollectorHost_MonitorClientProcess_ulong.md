# StandardCollectorHost::MonitorClientProcess(ulong)

- ea: `0x140006620`
- end: `0x1400067a6`
- name: `?MonitorClientProcess@StandardCollectorHost@@UEAAJK@Z`
- size: `390`
- prototype: `int __fastcall(StandardCollectorHost *this, HKEY, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003220`
- `0x140006620`
- `0x140010a70`
- `0x1400137e0`
- `0x14001473e`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x140006746`
- `KERNEL32!CreateThreadpoolTimer` at `0x140006746`
- `KERNEL32!GetLastError` at `0x140006758`
- `KERNEL32!GetLastError` at `0x140006758`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x14000670e`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x14000670e`
- `ADVAPI32!RegQueryValueExW` at `0x1400066a8`
- `ADVAPI32!RegQueryValueExW` at `0x1400066a8`
- `ADVAPI32!RegCloseKey` at `0x1400066c7`
- `ADVAPI32!RegCloseKey` at `0x1400066dc`
- `ADVAPI32!RegCloseKey` at `0x1400066c7`
- `ADVAPI32!RegCloseKey` at `0x1400066dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
int __fastcall StandardCollectorHost::MonitorClientProcess(
        StandardCollectorHost *this,
        HKEY a2,
        __int64 a3,
        unsigned int a4)
{
  unsigned int v4; // edi
  int v5; // eax
  bool v6; // r8
  HKEY v7; // rbx
  bool v8; // si
  RPC_STATUS v9; // eax
  signed int v10; // ecx
  signed int LastError; // eax
  HKEY hKey[4]; // [rsp+38h] [rbp-59h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+58h] [rbp-39h] BYREF
  _BYTE v15[56]; // [rsp+60h] [rbp-31h] BYREF
  unsigned int v16; // [rsp+98h] [rbp+7h]
  BYTE Data[4]; // [rsp+C8h] [rbp+37h] BYREF
  DWORD cbData; // [rsp+CCh] [rbp+3Bh] BYREF
  DWORD Type; // [rsp+D0h] [rbp+3Fh] BYREF

  memset(hKey, 0, 24);
  v4 = (unsigned int)a2;
  v5 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, a2, L"Software\\Microsoft\\VisualStudio\\DiagnosticsHub", a4);
  v7 = hKey[0];
  if ( v5
    || (*(_DWORD *)Data = 0,
        cbData = 4,
        RegQueryValueExW(hKey[0], L"ClientUsageTrackingEnabled", 0, &Type, Data, &cbData))
    || Type != 4 )
  {
    if ( v7 )
      RegCloseKey(v7);
  }
  else
  {
    v8 = *(_DWORD *)Data != 0;
    if ( v7 )
      RegCloseKey(v7);
    if ( !v8 )
      return 1;
  }
  if ( !v4 )
  {
    memset_0(v15, 0, 0x68u);
    RpcCallAttributes[0] = 2;
    RpcCallAttributes[1] = 16;
    v9 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
    v10 = (unsigned __int16)v9 | 0x80070000;
    if ( v9 <= 0 )
      v10 = v9;
    if ( v10 < 0 )
      goto LABEL_21;
    v4 = v16;
    if ( !v16 )
      return 1;
  }
  if ( !qword_140024848 )
  {
    qword_140024848 = (__int64)CreateThreadpoolTimer(
                                 anonymous_namespace_::ServiceLifetimeManager::HostShutdownMain,
                                 0,
                                 0);
    if ( !qword_140024848 )
    {
      LastError = GetLastError();
      v10 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v10 = LastError;
      if ( v10 < 0 )
      {
LABEL_21:
        _mm_lfence();
        return v10;
      }
    }
  }
  return DiagHubCommon::ProcessLifetimeMonitor::StartMonitoringProcess(
           (DiagHubCommon::ProcessLifetimeMonitor *)&dword_1400248A0,
           v4,
           v6);
}

```

## disassembly

```asm
0x140006620  mov     rax, rsp
0x140006623  mov     [rax+8], rbx
0x140006627  mov     [rax+18h], rsi
0x14000662b  mov     [rax+20h], rdi
0x14000662f  push    rbp
0x140006630  lea     rbp, [rax-5Fh]
0x140006634  sub     rsp, 0E0h
0x14000663b  mov     rax, cs:__security_cookie
0x140006642  xor     rax, rsp
0x140006645  mov     [rbp+57h+var_10], rax
0x140006649  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\VisualStudio\\Diag"...
0x140006650  mov     [rbp+57h+var_A8], 0
0x140006658  lea     rcx, [rbp+57h+hKey]; this
0x14000665c  mov     [rbp+57h+hKey], 0
0x140006664  mov     edi, edx
0x140006666  mov     [rbp+57h+var_A0], 0
0x14000666e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140006673  mov     rbx, [rbp+57h+hKey]
0x140006677  test    eax, eax
0x140006679  jnz     short loc_1400066D4
0x14000667b  mov     dword ptr [rbp+57h+Data], eax
0x14000667e  lea     r9, [rbp+57h+Type]; lpType
0x140006682  lea     rax, [rbp+57h+cbData]
0x140006686  mov     [rbp+57h+cbData], 4
0x14000668d  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x140006692  lea     rdx, aClientusagetra; "ClientUsageTrackingEnabled"
0x140006699  lea     rax, [rbp+57h+Data]
0x14000669d  xor     r8d, r8d; lpReserved
0x1400066a0  mov     rcx, rbx; hKey
0x1400066a3  mov     [rsp+0E0h+lpData], rax; lpData
0x1400066a8  call    cs:__imp_RegQueryValueExW
0x1400066ae  test    eax, eax
0x1400066b0  jnz     short loc_1400066D4
0x1400066b2  cmp     [rbp+57h+Type], 4
0x1400066b6  jnz     short loc_1400066D4
0x1400066b8  cmp     dword ptr [rbp+57h+Data], eax
0x1400066bb  setnz   sil
0x1400066bf  test    rbx, rbx
0x1400066c2  jz      short loc_1400066CD
0x1400066c4  mov     rcx, rbx; hKey
0x1400066c7  call    cs:__imp_RegCloseKey
0x1400066cd  test    sil, sil
0x1400066d0  jz      short loc_140006729
0x1400066d2  jmp     short loc_1400066E2
0x1400066d4  test    rbx, rbx
0x1400066d7  jz      short loc_1400066E2
0x1400066d9  mov     rcx, rbx; hKey
0x1400066dc  call    cs:__imp_RegCloseKey
0x1400066e2  mov     ebx, 80070000h
0x1400066e7  test    edi, edi
0x1400066e9  jnz     short loc_140006730
0x1400066eb  xor     edx, edx; Val
0x1400066ed  lea     r8d, [rdi+68h]; Size
0x1400066f1  lea     rcx, [rbp+57h+var_88]; void *
0x1400066f5  call    memset_0
0x1400066fa  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x1400066fe  mov     [rbp+57h+RpcCallAttributes], 2
0x140006705  xor     ecx, ecx; ClientBinding
0x140006707  mov     [rbp+57h+var_8C], 10h
0x14000670e  call    cs:__imp_RpcServerInqCallAttributesW
0x140006714  movzx   ecx, ax
0x140006717  or      ecx, ebx
0x140006719  test    eax, eax
0x14000671b  cmovle  ecx, eax
0x14000671e  test    ecx, ecx
0x140006720  js      short loc_14000676C
0x140006722  mov     edi, [rbp+57h+var_50]
0x140006725  test    edi, edi
0x140006727  jnz     short loc_140006730
0x140006729  mov     eax, 1
0x14000672e  jmp     short loc_140006781
0x140006730  cmp     cs:qword_140024848, 0
0x140006738  jnz     short loc_140006773
0x14000673a  xor     r8d, r8d; pcbe
0x14000673d  lea     rcx, _anonymous_namespace___ServiceLifetimeManager__HostShutdownMain; pfnti
0x140006744  xor     edx, edx; pv
0x140006746  call    cs:__imp_CreateThreadpoolTimer
0x14000674c  mov     cs:qword_140024848, rax
0x140006753  test    rax, rax
0x140006756  jnz     short loc_140006773
0x140006758  call    cs:__imp_GetLastError
0x14000675e  movzx   ecx, ax
0x140006761  or      ecx, ebx
0x140006763  test    eax, eax
0x140006765  cmovle  ecx, eax
0x140006768  test    ecx, ecx
0x14000676a  jns     short loc_140006773
0x14000676c  lfence
0x14000676f  mov     eax, ecx
0x140006771  jmp     short loc_140006781
0x140006773  mov     edx, edi; unsigned int
0x140006775  lea     rcx, dword_1400248A0; this
0x14000677c  call    ?StartMonitoringProcess@ProcessLifetimeMonitor@DiagHubCommon@@QEAAJI_N@Z; DiagHubCommon::ProcessLifetimeMonitor::StartMonitoringProcess(uint,bool)
0x140006781  mov     rcx, [rbp+57h+var_10]
0x140006785  xor     rcx, rsp; StackCookie
0x140006788  call    __security_check_cookie
0x14000678d  lea     r11, [rsp+0E0h+var_s0]
0x140006795  mov     rbx, [r11+10h]
0x140006799  mov     rsi, [r11+20h]
0x14000679d  mov     rdi, [r11+28h]
0x1400067a1  mov     rsp, r11
0x1400067a4  pop     rbp
0x1400067a5  retn
```
