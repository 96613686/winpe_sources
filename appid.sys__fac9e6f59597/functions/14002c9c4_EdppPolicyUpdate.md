# EdppPolicyUpdate

- ea: `0x14002c9c4`
- end: `0x14002cc2d`
- name: `EdppPolicyUpdate`
- size: `617`
- prototype: `__int64 __fastcall(char updated)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x14002cce0`

## callees

- `0x140001cb0`
- `0x14002c9c4`
- `0x14002cc34`
- `0x14002cd1c`
- `0x14002d18c`
- `0x1400328b0`
- `0x140032f60`
- `0x140035440`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14002cb52`
- `ntoskrnl!ObfDereferenceObject` at `0x14002cb52`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14002ca1b`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14002ca1b`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002cb2a`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002cb2a`
- `ntoskrnl!ZwGetNextProcess` at `0x14002cad3`
- `ntoskrnl!ZwGetNextProcess` at `0x14002cad3`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14002cb12`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14002cb12`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14002cbc9`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14002cbfd`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14002cbc9`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14002cbfd`
- `ntoskrnl!ZwClose` at `0x14002cae9`
- `ntoskrnl!ZwClose` at `0x14002cae9`
- `fwpkclnt!NikEdpNotifyProcessTokenChange0` at `0x14002cc10`
- `fwpkclnt!NikEdpNotifyProcessTokenChange0` at `0x14002cc10`

## pseudocode

```c
__int64 __fastcall EdppPolicyUpdate(char updated)
{
  __int64 Policy; // rbx
  char v3; // r14
  NTSTATUS NextProcess; // esi
  int v5; // r8d
  HANDLE v6; // rdi
  int v7; // r8d
  __int128 v9; // [rsp+40h] [rbp-19h] BYREF
  __int128 v10; // [rsp+50h] [rbp-9h] BYREF
  _OWORD ProcessInformation[5]; // [rsp+60h] [rbp+7h] BYREF
  ULONG ReturnLength; // [rsp+C8h] [rbp+6Fh] BYREF
  PEPROCESS Process; // [rsp+D0h] [rbp+77h] BYREF
  HANDLE ProcessHandle; // [rsp+D8h] [rbp+7Fh] BYREF

  ProcessHandle = 0;
  ReturnLength = 0;
  Process = 0;
  Policy = 0;
  v3 = 0;
  memset(ProcessInformation, 0, 44);
  v9 = 0;
  v10 = 0;
  NextProcess = RtlRunOnceExecuteOnce(&RunOnce, (PRTL_RUN_ONCE_INIT_FN)EdppInitializeCallback, 0, 0);
  if ( NextProcess >= 0 )
  {
    if ( !updated )
      updated = EdppPolicyUpdateRequired();
    Policy = SrpGetPolicy();
    if ( Policy && updated )
    {
      v6 = 0;
      SrpGetPluginPolicy(Policy, (unsigned int)&AiCategoryExe, v5, (unsigned int)&v9 + 8, (__int64)&v9);
      SrpGetPluginPolicy(Policy, (unsigned int)&AiCategoryAppx, v7, (unsigned int)&v10 + 8, (__int64)&v10);
      if ( EdpPluginConfigActive((__int64)byte_140019508) )
        v3 = 1;
      else
        _InterlockedExchange(&dword_14001952C, 0);
      while ( 1 )
      {
        NextProcess = ZwGetNextProcess(v6, 0x10000000, 512, 0, &ProcessHandle);
        if ( v6 )
          ZwClose(v6);
        if ( NextProcess < 0 )
          break;
        if ( ZwQueryInformationProcess(ProcessHandle, ProcessBasicInformation, ProcessInformation, 0x30u, &ReturnLength) >= 0
          && PsLookupProcessByProcessId(*(HANDLE *)&ProcessInformation[2], &Process) >= 0 )
        {
          EdppProcessEnumRoutine(Process, *(_QWORD *)&ProcessInformation[2], Policy, &v9);
          ObfDereferenceObject(Process);
          Process = 0;
        }
        v6 = ProcessHandle;
        ProcessHandle = 0;
      }
    }
  }
  AiFree(*((void **)&v9 + 1));
  AiFree(*((void **)&v10 + 1));
  SrpReleasePolicy(Policy);
  if ( v3 )
    _InterlockedExchange(&dword_14001952C, 1);
  ZwUpdateWnfStateData(&WNF_ENTR_EVALUATE_EDP_CONFIGURATION_STATE, 0, 0, 0, 0, 0, 0);
  ZwUpdateWnfStateData(&WNF_EDP_ENTERPRISE_CONTEXTS_UPDATED, 0, 0, 0, 0, 0, 0);
  NikEdpNotifyProcessTokenChange0(0, 1);
  return (unsigned int)NextProcess;
}

```

## disassembly

```asm
0x14002c9c4  push    rbp
0x14002c9c6  push    rbx
0x14002c9c7  push    rsi
0x14002c9c8  push    rdi
0x14002c9c9  push    r14
0x14002c9cb  lea     rbp, [rsp-37h]
0x14002c9d0  sub     rsp, 90h
0x14002c9d7  xorps   xmm0, xmm0
0x14002c9da  mov     [rbp+57h+ProcessHandle], 0
0x14002c9e2  xor     eax, eax
0x14002c9e4  lea     rdx, EdppInitializeCallback; InitFn
0x14002c9eb  mov     dil, cl
0x14002c9ee  mov     [rbp+57h+arg_8], eax
0x14002c9f1  movups  [rbp+57h+var_40], xmm0
0x14002c9f5  xor     r9d, r9d; Context
0x14002c9f8  mov     [rbp+57h+Process], rax
0x14002c9fc  xor     r8d, r8d; Parameter
0x14002c9ff  lea     rcx, RunOnce; RunOnce
0x14002ca06  movups  [rbp+57h+var_40+0Ch], xmm0
0x14002ca0a  xor     ebx, ebx
0x14002ca0c  xor     r14b, r14b
0x14002ca0f  movups  [rbp+57h+ProcessInformation], xmm0
0x14002ca13  movups  [rbp+57h+var_70], xmm0
0x14002ca17  movups  [rbp+57h+var_60], xmm0
0x14002ca1b  call    cs:__imp_RtlRunOnceExecuteOnce
0x14002ca22  nop     dword ptr [rax+rax+00h]
0x14002ca27  mov     esi, eax
0x14002ca29  test    eax, eax
0x14002ca2b  js      loc_14002CB77
0x14002ca31  test    dil, dil
0x14002ca34  jnz     short loc_14002CA3E
0x14002ca36  call    EdppPolicyUpdateRequired
0x14002ca3b  mov     dil, al
0x14002ca3e  call    SrpGetPolicy
0x14002ca43  mov     rbx, rax
0x14002ca46  test    rax, rax
0x14002ca49  jz      loc_14002CB77
0x14002ca4f  test    dil, dil
0x14002ca52  jz      loc_14002CB77
0x14002ca58  lea     rax, [rbp+57h+var_70]
0x14002ca5c  mov     rcx, rbx
0x14002ca5f  lea     r9, [rbp+57h+var_70+8]
0x14002ca63  mov     [rsp+0B0h+ReturnLength], rax
0x14002ca68  lea     rdx, AiCategoryExe
0x14002ca6f  xor     edi, edi
0x14002ca71  call    SrpGetPluginPolicy
0x14002ca76  lea     rax, [rbp+57h+var_60]
0x14002ca7a  mov     rcx, rbx
0x14002ca7d  lea     r9, [rbp+57h+var_60+8]
0x14002ca81  mov     [rsp+0B0h+ReturnLength], rax
0x14002ca86  lea     rdx, AiCategoryAppx
0x14002ca8d  call    SrpGetPluginPolicy
0x14002ca92  mov     r9d, dword ptr [rbp+57h+var_60]
0x14002ca96  lea     rcx, byte_140019508
0x14002ca9d  mov     r8d, dword ptr [rbp+57h+var_70]
0x14002caa1  xor     edx, edx
0x14002caa3  call    EdpPluginConfigActive
0x14002caa8  test    al, al
0x14002caaa  jz      short loc_14002CAB1
0x14002caac  mov     r14b, 1
0x14002caaf  jmp     short loc_14002CAB9
0x14002cab1  xor     eax, eax
0x14002cab3  xchg    eax, cs:dword_14001952C
0x14002cab9  lea     rax, [rbp+57h+ProcessHandle]
0x14002cabd  xor     r9d, r9d
0x14002cac0  mov     edx, 10000000h
0x14002cac5  mov     [rsp+0B0h+ReturnLength], rax
0x14002caca  mov     r8d, 200h
0x14002cad0  mov     rcx, rdi
0x14002cad3  call    cs:__imp_ZwGetNextProcess
0x14002cada  nop     dword ptr [rax+rax+00h]
0x14002cadf  mov     esi, eax
0x14002cae1  test    rdi, rdi
0x14002cae4  jz      short loc_14002CAF5
0x14002cae6  mov     rcx, rdi; Handle
0x14002cae9  call    cs:__imp_ZwClose
0x14002caf0  nop     dword ptr [rax+rax+00h]
0x14002caf5  test    esi, esi
0x14002caf7  js      short loc_14002CB77
0x14002caf9  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x14002cafd  lea     rax, [rbp+57h+arg_8]
0x14002cb01  mov     r9d, 30h ; '0'; ProcessInformationLength
0x14002cb07  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x14002cb0c  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x14002cb10  xor     edx, edx; ProcessInformationClass
0x14002cb12  call    cs:__imp_ZwQueryInformationProcess
0x14002cb19  nop     dword ptr [rax+rax+00h]
0x14002cb1e  test    eax, eax
0x14002cb20  js      short loc_14002CB66
0x14002cb22  mov     rcx, [rbp+57h+ProcessId]; ProcessId
0x14002cb26  lea     rdx, [rbp+57h+Process]; Process
0x14002cb2a  call    cs:__imp_PsLookupProcessByProcessId
0x14002cb31  nop     dword ptr [rax+rax+00h]
0x14002cb36  test    eax, eax
0x14002cb38  js      short loc_14002CB66
0x14002cb3a  mov     rdx, [rbp+57h+ProcessId]
0x14002cb3e  lea     r9, [rbp+57h+var_70]
0x14002cb42  mov     rcx, [rbp+57h+Process]
0x14002cb46  mov     r8, rbx
0x14002cb49  call    EdppProcessEnumRoutine
0x14002cb4e  mov     rcx, [rbp+57h+Process]; Object
0x14002cb52  call    cs:__imp_ObfDereferenceObject
0x14002cb59  nop     dword ptr [rax+rax+00h]
0x14002cb5e  mov     [rbp+57h+Process], 0
0x14002cb66  mov     rdi, [rbp+57h+ProcessHandle]
0x14002cb6a  mov     [rbp+57h+ProcessHandle], 0
0x14002cb72  jmp     loc_14002CAB9
0x14002cb77  mov     rcx, qword ptr [rbp+57h+var_70+8]
0x14002cb7b  call    AiFree
0x14002cb80  mov     rcx, qword ptr [rbp+57h+var_60+8]
0x14002cb84  call    AiFree
0x14002cb89  mov     rcx, rbx
0x14002cb8c  call    SrpReleasePolicy
0x14002cb91  test    r14b, r14b
0x14002cb94  jz      short loc_14002CBA1
0x14002cb96  mov     eax, 1
0x14002cb9b  xchg    eax, cs:dword_14001952C
0x14002cba1  mov     [rsp+0B0h+var_80], 0
0x14002cba9  lea     rcx, WNF_ENTR_EVALUATE_EDP_CONFIGURATION_STATE
0x14002cbb0  mov     [rsp+0B0h+var_88], 0
0x14002cbb8  xor     r9d, r9d
0x14002cbbb  xor     r8d, r8d
0x14002cbbe  mov     [rsp+0B0h+ReturnLength], 0
0x14002cbc7  xor     edx, edx
0x14002cbc9  call    cs:__imp_ZwUpdateWnfStateData
0x14002cbd0  nop     dword ptr [rax+rax+00h]
0x14002cbd5  mov     [rsp+0B0h+var_80], 0
0x14002cbdd  lea     rcx, WNF_EDP_ENTERPRISE_CONTEXTS_UPDATED
0x14002cbe4  mov     [rsp+0B0h+var_88], 0
0x14002cbec  xor     r9d, r9d
0x14002cbef  xor     r8d, r8d
0x14002cbf2  mov     [rsp+0B0h+ReturnLength], 0
0x14002cbfb  xor     edx, edx
0x14002cbfd  call    cs:__imp_ZwUpdateWnfStateData
0x14002cc04  nop     dword ptr [rax+rax+00h]
0x14002cc09  mov     edx, 1
0x14002cc0e  xor     ecx, ecx
0x14002cc10  call    cs:__imp_NikEdpNotifyProcessTokenChange0
0x14002cc17  nop     dword ptr [rax+rax+00h]
0x14002cc1c  mov     eax, esi
0x14002cc1e  add     rsp, 90h
0x14002cc25  pop     r14
0x14002cc27  pop     rdi
0x14002cc28  pop     rsi
0x14002cc29  pop     rbx
0x14002cc2a  pop     rbp
0x14002cc2b  retn
```
