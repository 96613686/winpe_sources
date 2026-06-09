# GetCachedBindingToMachineDC

- ea: `0x18000ef64`
- end: `0x18000f1a1`
- name: `GetCachedBindingToMachineDC`
- size: `573`
- prototype: `__int64 __fastcall(int, int, int, RPC_BINDING_HANDLE *, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ecb0`

## callees

- `0x18000ef64`
- `0x18000f640`
- `0x1800100d0`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000effa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f188`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000effa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f188`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000efbe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f126`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000efbe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f126`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f04e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f0d1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f04e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f0d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f088`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f11d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f17d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f088`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f11d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f17d`
- `RPCRT4!RpcBindingFree` at `0x18000f06d`
- `RPCRT4!RpcBindingFree` at `0x18000f0f7`
- `RPCRT4!RpcBindingFree` at `0x18000f14e`
- `RPCRT4!RpcBindingFree` at `0x18000f162`
- `RPCRT4!RpcBindingFree` at `0x18000f06d`
- `RPCRT4!RpcBindingFree` at `0x18000f0f7`
- `RPCRT4!RpcBindingFree` at `0x18000f14e`
- `RPCRT4!RpcBindingFree` at `0x18000f162`

## string_xrefs

- `0x18000f02e`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyrpccommon.cxx`

## pseudocode

```c
__int64 __fastcall GetCachedBindingToMachineDC(int a1, int a2, int a3, RPC_BINDING_HANDLE *a4, _DWORD *a5)
{
  RPC_BINDING_HANDLE *v6; // rdi
  int v10; // esi
  signed int v11; // eax
  unsigned int v12; // r9d
  int v13; // ebx
  RPC_BINDING_HANDLE v14; // r15
  int v15; // r12d
  unsigned __int64 CurrentTimeInULL; // r13
  RPC_BINDING_HANDLE v17; // rbx
  int v18; // r15d
  unsigned __int64 v19; // r12
  int v20; // ebx
  int v22; // [rsp+30h] [rbp-28h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp-20h] BYREF
  RPC_BINDING_HANDLE v24[3]; // [rsp+40h] [rbp-18h] BYREF
  int v26; // [rsp+A8h] [rbp+50h] BYREF
  int v27; // [rsp+B0h] [rbp+58h]
  RPC_BINDING_HANDLE *v28; // [rsp+B8h] [rbp+60h]

  v28 = a4;
  v27 = a3;
  Binding = 0;
  v24[0] = 0;
  v6 = &g_MachineFullDcRpcCache;
  v26 = 0;
  if ( !a2 )
    v6 = &g_MachineDefaultDcRpcCache;
  v22 = 0;
  AcquireSRWLockShared((PSRWLOCK)v6 + 2);
  if ( a3 | (GetCurrentTimeInULL() - (unsigned __int64)v6[1] > 0xC92A69C000LL) || !*v6 )
  {
    ReleaseSRWLockShared((PSRWLOCK)v6 + 2);
    v11 = KdsCreateClientBinding(0, a1, a2, a3, &Binding, &v26);
    v10 = v11;
    if ( v11 < 0 )
    {
      v12 = 790;
LABEL_8:
      v13 = 0;
      SidKeyDebugTraceError(v11, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyrpccommon.cxx", v12);
      goto LABEL_19;
    }
    AcquireSRWLockExclusive((PSRWLOCK)v6 + 2);
    v14 = Binding;
    v15 = v26;
    CurrentTimeInULL = GetCurrentTimeInULL();
    if ( *v6 )
      RpcBindingFree(v6);
    v6[1] = (RPC_BINDING_HANDLE)CurrentTimeInULL;
    *v6 = v14;
    Binding = 0;
    *((_DWORD *)v6 + 6) = v15;
    ReleaseSRWLockExclusive((PSRWLOCK)v6 + 2);
    if ( a2 )
    {
      v11 = KdsCreateClientBinding(0, a1, a2, v27, v24, &v22);
      v10 = v11;
      if ( v11 < 0 )
      {
        v12 = 821;
        goto LABEL_8;
      }
      AcquireSRWLockExclusive(&stru_180023508);
      v17 = v24[0];
      v18 = v22;
      v19 = GetCurrentTimeInULL();
      if ( g_MachineDefaultDcRpcCache )
        RpcBindingFree(&g_MachineDefaultDcRpcCache);
      g_MachineDefaultDcRpcCache = v17;
      qword_180023500 = v19;
      dword_180023510 = v18;
      v24[0] = 0;
      ReleaseSRWLockExclusive(&stru_180023508);
    }
    AcquireSRWLockShared((PSRWLOCK)v6 + 2);
    *v28 = *v6;
    goto LABEL_18;
  }
  v10 = 0;
  *a4 = *v6;
LABEL_18:
  v13 = 1;
  *a5 = *((_DWORD *)v6 + 6);
LABEL_19:
  if ( Binding )
  {
    RpcBindingFree(&Binding);
    Binding = 0;
  }
  if ( v24[0] )
  {
    RpcBindingFree(v24);
    Binding = 0;
  }
  if ( v10 < 0 )
  {
    v20 = v13 - 1;
    if ( v20 )
    {
      if ( v20 == 1 )
        ReleaseSRWLockExclusive((PSRWLOCK)v6 + 2);
    }
    else
    {
      ReleaseSRWLockShared((PSRWLOCK)v6 + 2);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000ef64  mov     [rsp-40h+arg_18], r9
0x18000ef69  mov     [rsp-40h+arg_10], r8d
0x18000ef6e  mov     [rsp-40h+arg_0], ecx
0x18000ef72  push    rbp
0x18000ef73  push    rbx
0x18000ef74  push    rsi
0x18000ef75  push    rdi
0x18000ef76  push    r12
0x18000ef78  push    r13
0x18000ef7a  push    r14
0x18000ef7c  push    r15
0x18000ef7e  mov     rbp, rsp
0x18000ef81  sub     rsp, 58h
0x18000ef85  xor     r13d, r13d
0x18000ef88  lea     rax, ?g_MachineDefaultDcRpcCache@@3U_RPC_TO_MACHINEDOMAIN_CACHE_ITEM@@A; _RPC_TO_MACHINEDOMAIN_CACHE_ITEM g_MachineDefaultDcRpcCache
0x18000ef8f  test    edx, edx
0x18000ef91  mov     [rbp+Binding], r13
0x18000ef95  mov     r12d, ecx
0x18000ef98  mov     [rbp+var_18], r13
0x18000ef9c  lea     rdi, ?g_MachineFullDcRpcCache@@3U_RPC_TO_MACHINEDOMAIN_CACHE_ITEM@@A; _RPC_TO_MACHINEDOMAIN_CACHE_ITEM g_MachineFullDcRpcCache
0x18000efa3  mov     [rbp+arg_8], r13d
0x18000efa7  cmovz   rdi, rax
0x18000efab  mov     [rbp+var_28], r13d
0x18000efaf  mov     r15, r9
0x18000efb2  mov     esi, r8d
0x18000efb5  mov     ebx, edx
0x18000efb7  lea     r14, [rdi+10h]
0x18000efbb  mov     rcx, r14; SRWLock
0x18000efbe  call    cs:__imp_AcquireSRWLockShared
0x18000efc4  call    ?GetCurrentTimeInULL@@YA_KXZ; GetCurrentTimeInULL(void)
0x18000efc9  sub     rax, [rdi+8]
0x18000efcd  mov     ecx, r13d
0x18000efd0  mov     rdx, 0C92A69C000h
0x18000efda  cmp     rax, rdx
0x18000efdd  setnbe  cl
0x18000efe0  or      ecx, esi
0x18000efe2  jnz     short loc_18000EFF7
0x18000efe4  mov     rax, [rdi]
0x18000efe7  test    rax, rax
0x18000efea  jz      short loc_18000EFF7
0x18000efec  mov     esi, r13d
0x18000efef  mov     [r15], rax
0x18000eff2  jmp     loc_18000F136
0x18000eff7  mov     rcx, r14; SRWLock
0x18000effa  call    cs:__imp_ReleaseSRWLockShared
0x18000f000  lea     rax, [rbp+arg_8]
0x18000f004  mov     r9d, esi; int
0x18000f007  mov     [rsp+58h+var_30], rax; int *
0x18000f00c  mov     r8d, ebx; int
0x18000f00f  lea     rax, [rbp+Binding]
0x18000f013  mov     edx, r12d; int
0x18000f016  xor     ecx, ecx; unsigned __int16 *
0x18000f018  mov     [rsp+58h+var_38], rax; void **
0x18000f01d  call    ?KdsCreateClientBinding@@YAJPEBGHHHPEAPEAXPEAH@Z; KdsCreateClientBinding(ushort const *,int,int,int,void * *,int *)
0x18000f022  mov     esi, eax
0x18000f024  test    eax, eax
0x18000f026  jns     short loc_18000F04B
0x18000f028  mov     r9d, 316h; unsigned int
0x18000f02e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000f035  mov     ecx, eax; unsigned int
0x18000f037  lea     rdx, aHr; "hr"
0x18000f03e  mov     ebx, r13d
0x18000f041  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000f046  jmp     loc_18000F144
0x18000f04b  mov     rcx, r14; SRWLock
0x18000f04e  call    cs:__imp_AcquireSRWLockExclusive
0x18000f054  mov     r15, [rbp+Binding]
0x18000f058  mov     r12d, [rbp+arg_8]
0x18000f05c  call    ?GetCurrentTimeInULL@@YA_KXZ; GetCurrentTimeInULL(void)
0x18000f061  cmp     qword ptr [rdi], 0
0x18000f065  mov     r13, rax
0x18000f068  jz      short loc_18000F073
0x18000f06a  mov     rcx, rdi; Binding
0x18000f06d  call    cs:__imp_RpcBindingFree
0x18000f073  mov     [rdi+8], r13
0x18000f077  mov     rcx, r14; SRWLock
0x18000f07a  xor     r13d, r13d
0x18000f07d  mov     [rdi], r15
0x18000f080  mov     [rbp+Binding], r13
0x18000f084  mov     [rdi+18h], r12d
0x18000f088  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f08e  test    ebx, ebx
0x18000f090  jz      loc_18000F123
0x18000f096  mov     r9d, [rbp+arg_10]; int
0x18000f09a  lea     rax, [rbp+var_28]
0x18000f09e  mov     edx, [rbp+arg_0]; int
0x18000f0a1  mov     r8d, ebx; int
0x18000f0a4  mov     [rsp+58h+var_30], rax; int *
0x18000f0a9  xor     ecx, ecx; unsigned __int16 *
0x18000f0ab  lea     rax, [rbp+var_18]
0x18000f0af  mov     [rsp+58h+var_38], rax; void **
0x18000f0b4  call    ?KdsCreateClientBinding@@YAJPEBGHHHPEAPEAXPEAH@Z; KdsCreateClientBinding(ushort const *,int,int,int,void * *,int *)
0x18000f0b9  mov     esi, eax
0x18000f0bb  test    eax, eax
0x18000f0bd  jns     short loc_18000F0CA
0x18000f0bf  mov     r9d, 335h
0x18000f0c5  jmp     loc_18000F02E
0x18000f0ca  lea     rcx, stru_180023508; SRWLock
0x18000f0d1  call    cs:__imp_AcquireSRWLockExclusive
0x18000f0d7  mov     rbx, [rbp+var_18]
0x18000f0db  mov     r15d, [rbp+var_28]
0x18000f0df  call    ?GetCurrentTimeInULL@@YA_KXZ; GetCurrentTimeInULL(void)
0x18000f0e4  cmp     cs:?g_MachineDefaultDcRpcCache@@3U_RPC_TO_MACHINEDOMAIN_CACHE_ITEM@@A, r13; _RPC_TO_MACHINEDOMAIN_CACHE_ITEM g_MachineDefaultDcRpcCache
0x18000f0eb  mov     r12, rax
0x18000f0ee  jz      short loc_18000F0FD
0x18000f0f0  lea     rcx, ?g_MachineDefaultDcRpcCache@@3U_RPC_TO_MACHINEDOMAIN_CACHE_ITEM@@A; Binding
0x18000f0f7  call    cs:__imp_RpcBindingFree
0x18000f0fd  lea     rcx, stru_180023508; SRWLock
0x18000f104  mov     cs:?g_MachineDefaultDcRpcCache@@3U_RPC_TO_MACHINEDOMAIN_CACHE_ITEM@@A, rbx; _RPC_TO_MACHINEDOMAIN_CACHE_ITEM g_MachineDefaultDcRpcCache
0x18000f10b  mov     cs:qword_180023500, r12
0x18000f112  mov     cs:dword_180023510, r15d
0x18000f119  mov     [rbp+var_18], r13
0x18000f11d  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f123  mov     rcx, r14; SRWLock
0x18000f126  call    cs:__imp_AcquireSRWLockShared
0x18000f12c  mov     rcx, [rbp+arg_18]
0x18000f130  mov     rax, [rdi]
0x18000f133  mov     [rcx], rax
0x18000f136  mov     rax, [rbp+arg_20]
0x18000f13a  mov     ebx, 1
0x18000f13f  mov     ecx, [rdi+18h]
0x18000f142  mov     [rax], ecx
0x18000f144  cmp     [rbp+Binding], r13
0x18000f148  jz      short loc_18000F158
0x18000f14a  lea     rcx, [rbp+Binding]; Binding
0x18000f14e  call    cs:__imp_RpcBindingFree
0x18000f154  mov     [rbp+Binding], r13
0x18000f158  cmp     [rbp+var_18], r13
0x18000f15c  jz      short loc_18000F16C
0x18000f15e  lea     rcx, [rbp+var_18]; Binding
0x18000f162  call    cs:__imp_RpcBindingFree
0x18000f168  mov     [rbp+Binding], r13
0x18000f16c  test    esi, esi
0x18000f16e  jns     short loc_18000F18E
0x18000f170  sub     ebx, 1
0x18000f173  jz      short loc_18000F185
0x18000f175  cmp     ebx, 1
0x18000f178  jnz     short loc_18000F18E
0x18000f17a  mov     rcx, r14; SRWLock
0x18000f17d  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f183  jmp     short loc_18000F18E
0x18000f185  mov     rcx, r14; SRWLock
0x18000f188  call    cs:__imp_ReleaseSRWLockShared
0x18000f18e  mov     eax, esi
0x18000f190  add     rsp, 58h
0x18000f194  pop     r15
0x18000f196  pop     r14
0x18000f198  pop     r13
0x18000f19a  pop     r12
0x18000f19c  pop     rdi
0x18000f19d  pop     rsi
0x18000f19e  pop     rbx
0x18000f19f  pop     rbp
0x18000f1a0  retn
```
