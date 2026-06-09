# DspPumpContextInterruptHandlerThread(void *)

- ea: `0x14008f830`
- end: `0x14008fb64`
- name: `?DspPumpContextInterruptHandlerThread@@YAKPEAX@Z`
- size: `820`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x140002710`
- `0x140028474`
- `0x14003de5c`
- `0x14004c130`
- `0x14005d0e0`
- `0x14008f830`
- `0x140090000`
- `0x140090630`
- `0x140090e80`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14008fa44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14008fa44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14008fa82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14008fa82`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14008fa8d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14008fa8d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14008f9b7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14008f9b7`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14008f8b9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14008f8b9`
- `ntdll!NtSetTimerResolution` at `0x14008f868`
- `ntdll!NtSetTimerResolution` at `0x14008fb40`
- `ntdll!NtSetTimerResolution` at `0x14008f868`
- `ntdll!NtSetTimerResolution` at `0x14008fb40`
- `ntdll!NtClose` at `0x14008fb29`
- `ntdll!NtClose` at `0x14008fb29`
- `AVRT!AvThreadOpenTaskIndex` at `0x14008f88e`
- `AVRT!AvThreadOpenTaskIndex` at `0x14008f88e`

## pseudocode

```c
__int64 __fastcall DspPumpContextInterruptHandlerThread(HANDLE *Parameter)
{
  void *v2; // r15
  DWORD v3; // eax
  const char *v4; // r9
  char i; // r14
  unsigned int *v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // edi
  unsigned int v10; // esi
  unsigned int v11; // ecx
  __int64 v12; // r8
  __int64 v13; // r10
  __int64 v14; // r11
  unsigned int v15; // edi
  _QWORD **v16; // rax
  signed int v17; // edi
  _DWORD *v18; // rsi
  DWORD CurrentProcessId; // eax
  int v20; // r8d
  int v21; // r9d
  HANDLE CurrentProcess; // rax
  __int64 v23; // r10
  __int64 v25; // [rsp+20h] [rbp-99h]
  DWORD TaskIndex; // [rsp+40h] [rbp-79h] BYREF
  ULONG ActualResolution; // [rsp+44h] [rbp-75h] BYREF
  unsigned int v28; // [rsp+48h] [rbp-71h] BYREF
  int v29; // [rsp+4Ch] [rbp-6Dh] BYREF
  DWORD v30; // [rsp+50h] [rbp-69h] BYREF
  signed int v31; // [rsp+54h] [rbp-65h] BYREF
  void *v32; // [rsp+58h] [rbp-61h] BYREF
  _QWORD v33[2]; // [rsp+60h] [rbp-59h] BYREF
  HANDLE Handles[2]; // [rsp+70h] [rbp-49h] BYREF
  GUID v35; // [rsp+80h] [rbp-39h] BYREF
  int v36; // [rsp+90h] [rbp-29h]
  int v37; // [rsp+94h] [rbp-25h]
  int v38; // [rsp+98h] [rbp-21h]
  int v39; // [rsp+9Ch] [rbp-1Dh]
  __int128 v40; // [rsp+A0h] [rbp-19h]
  __int128 v41; // [rsp+B0h] [rbp-9h]
  unsigned int *v42; // [rsp+C0h] [rbp+7h]
  __int64 v43; // [rsp+C8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  ActualResolution = 0;
  NtSetTimerResolution(0xAu, 1u, &ActualResolution);
  v32 = 0;
  TaskIndex = 0;
  SetEngineThreadPriority(&TaskIndex, &v32);
  v2 = (void *)AvThreadOpenTaskIndex(v32);
  Handles[0] = Parameter[15];
  Handles[1] = Parameter[17];
  while ( 1 )
  {
    while ( 1 )
    {
      v3 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      if ( v3 )
        break;
      for ( i = 0; ; i = 1 )
      {
        v6 = (unsigned int *)Parameter[16];
        v7 = *v6;
        if ( (_DWORD)v7 == v6[1] )
          break;
        v8 = v6[10 * v7 + 2];
        v9 = v6[10 * v7 + 4];
        v10 = v6[10 * v7 + 5];
        v11 = v7 + 1;
        v12 = 4;
        *v6 = v11 < 5 ? v11 : 0;
        if ( **((_DWORD **)Parameter[11] + 11) > 4u
          && (unsigned __int8)tlgKeywordOn(*((_QWORD *)Parameter[11] + 11), 0x100000, 4) )
        {
          v29 = v8;
          v42 = &v28;
          v43 = v12;
          *(_QWORD *)&v41 = v33;
          *((_QWORD *)&v40 + 1) = v12;
          *(_QWORD *)&v40 = &v29;
          v28 = v9;
          LODWORD(v25) = 5;
          v33[0] = v14;
          *((_QWORD *)&v41 + 1) = 8;
          tlgWriteTransfer_EventWriteTransfer(v13, byte_1400D26C1, 0, 0, v25, &v35);
        }
        v15 = v9 - 1;
        if ( v15 )
        {
          if ( v15 == 1 )
          {
            (*(void (__fastcall **)(HANDLE, _QWORD, __int64, __int64))(*(_QWORD *)Parameter[13] + 24LL))(
              Parameter[13],
              v10,
              v12,
              v8);
            CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::OnDspPumpPassComplete((CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext *)(Parameter + 8));
          }
        }
        else
        {
          Sleep(1u);
          v39 = *((_DWORD *)Parameter + 36);
          v16 = (_QWORD **)Parameter[11];
          v35 = GUID_3c58e72b_cb3c_4076_93e8_9c528830f2d2;
          v36 = 11;
          v37 = 2;
          v40 = 0;
          v38 = 1;
          v41 = 0;
          v33[1] = 0;
          HIDWORD(v25) = 0;
          v17 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64))(*v16[15] + 40LL))(v16[15], &v35, 64);
          if ( v17 < 0 )
          {
            v18 = (_DWORD *)*((_QWORD *)Parameter[11] + 11);
            if ( *v18 > 2u )
            {
              CurrentProcessId = GetCurrentProcessId();
              v31 = v17;
              v30 = CurrentProcessId;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (_DWORD)v18,
                (unsigned int)&byte_1400D2677,
                v20,
                v21,
                (__int64)&v31,
                (__int64)&v30);
            }
            if ( (v17 & 0x1FFF0000) == 0x70000 )
              v17 = (unsigned __int16)v17;
            CurrentProcess = GetCurrentProcess();
            TerminateProcess(CurrentProcess, v17);
          }
        }
      }
      if ( !i
        && **((_DWORD **)Parameter[11] + 11) > 4u
        && (unsigned __int8)tlgKeywordOn(*((_QWORD *)Parameter[11] + 11), 0x100000, v7) )
      {
        LODWORD(v25) = 2;
        tlgWriteTransfer_EventWriteTransfer(v23, byte_1400D2649, 0, 0, v25, &v35);
      }
    }
    if ( v3 == 1 )
      break;
    if ( v3 == -1 )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0xAD,
               (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\AudioPumpDspInterruptHandler.inl",
               v4);
  }
  if ( v2 )
  {
    TaskIndex = 0;
    NtClose(v2);
  }
  ResetEngineThreadPriority(&v32);
  NtSetTimerResolution(0, 0, &ActualResolution);
  return 0;
}

```

## disassembly

```asm
0x14008f830  push    rbp
0x14008f832  push    rbx
0x14008f833  push    rsi
0x14008f834  push    rdi
0x14008f835  push    r14
0x14008f837  push    r15
0x14008f839  lea     rbp, [rsp-2Fh]
0x14008f83e  sub     rsp, 0E8h
0x14008f845  mov     rax, cs:__security_cookie
0x14008f84c  xor     rax, rsp
0x14008f84f  mov     [rbp+57h+var_40], rax
0x14008f853  mov     rbx, rcx
0x14008f856  mov     [rbp+57h+ActualResolution], 0
0x14008f85d  mov     ecx, 0Ah; RequestedResolution
0x14008f862  lea     r8, [rbp+57h+ActualResolution]; ActualResolution
0x14008f866  mov     dl, 1; SetOrUnset
0x14008f868  call    cs:__imp_NtSetTimerResolution
0x14008f86e  lea     rdx, [rbp+57h+var_B8]; void **
0x14008f872  mov     [rbp+57h+var_B8], 0
0x14008f87a  lea     rcx, [rbp+57h+TaskIndex]; TaskIndex
0x14008f87e  mov     [rbp+57h+TaskIndex], 0
0x14008f885  call    ?SetEngineThreadPriority@@YAJPEAKPEAPEAX@Z; SetEngineThreadPriority(ulong *,void * *)
0x14008f88a  mov     rcx, [rbp+57h+var_B8]
0x14008f88e  call    cs:__imp_AvThreadOpenTaskIndex
0x14008f894  mov     rcx, [rbx+78h]
0x14008f898  mov     r15, rax
0x14008f89b  mov     [rbp+57h+Handles], rcx
0x14008f89f  mov     rcx, [rbx+88h]
0x14008f8a6  mov     [rbp+57h+var_98], rcx
0x14008f8aa  xor     r8d, r8d; bWaitAll
0x14008f8ad  lea     rdx, [rbp+57h+Handles]; lpHandles
0x14008f8b1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x14008f8b5  lea     ecx, [r8+2]; nCount
0x14008f8b9  call    cs:__imp_WaitForMultipleObjects
0x14008f8bf  test    eax, eax
0x14008f8c1  jnz     loc_14008FAF5
0x14008f8c7  xor     r14b, r14b
0x14008f8ca  mov     rdx, [rbx+80h]
0x14008f8d1  mov     r8d, [rdx]
0x14008f8d4  cmp     r8d, [rdx+4]
0x14008f8d8  jz      loc_14008FA98
0x14008f8de  lea     rcx, [r8+r8*4]
0x14008f8e2  mov     r9d, [rdx+rcx*8+8]
0x14008f8e7  mov     r11d, [rdx+rcx*8+0Ch]
0x14008f8ec  mov     edi, [rdx+rcx*8+10h]
0x14008f8f0  mov     esi, [rdx+rcx*8+14h]
0x14008f8f4  lea     ecx, [r8+1]
0x14008f8f8  cmp     ecx, 5
0x14008f8fb  mov     r8d, 4
0x14008f901  sbb     eax, eax
0x14008f903  and     eax, ecx
0x14008f905  mov     [rdx], eax
0x14008f907  mov     rax, [rbx+58h]
0x14008f90b  mov     r10, [rax+58h]
0x14008f90f  mov     eax, [r10]
0x14008f912  cmp     eax, r8d
0x14008f915  jbe     short loc_14008F981
0x14008f917  mov     edx, 100000h
0x14008f91c  mov     rcx, r10
0x14008f91f  call    _tlgKeywordOn
0x14008f924  test    al, al
0x14008f926  jz      short loc_14008F981
0x14008f928  lea     rax, [rbp+57h+var_C8]
0x14008f92c  mov     [rbp+57h+var_C4], r9d
0x14008f930  mov     [rbp+57h+var_50], rax
0x14008f934  lea     rdx, byte_1400D26C1
0x14008f93b  lea     rax, [rbp+57h+var_B0]
0x14008f93f  mov     [rbp+57h+var_48], r8
0x14008f943  mov     qword ptr [rbp+57h+var_60], rax
0x14008f947  xor     r9d, r9d
0x14008f94a  lea     rax, [rbp+57h+var_C4]
0x14008f94e  mov     qword ptr [rbp+57h+var_70+8], r8
0x14008f952  mov     qword ptr [rbp+57h+var_70], rax
0x14008f956  xor     r8d, r8d
0x14008f959  lea     rax, [rbp+57h+var_90]
0x14008f95d  mov     [rbp+57h+var_C8], edi
0x14008f960  mov     [rsp+110h+var_E8], rax
0x14008f965  mov     rcx, r10
0x14008f968  mov     dword ptr [rsp+110h+var_F0], 5
0x14008f970  mov     [rbp+57h+var_B0], r11
0x14008f974  mov     qword ptr [rbp+57h+var_60+8], 8
0x14008f97c  call    _tlgWriteTransfer_EventWriteTransfer
0x14008f981  mov     r14b, 1
0x14008f984  sub     edi, 1
0x14008f987  jz      short loc_14008F9B2
0x14008f989  cmp     edi, 1
0x14008f98c  jnz     loc_14008F8CA
0x14008f992  mov     rcx, [rbx+68h]
0x14008f996  mov     edx, esi
0x14008f998  mov     rax, [rcx]
0x14008f99b  mov     rax, [rax+18h]
0x14008f99f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008f9a4  lea     rcx, [rbx+40h]; this
0x14008f9a8  call    ?OnDspPumpPassComplete@CAudioPumpDspResourceTokenContext@CAudioPumpDspResourceManager@@UEAAXXZ; CAudioPumpDspResourceManager::CAudioPumpDspResourceTokenContext::OnDspPumpPassComplete(void)
0x14008f9ad  jmp     loc_14008F8CA
0x14008f9b2  mov     ecx, 1; dwMilliseconds
0x14008f9b7  call    cs:__imp_Sleep
0x14008f9bd  movups  xmm0, xmmword ptr cs:_GUID_3c58e72b_cb3c_4076_93e8_9c528830f2d2.Data1
0x14008f9c4  mov     eax, [rbx+90h]
0x14008f9ca  lea     rdx, [rbp+57h+var_A8]
0x14008f9ce  mov     [rbp+57h+var_74], eax
0x14008f9d1  xor     r9d, r9d
0x14008f9d4  mov     rax, [rbx+58h]
0x14008f9d8  movdqu  [rbp+57h+var_90], xmm0
0x14008f9dd  mov     [rbp+57h+var_80], 0Bh
0x14008f9e4  xorps   xmm0, xmm0
0x14008f9e7  mov     [rbp+57h+var_7C], 2
0x14008f9ee  movups  [rbp+57h+var_70], xmm0
0x14008f9f2  mov     [rbp+57h+var_78], 1
0x14008f9f9  lea     r8d, [r9+40h]
0x14008f9fd  movups  [rbp+57h+var_60], xmm0
0x14008fa01  mov     [rbp+57h+var_A8], 0
0x14008fa09  mov     rcx, [rax+78h]
0x14008fa0d  mov     [rsp+110h+var_E8], rdx
0x14008fa12  lea     rdx, [rbp+57h+var_90]
0x14008fa16  mov     [rsp+110h+var_F0], 0
0x14008fa1f  mov     rax, [rcx]
0x14008fa22  mov     rax, [rax+28h]
0x14008fa26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008fa2b  mov     edi, eax
0x14008fa2d  test    eax, eax
0x14008fa2f  jns     loc_14008F8CA
0x14008fa35  mov     rcx, [rbx+58h]
0x14008fa39  mov     rsi, [rcx+58h]
0x14008fa3d  mov     edx, [rsi]
0x14008fa3f  cmp     edx, 2
0x14008fa42  jbe     short loc_14008FA71
0x14008fa44  call    cs:__imp_GetCurrentProcessId
0x14008fa4a  lea     rdx, byte_1400D2677
0x14008fa51  mov     [rbp+57h+var_BC], edi
0x14008fa54  mov     [rbp+57h+var_C0], eax
0x14008fa57  mov     rcx, rsi
0x14008fa5a  lea     rax, [rbp+57h+var_C0]
0x14008fa5e  mov     [rsp+110h+var_E8], rax
0x14008fa63  lea     rax, [rbp+57h+var_BC]
0x14008fa67  mov     [rsp+110h+var_F0], rax
0x14008fa6c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14008fa71  mov     eax, edi
0x14008fa73  and     eax, 1FFF0000h
0x14008fa78  cmp     eax, 70000h
0x14008fa7d  jnz     short loc_14008FA82
0x14008fa7f  movzx   edi, di
0x14008fa82  call    cs:__imp_GetCurrentProcess
0x14008fa88  mov     rcx, rax; hProcess
0x14008fa8b  mov     edx, edi; uExitCode
0x14008fa8d  call    cs:__imp_TerminateProcess
0x14008fa93  jmp     loc_14008F8CA
0x14008fa98  test    r14b, r14b
0x14008fa9b  jnz     loc_14008F8AA
0x14008faa1  mov     rax, [rbx+58h]
0x14008faa5  mov     r10, [rax+58h]
0x14008faa9  mov     eax, [r10]
0x14008faac  cmp     eax, 4
0x14008faaf  jbe     loc_14008F8AA
0x14008fab5  mov     edx, 100000h
0x14008faba  mov     rcx, r10
0x14008fabd  call    _tlgKeywordOn
0x14008fac2  test    al, al
0x14008fac4  jz      loc_14008F8AA
0x14008faca  lea     rax, [rbp+57h+var_90]
0x14008face  xor     r9d, r9d
0x14008fad1  mov     [rsp+110h+var_E8], rax
0x14008fad6  lea     rdx, byte_1400D2649
0x14008fadd  xor     r8d, r8d
0x14008fae0  mov     dword ptr [rsp+110h+var_F0], 2
0x14008fae8  mov     rcx, r10
0x14008faeb  call    _tlgWriteTransfer_EventWriteTransfer
0x14008faf0  jmp     loc_14008F8AA
0x14008faf5  cmp     eax, 1
0x14008faf8  jz      short loc_14008FB1A
0x14008fafa  cmp     eax, 0FFFFFFFFh
0x14008fafd  jnz     loc_14008F8AA
0x14008fb03  mov     rcx, [rbp+5Fh]; this
0x14008fb07  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x14008fb0e  mov     edx, 0ADh; void *
0x14008fb13  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14008fb18  jmp     short loc_14008FB48
0x14008fb1a  test    r15, r15
0x14008fb1d  jz      short loc_14008FB2F
0x14008fb1f  mov     rcx, r15; Handle
0x14008fb22  mov     [rbp+57h+TaskIndex], 0
0x14008fb29  call    cs:__imp_NtClose
0x14008fb2f  lea     rcx, [rbp+57h+var_B8]; void **
0x14008fb33  call    ?ResetEngineThreadPriority@@YAJPEAPEAX@Z; ResetEngineThreadPriority(void * *)
0x14008fb38  lea     r8, [rbp+57h+ActualResolution]; ActualResolution
0x14008fb3c  xor     edx, edx; SetOrUnset
0x14008fb3e  xor     ecx, ecx; RequestedResolution
0x14008fb40  call    cs:__imp_NtSetTimerResolution
0x14008fb46  xor     eax, eax
0x14008fb48  mov     rcx, [rbp+57h+var_40]
0x14008fb4c  xor     rcx, rsp; StackCookie
0x14008fb4f  call    __security_check_cookie
0x14008fb54  add     rsp, 0E8h
0x14008fb5b  pop     r15
0x14008fb5d  pop     r14
0x14008fb5f  pop     rdi
0x14008fb60  pop     rsi
0x14008fb61  pop     rbx
0x14008fb62  pop     rbp
0x14008fb63  retn
```
