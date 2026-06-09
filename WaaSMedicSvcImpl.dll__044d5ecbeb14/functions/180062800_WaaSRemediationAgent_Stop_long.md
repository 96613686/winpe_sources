# WaaSRemediationAgent::Stop(long *)

- ea: `0x180062800`
- end: `0x180062a5c`
- name: `?Stop@WaaSRemediationAgent@@UEAAJPEAJ@Z`
- size: `604`
- prototype: `__int64 __fastcall(WaaSRemediationAgent *__hidden this, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update`

## callees

- `0x180012330`
- `0x18002e81c`
- `0x180062800`
- `0x180067144`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062831`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062831`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062a3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062a3d`

## string_xrefs

- `0x18006284e`: `Remediation agent stop received an invalid return code pointer.`
- `0x180062873`: `Remediation agent is unexpectedly not initialized.`
- `0x180062838`: `Task stop requested.`
- `0x18006293c`: `Remediation agent failed to stop the remediation task! hr = 0x%08x`
- `0x180062957`: `Will attempt to stop WaasRemediation if it is in progress`
- `0x18006289a`: `Remediation agent cannot process the stop request since a service shutdown is in progress.`
- `0x1800628aa`: `Remediation agent received an unexpected stop request since it's not started yet.`
- `0x1800629ef`: `WaaSRemediationAgent stopped the task with hr = 0x%08x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WaaSRemediationAgent::Stop(WaaSRemediationAgent *this, unsigned int *a2)
{
  const struct _GUID *v4; // rcx
  const unsigned __int16 *v5; // rdx
  int v6; // ebx
  int v7; // eax
  int v8; // esi
  int v9; // eax
  void *v10; // rcx
  int v11; // eax
  int v12; // eax
  volatile signed __int32 *v13; // rsi
  __int64 v14; // rcx
  __int128 v16; // [rsp+20h] [rbp-10h] BYREF
  void *v17; // [rsp+60h] [rbp+30h] BYREF
  void ***v18; // [rsp+68h] [rbp+38h]

  v18 = &WaaSRemediationAgent::m_cancelLock;
  EnterCriticalSection(&stru_1800A4400);
  LogLevelW(5u, L"Task stop requested.");
  if ( a2 )
  {
    *a2 = 0;
    if ( *((_BYTE *)this + 112) )
    {
      if ( *((_BYTE *)this + 114) )
      {
        v6 = -2147024846;
        LogLevelW(2u, L"Remediation agent cannot process the stop request since a service shutdown is in progress.");
        goto LABEL_27;
      }
      if ( *((_BYTE *)this + 113) )
      {
        v17 = 0;
        v7 = WaasMedic::CWaasMedic::CreateInstance(v4, &v17);
        v8 = v7;
        if ( v7 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v17 + 40LL))(v17);
          v8 = v9;
          if ( v9 < 0 )
            LogLevelW(2u, L"Error encountered when cancelling WaasMedic! hr=0x%08X", (unsigned int)v9);
        }
        else
        {
          LogLevelW(2u, L"Error encountered when creating instance of WaasMedic! hr=0x%08X", (unsigned int)v7);
        }
        v6 = 0;
        if ( v8 == -2147216629 )
          v6 = -2147216629;
        v10 = v17;
        if ( v17 )
        {
          v17 = 0;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 16LL))(v10);
        }
        if ( v6 < 0 )
        {
          v16 = 0;
          LogLevelW(5u, L"Will attempt to stop WaasRemediation if it is in progress");
          v11 = WaasMedic::CWaasRemediation::CreateInstance(&v16);
          v6 = v11;
          if ( v11 >= 0 )
          {
            v12 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v16 + 32LL))(v16);
            v6 = v12;
            if ( v12 < 0 )
              LogLevelW(2u, L"Error encountered when initalizaing WaasRemediation! hr=0x%08X", (unsigned int)v12);
          }
          else
          {
            LogLevelW(2u, L"Error encountered when creating instance of WaasRemediation! hr=0x%08X", (unsigned int)v11);
          }
          v13 = (volatile signed __int32 *)*((_QWORD *)&v16 + 1);
          if ( *((_QWORD *)&v16 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
              if ( !_InterlockedDecrement(v13 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
            }
          }
        }
        goto LABEL_27;
      }
      v5 = L"Remediation agent received an unexpected stop request since it's not started yet.";
    }
    else
    {
      v5 = L"Remediation agent is unexpectedly not initialized.";
    }
    v6 = -2147418113;
    LogLevelW(2u, v5);
LABEL_27:
    *a2 = v6;
    goto LABEL_28;
  }
  LogLevelW(2u, L"Remediation agent stop received an invalid return code pointer.");
LABEL_28:
  LogLevelW(4u, L"WaaSRemediationAgent stopped the task with hr = 0x%08x.", *a2);
  if ( *((_BYTE *)this + 112) && *((_BYTE *)this + 113) )
    *((_BYTE *)this + 113) = 0;
  v14 = *((_QWORD *)this + 16);
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    *((_QWORD *)this + 16) = 0;
  }
  LeaveCriticalSection(&stru_1800A4400);
  return 0;
}

```

## disassembly

```asm
0x180062800  mov     [rsp-28h+arg_10], rbx
0x180062805  mov     [rsp-28h+arg_18], rsi
0x18006280a  push    rbp
0x18006280b  push    rdi
0x18006280c  push    r12
0x18006280e  push    r14
0x180062810  push    r15
0x180062812  mov     rbp, rsp
0x180062815  sub     rsp, 30h
0x180062819  mov     r12, rdx
0x18006281c  mov     r14, rcx
0x18006281f  lea     rax, ?m_cancelLock@WaaSRemediationAgent@@1VCLock@WaasMedic@@A; WaasMedic::CLock WaaSRemediationAgent::m_cancelLock
0x180062826  mov     [rbp+arg_8], rax
0x18006282a  lea     rcx, stru_1800A4400; lpCriticalSection
0x180062831  call    cs:__imp_EnterCriticalSection
0x180062837  nop
0x180062838  lea     rdx, aTaskStopReques; "Task stop requested."
0x18006283f  mov     ecx, 5; unsigned __int8
0x180062844  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180062849  test    r12, r12
0x18006284c  jnz     short loc_180062864
0x18006284e  lea     rdx, aRemediationAge_7; "Remediation agent stop received an inva"...
0x180062855  lea     ecx, [r12+2]; unsigned __int8
0x18006285a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006285f  jmp     loc_1800629EB
0x180062864  mov     dword ptr [r12], 0
0x18006286c  cmp     byte ptr [r14+70h], 0
0x180062871  jnz     short loc_18006288E
0x180062873  lea     rdx, aRemediationAge_0; "Remediation agent is unexpectedly not i"...
0x18006287a  mov     ebx, 8000FFFFh
0x18006287f  mov     ecx, 2; unsigned __int8
0x180062884  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180062889  jmp     loc_1800629E7
0x18006288e  cmp     byte ptr [r14+72h], 0
0x180062893  jz      short loc_1800628A3
0x180062895  mov     ebx, 80070032h
0x18006289a  lea     rdx, aRemediationAge_2; "Remediation agent cannot process the st"...
0x1800628a1  jmp     short loc_18006287F
0x1800628a3  cmp     byte ptr [r14+71h], 0
0x1800628a8  jnz     short loc_1800628B3
0x1800628aa  lea     rdx, aRemediationAge_6; "Remediation agent received an unexpecte"...
0x1800628b1  jmp     short loc_18006287A
0x1800628b3  mov     [rbp+arg_0], 0
0x1800628bb  lea     rdx, [rbp+arg_0]; void **
0x1800628bf  call    ?CreateInstance@CWaasMedic@WaasMedic@@SAJAEBU_GUID@@PEAPEAX@Z; WaasMedic::CWaasMedic::CreateInstance(_GUID const &,void * *)
0x1800628c4  mov     esi, eax
0x1800628c6  mov     edi, 2
0x1800628cb  test    eax, eax
0x1800628cd  jns     short loc_1800628D8
0x1800628cf  lea     rdx, aErrorEncounter_3; "Error encountered when creating instanc"...
0x1800628d6  jmp     short loc_1800628F5
0x1800628d8  mov     rcx, [rbp+arg_0]
0x1800628dc  mov     rax, [rcx]
0x1800628df  mov     rax, [rax+28h]
0x1800628e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800628e8  mov     esi, eax
0x1800628ea  test    eax, eax
0x1800628ec  jns     short loc_180062900
0x1800628ee  lea     rdx, aErrorEncounter_14; "Error encountered when cancelling WaasM"...
0x1800628f5  mov     r8d, eax
0x1800628f8  mov     ecx, edi; unsigned __int8
0x1800628fa  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800628ff  nop
0x180062900  xor     ebx, ebx
0x180062902  cmp     esi, 8004130Bh
0x180062908  cmovz   ebx, esi
0x18006290b  mov     rcx, [rbp+arg_0]
0x18006290f  test    rcx, rcx
0x180062912  jz      short loc_180062929
0x180062914  mov     [rbp+arg_0], 0
0x18006291c  mov     rax, [rcx]
0x18006291f  mov     rax, [rax+10h]
0x180062923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062928  nop
0x180062929  test    ebx, ebx
0x18006292b  jns     loc_1800629E7
0x180062931  cmp     ebx, 8004130Bh
0x180062937  jz      short loc_18006294F
0x180062939  mov     r8d, ebx
0x18006293c  lea     rdx, aRemediationAge_3; "Remediation agent failed to stop the re"...
0x180062943  mov     ecx, edi; unsigned __int8
0x180062945  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006294a  jmp     loc_1800629E7
0x18006294f  xorps   xmm0, xmm0
0x180062952  movdqu  [rbp+var_10], xmm0
0x180062957  lea     rdx, aWillAttemptToS; "Will attempt to stop WaasRemediation if"...
0x18006295e  mov     ecx, 5; unsigned __int8
0x180062963  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180062968  lea     rcx, [rbp+var_10]
0x18006296c  call    ?CreateInstance@CWaasRemediation@WaasMedic@@SAJAEAV?$shared_ptr@VCWaasRemediation@WaasMedic@@@std@@@Z; WaasMedic::CWaasRemediation::CreateInstance(std::shared_ptr<WaasMedic::CWaasRemediation> &)
0x180062971  mov     ebx, eax
0x180062973  test    eax, eax
0x180062975  jns     short loc_180062980
0x180062977  lea     rdx, aErrorEncounter_13; "Error encountered when creating instanc"...
0x18006297e  jmp     short loc_18006299D
0x180062980  mov     rcx, qword ptr [rbp+var_10]
0x180062984  mov     rax, [rcx]
0x180062987  mov     rax, [rax+20h]
0x18006298b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062990  mov     ebx, eax
0x180062992  test    eax, eax
0x180062994  jns     short loc_1800629A8
0x180062996  lea     rdx, aErrorEncounter_12; "Error encountered when initalizaing Waa"...
0x18006299d  mov     r8d, eax
0x1800629a0  mov     ecx, edi; unsigned __int8
0x1800629a2  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800629a7  nop
0x1800629a8  mov     rsi, qword ptr [rbp+var_10+8]
0x1800629ac  test    rsi, rsi
0x1800629af  jz      short loc_1800629E7
0x1800629b1  or      edi, 0FFFFFFFFh
0x1800629b4  mov     eax, edi
0x1800629b6  lock xadd [rsi+8], eax
0x1800629bb  add     eax, edi
0x1800629bd  jnz     short loc_1800629E7
0x1800629bf  mov     rax, [rsi]
0x1800629c2  mov     rcx, rsi
0x1800629c5  mov     rax, [rax]
0x1800629c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800629cd  mov     eax, edi
0x1800629cf  lock xadd [rsi+0Ch], eax
0x1800629d4  add     eax, edi
0x1800629d6  jnz     short loc_1800629E7
0x1800629d8  mov     rax, [rsi]
0x1800629db  mov     rcx, rsi
0x1800629de  mov     rax, [rax+8]
0x1800629e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800629e7  mov     [r12], ebx
0x1800629eb  mov     r8d, [r12]
0x1800629ef  lea     rdx, aWaasremediatio_1; "WaaSRemediationAgent stopped the task w"...
0x1800629f6  mov     ecx, 4; unsigned __int8
0x1800629fb  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180062a00  cmp     byte ptr [r14+70h], 0
0x180062a05  jz      short loc_180062A13
0x180062a07  cmp     byte ptr [r14+71h], 0
0x180062a0c  jz      short loc_180062A13
0x180062a0e  mov     byte ptr [r14+71h], 0
0x180062a13  mov     rcx, [r14+80h]
0x180062a1a  test    rcx, rcx
0x180062a1d  jz      short loc_180062A36
0x180062a1f  mov     rax, [rcx]
0x180062a22  mov     rax, [rax+10h]
0x180062a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a2b  mov     qword ptr [r14+80h], 0
0x180062a36  lea     rcx, stru_1800A4400; lpCriticalSection
0x180062a3d  call    cs:__imp_LeaveCriticalSection
0x180062a43  xor     eax, eax
0x180062a45  mov     rbx, [rsp+30h+arg_10]
0x180062a4a  mov     rsi, [rsp+30h+arg_18]
0x180062a4f  add     rsp, 30h
0x180062a53  pop     r15
0x180062a55  pop     r14
0x180062a57  pop     r12
0x180062a59  pop     rdi
0x180062a5a  pop     rbp
0x180062a5b  retn
```
