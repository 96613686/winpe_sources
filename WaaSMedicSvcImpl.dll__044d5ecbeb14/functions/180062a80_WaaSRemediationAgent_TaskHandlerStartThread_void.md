# WaaSRemediationAgent::TaskHandlerStartThread(void *)

- ea: `0x180062a80`
- end: `0x180062c52`
- name: `?TaskHandlerStartThread@WaaSRemediationAgent@@SAKPEAX@Z`
- size: `466`
- prototype: `__int64 __fastcall(HANDLE *lpParameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18002e81c`
- `0x18005200c`
- `0x180062a80`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062b61`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062b61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062bd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062bd8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180062b43`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180062be8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180062b43`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180062be8`

## string_xrefs

- `0x180062b49`: `WaaSRemediationAgent now starting the task. Waiting for remediation lock...`
- `0x180062b67`: `WaaSRemediationAgent now starting the task. Remediation lock aquired.`
- `0x180062ad5`: `Failed to QI on WaaSRemediation agent interface. hr = 0x%08x`
- `0x180062b33`: `Failed to QI on Task completion callback to populate task thread proc params. hr = 0x%08x`
- `0x180062bf1`: `WaaSRemediationAgent completed the task. hr = 0x%08x`
- `0x180062b78`: `Task will perform scheduled run.`
- `0x180062ba3`: `Failed to execute WaasMedic launch remediation on a thread. hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WaaSRemediationAgent::TaskHandlerStartThread(HANDLE *lpParameter)
{
  char v2; // si
  __int64 (__fastcall ***v3)(HANDLE, GUID *, __int64 *); // rcx
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall ***v6)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rbp
  __int64 v8; // rcx
  int v9; // eax
  unsigned int *v10; // r8
  unsigned int v11; // r9d
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // [rsp+50h] [rbp+8h] BYREF
  __int64 v17; // [rsp+58h] [rbp+10h] BYREF

  v17 = 0;
  v16 = 0;
  v2 = 0;
  if ( lpParameter && (v3 = (__int64 (__fastcall ***)(HANDLE, GUID *, __int64 *))*lpParameter) != 0 )
  {
    v4 = (**v3)(v3, &IID_IUnknown, &v17);
    v5 = v4;
    if ( v4 >= 0 )
    {
      v6 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))*lpParameter;
      v7 = **(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*lpParameter;
      v8 = v16;
      if ( v16 )
      {
        v16 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      v9 = v7(v6, &GUID_4a263f7d_05d5_40d2_8eae_6a351acfb16f, &v16);
      v5 = v9;
      if ( v9 >= 0 )
      {
        v2 = 1;
        SetEvent(lpParameter[2]);
        LogLevelW(4u, L"WaaSRemediationAgent now starting the task. Waiting for remediation lock...");
        EnterCriticalSection(&stru_1800A43C8);
        LogLevelW(4u, L"WaaSRemediationAgent now starting the task. Remediation lock aquired.");
        LogLevelW(4u, L"Task will perform scheduled run.");
        v12 = WaaSRemediationAgent::ExecuteProcOnThread(
                (LPTHREAD_START_ROUTINE)WaasMedic::CWaasMedic::LaunchRemediation,
                lpParameter,
                v10,
                v11,
                1);
        v5 = v12;
        if ( v12 < 0 )
          LogLevelW(2u, L"Failed to execute WaasMedic launch remediation on a thread. hr = 0x%08x", (unsigned int)v12);
      }
      else
      {
        LogLevelW(
          2u,
          L"Failed to QI on Task completion callback to populate task thread proc params. hr = 0x%08x",
          (unsigned int)v9);
      }
    }
    else
    {
      LogLevelW(2u, L"Failed to QI on WaaSRemediation agent interface. hr = 0x%08x", (unsigned int)v4);
    }
  }
  else
  {
    v5 = -2147467261;
  }
  if ( v16 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v16 + 24LL))(v16, v5);
  if ( v2 )
  {
    LeaveCriticalSection(&stru_1800A43C8);
  }
  else if ( (v5 & 0x80000000) != 0 )
  {
    SetEvent(lpParameter[2]);
  }
  LogLevelW(4u, L"WaaSRemediationAgent completed the task. hr = 0x%08x", v5);
  v13 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return v5;
}

```

## disassembly

```asm
0x180062a80  mov     r11, rsp
0x180062a83  mov     [r11+18h], rbx
0x180062a87  push    rbp
0x180062a88  push    rsi
0x180062a89  push    rdi
0x180062a8a  sub     rsp, 30h
0x180062a8e  mov     rdi, rcx
0x180062a91  mov     qword ptr [r11+10h], 0
0x180062a99  mov     qword ptr [r11+8], 0
0x180062aa1  xor     sil, sil
0x180062aa4  test    rcx, rcx
0x180062aa7  jz      loc_180062BAF
0x180062aad  mov     rcx, [rcx]
0x180062ab0  test    rcx, rcx
0x180062ab3  jz      loc_180062BAF
0x180062ab9  mov     rax, [rcx]
0x180062abc  lea     r8, [r11+10h]
0x180062ac0  lea     rdx, IID_IUnknown
0x180062ac7  mov     rax, [rax]
0x180062aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062acf  mov     ebx, eax
0x180062ad1  test    eax, eax
0x180062ad3  jns     short loc_180062AEE
0x180062ad5  lea     rdx, aFailedToQiOnWa_0; "Failed to QI on WaaSRemediation agent i"...
0x180062adc  mov     r8d, eax
0x180062adf  mov     ecx, 2; unsigned __int8
0x180062ae4  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180062ae9  jmp     loc_180062BB4
0x180062aee  mov     rbx, [rdi]
0x180062af1  mov     rax, [rbx]
0x180062af4  mov     rbp, [rax]
0x180062af7  mov     rcx, [rsp+48h+arg_0]
0x180062afc  test    rcx, rcx
0x180062aff  jz      short loc_180062B16
0x180062b01  mov     [rsp+48h+arg_0], 0
0x180062b0a  mov     rdx, [rcx]
0x180062b0d  mov     rax, [rdx+10h]
0x180062b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062b16  lea     r8, [rsp+48h+arg_0]
0x180062b1b  lea     rdx, _GUID_4a263f7d_05d5_40d2_8eae_6a351acfb16f
0x180062b22  mov     rcx, rbx
0x180062b25  mov     rax, rbp
0x180062b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062b2d  mov     ebx, eax
0x180062b2f  test    eax, eax
0x180062b31  jns     short loc_180062B3C
0x180062b33  lea     rdx, aFailedToQiOnTa; "Failed to QI on Task completion callbac"...
0x180062b3a  jmp     short loc_180062ADC
0x180062b3c  mov     sil, 1
0x180062b3f  mov     rcx, [rdi+10h]; hEvent
0x180062b43  call    cs:__imp_SetEvent
0x180062b49  lea     rdx, aWaasremediatio_2; "WaaSRemediationAgent now starting the t"...
0x180062b50  mov     ecx, 4; unsigned __int8
0x180062b55  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180062b5a  lea     rcx, stru_1800A43C8; lpCriticalSection
0x180062b61  call    cs:__imp_EnterCriticalSection
0x180062b67  lea     rdx, aWaasremediatio_3; "WaaSRemediationAgent now starting the t"...
0x180062b6e  mov     ecx, 4; unsigned __int8
0x180062b73  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180062b78  lea     rdx, aTaskWillPerfor; "Task will perform scheduled run."
0x180062b7f  mov     ecx, 4; unsigned __int8
0x180062b84  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180062b89  mov     [rsp+48h+var_28], sil; bool
0x180062b8e  mov     rdx, rdi; lpParameter
0x180062b91  lea     rcx, ?LaunchRemediation@CWaasMedic@WaasMedic@@SAKPEAX@Z; lpStartAddress
0x180062b98  call    ?ExecuteProcOnThread@WaaSRemediationAgent@@CAKP6AKPEAX@Z0PEAKK_N@Z; WaaSRemediationAgent::ExecuteProcOnThread(ulong (*)(void *),void *,ulong *,ulong,bool)
0x180062b9d  mov     ebx, eax
0x180062b9f  test    eax, eax
0x180062ba1  jns     short loc_180062BB4
0x180062ba3  lea     rdx, aFailedToExecut_1; "Failed to execute WaasMedic launch reme"...
0x180062baa  jmp     loc_180062ADC
0x180062baf  mov     ebx, 80004003h
0x180062bb4  mov     rcx, [rsp+48h+arg_0]
0x180062bb9  test    rcx, rcx
0x180062bbc  jz      short loc_180062BCC
0x180062bbe  mov     rax, [rcx]
0x180062bc1  mov     edx, ebx
0x180062bc3  mov     rax, [rax+18h]
0x180062bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062bcc  test    sil, sil
0x180062bcf  jz      short loc_180062BE0
0x180062bd1  lea     rcx, stru_1800A43C8; lpCriticalSection
0x180062bd8  call    cs:__imp_LeaveCriticalSection
0x180062bde  jmp     short loc_180062BEE
0x180062be0  test    ebx, ebx
0x180062be2  jns     short loc_180062BEE
0x180062be4  mov     rcx, [rdi+10h]; hEvent
0x180062be8  call    cs:__imp_SetEvent
0x180062bee  mov     r8d, ebx
0x180062bf1  lea     rdx, aWaasremediatio; "WaaSRemediationAgent completed the task"...
0x180062bf8  mov     ecx, 4; unsigned __int8
0x180062bfd  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180062c02  nop
0x180062c03  mov     rcx, [rsp+48h+arg_0]
0x180062c08  test    rcx, rcx
0x180062c0b  jz      short loc_180062C23
0x180062c0d  mov     [rsp+48h+arg_0], 0
0x180062c16  mov     rax, [rcx]
0x180062c19  mov     rax, [rax+10h]
0x180062c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062c22  nop
0x180062c23  mov     rcx, [rsp+48h+arg_8]
0x180062c28  test    rcx, rcx
0x180062c2b  jz      short loc_180062C43
0x180062c2d  mov     [rsp+48h+arg_8], 0
0x180062c36  mov     rax, [rcx]
0x180062c39  mov     rax, [rax+10h]
0x180062c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062c42  nop
0x180062c43  mov     eax, ebx
0x180062c45  mov     rbx, [rsp+48h+arg_10]
0x180062c4a  add     rsp, 30h
0x180062c4e  pop     rdi
0x180062c4f  pop     rsi
0x180062c50  pop     rbp
0x180062c51  retn
```
