# BampUpdateThrottledProcessState

- ea: `0x1400153a0`
- end: `0x140015600`
- name: `BampUpdateThrottledProcessState`
- size: `608`
- prototype: `NTSTATUS __fastcall(__int64, _DWORD *, _DWORD *, __int64, _DWORD *)`
- caller_count: `6`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000c3f0`
- `0x14000c6f0`
- `0x14001202c`
- `0x140012eec`
- `0x140014d20`
- `0x140014f90`

## callees

- `0x1400026d0`
- `0x140011160`
- `0x1400153a0`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400155d2`
- `ntoskrnl!EtwWriteTransfer` at `0x1400155d2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015442`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015442`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140015457`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140015457`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001549f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001549f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140015493`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140015493`

## pseudocode

```c
NTSTATUS __fastcall BampUpdateThrottledProcessState(__int64 a1, _DWORD *a2, _DWORD *a3, __int64 a4, _DWORD *a5)
{
  NTSTATUS result; // eax
  __int64 v7; // rax
  int v8; // ecx
  int v9; // [rsp+30h] [rbp-71h] BYREF
  int v10; // [rsp+34h] [rbp-6Dh] BYREF
  int v11; // [rsp+38h] [rbp-69h] BYREF
  int v12; // [rsp+3Ch] [rbp-65h] BYREF
  int v13; // [rsp+40h] [rbp-61h] BYREF
  _DWORD v14[3]; // [rsp+44h] [rbp-5Dh] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-41h] BYREF
  void *v17; // [rsp+70h] [rbp-31h]
  int v18; // [rsp+78h] [rbp-29h]
  int v19; // [rsp+7Ch] [rbp-25h]
  int *v20; // [rsp+80h] [rbp-21h]
  __int64 v21; // [rsp+88h] [rbp-19h]
  int *v22; // [rsp+90h] [rbp-11h]
  __int64 v23; // [rsp+98h] [rbp-9h]
  int *v24; // [rsp+A0h] [rbp-1h]
  __int64 v25; // [rsp+A8h] [rbp+7h]
  int *v26; // [rsp+B0h] [rbp+Fh]
  __int64 v27; // [rsp+B8h] [rbp+17h]
  int *v28; // [rsp+C0h] [rbp+1Fh]
  __int64 v29; // [rsp+C8h] [rbp+27h]
  _DWORD *v30; // [rsp+D0h] [rbp+2Fh]
  __int64 v31; // [rsp+D8h] [rbp+37h]

  if ( a2 )
    *(_DWORD *)(a1 + 280) = *a2;
  if ( a3 )
    *(_DWORD *)(a1 + 284) = *a3;
  if ( a4 )
  {
    *(_QWORD *)(a1 + 288) = *(_QWORD *)a4;
    *(_DWORD *)(a1 + 296) = *(_DWORD *)(a4 + 8);
  }
  if ( a5 )
    *(_DWORD *)(a1 + 300) = *a5;
  if ( *(_QWORD *)(a1 + 280) != *(_QWORD *)(a1 + 304)
    || *(_QWORD *)(a1 + 288) != *(_QWORD *)(a1 + 312)
    || *(_QWORD *)(a1 + 296) != *(_QWORD *)(a1 + 320) )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&qword_140007588, 0);
    qword_140007590 = (__int64)KeGetCurrentThread();
    BampQueueThrottledProcessActionItem(a1, 0, 0, 0);
    qword_140007590 = 0;
    ExReleasePushLockExclusiveEx(&qword_140007588, 0);
    KeLeaveCriticalRegion();
  }
  result = dword_140007010;
  if ( (unsigned int)dword_140007010 > 4 )
  {
    v7 = *(_QWORD *)(a1 + 8);
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    v8 = *(_DWORD *)(v7 + 464);
    v20 = &v9;
    v10 = *(_DWORD *)(a1 + 280);
    v22 = &v10;
    v11 = *(_DWORD *)(a1 + 284);
    v24 = &v11;
    v12 = *(_DWORD *)(a1 + 292);
    v26 = &v12;
    v13 = *(_DWORD *)(a1 + 296);
    v28 = &v13;
    v14[0] = *(_DWORD *)(a1 + 300);
    v30 = v14;
    *(_DWORD *)&EventDescriptor.Level = 4;
    UserData.Ptr = (ULONGLONG)off_140007018;
    v9 = v8;
    v21 = 4;
    v23 = 4;
    v25 = 4;
    v27 = 4;
    v29 = 4;
    v31 = 4;
    UserData.Size = *(unsigned __int16 *)off_140007018;
    v17 = &unk_140005708;
    UserData.Reserved = 2;
    v18 = 93;
    v19 = 1;
    v14[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    return EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 8u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x1400153a0  mov     [rsp-8+arg_8], rbx
0x1400153a5  mov     [rsp-8+arg_10], rdi
0x1400153aa  push    rbp
0x1400153ab  lea     rbp, [rsp-4Fh]
0x1400153b0  sub     rsp, 0F0h
0x1400153b7  mov     rax, cs:__security_cookie
0x1400153be  xor     rax, rsp
0x1400153c1  mov     [rbp+4Fh+var_10], rax
0x1400153c5  mov     rbx, rcx
0x1400153c8  test    rdx, rdx
0x1400153cb  jz      short loc_1400153D5
0x1400153cd  mov     eax, [rdx]
0x1400153cf  mov     [rcx+118h], eax
0x1400153d5  test    r8, r8
0x1400153d8  jz      short loc_1400153E3
0x1400153da  mov     eax, [r8]
0x1400153dd  mov     [rcx+11Ch], eax
0x1400153e3  test    r9, r9
0x1400153e6  jz      short loc_1400153FF
0x1400153e8  movsd   xmm0, qword ptr [r9]
0x1400153ed  movsd   qword ptr [rcx+120h], xmm0
0x1400153f5  mov     eax, [r9+8]
0x1400153f9  mov     [rcx+128h], eax
0x1400153ff  mov     rax, [rbp+4Fh+arg_20]
0x140015403  test    rax, rax
0x140015406  jz      short loc_140015410
0x140015408  mov     eax, [rax]
0x14001540a  mov     [rcx+12Ch], eax
0x140015410  mov     rax, [rcx+118h]
0x140015417  xor     edi, edi
0x140015419  cmp     rax, [rcx+130h]
0x140015420  jnz     short loc_140015442
0x140015422  mov     rax, [rcx+120h]
0x140015429  cmp     rax, [rcx+138h]
0x140015430  jnz     short loc_140015442
0x140015432  mov     rax, [rcx+128h]
0x140015439  cmp     rax, [rcx+140h]
0x140015440  jz      short loc_1400154AB
0x140015442  call    cs:__imp_KeEnterCriticalRegion
0x140015449  nop     dword ptr [rax+rax+00h]
0x14001544e  xor     edx, edx
0x140015450  lea     rcx, qword_140007588
0x140015457  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001545e  nop     dword ptr [rax+rax+00h]
0x140015463  mov     rax, gs:188h
0x14001546c  xor     r9d, r9d
0x14001546f  xor     r8d, r8d
0x140015472  mov     cs:qword_140007590, rax
0x140015479  xor     edx, edx
0x14001547b  mov     rcx, rbx
0x14001547e  call    BampQueueThrottledProcessActionItem
0x140015483  xor     edx, edx
0x140015485  mov     cs:qword_140007590, rdi
0x14001548c  lea     rcx, qword_140007588
0x140015493  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001549a  nop     dword ptr [rax+rax+00h]
0x14001549f  call    cs:__imp_KeLeaveCriticalRegion
0x1400154a6  nop     dword ptr [rax+rax+00h]
0x1400154ab  mov     eax, cs:dword_140007010
0x1400154b1  cmp     eax, 4
0x1400154b4  jbe     loc_1400155DE
0x1400154ba  mov     rax, [rbx+8]
0x1400154be  lea     rdx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x1400154c2  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], 0B000000h
0x1400154c9  xor     r9d, r9d; RelatedActivityId
0x1400154cc  mov     [rbp+4Fh+EventDescriptor.Keyword], rdi
0x1400154d0  xor     r8d, r8d; ActivityId
0x1400154d3  mov     ecx, [rax+1D0h]
0x1400154d9  lea     rax, [rbp+4Fh+var_C0]
0x1400154dd  mov     [rbp+4Fh+var_70], rax
0x1400154e1  mov     eax, [rbx+118h]
0x1400154e7  mov     [rbp+4Fh+var_BC], eax
0x1400154ea  lea     rax, [rbp+4Fh+var_BC]
0x1400154ee  mov     [rbp+4Fh+var_60], rax
0x1400154f2  mov     eax, [rbx+11Ch]
0x1400154f8  mov     [rbp+4Fh+var_B8], eax
0x1400154fb  lea     rax, [rbp+4Fh+var_B8]
0x1400154ff  mov     [rbp+4Fh+var_50], rax
0x140015503  mov     eax, [rbx+124h]
0x140015509  mov     [rbp+4Fh+var_B4], eax
0x14001550c  lea     rax, [rbp+4Fh+var_B4]
0x140015510  mov     [rbp+4Fh+var_40], rax
0x140015514  mov     eax, [rbx+128h]
0x14001551a  mov     [rbp+4Fh+var_B0], eax
0x14001551d  lea     rax, [rbp+4Fh+var_B0]
0x140015521  mov     [rbp+4Fh+var_30], rax
0x140015525  mov     eax, [rbx+12Ch]
0x14001552b  mov     [rbp+4Fh+var_AC], eax
0x14001552e  lea     rax, [rbp+4Fh+var_AC]
0x140015532  mov     [rbp+4Fh+var_20], rax
0x140015536  movzx   eax, cs:word_1400056FE
0x14001553d  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], eax
0x140015540  mov     rax, cs:off_140007018
0x140015547  mov     [rbp+4Fh+var_90.Ptr], rax
0x14001554b  mov     [rbp+4Fh+var_C0], ecx
0x14001554e  lea     rcx, _TraceLoggingMetadata
0x140015555  mov     [rbp+4Fh+var_68], 4
0x14001555d  mov     [rbp+4Fh+var_58], 4
0x140015565  mov     [rbp+4Fh+var_48], 4
0x14001556d  mov     [rbp+4Fh+var_38], 4
0x140015575  mov     [rbp+4Fh+var_28], 4
0x14001557d  mov     [rbp+4Fh+var_18], 4
0x140015585  movzx   eax, word ptr [rax]
0x140015588  mov     [rbp+4Fh+var_90.Size], eax
0x14001558b  lea     rax, unk_140005708
0x140015592  mov     [rbp+4Fh+var_80], rax
0x140015596  lea     rax, _TraceLoggingMetadataEnd
0x14001559d  sub     eax, ecx
0x14001559f  mov     dword ptr [rbp+4Fh+var_90.0Ch], 2
0x1400155a6  mov     [rbp+4Fh+var_78], 5Dh ; ']'
0x1400155ad  mov     [rbp+4Fh+var_74], 1
0x1400155b4  mov     [rbp+4Fh+var_A8], eax
0x1400155b7  mov     eax, [rbp+4Fh+var_A8]
0x1400155ba  mov     rcx, cs:RegHandle; RegHandle
0x1400155c1  lea     rax, [rbp+4Fh+var_90]
0x1400155c5  mov     [rsp+0F0h+UserData], rax; UserData
0x1400155ca  mov     [rsp+0F0h+UserDataCount], 8; UserDataCount
0x1400155d2  call    cs:__imp_EtwWriteTransfer
0x1400155d9  nop     dword ptr [rax+rax+00h]
0x1400155de  mov     rcx, [rbp+4Fh+var_10]
0x1400155e2  xor     rcx, rsp; StackCookie
0x1400155e5  call    __security_check_cookie
0x1400155ea  lea     r11, [rsp+0F0h+var_s0]
0x1400155f2  mov     rbx, [r11+18h]
0x1400155f6  mov     rdi, [r11+20h]
0x1400155fa  mov     rsp, r11
0x1400155fd  pop     rbp
0x1400155fe  retn
```
