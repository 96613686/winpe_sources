# AfdTLStartBufferedVcSend

- ea: `0x140011670`
- end: `0x140011be7`
- name: `AfdTLStartBufferedVcSend`
- size: `1399`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID Entry)`
- caller_count: `4`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x140010eb0`
- `0x14001f120`
- `0x14002b8b0`
- `0x1400563d8`

## callees

- `0x140011670`
- `0x140012338`
- `0x140012610`
- `0x140012ee0`
- `0x140013990`
- `0x1400147d0`
- `0x14001c708`
- `0x14001ccdc`
- `0x14001ceb0`
- `0x14001db90`
- `0x1400726a0`
- `0x140072780`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140011bd9`
- `ntoskrnl!IofCallDriver` at `0x140011bd9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140011b3d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140011b3d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400117d2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140011b76`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400117d2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140011b76`
- `ntoskrnl!IoGetCurrentProcess` at `0x140011bb1`
- `ntoskrnl!IoGetCurrentProcess` at `0x140011bb1`
- `ntoskrnl!EtwWrite` at `0x1400119f8`
- `ntoskrnl!EtwWrite` at `0x1400119f8`

## pseudocode

```c
__int64 __fastcall AfdTLStartBufferedVcSend(
        _QWORD *a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        struct _KSPIN_LOCK_QUEUE *Entry)
{
  __int64 v6; // r15
  __int64 v9; // rdx
  __int64 v10; // rcx
  struct _KSPIN_LOCK_QUEUE *v11; // r12
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 result; // rax
  int v15; // esi
  bool v16; // zf
  volatile PKSPIN_LOCK Lock; // r14
  KSPIN_LOCK v18; // rdx
  __int64 v19; // rdi
  volatile PKSPIN_LOCK v20; // rcx
  _WORD *v21; // r9
  KSPIN_LOCK *v22; // rcx
  int v23; // edx
  signed __int64 v24; // rax
  bool v25; // cc
  signed __int64 v26; // rax
  __int64 v27; // rax
  PEPROCESS Next; // rax
  __int64 v29; // rax
  IRP *v30; // r15
  __int64 v31; // r14
  __int64 v32; // rdx
  int UserData; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+50h] [rbp-B0h] BYREF
  int v35; // [rsp+58h] [rbp-A8h] BYREF
  int v36; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+68h] [rbp-98h] BYREF
  int v38; // [rsp+70h] [rbp-90h] BYREF
  PEPROCESS v39; // [rsp+78h] [rbp-88h] BYREF
  struct _KSPIN_LOCK_QUEUE *v40; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v42[12]; // [rsp+90h] [rbp-70h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+F0h] [rbp-10h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+100h] [rbp+0h] BYREF
  GUID ActivityId; // [rsp+118h] [rbp+18h] BYREF
  __int128 v46; // [rsp+128h] [rbp+28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+140h] [rbp+40h] BYREF
  int *v48; // [rsp+150h] [rbp+50h]
  __int64 v49; // [rsp+158h] [rbp+58h]
  PEPROCESS *v50; // [rsp+160h] [rbp+60h]
  __int64 v51; // [rsp+168h] [rbp+68h]
  struct _KSPIN_LOCK_QUEUE **v52; // [rsp+170h] [rbp+70h]
  __int64 v53; // [rsp+178h] [rbp+78h]
  int *v54; // [rsp+180h] [rbp+80h]
  __int64 v55; // [rsp+188h] [rbp+88h]
  __int64 *v56; // [rsp+190h] [rbp+90h]
  __int64 v57; // [rsp+198h] [rbp+98h]
  int *v58; // [rsp+1A0h] [rbp+A0h]
  __int64 v59; // [rsp+1A8h] [rbp+A8h]
  int *v60; // [rsp+1B0h] [rbp+B0h]
  __int64 v61; // [rsp+1B8h] [rbp+B8h]

  v6 = a3;
  memset(v42, 0, 0x58u);
  v11 = (struct _KSPIN_LOCK_QUEUE *)a1[1];
  LockHandle.LockQueue = 0;
  v46 = 0;
  if ( g_AfdEtwTraceEnable || Microsoft_Windows_Networking_CorrelationEnabled )
  {
    LockHandle.LockQueue.Lock = 0;
    LockHandle.LockQueue.Next = v11;
    v46 = (unsigned __int64)Entry;
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
    {
      UserData = 2;
      EtwEx_tidActivityInfo(v10, &ActivityStart, &v46);
    }
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
      EtwEx_tidActivityInfoTransfer(v10, v9, &v46, &LockHandle, UserData);
  }
  if ( g_AfdEtwTraceEnable )
  {
    *(_DWORD *)&EventDescriptor.Id = AFD_EVENT_SEND;
    *(_WORD *)&EventDescriptor.Opcode = -5364;
    HIBYTE(EventDescriptor.Task) = 3;
    v27 = 0;
    if ( v11 )
    {
      LOBYTE(v27) = LOWORD(v11->Next) != 0xAFD1;
      ++v27;
    }
    EventDescriptor.Level = 4;
    EventDescriptor.Keyword = v27 | 0x8000000000000024uLL;
    v38 = 0;
    v37 = v6;
    v41 = a2;
    v36 = 1;
    v40 = v11;
    v35 = 3056;
    v34 = 0;
    v39 = 0;
    *(_QWORD *)ActivityId.Data4 = 0;
    if ( Entry )
      *(_QWORD *)&ActivityId.Data1 = Entry;
    else
      *(_QWORD *)&ActivityId.Data1 = v11;
    if ( v11 )
      Next = (PEPROCESS)v11[3].Next;
    else
      Next = IoGetCurrentProcess();
    v39 = Next;
    *(_QWORD *)&v47.Size = 4;
    v47.Ptr = (ULONGLONG)&v34;
    v49 = 4;
    v48 = &v35;
    v50 = &v39;
    v52 = &v40;
    v54 = &v36;
    v56 = &v41;
    v58 = &v37;
    v60 = &v38;
    v51 = 8;
    v53 = 8;
    v55 = 4;
    v57 = 8;
    v59 = 4;
    v61 = 4;
    EtwWrite(g_AfdEtwHandle, &EventDescriptor, &ActivityId, 8u, &v47);
  }
  v12 = a1[2];
  v42[0] = AfdTLBufferedSendComplete;
  v42[2] = Entry;
  v42[1] = AfdTLBufferedSendCompleteBatch;
  v13 = a1[3];
  LODWORD(v42[3]) = a4 | 4;
  v42[4] = a2;
  v42[6] = v6;
  v42[7] = Entry;
  result = (*(__int64 (__fastcall **)(__int64, _QWORD *))(v13 + 24))(v12, v42);
  v15 = result;
  if ( (_DWORD)result != 259 )
  {
    v16 = g_AfdEtwTraceEnable == 0;
    Lock = Entry[6].Lock;
    v18 = LODWORD(v42[8]);
    LockHandle.LockQueue = 0;
    *((_DWORD *)Lock + 12) = result;
    Lock[7] = v18;
    v19 = (__int64)Entry[3].Next;
    v20 = Entry[3].Lock;
    v21 = *(_WORD **)(v19 + 8);
    if ( !v16 || Microsoft_Windows_Networking_CorrelationEnabled )
    {
      *(_QWORD *)ActivityId.Data4 = 0;
      *(_QWORD *)&ActivityId.Data1 = v21;
      LockHandle.LockQueue.Lock = 0;
      LockHandle.LockQueue.Next = Entry;
    }
    if ( g_AfdEtwTraceEnable )
    {
      *(_DWORD *)&EventDescriptor.Id = AFD_EVENT_SEND;
      *(_WORD *)&EventDescriptor.Opcode = -5364;
      HIBYTE(EventDescriptor.Task) = 3;
      v29 = 0;
      if ( v21 )
      {
        LOBYTE(v29) = *v21 != 0xAFD1;
        ++v29;
      }
      EventDescriptor.Keyword = v29 | 0x8000000000000024uLL;
      EventDescriptor.Level = ((v15 >> 31) & 0xFE) + 4;
      AFDETW_TRACEDATA_CORE(&EventDescriptor, 1, 3024, (__int64)v21, UserData, 1, (char)v20, v18, v15, (__int64)Entry);
      if ( g_AfdEtwTraceEnable )
        goto LABEL_27;
    }
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
    {
LABEL_27:
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
        EtwEx_tidActivityInfo(v20, &ActivityStop, &LockHandle);
    }
    v22 = (KSPIN_LOCK *)(*(_QWORD *)(v19 + 8) + 56LL);
    memset(&LockHandle, 0, sizeof(LockHandle));
    KeAcquireInStackQueuedSpinLock(v22, &LockHandle);
    v23 = *((_DWORD *)Lock + 12);
    *(_DWORD *)(v19 + 120) -= *((_DWORD *)Lock + 14);
    --*(_DWORD *)(v19 + 124);
    if ( v23 < 0 )
    {
      v30 = *(IRP **)(v19 + 128);
      v31 = *(_QWORD *)(v19 + 8);
      if ( v30 )
        *(_QWORD *)(v19 + 128) = 0;
      if ( (unsigned int)(v23 + 1073741300) <= 1 || v23 == -1073741508 )
        *(_DWORD *)(v19 + 4) |= 0x2000u;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      AFDETW_TRACEABORT(2, 8022, v31, 15);
      AfdBeginAbort(v19);
      if ( v30 )
        IofCallDriver(*(PDEVICE_OBJECT *)(v19 + 24), v30);
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v31 + 56), &LockHandle);
      LOBYTE(v32) = 1;
      AfdDeleteConnectedReference(v19, v32);
    }
    AfdCompleteBufferedSendsUnlock(v19, &LockHandle);
    *((_DWORD *)Entry[3].Lock + 10) = Entry[4].Lock;
    AfdReturnBuffer((unsigned __int16 *)Entry, *(PEPROCESS *)(v19 + 32));
    v24 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v19 + 48), 0xFFFFFFFFFFFFFFFFuLL);
    v25 = v24 <= 1;
    v26 = v24 - 1;
    if ( v25 )
    {
      if ( v26 )
        __fastfail(0xEu);
      AfdCloseConnection(v19);
    }
    return (unsigned int)v15;
  }
  return result;
}

```

## disassembly

```asm
0x140011670  push    rbp
0x140011672  push    rbx
0x140011673  push    rsi
0x140011674  push    rdi
0x140011675  push    r12
0x140011677  push    r13
0x140011679  push    r14
0x14001167b  push    r15
0x14001167d  lea     rbp, [rsp-0D8h]
0x140011685  sub     rsp, 1D8h
0x14001168c  mov     rax, cs:__security_cookie
0x140011693  xor     rax, rsp
0x140011696  mov     [rbp+110h+var_50], rax
0x14001169d  mov     rbx, [rbp+110h+Entry]
0x1400116a4  mov     r14, rdx
0x1400116a7  mov     r15d, r8d
0x1400116aa  mov     rdi, rcx
0x1400116ad  xor     edx, edx; Val
0x1400116af  lea     rcx, [rbp+110h+var_180]; void *
0x1400116b3  mov     r8d, 58h ; 'X'; Size
0x1400116b9  mov     esi, r9d
0x1400116bc  call    memset
0x1400116c1  cmp     cs:g_AfdEtwTraceEnable, 0
0x1400116c8  xorps   xmm0, xmm0
0x1400116cb  mov     r12, [rdi+8]
0x1400116cf  xorps   xmm1, xmm1
0x1400116d2  movups  xmmword ptr [rbp+110h+LockHandle.LockQueue.Next], xmm0
0x1400116d6  movups  [rbp+110h+var_E8], xmm1
0x1400116da  jnz     loc_140011853
0x1400116e0  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400116e6  test    eax, eax
0x1400116e8  jnz     loc_140011853
0x1400116ee  cmp     cs:g_AfdEtwTraceEnable, 0
0x1400116f5  mov     ecx, 0AFD1h
0x1400116fa  mov     r13, 8000000000000024h
0x140011704  jnz     loc_1400118A1
0x14001170a  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140011710  mov     rcx, [rdi+10h]
0x140011714  lea     rax, AfdTLBufferedSendComplete
0x14001171b  mov     [rbp+110h+var_180], rax
0x14001171f  lea     rdx, [rbp+110h+var_180]
0x140011723  lea     rax, AfdTLBufferedSendCompleteBatch
0x14001172a  mov     [rbp+110h+var_170], rbx
0x14001172e  mov     [rbp+110h+var_178], rax
0x140011732  or      esi, 4
0x140011735  mov     rax, [rdi+18h]
0x140011739  mov     [rbp+110h+var_168], esi
0x14001173c  mov     [rbp+110h+var_160], r14
0x140011740  mov     [rbp+110h+var_150], r15
0x140011744  mov     [rbp+110h+var_148], rbx
0x140011748  mov     rax, [rax+18h]
0x14001174c  call    _guard_dispatch_icall
0x140011751  mov     esi, eax
0x140011753  cmp     eax, 103h
0x140011758  jz      loc_14001182F
0x14001175e  cmp     cs:g_AfdEtwTraceEnable, 0
0x140011765  xorps   xmm0, xmm0
0x140011768  mov     rdx, qword ptr [rbp+110h+var_140]
0x14001176c  mov     r14, [rbx+68h]
0x140011770  mov     edx, edx
0x140011772  movups  xmmword ptr [rbp+110h+LockHandle.LockQueue.Next], xmm0
0x140011776  mov     [r14+30h], eax
0x14001177a  mov     [r14+38h], rdx
0x14001177e  mov     rdi, [rbx+30h]
0x140011782  mov     rcx, [rbx+38h]
0x140011786  mov     r9, [rdi+8]
0x14001178a  jnz     loc_140011AC4
0x140011790  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140011796  test    eax, eax
0x140011798  jnz     loc_140011AC4
0x14001179e  cmp     cs:g_AfdEtwTraceEnable, 0
0x1400117a5  jnz     loc_140011A16
0x1400117ab  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400117b1  test    eax, eax
0x1400117b3  jnz     loc_140011A99
0x1400117b9  mov     rcx, [rdi+8]
0x1400117bd  lea     rdx, [rbp+110h+LockHandle]; LockHandle
0x1400117c1  xorps   xmm0, xmm0
0x1400117c4  xor     eax, eax
0x1400117c6  add     rcx, 38h ; '8'; SpinLock
0x1400117ca  mov     qword ptr [rbp+110h+LockHandle.OldIrql], rax
0x1400117ce  movups  xmmword ptr [rbp+110h+LockHandle.LockQueue.Next], xmm0
0x1400117d2  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400117d9  nop     dword ptr [rax+rax+00h]
0x1400117de  mov     edx, [r14+30h]
0x1400117e2  mov     eax, [r14+38h]
0x1400117e6  sub     [rdi+78h], eax
0x1400117e9  dec     dword ptr [rdi+7Ch]
0x1400117ec  test    edx, edx
0x1400117ee  js      loc_140011B13
0x1400117f4  lea     rdx, [rbp+110h+LockHandle]
0x1400117f8  mov     rcx, rdi
0x1400117fb  call    AfdCompleteBufferedSendsUnlock
0x140011800  mov     rcx, [rbx+38h]
0x140011804  mov     eax, [rbx+48h]
0x140011807  mov     [rcx+28h], eax
0x14001180a  mov     rcx, rbx; Entry
0x14001180d  mov     rdx, [rdi+20h]; Process
0x140011811  call    AfdReturnBuffer
0x140011816  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14001181d  lock xadd [rdi+30h], rax
0x140011823  sub     rax, 1
0x140011827  jle     loc_140011AE1
0x14001182d  mov     eax, esi
0x14001182f  mov     rcx, [rbp+110h+var_50]
0x140011836  xor     rcx, rsp; StackCookie
0x140011839  call    __security_check_cookie
0x14001183e  add     rsp, 1D8h
0x140011845  pop     r15
0x140011847  pop     r14
0x140011849  pop     r13
0x14001184b  pop     r12
0x14001184d  pop     rdi
0x14001184e  pop     rsi
0x14001184f  pop     rbx
0x140011850  pop     rbp
0x140011851  retn
0x140011853  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140011859  mov     [rbp+110h+LockHandle.LockQueue.Lock], 0
0x140011861  mov     [rbp+110h+LockHandle.LockQueue.Next], r12
0x140011865  mov     qword ptr [rbp+110h+var_E8+8], 0
0x14001186d  mov     qword ptr [rbp+110h+var_E8], rbx
0x140011871  test    eax, eax
0x140011873  jnz     loc_140011AF6
0x140011879  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14001187f  test    eax, eax
0x140011881  jz      loc_1400116EE
0x140011887  lea     r9, [rbp+110h+LockHandle]
0x14001188b  mov     dword ptr [rsp+210h+var_1E0], 2
0x140011893  lea     r8, [rbp+110h+var_E8]
0x140011897  call    EtwEx_tidActivityInfoTransfer
0x14001189c  jmp     loc_1400116EE
0x1400118a1  mov     eax, cs:AFD_EVENT_SEND
0x1400118a7  mov     dword ptr [rbp+110h+EventDescriptor.Id], eax
0x1400118aa  movzx   eax, cs:word_14007DA7D
0x1400118b1  mov     word ptr [rbp+110h+EventDescriptor.Opcode], ax
0x1400118b5  movzx   eax, cs:byte_14007DA7F
0x1400118bc  mov     byte ptr [rbp+110h+EventDescriptor.Task+1], al
0x1400118bf  xor     eax, eax
0x1400118c1  test    r12, r12
0x1400118c4  jz      short loc_1400118D1
0x1400118c6  cmp     [r12], cx
0x1400118cb  setnz   al
0x1400118ce  inc     rax
0x1400118d1  or      rax, r13
0x1400118d4  mov     [rbp+110h+EventDescriptor.Level], 4
0x1400118d8  mov     [rbp+110h+EventDescriptor.Keyword], rax
0x1400118dc  mov     rax, r12
0x1400118df  mov     [rsp+210h+var_1A0], 0
0x1400118e7  mov     [rsp+210h+var_1A8], r15d
0x1400118ec  mov     [rbp+110h+var_188], r14
0x1400118f0  mov     [rsp+210h+var_1B0], 1
0x1400118f8  mov     [rbp+110h+var_190], r12
0x1400118fc  mov     [rsp+210h+var_1B8], 0BF0h
0x140011904  mov     [rsp+210h+var_1C0], 0
0x14001190c  mov     [rsp+210h+var_198], 0
0x140011915  mov     qword ptr [rbp+110h+ActivityId.Data4], 0
0x14001191d  test    rbx, rbx
0x140011920  jz      loc_140011BA8
0x140011926  mov     qword ptr [rbp+110h+ActivityId.Data1], rbx
0x14001192a  test    r12, r12
0x14001192d  jz      loc_140011BB1
0x140011933  mov     rax, [rax+30h]
0x140011937  mov     rcx, cs:g_AfdEtwHandle; RegHandle
0x14001193e  lea     r8, [rbp+110h+ActivityId]; ActivityId
0x140011942  mov     [rsp+210h+var_198], rax
0x140011947  lea     rdx, [rbp+110h+EventDescriptor]; EventDescriptor
0x14001194b  lea     rax, [rsp+210h+var_1C0]
0x140011950  mov     qword ptr [rbp+110h+var_D0.Size], 4
0x140011958  mov     [rbp+110h+var_D0.Ptr], rax
0x14001195c  mov     r9d, 8; UserDataCount
0x140011962  lea     rax, [rsp+210h+var_1B8]
0x140011967  mov     [rbp+110h+var_B8], 4
0x14001196f  mov     [rbp+110h+var_C0], rax
0x140011973  lea     rax, [rsp+210h+var_198]
0x140011978  mov     [rbp+110h+var_B0], rax
0x14001197c  lea     rax, [rbp+110h+var_190]
0x140011980  mov     [rbp+110h+var_A0], rax
0x140011984  lea     rax, [rsp+210h+var_1B0]
0x140011989  mov     [rbp+110h+var_90], rax
0x140011990  lea     rax, [rbp+110h+var_188]
0x140011994  mov     [rbp+110h+var_80], rax
0x14001199b  lea     rax, [rsp+210h+var_1A8]
0x1400119a0  mov     [rbp+110h+var_70], rax
0x1400119a7  lea     rax, [rsp+210h+var_1A0]
0x1400119ac  mov     [rbp+110h+var_60], rax
0x1400119b3  lea     rax, [rbp+110h+var_D0]
0x1400119b7  mov     [rsp+210h+UserData], rax; UserData
0x1400119bc  mov     [rbp+110h+var_A8], 8
0x1400119c4  mov     [rbp+110h+var_98], 8
0x1400119cc  mov     [rbp+110h+var_88], 4
0x1400119d7  mov     [rbp+110h+var_78], 8
0x1400119e2  mov     [rbp+110h+var_68], 4
0x1400119ed  mov     [rbp+110h+var_58], 4
0x1400119f8  call    cs:__imp_EtwWrite
0x1400119ff  nop     dword ptr [rax+rax+00h]
0x140011a04  cmp     cs:g_AfdEtwTraceEnable, 0
0x140011a0b  jnz     loc_140011710
0x140011a11  jmp     loc_14001170A
0x140011a16  mov     eax, cs:AFD_EVENT_SEND
0x140011a1c  mov     dword ptr [rbp+110h+EventDescriptor.Id], eax
0x140011a1f  movzx   eax, cs:word_14007DA7D
0x140011a26  mov     word ptr [rbp+110h+EventDescriptor.Opcode], ax
0x140011a2a  movzx   eax, cs:byte_14007DA7F
0x140011a31  mov     byte ptr [rbp+110h+EventDescriptor.Task+1], al
0x140011a34  xor     eax, eax
0x140011a36  test    r9, r9
0x140011a39  jz      short loc_140011A4B
0x140011a3b  mov     r8d, 0AFD1h
0x140011a41  cmp     [r9], r8w
0x140011a45  setnz   al
0x140011a48  inc     rax
0x140011a4b  or      rax, r13
0x140011a4e  mov     [rsp+210h+var_1C8], rbx; __int64
0x140011a53  mov     [rbp+110h+EventDescriptor.Keyword], rax
0x140011a57  mov     r8d, 0BD0h
0x140011a5d  mov     dword ptr [rsp+210h+var_1D0], esi; char
0x140011a61  mov     eax, esi
0x140011a63  mov     dword ptr [rsp+210h+var_1D8], edx; char
0x140011a67  mov     edx, 1
0x140011a6c  sar     eax, 1Fh
0x140011a6f  mov     qword ptr [rsp+210h+var_1E0], rcx; char
0x140011a74  and     al, 0FEh
0x140011a76  add     al, 4
0x140011a78  mov     dword ptr [rsp+210h+var_1E8], 1; char
0x140011a80  lea     rcx, [rbp+110h+EventDescriptor]; EventDescriptor
0x140011a84  mov     [rbp+110h+EventDescriptor.Level], al
0x140011a87  call    AFDETW_TRACEDATA_CORE
0x140011a8c  cmp     cs:g_AfdEtwTraceEnable, 0
0x140011a93  jz      loc_1400117AB
0x140011a99  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140011a9f  test    eax, eax
0x140011aa1  jz      loc_1400117B9
0x140011aa7  lea     r8, [rbp+110h+LockHandle]
0x140011aab  mov     dword ptr [rsp+210h+UserData], 2
0x140011ab3  lea     rdx, ActivityStop
0x140011aba  call    EtwEx_tidActivityInfo
0x140011abf  jmp     loc_1400117B9
0x140011ac4  mov     qword ptr [rbp+110h+ActivityId.Data4], 0
0x140011acc  mov     qword ptr [rbp+110h+ActivityId.Data1], r9
0x140011ad0  mov     [rbp+110h+LockHandle.LockQueue.Lock], 0
0x140011ad8  mov     [rbp+110h+LockHandle.LockQueue.Next], rbx
0x140011adc  jmp     loc_14001179E
0x140011ae1  test    rax, rax
0x140011ae4  jz      loc_140011B91
0x140011aea  mov     ecx, 0Eh
0x140011aef  int     29h; Win8: RtlFailFast(ecx)
0x140011af1  jmp     loc_14001182D
0x140011af6  lea     r8, [rbp+110h+var_E8]
0x140011afa  mov     dword ptr [rsp+210h+UserData], 2
0x140011b02  lea     rdx, ActivityStart
0x140011b09  call    EtwEx_tidActivityInfo
0x140011b0e  jmp     loc_140011879
0x140011b13  mov     r15, [rdi+80h]
0x140011b1a  mov     r14, [rdi+8]
0x140011b1e  test    r15, r15
0x140011b21  jnz     loc_140011BC2
0x140011b27  lea     eax, [rdx+3FFFFDF4h]
0x140011b2d  cmp     eax, 1
0x140011b30  ja      short loc_140011B9E
0x140011b32  or      dword ptr [rdi+4], 2000h
0x140011b39  lea     rcx, [rbp+110h+LockHandle]; LockHandle
0x140011b3d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140011b44  nop     dword ptr [rax+rax+00h]
0x140011b49  mov     r9d, 0Fh
0x140011b4f  mov     r8, r14
0x140011b52  mov     edx, 1F56h
0x140011b57  mov     ecx, 2
0x140011b5c  call    AFDETW_TRACEABORT
0x140011b61  mov     rcx, rdi
0x140011b64  call    AfdBeginAbort
0x140011b69  test    r15, r15
0x140011b6c  jnz     short loc_140011BD2
0x140011b6e  lea     rcx, [r14+38h]; SpinLock
0x140011b72  lea     rdx, [rbp+110h+LockHandle]; LockHandle
0x140011b76  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140011b7d  nop     dword ptr [rax+rax+00h]
0x140011b82  mov     dl, 1
0x140011b84  mov     rcx, rdi
0x140011b87  call    AfdDeleteConnectedReference
0x140011b8c  jmp     loc_1400117F4
0x140011b91  mov     rcx, rdi
0x140011b94  call    AfdCloseConnection
0x140011b99  jmp     loc_14001182D
0x140011b9e  cmp     edx, 0C000013Ch
0x140011ba4  jnz     short loc_140011B39
0x140011ba6  jmp     short loc_140011B32
0x140011ba8  mov     qword ptr [rbp+110h+ActivityId.Data1], r12
0x140011bac  jmp     loc_14001192A
0x140011bb1  call    cs:__imp_IoGetCurrentProcess
0x140011bb8  nop     dword ptr [rax+rax+00h]
0x140011bbd  jmp     loc_140011937
0x140011bc2  mov     qword ptr [rdi+80h], 0
0x140011bcd  jmp     loc_140011B27
0x140011bd2  mov     rcx, [rdi+18h]; DeviceObject
0x140011bd6  mov     rdx, r15; Irp
0x140011bd9  call    cs:__imp_IofCallDriver
0x140011be0  nop     dword ptr [rax+rax+00h]
0x140011be5  jmp     short loc_140011B6E
```
