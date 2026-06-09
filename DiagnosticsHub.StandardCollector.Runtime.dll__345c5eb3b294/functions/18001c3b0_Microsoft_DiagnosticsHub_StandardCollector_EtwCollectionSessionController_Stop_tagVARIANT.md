# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::Stop(tagVARIANT *)

- ea: `0x18001c3b0`
- end: `0x18001c7a0`
- name: `?Stop@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@UEAAJPEAUtagVARIANT@@@Z`
- size: `1008`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180001a98`
- `0x1800023c4`
- `0x180002604`
- `0x18000288c`
- `0x18000334c`
- `0x18000b094`
- `0x18000b150`
- `0x18000f1b0`
- `0x18001c3b0`
- `0x18001f82c`
- `0x180020004`
- `0x180023a78`
- `0x1800256ac`
- `0x18002eaac`
- `0x180037f10`
- `0x18003d864`
- `0x180049b50`
- `0x18004a078`
- `0x18004b640`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18001c44c`
- `KERNEL32!SetEvent` at `0x18001c44c`
- `KERNEL32!DeleteFileW` at `0x18001c659`
- `KERNEL32!DeleteFileW` at `0x18001c6a0`
- `KERNEL32!DeleteFileW` at `0x18001c659`
- `KERNEL32!DeleteFileW` at `0x18001c6a0`
- `KERNEL32!LeaveCriticalSection` at `0x18001c522`
- `KERNEL32!LeaveCriticalSection` at `0x18001c648`
- `KERNEL32!LeaveCriticalSection` at `0x18001c522`
- `KERNEL32!LeaveCriticalSection` at `0x18001c648`
- `KERNEL32!EnterCriticalSection` at `0x18001c477`
- `KERNEL32!EnterCriticalSection` at `0x18001c477`
- `KERNEL32!GetLastError` at `0x18001c66a`
- `KERNEL32!GetLastError` at `0x18001c6b1`
- `KERNEL32!GetLastError` at `0x18001c66a`
- `KERNEL32!GetLastError` at `0x18001c6b1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c71f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c71f`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001c6f0`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001c6f0`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001c6fc`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001c6fc`

## string_xrefs

- `0x18001c677`: `Failed to delete ETL file: %s. Error code: %d`
- `0x18001c6be`: `Failed to delete merged ETL file: %s. Error code: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::Stop(
        Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *this,
        struct tagVARIANT *a2)
{
  __int64 result; // rax
  HANDLE *i; // rbx
  Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter **v6; // r15
  Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter **v7; // rsi
  Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter *v8; // r14
  struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation *j; // r14
  int CurrentResult; // esi
  struct ATL::IAtlStringMgr *Instance; // rax
  unsigned __int16 *v12; // rbx
  Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent *v13; // rcx
  LPCWSTR *k; // rsi
  LPCWSTR *v15; // r14
  LPCWSTR v16; // r15
  DiagHubCommon::LogStream *v17; // rdi
  DiagHubCommon::LogStream *v18; // rdi
  BSTR v19; // rax
  UINT v20; // eax
  __int64 v21; // [rsp+20h] [rbp-50h]
  unsigned __int16 *v22; // [rsp+30h] [rbp-40h] BYREF
  __int128 v23; // [rsp+38h] [rbp-38h] BYREF
  __int64 v24; // [rsp+48h] [rbp-28h]
  unsigned __int16 *v25; // [rsp+50h] [rbp-20h] BYREF
  BSTR bstr; // [rsp+58h] [rbp-18h] BYREF
  struct DhPackaging::IDhPackage *v27; // [rsp+60h] [rbp-10h] BYREF

  if ( *((_BYTE *)this + 3576) )
    return 3775987731LL;
  Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EmitMachineInfo(this);
  *((_BYTE *)this + 3577) = 1;
  result = Microsoft::DiagnosticsHub::StandardCollector::AgentController::CommunicateWithAgents(
             (__int64)this + 24,
             9,
             0,
             0,
             0);
  _mm_lfence();
  if ( (int)result >= 0 )
  {
    for ( i = (HANDLE *)((char *)this + 1112); i != (HANDLE *)((char *)this + 1880); i += 3 )
    {
      *(_DWORD *)i = 0;
      if ( *((int *)i + 4) >= 0 )
        SetEvent(i[1]);
    }
    v23 = 0;
    v24 = 0;
    v25 = (unsigned __int16 *)((char *)this + 3496);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 3496));
    v6 = (Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter **)*((_QWORD *)this + 450);
    v7 = (Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter **)*((_QWORD *)this + 449);
    if ( v7 != v6 )
    {
      do
      {
        v8 = *v7;
        if ( *v7 )
        {
          Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter::~EventSourceRegistryKeyFilter(*v7);
          operator delete(v8);
        }
        ++v7;
      }
      while ( v7 != v6 );
      *((_QWORD *)this + 450) = *((_QWORD *)this + 449);
    }
    for ( j = (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *)((char *)this + 2856);
          j != (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *)((char *)this + 3496);
          j = (struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation *)((char *)j + 128) )
    {
      CurrentResult = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::StopSuppliedEtwSession(
                        this,
                        j,
                        (const unsigned __int16 **)&v22);
      if ( CurrentResult < 0 )
      {
        _mm_lfence();
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 3496));
        goto LABEL_52;
      }
      if ( v22 )
        std::vector<unsigned short const *>::push_back(&v23, &v22);
    }
    _mm_lfence();
    *((_BYTE *)this + 3577) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 3496));
    v27 = 0;
    CurrentResult = Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::AfterStop(this, &v27);
    if ( CurrentResult >= 0 )
    {
      Instance = ATL::CAtlStringMgr::GetInstance();
      if ( !Instance )
        ATL::AtlThrowImpl(-2147467259);
      v12 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                               + 24);
      v22 = v12;
      bstr = 0;
      if ( !v27 || !a2 )
        goto LABEL_57;
      if ( (_QWORD)v23 == *((_QWORD *)&v23 + 1)
        || (_mm_lfence(),
            CurrentResult = Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::GetDirectoryPath(
                              *((Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory **)this + 491),
                              (const unsigned __int16 **)&v25),
            CurrentResult >= 0)
        && (_mm_lfence(),
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
              &v22,
              L"%ssc.user_aux.etl",
              v25),
            v12 = v22,
            CurrentResult = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::AddEtwSessionResultsToPackage(
                              this,
                              &v23,
                              v22,
                              v27),
            CurrentResult >= 0) )
      {
        _mm_lfence();
        v13 = (Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent *)*((_QWORD *)this + 337);
        if ( !v13
          || (CurrentResult = Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::GetCurrentResult(
                                v13,
                                v27),
              CurrentResult >= 0) )
        {
          _mm_lfence();
          CurrentResult = Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::CommitResult(
                            this,
                            1,
                            *((_DWORD *)this + 215),
                            &bstr);
          if ( CurrentResult >= 0 )
          {
LABEL_57:
            if ( !*((_BYTE *)this + 3938) )
            {
              v15 = (LPCWSTR *)*((_QWORD *)&v23 + 1);
              for ( k = (LPCWSTR *)v23; k != v15; ++k )
              {
                v16 = *k;
                if ( !DeleteFileW(*k) )
                {
                  v17 = _logger;
                  LODWORD(v21) = GetLastError();
                  DiagHubCommon::LogStream::Write(
                    (DiagHubCommon::LogStream *)((char *)v17 + 56),
                    L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
                    L"Failed to delete ETL file: %s. Error code: %d",
                    v16,
                    v21);
                }
              }
              if ( *((int *)v12 - 4) > 0 && !DeleteFileW(v12) )
              {
                v18 = _logger;
                LODWORD(v21) = GetLastError();
                DiagHubCommon::LogStream::Write(
                  (DiagHubCommon::LogStream *)((char *)v18 + 56),
                  L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
                  L"Failed to delete merged ETL file: %s. Error code: %d",
                  v12,
                  v21);
              }
            }
            if ( a2
              && ((a2->vt = 8, bstr)
                ? (v20 = SysStringByteLen(bstr), v19 = SysAllocStringByteLen((LPCSTR)bstr, v20))
                : (v19 = 0),
                  (a2->llVal = (LONGLONG)v19) == 0 && bstr) )
            {
              CurrentResult = -2147024882;
            }
            else
            {
              CurrentResult = 0;
            }
          }
        }
      }
      SysFreeString(bstr);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
      }
    }
    if ( v27 )
      (*(void (__fastcall **)(struct DhPackaging::IDhPackage *))(*(_QWORD *)v27 + 16LL))(v27);
LABEL_52:
    _mm_lfence();
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(&v23);
    return (unsigned int)CurrentResult;
  }
  return result;
}

```

## disassembly

```asm
0x18001c3b0  mov     [rsp-28h+arg_10], rbx
0x18001c3b5  mov     [rsp-28h+arg_18], rsi
0x18001c3ba  push    rbp
0x18001c3bb  push    rdi
0x18001c3bc  push    r12
0x18001c3be  push    r14
0x18001c3c0  push    r15
0x18001c3c2  mov     rbp, rsp
0x18001c3c5  sub     rsp, 70h
0x18001c3c9  mov     rax, cs:__security_cookie
0x18001c3d0  xor     rax, rsp
0x18001c3d3  mov     [rbp+var_8], rax
0x18001c3d7  mov     r12, rdx
0x18001c3da  mov     rdi, rcx
0x18001c3dd  mov     al, [rcx+0DF8h]
0x18001c3e3  test    al, al
0x18001c3e5  jz      short loc_18001C3F1
0x18001c3e7  mov     eax, 0E1110013h
0x18001c3ec  jmp     loc_18001C770
0x18001c3f1  call    ?EmitMachineInfo@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJXZ; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EmitMachineInfo(void)
0x18001c3f6  mov     eax, 1
0x18001c3fb  xchg    al, [rdi+0DF9h]
0x18001c401  lea     rcx, [rdi+18h]
0x18001c405  mov     [rsp+70h+var_50], 0
0x18001c40e  xor     r9d, r9d
0x18001c411  xor     r8d, r8d
0x18001c414  lea     edx, [r9+9]
0x18001c418  call    ?CommunicateWithAgents@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJW4SessionEvent@@PEBUtagVARIANT@@1PEAU6@@Z; Microsoft::DiagnosticsHub::StandardCollector::AgentController::CommunicateWithAgents(SessionEvent,tagVARIANT const *,tagVARIANT const *,tagVARIANT *)
0x18001c41d  lfence
0x18001c420  test    eax, eax
0x18001c422  js      loc_18001C770
0x18001c428  lea     rbx, [rdi+458h]
0x18001c42f  lea     rsi, [rbx+300h]
0x18001c436  jmp     short loc_18001C456
0x18001c438  mov     dword ptr [rbx], 0
0x18001c43e  mov     eax, [rbx+10h]
0x18001c441  shr     eax, 1Fh
0x18001c444  test    al, al
0x18001c446  jnz     short loc_18001C452
0x18001c448  mov     rcx, [rbx+8]; hEvent
0x18001c44c  call    cs:__imp_SetEvent
0x18001c452  add     rbx, 18h
0x18001c456  cmp     rbx, rsi
0x18001c459  jnz     short loc_18001C438
0x18001c45b  xor     eax, eax
0x18001c45d  xorps   xmm1, xmm1
0x18001c460  movdqu  [rbp+var_38], xmm1
0x18001c465  mov     [rbp+var_28], rax
0x18001c469  lea     rbx, [rdi+0DA8h]
0x18001c470  mov     [rbp+var_20], rbx
0x18001c474  mov     rcx, rbx; lpCriticalSection
0x18001c477  call    cs:__imp_EnterCriticalSection
0x18001c47d  nop
0x18001c47e  mov     r15, [rdi+0E10h]
0x18001c485  mov     rsi, [rdi+0E08h]
0x18001c48c  mov     eax, 8
0x18001c491  cmp     rsi, r15
0x18001c494  jz      short loc_18001C4CE
0x18001c496  mov     r14, [rsi]
0x18001c499  test    r14, r14
0x18001c49c  jz      short loc_18001C4B8
0x18001c49e  mov     rcx, r14; this
0x18001c4a1  call    ??1EventSourceRegistryKeyFilter@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter::~EventSourceRegistryKeyFilter(void)
0x18001c4a6  mov     edx, 38h ; '8'
0x18001c4ab  mov     rcx, r14; Block
0x18001c4ae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c4b3  mov     eax, 8
0x18001c4b8  add     rsi, rax
0x18001c4bb  cmp     rsi, r15
0x18001c4be  jnz     short loc_18001C496
0x18001c4c0  mov     rax, [rdi+0E08h]
0x18001c4c7  mov     [rdi+0E10h], rax
0x18001c4ce  lea     r14, [rdi+0B28h]
0x18001c4d5  lea     r15, [r14+280h]
0x18001c4dc  jmp     short loc_18001C50F
0x18001c4de  lea     r8, [rbp+var_40]; unsigned __int16 **
0x18001c4e2  mov     rdx, r14; struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation *
0x18001c4e5  mov     rcx, rdi; this
0x18001c4e8  call    ?StopSuppliedEtwSession@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEAUEtwSessionInformation@1234@PEAPEBG@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::StopSuppliedEtwSession(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation &,ushort const * *)
0x18001c4ed  mov     esi, eax
0x18001c4ef  test    eax, eax
0x18001c4f1  js      loc_18001C642
0x18001c4f7  cmp     [rbp+var_40], 0
0x18001c4fc  jz      short loc_18001C50B
0x18001c4fe  lea     rdx, [rbp+var_40]
0x18001c502  lea     rcx, [rbp+var_38]
0x18001c506  call    ?push_back@?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAAXAEBQEBG@Z; std::vector<ushort const *>::push_back(ushort const * const &)
0x18001c50b  sub     r14, 0FFFFFFFFFFFFFF80h
0x18001c50f  cmp     r14, r15
0x18001c512  jnz     short loc_18001C4DE
0x18001c514  lfence
0x18001c517  xor     eax, eax
0x18001c519  xchg    al, [rdi+0DF9h]
0x18001c51f  mov     rcx, rbx; lpCriticalSection
0x18001c522  call    cs:__imp_LeaveCriticalSection
0x18001c528  mov     [rbp+var_10], 0
0x18001c530  lea     rdx, [rbp+var_10]; struct DhPackaging::IDhPackage **
0x18001c534  mov     rcx, rdi; this
0x18001c537  call    ?AfterStop@CollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@IEAAJPEAPEAUIDhPackage@DhPackaging@@@Z; Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::AfterStop(DhPackaging::IDhPackage * *)
0x18001c53c  mov     esi, eax
0x18001c53e  test    eax, eax
0x18001c540  js      loc_18001C74B
0x18001c546  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x18001c54b  mov     rcx, rax
0x18001c54e  test    rax, rax
0x18001c551  jz      loc_18001C795
0x18001c557  mov     rax, [rax]
0x18001c55a  mov     rax, [rax+18h]
0x18001c55e  call    cs:__guard_dispatch_icall_fptr
0x18001c564  lea     rbx, [rax+18h]
0x18001c568  mov     [rbp+var_40], rbx
0x18001c56c  mov     [rbp+bstr], 0
0x18001c574  cmp     [rbp+var_10], 0
0x18001c579  jz      loc_18001C62B
0x18001c57f  test    r12, r12
0x18001c582  jz      loc_18001C62B
0x18001c588  mov     rax, qword ptr [rbp+var_38+8]
0x18001c58c  cmp     qword ptr [rbp+var_38], rax
0x18001c590  jz      short loc_18001C5E7
0x18001c592  lfence
0x18001c595  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x18001c599  mov     rcx, [rdi+0F58h]; this
0x18001c5a0  call    ?GetDirectoryPath@SecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJPEAPEBG@Z; Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::GetDirectoryPath(ushort const * *)
0x18001c5a5  mov     esi, eax
0x18001c5a7  test    eax, eax
0x18001c5a9  js      loc_18001C71B
0x18001c5af  lfence
0x18001c5b2  mov     r8, [rbp+var_20]
0x18001c5b6  lea     rdx, aSscUserAuxEtl; "%ssc.user_aux.etl"
0x18001c5bd  lea     rcx, [rbp+var_40]
0x18001c5c1  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18001c5c6  mov     r9, [rbp+var_10]
0x18001c5ca  mov     rbx, [rbp+var_40]
0x18001c5ce  mov     r8, rbx
0x18001c5d1  lea     rdx, [rbp+var_38]
0x18001c5d5  mov     rcx, rdi
0x18001c5d8  call    ?AddEtwSessionResultsToPackage@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEAV?$vector@PEBGV?$allocator@PEBG@std@@@std@@PEBGPEAUIDhPackage@DhPackaging@@@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::AddEtwSessionResultsToPackage(std::vector<ushort const *> &,ushort const *,DhPackaging::IDhPackage *)
0x18001c5dd  mov     esi, eax
0x18001c5df  test    eax, eax
0x18001c5e1  js      loc_18001C71B
0x18001c5e7  lfence
0x18001c5ea  mov     rcx, [rdi+0A88h]; this
0x18001c5f1  test    rcx, rcx
0x18001c5f4  jz      short loc_18001C609
0x18001c5f6  mov     rdx, [rbp+var_10]; struct DhPackaging::IDhPackage *
0x18001c5fa  call    ?GetCurrentResult@ManagedInformationAgent@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJPEAUIDhPackage@DhPackaging@@@Z; Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::GetCurrentResult(DhPackaging::IDhPackage *)
0x18001c5ff  mov     esi, eax
0x18001c601  test    eax, eax
0x18001c603  js      loc_18001C71B
0x18001c609  lfence
0x18001c60c  mov     r8d, [rdi+35Ch]; unsigned int
0x18001c613  lea     r9, [rbp+bstr]; unsigned __int16 **
0x18001c617  mov     dl, 1; bool
0x18001c619  mov     rcx, rdi; this
0x18001c61c  call    ?CommitResult@CollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@IEAAJ_NIPEAPEAG@Z; Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::CommitResult(bool,uint,ushort * *)
0x18001c621  mov     esi, eax
0x18001c623  test    eax, eax
0x18001c625  js      loc_18001C71B
0x18001c62b  cmp     byte ptr [rdi+0F62h], 0
0x18001c632  jnz     loc_18001C6D5
0x18001c638  mov     rsi, qword ptr [rbp+var_38]
0x18001c63c  mov     r14, qword ptr [rbp+var_38+8]
0x18001c640  jmp     short loc_18001C692
0x18001c642  lfence
0x18001c645  mov     rcx, rbx; lpCriticalSection
0x18001c648  call    cs:__imp_LeaveCriticalSection
0x18001c64e  jmp     loc_18001C762
0x18001c653  mov     r15, [rsi]
0x18001c656  mov     rcx, r15; lpFileName
0x18001c659  call    cs:__imp_DeleteFileW
0x18001c65f  test    eax, eax
0x18001c661  jnz     short loc_18001C68E
0x18001c663  mov     rdi, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001c66a  call    cs:__imp_GetLastError
0x18001c670  mov     dword ptr [rsp+70h+var_50], eax
0x18001c674  mov     r9, r15
0x18001c677  lea     r8, aFailedToDelete_1; "Failed to delete ETL file: %s. Error co"...
0x18001c67e  lea     rdx, aDAWork1SSource_17; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001c685  lea     rcx, [rdi+38h]; this
0x18001c689  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001c68e  add     rsi, 8
0x18001c692  cmp     rsi, r14
0x18001c695  jnz     short loc_18001C653
0x18001c697  cmp     dword ptr [rbx-10h], 0
0x18001c69b  jle     short loc_18001C6D5
0x18001c69d  mov     rcx, rbx; lpFileName
0x18001c6a0  call    cs:__imp_DeleteFileW
0x18001c6a6  test    eax, eax
0x18001c6a8  jnz     short loc_18001C6D5
0x18001c6aa  mov     rdi, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001c6b1  call    cs:__imp_GetLastError
0x18001c6b7  mov     dword ptr [rsp+70h+var_50], eax
0x18001c6bb  mov     r9, rbx
0x18001c6be  lea     r8, aFailedToDelete; "Failed to delete merged ETL file: %s. E"...
0x18001c6c5  lea     rdx, aDAWork1SSource_17; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001c6cc  lea     rcx, [rdi+38h]; this
0x18001c6d0  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001c6d5  test    r12, r12
0x18001c6d8  jz      short loc_18001C719
0x18001c6da  mov     word ptr [r12], 8
0x18001c6e1  cmp     [rbp+bstr], 0
0x18001c6e6  jnz     short loc_18001C6EC
0x18001c6e8  xor     eax, eax
0x18001c6ea  jmp     short loc_18001C702
0x18001c6ec  mov     rcx, [rbp+bstr]; bstr
0x18001c6f0  call    cs:__imp_SysStringByteLen
0x18001c6f6  mov     edx, eax; len
0x18001c6f8  mov     rcx, [rbp+bstr]; psz
0x18001c6fc  call    cs:__imp_SysAllocStringByteLen
0x18001c702  mov     [r12+8], rax
0x18001c707  test    rax, rax
0x18001c70a  jnz     short loc_18001C719
0x18001c70c  cmp     [rbp+bstr], rax
0x18001c710  jz      short loc_18001C719
0x18001c712  mov     esi, 8007000Eh
0x18001c717  jmp     short loc_18001C71B
0x18001c719  xor     esi, esi
0x18001c71b  mov     rcx, [rbp+bstr]; bstrString
0x18001c71f  call    cs:__imp_SysFreeString
0x18001c725  nop
0x18001c726  lea     rdx, [rbx-18h]
0x18001c72a  or      eax, 0FFFFFFFFh
0x18001c72d  lock xadd [rdx+10h], eax
0x18001c732  sub     eax, 1
0x18001c735  jg      short loc_18001C74B
0x18001c737  lfence
0x18001c73a  mov     rcx, [rdx]
0x18001c73d  mov     rax, [rcx]
0x18001c740  mov     rax, [rax+8]
0x18001c744  call    cs:__guard_dispatch_icall_fptr
0x18001c74a  nop
0x18001c74b  mov     rcx, [rbp+var_10]
0x18001c74f  test    rcx, rcx
0x18001c752  jz      short loc_18001C762
0x18001c754  mov     rdx, [rcx]
0x18001c757  mov     rax, [rdx+10h]
0x18001c75b  call    cs:__guard_dispatch_icall_fptr
0x18001c761  nop
0x18001c762  lfence
0x18001c765  lea     rcx, [rbp+var_38]
0x18001c769  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorMessageAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(void)
0x18001c76e  mov     eax, esi
0x18001c770  mov     rcx, [rbp+var_8]
0x18001c774  xor     rcx, rsp; StackCookie
0x18001c777  call    __security_check_cookie
0x18001c77c  lea     r11, [rsp+70h+var_s0]
0x18001c781  mov     rbx, [r11+40h]
0x18001c785  mov     rsi, [r11+48h]
0x18001c789  mov     rsp, r11
0x18001c78c  pop     r15
0x18001c78e  pop     r14
0x18001c790  pop     r12
0x18001c792  pop     rdi
0x18001c793  pop     rbp
0x18001c794  retn
0x18001c795  mov     ecx, 80004005h; int
0x18001c79a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
