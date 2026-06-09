# GetKeyFromKdsService(uchar *,ulong,_GUID *,long,long,long,int,ulong,ushort const *,ulong,ushort const *,uchar * *,ulong *)

- ea: `0x180019274`
- end: `0x1800196c3`
- name: `?GetKeyFromKdsService@@YAJPEAEKPEAU_GUID@@JJJHKPEBGK2PEAPEAEPEAK@Z`
- size: `1103`
- prototype: `__int64 __fastcall(unsigned __int8 *, int, struct _GUID *, int, int, int, int, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180016df0`
- `0x180017030`
- `0x1800196cc`
- `0x180019bec`

## callees

- `0x18000ecb0`
- `0x18000f9f0`
- `0x18000fc80`
- `0x180010950`
- `0x180010d60`
- `0x180019274`
- `0x18001a450`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x18001a806`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001a83b`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001a806`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001a83b`
- `RPCRT4!RpcBindingFree` at `0x1800196ab`
- `RPCRT4!RpcBindingFree` at `0x1800196ab`

## string_xrefs

- `0x1800192e1`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x180019474`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x1800194c8`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x1800195f3`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x180019643`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`

## pseudocode

```c
__int64 __fastcall GetKeyFromKdsService(
        unsigned __int8 *a1,
        int a2,
        struct _GUID *a3,
        int a4,
        int a5,
        int a6,
        int a7,
        unsigned int a8,
        unsigned __int16 *a9,
        unsigned int a10,
        unsigned __int16 *a11,
        unsigned __int8 **a12,
        unsigned int *a13)
{
  int v13; // ebx
  unsigned int v14; // r9d
  unsigned int v15; // ecx
  unsigned int v16; // esi
  int v17; // r15d
  const unsigned __int16 *v18; // r12
  unsigned int v19; // r13d
  __int64 v20; // rax
  int ClientLRPCBinding; // eax
  int v22; // ecx
  signed int Key; // eax
  unsigned __int64 v24; // rax
  __int64 v25; // rcx
  int v26; // eax
  signed int v27; // eax
  unsigned int v29; // [rsp+50h] [rbp-58h] BYREF
  int v30; // [rsp+54h] [rbp-54h] BYREF
  unsigned int v31; // [rsp+58h] [rbp-50h] BYREF
  signed int v32; // [rsp+5Ch] [rbp-4Ch]
  void *v33; // [rsp+60h] [rbp-48h] BYREF
  void *lpMem; // [rsp+68h] [rbp-40h] BYREF
  RPC_BINDING_HANDLE Binding[7]; // [rsp+70h] [rbp-38h] BYREF
  int v36; // [rsp+B0h] [rbp+8h]
  int v38; // [rsp+C0h] [rbp+18h]

  v38 = (int)a3;
  v36 = (int)a1;
  v33 = 0;
  Binding[0] = 0;
  v29 = 0;
  lpMem = 0;
  v31 = 0;
  v30 = 0;
  if ( (a8 & 0xDFFFFFFF) != 0 )
  {
    v13 = -2147024809;
    v14 = 1183;
    v15 = -2147024809;
LABEL_3:
    SidKeyDebugTraceError(v15, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx", v14);
    goto LABEL_30;
  }
  v16 = (a8 >> 29) & 1;
  if ( v16 )
  {
    ClientLRPCBinding = KdsCreateClientLRPCBinding(Binding);
    v18 = a11;
    v19 = a10;
    v17 = a7;
    goto LABEL_9;
  }
  v17 = a7;
  v18 = a11;
  v19 = a10;
  v13 = GetAndLockCachedRPCBinding(a9, a10, a11, a7, 0, 0, &v33, (enum _RPC_CACHE_TYPE *)&v29, &v30);
  if ( (unsigned int)(v13 + 2147023179) <= 0x24 )
  {
    v20 = 0x1000000021LL;
    if ( _bittest64(&v20, v13 + 2147023179) )
    {
      ClientLRPCBinding = GetAndLockCachedRPCBinding(a9, a10, a11, a7, 0, 1, &v33, (enum _RPC_CACHE_TYPE *)&v29, &v30);
LABEL_9:
      v13 = ClientLRPCBinding;
    }
  }
  if ( v13 < 0 )
  {
    v14 = 1235;
LABEL_12:
    v15 = v13;
    goto LABEL_3;
  }
  v22 = (int)Binding[0];
  if ( v33 )
    v22 = (int)v33;
  Key = GetKey(v22, a2, v36, v38, a4, a5, a6, (__int64)&v31, (__int64)&lpMem);
  v13 = Key;
  v32 = Key;
  if ( Key < 0 )
    SidKeyDebugTraceError(
      Key,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
      0x4E6u);
  if ( !v16 )
  {
    if ( (UnlockRpcCache(v29), v24 = (unsigned int)(v13 + 2147023179), (unsigned int)v24 <= 0x24)
      && (v25 = 0x1000000621LL, _bittest64(&v25, v24))
      || v30 == 1 && v13 == -2147024891 )
    {
      v26 = GetAndLockCachedRPCBinding(a9, v19, v18, v17, 1, 1, &v33, (enum _RPC_CACHE_TYPE *)&v29, &v30);
      v13 = v26;
      if ( v26 < 0 )
      {
        v14 = 1292;
        v15 = v26;
        goto LABEL_3;
      }
      v27 = GetKey((_DWORD)v33, a2, v36, v38, a4, a5, a6, (__int64)&v31, (__int64)&lpMem);
      v13 = v27;
      v32 = v27;
      if ( v27 < 0 )
        SidKeyDebugTraceError(
          v27,
          "hr",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
          0x51Fu);
      UnlockRpcCache(v29);
    }
  }
  if ( v13 < 0 )
  {
    v14 = 1329;
    goto LABEL_12;
  }
  *a12 = (unsigned __int8 *)lpMem;
  lpMem = 0;
  *a13 = v31;
LABEL_30:
  if ( lpMem )
    SIDKeyProvFree(lpMem);
  if ( Binding[0] )
    RpcBindingFree(Binding);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180019274  mov     rax, rsp
0x180019277  mov     [rax+20h], r9d
0x18001927b  mov     [rax+18h], r8
0x18001927f  mov     [rax+10h], edx
0x180019282  mov     [rax+8], rcx
0x180019286  push    rbx
0x180019287  push    rsi
0x180019288  push    r12
0x18001928a  push    r13
0x18001928c  push    r15
0x18001928e  sub     rsp, 80h
0x180019295  mov     qword ptr [rax-48h], 0
0x18001929d  mov     qword ptr [rax-38h], 0
0x1800192a5  mov     dword ptr [rax-58h], 0
0x1800192ac  mov     qword ptr [rax-40h], 0
0x1800192b4  mov     dword ptr [rax-50h], 0
0x1800192bb  mov     dword ptr [rax-54h], 0
0x1800192c2  mov     esi, [rsp+0A8h+arg_38]
0x1800192c9  test    esi, 0DFFFFFFFh
0x1800192cf  jz      short loc_1800192F9
0x1800192d1  mov     ebx, 80070057h
0x1800192d6  mov     r9d, 49Fh; unsigned int
0x1800192dc  mov     ecx, 80070057h; unsigned int
0x1800192e1  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800192e8  lea     rdx, aHr; "hr"
0x1800192ef  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800192f4  jmp     loc_18001968F
0x1800192f9  shr     esi, 1Dh
0x1800192fc  and     esi, 1
0x1800192ff  mov     [rsp+0A8h+arg_38], esi
0x180019306  jnz     loc_1800193CD
0x18001930c  lea     rax, [rsp+0A8h+var_54]
0x180019311  mov     [rsp+0A8h+var_68], rax; int *
0x180019316  lea     rax, [rsp+0A8h+var_58]
0x18001931b  mov     [rsp+0A8h+var_70], rax; enum _RPC_CACHE_TYPE *
0x180019320  lea     rax, [rsp+0A8h+var_48]
0x180019325  mov     [rsp+0A8h+var_78], rax; void **
0x18001932a  mov     [rsp+0A8h+var_80], 0; int
0x180019332  mov     [rsp+0A8h+var_88], 0; int
0x18001933a  mov     r15d, [rsp+0A8h+arg_30]
0x180019342  mov     r9d, r15d; int
0x180019345  mov     r12, [rsp+0A8h+arg_50]
0x18001934d  mov     r8, r12; unsigned __int16 *
0x180019350  mov     r13d, [rsp+0A8h+arg_48]
0x180019358  mov     edx, r13d; unsigned int
0x18001935b  mov     rcx, [rsp+0A8h+arg_40]; unsigned __int16 *
0x180019363  call    ?GetAndLockCachedRPCBinding@@YAJPEBGK0HHHPEAPEAXPEAW4_RPC_CACHE_TYPE@@PEAH@Z; GetAndLockCachedRPCBinding(ushort const *,ulong,ushort const *,int,int,int,void * *,_RPC_CACHE_TYPE *,int *)
0x180019368  mov     ebx, eax
0x18001936a  add     eax, 7FF8F94Bh
0x18001936f  cmp     eax, 24h ; '$'
0x180019372  ja      short loc_1800193F1
0x180019374  movsxd  rcx, eax
0x180019377  mov     rax, 1000000021h
0x180019381  bt      rax, rcx
0x180019385  jnb     short loc_1800193F1
0x180019387  lea     rax, [rsp+0A8h+var_54]
0x18001938c  mov     [rsp+0A8h+var_68], rax; int *
0x180019391  lea     rax, [rsp+0A8h+var_58]
0x180019396  mov     [rsp+0A8h+var_70], rax; enum _RPC_CACHE_TYPE *
0x18001939b  lea     rax, [rsp+0A8h+var_48]
0x1800193a0  mov     [rsp+0A8h+var_78], rax; void **
0x1800193a5  mov     [rsp+0A8h+var_80], 1; int
0x1800193ad  mov     [rsp+0A8h+var_88], 0; int
0x1800193b5  mov     r9d, r15d; int
0x1800193b8  mov     r8, r12; unsigned __int16 *
0x1800193bb  mov     edx, r13d; unsigned int
0x1800193be  mov     rcx, [rsp+0A8h+arg_40]; unsigned __int16 *
0x1800193c6  call    ?GetAndLockCachedRPCBinding@@YAJPEBGK0HHHPEAPEAXPEAW4_RPC_CACHE_TYPE@@PEAH@Z; GetAndLockCachedRPCBinding(ushort const *,ulong,ushort const *,int,int,int,void * *,_RPC_CACHE_TYPE *,int *)
0x1800193cb  jmp     short loc_1800193EF
0x1800193cd  lea     rcx, [rsp+0A8h+Binding]; void **
0x1800193d2  call    ?KdsCreateClientLRPCBinding@@YAJPEAPEAX@Z; KdsCreateClientLRPCBinding(void * *)
0x1800193d7  mov     r12, [rsp+0A8h+arg_50]
0x1800193df  mov     r13d, [rsp+0A8h+arg_48]
0x1800193e7  mov     r15d, [rsp+0A8h+arg_30]
0x1800193ef  mov     ebx, eax
0x1800193f1  test    ebx, ebx
0x1800193f3  jns     short loc_180019402
0x1800193f5  mov     r9d, 4D3h
0x1800193fb  mov     ecx, ebx
0x1800193fd  jmp     loc_1800192E1
0x180019402  mov     rcx, [rsp+0A8h+Binding]
0x180019407  cmp     [rsp+0A8h+var_48], 0
0x18001940d  cmovnz  rcx, [rsp+0A8h+var_48]
0x180019413  lea     rax, [rsp+0A8h+lpMem]
0x180019418  mov     [rsp+0A8h+var_68], rax
0x18001941d  lea     rax, [rsp+0A8h+var_50]
0x180019422  mov     [rsp+0A8h+var_70], rax
0x180019427  mov     eax, [rsp+0A8h+arg_28]
0x18001942e  mov     dword ptr [rsp+0A8h+var_78], eax
0x180019432  mov     eax, [rsp+0A8h+arg_20]
0x180019439  mov     [rsp+0A8h+var_80], eax
0x18001943d  mov     eax, [rsp+0A8h+arg_18]
0x180019444  mov     [rsp+0A8h+var_88], eax
0x180019448  mov     r9, [rsp+0A8h+arg_10]
0x180019450  mov     r8, [rsp+0A8h+arg_0]
0x180019458  mov     edx, [rsp+0A8h+arg_8]
0x18001945f  call    GetKey
0x180019464  mov     ebx, eax
0x180019466  mov     [rsp+0A8h+var_4C], eax
0x18001946a  test    eax, eax
0x18001946c  jns     short loc_18001948A
0x18001946e  mov     r9d, 4E6h; unsigned int
0x180019474  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18001947b  lea     rdx, aHr; "hr"
0x180019482  mov     ecx, eax; unsigned int
0x180019484  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180019489  nop
0x18001948a  test    esi, esi
0x18001948c  jnz     short loc_180019497
0x18001948e  mov     ecx, [rsp+0A8h+var_58]
0x180019492  call    ?UnlockRpcCache@@YAXW4_RPC_CACHE_TYPE@@@Z; UnlockRpcCache(_RPC_CACHE_TYPE)
0x180019497  jmp     short loc_1800194FC
0x180019499  mov     ebx, eax
0x18001949b  test    eax, eax
0x18001949d  jz      short loc_1800194C2
0x18001949f  test    ebx, ebx
0x1800194a1  jns     short loc_1800194B7
0x1800194a3  and     eax, 1FFF0000h
0x1800194a8  cmp     eax, 10000h
0x1800194ad  jz      short loc_1800194C2
0x1800194af  or      ebx, 10000000h
0x1800194b5  jmp     short loc_1800194C2
0x1800194b7  jle     short loc_1800194C2
0x1800194b9  movzx   ebx, bx
0x1800194bc  or      ebx, 80070000h
0x1800194c2  mov     r9d, 4F3h; unsigned int
0x1800194c8  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800194cf  lea     rdx, aHr; "hr"
0x1800194d6  mov     ecx, ebx; unsigned int
0x1800194d8  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800194dd  mov     r12, [rsp+0A8h+arg_50]
0x1800194e5  mov     r13d, [rsp+0A8h+arg_48]
0x1800194ed  mov     r15d, [rsp+0A8h+arg_30]
0x1800194f5  mov     esi, [rsp+0A8h+arg_38]
0x1800194fc  test    esi, esi
0x1800194fe  jnz     loc_180019659
0x180019504  lea     eax, [rbx+7FF8F94Bh]
0x18001950a  cmp     eax, 24h ; '$'
0x18001950d  ja      short loc_18001951F
0x18001950f  mov     rcx, 1000000621h
0x180019519  bt      rcx, rax
0x18001951d  jb      short loc_180019536
0x18001951f  cmp     [rsp+0A8h+var_54], 1
0x180019524  jnz     loc_180019659
0x18001952a  cmp     ebx, 80070005h
0x180019530  jnz     loc_180019659
0x180019536  lea     rax, [rsp+0A8h+var_54]
0x18001953b  mov     [rsp+0A8h+var_68], rax; int *
0x180019540  lea     rax, [rsp+0A8h+var_58]
0x180019545  mov     [rsp+0A8h+var_70], rax; enum _RPC_CACHE_TYPE *
0x18001954a  lea     rax, [rsp+0A8h+var_48]
0x18001954f  mov     [rsp+0A8h+var_78], rax; void **
0x180019554  mov     [rsp+0A8h+var_80], 1; int
0x18001955c  mov     [rsp+0A8h+var_88], 1; int
0x180019564  mov     r9d, r15d; int
0x180019567  mov     r8, r12; unsigned __int16 *
0x18001956a  mov     edx, r13d; unsigned int
0x18001956d  mov     rcx, [rsp+0A8h+arg_40]; unsigned __int16 *
0x180019575  call    ?GetAndLockCachedRPCBinding@@YAJPEBGK0HHHPEAPEAXPEAW4_RPC_CACHE_TYPE@@PEAH@Z; GetAndLockCachedRPCBinding(ushort const *,ulong,ushort const *,int,int,int,void * *,_RPC_CACHE_TYPE *,int *)
0x18001957a  mov     ebx, eax
0x18001957c  test    eax, eax
0x18001957e  jns     short loc_18001958D
0x180019580  mov     r9d, 50Ch
0x180019586  mov     ecx, eax
0x180019588  jmp     loc_1800192E1
0x18001958d  lea     rax, [rsp+0A8h+lpMem]
0x180019592  mov     [rsp+0A8h+var_68], rax
0x180019597  lea     rax, [rsp+0A8h+var_50]
0x18001959c  mov     [rsp+0A8h+var_70], rax
0x1800195a1  mov     eax, [rsp+0A8h+arg_28]
0x1800195a8  mov     dword ptr [rsp+0A8h+var_78], eax
0x1800195ac  mov     eax, [rsp+0A8h+arg_20]
0x1800195b3  mov     [rsp+0A8h+var_80], eax
0x1800195b7  mov     eax, [rsp+0A8h+arg_18]
0x1800195be  mov     [rsp+0A8h+var_88], eax
0x1800195c2  mov     r9, [rsp+0A8h+arg_10]
0x1800195ca  mov     r8, [rsp+0A8h+arg_0]
0x1800195d2  mov     edx, [rsp+0A8h+arg_8]
0x1800195d9  mov     rcx, [rsp+0A8h+var_48]
0x1800195de  call    GetKey
0x1800195e3  mov     ebx, eax
0x1800195e5  mov     [rsp+0A8h+var_4C], eax
0x1800195e9  test    eax, eax
0x1800195eb  jns     short loc_180019609
0x1800195ed  mov     r9d, 51Fh; unsigned int
0x1800195f3  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800195fa  lea     rdx, aHr; "hr"
0x180019601  mov     ecx, eax; unsigned int
0x180019603  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180019608  nop
0x180019609  mov     ecx, [rsp+0A8h+var_58]
0x18001960d  call    ?UnlockRpcCache@@YAXW4_RPC_CACHE_TYPE@@@Z; UnlockRpcCache(_RPC_CACHE_TYPE)
0x180019612  jmp     short loc_180019659
0x180019614  mov     ebx, eax
0x180019616  test    eax, eax
0x180019618  jz      short loc_18001963D
0x18001961a  test    ebx, ebx
0x18001961c  jns     short loc_180019632
0x18001961e  and     eax, 1FFF0000h
0x180019623  cmp     eax, 10000h
0x180019628  jz      short loc_18001963D
0x18001962a  or      ebx, 10000000h
0x180019630  jmp     short loc_18001963D
0x180019632  jle     short loc_18001963D
0x180019634  movzx   ebx, bx
0x180019637  or      ebx, 80070000h
0x18001963d  mov     r9d, 529h; unsigned int
0x180019643  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18001964a  lea     rdx, aHr; "hr"
0x180019651  mov     ecx, ebx; unsigned int
0x180019653  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180019658  nop
0x180019659  test    ebx, ebx
0x18001965b  jns     short loc_180019668
0x18001965d  mov     r9d, 531h
0x180019663  jmp     loc_1800193FB
0x180019668  mov     rcx, [rsp+0A8h+lpMem]
0x18001966d  mov     rax, [rsp+0A8h+arg_58]
0x180019675  mov     [rax], rcx
0x180019678  mov     [rsp+0A8h+lpMem], 0
0x180019681  mov     ecx, [rsp+0A8h+var_50]
0x180019685  mov     rax, [rsp+0A8h+arg_60]
0x18001968d  mov     [rax], ecx
0x18001968f  mov     rcx, [rsp+0A8h+lpMem]; lpMem
0x180019694  test    rcx, rcx
0x180019697  jz      short loc_18001969E
0x180019699  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18001969e  cmp     [rsp+0A8h+Binding], 0
0x1800196a4  jz      short loc_1800196B1
0x1800196a6  lea     rcx, [rsp+0A8h+Binding]; Binding
0x1800196ab  call    cs:__imp_RpcBindingFree
0x1800196b1  mov     eax, ebx
0x1800196b3  add     rsp, 80h
0x1800196ba  pop     r15
0x1800196bc  pop     r13
0x1800196be  pop     r12
0x1800196c0  pop     rsi
0x1800196c1  pop     rbx
0x1800196c2  retn
0x18001a7d6  push    rbp
0x18001a7d8  sub     rsp, 50h
0x18001a7dc  mov     rbp, rdx
0x18001a7df  cmp     dword ptr [rbp+0E8h], 0
0x18001a7e6  jnz     short loc_18001A7F1
0x18001a7e8  mov     ecx, [rbp+50h]
0x18001a7eb  call    ?UnlockRpcCache@@YAXW4_RPC_CACHE_TYPE@@@Z; UnlockRpcCache(_RPC_CACHE_TYPE)
0x18001a7f0  nop
0x18001a7f1  add     rsp, 50h
0x18001a7f5  pop     rbp
0x18001a7f6  retn
0x18001a7f8  push    rbp
0x18001a7fa  sub     rsp, 50h
0x18001a7fe  mov     rbp, rdx
0x18001a801  mov     rcx, [rcx]
0x18001a804  mov     ecx, [rcx]; ExceptionCode
0x18001a806  call    cs:__imp_I_RpcExceptionFilter
0x18001a80c  nop
0x18001a80d  add     rsp, 50h
0x18001a811  pop     rbp
0x18001a812  retn
0x18001a814  push    rbp
0x18001a816  sub     rsp, 50h
0x18001a81a  mov     rbp, rdx
0x18001a81d  mov     ecx, [rbp+50h]
0x18001a820  call    ?UnlockRpcCache@@YAXW4_RPC_CACHE_TYPE@@@Z; UnlockRpcCache(_RPC_CACHE_TYPE)
0x18001a825  nop
0x18001a826  add     rsp, 50h
0x18001a82a  pop     rbp
0x18001a82b  retn
0x18001a82d  push    rbp
0x18001a82f  sub     rsp, 50h
0x18001a833  mov     rbp, rdx
0x18001a836  mov     rcx, [rcx]
0x18001a839  mov     ecx, [rcx]; ExceptionCode
0x18001a83b  call    cs:__imp_I_RpcExceptionFilter
0x18001a841  nop
0x18001a842  add     rsp, 50h
0x18001a846  pop     rbp
0x18001a847  retn
```
