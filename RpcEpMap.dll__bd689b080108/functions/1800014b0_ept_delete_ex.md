# ept_delete_ex

- ea: `0x1800014b0`
- end: `0x180001804`
- name: `ept_delete_ex`
- size: `852`
- prototype: `RPC_STATUS *__fastcall(__int64, LPVOID *, unsigned int, __int64, int, RPC_STATUS *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800014b0`
- `0x18000180c`
- `0x180002714`
- `0x180002798`
- `0x18000359c`
- `0x180005b24`
- `0x18000a8b4`

## import_xrefs

- `RPCRT4!TowerExplode` at `0x180001671`
- `RPCRT4!TowerExplode` at `0x180001671`
- `RPCRT4!RpcRaiseException` at `0x1800017fd`
- `RPCRT4!RpcRaiseException` at `0x1800017fd`
- `RPCRT4!I_RpcFree` at `0x18000174b`
- `RPCRT4!I_RpcFree` at `0x18000175b`
- `RPCRT4!I_RpcFree` at `0x18000174b`
- `RPCRT4!I_RpcFree` at `0x18000175b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000154e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000154e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800016b7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800016b7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800016ee`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800016ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800014ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800014ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000177b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800017b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000177b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800017b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800014e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800014e0`

## pseudocode

```c
RPC_STATUS *__fastcall ept_delete_ex(__int64 a1, LPVOID *a2, unsigned int a3, __int64 a4, int a5, RPC_STATUS *a6)
{
  __int64 v7; // r15
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  int v11; // r12d
  char *v12; // rbx
  __int64 v13; // r14
  unsigned __int16 i; // bp
  unsigned __int16 v15; // si
  __int64 v16; // rbp
  _DWORD *v17; // r10
  LPVOID v18; // rcx
  int v19; // eax
  __int64 v20; // rdx
  int v21; // eax
  int v22; // edx
  unsigned __int16 v23; // si
  __int64 v24; // rbp
  char *v25; // rcx
  int v26; // r14d
  unsigned __int16 v27; // bp
  RPC_STATUS v28; // esi
  void *v29; // rcx
  void *v30; // rcx
  RPC_STATUS *result; // rax
  RPC_STATUS v32; // [rsp+50h] [rbp-58h]
  __int64 v33; // [rsp+58h] [rbp-50h] BYREF
  ULONGLONG TickCount64; // [rsp+60h] [rbp-48h]
  int v35; // [rsp+C0h] [rbp+18h]

  v7 = a3;
  *a6 = 1753;
  TickCount64 = GetTickCount64();
  v9 = HeapAlloc(hEpMapperHeap, 0, 80 * v7);
  v10 = v9;
  if ( v9 )
  {
    v11 = 0;
    v32 = 0;
    v35 = 0;
    v12 = 0;
    memset_0(v9, 0, 80 * v7);
    v13 = a4;
    for ( i = 0; i < (unsigned int)v7; ++i )
    {
      v12 = (char *)&v10[10 * i];
      v21 = TowerExplode(*(_QWORD *)(v13 + 16), v12 + 32, v12 + 52, v12 + 16, v12 + 24, 0);
      v35 = v21;
      v11 = v21;
      if ( v21 == 14 )
        goto LABEL_30;
      if ( !v21 )
      {
        v22 = *((unsigned __int16 *)v12 + 25) | (*((unsigned __int16 *)v12 + 24) << 16);
        *(_DWORD *)v12 = 1;
        *((_DWORD *)v12 + 18) = v22;
      }
      v13 += 88;
    }
    RtlAcquireSRWLockExclusive(&EpMapRWLock);
    v15 = 0;
    v16 = a4;
    while ( v15 < (unsigned int)v7 )
    {
      if ( *(_DWORD *)v12 )
      {
        v17 = *a2;
        if ( !*a2 || *v17 != -557122643 || !v17[1] )
        {
          v11 = 1752;
          v26 = 1;
          RPC_SRWLOCK::Clear(1, 1);
          goto LABEL_31;
        }
        v18 = *a2;
        v33 = 0;
        v12 = (char *)&v10[10 * v15];
        v19 = ept_delete_ex_helper(
                v18,
                v16,
                v12 + 32,
                *((unsigned int *)v12 + 18),
                *((_QWORD *)v12 + 2),
                *((_QWORD *)v12 + 3),
                a5,
                TickCount64,
                &v33);
        v35 = v19;
        v11 = v19;
        if ( v19 )
        {
          v32 = v19;
        }
        else if ( v33 )
        {
          UnLinkFromIFOBJList(*a2, v33);
          *((_QWORD *)v12 + 1) = v20;
        }
        if ( !*((_DWORD *)*a2 + 1) )
        {
          HeapFree(hEpMapperHeap, 0, *a2);
          *a2 = 0;
        }
      }
      v16 += 88;
      ++v15;
    }
    RtlReleaseSRWLockExclusive(&EpMapRWLock);
    v23 = 0;
    if ( (_DWORD)v7 )
    {
      do
      {
        if ( LODWORD(v10[10 * v23]) )
        {
          v24 = v10[10 * v23 + 1];
          if ( v24 )
          {
            if ( *(_QWORD *)(v24 + 136) )
              RtlUnsubscribeWnfNotificationWaitForCompletion();
            CleanupIFOBJNode(v24);
          }
          v25 = (char *)v10[10 * v23 + 2];
          if ( v25 )
            UpdateEpMapperPortsIfNecessary(v25);
        }
        ++v23;
      }
      while ( v23 < (unsigned int)v7 );
      v11 = v35;
    }
LABEL_30:
    v26 = 0;
LABEL_31:
    v27 = 0;
    v28 = v11;
    if ( (_DWORD)v7 )
    {
      do
      {
        if ( LODWORD(v10[10 * v27]) )
        {
          v29 = (void *)v10[10 * v27 + 2];
          if ( v29 )
            I_RpcFree(v29);
          v30 = (void *)v10[10 * v27 + 3];
          if ( v30 )
            I_RpcFree(v30);
        }
        ++v27;
      }
      while ( v27 < (unsigned int)v7 );
      v28 = v11;
    }
    HeapFree(hEpMapperHeap, 0, v10);
    if ( v26 )
      RpcRaiseException(v28);
    if ( !v28 )
    {
      result = a6;
      *a6 = v32;
      return result;
    }
  }
  else
  {
    v28 = 14;
  }
  result = a6;
  *a6 = v28;
  return result;
}

```

## disassembly

```asm
0x1800014b0  mov     [rsp+arg_0], rbx
0x1800014b5  mov     [rsp+arg_18], r9
0x1800014ba  push    rbp
0x1800014bb  push    rsi
0x1800014bc  push    rdi
0x1800014bd  push    r12
0x1800014bf  push    r13
0x1800014c1  push    r14
0x1800014c3  push    r15
0x1800014c5  sub     rsp, 70h
0x1800014c9  mov     rax, [rsp+0A8h+arg_28]
0x1800014d1  mov     rbp, r9
0x1800014d4  mov     r15d, r8d
0x1800014d7  mov     r13, rdx
0x1800014da  mov     dword ptr [rax], 6D9h
0x1800014e0  call    cs:__imp_GetTickCount64
0x1800014e6  mov     rcx, cs:hEpMapperHeap; hHeap
0x1800014ed  lea     rsi, [r15+r15*4]
0x1800014f1  shl     rsi, 4
0x1800014f5  xor     edx, edx; dwFlags
0x1800014f7  mov     r8, rsi; dwBytes
0x1800014fa  mov     [rsp+0A8h+var_48], rax
0x1800014ff  call    cs:__imp_HeapAlloc
0x180001505  mov     rdi, rax
0x180001508  test    rax, rax
0x18000150b  jz      loc_1800017E1
0x180001511  xor     r12d, r12d
0x180001514  mov     [rsp+0A8h+var_58], 0
0x18000151c  mov     r8, rsi; Size
0x18000151f  mov     [rsp+0A8h+arg_10], r12d
0x180001527  xor     edx, edx; Val
0x180001529  mov     rcx, rax; void *
0x18000152c  xor     ebx, ebx
0x18000152e  call    memset_0
0x180001533  mov     r14, rbp
0x180001536  lea     esi, [rbx+0Eh]
0x180001539  xor     ebp, ebp
0x18000153b  movzx   eax, bp
0x18000153e  cmp     eax, r15d
0x180001541  jb      loc_180001641
0x180001547  lea     rcx, ?EpMapRWLock@@3VRPC_SRWLOCK@@A; RPC_SRWLOCK EpMapRWLock
0x18000154e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180001554  mov     r14d, [rsp+0A8h+arg_20]
0x18000155c  xor     esi, esi
0x18000155e  mov     rbp, [rsp+0A8h+arg_18]
0x180001566  lea     ecx, [rsi+1]
0x180001569  movzx   eax, si
0x18000156c  cmp     eax, r15d
0x18000156f  jnb     loc_1800016B0
0x180001575  cmp     dword ptr [rbx], 0
0x180001578  jz      loc_180001635
0x18000157e  mov     r10, [r13+0]
0x180001582  test    r10, r10
0x180001585  jz      loc_1800017CC
0x18000158b  cmp     dword ptr [r10], 0DECAFBADh
0x180001592  jnz     loc_1800017CC
0x180001598  cmp     dword ptr [r10+4], 0
0x18000159d  jz      loc_1800017CC
0x1800015a3  movzx   eax, si
0x1800015a6  mov     rdx, rbp
0x1800015a9  mov     rcx, r10
0x1800015ac  mov     [rsp+0A8h+var_50], 0
0x1800015b5  lea     rbx, [rax+rax*4]
0x1800015b9  lea     rax, [rsp+0A8h+var_50]
0x1800015be  shl     rbx, 4
0x1800015c2  mov     [rsp+0A8h+var_68], rax
0x1800015c7  add     rbx, rdi
0x1800015ca  mov     rax, [rsp+0A8h+var_48]
0x1800015cf  mov     [rsp+0A8h+var_70], rax
0x1800015d4  mov     [rsp+0A8h+var_78], r14d
0x1800015d9  mov     rax, [rbx+18h]
0x1800015dd  lea     r8, [rbx+20h]
0x1800015e1  mov     r9d, [rbx+48h]
0x1800015e5  mov     [rsp+0A8h+var_80], rax
0x1800015ea  mov     rax, [rbx+10h]
0x1800015ee  mov     [rsp+0A8h+var_88], rax
0x1800015f3  call    ept_delete_ex_helper
0x1800015f8  mov     [rsp+0A8h+arg_10], eax
0x1800015ff  mov     r12d, eax
0x180001602  test    eax, eax
0x180001604  jnz     loc_1800017F2
0x18000160a  mov     rdx, [rsp+0A8h+var_50]
0x18000160f  test    rdx, rdx
0x180001612  jz      short loc_180001621
0x180001614  mov     rcx, [r13+0]
0x180001618  call    UnLinkFromIFOBJList
0x18000161d  mov     [rbx+8], rdx
0x180001621  mov     r8, [r13+0]; lpMem
0x180001625  cmp     dword ptr [r8+4], 0
0x18000162a  jz      loc_1800017B0
0x180001630  mov     ecx, 1
0x180001635  add     rbp, 58h ; 'X'
0x180001639  add     si, cx
0x18000163c  jmp     loc_180001569
0x180001641  mov     rcx, [r14+10h]
0x180001645  movzx   eax, bp
0x180001648  mov     [rsp+0A8h+var_80], 0
0x180001651  lea     rbx, [rax+rax*4]
0x180001655  shl     rbx, 4
0x180001659  add     rbx, rdi
0x18000165c  lea     rax, [rbx+18h]
0x180001660  lea     r9, [rbx+10h]
0x180001664  mov     [rsp+0A8h+var_88], rax
0x180001669  lea     r8, [rbx+34h]
0x18000166d  lea     rdx, [rbx+20h]
0x180001671  call    cs:__imp_TowerExplode
0x180001677  mov     [rsp+0A8h+arg_10], eax
0x18000167e  mov     r12d, eax
0x180001681  cmp     eax, esi
0x180001683  jz      loc_180001721
0x180001689  test    eax, eax
0x18000168b  mov     eax, 1
0x180001690  jnz     short loc_1800016A4
0x180001692  movzx   edx, word ptr [rbx+30h]
0x180001696  movzx   ecx, word ptr [rbx+32h]
0x18000169a  shl     edx, 10h
0x18000169d  or      edx, ecx
0x18000169f  mov     [rbx], eax
0x1800016a1  mov     [rbx+48h], edx
0x1800016a4  add     r14, 58h ; 'X'
0x1800016a8  add     bp, ax
0x1800016ab  jmp     loc_18000153B
0x1800016b0  lea     rcx, ?EpMapRWLock@@3VRPC_SRWLOCK@@A; RPC_SRWLOCK EpMapRWLock
0x1800016b7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800016bd  xor     esi, esi
0x1800016bf  test    r15d, r15d
0x1800016c2  jz      short loc_180001721
0x1800016c4  lea     r12d, [rsi+1]
0x1800016c8  movzx   eax, si
0x1800016cb  lea     rbx, [rax+rax*4]
0x1800016cf  add     rbx, rbx
0x1800016d2  cmp     dword ptr [rdi+rbx*8], 0
0x1800016d6  jz      short loc_18000170D
0x1800016d8  mov     rbp, [rdi+rbx*8+8]
0x1800016dd  test    rbp, rbp
0x1800016e0  jz      short loc_1800016FC
0x1800016e2  mov     rcx, [rbp+88h]
0x1800016e9  test    rcx, rcx
0x1800016ec  jz      short loc_1800016F4
0x1800016ee  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800016f4  mov     rcx, rbp
0x1800016f7  call    CleanupIFOBJNode
0x1800016fc  mov     rcx, [rdi+rbx*8+10h]; String1
0x180001701  test    rcx, rcx
0x180001704  jz      short loc_18000170D
0x180001706  xor     edx, edx
0x180001708  call    UpdateEpMapperPortsIfNecessary
0x18000170d  add     si, r12w
0x180001711  movzx   eax, si
0x180001714  cmp     eax, r15d
0x180001717  jb      short loc_1800016C8
0x180001719  mov     r12d, [rsp+0A8h+arg_10]
0x180001721  xor     r14d, r14d
0x180001724  xor     ebp, ebp
0x180001726  mov     esi, r12d
0x180001729  test    r15d, r15d
0x18000172c  jz      short loc_18000176F
0x18000172e  lea     esi, [rbp+1]
0x180001731  movzx   eax, bp
0x180001734  lea     rbx, [rax+rax*4]
0x180001738  add     rbx, rbx
0x18000173b  cmp     dword ptr [rdi+rbx*8], 0
0x18000173f  jz      short loc_180001761
0x180001741  mov     rcx, [rdi+rbx*8+10h]; Object
0x180001746  test    rcx, rcx
0x180001749  jz      short loc_180001751
0x18000174b  call    cs:__imp_I_RpcFree
0x180001751  mov     rcx, [rdi+rbx*8+18h]; Object
0x180001756  test    rcx, rcx
0x180001759  jz      short loc_180001761
0x18000175b  call    cs:__imp_I_RpcFree
0x180001761  add     bp, si
0x180001764  movzx   eax, bp
0x180001767  cmp     eax, r15d
0x18000176a  jb      short loc_180001731
0x18000176c  mov     esi, r12d
0x18000176f  mov     rcx, cs:hEpMapperHeap; hHeap
0x180001776  mov     r8, rdi; lpMem
0x180001779  xor     edx, edx; dwFlags
0x18000177b  call    cs:__imp_HeapFree
0x180001781  test    r14d, r14d
0x180001784  jnz     short loc_1800017FB
0x180001786  test    esi, esi
0x180001788  jnz     short loc_1800017E6
0x18000178a  mov     rax, [rsp+0A8h+arg_28]
0x180001792  mov     ecx, [rsp+0A8h+var_58]
0x180001796  mov     [rax], ecx
0x180001798  mov     rbx, [rsp+0A8h+arg_0]
0x1800017a0  add     rsp, 70h
0x1800017a4  pop     r15
0x1800017a6  pop     r14
0x1800017a8  pop     r13
0x1800017aa  pop     r12
0x1800017ac  pop     rdi
0x1800017ad  pop     rsi
0x1800017ae  pop     rbp
0x1800017af  retn
0x1800017b0  mov     rcx, cs:hEpMapperHeap; hHeap
0x1800017b7  xor     edx, edx; dwFlags
0x1800017b9  call    cs:__imp_HeapFree
0x1800017bf  mov     qword ptr [r13+0], 0
0x1800017c7  jmp     loc_180001630
0x1800017cc  mov     edx, ecx
0x1800017ce  mov     r12d, 6D8h
0x1800017d4  mov     r14d, ecx
0x1800017d7  call    ?Clear@RPC_SRWLOCK@@QEAAXW4LockMode@1@@Z; RPC_SRWLOCK::Clear(RPC_SRWLOCK::LockMode)
0x1800017dc  jmp     loc_180001724
0x1800017e1  mov     esi, 0Eh
0x1800017e6  mov     rax, [rsp+0A8h+arg_28]
0x1800017ee  mov     [rax], esi
0x1800017f0  jmp     short loc_180001798
0x1800017f2  mov     [rsp+0A8h+var_58], eax
0x1800017f6  jmp     loc_180001621
0x1800017fb  mov     ecx, esi; exception
0x1800017fd  call    cs:__imp_RpcRaiseException
```
