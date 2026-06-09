# GetCachedBindingForRemoteDomain

- ea: `0x18000edb8`
- end: `0x18000ef5e`
- name: `GetCachedBindingForRemoteDomain`
- size: `422`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, int, int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ecb0`

## callees

- `0x18000eab8`
- `0x18000ebec`
- `0x18000edb8`
- `0x18000f640`
- `0x1800100d0`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ee10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ef45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ee10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ef45`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000edf8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000eea0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000edf8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000eea0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ee5b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ee5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ee93`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ef36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ee93`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ef36`
- `RPCRT4!RpcBindingFree` at `0x18000ee76`
- `RPCRT4!RpcBindingFree` at `0x18000ef12`
- `RPCRT4!RpcBindingFree` at `0x18000ee76`
- `RPCRT4!RpcBindingFree` at `0x18000ef12`

## string_xrefs

- `0x18000eef2`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyrpccommon.cxx`

## pseudocode

```c
__int64 __fastcall GetCachedBindingForRemoteDomain(unsigned __int16 *a1, unsigned int a2, int a3, int a4, _QWORD *a5)
{
  struct _RPC_HANDLE_CACHE *CachedRPCHandle; // r14
  int v10; // esi
  int v11; // eax
  int v12; // ebp
  unsigned int v13; // r9d
  unsigned int v14; // ecx
  RPC_BINDING_HANDLE v15; // rdi
  unsigned __int64 CurrentTimeInULL; // rbx
  struct _RPC_HANDLE_CACHE *v17; // rax
  int v18; // esi
  int v20; // [rsp+30h] [rbp-58h] BYREF
  RPC_BINDING_HANDLE Binding[10]; // [rsp+38h] [rbp-50h] BYREF

  Binding[0] = 0;
  GetCurrentTimeInULL();
  v20 = 0;
  *a5 = 0;
  AcquireSRWLockShared(&g_RPCHandleCacheLock);
  CachedRPCHandle = FindCachedRPCHandle(a1);
  ReleaseSRWLockShared(&g_RPCHandleCacheLock);
  v10 = 1;
  v11 = KdsCreateClientBinding(a1, a3, 1, a4, Binding, &v20);
  v12 = v11;
  if ( v11 < 0 )
  {
    v10 = 0;
    v13 = 1047;
LABEL_3:
    v14 = v11;
    goto LABEL_11;
  }
  AcquireSRWLockExclusive(&g_RPCHandleCacheLock);
  if ( CachedRPCHandle )
  {
    v15 = Binding[0];
    CurrentTimeInULL = GetCurrentTimeInULL();
    RpcBindingFree((RPC_BINDING_HANDLE *)CachedRPCHandle);
    *(_QWORD *)CachedRPCHandle = v15;
    *((_QWORD *)CachedRPCHandle + 2) = CurrentTimeInULL;
  }
  else
  {
    v11 = AddCacheEntry(a1, a2, Binding[0]);
    v12 = v11;
    if ( v11 < 0 )
    {
      v10 = 2;
      v13 = 1071;
      goto LABEL_3;
    }
  }
  Binding[0] = 0;
  ReleaseSRWLockExclusive(&g_RPCHandleCacheLock);
  AcquireSRWLockShared(&g_RPCHandleCacheLock);
  v17 = FindCachedRPCHandle(a1);
  if ( v17 )
  {
    *a5 = *(_QWORD *)v17;
    goto LABEL_12;
  }
  v12 = -2147467259;
  v13 = 1092;
  v14 = -2147467259;
LABEL_11:
  SidKeyDebugTraceError(v14, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyrpccommon.cxx", v13);
LABEL_12:
  if ( Binding[0] )
  {
    RpcBindingFree(Binding);
    Binding[0] = 0;
  }
  if ( v12 < 0 )
  {
    v18 = v10 - 1;
    if ( v18 )
    {
      if ( v18 == 1 )
        ReleaseSRWLockExclusive(&g_RPCHandleCacheLock);
    }
    else
    {
      ReleaseSRWLockShared(&g_RPCHandleCacheLock);
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000edb8  push    rbx
0x18000edba  push    rbp
0x18000edbb  push    rsi
0x18000edbc  push    rdi
0x18000edbd  push    r12
0x18000edbf  push    r13
0x18000edc1  push    r14
0x18000edc3  push    r15
0x18000edc5  sub     rsp, 48h
0x18000edc9  xor     esi, esi
0x18000edcb  mov     ebx, r9d
0x18000edce  mov     [rsp+88h+Binding], rsi
0x18000edd3  mov     edi, r8d
0x18000edd6  mov     r13d, edx
0x18000edd9  mov     r15, rcx
0x18000eddc  call    ?GetCurrentTimeInULL@@YA_KXZ; GetCurrentTimeInULL(void)
0x18000ede1  mov     r12, [rsp+88h+arg_20]
0x18000ede9  lea     rcx, ?g_RPCHandleCacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000edf0  mov     [rsp+88h+var_58], esi
0x18000edf4  mov     [r12], rsi
0x18000edf8  call    cs:__imp_AcquireSRWLockShared
0x18000edfe  mov     rcx, r15; unsigned __int16 *
0x18000ee01  call    ?FindCachedRPCHandle@@YAPEAU_RPC_HANDLE_CACHE@@PEBG@Z; FindCachedRPCHandle(ushort const *)
0x18000ee06  lea     rcx, ?g_RPCHandleCacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000ee0d  mov     r14, rax
0x18000ee10  call    cs:__imp_ReleaseSRWLockShared
0x18000ee16  lea     rax, [rsp+88h+var_58]
0x18000ee1b  mov     esi, 1
0x18000ee20  mov     [rsp+88h+var_60], rax; int *
0x18000ee25  mov     r9d, ebx; int
0x18000ee28  lea     rax, [rsp+88h+Binding]
0x18000ee2d  mov     r8d, esi; int
0x18000ee30  mov     edx, edi; int
0x18000ee32  mov     [rsp+88h+var_68], rax; void **
0x18000ee37  mov     rcx, r15; unsigned __int16 *
0x18000ee3a  call    ?KdsCreateClientBinding@@YAJPEBGHHHPEAPEAXPEAH@Z; KdsCreateClientBinding(ushort const *,int,int,int,void * *,int *)
0x18000ee3f  mov     ebp, eax
0x18000ee41  test    eax, eax
0x18000ee43  jns     short loc_18000EE54
0x18000ee45  xor     esi, esi
0x18000ee47  mov     r9d, 417h
0x18000ee4d  mov     ecx, eax
0x18000ee4f  jmp     loc_18000EEF2
0x18000ee54  lea     rcx, ?g_RPCHandleCacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000ee5b  call    cs:__imp_AcquireSRWLockExclusive
0x18000ee61  test    r14, r14
0x18000ee64  jz      short loc_18000EEBC
0x18000ee66  mov     rdi, [rsp+88h+Binding]
0x18000ee6b  call    ?GetCurrentTimeInULL@@YA_KXZ; GetCurrentTimeInULL(void)
0x18000ee70  mov     rcx, r14; Binding
0x18000ee73  mov     rbx, rax
0x18000ee76  call    cs:__imp_RpcBindingFree
0x18000ee7c  mov     [r14], rdi
0x18000ee7f  mov     [r14+10h], rbx
0x18000ee83  lea     rcx, ?g_RPCHandleCacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000ee8a  mov     [rsp+88h+Binding], 0
0x18000ee93  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ee99  lea     rcx, ?g_RPCHandleCacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000eea0  call    cs:__imp_AcquireSRWLockShared
0x18000eea6  mov     rcx, r15; unsigned __int16 *
0x18000eea9  call    ?FindCachedRPCHandle@@YAPEAU_RPC_HANDLE_CACHE@@PEBG@Z; FindCachedRPCHandle(ushort const *)
0x18000eeae  test    rax, rax
0x18000eeb1  jz      short loc_18000EEE2
0x18000eeb3  mov     rax, [rax]
0x18000eeb6  mov     [r12], rax
0x18000eeba  jmp     short loc_18000EF05
0x18000eebc  mov     r8, [rsp+88h+Binding]; void *
0x18000eec1  mov     edx, r13d; unsigned int
0x18000eec4  mov     rcx, r15; Src
0x18000eec7  call    ?AddCacheEntry@@YAJPEBGKPEAX@Z; AddCacheEntry(ushort const *,ulong,void *)
0x18000eecc  mov     ebp, eax
0x18000eece  test    eax, eax
0x18000eed0  jns     short loc_18000EE83
0x18000eed2  mov     esi, 2
0x18000eed7  mov     r9d, 42Fh
0x18000eedd  jmp     loc_18000EE4D
0x18000eee2  mov     ebp, 80004005h
0x18000eee7  mov     r9d, 444h; unsigned int
0x18000eeed  mov     ecx, 80004005h; unsigned int
0x18000eef2  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000eef9  lea     rdx, aHr; "hr"
0x18000ef00  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000ef05  cmp     [rsp+88h+Binding], 0
0x18000ef0b  jz      short loc_18000EF21
0x18000ef0d  lea     rcx, [rsp+88h+Binding]; Binding
0x18000ef12  call    cs:__imp_RpcBindingFree
0x18000ef18  mov     [rsp+88h+Binding], 0
0x18000ef21  test    ebp, ebp
0x18000ef23  jns     short loc_18000EF4B
0x18000ef25  sub     esi, 1
0x18000ef28  jz      short loc_18000EF3E
0x18000ef2a  cmp     esi, 1
0x18000ef2d  jnz     short loc_18000EF4B
0x18000ef2f  lea     rcx, ?g_RPCHandleCacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000ef36  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ef3c  jmp     short loc_18000EF4B
0x18000ef3e  lea     rcx, ?g_RPCHandleCacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000ef45  call    cs:__imp_ReleaseSRWLockShared
0x18000ef4b  mov     eax, ebp
0x18000ef4d  add     rsp, 48h
0x18000ef51  pop     r15
0x18000ef53  pop     r14
0x18000ef55  pop     r13
0x18000ef57  pop     r12
0x18000ef59  pop     rdi
0x18000ef5a  pop     rsi
0x18000ef5b  pop     rbp
0x18000ef5c  pop     rbx
0x18000ef5d  retn
```
