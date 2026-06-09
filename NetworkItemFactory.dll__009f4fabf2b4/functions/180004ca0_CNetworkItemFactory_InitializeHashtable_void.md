# CNetworkItemFactory::_InitializeHashtable(void)

- ea: `0x180004ca0`
- end: `0x180004daa`
- name: `?_InitializeHashtable@CNetworkItemFactory@@AEAAJXZ`
- size: `266`
- prototype: `__int64 __fastcall(CNetworkItemFactory *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003470`
- `0x180004ba0`

## callees

- `0x180004ca0`
- `0x1800070c8`
- `0x180007a34`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CNetworkItemFactory::_InitializeHashtable(CNetworkItemFactory *this)
{
  LKRhash::CLKRHashTable *v2; // rbx
  LKRhash::CLKRHashTable *v3; // rbx
  unsigned int v5; // [rsp+38h] [rbp-40h]
  unsigned int v6; // [rsp+40h] [rbp-38h]
  bool v7; // [rsp+48h] [rbp-30h]
  bool v8; // [rsp+50h] [rbp-28h]
  struct CLKRhashAllocator *v9; // [rsp+58h] [rbp-20h]

  if ( !*((_QWORD *)this + 10) )
  {
    v2 = (LKRhash::CLKRHashTable *)operator new(0x50u);
    if ( v2 )
      LKRhash::CLKRHashTable::CLKRHashTable(
        v2,
        "FIID To NetworkItem",
        LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,unsigned short const *,LKRhash::CLKRHashTable>::_ExtractKey,
        LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,unsigned short const *,LKRhash::CLKRHashTable>::_CalcKeyHash,
        (bool (*)(unsigned __int64, unsigned __int64))LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,unsigned short const *,LKRhash::CLKRHashTable>::_EqualKeys,
        (void (*)(const void *, int))LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,unsigned short const *,LKRhash::CLKRHashTable>::_AddRefRecord,
        4.0,
        v5,
        v6,
        v7,
        v8,
        v9);
    else
      v2 = 0;
    *((_QWORD *)this + 10) = v2;
  }
  v3 = (LKRhash::CLKRHashTable *)*((_QWORD *)this + 11);
  if ( !v3 )
  {
    v3 = (LKRhash::CLKRHashTable *)operator new(0x50u);
    if ( v3 )
      LKRhash::CLKRHashTable::CLKRHashTable(
        v3,
        "Name To NetworkItem",
        LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,unsigned short const *,LKRhash::CLKRHashTable>::_ExtractKey,
        LKRhash::CTypedHashTable<CNameToNetworkItemHashTable,IDToNetworkItemRecord const,unsigned short const *,LKRhash::CLKRHashTable>::_CalcKeyHash,
        (bool (*)(unsigned __int64, unsigned __int64))LKRhash::CTypedHashTable<CNameToNetworkItemHashTable,IDToNetworkItemRecord const,unsigned short const *,LKRhash::CLKRHashTable>::_EqualKeys,
        (void (*)(const void *, int))LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,unsigned short const *,LKRhash::CLKRHashTable>::_AddRefRecord,
        4.0,
        v5,
        v6,
        v7,
        v8,
        v9);
    else
      v3 = 0;
    *((_QWORD *)this + 11) = v3;
  }
  if ( *((_QWORD *)this + 10) && v3 )
    return 0;
  else
    return 2147942414LL;
}

```

## disassembly

```asm
0x180004ca0  mov     [rsp+arg_8], rbx
0x180004ca5  push    rdi
0x180004ca6  sub     rsp, 70h
0x180004caa  movaps  [rsp+78h+var_18], xmm6
0x180004caf  mov     rdi, rcx
0x180004cb2  movsd   xmm6, cs:__real@4010000000000000
0x180004cba  cmp     qword ptr [rcx+50h], 0
0x180004cbf  jnz     short loc_180004D1E
0x180004cc1  mov     ecx, 50h ; 'P'; unsigned __int64
0x180004cc6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004ccb  mov     rbx, rax
0x180004cce  mov     [rsp+78h+arg_0], rax
0x180004cd6  test    rax, rax
0x180004cd9  jz      short loc_180004D18
0x180004cdb  movsd   [rsp+78h+var_48], xmm6; double
0x180004ce1  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VCIDToNetworkItemHashTable@@$$CBVIDToNetworkItemRecord@@PEBGVCLKRHashTable@LKRhash@@@LKRhash@@CAXPEBXH@Z; LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,ushort const *,LKRhash::CLKRHashTable>::_AddRefRecord(void const *,int)
0x180004ce8  mov     [rsp+78h+var_50], rax; void (*)(const void *, int)
0x180004ced  lea     rax, ?_EqualKeys@?$CTypedHashTable@VCIDToNetworkItemHashTable@@$$CBVIDToNetworkItemRecord@@PEBGVCLKRHashTable@LKRhash@@@LKRhash@@CA_N_K0@Z; LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,ushort const *,LKRhash::CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x180004cf4  mov     [rsp+78h+var_58], rax; bool (*)(unsigned __int64, unsigned __int64)
0x180004cf9  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VCIDToNetworkItemHashTable@@$$CBVIDToNetworkItemRecord@@PEBGVCLKRHashTable@LKRhash@@@LKRhash@@CAK_K@Z; unsigned int (*)(unsigned __int64)
0x180004d00  lea     r8, ?_ExtractKey@?$CTypedHashTable@VCIDToNetworkItemHashTable@@$$CBVIDToNetworkItemRecord@@PEBGVCLKRHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; unsigned __int64 (*)(const void *)
0x180004d07  lea     rdx, aFiidToNetworki; "FIID To NetworkItem"
0x180004d0e  mov     rcx, rbx; this
0x180004d11  call    ??0CLKRHashTable@LKRhash@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N7PEAVCLKRhashAllocator@@@Z; LKRhash::CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool,bool,CLKRhashAllocator *)
0x180004d16  jmp     short loc_180004D1A
0x180004d18  xor     ebx, ebx
0x180004d1a  mov     [rdi+50h], rbx
0x180004d1e  mov     rbx, [rdi+58h]
0x180004d22  test    rbx, rbx
0x180004d25  jnz     short loc_180004D82
0x180004d27  lea     ecx, [rbx+50h]; unsigned __int64
0x180004d2a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004d2f  mov     rbx, rax
0x180004d32  mov     [rsp+78h+arg_0], rax
0x180004d3a  test    rax, rax
0x180004d3d  jz      short loc_180004D7C
0x180004d3f  movsd   [rsp+78h+var_48], xmm6; double
0x180004d45  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VCIDToNetworkItemHashTable@@$$CBVIDToNetworkItemRecord@@PEBGVCLKRHashTable@LKRhash@@@LKRhash@@CAXPEBXH@Z; LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,ushort const *,LKRhash::CLKRHashTable>::_AddRefRecord(void const *,int)
0x180004d4c  mov     [rsp+78h+var_50], rax; void (*)(const void *, int)
0x180004d51  lea     rax, ?_EqualKeys@?$CTypedHashTable@VCNameToNetworkItemHashTable@@$$CBVIDToNetworkItemRecord@@PEBGVCLKRHashTable@LKRhash@@@LKRhash@@CA_N_K0@Z; LKRhash::CTypedHashTable<CNameToNetworkItemHashTable,IDToNetworkItemRecord const,ushort const *,LKRhash::CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x180004d58  mov     [rsp+78h+var_58], rax; bool (*)(unsigned __int64, unsigned __int64)
0x180004d5d  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VCNameToNetworkItemHashTable@@$$CBVIDToNetworkItemRecord@@PEBGVCLKRHashTable@LKRhash@@@LKRhash@@CAK_K@Z; unsigned int (*)(unsigned __int64)
0x180004d64  lea     r8, ?_ExtractKey@?$CTypedHashTable@VCIDToNetworkItemHashTable@@$$CBVIDToNetworkItemRecord@@PEBGVCLKRHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; unsigned __int64 (*)(const void *)
0x180004d6b  lea     rdx, aNameToNetworki; "Name To NetworkItem"
0x180004d72  mov     rcx, rbx; this
0x180004d75  call    ??0CLKRHashTable@LKRhash@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N7PEAVCLKRhashAllocator@@@Z; LKRhash::CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool,bool,CLKRhashAllocator *)
0x180004d7a  jmp     short loc_180004D7E
0x180004d7c  xor     ebx, ebx
0x180004d7e  mov     [rdi+58h], rbx
0x180004d82  cmp     qword ptr [rdi+50h], 0
0x180004d87  jz      short loc_180004D92
0x180004d89  test    rbx, rbx
0x180004d8c  jz      short loc_180004D92
0x180004d8e  xor     eax, eax
0x180004d90  jmp     short loc_180004D97
0x180004d92  mov     eax, 8007000Eh
0x180004d97  mov     rbx, [rsp+78h+arg_8]
0x180004d9f  movaps  xmm6, [rsp+78h+var_18]
0x180004da4  add     rsp, 70h
0x180004da8  pop     rdi
0x180004da9  retn
```
