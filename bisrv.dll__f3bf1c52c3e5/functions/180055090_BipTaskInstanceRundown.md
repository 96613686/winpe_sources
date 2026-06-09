# BipTaskInstanceRundown

- ea: `0x180055090`
- end: `0x1800553a9`
- name: `BipTaskInstanceRundown`
- size: `793`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180059ad0`

## callees

- `0x18001542c`
- `0x180055090`
- `0x180060c28`
- `0x1800946a0`
- `0x180095010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800551e5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180055229`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005532f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180055369`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800551e5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180055229`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005532f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180055369`
- `ntdll!TpReleaseTimer` at `0x1800552c8`
- `ntdll!TpReleaseTimer` at `0x180055309`
- `ntdll!TpReleaseTimer` at `0x1800552c8`
- `ntdll!TpReleaseTimer` at `0x180055309`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180055208`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180055282`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180055348`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005537b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180055208`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180055282`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180055348`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005537b`
- `ntdll!TpWaitForTimer` at `0x1800552bf`
- `ntdll!TpWaitForTimer` at `0x180055300`
- `ntdll!TpWaitForTimer` at `0x1800552bf`
- `ntdll!TpWaitForTimer` at `0x180055300`
- `ntdll!TpSetTimer` at `0x1800552b1`
- `ntdll!TpSetTimer` at `0x1800552f2`
- `ntdll!TpSetTimer` at `0x1800552b1`
- `ntdll!TpSetTimer` at `0x1800552f2`
- `ntdll!RtlWaitOnAddress` at `0x18005521f`
- `ntdll!RtlWaitOnAddress` at `0x18005535f`
- `ntdll!RtlWaitOnAddress` at `0x18005521f`
- `ntdll!RtlWaitOnAddress` at `0x18005535f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800551db`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800551db`

## pseudocode

```c
__int64 __fastcall BipTaskInstanceRundown(__int64 a1)
{
  __int64 v2; // rcx
  GUID v3; // xmm1
  GUID *v4; // rax
  unsigned int *v5; // rdi
  unsigned int v6; // eax
  __int64 v7; // r15
  __int64 v8; // r12
  __int64 v9; // r14
  __int64 v10; // r13
  unsigned int i; // eax
  unsigned int v13; // [rsp+30h] [rbp-89h] BYREF
  __int64 v14; // [rsp+38h] [rbp-81h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-79h] BYREF
  __int128 v16; // [rsp+50h] [rbp-69h] BYREF
  GUID v17; // [rsp+60h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-49h] BYREF
  char *v19; // [rsp+80h] [rbp-39h]
  int v20; // [rsp+88h] [rbp-31h]
  int v21; // [rsp+8Ch] [rbp-2Dh]
  GUID *v22; // [rsp+90h] [rbp-29h]
  __int64 v23; // [rsp+98h] [rbp-21h]
  __int128 *v24; // [rsp+A0h] [rbp-19h]
  __int64 v25; // [rsp+A8h] [rbp-11h]
  __int64 v26; // [rsp+B0h] [rbp-9h]
  __int64 v27; // [rsp+B8h] [rbp-1h]

  v13 = 0;
  v2 = *(_QWORD *)(a1 + 64);
  if ( (unsigned int)dword_1800C3098 > 5 && (qword_1800C30A8 & 2) != 0 && (qword_1800C30B0 & 2) == qword_1800C30B0 )
  {
    v3 = GUID_NULL;
    if ( v2 )
    {
      v4 = *(GUID **)(v2 + 72);
      v16 = *(_OWORD *)(v2 + 32);
      if ( v4 )
        v3 = v4[2];
    }
    else
    {
      v16 = 0;
    }
    v17 = v3;
    v24 = &v16;
    v26 = a1;
    v22 = &v17;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    v27 = 16;
    v25 = 16;
    v23 = 16;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 2;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v19 = byte_1800AE865;
    UserData.Reserved = 2;
    v20 = 53;
    v21 = 1;
    LODWORD(v14) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
  }
  RtlAcquireSRWLockExclusive(a1 + 48);
  v5 = (unsigned int *)(a1 + 136);
  v6 = *(_DWORD *)(a1 + 136);
  if ( (v6 & 0x800) != 0 )
  {
    do
    {
      v13 = v6;
      RtlReleaseSRWLockExclusive(a1 + 48);
      RtlWaitOnAddress(a1 + 136, &v13, 4, 0);
      RtlAcquireSRWLockExclusive(a1 + 48);
      v6 = *v5;
    }
    while ( (*v5 & 0x800) != 0 );
  }
  v7 = *(_QWORD *)(a1 + 128);
  v8 = *(_QWORD *)(a1 + 112);
  v9 = *(_QWORD *)(a1 + 120);
  v14 = *(_QWORD *)(a1 + 312);
  *(_QWORD *)(a1 + 312) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  v10 = *(_QWORD *)(a1 + 80);
  *v5 = v6 & 0xFFFEFBFF | 0x10000;
  *(_QWORD *)(a1 + 80) = 0;
  RtlReleaseSRWLockExclusive(a1 + 48);
  if ( v14 )
    (*((void (__fastcall **)(__int64))&xmmword_1800C41C0 + 1))(v14);
  if ( v7 )
  {
    TpSetTimer(v7, 0, 0, 0);
    TpWaitForTimer(v7, 1);
    TpReleaseTimer(v7);
  }
  if ( v8 )
    (*((void (__fastcall **)(__int64))&xmmword_1800C41C0 + 1))(v8);
  if ( v9 )
  {
    TpSetTimer(v9, 0, 0, 0);
    TpWaitForTimer(v9, 1);
    TpReleaseTimer(v9);
  }
  if ( v10 )
    (*((void (__fastcall **)(__int64))&xmmword_1800C4150 + 1))(v10);
  BipTaskInstanceReleaseSystemResource(a1);
  RtlAcquireSRWLockExclusive(a1 + 48);
  for ( i = *v5; (*v5 & 0x1000) != 0; i = *v5 )
  {
    v13 = i;
    RtlReleaseSRWLockExclusive(a1 + 48);
    RtlWaitOnAddress(a1 + 136, &v13, 4, 0);
    RtlAcquireSRWLockExclusive(a1 + 48);
  }
  RtlReleaseSRWLockExclusive(a1 + 48);
  return BipStandbyBudgetCheckRecordTaskInstanceRuntime(a1);
}

```

## disassembly

```asm
0x180055090  push    rbp
0x180055092  push    rbx
0x180055093  push    rsi
0x180055094  push    rdi
0x180055095  push    r12
0x180055097  push    r13
0x180055099  push    r14
0x18005509b  push    r15
0x18005509d  lea     rbp, [rsp-1Fh]
0x1800550a2  sub     rsp, 0D8h
0x1800550a9  mov     rax, cs:__security_cookie
0x1800550b0  xor     rax, rsp
0x1800550b3  mov     [rbp+57h+var_50], rax
0x1800550b7  mov     eax, cs:dword_1800C3098
0x1800550bd  xor     r13d, r13d
0x1800550c0  mov     [rsp+110h+var_E0], r13d
0x1800550c5  mov     rsi, rcx
0x1800550c8  mov     rcx, [rcx+40h]
0x1800550cc  cmp     eax, 5
0x1800550cf  jbe     loc_1800551E1
0x1800550d5  mov     rdx, cs:qword_1800C30B0
0x1800550dc  mov     rax, cs:qword_1800C30A8
0x1800550e3  test    al, 2
0x1800550e5  jz      loc_1800551E1
0x1800550eb  mov     rax, rdx
0x1800550ee  and     eax, 2
0x1800550f1  cmp     rax, rdx
0x1800550f4  jnz     loc_1800551E1
0x1800550fa  xorps   xmm0, xmm0
0x1800550fd  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180055104  test    rcx, rcx
0x180055107  jz      short loc_180055121
0x180055109  movups  xmm0, xmmword ptr [rcx+20h]
0x18005510d  mov     rax, [rcx+48h]
0x180055111  movdqa  [rbp+57h+var_C0], xmm0
0x180055116  test    rax, rax
0x180055119  jz      short loc_180055126
0x18005511b  movups  xmm1, xmmword ptr [rax+20h]
0x18005511f  jmp     short loc_180055126
0x180055121  movdqa  [rbp+57h+var_C0], xmm0
0x180055126  movdqa  [rbp+57h+var_B0], xmm1
0x18005512b  lea     rax, [rbp+57h+var_C0]
0x18005512f  mov     [rbp+57h+var_70], rax
0x180055133  lea     rcx, _TraceLoggingMetadata
0x18005513a  lea     rax, [rbp+57h+var_B0]
0x18005513e  mov     [rbp+57h+var_60], rsi
0x180055142  mov     [rbp+57h+var_80], rax
0x180055146  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18005514a  movzx   eax, cs:word_1800AE85B
0x180055151  xor     r9d, r9d; RelatedActivityId
0x180055154  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180055157  xor     r8d, r8d; ActivityId
0x18005515a  mov     rax, cs:off_1800C30A0
0x180055161  mov     [rbp+57h+var_A0.Ptr], rax
0x180055165  mov     [rbp+57h+var_58], 10h
0x18005516d  mov     [rbp+57h+var_68], 10h
0x180055175  mov     [rbp+57h+var_78], 10h
0x18005517d  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180055184  mov     [rbp+57h+EventDescriptor.Keyword], 2
0x18005518c  movzx   eax, word ptr [rax]
0x18005518f  mov     [rbp+57h+var_A0.Size], eax
0x180055192  lea     rax, byte_1800AE865
0x180055199  mov     [rbp+57h+var_90], rax
0x18005519d  lea     rax, _TraceLoggingMetadataEnd
0x1800551a4  sub     eax, ecx
0x1800551a6  mov     dword ptr [rbp+57h+var_A0.0Ch], 2
0x1800551ad  mov     [rbp+57h+var_88], 35h ; '5'
0x1800551b4  mov     [rbp+57h+var_84], 1
0x1800551bb  mov     dword ptr [rsp+110h+var_D8], eax
0x1800551bf  mov     eax, dword ptr [rsp+110h+var_D8]
0x1800551c3  mov     rcx, cs:RegHandle; RegHandle
0x1800551ca  lea     rax, [rbp+57h+var_A0]
0x1800551ce  mov     [rsp+110h+UserData], rax; UserData
0x1800551d3  mov     [rsp+110h+UserDataCount], 5; UserDataCount
0x1800551db  call    cs:__imp_EventWriteTransfer
0x1800551e1  lea     rcx, [rsi+30h]
0x1800551e5  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800551eb  lea     rdi, [rsi+88h]
0x1800551f2  mov     eax, [rdi]
0x1800551f4  bt      eax, 0Bh
0x1800551f8  jnb     short loc_180055237
0x1800551fa  nop     word ptr [rax+rax+00h]
0x180055200  lea     rcx, [rsi+30h]
0x180055204  mov     [rsp+110h+var_E0], eax
0x180055208  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005520e  xor     r9d, r9d
0x180055211  lea     rdx, [rsp+110h+var_E0]
0x180055216  mov     r8d, 4
0x18005521c  mov     rcx, rdi
0x18005521f  call    cs:__imp_RtlWaitOnAddress
0x180055225  lea     rcx, [rsi+30h]
0x180055229  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18005522f  mov     eax, [rdi]
0x180055231  bt      eax, 0Bh
0x180055235  jb      short loc_180055200
0x180055237  mov     rcx, [rsi+138h]
0x18005523e  btr     eax, 0Ah
0x180055242  mov     r15, [rsi+80h]
0x180055249  bts     eax, 10h
0x18005524d  mov     r12, [rsi+70h]
0x180055251  mov     r14, [rsi+78h]
0x180055255  mov     [rsp+110h+var_D8], rcx
0x18005525a  lea     rcx, [rsi+30h]
0x18005525e  mov     [rsi+138h], r13
0x180055265  mov     [rsi+80h], r13
0x18005526c  mov     [rsi+70h], r13
0x180055270  mov     [rsi+78h], r13
0x180055274  mov     r13, [rsi+50h]
0x180055278  mov     [rdi], eax
0x18005527a  mov     qword ptr [rsi+50h], 0
0x180055282  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180055288  mov     rax, [rsp+110h+var_D8]
0x18005528d  test    rax, rax
0x180055290  jz      short loc_1800552A1
0x180055292  mov     rcx, rax
0x180055295  mov     rax, qword ptr cs:xmmword_1800C41C0+8
0x18005529c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552a1  test    r15, r15
0x1800552a4  jz      short loc_1800552CE
0x1800552a6  xor     r9d, r9d
0x1800552a9  xor     r8d, r8d
0x1800552ac  xor     edx, edx
0x1800552ae  mov     rcx, r15
0x1800552b1  call    cs:__imp_TpSetTimer
0x1800552b7  mov     edx, 1
0x1800552bc  mov     rcx, r15
0x1800552bf  call    cs:__imp_TpWaitForTimer
0x1800552c5  mov     rcx, r15
0x1800552c8  call    cs:__imp_TpReleaseTimer
0x1800552ce  test    r12, r12
0x1800552d1  jz      short loc_1800552E2
0x1800552d3  mov     rax, qword ptr cs:xmmword_1800C41C0+8
0x1800552da  mov     rcx, r12
0x1800552dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552e2  test    r14, r14
0x1800552e5  jz      short loc_18005530F
0x1800552e7  xor     r9d, r9d
0x1800552ea  xor     r8d, r8d
0x1800552ed  xor     edx, edx
0x1800552ef  mov     rcx, r14
0x1800552f2  call    cs:__imp_TpSetTimer
0x1800552f8  mov     edx, 1
0x1800552fd  mov     rcx, r14
0x180055300  call    cs:__imp_TpWaitForTimer
0x180055306  mov     rcx, r14
0x180055309  call    cs:__imp_TpReleaseTimer
0x18005530f  test    r13, r13
0x180055312  jz      short loc_180055323
0x180055314  mov     rax, qword ptr cs:xmmword_1800C4150+8
0x18005531b  mov     rcx, r13
0x18005531e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055323  mov     rcx, rsi
0x180055326  call    BipTaskInstanceReleaseSystemResource
0x18005532b  lea     rcx, [rsi+30h]
0x18005532f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180055335  mov     eax, [rdi]
0x180055337  bt      eax, 0Ch
0x18005533b  jnb     short loc_180055377
0x18005533d  nop     dword ptr [rax]
0x180055340  lea     rcx, [rsi+30h]
0x180055344  mov     [rsp+110h+var_E0], eax
0x180055348  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005534e  xor     r9d, r9d
0x180055351  lea     rdx, [rsp+110h+var_E0]
0x180055356  mov     r8d, 4
0x18005535c  mov     rcx, rdi
0x18005535f  call    cs:__imp_RtlWaitOnAddress
0x180055365  lea     rcx, [rsi+30h]
0x180055369  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18005536f  mov     eax, [rdi]
0x180055371  bt      eax, 0Ch
0x180055375  jb      short loc_180055340
0x180055377  lea     rcx, [rsi+30h]
0x18005537b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180055381  mov     rcx, rsi
0x180055384  call    BipStandbyBudgetCheckRecordTaskInstanceRuntime
0x180055389  mov     rcx, [rbp+57h+var_50]
0x18005538d  xor     rcx, rsp; StackCookie
0x180055390  call    __security_check_cookie
0x180055395  add     rsp, 0D8h
0x18005539c  pop     r15
0x18005539e  pop     r14
0x1800553a0  pop     r13
0x1800553a2  pop     r12
0x1800553a4  pop     rdi
0x1800553a5  pop     rsi
0x1800553a6  pop     rbx
0x1800553a7  pop     rbp
0x1800553a8  retn
```
