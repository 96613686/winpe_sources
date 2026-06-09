# IoctlKfdCommitTransaction

- ea: `0x140048db0`
- end: `0x1400494e5`
- name: `IoctlKfdCommitTransaction`
- size: `1845`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x14000c4e0`
- `0x14000c774`
- `0x14000c810`
- `0x14001b820`
- `0x14003ef24`
- `0x140048db0`
- `0x140049674`
- `0x14004efd4`
- `0x140061abc`
- `0x140077fa0`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140048f03`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400490e0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004913b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400493c2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140048f03`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400490e0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004913b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400493c2`
- `ntoskrnl!EtwWriteTransfer` at `0x140049371`
- `ntoskrnl!EtwWriteTransfer` at `0x140049371`
- `ntoskrnl!KeGetCurrentIrql` at `0x140048ec7`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400490a5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140048ec7`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400490a5`
- `NDIS!NdisReleaseRWLock` at `0x140049174`
- `NDIS!NdisReleaseRWLock` at `0x1400493f5`
- `NDIS!NdisReleaseRWLock` at `0x140049174`
- `NDIS!NdisReleaseRWLock` at `0x1400493f5`
- `NDIS!NdisAcquireRWLockWrite` at `0x140048ee5`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400490c3`
- `NDIS!NdisAcquireRWLockWrite` at `0x140048ee5`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400490c3`

## string_xrefs

- `0x140048fc7`: `GetLayerFromIdRead`
- `0x140049003`: `GetLayerFromIdRead`
- `0x140048e32`: `IoctlKfdCommitTransaction`

## pseudocode

```c
__int64 __fastcall IoctlKfdCommitTransaction(__int64 a1, unsigned int a2, _QWORD *a3)
{
  __int64 v3; // r13
  __int64 BatchUpdateContext; // r15
  PNPAGED_LOOKASIDE_LIST v6; // rbx
  int v7; // esi
  KIRQL CurrentIrql; // di
  int v9; // r8d
  __int64 v10; // rdx
  PNPAGED_LOOKASIDE_LIST v11; // rbx
  __int64 v12; // r14
  unsigned __int16 v13; // r12
  __int64 v14; // rcx
  __int16 v15; // ax
  __int64 v16; // rax
  __int64 v17; // rsi
  volatile signed __int32 *v18; // rcx
  PNPAGED_LOOKASIDE_LIST v19; // rdi
  KIRQL v20; // bl
  __int64 v21; // rdx
  PNPAGED_LOOKASIDE_LIST v22; // rbx
  _DWORD *v23; // rdx
  PNPAGED_LOOKASIDE_LIST v24; // rcx
  char *v25; // r9
  char *v26; // rax
  char v27; // cl
  __int64 v30; // rcx
  int v31; // edx
  __int64 v32; // rcx
  _DWORD *v33; // rdx
  __int64 v34; // rcx
  struct _LOCK_STATE_EX v35; // [rsp+30h] [rbp-89h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+34h] [rbp-85h] BYREF
  unsigned int v37; // [rsp+38h] [rbp-81h]
  __int64 v38; // [rsp+40h] [rbp-79h]
  __int16 v39; // [rsp+48h] [rbp-71h] BYREF
  __int64 v40; // [rsp+50h] [rbp-69h] BYREF
  int v41; // [rsp+58h] [rbp-61h]
  unsigned int v42; // [rsp+5Ch] [rbp-5Dh]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-59h] BYREF
  __int64 v44; // [rsp+70h] [rbp-49h] BYREF
  __int64 v45; // [rsp+78h] [rbp-41h]
  _QWORD *v46; // [rsp+80h] [rbp-39h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-29h] BYREF
  char *v48; // [rsp+A0h] [rbp-19h]
  unsigned int v49; // [rsp+A8h] [rbp-11h]
  int v50; // [rsp+ACh] [rbp-Dh]
  __int64 *v51; // [rsp+B0h] [rbp-9h]
  _QWORD v52[3]; // [rsp+B8h] [rbp-1h]

  v3 = a1;
  v45 = a1;
  v46 = a3;
  v40 = 0;
  *a3 = 0;
  v42 = a2;
  BatchUpdateContext = KfdGetBatchUpdateContext(&v40);
  if ( !BatchUpdateContext )
  {
    if ( !*(_QWORD *)v40 )
    {
      LODWORD(BatchUpdateContext) = -1073741811;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"IoctlKfdCommitTransaction",
          13);
      }
      goto LABEL_7;
    }
    v6 = gWfpGlobal;
    v41 = *(_DWORD *)(*(_QWORD *)v40 + 8LL) & 1;
    v7 = 8 * (v41 ^ 1) + 2;
    *(_WORD *)&LockState.OldIrql = 0;
    LockState.Flags = 0;
    v38 = v40 + 20;
    CurrentIrql = KeGetCurrentIrql();
    NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)v6[1].L.ListHead.Alignment, &LockState, 0);
    if ( CurrentIrql != 2 && gWfpPerProContext )
    {
      v10 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      *(_QWORD *)(v10 + 8) = MEMORY[0xFFFFF78000000008];
      *(_DWORD *)v10 = 4;
    }
    gWfpGlobal[11].L.Future[6] = v7;
    v11 = gWfpGlobal;
    v12 = 0;
    v13 = 0;
    if ( *((_WORD *)&gWfpGlobal[3].L.SingleListHead + 4) )
    {
      v14 = v38;
      while ( !*(_BYTE *)(v13 + v14) )
      {
LABEL_71:
        v11 = gWfpGlobal;
        if ( ++v13 >= *((_WORD *)&gWfpGlobal[3].L.SingleListHead + 4) )
        {
          v3 = v45;
          goto LABEL_73;
        }
      }
      if ( v13 >= *((_WORD *)&v11[3].L.SingleListHead + 4) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
        {
          WPP_SF_sd(
            WPP_GLOBAL_Control->AttachedDevice,
            10,
            (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
            (unsigned int)"GetLayerFromIdRead",
            13);
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
        {
          WPP_SF_sd(
            WPP_GLOBAL_Control->AttachedDevice,
            15,
            (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
            (unsigned int)"GetLayerFromIdRead",
            13);
        }
      }
      else
      {
        v12 = v11[3].L.ListHead.Alignment + 136LL * v13;
      }
      *(_WORD *)&v35.OldIrql = 0;
      v35.Flags = 0;
      if ( HIDWORD(gWfpGlobal[1].L.Allocate) )
      {
        v15 = *(_WORD *)(v12 + 8);
        switch ( v15 )
        {
          case ',':
            v16 = 96;
            v17 = 1008;
            goto LABEL_34;
          case '.':
            v16 = 144;
            v17 = 1056;
            goto LABEL_34;
          case '0':
            v16 = 0;
            v17 = 912;
            goto LABEL_34;
          case '2':
            v16 = 48;
            v17 = 960;
LABEL_34:
            v18 = (volatile signed __int32 *)((char *)gWfpGlobal + v16);
            if ( !_InterlockedIncrement((volatile signed __int32 *)((char *)&gWfpGlobal[7].L.SingleListHead + v16 + 8)) )
              _InterlockedIncrement(v18 + 226);
            v19 = gWfpGlobal;
            v20 = KeGetCurrentIrql();
            NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)v19[13].L.ListEntry.Flink, &v35, 0);
            if ( v20 != 2 && gWfpPerProContext )
            {
              v21 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
              *(_QWORD *)(v21 + 8) = MEMORY[0xFFFFF78000000008];
              *(_DWORD *)v21 = 4;
            }
            if ( *(_DWORD *)((char *)&gWfpGlobal->L.ListHead.Alignment + v17) == 1 )
              *(_DWORD *)((char *)&gWfpGlobal->L.ListHead.Alignment + v17) = 3;
            v22 = gWfpGlobal;
            if ( gWfpPerProContext )
            {
              v23 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
              if ( *v23 == 4 )
                *v23 = 0;
            }
            NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v22[13].L.ListEntry.Flink, &v35);
            break;
        }
      }
      if ( !_InterlockedIncrement((volatile signed __int32 *)(v12 + 68)) )
        _InterlockedIncrement((volatile signed __int32 *)(v12 + 68));
      v24 = gWfpGlobal;
      if ( !_InterlockedIncrement((volatile signed __int32 *)&gWfpGlobal[7]) )
        _InterlockedIncrement((volatile signed __int32 *)&v24[7]);
      if ( *(_DWORD *)(v12 + 16) == 1 )
      {
        *(_DWORD *)(v12 + 16) = 3;
        if ( (unsigned int)dword_14009A108 >= 6
          && (qword_14009A118 & 0x400000000000LL) != 0
          && (qword_14009A120 & 0x400000000000LL) == qword_14009A120 )
        {
          v44 = 1;
          v51 = &v44;
          v39 = *(_WORD *)(v12 + 8);
          v52[1] = &v39;
          *(_DWORD *)&EventDescriptor.Level = 5;
          UserData.Ptr = (ULONGLONG)off_14009A110;
          v52[0] = 8;
          v52[2] = 2;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0x400000000000LL;
          UserData.Size = *(unsigned __int16 *)off_14009A110;
          UserData.Reserved = 2;
          v48 = &byte_140090847;
          v49 = 51;
          v50 = 1;
          v37 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_14009A130 == TlgAggregateInternalRegisteredProviderEtwCallback )
          {
            LOBYTE(v9) = 0;
            v25 = &v48[v49];
            v26 = v48 + 2;
            do
              v27 = *v26++;
            while ( v27 < 0 );
            while ( *v26++ )
              ;
            if ( v26 >= v25 )
              goto LABEL_69;
            while ( 1 )
            {
              while ( *v26++ )
                ;
              LODWORD(v30) = (unsigned __int8)*v26;
              if ( (v30 & 0x80u) == 0LL )
                break;
              LOBYTE(v30) = v30 & 0x7F;
              if ( v26[1] >= 0 )
                break;
              v31 = (unsigned __int8)v26[2];
              v26 += 2;
              if ( (v31 & 0x80u) != 0 )
              {
                while ( (_BYTE)v31 == 0x80 )
                {
                  v31 = (unsigned __int8)*++v26;
                  if ( (v31 & 0x80u) == 0 )
                    goto LABEL_64;
                }
                break;
              }
LABEL_64:
              if ( (_BYTE)v30 == 9 )
              {
                LODWORD(v30) = v31 - 113;
                if ( (unsigned __int8)(v31 - 113) <= 2u )
                {
                  v32 = (unsigned __int8)v9;
                  LOBYTE(v9) = v9 + 1;
                  v30 = 2 * v32;
                  BYTE5(v52[v30]) = v31;
                  if ( v26 < v25 )
                    continue;
                }
              }
              break;
            }
            if ( (_BYTE)v9 )
              InsertEventEntryInLookUpTable(v30, (unsigned int)&EventDescriptor, v9, (unsigned int)&UserData, v9);
            else
LABEL_69:
              EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
          }
        }
      }
      v14 = v38;
      goto LABEL_71;
    }
LABEL_73:
    if ( gWfpPerProContext )
    {
      v33 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      if ( *v33 == 4 )
        *v33 = 0;
    }
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v11[1].L.ListHead.Alignment, &LockState);
    BatchUpdateContext = KfdCommitTransaction(v40);
    if ( !BatchUpdateContext )
    {
      if ( v41 )
      {
        KfdDestroyBoottimePolicy();
        HIDWORD(gWfpGlobal[9].L.ListEntry.Flink) = 0;
        gWfpGlobal[9].L.Future[1] = 0;
        gWfpGlobal[9].L.Future[7] = 0;
      }
      BatchUpdateContext = KfdSetVisibleFilterState(8);
      KfdNotifyLayerEvent(2, 0, v40);
      if ( v42 < 0x63 )
        __fastfail(5u);
      v34 = v40;
      *(_OWORD *)v3 = *(_OWORD *)(v40 + 20);
      *(_OWORD *)(v3 + 16) = *(_OWORD *)(v34 + 36);
      *(_OWORD *)(v3 + 32) = *(_OWORD *)(v34 + 52);
      *(_OWORD *)(v3 + 48) = *(_OWORD *)(v34 + 68);
      *(_OWORD *)(v3 + 64) = *(_OWORD *)(v34 + 84);
      *(_OWORD *)(v3 + 80) = *(_OWORD *)(v34 + 100);
      *(_DWORD *)(v3 + 95) = *(_DWORD *)(v34 + 115);
      *v46 = 99;
      KfdFreeBatchUpdateContext();
      if ( !BatchUpdateContext )
      {
        ++gWfpGlobal[11].L.Future[9];
        return (unsigned int)BatchUpdateContext;
      }
    }
  }
LABEL_7:
  ++LODWORD(gWfpGlobal[12].L.ListHead.Alignment);
  return (unsigned int)BatchUpdateContext;
}

```

## disassembly

```asm
0x140048db0  push    rbp
0x140048db2  push    rsi
0x140048db3  push    r13
0x140048db5  push    r15
0x140048db7  lea     rbp, [rsp-3Fh]
0x140048dbc  sub     rsp, 0F8h
0x140048dc3  mov     rax, cs:__security_cookie
0x140048dca  xor     rax, rsp
0x140048dcd  mov     [rbp+57h+var_40], rax
0x140048dd1  mov     r13, rcx
0x140048dd4  mov     [rbp+57h+var_98], rcx
0x140048dd8  xor     ecx, ecx
0x140048dda  mov     [rbp+57h+var_90], r8
0x140048dde  mov     [rbp+57h+var_C0], rcx
0x140048de2  mov     [r8], rcx
0x140048de5  lea     rcx, [rbp+57h+var_C0]
0x140048de9  mov     [rbp+57h+var_B4], edx
0x140048dec  call    KfdGetBatchUpdateContext
0x140048df1  mov     r15, rax
0x140048df4  test    rax, rax
0x140048df7  jnz     short loc_140048E4F
0x140048df9  mov     rcx, [rbp+57h+var_C0]
0x140048dfd  mov     rax, [rcx]
0x140048e00  test    rax, rax
0x140048e03  jnz     short loc_140048E7A
0x140048e05  mov     rcx, cs:WPP_GLOBAL_Control
0x140048e0c  lea     rax, WPP_GLOBAL_Control
0x140048e13  mov     r15, 0FFFFFFFFC000000Dh
0x140048e1a  cmp     rcx, rax
0x140048e1d  jz      short loc_140048E4F
0x140048e1f  cmp     byte ptr [rcx+29h], 2
0x140048e23  jb      short loc_140048E4F
0x140048e25  test    dword ptr [rcx+2Ch], 1000h
0x140048e2c  jz      short loc_140048E4F
0x140048e2e  mov     rcx, [rcx+18h]
0x140048e32  lea     r9, aIoctlkfdcommit; "IoctlKfdCommitTransaction"
0x140048e39  mov     edx, 0Ah
0x140048e3e  mov     [rsp+110h+UserDataCount], r15d
0x140048e43  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140048e4a  call    WPP_SF_sd
0x140048e4f  mov     rax, cs:gWfpGlobal
0x140048e56  inc     dword ptr [rax+600h]
0x140048e5c  mov     eax, r15d
0x140048e5f  mov     rcx, [rbp+57h+var_40]
0x140048e63  xor     rcx, rsp; StackCookie
0x140048e66  call    __security_check_cookie
0x140048e6b  add     rsp, 0F8h
0x140048e72  pop     r15
0x140048e74  pop     r13
0x140048e76  pop     rsi
0x140048e77  pop     rbp
0x140048e78  retn
0x140048e7a  mov     eax, [rax+8]
0x140048e7d  and     eax, 1
0x140048e80  mov     [rsp+110h+arg_8], rbx
0x140048e88  mov     rbx, cs:gWfpGlobal
0x140048e8f  mov     [rbp+57h+var_B8], eax
0x140048e92  xor     eax, 1
0x140048e95  mov     [rsp+110h+var_20], rdi
0x140048e9d  mov     [rsp+110h+var_28], r12
0x140048ea5  mov     [rsp+110h+var_30], r14
0x140048ead  lea     esi, ds:2[rax*8]
0x140048eb4  lea     rax, [rcx+14h]
0x140048eb8  xor     ecx, ecx
0x140048eba  mov     word ptr [rsp+110h+LockState.OldIrql], cx
0x140048ebf  mov     [rsp+110h+LockState.Flags], cl
0x140048ec3  mov     [rbp+57h+var_D0], rax
0x140048ec7  call    cs:__imp_KeGetCurrentIrql
0x140048ece  nop     dword ptr [rax+rax+00h]
0x140048ed3  mov     rcx, [rbx+80h]; Lock
0x140048eda  lea     rdx, [rsp+110h+LockState]; LockState
0x140048edf  xor     r8d, r8d; Flags
0x140048ee2  movzx   edi, al
0x140048ee5  call    cs:__imp_NdisAcquireRWLockWrite
0x140048eec  nop     dword ptr [rax+rax+00h]
0x140048ef1  cmp     dil, 2
0x140048ef5  jz      short loc_140048F37
0x140048ef7  cmp     cs:gWfpPerProContext, 0
0x140048eff  jz      short loc_140048F37
0x140048f01  xor     ecx, ecx; ProcNumber
0x140048f03  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140048f0a  nop     dword ptr [rax+rax+00h]
0x140048f0f  imul    eax, cs:gWfpPerProContextSize
0x140048f16  mov     ecx, eax
0x140048f18  mov     rax, cs:gWfpPerProContext
0x140048f1f  mov     rdx, [rcx+rax]
0x140048f23  mov     rax, ds:0FFFFF78000000008h
0x140048f2d  mov     [rdx+8], rax
0x140048f31  mov     dword ptr [rdx], 4
0x140048f37  mov     rax, cs:gWfpGlobal
0x140048f3e  mov     [rax+5F0h], esi
0x140048f44  xor     esi, esi
0x140048f46  mov     rbx, cs:gWfpGlobal
0x140048f4d  mov     r14d, esi
0x140048f50  mov     r12d, esi
0x140048f53  cmp     si, [rbx+188h]
0x140048f5a  jnb     loc_14004939E
0x140048f60  mov     rcx, [rbp+57h+var_D0]
0x140048f64  lea     rdi, WPP_GLOBAL_Control
0x140048f6b  mov     r15, 0FFFFFFFFC000000Dh
0x140048f72  lea     r13, byte_140090847
0x140048f79  nop     dword ptr [rax+00000000h]
0x140048f80  movzx   eax, r12w
0x140048f84  cmp     byte ptr [rax+rcx], 0
0x140048f88  jz      loc_140049381
0x140048f8e  cmp     r12w, [rbx+188h]
0x140048f96  jnb     short loc_140048FA8
0x140048f98  imul    r14, rax, 88h
0x140048f9f  add     r14, [rbx+180h]
0x140048fa6  jmp     short loc_140049020
0x140048fa8  mov     rcx, cs:WPP_GLOBAL_Control
0x140048faf  cmp     rcx, rdi
0x140048fb2  jz      short loc_140048FE4
0x140048fb4  cmp     byte ptr [rcx+29h], 2
0x140048fb8  jb      short loc_140048FE4
0x140048fba  test    dword ptr [rcx+2Ch], 1000h
0x140048fc1  jz      short loc_140048FE4
0x140048fc3  mov     rcx, [rcx+18h]
0x140048fc7  lea     r9, aGetlayerfromid_0; "GetLayerFromIdRead"
0x140048fce  mov     edx, 0Ah
0x140048fd3  mov     [rsp+110h+UserDataCount], r15d
0x140048fd8  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140048fdf  call    WPP_SF_sd
0x140048fe4  mov     rcx, cs:WPP_GLOBAL_Control
0x140048feb  cmp     rcx, rdi
0x140048fee  jz      short loc_140049020
0x140048ff0  cmp     byte ptr [rcx+29h], 2
0x140048ff4  jb      short loc_140049020
0x140048ff6  test    dword ptr [rcx+2Ch], 1000h
0x140048ffd  jz      short loc_140049020
0x140048fff  mov     rcx, [rcx+18h]
0x140049003  lea     r9, aGetlayerfromid_0; "GetLayerFromIdRead"
0x14004900a  mov     edx, 0Fh
0x14004900f  mov     [rsp+110h+UserDataCount], r15d
0x140049014  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14004901b  call    WPP_SF_sd
0x140049020  mov     rcx, cs:gWfpGlobal
0x140049027  xor     eax, eax
0x140049029  mov     word ptr [rsp+110h+var_E0.OldIrql], ax
0x14004902e  mov     [rsp+110h+var_E0.Flags], al
0x140049032  cmp     [rcx+0B4h], eax
0x140049038  jz      loc_140049187
0x14004903e  movzx   eax, word ptr [r14+8]
0x140049043  cmp     ax, 2Ch ; ','
0x140049047  jz      short loc_140049081
0x140049049  cmp     ax, 2Eh ; '.'
0x14004904d  jz      short loc_140049075
0x14004904f  cmp     ax, 30h ; '0'
0x140049053  jz      short loc_14004906B
0x140049055  cmp     ax, 32h ; '2'
0x140049059  jnz     loc_140049187
0x14004905f  mov     eax, 30h ; '0'
0x140049064  mov     esi, 3C0h
0x140049069  jmp     short loc_14004908B
0x14004906b  mov     rax, rsi
0x14004906e  mov     esi, 390h
0x140049073  jmp     short loc_14004908B
0x140049075  mov     eax, 90h
0x14004907a  mov     esi, 420h
0x14004907f  jmp     short loc_14004908B
0x140049081  mov     eax, 60h ; '`'
0x140049086  mov     esi, 3F0h
0x14004908b  add     rcx, rax
0x14004908e  lock inc dword ptr [rcx+388h]
0x140049095  jnz     short loc_14004909E
0x140049097  lock inc dword ptr [rcx+388h]
0x14004909e  mov     rdi, cs:gWfpGlobal
0x1400490a5  call    cs:__imp_KeGetCurrentIrql
0x1400490ac  nop     dword ptr [rax+rax+00h]
0x1400490b1  mov     rcx, [rdi+6C0h]; Lock
0x1400490b8  lea     rdx, [rsp+110h+var_E0]; LockState
0x1400490bd  xor     r8d, r8d; Flags
0x1400490c0  movzx   ebx, al
0x1400490c3  call    cs:__imp_NdisAcquireRWLockWrite
0x1400490ca  nop     dword ptr [rax+rax+00h]
0x1400490cf  cmp     bl, 2
0x1400490d2  jz      short loc_140049114
0x1400490d4  cmp     cs:gWfpPerProContext, 0
0x1400490dc  jz      short loc_140049114
0x1400490de  xor     ecx, ecx; ProcNumber
0x1400490e0  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400490e7  nop     dword ptr [rax+rax+00h]
0x1400490ec  imul    eax, cs:gWfpPerProContextSize
0x1400490f3  mov     ecx, eax
0x1400490f5  mov     rax, cs:gWfpPerProContext
0x1400490fc  mov     rdx, [rcx+rax]
0x140049100  mov     rax, ds:0FFFFF78000000008h
0x14004910a  mov     [rdx+8], rax
0x14004910e  mov     dword ptr [rdx], 4
0x140049114  mov     rax, cs:gWfpGlobal
0x14004911b  cmp     dword ptr [rsi+rax], 1
0x14004911f  jnz     short loc_140049128
0x140049121  mov     dword ptr [rsi+rax], 3
0x140049128  cmp     cs:gWfpPerProContext, 0
0x140049130  mov     rbx, cs:gWfpGlobal
0x140049137  jz      short loc_140049166
0x140049139  xor     ecx, ecx; ProcNumber
0x14004913b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140049142  nop     dword ptr [rax+rax+00h]
0x140049147  imul    eax, cs:gWfpPerProContextSize
0x14004914e  xor     esi, esi
0x140049150  mov     ecx, eax
0x140049152  mov     rax, cs:gWfpPerProContext
0x140049159  mov     rdx, [rcx+rax]
0x14004915d  cmp     dword ptr [rdx], 4
0x140049160  jnz     short loc_140049168
0x140049162  mov     [rdx], esi
0x140049164  jmp     short loc_140049168
0x140049166  xor     esi, esi
0x140049168  mov     rcx, [rbx+6C0h]; Lock
0x14004916f  lea     rdx, [rsp+110h+var_E0]; LockState
0x140049174  call    cs:__imp_NdisReleaseRWLock
0x14004917b  nop     dword ptr [rax+rax+00h]
0x140049180  lea     rdi, WPP_GLOBAL_Control
0x140049187  lock inc dword ptr [r14+44h]
0x14004918c  jnz     short loc_140049193
0x14004918e  lock inc dword ptr [r14+44h]
0x140049193  mov     rcx, cs:gWfpGlobal
0x14004919a  lock inc dword ptr [rcx+380h]
0x1400491a1  jnz     short loc_1400491AA
0x1400491a3  lock inc dword ptr [rcx+380h]
0x1400491aa  cmp     dword ptr [r14+10h], 1
0x1400491af  jnz     loc_14004937D
0x1400491b5  mov     dword ptr [r14+10h], 3
0x1400491bd  mov     eax, cs:dword_14009A108
0x1400491c3  test    eax, eax
0x1400491c5  jz      loc_14004937D
0x1400491cb  mov     eax, cs:dword_14009A108
0x1400491d1  cmp     eax, 5
0x1400491d4  jbe     loc_14004937D
0x1400491da  mov     rcx, cs:qword_14009A120
0x1400491e1  mov     rdx, 400000000000h
0x1400491eb  mov     rax, cs:qword_14009A118
0x1400491f2  test    rdx, rax
0x1400491f5  jz      loc_14004937D
0x1400491fb  mov     rax, rcx
0x1400491fe  and     rax, rdx
0x140049201  cmp     rax, rcx
0x140049204  jnz     loc_14004937D
0x14004920a  lea     rax, [rbp+57h+var_A0]
0x14004920e  mov     [rbp+57h+var_A0], 1
0x140049216  mov     [rbp+57h+var_60], rax
0x14004921a  lea     rcx, _TraceLoggingMetadata
0x140049221  movzx   eax, word ptr [r14+8]
0x140049226  mov     [rbp+57h+var_C8], ax
0x14004922a  lea     rax, [rbp+57h+var_C8]
0x14004922e  mov     [rbp+57h+var_50], rax
0x140049232  movzx   eax, cs:word_14009083D
0x140049239  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x14004923c  mov     rax, cs:off_14009A110; ":"
0x140049243  mov     [rbp+57h+var_80.Ptr], rax
0x140049247  mov     [rbp+57h+var_58], 8
0x14004924f  mov     [rbp+57h+var_48], 2
0x140049257  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x14004925e  mov     [rbp+57h+EventDescriptor.Keyword], rdx
0x140049262  movzx   eax, word ptr [rax]
0x140049265  mov     [rbp+57h+var_80.Size], eax
0x140049268  lea     rax, _TraceLoggingMetadataEnd
0x14004926f  sub     eax, ecx
0x140049271  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x140049278  mov     [rbp+57h+var_70], r13
0x14004927c  mov     [rbp+57h+var_68], 33h ; '3'
0x140049283  mov     [rbp+57h+var_64], 1
0x14004928a  mov     [rsp+110h+var_D8], eax
0x14004928e  mov     eax, [rsp+110h+var_D8]
0x140049292  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x140049299  cmp     cs:qword_14009A130, rax
0x1400492a0  jnz     loc_14004937D
0x1400492a6  mov     rax, [rbp+57h+var_70]
0x1400492aa  xor     r8b, r8b
0x1400492ad  mov     r9d, [rbp+57h+var_68]
0x1400492b1  add     r9, rax
0x1400492b4  add     rax, 2
0x1400492b8  nop     dword ptr [rax+rax+00000000h]
0x1400492c0  movzx   ecx, byte ptr [rax]
0x1400492c3  inc     rax
0x1400492c6  test    cl, cl
0x1400492c8  js      short loc_1400492C0
0x1400492ca  nop     word ptr [rax+rax+00h]
0x1400492d0  movzx   ecx, byte ptr [rax]
0x1400492d3  inc     rax
0x1400492d6  test    cl, cl
0x1400492d8  jnz     short loc_1400492D0
0x1400492da  cmp     rax, r9
0x1400492dd  jnb     short loc_14004934F
0x1400492df  nop
0x1400492e0  movzx   ecx, byte ptr [rax]
0x1400492e3  inc     rax
0x1400492e6  test    cl, cl
0x1400492e8  jnz     short loc_1400492E0
0x1400492ea  movzx   ecx, byte ptr [rax]
0x1400492ed  test    cl, cl
0x1400492ef  jns     short loc_140049336
0x1400492f1  and     cl, 7Fh
0x1400492f4  cmp     byte ptr [rax+1], 0
0x1400492f8  jge     short loc_140049336
0x1400492fa  movzx   edx, byte ptr [rax+2]
0x1400492fe  add     rax, 2
0x140049302  test    dl, dl
0x140049304  jns     short loc_140049316
  ... truncated ...
```
