# BipWorkItemCreateAggregatedEvent

- ea: `0x18005ace4`
- end: `0x18005b0be`
- name: `BipWorkItemCreateAggregatedEvent`
- size: `986`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180008598`
- `0x1800802c0`

## callees

- `0x18000d7c0`
- `0x18000da50`
- `0x1800121b0`
- `0x180016370`
- `0x18003b408`
- `0x18003dc6c`
- `0x180053100`
- `0x18005ace4`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlWakeAddressAll` at `0x18005affa`
- `ntdll!RtlWakeAddressAll` at `0x18005affa`
- `ntdll!RtlFreeHeap` at `0x18005b011`
- `ntdll!RtlFreeHeap` at `0x18005b011`
- `ntdll!RtlAllocateHeap` at `0x18005ae48`
- `ntdll!RtlAllocateHeap` at `0x18005af3a`
- `ntdll!RtlAllocateHeap` at `0x18005ae48`
- `ntdll!RtlAllocateHeap` at `0x18005af3a`
- `EventAggregation!EaCreateAggregation` at `0x18005af99`
- `EventAggregation!EaCreateAggregation` at `0x18005af99`
- `EventAggregation!EaDeleteAggregation` at `0x18005b037`
- `EventAggregation!EaDeleteAggregation` at `0x18005b037`

## pseudocode

```c
__int64 __fastcall BipWorkItemCreateAggregatedEvent(__int64 a1, char a2)
{
  __int64 v2; // rbx
  __int64 v5; // rax
  _QWORD *v6; // r14
  _BYTE *v7; // r15
  unsigned __int64 v8; // rcx
  int v9; // ebx
  int v10; // esi
  unsigned int v11; // edx
  __int64 v12; // r8
  _BYTE *Heap; // rax
  unsigned int v14; // r9d
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rsi
  unsigned __int64 v20; // rsi
  __int64 v21; // rdx
  __int128 *v22; // rax
  _QWORD *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  int v32; // [rsp+48h] [rbp-B8h] BYREF
  int v33; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v35[3]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+88h] [rbp-78h]
  __int128 v37; // [rsp+90h] [rbp-70h] BYREF
  __int128 v38; // [rsp+A0h] [rbp-60h]
  __int128 v39; // [rsp+B0h] [rbp-50h]
  __int64 v40; // [rsp+C0h] [rbp-40h]
  _OWORD v41[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v42; // [rsp+E8h] [rbp-18h]

  v2 = *(unsigned int *)(a1 + 624);
  v40 = 0;
  v36 = 0;
  v42 = 0;
  v5 = *(_QWORD *)(a1 + 72);
  v6 = 0;
  memset(v41, 0, sizeof(v41));
  v31 = 0;
  v7 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  memset(v35, 0, sizeof(v35));
  *((_QWORD *)&v41[0] + 1) = *(_QWORD *)(v5 + 148);
  BipAcquireGlobalLock(*((_QWORD *)&v41[0] + 1));
  if ( !(unsigned __int8)BipIsWorkItemActivatable(a1) )
  {
    v9 = -1073741738;
    v10 = 1000;
    goto LABEL_33;
  }
  if ( *(_QWORD *)(a1 + 520) )
  {
    v9 = -1073741791;
    v10 = 2000;
    goto LABEL_33;
  }
  if ( (*(_BYTE *)(a1 + 564) & 1) != 0 )
  {
    v9 = -1073741791;
    v10 = 3000;
    goto LABEL_33;
  }
  v8 = *((_QWORD *)&v41[0] + 1) == 0;
  v11 = 0;
  if ( (_DWORD)v2 )
  {
    while ( !(_BYTE)v8 )
    {
      v12 = *(_QWORD *)(32LL * v11 + a1 + 632);
      if ( !*(_DWORD *)(v12 + 148) )
        v8 = *(_DWORD *)(v12 + 152) == 0;
      if ( ++v11 >= (unsigned int)v2 )
        goto LABEL_12;
    }
    goto LABEL_13;
  }
LABEL_12:
  if ( !(_BYTE)v8 )
  {
    if ( (unsigned int)v2 <= 1 )
    {
      if ( (_DWORD)v2 == 1 )
      {
        v18 = *(_QWORD *)(a1 + 632);
        LODWORD(v37) = 0;
        v8 = *(_QWORD *)(v18 + 148);
        LOBYTE(v40) = *(_BYTE *)(a1 + 656);
        *(_QWORD *)&v38 = v8;
      }
    }
    else
    {
      Heap = RtlAllocateHeap(BipHeap, 0, 56 * v2);
      v7 = Heap;
      if ( !Heap )
      {
        v10 = 6000;
        v9 = -1073741801;
        goto LABEL_33;
      }
      memset_0(Heap, 0, 56 * v2);
      v14 = 0;
      v15 = 0;
      do
      {
        v16 = 56 * v15;
        ++v14;
        v17 = 32 * v15++;
        *(_DWORD *)&v7[v16] = 0;
        v7[v16 + 48] = *(_BYTE *)(v17 + a1 + 656);
        v8 = *(_QWORD *)(*(_QWORD *)(v17 + a1 + 632) + 148LL);
        *(_QWORD *)&v7[v16 + 16] = v8;
      }
      while ( v14 < (unsigned int)v2 );
      LODWORD(v37) = 1;
      DWORD2(v37) = 0;
      HIDWORD(v37) = v2;
      *(_QWORD *)&v38 = v7;
    }
    v19 = -(__int64)((*(_DWORD *)(a1 + 24) & 0x10) != 0);
    *(_DWORD *)(a1 + 564) |= 1u;
    v20 = (unsigned __int64)&BipWorkItemStopCallback & v19;
    BipLockWatchdogContextDisarmWatchdog((struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)v8);
    LOBYTE(v21) = 1;
    BipSyncReleaseLock(&BipGlobalLock, v21);
    *(_QWORD *)&v35[0] = v41;
    v22 = &v37;
    if ( !(_DWORD)v2 )
      v22 = (__int128 *)*((_QWORD *)&v35[0] + 1);
    *((_QWORD *)&v35[0] + 1) = v22;
    v23 = RtlAllocateHeap(BipHeap, 0, 0x20u);
    v6 = v23;
    if ( v23 )
    {
      *v23 = 0;
      v23[1] = 0;
      v23[2] = 0;
      v23[3] = a1;
      v9 = EaCreateAggregation(
             v35,
             &BipWorkItemStartCallback,
             v20,
             &BipWorkItemCleanupCallback,
             BipWorkItemLatchCallback,
             v23,
             0,
             &v31);
      if ( v9 >= 0 )
      {
        BipAcquireGlobalLock(v24);
        v10 = 0;
        v6[2] = v31;
        *(_QWORD *)(a1 + 520) = v6;
        v6 = 0;
        v31 = 0;
        *(_DWORD *)(a1 + 536) = 0;
        goto LABEL_32;
      }
      v10 = 8000;
    }
    else
    {
      v9 = -1073741801;
      v10 = 7000;
    }
    BipAcquireGlobalLock(v24);
LABEL_32:
    *(_DWORD *)(a1 + 564) &= ~1u;
    goto LABEL_33;
  }
LABEL_13:
  if ( (a2 & 1) != 0 )
  {
    v10 = 5000;
    v9 = 259;
  }
  else
  {
    v10 = 4000;
    v9 = -1073741823;
  }
LABEL_33:
  BipLockWatchdogContextDisarmWatchdog((struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)v8);
  LOBYTE(v25) = 1;
  BipSyncReleaseLock(&BipGlobalLock, v25);
  RtlWakeAddressAll(a1 + 564);
  if ( v7 )
    RtlFreeHeap(BipHeap, 0, v7);
  if ( v6 )
    BipWorkItemEaContextCheckQueueCleanup(a1, v6, 2);
  if ( v31 )
    EaDeleteAggregation();
  if ( v9 < 0 && (unsigned int)dword_1800C3098 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 3, v26) )
  {
    v32 = v10;
    v34 = a1 + 32;
    v33 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      v27,
      (unsigned __int8 *)&word_1800B2DCE,
      v28,
      v29,
      (__int64)&v33,
      &v34,
      (__int64)&v32);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005ace4  push    rbp
0x18005ace6  push    rbx
0x18005ace7  push    rsi
0x18005ace8  push    rdi
0x18005ace9  push    r12
0x18005aceb  push    r13
0x18005aced  push    r14
0x18005acef  push    r15
0x18005acf1  lea     rbp, [rsp-8]
0x18005acf6  sub     rsp, 108h
0x18005acfd  mov     rax, cs:__security_cookie
0x18005ad04  xor     rax, rsp
0x18005ad07  mov     [rbp+40h+var_50], rax
0x18005ad0b  mov     ebx, [rcx+270h]
0x18005ad11  xorps   xmm0, xmm0
0x18005ad14  xor     eax, eax
0x18005ad16  xorps   xmm1, xmm1
0x18005ad19  mov     [rbp+40h+var_80], rax
0x18005ad1d  xor     r12d, r12d
0x18005ad20  mov     [rbp+40h+var_B8], rax
0x18005ad24  mov     rdi, rcx
0x18005ad27  mov     [rbp+40h+var_58], rax
0x18005ad2b  mov     esi, edx
0x18005ad2d  mov     rax, [rcx+48h]
0x18005ad31  mov     r14d, r12d
0x18005ad34  movups  [rbp+40h+var_78], xmm0
0x18005ad38  mov     [rsp+140h+var_100], r12
0x18005ad3d  mov     r15d, r12d
0x18005ad40  movups  [rbp+40h+var_B0], xmm0
0x18005ad44  movups  [rbp+40h+var_A0], xmm0
0x18005ad48  movups  [rbp+40h+var_90], xmm0
0x18005ad4c  movups  [rsp+140h+var_E8], xmm1
0x18005ad51  movups  [rsp+140h+var_D8], xmm1
0x18005ad56  movups  [rsp+140h+var_C8], xmm1
0x18005ad5b  movups  [rbp+40h+var_68], xmm0
0x18005ad5f  mov     rcx, [rax+94h]
0x18005ad66  mov     qword ptr [rbp+40h+var_78+8], rcx
0x18005ad6a  call    BipAcquireGlobalLock
0x18005ad6f  mov     rcx, rdi
0x18005ad72  call    BipIsWorkItemActivatable
0x18005ad77  lea     r13d, [r12+1]
0x18005ad7c  test    al, al
0x18005ad7e  jnz     short loc_18005AD8F
0x18005ad80  mov     ebx, 0C0000056h
0x18005ad85  mov     esi, 3E8h
0x18005ad8a  jmp     loc_18005AFDF
0x18005ad8f  cmp     [rdi+208h], r12
0x18005ad96  jz      short loc_18005ADA7
0x18005ad98  mov     ebx, 0C0000021h
0x18005ad9d  mov     esi, 7D0h
0x18005ada2  jmp     loc_18005AFDF
0x18005ada7  test    [rdi+234h], r13b
0x18005adae  jz      short loc_18005ADBF
0x18005adb0  mov     ebx, 0C0000021h
0x18005adb5  mov     esi, 0BB8h
0x18005adba  jmp     loc_18005AFDF
0x18005adbf  movzx   ecx, r12b
0x18005adc3  cmp     dword ptr [rbp+40h+var_78+8], r12d
0x18005adc7  jnz     short loc_18005ADD1
0x18005adc9  cmp     dword ptr [rbp+40h+var_78+0Ch], r12d
0x18005adcd  cmovz   ecx, r13d
0x18005add1  mov     edx, r12d
0x18005add4  test    ebx, ebx
0x18005add6  jz      short loc_18005AE08
0x18005add8  test    cl, cl
0x18005adda  jnz     short loc_18005AE0C
0x18005addc  mov     eax, edx
0x18005adde  shl     rax, 5
0x18005ade2  mov     r8, [rax+rdi+278h]
0x18005adea  cmp     [r8+94h], r12d
0x18005adf1  jnz     short loc_18005AE01
0x18005adf3  cmp     [r8+98h], r12d
0x18005adfa  movzx   ecx, cl
0x18005adfd  cmovz   ecx, r13d
0x18005ae01  add     edx, r13d
0x18005ae04  cmp     edx, ebx
0x18005ae06  jb      short loc_18005ADD8
0x18005ae08  test    cl, cl
0x18005ae0a  jz      short loc_18005AE2F
0x18005ae0c  test    r13b, sil
0x18005ae0f  jnz     short loc_18005AE20
0x18005ae11  mov     esi, 0FA0h
0x18005ae16  mov     ebx, 0C0000001h
0x18005ae1b  jmp     loc_18005AFDF
0x18005ae20  mov     esi, 1388h
0x18005ae25  mov     ebx, 103h
0x18005ae2a  jmp     loc_18005AFDF
0x18005ae2f  cmp     ebx, r13d
0x18005ae32  jbe     loc_18005AEC3
0x18005ae38  mov     rcx, cs:BipHeap; HeapHandle
0x18005ae3f  xor     edx, edx; Flags
0x18005ae41  imul    rsi, rbx, 38h ; '8'
0x18005ae45  mov     r8, rsi; Size
0x18005ae48  call    cs:__imp_RtlAllocateHeap
0x18005ae4e  mov     r15, rax
0x18005ae51  test    rax, rax
0x18005ae54  jnz     short loc_18005AE65
0x18005ae56  mov     esi, 1770h
0x18005ae5b  mov     ebx, 0C0000017h
0x18005ae60  jmp     loc_18005AFDF
0x18005ae65  mov     r8, rsi; Size
0x18005ae68  xor     edx, edx; Val
0x18005ae6a  mov     rcx, r15; void *
0x18005ae6d  call    memset_0
0x18005ae72  mov     r9d, r12d
0x18005ae75  mov     r8, r12
0x18005ae78  imul    rdx, r8, 38h ; '8'
0x18005ae7c  mov     rcx, r8
0x18005ae7f  add     r9d, r13d
0x18005ae82  shl     rcx, 5
0x18005ae86  add     r8, r13
0x18005ae89  mov     [rdx+r15], r12d
0x18005ae8d  mov     al, [rcx+rdi+290h]
0x18005ae94  mov     [rdx+r15+30h], al
0x18005ae99  mov     rax, [rcx+rdi+278h]
0x18005aea1  mov     rcx, [rax+94h]
0x18005aea8  mov     [rdx+r15+10h], rcx
0x18005aead  cmp     r9d, ebx
0x18005aeb0  jb      short loc_18005AE78
0x18005aeb2  mov     dword ptr [rbp+40h+var_B0], r13d
0x18005aeb6  mov     dword ptr [rbp+40h+var_B0+8], r12d
0x18005aeba  mov     dword ptr [rbp+40h+var_B0+0Ch], ebx
0x18005aebd  mov     qword ptr [rbp+40h+var_A0], r15
0x18005aec1  jmp     short loc_18005AEE4
0x18005aec3  jnz     short loc_18005AEE4
0x18005aec5  mov     rax, [rdi+278h]
0x18005aecc  mov     dword ptr [rbp+40h+var_B0], r12d
0x18005aed0  mov     rcx, [rax+94h]; struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *
0x18005aed7  mov     al, [rdi+290h]
0x18005aedd  mov     byte ptr [rbp+40h+var_80], al
0x18005aee0  mov     qword ptr [rbp+40h+var_A0], rcx
0x18005aee4  mov     eax, [rdi+18h]
0x18005aee7  and     al, 10h
0x18005aee9  neg     al
0x18005aeeb  lea     rax, ?BipWorkItemStopCallback@@YAXPEAXU_CBROKERED_EVENT_ID@@0K@Z; BipWorkItemStopCallback(void *,_CBROKERED_EVENT_ID,void *,ulong)
0x18005aef2  sbb     rsi, rsi
0x18005aef5  or      [rdi+234h], r13d
0x18005aefc  and     rsi, rax
0x18005aeff  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x18005af04  mov     dl, r13b
0x18005af07  lea     rcx, BipGlobalLock
0x18005af0e  call    BipSyncReleaseLock
0x18005af13  mov     rcx, cs:BipHeap; HeapHandle
0x18005af1a  lea     rax, [rbp+40h+var_78]
0x18005af1e  mov     qword ptr [rsp+140h+var_E8], rax
0x18005af23  test    ebx, ebx
0x18005af25  lea     rax, [rbp+40h+var_B0]
0x18005af29  cmovz   rax, qword ptr [rsp+140h+var_E8+8]
0x18005af2f  xor     edx, edx; Flags
0x18005af31  mov     qword ptr [rsp+140h+var_E8+8], rax
0x18005af36  lea     r8d, [rdx+20h]; Size
0x18005af3a  call    cs:__imp_RtlAllocateHeap
0x18005af40  mov     r14, rax
0x18005af43  test    rax, rax
0x18005af46  jnz     short loc_18005AF54
0x18005af48  mov     ebx, 0C0000017h
0x18005af4d  mov     esi, 1B58h
0x18005af52  jmp     short loc_18005AFAA
0x18005af54  mov     [rax], r12
0x18005af57  lea     r9, ?BipWorkItemCleanupCallback@@YAXPEAXU_CBROKERED_EVENT_ID@@0K@Z; BipWorkItemCleanupCallback(void *,_CBROKERED_EVENT_ID,void *,ulong)
0x18005af5e  mov     [rax+8], r12
0x18005af62  lea     rdx, ?BipWorkItemStartCallback@@YAXPEAXU_CBROKERED_EVENT_ID@@00KKPEAW4_BI_ACTIVATION_STATUS@@@Z; BipWorkItemStartCallback(void *,_CBROKERED_EVENT_ID,void *,void *,ulong,ulong,_BI_ACTIVATION_STATUS *)
0x18005af69  mov     [rax+10h], r12
0x18005af6d  lea     rcx, [rsp+140h+var_E8]
0x18005af72  mov     [rax+18h], rdi
0x18005af76  mov     r8, rsi
0x18005af79  lea     rax, [rsp+140h+var_100]
0x18005af7e  mov     [rsp+140h+var_108], rax
0x18005af83  lea     rax, ?BipWorkItemLatchCallback@@YAXPEAX00KK@Z; BipWorkItemLatchCallback(void *,void *,void *,ulong,ulong)
0x18005af8a  mov     dword ptr [rsp+140h+var_110], r12d
0x18005af8f  mov     [rsp+140h+var_118], r14
0x18005af94  mov     [rsp+140h+var_120], rax
0x18005af99  call    cs:__imp_EaCreateAggregation
0x18005af9f  mov     ebx, eax
0x18005afa1  test    eax, eax
0x18005afa3  jns     short loc_18005AFB1
0x18005afa5  mov     esi, 1F40h
0x18005afaa  call    BipAcquireGlobalLock
0x18005afaf  jmp     short loc_18005AFD8
0x18005afb1  call    BipAcquireGlobalLock
0x18005afb6  mov     rax, [rsp+140h+var_100]
0x18005afbb  mov     esi, r12d
0x18005afbe  mov     [r14+10h], rax
0x18005afc2  mov     [rdi+208h], r14
0x18005afc9  mov     r14, r12
0x18005afcc  mov     [rsp+140h+var_100], r12
0x18005afd1  mov     [rdi+218h], r12d
0x18005afd8  and     dword ptr [rdi+234h], 0FFFFFFFEh
0x18005afdf  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x18005afe4  mov     dl, r13b
0x18005afe7  lea     rcx, BipGlobalLock
0x18005afee  call    BipSyncReleaseLock
0x18005aff3  lea     rcx, [rdi+234h]
0x18005affa  call    cs:__imp_RtlWakeAddressAll
0x18005b000  test    r15, r15
0x18005b003  jz      short loc_18005B017
0x18005b005  mov     rcx, cs:BipHeap; HeapHandle
0x18005b00c  mov     r8, r15; P
0x18005b00f  xor     edx, edx; Flags
0x18005b011  call    cs:__imp_RtlFreeHeap
0x18005b017  test    r14, r14
0x18005b01a  jz      short loc_18005B02D
0x18005b01c  mov     r8d, 2
0x18005b022  mov     rdx, r14
0x18005b025  mov     rcx, rdi
0x18005b028  call    BipWorkItemEaContextCheckQueueCleanup
0x18005b02d  mov     rcx, [rsp+140h+var_100]
0x18005b032  test    rcx, rcx
0x18005b035  jz      short loc_18005B03D
0x18005b037  call    cs:__imp_EaDeleteAggregation
0x18005b03d  test    ebx, ebx
0x18005b03f  jns     short loc_18005B09C
0x18005b041  mov     eax, cs:dword_1800C3098
0x18005b047  cmp     eax, 2
0x18005b04a  jbe     short loc_18005B09C
0x18005b04c  mov     edx, 3
0x18005b051  lea     rcx, dword_1800C3098
0x18005b058  call    _tlgKeywordOn
0x18005b05d  test    al, al
0x18005b05f  jz      short loc_18005B09C
0x18005b061  lea     rax, [rdi+20h]
0x18005b065  mov     [rsp+140h+var_F8], esi
0x18005b069  mov     [rsp+140h+var_F0], rax
0x18005b06e  lea     rdx, word_1800B2DCE
0x18005b075  lea     rax, [rsp+140h+var_F8]
0x18005b07a  mov     [rsp+140h+var_F4], ebx
0x18005b07e  mov     [rsp+140h+var_110], rax
0x18005b083  lea     rax, [rsp+140h+var_F0]
0x18005b088  mov     [rsp+140h+var_118], rax
0x18005b08d  lea     rax, [rsp+140h+var_F4]
0x18005b092  mov     [rsp+140h+var_120], rax
0x18005b097  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18005b09c  mov     eax, ebx
0x18005b09e  mov     rcx, [rbp+40h+var_50]
0x18005b0a2  xor     rcx, rsp; StackCookie
0x18005b0a5  call    __security_check_cookie
0x18005b0aa  add     rsp, 108h
0x18005b0b1  pop     r15
0x18005b0b3  pop     r14
0x18005b0b5  pop     r13
0x18005b0b7  pop     r12
0x18005b0b9  pop     rdi
0x18005b0ba  pop     rsi
0x18005b0bb  pop     rbx
0x18005b0bc  pop     rbp
0x18005b0bd  retn
```
