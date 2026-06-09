# WskTdiTLRequestConnect

- ea: `0x140064580`
- end: `0x140064911`
- name: `WskTdiTLRequestConnect`
- size: `913`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation`

## callees

- `0x140003670`
- `0x140005b60`
- `0x140013030`
- `0x140015990`
- `0x1400640e8`
- `0x140064580`
- `0x140065f30`
- `0x140066380`
- `0x140072800`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1400645d8`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1400645d8`
- `ntoskrnl!PsReturnPoolQuota` at `0x140064704`
- `ntoskrnl!PsReturnPoolQuota` at `0x140064704`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400647e1`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400648c5`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400647e1`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400648c5`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x1400647a5`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x1400647a5`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x1400647d5`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x1400647d5`
- `ntoskrnl!ObfReferenceObject` at `0x1400645bd`
- `ntoskrnl!ObfReferenceObject` at `0x1400645bd`
- `ntoskrnl!ObfDereferenceObject` at `0x140064714`
- `ntoskrnl!ObfDereferenceObject` at `0x140064714`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140064886`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140064886`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006489d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006489d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400646c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400646dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400646c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400646dd`
- `ntoskrnl!ExAllocatePool2` at `0x140064600`
- `ntoskrnl!ExAllocatePool2` at `0x140064600`
- `NETIO!NetioInsertWorkQueue` at `0x1400648f0`
- `NETIO!NetioInsertWorkQueue` at `0x1400648f0`

## pseudocode

```c
__int64 __fastcall WskTdiTLRequestConnect(__int64 a1, __int64 a2)
{
  UCHAR v3; // al
  __int64 v4; // rdx
  __int64 v5; // rcx
  size_t v6; // rsi
  void *v7; // rcx
  char v8; // r13
  NTSTATUS v9; // ebx
  __int64 v10; // rcx
  __int64 Pool2; // rbp
  void *ZeroedFromLookasideList; // rax
  void *v13; // r14
  __int64 v14; // rcx
  void *v15; // rax
  void *v16; // r15
  _OWORD *ErrorLogEntry; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 *v22; // rcx
  __int64 v23; // rbp
  void *PoolPriority; // rax
  void *v25; // rbx
  __int64 result; // rax
  KIRQL v27; // al
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9

  v3 = SOCKADDR_SIZE(**(_WORD **)(a2 + 88));
  v6 = v3;
  if ( *(_DWORD *)(v4 + 16) )
  {
    v23 = *(_QWORD *)(v4 + 24);
    if ( v3 > (unsigned int)AfdStandardAddressLength )
      PoolPriority = (void *)AfdAllocatePoolPriority(64, v3, 1382311489, 0);
    else
      PoolPriority = (void *)AfdAllocateZeroedFromLookasideList(v5, v3);
    v25 = PoolPriority;
    if ( !PoolPriority )
    {
      v9 = -1073741670;
      goto LABEL_34;
    }
    memmove(PoolPriority, *(const void **)(a2 + 88), v6);
    *(_QWORD *)(v23 + 200) = v25;
    v27 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v23 + 8));
    *(_DWORD *)(v23 + 16) |= 0x200u;
    KeReleaseSpinLock((PKSPIN_LOCK)(v23 + 8), v27);
    *(_QWORD *)(v23 + 304) = *(_QWORD *)(a2 + 8);
    *(_QWORD *)(v23 + 312) = *(_QWORD *)a2;
    if ( !KeGetCurrentIrql() )
    {
      *(_QWORD *)(v23 + 296) = 0;
      WskTdiWQRoutineEndpointBind((_QWORD *)(v23 + 296), v28, v29, v30);
      return 259;
    }
    v21 = v23 + 296;
    v22 = WskTdiWQEndpointBind;
    goto LABEL_38;
  }
  v7 = *(void **)(v4 + 40);
  v8 = 0;
  if ( v7 )
  {
    ObfReferenceObject(v7);
    v8 = 1;
    v9 = PsChargeProcessPoolQuota(*(PEPROCESS *)(a2 + 40), (POOL_TYPE)512, 0x140u);
    if ( v9 < 0 )
      goto LABEL_21;
  }
  Pool2 = ExAllocatePool2(64, 320, 1951093591);
  if ( !Pool2 )
  {
    v9 = -1073741670;
LABEL_19:
    if ( !v8 )
    {
LABEL_34:
      *(_QWORD *)(a2 + 80) = 0;
      result = (unsigned int)v9;
      *(_QWORD *)(a2 + 120) = 0;
      return result;
    }
    PsReturnPoolQuota(*(PEPROCESS *)(a2 + 40), (POOL_TYPE)512, 0x140u);
LABEL_21:
    ObfDereferenceObject(*(PVOID *)(a2 + 40));
    goto LABEL_34;
  }
  *(_QWORD *)(Pool2 + 272) = *(_QWORD *)(a2 + 40);
  if ( (unsigned int)v6 > (unsigned int)AfdStandardAddressLength )
    ZeroedFromLookasideList = (void *)AfdAllocatePoolPriority(64, v6, 1382311489, 0);
  else
    ZeroedFromLookasideList = (void *)AfdAllocateZeroedFromLookasideList(v10, v6);
  v13 = ZeroedFromLookasideList;
  if ( !ZeroedFromLookasideList )
  {
    v9 = -1073741670;
LABEL_18:
    ExFreePoolWithTag((PVOID)Pool2, 0x744B5357u);
    goto LABEL_19;
  }
  memmove(ZeroedFromLookasideList, *(const void **)(a2 + 88), v6);
  *(_QWORD *)(Pool2 + 200) = v13;
  if ( (unsigned int)v6 > (unsigned int)AfdStandardAddressLength )
    v15 = (void *)AfdAllocatePoolPriority(64, v6, 1382311489, 0);
  else
    v15 = (void *)AfdAllocateZeroedFromLookasideList(v14, v6);
  v16 = v15;
  if ( !v15 )
  {
    v9 = -1073741670;
    if ( (unsigned int)v6 > (unsigned int)AfdStandardAddressLength )
      ExFreePoolWithTag(v13, 0x52646641u);
    else
      PplFreeToLookasideList((__int64)PplAddressPool, v13);
    goto LABEL_18;
  }
  memmove(v15, *(const void **)(a2 + 64), v6);
  *(_DWORD *)(Pool2 + 16) |= 0x600u;
  *(_QWORD *)(Pool2 + 48) = v16;
  *(_QWORD *)(Pool2 + 304) = *(_QWORD *)(a2 + 8);
  *(_QWORD *)(Pool2 + 312) = *(_QWORD *)a2;
  *(_QWORD *)(Pool2 + 40) = *(_QWORD *)(a2 + 56);
  if ( !(unsigned __int8)WskTdiTLHybridCreateEndpoint(
                           Pool2,
                           *(unsigned __int16 *)(a2 + 24),
                           *(unsigned __int16 *)(a2 + 26),
                           *(unsigned __int16 *)(a2 + 28),
                           *(_QWORD *)(a2 + 40),
                           *(_QWORD *)(a2 + 48),
                           *(_QWORD *)(a2 + 56)) )
  {
    if ( *(_QWORD *)(a2 + 48) )
    {
      ErrorLogEntry = IoAllocateErrorLogEntry(AfdDeviceObject, 0x30u);
      if ( ErrorLogEntry )
      {
        *ErrorLogEntry = 0;
        ErrorLogEntry[1] = 0;
        ErrorLogEntry[2] = 0;
        *((_DWORD *)ErrorLogEntry + 3) = -1073725824;
        *((_DWORD *)ErrorLogEntry + 4) = *(unsigned __int16 *)(a2 + 24);
        IoWriteErrorLogEntry(ErrorLogEntry);
      }
    }
    if ( !KeGetCurrentIrql() )
    {
      *(_QWORD *)(Pool2 + 296) = 0;
      WskTdiWQRoutineEndpointCreate((__int64 *)(Pool2 + 296), v18, v19, v20);
      return 259;
    }
    v21 = Pool2 + 296;
    v22 = WskTdiWQEndpointCreate;
LABEL_38:
    NetioInsertWorkQueue(v22, v21);
  }
  return 259;
}

```

## disassembly

```asm
0x140064580  push    rbx
0x140064582  push    rbp
0x140064583  push    rsi
0x140064584  push    rdi
0x140064585  push    r13
0x140064587  push    r14
0x140064589  push    r15
0x14006458b  sub     rsp, 40h
0x14006458f  mov     rcx, [rdx+58h]
0x140064593  mov     rdi, rdx
0x140064596  movzx   ecx, word ptr [rcx]; af
0x140064599  call    SOCKADDR_SIZE
0x14006459e  cmp     dword ptr [rdx+10h], 0
0x1400645a2  movzx   esi, al
0x1400645a5  jnz     loc_140064820
0x1400645ab  mov     rcx, [rdx+28h]; Object
0x1400645af  xor     r13b, r13b
0x1400645b2  mov     r14d, 140h
0x1400645b8  test    rcx, rcx
0x1400645bb  jz      short loc_1400645EE
0x1400645bd  call    cs:__imp_ObfReferenceObject
0x1400645c4  nop     dword ptr [rax+rax+00h]
0x1400645c9  mov     rcx, [rdi+28h]; Process
0x1400645cd  mov     r8d, r14d; Amount
0x1400645d0  mov     edx, 200h; PoolType
0x1400645d5  mov     r13b, 1
0x1400645d8  call    cs:__imp_PsChargeProcessPoolQuota
0x1400645df  nop     dword ptr [rax+rax+00h]
0x1400645e4  mov     ebx, eax
0x1400645e6  test    eax, eax
0x1400645e8  js      loc_140064710
0x1400645ee  mov     r15d, 40h ; '@'
0x1400645f4  mov     r8d, 744B5357h
0x1400645fa  mov     ecx, r15d
0x1400645fd  mov     rdx, r14
0x140064600  call    cs:__imp_ExAllocatePool2
0x140064607  nop     dword ptr [rax+rax+00h]
0x14006460c  mov     rbp, rax
0x14006460f  test    rax, rax
0x140064612  jnz     short loc_14006461E
0x140064614  mov     ebx, 0C000009Ah
0x140064619  jmp     loc_1400646EF
0x14006461e  mov     rax, [rdi+28h]
0x140064622  mov     rbx, rsi
0x140064625  mov     [rbp+110h], rax
0x14006462c  mov     rdx, rbx
0x14006462f  cmp     esi, cs:AfdStandardAddressLength
0x140064635  ja      short loc_14006463E
0x140064637  call    AfdAllocateZeroedFromLookasideList
0x14006463c  jmp     short loc_14006464F
0x14006463e  xor     r9d, r9d
0x140064641  mov     r8d, 52646641h
0x140064647  mov     rcx, r15
0x14006464a  call    AfdAllocatePoolPriority
0x14006464f  mov     r14, rax
0x140064652  test    rax, rax
0x140064655  jnz     short loc_14006465E
0x140064657  mov     ebx, 0C000009Ah
0x14006465c  jmp     short loc_1400646D5
0x14006465e  mov     rdx, [rdi+58h]; Src
0x140064662  mov     r8, rbx; Size
0x140064665  mov     rcx, r14; void *
0x140064668  call    memmove
0x14006466d  mov     [rbp+0C8h], r14
0x140064674  mov     rdx, rbx
0x140064677  cmp     esi, cs:AfdStandardAddressLength
0x14006467d  ja      short loc_140064686
0x14006467f  call    AfdAllocateZeroedFromLookasideList
0x140064684  jmp     short loc_140064697
0x140064686  xor     r9d, r9d
0x140064689  mov     r8d, 52646641h
0x14006468f  mov     rcx, r15
0x140064692  call    AfdAllocatePoolPriority
0x140064697  mov     r15, rax
0x14006469a  test    rax, rax
0x14006469d  jnz     loc_140064725
0x1400646a3  mov     ebx, 0C000009Ah
0x1400646a8  cmp     esi, cs:AfdStandardAddressLength
0x1400646ae  ja      short loc_1400646C1
0x1400646b0  mov     rcx, cs:PplAddressPool
0x1400646b7  mov     rdx, r14
0x1400646ba  call    PplFreeToLookasideList
0x1400646bf  jmp     short loc_1400646D5
0x1400646c1  mov     edx, 52646641h; Tag
0x1400646c6  mov     rcx, r14; P
0x1400646c9  call    cs:__imp_ExFreePoolWithTag
0x1400646d0  nop     dword ptr [rax+rax+00h]
0x1400646d5  mov     edx, 744B5357h; Tag
0x1400646da  mov     rcx, rbp; P
0x1400646dd  call    cs:__imp_ExFreePoolWithTag
0x1400646e4  nop     dword ptr [rax+rax+00h]
0x1400646e9  mov     r14d, 140h
0x1400646ef  test    r13b, r13b
0x1400646f2  jz      loc_140064855
0x1400646f8  mov     rcx, [rdi+28h]; Process
0x1400646fc  mov     r8, r14; Amount
0x1400646ff  mov     edx, 200h; PoolType
0x140064704  call    cs:__imp_PsReturnPoolQuota
0x14006470b  nop     dword ptr [rax+rax+00h]
0x140064710  mov     rcx, [rdi+28h]; Object
0x140064714  call    cs:__imp_ObfDereferenceObject
0x14006471b  nop     dword ptr [rax+rax+00h]
0x140064720  jmp     loc_140064855
0x140064725  mov     rdx, [rdi+40h]; Src
0x140064729  mov     r8, rbx; Size
0x14006472c  mov     rcx, r15; void *
0x14006472f  call    memmove
0x140064734  or      dword ptr [rbp+10h], 600h
0x14006473b  mov     rcx, rbp
0x14006473e  mov     [rbp+30h], r15
0x140064742  mov     rax, [rdi+8]
0x140064746  mov     [rbp+130h], rax
0x14006474d  mov     rax, [rdi]
0x140064750  mov     [rbp+138h], rax
0x140064757  mov     rax, [rdi+38h]
0x14006475b  mov     [rbp+28h], rax
0x14006475f  mov     rax, [rdi+38h]
0x140064763  movzx   r9d, word ptr [rdi+1Ch]
0x140064768  movzx   r8d, word ptr [rdi+1Ah]
0x14006476d  movzx   edx, word ptr [rdi+18h]
0x140064771  mov     [rsp+78h+var_48], rax
0x140064776  mov     rax, [rdi+30h]
0x14006477a  mov     [rsp+78h+var_50], rax
0x14006477f  mov     rax, [rdi+28h]
0x140064783  mov     [rsp+78h+var_58], rax
0x140064788  call    WskTdiTLHybridCreateEndpoint
0x14006478d  test    al, al
0x14006478f  jnz     loc_1400648FC
0x140064795  cmp     qword ptr [rdi+30h], 0
0x14006479a  jz      short loc_1400647E1
0x14006479c  mov     rcx, cs:AfdDeviceObject; IoObject
0x1400647a3  mov     dl, 30h ; '0'; EntrySize
0x1400647a5  call    cs:__imp_IoAllocateErrorLogEntry
0x1400647ac  nop     dword ptr [rax+rax+00h]
0x1400647b1  test    rax, rax
0x1400647b4  jz      short loc_1400647E1
0x1400647b6  xorps   xmm0, xmm0
0x1400647b9  movups  xmmword ptr [rax], xmm0
0x1400647bc  movups  xmmword ptr [rax+10h], xmm0
0x1400647c0  movups  xmmword ptr [rax+20h], xmm0
0x1400647c4  mov     dword ptr [rax+0Ch], 0C0003E80h
0x1400647cb  movzx   ecx, word ptr [rdi+18h]
0x1400647cf  mov     [rax+10h], ecx
0x1400647d2  mov     rcx, rax; ElEntry
0x1400647d5  call    cs:__imp_IoWriteErrorLogEntry
0x1400647dc  nop     dword ptr [rax+rax+00h]
0x1400647e1  call    cs:__imp_KeGetCurrentIrql
0x1400647e8  nop     dword ptr [rax+rax+00h]
0x1400647ed  test    al, al
0x1400647ef  jnz     short loc_14006480D
0x1400647f1  lea     rcx, [rbp+128h]
0x1400647f8  mov     qword ptr [rbp+128h], 0
0x140064803  call    WskTdiWQRoutineEndpointCreate
0x140064808  jmp     loc_1400648FC
0x14006480d  lea     rdx, [rbp+128h]
0x140064814  lea     rcx, WskTdiWQEndpointCreate
0x14006481b  jmp     loc_1400648F0
0x140064820  cmp     esi, cs:AfdStandardAddressLength
0x140064826  mov     rbp, [rdx+18h]
0x14006482a  mov     rdx, rsi
0x14006482d  ja      short loc_140064836
0x14006482f  call    AfdAllocateZeroedFromLookasideList
0x140064834  jmp     short loc_140064848
0x140064836  xor     r9d, r9d
0x140064839  mov     r8d, 52646641h
0x14006483f  lea     ecx, [r9+40h]
0x140064843  call    AfdAllocatePoolPriority
0x140064848  mov     rbx, rax
0x14006484b  test    rax, rax
0x14006484e  jnz     short loc_14006486C
0x140064850  mov     ebx, 0C000009Ah
0x140064855  mov     qword ptr [rdi+50h], 0
0x14006485d  mov     eax, ebx
0x14006485f  mov     qword ptr [rdi+78h], 0
0x140064867  jmp     loc_140064901
0x14006486c  mov     rdx, [rdi+58h]; Src
0x140064870  mov     r8, rsi; Size
0x140064873  mov     rcx, rbx; void *
0x140064876  call    memmove
0x14006487b  lea     rcx, [rbp+8]; SpinLock
0x14006487f  mov     [rbp+0C8h], rbx
0x140064886  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14006488d  nop     dword ptr [rax+rax+00h]
0x140064892  bts     dword ptr [rbp+10h], 9
0x140064897  lea     rcx, [rbp+8]; SpinLock
0x14006489b  mov     dl, al; NewIrql
0x14006489d  call    cs:__imp_KeReleaseSpinLock
0x1400648a4  nop     dword ptr [rax+rax+00h]
0x1400648a9  mov     rax, [rdi+8]
0x1400648ad  lea     rbx, [rbp+128h]
0x1400648b4  mov     [rbp+130h], rax
0x1400648bb  mov     rax, [rdi]
0x1400648be  mov     [rbp+138h], rax
0x1400648c5  call    cs:__imp_KeGetCurrentIrql
0x1400648cc  nop     dword ptr [rax+rax+00h]
0x1400648d1  test    al, al
0x1400648d3  jnz     short loc_1400648E6
0x1400648d5  mov     rcx, rbx
0x1400648d8  mov     qword ptr [rbx], 0
0x1400648df  call    WskTdiWQRoutineEndpointBind
0x1400648e4  jmp     short loc_1400648FC
0x1400648e6  mov     rdx, rbx
0x1400648e9  lea     rcx, WskTdiWQEndpointBind
0x1400648f0  call    cs:__imp_NetioInsertWorkQueue
0x1400648f7  nop     dword ptr [rax+rax+00h]
0x1400648fc  mov     eax, 103h
0x140064901  add     rsp, 40h
0x140064905  pop     r15
0x140064907  pop     r14
0x140064909  pop     r13
0x14006490b  pop     rdi
0x14006490c  pop     rsi
0x14006490d  pop     rbp
0x14006490e  pop     rbx
0x14006490f  retn
```
