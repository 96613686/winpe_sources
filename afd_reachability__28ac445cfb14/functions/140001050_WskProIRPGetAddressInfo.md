# WskProIRPGetAddressInfo

- ea: `0x140001050`
- end: `0x1400014ea`
- name: `WskProIRPGetAddressInfo`
- size: `1178`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140032d90`

## callees

- `0x140001050`
- `0x140002f44`
- `0x14001087c`
- `0x140029ccc`
- `0x14004028c`
- `0x140048eac`
- `0x14009304c`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1400013bb`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1400013bb`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400014b7`
- `ntoskrnl!PsReturnPoolQuota` at `0x1400014b7`
- `ntoskrnl!PsGetCurrentProcess` at `0x140001128`
- `ntoskrnl!PsGetCurrentProcess` at `0x140001128`
- `ntoskrnl!ExInitializeResourceLite` at `0x140001205`
- `ntoskrnl!ExInitializeResourceLite` at `0x140001205`
- `ntoskrnl!PsReferenceSiloContext` at `0x140001231`
- `ntoskrnl!PsReferenceSiloContext` at `0x140001231`
- `ntoskrnl!ObfReferenceObject` at `0x14000139d`
- `ntoskrnl!ObfReferenceObject` at `0x14000139d`
- `ntoskrnl!IofCompleteRequest` at `0x1400011ae`
- `ntoskrnl!IofCompleteRequest` at `0x1400011ae`
- `ntoskrnl!ObfDereferenceObject` at `0x1400014cc`
- `ntoskrnl!ObfDereferenceObject` at `0x1400014cc`
- `ntoskrnl!ExAllocatePool2` at `0x140001148`
- `ntoskrnl!ExAllocatePool2` at `0x1400011e6`
- `ntoskrnl!ExAllocatePool2` at `0x140001148`
- `ntoskrnl!ExAllocatePool2` at `0x1400011e6`
- `msrpc!RpcAsyncInitializeHandle` at `0x140001303`
- `msrpc!RpcAsyncInitializeHandle` at `0x140001303`

## pseudocode

```c
__int64 __fastcall WskProIRPGetAddressInfo(PIRP Irp, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r13
  __int64 v5; // rsi
  unsigned __int8 v6; // r15
  unsigned __int8 v7; // bp
  __int64 Pool2; // rdi
  __int64 v9; // r12
  signed __int32 v11; // eax
  _OWORD *v12; // rax
  __int64 v13; // rax
  bool v14; // cl
  _QWORD *v15; // rax
  void *v16; // rcx
  int v17; // ebp
  int v18; // ebx
  char v19; // r12
  __int64 v21; // rax
  __int64 Current; // rax
  int v23; // eax
  _OWORD *v24; // rcx
  _DWORD *v25; // rax
  __int64 v26; // rbx

  v4 = *(_QWORD *)(a2 + 8);
  v5 = *(_QWORD *)(a2 + 16);
  v6 = 0;
  v7 = 0;
  Pool2 = 0;
  v9 = a2;
  if ( (BYTE3(xmmword_1400875E0) & 1) != 0 )
    WPP_SF_q(1048, 33, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids, Irp);
  do
  {
    v11 = *(_DWORD *)(v4 + 16);
    if ( (v11 & 1) != 0 )
    {
      v19 = 0;
      v18 = -1073741816;
      goto LABEL_21;
    }
  }
  while ( v11 != _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 16), v11 + 2, v11) );
  v12 = *(_OWORD **)v5;
  LOBYTE(a2) = 0;
  if ( *(_QWORD *)v5 && *((_QWORD *)v12 + 1) )
  {
    if ( *((_WORD *)v12 + 1) >= *(_WORD *)v12 )
    {
      LOBYTE(a2) = *(_WORD *)v12 != 0;
      goto LABEL_9;
    }
    goto LABEL_44;
  }
LABEL_9:
  v13 = *(_QWORD *)(v5 + 8);
  v14 = 0;
  if ( v13 && *(_QWORD *)(v13 + 8) )
  {
    if ( *(_WORD *)(v13 + 2) < *(_WORD *)v13 )
      goto LABEL_44;
    v14 = *(_WORD *)v13 != 0;
  }
  if ( !(_BYTE)a2 && !v14 || (v15 = *(_QWORD **)(v5 + 40)) == 0 )
  {
LABEL_44:
    v18 = -1073741811;
LABEL_20:
    v19 = 1;
    goto LABEL_21;
  }
  *v15 = 0;
  if ( *(_QWORD *)(v5 + 48) )
  {
    if ( WskKnrIsCurrentThreadImpersonated() == 1 )
      goto LABEL_44;
  }
  else if ( *(_QWORD *)(v5 + 56) )
  {
    goto LABEL_44;
  }
  v16 = *(void **)(v5 + 48);
  if ( !v16
    || (ObfReferenceObject(v16),
        v6 = 1,
        v18 = PsChargeProcessPoolQuota(*(PEPROCESS *)(v5 + 48), (POOL_TYPE)512, 0xD8u),
        v18 >= 0) )
  {
    if ( *(_QWORD *)(v5 + 48) )
    {
      v17 = 3;
    }
    else
    {
      v17 = (*(_QWORD *)(v5 + 56) != 0) + 2;
      *(_QWORD *)(v5 + 48) = PsGetCurrentProcess(v16, a2, a3, a4);
    }
    Pool2 = ExAllocatePool2(64, 216, 1934773835);
    if ( Pool2 && (v21 = ExAllocatePool2(256, 272, 1934773835), (*(_QWORD *)(Pool2 + 184) = v21) != 0) )
    {
      v18 = ExInitializeResourceLite((PERESOURCE)Pool2);
      if ( v18 >= 0 )
      {
        *(_DWORD *)(Pool2 + 164) |= 0x20u;
        Current = AfdPodGetCurrent();
        *(_QWORD *)(Pool2 + 192) = Current;
        PsReferenceSiloContext(Current);
        if ( (BYTE3(xmmword_1400875E0) & 1) != 0 )
          WPP_SF_qD(
            1048,
            34,
            WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids,
            Irp,
            *(_DWORD *)(*(_QWORD *)(Pool2 + 192) + 8LL));
        v23 = *(_DWORD *)(Pool2 + 164);
        *(_QWORD *)(Pool2 + 112) = v4;
        *(_QWORD *)(Pool2 + 120) = Irp;
        *(_DWORD *)(Pool2 + 164) = v23 & 0xFFFFFFF9 | (4 * v6) | 1;
        **(_QWORD **)(Pool2 + 184) = *(_QWORD *)(v5 + 48);
        *(_QWORD *)(*(_QWORD *)(Pool2 + 184) + 8LL) = *(_QWORD *)(v5 + 56);
        *(_DWORD *)(*(_QWORD *)(Pool2 + 184) + 16LL) = v17;
        if ( *(_QWORD *)v5 )
          *(_OWORD *)(*(_QWORD *)(Pool2 + 184) + 24LL) = *(_OWORD *)*(_QWORD *)v5;
        v24 = *(_OWORD **)(v5 + 8);
        if ( v24 )
          *(_OWORD *)(*(_QWORD *)(Pool2 + 184) + 40LL) = *v24;
        *(_DWORD *)(*(_QWORD *)(Pool2 + 184) + 56LL) = *(_DWORD *)(v5 + 16);
        *(_QWORD *)(*(_QWORD *)(Pool2 + 184) + 64LL) = *(_QWORD *)(v5 + 24);
        v25 = *(_DWORD **)(v5 + 32);
        if ( v25 )
        {
          *(_DWORD *)(*(_QWORD *)(Pool2 + 184) + 72LL) = *v25;
          *(_DWORD *)(*(_QWORD *)(Pool2 + 184) + 76LL) = *(_DWORD *)(*(_QWORD *)(v5 + 32) + 4LL);
          *(_DWORD *)(*(_QWORD *)(Pool2 + 184) + 80LL) = *(_DWORD *)(*(_QWORD *)(v5 + 32) + 8LL);
          *(_DWORD *)(*(_QWORD *)(Pool2 + 184) + 84LL) = *(_DWORD *)(*(_QWORD *)(v5 + 32) + 12LL);
        }
        *(_QWORD *)(*(_QWORD *)(Pool2 + 184) + 152LL) = *(_QWORD *)(v5 + 40);
        *(_QWORD *)(v9 + 24) = Pool2;
        v26 = *(_QWORD *)(Pool2 + 184);
        RpcAsyncInitializeHandle((PRPC_ASYNC_STATE)(v26 + 184), 0x58u);
        *(_DWORD *)(v26 + 228) = 2;
        *(_QWORD *)(v26 + 232) = WskKnrRpcComplete;
        *(_QWORD *)(v26 + 208) = Pool2;
        WskKnrRpcInvoke(Pool2);
        return 259;
      }
    }
    else
    {
      v18 = -1073741670;
    }
    v7 = v6;
    goto LABEL_20;
  }
  v19 = 1;
LABEL_21:
  if ( (BYTE3(xmmword_1400875D0) & 1) != 0 )
    WPP_SF_q(536, 35, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids, Irp);
  if ( Pool2 )
    WskKnrFreeRequest((PERESOURCE)Pool2);
  if ( v7 )
    PsReturnPoolQuota(*(PEPROCESS *)(v5 + 48), (POOL_TYPE)512, 0xD8u);
  if ( v6 )
    ObfDereferenceObject(*(PVOID *)(v5 + 48));
  if ( v19 )
    AfdWskDereferenceClient(v4);
  Irp->IoStatus.Status = v18;
  Irp->IoStatus.Information = 0;
  IofCompleteRequest(Irp, 0);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x140001050  push    rbx
0x140001052  push    rbp
0x140001053  push    rsi
0x140001054  push    rdi
0x140001055  push    r12
0x140001057  push    r13
0x140001059  push    r14
0x14000105b  push    r15
0x14000105d  sub     rsp, 38h
0x140001061  mov     r13, [rdx+8]
0x140001065  xor     ebx, ebx
0x140001067  mov     rsi, [rdx+10h]
0x14000106b  mov     r15b, bl
0x14000106e  mov     bpl, bl
0x140001071  mov     edi, ebx
0x140001073  mov     r12, rdx
0x140001076  mov     r14, rcx
0x140001079  test    byte ptr cs:xmmword_1400875E0+3, 1
0x140001080  jnz     loc_14000134A
0x140001086  mov     eax, [r13+10h]
0x14000108a  test    al, 1
0x14000108c  jnz     loc_140001470
0x140001092  lea     ecx, [rax+2]
0x140001095  lock cmpxchg [r13+10h], ecx
0x14000109b  jnz     short loc_140001086
0x14000109d  mov     rax, [rsi]
0x1400010a0  mov     dl, bl
0x1400010a2  mov     [rsp+78h+arg_8], 1
0x1400010aa  test    rax, rax
0x1400010ad  jz      short loc_1400010C8
0x1400010af  cmp     [rax+8], rbx
0x1400010b3  jz      short loc_1400010C8
0x1400010b5  movzx   ecx, word ptr [rax]
0x1400010b8  cmp     [rax+2], cx
0x1400010bc  jb      loc_140001340
0x1400010c2  test    cx, cx
0x1400010c5  setnz   dl
0x1400010c8  mov     rax, [rsi+8]
0x1400010cc  mov     cl, bl
0x1400010ce  test    rax, rax
0x1400010d1  jnz     loc_140001368
0x1400010d7  test    dl, dl
0x1400010d9  jz      loc_140001386
0x1400010df  mov     rax, [rsi+28h]
0x1400010e3  test    rax, rax
0x1400010e6  jz      loc_140001340
0x1400010ec  mov     [rax], rbx
0x1400010ef  cmp     [rsi+30h], rbx
0x1400010f3  jnz     loc_14000138F
0x1400010f9  cmp     [rsi+38h], rbx
0x1400010fd  jnz     loc_140001340
0x140001103  mov     rcx, [rsi+30h]; Object
0x140001107  test    rcx, rcx
0x14000110a  jnz     loc_14000139D
0x140001110  cmp     [rsi+30h], rbx
0x140001114  jnz     loc_1400011CE
0x14000111a  mov     rax, [rsi+38h]
0x14000111e  neg     rax
0x140001121  sbb     ebp, ebp
0x140001123  neg     ebp
0x140001125  add     ebp, 2
0x140001128  call    cs:__imp_PsGetCurrentProcess
0x14000112f  nop     dword ptr [rax+rax+00h]
0x140001134  mov     [rsi+30h], rax
0x140001138  mov     edx, 0D8h
0x14000113d  mov     ecx, 40h ; '@'
0x140001142  mov     r8d, 73524E4Bh
0x140001148  call    cs:__imp_ExAllocatePool2
0x14000114f  nop     dword ptr [rax+rax+00h]
0x140001154  mov     rdi, rax
0x140001157  test    rax, rax
0x14000115a  jnz     short loc_1400011D8
0x14000115c  mov     ebx, 0C000009Ah
0x140001161  mov     bpl, r15b
0x140001164  mov     r12b, [rsp+78h+arg_8]
0x14000116c  test    byte ptr cs:xmmword_1400875D0+3, 1
0x140001173  jnz     loc_14000147D
0x140001179  test    rdi, rdi
0x14000117c  jnz     loc_14000149B
0x140001182  test    bpl, bpl
0x140001185  jnz     loc_1400014A8
0x14000118b  test    r15b, r15b
0x14000118e  jnz     loc_1400014C8
0x140001194  test    r12b, r12b
0x140001197  jnz     loc_1400014DD
0x14000119d  xor     edx, edx; PriorityBoost
0x14000119f  mov     [r14+30h], ebx
0x1400011a3  mov     rcx, r14; Irp
0x1400011a6  mov     qword ptr [r14+38h], 0
0x1400011ae  call    cs:__imp_IofCompleteRequest
0x1400011b5  nop     dword ptr [rax+rax+00h]
0x1400011ba  mov     eax, ebx
0x1400011bc  add     rsp, 38h
0x1400011c0  pop     r15
0x1400011c2  pop     r14
0x1400011c4  pop     r13
0x1400011c6  pop     r12
0x1400011c8  pop     rdi
0x1400011c9  pop     rsi
0x1400011ca  pop     rbp
0x1400011cb  pop     rbx
0x1400011cc  retn
0x1400011ce  mov     ebp, 3
0x1400011d3  jmp     loc_140001138
0x1400011d8  mov     edx, 110h
0x1400011dd  mov     r8d, 73524E4Bh
0x1400011e3  lea     ecx, [rdx-10h]
0x1400011e6  call    cs:__imp_ExAllocatePool2
0x1400011ed  nop     dword ptr [rax+rax+00h]
0x1400011f2  mov     [rdi+0B8h], rax
0x1400011f9  test    rax, rax
0x1400011fc  jz      loc_14000115C
0x140001202  mov     rcx, rdi; Resource
0x140001205  call    cs:__imp_ExInitializeResourceLite
0x14000120c  nop     dword ptr [rax+rax+00h]
0x140001211  mov     ebx, eax
0x140001213  test    eax, eax
0x140001215  js      loc_140001161
0x14000121b  or      dword ptr [rdi+0A4h], 20h
0x140001222  call    AfdPodGetCurrent
0x140001227  mov     rcx, rax
0x14000122a  mov     [rdi+0C0h], rax
0x140001231  call    cs:__imp_PsReferenceSiloContext
0x140001238  nop     dword ptr [rax+rax+00h]
0x14000123d  test    byte ptr cs:xmmword_1400875E0+3, 1
0x140001244  jnz     loc_1400013D8
0x14000124a  mov     eax, [rdi+0A4h]
0x140001250  mov     [rdi+70h], r13
0x140001254  and     eax, 0FFFFFFFBh
0x140001257  mov     [rdi+78h], r14
0x14000125b  movzx   ecx, r15b
0x14000125f  shl     ecx, 2
0x140001262  or      ecx, eax
0x140001264  and     ecx, 0FFFFFFFDh
0x140001267  or      ecx, 1
0x14000126a  mov     [rdi+0A4h], ecx
0x140001270  mov     rcx, [rdi+0B8h]
0x140001277  mov     rax, [rsi+30h]
0x14000127b  mov     [rcx], rax
0x14000127e  mov     rcx, [rdi+0B8h]
0x140001285  mov     rax, [rsi+38h]
0x140001289  mov     [rcx+8], rax
0x14000128d  mov     rax, [rdi+0B8h]
0x140001294  mov     [rax+10h], ebp
0x140001297  mov     rcx, [rsi]
0x14000129a  test    rcx, rcx
0x14000129d  jnz     loc_140001404
0x1400012a3  mov     rcx, [rsi+8]
0x1400012a7  test    rcx, rcx
0x1400012aa  jnz     loc_140001418
0x1400012b0  mov     rcx, [rdi+0B8h]
0x1400012b7  mov     eax, [rsi+10h]
0x1400012ba  mov     [rcx+38h], eax
0x1400012bd  mov     rax, [rsi+18h]
0x1400012c1  mov     rcx, [rdi+0B8h]
0x1400012c8  mov     [rcx+40h], rax
0x1400012cc  mov     rax, [rsi+20h]
0x1400012d0  test    rax, rax
0x1400012d3  jnz     loc_14000142C
0x1400012d9  mov     rcx, [rdi+0B8h]
0x1400012e0  mov     edx, 58h ; 'X'; Size
0x1400012e5  mov     rax, [rsi+28h]
0x1400012e9  mov     [rcx+98h], rax
0x1400012f0  mov     [r12+18h], rdi
0x1400012f5  mov     rbx, [rdi+0B8h]
0x1400012fc  lea     rcx, [rbx+0B8h]; pAsync
0x140001303  call    cs:__imp_RpcAsyncInitializeHandle
0x14000130a  nop     dword ptr [rax+rax+00h]
0x14000130f  lea     rax, WskKnrRpcComplete
0x140001316  mov     dword ptr [rbx+0E4h], 2
0x140001320  mov     rcx, rdi
0x140001323  mov     [rbx+0E8h], rax
0x14000132a  mov     [rbx+0D0h], rdi
0x140001331  call    WskKnrRpcInvoke
0x140001336  mov     eax, 103h
0x14000133b  jmp     loc_1400011BC
0x140001340  mov     ebx, 0C000000Dh
0x140001345  jmp     loc_140001164
0x14000134a  mov     edx, 21h ; '!'
0x14000134f  lea     r8, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids
0x140001356  mov     ecx, 418h
0x14000135b  mov     r9, r14
0x14000135e  call    WPP_SF_q
0x140001363  jmp     loc_140001086
0x140001368  cmp     [rax+8], rbx
0x14000136c  jz      loc_1400010D7
0x140001372  movzx   ecx, word ptr [rax]
0x140001375  cmp     [rax+2], cx
0x140001379  jb      short loc_140001340
0x14000137b  test    cx, cx
0x14000137e  setnz   cl
0x140001381  jmp     loc_1400010D7
0x140001386  test    cl, cl
0x140001388  jz      short loc_140001340
0x14000138a  jmp     loc_1400010DF
0x14000138f  call    WskKnrIsCurrentThreadImpersonated
0x140001394  cmp     al, 1
0x140001396  jz      short loc_140001340
0x140001398  jmp     loc_140001103
0x14000139d  call    cs:__imp_ObfReferenceObject
0x1400013a4  nop     dword ptr [rax+rax+00h]
0x1400013a9  mov     rcx, [rsi+30h]; Process
0x1400013ad  mov     edx, 200h; PoolType
0x1400013b2  mov     r8d, 0D8h; Amount
0x1400013b8  mov     r15b, 1
0x1400013bb  call    cs:__imp_PsChargeProcessPoolQuota
0x1400013c2  nop     dword ptr [rax+rax+00h]
0x1400013c7  mov     ebx, eax
0x1400013c9  test    eax, eax
0x1400013cb  js      loc_140074774
0x1400013d1  xor     ebx, ebx
0x1400013d3  jmp     loc_140001110
0x1400013d8  mov     rax, [rdi+0C0h]
0x1400013df  lea     r8, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids
0x1400013e6  mov     edx, 22h ; '"'
0x1400013eb  mov     ecx, 418h
0x1400013f0  mov     r9, r14
0x1400013f3  mov     eax, [rax+8]
0x1400013f6  mov     [rsp+78h+var_58], eax
0x1400013fa  call    WPP_SF_qD
0x1400013ff  jmp     loc_14000124A
0x140001404  mov     rax, [rdi+0B8h]
0x14000140b  movups  xmm0, xmmword ptr [rcx]
0x14000140e  movdqu  xmmword ptr [rax+18h], xmm0
0x140001413  jmp     loc_1400012A3
0x140001418  mov     rax, [rdi+0B8h]
0x14000141f  movups  xmm0, xmmword ptr [rcx]
0x140001422  movdqu  xmmword ptr [rax+28h], xmm0
0x140001427  jmp     loc_1400012B0
0x14000142c  mov     eax, [rax]
0x14000142e  mov     rcx, [rdi+0B8h]
0x140001435  mov     [rcx+48h], eax
0x140001438  mov     rax, [rsi+20h]
0x14000143c  mov     rcx, [rdi+0B8h]
0x140001443  mov     eax, [rax+4]
0x140001446  mov     [rcx+4Ch], eax
0x140001449  mov     rax, [rsi+20h]
0x14000144d  mov     rcx, [rdi+0B8h]
0x140001454  mov     eax, [rax+8]
0x140001457  mov     [rcx+50h], eax
0x14000145a  mov     rax, [rsi+20h]
0x14000145e  mov     rcx, [rdi+0B8h]
0x140001465  mov     eax, [rax+0Ch]
0x140001468  mov     [rcx+54h], eax
0x14000146b  jmp     loc_1400012D9
0x140001470  mov     r12b, bl
0x140001473  mov     ebx, 0C0000008h
0x140001478  jmp     loc_14000116C
0x14000147d  mov     edx, 23h ; '#'
0x140001482  lea     r8, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids
0x140001489  mov     ecx, 218h
0x14000148e  mov     r9, r14
0x140001491  call    WPP_SF_q
0x140001496  jmp     loc_140001179
0x14000149b  mov     rcx, rdi; Resource
0x14000149e  call    WskKnrFreeRequest
0x1400014a3  jmp     loc_140001182
0x1400014a8  mov     rcx, [rsi+30h]; Process
0x1400014ac  mov     edx, 200h; PoolType
0x1400014b1  mov     r8d, 0D8h; Amount
0x1400014b7  call    cs:__imp_PsReturnPoolQuota
0x1400014be  nop     dword ptr [rax+rax+00h]
0x1400014c3  jmp     loc_14000118B
0x1400014c8  mov     rcx, [rsi+30h]; Object
0x1400014cc  call    cs:__imp_ObfDereferenceObject
0x1400014d3  nop     dword ptr [rax+rax+00h]
0x1400014d8  jmp     loc_140001194
0x1400014dd  mov     rcx, r13
0x1400014e0  call    AfdWskDereferenceClient
0x1400014e5  jmp     loc_14000119D
0x140074774  mov     r12b, r15b
0x140074777  jmp     loc_14000116C
```
