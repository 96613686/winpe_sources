# BipBackgroundTaskBeginCallouts(_BI_ACTIVATED_TASK_INSTANCE *)

- ea: `0x1800133d4`
- end: `0x1800136bb`
- name: `?BipBackgroundTaskBeginCallouts@@YAJPEAU_BI_ACTIVATED_TASK_INSTANCE@@@Z`
- size: `743`
- prototype: `__int64 __fastcall(struct _BI_ACTIVATED_TASK_INSTANCE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180012960`

## callees

- `0x180005670`
- `0x18000a9f0`
- `0x180010c70`
- `0x1800133d4`
- `0x180015d9c`
- `0x180016100`
- `0x1800409bc`
- `0x180052ec4`
- `0x180055860`
- `0x180055a9c`
- `0x18005bed4`
- `0x18006d364`

## import_xrefs

- `ntdll!NtClearEvent` at `0x180013498`
- `ntdll!NtClearEvent` at `0x180013498`
- `ntdll!NtSetEvent` at `0x18001366b`
- `ntdll!NtSetEvent` at `0x18001366b`
- `ntdll!RtlFreeHeap` at `0x180013694`
- `ntdll!RtlFreeHeap` at `0x180013694`
- `ntdll!RtlAllocateHeap` at `0x18001344d`
- `ntdll!RtlAllocateHeap` at `0x18001344d`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x180013481`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x180013481`

## pseudocode

```c
__int64 __fastcall BipBackgroundTaskBeginCallouts(struct _BI_ACTIVATED_TASK_INSTANCE *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v5; // r14
  int v6; // edx
  __int64 v7; // r13
  __int64 v8; // rdx
  int v9; // ecx
  int v10; // esi
  __int64 v11; // rbp
  PVOID Heap; // rax
  void *v13; // r15
  __int64 v14; // rcx
  int v15; // ecx
  char v16; // r12
  unsigned int CrmActivityId; // eax
  __int64 v18; // r14
  int v19; // ebp
  __int64 **v20; // rcx
  __int64 *v21; // rdx
  __int64 **v22; // rax
  int v24; // r8d
  __int64 v25; // r10
  unsigned int v26; // edx
  unsigned int v27; // r9d
  int v28; // [rsp+80h] [rbp+8h] BYREF
  __int64 v29; // [rsp+88h] [rbp+10h]

  v3 = *((_QWORD *)a1 + 8);
  v5 = *((_QWORD *)a1 + 9);
  v29 = v5;
  v6 = *(_DWORD *)(v3 + 400);
  v7 = *(_QWORD *)(v3 + 80);
  if ( v6 )
  {
    v8 = (unsigned int)(v6 - 1);
    if ( (_DWORD)v8 != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(a1, v8, a3);
  }
  v9 = *(_DWORD *)(v3 + 400);
  if ( v9 )
  {
    if ( v9 == 2 )
      v10 = 1;
    else
      v10 = 4;
  }
  else
  {
    v10 = *(_DWORD *)(v3 + 448);
    if ( v10 == 4 )
      return 3221226021LL;
  }
  v11 = *(_QWORD *)(v3 + 88);
  Heap = RtlAllocateHeap(BipHeap, 0, 0x1D0u);
  v13 = Heap;
  if ( !Heap )
    return 3221225495LL;
  v14 = *(_QWORD *)(v11 + 16) + 160LL;
  v28 = 464;
  PsmCreateKey(v14, v11 + 60, Heap, &v28);
  ++*(_DWORD *)(v5 + 100);
  *(_DWORD *)(v5 + 48) |= 0x1000u;
  NtClearEvent(*(HANDLE *)(v7 + 560));
  v15 = *(_DWORD *)(v3 + 400);
  if ( !v15 || v15 == 2 )
    BipPdcReferenceAcquire((__int64 *)&xmmword_1800C40C8, (__int64)a1);
  v16 = 0;
  CrmActivityId = BipWorkItemGetCrmActivityId(v3);
  v18 = (int)CrmActivityId;
  v19 = BipCrmActivityStart(qword_1800C41E8, v3, CrmActivityId, v13, a1);
  if ( v19 < 0 )
    goto LABEL_34;
  *((_DWORD *)a1 + 84) = v18;
  if ( (unsigned int)(v18 - 26) <= 6 && (unsigned int)CempListEntryIsNull(v3 + 224) )
  {
    v21 = &qword_1800C40B0[2 * v18];
    v22 = (__int64 **)v21[1];
    if ( *v22 != v21 )
      __fastfail(3u);
    *v20 = v21;
    v20[1] = (__int64 *)v22;
    *v22 = (__int64 *)v20;
    v21[1] = (__int64)v20;
  }
  v16 = 1;
  if ( *(_DWORD *)(v3 + 400) )
    goto LABEL_31;
  v24 = *(_DWORD *)(v7 + 572) != 0 ? 2 : 0;
  if ( (*(_BYTE *)(v7 + 568) & 1) != 0 )
    v24 |= 4u;
  v25 = *(_QWORD *)(v3 + 72);
  if ( (*(_DWORD *)(v25 + 24) & 0x400) == 0
    || (unsigned __int8)BipUtilActTypeIsDebugSupported(0)
    && (unsigned __int8)BipUtilActTypeIsDebugSupported(v26)
    && (*(_DWORD *)(v25 + 24) & 0x2000) != 0
    && *(_DWORD *)(*(_QWORD *)(v3 + 80) + 572LL) )
  {
    v24 |= 1u;
  }
  v19 = BipSystemPsmReferenceBrokeredExecution(
          *(_QWORD *)(v25 + 168),
          *((_DWORD *)a1 + 35),
          (_DWORD)v13,
          v10,
          *((_QWORD *)a1 + 40),
          0,
          v24,
          (__int64)a1 + 80);
  if ( v19 >= 0 )
  {
LABEL_31:
    if ( dword_1800C3098 || (Microsoft_Windows_BrokerInfrastructureEnableBits & 1) != 0 )
      BipTraceTaskActivation(a1);
  }
  else
  {
LABEL_34:
    v27 = 12;
    if ( v29 )
      BipLeaveInstanceState(v29 + 48, 12);
    if ( !(unsigned __int8)BipIsPackageInState(v7, v27) )
      NtSetEvent(*(HANDLE *)(v7 + 560), 0);
    if ( v16 )
      BipCrmActivityStop(qword_1800C41E8, (unsigned int)v18, a1);
  }
  RtlFreeHeap(BipHeap, 0, v13);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1800133d4  mov     [rsp+arg_10], rbx
0x1800133d9  push    rbp
0x1800133da  push    rsi
0x1800133db  push    rdi
0x1800133dc  push    r12
0x1800133de  push    r13
0x1800133e0  push    r14
0x1800133e2  push    r15
0x1800133e4  sub     rsp, 40h
0x1800133e8  mov     rbx, [rcx+40h]
0x1800133ec  mov     rdi, rcx
0x1800133ef  mov     r14, [rcx+48h]
0x1800133f3  mov     [rsp+78h+arg_8], r14
0x1800133fb  mov     edx, [rbx+190h]
0x180013401  mov     r13, [rbx+50h]
0x180013405  test    edx, edx
0x180013407  jz      short loc_180013418
0x180013409  sub     edx, 1
0x18001340c  jz      short loc_180013413
0x18001340e  cmp     edx, 1
0x180013411  jz      short loc_180013418
0x180013413  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180013418  mov     ecx, [rbx+190h]
0x18001341e  mov     edx, 4
0x180013423  test    ecx, ecx
0x180013425  jz      loc_180013542
0x18001342b  cmp     ecx, 2
0x18001342e  jnz     loc_180013534
0x180013434  lea     esi, [rcx-1]
0x180013437  mov     rcx, cs:BipHeap; HeapHandle
0x18001343e  mov     r12d, 1D0h
0x180013444  mov     rbp, [rbx+58h]
0x180013448  mov     r8d, r12d; Size
0x18001344b  xor     edx, edx; Flags
0x18001344d  call    cs:__imp_RtlAllocateHeap
0x180013453  mov     r15, rax
0x180013456  test    rax, rax
0x180013459  jz      loc_18001369E
0x18001345f  mov     rcx, [rbp+10h]
0x180013463  lea     rdx, [rbp+3Ch]
0x180013467  add     rcx, 0A0h
0x18001346e  mov     [rsp+78h+arg_0], r12d
0x180013476  lea     r9, [rsp+78h+arg_0]
0x18001347e  mov     r8, rax
0x180013481  call    cs:__imp_PsmCreateKey
0x180013487  inc     dword ptr [r14+64h]
0x18001348b  bts     dword ptr [r14+30h], 0Ch
0x180013491  mov     rcx, [r13+230h]; EventHandle
0x180013498  call    cs:__imp_NtClearEvent
0x18001349e  mov     ecx, [rbx+190h]
0x1800134a4  test    ecx, ecx
0x1800134a6  jz      short loc_1800134B2
0x1800134a8  sub     ecx, 1
0x1800134ab  jz      short loc_1800134C1
0x1800134ad  cmp     ecx, 1
0x1800134b0  jnz     short loc_1800134C1
0x1800134b2  mov     rdx, rdi
0x1800134b5  lea     rcx, xmmword_1800C40C8
0x1800134bc  call    BipPdcReferenceAcquire
0x1800134c1  mov     rcx, rbx
0x1800134c4  xor     r12b, r12b
0x1800134c7  call    ?BipWorkItemGetCrmActivityId@@YA?AW4_CRM_ACTIVITY_ID@@PEAU_BI_WORK_ITEM@@@Z; BipWorkItemGetCrmActivityId(_BI_WORK_ITEM *)
0x1800134cc  movsxd  r14, eax
0x1800134cf  lea     rcx, qword_1800C41E8
0x1800134d6  mov     r8d, r14d
0x1800134d9  mov     [rsp+78h+var_58], rdi
0x1800134de  mov     r9, r15
0x1800134e1  mov     rdx, rbx
0x1800134e4  call    ?BipCrmActivityStart@@YAJPEAU_BI_CRM_CONTEXT@@PEAU_BI_WORK_ITEM@@W4_CRM_ACTIVITY_ID@@PEAU_BI_PSM_KEY@@PEAU_GUID@@@Z; BipCrmActivityStart(_BI_CRM_CONTEXT *,_BI_WORK_ITEM *,_CRM_ACTIVITY_ID,_BI_PSM_KEY *,_GUID *)
0x1800134e9  mov     ebp, eax
0x1800134eb  test    eax, eax
0x1800134ed  js      loc_180013634
0x1800134f3  lea     ecx, [r14-1Ah]
0x1800134f7  mov     [rdi+150h], r14d
0x1800134fe  cmp     ecx, 6
0x180013501  ja      short loc_180013568
0x180013503  lea     rcx, [rbx+0E0h]
0x18001350a  call    CempListEntryIsNull
0x18001350f  test    eax, eax
0x180013511  jz      short loc_180013568
0x180013513  mov     rax, r14
0x180013516  lea     rdx, qword_1800C40B0
0x18001351d  shl     rax, 4
0x180013521  add     rdx, rax
0x180013524  mov     rax, [rdx+8]
0x180013528  cmp     [rax], rdx
0x18001352b  jz      short loc_18001355A
0x18001352d  mov     ecx, 3
0x180013532  int     29h; Win8: RtlFailFast(ecx)
0x180013534  mov     esi, edx
0x180013536  test    ecx, ecx
0x180013538  jz      short loc_180013550
0x18001353a  sub     ecx, 1
0x18001353d  jmp     loc_180013437
0x180013542  mov     esi, [rbx+1C0h]
0x180013548  cmp     esi, edx
0x18001354a  jnz     loc_180013437
0x180013550  mov     eax, 0C0000225h
0x180013555  jmp     loc_1800136A3
0x18001355a  mov     [rcx], rdx
0x18001355d  mov     [rcx+8], rax
0x180013561  mov     [rax], rcx
0x180013564  mov     [rdx+8], rcx
0x180013568  mov     edx, [rbx+190h]
0x18001356e  mov     r12b, 1
0x180013571  test    edx, edx
0x180013573  jnz     loc_180013615
0x180013579  mov     eax, [r13+23Ch]
0x180013580  neg     eax
0x180013582  sbb     r8d, r8d
0x180013585  and     r8d, 2
0x180013589  test    [r13+238h], r12b
0x180013590  jz      short loc_180013596
0x180013592  or      r8d, 4
0x180013596  mov     r10, [rbx+48h]
0x18001359a  test    dword ptr [r10+18h], 400h
0x1800135a2  jz      short loc_1800135D1
0x1800135a4  mov     ecx, edx
0x1800135a6  call    BipUtilActTypeIsDebugSupported
0x1800135ab  test    al, al
0x1800135ad  jz      short loc_1800135D5
0x1800135af  mov     ecx, edx
0x1800135b1  call    BipUtilActTypeIsDebugSupported
0x1800135b6  test    al, al
0x1800135b8  jz      short loc_1800135D5
0x1800135ba  test    dword ptr [r10+18h], 2000h
0x1800135c2  jz      short loc_1800135D5
0x1800135c4  mov     rax, [rbx+50h]
0x1800135c8  cmp     dword ptr [rax+23Ch], 0
0x1800135cf  jz      short loc_1800135D5
0x1800135d1  or      r8d, 1
0x1800135d5  mov     edx, [rdi+8Ch]
0x1800135db  lea     rax, [rdi+50h]
0x1800135df  mov     rcx, [r10+0A8h]
0x1800135e6  mov     r9d, esi
0x1800135e9  mov     [rsp+78h+var_40], rax
0x1800135ee  mov     rax, [rdi+140h]
0x1800135f5  mov     [rsp+78h+var_48], r8d
0x1800135fa  mov     r8, r15
0x1800135fd  mov     [rsp+78h+var_50], 0
0x180013605  mov     [rsp+78h+var_58], rax
0x18001360a  call    BipSystemPsmReferenceBrokeredExecution
0x18001360f  mov     ebp, eax
0x180013611  test    eax, eax
0x180013613  js      short loc_180013634
0x180013615  mov     eax, cs:dword_1800C3098
0x18001361b  test    eax, eax
0x18001361d  jnz     short loc_180013628
0x18001361f  test    cs:Microsoft_Windows_BrokerInfrastructureEnableBits, r12b
0x180013626  jz      short loc_180013630
0x180013628  mov     rcx, rdi
0x18001362b  call    BipTraceTaskActivation
0x180013630  test    ebp, ebp
0x180013632  jns     short loc_180013688
0x180013634  mov     rax, [rsp+78h+arg_8]
0x18001363c  mov     r9d, 0Ch
0x180013642  test    rax, rax
0x180013645  jz      short loc_180013653
0x180013647  mov     edx, r9d
0x18001364a  lea     rcx, [rax+30h]
0x18001364e  call    BipLeaveInstanceState
0x180013653  mov     edx, r9d
0x180013656  mov     rcx, r13
0x180013659  call    BipIsPackageInState
0x18001365e  test    al, al
0x180013660  jnz     short loc_180013671
0x180013662  mov     rcx, [r13+230h]; EventHandle
0x180013669  xor     edx, edx; PreviousState
0x18001366b  call    cs:__imp_NtSetEvent
0x180013671  test    r12b, r12b
0x180013674  jz      short loc_180013688
0x180013676  mov     r8, rdi
0x180013679  lea     rcx, qword_1800C41E8
0x180013680  mov     edx, r14d
0x180013683  call    ?BipCrmActivityStop@@YAXPEAU_BI_CRM_CONTEXT@@W4_CRM_ACTIVITY_ID@@PEAU_GUID@@@Z; BipCrmActivityStop(_BI_CRM_CONTEXT *,_CRM_ACTIVITY_ID,_GUID *)
0x180013688  mov     rcx, cs:BipHeap; HeapHandle
0x18001368f  mov     r8, r15; P
0x180013692  xor     edx, edx; Flags
0x180013694  call    cs:__imp_RtlFreeHeap
0x18001369a  mov     eax, ebp
0x18001369c  jmp     short loc_1800136A3
0x18001369e  mov     eax, 0C0000017h
0x1800136a3  mov     rbx, [rsp+78h+arg_10]
0x1800136ab  add     rsp, 40h
0x1800136af  pop     r15
0x1800136b1  pop     r14
0x1800136b3  pop     r13
0x1800136b5  pop     r12
0x1800136b7  pop     rdi
0x1800136b8  pop     rsi
0x1800136b9  pop     rbp
0x1800136ba  retn
```
