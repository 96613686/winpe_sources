# UbpmConsumerDecPendingActions

- ea: `0x180008720`
- end: `0x180008914`
- name: `UbpmConsumerDecPendingActions`
- size: `500`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002ec0`
- `0x180003100`
- `0x180007ec0`
- `0x18000f880`
- `0x180011480`
- `0x1800282b0`
- `0x1800293d0`
- `0x18002d260`
- `0x18002d890`

## callees

- `0x180008720`
- `0x180036d44`
- `0x180040260`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008746`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008746`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800088ef`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800088ef`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18000877d`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18000877d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800088dc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800088dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008752`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008752`

## pseudocode

```c
__int64 __fastcall UbpmConsumerDecPendingActions(__int64 a1)
{
  __int64 v2; // rcx
  bool v3; // zf
  int v4; // edx
  int v5; // eax
  __int64 v6; // rax
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  int v11; // [rsp+34h] [rbp-75h] BYREF
  int v12; // [rsp+38h] [rbp-71h] BYREF
  int v13; // [rsp+3Ch] [rbp-6Dh] BYREF
  __int64 v14; // [rsp+40h] [rbp-69h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-61h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-49h] BYREF
  char *v17; // [rsp+70h] [rbp-39h]
  int v18; // [rsp+78h] [rbp-31h]
  int v19; // [rsp+7Ch] [rbp-2Dh]
  __int64 *v20; // [rsp+80h] [rbp-29h]
  int v21; // [rsp+88h] [rbp-21h]
  int v22; // [rsp+8Ch] [rbp-1Dh]
  int *v23; // [rsp+90h] [rbp-19h]
  __int64 v24; // [rsp+98h] [rbp-11h]
  int *v25; // [rsp+A0h] [rbp-9h]
  __int64 v26; // [rsp+A8h] [rbp-1h]
  __int64 *v27; // [rsp+B0h] [rbp+7h]
  __int64 v28; // [rsp+B8h] [rbp+Fh]
  int *v29; // [rsp+C0h] [rbp+17h]
  __int64 v30; // [rsp+C8h] [rbp+1Fh]

  RtlAcquireSRWLockExclusive(a1 + 72);
  *(_DWORD *)(a1 + 80) = GetCurrentThreadId();
  if ( *(int *)(a1 + 88) <= 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v2);
  v3 = (*(_DWORD *)(a1 + 88))-- == 1;
  v4 = 0;
  if ( v3 )
  {
    WakeConditionVariable((PCONDITION_VARIABLE)(a1 + 96));
    v4 = 1;
  }
  if ( (unsigned int)dword_18004F0F0 > 5 && (qword_18004F100 & 1) != 0 && (qword_18004F108 & 1) == qword_18004F108 )
  {
    v5 = *(_DWORD *)(a1 + 92) & 1;
    v11 = v4;
    v12 = v5;
    v13 = *(_DWORD *)(a1 + 88);
    v6 = *(_QWORD *)(a1 + 24);
    v14 = a1;
    v30 = 4;
    v28 = 8;
    v7 = *(__int64 **)(v6 + 8);
    v29 = &v11;
    v27 = &v14;
    v25 = &v12;
    v23 = &v13;
    v26 = 4;
    v24 = 4;
    if ( v7 )
    {
      v8 = -1;
      do
        v3 = *((_WORD *)v7 + ++v8) == 0;
      while ( !v3 );
      v9 = 2 * v8 + 2;
    }
    else
    {
      v7 = &qword_1800439C0;
      v9 = 2;
    }
    v21 = v9;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18004F0F8;
    v20 = v7;
    v22 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 1;
    UserData.Size = *(unsigned __int16 *)off_18004F0F8;
    v17 = byte_180045F41;
    UserData.Reserved = 2;
    v18 = 114;
    v19 = 1;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 7u, &UserData);
  }
  *(_DWORD *)(a1 + 80) = 0;
  return RtlReleaseSRWLockExclusive(a1 + 72);
}

```

## disassembly

```asm
0x180008720  push    rbp
0x180008722  push    rbx
0x180008723  push    rsi
0x180008724  push    rdi
0x180008725  lea     rbp, [rsp-3Fh]
0x18000872a  sub     rsp, 0E8h
0x180008731  mov     rax, cs:__security_cookie
0x180008738  xor     rax, rsp
0x18000873b  mov     [rbp+57h+var_30], rax
0x18000873f  mov     rbx, rcx
0x180008742  add     rcx, 48h ; 'H'
0x180008746  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000874d  nop     dword ptr [rax+rax+00h]
0x180008752  call    cs:__imp_GetCurrentThreadId
0x180008759  nop     dword ptr [rax+rax+00h]
0x18000875e  mov     [rbx+50h], eax
0x180008761  cmp     dword ptr [rbx+58h], 0
0x180008765  jg      short loc_18000876C
0x180008767  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000876c  sub     dword ptr [rbx+58h], 1
0x180008770  mov     esi, 0
0x180008775  mov     edx, esi
0x180008777  jnz     short loc_18000878E
0x180008779  lea     rcx, [rbx+60h]; ConditionVariable
0x18000877d  call    cs:__imp_WakeConditionVariable
0x180008784  nop     dword ptr [rax+rax+00h]
0x180008789  mov     edx, 1
0x18000878e  mov     eax, cs:dword_18004F0F0
0x180008794  cmp     eax, 5
0x180008797  jbe     loc_1800088E8
0x18000879d  mov     rcx, cs:qword_18004F108
0x1800087a4  mov     rax, cs:qword_18004F100
0x1800087ab  test    al, 1
0x1800087ad  jz      loc_1800088E8
0x1800087b3  mov     rax, rcx
0x1800087b6  and     eax, 1
0x1800087b9  cmp     rax, rcx
0x1800087bc  jnz     loc_1800088E8
0x1800087c2  mov     eax, [rbx+5Ch]
0x1800087c5  and     eax, 1
0x1800087c8  mov     [rbp+57h+var_CC], edx
0x1800087cb  mov     [rbp+57h+var_C8], eax
0x1800087ce  mov     eax, [rbx+58h]
0x1800087d1  mov     [rbp+57h+var_C4], eax
0x1800087d4  mov     rax, [rbx+18h]
0x1800087d8  mov     [rbp+57h+var_C0], rbx
0x1800087dc  mov     [rbp+57h+var_38], 4
0x1800087e4  mov     [rbp+57h+var_48], 8
0x1800087ec  mov     rcx, [rax+8]
0x1800087f0  lea     rax, [rbp+57h+var_CC]
0x1800087f4  mov     [rbp+57h+var_40], rax
0x1800087f8  lea     rax, [rbp+57h+var_C0]
0x1800087fc  mov     [rbp+57h+var_50], rax
0x180008800  lea     rax, [rbp+57h+var_C8]
0x180008804  mov     [rbp+57h+var_60], rax
0x180008808  lea     rax, [rbp+57h+var_C4]
0x18000880c  mov     [rbp+57h+var_70], rax
0x180008810  mov     [rbp+57h+var_58], 4
0x180008818  mov     [rbp+57h+var_68], 4
0x180008820  test    rcx, rcx
0x180008823  jz      short loc_180008844
0x180008825  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000882c  nop     dword ptr [rax+00h]
0x180008830  cmp     [rcx+rax*2+2], si
0x180008835  lea     rax, [rax+1]
0x180008839  jnz     short loc_180008830
0x18000883b  lea     eax, ds:2[rax*2]
0x180008842  jmp     short loc_180008850
0x180008844  lea     rcx, qword_1800439C0
0x18000884b  mov     eax, 2
0x180008850  mov     [rbp+57h+var_78], eax
0x180008853  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180008857  movzx   eax, cs:word_180045F37
0x18000885e  xor     r9d, r9d; RelatedActivityId
0x180008861  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180008864  xor     r8d, r8d; ActivityId
0x180008867  mov     rax, cs:off_18004F0F8
0x18000886e  mov     [rbp+57h+var_A0.Ptr], rax
0x180008872  mov     [rbp+57h+var_80], rcx
0x180008876  lea     rcx, _TraceLoggingMetadata
0x18000887d  mov     [rbp+57h+var_74], esi
0x180008880  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180008887  mov     [rbp+57h+EventDescriptor.Keyword], 1
0x18000888f  movzx   eax, word ptr [rax]
0x180008892  mov     [rbp+57h+var_A0.Size], eax
0x180008895  lea     rax, byte_180045F41
0x18000889c  mov     [rbp+57h+var_90], rax
0x1800088a0  lea     rax, _TraceLoggingMetadataEnd
0x1800088a7  sub     eax, ecx
0x1800088a9  mov     dword ptr [rbp+57h+var_A0.0Ch], 2
0x1800088b0  mov     [rbp+57h+var_88], 72h ; 'r'
0x1800088b7  mov     [rbp+57h+var_84], 1
0x1800088be  mov     [rbp+57h+var_D0], eax
0x1800088c1  mov     eax, [rbp+57h+var_D0]
0x1800088c4  mov     rcx, cs:RegHandle; RegHandle
0x1800088cb  lea     rax, [rbp+57h+var_A0]
0x1800088cf  mov     [rsp+100h+UserData], rax; UserData
0x1800088d4  mov     [rsp+100h+UserDataCount], 7; UserDataCount
0x1800088dc  call    cs:__imp_EventWriteTransfer
0x1800088e3  nop     dword ptr [rax+rax+00h]
0x1800088e8  lea     rcx, [rbx+48h]
0x1800088ec  mov     [rbx+50h], esi
0x1800088ef  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800088f6  nop     dword ptr [rax+rax+00h]
0x1800088fb  mov     rcx, [rbp+57h+var_30]
0x1800088ff  xor     rcx, rsp; StackCookie
0x180008902  call    __security_check_cookie
0x180008907  add     rsp, 0E8h
0x18000890e  pop     rdi
0x18000890f  pop     rsi
0x180008910  pop     rbx
0x180008911  pop     rbp
0x180008912  retn
```
