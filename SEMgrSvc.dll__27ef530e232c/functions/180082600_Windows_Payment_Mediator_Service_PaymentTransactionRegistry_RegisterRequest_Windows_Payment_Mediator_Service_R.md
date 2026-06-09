# Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegisterRequest(Windows::Payment::Mediator::Service::RpcCallManager &,std::shared_ptr<Windows::Payment::Mediator::Service::PaymentRequestTransaction>)

- ea: `0x180082600`
- end: `0x18008294b`
- name: `?RegisterRequest@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@QEAAIAEAVRpcCallManager@2345@V?$shared_ptr@VPaymentRequestTransaction@Service@Mediator@Payment@Windows@@@std@@@Z`
- size: `843`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180083308`

## callees

- `0x18000c944`
- `0x18000c964`
- `0x180065a0c`
- `0x180081dc4`
- `0x180082014`
- `0x180082384`
- `0x180082600`
- `0x180082d30`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008277d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800828ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008277d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800828ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180082736`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180082736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082829`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008283c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008283c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180082631`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180082631`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800826ba`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800826ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800826dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082787`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082834`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800826dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082787`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082834`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008263d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008263d`
- `bcrypt!BCryptGenRandom` at `0x180082750`
- `bcrypt!BCryptGenRandom` at `0x180082750`

## string_xrefs

- `0x180082655`: `onecoreuap\ds\nfc\product\payment\service\lib\paymenttransactionregistry.cpp`
- `0x1800826c8`: `onecoreuap\ds\nfc\product\payment\service\lib\paymenttransactionregistry.cpp`
- `0x180082761`: `onecoreuap\ds\nfc\product\payment\service\lib\paymenttransactionregistry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegisterRequest(
        LPCRITICAL_SECTION lpCriticalSection,
        __int64 a2,
        _QWORD *a3)
{
  DWORD LengthSid; // ebx
  HLOCAL v7; // rax
  void *v8; // rdi
  volatile signed __int32 *v9; // rdi
  const char *v11; // r9
  unsigned int v12; // r14d
  volatile signed __int32 *v13; // rdi
  NTSTATUS v14; // eax
  __int64 v15; // r12
  unsigned int i; // ebx
  __int64 v17; // rax
  void *v18; // r13
  void *v19; // rbx
  void **v20; // r14
  void *v21; // r12
  DWORD LastError; // ebx
  volatile signed __int32 *v23; // rdi
  __int64 v24; // rdx
  _QWORD *v25; // rax
  volatile signed __int32 *v26; // rdi
  void *v27; // [rsp+20h] [rbp-40h] BYREF
  _QWORD v28[2]; // [rsp+28h] [rbp-38h] BYREF
  char v29[16]; // [rsp+38h] [rbp-28h] BYREF
  void *v30; // [rsp+48h] [rbp-18h] BYREF
  __int128 v31; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  __int64 v33; // [rsp+A8h] [rbp+48h] BYREF
  _QWORD *v34; // [rsp+B0h] [rbp+50h]
  unsigned int pbBuffer; // [rsp+B8h] [rbp+58h] BYREF

  v34 = a3;
  v33 = a2;
  LengthSid = GetLengthSid(**(PSID **)(a2 + 32));
  v7 = LocalAlloc(0, LengthSid);
  v8 = v7;
  if ( v7 )
  {
    if ( CopySid(LengthSid, v7, **(PSID **)(a2 + 32)) )
    {
      pbBuffer = 0;
      EnterCriticalSection(lpCriticalSection);
      v28[0] = lpCriticalSection;
      v14 = BCryptGenRandom(0, (PUCHAR)&pbBuffer, 4u, 2u);
      if ( v14 >= 0 )
      {
        v15 = *(_QWORD *)&lpCriticalSection[1].LockCount;
        for ( i = pbBuffer;
              !i
           || *(_QWORD *)std::_Hash<std::_Umap_traits<unsigned int,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>,0>>::find(
                           &lpCriticalSection[1],
                           &v27,
                           &pbBuffer) != v15;
              pbBuffer = i )
        {
          ++i;
        }
        v30 = v8;
        v28[1] = 0;
        v17 = a3[1];
        if ( v17 )
          _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
        v18 = (void *)*a3;
        *(_QWORD *)&v31 = *a3;
        v19 = (void *)a3[1];
        v27 = v19;
        *((_QWORD *)&v31 + 1) = v19;
        v20 = (void **)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned int,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>,0>>::_Try_emplace<unsigned int const &,>(
                                     &lpCriticalSection[1],
                                     v29,
                                     &pbBuffer)
                      + 24LL);
        if ( v20 != &v30 )
        {
          v21 = *v20;
          if ( *v20 )
          {
            LastError = GetLastError();
            LocalFree(v21);
            SetLastError(LastError);
            v19 = v27;
          }
          *v20 = v8;
          v30 = 0;
        }
        v31 = 0;
        v20[1] = v18;
        v23 = (volatile signed __int32 *)v20[2];
        v20[2] = v19;
        if ( v23 )
        {
          if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
            if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
          }
        }
        Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry::~RegistryEntry((Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry *)&v30);
        v27 = *(void **)(v33 + 48);
        v24 = *a3;
        v25 = (_QWORD *)(*a3 + 80LL);
        if ( *(_QWORD *)(*a3 + 104LL) > 7u )
          v25 = (_QWORD *)*v25;
        v28[0] = v25;
        LODWORD(v33) = *(_DWORD *)(v24 + 72);
        ((void (__fastcall *)(__int64 *, __int64, _QWORD *, void **))Windows::Payment::Mediator::Service::PaymentLoggingProvider::PaymentRequestRegistered<unsigned int,_GUID const &,unsigned short const *,unsigned short const *>)(
          &v33,
          v24 + 56,
          v28,
          &v27);
        LeaveCriticalSection(lpCriticalSection);
        v12 = pbBuffer;
        v26 = (volatile signed __int32 *)a3[1];
        if ( v26 )
        {
          if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
            if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
          }
        }
        return v12;
      }
      v12 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x2D,
              (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\paymenttransactionregistry.cpp",
              (const char *)(unsigned int)v14,
              (int)v27);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      LocalFree(v8);
      v13 = (volatile signed __int32 *)a3[1];
      if ( v13 )
        goto LABEL_9;
    }
    else
    {
      v12 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x21,
              (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\paymenttransactionregistry.cpp",
              v11);
      LocalFree(v8);
      v13 = (volatile signed __int32 *)a3[1];
      if ( v13 )
      {
LABEL_9:
        if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
    }
    return v12;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x20,
    (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\paymenttransactionregistry.cpp",
    (const char *)0x8007000ELL,
    (int)v27);
  v9 = (volatile signed __int32 *)a3[1];
  if ( v9 && _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
    if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180082600  mov     [rsp-38h+arg_0], rbx
0x180082605  mov     [rsp-38h+arg_10], r8
0x18008260a  mov     [rsp-38h+arg_8], rdx
0x18008260f  push    rbp
0x180082610  push    rsi
0x180082611  push    rdi
0x180082612  push    r12
0x180082614  push    r13
0x180082616  push    r14
0x180082618  push    r15
0x18008261a  mov     rbp, rsp
0x18008261d  sub     rsp, 60h
0x180082621  mov     rsi, r8
0x180082624  mov     r14, rdx
0x180082627  mov     r15, rcx
0x18008262a  mov     rcx, [rdx+20h]
0x18008262e  mov     rcx, [rcx]; pSid
0x180082631  call    cs:__imp_GetLengthSid
0x180082637  mov     ebx, eax
0x180082639  mov     edx, eax; uBytes
0x18008263b  xor     ecx, ecx; uFlags
0x18008263d  call    cs:__imp_LocalAlloc
0x180082643  mov     rdi, rax
0x180082646  test    rax, rax
0x180082649  jnz     short loc_1800826AE
0x18008264b  mov     rcx, [rbp+38h]; this
0x18008264f  mov     r9d, 8007000Eh; char *
0x180082655  lea     r8, aOnecoreuapDsNf_49; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x18008265c  lea     edx, [rax+20h]; void *
0x18008265f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082664  nop
0x180082665  mov     rdi, [rsi+8]
0x180082669  test    rdi, rdi
0x18008266c  jz      short loc_1800826A4
0x18008266e  or      ebx, 0FFFFFFFFh
0x180082671  mov     eax, ebx
0x180082673  lock xadd [rdi+8], eax
0x180082678  add     eax, ebx
0x18008267a  jnz     short loc_1800826A4
0x18008267c  mov     rax, [rdi]
0x18008267f  mov     rcx, rdi
0x180082682  mov     rax, [rax]
0x180082685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008268a  mov     eax, ebx
0x18008268c  lock xadd [rdi+0Ch], eax
0x180082691  add     eax, ebx
0x180082693  jnz     short loc_1800826A4
0x180082695  mov     rax, [rdi]
0x180082698  mov     rcx, rdi
0x18008269b  mov     rax, [rax+8]
0x18008269f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800826a4  mov     eax, 8007000Eh
0x1800826a9  jmp     loc_180082933
0x1800826ae  mov     r8, [r14+20h]
0x1800826b2  mov     r8, [r8]; pSourceSid
0x1800826b5  mov     rdx, rdi; pDestinationSid
0x1800826b8  mov     ecx, ebx; nDestinationSidLength
0x1800826ba  call    cs:__imp_CopySid
0x1800826c0  test    eax, eax
0x1800826c2  jnz     short loc_18008272C
0x1800826c4  mov     rcx, [rbp+38h]; this
0x1800826c8  lea     r8, aOnecoreuapDsNf_49; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x1800826cf  lea     edx, [rax+21h]; void *
0x1800826d2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800826d7  mov     r14d, eax
0x1800826da  mov     rcx, rdi; hMem
0x1800826dd  call    cs:__imp_LocalFree
0x1800826e3  nop
0x1800826e4  mov     rdi, [rsi+8]
0x1800826e8  test    rdi, rdi
0x1800826eb  jz      loc_180082930
0x1800826f1  or      ebx, 0FFFFFFFFh
0x1800826f4  mov     ecx, ebx
0x1800826f6  lock xadd [rdi+8], ecx
0x1800826fb  add     ecx, ebx
0x1800826fd  jnz     loc_180082930
0x180082703  mov     rax, [rdi]
0x180082706  mov     rcx, rdi
0x180082709  mov     rax, [rax]
0x18008270c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082711  mov     eax, ebx
0x180082713  lock xadd [rdi+0Ch], eax
0x180082718  add     eax, ebx
0x18008271a  jnz     loc_180082930
0x180082720  mov     rax, [rdi]
0x180082723  mov     rax, [rax+8]
0x180082727  jmp     loc_180082928
0x18008272c  mov     [rbp+pbBuffer], 0
0x180082733  mov     rcx, r15; lpCriticalSection
0x180082736  call    cs:__imp_EnterCriticalSection
0x18008273c  mov     [rbp+var_38], r15
0x180082740  mov     r9d, 2; dwFlags
0x180082746  lea     r8d, [r9+2]; cbBuffer
0x18008274a  lea     rdx, [rbp+pbBuffer]; pbBuffer
0x18008274e  xor     ecx, ecx; hAlgorithm
0x180082750  call    cs:__imp_BCryptGenRandom
0x180082756  test    eax, eax
0x180082758  jns     short loc_1800827AC
0x18008275a  mov     rcx, [rbp+38h]; this
0x18008275e  mov     r9d, eax; char *
0x180082761  lea     r8, aOnecoreuapDsNf_49; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x180082768  mov     edx, 2Dh ; '-'; void *
0x18008276d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180082772  mov     r14d, eax
0x180082775  test    r15, r15
0x180082778  jz      short loc_180082784
0x18008277a  mov     rcx, r15; lpCriticalSection
0x18008277d  call    cs:__imp_LeaveCriticalSection
0x180082783  nop
0x180082784  mov     rcx, rdi; hMem
0x180082787  call    cs:__imp_LocalFree
0x18008278d  nop
0x18008278e  mov     rdi, [rsi+8]
0x180082792  test    rdi, rdi
0x180082795  jz      loc_180082930
0x18008279b  or      ebx, 0FFFFFFFFh
0x18008279e  mov     eax, ebx
0x1800827a0  lock xadd [rdi+8], eax
0x1800827a5  add     eax, ebx
0x1800827a7  jmp     loc_1800826FD
0x1800827ac  mov     r12, [r15+30h]
0x1800827b0  mov     ebx, [rbp+pbBuffer]
0x1800827b3  test    ebx, ebx
0x1800827b5  jz      short loc_1800827CD
0x1800827b7  lea     r8, [rbp+pbBuffer]
0x1800827bb  lea     rdx, [rbp+var_40]
0x1800827bf  lea     rcx, [r15+28h]
0x1800827c3  call    ?find@?$_Hash@V?$_Umap_traits@IURegistryEntry@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIURegistryEntry@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@@std@@@8@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIURegistryEntry@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@@std@@@std@@@std@@@2@AEBI@Z; std::_Hash<std::_Umap_traits<uint,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>,0>>::find(uint const &)
0x1800827c8  cmp     [rax], r12
0x1800827cb  jz      short loc_1800827D4
0x1800827cd  inc     ebx
0x1800827cf  mov     [rbp+pbBuffer], ebx
0x1800827d2  jmp     short loc_1800827B3
0x1800827d4  mov     [rbp+var_18], rdi
0x1800827d8  mov     [rbp+var_30], 0
0x1800827e0  mov     rax, [rsi+8]
0x1800827e4  test    rax, rax
0x1800827e7  jz      short loc_1800827ED
0x1800827e9  lock inc dword ptr [rax+8]
0x1800827ed  mov     r13, [rsi]
0x1800827f0  mov     qword ptr [rbp+var_10], r13
0x1800827f4  mov     rbx, [rsi+8]
0x1800827f8  mov     [rbp+var_40], rbx
0x1800827fc  mov     qword ptr [rbp+var_10+8], rbx
0x180082800  lea     r8, [rbp+pbBuffer]
0x180082804  lea     rdx, [rbp+var_28]
0x180082808  lea     rcx, [r15+28h]
0x18008280c  call    ??$_Try_emplace@AEBI$$V@?$_Hash@V?$_Umap_traits@IURegistryEntry@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIURegistryEntry@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@@std@@@8@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBIURegistryEntry@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@@std@@PEAX@std@@_N@1@AEBI@Z; std::_Hash<std::_Umap_traits<uint,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>,0>>::_Try_emplace<uint const &,>(uint const &)
0x180082811  mov     r14, [rax]
0x180082814  add     r14, 18h
0x180082818  lea     rax, [rbp+var_18]
0x18008281c  cmp     r14, rax
0x18008281f  jz      short loc_180082851
0x180082821  mov     r12, [r14]
0x180082824  test    r12, r12
0x180082827  jz      short loc_180082846
0x180082829  call    cs:__imp_GetLastError
0x18008282f  mov     ebx, eax
0x180082831  mov     rcx, r12; hMem
0x180082834  call    cs:__imp_LocalFree
0x18008283a  mov     ecx, ebx; dwErrCode
0x18008283c  call    cs:__imp_SetLastError
0x180082842  mov     rbx, [rbp+var_40]
0x180082846  mov     [r14], rdi
0x180082849  mov     [rbp+var_18], 0
0x180082851  xorps   xmm0, xmm0
0x180082854  movdqu  [rbp+var_10], xmm0
0x180082859  mov     [r14+8], r13
0x18008285d  mov     rdi, [r14+10h]
0x180082861  mov     [r14+10h], rbx
0x180082865  or      ebx, 0FFFFFFFFh
0x180082868  test    rdi, rdi
0x18008286b  jz      short loc_1800828A1
0x18008286d  mov     eax, ebx
0x18008286f  lock xadd [rdi+8], eax
0x180082874  add     eax, ebx
0x180082876  jnz     short loc_1800828A1
0x180082878  mov     rax, [rdi]
0x18008287b  mov     rcx, rdi
0x18008287e  mov     rax, [rax]
0x180082881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082886  mov     eax, ebx
0x180082888  lock xadd [rdi+0Ch], eax
0x18008288d  add     eax, ebx
0x18008288f  jnz     short loc_1800828A1
0x180082891  mov     rax, [rdi]
0x180082894  mov     rcx, rdi
0x180082897  mov     rax, [rax+8]
0x18008289b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800828a0  nop
0x1800828a1  lea     rcx, [rbp+var_18]; this
0x1800828a5  call    ??1RegistryEntry@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@QEAA@XZ; Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry::~RegistryEntry(void)
0x1800828aa  mov     rcx, [rbp+arg_8]
0x1800828ae  mov     rax, [rcx+30h]
0x1800828b2  mov     [rbp+var_40], rax
0x1800828b6  mov     rdx, [rsi]
0x1800828b9  lea     rax, [rdx+50h]
0x1800828bd  cmp     qword ptr [rax+18h], 7
0x1800828c2  jbe     short loc_1800828C7
0x1800828c4  mov     rax, [rax]
0x1800828c7  mov     [rbp+var_38], rax
0x1800828cb  mov     eax, [rdx+48h]
0x1800828ce  mov     dword ptr [rbp+arg_8], eax
0x1800828d1  add     rdx, 38h ; '8'
0x1800828d5  lea     r9, [rbp+var_40]
0x1800828d9  lea     r8, [rbp+var_38]
0x1800828dd  lea     rcx, [rbp+arg_8]
0x1800828e1  call    ??$PaymentRequestRegistered@IAEBU_GUID@@PEBGPEBG@PaymentLoggingProvider@Service@Mediator@Payment@Windows@@SAX$$QEAIAEBU_GUID@@$$QEAPEBG2@Z; Windows::Payment::Mediator::Service::PaymentLoggingProvider::PaymentRequestRegistered<uint,_GUID const &,ushort const *,ushort const *>(uint &&,_GUID const &,ushort const * &&,ushort const * &&)
0x1800828e6  nop
0x1800828e7  mov     rcx, r15; lpCriticalSection
0x1800828ea  call    cs:__imp_LeaveCriticalSection
0x1800828f0  mov     r14d, [rbp+pbBuffer]
0x1800828f4  mov     rdi, [rsi+8]
0x1800828f8  test    rdi, rdi
0x1800828fb  jz      short loc_180082930
0x1800828fd  mov     eax, ebx
0x1800828ff  lock xadd [rdi+8], eax
0x180082904  add     eax, ebx
0x180082906  jnz     short loc_180082930
0x180082908  mov     rax, [rdi]
0x18008290b  mov     rcx, rdi
0x18008290e  mov     rax, [rax]
0x180082911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082916  mov     edx, ebx
0x180082918  lock xadd [rdi+0Ch], edx
0x18008291d  add     edx, ebx
0x18008291f  jnz     short loc_180082930
0x180082921  mov     rdx, [rdi]
0x180082924  mov     rax, [rdx+8]
0x180082928  mov     rcx, rdi
0x18008292b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082930  mov     eax, r14d
0x180082933  mov     rbx, [rsp+60h+arg_0]
0x18008293b  add     rsp, 60h
0x18008293f  pop     r15
0x180082941  pop     r14
0x180082943  pop     r13
0x180082945  pop     r12
0x180082947  pop     rdi
0x180082948  pop     rsi
0x180082949  pop     rbp
0x18008294a  retn
```
