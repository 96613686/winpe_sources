# RefCountMap<tagSAFEARRAY *>::Increment(tagSAFEARRAY *)

- ea: `0x180099108`
- end: `0x1800991e2`
- name: `?Increment@?$RefCountMap@PEAUtagSAFEARRAY@@@@QEAAJPEAUtagSAFEARRAY@@@Z`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180076ac0`

## callees

- `0x18000da6c`
- `0x180023858`
- `0x180025dbc`
- `0x18003e5e0`
- `0x180043bb4`
- `0x180047e10`
- `0x18009901c`
- `0x180099108`
- `0x1800992c8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180099180`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180099180`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RefCountMap<tagSAFEARRAY *>::Increment(__int64 a1, __int64 a2)
{
  bool v2; // al
  bool v3; // r8
  void *v4; // rax
  __int64 v5; // rbx
  __int64 result; // rax
  __int64 v7; // rax
  _BYTE v8[16]; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v9[24]; // [rsp+30h] [rbp-18h] BYREF
  LPINIT_ONCE lpInitOnce; // [rsp+50h] [rbp+8h] BYREF
  __int64 v11; // [rsp+58h] [rbp+10h] BYREF
  void *v12; // [rsp+60h] [rbp+18h]

  v11 = a2;
  lpInitOnce = 0;
  v2 = InitOnceHolder::BeginInitialize((InitOnceHolder *)&lpInitOnce, &stru_1800C33A0);
  try
  {
    if ( v2 )
    {
      v4 = operator new(0x10u);
      v5 = (__int64)v4;
      v12 = v4;
      if ( v4 )
      {
        std::_Compressed_pair<std::less<unsigned short *>,std::_Compressed_pair<throwingAllocator<std::_Tree_node<std::pair<unsigned short * const,int>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short * const,int>>>,1>,1>::_Compressed_pair<std::less<unsigned short *>,std::_Compressed_pair<throwingAllocator<std::_Tree_node<std::pair<unsigned short * const,int>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short * const,int>>>,1>,1>(v4);
        std::_Tree<std::_Tmap_traits<unsigned short *,int,std::less<unsigned short *>,throwingAllocator<std::pair<unsigned short * const,int>>,0>>::_Alloc_sentinel_and_proxy();
      }
      qword_1800C3398 = v5;
      if ( !v5 )
      {
        InitOnceHolder::~InitOnceHolder((InitOnceHolder *)&lpInitOnce);
        return 2147942414LL;
      }
      InitOnceComplete(lpInitOnce, 0, 0);
      lpInitOnce = 0;
    }
    ATL::CCritSecLock::CCritSecLock(
      (ATL::CCritSecLock *)v8,
      (struct _RTL_CRITICAL_SECTION *)SafeArrayDescriptorRefCounts,
      v3);
    v7 = std::map<tagSAFEARRAY *,int,std::less<tagSAFEARRAY *>,throwingAllocator<std::pair<tagSAFEARRAY * const,int>>>::_Try_emplace<tagSAFEARRAY * const &,>(
           qword_1800C3398,
           v9,
           &v11);
    ++*(_DWORD *)(*(_QWORD *)v7 + 40LL);
    ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v8);
    InitOnceHolder::~InitOnceHolder((InitOnceHolder *)&lpInitOnce);
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180099108  mov     rax, rsp
0x18009910b  mov     [rax+10h], rdx
0x18009910f  mov     [rax+8], rcx
0x180099113  push    rbx
0x180099114  sub     rsp, 40h
0x180099118  mov     qword ptr [rax+8], 0
0x180099120  lea     rdx, stru_1800C33A0; union _RTL_RUN_ONCE *
0x180099127  lea     rcx, [rax+8]; this
0x18009912b  call    ?BeginInitialize@InitOnceHolder@@QEAA_NPEAT_RTL_RUN_ONCE@@@Z; InitOnceHolder::BeginInitialize(_RTL_RUN_ONCE *)
0x180099130  test    al, al
0x180099132  jz      short loc_18009918F
0x180099134  mov     ecx, 10h; unsigned __int64
0x180099139  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009913e  mov     rbx, rax
0x180099141  mov     [rsp+48h+arg_10], rax
0x180099146  test    rbx, rbx
0x180099149  jz      short loc_180099159
0x18009914b  mov     rcx, rax
0x18009914e  call    ??$?0AEBU?$less@PEAG@std@@U_Zero_then_variadic_args_t@1@@?$_Compressed_pair@U?$less@PEAG@std@@V?$_Compressed_pair@V?$throwingAllocator@U?$_Tree_node@U?$pair@QEAGH@std@@PEAX@std@@@@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAGH@std@@@std@@@std@@$00@2@$00@std@@QEAA@U_One_then_variadic_args_t@1@AEBU?$less@PEAG@1@$$QEAU_Zero_then_variadic_args_t@1@@Z; std::_Compressed_pair<std::less<ushort *>,std::_Compressed_pair<throwingAllocator<std::_Tree_node<std::pair<ushort * const,int>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<ushort * const,int>>>,1>,1>::_Compressed_pair<std::less<ushort *>,std::_Compressed_pair<throwingAllocator<std::_Tree_node<std::pair<ushort * const,int>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<ushort * const,int>>>,1>,1>(std::_One_then_variadic_args_t,std::less<ushort *> const &,std::_Zero_then_variadic_args_t &&)
0x180099153  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@PEAGHU?$less@PEAG@std@@V?$throwingAllocator@U?$pair@QEAGH@std@@@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<ushort *,int,std::less<ushort *>,throwingAllocator<std::pair<ushort * const,int>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180099158  nop
0x180099159  mov     cs:qword_1800C3398, rbx
0x180099160  test    rbx, rbx
0x180099163  jnz     short loc_180099176
0x180099165  lea     rcx, [rsp+48h+lpInitOnce]; this
0x18009916a  call    ??1InitOnceHolder@@QEAA@XZ; InitOnceHolder::~InitOnceHolder(void)
0x18009916f  mov     eax, 8007000Eh
0x180099174  jmp     short loc_1800991DB
0x180099176  xor     r8d, r8d; lpContext
0x180099179  xor     edx, edx; dwFlags
0x18009917b  mov     rcx, [rsp+48h+lpInitOnce]; lpInitOnce
0x180099180  call    cs:__imp_InitOnceComplete
0x180099186  mov     [rsp+48h+lpInitOnce], 0
0x18009918f  lea     rdx, ?SafeArrayDescriptorRefCounts@@3V?$RefCountMap@PEAUtagSAFEARRAY@@@@A; struct _RTL_CRITICAL_SECTION *
0x180099196  lea     rcx, [rsp+48h+var_28]; this
0x18009919b  call    ??0CCritSecLock@ATL@@QEAA@AEAU_RTL_CRITICAL_SECTION@@_N@Z; ATL::CCritSecLock::CCritSecLock(_RTL_CRITICAL_SECTION &,bool)
0x1800991a0  nop
0x1800991a1  lea     r8, [rsp+48h+arg_8]
0x1800991a6  lea     rdx, [rsp+48h+var_18]
0x1800991ab  mov     rcx, cs:qword_1800C3398
0x1800991b2  call    ??$_Try_emplace@AEBQEAUtagSAFEARRAY@@$$V@?$map@PEAUtagSAFEARRAY@@HU?$less@PEAUtagSAFEARRAY@@@std@@V?$throwingAllocator@U?$pair@QEAUtagSAFEARRAY@@H@std@@@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAUtagSAFEARRAY@@H@std@@PEAX@std@@_N@1@AEBQEAUtagSAFEARRAY@@@Z; std::map<tagSAFEARRAY *,int,std::less<tagSAFEARRAY *>,throwingAllocator<std::pair<tagSAFEARRAY * const,int>>>::_Try_emplace<tagSAFEARRAY * const &,>(tagSAFEARRAY * const &)
0x1800991b7  mov     rax, [rax]
0x1800991ba  inc     dword ptr [rax+28h]
0x1800991bd  lea     rcx, [rsp+48h+var_28]; this
0x1800991c2  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x1800991c7  nop
0x1800991c8  lea     rcx, [rsp+48h+lpInitOnce]; this
0x1800991cd  call    ??1InitOnceHolder@@QEAA@XZ; InitOnceHolder::~InitOnceHolder(void)
0x1800991d2  xor     eax, eax
0x1800991d4  jmp     short loc_1800991DB
0x1800991d6  mov     eax, 8007000Eh
0x1800991db  add     rsp, 40h
0x1800991df  pop     rbx
0x1800991e0  retn
```
