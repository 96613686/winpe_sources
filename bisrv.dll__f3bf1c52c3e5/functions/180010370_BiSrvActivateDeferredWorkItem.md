# BiSrvActivateDeferredWorkItem

- ea: `0x180010370`
- end: `0x1800105bc`
- name: `BiSrvActivateDeferredWorkItem`
- size: `588`
- prototype: `__int64 __fastcall(PSID Sid1, void *Source1)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004f760`
- `0x180065890`
- `0x1800907f0`
- `0x1800925c0`

## callees

- `0x18000d50c`
- `0x18000d7c0`
- `0x18000da50`
- `0x18000f020`
- `0x180010370`
- `0x18004df58`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180010432`
- `ntdll!RtlReleaseSRWLockShared` at `0x180010432`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800103c1`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800103c1`
- `ntdll!RtlGetNextEntryHashTable` at `0x18001041c`
- `ntdll!RtlGetNextEntryHashTable` at `0x18001041c`
- `ntdll!RtlLookupEntryHashTable` at `0x1800103dd`
- `ntdll!RtlLookupEntryHashTable` at `0x1800103dd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800104e2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800104e2`
- `ntdll!RtlEqualSid` at `0x18001048c`
- `ntdll!RtlEqualSid` at `0x18001048c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180010404`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180010404`

## pseudocode

```c
__int64 __fastcall BiSrvActivateDeferredWorkItem(PSID Sid1, unsigned __int8 *Source1)
{
  unsigned __int64 v2; // rbx
  __int64 v3; // rbp
  unsigned __int8 *v6; // r8
  int v7; // r9d
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 i; // rax
  __int64 v11; // rbx
  unsigned int v12; // edi
  int v13; // esi
  __int64 v14; // rcx
  __int64 *j; // rax
  void *v16; // rdx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v17; // rcx
  _QWORD *ThreadLocalStoragePointer; // rax
  int v19; // r14d
  __int64 v20; // rbx
  __int64 v22; // rdx
  __int128 v23; // [rsp+20h] [rbp-58h] BYREF
  __int64 v24; // [rsp+30h] [rbp-48h]

  v2 = qword_1800C4148;
  v3 = 0;
  v24 = 0;
  v6 = Source1;
  v7 = 16;
  v23 = 0;
  do
  {
    v8 = *v6++;
    v2 = v8 + 39 * v2;
    --v7;
  }
  while ( v7 );
  RtlAcquireSRWLockShared(&qword_1800C4390);
  v9 = 1;
  if ( v2 )
    v9 = v2;
  for ( i = RtlLookupEntryHashTable(qword_1800C4388, v9, &v23); ; i = RtlGetNextEntryHashTable(qword_1800C4388, &v23) )
  {
    v11 = i;
    v12 = -1073741275;
    if ( !i )
      break;
    v3 = i;
    if ( RtlCompareMemory(Source1, (const void *)(i + 32), 0x10u) == 16 )
    {
      v13 = 0;
      _InterlockedAdd((volatile signed __int32 *)(v11 + 28), 1u);
      goto LABEL_10;
    }
  }
  v13 = -1073741275;
LABEL_10:
  RtlReleaseSRWLockShared(&qword_1800C4390);
  if ( v13 < 0 )
  {
    v12 = v13;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_7356033c0bb43066cc7d8f8866379e89_Traceguids);
  }
  else
  {
    BipAcquireGlobalLock(v14);
    if ( *(int *)(v3 + 24) < 0 )
    {
      v17 = (struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = 11;
LABEL_25:
        WPP_SF_(*((_QWORD *)v17 + 2), v22, WPP_7356033c0bb43066cc7d8f8866379e89_Traceguids);
      }
    }
    else
    {
      for ( j = *(__int64 **)(v3 + 144); ; j = (__int64 *)*j )
      {
        if ( j == (__int64 *)(v3 + 144) )
        {
          v17 = (struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v22 = 12;
            goto LABEL_25;
          }
          goto LABEL_20;
        }
        if ( *((_DWORD *)j + 10) == 40960 )
          break;
      }
      if ( !Sid1 || (v16 = *(void **)(*(_QWORD *)(v3 + 72) + 168LL)) != 0 && RtlEqualSid(Sid1, v16) )
      {
        v12 = BipUnbufferPendingActivations(v3);
        goto LABEL_20;
      }
      v12 = -1073741823;
      v17 = (struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = 13;
        goto LABEL_25;
      }
    }
LABEL_20:
    BipLockWatchdogContextDisarmWatchdog(v17);
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v19 = ~(1 << dword_1800C3CB0);
    dword_1800C3CB4 = 0;
    v20 = ThreadLocalStoragePointer[(unsigned int)tls_index];
    *(_DWORD *)(v20 + 8) &= v19;
    RtlReleaseSRWLockExclusive(&BipGlobalLock);
    *(_DWORD *)(v20 + 4) &= v19;
    BipWorkItemDereference(v3);
  }
  return v12;
}

```

## disassembly

```asm
0x180010370  push    rbx
0x180010372  push    rbp
0x180010373  push    rsi
0x180010374  push    rdi
0x180010375  push    r14
0x180010377  push    r15
0x180010379  sub     rsp, 48h
0x18001037d  mov     rbx, cs:qword_1800C4148
0x180010384  xor     ebp, ebp
0x180010386  xorps   xmm0, xmm0
0x180010389  xor     eax, eax
0x18001038b  mov     rsi, rdx
0x18001038e  mov     [rsp+78h+var_48], rax
0x180010393  mov     r15, rcx
0x180010396  mov     r8, rdx
0x180010399  lea     r9d, [rbp+10h]
0x18001039d  lea     r14d, [rbp+1]
0x1800103a1  movups  [rsp+78h+var_58], xmm0
0x1800103a6  movzx   eax, byte ptr [r8]
0x1800103aa  add     r8, r14
0x1800103ad  imul    rbx, 27h ; '''
0x1800103b1  add     rbx, rax
0x1800103b4  add     r9d, 0FFFFFFFFh
0x1800103b8  jnz     short loc_1800103A6
0x1800103ba  lea     rcx, qword_1800C4390
0x1800103c1  call    cs:__imp_RtlAcquireSRWLockShared
0x1800103c7  mov     rcx, cs:qword_1800C4388
0x1800103ce  lea     r8, [rsp+78h+var_58]
0x1800103d3  test    rbx, rbx
0x1800103d6  mov     rdx, r14
0x1800103d9  cmovnz  rdx, rbx
0x1800103dd  call    cs:__imp_RtlLookupEntryHashTable
0x1800103e3  mov     rbx, rax
0x1800103e6  mov     edi, 0C0000225h
0x1800103eb  test    rax, rax
0x1800103ee  jz      loc_180010535
0x1800103f4  lea     rdx, [rax+20h]; Source2
0x1800103f8  mov     r8d, 10h; Length
0x1800103fe  mov     rcx, rsi; Source1
0x180010401  mov     rbp, rax
0x180010404  call    cs:__imp_RtlCompareMemory
0x18001040a  cmp     rax, 10h
0x18001040e  jz      short loc_180010424
0x180010410  mov     rcx, cs:qword_1800C4388
0x180010417  lea     rdx, [rsp+78h+var_58]
0x18001041c  call    cs:__imp_RtlGetNextEntryHashTable
0x180010422  jmp     short loc_1800103E3
0x180010424  xor     esi, esi
0x180010426  lock add [rbx+1Ch], r14d
0x18001042b  lea     rcx, qword_1800C4390
0x180010432  call    cs:__imp_RtlReleaseSRWLockShared
0x180010438  test    esi, esi
0x18001043a  js      loc_180010585
0x180010440  call    BipAcquireGlobalLock
0x180010445  cmp     dword ptr [rbp+18h], 0
0x180010449  jl      loc_18001053C
0x18001044f  lea     rcx, [rbp+90h]
0x180010456  mov     rax, [rcx]
0x180010459  cmp     rax, rcx
0x18001045c  jz      loc_180010508
0x180010462  cmp     dword ptr [rax+28h], 0A000h
0x180010469  jz      short loc_180010470
0x18001046b  mov     rax, [rax]
0x18001046e  jmp     short loc_180010459
0x180010470  test    r15, r15
0x180010473  jz      short loc_18001049A
0x180010475  mov     rax, [rbp+48h]
0x180010479  mov     rdx, [rax+0A8h]; Sid2
0x180010480  test    rdx, rdx
0x180010483  jz      loc_18001055E
0x180010489  mov     rcx, r15; Sid1
0x18001048c  call    cs:__imp_RtlEqualSid
0x180010492  test    al, al
0x180010494  jz      loc_18001055E
0x18001049a  mov     rcx, rbp
0x18001049d  call    BipUnbufferPendingActivations
0x1800104a2  mov     edi, eax
0x1800104a4  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x1800104a9  mov     ecx, cs:dword_1800C3CB0
0x1800104af  mov     edx, cs:_tls_index
0x1800104b5  mov     rax, gs:58h
0x1800104be  shl     r14d, cl
0x1800104c1  lea     rcx, BipGlobalLock
0x1800104c8  not     r14d
0x1800104cb  mov     cs:dword_1800C3CB4, 0
0x1800104d5  mov     rbx, [rax+rdx*8]
0x1800104d9  mov     eax, 8
0x1800104de  and     [rax+rbx], r14d
0x1800104e2  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800104e8  mov     eax, 4
0x1800104ed  mov     rcx, rbp
0x1800104f0  and     [rax+rbx], r14d
0x1800104f4  call    BipWorkItemDereference
0x1800104f9  mov     eax, edi
0x1800104fb  add     rsp, 48h
0x1800104ff  pop     r15
0x180010501  pop     r14
0x180010503  pop     rdi
0x180010504  pop     rsi
0x180010505  pop     rbp
0x180010506  pop     rbx
0x180010507  retn
0x180010508  mov     rcx, cs:WPP_GLOBAL_Control
0x18001050f  test    byte ptr [rcx+1Ch], 40h
0x180010513  jz      short loc_1800104A4
0x180010515  cmp     byte ptr [rcx+19h], 2
0x180010519  jb      short loc_1800104A4
0x18001051b  mov     edx, 0Ch
0x180010520  mov     rcx, [rcx+10h]
0x180010524  lea     r8, WPP_7356033c0bb43066cc7d8f8866379e89_Traceguids
0x18001052b  call    WPP_SF_
0x180010530  jmp     loc_1800104A4
0x180010535  mov     esi, edi
0x180010537  jmp     loc_18001042B
0x18001053c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010543  test    byte ptr [rcx+1Ch], 40h
0x180010547  jz      loc_1800104A4
0x18001054d  cmp     byte ptr [rcx+19h], 2
0x180010551  jb      loc_1800104A4
0x180010557  mov     edx, 0Bh
0x18001055c  jmp     short loc_180010520
0x18001055e  mov     edi, 0C0000001h
0x180010563  mov     rcx, cs:WPP_GLOBAL_Control
0x18001056a  test    byte ptr [rcx+1Ch], 40h
0x18001056e  jz      loc_1800104A4
0x180010574  cmp     byte ptr [rcx+19h], 2
0x180010578  jb      loc_1800104A4
0x18001057e  mov     edx, 0Dh
0x180010583  jmp     short loc_180010520
0x180010585  mov     edi, esi
0x180010587  mov     rcx, cs:WPP_GLOBAL_Control
0x18001058e  test    byte ptr [rcx+1Ch], 40h
0x180010592  jz      loc_1800104F9
0x180010598  cmp     byte ptr [rcx+19h], 2
0x18001059c  jb      loc_1800104F9
0x1800105a2  mov     rcx, [rcx+10h]
0x1800105a6  lea     r8, WPP_7356033c0bb43066cc7d8f8866379e89_Traceguids
0x1800105ad  mov     edx, 0Ah
0x1800105b2  call    WPP_SF_
0x1800105b7  jmp     loc_1800104F9
```
