# MemoryManager::CreateSectionBackedGpaRange(_VID_SECTION_VIEW *,uchar,unsigned __int64,unsigned __int64,void * *,void * *,void * *)

- ea: `0x1400d6150`
- end: `0x1400d65af`
- name: `?CreateSectionBackedGpaRange@MemoryManager@@UEAAJPEAU_VID_SECTION_VIEW@@E_K1PEAPEAX22@Z`
- size: `1119`
- prototype: `__int64 __fastcall(struct IVidPartitionManager **this, struct _VID_SECTION_VIEW *, char, __int64, unsigned __int64, void **, void **, void **)`
- caller_count: `0`
- callee_count: `26`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400222f8`
- `0x14002c730`
- `0x14003179c`
- `0x140031808`
- `0x140031c88`
- `0x140033a04`
- `0x14003f2b4`
- `0x14003fae4`
- `0x140040fd8`
- `0x140041a3c`
- `0x140042240`
- `0x14004babc`
- `0x14004bea4`
- `0x14004e028`
- `0x1400505e4`
- `0x140052db0`
- `0x140054af0`
- `0x1400558ac`
- `0x14005b628`
- `0x14009d7ac`
- `0x1400d6150`
- `0x1400d65b8`
- `0x140132940`
- `0x1401335fc`
- `0x1402134e8`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d6516`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d6516`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400d61ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400d61ce`
- `vid!VidCreateVaGpaRange` at `0x1400d63d0`
- `vid!VidCreateVaGpaRange` at `0x1400d63d0`

## string_xrefs

- `0x1400d64e6`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x1400d6221`: `CreateSectionBackedGpaRange`
- `0x1400d6535`: `Failed to create section. HR=%d.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall MemoryManager::CreateSectionBackedGpaRange(
        struct IVidPartitionManager **this,
        struct _VID_SECTION_VIEW *a2,
        char a3,
        __int64 a4,
        unsigned __int64 a5,
        void **a6,
        void **a7,
        void **a8)
{
  volatile signed __int32 *v11; // rbx
  DWORD CurrentThreadId; // esi
  __int64 v13; // r8
  unsigned __int32 v14; // eax
  unsigned __int32 v15; // edx
  MemoryBlock *MemoryBlock; // rsi
  void *v17; // r14
  const char *v18; // r9
  double v19; // xmm0_8
  void *v20; // rcx
  unsigned int v22; // [rsp+20h] [rbp-368h]
  __int64 v24; // [rsp+44h] [rbp-344h] BYREF
  struct MemoryBlock *v25; // [rsp+50h] [rbp-338h]
  MemoryManager *v26; // [rsp+58h] [rbp-330h]
  _QWORD v27[2]; // [rsp+60h] [rbp-328h] BYREF
  void **v28; // [rsp+70h] [rbp-318h]
  __int128 v29; // [rsp+80h] [rbp-308h] BYREF
  volatile signed __int32 *v30; // [rsp+90h] [rbp-2F8h]
  char *v31[4]; // [rsp+98h] [rbp-2F0h] BYREF
  void *v32; // [rsp+B8h] [rbp-2D0h] BYREF
  _QWORD v33[8]; // [rsp+C0h] [rbp-2C8h] BYREF
  char v34; // [rsp+101h] [rbp-287h]
  __int64 v35; // [rsp+110h] [rbp-278h]
  __int128 v36; // [rsp+118h] [rbp-270h]
  __int64 v37; // [rsp+128h] [rbp-260h]
  __int64 v38; // [rsp+130h] [rbp-258h]
  RTL_SRWLOCK v39[10]; // [rsp+140h] [rbp-248h] BYREF
  struct _GUID v40; // [rsp+190h] [rbp-1F8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+0h]

  v26 = (MemoryManager *)this;
  v38 = a4;
  v28 = a7;
  v27[0] = a8;
  v25 = 0;
  v32 = (void *)-1LL;
  v11 = (volatile signed __int32 *)(this + 88);
  CurrentThreadId = GetCurrentThreadId();
  v14 = _InterlockedCompareExchange(v11, 1, 0);
  if ( v14 )
  {
    if ( *((_DWORD *)v11 + 1) == CurrentThreadId )
    {
      _InterlockedAdd(v11 + 2, 1u);
      goto LABEL_8;
    }
    do
    {
      while ( (v14 & 1) != 0 || v14 >= 4 )
      {
        LOBYTE(v13) = 1;
        if ( !(unsigned int)RrwpLockWait(v11, 0xFFFFFFFFLL, v13) )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x2FE,
            (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
            (const char *)0x102,
            v22);
        _m_prefetchw((const void *)v11);
        v14 = *v11;
      }
      v15 = v14;
      v14 = _InterlockedCompareExchange(v11, v14 + 1, v14);
    }
    while ( v14 != v15 );
  }
  _InterlockedExchange(v11 + 1, CurrentThreadId);
LABEL_8:
  v30 = v11;
  std::wstring::wstring(v31, L"CreateSectionBackedGpaRange");
  v29 = *(_OWORD *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this[4] + 2) + 16LL))((char *)this[4] + 16);
  MemoryTraceTracker::MemoryTraceTracker((__int64)v39, &v29, (__int64)v31, 0);
  std::wstring::_Tidy_deallocate(v31);
  memset_0(v33, 0, 0x70u);
  v33[0] = a5;
  v33[1] = a5;
  v33[2] = 8;
  v34 = a3;
  v36 = *(_OWORD *)a2;
  v37 = *((_QWORD *)a2 + 2);
  if ( a6 )
    v35 = (__int64)*a6;
  MemoryBlock = MemoryBlock::CreateMemoryBlock((__int64)this[2], v33, 0, 0, 0, 0, v39);
  v25 = MemoryBlock;
  v17 = (void *)*((_QWORD *)MemoryBlock + 19);
  MemoryBlock::NotificationHandlerRegister(MemoryBlock, this[3], (struct MemoryNotificationsCallback *)(this + 9));
  memset_0(&v40, 0, 0x1B0u);
  MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>(
    (__int64)&v40,
    (__int64)v39);
  v24 = 0;
  MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::Start<int,unsigned __int64 &,unsigned __int64 &,int>(
    &v40,
    (__int64)&v24);
  if ( !(unsigned int)VidCreateVaGpaRange(this[2], a4, a5, v17, 0, &v32) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1F58,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      v18);
  v19 = MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::Stop(&v40);
  MemoryTraceTracker::IncreaseTimeSpentInOperation(v39, (__int64)&off_1402C5B20, v19);
  MemoryTraceTracker::Complete((MemoryTraceTracker *)v39);
  MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::~MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>(&v40);
  MemoryTraceTracker::~MemoryTraceTracker((MemoryTraceTracker *)v39);
  (*(void (__fastcall **)(struct IVidPartitionManager *))(*(_QWORD *)this[3] + 216LL))(this[3]);
  MemoryBlockContainer::Insert(this[20], MemoryBlock);
  *v28 = v17;
  v20 = v32;
  *(_QWORD *)v27[0] = v32;
  if ( a6 )
    *a6 = (void *)*((_QWORD *)MemoryBlock + 30);
  v27[0] = a4;
  v27[1] = v20;
  std::_Tree<std::_Tmap_traits<unsigned __int64,void *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,void *>>,0>>::_Emplace<std::pair<unsigned __int64,void *>>(
    this + 94,
    &v29,
    v27);
  RrwLockRelease(v11);
  return 0;
}

```

## disassembly

```asm
0x1400d6150  push    rbx
0x1400d6152  push    rsi
0x1400d6153  push    rdi
0x1400d6154  push    r12
0x1400d6156  push    r13
0x1400d6158  push    r14
0x1400d615a  push    r15
0x1400d615c  sub     rsp, 350h
0x1400d6163  mov     rax, cs:__security_cookie
0x1400d616a  xor     rax, rsp
0x1400d616d  mov     [rsp+388h+var_48], rax
0x1400d6175  mov     r13, r9
0x1400d6178  mov     [rsp+388h+var_348], r8b
0x1400d617d  mov     r14, rdx
0x1400d6180  mov     rdi, rcx
0x1400d6183  mov     [rsp+388h+var_330], rcx
0x1400d6188  mov     [rsp+388h+var_258], r9
0x1400d6190  mov     r15, [rsp+388h+arg_28]
0x1400d6198  mov     rax, [rsp+388h+arg_30]
0x1400d61a0  mov     [rsp+388h+var_318], rax
0x1400d61a5  mov     rax, [rsp+388h+arg_38]
0x1400d61ad  mov     [rsp+388h+var_328], rax
0x1400d61b2  mov     [rsp+388h+var_338], 0
0x1400d61bb  mov     [rsp+388h+var_2D0], 0FFFFFFFFFFFFFFFFh
0x1400d61c7  lea     rbx, [rcx+2C0h]
0x1400d61ce  call    cs:__imp_GetCurrentThreadId
0x1400d61d5  nop     dword ptr [rax+rax+00h]
0x1400d61da  mov     esi, eax
0x1400d61dc  xor     eax, eax
0x1400d61de  lea     r12d, [rax+1]
0x1400d61e2  lock cmpxchg [rbx], r12d
0x1400d61e7  jz      short loc_1400D6216
0x1400d61e9  mov     ecx, [rbx+4]
0x1400d61ec  cmp     ecx, esi
0x1400d61ee  jnz     short loc_1400D61F7
0x1400d61f0  lock add [rbx+8], r12d
0x1400d61f5  jmp     short loc_1400D6219
0x1400d61f7  test    r12b, al
0x1400d61fa  jnz     loc_1400D64C2
0x1400d6200  cmp     eax, 4
0x1400d6203  jnb     loc_1400D64C2
0x1400d6209  mov     edx, eax
0x1400d620b  lea     ecx, [rax+1]
0x1400d620e  lock cmpxchg [rbx], ecx
0x1400d6212  cmp     eax, edx
0x1400d6214  jnz     short loc_1400D61F7
0x1400d6216  xchg    esi, [rbx+4]
0x1400d6219  mov     [rsp+388h+var_2F8], rbx
0x1400d6221  lea     rdx, aCreatesectionb; "CreateSectionBackedGpaRange"
0x1400d6228  lea     rcx, [rsp+388h+var_2F0]
0x1400d6230  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400d6235  nop
0x1400d6236  mov     rcx, [rdi+20h]
0x1400d623a  add     rcx, 10h
0x1400d623e  mov     rax, [rcx]
0x1400d6241  mov     rax, [rax+10h]
0x1400d6245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400d624a  movups  xmm0, xmmword ptr [rax]
0x1400d624d  movdqu  [rsp+388h+var_308], xmm0
0x1400d6256  xor     r9d, r9d
0x1400d6259  lea     r8, [rsp+388h+var_2F0]
0x1400d6261  lea     rdx, [rsp+388h+var_308]
0x1400d6269  lea     rcx, [rsp+388h+var_248]
0x1400d6271  call    ??0MemoryTraceTracker@@QEAA@U_GUID@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU1@@Z; MemoryTraceTracker::MemoryTraceTracker(_GUID,std::wstring &&,_GUID const *)
0x1400d6276  nop
0x1400d6277  lea     rcx, [rsp+388h+var_2F0]
0x1400d627f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400d6284  xor     edx, edx; Val
0x1400d6286  lea     r8d, [rdx+70h]; Size
0x1400d628a  lea     rcx, [rsp+388h+var_2C8]; void *
0x1400d6292  call    memset_0
0x1400d6297  mov     r12, [rsp+388h+arg_20]
0x1400d629f  mov     [rsp+388h+var_2C8], r12
0x1400d62a7  mov     [rsp+388h+var_2C0], r12
0x1400d62af  mov     [rsp+388h+var_2B8], 8
0x1400d62bb  mov     al, [rsp+388h+var_348]
0x1400d62bf  mov     [rsp+388h+var_287], al
0x1400d62c6  movups  xmm0, xmmword ptr [r14]
0x1400d62ca  movups  [rsp+388h+var_270], xmm0
0x1400d62d2  movsd   xmm1, qword ptr [r14+10h]
0x1400d62d8  movsd   [rsp+388h+var_260], xmm1
0x1400d62e1  test    r15, r15
0x1400d62e4  jz      short loc_1400D62F1
0x1400d62e6  mov     rax, [r15]
0x1400d62e9  mov     [rsp+388h+var_278], rax
0x1400d62f1  lea     rax, [rsp+388h+var_248]
0x1400d62f9  mov     [rsp+388h+var_358], rax
0x1400d62fe  mov     [rsp+388h+var_360], 0
0x1400d6307  mov     [rsp+388h+var_368], 0
0x1400d6310  xor     r9d, r9d
0x1400d6313  xor     r8d, r8d
0x1400d6316  lea     rdx, [rsp+388h+var_2C8]
0x1400d631e  mov     rcx, [rdi+10h]
0x1400d6322  call    ?CreateMemoryBlock@MemoryBlock@@KAPEAV1@PEAXPEAU_VID_MEMORY_BLOCK_CONFIG@@T_ADDITIONAL_MB_ATTRIBUTES@1@_KPEAVPoisonedPageContainer@@PEAU_VID_FILE_MAPPING@@AEAUMemoryTraceTracker@@@Z; MemoryBlock::CreateMemoryBlock(void *,_VID_MEMORY_BLOCK_CONFIG *,MemoryBlock::_ADDITIONAL_MB_ATTRIBUTES,unsigned __int64,PoisonedPageContainer *,_VID_FILE_MAPPING *,MemoryTraceTracker &)
0x1400d6327  mov     rsi, rax
0x1400d632a  mov     [rsp+388h+var_338], rax
0x1400d632f  mov     r14, [rax+98h]
0x1400d6336  lea     r8, [rdi+48h]; struct MemoryNotificationsCallback *
0x1400d633a  mov     rdx, [rdi+18h]; struct IVidPartitionManager *
0x1400d633e  mov     rcx, rax; this
0x1400d6341  call    ?NotificationHandlerRegister@MemoryBlock@@IEAAXPEAUIVidPartitionManager@@AEAVMemoryNotificationsCallback@@@Z; MemoryBlock::NotificationHandlerRegister(IVidPartitionManager *,MemoryNotificationsCallback &)
0x1400d6346  xor     edx, edx; Val
0x1400d6348  mov     r8d, 1B0h; Size
0x1400d634e  lea     rcx, [rsp+388h+var_1F8]; void *
0x1400d6356  call    memset_0
0x1400d635b  lea     rdx, [rsp+388h+var_248]
0x1400d6363  lea     rcx, [rsp+388h+var_1F8]
0x1400d636b  call    ??0?$MemoryTrace@VGpaMapRamMemoryBlock@VmWorkerTrace@@@@QEAA@AEBUMemoryTraceTracker@@@Z; MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>(MemoryTraceTracker const &)
0x1400d6370  nop
0x1400d6371  mov     dword ptr [rsp+388h+var_344], 0
0x1400d6379  mov     dword ptr [rsp+388h+var_344+4], 0
0x1400d6381  lea     rax, [rsp+388h+var_344]
0x1400d6386  mov     [rsp+388h+var_368], rax; __int64
0x1400d638b  lea     r9, [rsp+388h+arg_20]
0x1400d6393  lea     r8, [rsp+388h+var_258]
0x1400d639b  lea     rdx, [rsp+388h+var_344+4]
0x1400d63a0  lea     rcx, [rsp+388h+var_1F8]; struct _GUID *
0x1400d63a8  call    ??$Start@HAEA_KAEA_KH@?$MemoryTrace@VGpaMapRamMemoryBlock@VmWorkerTrace@@@@QEAAX$$QEAHAEA_K10@Z; MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::Start<int,unsigned __int64 &,unsigned __int64 &,int>(int &&,unsigned __int64 &,unsigned __int64 &,int &&)
0x1400d63ad  lea     rax, [rsp+388h+var_2D0]
0x1400d63b5  mov     [rsp+388h+var_360], rax
0x1400d63ba  mov     [rsp+388h+var_368], 0
0x1400d63c3  mov     r9, r14
0x1400d63c6  mov     r8, r12
0x1400d63c9  mov     rdx, r13
0x1400d63cc  mov     rcx, [rdi+10h]
0x1400d63d0  call    cs:__imp_VidCreateVaGpaRange
0x1400d63d7  nop     dword ptr [rax+rax+00h]
0x1400d63dc  mov     rcx, [rsp+388h]; this
0x1400d63e4  test    eax, eax
0x1400d63e6  jnz     short loc_1400D63F9
0x1400d63e8  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400d63ef  mov     edx, 1F58h; void *
0x1400d63f4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400d63f9  lea     rcx, [rsp+388h+var_1F8]
0x1400d6401  call    ?Stop@?$MemoryTrace@VGpaMapRamMemoryBlock@VmWorkerTrace@@@@QEAANXZ; MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::Stop(void)
0x1400d6406  movaps  xmm2, xmm0
0x1400d6409  lea     rdx, off_1402C5B20; "GpaMappingRamMemoryBlocks"
0x1400d6410  lea     rcx, [rsp+388h+var_248]
0x1400d6418  call    ?IncreaseTimeSpentInOperation@MemoryTraceTracker@@QEAAXAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@N@Z; MemoryTraceTracker::IncreaseTimeSpentInOperation(std::basic_string_view<ushort> const &,double)
0x1400d641d  lea     rcx, [rsp+388h+var_248]; this
0x1400d6425  call    ?Complete@MemoryTraceTracker@@QEAA_KXZ; MemoryTraceTracker::Complete(void)
0x1400d642a  nop
0x1400d642b  lea     rcx, [rsp+388h+var_1F8]
0x1400d6433  call    ??1?$MemoryTrace@VGpaMapRamMemoryBlock@VmWorkerTrace@@@@QEAA@XZ; MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::~MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>(void)
0x1400d6438  nop
0x1400d6439  lea     rcx, [rsp+388h+var_248]; this
0x1400d6441  call    ??1MemoryTraceTracker@@QEAA@XZ; MemoryTraceTracker::~MemoryTraceTracker(void)
0x1400d6446  mov     rcx, [rdi+18h]
0x1400d644a  mov     rax, [rcx]
0x1400d644d  mov     rax, [rax+0D8h]
0x1400d6454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400d6459  mov     rdx, rsi; struct MemoryBlock *
0x1400d645c  mov     rcx, [rdi+0A0h]; this
0x1400d6463  call    ?Insert@MemoryBlockContainer@@QEAAXPEAVMemoryBlock@@@Z; MemoryBlockContainer::Insert(MemoryBlock *)
0x1400d6468  mov     rax, [rsp+388h+var_318]
0x1400d646d  mov     [rax], r14
0x1400d6470  mov     rcx, [rsp+388h+var_2D0]
0x1400d6478  mov     rax, [rsp+388h+var_328]
0x1400d647d  mov     [rax], rcx
0x1400d6480  test    r15, r15
0x1400d6483  jz      short loc_1400D648F
0x1400d6485  mov     rax, [rsi+0F0h]
0x1400d648c  mov     [r15], rax
0x1400d648f  mov     [rsp+388h+var_328], r13
0x1400d6494  mov     [rsp+388h+var_320], rcx
0x1400d6499  lea     rcx, [rdi+2F0h]
0x1400d64a0  lea     r8, [rsp+388h+var_328]
0x1400d64a5  lea     rdx, [rsp+388h+var_308]
0x1400d64ad  call    ??$_Emplace@U?$pair@_KPEAX@std@@@?$_Tree@V?$_Tmap_traits@_KPEAXU?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAX@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KPEAX@std@@PEAX@std@@_N@1@$$QEAU?$pair@_KPEAX@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,void *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,void *>>,0>>::_Emplace<std::pair<unsigned __int64,void *>>(std::pair<unsigned __int64,void *> &&)
0x1400d64b2  nop
0x1400d64b3  mov     rcx, rbx
0x1400d64b6  call    RrwLockRelease
0x1400d64bb  xor     eax, eax
0x1400d64bd  jmp     loc_1400D657F
0x1400d64c2  mov     r8b, r12b
0x1400d64c5  or      edx, 0FFFFFFFFh
0x1400d64c8  mov     rcx, rbx
0x1400d64cb  call    RrwpLockWait
0x1400d64d0  test    eax, eax
0x1400d64d2  jnz     loc_1400D65A3
0x1400d64d8  mov     rcx, [rsp+388h]; this
0x1400d64e0  mov     r9d, 102h; char *
0x1400d64e6  lea     r8, aOnecoreVmCommo_24; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x1400d64ed  mov     edx, 2FEh; void *
0x1400d64f2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400d64f8  mov     ebx, dword ptr [rsp+388h+var_344]
0x1400d64fc  test    ebx, ebx
0x1400d64fe  jns     short loc_1400D657D
0x1400d6500  lea     eax, [rbx+3FC8FFD5h]
0x1400d6506  cmp     eax, 2
0x1400d6509  ja      short loc_1400D6522
0x1400d650b  mov     ebx, 5AAh
0x1400d6510  mov     dword ptr [rsp+388h+var_344], ebx
0x1400d6514  mov     ecx, ebx; dwErrCode
0x1400d6516  call    cs:__imp_SetLastError
0x1400d651d  nop     dword ptr [rax+rax+00h]
0x1400d6522  mov     edi, 4020h
0x1400d6527  mov     ecx, edi
0x1400d6529  call    VmlIsDebugTraceEnabled
0x1400d652e  test    eax, eax
0x1400d6530  jz      short loc_1400D6543
0x1400d6532  mov     r8d, ebx
0x1400d6535  lea     rdx, aFailedToCreate_10; "Failed to create section. HR=%d.\n"
0x1400d653c  mov     ecx, edi
0x1400d653e  call    VmlDebugTrace
0x1400d6543  mov     rdx, [rsp+388h+var_2D0]; void *
0x1400d654b  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1400d654f  jz      short loc_1400D6562
0x1400d6551  mov     rcx, [rsp+388h+var_330]; this
0x1400d6556  call    ?DestroyGpaRange@MemoryManager@@AEAAXPEAX@Z; MemoryManager::DestroyGpaRange(void *)
0x1400d655b  nop
0x1400d655c  jmp     short loc_1400D6562
0x1400d655e  mov     ebx, dword ptr [rsp+388h+var_344]
0x1400d6562  mov     rdx, [rsp+388h+var_338]; struct MemoryBlock *
0x1400d6567  test    rdx, rdx
0x1400d656a  jz      short loc_1400D657D
0x1400d656c  mov     rcx, [rsp+388h+var_330]; this
0x1400d6571  call    ?DestroyMemoryBlockInternal@MemoryManager@@AEAAXPEAVMemoryBlock@@@Z; MemoryManager::DestroyMemoryBlockInternal(MemoryBlock *)
0x1400d6576  nop
0x1400d6577  jmp     short loc_1400D657D
0x1400d6579  mov     ebx, dword ptr [rsp+388h+var_344]
0x1400d657d  mov     eax, ebx
0x1400d657f  mov     rcx, [rsp+388h+var_48]
0x1400d6587  xor     rcx, rsp; StackCookie
0x1400d658a  call    __security_check_cookie
0x1400d658f  add     rsp, 350h
0x1400d6596  pop     r15
0x1400d6598  pop     r14
0x1400d659a  pop     r13
0x1400d659c  pop     r12
0x1400d659e  pop     rdi
0x1400d659f  pop     rsi
0x1400d65a0  pop     rbx
0x1400d65a1  retn
0x1400d65a3  prefetchw byte ptr [rbx]
0x1400d65a6  mov     eax, [rbx]
0x1400d65a8  jmp     loc_1400D61F7
```
