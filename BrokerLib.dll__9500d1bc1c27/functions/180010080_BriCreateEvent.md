# _BriCreateEvent

- ea: `0x180010080`
- end: `0x1800109ab`
- name: `_BriCreateEvent`
- size: `2347`
- prototype: `__int64 __usercall@<rax>(RPC_BINDING_HANDLE Binding@<rcx>, HANDLE ProcessHandle@<rdx>, __int64, __int64, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180010000`

## callees

- `0x18000ae30`
- `0x18000afdc`
- `0x18000aff4`
- `0x18000b190`
- `0x18000b2b0`
- `0x180010080`
- `0x180015af0`
- `0x18001ab8c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18001038b`
- `ntdll!NtQueryInformationToken` at `0x18001038b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180010534`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180010534`
- `ntdll!RtlLengthSid` at `0x18001028a`
- `ntdll!RtlLengthSid` at `0x18001070d`
- `ntdll!RtlLengthSid` at `0x18001028a`
- `ntdll!RtlLengthSid` at `0x18001070d`
- `ntdll!NtOpenThreadToken` at `0x180010341`
- `ntdll!NtOpenThreadToken` at `0x180010341`
- `ntdll!RtlRbInsertNodeEx` at `0x180010600`
- `ntdll!RtlRbInsertNodeEx` at `0x180010600`
- `ntdll!TpSetWaitEx` at `0x180010621`
- `ntdll!TpSetWaitEx` at `0x180010621`
- `ntdll!NtDuplicateObject` at `0x18001050d`
- `ntdll!NtDuplicateObject` at `0x18001050d`
- `ntdll!TpAllocWait` at `0x180010528`
- `ntdll!TpAllocWait` at `0x180010528`
- `ntdll!RtlValidSid` at `0x180010276`
- `ntdll!RtlValidSid` at `0x1800106fa`
- `ntdll!RtlValidSid` at `0x180010276`
- `ntdll!RtlValidSid` at `0x1800106fa`
- `ntdll!RtlAllocateHeap` at `0x180010484`
- `ntdll!RtlAllocateHeap` at `0x180010484`
- `ntdll!RtlNtStatusToDosError` at `0x1800103e1`
- `ntdll!RtlNtStatusToDosError` at `0x1800103e1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010547`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010547`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010565`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001062e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010565`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001062e`
- `ntdll!RtlCopySid` at `0x1800103a7`
- `ntdll!RtlCopySid` at `0x1800103a7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010234`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001096c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010234`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001096c`
- `RPCRT4!RpcRevertToSelf` at `0x1800103b3`
- `RPCRT4!RpcRevertToSelf` at `0x1800103c6`
- `RPCRT4!RpcRevertToSelf` at `0x1800103b3`
- `RPCRT4!RpcRevertToSelf` at `0x1800103c6`
- `RPCRT4!RpcImpersonateClient` at `0x180010318`
- `RPCRT4!RpcImpersonateClient` at `0x180010318`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001032c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001032c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800103d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800103d5`

## pseudocode

```c
__int64 __fastcall BriCreateEvent(
        RPC_BINDING_HANDLE Binding,
        HANDLE ProcessHandle,
        unsigned int a3,
        const WCHAR *a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        __int64 a9,
        __m128i *a10,
        __int64 *a11,
        __int64 a12)
{
  __int64 *v12; // r13
  __int64 v14; // rcx
  __int64 v16; // r14
  void *v17; // rcx
  ULONG v18; // ebx
  struct _BROKER **v19; // r8
  ULONG BrokerEndpointByBinding; // edi
  signed int v21; // ebx
  HANDLE CurrentThread; // rax
  __int128 *v23; // rbx
  __int64 v24; // r12
  ULONG BrokeredEvent; // eax
  void **Heap; // rax
  void **v27; // rsi
  __int64 v28; // r15
  int v29; // eax
  __int64 v30; // r8
  __int64 v31; // rax
  unsigned __int64 v32; // rbx
  int v33; // edi
  unsigned __int64 v34; // rcx
  struct _RTL_BALANCED_NODE *v35; // rax
  void *v36; // rcx
  __m128i v37; // xmm2
  __m128i v38; // xmm0
  _QWORD *v39; // rcx
  __m128i v40; // xmm1
  __m128i *v41; // rax
  int v42; // esi
  struct _RTL_BALANCED_NODE *v43; // rcx
  void *v44; // rcx
  ULONG v45; // ebx
  unsigned __int8 *v46; // rcx
  int v47; // eax
  const WCHAR *v48; // rcx
  int v50; // eax
  char v52; // [rsp+60h] [rbp-A0h] BYREF
  ULONG ReturnLength; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v54; // [rsp+68h] [rbp-98h] BYREF
  ULONG v55; // [rsp+70h] [rbp-90h] BYREF
  int v56; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v57; // [rsp+78h] [rbp-88h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v59; // [rsp+88h] [rbp-78h]
  unsigned int v60; // [rsp+8Ch] [rbp-74h]
  __m128i *v61; // [rsp+90h] [rbp-70h]
  void *v62; // [rsp+98h] [rbp-68h] BYREF
  __int64 *v63; // [rsp+A0h] [rbp-60h]
  __int64 *v64; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v65; // [rsp+B0h] [rbp-50h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+B8h] [rbp-48h] BYREF
  const WCHAR *v67; // [rsp+C8h] [rbp-38h]
  __int64 v68; // [rsp+D0h] [rbp-30h]
  __m128i v69; // [rsp+D8h] [rbp-28h]
  __m128i v70; // [rsp+E8h] [rbp-18h]
  _OWORD TokenInformation[5]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v72; // [rsp+150h] [rbp+50h]
  __int64 v73; // [rsp+160h] [rbp+60h] BYREF
  __int128 v74; // [rsp+168h] [rbp+68h] BYREF
  __int128 v75; // [rsp+178h] [rbp+78h] BYREF
  __int128 DestinationSid; // [rsp+190h] [rbp+90h] BYREF
  __int128 v77; // [rsp+1A0h] [rbp+A0h]
  __int128 v78; // [rsp+1B0h] [rbp+B0h]
  __int128 v79; // [rsp+1C0h] [rbp+C0h]
  int v80; // [rsp+1D0h] [rbp+D0h]
  struct _EVENT_DATA_DESCRIPTOR v81; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v82; // [rsp+1F0h] [rbp+F0h]
  __int128 v83; // [rsp+200h] [rbp+100h]
  __int128 v84; // [rsp+210h] [rbp+110h]
  __int128 v85; // [rsp+220h] [rbp+120h]
  __int128 v86; // [rsp+230h] [rbp+130h]
  __int128 v87; // [rsp+240h] [rbp+140h]
  const WCHAR *v88; // [rsp+250h] [rbp+150h]
  int v89; // [rsp+258h] [rbp+158h]
  int v90; // [rsp+25Ch] [rbp+15Ch]
  unsigned __int8 *v91; // [rsp+260h] [rbp+160h]
  int v92; // [rsp+268h] [rbp+168h]
  int v93; // [rsp+26Ch] [rbp+16Ch]
  __int64 *v94; // [rsp+270h] [rbp+170h]
  __int64 v95; // [rsp+278h] [rbp+178h]
  int *v96; // [rsp+280h] [rbp+180h]
  __int64 v97; // [rsp+288h] [rbp+188h]
  ULONG *v98; // [rsp+290h] [rbp+190h]
  __int64 v99; // [rsp+298h] [rbp+198h]
  ULONG *p_ReturnLength; // [rsp+2A0h] [rbp+1A0h]
  __int64 v101; // [rsp+2A8h] [rbp+1A8h]
  __int64 *v102; // [rsp+2B0h] [rbp+1B0h]
  __int64 v103; // [rsp+2B8h] [rbp+1B8h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+2C0h] [rbp+1C0h] BYREF
  void *v105; // [rsp+2D0h] [rbp+1D0h]
  int v106; // [rsp+2D8h] [rbp+1D8h]
  int v107; // [rsp+2DCh] [rbp+1DCh]

  v12 = 0;
  v14 = (__int64)a10;
  v65 = a9;
  v68 = a12;
  v80 = 0;
  TokenHandle = 0;
  v62 = 0;
  v54 = 0;
  DestinationSid = 0;
  v55 = -1;
  v77 = 0;
  v56 = -1;
  v78 = 0;
  v73 = BLP_TRACELOGGING_INVALID_WNFSTATENAME;
  v67 = a4;
  v59 = a3;
  v57 = a5;
  v61 = a10;
  v64 = a11;
  v63 = 0;
  v79 = 0;
  v75 = BLP_TRACELOGGING_INVALID_GUID;
  v74 = BLP_TRACELOGGING_INVALID_GUID;
  v69 = 0;
  v70 = 0;
  if ( (unsigned int)dword_180028000 > 4 )
  {
    if ( (qword_180028010 & 1) != 0 && (qword_180028018 & 1) == qword_180028018 )
    {
      *(_DWORD *)&EventDescriptor.Level = 260;
      UserData.Ptr = (ULONGLONG)off_180028008;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 1;
      UserData.Size = *(unsigned __int16 *)off_180028008;
      v105 = &unk_180022339;
      UserData.Reserved = 2;
      v106 = 18;
      v107 = 1;
      ReturnLength = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
    }
    v14 = (__int64)v61;
  }
  v16 = -1;
  if ( !a11
    || !v14
    || !a5
    || (v17 = *(void **)(a5 + 8)) == 0
    || *(_DWORD *)a5 < 2u
    || !RtlValidSid(v17)
    || (v18 = *(_DWORD *)a5, v18 < RtlLengthSid(*(PSID *)(a5 + 8))) )
  {
    BrokerEndpointByBinding = 87;
    goto LABEL_61;
  }
  BrokerEndpointByBinding = Broker::GetBrokerEndpointByBinding(Binding, &v62, v19);
  if ( BrokerEndpointByBinding )
  {
    TokenHandle = v62;
    goto LABEL_61;
  }
  v80 = 0;
  DestinationSid = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  if ( ProcessHandle )
  {
    TokenHandle = 0;
    v81 = 0;
    v82 = 0;
    v83 = 0;
    v84 = 0;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    if ( RpcImpersonateClient(Binding) )
    {
      v21 = -1073741823;
    }
    else
    {
      CurrentThread = GetCurrentThread();
      v21 = NtOpenThreadToken(CurrentThread, 8u, 1u, &TokenHandle);
      if ( v21 < 0
        || (ReturnLength = 0,
            v72 = 0,
            memset(TokenInformation, 0, sizeof(TokenInformation)),
            v21 = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength),
            v21 < 0)
        || (v21 = RtlCopySid(0x44u, &DestinationSid, *(PSID *)&TokenInformation[0]), v21 < 0) )
      {
        RpcRevertToSelf();
      }
      else
      {
        v21 = RpcRevertToSelf() != 0 ? 0xC0000001 : 0;
      }
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    if ( v21 < 0 )
    {
      BrokerEndpointByBinding = RtlNtStatusToDosError(v21);
      TokenHandle = v62;
LABEL_61:
      v24 = v57;
      v28 = 0;
      goto LABEL_62;
    }
  }
  v23 = (__int128 *)v62;
  v24 = v57;
  TokenHandle = v62;
  BrokeredEvent = BrpCreateBrokeredEvent(v59, v62, v67, *(_QWORD *)(v57 + 8));
  v12 = v63;
  BrokerEndpointByBinding = BrokeredEvent;
  if ( BrokeredEvent )
    goto LABEL_29;
  v75 = *v23;
  v74 = *(_OWORD *)v63;
  v73 = v63[2];
  Heap = (void **)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x58u);
  v27 = Heap;
  if ( !Heap )
  {
    BrokerEndpointByBinding = 14;
LABEL_29:
    v28 = v54;
LABEL_62:
    v42 = -1;
    goto LABEL_63;
  }
  *Heap = 0;
  Heap[1] = 0;
  Heap[2] = 0;
  Heap[3] = 0;
  Heap[4] = 0;
  Heap[5] = 0;
  Heap[6] = 0;
  Heap[7] = &BrpDeleteBrokeredEventCallback;
  Heap[8] = (void *)16;
  Heap[9] = v23;
  Heap[10] = v12;
  BrokerEndpointByBinding = BrpRpcClientProcessHandleCheck(ProcessHandle);
  if ( BrokerEndpointByBinding
    || ProcessHandle
    && ((v29 = NtDuplicateObject(
                 (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                 ProcessHandle,
                 (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                 v27 + 4,
                 0,
                 0,
                 2u),
         v29 < 0)
     || (v29 = TpAllocWait(v27 + 5, BrpRpcContextProcessWaitCallback, v27, 0), v29 < 0))
    && (BrokerEndpointByBinding = RtlNtStatusToDosErrorNoTeb(v29)) != 0 )
  {
LABEL_37:
    BrpRpcContextEntryDestroy(v27, 3);
    v28 = v54;
    goto LABEL_62;
  }
  RtlAcquireSRWLockExclusive(&RpcContextTable);
  v31 = qword_180028968;
  if ( qword_180028968 == -1 )
  {
    BrokerEndpointByBinding = 534;
    RtlReleaseSRWLockExclusive(&RpcContextTable);
    goto LABEL_37;
  }
  ++qword_180028968;
  v27[3] = (void *)(v31 + 1);
  v32 = (unsigned __int64)xmmword_180028970;
  if ( (*(_BYTE *)(&xmmword_180028970 + 1) & 1) != 0 )
  {
    if ( !xmmword_180028970 )
    {
LABEL_46:
      LOBYTE(v30) = 0;
      goto LABEL_47;
    }
    v32 = (unsigned __int64)&xmmword_180028970 ^ (unsigned __int64)xmmword_180028970;
  }
  LOBYTE(v30) = 0;
  v33 = *(_BYTE *)(&xmmword_180028970 + 1) & 1;
  if ( !v32 )
    goto LABEL_47;
  while ( (int)BrpRpcContextCompareById(v27 + 3, (struct _RTL_BALANCED_NODE *)v32) < 0 )
  {
    v43 = *(struct _RTL_BALANCED_NODE **)v32;
    if ( v33 && v43 )
      v35 = (struct _RTL_BALANCED_NODE *)((unsigned __int64)v43 ^ v32);
    else
      v35 = *(struct _RTL_BALANCED_NODE **)v32;
    if ( !v35 )
      goto LABEL_46;
LABEL_58:
    v32 = (unsigned __int64)v35;
  }
  v34 = *(_QWORD *)(v32 + 8);
  if ( v33 && v34 )
    v35 = (struct _RTL_BALANCED_NODE *)(v34 ^ v32);
  else
    v35 = *(struct _RTL_BALANCED_NODE **)(v32 + 8);
  if ( v35 )
    goto LABEL_58;
  LOBYTE(v30) = 1;
LABEL_47:
  RtlRbInsertNodeEx(&xmmword_180028970, v32, v30, v27);
  v36 = v27[5];
  v28 = (__int64)v27[3];
  *((_BYTE *)v27 + 48) = 1;
  if ( v36 )
    TpSetWaitEx(v36, v27[4], 0, 0);
  RtlReleaseSRWLockExclusive(&RpcContextTable);
  v37 = v69;
  v12 = 0;
  v38 = v70;
  v39 = (_QWORD *)v65;
  BrokerEndpointByBinding = 0;
  v40 = v69;
  v56 = v69.m128i_i32[0];
  *v64 = v28;
  *v39 = v73;
  v41 = v61;
  v42 = _mm_cvtsi128_si32(_mm_srli_si128(v40, 4));
  *v61 = v37;
  v41[1] = v38;
  v55 = _mm_cvtsi128_si32(_mm_srli_si128(v37, 8));
LABEL_63:
  if ( dword_180028000 )
  {
    if ( v24
      && (v44 = *(void **)(v24 + 8)) != 0
      && *(_DWORD *)v24 >= 2u
      && RtlValidSid(v44)
      && (v45 = *(_DWORD *)v24, v45 >= RtlLengthSid(*(PSID *)(v24 + 8))) )
    {
      v46 = *(unsigned __int8 **)(v24 + 8);
    }
    else
    {
      v46 = (unsigned __int8 *)&BLP_TRACELOGGING_INVALID_SID;
    }
    if ( (unsigned int)dword_180028000 > 4 && (qword_180028010 & 1) != 0 && (qword_180028018 & 1) == qword_180028018 )
    {
      ReturnLength = v55;
      LODWORD(v57) = a7;
      v52 = v59;
      v64 = &v73;
      v102 = &v65;
      p_ReturnLength = &ReturnLength;
      v98 = &v55;
      v96 = &v56;
      v94 = &v57;
      v65 = v28;
      v55 = v42;
      LODWORD(v54) = BrokerEndpointByBinding;
      v103 = 8;
      v101 = 4;
      v99 = 4;
      v97 = 4;
      v95 = 4;
      v47 = v46[1];
      v91 = v46;
      v48 = v67;
      v93 = 0;
      v92 = 4 * v47 + 8;
      if ( v67 )
      {
        while ( v67[++v16] != 0 )
          ;
        v50 = 2 * v16 + 2;
      }
      else
      {
        v48 = &LocaleName;
        v50 = 2;
      }
      v89 = v50;
      v88 = v48;
      *(_QWORD *)&v87 = &v52;
      v90 = 0;
      *(_QWORD *)&v86 = &v64;
      *((_QWORD *)&v87 + 1) = 1;
      *(_QWORD *)&v85 = &v54;
      *((_QWORD *)&v86 + 1) = 8;
      *(_QWORD *)&v84 = &v74;
      *(_QWORD *)&v83 = &v75;
      *(_DWORD *)&EventDescriptor.Level = 516;
      v81.Ptr = (ULONGLONG)off_180028008;
      *((_QWORD *)&v85 + 1) = 4;
      *((_QWORD *)&v84 + 1) = 16;
      *((_QWORD *)&v83 + 1) = 16;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 1;
      v81.Size = *(unsigned __int16 *)off_180028008;
      *(_QWORD *)&v82 = &unk_180022357;
      v81.Reserved = 2;
      *((_QWORD *)&v82 + 1) = 0x1000000A2LL;
      v60 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xEu, &v81);
    }
  }
  if ( v12 )
    BrpDeleteBrokeredEvent(v59, TokenHandle, v12);
  return BrokerEndpointByBinding;
}

```

## disassembly

```asm
0x180010080  push    rbp
0x180010082  push    rbx
0x180010083  push    rsi
0x180010084  push    rdi
0x180010085  push    r12
0x180010087  push    r13
0x180010089  push    r14
0x18001008b  push    r15
0x18001008d  lea     rbp, [rsp-1F8h]
0x180010095  sub     rsp, 2F8h
0x18001009c  mov     rax, cs:__security_cookie
0x1800100a3  xor     rax, rsp
0x1800100a6  mov     [rbp+230h+var_50], rax
0x1800100ad  mov     rax, [rbp+230h+arg_40]
0x1800100b4  xorps   xmm0, xmm0
0x1800100b7  mov     rdi, [rbp+230h+arg_20]
0x1800100be  xor     r13d, r13d
0x1800100c1  mov     rbx, [rbp+230h+arg_50]
0x1800100c8  mov     rsi, rcx
0x1800100cb  mov     rcx, [rbp+230h+arg_48]
0x1800100d2  mov     r15, rdx
0x1800100d5  mov     r12, [rbp+230h+arg_28]
0x1800100dc  lea     rdx, _TraceLoggingMetadata
0x1800100e3  mov     [rbp+230h+var_280], rax
0x1800100e7  mov     rax, [rbp+230h+arg_58]
0x1800100ee  mov     [rbp+230h+var_260], rax
0x1800100f2  xor     eax, eax
0x1800100f4  mov     [rbp+230h+var_160], eax
0x1800100fa  mov     [rbp+230h+TokenHandle], rax
0x1800100fe  mov     [rbp+230h+var_298], rax
0x180010102  mov     [rsp+330h+var_2C8], rax
0x180010107  mov     eax, 0FFFFFFFFh
0x18001010c  movups  [rbp+230h+DestinationSid], xmm0
0x180010113  mov     [rsp+330h+var_2C0], eax
0x180010117  movups  [rbp+230h+var_190], xmm0
0x18001011e  mov     [rsp+330h+var_2BC], eax
0x180010122  mov     rax, cs:BLP_TRACELOGGING_INVALID_WNFSTATENAME
0x180010129  movups  [rbp+230h+var_180], xmm0
0x180010130  mov     [rbp+230h+var_1D0], rax
0x180010134  mov     eax, cs:dword_180028000
0x18001013a  mov     [rbp+230h+var_268], r9
0x18001013e  mov     [rbp+230h+var_2A8], r8d
0x180010142  mov     [rsp+330h+var_2B8], rdi
0x180010147  mov     [rbp+230h+var_2A0], rcx
0x18001014b  mov     [rbp+230h+var_288], rbx
0x18001014f  mov     [rbp+230h+var_290], r13
0x180010153  movups  [rbp+230h+var_170], xmm0
0x18001015a  movups  xmm0, cs:BLP_TRACELOGGING_INVALID_GUID
0x180010161  movups  [rbp+230h+var_1B8], xmm0
0x180010165  movups  [rbp+230h+var_1C8], xmm0
0x180010169  xorps   xmm0, xmm0
0x18001016c  movups  [rbp+230h+var_258], xmm0
0x180010170  movups  [rbp+230h+var_248], xmm0
0x180010174  cmp     eax, 4
0x180010177  jbe     loc_18001023E
0x18001017d  mov     rcx, cs:qword_180028018
0x180010184  mov     rax, cs:qword_180028010
0x18001018b  test    al, 1
0x18001018d  jz      loc_18001023A
0x180010193  mov     rax, rcx
0x180010196  and     eax, 1
0x180010199  cmp     rax, rcx
0x18001019c  jnz     loc_18001023A
0x1800101a2  movzx   eax, cs:word_18002232F
0x1800101a9  xor     r9d, r9d; RelatedActivityId
0x1800101ac  mov     dword ptr [rbp+230h+EventDescriptor.Level], eax
0x1800101af  xor     r8d, r8d; ActivityId
0x1800101b2  mov     rax, cs:off_180028008
0x1800101b9  mov     [rbp+230h+var_70.Ptr], rax
0x1800101c0  mov     dword ptr [rbp+230h+EventDescriptor.Id], 0B000000h
0x1800101c7  mov     [rbp+230h+EventDescriptor.Keyword], 1
0x1800101cf  movzx   eax, word ptr [rax]
0x1800101d2  mov     [rbp+230h+var_70.Size], eax
0x1800101d8  lea     rax, unk_180022339
0x1800101df  mov     [rbp+230h+var_60], rax
0x1800101e6  lea     rax, _TraceLoggingMetadataEnd
0x1800101ed  sub     eax, edx
0x1800101ef  mov     dword ptr [rbp+230h+var_70.0Ch], 2
0x1800101f9  mov     [rbp+230h+var_58], 12h
0x180010203  lea     rdx, [rbp+230h+EventDescriptor]; EventDescriptor
0x180010207  mov     [rbp+230h+var_54], 1
0x180010211  mov     [rsp+330h+ReturnLength], eax
0x180010215  mov     eax, [rsp+330h+ReturnLength]
0x180010219  mov     rcx, cs:RegHandle; RegHandle
0x180010220  lea     rax, [rbp+230h+var_70]
0x180010227  mov     [rsp+330h+UserData], rax; UserData
0x18001022c  mov     [rsp+330h+UserDataCount], 2; UserDataCount
0x180010234  call    cs:__imp_EventWriteTransfer
0x18001023a  mov     rcx, [rbp+230h+var_2A0]
0x18001023e  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180010245  test    rbx, rbx
0x180010248  jz      loc_1800106C4
0x18001024e  test    rcx, rcx
0x180010251  jz      loc_1800106C4
0x180010257  test    rdi, rdi
0x18001025a  jz      loc_1800106C4
0x180010260  mov     rcx, [rdi+8]; Sid
0x180010264  test    rcx, rcx
0x180010267  jz      loc_1800106C4
0x18001026d  cmp     dword ptr [rdi], 2
0x180010270  jb      loc_1800106C4
0x180010276  call    cs:__imp_RtlValidSid
0x18001027c  test    al, al
0x18001027e  jz      loc_1800106C4
0x180010284  mov     rcx, [rdi+8]; Sid
0x180010288  mov     ebx, [rdi]
0x18001028a  call    cs:__imp_RtlLengthSid
0x180010290  cmp     ebx, eax
0x180010292  jb      loc_1800106C4
0x180010298  lea     rdx, [rbp+230h+var_298]; void *
0x18001029c  mov     rcx, rsi; Binding
0x18001029f  call    ?GetBrokerEndpointByBinding@Broker@@YAKPEAXPEAPEAU_BROKER@@@Z; Broker::GetBrokerEndpointByBinding(void *,_BROKER * *)
0x1800102a4  mov     edi, eax
0x1800102a6  test    eax, eax
0x1800102a8  jnz     loc_1800106BA
0x1800102ae  xorps   xmm0, xmm0
0x1800102b1  xor     eax, eax
0x1800102b3  mov     [rbp+230h+var_160], eax
0x1800102b9  movups  [rbp+230h+DestinationSid], xmm0
0x1800102c0  movups  [rbp+230h+var_190], xmm0
0x1800102c7  movups  [rbp+230h+var_180], xmm0
0x1800102ce  movups  [rbp+230h+var_170], xmm0
0x1800102d5  test    r15, r15
0x1800102d8  jz      loc_1800103F6
0x1800102de  xor     edi, edi
0x1800102e0  mov     rcx, rsi; BindingHandle
0x1800102e3  mov     [rbp+230h+TokenHandle], rdi
0x1800102e7  movups  xmmword ptr [rbp+230h+var_150.Ptr], xmm0
0x1800102ee  movups  [rbp+230h+var_140], xmm0
0x1800102f5  movups  [rbp+230h+var_130], xmm0
0x1800102fc  movups  [rbp+230h+var_120], xmm0
0x180010303  movups  [rbp+230h+var_110], xmm0
0x18001030a  movups  [rbp+230h+var_100], xmm0
0x180010311  movups  [rbp+230h+var_F0], xmm0
0x180010318  call    cs:__imp_RpcImpersonateClient
0x18001031e  test    eax, eax
0x180010320  jz      short loc_18001032C
0x180010322  mov     ebx, 0C0000001h
0x180010327  jmp     loc_1800103CC
0x18001032c  call    cs:__imp_GetCurrentThread
0x180010332  lea     r9, [rbp+230h+TokenHandle]; TokenHandle
0x180010336  mov     r8b, 1; OpenAsSelf
0x180010339  mov     rcx, rax; ThreadHandle
0x18001033c  mov     edx, 8; DesiredAccess
0x180010341  call    cs:__imp_NtOpenThreadToken
0x180010347  mov     ebx, eax
0x180010349  test    eax, eax
0x18001034b  js      short loc_1800103C6
0x18001034d  mov     rcx, [rbp+230h+TokenHandle]; TokenHandle
0x180010351  lea     r8, [rbp+230h+TokenInformation]; TokenInformation
0x180010355  xorps   xmm0, xmm0
0x180010358  mov     [rsp+330h+ReturnLength], edi
0x18001035c  xor     eax, eax
0x18001035e  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180010364  mov     [rbp+230h+var_1E0], rax
0x180010368  mov     edx, 1; TokenInformationClass
0x18001036d  lea     rax, [rsp+330h+ReturnLength]
0x180010372  mov     qword ptr [rsp+330h+UserDataCount], rax; ReturnLength
0x180010377  movups  [rbp+230h+TokenInformation], xmm0
0x18001037b  movups  [rbp+230h+var_220], xmm0
0x18001037f  movups  [rbp+230h+var_210], xmm0
0x180010383  movups  [rbp+230h+var_200], xmm0
0x180010387  movups  [rbp+230h+var_1F0], xmm0
0x18001038b  call    cs:__imp_NtQueryInformationToken
0x180010391  mov     ebx, eax
0x180010393  test    eax, eax
0x180010395  js      short loc_1800103C6
0x180010397  mov     r8, qword ptr [rbp+230h+TokenInformation]; SourceSid
0x18001039b  lea     rdx, [rbp+230h+DestinationSid]; DestinationSid
0x1800103a2  mov     ecx, 44h ; 'D'; DestinationSidLength
0x1800103a7  call    cs:__imp_RtlCopySid
0x1800103ad  mov     ebx, eax
0x1800103af  test    eax, eax
0x1800103b1  js      short loc_1800103C6
0x1800103b3  call    cs:__imp_RpcRevertToSelf
0x1800103b9  neg     eax
0x1800103bb  mov     ebx, 0C0000001h
0x1800103c0  sbb     ecx, ecx
0x1800103c2  and     ebx, ecx
0x1800103c4  jmp     short loc_1800103CC
0x1800103c6  call    cs:__imp_RpcRevertToSelf
0x1800103cc  mov     rcx, [rbp+230h+TokenHandle]; hObject
0x1800103d0  test    rcx, rcx
0x1800103d3  jz      short loc_1800103DB
0x1800103d5  call    cs:__imp_CloseHandle
0x1800103db  test    ebx, ebx
0x1800103dd  jns     short loc_1800103F6
0x1800103df  mov     ecx, ebx; Status
0x1800103e1  call    cs:__imp_RtlNtStatusToDosError
0x1800103e7  mov     rcx, [rbp+230h+var_298]
0x1800103eb  mov     edi, eax
0x1800103ed  mov     [rbp+230h+TokenHandle], rcx
0x1800103f1  jmp     loc_1800106C9
0x1800103f6  mov     rax, [rbp+230h+var_260]
0x1800103fa  mov     rbx, [rbp+230h+var_298]
0x1800103fe  mov     r8, [rbp+230h+var_268]
0x180010402  mov     rdx, rbx
0x180010405  mov     ecx, [rbp+230h+var_2A8]
0x180010408  mov     [rsp+330h+var_2E0], rax
0x18001040d  lea     rax, [rbp+230h+var_258]
0x180010411  mov     [rsp+330h+var_2E8], rax
0x180010416  lea     rax, [rbp+230h+var_290]
0x18001041a  mov     [rsp+330h+var_2F0], rax
0x18001041f  mov     rax, [rbp+230h+arg_38]
0x180010426  mov     [rsp+330h+var_2F8], rax
0x18001042b  mov     eax, [rbp+230h+arg_30]
0x180010431  mov     [rsp+330h+Options], eax
0x180010435  mov     [rsp+330h+UserData], r12
0x18001043a  mov     r12, [rsp+330h+var_2B8]
0x18001043f  mov     [rbp+230h+TokenHandle], rbx
0x180010443  mov     r9, [r12+8]
0x180010448  call    ?BrpCreateBrokeredEvent@@YAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEBGPEAX3PEAU_BR_EVENT_PARAMETERS@@KPEBU_GUID@@PEAPEAU_BROKERED_EVENT@@PEAU_BR_NEW_EVENT_INFORMATION@@PEAU_CBROKERED_EVENT_ID@@@Z; BrpCreateBrokeredEvent(_BR_EVENT_CALL_REASON,_BROKER *,ushort const *,void *,void *,_BR_EVENT_PARAMETERS *,ulong,_GUID const *,_BROKERED_EVENT * *,_BR_NEW_EVENT_INFORMATION *,_CBROKERED_EVENT_ID *)
0x18001044d  mov     r13, [rbp+230h+var_290]
0x180010451  mov     edi, eax
0x180010453  test    eax, eax
0x180010455  jnz     short loc_180010497
0x180010457  movups  xmm0, xmmword ptr [rbx]
0x18001045a  xor     edx, edx; Flags
0x18001045c  mov     r8d, 58h ; 'X'; Size
0x180010462  movups  [rbp+230h+var_1B8], xmm0
0x180010466  movups  xmm0, xmmword ptr [r13+0]
0x18001046b  movups  [rbp+230h+var_1C8], xmm0
0x18001046f  mov     rax, [r13+10h]
0x180010473  mov     [rbp+230h+var_1D0], rax
0x180010477  mov     rcx, gs:60h
0x180010480  mov     rcx, [rcx+30h]; HeapHandle
0x180010484  call    cs:__imp_RtlAllocateHeap
0x18001048a  mov     rsi, rax
0x18001048d  test    rax, rax
0x180010490  jnz     short loc_1800104A1
0x180010492  mov     edi, 0Eh
0x180010497  mov     r15, [rsp+330h+var_2C8]
0x18001049c  jmp     loc_1800106D1
0x1800104a1  xor     eax, eax
0x1800104a3  mov     rcx, r15; ProcessHandle
0x1800104a6  mov     [rsi], rax
0x1800104a9  mov     [rsi+8], rax
0x1800104ad  mov     [rsi+10h], rax
0x1800104b1  mov     [rsi+18h], rax
0x1800104b5  mov     [rsi+20h], rax
0x1800104b9  mov     [rsi+28h], rax
0x1800104bd  mov     [rsi+30h], rax
0x1800104c1  lea     rax, ?BrpDeleteBrokeredEventCallback@@YAX_KPEAXW4_BR_EVENT_CALL_REASON@@@Z; BrpDeleteBrokeredEventCallback(unsigned __int64,void *,_BR_EVENT_CALL_REASON)
0x1800104c8  mov     [rsi+38h], rax
0x1800104cc  mov     qword ptr [rsi+40h], 10h
0x1800104d4  mov     [rsi+48h], rbx
0x1800104d8  mov     [rsi+50h], r13
0x1800104dc  call    ?BrpRpcClientProcessHandleCheck@@YAKPEAX@Z; BrpRpcClientProcessHandleCheck(void *)
0x1800104e1  mov     edi, eax
0x1800104e3  test    eax, eax
0x1800104e5  jnz     loc_18001056B
0x1800104eb  test    r15, r15
0x1800104ee  jz      short loc_180010540
0x1800104f0  mov     [rsp+330h+Options], 2; Options
0x1800104f8  lea     r9, [rsi+20h]; TargetHandle
0x1800104fc  mov     dword ptr [rsp+330h+UserData], eax; HandleAttributes
0x180010500  mov     r8, r14; TargetProcessHandle
0x180010503  mov     rdx, r15; SourceHandle
0x180010506  mov     [rsp+330h+UserDataCount], eax; DesiredAccess
0x18001050a  mov     rcx, r14; SourceProcessHandle
0x18001050d  call    cs:__imp_NtDuplicateObject
0x180010513  test    eax, eax
0x180010515  js      short loc_180010532
0x180010517  lea     rcx, [rsi+28h]
0x18001051b  xor     r9d, r9d
0x18001051e  mov     r8, rsi
0x180010521  lea     rdx, ?BrpRpcContextProcessWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; BrpRpcContextProcessWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)
0x180010528  call    cs:__imp_TpAllocWait
0x18001052e  test    eax, eax
0x180010530  jns     short loc_180010540
0x180010532  mov     ecx, eax; Status
0x180010534  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001053a  mov     edi, eax
0x18001053c  test    eax, eax
0x18001053e  jnz     short loc_18001056B
0x180010540  lea     rcx, ?RpcContextTable@@3U_BR_RPC_CONTEXT_TABLE@@A; _BR_RPC_CONTEXT_TABLE RpcContextTable
0x180010547  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001054d  mov     rax, cs:qword_180028968
0x180010554  cmp     rax, r14
0x180010557  jnz     short loc_180010582
0x180010559  lea     rcx, ?RpcContextTable@@3U_BR_RPC_CONTEXT_TABLE@@A; _BR_RPC_CONTEXT_TABLE RpcContextTable
0x180010560  mov     edi, 216h
0x180010565  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001056b  mov     edx, 3
0x180010570  mov     rcx, rsi
0x180010573  call    ?BrpRpcContextEntryDestroy@@YAXPEAU_BR_RPC_CONTEXT_ENTRY@@W4_BR_EVENT_CALL_REASON@@@Z; BrpRpcContextEntryDestroy(_BR_RPC_CONTEXT_ENTRY *,_BR_EVENT_CALL_REASON)
0x180010578  mov     r15, [rsp+330h+var_2C8]
0x18001057d  jmp     loc_1800106D1
0x180010582  inc     rax
0x180010585  lea     r13, xmmword_180028970
0x18001058c  mov     cs:qword_180028968, rax
0x180010593  mov     [rsi+18h], rax
0x180010597  mov     rax, qword ptr cs:xmmword_180028970+8
0x18001059e  mov     rbx, qword ptr cs:xmmword_180028970
0x1800105a5  test    al, 1
0x1800105a7  jz      short loc_1800105B1
0x1800105a9  test    rbx, rbx
0x1800105ac  jz      short loc_1800105F4
0x1800105ae  xor     rbx, r13
0x1800105b1  movzx   edi, al
  ... truncated ...
```
