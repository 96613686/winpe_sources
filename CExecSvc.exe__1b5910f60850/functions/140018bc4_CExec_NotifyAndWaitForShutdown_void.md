# CExec::NotifyAndWaitForShutdown(void)

- ea: `0x140018bc4`
- end: `0x140018e7e`
- name: `?NotifyAndWaitForShutdown@CExec@@YA_NXZ`
- size: `698`
- prototype: `char __fastcall(CExec *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000c340`

## callees

- `0x140002310`
- `0x140002ecc`
- `0x14000d338`
- `0x140018780`
- `0x140018bc4`
- `0x1400192a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140018bf5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140018bf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140018dfe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140018e26`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140018dfe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140018e26`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018d45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018d78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018d45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018d78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018dba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018dcf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018dba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018dcf`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x140018df1`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x140018df1`
- `ntdll!CsrClientCallServer` at `0x140018c86`
- `ntdll!CsrClientCallServer` at `0x140018c86`

## string_xrefs

- `0x140018e37`: `onecore\vm\common\vml\VmRegistry.h`
- `0x140018e6c`: `onecore\vm\common\vml\VmRegistry.h`
- `0x140018cb1`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140018d37`: `SYSTEM\CurrentControlSet\Services`

## pseudocode

```c
char __fastcall CExec::NotifyAndWaitForShutdown(CExec *this)
{
  char v1; // di
  __int64 *v2; // rbx
  NTSTATUS v3; // eax
  __int64 **v4; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  unsigned int v7; // eax
  unsigned int v8; // eax
  const unsigned __int16 *v9; // rdx
  DWORD v10; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  char *v14; // [rsp+28h] [rbp-D8h]
  RTL_SRWLOCK *v15; // [rsp+30h] [rbp-D0h]
  __int64 v16; // [rsp+38h] [rbp-C8h]
  HKEY v17; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v18; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  _BYTE ApiMessage[64]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v21; // [rsp+C0h] [rbp-40h]
  __int64 v22; // [rsp+D0h] [rbp-30h]
  int v23; // [rsp+D8h] [rbp-28h]
  __int64 v24; // [rsp+DCh] [rbp-24h]
  int v25; // [rsp+E4h] [rbp-1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+478h] [rbp+378h]

  AcquireSRWLockShared(&CExec::g_ContainerProcessesLock);
  v15 = &CExec::g_ContainerProcessesLock;
  LOBYTE(v16) = 1;
  v1 = 1;
  v2 = *(__int64 **)CExec::g_ContainerProcesses;
  while ( !*((_BYTE *)v2 + 25) )
  {
    memset_0(ApiMessage, 0, 0x3B8u);
    v21 = 0;
    v22 = 0;
    v23 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
    v24 = 0;
    v25 = 0;
    v22 = *(unsigned int *)(v2[5] + 32);
    v23 = 6;
    v3 = CsrClientCallServer(ApiMessage, 0, (CSR_API_NUMBER)0x30401, 0x28u);
    if ( v3 < 0 )
    {
      LODWORD(v14) = *(_DWORD *)(v2[5] + 32);
      wil::details::in1diag3::Log_NtStatusMsg(
        retaddr,
        (void *)0x1EE,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        (const char *)(unsigned int)v3,
        (int)"%d",
        v14,
        v15,
        v16);
      v1 = 0;
    }
    v4 = (__int64 **)v2[2];
    if ( *((_BYTE *)v4 + 25) )
    {
      for ( i = (__int64 *)v2[1]; !*((_BYTE *)i + 25) && v2 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v2 = i;
      v2 = i;
    }
    else
    {
      v2 = (__int64 *)v2[2];
      for ( j = *v4; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v2 = j;
    }
  }
  if ( !v1 )
  {
LABEL_27:
    ReleaseSRWLockShared(&CExec::g_ContainerProcessesLock);
    return 0;
  }
  hKey = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services", 0, 0x80000000, &hKey);
  if ( v7 )
  {
    if ( v7 == 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x129,
        (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
        (const char *)2,
        phkResult);
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1F9,
      (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
      (const char *)v7,
      phkResult);
  }
  v17 = 0;
  v18 = 0;
  v8 = RegOpenKeyExW(hKey, L"cexecsvc", 0, 0x80000000, &v17);
  if ( v8 )
  {
    if ( v8 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1F9,
        (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
        (const char *)v8,
        phkResulta);
  }
  else if ( (unsigned int)Vml::VmRegistryKey::QueryValue((Vml::VmRegistryKey *)&v17, v9, &v18) )
  {
    v10 = 1000 * v18;
    goto LABEL_21;
  }
  v10 = 5000;
LABEL_21:
  if ( v17 )
  {
    RegCloseKey(v17);
    v17 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  while ( qword_14003A4B8 )
  {
    if ( !SleepConditionVariableSRW(&CExec::g_ContainerProcessesEmptySignal, &CExec::g_ContainerProcessesLock, v10, 1u) )
      goto LABEL_27;
  }
  ReleaseSRWLockShared(&CExec::g_ContainerProcessesLock);
  return 1;
}

```

## disassembly

```asm
0x140018bc4  push    rbp
0x140018bc6  push    rbx
0x140018bc7  push    rsi
0x140018bc8  push    rdi
0x140018bc9  push    r14
0x140018bcb  lea     rbp, [rsp-350h]
0x140018bd3  sub     rsp, 450h
0x140018bda  mov     rax, cs:__security_cookie
0x140018be1  xor     rax, rsp
0x140018be4  mov     [rbp+370h+var_30], rax
0x140018beb  lea     r14, ?g_ContainerProcessesLock@CExec@@3VVmSlimReaderWriterLock@Vml@@A; Vml::VmSlimReaderWriterLock CExec::g_ContainerProcessesLock
0x140018bf2  mov     rcx, r14; SRWLock
0x140018bf5  call    cs:__imp_AcquireSRWLockShared
0x140018bfb  mov     [rsp+470h+var_440], r14
0x140018c00  mov     byte ptr [rsp+470h+var_438], 1
0x140018c05  mov     dil, 1
0x140018c08  mov     rbx, cs:?g_ContainerProcesses@CExec@@3V?$map@KV?$shared_ptr@UProcessTracker@CExec@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@@2@@std@@A; std::map<ulong,std::shared_ptr<CExec::ProcessTracker>> CExec::g_ContainerProcesses
0x140018c0f  mov     rbx, [rbx]
0x140018c12  xor     esi, esi
0x140018c14  cmp     [rbx+19h], sil
0x140018c18  jnz     loc_140018D14
0x140018c1e  xor     edx, edx; Val
0x140018c20  mov     r8d, 3B8h; Size
0x140018c26  lea     rcx, [rbp+370h+ApiMessage]; void *
0x140018c2a  call    memset_0
0x140018c2f  xorps   xmm0, xmm0
0x140018c32  xor     eax, eax
0x140018c34  movups  [rsp+470h+var_420], xmm0
0x140018c39  mov     [rsp+470h+var_410], rax
0x140018c3e  movdqu  [rbp+370h+var_3B0], xmm0
0x140018c43  movsd   [rbp+370h+var_3A0], xmm0
0x140018c48  psrldq  xmm0, 8
0x140018c4d  movd    [rbp+370h+var_398], xmm0
0x140018c52  movsd   xmm0, qword ptr [rsp+470h+var_420+0Ch]
0x140018c58  movsd   [rbp+370h+var_394], xmm0
0x140018c5d  mov     eax, dword ptr [rsp+470h+var_410+4]
0x140018c61  mov     [rbp+370h+var_38C], eax
0x140018c64  mov     rax, [rbx+28h]
0x140018c68  mov     ecx, [rax+20h]
0x140018c6b  mov     [rbp+370h+var_3A0], rcx
0x140018c6f  mov     [rbp+370h+var_398], 6
0x140018c76  xor     edx, edx; CaptureBuffer
0x140018c78  lea     r9d, [rdx+28h]; DataLength
0x140018c7c  mov     r8d, 30401h; ApiNumber
0x140018c82  lea     rcx, [rbp+370h+ApiMessage]; ApiMessage
0x140018c86  call    cs:__imp_CsrClientCallServer
0x140018c8c  mov     r9d, eax; char *
0x140018c8f  test    eax, eax
0x140018c91  jns     short loc_140018CC5
0x140018c93  mov     rax, [rbx+28h]
0x140018c97  mov     rcx, [rbp+378h]; this
0x140018c9e  mov     eax, [rax+20h]
0x140018ca1  mov     dword ptr [rsp+470h+var_448], eax; char *
0x140018ca5  lea     rax, aD; "%d"
0x140018cac  mov     [rsp+470h+phkResult], rax; int
0x140018cb1  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\service\\cexec\\l"...
0x140018cb8  mov     edx, 1EEh; void *
0x140018cbd  call    ?Log_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x140018cc2  mov     dil, sil
0x140018cc5  mov     rcx, [rbx+10h]
0x140018cc9  cmp     [rcx+19h], sil
0x140018ccd  jz      short loc_140018CF0
0x140018ccf  mov     rax, [rbx+8]
0x140018cd3  jmp     short loc_140018CE2
0x140018cd5  cmp     rbx, [rax+10h]
0x140018cd9  jnz     short loc_140018CE8
0x140018cdb  mov     rbx, rax
0x140018cde  mov     rax, [rax+8]
0x140018ce2  cmp     [rax+19h], sil
0x140018ce6  jz      short loc_140018CD5
0x140018ce8  mov     rbx, rax
0x140018ceb  jmp     loc_140018C14
0x140018cf0  mov     rbx, rcx
0x140018cf3  mov     rcx, [rcx]
0x140018cf6  cmp     [rcx+19h], sil
0x140018cfa  jnz     loc_140018C14
0x140018d00  mov     rbx, rcx
0x140018d03  mov     rax, [rcx]
0x140018d06  mov     rcx, rax
0x140018d09  cmp     [rax+19h], sil
0x140018d0d  jz      short loc_140018D00
0x140018d0f  jmp     loc_140018C14
0x140018d14  test    dil, dil
0x140018d17  jz      loc_140018DFB
0x140018d1d  mov     [rsp+470h+hKey], rsi
0x140018d22  lea     rax, [rsp+470h+hKey]
0x140018d27  mov     [rsp+470h+phkResult], rax; unsigned int
0x140018d2c  mov     ebx, 80000000h
0x140018d31  mov     r9d, ebx; samDesired
0x140018d34  xor     r8d, r8d; ulOptions
0x140018d37  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services"
0x140018d3e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140018d45  call    cs:__imp_RegOpenKeyExW
0x140018d4b  test    eax, eax
0x140018d4d  jnz     loc_140018E30
0x140018d53  mov     [rsp+470h+var_408], rsi
0x140018d58  mov     [rsp+470h+var_400], esi
0x140018d5c  lea     rax, [rsp+470h+var_408]
0x140018d61  mov     [rsp+470h+phkResult], rax; unsigned int
0x140018d66  mov     r9d, ebx; samDesired
0x140018d69  xor     r8d, r8d; ulOptions
0x140018d6c  lea     rdx, Endpoint; "cexecsvc"
0x140018d73  mov     rcx, [rsp+470h+hKey]; hKey
0x140018d78  call    cs:__imp_RegOpenKeyExW
0x140018d7e  test    eax, eax
0x140018d80  jnz     short loc_140018DA2
0x140018d82  lea     r8, [rsp+470h+var_400]; unsigned int *
0x140018d87  lea     rcx, [rsp+470h+var_408]; this
0x140018d8c  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAK@Z; Vml::VmRegistryKey::QueryValue(ushort const *,ulong &)
0x140018d91  test    eax, eax
0x140018d93  jz      short loc_140018DAB
0x140018d95  mov     eax, [rsp+470h+var_400]
0x140018d99  imul    rbx, rax, 3E8h
0x140018da0  jmp     short loc_140018DB0
0x140018da2  cmp     eax, 2
0x140018da5  jnz     loc_140018E62
0x140018dab  mov     ebx, 1388h
0x140018db0  mov     rcx, [rsp+470h+var_408]; hKey
0x140018db5  test    rcx, rcx
0x140018db8  jz      short loc_140018DC5
0x140018dba  call    cs:__imp_RegCloseKey
0x140018dc0  mov     [rsp+470h+var_408], rsi
0x140018dc5  mov     rcx, [rsp+470h+hKey]; hKey
0x140018dca  test    rcx, rcx
0x140018dcd  jz      short loc_140018DD5
0x140018dcf  call    cs:__imp_RegCloseKey
0x140018dd5  cmp     cs:qword_14003A4B8, rsi
0x140018ddc  jz      short loc_140018E23
0x140018dde  mov     r9d, 1; Flags
0x140018de4  mov     r8d, ebx; dwMilliseconds
0x140018de7  mov     rdx, r14; SRWLock
0x140018dea  lea     rcx, ?g_ContainerProcessesEmptySignal@CExec@@3VVmConditionVariable@Vml@@A; ConditionVariable
0x140018df1  call    cs:__imp_SleepConditionVariableSRW
0x140018df7  test    eax, eax
0x140018df9  jnz     short loc_140018DD5
0x140018dfb  mov     rcx, r14; SRWLock
0x140018dfe  call    cs:__imp_ReleaseSRWLockShared
0x140018e04  xor     al, al
0x140018e06  mov     rcx, [rbp+370h+var_30]
0x140018e0d  xor     rcx, rsp; StackCookie
0x140018e10  call    __security_check_cookie
0x140018e15  add     rsp, 450h
0x140018e1c  pop     r14
0x140018e1e  pop     rdi
0x140018e1f  pop     rsi
0x140018e20  pop     rbx
0x140018e21  pop     rbp
0x140018e22  retn
0x140018e23  mov     rcx, r14; SRWLock
0x140018e26  call    cs:__imp_ReleaseSRWLockShared
0x140018e2c  mov     al, 1
0x140018e2e  jmp     short loc_140018E06
0x140018e30  mov     rcx, [rbp+378h]; this
0x140018e37  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x140018e3e  cmp     eax, 2
0x140018e41  jnz     short loc_140018E54
0x140018e43  mov     r9d, 2; char *
0x140018e49  mov     edx, 129h; void *
0x140018e4e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140018e54  mov     r9d, eax; char *
0x140018e57  mov     edx, 1F9h; void *
0x140018e5c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140018e62  mov     rcx, [rbp+378h]; this
0x140018e69  mov     r9d, eax; char *
0x140018e6c  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x140018e73  mov     edx, 1F9h; void *
0x140018e78  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
