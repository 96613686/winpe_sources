# MpFgSendNotification

- ea: `0x140070748`
- end: `0x140070c9a`
- name: `MpFgSendNotification`
- size: `1362`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003c7b0`
- `0x1400704f8`

## callees

- `0x1400026c0`
- `0x1400027d0`
- `0x1400034e0`
- `0x140003d20`
- `0x1400051bc`
- `0x1400118d0`
- `0x140011bc0`
- `0x140038710`
- `0x140056c20`
- `0x140066180`
- `0x140070748`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x140070b95`
- `ntoskrnl!KeSetTimer` at `0x140070b95`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140070a01`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140070a01`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140070a2e`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140070a2e`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x140070a6f`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x140070b3f`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x140070a6f`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x140070b3f`
- `ntoskrnl!KeReadStateTimer` at `0x140070b6c`
- `ntoskrnl!KeReadStateTimer` at `0x140070b6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070c3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070c3f`
- `ntoskrnl!ExAcquireFastMutex` at `0x140070955`
- `ntoskrnl!ExAcquireFastMutex` at `0x140070955`
- `ntoskrnl!ExReleaseFastMutex` at `0x140070c24`
- `ntoskrnl!ExReleaseFastMutex` at `0x14008ced6`
- `ntoskrnl!ExReleaseFastMutex` at `0x140070c24`
- `ntoskrnl!ExReleaseFastMutex` at `0x14008ced6`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140070aec`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140070aec`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140070c62`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140070c62`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x140070a83`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x140070a83`

## pseudocode

```c
__int64 __fastcall MpFgSendNotification(__int64 a1, const UNICODE_STRING *a2, char a3)
{
  struct _FLT_GENERIC_WORKITEM *v6; // r14
  __int64 v7; // rdx
  __int64 v8; // rcx
  int SessionId; // ecx
  NTSTATUS v10; // ebx
  __int64 v11; // rdx
  const UNICODE_STRING *v12; // rcx
  int v13; // ecx
  PRTL_AVL_TABLE *v14; // rcx
  struct _RTL_AVL_TABLE *v15; // rcx
  __int64 v16; // rdx
  ULONG v17; // ebx
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // rax
  int TableContext; // [rsp+20h] [rbp-A8h]
  int TableContexta; // [rsp+20h] [rbp-A8h]
  _QWORD Buffer[10]; // [rsp+40h] [rbp-88h] BYREF
  unsigned __int8 NewElement[8]; // [rsp+90h] [rbp-38h] BYREF

  memset(Buffer, 0, sizeof(Buffer));
  NewElement[0] = 1;
  v6 = 0;
  LODWORD(Buffer[0]) = 5298716;
  LOBYTE(Buffer[7]) = (*(_DWORD *)(a1 + 56) & 0x40000) != 0;
  Buffer[1] = *(_QWORD *)(a1 + 24);
  Buffer[2] = *(_QWORD *)(a1 + 32);
  *(_OWORD *)((char *)&Buffer[7] + 4) = *(_OWORD *)(a1 + 168);
  BYTE1(Buffer[7]) = a3;
  SessionId = MpQuerySessionId(v8, v7, &Buffer[4]);
  if ( SessionId < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      25,
      WPP_d4b33eac157739e0890aa4122bf243af_Traceguids,
      KeGetCurrentThread(),
      SessionId);
  }
  Buffer[6] = MpAllocatePoolWithTag(1, a2->MaximumLength, 1732661325);
  if ( !Buffer[6] )
  {
    v10 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v11 = 26;
      TableContext = -1073741670;
LABEL_9:
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        v11,
        WPP_d4b33eac157739e0890aa4122bf243af_Traceguids,
        KeGetCurrentThread(),
        TableContext);
      goto LABEL_53;
    }
    goto LABEL_53;
  }
  LOWORD(Buffer[5]) = 0;
  WORD1(Buffer[5]) = a2->MaximumLength;
  v10 = RtlUnicodeStringCopy((PUNICODE_STRING)&Buffer[5], a2);
  if ( v10 >= 0 )
  {
    v12 = *(const UNICODE_STRING **)(a1 + 128);
    if ( v12 )
    {
      v13 = MpDuplicateString(v12);
      if ( v13 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          28,
          WPP_d4b33eac157739e0890aa4122bf243af_Traceguids,
          KeGetCurrentThread(),
          v13);
      }
    }
    ExAcquireFastMutex((PFAST_MUTEX)((char *)DeferredContext + 272));
    v14 = (PRTL_AVL_TABLE *)DeferredContext;
    if ( !*((_QWORD *)DeferredContext + 33) )
    {
      v15 = (struct _RTL_AVL_TABLE *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)DeferredContext + 3);
      *((_QWORD *)DeferredContext + 33) = v15;
      if ( !v15 )
      {
        v10 = -1073741670;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_52;
        v16 = 29;
        goto LABEL_24;
      }
      RtlInitializeGenericTableAvl(
        v15,
        (PRTL_AVL_COMPARE_ROUTINE)MpFgAuditTableCompareRoutine,
        MpFgAvlAllocateRoutine,
        MpFgAvlFreeRoutine,
        0);
      v14 = (PRTL_AVL_TABLE *)DeferredContext;
    }
    if ( RtlInsertElementGenericTableAvl(v14[33], Buffer, 0x50u, NewElement) )
    {
      if ( NewElement[0] )
      {
        Buffer[6] = 0;
        Buffer[3] = 0;
        v17 = *((_DWORD *)DeferredContext + 63);
        if ( RtlNumberGenericTableElementsAvl(*((PRTL_AVL_TABLE *)DeferredContext + 33)) < v17 )
        {
          if ( RtlNumberGenericTableElementsAvl(*((PRTL_AVL_TABLE *)DeferredContext + 33)) == 1
            && (!*((_BYTE *)DeferredContext + 248) || KeReadStateTimer((PKTIMER)((char *)DeferredContext + 120))) )
          {
            KeSetTimer(
              (PKTIMER)((char *)DeferredContext + 120),
              *(LARGE_INTEGER *)((char *)DeferredContext + 256),
              (PKDPC)((char *)DeferredContext + 184));
            *((_BYTE *)DeferredContext + 248) = 1;
          }
        }
        else
        {
          GenericWorkItem = FltAllocateGenericWorkItem();
          v6 = GenericWorkItem;
          if ( !GenericWorkItem )
          {
            v10 = -1073741670;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              goto LABEL_52;
            }
            v16 = 32;
            goto LABEL_24;
          }
          v10 = FltQueueGenericWorkItem(
                  GenericWorkItem,
                  *(PVOID *)(MpData + 16),
                  (PFLT_GENERIC_WORKITEM_ROUTINE)FgSendEventsWorker,
                  DelayedWorkQueue,
                  DeferredContext);
          if ( v10 < 0 )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              goto LABEL_52;
            }
            _mm_lfence();
            v16 = 33;
            TableContexta = v10;
            goto LABEL_25;
          }
        }
        v6 = 0;
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          31,
          WPP_d4b33eac157739e0890aa4122bf243af_Traceguids,
          KeGetCurrentThread());
      }
      v10 = 0;
      goto LABEL_52;
    }
    v10 = -1073741670;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_52;
    v16 = 30;
LABEL_24:
    TableContexta = -1073741670;
LABEL_25:
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v16,
      WPP_d4b33eac157739e0890aa4122bf243af_Traceguids,
      KeGetCurrentThread(),
      TableContexta);
LABEL_52:
    ExReleaseFastMutex((PFAST_MUTEX)((char *)DeferredContext + 272));
    goto LABEL_53;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    _mm_lfence();
    v11 = 27;
    TableContext = v10;
    goto LABEL_9;
  }
LABEL_53:
  if ( Buffer[6] )
    ExFreePoolWithTag((PVOID)Buffer[6], 0x6746504Du);
  if ( Buffer[3] )
    MpFreeString(Buffer[3]);
  if ( v6 )
    FltFreeGenericWorkItem(v6);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140070748  mov     [rsp+arg_18], rbx
0x14007074d  push    rdi
0x14007074e  push    r12
0x140070750  push    r13
0x140070752  push    r14
0x140070754  push    r15
0x140070756  sub     rsp, 0A0h
0x14007075d  mov     rax, cs:__security_cookie
0x140070764  xor     rax, rsp
0x140070767  mov     [rsp+0C8h+var_30], rax
0x14007076f  mov     bl, r8b
0x140070772  mov     r15, rdx
0x140070775  mov     r13, rcx
0x140070778  xor     edx, edx; Val
0x14007077a  lea     r8d, [rdx+50h]; Size
0x14007077e  lea     rcx, [rsp+0C8h+Buffer]; void *
0x140070783  call    memset
0x140070788  mov     [rsp+0C8h+NewElement], 1
0x140070790  xor     r12d, r12d
0x140070793  mov     r14d, r12d
0x140070796  mov     [rsp+0C8h+Buffer], 50DA1Ch
0x14007079e  mov     eax, [r13+38h]
0x1400707a2  shr     eax, 12h
0x1400707a5  and     al, 1
0x1400707a7  mov     [rsp+0C8h+var_50], al
0x1400707ab  mov     rax, [r13+18h]
0x1400707af  mov     [rsp+0C8h+var_80], rax
0x1400707b4  mov     rax, [r13+20h]
0x1400707b8  mov     [rsp+0C8h+var_78], rax
0x1400707bd  movups  xmm0, xmmword ptr [r13+0A8h]
0x1400707c5  movdqu  [rsp+0C8h+var_4C], xmm0
0x1400707cb  mov     [rsp+0C8h+var_4F], bl
0x1400707cf  lea     r8, [rsp+0C8h+var_68]
0x1400707d4  call    MpQuerySessionId
0x1400707d9  mov     ecx, eax
0x1400707db  test    eax, eax
0x1400707dd  jns     short loc_140070827
0x1400707df  lea     rdi, WPP_GLOBAL_Control
0x1400707e6  mov     rax, cs:WPP_GLOBAL_Control
0x1400707ed  cmp     rax, rdi
0x1400707f0  jz      short loc_14007082E
0x1400707f2  mov     eax, [rax+2Ch]
0x1400707f5  test    al, 1
0x1400707f7  jz      short loc_14007082E
0x1400707f9  lfence
0x1400707fc  mov     r9, gs:188h
0x140070805  lea     edx, [r12+19h]
0x14007080a  mov     [rsp+0C8h+TableContext], ecx
0x14007080e  lea     r8, WPP_d4b33eac157739e0890aa4122bf243af_Traceguids
0x140070815  mov     rcx, cs:WPP_GLOBAL_Control
0x14007081c  mov     rcx, [rcx+18h]
0x140070820  call    WPP_SF_qD
0x140070825  jmp     short loc_14007082E
0x140070827  lea     rdi, WPP_GLOBAL_Control
0x14007082e  movzx   edx, word ptr [r15+2]
0x140070833  mov     ecx, 1
0x140070838  mov     r8d, 6746504Dh
0x14007083e  call    MpAllocatePoolWithTag
0x140070843  mov     [rsp+0C8h+DestinationString.Buffer], rax
0x140070848  test    rax, rax
0x14007084b  jnz     short loc_14007089F
0x14007084d  mov     ebx, 0C000009Ah
0x140070852  mov     rax, cs:WPP_GLOBAL_Control
0x140070859  cmp     rax, rdi
0x14007085c  jz      loc_140070C30
0x140070862  mov     eax, [rax+2Ch]
0x140070865  test    al, 1
0x140070867  jz      loc_140070C30
0x14007086d  mov     edx, 1Ah
0x140070872  mov     [rsp+0C8h+TableContext], 0C000009Ah
0x14007087a  mov     r9, gs:188h
0x140070883  lea     r8, WPP_d4b33eac157739e0890aa4122bf243af_Traceguids
0x14007088a  mov     rcx, cs:WPP_GLOBAL_Control
0x140070891  mov     rcx, [rcx+18h]
0x140070895  call    WPP_SF_qD
0x14007089a  jmp     loc_140070C30
0x14007089f  mov     [rsp+0C8h+DestinationString.Length], r12w
0x1400708a5  movzx   eax, word ptr [r15+2]
0x1400708aa  mov     [rsp+0C8h+DestinationString.MaximumLength], ax
0x1400708af  mov     rdx, r15; SourceString
0x1400708b2  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x1400708b7  call    RtlUnicodeStringCopy
0x1400708bc  mov     ebx, eax
0x1400708be  test    eax, eax
0x1400708c0  jns     short loc_1400708EB
0x1400708c2  mov     rax, cs:WPP_GLOBAL_Control
0x1400708c9  cmp     rax, rdi
0x1400708cc  jz      loc_140070C30
0x1400708d2  mov     eax, [rax+2Ch]
0x1400708d5  test    al, 1
0x1400708d7  jz      loc_140070C30
0x1400708dd  lfence
0x1400708e0  mov     edx, 1Bh
0x1400708e5  mov     [rsp+0C8h+TableContext], ebx
0x1400708e9  jmp     short loc_14007087A
0x1400708eb  mov     rcx, [r13+80h]; SourceString
0x1400708f2  test    rcx, rcx
0x1400708f5  jz      short loc_140070947
0x1400708f7  lea     rdx, [rsp+0C8h+var_70]
0x1400708fc  call    MpDuplicateString
0x140070901  mov     ecx, eax
0x140070903  test    eax, eax
0x140070905  jns     short loc_140070947
0x140070907  mov     rax, cs:WPP_GLOBAL_Control
0x14007090e  cmp     rax, rdi
0x140070911  jz      short loc_140070947
0x140070913  mov     eax, [rax+2Ch]
0x140070916  test    al, 1
0x140070918  jz      short loc_140070947
0x14007091a  lfence
0x14007091d  mov     r9, gs:188h
0x140070926  mov     edx, 1Ch
0x14007092b  mov     [rsp+0C8h+TableContext], ecx
0x14007092f  lea     r8, WPP_d4b33eac157739e0890aa4122bf243af_Traceguids
0x140070936  mov     rcx, cs:WPP_GLOBAL_Control
0x14007093d  mov     rcx, [rcx+18h]
0x140070941  call    WPP_SF_qD
0x140070946  nop
0x140070947  mov     rcx, cs:DeferredContext
0x14007094e  add     rcx, 110h; FastMutex
0x140070955  call    cs:__imp_ExAcquireFastMutex
0x14007095c  nop     dword ptr [rax+rax+00h]
0x140070961  mov     rcx, cs:DeferredContext
0x140070968  cmp     [rcx+108h], r12
0x14007096f  jnz     loc_140070A14
0x140070975  add     rcx, 180h; Lookaside
0x14007097c  call    ExAllocateFromPagedLookasideList
0x140070981  mov     rcx, rax; Table
0x140070984  mov     rax, cs:DeferredContext
0x14007098b  mov     [rax+108h], rcx
0x140070992  test    rcx, rcx
0x140070995  jnz     short loc_1400709E7
0x140070997  mov     ebx, 0C000009Ah
0x14007099c  mov     rax, cs:WPP_GLOBAL_Control
0x1400709a3  cmp     rax, rdi
0x1400709a6  jz      loc_140070C16
0x1400709ac  mov     eax, [rax+2Ch]
0x1400709af  test    al, 1
0x1400709b1  jz      loc_140070C16
0x1400709b7  lea     edx, [rcx+1Dh]
0x1400709ba  mov     [rsp+0C8h+TableContext], 0C000009Ah
0x1400709c2  mov     r9, gs:188h
0x1400709cb  lea     r8, WPP_d4b33eac157739e0890aa4122bf243af_Traceguids
0x1400709d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400709d9  mov     rcx, [rcx+18h]
0x1400709dd  call    WPP_SF_qD
0x1400709e2  jmp     loc_140070C16
0x1400709e7  mov     qword ptr [rsp+0C8h+TableContext], r12; TableContext
0x1400709ec  lea     r9, MpFgAvlFreeRoutine; FreeRoutine
0x1400709f3  lea     r8, MpFgAvlAllocateRoutine; AllocateRoutine
0x1400709fa  lea     rdx, MpFgAuditTableCompareRoutine; CompareRoutine
0x140070a01  call    cs:__imp_RtlInitializeGenericTableAvl
0x140070a08  nop     dword ptr [rax+rax+00h]
0x140070a0d  mov     rcx, cs:DeferredContext
0x140070a14  lea     r9, [rsp+0C8h+NewElement]; NewElement
0x140070a1c  mov     r8d, 50h ; 'P'; BufferSize
0x140070a22  lea     rdx, [rsp+0C8h+Buffer]; Buffer
0x140070a27  mov     rcx, [rcx+108h]; Table
0x140070a2e  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140070a35  nop     dword ptr [rax+rax+00h]
0x140070a3a  test    rax, rax
0x140070a3d  jz      loc_140070BB9
0x140070a43  cmp     [rsp+0C8h+NewElement], r12b
0x140070a4b  jz      loc_140070BB4
0x140070a51  mov     [rsp+0C8h+DestinationString.Buffer], r12
0x140070a56  mov     [rsp+0C8h+var_70], r12
0x140070a5b  mov     rcx, cs:DeferredContext
0x140070a62  mov     ebx, [rcx+0FCh]
0x140070a68  mov     rcx, [rcx+108h]; Table
0x140070a6f  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x140070a76  nop     dword ptr [rax+rax+00h]
0x140070a7b  cmp     eax, ebx
0x140070a7d  jb      loc_140070B31
0x140070a83  call    cs:__imp_FltAllocateGenericWorkItem
0x140070a8a  nop     dword ptr [rax+rax+00h]
0x140070a8f  mov     r14, rax
0x140070a92  mov     [rsp+0C8h+var_98], rax
0x140070a97  test    rax, rax
0x140070a9a  jnz     short loc_140070AC5
0x140070a9c  mov     ebx, 0C000009Ah
0x140070aa1  mov     rcx, cs:WPP_GLOBAL_Control
0x140070aa8  cmp     rcx, rdi
0x140070aab  jz      loc_140070C16
0x140070ab1  mov     ecx, [rcx+2Ch]
0x140070ab4  test    cl, 1
0x140070ab7  jz      loc_140070C16
0x140070abd  lea     edx, [rax+20h]
0x140070ac0  jmp     loc_1400709BA
0x140070ac5  mov     rax, cs:DeferredContext
0x140070acc  mov     qword ptr [rsp+0C8h+TableContext], rax; Context
0x140070ad1  mov     r9d, 1; QueueType
0x140070ad7  lea     r8, FgSendEventsWorker; WorkerRoutine
0x140070ade  mov     rdx, cs:MpData
0x140070ae5  mov     rdx, [rdx+10h]; FltObject
0x140070ae9  mov     rcx, r14; FltWorkItem
0x140070aec  call    cs:__imp_FltQueueGenericWorkItem
0x140070af3  nop     dword ptr [rax+rax+00h]
0x140070af8  mov     ebx, eax
0x140070afa  test    eax, eax
0x140070afc  jns     short loc_140070B2A
0x140070afe  mov     rax, cs:WPP_GLOBAL_Control
0x140070b05  cmp     rax, rdi
0x140070b08  jz      loc_140070C16
0x140070b0e  mov     eax, [rax+2Ch]
0x140070b11  test    al, 1
0x140070b13  jz      loc_140070C16
0x140070b19  lfence
0x140070b1c  mov     edx, 21h ; '!'
0x140070b21  mov     [rsp+0C8h+TableContext], ebx
0x140070b25  jmp     loc_1400709C2
0x140070b2a  mov     [rsp+0C8h+var_98], r12
0x140070b2f  jmp     short loc_140070BAF
0x140070b31  mov     rcx, cs:DeferredContext
0x140070b38  mov     rcx, [rcx+108h]; Table
0x140070b3f  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x140070b46  nop     dword ptr [rax+rax+00h]
0x140070b4b  cmp     eax, 1
0x140070b4e  jnz     short loc_140070BAF
0x140070b50  mov     rax, cs:DeferredContext
0x140070b57  mov     cl, [rax+0F8h]
0x140070b5d  test    cl, cl
0x140070b5f  jz      short loc_140070B7C
0x140070b61  mov     rcx, cs:DeferredContext
0x140070b68  add     rcx, 78h ; 'x'; Timer
0x140070b6c  call    cs:__imp_KeReadStateTimer
0x140070b73  nop     dword ptr [rax+rax+00h]
0x140070b78  test    al, al
0x140070b7a  jz      short loc_140070BAF
0x140070b7c  mov     rdx, cs:DeferredContext
0x140070b83  lea     r8, [rdx+0B8h]; Dpc
0x140070b8a  lea     rcx, [rdx+78h]; Timer
0x140070b8e  mov     rdx, [rdx+100h]; DueTime
0x140070b95  call    cs:__imp_KeSetTimer
0x140070b9c  nop     dword ptr [rax+rax+00h]
0x140070ba1  mov     rax, cs:DeferredContext
0x140070ba8  mov     byte ptr [rax+0F8h], 1
0x140070baf  mov     r14, r12
0x140070bb2  jmp     short loc_140070C13
0x140070bb4  test    rax, rax
0x140070bb7  jnz     short loc_140070BDB
0x140070bb9  mov     ebx, 0C000009Ah
0x140070bbe  mov     rax, cs:WPP_GLOBAL_Control
0x140070bc5  cmp     rax, rdi
0x140070bc8  jz      short loc_140070C16
0x140070bca  mov     eax, [rax+2Ch]
0x140070bcd  test    al, 1
0x140070bcf  jz      short loc_140070C16
0x140070bd1  mov     edx, 1Eh
0x140070bd6  jmp     loc_1400709BA
0x140070bdb  mov     rax, cs:WPP_GLOBAL_Control
0x140070be2  cmp     rax, rdi
0x140070be5  jz      short loc_140070C13
0x140070be7  mov     eax, [rax+2Ch]
0x140070bea  test    al, 4
0x140070bec  jz      short loc_140070C13
0x140070bee  mov     r9, gs:188h
0x140070bf7  mov     edx, 1Fh
0x140070bfc  lea     r8, WPP_d4b33eac157739e0890aa4122bf243af_Traceguids
0x140070c03  mov     rcx, cs:WPP_GLOBAL_Control
0x140070c0a  mov     rcx, [rcx+18h]
0x140070c0e  call    WPP_SF_q
0x140070c13  mov     ebx, r12d
0x140070c16  mov     rcx, cs:DeferredContext
0x140070c1d  add     rcx, 110h; FastMutex
0x140070c24  call    cs:__imp_ExReleaseFastMutex
0x140070c2b  nop     dword ptr [rax+rax+00h]
0x140070c30  mov     rcx, [rsp+0C8h+DestinationString.Buffer]; P
0x140070c35  test    rcx, rcx
0x140070c38  jz      short loc_140070C4B
0x140070c3a  mov     edx, 6746504Dh; Tag
0x140070c3f  call    cs:__imp_ExFreePoolWithTag
0x140070c46  nop     dword ptr [rax+rax+00h]
0x140070c4b  mov     rcx, [rsp+0C8h+var_70]
0x140070c50  test    rcx, rcx
0x140070c53  jz      short loc_140070C5A
0x140070c55  call    MpFreeString
0x140070c5a  test    r14, r14
0x140070c5d  jz      short loc_140070C6E
0x140070c5f  mov     rcx, r14; FltWorkItem
0x140070c62  call    cs:__imp_FltFreeGenericWorkItem
0x140070c69  nop     dword ptr [rax+rax+00h]
0x140070c6e  mov     eax, ebx
0x140070c70  mov     rcx, [rsp+0C8h+var_30]
0x140070c78  xor     rcx, rsp; StackCookie
0x140070c7b  call    __security_check_cookie
0x140070c80  mov     rbx, [rsp+0C8h+arg_18]
0x140070c88  add     rsp, 0A0h
0x140070c8f  pop     r15
0x140070c91  pop     r14
0x140070c93  pop     r13
0x140070c95  pop     r12
0x140070c97  pop     rdi
0x140070c98  retn
0x14008cebf  push    rbp
0x14008cec1  sub     rsp, 30h
0x14008cec5  mov     rbp, rdx
0x14008cec8  mov     rcx, cs:DeferredContext
0x14008cecf  add     rcx, 110h; FastMutex
0x14008ced6  call    cs:__imp_ExReleaseFastMutex
0x14008cedd  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
