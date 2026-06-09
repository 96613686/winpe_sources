# WorkerTaskMigrationTarget::ReceiveGuestMemoryContent(EndpointMessageSequencerCollectionTarget *,std::unordered_map<MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>,std::allocator<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>,std::hash<MuxMigrationReply::ReplyType>,std::equal_to<MuxMigrationReply::ReplyType>,std::allocator<std::pair<MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>,std::allocator<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>>>>,Vml::VmComPtr<IMigrationTransferDependencyGroup>)

- ea: `0x14008ed50`
- end: `0x14008f282`
- name: `?ReceiveGuestMemoryContent@WorkerTaskMigrationTarget@@AEAAJPEAVEndpointMessageSequencerCollectionTarget@@V?$unordered_map@W4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@@2@@std@@U?$hash@W4ReplyType@MuxMigrationReply@@@4@U?$equal_to@W4ReplyType@MuxMigrationReply@@@4@V?$allocator@U?$pair@$$CBW4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@@2@@std@@@std@@@4@@std@@V?$VmComPtr@UIMigrationTransferDependencyGroup@@@Vml@@@Z`
- size: `1330`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `19`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140079390`
- `0x14008f4d0`

## callees

- `0x14002dd68`
- `0x140032f40`
- `0x14006af38`
- `0x140088c0c`
- `0x140089884`
- `0x14008eb7c`
- `0x14008ed50`
- `0x14008f288`
- `0x14008f40c`
- `0x14009b150`
- `0x1400a30a8`
- `0x1400a3e28`
- `0x1400a70f0`
- `0x1400e2ca4`
- `0x140108f9c`
- `0x140132940`
- `0x140222ba8`
- `0x140222c00`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14008edd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14008f1c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14008edd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14008f1c6`

## string_xrefs

- `0x14008efa8`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008efd9`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008f016`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008f092`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008f0c7`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008f136`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008f167`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008f223`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall WorkerTaskMigrationTarget::ReceiveGuestMemoryContent(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4)
{
  __int64 v8; // rcx
  unsigned int *v9; // r12
  __int64 v10; // rax
  int v11; // r9d
  __int64 v12; // rdi
  int v13; // eax
  int v14; // eax
  EndpointMessageSequencerTarget **v15; // rdi
  EndpointMessageSequencerTarget **v16; // rsi
  __int64 v17; // rdi
  int v18; // eax
  char i; // al
  __int64 v20; // r8
  int v21; // edi
  int v22; // eax
  int v23; // eax
  __int64 result; // rax
  int v25; // eax
  const char *v26; // [rsp+20h] [rbp-198h]
  int v27; // [rsp+20h] [rbp-198h]
  int v28[2]; // [rsp+80h] [rbp-138h] BYREF
  __int64 v29; // [rsp+88h] [rbp-130h] BYREF
  void *v30; // [rsp+90h] [rbp-128h]
  __int64 v31; // [rsp+98h] [rbp-120h]
  __int64 v32; // [rsp+A0h] [rbp-118h]
  _BYTE v33[32]; // [rsp+A8h] [rbp-110h] BYREF
  __int64 v34[8]; // [rsp+C8h] [rbp-F0h] BYREF
  __int64 v35; // [rsp+108h] [rbp-B0h]
  int v36[2]; // [rsp+110h] [rbp-A8h] BYREF
  __int64 v37[4]; // [rsp+118h] [rbp-A0h] BYREF
  __int128 v38; // [rsp+138h] [rbp-80h]
  __int128 v39; // [rsp+148h] [rbp-70h]
  __int128 v40; // [rsp+158h] [rbp-60h]
  __int64 v41; // [rsp+168h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v35 = a3;
  v30 = a4;
  v8 = *(_QWORD *)(a1 + 464);
  try
  {
    *(_QWORD *)(a1 + 472) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 496LL))(v8);
    if ( *(_DWORD *)(a1 + 492) )
    {
      Vml::VmSlimReaderWriterLock::AcquireExclusive((Vml::VmSlimReaderWriterLock *)(a1 + 592));
      *(_BYTE *)(a1 + 608) = 1;
      *(_DWORD *)(a1 + 600) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 592));
    }
    v32 = 1;
    v31 = a1;
    v37[0] = (__int64)&MigrationTargetMemoryStatistics::`vftable';
    v37[1] = *(_QWORD *)(a1 + 440);
    v37[2] = *(_QWORD *)(a1 + 432);
    v9 = (unsigned int *)(a1 + 612);
    v37[3] = a1 + 612;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    *(_QWORD *)v36 = 0;
    *(_QWORD *)v28 = &v29;
    v10 = *a4;
    *a4 = 0;
    v29 = v10;
    std::_Hash<std::_Umap_traits<enum MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>,std::_Uhash_compare<enum MuxMigrationReply::ReplyType,std::hash<enum MuxMigrationReply::ReplyType>,std::equal_to<enum MuxMigrationReply::ReplyType>>,std::allocator<std::pair<enum MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>>>,0>>::_Hash<std::_Umap_traits<enum MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>,std::_Uhash_compare<enum MuxMigrationReply::ReplyType,std::hash<enum MuxMigrationReply::ReplyType>,std::equal_to<enum MuxMigrationReply::ReplyType>>,std::allocator<std::pair<enum MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>>>,0>>(
      v34,
      a3);
    LOBYTE(v11) = *(_DWORD *)(a1 + 488) != 0;
    CreateVmMigrationMessageHandler(
      (int)v36,
      a1 + 640,
      *(_QWORD *)(a1 + 464),
      v11,
      *(_DWORD *)(a1 + 484) != 0,
      *(_BYTE *)(a1 + 408),
      *(_DWORD *)(a1 + 492) != 0,
      *(_QWORD *)(a1 + 584),
      a1 + 496,
      (__int64)v37,
      *(_QWORD *)(a1 + 440),
      *(_QWORD *)(a1 + 720),
      a2,
      (__int64)v34,
      &v29);
    if ( !(***(unsigned __int8 (__fastcall ****)(_QWORD))(a1 + 720))(*(_QWORD *)(a1 + 720)) )
    {
      for ( i = 1; ; i = 0 )
      {
        *(_QWORD *)v28 = 0;
        v20 = i != 0 ? 900000 : 30000;
        v21 = *(_DWORD *)(a1 + 480) & 8;
        if ( v21 )
          v20 = 3600000;
        v22 = VmMigrationConnection::WaitForRequest(*(_QWORD *)(a1 + 440), 27, v20);
        if ( v22 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x83B,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)(unsigned int)v22,
            (int)v28);
        v23 = VmMigrationConnection::AcknowledgeMessageSequence(*(VmMigrationConnection **)(a1 + 440), 0, 0);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x83C,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)(unsigned int)v23,
            (int)v28);
        if ( !v21 )
        {
          MigrationTargetMemoryStatistics::OnNewMemoryTransferPassStartedAtTarget((MigrationTargetMemoryStatistics *)v37);
          v25 = VmMigrationConnection::ReceiveAsynchronousMessageSequence(*(_QWORD *)(a1 + 440), 6, *(_QWORD *)v36, *v9);
          if ( v25 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x854,
              (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
              (const char *)(unsigned int)v25,
              (int)v28);
        }
      }
    }
    v12 = *(_QWORD *)(VmMigrationConnection::WaitForRequest(*(_QWORD *)(a1 + 440), v33, 48, 900000) + 16);
    std::unique_ptr<VmMigrationNetworkBuffer,VmMigrationNetworkBufferDeleter>::~unique_ptr<VmMigrationNetworkBuffer,VmMigrationNetworkBufferDeleter>(v33);
    if ( (unsigned __int8)MuxMigrationHeader::TransferRequestHeaderData::Parse(v12) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x80B,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)0x8007000DLL,
        v27);
    v13 = VmMigrationConnection::AcknowledgeMessageSequence(*(VmMigrationConnection **)(a1 + 440), 0, 0);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x80D,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v13,
        v27);
    v14 = VmMigrationConnection::ReceiveAsynchronousMessageSequence(*(_QWORD *)(a1 + 440), 49, *(_QWORD *)v36, *v9);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x812,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v14,
        v27);
    if ( a2 )
    {
      v15 = *(EndpointMessageSequencerTarget ***)(a2 + 24);
      v16 = *(EndpointMessageSequencerTarget ***)(a2 + 32);
      while ( v15 != v16 )
      {
        EndpointMessageSequencerTarget::EnsureTransferCompleted(*v15);
        v15 += 2;
      }
    }
    v17 = *(_QWORD *)(VmMigrationConnection::WaitForRequest(*(_QWORD *)(a1 + 440), v33, 48, 30000) + 16);
    std::unique_ptr<VmMigrationNetworkBuffer,VmMigrationNetworkBufferDeleter>::~unique_ptr<VmMigrationNetworkBuffer,VmMigrationNetworkBufferDeleter>(v33);
    if ( (unsigned __int8)MuxMigrationHeader::TransferRequestHeaderData::Parse(v17) != 1 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x81E,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)0x8007000DLL,
        v27);
    v18 = VmMigrationConnection::AcknowledgeMessageSequence(*(VmMigrationConnection **)(a1 + 440), 0, 0);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x820,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v18,
        v27);
    std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>(v36);
    if ( *(_DWORD *)(a1 + 492) )
    {
      Vml::VmSlimReaderWriterLock::AcquireExclusive((Vml::VmSlimReaderWriterLock *)(a1 + 592));
      *(_BYTE *)(a1 + 608) = 0;
      *(_DWORD *)(a1 + 600) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 592));
    }
    std::_Hash<std::_Umap_traits<enum MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>,std::_Uhash_compare<enum MuxMigrationReply::ReplyType,std::hash<enum MuxMigrationReply::ReplyType>,std::equal_to<enum MuxMigrationReply::ReplyType>>,std::allocator<std::pair<enum MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>>,0>>::~_Hash<std::_Umap_traits<enum MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>,std::_Uhash_compare<enum MuxMigrationReply::ReplyType,std::hash<enum MuxMigrationReply::ReplyType>,std::equal_to<enum MuxMigrationReply::ReplyType>>,std::allocator<std::pair<enum MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>>,0>>(a3);
    Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(a4);
    result = 0;
  }
  catch ( ... )
  {
    v36[0] = wil::details::in1diag3::Return_CaughtExceptionMsg(
               retaddr,
               (void *)0x85D,
               (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
               "Failed to receive guest memory content",
               v26);
    std::_Hash<std::_Umap_traits<enum MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>,std::_Uhash_compare<enum MuxMigrationReply::ReplyType,std::hash<enum MuxMigrationReply::ReplyType>,std::equal_to<enum MuxMigrationReply::ReplyType>>,std::allocator<std::pair<enum MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>>,0>>::~_Hash<std::_Umap_traits<enum MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>,std::_Uhash_compare<enum MuxMigrationReply::ReplyType,std::hash<enum MuxMigrationReply::ReplyType>,std::equal_to<enum MuxMigrationReply::ReplyType>>,std::allocator<std::pair<enum MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>>,0>>(v35);
    Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(v30);
    return (unsigned int)v36[0];
  }
  return result;
}

```

## disassembly

```asm
0x14008ed50  push    rbx
0x14008ed52  push    rsi
0x14008ed53  push    rdi
0x14008ed54  push    r12
0x14008ed56  push    r13
0x14008ed58  push    r14
0x14008ed5a  push    r15
0x14008ed5c  sub     rsp, 180h
0x14008ed63  mov     rax, cs:__security_cookie
0x14008ed6a  xor     rax, rsp
0x14008ed6d  mov     [rsp+1B8h+var_48], rax
0x14008ed75  mov     r14, r9
0x14008ed78  mov     r15, r8
0x14008ed7b  mov     rsi, rdx
0x14008ed7e  mov     rbx, rcx
0x14008ed81  mov     [rsp+1B8h+var_B0], r8
0x14008ed89  mov     [rsp+1B8h+var_128], r9
0x14008ed91  mov     rcx, [rcx+1D0h]
0x14008ed98  mov     rax, [rcx]
0x14008ed9b  mov     rax, [rax+1F0h]
0x14008eda2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008eda7  mov     [rbx+1D8h], rax
0x14008edae  xor     r13d, r13d
0x14008edb1  cmp     [rbx+1ECh], r13d
0x14008edb8  jz      short loc_14008EDE3
0x14008edba  lea     rdi, [rbx+250h]
0x14008edc1  mov     rcx, rdi; this
0x14008edc4  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x14008edc9  mov     byte ptr [rbx+260h], 1
0x14008edd0  mov     [rdi+8], r13d
0x14008edd4  mov     rcx, rdi; SRWLock
0x14008edd7  call    cs:__imp_ReleaseSRWLockExclusive
0x14008edde  nop     dword ptr [rax+rax+00h]
0x14008ede3  xorps   xmm0, xmm0
0x14008ede6  movups  [rsp+1B8h+var_120], xmm0
0x14008edee  mov     qword ptr [rsp+1B8h+var_120], rbx
0x14008edf6  mov     byte ptr [rsp+1B8h+var_120+8], 1
0x14008edfe  lea     rax, ??_7MigrationTargetMemoryStatistics@@6B@; const MigrationTargetMemoryStatistics::`vftable'
0x14008ee05  mov     [rsp+1B8h+var_A0], rax
0x14008ee0d  mov     rax, [rbx+1B8h]
0x14008ee14  mov     [rsp+1B8h+var_98], rax
0x14008ee1c  mov     rax, [rbx+1B0h]
0x14008ee23  mov     [rsp+1B8h+var_90], rax
0x14008ee2b  lea     r12, [rbx+264h]
0x14008ee32  mov     [rsp+1B8h+var_88], r12
0x14008ee3a  movdqu  [rsp+1B8h+var_80], xmm0
0x14008ee43  xorps   xmm1, xmm1
0x14008ee46  movdqu  [rsp+1B8h+var_70], xmm1
0x14008ee4f  movdqu  [rsp+1B8h+var_60], xmm0
0x14008ee58  mov     [rsp+1B8h+var_50], r13
0x14008ee60  mov     qword ptr [rsp+1B8h+var_A8], r13
0x14008ee68  lea     rax, [rsp+1B8h+var_130]
0x14008ee70  mov     qword ptr [rsp+1B8h+var_138], rax
0x14008ee78  mov     rax, [r14]
0x14008ee7b  mov     [r14], r13
0x14008ee7e  mov     [rsp+1B8h+var_130], rax
0x14008ee86  mov     rdx, r15
0x14008ee89  lea     rcx, [rsp+1B8h+var_F0]
0x14008ee91  call    ??0?$_Hash@V?$_Umap_traits@W4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VIReplyProcessor@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VIReplyProcessor@MuxMigrationReply@@@std@@@2@@std@@V?$_Uhash_compare@W4ReplyType@MuxMigrationReply@@U?$hash@W4ReplyType@MuxMigrationReply@@@std@@U?$equal_to@W4ReplyType@MuxMigrationReply@@@4@@4@V?$allocator@U?$pair@$$CBW4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VIReplyProcessor@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VIReplyProcessor@MuxMigrationReply@@@std@@@2@@std@@@std@@@4@$0A@@std@@@std@@IEAA@$$QEAV01@@Z; std::_Hash<std::_Umap_traits<MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>,std::_Uhash_compare<MuxMigrationReply::ReplyType,std::hash<MuxMigrationReply::ReplyType>,std::equal_to<MuxMigrationReply::ReplyType>>,std::allocator<std::pair<MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>>>,0>>::_Hash<std::_Umap_traits<MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>,std::_Uhash_compare<MuxMigrationReply::ReplyType,std::hash<MuxMigrationReply::ReplyType>,std::equal_to<MuxMigrationReply::ReplyType>>,std::allocator<std::pair<MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>>>,0>>(std::_Hash<std::_Umap_traits<MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>,std::_Uhash_compare<MuxMigrationReply::ReplyType,std::hash<MuxMigrationReply::ReplyType>,std::equal_to<MuxMigrationReply::ReplyType>>,std::allocator<std::pair<MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>>>,0>> &&)
0x14008ee96  lea     rcx, [rbx+1F0h]
0x14008ee9d  cmp     [rbx+1ECh], r13d
0x14008eea4  setnz   r8b
0x14008eea8  cmp     [rbx+1E4h], r13d
0x14008eeaf  setnz   r10b
0x14008eeb3  cmp     [rbx+1E8h], r13d
0x14008eeba  setnz   r9b; int
0x14008eebe  lea     rdx, [rbx+280h]; int
0x14008eec5  lea     rax, [rsp+1B8h+var_130]
0x14008eecd  mov     [rsp+1B8h+var_148], rax; void *
0x14008eed2  lea     rax, [rsp+1B8h+var_F0]
0x14008eeda  mov     [rsp+1B8h+var_150], rax; __int64
0x14008eedf  mov     [rsp+1B8h+var_158], rsi; __int64
0x14008eee4  mov     rax, [rbx+2D0h]
0x14008eeeb  mov     [rsp+1B8h+var_160], rax; __int64
0x14008eef0  mov     rax, [rbx+1B8h]
0x14008eef7  mov     [rsp+1B8h+var_168], rax; __int64
0x14008eefc  lea     rax, [rsp+1B8h+var_A0]
0x14008ef04  mov     [rsp+1B8h+var_170], rax; __int64
0x14008ef09  mov     [rsp+1B8h+var_178], rcx; __int64
0x14008ef0e  mov     rax, [rbx+248h]
0x14008ef15  mov     [rsp+1B8h+var_180], rax; __int64
0x14008ef1a  mov     [rsp+1B8h+var_188], r8b; char
0x14008ef1f  mov     al, [rbx+198h]
0x14008ef25  mov     [rsp+1B8h+var_190], al; char
0x14008ef29  mov     [rsp+1B8h+var_198], r10b; int
0x14008ef2e  mov     r8, [rbx+1D0h]; int
0x14008ef35  lea     rcx, [rsp+1B8h+var_A8]; int
0x14008ef3d  call    ?CreateVmMigrationMessageHandler@@YA?AV?$unique_ptr@VIVmMigrationMessageHandler@@U?$default_delete@VIVmMigrationMessageHandler@@@std@@@std@@PEBVWorkerTaskMigrationTargetSettings@@PEAUIMemoryManager@@_N222_KPEAV?$GmoMigrationQueue@UDECOMPRESSOR_INFO@WorkerTaskMigrationTarget@@@@PEAVMigrationTargetMemoryStatistics@@PEAVVmMigrationConnection@@PEAVIMigrationTransferOrchestratorTarget@@PEAVEndpointMessageSequencerCollectionTarget@@V?$unordered_map@W4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@@2@@std@@U?$hash@W4ReplyType@MuxMigrationReply@@@4@U?$equal_to@W4ReplyType@MuxMigrationReply@@@4@V?$allocator@U?$pair@$$CBW4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@@2@@std@@@std@@@4@@2@V?$VmComPtr@UIMigrationTransferDependencyGroup@@@Vml@@@Z; CreateVmMigrationMessageHandler(WorkerTaskMigrationTargetSettings const *,IMemoryManager *,bool,bool,bool,bool,unsigned __int64,GmoMigrationQueue<WorkerTaskMigrationTarget::DECOMPRESSOR_INFO> *,MigrationTargetMemoryStatistics *,VmMigrationConnection *,IMigrationTransferOrchestratorTarget *,EndpointMessageSequencerCollectionTarget *,std::unordered_map<MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>,Vml::VmComPtr<IMigrationTransferDependencyGroup>)
0x14008ef42  nop
0x14008ef43  mov     rcx, [rbx+2D0h]
0x14008ef4a  mov     rax, [rcx]
0x14008ef4d  mov     rax, [rax]
0x14008ef50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008ef55  test    al, al
0x14008ef57  jz      loc_14008F0D8
0x14008ef5d  mov     r9d, 0DBBA0h
0x14008ef63  mov     r8d, 30h ; '0'
0x14008ef69  lea     rdx, [rsp+1B8h+var_110]
0x14008ef71  mov     rcx, [rbx+1B8h]
0x14008ef78  call    ?WaitForRequest@VmMigrationConnection@@QEAA?AU?$pair@V?$unique_ptr@VVmMigrationNetworkBuffer@@VVmMigrationNetworkBufferDeleter@@@std@@_K@std@@W4MESSAGE_SEQUENCE_TYPE@1@K@Z; VmMigrationConnection::WaitForRequest(VmMigrationConnection::MESSAGE_SEQUENCE_TYPE,ulong)
0x14008ef7d  mov     rdi, [rax+10h]
0x14008ef81  lea     rcx, [rsp+1B8h+var_110]
0x14008ef89  call    ??1?$unique_ptr@VVmMigrationNetworkBuffer@@VVmMigrationNetworkBufferDeleter@@@std@@QEAA@XZ; std::unique_ptr<VmMigrationNetworkBuffer,VmMigrationNetworkBufferDeleter>::~unique_ptr<VmMigrationNetworkBuffer,VmMigrationNetworkBufferDeleter>(void)
0x14008ef8e  mov     rcx, rdi
0x14008ef91  call    ?Parse@TransferRequestHeaderData@MuxMigrationHeader@@SA?AW4TransferRequestFlags@2@_K@Z; MuxMigrationHeader::TransferRequestHeaderData::Parse(unsigned __int64)
0x14008ef96  mov     rcx, [rsp+1B8h]; this
0x14008ef9e  test    al, al
0x14008efa0  jz      short loc_14008EFB9
0x14008efa2  mov     r9d, 8007000Dh; char *
0x14008efa8  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008efaf  mov     edx, 80Bh; void *
0x14008efb4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008efb9  xor     r8d, r8d; unsigned __int64
0x14008efbc  xor     edx, edx; struct VmMigrationNetworkBuffer *
0x14008efbe  mov     rcx, [rbx+1B8h]; this
0x14008efc5  call    ?AcknowledgeMessageSequence@VmMigrationConnection@@QEAAJPEBVVmMigrationNetworkBuffer@@_K@Z; VmMigrationConnection::AcknowledgeMessageSequence(VmMigrationNetworkBuffer const *,unsigned __int64)
0x14008efca  mov     rcx, [rsp+1B8h]; this
0x14008efd2  test    eax, eax
0x14008efd4  jns     short loc_14008EFEA
0x14008efd6  mov     r9d, eax; char *
0x14008efd9  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008efe0  mov     edx, 80Dh; void *
0x14008efe5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008efea  mov     r9d, [r12]
0x14008efee  mov     r8, qword ptr [rsp+1B8h+var_A8]
0x14008eff6  mov     edx, 31h ; '1'
0x14008effb  mov     rcx, [rbx+1B8h]
0x14008f002  call    ?ReceiveAsynchronousMessageSequence@VmMigrationConnection@@QEAAJW4MESSAGE_SEQUENCE_TYPE@1@PEAVIVmMigrationMessageHandler@@I@Z; VmMigrationConnection::ReceiveAsynchronousMessageSequence(VmMigrationConnection::MESSAGE_SEQUENCE_TYPE,IVmMigrationMessageHandler *,uint)
0x14008f007  mov     rcx, [rsp+1B8h]; this
0x14008f00f  test    eax, eax
0x14008f011  jns     short loc_14008F027
0x14008f013  mov     r9d, eax; char *
0x14008f016  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008f01d  mov     edx, 812h; void *
0x14008f022  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008f027  test    rsi, rsi
0x14008f02a  jz      short loc_14008F047
0x14008f02c  mov     rdi, [rsi+18h]
0x14008f030  mov     rsi, [rsi+20h]
0x14008f034  cmp     rdi, rsi
0x14008f037  jz      short loc_14008F047
0x14008f039  mov     rcx, [rdi]; this
0x14008f03c  call    ?EnsureTransferCompleted@EndpointMessageSequencerTarget@@QEAAXXZ; EndpointMessageSequencerTarget::EnsureTransferCompleted(void)
0x14008f041  add     rdi, 10h
0x14008f045  jmp     short loc_14008F034
0x14008f047  mov     r9d, 7530h
0x14008f04d  mov     r8d, 30h ; '0'
0x14008f053  lea     rdx, [rsp+1B8h+var_110]
0x14008f05b  mov     rcx, [rbx+1B8h]
0x14008f062  call    ?WaitForRequest@VmMigrationConnection@@QEAA?AU?$pair@V?$unique_ptr@VVmMigrationNetworkBuffer@@VVmMigrationNetworkBufferDeleter@@@std@@_K@std@@W4MESSAGE_SEQUENCE_TYPE@1@K@Z; VmMigrationConnection::WaitForRequest(VmMigrationConnection::MESSAGE_SEQUENCE_TYPE,ulong)
0x14008f067  mov     rdi, [rax+10h]
0x14008f06b  lea     rcx, [rsp+1B8h+var_110]
0x14008f073  call    ??1?$unique_ptr@VVmMigrationNetworkBuffer@@VVmMigrationNetworkBufferDeleter@@@std@@QEAA@XZ; std::unique_ptr<VmMigrationNetworkBuffer,VmMigrationNetworkBufferDeleter>::~unique_ptr<VmMigrationNetworkBuffer,VmMigrationNetworkBufferDeleter>(void)
0x14008f078  mov     rcx, rdi
0x14008f07b  call    ?Parse@TransferRequestHeaderData@MuxMigrationHeader@@SA?AW4TransferRequestFlags@2@_K@Z; MuxMigrationHeader::TransferRequestHeaderData::Parse(unsigned __int64)
0x14008f080  mov     rcx, [rsp+1B8h]; this
0x14008f088  cmp     al, 1
0x14008f08a  jz      short loc_14008F0A3
0x14008f08c  mov     r9d, 8007000Dh; char *
0x14008f092  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008f099  mov     edx, 81Eh; void *
0x14008f09e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008f0a3  xor     r8d, r8d; unsigned __int64
0x14008f0a6  xor     edx, edx; struct VmMigrationNetworkBuffer *
0x14008f0a8  mov     rcx, [rbx+1B8h]; this
0x14008f0af  call    ?AcknowledgeMessageSequence@VmMigrationConnection@@QEAAJPEBVVmMigrationNetworkBuffer@@_K@Z; VmMigrationConnection::AcknowledgeMessageSequence(VmMigrationNetworkBuffer const *,unsigned __int64)
0x14008f0b4  mov     rcx, [rsp+1B8h]; this
0x14008f0bc  test    eax, eax
0x14008f0be  jns     loc_14008F192
0x14008f0c4  mov     r9d, eax; char *
0x14008f0c7  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008f0ce  mov     edx, 820h; void *
0x14008f0d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008f0d8  mov     al, 1
0x14008f0da  mov     qword ptr [rsp+1B8h+var_138], r13
0x14008f0e2  mov     edi, [rbx+1E0h]
0x14008f0e8  neg     al
0x14008f0ea  sbb     r8d, r8d
0x14008f0ed  and     r8d, 0D4670h
0x14008f0f4  add     r8d, 7530h
0x14008f0fb  mov     eax, 36EE80h
0x14008f100  and     edi, 8
0x14008f103  cmovnz  r8d, eax
0x14008f107  lea     rax, [rsp+1B8h+var_138]
0x14008f10f  mov     qword ptr [rsp+1B8h+var_198], rax; int
0x14008f114  xor     r9d, r9d
0x14008f117  lea     edx, [r9+1Bh]
0x14008f11b  mov     rcx, [rbx+1B8h]
0x14008f122  call    ?WaitForRequest@VmMigrationConnection@@QEAAJW4MESSAGE_SEQUENCE_TYPE@1@KPEAPEAVVmMigrationNetworkBuffer@@AEA_K@Z; VmMigrationConnection::WaitForRequest(VmMigrationConnection::MESSAGE_SEQUENCE_TYPE,ulong,VmMigrationNetworkBuffer * *,unsigned __int64 &)
0x14008f127  mov     rcx, [rsp+1B8h]; this
0x14008f12f  test    eax, eax
0x14008f131  jns     short loc_14008F147
0x14008f133  mov     r9d, eax; char *
0x14008f136  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008f13d  mov     edx, 83Bh; void *
0x14008f142  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008f147  xor     r8d, r8d; unsigned __int64
0x14008f14a  xor     edx, edx; struct VmMigrationNetworkBuffer *
0x14008f14c  mov     rcx, [rbx+1B8h]; this
0x14008f153  call    ?AcknowledgeMessageSequence@VmMigrationConnection@@QEAAJPEBVVmMigrationNetworkBuffer@@_K@Z; VmMigrationConnection::AcknowledgeMessageSequence(VmMigrationNetworkBuffer const *,unsigned __int64)
0x14008f158  mov     rcx, [rsp+1B8h]; this
0x14008f160  test    eax, eax
0x14008f162  jns     short loc_14008F178
0x14008f164  mov     r9d, eax; char *
0x14008f167  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008f16e  mov     edx, 83Ch; void *
0x14008f173  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008f178  test    byte ptr [rsp+1B8h+var_138], 1
0x14008f180  jz      short loc_14008F1E8
0x14008f182  mov     dl, 1; bool
0x14008f184  lea     rcx, [rsp+1B8h+var_A0]; this
0x14008f18c  call    ?UpdatePerfCounters@MigrationTargetMemoryStatistics@@QEAAX_N@Z; MigrationTargetMemoryStatistics::UpdatePerfCounters(bool)
0x14008f191  nop
0x14008f192  lea     rcx, [rsp+1B8h+var_A8]
0x14008f19a  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x14008f19f  nop
0x14008f1a0  cmp     [rbx+1ECh], r13d
0x14008f1a7  jz      short loc_14008F1D3
0x14008f1a9  lea     rdi, [rbx+250h]
0x14008f1b0  mov     rcx, rdi; this
0x14008f1b3  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x14008f1b8  mov     [rbx+260h], r13b
0x14008f1bf  mov     [rdi+8], r13d
0x14008f1c3  mov     rcx, rdi; SRWLock
0x14008f1c6  call    cs:__imp_ReleaseSRWLockExclusive
0x14008f1cd  nop     dword ptr [rax+rax+00h]
0x14008f1d2  nop
0x14008f1d3  mov     rcx, r15
0x14008f1d6  call    ??1?$_Hash@V?$_Umap_traits@W4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@@2@@std@@V?$_Uhash_compare@W4ReplyType@MuxMigrationReply@@U?$hash@W4ReplyType@MuxMigrationReply@@@std@@U?$equal_to@W4ReplyType@MuxMigrationReply@@@4@@4@V?$allocator@U?$pair@$$CBW4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@@2@@std@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>,std::_Uhash_compare<MuxMigrationReply::ReplyType,std::hash<MuxMigrationReply::ReplyType>,std::equal_to<MuxMigrationReply::ReplyType>>,std::allocator<std::pair<MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>>,0>>::~_Hash<std::_Umap_traits<MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>,std::_Uhash_compare<MuxMigrationReply::ReplyType,std::hash<MuxMigrationReply::ReplyType>,std::equal_to<MuxMigrationReply::ReplyType>>,std::allocator<std::pair<MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>>,0>>(void)
0x14008f1db  nop
0x14008f1dc  mov     rcx, r14; void *
0x14008f1df  call    ??1?$VmComPtr@UIVmMetricValueSink@@@Vml@@QEAA@XZ; Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(void)
0x14008f1e4  xor     eax, eax
0x14008f1e6  jmp     short loc_14008F25E
0x14008f1e8  test    edi, edi
0x14008f1ea  jnz     short loc_14008F234
0x14008f1ec  lea     rcx, [rsp+1B8h+var_A0]; this
0x14008f1f4  call    ?OnNewMemoryTransferPassStartedAtTarget@MigrationTargetMemoryStatistics@@QEAAXXZ; MigrationTargetMemoryStatistics::OnNewMemoryTransferPassStartedAtTarget(void)
0x14008f1f9  mov     r9d, [r12]
0x14008f1fd  mov     r8, qword ptr [rsp+1B8h+var_A8]
0x14008f205  lea     edx, [rdi+6]
0x14008f208  mov     rcx, [rbx+1B8h]
0x14008f20f  call    ?ReceiveAsynchronousMessageSequence@VmMigrationConnection@@QEAAJW4MESSAGE_SEQUENCE_TYPE@1@PEAVIVmMigrationMessageHandler@@I@Z; VmMigrationConnection::ReceiveAsynchronousMessageSequence(VmMigrationConnection::MESSAGE_SEQUENCE_TYPE,IVmMigrationMessageHandler *,uint)
0x14008f214  mov     rcx, [rsp+1B8h]; this
0x14008f21c  test    eax, eax
0x14008f21e  jns     short loc_14008F234
0x14008f220  mov     r9d, eax; char *
0x14008f223  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008f22a  mov     edx, 854h; void *
0x14008f22f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008f234  mov     al, r13b
0x14008f237  jmp     loc_14008F0DA
0x14008f23c  mov     rcx, [rsp+1B8h+var_B0]
0x14008f244  call    ??1?$_Hash@V?$_Umap_traits@W4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@@2@@std@@V?$_Uhash_compare@W4ReplyType@MuxMigrationReply@@U?$hash@W4ReplyType@MuxMigrationReply@@@std@@U?$equal_to@W4ReplyType@MuxMigrationReply@@@4@@4@V?$allocator@U?$pair@$$CBW4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@@2@@std@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>,std::_Uhash_compare<MuxMigrationReply::ReplyType,std::hash<MuxMigrationReply::ReplyType>,std::equal_to<MuxMigrationReply::ReplyType>>,std::allocator<std::pair<MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>>,0>>::~_Hash<std::_Umap_traits<MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>,std::_Uhash_compare<MuxMigrationReply::ReplyType,std::hash<MuxMigrationReply::ReplyType>,std::equal_to<MuxMigrationReply::ReplyType>>,std::allocator<std::pair<MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>>,0>>(void)
0x14008f249  nop
0x14008f24a  mov     rcx, [rsp+1B8h+var_128]; void *
0x14008f252  call    ??1?$VmComPtr@UIVmMetricValueSink@@@Vml@@QEAA@XZ; Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(void)
0x14008f257  mov     eax, [rsp+1B8h+var_A8]
0x14008f25e  mov     rcx, [rsp+1B8h+var_48]
0x14008f266  xor     rcx, rsp; StackCookie
0x14008f269  call    __security_check_cookie
0x14008f26e  add     rsp, 180h
0x14008f275  pop     r15
0x14008f277  pop     r14
0x14008f279  pop     r13
0x14008f27b  pop     r12
0x14008f27d  pop     rdi
0x14008f27e  pop     rsi
0x14008f27f  pop     rbx
0x14008f280  retn
```
