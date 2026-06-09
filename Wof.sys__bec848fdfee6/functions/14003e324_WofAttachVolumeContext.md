# WofAttachVolumeContext

- ea: `0x14003e324`
- end: `0x14003e867`
- name: `WofAttachVolumeContext`
- size: `1347`
- prototype: `__int64 __fastcall(__int64, int, PFLT_CONTEXT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x14003bcc0`

## callees

- `0x14000ba78`
- `0x14000dbd8`
- `0x14000dc88`
- `0x14000de64`
- `0x14000e000`
- `0x140011640`
- `0x1400119c0`
- `0x14003e324`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14003e639`
- `ntoskrnl!KeInitializeEvent` at `0x14003e639`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e49d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e4c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e4e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e73a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e835`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e49d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e4c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e4e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e73a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e835`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003e3e1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003e67c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003e6eb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003e3e1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003e67c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003e6eb`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003e6d2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003e6d2`
- `FLTMGR!FltDeleteInstanceContext` at `0x14003e516`
- `FLTMGR!FltDeleteInstanceContext` at `0x14003e516`
- `FLTMGR!FltSetInstanceContext` at `0x14003e7c6`
- `FLTMGR!FltSetInstanceContext` at `0x14003e7c6`
- `FLTMGR!FltReleaseContext` at `0x14003e504`
- `FLTMGR!FltReleaseContext` at `0x14003e84a`
- `FLTMGR!FltReleaseContext` at `0x14003e504`
- `FLTMGR!FltReleaseContext` at `0x14003e84a`
- `FLTMGR!FltGetVolumeGuidName` at `0x14003e720`
- `FLTMGR!FltGetVolumeGuidName` at `0x14003e720`
- `FLTMGR!FltGetVolumeProperties` at `0x14003e367`
- `FLTMGR!FltGetVolumeProperties` at `0x14003e42c`
- `FLTMGR!FltGetVolumeProperties` at `0x14003e367`
- `FLTMGR!FltGetVolumeProperties` at `0x14003e42c`
- `FLTMGR!FltAllocateContext` at `0x14003e583`
- `FLTMGR!FltAllocateContext` at `0x14003e583`

## pseudocode

```c
__int64 __fastcall WofAttachVolumeContext(__int64 a1, int a2, PFLT_CONTEXT *a3)
{
  NTSTATUS VolumeProperties; // eax
  int v7; // edx
  NTSTATUS v8; // ebx
  int v9; // r9d
  struct _FLT_VOLUME_PROPERTIES *PoolWithTag; // rax
  struct _FLT_VOLUME_PROPERTIES *v11; // r14
  int v12; // edx
  _QWORD *v13; // rax
  void *v14; // rcx
  _QWORD *v15; // rax
  void *v16; // rcx
  NTSTATUS v17; // eax
  int v18; // edx
  int v19; // r8d
  NTSTATUS v21; // eax
  int v22; // edx
  int v23; // r9d
  _OWORD *v24; // rax
  _QWORD *v25; // rax
  struct _KEVENT *v26; // rcx
  PVOID v27; // rax
  USHORT Length; // cx
  _WORD *v29; // rdx
  void *v30; // rcx
  PVOID v31; // rax
  _WORD *v32; // rcx
  unsigned int i; // r15d
  __int64 v34; // rax
  int v35; // r8d
  int v36; // r9d
  int ReturnedContext; // [rsp+20h] [rbp-40h]
  __int64 v38; // [rsp+28h] [rbp-38h]
  PFLT_CONTEXT Context; // [rsp+50h] [rbp-10h] BYREF
  ULONG LengthReturned; // [rsp+A0h] [rbp+40h] BYREF
  ULONG v41; // [rsp+B8h] [rbp+58h] BYREF

  v41 = 0;
  LengthReturned = 0;
  Context = 0;
  VolumeProperties = FltGetVolumeProperties(*(PFLT_VOLUME *)(a1 + 16), 0, 0, &LengthReturned);
  v8 = VolumeProperties;
  if ( VolumeProperties != -2147483643 && VolumeProperties != -1073741789 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_15:
      v13 = Context;
      if ( Context )
      {
        v14 = (void *)*((_QWORD *)Context + 9);
        if ( v14 )
        {
          ExFreePoolWithTag(v14, 0);
          v13 = Context;
        }
        v13[9] = 0;
        v15 = Context;
        v16 = (void *)*((_QWORD *)Context + 11);
        if ( v16 )
        {
          ExFreePoolWithTag(v16, 0);
          v15 = Context;
        }
        v15[11] = 0;
        FltReleaseContext(Context);
        v17 = FltDeleteInstanceContext(*(PFLT_INSTANCE *)(a1 + 24), 0);
        if ( v17 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_D(WPP_GLOBAL_Control->DeviceExtension, v18, v19, 16, ReturnedContext, v17);
      }
      return (unsigned int)v8;
    }
    v9 = 11;
    v38 = *(_QWORD *)(a1 + 16);
LABEL_5:
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      4,
      v9,
      (__int64)WPP_4bc7650b61d83c5431af80a6c7908977_Traceguids,
      v38);
    goto LABEL_15;
  }
  PoolWithTag = (struct _FLT_VOLUME_PROPERTIES *)ExAllocatePoolWithTag((POOL_TYPE)512, LengthReturned, 0x56666F57u);
  v11 = PoolWithTag;
  if ( !PoolWithTag )
  {
    v8 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_15;
    v9 = 10;
    v38 = *(_QWORD *)(a1 + 16);
    goto LABEL_5;
  }
  v8 = FltGetVolumeProperties(*(PFLT_VOLUME *)(a1 + 16), PoolWithTag, LengthReturned, &v41);
  if ( v8 < 0 )
    goto LABEL_14;
  if ( v11->DeviceType == 20 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 4;
      WPP_RECORDER_SF_qZ(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        4,
        12,
        (__int64)WPP_4bc7650b61d83c5431af80a6c7908977_Traceguids,
        *(_QWORD *)(a1 + 16),
        (__int64)&v11->FileSystemDeviceName);
    }
    v8 = -1073741637;
    goto LABEL_14;
  }
  v21 = FltAllocateContext(WofGlobal, 2u, (unsigned int)Size, (POOL_TYPE)512, &Context);
  v8 = v21;
  if ( v21 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = 13;
LABEL_27:
      LOBYTE(v22) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v22,
        4,
        v23,
        (__int64)WPP_4bc7650b61d83c5431af80a6c7908977_Traceguids,
        v21);
    }
LABEL_14:
    ExFreePoolWithTag(v11, 0);
    goto LABEL_15;
  }
  memset(Context, 0, (unsigned int)Size);
  v24 = Context;
  *((_OWORD *)Context + 6) = *(_OWORD *)a1;
  v24[7] = *(_OWORD *)(a1 + 16);
  v24[8] = *(_OWORD *)(a1 + 32);
  v25 = (char *)Context + 152;
  *((_QWORD *)Context + 20) = (char *)Context + 152;
  *v25 = v25;
  v26 = (struct _KEVENT *)Context;
  *(_DWORD *)Context = 1;
  v26->Header.WaitListHead.Flink = 0;
  LODWORD(v26->Header.WaitListHead.Blink) = 0;
  KeInitializeEvent(v26 + 1, SynchronizationEvent, 0);
  *((_DWORD *)Context + 36) = a2;
  *((_DWORD *)Context + 14) |= 1u;
  _InterlockedAdd(&dword_14001845C, 1u);
  v27 = ExAllocatePoolWithTag((POOL_TYPE)512, v11->RealDeviceName.Length + 2LL, 0x56666F57u);
  Length = v11->RealDeviceName.Length;
  v29 = Context;
  *((_OWORD *)Context + 4) = 0;
  v29[33] = Length;
  *((_QWORD *)v29 + 9) = v27;
  v30 = (void *)*((_QWORD *)Context + 9);
  if ( !v30
    || (memset(v30, 0, v11->RealDeviceName.Length + 2LL),
        RtlCopyUnicodeString((PUNICODE_STRING)Context + 4, &v11->RealDeviceName),
        v31 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x62u, 0x56666F57u),
        v32 = Context,
        *((_OWORD *)Context + 5) = 0,
        v32[41] = 98,
        *((_QWORD *)v32 + 11) = v31,
        !*((_QWORD *)Context + 11)) )
  {
    v8 = -1073741670;
    goto LABEL_14;
  }
  if ( FltGetVolumeGuidName(*(PFLT_VOLUME *)(a1 + 16), (PUNICODE_STRING)Context + 5, 0) >= 0 )
  {
    *((_DWORD *)Context + 14) |= 2u;
  }
  else
  {
    ExFreePoolWithTag(*((PVOID *)Context + 11), 0);
    *((_OWORD *)Context + 5) = 0;
    *((_DWORD *)Context + 14) &= ~2u;
  }
  for ( i = 0; i < 4; ++i )
  {
    v34 = 424LL * i;
    if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v34) )
    {
      v8 = (*(__int64 (__fastcall **)(char *))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v34 + 160))((char *)Context + *(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v34 + 20));
      if ( v8 < 0 )
        goto LABEL_14;
      *((_DWORD *)Context + 42) = i;
    }
  }
  v21 = FltSetInstanceContext(*(PFLT_INSTANCE *)(a1 + 24), FLT_SET_CONTEXT_REPLACE_IF_EXISTS, Context, 0);
  v8 = v21;
  if ( v21 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_14;
    v23 = 14;
    goto LABEL_27;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qqqZ(
      WPP_GLOBAL_Control->DeviceExtension,
      v22,
      v35,
      v36,
      ReturnedContext,
      (char)Context,
      *(_QWORD *)(a1 + 24),
      *(_QWORD *)(a1 + 16),
      (__int64)&v11->RealDeviceName);
  ExFreePoolWithTag(v11, 0);
  if ( a3 )
    *a3 = Context;
  else
    FltReleaseContext(Context);
  return 0;
}

```

## disassembly

```asm
0x14003e324  mov     [rsp-38h+arg_8], rbx
0x14003e329  push    rbp
0x14003e32a  push    rsi
0x14003e32b  push    rdi
0x14003e32c  push    r12
0x14003e32e  push    r13
0x14003e330  push    r14
0x14003e332  push    r15
0x14003e334  mov     rbp, rsp
0x14003e337  sub     rsp, 60h
0x14003e33b  mov     r12, r8
0x14003e33e  mov     [rbp+arg_18], 0
0x14003e345  mov     r15d, edx
0x14003e348  mov     [rbp+LengthReturned], 0
0x14003e34f  mov     rsi, rcx
0x14003e352  mov     [rbp+Context], 0
0x14003e35a  mov     rcx, [rcx+10h]; Volume
0x14003e35e  lea     r9, [rbp+LengthReturned]; LengthReturned
0x14003e362  xor     r8d, r8d; VolumePropertiesLength
0x14003e365  xor     edx, edx; VolumeProperties
0x14003e367  call    cs:__imp_FltGetVolumeProperties
0x14003e36e  nop     dword ptr [rax+rax+00h]
0x14003e373  mov     ebx, eax
0x14003e375  cmp     eax, 80000005h
0x14003e37a  jz      short loc_14003E3CF
0x14003e37c  cmp     eax, 0C0000023h
0x14003e381  jz      short loc_14003E3CF
0x14003e383  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003e38a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003e391  jz      loc_14003E4A9
0x14003e397  mov     rcx, [rsi+10h]
0x14003e39b  mov     r9d, 0Bh
0x14003e3a1  mov     [rsp+60h+var_38], rcx
0x14003e3a6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e3ad  lea     rax, WPP_4bc7650b61d83c5431af80a6c7908977_Traceguids
0x14003e3b4  mov     r8d, 4
0x14003e3ba  mov     [rsp+60h+ReturnedContext], rax
0x14003e3bf  mov     dl, 2
0x14003e3c1  mov     rcx, [rcx+40h]
0x14003e3c5  call    WPP_RECORDER_SF_q
0x14003e3ca  jmp     loc_14003E4A9
0x14003e3cf  mov     edx, [rbp+LengthReturned]; NumberOfBytes
0x14003e3d2  mov     r13d, 200h
0x14003e3d8  mov     ecx, r13d; PoolType
0x14003e3db  mov     r8d, 56666F57h; Tag
0x14003e3e1  call    cs:__imp_ExAllocatePoolWithTag
0x14003e3e8  nop     dword ptr [rax+rax+00h]
0x14003e3ed  mov     r14, rax
0x14003e3f0  test    rax, rax
0x14003e3f3  jnz     short loc_14003E41D
0x14003e3f5  mov     ebx, 0C000009Ah
0x14003e3fa  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003e401  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003e408  jz      loc_14003E4A9
0x14003e40e  lea     r9d, [rax+0Ah]
0x14003e412  mov     rax, [rsi+10h]
0x14003e416  mov     [rsp+60h+var_38], rax
0x14003e41b  jmp     short loc_14003E3A6
0x14003e41d  mov     r8d, [rbp+LengthReturned]; VolumePropertiesLength
0x14003e421  lea     r9, [rbp+arg_18]; LengthReturned
0x14003e425  mov     rcx, [rsi+10h]; Volume
0x14003e429  mov     rdx, r14; VolumeProperties
0x14003e42c  call    cs:__imp_FltGetVolumeProperties
0x14003e433  nop     dword ptr [rax+rax+00h]
0x14003e438  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003e43f  mov     ebx, eax
0x14003e441  test    eax, eax
0x14003e443  js      short loc_14003E498
0x14003e445  cmp     dword ptr [r14], 14h
0x14003e449  jnz     loc_14003E564
0x14003e44f  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003e456  jz      short loc_14003E493
0x14003e458  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e45f  lea     rax, [r14+28h]
0x14003e463  mov     [rsp+60h+var_30], rax
0x14003e468  mov     r9d, 0Ch
0x14003e46e  mov     rax, [rsi+10h]
0x14003e472  mov     [rsp+60h+var_38], rax
0x14003e477  lea     rax, WPP_4bc7650b61d83c5431af80a6c7908977_Traceguids
0x14003e47e  mov     rcx, [rcx+40h]
0x14003e482  lea     r8d, [r9-8]
0x14003e486  mov     [rsp+60h+ReturnedContext], rax
0x14003e48b  mov     dl, r8b
0x14003e48e  call    WPP_RECORDER_SF_qZ
0x14003e493  mov     ebx, 0C00000BBh
0x14003e498  xor     edx, edx; Tag
0x14003e49a  mov     rcx, r14; P
0x14003e49d  call    cs:__imp_ExFreePoolWithTag
0x14003e4a4  nop     dword ptr [rax+rax+00h]
0x14003e4a9  mov     rax, [rbp+Context]
0x14003e4ad  test    rax, rax
0x14003e4b0  jz      loc_14003E549
0x14003e4b6  mov     rcx, [rax+48h]; P
0x14003e4ba  test    rcx, rcx
0x14003e4bd  jz      short loc_14003E4D1
0x14003e4bf  xor     edx, edx; Tag
0x14003e4c1  call    cs:__imp_ExFreePoolWithTag
0x14003e4c8  nop     dword ptr [rax+rax+00h]
0x14003e4cd  mov     rax, [rbp+Context]
0x14003e4d1  mov     qword ptr [rax+48h], 0
0x14003e4d9  mov     rax, [rbp+Context]
0x14003e4dd  mov     rcx, [rax+58h]; P
0x14003e4e1  test    rcx, rcx
0x14003e4e4  jz      short loc_14003E4F8
0x14003e4e6  xor     edx, edx; Tag
0x14003e4e8  call    cs:__imp_ExFreePoolWithTag
0x14003e4ef  nop     dword ptr [rax+rax+00h]
0x14003e4f4  mov     rax, [rbp+Context]
0x14003e4f8  mov     qword ptr [rax+58h], 0
0x14003e500  mov     rcx, [rbp+Context]; Context
0x14003e504  call    cs:__imp_FltReleaseContext
0x14003e50b  nop     dword ptr [rax+rax+00h]
0x14003e510  mov     rcx, [rsi+18h]; Instance
0x14003e514  xor     edx, edx; OldContext
0x14003e516  call    cs:__imp_FltDeleteInstanceContext
0x14003e51d  nop     dword ptr [rax+rax+00h]
0x14003e522  test    eax, eax
0x14003e524  jns     short loc_14003E549
0x14003e526  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003e52d  jz      short loc_14003E549
0x14003e52f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e536  mov     r9d, 10h
0x14003e53c  mov     dword ptr [rsp+60h+var_38], eax
0x14003e540  mov     rcx, [rcx+40h]
0x14003e544  call    WPP_RECORDER_SF_D
0x14003e549  mov     eax, ebx
0x14003e54b  mov     rbx, [rsp+60h+arg_8]
0x14003e553  add     rsp, 60h
0x14003e557  pop     r15
0x14003e559  pop     r14
0x14003e55b  pop     r13
0x14003e55d  pop     r12
0x14003e55f  pop     rdi
0x14003e560  pop     rsi
0x14003e561  pop     rbp
0x14003e562  retn
0x14003e564  mov     r8d, cs:Size; ContextSize
0x14003e56b  lea     rax, [rbp+Context]
0x14003e56f  mov     rcx, cs:WofGlobal; Filter
0x14003e576  mov     edx, 2; ContextType
0x14003e57b  mov     r9d, r13d; PoolType
0x14003e57e  mov     [rsp+60h+ReturnedContext], rax; ReturnedContext
0x14003e583  call    cs:__imp_FltAllocateContext
0x14003e58a  nop     dword ptr [rax+rax+00h]
0x14003e58f  mov     ebx, eax
0x14003e591  test    eax, eax
0x14003e593  jns     short loc_14003E5D5
0x14003e595  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003e59c  jz      loc_14003E498
0x14003e5a2  mov     r9d, 0Dh
0x14003e5a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e5af  mov     r8d, 4
0x14003e5b5  mov     dword ptr [rsp+60h+var_38], eax
0x14003e5b9  mov     dl, 2
0x14003e5bb  lea     rax, WPP_4bc7650b61d83c5431af80a6c7908977_Traceguids
0x14003e5c2  mov     [rsp+60h+ReturnedContext], rax
0x14003e5c7  mov     rcx, [rcx+40h]
0x14003e5cb  call    WPP_RECORDER_SF_d
0x14003e5d0  jmp     loc_14003E498
0x14003e5d5  mov     r8d, cs:Size; Size
0x14003e5dc  xor     edx, edx; Val
0x14003e5de  mov     rcx, [rbp+Context]; void *
0x14003e5e2  call    memset
0x14003e5e7  mov     rax, [rbp+Context]
0x14003e5eb  mov     ebx, 1
0x14003e5f0  movups  xmm0, xmmword ptr [rsi]
0x14003e5f3  xor     r8d, r8d; State
0x14003e5f6  mov     edx, ebx; Type
0x14003e5f8  movups  xmmword ptr [rax+60h], xmm0
0x14003e5fc  movups  xmm1, xmmword ptr [rsi+10h]
0x14003e600  movups  xmmword ptr [rax+70h], xmm1
0x14003e604  movups  xmm0, xmmword ptr [rsi+20h]
0x14003e608  movups  xmmword ptr [rax+80h], xmm0
0x14003e60f  mov     rax, [rbp+Context]
0x14003e613  add     rax, 98h
0x14003e619  mov     [rax+8], rax
0x14003e61d  mov     [rax], rax
0x14003e620  mov     rcx, [rbp+Context]
0x14003e624  mov     [rcx], ebx
0x14003e626  mov     qword ptr [rcx+8], 0
0x14003e62e  mov     dword ptr [rcx+10h], 0
0x14003e635  add     rcx, 18h; Event
0x14003e639  call    cs:__imp_KeInitializeEvent
0x14003e640  nop     dword ptr [rax+rax+00h]
0x14003e645  mov     rax, [rbp+Context]
0x14003e649  mov     [rax+90h], r15d
0x14003e650  mov     rax, [rbp+Context]
0x14003e654  or      [rax+38h], ebx
0x14003e657  lock add cs:dword_14001845C, ebx
0x14003e65e  lea     r13, [r14+38h]
0x14003e662  mov     ebx, 56666F57h
0x14003e667  movzx   edx, word ptr [r13+0]
0x14003e66c  mov     r15d, 200h
0x14003e672  add     rdx, 2; NumberOfBytes
0x14003e676  mov     r8d, ebx; Tag
0x14003e679  mov     ecx, r15d; PoolType
0x14003e67c  call    cs:__imp_ExAllocatePoolWithTag
0x14003e683  nop     dword ptr [rax+rax+00h]
0x14003e688  movzx   ecx, word ptr [r13+0]
0x14003e68d  xorps   xmm0, xmm0
0x14003e690  mov     rdx, [rbp+Context]
0x14003e694  movups  xmmword ptr [rdx+40h], xmm0
0x14003e698  mov     [rdx+42h], cx
0x14003e69c  mov     [rdx+48h], rax
0x14003e6a0  mov     rax, [rbp+Context]
0x14003e6a4  mov     rcx, [rax+48h]; void *
0x14003e6a8  test    rcx, rcx
0x14003e6ab  jnz     short loc_14003E6B7
0x14003e6ad  mov     ebx, 0C000009Ah
0x14003e6b2  jmp     loc_14003E498
0x14003e6b7  movzx   r8d, word ptr [r13+0]
0x14003e6bc  xor     edx, edx; Val
0x14003e6be  add     r8, 2; Size
0x14003e6c2  call    memset
0x14003e6c7  mov     rcx, [rbp+Context]
0x14003e6cb  mov     rdx, r13; SourceString
0x14003e6ce  add     rcx, 40h ; '@'; DestinationString
0x14003e6d2  call    cs:__imp_RtlCopyUnicodeString
0x14003e6d9  nop     dword ptr [rax+rax+00h]
0x14003e6de  mov     r8d, ebx; Tag
0x14003e6e1  mov     ecx, r15d; PoolType
0x14003e6e4  mov     ebx, 62h ; 'b'
0x14003e6e9  mov     edx, ebx; NumberOfBytes
0x14003e6eb  call    cs:__imp_ExAllocatePoolWithTag
0x14003e6f2  nop     dword ptr [rax+rax+00h]
0x14003e6f7  mov     rcx, [rbp+Context]
0x14003e6fb  xorps   xmm0, xmm0
0x14003e6fe  movups  xmmword ptr [rcx+50h], xmm0
0x14003e702  mov     [rcx+52h], bx
0x14003e706  mov     [rcx+58h], rax
0x14003e70a  mov     rdx, [rbp+Context]
0x14003e70e  cmp     qword ptr [rdx+58h], 0
0x14003e713  jz      short loc_14003E6AD
0x14003e715  mov     rcx, [rsi+10h]; Volume
0x14003e719  add     rdx, 50h ; 'P'; VolumeGuidName
0x14003e71d  xor     r8d, r8d; BufferSizeNeeded
0x14003e720  call    cs:__imp_FltGetVolumeGuidName
0x14003e727  nop     dword ptr [rax+rax+00h]
0x14003e72c  test    eax, eax
0x14003e72e  jns     short loc_14003E75B
0x14003e730  mov     rcx, [rbp+Context]
0x14003e734  xor     edx, edx; Tag
0x14003e736  mov     rcx, [rcx+58h]; P
0x14003e73a  call    cs:__imp_ExFreePoolWithTag
0x14003e741  nop     dword ptr [rax+rax+00h]
0x14003e746  mov     rax, [rbp+Context]
0x14003e74a  xorps   xmm0, xmm0
0x14003e74d  movups  xmmword ptr [rax+50h], xmm0
0x14003e751  mov     rax, [rbp+Context]
0x14003e755  and     dword ptr [rax+38h], 0FFFFFFFDh
0x14003e759  jmp     short loc_14003E763
0x14003e75b  mov     rax, [rbp+Context]
0x14003e75f  or      dword ptr [rax+38h], 2
0x14003e763  xor     r15d, r15d
0x14003e766  lea     rdx, WPP_MAIN_CB.Queue+10h
0x14003e76d  cmp     r15d, 4
0x14003e771  jnb     short loc_14003E7B9
0x14003e773  mov     eax, r15d
0x14003e776  imul    rax, 1A8h
0x14003e77d  cmp     byte ptr [rax+rdx], 0
0x14003e781  jz      short loc_14003E7B4
0x14003e783  mov     ecx, [rax+rdx+14h]
0x14003e787  add     rcx, [rbp+Context]
0x14003e78b  mov     rax, [rax+rdx+0A0h]
0x14003e793  call    _guard_dispatch_icall
0x14003e798  mov     ebx, eax
0x14003e79a  test    eax, eax
0x14003e79c  js      loc_14003E498
0x14003e7a2  mov     rax, [rbp+Context]
0x14003e7a6  lea     rdx, WPP_MAIN_CB.Queue+10h
0x14003e7ad  mov     [rax+0A8h], r15d
0x14003e7b4  inc     r15d
0x14003e7b7  jmp     short loc_14003E76D
0x14003e7b9  mov     r8, [rbp+Context]; NewContext
0x14003e7bd  xor     r9d, r9d; OldContext
0x14003e7c0  mov     rcx, [rsi+18h]; Instance
0x14003e7c4  xor     edx, edx; Operation
0x14003e7c6  call    cs:__imp_FltSetInstanceContext
0x14003e7cd  nop     dword ptr [rax+rax+00h]
0x14003e7d2  mov     ebx, eax
0x14003e7d4  test    eax, eax
0x14003e7d6  jns     short loc_14003E7F0
0x14003e7d8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003e7df  jz      loc_14003E498
0x14003e7e5  mov     r9d, 0Eh
0x14003e7eb  jmp     loc_14003E5A8
0x14003e7f0  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003e7f7  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003e7fe  jz      short loc_14003E830
0x14003e800  mov     rax, [rsi+10h]
0x14003e804  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e80b  mov     [rsp+60h+var_20], r13
0x14003e810  mov     [rsp+60h+var_28], rax
0x14003e815  mov     rax, [rsi+18h]
0x14003e819  mov     rcx, [rcx+40h]
0x14003e81d  mov     [rsp+60h+var_30], rax
0x14003e822  mov     rax, [rbp+Context]
0x14003e826  mov     [rsp+60h+var_38], rax
0x14003e82b  call    WPP_RECORDER_SF_qqqZ
0x14003e830  xor     edx, edx; Tag
  ... truncated ...
```
