# CanMakePaymentRequestManager::MakeRequest(_PaymentServiceRequest const *,Windows::Payment::Mediator::Service::RpcCallManager &)

- ea: `0x180084ca4`
- end: `0x180085024`
- name: `?MakeRequest@CanMakePaymentRequestManager@@QEAA?AV?$shared_ptr@VCanMakePaymentRequest@@@std@@PEBU_PaymentServiceRequest@@AEAVRpcCallManager@Service@Mediator@Payment@Windows@@@Z`
- size: `896`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007ea9c`

## callees

- `0x1800049a0`
- `0x180004ec0`
- `0x1800057c6`
- `0x180009634`
- `0x18000c964`
- `0x18002daa4`
- `0x180081294`
- `0x18008157c`
- `0x180083e4c`
- `0x180084060`
- `0x18008466c`
- `0x180084964`
- `0x180084ca4`
- `0x180085a1c`
- `0x180085cc4`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180084ed2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180084ed2`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x180084d19`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x180084d19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084fbf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084fbf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180084dbb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180084dbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084d23`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180084e88`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180084e88`
- `BrokerLib!BrSignalBrokerEvent2` at `0x180084f0f`
- `BrokerLib!BrSignalBrokerEvent2` at `0x180084f0f`

## string_xrefs

- `0x180085012`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180084d40`: `onecoreuap\ds\nfc\product\payment\service\lib\paymentbackgroundmanager.cpp`
- `0x180084feb`: `onecoreuap\ds\nfc\product\payment\service\lib\canmakepaymentrequestmanager.cpp`
- `0x180085000`: `onecoreuap\ds\nfc\product\payment\service\lib\canmakepaymentrequestmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall CanMakePaymentRequestManager::MakeRequest(
        LPCRITICAL_SECTION lpCriticalSection,
        _QWORD *a2,
        const struct _PaymentServiceRequest *a3,
        Windows::Payment::Mediator::Service::RpcCallManager *a4)
{
  void *v8; // r14
  const char *v9; // r9
  int v10; // ebx
  _DWORD *v11; // rdi
  unsigned int v12; // r14d
  LPCRITICAL_SECTION v13; // r12
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdi
  volatile signed __int32 *v17; // rbx
  ULONGLONG TickCount64; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  unsigned int v22; // eax
  char v23; // bl
  signed int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rcx
  volatile signed __int32 *v28; // rcx
  int v30; // [rsp+20h] [rbp-59h]
  int v31; // [rsp+20h] [rbp-59h]
  __int128 v32; // [rsp+30h] [rbp-49h] BYREF
  int v33; // [rsp+40h] [rbp-39h]
  unsigned __int16 *v34; // [rsp+48h] [rbp-31h]
  _QWORD *v35; // [rsp+50h] [rbp-29h] BYREF
  _QWORD *v36; // [rsp+58h] [rbp-21h]
  _QWORD *v37; // [rsp+68h] [rbp-11h]
  _QWORD CompareAddress[2]; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v37 = a2;
  v33 = 0;
  v8 = (void *)**((_QWORD **)a4 + 4);
  *(_QWORD *)&v32 = v8;
  v34 = (unsigned __int16 *)Windows::Payment::Mediator::Service::RpcCallManager::PackageFamilyName(a4);
  do
  {
    if ( dword_180132F98 )
    {
      v10 = 0;
      goto LABEL_7;
    }
    LODWORD(CompareAddress[0]) = 0;
  }
  while ( WaitOnAddress(&dword_180132F98, CompareAddress, 4u, 0xFFFFFFFF) );
  if ( GetLastError() != 1460 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xDBF,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v9);
  v10 = -2147418113;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE7,
    (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\paymentbackgroundmanager.cpp",
    (const char *)0x8000FFFFLL,
    v30);
LABEL_7:
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\canmakepaymentrequestmanager.cpp",
      (const char *)(unsigned int)v10,
      v30);
  v11 = operator new(0x108u);
  CompareAddress[0] = v11;
  *(_OWORD *)v11 = 0;
  v11[2] = 1;
  v11[3] = 1;
  *(_QWORD *)v11 = &std::_Ref_count_obj2<CanMakePaymentRequest>::`vftable';
  CanMakePaymentRequest::CanMakePaymentRequest((CanMakePaymentRequest *)(v11 + 4), a3, v8, v34);
  *a2 = v11 + 4;
  a2[1] = v11;
  v12 = 3;
  v33 = 3;
  EnterCriticalSection(lpCriticalSection);
  v34 = (unsigned __int16 *)lpCriticalSection;
  v13 = lpCriticalSection + 1;
  ++lpCriticalSection[1].DebugInfo;
  if ( Windows::Payment::Mediator::Service::RpcCallManager::IsRunningInForeground(a4) )
  {
    CanMakePaymentRequestManager::GetPaymentProviders(lpCriticalSection, &v35, v32);
    if ( v35 == v36 )
    {
      v12 = 2;
    }
    else
    {
      v14 = *a2;
      v32 = 0;
      v15 = *(_QWORD *)(v14 + 240);
      if ( v15 )
        _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
      v32 = *(_OWORD *)(v14 + 232);
      v16 = *(_QWORD *)std::_Hash<std::_Umap_traits<std::shared_ptr<CanMakePaymentRequestSource>,CanMakePaymentRequestManager::CanMakePaymentRequestSourceTracker,std::_Uhash_compare<std::shared_ptr<CanMakePaymentRequestSource>,std::hash<std::shared_ptr<CanMakePaymentRequestSource>>,std::equal_to<std::shared_ptr<CanMakePaymentRequestSource>>>,std::allocator<std::pair<std::shared_ptr<CanMakePaymentRequestSource> const,CanMakePaymentRequestManager::CanMakePaymentRequestSourceTracker>>,0>>::_Try_emplace<std::shared_ptr<CanMakePaymentRequestSource> const &,>(
                         &lpCriticalSection[4].OwningThread,
                         CompareAddress,
                         &v32);
      v17 = (volatile signed __int32 *)*((_QWORD *)&v32 + 1);
      if ( *((_QWORD *)&v32 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v32 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
          if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
        }
      }
      TickCount64 = GetTickCount64();
      if ( TickCount64 > *(_QWORD *)(v16 + 40) )
      {
        *(_QWORD *)(v16 + 40) = TickCount64 + 120000;
        *(_DWORD *)(v16 + 32) = 0;
      }
      v22 = *(_DWORD *)(v16 + 32);
      if ( v22 < 0x3E8 )
      {
        v23 = 0;
        v12 = 0;
        *(_DWORD *)(v16 + 32) = v22 + 1;
        if ( lpCriticalSection == (LPCRITICAL_SECTION)-40LL )
        {
          CompareAddress[0] = 0;
          *(_DWORD *)_o__errno(v20, v19, v21) = 22;
          invalid_parameter_noinfo();
        }
        else
        {
          CompareAddress[0] = v13->DebugInfo;
        }
        if ( v35 != v36 )
        {
          v24 = BrSignalBrokerEvent2(*v35, v35[1], 0, qword_1801158E0, 8, CompareAddress, v32);
          if ( v24 > 0 )
            v24 = (unsigned __int16)v24 | 0x80070000;
          if ( v24 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x6B,
              (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\canmakepaymentrequestmanager.cpp",
              (const char *)(unsigned int)v24,
              v31);
        }
        goto LABEL_29;
      }
    }
    v23 = 1;
LABEL_29:
    std::vector<CanMakePaymentRequestManager::CanMakePaymentProvider>::~vector<CanMakePaymentRequestManager::CanMakePaymentProvider>(&v35);
    goto LABEL_31;
  }
  v23 = 1;
LABEL_31:
  *(_QWORD *)(*a2 + 16LL) = v13->DebugInfo;
  *(_QWORD *)&v32 = *(_QWORD *)(*a2 + 16LL);
  v25 = *(_QWORD *)std::_Hash<std::_Umap_traits<unsigned __int64,std::weak_ptr<CanMakePaymentRequest>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::weak_ptr<CanMakePaymentRequest>>>,0>>::_Try_emplace<unsigned __int64,>(
                     &lpCriticalSection[2].SpinCount,
                     CompareAddress,
                     &v32);
  v26 = a2[1];
  if ( v26 )
  {
    v27 = *a2;
    _InterlockedIncrement((volatile signed __int32 *)(v26 + 12));
  }
  else
  {
    v27 = 0;
  }
  *(_QWORD *)(v25 + 24) = v27;
  v28 = *(volatile signed __int32 **)(v25 + 32);
  *(_QWORD *)(v25 + 32) = v26;
  if ( v28 && !_InterlockedDecrement(v28 + 3) )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
  if ( v23 )
    CanMakePaymentRequest::ReportCanMakePaymentResult(*a2, v12);
  LeaveCriticalSection(lpCriticalSection);
  return a2;
}

```

## disassembly

```asm
0x180084ca4  push    rbp
0x180084ca6  push    rbx
0x180084ca7  push    rsi
0x180084ca8  push    rdi
0x180084ca9  push    r12
0x180084cab  push    r13
0x180084cad  push    r14
0x180084caf  push    r15
0x180084cb1  lea     rbp, [rsp-1Fh]
0x180084cb6  sub     rsp, 98h
0x180084cbd  mov     rax, cs:__security_cookie
0x180084cc4  xor     rax, rsp
0x180084cc7  mov     [rbp+57h+var_50], rax
0x180084ccb  mov     r13, r9
0x180084cce  mov     r12, r8
0x180084cd1  mov     rsi, rdx
0x180084cd4  mov     r15, rcx
0x180084cd7  mov     [rbp+57h+var_68], rdx
0x180084cdb  mov     [rbp+57h+var_90], 0
0x180084ce2  mov     rax, [r9+20h]
0x180084ce6  mov     r14, [rax]
0x180084ce9  mov     qword ptr [rbp+57h+var_A0], r14
0x180084ced  mov     rcx, r9; this
0x180084cf0  call    ?PackageFamilyName@RpcCallManager@Service@Mediator@Payment@Windows@@QEAAPEBGXZ; Windows::Payment::Mediator::Service::RpcCallManager::PackageFamilyName(void)
0x180084cf5  mov     [rbp+57h+var_88], rax
0x180084cf9  mov     eax, cs:dword_180132F98
0x180084cff  test    eax, eax
0x180084d01  jnz     short loc_180084D53
0x180084d03  mov     dword ptr [rbp+57h+CompareAddress], eax
0x180084d06  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180084d0a  lea     r8d, [rax+4]; AddressSize
0x180084d0e  lea     rdx, [rbp+57h+CompareAddress]; CompareAddress
0x180084d12  lea     rcx, dword_180132F98; Address
0x180084d19  call    cs:__imp_WaitOnAddress
0x180084d1f  test    eax, eax
0x180084d21  jnz     short loc_180084CF9
0x180084d23  call    cs:__imp_GetLastError
0x180084d29  mov     rcx, [rbp+5Fh]; this
0x180084d2d  cmp     eax, 5B4h
0x180084d32  jnz     loc_180085012
0x180084d38  mov     ebx, 8000FFFFh
0x180084d3d  mov     r9d, ebx; char *
0x180084d40  lea     r8, aOnecoreuapDsNf_36; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x180084d47  mov     edx, 0E7h; void *
0x180084d4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084d51  jmp     short loc_180084D55
0x180084d53  xor     ebx, ebx
0x180084d55  mov     rcx, [rbp+5Fh]; this
0x180084d59  test    ebx, ebx
0x180084d5b  js      loc_180084FE8
0x180084d61  mov     ecx, 108h; Size
0x180084d66  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180084d6b  mov     rdi, rax
0x180084d6e  mov     [rbp+57h+CompareAddress], rax
0x180084d72  xorps   xmm0, xmm0
0x180084d75  movups  xmmword ptr [rax], xmm0
0x180084d78  mov     dword ptr [rax+8], 1
0x180084d7f  mov     dword ptr [rax+0Ch], 1
0x180084d86  lea     rax, ??_7?$_Ref_count_obj2@VCanMakePaymentRequest@@@std@@6B@; const std::_Ref_count_obj2<CanMakePaymentRequest>::`vftable'
0x180084d8d  mov     [rdi], rax
0x180084d90  lea     rbx, [rdi+10h]
0x180084d94  mov     r9, [rbp+57h+var_88]; unsigned __int16 *
0x180084d98  mov     r8, r14; void *
0x180084d9b  mov     rdx, r12; struct _PaymentServiceRequest *
0x180084d9e  mov     rcx, rbx; this
0x180084da1  call    ??0CanMakePaymentRequest@@QEAA@PEBU_PaymentServiceRequest@@PEAXPEBG@Z; CanMakePaymentRequest::CanMakePaymentRequest(_PaymentServiceRequest const *,void *,ushort const *)
0x180084da6  nop
0x180084da7  mov     [rsi], rbx
0x180084daa  mov     [rsi+8], rdi
0x180084dae  mov     r14d, 3
0x180084db4  mov     [rbp+57h+var_90], r14d
0x180084db8  mov     rcx, r15; lpCriticalSection
0x180084dbb  call    cs:__imp_EnterCriticalSection
0x180084dc1  mov     [rbp+57h+var_88], r15
0x180084dc5  lea     r12, [r15+28h]
0x180084dc9  inc     qword ptr [r12]
0x180084dcd  mov     rcx, r13; this
0x180084dd0  call    ?IsRunningInForeground@RpcCallManager@Service@Mediator@Payment@Windows@@QEBA_NXZ; Windows::Payment::Mediator::Service::RpcCallManager::IsRunningInForeground(void)
0x180084dd5  or      r13d, 0FFFFFFFFh
0x180084dd9  test    al, al
0x180084ddb  jz      loc_180084F42
0x180084de1  mov     r8, qword ptr [rbp+57h+var_A0]
0x180084de5  lea     rdx, [rbp+57h+var_80]
0x180084de9  mov     rcx, r15
0x180084dec  call    ?GetPaymentProviders@CanMakePaymentRequestManager@@IEBA?AV?$vector@UCanMakePaymentProvider@CanMakePaymentRequestManager@@V?$allocator@UCanMakePaymentProvider@CanMakePaymentRequestManager@@@std@@@std@@PEAX@Z; CanMakePaymentRequestManager::GetPaymentProviders(void *)
0x180084df1  nop
0x180084df2  mov     rax, [rbp+57h+var_78]
0x180084df6  cmp     [rbp+57h+var_80], rax
0x180084dfa  jz      loc_180084F2F
0x180084e00  mov     rcx, [rsi]
0x180084e03  xorps   xmm0, xmm0
0x180084e06  movdqu  [rbp+57h+var_A0], xmm0
0x180084e0b  mov     rax, [rcx+0F0h]
0x180084e12  test    rax, rax
0x180084e15  jz      short loc_180084E1B
0x180084e17  lock inc dword ptr [rax+8]
0x180084e1b  mov     rax, [rcx+0E8h]
0x180084e22  mov     qword ptr [rbp+57h+var_A0], rax
0x180084e26  mov     rax, [rcx+0F0h]
0x180084e2d  mov     qword ptr [rbp+57h+var_A0+8], rax
0x180084e31  lea     r8, [rbp+57h+var_A0]
0x180084e35  lea     rdx, [rbp+57h+CompareAddress]
0x180084e39  lea     rcx, [r15+0B0h]
0x180084e40  call    ??$_Try_emplace@AEBV?$shared_ptr@VCanMakePaymentRequestSource@@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$shared_ptr@VCanMakePaymentRequestSource@@@std@@UCanMakePaymentRequestSourceTracker@CanMakePaymentRequestManager@@V?$_Uhash_compare@V?$shared_ptr@VCanMakePaymentRequestSource@@@std@@U?$hash@V?$shared_ptr@VCanMakePaymentRequestSource@@@std@@@2@U?$equal_to@V?$shared_ptr@VCanMakePaymentRequestSource@@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$shared_ptr@VCanMakePaymentRequestSource@@@std@@UCanMakePaymentRequestSourceTracker@CanMakePaymentRequestManager@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$shared_ptr@VCanMakePaymentRequestSource@@@std@@UCanMakePaymentRequestSourceTracker@CanMakePaymentRequestManager@@@std@@PEAX@std@@_N@1@AEBV?$shared_ptr@VCanMakePaymentRequestSource@@@1@@Z; std::_Hash<std::_Umap_traits<std::shared_ptr<CanMakePaymentRequestSource>,CanMakePaymentRequestManager::CanMakePaymentRequestSourceTracker,std::_Uhash_compare<std::shared_ptr<CanMakePaymentRequestSource>,std::hash<std::shared_ptr<CanMakePaymentRequestSource>>,std::equal_to<std::shared_ptr<CanMakePaymentRequestSource>>>,std::allocator<std::pair<std::shared_ptr<CanMakePaymentRequestSource> const,CanMakePaymentRequestManager::CanMakePaymentRequestSourceTracker>>,0>>::_Try_emplace<std::shared_ptr<CanMakePaymentRequestSource> const &,>(std::shared_ptr<CanMakePaymentRequestSource> const &)
0x180084e45  mov     rdi, [rax]
0x180084e48  mov     rbx, qword ptr [rbp+57h+var_A0+8]
0x180084e4c  test    rbx, rbx
0x180084e4f  jz      short loc_180084E88
0x180084e51  mov     eax, r13d
0x180084e54  lock xadd [rbx+8], eax
0x180084e59  add     eax, r13d
0x180084e5c  jnz     short loc_180084E88
0x180084e5e  mov     rax, [rbx]
0x180084e61  mov     rcx, rbx
0x180084e64  mov     rax, [rax]
0x180084e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084e6c  mov     eax, r13d
0x180084e6f  lock xadd [rbx+0Ch], eax
0x180084e74  add     eax, r13d
0x180084e77  jnz     short loc_180084E88
0x180084e79  mov     rax, [rbx]
0x180084e7c  mov     rcx, rbx
0x180084e7f  mov     rax, [rax+8]
0x180084e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084e88  call    cs:__imp_GetTickCount64
0x180084e8e  cmp     rax, [rdi+28h]
0x180084e92  jbe     short loc_180084EA5
0x180084e94  add     rax, 1D4C0h
0x180084e9a  mov     [rdi+28h], rax
0x180084e9e  mov     dword ptr [rdi+20h], 0
0x180084ea5  mov     eax, [rdi+20h]
0x180084ea8  cmp     eax, 3E8h
0x180084ead  jnb     loc_180084F35
0x180084eb3  xor     bl, bl
0x180084eb5  xor     r14d, r14d
0x180084eb8  inc     eax
0x180084eba  mov     [rdi+20h], eax
0x180084ebd  test    r12, r12
0x180084ec0  jz      short loc_180084ECC
0x180084ec2  mov     rax, [r12]
0x180084ec6  mov     [rbp+57h+CompareAddress], rax
0x180084eca  jmp     short loc_180084EE3
0x180084ecc  xor     eax, eax
0x180084ece  mov     [rbp+57h+CompareAddress], rax
0x180084ed2  call    cs:__imp__o__errno
0x180084ed8  mov     dword ptr [rax], 16h
0x180084ede  call    _invalid_parameter_noinfo
0x180084ee3  mov     rcx, [rbp+57h+var_80]
0x180084ee7  cmp     rcx, [rbp+57h+var_78]
0x180084eeb  jz      short loc_180084F37
0x180084eed  lea     rax, [rbp+57h+CompareAddress]
0x180084ef1  mov     [rsp+0D0h+var_A8], rax
0x180084ef6  mov     [rsp+0D0h+var_B0], 8; int
0x180084efe  lea     r9, qword_1801158E0
0x180084f05  xor     r8d, r8d
0x180084f08  mov     rdx, [rcx+8]
0x180084f0c  mov     rcx, [rcx]
0x180084f0f  call    cs:__imp_BrSignalBrokerEvent2
0x180084f15  test    eax, eax
0x180084f17  jle     short loc_180084F21
0x180084f19  movzx   eax, ax
0x180084f1c  or      eax, 80070000h
0x180084f21  mov     rcx, [rbp+5Fh]; this
0x180084f25  test    eax, eax
0x180084f27  js      loc_180084FFD
0x180084f2d  jmp     short loc_180084F37
0x180084f2f  mov     r14d, 2
0x180084f35  mov     bl, 1
0x180084f37  lea     rcx, [rbp+57h+var_80]
0x180084f3b  call    ??1?$vector@UCanMakePaymentProvider@CanMakePaymentRequestManager@@V?$allocator@UCanMakePaymentProvider@CanMakePaymentRequestManager@@@std@@@std@@QEAA@XZ; std::vector<CanMakePaymentRequestManager::CanMakePaymentProvider>::~vector<CanMakePaymentRequestManager::CanMakePaymentProvider>(void)
0x180084f40  jmp     short loc_180084F44
0x180084f42  mov     bl, 1
0x180084f44  mov     rcx, [rsi]
0x180084f47  mov     rax, [r12]
0x180084f4b  mov     [rcx+10h], rax
0x180084f4f  mov     rax, [rsi]
0x180084f52  mov     rcx, [rax+10h]
0x180084f56  mov     qword ptr [rbp+57h+var_A0], rcx
0x180084f5a  lea     r8, [rbp+57h+var_A0]
0x180084f5e  lea     rdx, [rbp+57h+CompareAddress]
0x180084f62  lea     rcx, [r15+70h]
0x180084f66  call    ??$_Try_emplace@_K$$V@?$_Hash@V?$_Umap_traits@_KV?$weak_ptr@VCanMakePaymentRequest@@@std@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@2@V?$allocator@U?$pair@$$CB_KV?$weak_ptr@VCanMakePaymentRequest@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CB_KV?$weak_ptr@VCanMakePaymentRequest@@@std@@@std@@PEAX@std@@_N@1@$$QEA_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,std::weak_ptr<CanMakePaymentRequest>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::weak_ptr<CanMakePaymentRequest>>>,0>>::_Try_emplace<unsigned __int64,>(unsigned __int64 &&)
0x180084f6b  mov     rdx, [rax]
0x180084f6e  mov     rax, [rsi+8]
0x180084f72  test    rax, rax
0x180084f75  jz      short loc_180084F80
0x180084f77  mov     rcx, [rsi]
0x180084f7a  lock inc dword ptr [rax+0Ch]
0x180084f7e  jmp     short loc_180084F82
0x180084f80  xor     ecx, ecx
0x180084f82  mov     [rdx+18h], rcx
0x180084f86  mov     rcx, [rdx+20h]
0x180084f8a  mov     [rdx+20h], rax
0x180084f8e  test    rcx, rcx
0x180084f91  jz      short loc_180084FAC
0x180084f93  mov     eax, r13d
0x180084f96  lock xadd [rcx+0Ch], eax
0x180084f9b  add     eax, r13d
0x180084f9e  jnz     short loc_180084FAC
0x180084fa0  mov     rax, [rcx]
0x180084fa3  mov     rax, [rax+8]
0x180084fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084fac  test    bl, bl
0x180084fae  jz      short loc_180084FBC
0x180084fb0  mov     edx, r14d
0x180084fb3  mov     rcx, [rsi]
0x180084fb6  call    ?ReportCanMakePaymentResult@CanMakePaymentRequest@@QEAAXW4PaymentServiceCanMakePaymentResultStatus@@@Z; CanMakePaymentRequest::ReportCanMakePaymentResult(PaymentServiceCanMakePaymentResultStatus)
0x180084fbb  nop
0x180084fbc  mov     rcx, r15; lpCriticalSection
0x180084fbf  call    cs:__imp_LeaveCriticalSection
0x180084fc5  mov     rax, rsi
0x180084fc8  mov     rcx, [rbp+57h+var_50]
0x180084fcc  xor     rcx, rsp; StackCookie
0x180084fcf  call    __security_check_cookie
0x180084fd4  add     rsp, 98h
0x180084fdb  pop     r15
0x180084fdd  pop     r14
0x180084fdf  pop     r13
0x180084fe1  pop     r12
0x180084fe3  pop     rdi
0x180084fe4  pop     rsi
0x180084fe5  pop     rbx
0x180084fe6  pop     rbp
0x180084fe7  retn
0x180084fe8  mov     r9d, ebx; char *
0x180084feb  lea     r8, aOnecoreuapDsNf_42; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x180084ff2  mov     edx, 44h ; 'D'; void *
0x180084ff7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180084ffd  mov     r9d, eax; char *
0x180085000  lea     r8, aOnecoreuapDsNf_42; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x180085007  mov     edx, 6Bh ; 'k'; void *
0x18008500c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085012  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180085019  mov     edx, 0DBFh; void *
0x18008501e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
