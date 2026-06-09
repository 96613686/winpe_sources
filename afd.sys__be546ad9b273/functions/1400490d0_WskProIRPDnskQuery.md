# WskProIRPDnskQuery

- ea: `0x1400490d0`
- end: `0x140049458`
- name: `WskProIRPDnskQuery`
- size: `904`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140032db0`

## callees

- `0x140002f44`
- `0x14001087c`
- `0x140029ccc`
- `0x1400402ac`
- `0x140048f4c`
- `0x1400490d0`
- `0x14009304c`
- `0x1400930cc`
- `0x140093580`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1400491a9`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1400491a9`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400493fa`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400493fa`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400491d8`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400491d8`
- `ntoskrnl!ExInitializeResourceLite` at `0x140049253`
- `ntoskrnl!ExInitializeResourceLite` at `0x140049253`
- `ntoskrnl!PsReferenceSiloContext` at `0x14004927b`
- `ntoskrnl!PsReferenceSiloContext` at `0x14004927b`
- `ntoskrnl!ObfReferenceObject` at `0x140049188`
- `ntoskrnl!ObfReferenceObject` at `0x140049188`
- `ntoskrnl!IofCompleteRequest` at `0x140049438`
- `ntoskrnl!IofCompleteRequest` at `0x140049438`
- `ntoskrnl!ObfDereferenceObject` at `0x14004940f`
- `ntoskrnl!ObfDereferenceObject` at `0x14004940f`
- `ntoskrnl!ExAllocatePool2` at `0x140049209`
- `ntoskrnl!ExAllocatePool2` at `0x140049238`
- `ntoskrnl!ExAllocatePool2` at `0x140049209`
- `ntoskrnl!ExAllocatePool2` at `0x140049238`
- `msrpc!RpcAsyncInitializeHandle` at `0x140049347`
- `msrpc!RpcAsyncInitializeHandle` at `0x140049347`

## pseudocode

```c
__int64 __fastcall WskProIRPDnskQuery(PIRP Irp, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r13
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

  v4 = a2[1];
  v5 = a2[2];
  v6 = 0;
  v7 = 0;
  Pool2 = 0;
  if ( (BYTE3(xmmword_1400875E0) & 1) != 0 )
    WPP_SF_qqqq(Irp, a2, a3, KeGetCurrentThread(), Irp, v4, v5);
  do
  {
    v11 = *(_DWORD *)(v4 + 16);
    if ( (v11 & 1) != 0 )
    {
      v14 = 0;
      v13 = -1073741816;
      goto LABEL_33;
    }
  }
  while ( v11 != _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 16), v11 + 2, v11) );
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
        WskKnrRpcInvoke(Pool2);
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
0x1400490d0  push    rbx
0x1400490d2  push    rbp
0x1400490d3  push    rsi
0x1400490d4  push    rdi
0x1400490d5  push    r12
0x1400490d7  push    r13
0x1400490d9  push    r14
0x1400490db  push    r15
0x1400490dd  sub     rsp, 48h
0x1400490e1  mov     r13, [rdx+8]
0x1400490e5  xor     ebx, ebx
0x1400490e7  mov     rdi, [rdx+10h]
0x1400490eb  mov     r15d, ebx
0x1400490ee  mov     r14d, ebx
0x1400490f1  mov     esi, ebx
0x1400490f3  mov     r12, rdx
0x1400490f6  mov     rbp, rcx
0x1400490f9  test    byte ptr cs:xmmword_1400875E0+3, 1
0x140049100  jz      short loc_14004911F
0x140049102  mov     r9, gs:188h
0x14004910b  mov     [rsp+88h+var_58], rdi
0x140049110  mov     [rsp+88h+var_60], r13
0x140049115  mov     [rsp+88h+var_68], rcx
0x14004911a  call    WPP_SF_qqqq
0x14004911f  mov     eax, [r13+10h]
0x140049123  test    al, 1
0x140049125  jnz     loc_1400493A6
0x14004912b  lea     ecx, [rax+2]
0x14004912e  lock cmpxchg [r13+10h], ecx
0x140049134  jnz     short loc_14004911F
0x140049136  mov     rax, [rdi+8]
0x14004913a  mov     [rsp+88h+arg_8], 1
0x140049145  test    rax, rax
0x140049148  jz      short loc_14004914D
0x14004914a  mov     [rax], rbx
0x14004914d  mov     rax, [rdi]
0x140049150  test    rax, rax
0x140049153  jz      short loc_140049161
0x140049155  cmp     [rdi+8], rbx
0x140049159  jz      short loc_140049161
0x14004915b  cmp     [rax+8], rbx
0x14004915f  jnz     short loc_140049173
0x140049161  mov     ebx, 0C000000Dh
0x140049166  mov     r12d, [rsp+88h+arg_8]
0x14004916e  jmp     loc_1400493B3
0x140049173  cmp     [rdi+10h], rbx
0x140049177  jnz     short loc_1400491EA
0x140049179  cmp     [rdi+18h], rbx
0x14004917d  jnz     short loc_140049161
0x14004917f  mov     rcx, [rdi+10h]; Object
0x140049183  test    rcx, rcx
0x140049186  jz      short loc_1400491C1
0x140049188  call    cs:__imp_ObfReferenceObject
0x14004918f  nop     dword ptr [rax+rax+00h]
0x140049194  mov     rcx, [rdi+10h]; Process
0x140049198  mov     edx, 200h; PoolType
0x14004919d  mov     r8d, 0D8h; Amount
0x1400491a3  mov     r15d, 1
0x1400491a9  call    cs:__imp_PsChargeProcessPoolQuota
0x1400491b0  nop     dword ptr [rax+rax+00h]
0x1400491b5  mov     ebx, eax
0x1400491b7  test    eax, eax
0x1400491b9  js      loc_1400493B0
0x1400491bf  xor     ebx, ebx
0x1400491c1  cmp     [rdi+10h], rbx
0x1400491c5  jnz     short loc_1400491F3
0x1400491c7  mov     rax, [rdi+18h]
0x1400491cb  neg     rax
0x1400491ce  sbb     r14d, r14d
0x1400491d1  neg     r14d
0x1400491d4  add     r14d, 2
0x1400491d8  call    cs:__imp_PsGetCurrentProcess
0x1400491df  nop     dword ptr [rax+rax+00h]
0x1400491e4  mov     [rdi+10h], rax
0x1400491e8  jmp     short loc_1400491F9
0x1400491ea  call    WskKnrIsCurrentThreadImpersonated
0x1400491ef  test    al, al
0x1400491f1  jmp     short loc_14004917D
0x1400491f3  mov     r14d, 3
0x1400491f9  mov     edx, 0D8h
0x1400491fe  mov     ecx, 40h ; '@'
0x140049203  mov     r8d, 73524E4Bh
0x140049209  call    cs:__imp_ExAllocatePool2
0x140049210  nop     dword ptr [rax+rax+00h]
0x140049215  mov     rsi, rax
0x140049218  test    rax, rax
0x14004921b  jnz     short loc_14004922A
0x14004921d  mov     ebx, 0C000009Ah
0x140049222  mov     r14d, r15d
0x140049225  jmp     loc_140049166
0x14004922a  mov     edx, 110h
0x14004922f  mov     r8d, 73524E4Bh
0x140049235  lea     ecx, [rdx-10h]
0x140049238  call    cs:__imp_ExAllocatePool2
0x14004923f  nop     dword ptr [rax+rax+00h]
0x140049244  mov     [rsi+0B8h], rax
0x14004924b  test    rax, rax
0x14004924e  jz      short loc_14004921D
0x140049250  mov     rcx, rsi; Resource
0x140049253  call    cs:__imp_ExInitializeResourceLite
0x14004925a  nop     dword ptr [rax+rax+00h]
0x14004925f  mov     ebx, eax
0x140049261  test    eax, eax
0x140049263  js      short loc_140049222
0x140049265  or      dword ptr [rsi+0A4h], 20h
0x14004926c  call    AfdPodGetCurrent
0x140049271  mov     rcx, rax
0x140049274  mov     [rsi+0C0h], rax
0x14004927b  call    cs:__imp_PsReferenceSiloContext
0x140049282  nop     dword ptr [rax+rax+00h]
0x140049287  test    byte ptr cs:xmmword_1400875E0+3, 1
0x14004928e  jz      short loc_1400492B7
0x140049290  mov     rax, [rsi+0C0h]
0x140049297  lea     r8, WPP_5e35edc2639936f2cd25c7f5a05fa440_Traceguids
0x14004929e  mov     edx, 0Ch
0x1400492a3  mov     ecx, 418h
0x1400492a8  mov     r9, rbp
0x1400492ab  mov     eax, [rax+8]
0x1400492ae  mov     dword ptr [rsp+88h+var_68], eax
0x1400492b2  call    WPP_SF_qD
0x1400492b7  mov     ecx, [rsi+0A4h]
0x1400492bd  lea     eax, ds:0[r15*4]
0x1400492c5  mov     [rsi+70h], r13
0x1400492c9  and     ecx, 0FFFFFFFBh
0x1400492cc  mov     [rsi+78h], rbp
0x1400492d0  or      ecx, eax
0x1400492d2  or      ecx, 3
0x1400492d5  mov     edx, 58h ; 'X'; Size
0x1400492da  mov     [rsi+0A4h], ecx
0x1400492e0  mov     rcx, [rsi+0B8h]
0x1400492e7  mov     rax, [rdi+10h]
0x1400492eb  mov     [rcx], rax
0x1400492ee  mov     rcx, [rsi+0B8h]
0x1400492f5  mov     rax, [rdi+18h]
0x1400492f9  mov     [rcx+8], rax
0x1400492fd  mov     rax, [rsi+0B8h]
0x140049304  mov     [rax+10h], r14d
0x140049308  mov     rcx, [rsi+0B8h]
0x14004930f  mov     rax, [rdi]
0x140049312  mov     [rcx+18h], rax
0x140049316  mov     rax, [rdi+8]
0x14004931a  mov     qword ptr [rdi], 0
0x140049321  mov     rcx, [rsi+0B8h]
0x140049328  mov     [rcx+20h], rax
0x14004932c  mov     qword ptr [rdi+8], 0
0x140049334  mov     [r12+18h], rsi
0x140049339  mov     rbx, [rsi+0B8h]
0x140049340  lea     rcx, [rbx+0B8h]; pAsync
0x140049347  call    cs:__imp_RpcAsyncInitializeHandle
0x14004934e  nop     dword ptr [rax+rax+00h]
0x140049353  lea     rax, WskKnrRpcComplete
0x14004935a  mov     dword ptr [rbx+0E4h], 2
0x140049364  mov     [rbx+0E8h], rax
0x14004936b  mov     [rbx+0D0h], rsi
0x140049372  test    byte ptr cs:xmmword_1400875E0+3, 1
0x140049379  jz      short loc_140049394
0x14004937b  mov     edx, 0Dh
0x140049380  lea     r8, WPP_5e35edc2639936f2cd25c7f5a05fa440_Traceguids
0x140049387  mov     ecx, 418h
0x14004938c  mov     r9, rbp
0x14004938f  call    WPP_SF_q
0x140049394  mov     rcx, rsi
0x140049397  call    WskKnrRpcInvoke
0x14004939c  mov     eax, 103h
0x1400493a1  jmp     loc_140049446
0x1400493a6  mov     r12d, ebx
0x1400493a9  mov     ebx, 0C0000008h
0x1400493ae  jmp     short loc_1400493B3
0x1400493b0  mov     r12d, r15d
0x1400493b3  test    byte ptr cs:xmmword_1400875D0+3, 1
0x1400493ba  jz      short loc_1400493D9
0x1400493bc  mov     edx, 0Eh
0x1400493c1  mov     dword ptr [rsp+88h+var_68], ebx
0x1400493c5  mov     ecx, 218h
0x1400493ca  lea     r8, WPP_5e35edc2639936f2cd25c7f5a05fa440_Traceguids
0x1400493d1  mov     r9, rbp
0x1400493d4  call    WPP_SF_qD
0x1400493d9  test    rsi, rsi
0x1400493dc  jz      short loc_1400493E6
0x1400493de  mov     rcx, rsi; Resource
0x1400493e1  call    WskKnrFreeRequest
0x1400493e6  test    r14d, r14d
0x1400493e9  jz      short loc_140049406
0x1400493eb  mov     rcx, [rdi+10h]; Process
0x1400493ef  mov     edx, 200h; PoolType
0x1400493f4  mov     r8d, 0D8h; Amount
0x1400493fa  call    cs:__imp_PsReturnPoolQuota
0x140049401  nop     dword ptr [rax+rax+00h]
0x140049406  test    r15d, r15d
0x140049409  jz      short loc_14004941B
0x14004940b  mov     rcx, [rdi+10h]; Object
0x14004940f  call    cs:__imp_ObfDereferenceObject
0x140049416  nop     dword ptr [rax+rax+00h]
0x14004941b  test    r12d, r12d
0x14004941e  jz      short loc_140049428
0x140049420  mov     rcx, r13
0x140049423  call    AfdWskDereferenceClient
0x140049428  xor     edx, edx; PriorityBoost
0x14004942a  mov     [rbp+30h], ebx
0x14004942d  mov     rcx, rbp; Irp
0x140049430  mov     qword ptr [rbp+38h], 0
0x140049438  call    cs:__imp_IofCompleteRequest
0x14004943f  nop     dword ptr [rax+rax+00h]
0x140049444  mov     eax, ebx
0x140049446  add     rsp, 48h
0x14004944a  pop     r15
0x14004944c  pop     r14
0x14004944e  pop     r13
0x140049450  pop     r12
0x140049452  pop     rdi
0x140049453  pop     rsi
0x140049454  pop     rbp
0x140049455  pop     rbx
0x140049456  retn
```
