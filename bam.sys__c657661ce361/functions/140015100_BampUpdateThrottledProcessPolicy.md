# BampUpdateThrottledProcessPolicy

- ea: `0x140015100`
- end: `0x140015392`
- name: `BampUpdateThrottledProcessPolicy`
- size: `658`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000f460`

## callees

- `0x1400026d0`
- `0x1400100b0`
- `0x140010a30`
- `0x140013740`
- `0x140015100`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400151e9`
- `ntoskrnl!EtwWriteTransfer` at `0x140015303`
- `ntoskrnl!EtwWriteTransfer` at `0x1400151e9`
- `ntoskrnl!EtwWriteTransfer` at `0x140015303`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400151f5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400151f5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140015207`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140015207`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015325`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015349`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015325`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015349`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140015319`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001533d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140015319`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001533d`

## pseudocode

```c
void __fastcall BampUpdateThrottledProcessPolicy(_QWORD *P)
{
  __int64 v2; // rax
  int v3; // ecx
  __int64 v4; // rax
  int v5; // ecx
  int v6; // [rsp+30h] [rbp-49h] BYREF
  _DWORD v7[3]; // [rsp+34h] [rbp-45h] BYREF
  __int64 v8; // [rsp+40h] [rbp-39h] BYREF
  int v9; // [rsp+48h] [rbp-31h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-19h] BYREF
  int *v12; // [rsp+70h] [rbp-9h]
  int v13; // [rsp+78h] [rbp-1h]
  int v14; // [rsp+7Ch] [rbp+3h]
  int *v15; // [rsp+80h] [rbp+7h]
  __int64 v16; // [rsp+88h] [rbp+Fh]
  int *v17; // [rsp+90h] [rbp+17h]
  __int64 v18; // [rsp+98h] [rbp+1Fh]

  v8 = 0;
  v9 = 0;
  if ( (unsigned int)dword_140007010 > 5 )
  {
    v2 = P[1];
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    v3 = *(_DWORD *)(v2 + 464);
    v15 = &v6;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_140007018;
    v6 = v3;
    v16 = 4;
    UserData.Size = *(unsigned __int16 *)off_140007018;
    v12 = &dword_1400051E4;
    UserData.Reserved = 2;
    v13 = 36;
    v14 = 1;
    v7[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(P + 2, 0);
  P[3] = KeGetCurrentThread();
  BampComputeThrottledProcessPolicy(P, &v8);
  if ( P[44] == v8 && *((_DWORD *)P + 90) == v9 )
  {
    if ( (unsigned int)dword_140007010 > 5 )
    {
      v4 = P[1];
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      v5 = *(_DWORD *)(v4 + 464);
      v15 = v7;
      v6 = *((_DWORD *)P + 88);
      v17 = &v6;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_140007018;
      v7[0] = v5;
      v16 = 4;
      v18 = 4;
      UserData.Size = *(unsigned __int16 *)off_140007018;
      v12 = (int *)&byte_1400051A7;
      UserData.Reserved = 2;
      v13 = 49;
      v14 = 1;
      v7[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
    }
    P[3] = 0;
    ExReleasePushLockExclusiveEx(P + 2, 0);
    KeLeaveCriticalRegion();
  }
  else
  {
    P[3] = 0;
    ExReleasePushLockExclusiveEx(P + 2, 0);
    KeLeaveCriticalRegion();
    BampApplyThrottledProcessPolicy((__int64)P, (int *)&v8);
    BampUpdateThrottledProcessSiufState(P);
  }
}

```

## disassembly

```asm
0x140015100  mov     [rsp-8+arg_8], rbx
0x140015105  mov     [rsp-8+arg_10], rsi
0x14001510a  push    rbp
0x14001510b  push    rdi
0x14001510c  push    r12
0x14001510e  push    r14
0x140015110  push    r15
0x140015112  lea     rbp, [rsp-37h]
0x140015117  sub     rsp, 0B0h
0x14001511e  mov     rax, cs:__security_cookie
0x140015125  xor     rax, rsp
0x140015128  mov     [rbp+57h+var_30], rax
0x14001512c  xor     eax, eax
0x14001512e  lea     r14, _TraceLoggingMetadataEnd
0x140015135  mov     [rbp+57h+var_90], rax
0x140015139  lea     r12, _TraceLoggingMetadata
0x140015140  mov     [rbp+57h+var_88], eax
0x140015143  xor     r15d, r15d
0x140015146  mov     eax, cs:dword_140007010
0x14001514c  mov     rbx, rcx
0x14001514f  cmp     eax, 5
0x140015152  jbe     loc_1400151F5
0x140015158  mov     rax, [rcx+8]
0x14001515c  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140015160  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140015167  xor     r9d, r9d; RelatedActivityId
0x14001516a  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x14001516e  xor     r8d, r8d; ActivityId
0x140015171  mov     ecx, [rax+1D0h]
0x140015177  lea     rax, [rbp+57h+var_A0]
0x14001517b  mov     [rbp+57h+var_50], rax
0x14001517f  movzx   eax, cs:word_1400051DA
0x140015186  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x140015189  mov     rax, cs:off_140007018
0x140015190  mov     [rbp+57h+var_70.Ptr], rax
0x140015194  mov     [rbp+57h+var_A0], ecx
0x140015197  mov     [rbp+57h+var_48], 4
0x14001519f  movzx   eax, word ptr [rax]
0x1400151a2  mov     [rbp+57h+var_70.Size], eax
0x1400151a5  lea     rax, dword_1400051E4
0x1400151ac  mov     [rbp+57h+var_60], rax
0x1400151b0  mov     rax, r14
0x1400151b3  sub     eax, r12d
0x1400151b6  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x1400151bd  mov     [rbp+57h+var_58], 24h ; '$'
0x1400151c4  mov     [rbp+57h+var_54], 1
0x1400151cb  mov     [rbp+57h+var_9C], eax
0x1400151ce  mov     eax, [rbp+57h+var_9C]
0x1400151d1  mov     rcx, cs:RegHandle; RegHandle
0x1400151d8  lea     rax, [rbp+57h+var_70]
0x1400151dc  mov     [rsp+0D0h+UserData], rax; UserData
0x1400151e1  mov     [rsp+0D0h+UserDataCount], 3; UserDataCount
0x1400151e9  call    cs:__imp_EtwWriteTransfer
0x1400151f0  nop     dword ptr [rax+rax+00h]
0x1400151f5  call    cs:__imp_KeEnterCriticalRegion
0x1400151fc  nop     dword ptr [rax+rax+00h]
0x140015201  xor     edx, edx
0x140015203  lea     rcx, [rbx+10h]
0x140015207  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001520e  nop     dword ptr [rax+rax+00h]
0x140015213  mov     rax, gs:188h
0x14001521c  lea     rdx, [rbp+57h+var_90]
0x140015220  mov     rcx, rbx
0x140015223  mov     [rbx+18h], rax
0x140015227  call    BampComputeThrottledProcessPolicy
0x14001522c  mov     rax, [rbx+160h]
0x140015233  cmp     rax, [rbp+57h+var_90]
0x140015237  jnz     loc_140015333
0x14001523d  mov     eax, [rbx+168h]
0x140015243  cmp     eax, [rbp+57h+var_88]
0x140015246  jnz     loc_140015333
0x14001524c  mov     eax, cs:dword_140007010
0x140015252  cmp     eax, 5
0x140015255  jbe     loc_14001530F
0x14001525b  mov     rax, [rbx+8]
0x14001525f  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140015263  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x14001526a  sub     r14d, r12d
0x14001526d  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x140015271  xor     r9d, r9d; RelatedActivityId
0x140015274  xor     r8d, r8d; ActivityId
0x140015277  mov     ecx, [rax+1D0h]
0x14001527d  lea     rax, [rbp+57h+var_9C]
0x140015281  mov     [rbp+57h+var_50], rax
0x140015285  mov     eax, [rbx+160h]
0x14001528b  mov     [rbp+57h+var_A0], eax
0x14001528e  lea     rax, [rbp+57h+var_A0]
0x140015292  mov     [rbp+57h+var_40], rax
0x140015296  movzx   eax, cs:word_14000519D
0x14001529d  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1400152a0  mov     rax, cs:off_140007018
0x1400152a7  mov     [rbp+57h+var_70.Ptr], rax
0x1400152ab  mov     [rbp+57h+var_9C], ecx
0x1400152ae  mov     [rbp+57h+var_48], 4
0x1400152b6  mov     [rbp+57h+var_38], 4
0x1400152be  movzx   eax, word ptr [rax]
0x1400152c1  mov     [rbp+57h+var_70.Size], eax
0x1400152c4  lea     rax, byte_1400051A7
0x1400152cb  mov     [rbp+57h+var_60], rax
0x1400152cf  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x1400152d6  mov     [rbp+57h+var_58], 31h ; '1'
0x1400152dd  mov     [rbp+57h+var_54], 1
0x1400152e4  mov     [rbp+57h+var_98], r14d
0x1400152e8  mov     eax, [rbp+57h+var_98]
0x1400152eb  mov     rcx, cs:RegHandle; RegHandle
0x1400152f2  lea     rax, [rbp+57h+var_70]
0x1400152f6  mov     [rsp+0D0h+UserData], rax; UserData
0x1400152fb  mov     [rsp+0D0h+UserDataCount], 4; UserDataCount
0x140015303  call    cs:__imp_EtwWriteTransfer
0x14001530a  nop     dword ptr [rax+rax+00h]
0x14001530f  xor     edx, edx
0x140015311  mov     [rbx+18h], r15
0x140015315  lea     rcx, [rbx+10h]
0x140015319  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140015320  nop     dword ptr [rax+rax+00h]
0x140015325  call    cs:__imp_KeLeaveCriticalRegion
0x14001532c  nop     dword ptr [rax+rax+00h]
0x140015331  jmp     short loc_140015369
0x140015333  xor     edx, edx
0x140015335  mov     [rbx+18h], r15
0x140015339  lea     rcx, [rbx+10h]
0x14001533d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140015344  nop     dword ptr [rax+rax+00h]
0x140015349  call    cs:__imp_KeLeaveCriticalRegion
0x140015350  nop     dword ptr [rax+rax+00h]
0x140015355  lea     rdx, [rbp+57h+var_90]
0x140015359  mov     rcx, rbx
0x14001535c  call    BampApplyThrottledProcessPolicy
0x140015361  mov     rcx, rbx; P
0x140015364  call    BampUpdateThrottledProcessSiufState
0x140015369  mov     rcx, [rbp+57h+var_30]
0x14001536d  xor     rcx, rsp; StackCookie
0x140015370  call    __security_check_cookie
0x140015375  lea     r11, [rsp+0D0h+var_20]
0x14001537d  mov     rbx, [r11+38h]
0x140015381  mov     rsi, [r11+40h]
0x140015385  mov     rsp, r11
0x140015388  pop     r15
0x14001538a  pop     r14
0x14001538c  pop     r12
0x14001538e  pop     rdi
0x14001538f  pop     rbp
0x140015390  retn
```
