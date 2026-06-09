# BriCreateBrokeredEventEx

- ea: `0x1800022b0`
- end: `0x1800026e2`
- name: `BriCreateBrokeredEventEx`
- size: `1074`
- prototype: `__int64 __usercall@<rax>(void *Source1@<rcx>, int, __int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001c30`
- `0x180001e00`
- `0x1800086d0`

## callees

- `0x1800022b0`
- `0x1800026f0`
- `0x180002e30`
- `0x180004270`
- `0x180006e70`
- `0x1800072e0`
- `0x18000b160`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002561`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000261c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002561`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000261c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002505`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002505`
- `ntdll!RtlAllocateHeap` at `0x1800024d4`
- `ntdll!RtlAllocateHeap` at `0x1800024d4`
- `ntdll!RtlComputeCrc32` at `0x180002523`
- `ntdll!RtlComputeCrc32` at `0x180002523`
- `ntdll!NtDuplicateObject` at `0x1800023d7`
- `ntdll!NtDuplicateObject` at `0x1800023d7`
- `ntdll!NtClose` at `0x18000258f`
- `ntdll!NtClose` at `0x18000258f`
- `ntdll!RtlRunOnceExecuteOnce` at `0x1800023a4`
- `ntdll!RtlRunOnceExecuteOnce` at `0x1800023a4`
- `ntdll!RtlLengthSid` at `0x180002408`
- `ntdll!RtlLengthSid` at `0x180002408`
- `ntdll!RtlValidSid` at `0x180002382`
- `ntdll!RtlValidSid` at `0x180002382`
- `ntdll!RtlInsertEntryHashTable` at `0x180002542`
- `ntdll!RtlInsertEntryHashTable` at `0x180002542`
- `RPCRT4!NdrClientCall3` at `0x1800024a6`
- `RPCRT4!NdrClientCall3` at `0x1800024a6`
- `RPCRT4!RpcBindingFree` at `0x1800025a1`
- `RPCRT4!RpcBindingFree` at `0x1800025e8`
- `RPCRT4!RpcBindingFree` at `0x1800025a1`
- `RPCRT4!RpcBindingFree` at `0x1800025e8`
- `RPCRT4!UuidEqual` at `0x18000242e`
- `RPCRT4!UuidEqual` at `0x18000242e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000250b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000250b`

## pseudocode

```c
__int64 __fastcall BriCreateBrokeredEventEx(
        UUID *Source1,
        __int64 a2,
        void *a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        _QWORD *a7,
        _OWORD *a8,
        __int64 a9)
{
  unsigned int v11; // esi
  NTSTATUS v12; // ebx
  unsigned int RpcBindingHandle; // eax
  ULONG v14; // eax
  void *v15; // rbx
  RPC_BINDING_HANDLE v16; // rsi
  unsigned int Event2; // eax
  char *Heap; // rax
  UCHAR *v19; // rsi
  ULONG v20; // eax
  __int64 v21; // r8
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  ULONG HandleAttributes[2]; // [rsp+30h] [rbp-D8h]
  __int64 v26; // [rsp+50h] [rbp-B8h]
  int v27; // [rsp+8Ch] [rbp-7Ch]
  __int64 v28; // [rsp+90h] [rbp-78h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp-70h] BYREF
  RPC_STATUS Status[2]; // [rsp+A0h] [rbp-68h] BYREF
  void *TargetHandle; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v32; // [rsp+B0h] [rbp-58h] BYREF
  void *v33; // [rsp+B8h] [rbp-50h]
  __int64 v34; // [rsp+C0h] [rbp-48h]
  __int64 v35; // [rsp+C8h] [rbp-40h]
  __int64 v36; // [rsp+D0h] [rbp-38h]
  __int64 v37; // [rsp+D8h] [rbp-30h]
  __int64 v38; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v39; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v40; // [rsp+F8h] [rbp-10h]

  v35 = a6;
  v34 = a9;
  v36 = a4;
  v37 = a2;
  if ( (a5 & 0xFFFFFFFC) != 0 )
    return 3221225485LL;
  v11 = (a5 & 1) + 1;
  v27 = 0;
  while ( 1 )
  {
    v38 = 0;
    LODWORD(v33) = 0;
    v32 = 0;
    Binding = 0;
    TargetHandle = 0;
    v28 = 0;
    v39 = 0;
    v40 = 0;
    if ( !Source1 || !a7 || !a8 || !a3 )
      break;
    if ( RtlValidSid(a3) )
    {
      v12 = RtlRunOnceExecuteOnce(&BrokerInternalClientInitOnce, BrpInitOnceRunOnceCallback, 0, 0);
      if ( v12 >= 0 )
      {
        v12 = NtDuplicateObject(
                (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                &TargetHandle,
                0x101000u,
                0,
                0);
        if ( v12 >= 0 )
        {
          *a7 = 0;
          RpcBindingHandle = BripCreateRpcBindingHandle(Source1);
          if ( RpcBindingHandle )
          {
            v12 = BripMapRpcStatus(RpcBindingHandle);
          }
          else
          {
            v33 = a3;
            v14 = RtlLengthSid(a3);
            v15 = TargetHandle;
            v16 = Binding;
            LODWORD(v32) = v14;
            Status[0] = 0;
            if ( UuidEqual(Source1, (UUID *)&g_SmsRouterBrokerId, Status) )
            {
              Event2 = BriCreateEvent2(
                         (_DWORD)v16,
                         (_DWORD)v15,
                         (a5 & 1) + 1,
                         v37,
                         (__int64)&v32,
                         v36,
                         (a5 >> 1) & 1,
                         v35,
                         (__int64)&v38,
                         (__int64)&v39,
                         (__int64)&v28,
                         v34);
            }
            else
            {
              LODWORD(v26) = (a5 >> 1) & 1;
              HandleAttributes[0] = (a5 & 1) + 1;
              Event2 = (unsigned int)NdrClientCall3(
                                       (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                       1u,
                                       0,
                                       v16,
                                       v15,
                                       *(_QWORD *)HandleAttributes,
                                       v37,
                                       &v32,
                                       v36,
                                       v26,
                                       v35,
                                       &v38,
                                       &v39,
                                       &v28,
                                       v34).Pointer;
            }
            if ( Event2 )
            {
              v12 = BripMapRpcStatus(Event2);
            }
            else
            {
              *(_QWORD *)Status = v28;
              Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x38u);
              v19 = (UCHAR *)Heap;
              if ( Heap )
              {
                *(UUID *)(Heap + 40) = *Source1;
                *((_QWORD *)Heap + 4) = v38;
                *((_QWORD *)Heap + 3) = *(_QWORD *)Status;
                RtlAcquireSRWLockExclusive(&BrokeredEventTableLock);
                dword_1800121A8 = GetCurrentThreadId();
                v20 = RtlComputeCrc32(0, v19 + 32, 8u);
                v21 = 1;
                if ( v20 )
                  v21 = v20;
                if ( (unsigned __int8)RtlInsertEntryHashTable(BrokeredEventTable, v19, v21, 0) )
                {
                  dword_1800121A8 = 0;
                  RtlReleaseSRWLockExclusive(&BrokeredEventTableLock);
                  v22 = v39;
                  v12 = 0;
                  v23 = v40;
                  *a7 = v38;
                  *a8 = v22;
                  a8[1] = v23;
                }
                else
                {
                  v12 = -1073741670;
                  EaLibFree(v19);
                  dword_1800121A8 = 0;
                  RtlReleaseSRWLockExclusive(&BrokeredEventTableLock);
                }
              }
              else
              {
                v12 = -1073741670;
              }
            }
            v11 = (a5 & 1) + 1;
          }
        }
      }
    }
    else
    {
      v12 = -1073741811;
    }
    if ( TargetHandle )
      NtClose(TargetHandle);
    if ( v12 < 0 && v28 )
      EapSystemBriDeleteEvent(Source1, Binding, v11, &v28);
    RpcBindingFree(&Binding);
    if ( v12 == -1073610724 && (unsigned int)++v27 <= 1 )
      continue;
    return (unsigned int)v12;
  }
  v12 = -1073741811;
  RpcBindingFree(&Binding);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800022b0  mov     r11, rsp
0x1800022b3  push    rbp
0x1800022b4  push    rdi
0x1800022b5  push    r12
0x1800022b7  push    r13
0x1800022b9  push    r14
0x1800022bb  push    r15
0x1800022bd  lea     rbp, [r11-58h]
0x1800022c1  sub     rsp, 128h
0x1800022c8  mov     rax, cs:__security_cookie
0x1800022cf  xor     rax, rsp
0x1800022d2  mov     [rbp+50h+var_50], rax
0x1800022d6  mov     rax, [rbp+50h+arg_28]
0x1800022dd  mov     r14, r8
0x1800022e0  mov     edi, [rbp+50h+arg_20]
0x1800022e6  mov     r15, rcx
0x1800022e9  mov     r12, [rbp+50h+arg_30]
0x1800022f0  mov     r13, [rbp+50h+arg_38]
0x1800022f7  mov     [rbp+50h+var_90], rax
0x1800022fb  mov     rax, [rbp+50h+arg_40]
0x180002302  mov     [rbp+50h+var_98], rax
0x180002306  mov     [rbp+50h+var_88], r9
0x18000230a  mov     [rbp+50h+var_80], rdx
0x18000230e  test    edi, 0FFFFFFFCh
0x180002314  jnz     loc_1800025F7
0x18000231a  mov     [r11-38h], rbx
0x18000231e  mov     [r11-40h], rsi
0x180002322  mov     esi, edi
0x180002324  and     esi, 1
0x180002327  shr     edi, 1
0x180002329  inc     esi
0x18000232b  and     edi, 1
0x18000232e  xor     ecx, ecx
0x180002330  mov     [rbp+50h+var_D0], esi
0x180002333  mov     [rbp+50h+var_CC], ecx
0x180002336  xor     eax, eax
0x180002338  mov     [rbp+50h+var_78], rcx
0x18000233c  mov     qword ptr [rbp+50h+var_A4], rax
0x180002340  xorps   xmm0, xmm0
0x180002343  mov     [rbp-58h], rax
0x180002347  mov     [rbp+50h+Binding], rcx
0x18000234b  mov     [rbp+50h+TargetHandle], rcx
0x18000234f  mov     [rbp+50h+var_C8], rcx
0x180002353  movups  [rbp+50h+var_70], xmm0
0x180002357  movups  [rbp+50h+var_60], xmm0
0x18000235b  test    r15, r15
0x18000235e  jz      loc_1800025DF
0x180002364  test    r12, r12
0x180002367  jz      loc_1800025DF
0x18000236d  test    r13, r13
0x180002370  jz      loc_1800025DF
0x180002376  test    r14, r14
0x180002379  jz      loc_1800025DF
0x18000237f  mov     rcx, r14; Sid
0x180002382  call    cs:__imp_RtlValidSid
0x180002388  test    al, al
0x18000238a  jz      loc_1800025F0
0x180002390  xor     r9d, r9d
0x180002393  lea     rdx, BrpInitOnceRunOnceCallback
0x18000239a  xor     r8d, r8d
0x18000239d  lea     rcx, BrokerInternalClientInitOnce
0x1800023a4  call    cs:__imp_RtlRunOnceExecuteOnce
0x1800023aa  mov     ebx, eax
0x1800023ac  test    eax, eax
0x1800023ae  js      loc_180002586
0x1800023b4  xor     eax, eax
0x1800023b6  lea     r9, [rbp+50h+TargetHandle]; TargetHandle
0x1800023ba  mov     rdx, 0FFFFFFFFFFFFFFFFh; SourceHandle
0x1800023c1  mov     [rsp+150h+Options], eax; Options
0x1800023c5  mov     [rsp+150h+HandleAttributes], eax; HandleAttributes
0x1800023c9  mov     rcx, rdx; SourceProcessHandle
0x1800023cc  mov     r8, rdx; TargetProcessHandle
0x1800023cf  mov     [rsp+150h+DesiredAccess], 101000h; DesiredAccess
0x1800023d7  call    cs:__imp_NtDuplicateObject
0x1800023dd  mov     ebx, eax
0x1800023df  test    eax, eax
0x1800023e1  js      loc_180002586
0x1800023e7  xor     eax, eax
0x1800023e9  lea     rdx, [rbp+50h+Binding]
0x1800023ed  mov     rcx, r15; Source1
0x1800023f0  mov     [r12], rax
0x1800023f4  call    BripCreateRpcBindingHandle
0x1800023f9  test    eax, eax
0x1800023fb  jnz     loc_180002642
0x180002401  mov     rcx, r14; Sid
0x180002404  mov     qword ptr [rbp+50h+var_A4+4], r14
0x180002408  call    cs:__imp_RtlLengthSid
0x18000240e  mov     rbx, [rbp+50h+TargetHandle]
0x180002412  lea     r8, [rbp+50h+Status]; Status
0x180002416  mov     rsi, [rbp+50h+Binding]
0x18000241a  lea     rdx, g_SmsRouterBrokerId; Uuid2
0x180002421  mov     rcx, r15; Uuid1
0x180002424  mov     [rbp+50h+var_A8], eax
0x180002427  mov     [rbp+50h+Status], 0
0x18000242e  call    cs:__imp_UuidEqual
0x180002434  test    eax, eax
0x180002436  mov     rax, [rbp+50h+var_98]
0x18000243a  jnz     loc_180002650
0x180002440  mov     [rsp+70h], rax
0x180002445  lea     rcx, pProxyInfo; pProxyInfo
0x18000244c  lea     rax, [rbp+50h+var_C8]
0x180002450  mov     r9, rsi
0x180002453  mov     [rsp+150h+var_E8], rax
0x180002458  xor     r8d, r8d; pReturnValue
0x18000245b  lea     rax, [rbp+50h+var_70]
0x18000245f  mov     edx, 1; nProcNum
0x180002464  mov     [rsp+150h+var_F0], rax
0x180002469  lea     rax, [rbp+50h+var_78]
0x18000246d  mov     [rsp+150h+var_F8], rax
0x180002472  mov     rax, [rbp+50h+var_90]
0x180002476  mov     [rsp+150h+var_100], rax
0x18000247b  mov     rax, [rbp+50h+var_88]
0x18000247f  mov     dword ptr [rsp+150h+var_108], edi
0x180002483  mov     [rsp+150h+var_110], rax
0x180002488  lea     rax, [rbp+50h+var_A8]
0x18000248c  mov     [rsp+150h+var_118], rax
0x180002491  mov     rax, [rbp+50h+var_80]
0x180002495  mov     qword ptr [rsp+150h+Options], rax
0x18000249a  mov     eax, [rbp+50h+var_D0]
0x18000249d  mov     [rsp+150h+HandleAttributes], eax
0x1800024a1  mov     qword ptr [rsp+150h+DesiredAccess], rbx
0x1800024a6  call    cs:__imp_NdrClientCall3
0x1800024ac  test    eax, eax
0x1800024ae  jnz     loc_1800026A7
0x1800024b4  mov     rcx, gs:60h
0x1800024bd  mov     edx, 8; Flags
0x1800024c2  mov     rax, [rbp+50h+var_C8]
0x1800024c6  mov     r8d, 38h ; '8'; Size
0x1800024cc  mov     qword ptr [rbp+50h+Status], rax
0x1800024d0  mov     rcx, [rcx+30h]; HeapHandle
0x1800024d4  call    cs:__imp_RtlAllocateHeap
0x1800024da  mov     rsi, rax
0x1800024dd  test    rax, rax
0x1800024e0  jz      loc_1800026B5
0x1800024e6  movups  xmm0, xmmword ptr [r15]
0x1800024ea  lea     rcx, BrokeredEventTableLock
0x1800024f1  movups  xmmword ptr [rax+28h], xmm0
0x1800024f5  mov     rax, [rbp+50h+var_78]
0x1800024f9  mov     [rsi+20h], rax
0x1800024fd  mov     rax, qword ptr [rbp+50h+Status]
0x180002501  mov     [rsi+18h], rax
0x180002505  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000250b  call    cs:__imp_GetCurrentThreadId
0x180002511  mov     r8d, 8; Length
0x180002517  lea     rdx, [rsi+20h]; Buffer
0x18000251b  xor     ecx, ecx; InitialCrc
0x18000251d  mov     cs:dword_1800121A8, eax
0x180002523  call    cs:__imp_RtlComputeCrc32
0x180002529  mov     rcx, cs:BrokeredEventTable
0x180002530  mov     r8d, 1
0x180002536  test    eax, eax
0x180002538  mov     rdx, rsi
0x18000253b  cmovnz  r8d, eax
0x18000253f  xor     r9d, r9d
0x180002542  call    cs:__imp_RtlInsertEntryHashTable
0x180002548  test    al, al
0x18000254a  jz      loc_1800025FE
0x180002550  lea     rcx, BrokeredEventTableLock
0x180002557  mov     cs:dword_1800121A8, 0
0x180002561  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002567  movups  xmm0, [rbp+50h+var_70]
0x18000256b  mov     rax, [rbp+50h+var_78]
0x18000256f  xor     ebx, ebx
0x180002571  movups  xmm1, [rbp+50h+var_60]
0x180002575  mov     [r12], rax
0x180002579  movups  xmmword ptr [r13+0], xmm0
0x18000257e  movups  xmmword ptr [r13+10h], xmm1
0x180002583  mov     esi, [rbp+50h+var_D0]
0x180002586  mov     rcx, [rbp+50h+TargetHandle]; Handle
0x18000258a  test    rcx, rcx
0x18000258d  jz      short loc_180002595
0x18000258f  call    cs:__imp_NtClose
0x180002595  test    ebx, ebx
0x180002597  js      loc_1800026BF
0x18000259d  lea     rcx, [rbp+50h+Binding]; Binding
0x1800025a1  call    cs:__imp_RpcBindingFree
0x1800025a7  cmp     ebx, 0C002001Ch
0x1800025ad  jz      short loc_180002627
0x1800025af  mov     rsi, [rsp+150h+var_38]
0x1800025b7  mov     eax, ebx
0x1800025b9  mov     rbx, [rsp+120h]
0x1800025c1  mov     rcx, [rbp+50h+var_50]
0x1800025c5  xor     rcx, rsp; StackCookie
0x1800025c8  call    __security_check_cookie
0x1800025cd  add     rsp, 128h
0x1800025d4  pop     r15
0x1800025d6  pop     r14
0x1800025d8  pop     r13
0x1800025da  pop     r12
0x1800025dc  pop     rdi
0x1800025dd  pop     rbp
0x1800025de  retn
0x1800025df  lea     rcx, [rbp+50h+Binding]; Binding
0x1800025e3  mov     ebx, 0C000000Dh
0x1800025e8  call    cs:__imp_RpcBindingFree
0x1800025ee  jmp     short loc_1800025AF
0x1800025f0  mov     ebx, 0C000000Dh
0x1800025f5  jmp     short loc_180002586
0x1800025f7  mov     eax, 0C000000Dh
0x1800025fc  jmp     short loc_1800025C1
0x1800025fe  mov     ebx, 0C000009Ah
0x180002603  mov     rcx, rsi
0x180002606  call    EaLibFree
0x18000260b  lea     rcx, BrokeredEventTableLock
0x180002612  mov     cs:dword_1800121A8, 0
0x18000261c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002622  jmp     loc_180002583
0x180002627  mov     eax, [rbp+50h+var_CC]
0x18000262a  mov     ecx, 0
0x18000262f  inc     eax
0x180002631  mov     [rbp+50h+var_CC], eax
0x180002634  cmp     eax, 1
0x180002637  jbe     loc_180002336
0x18000263d  jmp     loc_1800025AF
0x180002642  mov     ecx, eax
0x180002644  call    BripMapRpcStatus
0x180002649  mov     ebx, eax
0x18000264b  jmp     loc_180002586
0x180002650  mov     r9, [rbp+50h+var_80]
0x180002654  mov     rdx, rbx
0x180002657  mov     r8d, [rbp+50h+var_D0]
0x18000265b  mov     rcx, rsi
0x18000265e  mov     [rsp+150h+var_F8], rax
0x180002663  lea     rax, [rbp+50h+var_C8]
0x180002667  mov     [rsp+150h+var_100], rax
0x18000266c  lea     rax, [rbp+50h+var_70]
0x180002670  mov     [rsp+150h+var_108], rax
0x180002675  lea     rax, [rbp+50h+var_78]
0x180002679  mov     [rsp+150h+var_110], rax
0x18000267e  mov     rax, [rbp+50h+var_90]
0x180002682  mov     [rsp+150h+var_118], rax
0x180002687  mov     rax, [rbp+50h+var_88]
0x18000268b  mov     [rsp+150h+Options], edi
0x18000268f  mov     qword ptr [rsp+150h+HandleAttributes], rax
0x180002694  lea     rax, [rbp+50h+var_A8]
0x180002698  mov     qword ptr [rsp+150h+DesiredAccess], rax
0x18000269d  call    BriCreateEvent2
0x1800026a2  jmp     loc_1800024AC
0x1800026a7  mov     ecx, eax
0x1800026a9  call    BripMapRpcStatus
0x1800026ae  mov     ebx, eax
0x1800026b0  jmp     loc_180002583
0x1800026b5  mov     ebx, 0C000009Ah
0x1800026ba  jmp     loc_180002583
0x1800026bf  cmp     [rbp+50h+var_C8], 0
0x1800026c4  jz      loc_18000259D
0x1800026ca  mov     rdx, [rbp+50h+Binding]
0x1800026ce  lea     r9, [rbp+50h+var_C8]
0x1800026d2  mov     r8d, esi
0x1800026d5  mov     rcx, r15
0x1800026d8  call    EapSystemBriDeleteEvent
0x1800026dd  jmp     loc_18000259D
```
