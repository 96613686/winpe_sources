# WskProTLEVENTConnect

- ea: `0x140015ff0`
- end: `0x1400166b6`
- name: `WskProTLEVENTConnect`
- size: `1734`
- prototype: `NTSTATUS __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140005b60`
- `0x140010948`
- `0x140013990`
- `0x1400147d0`
- `0x140015ff0`
- `0x140026380`
- `0x140026dd0`
- `0x14005fe38`
- `0x1400726a0`
- `0x140072780`
- `0x140072800`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140016573`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140016573`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400165a5`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400166a5`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400165a5`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400166a5`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400160da`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140016623`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140016688`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400160da`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140016623`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140016688`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001610b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400165d9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400165f7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001663c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140076504`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001610b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400165d9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400165f7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001663c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140076504`
- `ntoskrnl!KeInitializeSpinLock` at `0x140016187`
- `ntoskrnl!KeInitializeSpinLock` at `0x140016187`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400763b2`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400763b2`
- `ntoskrnl!IofCompleteRequest` at `0x140016410`
- `ntoskrnl!IofCompleteRequest` at `0x140016410`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400763a2`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400763a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016424`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140076448`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140076494`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016424`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140076448`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140076494`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14001607d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14001607d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016440`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007637e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140076433`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007646c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400764e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016440`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007637e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140076433`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007646c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400764e9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140016146`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140016146`
- `NETIO!NmrClientDetachProviderComplete` at `0x140016656`
- `NETIO!NmrClientDetachProviderComplete` at `0x140016656`

## pseudocode

```c
NTSTATUS __fastcall WskProTLEVENTConnect(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rsi
  struct _KPROCESS *v5; // rcx
  char *v6; // rbx
  _WORD *v7; // rax
  _WORD *v8; // rbx
  char v9; // r13
  KIRQL v10; // r12
  unsigned __int8 v11; // r13
  _QWORD *v12; // r15
  KSPIN_LOCK *v13; // rcx
  _QWORD *v14; // rax
  KSPIN_LOCK *v15; // rcx
  char *v16; // rsi
  struct _KPROCESS *v17; // rcx
  NTSTATUS result; // eax
  __int64 v19; // rcx
  __int64 v20; // r9
  __int64 v21; // rdx
  char v22; // r12
  __int64 (__fastcall *v23)(PVOID, int); // rcx
  int v24; // esi
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // r14
  int v28; // ebx
  KIRQL v29; // r14
  _WORD *v30; // rcx
  __int64 v31; // rcx
  struct _KPROCESS *v32; // rcx
  KSPIN_LOCK *v33; // rcx
  KSPIN_LOCK *v34; // rcx
  KSPIN_LOCK *v35; // rcx
  __int64 v36; // rax
  void *v37; // rsi
  UCHAR v38; // al
  const void *v39; // rdx
  void *v40; // r9
  UCHAR v41; // al
  const void *v42; // rdx
  KIRQL v43; // al
  KIRQL v45; // dl
  KIRQL v46; // [rsp+40h] [rbp-69h] BYREF
  KIRQL Irql; // [rsp+41h] [rbp-68h] BYREF
  char v48; // [rsp+42h] [rbp-67h]
  _QWORD v49[2]; // [rsp+50h] [rbp-59h] BYREF
  int v50; // [rsp+60h] [rbp-49h]
  int v51; // [rsp+64h] [rbp-45h]
  __int64 v52; // [rsp+68h] [rbp-41h]
  int *v53; // [rsp+70h] [rbp-39h]
  __int64 v54; // [rsp+78h] [rbp-31h]
  __int128 v55; // [rsp+80h] [rbp-29h]
  __int128 v56; // [rsp+90h] [rbp-19h]
  __int64 (__fastcall *v57)(PVOID, int); // [rsp+A0h] [rbp-9h] BYREF
  _WORD *v58; // [rsp+A8h] [rbp-1h]
  _WORD *v59; // [rsp+B0h] [rbp+7h] BYREF
  __int64 v60; // [rsp+B8h] [rbp+Fh]

  v2 = (_QWORD *)(a1 + 80);
  if ( (_QWORD *)*v2 == v2 && ((*(_WORD *)(a1 + 32) | *(_WORD *)(a1 + 34)) & 0x200) == 0 )
    return -1073741616;
  v5 = *(struct _KPROCESS **)(a1 + 168);
  if ( !v5 || (result = PsChargeProcessPoolQuota(v5, (POOL_TYPE)512, 0xC8u), result >= 0) )
  {
    v6 = (char *)WskProPplSocket + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
    if ( !v6[176] )
      PplpLazyInitializeLookasideList((__int64)WskProPplSocket, (__int64)(v6 + 64));
    v7 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v6 + 64));
    v8 = v7;
    if ( v7 )
    {
      v9 = *(_BYTE *)(a2 + 72);
      v10 = 0;
      v46 = 0;
      v48 = 0;
      v11 = v9 & 1;
      v12 = 0;
      memset(v7, 0, 0xC8u);
      if ( !_bittest16((const signed __int16 *)(a1 + 32), 9u) || (_QWORD *)*v2 != v2 )
      {
        v13 = (KSPIN_LOCK *)(a1 + 16);
        if ( v11 )
        {
          KeAcquireSpinLockAtDpcLevel(v13);
        }
        else
        {
          v10 = KeAcquireSpinLockRaiseToDpc(v13);
          v46 = v10;
        }
        v14 = (_QWORD *)*v2;
        if ( (_QWORD *)*v2 == v2 )
        {
          v15 = (KSPIN_LOCK *)(a1 + 16);
          if ( !_bittest16((const signed __int16 *)(a1 + 34), 9u) )
          {
            if ( v11 )
              KeReleaseSpinLockFromDpcLevel(v15);
            else
              KeReleaseSpinLock(v15, v10);
            v16 = (char *)WskProPplSocket + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
            if ( !v16[176] )
              PplpLazyInitializeLookasideList((__int64)WskProPplSocket, (__int64)(v16 + 64));
            ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v16 + 64), v8);
            v17 = *(struct _KPROCESS **)(a1 + 168);
            if ( v17 )
              PsReturnPoolQuota(v17, (POOL_TYPE)512, 0xC8u);
            return -1073741616;
          }
          ++*(_DWORD *)(a1 + 96);
          if ( v11 )
            KeReleaseSpinLockFromDpcLevel(v15);
          else
            KeReleaseSpinLock(v15, v10);
          v48 = 1;
        }
        else
        {
          if ( (_QWORD *)v14[1] != v2 || (v31 = *v14, *(_QWORD **)(*v14 + 8LL) != v14) )
            __fastfail(3u);
          *v2 = v31;
          v12 = v14 - 21;
          *(_QWORD *)(v31 + 8) = v2;
          v33 = (KSPIN_LOCK *)(a1 + 16);
          *v14 = 0;
          if ( v11 )
            KeReleaseSpinLockFromDpcLevel(v33);
          else
            KeReleaseSpinLock(v33, v10);
          if ( !_InterlockedExchange64(v12 + 13, 0) && *((_BYTE *)v12 + 68) )
          {
            Irql = 0;
            IoAcquireCancelSpinLock(&Irql);
            IoReleaseCancelSpinLock(Irql);
          }
          v36 = v12[23];
          v37 = *(void **)(v36 + 32);
          if ( *(_QWORD *)(v36 + 24) )
          {
            v38 = SOCKADDR_SIZE(**(_WORD **)(a2 + 16));
            memmove(v40, v39, v38);
          }
          if ( v37 )
          {
            v41 = SOCKADDR_SIZE(**(_WORD **)(a2 + 24));
            memmove(v37, v42, v41);
          }
          *((_QWORD *)v8 + 8) = v12[15];
          *((_QWORD *)v8 + 9) = v12[16];
          v12[7] = v8 + 12;
          *((_DWORD *)v12 + 12) = 0;
        }
      }
      *v8 = -21278;
      *((_BYTE *)v8 + 2) = 2;
      *((_DWORD *)v8 + 2) = 1;
      *((_DWORD *)v8 + 3) = 1;
      KeInitializeSpinLock((PKSPIN_LOCK)v8 + 2);
      *((_QWORD *)v8 + 3) = &WskProAPIConnectionSocketDispatch;
      *((_QWORD *)v8 + 6) = *(_QWORD *)(a1 + 48);
      *((_QWORD *)v8 + 20) = *(_QWORD *)(a1 + 160);
      *((_QWORD *)v8 + 16) = v8 + 60;
      *((_QWORD *)v8 + 15) = v8 + 60;
      *((_QWORD *)v8 + 21) = *(_QWORD *)(a1 + 168);
      v8[92] = *(_WORD *)(a1 + 184);
      if ( (*(_DWORD *)(a1 + 4) & 0x4000) != 0 )
        *((_OWORD *)v8 + 6) = *(_OWORD *)a2;
      *((_QWORD *)v8 + 11) = a1;
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
      *((_QWORD *)v8 + 5) = *(_QWORD *)(a2 + 32);
      v21 = 208;
      *((_QWORD *)v8 + 7) = *(_QWORD *)(a2 + 40);
      *(_QWORD *)(a2 + 64) = WskProTLClientConnectDispatch;
      *(_QWORD *)(a2 + 56) = v8;
      LOWORD(v21) = *(_WORD *)(*(_QWORD *)(a1 + 160) + 74LL) & 0xD0;
      v8[16] = v21;
      if ( !v12 )
      {
        v19 = *(unsigned __int16 *)(a1 + 34);
        LOWORD(v19) = ~(_WORD)v21 & v19 & 0xD0;
        v8[17] = v19;
      }
      if ( (v21 & 0x10) != 0 || (v22 = 0, (v8[17] & 0x10) != 0) )
      {
        _InterlockedIncrement((volatile signed __int32 *)v8 + 3);
        v22 = 1;
      }
      if ( v12 )
      {
        if ( Microsoft_Windows_Networking_CorrelationEnabled )
        {
          v60 = 0;
          v59 = v12;
          EtwEx_tidActivityInfo(v19, &ActivityStart, &v59, v20, 2);
        }
        v30 = *(_WORD **)(a2 + 48);
        v60 = 0;
        v58 = 0;
        if ( Microsoft_Windows_Networking_CorrelationEnabled )
        {
          v57 = (__int64 (__fastcall *)(PVOID, int))v12;
          v59 = v30;
          EtwEx_tidActivityInfoTransfer(v30, v21, &v57, &v59);
        }
        IofCompleteRequest((PIRP)v12, 2);
        v24 = 0;
      }
      else
      {
        if ( Microsoft_Windows_Networking_CorrelationEnabled )
        {
          v58 = 0;
          v57 = (__int64 (__fastcall *)(PVOID, int))(v8 + 12);
          EtwEx_tidActivityInfo(v19, &ActivityStart, &v57, v20, 4);
        }
        v23 = *(__int64 (__fastcall **)(PVOID, int))(a2 + 48);
        v58 = 0;
        v60 = 0;
        if ( Microsoft_Windows_Networking_CorrelationEnabled )
        {
          v59 = v8 + 12;
          v57 = v23;
          EtwEx_tidActivityInfoTransfer(v23, v21, &v59, &v57);
        }
        v24 = (**(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD, _QWORD, __int64, __int64, __int64))(a1 + 72))(
                *(_QWORD *)(a1 + 64),
                8 * (unsigned int)v11,
                *(_QWORD *)(a2 + 16),
                *(_QWORD *)(a2 + 24),
                (__int64)(v8 + 12),
                (__int64)(v8 + 32),
                (__int64)(v8 + 36));
        if ( v24 == -1073741616 )
        {
          v34 = (KSPIN_LOCK *)(v8 + 8);
          if ( v11 )
          {
            KeAcquireSpinLockAtDpcLevel(v34);
            *((_DWORD *)v8 + 1) |= 0x10u;
            *((_DWORD *)v8 + 8) = 0;
            KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v8 + 2);
            v29 = v46;
          }
          else
          {
            v43 = KeAcquireSpinLockRaiseToDpc(v34);
            *((_DWORD *)v8 + 1) |= 0x10u;
            v29 = v43;
            v46 = v43;
            *((_DWORD *)v8 + 8) = 0;
            KeReleaseSpinLock((PKSPIN_LOCK)v8 + 2, v43);
          }
          if ( v22 )
            WskProReleaseTLEndpoint(v8);
          WskProCoreCloseSocket(v8);
          v24 = 0;
LABEL_42:
          if ( !v48 )
            return v24;
          v35 = (KSPIN_LOCK *)(a1 + 16);
          if ( v11 )
          {
            KeAcquireSpinLockAtDpcLevel(v35);
          }
          else
          {
            v29 = KeAcquireSpinLockRaiseToDpc(v35);
            v46 = v29;
          }
          if ( (*(_DWORD *)(a1 + 96))-- == 1 )
          {
            if ( *(_QWORD *)(a1 + 112) )
            {
              if ( (unsigned __int8)WskProCompleteCallbackDisableIrps(a1, 512, &v46, v11) )
                return v24;
              if ( !v11 )
              {
                v45 = v46;
LABEL_93:
                KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 16), v45);
                return v24;
              }
LABEL_95:
              KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 16));
              return v24;
            }
            if ( v11 )
              goto LABEL_95;
          }
          else if ( v11 )
          {
            goto LABEL_95;
          }
          v45 = v29;
          goto LABEL_93;
        }
      }
      if ( v22 )
      {
        if ( ((*((_BYTE *)v8 + 32) | *((_BYTE *)v8 + 34)) & 0x10) != 0 )
        {
          v25 = *((_QWORD *)v8 + 5);
          v49[0] = AfdTLDontCareIOCompletion;
          v52 = 52;
          v53 = &AfdTLSockOptEnable;
          v26 = *((_QWORD *)v8 + 7);
          v55 = 0;
          v56 = 0;
          v49[1] = v8;
          v50 = 0;
          v51 = 65533;
          v54 = 4;
          (*(void (__fastcall **)(__int64, _QWORD *))(v26 + 8))(v25, v49);
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 3, 0xFFFFFFFF) == 1 )
        {
          v27 = *((_QWORD *)v8 + 6);
          v57 = WskProTLCloseEndpointComplete;
          v58 = v8;
          _InterlockedAdd((volatile signed __int32 *)(v27 + 16), 2u);
          v28 = (**((__int64 (__fastcall ***)(_QWORD, _QWORD))v8 + 7))(*((_QWORD *)v8 + 5), &v57);
          if ( (__int64 *)v27 != WskTdiTransport
            && _InterlockedExchangeAdd((volatile signed __int32 *)(v27 + 16), 0xFFFFFFFE) == 3 )
          {
            NmrClientDetachProviderComplete(*(HANDLE *)(v27 + 64));
          }
          if ( v28 != 259 )
            v57(v58, v28);
        }
      }
      v29 = v46;
      goto LABEL_42;
    }
    v32 = *(struct _KPROCESS **)(a1 + 168);
    if ( v32 )
      PsReturnPoolQuota(v32, (POOL_TYPE)512, 0xC8u);
    return -1073741670;
  }
  return result;
}

```

## disassembly

```asm
0x140015ff0  mov     [rsp-8+arg_10], rbx
0x140015ff5  push    rbp
0x140015ff6  push    rsi
0x140015ff7  push    rdi
0x140015ff8  push    r12
0x140015ffa  push    r13
0x140015ffc  push    r14
0x140015ffe  push    r15
0x140016000  lea     rbp, [rsp-27h]
0x140016005  sub     rsp, 0D0h
0x14001600c  mov     rax, cs:__security_cookie
0x140016013  xor     rax, rsp
0x140016016  mov     [rbp+57h+var_40], rax
0x14001601a  lea     rsi, [rcx+50h]
0x14001601e  mov     r14, rdx
0x140016021  mov     rdi, rcx
0x140016024  mov     r15d, 200h
0x14001602a  cmp     [rsi], rsi
0x14001602d  jnz     short loc_140016041
0x14001602f  movzx   ecx, word ptr [rcx+22h]
0x140016033  or      cx, [rdi+20h]
0x140016037  test    r15w, cx
0x14001603b  jz      loc_140016162
0x140016041  mov     rcx, [rdi+0A8h]; Process
0x140016048  test    rcx, rcx
0x14001604b  jnz     loc_14001656A
0x140016051  mov     eax, gs:1A4h
0x140016059  mov     r8, cs:WskProPplSocket
0x140016060  lea     ebx, [rax+1]
0x140016063  shl     rbx, 7
0x140016067  add     rbx, r8
0x14001606a  movzx   eax, byte ptr [rbx+0B0h]
0x140016071  test    al, al
0x140016073  jz      loc_14001646B
0x140016079  lea     rcx, [rbx+40h]; Lookaside
0x14001607d  call    cs:__imp_ExAllocateFromLookasideListEx
0x140016084  nop     dword ptr [rax+rax+00h]
0x140016089  mov     rbx, rax
0x14001608c  test    rax, rax
0x14001608f  jz      loc_14001658C
0x140016095  movzx   r13d, byte ptr [r14+48h]
0x14001609a  xor     r12b, r12b
0x14001609d  xor     edx, edx; Val
0x14001609f  mov     [rbp+57h+var_C0], r12b
0x1400160a3  mov     r8d, 0C8h; Size
0x1400160a9  mov     [rbp+57h+var_BE], 0
0x1400160ad  mov     rcx, rax; void *
0x1400160b0  and     r13b, 1
0x1400160b4  xor     r15d, r15d
0x1400160b7  call    memset
0x1400160bc  bt      word ptr [rdi+20h], 9
0x1400160c2  jnb     short loc_1400160CD
0x1400160c4  cmp     [rsi], rsi
0x1400160c7  jz      loc_14001616C
0x1400160cd  lea     rcx, [rdi+10h]; SpinLock
0x1400160d1  test    r13b, r13b
0x1400160d4  jz      loc_140016424
0x1400160da  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400160e1  nop     dword ptr [rax+rax+00h]
0x1400160e6  mov     rax, [rsi]
0x1400160e9  cmp     rax, rsi
0x1400160ec  jnz     loc_140016451
0x1400160f2  bt      word ptr [rdi+22h], 9
0x1400160f8  lea     rcx, [rdi+10h]; SpinLock
0x1400160fc  jb      loc_1400165EB
0x140016102  test    r13b, r13b
0x140016105  jz      loc_14001643C
0x14001610b  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140016112  nop     dword ptr [rax+rax+00h]
0x140016117  mov     eax, gs:1A4h
0x14001611f  mov     rcx, cs:WskProPplSocket
0x140016126  lea     esi, [rax+1]
0x140016129  shl     rsi, 7
0x14001612d  add     rsi, rcx
0x140016130  movzx   eax, byte ptr [rsi+0B0h]
0x140016137  test    al, al
0x140016139  jz      loc_14001648E
0x14001613f  mov     rdx, rbx; Entry
0x140016142  lea     rcx, [rsi+40h]; Lookaside
0x140016146  call    cs:__imp_ExFreeToLookasideListEx
0x14001614d  nop     dword ptr [rax+rax+00h]
0x140016152  mov     rcx, [rdi+0A8h]; Process
0x140016159  test    rcx, rcx
0x14001615c  jnz     loc_14001669A
0x140016162  mov     eax, 0C00000D0h
0x140016167  jmp     loc_1400163BE
0x14001616c  mov     word ptr [rbx], 0ACE2h
0x140016171  lea     rcx, [rbx+10h]; SpinLock
0x140016175  mov     byte ptr [rbx+2], 2
0x140016179  mov     dword ptr [rbx+8], 1
0x140016180  mov     dword ptr [rbx+0Ch], 1
0x140016187  call    cs:__imp_KeInitializeSpinLock
0x14001618e  nop     dword ptr [rax+rax+00h]
0x140016193  lea     rax, WskProAPIConnectionSocketDispatch
0x14001619a  mov     [rbx+18h], rax
0x14001619e  lea     rsi, [rbx+18h]
0x1400161a2  mov     rax, [rdi+30h]
0x1400161a6  mov     [rbx+30h], rax
0x1400161aa  mov     rax, [rdi+0A0h]
0x1400161b1  mov     [rbx+0A0h], rax
0x1400161b8  lea     rax, [rbx+78h]
0x1400161bc  mov     [rax+8], rax
0x1400161c0  mov     [rax], rax
0x1400161c3  mov     rax, [rdi+0A8h]
0x1400161ca  mov     [rbx+0A8h], rax
0x1400161d1  movzx   eax, word ptr [rdi+0B8h]
0x1400161d8  mov     [rbx+0B8h], ax
0x1400161df  test    dword ptr [rdi+4], 4000h
0x1400161e6  jnz     loc_140016609
0x1400161ec  mov     [rbx+58h], rdi
0x1400161f0  lock inc dword ptr [rdi+8]
0x1400161f4  mov     rax, [r14+20h]
0x1400161f8  mov     r8d, 0D0h
0x1400161fe  mov     [rbx+28h], rax
0x140016202  mov     edx, r8d
0x140016205  mov     rax, [r14+28h]
0x140016209  mov     [rbx+38h], rax
0x14001620d  lea     rax, WskProTLClientConnectDispatch
0x140016214  mov     [r14+40h], rax
0x140016218  mov     [r14+38h], rbx
0x14001621c  mov     rax, [rdi+0A0h]
0x140016223  and     dx, [rax+4Ah]
0x140016227  mov     [rbx+20h], dx
0x14001622b  test    r15, r15
0x14001622e  jnz     short loc_140016245
0x140016230  movzx   ecx, word ptr [rdi+22h]
0x140016234  movzx   eax, dx
0x140016237  not     ax
0x14001623a  and     cx, ax
0x14001623d  and     cx, r8w
0x140016241  mov     [rbx+22h], cx
0x140016245  test    dl, 10h
0x140016248  jz      loc_14001647C
0x14001624e  lock inc dword ptr [rbx+0Ch]
0x140016252  mov     r12b, 1
0x140016255  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14001625b  test    r15, r15
0x14001625e  jnz     loc_1400163E6
0x140016264  test    eax, eax
0x140016266  jnz     loc_1400164CC
0x14001626c  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140016272  mov     rcx, [r14+30h]
0x140016276  mov     [rbp+57h+var_58], 0
0x14001627e  mov     [rbp+57h+var_48], 0
0x140016286  test    eax, eax
0x140016288  jnz     loc_14001649C
0x14001628e  mov     rax, [rdi+48h]
0x140016292  lea     rcx, [rbx+48h]
0x140016296  mov     r8, [r14+10h]
0x14001629a  lea     r9, [rbx+40h]
0x14001629e  mov     [rsp+100h+var_D0], rcx
0x1400162a3  mov     rcx, [rdi+40h]
0x1400162a7  mov     rax, [rax]
0x1400162aa  mov     [rsp+100h+var_D8], r9
0x1400162af  mov     r9, [r14+18h]
0x1400162b3  movzx   edx, r13b
0x1400162b7  shl     edx, 3
0x1400162ba  mov     [rsp+100h+var_E0], rsi
0x1400162bf  call    _guard_dispatch_icall
0x1400162c4  mov     esi, eax
0x1400162c6  cmp     eax, 0C00000D0h
0x1400162cb  jz      loc_140016616
0x1400162d1  xor     r14d, r14d
0x1400162d4  test    r12b, r12b
0x1400162d7  jz      loc_1400163AD
0x1400162dd  movzx   ecx, byte ptr [rbx+22h]
0x1400162e1  or      cl, [rbx+20h]
0x1400162e4  test    cl, 10h
0x1400162e7  jz      short loc_140016343
0x1400162e9  mov     rcx, [rbx+28h]
0x1400162ed  lea     rax, AfdTLDontCareIOCompletion
0x1400162f4  mov     [rbp+57h+var_B0], rax
0x1400162f8  lea     rdx, [rbp+57h+var_B0]
0x1400162fc  lea     rax, AfdTLSockOptEnable
0x140016303  mov     [rbp+57h+var_98], 34h ; '4'
0x14001630b  mov     [rbp+57h+var_90], rax
0x14001630f  xorps   xmm0, xmm0
0x140016312  mov     rax, [rbx+38h]
0x140016316  xorps   xmm1, xmm1
0x140016319  movdqa  [rbp+57h+var_80], xmm0
0x14001631e  movdqa  [rbp+57h+var_70], xmm1
0x140016323  mov     [rbp+57h+var_A8], rbx
0x140016327  mov     [rbp+57h+var_A0], r14d
0x14001632b  mov     [rbp+57h+var_9C], 0FFFDh
0x140016332  mov     [rbp+57h+var_88], 4
0x14001633a  mov     rax, [rax+8]
0x14001633e  call    _guard_dispatch_icall
0x140016343  mov     eax, 0FFFFFFFFh
0x140016348  lock xadd [rbx+0Ch], eax
0x14001634d  cmp     eax, 1
0x140016350  jnz     short loc_1400163AD
0x140016352  mov     r14, [rbx+30h]
0x140016356  lea     rax, WskProTLCloseEndpointComplete
0x14001635d  mov     [rbp+57h+var_60], rax
0x140016361  mov     [rbp+57h+var_58], rbx
0x140016365  lock add dword ptr [r14+10h], 2
0x14001636b  mov     rax, [rbx+38h]
0x14001636f  lea     rdx, [rbp+57h+var_60]
0x140016373  mov     rcx, [rbx+28h]
0x140016377  mov     rax, [rax]
0x14001637a  call    _guard_dispatch_icall
0x14001637f  mov     ebx, eax
0x140016381  lea     rax, WskTdiTransport
0x140016388  cmp     r14, rax
0x14001638b  jz      short loc_1400163A1
0x14001638d  mov     ecx, 0FFFFFFFEh
0x140016392  lock xadd [r14+10h], ecx
0x140016398  cmp     ecx, 3
0x14001639b  jz      loc_140016652
0x1400163a1  cmp     ebx, 103h
0x1400163a7  jnz     loc_140016667
0x1400163ad  movzx   r14d, [rbp+57h+var_C0]
0x1400163b2  cmp     [rbp+57h+var_BE], 0
0x1400163b6  jnz     loc_14001667B
0x1400163bc  mov     eax, esi
0x1400163be  mov     rcx, [rbp+57h+var_40]
0x1400163c2  xor     rcx, rsp; StackCookie
0x1400163c5  call    __security_check_cookie
0x1400163ca  mov     rbx, [rsp+100h+arg_10]
0x1400163d2  add     rsp, 0D0h
0x1400163d9  pop     r15
0x1400163db  pop     r14
0x1400163dd  pop     r13
0x1400163df  pop     r12
0x1400163e1  pop     rdi
0x1400163e2  pop     rsi
0x1400163e3  pop     rbp
0x1400163e4  retn
0x1400163e6  test    eax, eax
0x1400163e8  jnz     loc_140016533
0x1400163ee  mov     rcx, [r14+30h]
0x1400163f2  xor     r14d, r14d
0x1400163f5  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400163fb  mov     [rbp+57h+var_48], r14
0x1400163ff  mov     [rbp+57h+var_58], r14
0x140016403  test    eax, eax
0x140016405  jnz     loc_140016503
0x14001640b  mov     dl, 2; PriorityBoost
0x14001640d  mov     rcx, r15; Irp
0x140016410  call    cs:__imp_IofCompleteRequest
0x140016417  nop     dword ptr [rax+rax+00h]
0x14001641c  mov     esi, r14d
0x14001641f  jmp     loc_1400162D4
0x140016424  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001642b  nop     dword ptr [rax+rax+00h]
0x140016430  movzx   r12d, al
0x140016434  mov     [rbp+57h+var_C0], al
0x140016437  jmp     loc_1400160E6
0x14001643c  movzx   edx, r12b; NewIrql
0x140016440  call    cs:__imp_KeReleaseSpinLock
0x140016447  nop     dword ptr [rax+rax+00h]
0x14001644c  jmp     loc_140016117
0x140016451  cmp     [rax+8], rsi
0x140016455  jnz     short loc_140016464
0x140016457  mov     rcx, [rax]
0x14001645a  cmp     [rcx+8], rax
0x14001645e  jz      loc_1400165B7
0x140016464  mov     ecx, 3
0x140016469  int     29h; Win8: RtlFailFast(ecx)
0x14001646b  lea     rdx, [rbx+40h]
0x14001646f  mov     rcx, r8
0x140016472  call    PplpLazyInitializeLookasideList
0x140016477  jmp     loc_140016079
0x14001647c  xor     r12b, r12b
0x14001647f  test    byte ptr [rbx+22h], 10h
0x140016483  jz      loc_140016255
0x140016489  jmp     loc_14001624E
0x14001648e  lea     rdx, [rsi+40h]
0x140016492  call    PplpLazyInitializeLookasideList
0x140016497  jmp     loc_14001613F
0x14001649c  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400164a2  mov     [rbp+57h+var_50], rsi
0x1400164a6  mov     [rbp+57h+var_60], rcx
0x1400164aa  test    eax, eax
0x1400164ac  jz      loc_14001628E
0x1400164b2  lea     r9, [rbp+57h+var_60]
0x1400164b6  mov     dword ptr [rsp+100h+var_D0], 8
0x1400164be  lea     r8, [rbp+57h+var_50]
0x1400164c2  call    EtwEx_tidActivityInfoTransfer
0x1400164c7  jmp     loc_14001628E
0x1400164cc  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400164d2  mov     [rbp+57h+var_58], 0
0x1400164da  mov     [rbp+57h+var_60], rsi
0x1400164de  test    eax, eax
0x1400164e0  jz      loc_14001626C
0x1400164e6  lea     r8, [rbp+57h+var_60]
0x1400164ea  mov     dword ptr [rsp+100h+var_E0], 4
0x1400164f2  lea     rdx, ActivityStart
0x1400164f9  call    EtwEx_tidActivityInfo
0x1400164fe  jmp     loc_14001626C
0x140016503  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140016509  mov     [rbp+57h+var_60], r15
0x14001650d  mov     [rbp+57h+var_50], rcx
0x140016511  test    eax, eax
0x140016513  jz      loc_14001640B
0x140016519  lea     r9, [rbp+57h+var_50]
0x14001651d  mov     dword ptr [rsp+100h+var_D0], 7
0x140016525  lea     r8, [rbp+57h+var_60]
0x140016529  call    EtwEx_tidActivityInfoTransfer
0x14001652e  jmp     loc_14001640B
  ... truncated ...
```
