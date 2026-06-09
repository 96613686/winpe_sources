# GetAndLockCachedRPCBinding(ushort const *,ulong,ushort const *,int,int,int,void * *,_RPC_CACHE_TYPE *,int *)

- ea: `0x18000ecb0`
- end: `0x18000edaf`
- name: `?GetAndLockCachedRPCBinding@@YAJPEBGK0HHHPEAPEAXPEAW4_RPC_CACHE_TYPE@@PEAH@Z`
- size: `255`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, const unsigned __int16 *, int, int, int, void **, enum _RPC_CACHE_TYPE *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019274`

## callees

- `0x18000ecb0`
- `0x18000edb8`
- `0x18000ef64`
- `0x18000f560`
- `0x18001a450`

## string_xrefs

- `0x18000ed8f`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyrpccommon.cxx`

## pseudocode

```c
__int64 __fastcall GetAndLockCachedRPCBinding(
        unsigned __int16 *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        int a4,
        int a5,
        int a6,
        void **a7,
        enum _RPC_CACHE_TYPE *a8,
        int *a9)
{
  signed int CachedBindingToMachineDC; // eax
  unsigned int v13; // ebx
  unsigned int v14; // r9d
  int v15; // eax
  int v16; // edx
  int v17; // r8d
  int v18; // r9d
  int v20; // [rsp+70h] [rbp+18h] BYREF

  v20 = 0;
  if ( a3 )
  {
    CachedBindingToMachineDC = IsMachineInTheSameForest(a3, &v20);
    v13 = CachedBindingToMachineDC;
    if ( CachedBindingToMachineDC < 0 )
    {
      v14 = 1212;
LABEL_11:
      SidKeyDebugTraceError(
        CachedBindingToMachineDC,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyrpccommon.cxx",
        v14);
      return v13;
    }
    v15 = v20;
  }
  else
  {
    v15 = 1;
  }
  if ( v15 )
  {
    v16 = a5;
    v17 = a6;
    *(_DWORD *)a8 = a5 != 0;
    CachedBindingToMachineDC = GetCachedBindingToMachineDC(a4, v16, v17, (__int64)a9);
    v13 = CachedBindingToMachineDC;
    if ( CachedBindingToMachineDC < 0 )
    {
      v14 = 1233;
      goto LABEL_11;
    }
  }
  else
  {
    v18 = a6;
    *a9 = 0;
    *(_DWORD *)a8 = 2;
    CachedBindingToMachineDC = GetCachedBindingForRemoteDomain(a1, a2, a4, v18, (__int64)a7);
    v13 = CachedBindingToMachineDC;
    if ( CachedBindingToMachineDC < 0 )
    {
      v14 = 1250;
      goto LABEL_11;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x18000ecb0  push    rbx
0x18000ecb2  push    rbp
0x18000ecb3  push    rsi
0x18000ecb4  push    rdi
0x18000ecb5  sub     rsp, 38h
0x18000ecb9  mov     [rsp+58h+arg_10], 0
0x18000ecc1  mov     edi, r9d
0x18000ecc4  mov     esi, edx
0x18000ecc6  mov     rbp, rcx
0x18000ecc9  test    r8, r8
0x18000eccc  jz      short loc_18000ECF2
0x18000ecce  lea     rdx, [rsp+58h+arg_10]
0x18000ecd3  mov     rcx, r8
0x18000ecd6  call    IsMachineInTheSameForest
0x18000ecdb  mov     ebx, eax
0x18000ecdd  test    eax, eax
0x18000ecdf  jns     short loc_18000ECEC
0x18000ece1  mov     r9d, 4BCh
0x18000ece7  jmp     loc_18000ED8F
0x18000ecec  mov     eax, [rsp+58h+arg_10]
0x18000ecf0  jmp     short loc_18000ECF7
0x18000ecf2  mov     eax, 1
0x18000ecf7  test    eax, eax
0x18000ecf9  jz      short loc_18000ED45
0x18000ecfb  mov     edx, [rsp+58h+arg_20]; int
0x18000ed02  xor     ecx, ecx
0x18000ed04  mov     rax, [rsp+58h+arg_38]
0x18000ed0c  test    edx, edx
0x18000ed0e  mov     r9, [rsp+58h+arg_30]
0x18000ed16  mov     r8d, [rsp+58h+arg_28]; int
0x18000ed1e  setnz   cl
0x18000ed21  mov     [rax], ecx
0x18000ed23  mov     ecx, edi; int
0x18000ed25  mov     rax, [rsp+58h+arg_40]
0x18000ed2d  mov     [rsp+58h+var_38], rax; __int64
0x18000ed32  call    GetCachedBindingToMachineDC
0x18000ed37  mov     ebx, eax
0x18000ed39  test    eax, eax
0x18000ed3b  jns     short loc_18000EDA4
0x18000ed3d  mov     r9d, 4D1h
0x18000ed43  jmp     short loc_18000ED8F
0x18000ed45  mov     rax, [rsp+58h+arg_40]
0x18000ed4d  mov     r8d, edi; int
0x18000ed50  mov     r9d, [rsp+58h+arg_28]; int
0x18000ed58  mov     edx, esi; unsigned int
0x18000ed5a  mov     rcx, rbp; unsigned __int16 *
0x18000ed5d  mov     dword ptr [rax], 0
0x18000ed63  mov     rax, [rsp+58h+arg_38]
0x18000ed6b  mov     dword ptr [rax], 2
0x18000ed71  mov     rax, [rsp+58h+arg_30]
0x18000ed79  mov     [rsp+58h+var_38], rax; __int64
0x18000ed7e  call    GetCachedBindingForRemoteDomain
0x18000ed83  mov     ebx, eax
0x18000ed85  test    eax, eax
0x18000ed87  jns     short loc_18000EDA4
0x18000ed89  mov     r9d, 4E2h; unsigned int
0x18000ed8f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000ed96  mov     ecx, eax; unsigned int
0x18000ed98  lea     rdx, aHr; "hr"
0x18000ed9f  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000eda4  mov     eax, ebx
0x18000eda6  add     rsp, 38h
0x18000edaa  pop     rdi
0x18000edab  pop     rsi
0x18000edac  pop     rbp
0x18000edad  pop     rbx
0x18000edae  retn
```
