# TxfTransMgrSearchAddTrans

- ea: `0x140188078`
- end: `0x140188bba`
- name: `TxfTransMgrSearchAddTrans`
- size: `2882`
- prototype: ``
- caller_count: `14`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140017480`
- `0x1400ffd84`
- `0x140130b90`
- `0x14017db70`
- `0x140185c50`
- `0x140187a00`
- `0x140187df0`
- `0x140189244`
- `0x14018a0bc`
- `0x140193f80`
- `0x1401d5b20`
- `0x1401d6998`
- `0x1401d9840`
- `0x14020a67c`

## callees

- `0x140007ea0`
- `0x140033030`
- `0x14004088c`
- `0x140188078`
- `0x140188d34`
- `0x14018dc9c`
- `0x140196e80`
- `0x1401da980`
- `0x1401db394`
- `0x14026f420`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140188b0f`
- `ntoskrnl!KeSetEvent` at `0x140188b0f`
- `ntoskrnl!TmIsTransactionActive` at `0x140188208`
- `ntoskrnl!TmIsTransactionActive` at `0x140188a74`
- `ntoskrnl!TmIsTransactionActive` at `0x140188208`
- `ntoskrnl!TmIsTransactionActive` at `0x140188a74`
- `ntoskrnl!ObfReferenceObject` at `0x14018838e`
- `ntoskrnl!ObfReferenceObject` at `0x1401886bb`
- `ntoskrnl!ObfReferenceObject` at `0x14018838e`
- `ntoskrnl!ObfReferenceObject` at `0x1401886bb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14018888e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14018888e`
- `ntoskrnl!TmGetTransactionId` at `0x1401886a7`
- `ntoskrnl!TmGetTransactionId` at `0x1401886a7`
- `ntoskrnl!TmCreateEnlistment` at `0x140188488`
- `ntoskrnl!TmCreateEnlistment` at `0x140188488`
- `ntoskrnl!TmEnlistmentObjectType` at `0x14018887e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14018826b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401883d0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401884a4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140188b93`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14018826b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401883d0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401884a4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140188b93`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401882d1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401883e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018840f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140188506`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401888da`
- `ntoskrnl!ExReleaseResourceLite` at `0x140188b46`
- `ntoskrnl!ExReleaseResourceLite` at `0x140188bac`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aad32`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aad54`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401882d1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401883e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018840f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140188506`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401888da`
- `ntoskrnl!ExReleaseResourceLite` at `0x140188b46`
- `ntoskrnl!ExReleaseResourceLite` at `0x140188bac`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aad32`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aad54`
- `ntoskrnl!RtlCompareMemory` at `0x140188561`
- `ntoskrnl!RtlCompareMemory` at `0x140188561`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401880fa`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401880fa`
- `ntoskrnl!ExRaiseStatus` at `0x1401883a9`
- `ntoskrnl!ExRaiseStatus` at `0x1401883a9`

## pseudocode

```c
__int64 __fastcall TxfTransMgrSearchAddTrans(
        __int64 a1,
        _OWORD *a2,
        struct _KTRANSACTION *a3,
        char a4,
        __int64 a5,
        _QWORD *a6)
{
  const void *v8; // r9
  NTSTATUS TransactionRequest; // esi
  _QWORD *EnlistmentKey; // rdi
  __int64 v12; // r12
  struct _ERESOURCE *v13; // rcx
  char v14; // r12
  _QWORD *v15; // r14
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // r14d
  __int64 v19; // rdx
  __int64 v20; // rdi
  __int64 v21; // rdx
  struct _KEVENT *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // r8
  _QWORD *v28; // [rsp+58h] [rbp-80h] BYREF
  _QWORD v29[2]; // [rsp+60h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-68h] BYREF
  char v31; // [rsp+E0h] [rbp+8h] BYREF
  _OWORD *v32; // [rsp+E8h] [rbp+10h]
  char v33; // [rsp+F8h] [rbp+20h] BYREF

  v32 = a2;
  v8 = a2;
  TransactionRequest = 0;
  EnlistmentKey = 0;
  v28 = 0;
  v31 = 0;
  v33 = 0;
  memset(&ObjectAttributes, 0, 44);
  v12 = a1 + 144;
  v29[1] = a1 + 144;
  *a6 = 0;
  do
  {
    if ( !v31 )
    {
      v13 = *(struct _ERESOURCE **)(v12 + 16);
      if ( (a4 & 2) != 0 )
        ExAcquireResourceExclusiveLite(v13, 1u);
      else
        ExAcquireResourceSharedLite(v13, 1u);
      v31 = 1;
      v8 = v32;
    }
    if ( (a4 & 0xC) != 0
      || _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 132), 4, 4) == 1
      || _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 132), 4, 4) == 2 )
    {
      if ( (*(_DWORD *)(a1 + 136) & 0x1000) != 0
        && _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 132), 4, 4) == 2
        && (a4 & 4) == 0 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 3222929452LL, 3213668);
        TransactionRequest = -1072037844;
        goto LABEL_137;
      }
      if ( (*(_DWORD *)(a1 + 136) & 0xA00000) != 0
        && _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 132), 4, 4) == 2
        && (a4 & 4) == 0 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 3221225626LL, 3213684);
        TransactionRequest = -1073741670;
        goto LABEL_137;
      }
      v14 = 0;
      if ( a3 || v8 || (a4 & 8) == 0 )
      {
        EnlistmentKey = *(_QWORD **)(a1 + 152);
        v28 = EnlistmentKey;
        while ( 1 )
        {
          v15 = EnlistmentKey;
          if ( !EnlistmentKey )
            break;
          if ( ((EnlistmentKey[2] & 0x2000) == 0 || (a4 & 0x40) != 0)
            && (a3 && (struct _KTRANSACTION *)EnlistmentKey[29] == a3
             || v8 && RtlCompareMemory(v8, EnlistmentKey + 32, 0x10u) == 16) )
          {
            goto LABEL_30;
          }
          EnlistmentKey = (_QWORD *)EnlistmentKey[13];
          v28 = (_QWORD *)v15[13];
          v8 = v32;
        }
      }
      else if ( *(_QWORD *)(a1 + 696) )
      {
        EnlistmentKey = *(_QWORD **)(a1 + 696);
        v28 = EnlistmentKey;
        v14 = 1;
      }
      if ( v14 )
      {
LABEL_30:
        ExAcquireResourceExclusiveLite((PERESOURCE)(EnlistmentKey[3] + 80LL), 1u);
        v33 = 1;
        if ( (EnlistmentKey[2] & 0x20000) != 0 )
        {
          v12 = a1 + 144;
          TransactionRequest = TxfWaitForEnlistmentCompletion(
                                 a5,
                                 (_DWORD)EnlistmentKey,
                                 (unsigned int)&v33,
                                 (int)a1 + 144,
                                 (__int64)&v31);
          EnlistmentKey = 0;
          v28 = 0;
          if ( TransactionRequest >= 0 )
          {
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 3221226029LL, 3213804);
            TransactionRequest = -1073741267;
          }
          goto LABEL_137;
        }
        v18 = a4 & 1;
        LOBYTE(v16) = (a4 & 1) != 0 || (a4 & 4) != 0;
        LOBYTE(v17) = (a4 & 0x10) != 0;
        TransactionRequest = TxfGetTransactionRequest(EnlistmentKey, v16, v17);
        if ( TransactionRequest >= 0 )
          *a6 = EnlistmentKey;
        ExReleaseResourceLite((PERESOURCE)(EnlistmentKey[3] + 80LL));
        v33 = 0;
      }
      else
      {
        if ( (a4 & 2) == 0 )
        {
          if ( !a3 || TmIsTransactionActive(a3) )
          {
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 3222863969LL, 3213856);
            TransactionRequest = -1072103327;
            goto LABEL_27;
          }
          if ( !NtfsStatusDebugFlags )
            goto LABEL_26;
          v26 = 3213852;
          goto LABEL_89;
        }
        if ( (a4 & 8) == 0 && (a4 & 1) == 0 && !TmIsTransactionActive(a3) )
        {
          if ( !NtfsStatusDebugFlags )
          {
LABEL_26:
            TransactionRequest = -1072103421;
LABEL_27:
            v12 = a1 + 144;
            goto LABEL_137;
          }
          v26 = 3213886;
LABEL_89:
          NtfsStatusTraceAndDebugInternal(0, 3222863875LL, v26);
          goto LABEL_26;
        }
        v18 = a4 & 1;
        if ( (a4 & 1) == 0 )
        {
          if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 132), 4, 4) != 2 )
          {
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 3222863877LL, 3213899);
            TransactionRequest = -1072103419;
            v12 = a1 + 144;
            goto LABEL_137;
          }
          v18 = 0;
        }
      }
      if ( (a4 & 0x20) != 0 && (!EnlistmentKey || !EnlistmentKey[30]) && a3 && a5 )
      {
        v20 = TxfSearchAddTxfFcbCleanupList(*(_QWORD *)(a5 + 144), 0, 5, 0, 1);
        *(_DWORD *)(v20 + 16) |= 0x10000u;
        if ( *a6 )
        {
          *a6 = 0;
          if ( (a4 & 0x10) != 0 )
          {
            LOBYTE(v19) = 1;
            TxfDereferenceTransaction(&v28, v19);
          }
        }
        *(_QWORD *)(v20 + 24) = 0;
        *(_QWORD *)(v20 + 32) = a1;
        _InterlockedAdd((volatile signed __int32 *)(a1 + 64), 1u);
        _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(v20 + 32) + 48LL), 1u);
        ObfReferenceObject(a3);
        *(_QWORD *)(v20 + 40) = a3;
        ExRaiseStatus(-1073741608);
      }
      if ( EnlistmentKey )
      {
        v12 = a1 + 144;
      }
      else
      {
        EnlistmentKey = TxfTransAllocate();
        v28 = EnlistmentKey;
        *a6 = EnlistmentKey;
        if ( v18 )
          _InterlockedOr((volatile signed __int32 *)EnlistmentKey + 4, 0x62u);
        if ( v32 )
          *((_OWORD *)EnlistmentKey + 16) = *v32;
        else
          TmGetTransactionId(a3, (PUOW)EnlistmentKey + 16);
        if ( a3 )
        {
          ObfReferenceObject(a3);
          EnlistmentKey[29] = a3;
        }
        _InterlockedOr((volatile signed __int32 *)EnlistmentKey + 4, 0x2000000u);
        if ( a1 != *(_QWORD *)(*(_QWORD *)(a1 + 16) + 6248LL) && (*(_DWORD *)(a1 + 128) & 0x10) != 0 )
          _InterlockedOr((volatile signed __int32 *)EnlistmentKey + 4, 0x1000000u);
        v12 = a1 + 144;
        EnlistmentKey[38] = _InterlockedIncrement64((volatile signed __int64 *)(a1 + 224));
        _InterlockedAdd((volatile signed __int32 *)(a1 + 64), 1u);
        _InterlockedAdd((volatile signed __int32 *)(a1 + 40), 1u);
        v24 = EnlistmentKey[26];
        if ( v24 )
        {
          _InterlockedDecrement((volatile signed __int32 *)(v24 + 40));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(EnlistmentKey[26] + 64LL), 0xFFFFFFFF) == 1 )
            TxfDeleteTxfRmcb((char *)EnlistmentKey[26]);
        }
        EnlistmentKey[26] = a1;
        *((_WORD *)EnlistmentKey + 4) = 1;
        *((_DWORD *)EnlistmentKey + 1) = 1;
        if ( v18 )
          *((_DWORD *)EnlistmentKey + 1) = 2;
        EnlistmentKey[5] = CLFS_LSN_NULL_EXT;
        EnlistmentKey[6] = CLFS_LSN_NULL_EXT;
        EnlistmentKey[4] = CLFS_LSN_NULL_EXT;
        EnlistmentKey[8] = CLFS_LSN_NULL_EXT;
        EnlistmentKey[37] = CLFS_LSN_NULL_EXT;
        EnlistmentKey[48] = CLFS_LSN_NULL_EXT;
        EnlistmentKey[9] = CLFS_LSN_NULL_EXT;
        EnlistmentKey[23] = EnlistmentKey + 22;
        EnlistmentKey[22] = EnlistmentKey + 22;
        EnlistmentKey[41] = EnlistmentKey + 40;
        EnlistmentKey[40] = EnlistmentKey + 40;
        if ( (*(_DWORD *)(a1 + 136) & 0x400000) != 0 )
        {
          TxfTransFreeze(EnlistmentKey, 68);
          _InterlockedOr((volatile signed __int32 *)EnlistmentKey + 4, 0x10000000u);
        }
        v25 = *(_QWORD *)(a1 + 152);
        if ( v25 )
        {
          EnlistmentKey[13] = v25;
          *(_QWORD *)(*(_QWORD *)(a1 + 152) + 112LL) = EnlistmentKey;
        }
        *(_QWORD *)(a1 + 152) = EnlistmentKey;
      }
      if ( (a4 & 0x20) != 0 && !EnlistmentKey[30] )
      {
        ExAcquireResourceExclusiveLite((PERESOURCE)(EnlistmentKey[3] + 80LL), 1u);
        v33 = 1;
        ExReleaseResourceLite(*(PERESOURCE *)(v12 + 16));
        v31 = 0;
        _InterlockedOr((volatile signed __int32 *)EnlistmentKey + 4, 0x20000u);
        ExReleaseResourceLite((PERESOURCE)(EnlistmentKey[3] + 80LL));
        v33 = 0;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 512;
        ObjectAttributes.ObjectName = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        TransactionRequest = TmCreateEnlistment(
                               (PHANDLE)EnlistmentKey + 31,
                               0,
                               0xF001Fu,
                               &ObjectAttributes,
                               *(PRKRESOURCEMANAGER *)(a1 + 648),
                               a3,
                               0,
                               0x20Eu,
                               EnlistmentKey);
        ExAcquireResourceExclusiveLite((PERESOURCE)(EnlistmentKey[3] + 80LL), 1u);
        v33 = 1;
        _InterlockedAnd((volatile signed __int32 *)EnlistmentKey + 4, 0xFFFDFFFF);
        v22 = (struct _KEVENT *)EnlistmentKey[49];
        if ( v22 )
          KeSetEvent(v22, 0, 0);
        if ( TransactionRequest >= 0 )
        {
          TransactionRequest = ObReferenceObjectByHandle(
                                 (HANDLE)EnlistmentKey[31],
                                 0,
                                 (POBJECT_TYPE)TmEnlistmentObjectType,
                                 0,
                                 (PVOID *)EnlistmentKey + 30,
                                 0);
          if ( NtfsStatusDebugFlags
            && TransactionRequest
            && TransactionRequest != 294
            && (unsigned int)(TransactionRequest - 298) > 1
            && (unsigned int)TransactionRequest < 0xFFFFFFED
            && TransactionRequest != -1073741608
            && TransactionRequest != -1073741802
            && TransactionRequest != -1073741807
            && (unsigned int)(TransactionRequest + 2147483643) > 1
            && TransactionRequest != 259 )
          {
            NtfsStatusTraceAndDebugInternal(0, (unsigned int)TransactionRequest, 3214269);
          }
          ++*((_DWORD *)EnlistmentKey + 1);
          if ( (EnlistmentKey[2] & 0x200) != 0 )
          {
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 29, 3214288);
            TransactionRequest = 29;
          }
          EnlistmentKey[47] = MEMORY[0xFFFFF78000000014];
          ExReleaseResourceLite((PERESOURCE)(EnlistmentKey[3] + 80LL));
          v33 = 0;
        }
        else
        {
          if ( NtfsStatusDebugFlags
            && (unsigned int)TransactionRequest < 0xFFFFFFED
            && TransactionRequest != -1073741802
            && TransactionRequest != -1073741807
            && (unsigned int)(TransactionRequest + 2147483643) > 1
            && TransactionRequest != -1073741608 )
          {
            NtfsStatusTraceAndDebugInternal(0, (unsigned int)TransactionRequest, 3214222);
          }
          _InterlockedOr((volatile signed __int32 *)EnlistmentKey + 4, 2u);
          if ( (EnlistmentKey[2] & 0x200) != 0 )
          {
            v29[0] = EnlistmentKey;
            LOBYTE(v21) = 1;
            TxfDereferenceTransaction(v29, v21);
          }
          ExReleaseResourceLite((PERESOURCE)(EnlistmentKey[3] + 80LL));
          v33 = 0;
          TxfRemoveTransactionFromList(EnlistmentKey);
          *a6 = 0;
          LOBYTE(v23) = 1;
          TxfDereferenceTransaction(&v28, v23);
          EnlistmentKey = v28;
        }
        goto LABEL_27;
      }
    }
    else
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3222863877LL, 3213655);
      TransactionRequest = -1072103419;
    }
LABEL_137:
    if ( v31 )
    {
      ExReleaseResourceLite(*(PERESOURCE *)(v12 + 16));
      v31 = 0;
    }
    if ( v33 )
      ExReleaseResourceLite((PERESOURCE)(EnlistmentKey[3] + 80LL));
    v8 = v32;
  }
  while ( TransactionRequest == -1073741267 );
  return (unsigned int)TransactionRequest;
}

```

## disassembly

```asm
0x140188078  mov     r11, rsp
0x14018807b  mov     [r11+10h], rdx
0x14018807f  push    rbx
0x140188080  push    rsi
0x140188081  push    rdi
0x140188082  push    r12
0x140188084  push    r13
0x140188086  push    r14
0x140188088  push    r15
0x14018808a  sub     rsp, 0A0h
0x140188091  mov     ebx, r9d
0x140188094  mov     r13, r8
0x140188097  mov     r9, rdx
0x14018809a  mov     r15, rcx
0x14018809d  xor     esi, esi
0x14018809f  xor     edi, edi
0x1401880a1  mov     [r11-80h], rdi
0x1401880a5  mov     [r11+8], sil
0x1401880a9  mov     [r11+20h], sil
0x1401880ad  xor     eax, eax
0x1401880af  xorps   xmm0, xmm0
0x1401880b2  movups  xmmword ptr [rsp+0D8h+ObjectAttributes.Length], xmm0
0x1401880b7  movups  xmmword ptr [r11-58h], xmm0
0x1401880bc  movups  xmmword ptr [r11-4Ch], xmm0
0x1401880c1  lea     r12, [rcx+90h]
0x1401880c8  mov     [rsp+0D8h+var_70], r12
0x1401880cd  mov     rax, [rsp+0D8h+arg_28]
0x1401880d5  mov     [rax], rsi
0x1401880d8  lea     ecx, [rsi+4]
0x1401880db  lea     r14d, [rsi+1]
0x1401880df  cmp     [rsp+0D8h+arg_0], 0
0x1401880e7  jnz     short loc_14018811B
0x1401880e9  mov     rcx, [r12+10h]; Resource
0x1401880ee  mov     dl, r14b; Wait
0x1401880f1  test    bl, 2
0x1401880f4  jnz     loc_140188B93
0x1401880fa  call    cs:__imp_ExAcquireResourceSharedLite
0x140188101  nop     dword ptr [rax+rax+00h]
0x140188106  mov     [rsp+0D8h+arg_0], r14b
0x14018810e  mov     r9, [rsp+0D8h+arg_8]
0x140188116  mov     ecx, 4
0x14018811b  test    bl, 0Ch
0x14018811e  jnz     short loc_140188144
0x140188120  mov     eax, ecx
0x140188122  lock cmpxchg [r15+84h], ecx
0x14018812b  cmp     eax, r14d
0x14018812e  jz      short loc_140188144
0x140188130  mov     eax, ecx
0x140188132  lock cmpxchg [r15+84h], ecx
0x14018813b  cmp     eax, 2
0x14018813e  jnz     loc_140188964
0x140188144  test    dword ptr [r15+88h], 1000h
0x14018814f  jnz     loc_140188A33
0x140188155  test    dword ptr [r15+88h], 0A00000h
0x140188160  jz      short loc_14018818E
0x140188162  mov     eax, ecx
0x140188164  lock cmpxchg [r15+84h], ecx
0x14018816d  cmp     eax, 2
0x140188170  jnz     short loc_14018818E
0x140188172  test    cl, bl
0x140188174  jnz     short loc_14018818E
0x140188176  mov     al, cs:NtfsStatusDebugFlags
0x14018817c  test    al, al
0x14018817e  jnz     loc_140188990
0x140188184  mov     esi, 0C000009Ah
0x140188189  jmp     loc_140188973
0x14018818e  xor     r12b, r12b
0x140188191  mov     [rsp+0D8h+var_88], r12b
0x140188196  test    r13, r13
0x140188199  jz      loc_14018857C
0x14018819f  mov     rdi, [r15+98h]
0x1401881a6  mov     [rsp+0D8h+var_80], rdi
0x1401881ab  mov     r14, rdi
0x1401881ae  mov     rdx, rdi
0x1401881b1  test    rdx, rdx
0x1401881b4  jz      short loc_1401881DD
0x1401881b6  test    dword ptr [rdi+10h], 2000h
0x1401881bd  setnz   cl
0x1401881c0  test    bl, 40h
0x1401881c3  setz    al
0x1401881c6  test    al, cl
0x1401881c8  jz      short loc_14018823F
0x1401881ca  mov     rdi, [r14+68h]
0x1401881ce  mov     [rsp+0D8h+var_80], rdi
0x1401881d3  mov     r9, [rsp+0D8h+arg_8]
0x1401881db  jmp     short loc_1401881AB
0x1401881dd  mov     r14d, 1
0x1401881e3  test    r12b, r12b
0x1401881e6  jnz     short loc_140188260
0x1401881e8  test    bl, 2
0x1401881eb  jz      loc_140188A68
0x1401881f1  test    bl, 8
0x1401881f4  setz    cl
0x1401881f7  test    r14b, bl
0x1401881fa  setz    al
0x1401881fd  test    al, cl
0x1401881ff  jz      loc_14018861D
0x140188205  mov     rcx, r13; Transaction
0x140188208  call    cs:__imp_TmIsTransactionActive
0x14018820f  nop     dword ptr [rax+rax+00h]
0x140188214  test    al, al
0x140188216  jnz     loc_14018861D
0x14018821c  mov     al, cs:NtfsStatusDebugFlags
0x140188222  test    al, al
0x140188224  jnz     loc_1401887F0
0x14018822a  mov     esi, 0C0190003h
0x14018822f  mov     [rsp+0D8h+var_84], esi
0x140188233  lea     r12, [r15+90h]
0x14018823a  jmp     loc_140188B37
0x14018823f  test    r13, r13
0x140188242  jz      loc_140188548
0x140188248  cmp     [r14+0E8h], r13
0x14018824f  jnz     loc_140188548
0x140188255  mov     r14d, 1
0x14018825b  mov     [rsp+0D8h+var_88], r14b
0x140188260  mov     rcx, [rdi+18h]
0x140188264  add     rcx, 50h ; 'P'; Resource
0x140188268  mov     dl, r14b; Wait
0x14018826b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140188272  nop     dword ptr [rax+rax+00h]
0x140188277  mov     [rsp+0D8h+arg_18], r14b
0x14018827f  test    dword ptr [rdi+10h], 20000h
0x140188286  jnz     loc_1401885B3
0x14018828c  mov     eax, ebx
0x14018828e  and     eax, 10h
0x140188291  mov     r14d, ebx
0x140188294  mov     r12d, 1
0x14018829a  and     r14d, r12d
0x14018829d  jz      loc_140188A54
0x1401882a3  mov     dl, r12b
0x1401882a6  test    eax, eax
0x1401882a8  setnz   r8b
0x1401882ac  mov     rcx, rdi
0x1401882af  call    TxfGetTransactionRequest
0x1401882b4  mov     esi, eax
0x1401882b6  mov     [rsp+0D8h+var_84], eax
0x1401882ba  test    eax, eax
0x1401882bc  js      short loc_1401882C9
0x1401882be  mov     rax, [rsp+0D8h+arg_28]
0x1401882c6  mov     [rax], rdi
0x1401882c9  mov     rcx, [rdi+18h]
0x1401882cd  add     rcx, 50h ; 'P'; Resource
0x1401882d1  call    cs:__imp_ExReleaseResourceLite
0x1401882d8  nop     dword ptr [rax+rax+00h]
0x1401882dd  mov     [rsp+0D8h+arg_18], 0
0x1401882e5  test    bl, 20h
0x1401882e8  jnz     short loc_14018830E
0x1401882ea  test    rdi, rdi
0x1401882ed  jz      loc_14018866B
0x1401882f3  lea     r12, [r15+90h]
0x1401882fa  test    bl, 20h
0x1401882fd  jnz     loc_1401883B5
0x140188303  mov     r14d, 1
0x140188309  jmp     loc_140188B37
0x14018830e  test    rdi, rdi
0x140188311  jz      short loc_14018831D
0x140188313  cmp     qword ptr [rdi+0F0h], 0
0x14018831b  jnz     short loc_1401882EA
0x14018831d  test    r13, r13
0x140188320  jz      short loc_1401882EA
0x140188322  mov     rax, [rsp+0D8h+arg_20]
0x14018832a  test    rax, rax
0x14018832d  jz      short loc_1401882EA
0x14018832f  mov     byte ptr [rsp+0D8h+ResourceManager], r12b
0x140188334  xor     r9d, r9d
0x140188337  xor     edx, edx
0x140188339  lea     r8d, [r9+5]
0x14018833d  mov     rcx, [rax+90h]
0x140188344  call    TxfSearchAddTxfFcbCleanupList
0x140188349  mov     rdi, rax
0x14018834c  bts     dword ptr [rax+10h], 10h
0x140188351  mov     rax, [rsp+0D8h+arg_28]
0x140188359  xor     esi, esi
0x14018835b  cmp     [rax], rsi
0x14018835e  jz      short loc_140188375
0x140188360  mov     [rax], rsi
0x140188363  test    bl, 10h
0x140188366  jz      short loc_140188375
0x140188368  mov     dl, r12b
0x14018836b  lea     rcx, [rsp+0D8h+var_80]
0x140188370  call    TxfDereferenceTransaction
0x140188375  mov     [rdi+18h], rsi
0x140188379  mov     [rdi+20h], r15
0x14018837d  lock add [r15+40h], r12d
0x140188382  mov     rax, [rdi+20h]
0x140188386  lock add [rax+30h], r12d
0x14018838b  mov     rcx, r13; Object
0x14018838e  call    cs:__imp_ObfReferenceObject
0x140188395  nop     dword ptr [rax+rax+00h]
0x14018839a  mov     [rdi+28h], r13
0x14018839e  mov     al, cs:NtfsStatusDebugFlags
0x1401883a4  mov     ecx, 0C00000D8h; Status
0x1401883a9  call    cs:__imp_ExRaiseStatus
0x1401883b5  lea     r14, [rdi+0F0h]
0x1401883bc  cmp     qword ptr [r14], 0
0x1401883c0  jnz     loc_140188303
0x1401883c6  mov     rcx, [rdi+18h]
0x1401883ca  add     rcx, 50h ; 'P'; Resource
0x1401883ce  mov     dl, 1; Wait
0x1401883d0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401883d7  nop     dword ptr [rax+rax+00h]
0x1401883dc  mov     [rsp+0D8h+arg_18], 1
0x1401883e4  mov     rcx, [r12+10h]; Resource
0x1401883e9  call    cs:__imp_ExReleaseResourceLite
0x1401883f0  nop     dword ptr [rax+rax+00h]
0x1401883f5  xor     esi, esi
0x1401883f7  mov     [rsp+0D8h+arg_0], sil
0x1401883ff  lock or dword ptr [rdi+10h], 20000h
0x140188407  mov     rcx, [rdi+18h]
0x14018840b  add     rcx, 50h ; 'P'; Resource
0x14018840f  call    cs:__imp_ExReleaseResourceLite
0x140188416  nop     dword ptr [rax+rax+00h]
0x14018841b  mov     [rsp+0D8h+arg_18], sil
0x140188423  mov     [rsp+0D8h+ObjectAttributes.Length], 30h ; '0'
0x14018842b  mov     [rsp+0D8h+ObjectAttributes.RootDirectory], rsi
0x140188430  mov     [rsp+0D8h+ObjectAttributes.Attributes], 200h
0x14018843b  mov     [rsp+0D8h+ObjectAttributes.ObjectName], rsi
0x140188443  xorps   xmm0, xmm0
0x140188446  movdqu  xmmword ptr [rsp+0D8h+ObjectAttributes.SecurityDescriptor], xmm0
0x14018844f  lea     r12, [rdi+0F8h]
0x140188456  mov     [rsp+0D8h+EnlistmentKey], rdi; EnlistmentKey
0x14018845b  mov     [rsp+0D8h+NotificationMask], 20Eh; NotificationMask
0x140188463  mov     [rsp+0D8h+CreateOptions], esi; CreateOptions
0x140188467  mov     [rsp+0D8h+Transaction], r13; Transaction
0x14018846c  mov     rax, [r15+288h]
0x140188473  mov     [rsp+0D8h+ResourceManager], rax; ResourceManager
0x140188478  lea     r9, [rsp+0D8h+ObjectAttributes]; ObjectAttributes
0x14018847d  xor     edx, edx; PreviousMode
0x14018847f  mov     r8d, 0F001Fh; DesiredAccess
0x140188485  mov     rcx, r12; EnlistmentHandle
0x140188488  call    cs:__imp_TmCreateEnlistment
0x14018848f  nop     dword ptr [rax+rax+00h]
0x140188494  mov     esi, eax
0x140188496  mov     [rsp+0D8h+var_84], eax
0x14018849a  mov     rcx, [rdi+18h]
0x14018849e  add     rcx, 50h ; 'P'; Resource
0x1401884a2  mov     dl, 1; Wait
0x1401884a4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401884ab  nop     dword ptr [rax+rax+00h]
0x1401884b0  mov     [rsp+0D8h+arg_18], 1
0x1401884b8  lock and dword ptr [rdi+10h], 0FFFDFFFFh
0x1401884c0  mov     rcx, [rdi+188h]; Event
0x1401884c7  test    rcx, rcx
0x1401884ca  jnz     loc_140188B0A
0x1401884d0  test    esi, esi
0x1401884d2  jns     loc_14018886D
0x1401884d8  mov     al, cs:NtfsStatusDebugFlags
0x1401884de  test    al, al
0x1401884e0  jnz     loc_140188807
0x1401884e6  mov     r14d, 1
0x1401884ec  lock or dword ptr [rdi+10h], 2
0x1401884f1  test    dword ptr [rdi+10h], 200h
0x1401884f8  jnz     loc_140188B20
0x1401884fe  mov     rcx, [rdi+18h]
0x140188502  add     rcx, 50h ; 'P'; Resource
0x140188506  call    cs:__imp_ExReleaseResourceLite
0x14018850d  nop     dword ptr [rax+rax+00h]
0x140188512  mov     [rsp+0D8h+arg_18], 0
0x14018851a  mov     rcx, rdi
0x14018851d  call    TxfRemoveTransactionFromList
0x140188522  mov     rax, [rsp+0D8h+arg_28]
0x14018852a  mov     qword ptr [rax], 0
0x140188531  mov     dl, r14b
0x140188534  lea     rcx, [rsp+0D8h+var_80]
0x140188539  call    TxfDereferenceTransaction
0x14018853e  mov     rdi, [rsp+0D8h+var_80]
0x140188543  jmp     loc_140188233
0x140188548  test    r9, r9
0x14018854b  jz      loc_1401881CA
0x140188551  add     rdx, 100h; Source2
0x140188558  mov     r8d, 10h; Length
0x14018855e  mov     rcx, r9; Source1
0x140188561  call    cs:__imp_RtlCompareMemory
0x140188568  nop     dword ptr [rax+rax+00h]
0x14018856d  cmp     rax, 10h
0x140188571  jnz     loc_1401881CA
0x140188577  jmp     loc_140188255
0x14018857c  test    r9, r9
0x14018857f  jnz     loc_14018819F
0x140188585  test    bl, 8
0x140188588  jz      loc_14018819F
0x14018858e  mov     rax, [r15+2B8h]
0x140188595  test    rax, rax
0x140188598  jz      loc_1401881E3
0x14018859e  mov     rdi, rax
0x1401885a1  mov     [rsp+0D8h+var_80], rax
0x1401885a6  mov     r12b, r14b
0x1401885a9  mov     [rsp+0D8h+var_88], r14b
0x1401885ae  jmp     loc_1401881E3
0x1401885b3  lea     rax, [rsp+0D8h+arg_0]
0x1401885bb  mov     [rsp+0D8h+ResourceManager], rax
0x1401885c0  lea     r12, [r15+90h]
0x1401885c7  mov     r9, r12
0x1401885ca  lea     r8, [rsp+0D8h+arg_18]
0x1401885d2  mov     rdx, rdi
0x1401885d5  mov     rcx, [rsp+0D8h+arg_20]
0x1401885dd  call    TxfWaitForEnlistmentCompletion
0x1401885e2  mov     esi, eax
0x1401885e4  mov     [rsp+0D8h+var_84], eax
0x1401885e8  xor     edi, edi
  ... truncated ...
```
