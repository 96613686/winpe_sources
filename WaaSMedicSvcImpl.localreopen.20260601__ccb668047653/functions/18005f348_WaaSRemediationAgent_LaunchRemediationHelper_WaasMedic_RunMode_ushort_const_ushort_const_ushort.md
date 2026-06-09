# WaaSRemediationAgent::LaunchRemediationHelper(WaasMedic::RunMode,ushort const *,ushort const *,ushort * *)

- ea: `0x18005f348`
- end: `0x18005f5f7`
- name: `?LaunchRemediationHelper@WaaSRemediationAgent@@AEAAJW4RunMode@WaasMedic@@PEBG1PEAPEAG@Z`
- size: `687`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned __int16 *, __int64)`
- caller_count: `4`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800487ec`
- `0x180055a10`
- `0x18005f600`
- `0x18005fa20`

## callees

- `0x1800050a0`
- `0x180005584`
- `0x180005bbc`
- `0x180008c2c`
- `0x180012330`
- `0x18001c554`
- `0x18002524c`
- `0x180025398`
- `0x180025470`
- `0x1800296b4`
- `0x18002e81c`
- `0x180035140`
- `0x18005f348`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f3a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f3a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f552`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f552`

## string_xrefs

- `0x18005f484`: `Error encountered when attempting WaasMedic initialization! hr=0x%08X`
- `0x18005f4bf`: `Error encountered during run of WaasMedic! hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaaSRemediationAgent::LaunchRemediationHelper(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned __int16 *a4,
        __int64 a5)
{
  __int64 v7; // rdi
  __int64 v8; // r14
  int IsWUConnected; // eax
  unsigned int v10; // ebx
  unsigned int v11; // r12d
  bool v12; // bl
  WaasMedic::SummaryEvent *v13; // rax
  int v14; // eax
  __int64 v15; // rsi
  int v16; // eax
  __int64 v17; // r9
  int v18; // eax
  volatile signed __int64 *v19; // rcx
  int v20; // esi
  volatile signed __int32 *v21; // rdi
  bool v23; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v24; // [rsp+34h] [rbp-CCh]
  unsigned __int16 *v25; // [rsp+38h] [rbp-C8h]
  __int128 v26; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h]
  WaasMedic::SummaryEvent *v28; // [rsp+58h] [rbp-A8h]
  char v29[144]; // [rsp+60h] [rbp-A0h] BYREF

  v25 = a4;
  v24 = a2;
  v26 = 0;
  v7 = 0;
  v23 = 0;
  v8 = a1 + 72;
  v27 = a1 + 72;
  if ( a1 != -72 )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  memset_0(v29, 0, 0x81u);
  IsWUConnected = WaasMedic::Policy::IsWUConnected(&v23);
  v10 = IsWUConnected;
  if ( IsWUConnected < 0 )
  {
    LogLevelW(
      2u,
      L"Error encountered while checking for zero exhaust policy on the device! hr=0x%08X",
      (unsigned int)IsWUConnected);
LABEL_5:
    v11 = v24;
    goto LABEL_19;
  }
  v12 = v23;
  if ( v23 )
  {
    v13 = (WaasMedic::SummaryEvent *)operator new(0xA8u, (const struct std::nothrow_t *)&std::nothrow);
    v28 = v13;
    if ( v13 )
      v7 = WaasMedic::SummaryEvent::SummaryEvent(v13);
    else
      v7 = 0;
    if ( !v7 )
    {
      v10 = -2147024882;
      LogLevelW(2u, L"Failed to allocate memory for SummaryEvent");
      goto LABEL_5;
    }
    *(_BYTE *)(v7 + 22) = v12;
    WaasMedic::SummaryEvent::SetVersion((WaasMedic::SummaryEvent *)v7);
  }
  v14 = WaasMedic::CWaasRemediation::CreateInstance(&v26);
  v10 = v14;
  if ( v14 < 0 )
  {
    LogLevelW(2u, L"Error encountered when creating instance of WaasMedic! hr=0x%08X", (unsigned int)v14);
    goto LABEL_5;
  }
  v15 = v26;
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)v26 + 8LL))(v26, *(_QWORD *)(a1 + 160), v7);
  v10 = v16;
  if ( v16 < 0 )
  {
    LogLevelW(2u, L"Error encountered when attempting WaasMedic initialization! hr=0x%08X", (unsigned int)v16);
    goto LABEL_5;
  }
  v17 = a3;
  v11 = v24;
  v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, __int64))(*(_QWORD *)v15 + 24LL))(
          v15,
          0,
          v24,
          v17,
          a5);
  v10 = v18;
  if ( v18 >= 0 )
    goto LABEL_20;
  LogLevelW(2u, L"Error encountered during run of WaasMedic! hr=0x%08X", (unsigned int)v18);
LABEL_19:
  LogLevelW(2u, L"Reporting failure to execute WaasMedic! hr=0x%08x", v10);
LABEL_20:
  v19 = *(volatile signed __int64 **)(a1 + 160);
  if ( !v19 )
  {
    v29[0] = 0;
LABEL_22:
    v20 = 0;
    goto LABEL_23;
  }
  if ( TraceLoggingCorrelationVector::ToStringImpl(
         (TraceLoggingCorrelationVector *)v19,
         _InterlockedExchangeAdd64(v19 + 17, 0),
         v29) )
  {
    goto LABEL_22;
  }
  v20 = -2147418113;
  LogLevelW(2u, L"Failed to get cV in WaasMedic engine. hr=0x%08x", 2147549183LL);
LABEL_23:
  if ( v7 )
  {
    *(_DWORD *)(v7 + 116) = v11;
    *(_DWORD *)(v7 + 100) = v20;
    WaasMedic::TelemetryCoreProvider::ReportSummary(v29, (struct WaasMedic::SummaryEvent *)v7, 1, v25);
    WaasMedic::SummaryEvent::~SummaryEvent((WaasMedic::SummaryEvent *)v7);
    operator delete((void *)v7, (const struct std::nothrow_t *)0xA8);
  }
  if ( (v10 & 0x80000000) == 0 )
    v10 = v20;
  LogLevelW(4u, L"Engine exiting. hr=0x%08X", v10);
  if ( v8 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 16));
  v21 = (volatile signed __int32 *)*((_QWORD *)&v26 + 1);
  if ( *((_QWORD *)&v26 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v26 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18005f348  push    rbp
0x18005f34a  push    rbx
0x18005f34b  push    rsi
0x18005f34c  push    rdi
0x18005f34d  push    r12
0x18005f34f  push    r13
0x18005f351  push    r14
0x18005f353  push    r15
0x18005f355  lea     rbp, [rsp-8]
0x18005f35a  sub     rsp, 108h
0x18005f361  mov     rax, cs:__security_cookie
0x18005f368  xor     rax, rsp
0x18005f36b  mov     [rbp+40h+var_50], rax
0x18005f36f  mov     [rsp+140h+var_108], r9
0x18005f374  mov     r12, r8
0x18005f377  mov     [rsp+140h+var_10C], edx
0x18005f37b  mov     r15, rcx
0x18005f37e  mov     r13, [rbp+40h+arg_20]
0x18005f382  xorps   xmm0, xmm0
0x18005f385  movdqu  [rsp+140h+var_100], xmm0
0x18005f38b  xor     edi, edi
0x18005f38d  mov     [rsp+140h+var_110], dil
0x18005f392  lea     r14, [rcx+48h]
0x18005f396  mov     [rsp+140h+var_F0], r14
0x18005f39b  test    r14, r14
0x18005f39e  jz      short loc_18005F3AB
0x18005f3a0  lea     rcx, [r14+10h]; lpCriticalSection
0x18005f3a4  call    cs:__imp_EnterCriticalSection
0x18005f3aa  nop
0x18005f3ab  xor     edx, edx; Val
0x18005f3ad  mov     r8d, 81h; Size
0x18005f3b3  lea     rcx, [rsp+140h+var_E0]; void *
0x18005f3b8  call    memset_0
0x18005f3bd  lea     rcx, [rsp+140h+var_110]; bool *
0x18005f3c2  call    ?IsWUConnected@Policy@WaasMedic@@SAJAEA_N@Z; WaasMedic::Policy::IsWUConnected(bool &)
0x18005f3c7  mov     ebx, eax
0x18005f3c9  mov     esi, 2
0x18005f3ce  test    eax, eax
0x18005f3d0  jns     short loc_18005F3ED
0x18005f3d2  lea     rdx, aErrorEncounter_11; "Error encountered while checking for ze"...
0x18005f3d9  mov     r8d, eax
0x18005f3dc  mov     ecx, esi; unsigned __int8
0x18005f3de  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f3e3  mov     r12d, [rsp+140h+var_10C]
0x18005f3e8  jmp     loc_18005F4D2
0x18005f3ed  mov     bl, [rsp+140h+var_110]
0x18005f3f1  test    bl, bl
0x18005f3f3  jz      short loc_18005F444
0x18005f3f5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005f3fc  mov     ecx, 0A8h; unsigned __int64
0x18005f401  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005f406  mov     [rsp+140h+var_E8], rax
0x18005f40b  test    rax, rax
0x18005f40e  jz      short loc_18005F41D
0x18005f410  mov     rcx, rax; this
0x18005f413  call    ??0SummaryEvent@WaasMedic@@QEAA@XZ; WaasMedic::SummaryEvent::SummaryEvent(void)
0x18005f418  mov     rdi, rax
0x18005f41b  jmp     short loc_18005F41F
0x18005f41d  xor     edi, edi
0x18005f41f  test    rdi, rdi
0x18005f422  jnz     short loc_18005F439
0x18005f424  mov     ebx, 8007000Eh
0x18005f429  lea     rdx, aFailedToAlloca_31; "Failed to allocate memory for SummaryEv"...
0x18005f430  mov     ecx, esi; unsigned __int8
0x18005f432  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f437  jmp     short loc_18005F3E3
0x18005f439  mov     [rdi+16h], bl
0x18005f43c  mov     rcx, rdi; this
0x18005f43f  call    ?SetVersion@SummaryEvent@WaasMedic@@QEAAXXZ; WaasMedic::SummaryEvent::SetVersion(void)
0x18005f444  lea     rcx, [rsp+140h+var_100]
0x18005f449  call    ?CreateInstance@CWaasRemediation@WaasMedic@@SAJAEAV?$shared_ptr@VCWaasRemediation@WaasMedic@@@std@@@Z; WaasMedic::CWaasRemediation::CreateInstance(std::shared_ptr<WaasMedic::CWaasRemediation> &)
0x18005f44e  mov     ebx, eax
0x18005f450  test    eax, eax
0x18005f452  jns     short loc_18005F460
0x18005f454  lea     rdx, aErrorEncounter_3; "Error encountered when creating instanc"...
0x18005f45b  jmp     loc_18005F3D9
0x18005f460  mov     rsi, qword ptr [rsp+140h+var_100]
0x18005f465  mov     rax, [rsi]
0x18005f468  mov     r8, rdi
0x18005f46b  mov     rdx, [r15+0A0h]
0x18005f472  mov     rcx, rsi
0x18005f475  mov     rax, [rax+8]
0x18005f479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f47e  mov     ebx, eax
0x18005f480  test    eax, eax
0x18005f482  jns     short loc_18005F495
0x18005f484  lea     rdx, aErrorEncounter_4; "Error encountered when attempting WaasM"...
0x18005f48b  mov     esi, 2
0x18005f490  jmp     loc_18005F3D9
0x18005f495  mov     rax, [rsi]
0x18005f498  mov     [rsp+140h+var_120], r13
0x18005f49d  mov     r9, r12
0x18005f4a0  mov     r12d, [rsp+140h+var_10C]
0x18005f4a5  mov     r8d, r12d
0x18005f4a8  xor     edx, edx
0x18005f4aa  mov     rcx, rsi
0x18005f4ad  mov     rax, [rax+18h]
0x18005f4b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f4b6  mov     ebx, eax
0x18005f4b8  test    eax, eax
0x18005f4ba  jns     short loc_18005F4E3
0x18005f4bc  mov     r8d, eax
0x18005f4bf  lea     rdx, aErrorEncounter_6; "Error encountered during run of WaasMed"...
0x18005f4c6  mov     esi, 2
0x18005f4cb  mov     ecx, esi; unsigned __int8
0x18005f4cd  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f4d2  mov     r8d, ebx
0x18005f4d5  lea     rdx, aReportingFailu; "Reporting failure to execute WaasMedic!"...
0x18005f4dc  mov     ecx, esi; unsigned __int8
0x18005f4de  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f4e3  mov     rcx, [r15+0A0h]; this
0x18005f4ea  test    rcx, rcx
0x18005f4ed  jnz     loc_18005F5BB
0x18005f4f3  mov     [rsp+140h+var_E0], cl
0x18005f4f7  xor     esi, esi
0x18005f4f9  test    rdi, rdi
0x18005f4fc  jz      short loc_18005F52F
0x18005f4fe  mov     [rdi+74h], r12d
0x18005f502  mov     [rdi+64h], esi
0x18005f505  mov     r9, [rsp+140h+var_108]; unsigned __int16 *
0x18005f50a  mov     r8b, 1; bool
0x18005f50d  mov     rdx, rdi; struct WaasMedic::SummaryEvent *
0x18005f510  lea     rcx, [rsp+140h+var_E0]; char *
0x18005f515  call    ?ReportSummary@TelemetryCoreProvider@WaasMedic@@SAXPEBDPEAVSummaryEvent@2@_NPEBG@Z; WaasMedic::TelemetryCoreProvider::ReportSummary(char const *,WaasMedic::SummaryEvent *,bool,ushort const *)
0x18005f51a  mov     rcx, rdi; this
0x18005f51d  call    ??1SummaryEvent@WaasMedic@@QEAA@XZ; WaasMedic::SummaryEvent::~SummaryEvent(void)
0x18005f522  mov     edx, 0A8h; struct std::nothrow_t *
0x18005f527  mov     rcx, rdi; void *
0x18005f52a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005f52f  test    ebx, ebx
0x18005f531  cmovns  ebx, esi
0x18005f534  mov     r8d, ebx
0x18005f537  lea     rdx, aEngineExitingH; "Engine exiting. hr=0x%08X"
0x18005f53e  mov     ecx, 4; unsigned __int8
0x18005f543  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f548  nop
0x18005f549  test    r14, r14
0x18005f54c  jz      short loc_18005F559
0x18005f54e  lea     rcx, [r14+10h]; lpCriticalSection
0x18005f552  call    cs:__imp_LeaveCriticalSection
0x18005f558  nop
0x18005f559  mov     rdi, qword ptr [rsp+140h+var_100+8]
0x18005f55e  test    rdi, rdi
0x18005f561  jz      short loc_18005F599
0x18005f563  or      esi, 0FFFFFFFFh
0x18005f566  mov     eax, esi
0x18005f568  lock xadd [rdi+8], eax
0x18005f56d  add     eax, esi
0x18005f56f  jnz     short loc_18005F599
0x18005f571  mov     rax, [rdi]
0x18005f574  mov     rcx, rdi
0x18005f577  mov     rax, [rax]
0x18005f57a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f57f  mov     eax, esi
0x18005f581  lock xadd [rdi+0Ch], eax
0x18005f586  add     eax, esi
0x18005f588  jnz     short loc_18005F599
0x18005f58a  mov     rax, [rdi]
0x18005f58d  mov     rcx, rdi
0x18005f590  mov     rax, [rax+8]
0x18005f594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f599  mov     eax, ebx
0x18005f59b  mov     rcx, [rbp+40h+var_50]
0x18005f59f  xor     rcx, rsp; StackCookie
0x18005f5a2  call    __security_check_cookie
0x18005f5a7  add     rsp, 108h
0x18005f5ae  pop     r15
0x18005f5b0  pop     r14
0x18005f5b2  pop     r13
0x18005f5b4  pop     r12
0x18005f5b6  pop     rdi
0x18005f5b7  pop     rsi
0x18005f5b8  pop     rbx
0x18005f5b9  pop     rbp
0x18005f5ba  retn
0x18005f5bb  xor     edx, edx
0x18005f5bd  lock xadd [rcx+88h], rdx; unsigned __int64
0x18005f5c6  lea     r8, [rsp+140h+var_E0]; char *
0x18005f5cb  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18005f5d0  test    al, al
0x18005f5d2  jnz     loc_18005F4F7
0x18005f5d8  mov     esi, 8000FFFFh
0x18005f5dd  mov     r8d, esi
0x18005f5e0  lea     rdx, aFailedToGetCvI_0; "Failed to get cV in WaasMedic engine. h"...
0x18005f5e7  mov     ecx, 2; unsigned __int8
0x18005f5ec  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f5f1  jmp     loc_18005F4F9
```
