# CommonFileMapping::~CommonFileMapping(void)

- ea: `0x180020d5c`
- end: `0x180020e07`
- name: `??1CommonFileMapping@@QEAA@XZ`
- size: `171`
- prototype: `void __fastcall(void **this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001f868`
- `0x18001f8d0`
- `0x18001fae0`

## callees

- `0x180020d5c`
- `0x1800211a0`
- `0x18002164c`
- `0x180024010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180020de1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180020de1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020dd1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020dd1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020d70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020d70`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CommonFileMapping::~CommonFileMapping(void **this)
{
  __int64 v2; // rcx
  __int64 *v3; // rax
  __int64 v4; // rbx
  void (__fastcall ***v6)(_QWORD, __int64); // rcx
  char v7; // [rsp+30h] [rbp+8h] BYREF
  char v8; // [rsp+38h] [rbp+10h] BYREF

  EnterCriticalSection(&g_SyncLock);
  v3 = (__int64 *)std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>,0>>::find(
                    v2,
                    &v8,
                    this);
  v4 = *v3;
  if ( *v3 != CommonFileMapping::m_mapSingleton && (*(_DWORD *)(v4 + 80))-- == 1 )
  {
    v6 = *(void (__fastcall ****)(_QWORD, __int64))(v4 + 72);
    if ( v6 )
      (**v6)(v6, 1);
    *(_QWORD *)(v4 + 72) = 0;
    std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>,0>>::erase(
      &CommonFileMapping::m_mapSingleton,
      &v7,
      v4);
  }
  LeaveCriticalSection(&g_SyncLock);
  if ( (unsigned __int64)this[3] >= 8 )
    operator delete(*this);
  this[3] = (void *)7;
  this[2] = 0;
  *(_WORD *)this = 0;
}

```

## disassembly

```asm
0x180020d5c  mov     [rsp+arg_10], rbx
0x180020d61  push    rdi
0x180020d62  sub     rsp, 20h
0x180020d66  mov     rdi, rcx
0x180020d69  lea     rcx, ?g_SyncLock@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; lpCriticalSection
0x180020d70  call    cs:__imp_EnterCriticalSection
0x180020d76  mov     r8, rdi
0x180020d79  lea     rdx, [rsp+28h+arg_8]
0x180020d7e  call    ?find@?$_Tree@V?$_Tmap_traits@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@std@@@std@@@2@AEBUtagSFILENAMEwithATTRIBUTE@@@Z; std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>,0>>::find(tagSFILENAMEwithATTRIBUTE const &)
0x180020d83  mov     rbx, [rax]
0x180020d86  cmp     rbx, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x180020d8d  jz      short loc_180020DCA
0x180020d8f  add     dword ptr [rbx+50h], 0FFFFFFFFh
0x180020d93  jnz     short loc_180020DCA
0x180020d95  mov     rcx, [rbx+48h]
0x180020d99  test    rcx, rcx
0x180020d9c  jz      short loc_180020DAE
0x180020d9e  mov     rax, [rcx]
0x180020da1  mov     edx, 1
0x180020da6  mov     rax, [rax]
0x180020da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020dae  mov     qword ptr [rbx+48h], 0
0x180020db6  mov     r8, rbx
0x180020db9  lea     rdx, [rsp+28h+arg_0]
0x180020dbe  lea     rcx, ?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x180020dc5  call    ?erase@?$_Tree@V?$_Tmap_traits@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>>>)
0x180020dca  lea     rcx, ?g_SyncLock@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; lpCriticalSection
0x180020dd1  call    cs:__imp_LeaveCriticalSection
0x180020dd7  cmp     qword ptr [rdi+18h], 8
0x180020ddc  jb      short loc_180020DE7
0x180020dde  mov     rcx, [rdi]
0x180020de1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180020de7  mov     qword ptr [rdi+18h], 7
0x180020def  mov     qword ptr [rdi+10h], 0
0x180020df7  xor     eax, eax
0x180020df9  mov     [rdi], ax
0x180020dfc  mov     rbx, [rsp+28h+arg_10]
0x180020e01  add     rsp, 20h
0x180020e05  pop     rdi
0x180020e06  retn
```
