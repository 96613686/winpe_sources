# RefCountMap<void *>::Increment(void *)

- ea: `0x1800991e8`
- end: `0x1800992c2`
- name: `?Increment@?$RefCountMap@PEAX@@QEAAJPEAX@Z`
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
- `0x1800991e8`
- `0x1800992c8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180099260`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180099260`

## pseudocode

```c
__int64 __fastcall RefCountMap<void *>::Increment(__int64 a1, __int64 a2)
{
  bool v2; // r8
  void *v3; // rax
  __int64 v4; // rbx
  __int64 v6; // rax
  _BYTE v7[16]; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v8[24]; // [rsp+30h] [rbp-18h] BYREF
  LPINIT_ONCE lpInitOnce; // [rsp+50h] [rbp+8h] BYREF
  __int64 v10; // [rsp+58h] [rbp+10h] BYREF
  void *v11; // [rsp+60h] [rbp+18h]

  v10 = a2;
  lpInitOnce = 0;
  if ( InitOnceHolder::BeginInitialize((InitOnceHolder *)&lpInitOnce, &InitOnce) )
  {
    v3 = operator new(0x10u);
    v4 = (__int64)v3;
    v11 = v3;
    if ( v3 )
    {
      std::_Compressed_pair<std::less<unsigned short *>,std::_Compressed_pair<throwingAllocator<std::_Tree_node<std::pair<unsigned short * const,int>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short * const,int>>>,1>,1>::_Compressed_pair<std::less<unsigned short *>,std::_Compressed_pair<throwingAllocator<std::_Tree_node<std::pair<unsigned short * const,int>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short * const,int>>>,1>,1>(v3);
      std::_Tree<std::_Tmap_traits<unsigned short *,int,std::less<unsigned short *>,throwingAllocator<std::pair<unsigned short * const,int>>,0>>::_Alloc_sentinel_and_proxy();
    }
    qword_1800C33D0 = v4;
    if ( !v4 )
    {
      InitOnceHolder::~InitOnceHolder((InitOnceHolder *)&lpInitOnce);
      return 2147942414LL;
    }
    InitOnceComplete(lpInitOnce, 0, 0);
    lpInitOnce = 0;
  }
  ATL::CCritSecLock::CCritSecLock((ATL::CCritSecLock *)v7, (struct _RTL_CRITICAL_SECTION *)SafeArrayDataRefCounts, v2);
  v6 = std::map<tagSAFEARRAY *,int,std::less<tagSAFEARRAY *>,throwingAllocator<std::pair<tagSAFEARRAY * const,int>>>::_Try_emplace<tagSAFEARRAY * const &,>(
         qword_1800C33D0,
         v8,
         &v10);
  ++*(_DWORD *)(*(_QWORD *)v6 + 40LL);
  ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v7);
  InitOnceHolder::~InitOnceHolder((InitOnceHolder *)&lpInitOnce);
  return 0;
}

```

## disassembly

```asm
0x1800991e8  mov     rax, rsp
0x1800991eb  mov     [rax+10h], rdx
0x1800991ef  mov     [rax+8], rcx
0x1800991f3  push    rbx
0x1800991f4  sub     rsp, 40h
0x1800991f8  mov     qword ptr [rax+8], 0
0x180099200  lea     rdx, InitOnce; union _RTL_RUN_ONCE *
0x180099207  lea     rcx, [rax+8]; this
0x18009920b  call    ?BeginInitialize@InitOnceHolder@@QEAA_NPEAT_RTL_RUN_ONCE@@@Z; InitOnceHolder::BeginInitialize(_RTL_RUN_ONCE *)
0x180099210  test    al, al
0x180099212  jz      short loc_18009926F
0x180099214  mov     ecx, 10h; unsigned __int64
0x180099219  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009921e  mov     rbx, rax
0x180099221  mov     [rsp+48h+arg_10], rax
0x180099226  test    rbx, rbx
0x180099229  jz      short loc_180099239
0x18009922b  mov     rcx, rax
0x18009922e  call    ??$?0AEBU?$less@PEAG@std@@U_Zero_then_variadic_args_t@1@@?$_Compressed_pair@U?$less@PEAG@std@@V?$_Compressed_pair@V?$throwingAllocator@U?$_Tree_node@U?$pair@QEAGH@std@@PEAX@std@@@@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAGH@std@@@std@@@std@@$00@2@$00@std@@QEAA@U_One_then_variadic_args_t@1@AEBU?$less@PEAG@1@$$QEAU_Zero_then_variadic_args_t@1@@Z; std::_Compressed_pair<std::less<ushort *>,std::_Compressed_pair<throwingAllocator<std::_Tree_node<std::pair<ushort * const,int>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<ushort * const,int>>>,1>,1>::_Compressed_pair<std::less<ushort *>,std::_Compressed_pair<throwingAllocator<std::_Tree_node<std::pair<ushort * const,int>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<ushort * const,int>>>,1>,1>(std::_One_then_variadic_args_t,std::less<ushort *> const &,std::_Zero_then_variadic_args_t &&)
0x180099233  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@PEAGHU?$less@PEAG@std@@V?$throwingAllocator@U?$pair@QEAGH@std@@@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<ushort *,int,std::less<ushort *>,throwingAllocator<std::pair<ushort * const,int>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180099238  nop
0x180099239  mov     cs:qword_1800C33D0, rbx
0x180099240  test    rbx, rbx
0x180099243  jnz     short loc_180099256
0x180099245  lea     rcx, [rsp+48h+lpInitOnce]; this
0x18009924a  call    ??1InitOnceHolder@@QEAA@XZ; InitOnceHolder::~InitOnceHolder(void)
0x18009924f  mov     eax, 8007000Eh
0x180099254  jmp     short loc_1800992BB
0x180099256  xor     r8d, r8d; lpContext
0x180099259  xor     edx, edx; dwFlags
0x18009925b  mov     rcx, [rsp+48h+lpInitOnce]; lpInitOnce
0x180099260  call    cs:__imp_InitOnceComplete
0x180099266  mov     [rsp+48h+lpInitOnce], 0
0x18009926f  lea     rdx, ?SafeArrayDataRefCounts@@3V?$RefCountMap@PEAX@@A; struct _RTL_CRITICAL_SECTION *
0x180099276  lea     rcx, [rsp+48h+var_28]; this
0x18009927b  call    ??0CCritSecLock@ATL@@QEAA@AEAU_RTL_CRITICAL_SECTION@@_N@Z; ATL::CCritSecLock::CCritSecLock(_RTL_CRITICAL_SECTION &,bool)
0x180099280  nop
0x180099281  lea     r8, [rsp+48h+arg_8]
0x180099286  lea     rdx, [rsp+48h+var_18]
0x18009928b  mov     rcx, cs:qword_1800C33D0
0x180099292  call    ??$_Try_emplace@AEBQEAUtagSAFEARRAY@@$$V@?$map@PEAUtagSAFEARRAY@@HU?$less@PEAUtagSAFEARRAY@@@std@@V?$throwingAllocator@U?$pair@QEAUtagSAFEARRAY@@H@std@@@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAUtagSAFEARRAY@@H@std@@PEAX@std@@_N@1@AEBQEAUtagSAFEARRAY@@@Z; std::map<tagSAFEARRAY *,int,std::less<tagSAFEARRAY *>,throwingAllocator<std::pair<tagSAFEARRAY * const,int>>>::_Try_emplace<tagSAFEARRAY * const &,>(tagSAFEARRAY * const &)
0x180099297  mov     rax, [rax]
0x18009929a  inc     dword ptr [rax+28h]
0x18009929d  lea     rcx, [rsp+48h+var_28]; this
0x1800992a2  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x1800992a7  nop
0x1800992a8  lea     rcx, [rsp+48h+lpInitOnce]; this
0x1800992ad  call    ??1InitOnceHolder@@QEAA@XZ; InitOnceHolder::~InitOnceHolder(void)
0x1800992b2  xor     eax, eax
0x1800992b4  jmp     short loc_1800992BB
0x1800992b6  mov     eax, 8007000Eh
0x1800992bb  add     rsp, 40h
0x1800992bf  pop     rbx
0x1800992c0  retn
```
