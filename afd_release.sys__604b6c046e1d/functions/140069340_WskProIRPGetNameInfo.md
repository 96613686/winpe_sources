# WskProIRPGetNameInfo

- ea: `0x140069340`
- end: `0x1400696b0`
- name: `WskProIRPGetNameInfo`
- size: `880`
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
- `0x140069340`
- `0x140072800`
- `0x140072b00`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140069423`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140069423`
- `ntoskrnl!PsReturnPoolQuota` at `0x140069651`
- `ntoskrnl!PsReturnPoolQuota` at `0x140069651`
- `ntoskrnl!PsGetCurrentProcess` at `0x14006944f`
- `ntoskrnl!PsGetCurrentProcess` at `0x14006944f`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400694d0`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400694d0`
- `ntoskrnl!PsReferenceSiloContext` at `0x1400694f8`
- `ntoskrnl!PsReferenceSiloContext` at `0x1400694f8`
- `ntoskrnl!ObfReferenceObject` at `0x140069405`
- `ntoskrnl!ObfReferenceObject` at `0x140069405`
- `ntoskrnl!IofCompleteRequest` at `0x140069690`
- `ntoskrnl!IofCompleteRequest` at `0x140069690`
- `ntoskrnl!ObfDereferenceObject` at `0x140069666`
- `ntoskrnl!ObfDereferenceObject` at `0x140069666`
- `ntoskrnl!ExAllocatePool2` at `0x140069476`
- `ntoskrnl!ExAllocatePool2` at `0x1400694b5`
- `ntoskrnl!ExAllocatePool2` at `0x140069476`
- `ntoskrnl!ExAllocatePool2` at `0x1400694b5`
- `msrpc!RpcAsyncInitializeHandle` at `0x1400695c4`
- `msrpc!RpcAsyncInitializeHandle` at `0x1400695c4`

## pseudocode

```c
__int64 __fastcall WskProIRPGetNameInfo(PIRP Irp, _QWORD *a2, __int64 a3, __int64 a4)
{
  volatile signed __int32 *v4; // r13
  __int64 v5; // rdi
  unsigned __int8 v6; // r15
  unsigned __int8 v7; // bp
  __int64 v8; // rsi
  signed __int32 v11; // eax
  unsigned int v12; // eax
  int v13; // ebx
  char v14; // r12
  __int64 v15; // rax
  __int64 v16; // rax
  void *v17; // rcx
  int v18; // ebp
  void *Pool2; // rax
  __int64 v20; // rax
  __int64 Current; // rax
  int v22; // eax
  __int64 v23; // rbx
  __int64 v24; // rdx
  __int64 v25; // r8

  v4 = (volatile signed __int32 *)a2[1];
  v5 = a2[2];
  v6 = 0;
  v7 = 0;
  v8 = 0;
  if ( (BYTE3(xmmword_1400875E0) & 1) != 0 )
    WPP_SF_q(1048, 36, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids, Irp);
  do
  {
    v11 = *((_DWORD *)v4 + 4);
    if ( (v11 & 1) != 0 )
    {
      v14 = 0;
      v13 = -1073741816;
      goto LABEL_31;
    }
  }
  while ( v11 != _InterlockedCompareExchange(v4 + 4, v11 + 2, v11) );
  if ( !*(_QWORD *)v5
    || (v12 = *(_DWORD *)(v5 + 8)) == 0
    || v12 > 0x80
    || ((v15 = *(_QWORD *)(v5 + 16)) == 0 || !*(_WORD *)(v15 + 2))
    && ((v16 = *(_QWORD *)(v5 + 24)) == 0 || !*(_WORD *)(v16 + 2)) )
  {
LABEL_8:
    v13 = -1073741811;
LABEL_9:
    v14 = 1;
    goto LABEL_31;
  }
  if ( *(_QWORD *)(v5 + 40) )
  {
    if ( WskKnrIsCurrentThreadImpersonated() == 1 )
      goto LABEL_8;
  }
  else if ( *(_QWORD *)(v5 + 48) )
  {
    goto LABEL_8;
  }
  v17 = *(void **)(v5 + 40);
  if ( !v17
    || (ObfReferenceObject(v17),
        v6 = 1,
        v13 = PsChargeProcessPoolQuota(*(PEPROCESS *)(v5 + 40), (POOL_TYPE)512, 0xD8u),
        v13 >= 0) )
  {
    if ( *(_QWORD *)(v5 + 40) )
    {
      v18 = 3;
    }
    else
    {
      v18 = (*(_QWORD *)(v5 + 48) != 0) + 2;
      *(_QWORD *)(v5 + 40) = PsGetCurrentProcess(v17, a2, a3, a4);
    }
    Pool2 = (void *)ExAllocatePool2(64, 216, 1934773835);
    v8 = (__int64)Pool2;
    if ( Pool2
      && (memset(Pool2, 0, 0xD8u), v20 = ExAllocatePool2(256, 272, 1934773835), (*(_QWORD *)(v8 + 184) = v20) != 0) )
    {
      v13 = ExInitializeResourceLite((PERESOURCE)v8);
      if ( v13 >= 0 )
      {
        *(_DWORD *)(v8 + 164) |= 0x20u;
        Current = AfdPodGetCurrent();
        *(_QWORD *)(v8 + 192) = Current;
        PsReferenceSiloContext(Current);
        v22 = *(_DWORD *)(v8 + 164);
        *(_QWORD *)(v8 + 112) = v4;
        *(_QWORD *)(v8 + 120) = Irp;
        *(_DWORD *)(v8 + 164) = v22 & 0xFFFFFFFA | (4 * v6) | 2;
        **(_QWORD **)(v8 + 184) = *(_QWORD *)(v5 + 40);
        *(_QWORD *)(*(_QWORD *)(v8 + 184) + 8LL) = *(_QWORD *)(v5 + 48);
        *(_DWORD *)(*(_QWORD *)(v8 + 184) + 16LL) = v18;
        *(_QWORD *)(*(_QWORD *)(v8 + 184) + 160LL) = *(_QWORD *)(v5 + 16);
        *(_QWORD *)(*(_QWORD *)(v8 + 184) + 168LL) = *(_QWORD *)(v5 + 24);
        *(_DWORD *)(*(_QWORD *)(v8 + 184) + 176LL) = *(_DWORD *)(v5 + 32);
        memmove((void *)(*(_QWORD *)(v8 + 184) + 24LL), *(const void **)v5, *(unsigned int *)(v5 + 8));
        *(_DWORD *)(*(_QWORD *)(v8 + 184) + 152LL) = *(_DWORD *)(v5 + 8);
        a2[3] = v8;
        v23 = *(_QWORD *)(v8 + 184);
        RpcAsyncInitializeHandle((PRPC_ASYNC_STATE)(v23 + 184), 0x58u);
        *(_DWORD *)(v23 + 228) = 2;
        *(_QWORD *)(v23 + 232) = WskKnrRpcComplete;
        *(_QWORD *)(v23 + 208) = v8;
        WskKnrRpcInvoke(v8, v24, v25);
        return 259;
      }
    }
    else
    {
      v13 = -1073741670;
    }
    v7 = v6;
    goto LABEL_9;
  }
  v14 = 1;
LABEL_31:
  if ( (BYTE3(xmmword_1400875D0) & 1) != 0 )
    WPP_SF_q(536, 37, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids, Irp);
  if ( v8 )
    WskKnrFreeRequest((PERESOURCE)v8);
  if ( v7 )
    PsReturnPoolQuota(*(PEPROCESS *)(v5 + 40), (POOL_TYPE)512, 0xD8u);
  if ( v6 )
    ObfDereferenceObject(*(PVOID *)(v5 + 40));
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
0x140069340  push    rbx
0x140069342  push    rbp
0x140069343  push    rsi
0x140069344  push    rdi
0x140069345  push    r12
0x140069347  push    r13
0x140069349  push    r14
0x14006934b  push    r15
0x14006934d  sub     rsp, 28h
0x140069351  mov     r13, [rdx+8]
0x140069355  xor     ebx, ebx
0x140069357  mov     rdi, [rdx+10h]
0x14006935b  mov     r15b, bl
0x14006935e  mov     bpl, bl
0x140069361  mov     esi, ebx
0x140069363  mov     r12, rdx
0x140069366  mov     r14, rcx
0x140069369  test    byte ptr cs:xmmword_1400875E0+3, 1
0x140069370  jz      short loc_140069389
0x140069372  lea     edx, [rbx+24h]
0x140069375  mov     ecx, 418h
0x14006937a  mov     r9, r14
0x14006937d  lea     r8, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids
0x140069384  call    WPP_SF_q
0x140069389  mov     eax, [r13+10h]
0x14006938d  test    al, 1
0x14006938f  jnz     loc_140069601
0x140069395  lea     ecx, [rax+2]
0x140069398  lock cmpxchg [r13+10h], ecx
0x14006939e  jnz     short loc_140069389
0x1400693a0  mov     [rsp+68h+arg_8], 1
0x1400693a5  cmp     [rdi], rbx
0x1400693a8  jz      short loc_1400693B8
0x1400693aa  mov     eax, [rdi+8]
0x1400693ad  test    eax, eax
0x1400693af  jz      short loc_1400693B8
0x1400693b1  cmp     eax, 80h
0x1400693b6  jbe     short loc_1400693C7
0x1400693b8  mov     ebx, 0C000000Dh
0x1400693bd  mov     r12b, [rsp+68h+arg_8]
0x1400693c2  jmp     loc_14006960E
0x1400693c7  mov     rax, [rdi+10h]
0x1400693cb  test    rax, rax
0x1400693ce  jz      short loc_1400693D6
0x1400693d0  cmp     [rax+2], bx
0x1400693d4  jnz     short loc_1400693E5
0x1400693d6  mov     rax, [rdi+18h]
0x1400693da  test    rax, rax
0x1400693dd  jz      short loc_1400693B8
0x1400693df  cmp     [rax+2], bx
0x1400693e3  jz      short loc_1400693B8
0x1400693e5  cmp     [rdi+28h], rbx
0x1400693e9  jnz     short loc_1400693F3
0x1400693eb  cmp     [rdi+30h], rbx
0x1400693ef  jz      short loc_1400693FC
0x1400693f1  jmp     short loc_1400693B8
0x1400693f3  call    WskKnrIsCurrentThreadImpersonated
0x1400693f8  cmp     al, 1
0x1400693fa  jz      short loc_1400693B8
0x1400693fc  mov     rcx, [rdi+28h]; Object
0x140069400  test    rcx, rcx
0x140069403  jz      short loc_14006943B
0x140069405  call    cs:__imp_ObfReferenceObject
0x14006940c  nop     dword ptr [rax+rax+00h]
0x140069411  mov     rcx, [rdi+28h]; Process
0x140069415  mov     edx, 200h; PoolType
0x14006941a  mov     r8d, 0D8h; Amount
0x140069420  mov     r15b, 1
0x140069423  call    cs:__imp_PsChargeProcessPoolQuota
0x14006942a  nop     dword ptr [rax+rax+00h]
0x14006942f  mov     ebx, eax
0x140069431  test    eax, eax
0x140069433  js      loc_14006960B
0x140069439  xor     ebx, ebx
0x14006943b  cmp     [rdi+28h], rbx
0x14006943f  jnz     short loc_140069461
0x140069441  mov     rax, [rdi+30h]
0x140069445  neg     rax
0x140069448  sbb     ebp, ebp
0x14006944a  neg     ebp
0x14006944c  add     ebp, 2
0x14006944f  call    cs:__imp_PsGetCurrentProcess
0x140069456  nop     dword ptr [rax+rax+00h]
0x14006945b  mov     [rdi+28h], rax
0x14006945f  jmp     short loc_140069466
0x140069461  mov     ebp, 3
0x140069466  mov     edx, 0D8h
0x14006946b  mov     ecx, 40h ; '@'
0x140069470  mov     r8d, 73524E4Bh
0x140069476  call    cs:__imp_ExAllocatePool2
0x14006947d  nop     dword ptr [rax+rax+00h]
0x140069482  mov     rsi, rax
0x140069485  test    rax, rax
0x140069488  jnz     short loc_140069497
0x14006948a  mov     ebx, 0C000009Ah
0x14006948f  mov     bpl, r15b
0x140069492  jmp     loc_1400693BD
0x140069497  xor     edx, edx; Val
0x140069499  mov     r8d, 0D8h; Size
0x14006949f  mov     rcx, rsi; void *
0x1400694a2  call    memset
0x1400694a7  mov     edx, 110h
0x1400694ac  mov     r8d, 73524E4Bh
0x1400694b2  lea     ecx, [rdx-10h]
0x1400694b5  call    cs:__imp_ExAllocatePool2
0x1400694bc  nop     dword ptr [rax+rax+00h]
0x1400694c1  mov     [rsi+0B8h], rax
0x1400694c8  test    rax, rax
0x1400694cb  jz      short loc_14006948A
0x1400694cd  mov     rcx, rsi; Resource
0x1400694d0  call    cs:__imp_ExInitializeResourceLite
0x1400694d7  nop     dword ptr [rax+rax+00h]
0x1400694dc  mov     ebx, eax
0x1400694de  test    eax, eax
0x1400694e0  js      short loc_14006948F
0x1400694e2  or      dword ptr [rsi+0A4h], 20h
0x1400694e9  call    AfdPodGetCurrent
0x1400694ee  mov     rcx, rax
0x1400694f1  mov     [rsi+0C0h], rax
0x1400694f8  call    cs:__imp_PsReferenceSiloContext
0x1400694ff  nop     dword ptr [rax+rax+00h]
0x140069504  mov     eax, [rsi+0A4h]
0x14006950a  mov     [rsi+70h], r13
0x14006950e  and     eax, 0FFFFFFFBh
0x140069511  mov     [rsi+78h], r14
0x140069515  movzx   ecx, r15b
0x140069519  shl     ecx, 2
0x14006951c  or      ecx, eax
0x14006951e  and     ecx, 0FFFFFFFEh
0x140069521  or      ecx, 2
0x140069524  mov     [rsi+0A4h], ecx
0x14006952a  mov     rcx, [rsi+0B8h]
0x140069531  mov     rax, [rdi+28h]
0x140069535  mov     [rcx], rax
0x140069538  mov     rcx, [rsi+0B8h]
0x14006953f  mov     rax, [rdi+30h]
0x140069543  mov     [rcx+8], rax
0x140069547  mov     rax, [rsi+0B8h]
0x14006954e  mov     [rax+10h], ebp
0x140069551  mov     rcx, [rsi+0B8h]
0x140069558  mov     rax, [rdi+10h]
0x14006955c  mov     [rcx+0A0h], rax
0x140069563  mov     rcx, [rsi+0B8h]
0x14006956a  mov     rax, [rdi+18h]
0x14006956e  mov     [rcx+0A8h], rax
0x140069575  mov     rcx, [rsi+0B8h]
0x14006957c  mov     eax, [rdi+20h]
0x14006957f  mov     [rcx+0B0h], eax
0x140069585  mov     rcx, [rsi+0B8h]
0x14006958c  mov     r8d, [rdi+8]; Size
0x140069590  add     rcx, 18h; void *
0x140069594  mov     rdx, [rdi]; Src
0x140069597  call    memmove
0x14006959c  mov     rcx, [rsi+0B8h]
0x1400695a3  mov     edx, 58h ; 'X'; Size
0x1400695a8  mov     eax, [rdi+8]
0x1400695ab  mov     [rcx+98h], eax
0x1400695b1  mov     [r12+18h], rsi
0x1400695b6  mov     rbx, [rsi+0B8h]
0x1400695bd  lea     rcx, [rbx+0B8h]; pAsync
0x1400695c4  call    cs:__imp_RpcAsyncInitializeHandle
0x1400695cb  nop     dword ptr [rax+rax+00h]
0x1400695d0  lea     rax, WskKnrRpcComplete
0x1400695d7  mov     dword ptr [rbx+0E4h], 2
0x1400695e1  mov     rcx, rsi
0x1400695e4  mov     [rbx+0E8h], rax
0x1400695eb  mov     [rbx+0D0h], rsi
0x1400695f2  call    WskKnrRpcInvoke
0x1400695f7  mov     eax, 103h
0x1400695fc  jmp     loc_14006969E
0x140069601  mov     r12b, bl
0x140069604  mov     ebx, 0C0000008h
0x140069609  jmp     short loc_14006960E
0x14006960b  mov     r12b, r15b
0x14006960e  test    byte ptr cs:xmmword_1400875D0+3, 1
0x140069615  jz      short loc_140069630
0x140069617  mov     edx, 25h ; '%'
0x14006961c  lea     r8, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids
0x140069623  mov     ecx, 218h
0x140069628  mov     r9, r14
0x14006962b  call    WPP_SF_q
0x140069630  test    rsi, rsi
0x140069633  jz      short loc_14006963D
0x140069635  mov     rcx, rsi; Resource
0x140069638  call    WskKnrFreeRequest
0x14006963d  test    bpl, bpl
0x140069640  jz      short loc_14006965D
0x140069642  mov     rcx, [rdi+28h]; Process
0x140069646  mov     edx, 200h; PoolType
0x14006964b  mov     r8d, 0D8h; Amount
0x140069651  call    cs:__imp_PsReturnPoolQuota
0x140069658  nop     dword ptr [rax+rax+00h]
0x14006965d  test    r15b, r15b
0x140069660  jz      short loc_140069672
0x140069662  mov     rcx, [rdi+28h]; Object
0x140069666  call    cs:__imp_ObfDereferenceObject
0x14006966d  nop     dword ptr [rax+rax+00h]
0x140069672  test    r12b, r12b
0x140069675  jz      short loc_14006967F
0x140069677  mov     rcx, r13
0x14006967a  call    AfdWskDereferenceClient
0x14006967f  xor     edx, edx; PriorityBoost
0x140069681  mov     [r14+30h], ebx
0x140069685  mov     rcx, r14; Irp
0x140069688  mov     qword ptr [r14+38h], 0
0x140069690  call    cs:__imp_IofCompleteRequest
0x140069697  nop     dword ptr [rax+rax+00h]
0x14006969c  mov     eax, ebx
0x14006969e  add     rsp, 28h
0x1400696a2  pop     r15
0x1400696a4  pop     r14
0x1400696a6  pop     r13
0x1400696a8  pop     r12
0x1400696aa  pop     rdi
0x1400696ab  pop     rsi
0x1400696ac  pop     rbp
0x1400696ad  pop     rbx
0x1400696ae  retn
```
