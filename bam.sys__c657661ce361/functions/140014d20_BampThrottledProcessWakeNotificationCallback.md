# BampThrottledProcessWakeNotificationCallback

- ea: `0x140014d20`
- end: `0x140014f87`
- name: `BampThrottledProcessWakeNotificationCallback`
- size: `615`
- prototype: `__int64 __fastcall(int, int, int, int, int, PVOID P)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400026d0`
- `0x1400107f0`
- `0x140014d20`
- `0x1400153a0`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140014f3c`
- `ntoskrnl!EtwWriteTransfer` at `0x140014f3c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140014db4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140014db4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140014dc6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140014dc6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014f5e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014f5e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140014f52`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140014f52`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140014e0f`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140014e0f`

## pseudocode

```c
__int64 __fastcall BampThrottledProcessWakeNotificationCallback(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        char *P)
{
  signed __int64 *v6; // roff
  signed __int64 v7; // rax
  unsigned __int64 v8; // rcx
  bool v9; // zf
  signed __int64 v10; // rtt
  __int64 v12; // rax
  int v13; // ecx
  unsigned int v14; // [rsp+30h] [rbp-39h] BYREF
  _DWORD v15[3]; // [rsp+34h] [rbp-35h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-19h] BYREF
  __int16 *v18; // [rsp+60h] [rbp-9h]
  int v19; // [rsp+68h] [rbp-1h]
  int v20; // [rsp+6Ch] [rbp+3h]
  _DWORD *v21; // [rsp+70h] [rbp+7h]
  __int64 v22; // [rsp+78h] [rbp+Fh]
  unsigned int *v23; // [rsp+80h] [rbp+17h]
  __int64 v24; // [rsp+88h] [rbp+1Fh]
  char *v25; // [rsp+90h] [rbp+27h]
  __int64 v26; // [rsp+98h] [rbp+2Fh]

  v6 = (signed __int64 *)(P + 264);
  _m_prefetchw(P + 264);
  v7 = *v6;
  v8 = *v6 + 1;
  v9 = v8 == 1;
  if ( v8 <= 1 )
  {
LABEL_5:
    if ( !v9 )
      __fastfail(0xEu);
  }
  else
  {
    while ( 1 )
    {
      v10 = v7;
      v7 = _InterlockedCompareExchange64((volatile signed __int64 *)P + 33, v8, v7);
      if ( v10 == v7 )
        break;
      v8 = v7 + 1;
      if ( v7 == -1 || v7 == 0 )
      {
        v9 = v8 == 1;
        goto LABEL_5;
      }
    }
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(P + 16, 0);
    v9 = (P[276] & 1) == 0;
    *((_QWORD *)P + 3) = KeGetCurrentThread();
    if ( !v9 )
    {
      ZwQueryInformationProcess(*((HANDLE *)P + 13), ProcessEnableAlignmentFaultFixup|0x40, P + 120, 0x30u, 0);
      v14 = (*((_DWORD *)P + 38) != 0 ? 2 : 0) | *((_DWORD *)P + 71) & 0xFFFFFFFC | (*((_DWORD *)P + 37) != 0);
      BampUpdateThrottledProcessState((__int64)P, 0, &v14, 0, 0);
      if ( (unsigned int)dword_140007010 > 4 )
      {
        v12 = *((_QWORD *)P + 1);
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        v13 = *(_DWORD *)(v12 + 464);
        v21 = v15;
        LOWORD(v14) = 7;
        v23 = &v14;
        v25 = P + 128;
        *(_DWORD *)&EventDescriptor.Level = 4;
        UserData.Ptr = (ULONGLONG)off_140007018;
        v15[0] = v13;
        v22 = 4;
        v24 = 2;
        v26 = 28;
        UserData.Size = *(unsigned __int16 *)off_140007018;
        v18 = word_140005562;
        UserData.Reserved = 2;
        v19 = 41;
        v20 = 1;
        v15[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
      }
    }
    *((_QWORD *)P + 3) = 0;
    ExReleasePushLockExclusiveEx(P + 16, 0);
    KeLeaveCriticalRegion();
    BampDereferenceThrottledProcessInformation(P);
  }
  return 0;
}

```

## disassembly

```asm
0x140014d20  mov     [rsp-8+arg_18], rdi
0x140014d25  push    rbp
0x140014d26  lea     rbp, [rsp-47h]
0x140014d2b  sub     rsp, 0B0h
0x140014d32  mov     rax, cs:__security_cookie
0x140014d39  xor     rax, rsp
0x140014d3c  mov     [rbp+47h+var_10], rax
0x140014d40  mov     rdi, [rbp+47h+P]
0x140014d44  prefetchw byte ptr [rdi+108h]
0x140014d4b  mov     rax, [rdi+108h]
0x140014d52  lea     rcx, [rax+1]
0x140014d56  cmp     rcx, 1
0x140014d5a  jbe     short loc_140014D7B
0x140014d5c  nop     dword ptr [rax+00h]
0x140014d60  lock cmpxchg [rdi+108h], rcx
0x140014d69  mov     rcx, rax
0x140014d6c  jz      short loc_140014DA4
0x140014d6e  inc     rcx
0x140014d71  cmp     rcx, 1
0x140014d75  ja      short loc_140014D60
0x140014d77  cmp     rcx, 1
0x140014d7b  jz      short loc_140014D84
0x140014d7d  mov     ecx, 0Eh
0x140014d82  int     29h; Win8: RtlFailFast(ecx)
0x140014d84  xor     eax, eax
0x140014d86  mov     rcx, [rbp+47h+var_10]
0x140014d8a  xor     rcx, rsp; StackCookie
0x140014d8d  call    __security_check_cookie
0x140014d92  mov     rdi, [rsp+0B0h+arg_18]
0x140014d9a  add     rsp, 0B0h
0x140014da1  pop     rbp
0x140014da2  retn
0x140014da4  mov     [rsp+0B0h+arg_8], rsi
0x140014dac  mov     [rsp+0B0h+arg_10], r14
0x140014db4  call    cs:__imp_KeEnterCriticalRegion
0x140014dbb  nop     dword ptr [rax+rax+00h]
0x140014dc0  xor     edx, edx
0x140014dc2  lea     rcx, [rdi+10h]
0x140014dc6  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140014dcd  nop     dword ptr [rax+rax+00h]
0x140014dd2  mov     rax, gs:188h
0x140014ddb  xor     r14d, r14d
0x140014dde  test    byte ptr [rdi+114h], 1
0x140014de5  mov     [rdi+18h], rax
0x140014de9  jz      loc_140014F48
0x140014def  mov     rcx, [rdi+68h]; ProcessHandle
0x140014df3  lea     r8, [rdi+78h]; ProcessInformation
0x140014df7  mov     r9d, 30h ; '0'; ProcessInformationLength
0x140014dfd  mov     [rsp+0B0h+arg_0], rbx
0x140014e05  mov     edx, 51h ; 'Q'; ProcessInformationClass
0x140014e0a  mov     [rsp+0B0h+ReturnLength], r14; ReturnLength
0x140014e0f  call    cs:__imp_ZwQueryInformationProcess
0x140014e16  nop     dword ptr [rax+rax+00h]
0x140014e1b  cmp     [rdi+94h], r14d
0x140014e22  lea     r8, [rbp+47h+var_80]
0x140014e26  mov     eax, [rdi+11Ch]
0x140014e2c  mov     edx, r14d
0x140014e2f  setnz   dl
0x140014e32  mov     [rsp+0B0h+ReturnLength], r14
0x140014e37  and     eax, 0FFFFFFFEh
0x140014e3a  or      edx, eax
0x140014e3c  mov     eax, [rdi+98h]
0x140014e42  and     edx, 0FFFFFFFDh
0x140014e45  neg     eax
0x140014e47  sbb     ecx, ecx
0x140014e49  xor     r9d, r9d
0x140014e4c  and     ecx, 2
0x140014e4f  or      edx, ecx
0x140014e51  mov     rcx, rdi
0x140014e54  mov     [rbp+47h+var_80], edx
0x140014e57  xor     edx, edx
0x140014e59  call    BampUpdateThrottledProcessState
0x140014e5e  mov     eax, cs:dword_140007010
0x140014e64  mov     rbx, [rsp+0B0h+arg_0]
0x140014e6c  cmp     eax, 4
0x140014e6f  jbe     loc_140014F48
0x140014e75  mov     rax, [rdi+8]
0x140014e79  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x140014e7d  mov     dword ptr [rbp+47h+EventDescriptor.Id], 0B000000h
0x140014e84  xor     r9d, r9d; RelatedActivityId
0x140014e87  mov     [rbp+47h+EventDescriptor.Keyword], r14
0x140014e8b  xor     r8d, r8d; ActivityId
0x140014e8e  mov     ecx, [rax+1D0h]
0x140014e94  lea     rax, [rbp+47h+var_7C]
0x140014e98  mov     [rbp+47h+var_40], rax
0x140014e9c  mov     eax, 7
0x140014ea1  mov     word ptr [rbp+47h+var_80], ax
0x140014ea5  lea     rax, [rbp+47h+var_80]
0x140014ea9  mov     [rbp+47h+var_30], rax
0x140014ead  lea     rax, [rdi+80h]
0x140014eb4  mov     [rbp+47h+var_20], rax
0x140014eb8  movzx   eax, cs:word_140005558
0x140014ebf  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x140014ec2  mov     rax, cs:off_140007018
0x140014ec9  mov     [rbp+47h+var_60.Ptr], rax
0x140014ecd  mov     [rbp+47h+var_7C], ecx
0x140014ed0  lea     rcx, _TraceLoggingMetadata
0x140014ed7  mov     [rbp+47h+var_38], 4
0x140014edf  mov     [rbp+47h+var_28], 2
0x140014ee7  mov     [rbp+47h+var_18], 1Ch
0x140014eef  movzx   eax, word ptr [rax]
0x140014ef2  mov     [rbp+47h+var_60.Size], eax
0x140014ef5  lea     rax, word_140005562
0x140014efc  mov     [rbp+47h+var_50], rax
0x140014f00  lea     rax, _TraceLoggingMetadataEnd
0x140014f07  sub     eax, ecx
0x140014f09  mov     dword ptr [rbp+47h+var_60.0Ch], 2
0x140014f10  mov     [rbp+47h+var_48], 29h ; ')'
0x140014f17  mov     [rbp+47h+var_44], 1
0x140014f1e  mov     [rbp+47h+var_78], eax
0x140014f21  mov     eax, [rbp+47h+var_78]
0x140014f24  mov     rcx, cs:RegHandle; RegHandle
0x140014f2b  lea     rax, [rbp+47h+var_60]
0x140014f2f  mov     [rsp+0B0h+UserData], rax; UserData
0x140014f34  mov     dword ptr [rsp+0B0h+ReturnLength], 5; UserDataCount
0x140014f3c  call    cs:__imp_EtwWriteTransfer
0x140014f43  nop     dword ptr [rax+rax+00h]
0x140014f48  xor     edx, edx
0x140014f4a  mov     [rdi+18h], r14
0x140014f4e  lea     rcx, [rdi+10h]
0x140014f52  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140014f59  nop     dword ptr [rax+rax+00h]
0x140014f5e  call    cs:__imp_KeLeaveCriticalRegion
0x140014f65  nop     dword ptr [rax+rax+00h]
0x140014f6a  mov     rcx, rdi; P
0x140014f6d  call    BampDereferenceThrottledProcessInformation
0x140014f72  mov     r14, [rsp+0B0h+arg_10]
0x140014f7a  mov     rsi, [rsp+0B0h+arg_8]
0x140014f82  jmp     loc_140014D84
```
