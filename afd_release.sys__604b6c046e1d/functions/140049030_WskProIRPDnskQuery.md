# WskProIRPDnskQuery

- ea: `0x140049030`
- end: `0x1400493b8`
- name: `WskProIRPDnskQuery`
- size: `904`
- prototype: `__int64 __fastcall(PIRP Irp, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140032d90`

## callees

- `0x140002f44`
- `0x14001087c`
- `0x140029ccc`
- `0x14004028c`
- `0x140048eac`
- `0x140049030`
- `0x14009304c`
- `0x1400930cc`
- `0x140093580`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140049109`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140049109`
- `ntoskrnl!PsReturnPoolQuota` at `0x14004935a`
- `ntoskrnl!PsReturnPoolQuota` at `0x14004935a`
- `ntoskrnl!PsGetCurrentProcess` at `0x140049138`
- `ntoskrnl!PsGetCurrentProcess` at `0x140049138`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400491b3`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400491b3`
- `ntoskrnl!PsReferenceSiloContext` at `0x1400491db`
- `ntoskrnl!PsReferenceSiloContext` at `0x1400491db`
- `ntoskrnl!ObfReferenceObject` at `0x1400490e8`
- `ntoskrnl!ObfReferenceObject` at `0x1400490e8`
- `ntoskrnl!IofCompleteRequest` at `0x140049398`
- `ntoskrnl!IofCompleteRequest` at `0x140049398`
- `ntoskrnl!ObfDereferenceObject` at `0x14004936f`
- `ntoskrnl!ObfDereferenceObject` at `0x14004936f`
- `ntoskrnl!ExAllocatePool2` at `0x140049169`
- `ntoskrnl!ExAllocatePool2` at `0x140049198`
- `ntoskrnl!ExAllocatePool2` at `0x140049169`
- `ntoskrnl!ExAllocatePool2` at `0x140049198`
- `msrpc!RpcAsyncInitializeHandle` at `0x1400492a7`
- `msrpc!RpcAsyncInitializeHandle` at `0x1400492a7`

## pseudocode

```c
__int64 __fastcall WskProIRPDnskQuery(PIRP Irp, _QWORD *a2, __int64 a3, __int64 a4)
{
  volatile signed __int32 *v4; // r13
  __int64 v5; // rdi
  int v6; // r15d
  int v7; // r14d
  __int64 Pool2; // rsi
  signed __int32 v11; // eax
  _QWORD *v12; // rax
  int v13; // ebx
  int v14; // r12d
  bool v15; // zf
  void *v16; // rcx
  int v17; // r14d
  __int64 v18; // rax
  __int64 Current; // rax
  int v20; // ecx
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rdx
  __int64 v24; // r8

  v4 = (volatile signed __int32 *)a2[1];
  v5 = a2[2];
  v6 = 0;
  v7 = 0;
  Pool2 = 0;
  if ( (BYTE3(xmmword_1400875E0) & 1) != 0 )
    WPP_SF_qqqq(Irp, a2, a3, KeGetCurrentThread(), Irp, v4, v5);
  do
  {
    v11 = *((_DWORD *)v4 + 4);
    if ( (v11 & 1) != 0 )
    {
      v14 = 0;
      v13 = -1073741816;
      goto LABEL_33;
    }
  }
  while ( v11 != _InterlockedCompareExchange(v4 + 4, v11 + 2, v11) );
  v12 = *(_QWORD **)(v5 + 8);
  if ( v12 )
    *v12 = 0;
  if ( !*(_QWORD *)v5
    || !*(_QWORD *)(v5 + 8)
    || !*(_QWORD *)(*(_QWORD *)v5 + 8LL)
    || (*(_QWORD *)(v5 + 16) ? (v15 = WskKnrIsCurrentThreadImpersonated() == 0) : (v15 = *(_QWORD *)(v5 + 24) == 0), !v15) )
  {
    v13 = -1073741811;
LABEL_11:
    v14 = 1;
    goto LABEL_33;
  }
  v16 = *(void **)(v5 + 16);
  if ( !v16
    || (ObfReferenceObject(v16),
        v6 = 1,
        v13 = PsChargeProcessPoolQuota(*(PEPROCESS *)(v5 + 16), (POOL_TYPE)512, 0xD8u),
        v13 >= 0) )
  {
    if ( *(_QWORD *)(v5 + 16) )
    {
      v17 = 3;
    }
    else
    {
      v17 = (*(_QWORD *)(v5 + 24) != 0) + 2;
      *(_QWORD *)(v5 + 16) = PsGetCurrentProcess(v16, a2, a3, a4);
    }
    Pool2 = ExAllocatePool2(64, 216, 1934773835);
    if ( Pool2 && (v18 = ExAllocatePool2(256, 272, 1934773835), (*(_QWORD *)(Pool2 + 184) = v18) != 0) )
    {
      v13 = ExInitializeResourceLite((PERESOURCE)Pool2);
      if ( v13 >= 0 )
      {
        *(_DWORD *)(Pool2 + 164) |= 0x20u;
        Current = AfdPodGetCurrent();
        *(_QWORD *)(Pool2 + 192) = Current;
        PsReferenceSiloContext(Current);
        if ( (BYTE3(xmmword_1400875E0) & 1) != 0 )
          WPP_SF_qD(
            1048,
            12,
            WPP_5e35edc2639936f2cd25c7f5a05fa440_Traceguids,
            Irp,
            *(_DWORD *)(*(_QWORD *)(Pool2 + 192) + 8LL));
        v20 = *(_DWORD *)(Pool2 + 164);
        *(_QWORD *)(Pool2 + 112) = v4;
        *(_QWORD *)(Pool2 + 120) = Irp;
        *(_DWORD *)(Pool2 + 164) = (4 * v6) | v20 & 0xFFFFFFFB | 3;
        **(_QWORD **)(Pool2 + 184) = *(_QWORD *)(v5 + 16);
        *(_QWORD *)(*(_QWORD *)(Pool2 + 184) + 8LL) = *(_QWORD *)(v5 + 24);
        *(_DWORD *)(*(_QWORD *)(Pool2 + 184) + 16LL) = v17;
        *(_QWORD *)(*(_QWORD *)(Pool2 + 184) + 24LL) = *(_QWORD *)v5;
        v21 = *(_QWORD *)(v5 + 8);
        *(_QWORD *)v5 = 0;
        *(_QWORD *)(*(_QWORD *)(Pool2 + 184) + 32LL) = v21;
        *(_QWORD *)(v5 + 8) = 0;
        a2[3] = Pool2;
        v22 = *(_QWORD *)(Pool2 + 184);
        RpcAsyncInitializeHandle((PRPC_ASYNC_STATE)(v22 + 184), 0x58u);
        *(_DWORD *)(v22 + 228) = 2;
        *(_QWORD *)(v22 + 232) = WskKnrRpcComplete;
        *(_QWORD *)(v22 + 208) = Pool2;
        if ( (BYTE3(xmmword_1400875E0) & 1) != 0 )
          WPP_SF_q(1048, 13, WPP_5e35edc2639936f2cd25c7f5a05fa440_Traceguids, Irp);
        WskKnrRpcInvoke(Pool2, v23, v24);
        return 259;
      }
    }
    else
    {
      v13 = -1073741670;
    }
    v7 = v6;
    goto LABEL_11;
  }
  v14 = 1;
LABEL_33:
  if ( (BYTE3(xmmword_1400875D0) & 1) != 0 )
    WPP_SF_qD(536, 14, WPP_5e35edc2639936f2cd25c7f5a05fa440_Traceguids, Irp, v13);
  if ( Pool2 )
    WskKnrFreeRequest((PERESOURCE)Pool2);
  if ( v7 )
    PsReturnPoolQuota(*(PEPROCESS *)(v5 + 16), (POOL_TYPE)512, 0xD8u);
  if ( v6 )
    ObfDereferenceObject(*(PVOID *)(v5 + 16));
  if ( v14 )
    AfdWskDereferenceClient(v4);
  Irp->IoStatus.Status = v13;
  Irp->IoStatus.Information = 0;
  IofCompleteRequest(Irp, 0);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140049030  push    rbx
0x140049032  push    rbp
0x140049033  push    rsi
0x140049034  push    rdi
0x140049035  push    r12
0x140049037  push    r13
0x140049039  push    r14
0x14004903b  push    r15
0x14004903d  sub     rsp, 48h
0x140049041  mov     r13, [rdx+8]
0x140049045  xor     ebx, ebx
0x140049047  mov     rdi, [rdx+10h]
0x14004904b  mov     r15d, ebx
0x14004904e  mov     r14d, ebx
0x140049051  mov     esi, ebx
0x140049053  mov     r12, rdx
0x140049056  mov     rbp, rcx
0x140049059  test    byte ptr cs:xmmword_1400875E0+3, 1
0x140049060  jz      short loc_14004907F
0x140049062  mov     r9, gs:188h
0x14004906b  mov     [rsp+88h+var_58], rdi
0x140049070  mov     [rsp+88h+var_60], r13
0x140049075  mov     [rsp+88h+var_68], rcx
0x14004907a  call    WPP_SF_qqqq
0x14004907f  mov     eax, [r13+10h]
0x140049083  test    al, 1
0x140049085  jnz     loc_140049306
0x14004908b  lea     ecx, [rax+2]
0x14004908e  lock cmpxchg [r13+10h], ecx
0x140049094  jnz     short loc_14004907F
0x140049096  mov     rax, [rdi+8]
0x14004909a  mov     [rsp+88h+arg_8], 1
0x1400490a5  test    rax, rax
0x1400490a8  jz      short loc_1400490AD
0x1400490aa  mov     [rax], rbx
0x1400490ad  mov     rax, [rdi]
0x1400490b0  test    rax, rax
0x1400490b3  jz      short loc_1400490C1
0x1400490b5  cmp     [rdi+8], rbx
0x1400490b9  jz      short loc_1400490C1
0x1400490bb  cmp     [rax+8], rbx
0x1400490bf  jnz     short loc_1400490D3
0x1400490c1  mov     ebx, 0C000000Dh
0x1400490c6  mov     r12d, [rsp+88h+arg_8]
0x1400490ce  jmp     loc_140049313
0x1400490d3  cmp     [rdi+10h], rbx
0x1400490d7  jnz     short loc_14004914A
0x1400490d9  cmp     [rdi+18h], rbx
0x1400490dd  jnz     short loc_1400490C1
0x1400490df  mov     rcx, [rdi+10h]; Object
0x1400490e3  test    rcx, rcx
0x1400490e6  jz      short loc_140049121
0x1400490e8  call    cs:__imp_ObfReferenceObject
0x1400490ef  nop     dword ptr [rax+rax+00h]
0x1400490f4  mov     rcx, [rdi+10h]; Process
0x1400490f8  mov     edx, 200h; PoolType
0x1400490fd  mov     r8d, 0D8h; Amount
0x140049103  mov     r15d, 1
0x140049109  call    cs:__imp_PsChargeProcessPoolQuota
0x140049110  nop     dword ptr [rax+rax+00h]
0x140049115  mov     ebx, eax
0x140049117  test    eax, eax
0x140049119  js      loc_140049310
0x14004911f  xor     ebx, ebx
0x140049121  cmp     [rdi+10h], rbx
0x140049125  jnz     short loc_140049153
0x140049127  mov     rax, [rdi+18h]
0x14004912b  neg     rax
0x14004912e  sbb     r14d, r14d
0x140049131  neg     r14d
0x140049134  add     r14d, 2
0x140049138  call    cs:__imp_PsGetCurrentProcess
0x14004913f  nop     dword ptr [rax+rax+00h]
0x140049144  mov     [rdi+10h], rax
0x140049148  jmp     short loc_140049159
0x14004914a  call    WskKnrIsCurrentThreadImpersonated
0x14004914f  test    al, al
0x140049151  jmp     short loc_1400490DD
0x140049153  mov     r14d, 3
0x140049159  mov     edx, 0D8h
0x14004915e  mov     ecx, 40h ; '@'
0x140049163  mov     r8d, 73524E4Bh
0x140049169  call    cs:__imp_ExAllocatePool2
0x140049170  nop     dword ptr [rax+rax+00h]
0x140049175  mov     rsi, rax
0x140049178  test    rax, rax
0x14004917b  jnz     short loc_14004918A
0x14004917d  mov     ebx, 0C000009Ah
0x140049182  mov     r14d, r15d
0x140049185  jmp     loc_1400490C6
0x14004918a  mov     edx, 110h
0x14004918f  mov     r8d, 73524E4Bh
0x140049195  lea     ecx, [rdx-10h]
0x140049198  call    cs:__imp_ExAllocatePool2
0x14004919f  nop     dword ptr [rax+rax+00h]
0x1400491a4  mov     [rsi+0B8h], rax
0x1400491ab  test    rax, rax
0x1400491ae  jz      short loc_14004917D
0x1400491b0  mov     rcx, rsi; Resource
0x1400491b3  call    cs:__imp_ExInitializeResourceLite
0x1400491ba  nop     dword ptr [rax+rax+00h]
0x1400491bf  mov     ebx, eax
0x1400491c1  test    eax, eax
0x1400491c3  js      short loc_140049182
0x1400491c5  or      dword ptr [rsi+0A4h], 20h
0x1400491cc  call    AfdPodGetCurrent
0x1400491d1  mov     rcx, rax
0x1400491d4  mov     [rsi+0C0h], rax
0x1400491db  call    cs:__imp_PsReferenceSiloContext
0x1400491e2  nop     dword ptr [rax+rax+00h]
0x1400491e7  test    byte ptr cs:xmmword_1400875E0+3, 1
0x1400491ee  jz      short loc_140049217
0x1400491f0  mov     rax, [rsi+0C0h]
0x1400491f7  lea     r8, WPP_5e35edc2639936f2cd25c7f5a05fa440_Traceguids
0x1400491fe  mov     edx, 0Ch
0x140049203  mov     ecx, 418h
0x140049208  mov     r9, rbp
0x14004920b  mov     eax, [rax+8]
0x14004920e  mov     dword ptr [rsp+88h+var_68], eax
0x140049212  call    WPP_SF_qD
0x140049217  mov     ecx, [rsi+0A4h]
0x14004921d  lea     eax, ds:0[r15*4]
0x140049225  mov     [rsi+70h], r13
0x140049229  and     ecx, 0FFFFFFFBh
0x14004922c  mov     [rsi+78h], rbp
0x140049230  or      ecx, eax
0x140049232  or      ecx, 3
0x140049235  mov     edx, 58h ; 'X'; Size
0x14004923a  mov     [rsi+0A4h], ecx
0x140049240  mov     rcx, [rsi+0B8h]
0x140049247  mov     rax, [rdi+10h]
0x14004924b  mov     [rcx], rax
0x14004924e  mov     rcx, [rsi+0B8h]
0x140049255  mov     rax, [rdi+18h]
0x140049259  mov     [rcx+8], rax
0x14004925d  mov     rax, [rsi+0B8h]
0x140049264  mov     [rax+10h], r14d
0x140049268  mov     rcx, [rsi+0B8h]
0x14004926f  mov     rax, [rdi]
0x140049272  mov     [rcx+18h], rax
0x140049276  mov     rax, [rdi+8]
0x14004927a  mov     qword ptr [rdi], 0
0x140049281  mov     rcx, [rsi+0B8h]
0x140049288  mov     [rcx+20h], rax
0x14004928c  mov     qword ptr [rdi+8], 0
0x140049294  mov     [r12+18h], rsi
0x140049299  mov     rbx, [rsi+0B8h]
0x1400492a0  lea     rcx, [rbx+0B8h]; pAsync
0x1400492a7  call    cs:__imp_RpcAsyncInitializeHandle
0x1400492ae  nop     dword ptr [rax+rax+00h]
0x1400492b3  lea     rax, WskKnrRpcComplete
0x1400492ba  mov     dword ptr [rbx+0E4h], 2
0x1400492c4  mov     [rbx+0E8h], rax
0x1400492cb  mov     [rbx+0D0h], rsi
0x1400492d2  test    byte ptr cs:xmmword_1400875E0+3, 1
0x1400492d9  jz      short loc_1400492F4
0x1400492db  mov     edx, 0Dh
0x1400492e0  lea     r8, WPP_5e35edc2639936f2cd25c7f5a05fa440_Traceguids
0x1400492e7  mov     ecx, 418h
0x1400492ec  mov     r9, rbp
0x1400492ef  call    WPP_SF_q
0x1400492f4  mov     rcx, rsi
0x1400492f7  call    WskKnrRpcInvoke
0x1400492fc  mov     eax, 103h
0x140049301  jmp     loc_1400493A6
0x140049306  mov     r12d, ebx
0x140049309  mov     ebx, 0C0000008h
0x14004930e  jmp     short loc_140049313
0x140049310  mov     r12d, r15d
0x140049313  test    byte ptr cs:xmmword_1400875D0+3, 1
0x14004931a  jz      short loc_140049339
0x14004931c  mov     edx, 0Eh
0x140049321  mov     dword ptr [rsp+88h+var_68], ebx
0x140049325  mov     ecx, 218h
0x14004932a  lea     r8, WPP_5e35edc2639936f2cd25c7f5a05fa440_Traceguids
0x140049331  mov     r9, rbp
0x140049334  call    WPP_SF_qD
0x140049339  test    rsi, rsi
0x14004933c  jz      short loc_140049346
0x14004933e  mov     rcx, rsi; Resource
0x140049341  call    WskKnrFreeRequest
0x140049346  test    r14d, r14d
0x140049349  jz      short loc_140049366
0x14004934b  mov     rcx, [rdi+10h]; Process
0x14004934f  mov     edx, 200h; PoolType
0x140049354  mov     r8d, 0D8h; Amount
0x14004935a  call    cs:__imp_PsReturnPoolQuota
0x140049361  nop     dword ptr [rax+rax+00h]
0x140049366  test    r15d, r15d
0x140049369  jz      short loc_14004937B
0x14004936b  mov     rcx, [rdi+10h]; Object
0x14004936f  call    cs:__imp_ObfDereferenceObject
0x140049376  nop     dword ptr [rax+rax+00h]
0x14004937b  test    r12d, r12d
0x14004937e  jz      short loc_140049388
0x140049380  mov     rcx, r13
0x140049383  call    AfdWskDereferenceClient
0x140049388  xor     edx, edx; PriorityBoost
0x14004938a  mov     [rbp+30h], ebx
0x14004938d  mov     rcx, rbp; Irp
0x140049390  mov     qword ptr [rbp+38h], 0
0x140049398  call    cs:__imp_IofCompleteRequest
0x14004939f  nop     dword ptr [rax+rax+00h]
0x1400493a4  mov     eax, ebx
0x1400493a6  add     rsp, 48h
0x1400493aa  pop     r15
0x1400493ac  pop     r14
0x1400493ae  pop     r13
0x1400493b0  pop     r12
0x1400493b2  pop     rdi
0x1400493b3  pop     rsi
0x1400493b4  pop     rbp
0x1400493b5  pop     rbx
0x1400493b6  retn
```
