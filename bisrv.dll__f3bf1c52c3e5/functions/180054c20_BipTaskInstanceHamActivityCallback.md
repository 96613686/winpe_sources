# BipTaskInstanceHamActivityCallback

- ea: `0x180054c20`
- end: `0x180055086`
- name: `BipTaskInstanceHamActivityCallback`
- size: `1126`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callees

- `0x180006210`
- `0x18000d7c0`
- `0x18000da50`
- `0x1800101a4`
- `0x18001079c`
- `0x18001d448`
- `0x180054c20`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180054db7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180054e6e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180054ea4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180054db7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180054e6e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180054ea4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180054dcb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180054e57`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180054e88`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180054eb8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180054f1f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180054dcb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180054e57`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180054e88`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180054eb8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180054f1f`
- `ntdll!RtlWakeAddressAll` at `0x180054dd8`
- `ntdll!RtlWakeAddressAll` at `0x180054dd8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180054d8d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180055058`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180054d8d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180055058`

## pseudocode

```c
int __fastcall BipTaskInstanceHamActivityCallback(__int64 *a1)
{
  __int128 *v1; // rsi
  __int64 v2; // rdi
  EVENT_DESCRIPTOR v3; // xmm1
  EVENT_DESCRIPTOR *v5; // r15
  unsigned __int8 v6; // r14
  const struct _TraceLoggingMetadata_t *v7; // rdx
  EVENT_DESCRIPTOR v8; // xmm0
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // edi
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // r8
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v16; // rcx
  _QWORD *ThreadLocalStoragePointer; // rax
  int v18; // edi
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rcx
  _QWORD *v22; // rax
  int v23; // edi
  __int64 v24; // rbx
  __int64 v25; // rax
  unsigned int v27; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+38h] [rbp-C8h]
  __int64 v29; // [rsp+40h] [rbp-C0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  EVENT_DESCRIPTOR v31; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v32; // [rsp+70h] [rbp-90h] BYREF
  EVENT_DESCRIPTOR v33; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-70h] BYREF
  __int16 *v35; // [rsp+A0h] [rbp-60h]
  int v36; // [rsp+A8h] [rbp-58h]
  int v37; // [rsp+ACh] [rbp-54h]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+B0h] [rbp-50h]
  __int64 v39; // [rsp+B8h] [rbp-48h]
  EVENT_DESCRIPTOR *v40; // [rsp+C0h] [rbp-40h]
  __int64 v41; // [rsp+C8h] [rbp-38h]
  __int128 *v42; // [rsp+D0h] [rbp-30h]
  __int64 v43; // [rsp+D8h] [rbp-28h]
  __int64 *v44; // [rsp+E0h] [rbp-20h]
  __int64 v45; // [rsp+E8h] [rbp-18h]
  unsigned int *v46; // [rsp+F0h] [rbp-10h]
  __int64 v47; // [rsp+F8h] [rbp-8h]

  v1 = (__int128 *)a1[1];
  v2 = *a1;
  v3 = 0;
  v32 = 0;
  v28 = v2;
  v33 = 0;
  v5 = (EVENT_DESCRIPTOR *)*((_QWORD *)v1 + 8);
  v32 = *v1;
  if ( v5 )
    v3 = v5[2];
  v6 = 0;
  v33 = v3;
  v7 = &TraceLoggingMetadata;
  if ( (unsigned int)dword_1800C3098 > 5 && (qword_1800C30A8 & 2) != 0 && (qword_1800C30B0 & 2) == qword_1800C30B0 )
  {
    v8 = 0;
    if ( v5 )
      v8 = v5[2];
    v31 = v8;
    v40 = &v31;
    v29 = v2;
    p_EventDescriptor = (EVENT_DESCRIPTOR *)&v29;
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    v42 = v1;
    v43 = 16;
    v41 = 16;
    v39 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 2;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v35 = (__int16 *)byte_1800AE815;
    UserData.Reserved = 2;
    v36 = 68;
    v37 = 1;
    v27 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
  }
  v9 = *((_DWORD *)a1 + 4);
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        if ( v11 == 1 )
        {
          RtlAcquireSRWLockExclusive(v1 + 3);
          *((_DWORD *)v1 + 34) &= ~0x1000u;
          RtlReleaseSRWLockExclusive(v1 + 3);
          RtlWakeAddressAll((char *)v1 + 136);
        }
        goto LABEL_26;
      }
      v6 = 1;
      v12 = 43525;
    }
    else
    {
      if ( (unsigned int)(*((_DWORD *)a1 + 6) - 1) <= 1 )
      {
        v13 = BiSrvConvertHamStopRequestToBiCancelReason(a1, v7);
        BipAcquireGlobalLock(v14);
        LOBYTE(v15) = 1;
        BipWorkItemTaskInstanceCancel(v1, v13, v15);
        BipLockWatchdogContextDisarmWatchdog(v16);
        ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
        v18 = ~(1 << dword_1800C3CB0);
        dword_1800C3CB4 = 0;
        v19 = ThreadLocalStoragePointer[(unsigned int)tls_index];
        *(_DWORD *)(v19 + 8) &= v18;
        RtlReleaseSRWLockExclusive(&BipGlobalLock);
        *(_DWORD *)(v19 + 4) &= v18;
      }
      else
      {
        v6 = 1;
      }
      v12 = 43524;
    }
    RtlAcquireSRWLockExclusive(v1 + 3);
    *((_DWORD *)v1 + 34) |= 0x4000u;
    *((_DWORD *)v1 + 71) = v12;
    RtlReleaseSRWLockExclusive(v1 + 3);
    if ( v6 )
      BipWorkItemTpWorkerQueueTaskInstanceReleaseSystemResource(v5, v1);
  }
  else
  {
    RtlAcquireSRWLockExclusive(v1 + 3);
    *((_DWORD *)v1 + 34) |= 0x2000u;
    RtlReleaseSRWLockExclusive(v1 + 3);
  }
  BipAcquireGlobalLock(v20);
  v21 = *((_QWORD *)v1 + 8);
  if ( *(int *)(v21 + 24) >= 0 && *(_QWORD *)(v21 + 144) != v21 + 144 )
    BipWorkItemTpWorkerQueueHamActivityWorker(v21, v1);
  BipLockWatchdogContextDisarmWatchdog((struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)v21);
  v22 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v23 = ~(1 << dword_1800C3CB0);
  dword_1800C3CB4 = 0;
  v24 = v22[(unsigned int)tls_index];
  *(_DWORD *)(v24 + 8) &= v23;
  RtlReleaseSRWLockExclusive(&BipGlobalLock);
  *(_DWORD *)(v24 + 4) &= v23;
  v2 = v28;
LABEL_26:
  LODWORD(v25) = dword_1800C3098;
  if ( (unsigned int)dword_1800C3098 > 5 )
  {
    LODWORD(v25) = qword_1800C30A8;
    if ( (qword_1800C30A8 & 2) != 0 )
    {
      v25 = qword_1800C30B0 & 2;
      if ( v25 == qword_1800C30B0 )
      {
        v27 = v6;
        LODWORD(v29) = *((_DWORD *)a1 + 4);
        v46 = &v27;
        v44 = &v29;
        v42 = &v32;
        v40 = &v33;
        p_EventDescriptor = &EventDescriptor;
        *(_DWORD *)&v31.Level = 517;
        UserData.Ptr = (ULONGLONG)off_1800C30A0;
        *(_QWORD *)&EventDescriptor.Id = v2;
        v47 = 4;
        v45 = 4;
        v43 = 16;
        v41 = 16;
        v39 = 8;
        *(_DWORD *)&v31.Id = 184549376;
        v31.Keyword = 2;
        UserData.Size = *(unsigned __int16 *)off_1800C30A0;
        v35 = &word_1800AE8A6;
        UserData.Reserved = 2;
        v36 = 99;
        v37 = 1;
        LODWORD(v28) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        LODWORD(v25) = EventWriteTransfer(RegHandle, &v31, 0, 0, 7u, &UserData);
      }
    }
  }
  return v25;
}

```

## disassembly

```asm
0x180054c20  mov     [rsp-8+arg_8], rbx
0x180054c25  mov     [rsp-8+arg_10], rsi
0x180054c2a  push    rbp
0x180054c2b  push    rdi
0x180054c2c  push    r12
0x180054c2e  push    r14
0x180054c30  push    r15
0x180054c32  lea     rbp, [rsp-10h]
0x180054c37  sub     rsp, 110h
0x180054c3e  mov     rax, cs:__security_cookie
0x180054c45  xor     rax, rsp
0x180054c48  mov     [rbp+30h+var_30], rax
0x180054c4c  mov     rsi, [rcx+8]
0x180054c50  xorps   xmm0, xmm0
0x180054c53  mov     rdi, [rcx]
0x180054c56  xorps   xmm1, xmm1
0x180054c59  movups  [rsp+130h+var_C0], xmm0
0x180054c5e  mov     r12, rcx
0x180054c61  mov     [rsp+130h+var_F8], rdi
0x180054c66  movups  [rbp+30h+var_B0], xmm1
0x180054c6a  mov     r15, [rsi+40h]
0x180054c6e  movups  xmm0, xmmword ptr [rsi]
0x180054c71  movups  [rsp+130h+var_C0], xmm0
0x180054c76  test    r15, r15
0x180054c79  jz      short loc_180054C80
0x180054c7b  movups  xmm1, xmmword ptr [r15+20h]
0x180054c80  mov     eax, cs:dword_1800C3098
0x180054c86  lea     rbx, _TraceLoggingMetadataEnd
0x180054c8d  xor     r14d, r14d
0x180054c90  movdqa  [rbp+30h+var_B0], xmm1
0x180054c95  lea     rdx, _TraceLoggingMetadata
0x180054c9c  cmp     eax, 5
0x180054c9f  jbe     loc_180054D93
0x180054ca5  mov     rcx, cs:qword_1800C30B0
0x180054cac  mov     rax, cs:qword_1800C30A8
0x180054cb3  test    al, 2
0x180054cb5  jz      loc_180054D93
0x180054cbb  mov     rax, rcx
0x180054cbe  and     eax, 2
0x180054cc1  cmp     rax, rcx
0x180054cc4  jnz     loc_180054D93
0x180054cca  xorps   xmm0, xmm0
0x180054ccd  test    r15, r15
0x180054cd0  jz      short loc_180054CD7
0x180054cd2  movups  xmm0, xmmword ptr [r15+20h]
0x180054cd7  movdqa  xmmword ptr [rsp+130h+var_D0.Id], xmm0
0x180054cdd  lea     rax, [rsp+130h+var_D0]
0x180054ce2  mov     [rbp+30h+var_70], rax
0x180054ce6  xor     r9d, r9d; RelatedActivityId
0x180054ce9  lea     rax, [rsp+130h+var_F0]
0x180054cee  mov     [rsp+130h+var_F0], rdi
0x180054cf3  mov     [rbp+30h+var_80], rax
0x180054cf7  xor     r8d, r8d; ActivityId
0x180054cfa  movzx   eax, cs:word_1800AE80B
0x180054d01  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x180054d05  mov     rax, cs:off_1800C30A0
0x180054d0c  mov     [rbp+30h+var_A0.Ptr], rax
0x180054d10  mov     [rbp+30h+var_60], rsi
0x180054d14  mov     [rbp+30h+var_58], 10h
0x180054d1c  mov     [rbp+30h+var_68], 10h
0x180054d24  mov     [rbp+30h+var_78], 8
0x180054d2c  mov     dword ptr [rsp+130h+EventDescriptor.Id], 0B000000h
0x180054d34  mov     [rsp+130h+EventDescriptor.Keyword], 2
0x180054d3d  movzx   eax, word ptr [rax]
0x180054d40  mov     [rbp+30h+var_A0.Size], eax
0x180054d43  lea     rax, byte_1800AE815
0x180054d4a  mov     [rbp+30h+var_90], rax
0x180054d4e  mov     rax, rbx
0x180054d51  sub     eax, edx
0x180054d53  mov     dword ptr [rbp+30h+var_A0.0Ch], 2
0x180054d5a  mov     [rbp+30h+var_88], 44h ; 'D'
0x180054d61  lea     rdx, [rsp+130h+EventDescriptor]; EventDescriptor
0x180054d66  mov     [rbp+30h+var_84], 1
0x180054d6d  mov     [rsp+130h+var_100], eax
0x180054d71  mov     eax, [rsp+130h+var_100]
0x180054d75  mov     rcx, cs:RegHandle; RegHandle
0x180054d7c  lea     rax, [rbp+30h+var_A0]
0x180054d80  mov     [rsp+130h+UserData], rax; UserData
0x180054d85  mov     [rsp+130h+UserDataCount], 5; UserDataCount
0x180054d8d  call    cs:__imp_EventWriteTransfer
0x180054d93  mov     ecx, [r12+10h]
0x180054d98  test    ecx, ecx
0x180054d9a  jz      loc_180054EA0
0x180054da0  sub     ecx, 1
0x180054da3  jz      short loc_180054DED
0x180054da5  sub     ecx, 1
0x180054da8  jz      short loc_180054DE3
0x180054daa  cmp     ecx, 1
0x180054dad  jnz     loc_180054F39
0x180054db3  lea     rcx, [rsi+30h]
0x180054db7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180054dbd  and     dword ptr [rsi+88h], 0FFFFEFFFh
0x180054dc7  lea     rcx, [rsi+30h]
0x180054dcb  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180054dd1  lea     rcx, [rsi+88h]
0x180054dd8  call    cs:__imp_RtlWakeAddressAll
0x180054dde  jmp     loc_180054F32
0x180054de3  mov     r14b, 1
0x180054de6  mov     edi, 0AA05h
0x180054deb  jmp     short loc_180054E6A
0x180054ded  mov     eax, [r12+18h]
0x180054df2  dec     eax
0x180054df4  cmp     eax, 1
0x180054df7  jbe     short loc_180054DFE
0x180054df9  mov     r14b, 1
0x180054dfc  jmp     short loc_180054E65
0x180054dfe  mov     rcx, r12
0x180054e01  call    BiSrvConvertHamStopRequestToBiCancelReason
0x180054e06  mov     ebx, eax
0x180054e08  call    BipAcquireGlobalLock
0x180054e0d  mov     r8b, 1
0x180054e10  mov     edx, ebx
0x180054e12  mov     rcx, rsi
0x180054e15  call    BipWorkItemTaskInstanceCancel
0x180054e1a  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x180054e1f  mov     ecx, cs:dword_1800C3CB0
0x180054e25  mov     edi, 1
0x180054e2a  mov     rax, gs:58h
0x180054e33  shl     edi, cl
0x180054e35  mov     ecx, cs:_tls_index
0x180054e3b  not     edi
0x180054e3d  mov     cs:dword_1800C3CB4, r14d
0x180054e44  mov     rbx, [rax+rcx*8]
0x180054e48  lea     rcx, BipGlobalLock
0x180054e4f  mov     eax, 8
0x180054e54  and     [rax+rbx], edi
0x180054e57  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180054e5d  mov     ecx, 4
0x180054e62  and     [rcx+rbx], edi
0x180054e65  mov     edi, 0AA04h
0x180054e6a  lea     rcx, [rsi+30h]
0x180054e6e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180054e74  or      dword ptr [rsi+88h], 4000h
0x180054e7e  lea     rcx, [rsi+30h]
0x180054e82  mov     [rsi+11Ch], edi
0x180054e88  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180054e8e  test    r14b, r14b
0x180054e91  jz      short loc_180054EBE
0x180054e93  mov     rdx, rsi
0x180054e96  mov     rcx, r15
0x180054e99  call    BipWorkItemTpWorkerQueueTaskInstanceReleaseSystemResource
0x180054e9e  jmp     short loc_180054EBE
0x180054ea0  lea     rcx, [rsi+30h]
0x180054ea4  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180054eaa  or      dword ptr [rsi+88h], 2000h
0x180054eb4  lea     rcx, [rsi+30h]
0x180054eb8  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180054ebe  call    BipAcquireGlobalLock
0x180054ec3  mov     rcx, [rsi+40h]
0x180054ec7  cmp     dword ptr [rcx+18h], 0
0x180054ecb  jl      short loc_180054EE1
0x180054ecd  lea     rax, [rcx+90h]
0x180054ed4  cmp     [rax], rax
0x180054ed7  jz      short loc_180054EE1
0x180054ed9  mov     rdx, rsi
0x180054edc  call    BipWorkItemTpWorkerQueueHamActivityWorker
0x180054ee1  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x180054ee6  mov     ecx, cs:dword_1800C3CB0
0x180054eec  mov     edi, 1
0x180054ef1  mov     edx, cs:_tls_index
0x180054ef7  xor     esi, esi
0x180054ef9  mov     rax, gs:58h
0x180054f02  shl     edi, cl
0x180054f04  lea     rcx, BipGlobalLock
0x180054f0b  not     edi
0x180054f0d  mov     cs:dword_1800C3CB4, esi
0x180054f13  mov     rbx, [rax+rdx*8]
0x180054f17  mov     eax, 8
0x180054f1c  and     [rax+rbx], edi
0x180054f1f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180054f25  mov     ecx, 4
0x180054f2a  and     [rcx+rbx], edi
0x180054f2d  mov     rdi, [rsp+130h+var_F8]
0x180054f32  lea     rbx, _TraceLoggingMetadataEnd
0x180054f39  mov     eax, cs:dword_1800C3098
0x180054f3f  cmp     eax, 5
0x180054f42  jbe     loc_18005505E
0x180054f48  mov     rcx, cs:qword_1800C30B0
0x180054f4f  mov     rax, cs:qword_1800C30A8
0x180054f56  test    al, 2
0x180054f58  jz      loc_18005505E
0x180054f5e  mov     rax, rcx
0x180054f61  and     eax, 2
0x180054f64  cmp     rax, rcx
0x180054f67  jnz     loc_18005505E
0x180054f6d  movzx   eax, r14b
0x180054f71  lea     rdx, [rsp+130h+var_D0]; EventDescriptor
0x180054f76  mov     [rsp+130h+var_100], eax
0x180054f7a  xor     r9d, r9d; RelatedActivityId
0x180054f7d  mov     eax, [r12+10h]
0x180054f82  xor     r8d, r8d; ActivityId
0x180054f85  mov     dword ptr [rsp+130h+var_F0], eax
0x180054f89  lea     rax, [rsp+130h+var_100]
0x180054f8e  mov     [rbp+30h+var_40], rax
0x180054f92  lea     rax, [rsp+130h+var_F0]
0x180054f97  mov     [rbp+30h+var_50], rax
0x180054f9b  lea     rax, [rsp+130h+var_C0]
0x180054fa0  mov     [rbp+30h+var_60], rax
0x180054fa4  lea     rax, [rbp+30h+var_B0]
0x180054fa8  mov     [rbp+30h+var_70], rax
0x180054fac  lea     rax, [rsp+130h+EventDescriptor]
0x180054fb1  mov     [rbp+30h+var_80], rax
0x180054fb5  movzx   eax, cs:word_1800AE89C
0x180054fbc  mov     dword ptr [rsp+130h+var_D0.Level], eax
0x180054fc0  mov     rax, cs:off_1800C30A0
0x180054fc7  mov     [rbp+30h+var_A0.Ptr], rax
0x180054fcb  mov     qword ptr [rsp+130h+EventDescriptor.Id], rdi
0x180054fd0  mov     [rbp+30h+var_38], 4
0x180054fd8  mov     [rbp+30h+var_48], 4
0x180054fe0  mov     [rbp+30h+var_58], 10h
0x180054fe8  mov     [rbp+30h+var_68], 10h
0x180054ff0  mov     [rbp+30h+var_78], 8
0x180054ff8  mov     dword ptr [rsp+130h+var_D0.Id], 0B000000h
0x180055000  mov     [rsp+130h+var_D0.Keyword], 2
0x180055009  movzx   eax, word ptr [rax]
0x18005500c  mov     [rbp+30h+var_A0.Size], eax
0x18005500f  lea     rax, word_1800AE8A6
0x180055016  mov     [rbp+30h+var_90], rax
0x18005501a  lea     rax, _TraceLoggingMetadata
0x180055021  sub     ebx, eax
0x180055023  mov     dword ptr [rbp+30h+var_A0.0Ch], 2
0x18005502a  mov     [rbp+30h+var_88], 63h ; 'c'
0x180055031  mov     [rbp+30h+var_84], 1
0x180055038  mov     dword ptr [rsp+130h+var_F8], ebx
0x18005503c  mov     eax, dword ptr [rsp+130h+var_F8]
0x180055040  mov     rcx, cs:RegHandle; RegHandle
0x180055047  lea     rax, [rbp+30h+var_A0]
0x18005504b  mov     [rsp+130h+UserData], rax; UserData
0x180055050  mov     [rsp+130h+UserDataCount], 7; UserDataCount
0x180055058  call    cs:__imp_EventWriteTransfer
0x18005505e  mov     rcx, [rbp+30h+var_30]
0x180055062  xor     rcx, rsp; StackCookie
0x180055065  call    __security_check_cookie
0x18005506a  lea     r11, [rsp+130h+var_20]
0x180055072  mov     rbx, [r11+38h]
0x180055076  mov     rsi, [r11+40h]
0x18005507a  mov     rsp, r11
0x18005507d  pop     r15
0x18005507f  pop     r14
0x180055081  pop     r12
0x180055083  pop     rdi
0x180055084  pop     rbp
0x180055085  retn
```
