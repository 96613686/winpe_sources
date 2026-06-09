# win_musl::InternalPartReceiverCom<win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>,IWin7InternalPartReceiver,win_musl::detail::CloseableCom<win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>,IWin7InternalPartReceiver,win_musl::InnerCom<win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>,IWin7InternalPartReceiver,win_scope::report_policy_throw>>>::AddOpcStream_Safe(wchar_t const *,__MIDL___MIDL_itf_opc2Eio_0000_0000_0002,__MIDL___MIDL_itf_dox2Ebase_0000_0000_0002,IByteCollection *,__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 const *)

- ea: `0x1800137d0`
- end: `0x180013d35`
- name: `?AddOpcStream_Safe@?$InternalPartReceiverCom@V?$scope@PEAVContainerSender@consumption@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@UIWin7InternalPartReceiver@@V?$CloseableCom@V?$scope@PEAVContainerSender@consumption@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@UIWin7InternalPartReceiver@@V?$InnerCom@V?$scope@PEAVContainerSender@consumption@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@UIWin7InternalPartReceiver@@Ureport_policy_throw@2@@win_musl@@@detail@win_musl@@@win_musl@@AEAAXPEB_WW4__MIDL___MIDL_itf_opc2Eio_0000_0000_0002@@U__MIDL___MIDL_itf_dox2Ebase_0000_0000_0002@@PEAUIByteCollection@@PEBU__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005@@@Z`
- size: `1381`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180082668`

## callees

- `0x1800016b0`
- `0x180005d50`
- `0x180013384`
- `0x1800137d0`
- `0x180013d3c`
- `0x180015114`
- `0x180015180`
- `0x1800155e8`
- `0x1800156a4`
- `0x180015af4`
- `0x180018c2c`
- `0x18001c5d0`
- `0x18001ca9c`
- `0x1800517a0`
- `0x18005ab90`
- `0x18007e450`
- `0x18009c21c`
- `0x1800cce54`
- `0x1800cd38c`
- `0x1800cdb60`
- `0x1800cdbbc`
- `0x1800d04d8`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001395a`
- `msvcrt!memcpy_s` at `0x18001395a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013998`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013998`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013b37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013b37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013985`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013985`

## string_xrefs

- `0x18001385a`: `Failed or Close already called on this receiver`
- `0x180013c4e`: `compressionOptions`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall win_musl::InternalPartReceiverCom<win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>,IWin7InternalPartReceiver,win_musl::detail::CloseableCom<win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>,IWin7InternalPartReceiver,win_musl::InnerCom<win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>,IWin7InternalPartReceiver,win_scope::report_policy_throw>>>::AddOpcStream_Safe(
        __int64 a1,
        _WORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  int v6; // r14d
  __int64 v9; // r15
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rdi
  void **v12; // rcx
  void **v13; // rcx
  bool v14; // dl
  win_dox *v15; // rcx
  void *v16; // rax
  int v17; // edx
  const char *v18; // r8
  unsigned int v19; // r9d
  volatile signed __int32 *v20; // rax
  volatile signed __int32 *v21; // rbx
  __int64 v22; // rdx
  volatile signed __int32 *v23; // rcx
  __int64 v24; // r14
  __int64 v26; // rsi
  __int128 *v27; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v28; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v29; // [rsp+60h] [rbp-A8h] BYREF
  void **v30; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v31[3]; // [rsp+78h] [rbp-90h] BYREF
  char v32[8]; // [rsp+90h] [rbp-78h] BYREF
  void *Destination[2]; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int64 v34; // [rsp+A8h] [rbp-60h]
  unsigned __int64 v35; // [rsp+B0h] [rbp-58h]
  _BYTE v36[48]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v38[160]; // [rsp+128h] [rbp+20h] BYREF

  v31[1] = -2;
  v6 = a3;
  if ( !a2 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      a3,
      54,
      L"IWin7InternalPartReceiver",
      L"AddPart",
      L"logicalItemName",
      0);
  if ( (_DWORD)a3 != -1 && (_DWORD)a3 && (_DWORD)a3 != 3 && (_DWORD)a3 != 1 && (_DWORD)a3 != 2 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      a3,
      69,
      L"IWin7InternalPartReceiver",
      L"AddPart",
      L"compressionOptions",
      2);
  if ( !a5 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      a3,
      76,
      L"IWin7InternalPartReceiver",
      L"AddPart",
      L"pIInternalByteCollection",
      0);
  if ( !*(_QWORD *)(a1 + 8) || dword_1801C4E50 == -1 )
  {
    win_musl::DebugLogHelper(
      "(no filename)",
      &word_18013A0B6,
      80,
      1024,
      -2147418113,
      L"Failed or Close already called on this receiver");
    std::string::string(v36, "Program has entered an unexpected state");
    std::logic_error::logic_error(pExceptionObject, v36);
    throw (std::logic_error *)pExceptionObject;
  }
  win_dox::to_interface<IReceiver>::resolve(v31, a5);
  v30 = &win_dox::OpcRelationshipCollection::`vftable';
  v9 = *(_QWORD *)(a1 + 8);
  v10 = 7;
  v35 = 7;
  v34 = 0;
  LOWORD(Destination[0]) = 0;
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  if ( v11 > 0x7FFFFFFFFFFFFFFELL )
    std::_String_base::_Xlen();
  if ( v11 > 7 )
  {
    std::wstring::_Copy(v32, v11, 0);
    v10 = v35;
  }
  else if ( !v11 )
  {
    v34 = 0;
    LOWORD(Destination[0]) = 0;
    goto LABEL_19;
  }
  v12 = Destination;
  if ( v10 >= 8 )
    v12 = (void **)Destination[0];
  memcpy_s(v12, 2 * v10, a2, 2 * v11);
  v13 = Destination;
  if ( v35 >= 8 )
    v13 = (void **)Destination[0];
  v34 = v11;
  *((_WORD *)v13 + v11) = 0;
LABEL_19:
  v31[2] = v9 + 200;
  EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 200));
  v15 = (win_dox *)*(unsigned int *)(v9 + 244);
  *(_DWORD *)(v9 + 244) = (_DWORD)v15 + 1;
  if ( !(_DWORD)v15 )
    *(_DWORD *)(v9 + 240) = GetCurrentThreadId();
  LOBYTE(v15) = *(_BYTE *)(v9 + 256);
  win_dox::ThrowIfFailed(v15, v14);
  v16 = operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v16 )
    SplException::RealThrowFromHR((SplException *)0x8007000ELL, v17, v18, v19);
  v26 = win_musl::consumption::MetroConsumptionState::ByteCollectionHolder::ByteCollectionHolder(
          (_DWORD)v16,
          (unsigned int)v32,
          v6,
          (unsigned int)&v30,
          a6);
  v29 = 0;
  v27 = (__int128 *)v26;
  if ( v26 )
  {
    v20 = (volatile signed __int32 *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v21 = v20;
    if ( !v20 )
    {
      win_scope::close_delete::close<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder>(&v27);
      win_scope::report_policy_throw::report_init_failure();
    }
    *((_QWORD *)v20 + 1) = 0;
    *(_QWORD *)v20 = &win_scope::counted_strong_weak<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::resource_policies>>::`vftable';
    *((_QWORD *)v20 + 2) = v26;
    *(_QWORD *)&v29 = v20;
    if ( _InterlockedIncrement(v20 + 2) == 1 )
      _InterlockedAdd(v20 + 3, 1u);
    *((_QWORD *)&v29 + 1) = v26;
    v22 = v26;
    v23 = v20;
  }
  else
  {
    v23 = 0;
    v22 = 0;
    v26 = *((_QWORD *)&v29 + 1);
    v21 = (volatile signed __int32 *)v29;
  }
  v24 = *(_QWORD *)(v9 + 64);
  v28 = 0;
  if ( v23 )
  {
    if ( _InterlockedIncrement(v23 + 2) == 1 )
      _InterlockedAdd(v23 + 3, 1u);
    *(_QWORD *)&v28 = v23;
    *((_QWORD *)&v28 + 1) = v22;
  }
  v27 = &v28;
  if ( *(_BYTE *)(v24 + 44) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)v38,
      0x39u,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"no more messages allowed");
    throw (SplException::THResultException *)v38;
  }
  std::deque<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>>::push_back(
    v24 + 400,
    &v28);
  win_musl::MessageHandlerCoordinator<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_mp_lib::type_list<win_musl::KeyedMessageHandler<std::wstring,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>,win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>>::TestDerecurse(v24 + 40);
  if ( *((_QWORD *)&v28 + 1) && (_QWORD)v28 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v28);
  if ( v21 && v26 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v29);
  if ( (*(_DWORD *)(v9 + 244))-- == 1 )
    *(_DWORD *)(v9 + 240) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 200));
  if ( v35 >= 8 )
    operator delete(Destination[0]);
  if ( v31[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v31[0] + 16LL))(v31[0]);
}

```

## disassembly

```asm
0x1800137d0  mov     rax, rsp
0x1800137d3  push    rbp
0x1800137d4  push    rsi
0x1800137d5  push    rdi
0x1800137d6  push    r12
0x1800137d8  push    r13
0x1800137da  push    r14
0x1800137dc  push    r15
0x1800137de  lea     rbp, [rax-108h]
0x1800137e5  sub     rsp, 1D0h
0x1800137ec  mov     qword ptr [rsp+78h], 0FFFFFFFFFFFFFFFEh
0x1800137f5  mov     [rax+20h], rbx
0x1800137f9  mov     rax, cs:__security_cookie
0x180013800  xor     rax, rsp
0x180013803  mov     [rbp+100h+var_40], rax
0x18001380a  mov     r14d, r8d
0x18001380d  mov     rsi, rdx
0x180013810  mov     rbx, rcx
0x180013813  mov     rdx, [rbp+100h+arg_20]
0x18001381a  mov     r12, [rbp+100h+arg_28]
0x180013821  xor     r13d, r13d
0x180013824  test    rsi, rsi
0x180013827  jz      loc_180013BF6
0x18001382d  cmp     r8d, 0FFFFFFFFh
0x180013831  jz      short loc_180013842
0x180013833  test    r8d, r8d
0x180013836  jz      short loc_180013842
0x180013838  cmp     r8d, 3
0x18001383c  jnz     loc_180013C32
0x180013842  test    rdx, rdx
0x180013845  jz      loc_180013C85
0x18001384b  cmp     [rcx+8], r13
0x18001384f  jz      short loc_18001385A
0x180013851  cmp     cs:dword_1801C4E50, 0FFFFFFFFh
0x180013858  jnz     short loc_1800138BC
0x18001385a  lea     rax, aFailedOrCloseA; "Failed or Close already called on this "...
0x180013861  mov     qword ptr [rsp+200h+var_1D8], rax
0x180013866  mov     [rsp+200h+var_1E0], 8000FFFFh
0x18001386e  mov     r9d, 400h
0x180013874  mov     r8d, 50h ; 'P'
0x18001387a  lea     rdx, word_18013A0B6
0x180013881  lea     rcx, aNoFilename; "(no filename)"
0x180013888  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x18001388d  lea     rdx, aProgramHasEnte; "Program has entered an unexpected state"
0x180013894  lea     rcx, [rbp+100h+var_150]
0x180013898  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x18001389d  nop
0x18001389e  lea     rdx, [rbp+100h+var_150]
0x1800138a2  lea     rcx, [rbp+100h+pExceptionObject]
0x1800138a6  call    ??0logic_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::logic_error::logic_error(std::string const &)
0x1800138ab  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x1800138b2  lea     rcx, [rbp+100h+pExceptionObject]; pExceptionObject
0x1800138b6  call    _CxxThrowException_0
0x1800138bc  lea     rax, ??_7OpcRelationshipSender@win_dox@@6B@; const win_dox::OpcRelationshipSender::`vftable'
0x1800138c3  mov     [rsp+200h+var_198], rax
0x1800138c8  lea     rcx, [rsp+200h+var_190]
0x1800138cd  call    ?resolve@?$to_interface@UIReceiver@@@win_dox@@SA?AV?$scope@PEAUIReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIReceiver@@@Z; win_dox::to_interface<IReceiver>::resolve(IReceiver *)
0x1800138d2  lea     rax, ??_7OpcRelationshipCollection@win_dox@@6B@; const win_dox::OpcRelationshipCollection::`vftable'
0x1800138d9  mov     [rsp+200h+var_198], rax
0x1800138de  mov     r15, [rbx+8]
0x1800138e2  mov     edx, 7
0x1800138e7  mov     [rbp+100h+var_158], rdx
0x1800138eb  mov     r8, r13
0x1800138ee  mov     [rbp+100h+var_160], r13
0x1800138f2  mov     word ptr [rbp+100h+Destination], r13w
0x1800138f7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800138fb  inc     rdi
0x1800138fe  cmp     [rsi+rdi*2], r13w
0x180013903  jnz     short loc_1800138FB
0x180013905  lea     rax, [rbp+100h+Destination]
0x180013909  cmp     rsi, rax
0x18001390c  jb      short loc_18001391B
0x18001390e  lea     rax, [rbp+100h+Destination]
0x180013912  cmp     rax, rsi
0x180013915  ja      loc_1800139EC
0x18001391b  mov     rax, 7FFFFFFFFFFFFFFEh
0x180013925  cmp     rdi, rax
0x180013928  ja      loc_180013CCF
0x18001392e  cmp     rdx, rdi
0x180013931  jb      loc_1800139D2
0x180013937  test    rdi, rdi
0x18001393a  jz      loc_180013A2A
0x180013940  lea     rcx, [rbp+100h+Destination]
0x180013944  cmp     rdx, 8
0x180013948  cmovnb  rcx, [rbp+100h+Destination]; Destination
0x18001394d  lea     rbx, [rdi+rdi]
0x180013951  add     rdx, rdx; DestinationSize
0x180013954  mov     r9, rbx; SourceSize
0x180013957  mov     r8, rsi; Source
0x18001395a  call    cs:__imp_memcpy_s
0x180013960  lea     rcx, [rbp+100h+Destination]
0x180013964  cmp     [rbp+100h+var_158], 8
0x180013969  cmovnb  rcx, [rbp+100h+Destination]
0x18001396e  mov     [rbp+100h+var_160], rdi
0x180013972  mov     [rcx+rbx], r13w
0x180013977  lea     rdi, [r15+0C8h]
0x18001397e  mov     [rbp+100h+var_180], rdi
0x180013982  mov     rcx, rdi; lpCriticalSection
0x180013985  call    cs:__imp_EnterCriticalSection
0x18001398b  mov     ecx, [rdi+2Ch]
0x18001398e  lea     eax, [rcx+1]
0x180013991  mov     [rdi+2Ch], eax
0x180013994  test    ecx, ecx
0x180013996  jnz     short loc_1800139A1
0x180013998  call    cs:__imp_GetCurrentThreadId
0x18001399e  mov     [rdi+28h], eax
0x1800139a1  mov     cl, [r15+100h]; this
0x1800139a8  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x1800139ad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800139b4  mov     ecx, 88h; unsigned __int64
0x1800139b9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800139be  test    rax, rax
0x1800139c1  jnz     loc_180013BA5
0x1800139c7  mov     ecx, 8007000Eh; this
0x1800139cc  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800139d2  mov     rdx, rdi
0x1800139d5  lea     rcx, [rbp+100h+var_178]
0x1800139d9  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x1800139de  mov     rdx, [rbp+100h+var_158]
0x1800139e2  test    rdi, rdi
0x1800139e5  jz      short loc_180013977
0x1800139e7  jmp     loc_180013940
0x1800139ec  lea     rax, [rbp+100h+Destination]
0x1800139f0  sub     rsi, rax
0x1800139f3  sar     rsi, 1
0x1800139f6  jnz     loc_180013CC1
0x1800139fc  sub     r8, rsi
0x1800139ff  cmp     rdi, r8
0x180013a02  cmovb   r8, rdi
0x180013a06  lea     rdx, [rsi+r8]
0x180013a0a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180013a0e  lea     rcx, [rbp+100h+var_178]
0x180013a12  call    ?erase@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x180013a17  mov     r8, rsi
0x180013a1a  xor     edx, edx
0x180013a1c  lea     rcx, [rbp+100h+var_178]
0x180013a20  call    ?erase@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x180013a25  jmp     loc_180013977
0x180013a2a  lea     rcx, [rbp+100h+Destination]
0x180013a2e  cmp     rdx, 8
0x180013a32  cmovnb  rcx, [rbp+100h+Destination]
0x180013a37  mov     [rbp+100h+var_160], r13
0x180013a3b  mov     [rcx], r13w
0x180013a3f  jmp     loc_180013977
0x180013a44  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013a4b  mov     ecx, 18h; unsigned __int64
0x180013a50  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180013a55  mov     rbx, rax
0x180013a58  test    rax, rax
0x180013a5b  jz      loc_180013CE1
0x180013a61  mov     [rax+8], r13
0x180013a65  lea     rax, ??_7?$counted_strong_weak@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@6B@; const win_scope::counted_strong_weak<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::resource_policies>>::`vftable'
0x180013a6c  mov     [rbx], rax
0x180013a6f  mov     [rbx+10h], rsi
0x180013a73  mov     qword ptr [rsp+200h+var_1B0+8], rbx
0x180013a78  mov     r8d, 1
0x180013a7e  mov     ecx, r8d
0x180013a81  lock xadd [rbx+8], ecx
0x180013a86  add     ecx, r8d
0x180013a89  cmp     ecx, r8d
0x180013a8c  jz      loc_180013B90
0x180013a92  mov     [rsp+200h+var_1A0], rsi
0x180013a97  mov     rdx, rsi
0x180013a9a  mov     rcx, rbx
0x180013a9d  mov     r14, [r15+40h]
0x180013aa1  xorps   xmm0, xmm0
0x180013aa4  movdqu  [rsp+200h+var_1C0+8], xmm0
0x180013aaa  test    rcx, rcx
0x180013aad  jz      short loc_180013ACD
0x180013aaf  mov     eax, r8d
0x180013ab2  lock xadd [rcx+8], eax
0x180013ab7  add     eax, r8d
0x180013aba  cmp     eax, r8d
0x180013abd  jz      loc_180013B86
0x180013ac3  mov     qword ptr [rsp+200h+var_1C0+8], rcx
0x180013ac8  mov     qword ptr [rsp+200h+var_1B0], rdx
0x180013acd  lea     rax, [rsp+200h+var_1C0+8]
0x180013ad2  mov     qword ptr [rsp+200h+var_1C0], rax
0x180013ad7  cmp     [r14+2Ch], r13b
0x180013adb  jnz     loc_180013CF1
0x180013ae1  lea     rcx, [r14+190h]
0x180013ae8  lea     rdx, [rsp+200h+var_1C0+8]
0x180013aed  call    ?push_back@?$deque@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$allocator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@QEAAXAEBV?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; std::deque<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>>::push_back(win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>> const &)
0x180013af2  lea     rcx, [r14+28h]
0x180013af6  call    ?TestDerecurse@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@AEAAXXZ; win_musl::MessageHandlerCoordinator<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_mp_lib::type_list<win_musl::KeyedMessageHandler<std::wstring,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>,win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>>::TestDerecurse(void)
0x180013afb  nop
0x180013afc  cmp     qword ptr [rsp+200h+var_1B0], r13
0x180013b01  jz      short loc_180013B15
0x180013b03  cmp     qword ptr [rsp+200h+var_1C0+8], r13
0x180013b08  jz      short loc_180013B15
0x180013b0a  lea     rcx, [rsp+200h+var_1C0+8]
0x180013b0f  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180013b14  nop
0x180013b15  test    rbx, rbx
0x180013b18  jz      short loc_180013B2A
0x180013b1a  test    rsi, rsi
0x180013b1d  jz      short loc_180013B2A
0x180013b1f  lea     rcx, [rsp+200h+var_1B0+8]
0x180013b24  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180013b29  nop
0x180013b2a  add     dword ptr [rdi+2Ch], 0FFFFFFFFh
0x180013b2e  jnz     short loc_180013B34
0x180013b30  mov     [rdi+28h], r13d
0x180013b34  mov     rcx, rdi; lpCriticalSection
0x180013b37  call    cs:__imp_LeaveCriticalSection
0x180013b3d  nop
0x180013b3e  cmp     [rbp+100h+var_158], 8
0x180013b43  jnb     short loc_180013B9A
0x180013b45  mov     rcx, [rsp+200h+var_190]
0x180013b4a  test    rcx, rcx
0x180013b4d  jz      short loc_180013B5C
0x180013b4f  mov     rax, [rcx]
0x180013b52  mov     rax, [rax+10h]
0x180013b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b5b  nop
0x180013b5c  mov     rcx, [rbp+100h+var_40]
0x180013b63  xor     rcx, rsp; StackCookie
0x180013b66  call    __security_check_cookie
0x180013b6b  mov     rbx, [rsp+200h+arg_18]
0x180013b73  add     rsp, 1D0h
0x180013b7a  pop     r15
0x180013b7c  pop     r14
0x180013b7e  pop     r13
0x180013b80  pop     r12
0x180013b82  pop     rdi
0x180013b83  pop     rsi
0x180013b84  pop     rbp
0x180013b85  retn
0x180013b86  lock add [rcx+0Ch], r8d
0x180013b8b  jmp     loc_180013AC3
0x180013b90  lock add [rbx+0Ch], r8d
0x180013b95  jmp     loc_180013A92
0x180013b9a  mov     rcx, [rbp+100h+Destination]; Block
0x180013b9e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013ba3  jmp     short loc_180013B45
0x180013ba5  mov     qword ptr [rsp+200h+var_1C0], rax
0x180013baa  mov     qword ptr [rsp+200h+var_1E0], r12
0x180013baf  lea     r9, [rsp+200h+var_198]
0x180013bb4  mov     r8d, r14d
0x180013bb7  lea     rdx, [rbp+100h+var_178]
0x180013bbb  mov     rcx, rax
0x180013bbe  call    ??0ByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@W4__MIDL___MIDL_itf_opc2Eio_0000_0000_0002@@AEAVByteCollection@win_dox@@PEBU__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005@@@Z; win_musl::consumption::MetroConsumptionState::ByteCollectionHolder::ByteCollectionHolder(std::wstring const &,__MIDL___MIDL_itf_opc2Eio_0000_0000_0002,win_dox::ByteCollection &,__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 const *)
0x180013bc3  mov     rsi, rax
0x180013bc6  xorps   xmm0, xmm0
0x180013bc9  movdqu  [rsp+200h+var_1B0+8], xmm0
0x180013bcf  mov     qword ptr [rsp+200h+var_1C0], rax
0x180013bd4  test    rax, rax
0x180013bd7  jnz     loc_180013A44
0x180013bdd  mov     rcx, r13
0x180013be0  mov     rdx, r13
0x180013be3  mov     rsi, [rsp+200h+var_1A0]
0x180013be8  mov     rbx, qword ptr [rsp+200h+var_1B0+8]
0x180013bed  lea     r8d, [rax+1]
0x180013bf1  jmp     loc_180013A9D
0x180013bf6  mov     dword ptr [rsp+200h+var_1C8], r13d
0x180013bfb  lea     rax, aLogicalitemnam; "logicalItemName"
0x180013c02  mov     [rsp+200h+var_1D0], rax
0x180013c07  lea     rax, aAddpart; "AddPart"
0x180013c0e  mov     qword ptr [rsp+200h+var_1D8], rax
0x180013c13  lea     rax, aIwin7internalp; "IWin7InternalPartReceiver"
0x180013c1a  mov     qword ptr [rsp+200h+var_1E0], rax
0x180013c1f  mov     r9d, 36h ; '6'
0x180013c25  lea     rdx, aNoFilename; "(no filename)"
0x180013c2c  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180013c32  cmp     r14d, 1
0x180013c36  jz      loc_180013842
0x180013c3c  cmp     r14d, 2
0x180013c40  jz      loc_180013842
0x180013c46  mov     dword ptr [rsp+200h+var_1C8], 2
0x180013c4e  lea     rax, aCompressionopt_2; "compressionOptions"
0x180013c55  mov     [rsp+200h+var_1D0], rax
0x180013c5a  lea     rax, aAddpart; "AddPart"
0x180013c61  mov     qword ptr [rsp+200h+var_1D8], rax
0x180013c66  lea     rax, aIwin7internalp; "IWin7InternalPartReceiver"
0x180013c6d  mov     qword ptr [rsp+200h+var_1E0], rax
0x180013c72  mov     r9d, 45h ; 'E'
0x180013c78  lea     rdx, aNoFilename; "(no filename)"
0x180013c7f  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180013c85  mov     dword ptr [rsp+200h+var_1C8], r13d
0x180013c8a  lea     rax, aPiinternalbyte; "pIInternalByteCollection"
0x180013c91  mov     [rsp+200h+var_1D0], rax
0x180013c96  lea     rax, aAddpart; "AddPart"
0x180013c9d  mov     qword ptr [rsp+200h+var_1D8], rax
0x180013ca2  lea     rax, aIwin7internalp; "IWin7InternalPartReceiver"
0x180013ca9  mov     qword ptr [rsp+200h+var_1E0], rax
0x180013cae  mov     r9d, 4Ch ; 'L'
0x180013cb4  lea     rdx, aNoFilename; "(no filename)"
0x180013cbb  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180013cc1  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x180013cc6  mov     r8, [rbp+100h+var_160]
0x180013cca  jmp     loc_1800139FC
0x180013ccf  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x180013cd4  mov     rdx, [rbp+100h+var_158]
0x180013cd8  mov     r8, [rbp+100h+var_160]
0x180013cdc  jmp     loc_18001392E
0x180013ce1  lea     rcx, [rsp+200h+var_1C0]
0x180013ce6  call    ??$close@VByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@@close_delete@win_scope@@SAXPEAPEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@@Z; win_scope::close_delete::close<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder>(win_musl::consumption::MetroConsumptionState::ByteCollectionHolder * *)
0x180013ceb  call    ?report_init_failure@report_policy_throw@win_scope@@SAXXZ; win_scope::report_policy_throw::report_init_failure(void)
0x180013cf1  lea     rax, aNoMoreMessages; "no more messages allowed"
0x180013cf8  mov     [rsp+200h+var_1D0], rax; struct win_musl::TStringEllipseBase *
  ... truncated ...
```
