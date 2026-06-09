# BipActivationCompletionCallback

- ea: `0x18003ad50`
- end: `0x18003b120`
- name: `BipActivationCompletionCallback`
- size: `976`
- prototype: `__int64 __fastcall(void *Source1)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003ab70`

## callees

- `0x180005670`
- `0x180008380`
- `0x1800084f8`
- `0x18000d50c`
- `0x18000d7c0`
- `0x18000da50`
- `0x18000fbd0`
- `0x180010630`
- `0x1800121b0`
- `0x180013d20`
- `0x1800154b0`
- `0x18002a410`
- `0x18002b060`
- `0x18002d4d0`
- `0x18003ad50`
- `0x18003d9b8`
- `0x18004b6c8`
- `0x180053100`
- `0x1800946a0`
- `0x180095010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003adcf`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003adcf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003b080`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003b080`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003af00`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003b051`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003af00`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003b051`
- `UMPDC!Pdcv2ActivationClientSetBrokeredProcessId` at `0x18003adfa`
- `UMPDC!Pdcv2ActivationClientSetBrokeredProcessId` at `0x18003adfa`

## pseudocode

```c
__int64 __fastcall BipActivationCompletionCallback(void *Source1, __int64 a2, unsigned int a3, char a4)
{
  __int64 v4; // rdi
  char v8; // r12
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // r8
  char v12; // bl
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // r15
  unsigned __int64 v16; // r14
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 result; // rax
  __int64 v21; // r8
  __int16 v23; // [rsp+34h] [rbp-CCh] BYREF
  int ActivationType; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v26[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v29[32]; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v30; // [rsp+90h] [rbp-70h]
  __int64 v31; // [rsp+98h] [rbp-68h]
  _QWORD v32[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v33[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v34[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v35; // [rsp+D0h] [rbp-30h]
  __int64 v36; // [rsp+D8h] [rbp-28h]
  int *p_ActivationType; // [rsp+E0h] [rbp-20h]
  __int64 v38; // [rsp+E8h] [rbp-18h]
  _QWORD *v39; // [rsp+F0h] [rbp-10h]
  __int64 v40; // [rsp+F8h] [rbp-8h]

  v4 = 0;
  SystemTimeAsFileTime = 0;
  v8 = 0;
  BipAcquireGlobalLock();
  if ( (int)BipLookupWorkItemByGuid(Source1) >= 0 )
  {
    v10 = ((__int64 (__fastcall *)(_QWORD, _QWORD))BipWorkItemFindActivatedInstance)(SystemTimeAsFileTime, a2);
    v4 = v10;
    if ( v10 )
    {
      RtlAcquireSRWLockExclusive(v10 + 48);
      v12 = 0;
      if ( (*(_BYTE *)(v4 + 136) & 0x40) == 0 )
      {
        if ( a3 )
        {
          v13 = *(_QWORD *)(v4 + 144);
          if ( v13 )
            Pdcv2ActivationClientSetBrokeredProcessId(v13, a3);
        }
        if ( *(_QWORD *)(v4 + 144) )
        {
          v14 = *(_QWORD *)(*(_QWORD *)(v4 + 64) + 72LL);
          if ( v14 )
          {
            if ( *(_DWORD *)(v14 + 580) == 1000 )
              v12 = 1;
          }
        }
        if ( *(_QWORD *)(v4 + 80) )
          BipSystemPsmCompleteActivation();
        *(_DWORD *)(v4 + 136) |= 8u;
        v8 = 1;
        if ( *(_QWORD *)(v4 + 312) || *(_QWORD *)(v4 + 128) )
          BipResourceTimerArmWithLockHeld(v4, *(unsigned int *)(v4 + 288));
        SystemTimeAsFileTime = 0;
        v27 = 0;
        LOWORD(ActivationType) = 0;
        v28 = 0;
        v23 = 0;
        v15 = *(_QWORD *)(v4 + 64);
        if ( (unsigned int)dword_1800C3098 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 2, v11) )
        {
          v31 = 1;
          v30 = &qword_1800A1850;
          v32[1] = 16;
          v32[0] = v15 + 32;
          v33[0] = v4;
          v33[1] = 16;
          tlgWriteTransfer_EventWriteTransfer(&dword_1800C3098, qword_1800B3A78, 0, 0, 5, v29);
        }
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v26[1] = SystemTimeAsFileTime;
        v26[0] = *(_QWORD *)(v4 + 156);
        v16 = *(_QWORD *)&SystemTimeAsFileTime - v26[0];
        if ( *(_QWORD *)&SystemTimeAsFileTime - v26[0] > 0x8F0D180u )
        {
          BipGetWorkItemTraceInformation(
            v15,
            (unsigned int)&v27,
            (unsigned int)&ActivationType,
            (unsigned int)&v28,
            (__int64)&v23);
          if ( (unsigned int)dword_1800C3098 > 3 )
          {
            if ( (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 0x400000000000LL, v17) )
            {
              v18 = *(_QWORD *)(v15 + 80) + 160LL;
              v30 = (const unsigned __int16 *)(v15 + 32);
              v31 = 16;
              tlgCreate1Sz_wchar_t(v32, v18);
              tlgCreate1Sz_wchar_t(v33, v27);
              tlgCreate1Sz_wchar_t(v34, v28);
              v35 = v4;
              v36 = 16;
              ActivationType = BipGetActivationType(v15);
              v38 = 4;
              p_ActivationType = &ActivationType;
              v40 = 8;
              v39 = v26;
              v26[0] = v16 / 0x2710;
              tlgWriteTransfer_EventWriteTransfer(&dword_1800C3098, &byte_1800B39E7, 0, 0, 9, v29);
            }
          }
        }
        GetSystemTimeAsFileTime((LPFILETIME)(v4 + 456));
        if ( (unsigned __int8)BipUtilActTypeIsDebugSupported(MEMORY[0x190]) )
          BipUpdateWorkItemInstanceState(*(_QWORD *)(v4 + 64), v4, 32, 0);
      }
      RtlReleaseSRWLockExclusive(v4 + 48);
      if ( v12 )
        BipPdcReferenceRelease((__int64)&xmmword_1800C40C8, v4);
    }
  }
  BipLockWatchdogContextDisarmWatchdog(v9);
  LOBYTE(v19) = 1;
  result = BipSyncReleaseLock(&BipGlobalLock, v19);
  if ( a4 )
  {
    if ( v8 )
    {
      result = BipWorkItemIsHamActivityBmManaged(*(_QWORD *)(v4 + 64));
      if ( (_BYTE)result )
      {
        if ( BmpManager )
          return (*(__int64 (__fastcall **)(struct Execution::IBackgroundManager *, __int64, __int64))(*(_QWORD *)BmpManager + 32LL))(
                   BmpManager,
                   v21 + 32,
                   v4);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003ad50  mov     [rsp-8+arg_18], rbx
0x18003ad55  push    rbp
0x18003ad56  push    rsi
0x18003ad57  push    rdi
0x18003ad58  push    r12
0x18003ad5a  push    r13
0x18003ad5c  push    r14
0x18003ad5e  push    r15
0x18003ad60  lea     rbp, [rsp-10h]
0x18003ad65  sub     rsp, 110h
0x18003ad6c  mov     rax, cs:__security_cookie
0x18003ad73  xor     rax, rsp
0x18003ad76  mov     [rbp+40h+var_40], rax
0x18003ad7a  xor     edi, edi
0x18003ad7c  mov     [rsp+140h+var_110], r9b
0x18003ad81  mov     qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18003ad86  mov     r14d, r8d
0x18003ad89  mov     r15, rdx
0x18003ad8c  mov     rbx, rcx
0x18003ad8f  xor     r12b, r12b
0x18003ad92  call    BipAcquireGlobalLock
0x18003ad97  lea     rdx, [rsp+140h+SystemTimeAsFileTime]
0x18003ad9c  mov     rcx, rbx; Source1
0x18003ad9f  call    BipLookupWorkItemByGuid
0x18003ada4  mov     rsi, qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime]
0x18003ada9  test    eax, eax
0x18003adab  js      loc_18003B09B
0x18003adb1  mov     rdx, r15
0x18003adb4  mov     rcx, rsi
0x18003adb7  call    BipWorkItemFindActivatedInstance
0x18003adbc  xor     r15d, r15d
0x18003adbf  mov     rdi, rax
0x18003adc2  test    rax, rax
0x18003adc5  jz      loc_18003B09E
0x18003adcb  lea     rcx, [rax+30h]
0x18003adcf  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18003add5  test    byte ptr [rdi+88h], 40h
0x18003addc  movzx   ebx, r15b
0x18003ade0  jnz     loc_18003B07C
0x18003ade6  test    r14d, r14d
0x18003ade9  jz      short loc_18003AE00
0x18003adeb  mov     rcx, [rdi+90h]
0x18003adf2  test    rcx, rcx
0x18003adf5  jz      short loc_18003AE00
0x18003adf7  mov     edx, r14d
0x18003adfa  call    cs:__imp_Pdcv2ActivationClientSetBrokeredProcessId
0x18003ae00  mov     r14d, 1
0x18003ae06  cmp     [rdi+90h], r15
0x18003ae0d  jz      short loc_18003AE2A
0x18003ae0f  mov     rax, [rdi+40h]
0x18003ae13  mov     rcx, [rax+48h]
0x18003ae17  test    rcx, rcx
0x18003ae1a  jz      short loc_18003AE2A
0x18003ae1c  cmp     dword ptr [rcx+244h], 3E8h
0x18003ae26  cmovz   ebx, r14d
0x18003ae2a  mov     rcx, [rdi+50h]
0x18003ae2e  test    rcx, rcx
0x18003ae31  jz      short loc_18003AE38
0x18003ae33  call    BipSystemPsmCompleteActivation
0x18003ae38  or      dword ptr [rdi+88h], 8
0x18003ae3f  mov     r12b, r14b
0x18003ae42  cmp     [rdi+138h], r15
0x18003ae49  jnz     short loc_18003AE54
0x18003ae4b  cmp     [rdi+80h], r15
0x18003ae52  jz      short loc_18003AE62
0x18003ae54  mov     edx, [rdi+120h]
0x18003ae5a  mov     rcx, rdi
0x18003ae5d  call    BipResourceTimerArmWithLockHeld
0x18003ae62  mov     eax, cs:dword_1800C3098
0x18003ae68  mov     qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime], r15
0x18003ae6d  mov     [rsp+140h+var_E8], r15
0x18003ae72  mov     word ptr [rsp+140h+var_108], r15w
0x18003ae78  mov     [rsp+140h+var_E0], r15
0x18003ae7d  mov     [rsp+140h+var_10C], r15w
0x18003ae83  mov     r15, [rdi+40h]
0x18003ae87  cmp     eax, 5
0x18003ae8a  jbe     short loc_18003AEFB
0x18003ae8c  mov     edx, 2
0x18003ae91  lea     rcx, dword_1800C3098
0x18003ae98  call    _tlgKeywordOn
0x18003ae9d  test    al, al
0x18003ae9f  jz      short loc_18003AEFB
0x18003aea1  lea     rax, qword_1800A1850
0x18003aea8  mov     [rbp+40h+var_A8], 1
0x18003aeb0  mov     [rbp+40h+var_B0], rax
0x18003aeb4  lea     rdx, qword_1800B3A78
0x18003aebb  lea     rax, [r15+20h]
0x18003aebf  mov     [rbp+40h+var_98], 10h
0x18003aec7  mov     [rbp+40h+var_A0], rax
0x18003aecb  lea     rcx, dword_1800C3098
0x18003aed2  lea     rax, [rsp+140h+var_D0]
0x18003aed7  mov     [rbp+40h+var_90], rdi
0x18003aedb  mov     [rsp+140h+var_118], rax
0x18003aee0  xor     r9d, r9d
0x18003aee3  xor     r8d, r8d
0x18003aee6  mov     dword ptr [rsp+140h+var_120], 5
0x18003aeee  mov     [rbp+40h+var_88], 10h
0x18003aef6  call    _tlgWriteTransfer_EventWriteTransfer
0x18003aefb  lea     rcx, [rsp+140h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003af00  call    cs:__imp_GetSystemTimeAsFileTime
0x18003af06  mov     eax, [rsp+140h+SystemTimeAsFileTime.dwHighDateTime]
0x18003af0a  mov     dword ptr [rsp+140h+var_F0+4], eax
0x18003af0e  mov     eax, [rsp+140h+SystemTimeAsFileTime.dwLowDateTime]
0x18003af12  mov     dword ptr [rsp+140h+var_F0], eax
0x18003af16  mov     eax, [rdi+0A0h]
0x18003af1c  mov     r14, [rsp+140h+var_F0]
0x18003af21  mov     dword ptr [rsp+140h+var_F8+4], eax
0x18003af25  mov     eax, [rdi+9Ch]
0x18003af2b  mov     dword ptr [rsp+140h+var_F8], eax
0x18003af2f  sub     r14, [rsp+140h+var_F8]
0x18003af34  cmp     r14, 8F0D180h
0x18003af3b  jbe     loc_18003B04A
0x18003af41  lea     rax, [rsp+140h+var_10C]
0x18003af46  mov     rcx, r15
0x18003af49  lea     r9, [rsp+140h+var_E0]
0x18003af4e  mov     [rsp+140h+var_120], rax
0x18003af53  lea     r8, [rsp+140h+var_108]
0x18003af58  lea     rdx, [rsp+140h+var_E8]
0x18003af5d  call    BipGetWorkItemTraceInformation
0x18003af62  mov     eax, cs:dword_1800C3098
0x18003af68  cmp     eax, 3
0x18003af6b  jbe     loc_18003B04A
0x18003af71  mov     rdx, 400000000000h
0x18003af7b  lea     rcx, dword_1800C3098
0x18003af82  call    _tlgKeywordOn
0x18003af87  test    al, al
0x18003af89  jz      loc_18003B04A
0x18003af8f  mov     rdx, [r15+50h]
0x18003af93  lea     rax, [r15+20h]
0x18003af97  add     rdx, 0A0h
0x18003af9e  mov     [rbp+40h+var_B0], rax
0x18003afa2  lea     rcx, [rbp+40h+var_A0]
0x18003afa6  mov     [rbp+40h+var_A8], 10h
0x18003afae  call    _tlgCreate1Sz_wchar_t
0x18003afb3  mov     rdx, [rsp+140h+var_E8]
0x18003afb8  lea     rcx, [rbp+40h+var_90]
0x18003afbc  call    _tlgCreate1Sz_wchar_t
0x18003afc1  mov     rdx, [rsp+140h+var_E0]
0x18003afc6  lea     rcx, [rbp+40h+var_80]
0x18003afca  call    _tlgCreate1Sz_wchar_t
0x18003afcf  mov     rcx, r15
0x18003afd2  mov     [rbp+40h+var_70], rdi
0x18003afd6  mov     [rbp+40h+var_68], 10h
0x18003afde  call    BipGetActivationType
0x18003afe3  mov     [rsp+140h+var_108], eax
0x18003afe7  lea     rcx, dword_1800C3098
0x18003afee  lea     rax, [rsp+140h+var_108]
0x18003aff3  mov     [rbp+40h+var_58], 4
0x18003affb  mov     [rbp+40h+var_60], rax
0x18003afff  xor     r9d, r9d
0x18003b002  mov     rax, 346DC5D63886594Bh
0x18003b00c  mov     [rbp+40h+var_48], 8
0x18003b014  mul     r14
0x18003b017  lea     rax, [rsp+140h+var_F8]
0x18003b01c  xor     r8d, r8d
0x18003b01f  shr     rdx, 0Bh
0x18003b023  mov     [rbp+40h+var_50], rax
0x18003b027  lea     rax, [rsp+140h+var_D0]
0x18003b02c  mov     [rsp+140h+var_F8], rdx
0x18003b031  lea     rdx, byte_1800B39E7
0x18003b038  mov     [rsp+140h+var_118], rax
0x18003b03d  mov     dword ptr [rsp+140h+var_120], 9
0x18003b045  call    _tlgWriteTransfer_EventWriteTransfer
0x18003b04a  lea     rcx, [rdi+1C8h]; lpSystemTimeAsFileTime
0x18003b051  call    cs:__imp_GetSystemTimeAsFileTime
0x18003b057  mov     ecx, [rsi+190h]
0x18003b05d  call    BipUtilActTypeIsDebugSupported
0x18003b062  xor     r15d, r15d
0x18003b065  test    al, al
0x18003b067  jz      short loc_18003B07C
0x18003b069  mov     rcx, [rdi+40h]
0x18003b06d  lea     r8d, [r15+20h]
0x18003b071  xor     r9d, r9d
0x18003b074  mov     rdx, rdi
0x18003b077  call    ?BipUpdateWorkItemInstanceState@@YAJPEAU_BI_WORK_ITEM@@PEAU_BI_ACTIVATED_TASK_INSTANCE@@W4_BI_WORK_ITEM_INSTANCE_STATE@@PEAX@Z; BipUpdateWorkItemInstanceState(_BI_WORK_ITEM *,_BI_ACTIVATED_TASK_INSTANCE *,_BI_WORK_ITEM_INSTANCE_STATE,void *)
0x18003b07c  lea     rcx, [rdi+30h]
0x18003b080  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18003b086  test    bl, bl
0x18003b088  jz      short loc_18003B09E
0x18003b08a  mov     rdx, rdi
0x18003b08d  lea     rcx, xmmword_1800C40C8
0x18003b094  call    BipPdcReferenceRelease
0x18003b099  jmp     short loc_18003B09E
0x18003b09b  xor     r15d, r15d
0x18003b09e  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x18003b0a3  mov     dl, 1
0x18003b0a5  lea     rcx, BipGlobalLock
0x18003b0ac  call    BipSyncReleaseLock
0x18003b0b1  cmp     [rsp+140h+var_110], r15b
0x18003b0b6  jz      short loc_18003B0EC
0x18003b0b8  test    r12b, r12b
0x18003b0bb  jz      short loc_18003B0EC
0x18003b0bd  mov     r8, [rdi+40h]
0x18003b0c1  mov     rcx, r8
0x18003b0c4  call    BipWorkItemIsHamActivityBmManaged
0x18003b0c9  test    al, al
0x18003b0cb  jz      short loc_18003B0EC
0x18003b0cd  mov     rcx, cs:?BmpManager@@3V?$ComPtr@UIBackgroundManager@Execution@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Execution::IBackgroundManager> BmpManager
0x18003b0d4  test    rcx, rcx
0x18003b0d7  jz      short loc_18003B0EC
0x18003b0d9  mov     rax, [rcx]
0x18003b0dc  lea     rdx, [r8+20h]
0x18003b0e0  mov     r8, rdi
0x18003b0e3  mov     rax, [rax+20h]
0x18003b0e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b0ec  test    rsi, rsi
0x18003b0ef  jz      short loc_18003B0F9
0x18003b0f1  mov     rcx, rsi
0x18003b0f4  call    BipWorkItemDereference
0x18003b0f9  mov     rcx, [rbp+40h+var_40]
0x18003b0fd  xor     rcx, rsp; StackCookie
0x18003b100  call    __security_check_cookie
0x18003b105  mov     rbx, [rsp+140h+arg_18]
0x18003b10d  add     rsp, 110h
0x18003b114  pop     r15
0x18003b116  pop     r14
0x18003b118  pop     r13
0x18003b11a  pop     r12
0x18003b11c  pop     rdi
0x18003b11d  pop     rsi
0x18003b11e  pop     rbp
0x18003b11f  retn
```
