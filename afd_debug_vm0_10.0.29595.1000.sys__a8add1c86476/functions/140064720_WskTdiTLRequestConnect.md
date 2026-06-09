# WskTdiTLRequestConnect

- ea: `0x140064720`
- end: `0x140064ab1`
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
- `0x140064288`
- `0x140064720`
- `0x1400660d0`
- `0x140066520`
- `0x140072980`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140064778`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140064778`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400648a4`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400648a4`
- `ntoskrnl!KeGetCurrentIrql` at `0x140064981`
- `ntoskrnl!KeGetCurrentIrql` at `0x140064a65`
- `ntoskrnl!KeGetCurrentIrql` at `0x140064981`
- `ntoskrnl!KeGetCurrentIrql` at `0x140064a65`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140064945`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140064945`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x140064975`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x140064975`
- `ntoskrnl!ObfReferenceObject` at `0x14006475d`
- `ntoskrnl!ObfReferenceObject` at `0x14006475d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400648b4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400648b4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140064a26`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140064a26`
- `ntoskrnl!KeReleaseSpinLock` at `0x140064a3d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140064a3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064869`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006487d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064869`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006487d`
- `ntoskrnl!ExAllocatePool2` at `0x1400647a0`
- `ntoskrnl!ExAllocatePool2` at `0x1400647a0`
- `NETIO!NetioInsertWorkQueue` at `0x140064a90`
- `NETIO!NetioInsertWorkQueue` at `0x140064a90`

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
0x140064720  push    rbx
0x140064722  push    rbp
0x140064723  push    rsi
0x140064724  push    rdi
0x140064725  push    r13
0x140064727  push    r14
0x140064729  push    r15
0x14006472b  sub     rsp, 40h
0x14006472f  mov     rcx, [rdx+58h]
0x140064733  mov     rdi, rdx
0x140064736  movzx   ecx, word ptr [rcx]; af
0x140064739  call    SOCKADDR_SIZE
0x14006473e  cmp     dword ptr [rdx+10h], 0
0x140064742  movzx   esi, al
0x140064745  jnz     loc_1400649C0
0x14006474b  mov     rcx, [rdx+28h]; Object
0x14006474f  xor     r13b, r13b
0x140064752  mov     r14d, 140h
0x140064758  test    rcx, rcx
0x14006475b  jz      short loc_14006478E
0x14006475d  call    cs:__imp_ObfReferenceObject
0x140064764  nop     dword ptr [rax+rax+00h]
0x140064769  mov     rcx, [rdi+28h]; Process
0x14006476d  mov     r8d, r14d; Amount
0x140064770  mov     edx, 200h; PoolType
0x140064775  mov     r13b, 1
0x140064778  call    cs:__imp_PsChargeProcessPoolQuota
0x14006477f  nop     dword ptr [rax+rax+00h]
0x140064784  mov     ebx, eax
0x140064786  test    eax, eax
0x140064788  js      loc_1400648B0
0x14006478e  mov     r15d, 40h ; '@'
0x140064794  mov     r8d, 744B5357h
0x14006479a  mov     ecx, r15d
0x14006479d  mov     rdx, r14
0x1400647a0  call    cs:__imp_ExAllocatePool2
0x1400647a7  nop     dword ptr [rax+rax+00h]
0x1400647ac  mov     rbp, rax
0x1400647af  test    rax, rax
0x1400647b2  jnz     short loc_1400647BE
0x1400647b4  mov     ebx, 0C000009Ah
0x1400647b9  jmp     loc_14006488F
0x1400647be  mov     rax, [rdi+28h]
0x1400647c2  mov     rbx, rsi
0x1400647c5  mov     [rbp+110h], rax
0x1400647cc  mov     rdx, rbx
0x1400647cf  cmp     esi, cs:AfdStandardAddressLength
0x1400647d5  ja      short loc_1400647DE
0x1400647d7  call    AfdAllocateZeroedFromLookasideList
0x1400647dc  jmp     short loc_1400647EF
0x1400647de  xor     r9d, r9d
0x1400647e1  mov     r8d, 52646641h
0x1400647e7  mov     rcx, r15
0x1400647ea  call    AfdAllocatePoolPriority
0x1400647ef  mov     r14, rax
0x1400647f2  test    rax, rax
0x1400647f5  jnz     short loc_1400647FE
0x1400647f7  mov     ebx, 0C000009Ah
0x1400647fc  jmp     short loc_140064875
0x1400647fe  mov     rdx, [rdi+58h]; Src
0x140064802  mov     r8, rbx; Size
0x140064805  mov     rcx, r14; void *
0x140064808  call    memmove
0x14006480d  mov     [rbp+0C8h], r14
0x140064814  mov     rdx, rbx
0x140064817  cmp     esi, cs:AfdStandardAddressLength
0x14006481d  ja      short loc_140064826
0x14006481f  call    AfdAllocateZeroedFromLookasideList
0x140064824  jmp     short loc_140064837
0x140064826  xor     r9d, r9d
0x140064829  mov     r8d, 52646641h
0x14006482f  mov     rcx, r15
0x140064832  call    AfdAllocatePoolPriority
0x140064837  mov     r15, rax
0x14006483a  test    rax, rax
0x14006483d  jnz     loc_1400648C5
0x140064843  mov     ebx, 0C000009Ah
0x140064848  cmp     esi, cs:AfdStandardAddressLength
0x14006484e  ja      short loc_140064861
0x140064850  mov     rcx, cs:PplAddressPool
0x140064857  mov     rdx, r14
0x14006485a  call    PplFreeToLookasideList
0x14006485f  jmp     short loc_140064875
0x140064861  mov     edx, 52646641h; Tag
0x140064866  mov     rcx, r14; P
0x140064869  call    cs:__imp_ExFreePoolWithTag
0x140064870  nop     dword ptr [rax+rax+00h]
0x140064875  mov     edx, 744B5357h; Tag
0x14006487a  mov     rcx, rbp; P
0x14006487d  call    cs:__imp_ExFreePoolWithTag
0x140064884  nop     dword ptr [rax+rax+00h]
0x140064889  mov     r14d, 140h
0x14006488f  test    r13b, r13b
0x140064892  jz      loc_1400649F5
0x140064898  mov     rcx, [rdi+28h]; Process
0x14006489c  mov     r8, r14; Amount
0x14006489f  mov     edx, 200h; PoolType
0x1400648a4  call    cs:__imp_PsReturnPoolQuota
0x1400648ab  nop     dword ptr [rax+rax+00h]
0x1400648b0  mov     rcx, [rdi+28h]; Object
0x1400648b4  call    cs:__imp_ObfDereferenceObject
0x1400648bb  nop     dword ptr [rax+rax+00h]
0x1400648c0  jmp     loc_1400649F5
0x1400648c5  mov     rdx, [rdi+40h]; Src
0x1400648c9  mov     r8, rbx; Size
0x1400648cc  mov     rcx, r15; void *
0x1400648cf  call    memmove
0x1400648d4  or      dword ptr [rbp+10h], 600h
0x1400648db  mov     rcx, rbp
0x1400648de  mov     [rbp+30h], r15
0x1400648e2  mov     rax, [rdi+8]
0x1400648e6  mov     [rbp+130h], rax
0x1400648ed  mov     rax, [rdi]
0x1400648f0  mov     [rbp+138h], rax
0x1400648f7  mov     rax, [rdi+38h]
0x1400648fb  mov     [rbp+28h], rax
0x1400648ff  mov     rax, [rdi+38h]
0x140064903  movzx   r9d, word ptr [rdi+1Ch]
0x140064908  movzx   r8d, word ptr [rdi+1Ah]
0x14006490d  movzx   edx, word ptr [rdi+18h]
0x140064911  mov     [rsp+78h+var_48], rax
0x140064916  mov     rax, [rdi+30h]
0x14006491a  mov     [rsp+78h+var_50], rax
0x14006491f  mov     rax, [rdi+28h]
0x140064923  mov     [rsp+78h+var_58], rax
0x140064928  call    WskTdiTLHybridCreateEndpoint
0x14006492d  test    al, al
0x14006492f  jnz     loc_140064A9C
0x140064935  cmp     qword ptr [rdi+30h], 0
0x14006493a  jz      short loc_140064981
0x14006493c  mov     rcx, cs:AfdDeviceObject; IoObject
0x140064943  mov     dl, 30h ; '0'; EntrySize
0x140064945  call    cs:__imp_IoAllocateErrorLogEntry
0x14006494c  nop     dword ptr [rax+rax+00h]
0x140064951  test    rax, rax
0x140064954  jz      short loc_140064981
0x140064956  xorps   xmm0, xmm0
0x140064959  movups  xmmword ptr [rax], xmm0
0x14006495c  movups  xmmword ptr [rax+10h], xmm0
0x140064960  movups  xmmword ptr [rax+20h], xmm0
0x140064964  mov     dword ptr [rax+0Ch], 0C0003E80h
0x14006496b  movzx   ecx, word ptr [rdi+18h]
0x14006496f  mov     [rax+10h], ecx
0x140064972  mov     rcx, rax; ElEntry
0x140064975  call    cs:__imp_IoWriteErrorLogEntry
0x14006497c  nop     dword ptr [rax+rax+00h]
0x140064981  call    cs:__imp_KeGetCurrentIrql
0x140064988  nop     dword ptr [rax+rax+00h]
0x14006498d  test    al, al
0x14006498f  jnz     short loc_1400649AD
0x140064991  lea     rcx, [rbp+128h]
0x140064998  mov     qword ptr [rbp+128h], 0
0x1400649a3  call    WskTdiWQRoutineEndpointCreate
0x1400649a8  jmp     loc_140064A9C
0x1400649ad  lea     rdx, [rbp+128h]
0x1400649b4  lea     rcx, WskTdiWQEndpointCreate
0x1400649bb  jmp     loc_140064A90
0x1400649c0  cmp     esi, cs:AfdStandardAddressLength
0x1400649c6  mov     rbp, [rdx+18h]
0x1400649ca  mov     rdx, rsi
0x1400649cd  ja      short loc_1400649D6
0x1400649cf  call    AfdAllocateZeroedFromLookasideList
0x1400649d4  jmp     short loc_1400649E8
0x1400649d6  xor     r9d, r9d
0x1400649d9  mov     r8d, 52646641h
0x1400649df  lea     ecx, [r9+40h]
0x1400649e3  call    AfdAllocatePoolPriority
0x1400649e8  mov     rbx, rax
0x1400649eb  test    rax, rax
0x1400649ee  jnz     short loc_140064A0C
0x1400649f0  mov     ebx, 0C000009Ah
0x1400649f5  mov     qword ptr [rdi+50h], 0
0x1400649fd  mov     eax, ebx
0x1400649ff  mov     qword ptr [rdi+78h], 0
0x140064a07  jmp     loc_140064AA1
0x140064a0c  mov     rdx, [rdi+58h]; Src
0x140064a10  mov     r8, rsi; Size
0x140064a13  mov     rcx, rbx; void *
0x140064a16  call    memmove
0x140064a1b  lea     rcx, [rbp+8]; SpinLock
0x140064a1f  mov     [rbp+0C8h], rbx
0x140064a26  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140064a2d  nop     dword ptr [rax+rax+00h]
0x140064a32  bts     dword ptr [rbp+10h], 9
0x140064a37  lea     rcx, [rbp+8]; SpinLock
0x140064a3b  mov     dl, al; NewIrql
0x140064a3d  call    cs:__imp_KeReleaseSpinLock
0x140064a44  nop     dword ptr [rax+rax+00h]
0x140064a49  mov     rax, [rdi+8]
0x140064a4d  lea     rbx, [rbp+128h]
0x140064a54  mov     [rbp+130h], rax
0x140064a5b  mov     rax, [rdi]
0x140064a5e  mov     [rbp+138h], rax
0x140064a65  call    cs:__imp_KeGetCurrentIrql
0x140064a6c  nop     dword ptr [rax+rax+00h]
0x140064a71  test    al, al
0x140064a73  jnz     short loc_140064A86
0x140064a75  mov     rcx, rbx
0x140064a78  mov     qword ptr [rbx], 0
0x140064a7f  call    WskTdiWQRoutineEndpointBind
0x140064a84  jmp     short loc_140064A9C
0x140064a86  mov     rdx, rbx
0x140064a89  lea     rcx, WskTdiWQEndpointBind
0x140064a90  call    cs:__imp_NetioInsertWorkQueue
0x140064a97  nop     dword ptr [rax+rax+00h]
0x140064a9c  mov     eax, 103h
0x140064aa1  add     rsp, 40h
0x140064aa5  pop     r15
0x140064aa7  pop     r14
0x140064aa9  pop     r13
0x140064aab  pop     rdi
0x140064aac  pop     rsi
0x140064aad  pop     rbp
0x140064aae  pop     rbx
0x140064aaf  retn
```
