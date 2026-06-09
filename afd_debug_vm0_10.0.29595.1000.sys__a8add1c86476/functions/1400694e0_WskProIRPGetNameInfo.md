# WskProIRPGetNameInfo

- ea: `0x1400694e0`
- end: `0x140069850`
- name: `WskProIRPGetNameInfo`
- size: `880`
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
- `0x1400694e0`
- `0x140072980`
- `0x140072c80`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1400695c3`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1400695c3`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400697f1`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400697f1`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400695ef`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400695ef`
- `ntoskrnl!ExInitializeResourceLite` at `0x140069670`
- `ntoskrnl!ExInitializeResourceLite` at `0x140069670`
- `ntoskrnl!PsReferenceSiloContext` at `0x140069698`
- `ntoskrnl!PsReferenceSiloContext` at `0x140069698`
- `ntoskrnl!ObfReferenceObject` at `0x1400695a5`
- `ntoskrnl!ObfReferenceObject` at `0x1400695a5`
- `ntoskrnl!IofCompleteRequest` at `0x140069830`
- `ntoskrnl!IofCompleteRequest` at `0x140069830`
- `ntoskrnl!ObfDereferenceObject` at `0x140069806`
- `ntoskrnl!ObfDereferenceObject` at `0x140069806`
- `ntoskrnl!ExAllocatePool2` at `0x140069616`
- `ntoskrnl!ExAllocatePool2` at `0x140069655`
- `ntoskrnl!ExAllocatePool2` at `0x140069616`
- `ntoskrnl!ExAllocatePool2` at `0x140069655`
- `msrpc!RpcAsyncInitializeHandle` at `0x140069764`
- `msrpc!RpcAsyncInitializeHandle` at `0x140069764`

## pseudocode

```c
__int64 __fastcall WskProIRPGetNameInfo(struct _OWNER_ENTRY *Irp, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r13
  __int64 v5; // rdi
  unsigned __int8 v6; // r15
  unsigned __int8 v7; // bp
  struct _ERESOURCE *v8; // rsi
  signed __int32 v11; // eax
  unsigned int v12; // eax
  int v13; // ebx
  char v14; // r12
  __int64 v15; // rax
  __int64 v16; // rax
  void *v17; // rcx
  int v18; // ebp
  struct _ERESOURCE *Pool2; // rax
  __int64 v20; // rax
  __int64 Current; // rax
  int v22; // eax
  char *Reserved2; // rbx

  v4 = a2[1];
  v5 = a2[2];
  v6 = 0;
  v7 = 0;
  v8 = 0;
  if ( (BYTE3(xmmword_1400875E0) & 1) != 0 )
    WPP_SF_q(1048, 36, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids, Irp);
  do
  {
    v11 = *(_DWORD *)(v4 + 16);
    if ( (v11 & 1) != 0 )
    {
      v14 = 0;
      v13 = -1073741816;
      goto LABEL_31;
    }
  }
  while ( v11 != _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 16), v11 + 2, v11) );
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
    Pool2 = (struct _ERESOURCE *)ExAllocatePool2(64, 216, 1934773835);
    v8 = Pool2;
    if ( Pool2
      && (memset(Pool2, 0, 0xD8u), v20 = ExAllocatePool2(256, 272, 1934773835), (v8[1].Reserved2 = (PVOID)v20) != 0) )
    {
      v13 = ExInitializeResourceLite(v8);
      if ( v13 >= 0 )
      {
        *((_DWORD *)&v8[1].OwnerEntry.8 + 1) |= 0x20u;
        Current = AfdPodGetCurrent();
        v8[1].CreatorBackTraceIndex = Current;
        PsReferenceSiloContext(Current);
        v22 = *((_DWORD *)&v8[1].OwnerEntry.8 + 1);
        v8[1].SystemResourcesList.Blink = (struct _LIST_ENTRY *)v4;
        v8[1].OwnerTable = Irp;
        *((_DWORD *)&v8[1].OwnerEntry.8 + 1) = v22 & 0xFFFFFFFA | (4 * v6) | 2;
        *(_QWORD *)v8[1].Reserved2 = *(_QWORD *)(v5 + 40);
        *((_QWORD *)v8[1].Reserved2 + 1) = *(_QWORD *)(v5 + 48);
        *((_DWORD *)v8[1].Reserved2 + 4) = v18;
        *((_QWORD *)v8[1].Reserved2 + 20) = *(_QWORD *)(v5 + 16);
        *((_QWORD *)v8[1].Reserved2 + 21) = *(_QWORD *)(v5 + 24);
        *((_DWORD *)v8[1].Reserved2 + 44) = *(_DWORD *)(v5 + 32);
        memmove((char *)v8[1].Reserved2 + 24, *(const void **)v5, *(unsigned int *)(v5 + 8));
        *((_DWORD *)v8[1].Reserved2 + 38) = *(_DWORD *)(v5 + 8);
        a2[3] = v8;
        Reserved2 = (char *)v8[1].Reserved2;
        RpcAsyncInitializeHandle((PRPC_ASYNC_STATE)(Reserved2 + 184), 0x58u);
        *((_DWORD *)Reserved2 + 57) = 2;
        *((_QWORD *)Reserved2 + 29) = WskKnrRpcComplete;
        *((_QWORD *)Reserved2 + 26) = v8;
        WskKnrRpcInvoke(v8);
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
    WskKnrFreeRequest(v8);
  if ( v7 )
    PsReturnPoolQuota(*(PEPROCESS *)(v5 + 40), (POOL_TYPE)512, 0xD8u);
  if ( v6 )
    ObfDereferenceObject(*(PVOID *)(v5 + 40));
  if ( v14 )
    AfdWskDereferenceClient(v4);
  LODWORD(Irp[3].OwnerThread) = v13;
  *(_QWORD *)&Irp[3].0 = 0;
  IofCompleteRequest((PIRP)Irp, 0);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400694e0  push    rbx
0x1400694e2  push    rbp
0x1400694e3  push    rsi
0x1400694e4  push    rdi
0x1400694e5  push    r12
0x1400694e7  push    r13
0x1400694e9  push    r14
0x1400694eb  push    r15
0x1400694ed  sub     rsp, 28h
0x1400694f1  mov     r13, [rdx+8]
0x1400694f5  xor     ebx, ebx
0x1400694f7  mov     rdi, [rdx+10h]
0x1400694fb  mov     r15b, bl
0x1400694fe  mov     bpl, bl
0x140069501  mov     esi, ebx
0x140069503  mov     r12, rdx
0x140069506  mov     r14, rcx
0x140069509  test    byte ptr cs:xmmword_1400875E0+3, 1
0x140069510  jz      short loc_140069529
0x140069512  lea     edx, [rbx+24h]
0x140069515  mov     ecx, 418h
0x14006951a  mov     r9, r14
0x14006951d  lea     r8, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids
0x140069524  call    WPP_SF_q
0x140069529  mov     eax, [r13+10h]
0x14006952d  test    al, 1
0x14006952f  jnz     loc_1400697A1
0x140069535  lea     ecx, [rax+2]
0x140069538  lock cmpxchg [r13+10h], ecx
0x14006953e  jnz     short loc_140069529
0x140069540  mov     [rsp+68h+arg_8], 1
0x140069545  cmp     [rdi], rbx
0x140069548  jz      short loc_140069558
0x14006954a  mov     eax, [rdi+8]
0x14006954d  test    eax, eax
0x14006954f  jz      short loc_140069558
0x140069551  cmp     eax, 80h
0x140069556  jbe     short loc_140069567
0x140069558  mov     ebx, 0C000000Dh
0x14006955d  mov     r12b, [rsp+68h+arg_8]
0x140069562  jmp     loc_1400697AE
0x140069567  mov     rax, [rdi+10h]
0x14006956b  test    rax, rax
0x14006956e  jz      short loc_140069576
0x140069570  cmp     [rax+2], bx
0x140069574  jnz     short loc_140069585
0x140069576  mov     rax, [rdi+18h]
0x14006957a  test    rax, rax
0x14006957d  jz      short loc_140069558
0x14006957f  cmp     [rax+2], bx
0x140069583  jz      short loc_140069558
0x140069585  cmp     [rdi+28h], rbx
0x140069589  jnz     short loc_140069593
0x14006958b  cmp     [rdi+30h], rbx
0x14006958f  jz      short loc_14006959C
0x140069591  jmp     short loc_140069558
0x140069593  call    WskKnrIsCurrentThreadImpersonated
0x140069598  cmp     al, 1
0x14006959a  jz      short loc_140069558
0x14006959c  mov     rcx, [rdi+28h]; Object
0x1400695a0  test    rcx, rcx
0x1400695a3  jz      short loc_1400695DB
0x1400695a5  call    cs:__imp_ObfReferenceObject
0x1400695ac  nop     dword ptr [rax+rax+00h]
0x1400695b1  mov     rcx, [rdi+28h]; Process
0x1400695b5  mov     edx, 200h; PoolType
0x1400695ba  mov     r8d, 0D8h; Amount
0x1400695c0  mov     r15b, 1
0x1400695c3  call    cs:__imp_PsChargeProcessPoolQuota
0x1400695ca  nop     dword ptr [rax+rax+00h]
0x1400695cf  mov     ebx, eax
0x1400695d1  test    eax, eax
0x1400695d3  js      loc_1400697AB
0x1400695d9  xor     ebx, ebx
0x1400695db  cmp     [rdi+28h], rbx
0x1400695df  jnz     short loc_140069601
0x1400695e1  mov     rax, [rdi+30h]
0x1400695e5  neg     rax
0x1400695e8  sbb     ebp, ebp
0x1400695ea  neg     ebp
0x1400695ec  add     ebp, 2
0x1400695ef  call    cs:__imp_PsGetCurrentProcess
0x1400695f6  nop     dword ptr [rax+rax+00h]
0x1400695fb  mov     [rdi+28h], rax
0x1400695ff  jmp     short loc_140069606
0x140069601  mov     ebp, 3
0x140069606  mov     edx, 0D8h
0x14006960b  mov     ecx, 40h ; '@'
0x140069610  mov     r8d, 73524E4Bh
0x140069616  call    cs:__imp_ExAllocatePool2
0x14006961d  nop     dword ptr [rax+rax+00h]
0x140069622  mov     rsi, rax
0x140069625  test    rax, rax
0x140069628  jnz     short loc_140069637
0x14006962a  mov     ebx, 0C000009Ah
0x14006962f  mov     bpl, r15b
0x140069632  jmp     loc_14006955D
0x140069637  xor     edx, edx; Val
0x140069639  mov     r8d, 0D8h; Size
0x14006963f  mov     rcx, rsi; void *
0x140069642  call    memset
0x140069647  mov     edx, 110h
0x14006964c  mov     r8d, 73524E4Bh
0x140069652  lea     ecx, [rdx-10h]
0x140069655  call    cs:__imp_ExAllocatePool2
0x14006965c  nop     dword ptr [rax+rax+00h]
0x140069661  mov     [rsi+0B8h], rax
0x140069668  test    rax, rax
0x14006966b  jz      short loc_14006962A
0x14006966d  mov     rcx, rsi; Resource
0x140069670  call    cs:__imp_ExInitializeResourceLite
0x140069677  nop     dword ptr [rax+rax+00h]
0x14006967c  mov     ebx, eax
0x14006967e  test    eax, eax
0x140069680  js      short loc_14006962F
0x140069682  or      dword ptr [rsi+0A4h], 20h
0x140069689  call    AfdPodGetCurrent
0x14006968e  mov     rcx, rax
0x140069691  mov     [rsi+0C0h], rax
0x140069698  call    cs:__imp_PsReferenceSiloContext
0x14006969f  nop     dword ptr [rax+rax+00h]
0x1400696a4  mov     eax, [rsi+0A4h]
0x1400696aa  mov     [rsi+70h], r13
0x1400696ae  and     eax, 0FFFFFFFBh
0x1400696b1  mov     [rsi+78h], r14
0x1400696b5  movzx   ecx, r15b
0x1400696b9  shl     ecx, 2
0x1400696bc  or      ecx, eax
0x1400696be  and     ecx, 0FFFFFFFEh
0x1400696c1  or      ecx, 2
0x1400696c4  mov     [rsi+0A4h], ecx
0x1400696ca  mov     rcx, [rsi+0B8h]
0x1400696d1  mov     rax, [rdi+28h]
0x1400696d5  mov     [rcx], rax
0x1400696d8  mov     rcx, [rsi+0B8h]
0x1400696df  mov     rax, [rdi+30h]
0x1400696e3  mov     [rcx+8], rax
0x1400696e7  mov     rax, [rsi+0B8h]
0x1400696ee  mov     [rax+10h], ebp
0x1400696f1  mov     rcx, [rsi+0B8h]
0x1400696f8  mov     rax, [rdi+10h]
0x1400696fc  mov     [rcx+0A0h], rax
0x140069703  mov     rcx, [rsi+0B8h]
0x14006970a  mov     rax, [rdi+18h]
0x14006970e  mov     [rcx+0A8h], rax
0x140069715  mov     rcx, [rsi+0B8h]
0x14006971c  mov     eax, [rdi+20h]
0x14006971f  mov     [rcx+0B0h], eax
0x140069725  mov     rcx, [rsi+0B8h]
0x14006972c  mov     r8d, [rdi+8]; Size
0x140069730  add     rcx, 18h; void *
0x140069734  mov     rdx, [rdi]; Src
0x140069737  call    memmove
0x14006973c  mov     rcx, [rsi+0B8h]
0x140069743  mov     edx, 58h ; 'X'; Size
0x140069748  mov     eax, [rdi+8]
0x14006974b  mov     [rcx+98h], eax
0x140069751  mov     [r12+18h], rsi
0x140069756  mov     rbx, [rsi+0B8h]
0x14006975d  lea     rcx, [rbx+0B8h]; pAsync
0x140069764  call    cs:__imp_RpcAsyncInitializeHandle
0x14006976b  nop     dword ptr [rax+rax+00h]
0x140069770  lea     rax, WskKnrRpcComplete
0x140069777  mov     dword ptr [rbx+0E4h], 2
0x140069781  mov     rcx, rsi
0x140069784  mov     [rbx+0E8h], rax
0x14006978b  mov     [rbx+0D0h], rsi
0x140069792  call    WskKnrRpcInvoke
0x140069797  mov     eax, 103h
0x14006979c  jmp     loc_14006983E
0x1400697a1  mov     r12b, bl
0x1400697a4  mov     ebx, 0C0000008h
0x1400697a9  jmp     short loc_1400697AE
0x1400697ab  mov     r12b, r15b
0x1400697ae  test    byte ptr cs:xmmword_1400875D0+3, 1
0x1400697b5  jz      short loc_1400697D0
0x1400697b7  mov     edx, 25h ; '%'
0x1400697bc  lea     r8, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids
0x1400697c3  mov     ecx, 218h
0x1400697c8  mov     r9, r14
0x1400697cb  call    WPP_SF_q
0x1400697d0  test    rsi, rsi
0x1400697d3  jz      short loc_1400697DD
0x1400697d5  mov     rcx, rsi; Resource
0x1400697d8  call    WskKnrFreeRequest
0x1400697dd  test    bpl, bpl
0x1400697e0  jz      short loc_1400697FD
0x1400697e2  mov     rcx, [rdi+28h]; Process
0x1400697e6  mov     edx, 200h; PoolType
0x1400697eb  mov     r8d, 0D8h; Amount
0x1400697f1  call    cs:__imp_PsReturnPoolQuota
0x1400697f8  nop     dword ptr [rax+rax+00h]
0x1400697fd  test    r15b, r15b
0x140069800  jz      short loc_140069812
0x140069802  mov     rcx, [rdi+28h]; Object
0x140069806  call    cs:__imp_ObfDereferenceObject
0x14006980d  nop     dword ptr [rax+rax+00h]
0x140069812  test    r12b, r12b
0x140069815  jz      short loc_14006981F
0x140069817  mov     rcx, r13
0x14006981a  call    AfdWskDereferenceClient
0x14006981f  xor     edx, edx; PriorityBoost
0x140069821  mov     [r14+30h], ebx
0x140069825  mov     rcx, r14; Irp
0x140069828  mov     qword ptr [r14+38h], 0
0x140069830  call    cs:__imp_IofCompleteRequest
0x140069837  nop     dword ptr [rax+rax+00h]
0x14006983c  mov     eax, ebx
0x14006983e  add     rsp, 28h
0x140069842  pop     r15
0x140069844  pop     r14
0x140069846  pop     r13
0x140069848  pop     r12
0x14006984a  pop     rdi
0x14006984b  pop     rsi
0x14006984c  pop     rbp
0x14006984d  pop     rbx
0x14006984e  retn
```
