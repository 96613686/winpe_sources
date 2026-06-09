# _Windows::Payment::Mediator::Service::WalletImpl::ConnectToTransaction_::_2_::_lambda_1_::operator()

- ea: `0x18007da08`
- end: `0x18007df5c`
- name: `_Windows::Payment::Mediator::Service::WalletImpl::ConnectToTransaction_::_2_::_lambda_1_::operator()`
- size: `1364`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18007e640`

## callees

- `0x1800049a0`
- `0x180004e9c`
- `0x180005858`
- `0x18002daa4`
- `0x180035e6c`
- `0x18007da08`
- `0x1800811c0`
- `0x18008157c`
- `0x180081ee8`
- `0x180082210`
- `0x1800824f0`
- `0x180082d30`
- `0x1800835b8`
- `0x180086d14`
- `0x180089134`
- `0x18008b778`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007dbe2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007dbe2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007daf1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007daf1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007dac1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007dac1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18007db47`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18007db47`

## string_xrefs

- `0x18007decc`: `onecoreuap\ds\nfc\product\payment\service\lib\walletimpl.cpp`
- `0x18007dee4`: `onecoreuap\ds\nfc\product\payment\service\lib\walletimpl.cpp`
- `0x18007defc`: `onecoreuap\ds\nfc\product\payment\service\lib\walletimpl.cpp`
- `0x18007df17`: `onecoreuap\ds\nfc\product\payment\service\lib\paymenttransactionregistry.cpp`
- `0x18007df2f`: `onecoreuap\ds\nfc\product\payment\service\lib\paymenttransactionregistry.cpp`
- `0x18007df4a`: `onecoreuap\ds\nfc\product\payment\service\lib\paymenttransactionregistry.cpp`
- `0x18007dcaa`: `Windows::Payment::Mediator::Service::PaymentServiceTransactionImpl::RuntimeClassInitialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall Windows::Payment::Mediator::Service::WalletImpl::ConnectToTransaction_::_2_::_lambda_1_::operator()(
        __int64 *a1)
{
  const WCHAR *v2; // r8
  struct Windows::Payment::Mediator::Service::PaymentTransactionRegistry *v3; // r14
  __int64 v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rbx
  bool v7; // zf
  const wchar_t *v8; // rax
  const wchar_t *v9; // rcx
  __int64 v10; // rdx
  size_t v11; // r8
  __int64 v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rsi
  volatile signed __int32 *v16; // rbx
  Windows::Payment::Mediator::Service::PaymentServiceTransactionImpl *v17; // rax
  int v18; // edi
  __int64 v19; // rbx
  _QWORD *v20; // rdx
  __int128 v21; // xmm6
  __int128 v22; // xmm7
  __int128 v23; // xmm8
  __int128 v24; // xmm9
  __int128 v25; // xmm10
  __int128 v26; // xmm11
  __int128 v27; // xmm12
  __int128 v28; // xmm13
  __int128 v29; // xmm14
  __int128 v30; // xmm15
  _OWORD *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  volatile signed __int32 *v34; // rbx
  BOOL bIgnoreCase; // [rsp+28h] [rbp-E0h]
  BOOL bIgnoreCasea; // [rsp+28h] [rbp-E0h]
  __int64 v37; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v38; // [rsp+40h] [rbp-C8h] BYREF
  __int128 v39; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v40; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v41; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v42; // [rsp+78h] [rbp-90h]
  _OWORD v43[13]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v44[7]; // [rsp+158h] [rbp+50h] BYREF
  _QWORD *v45; // [rsp+190h] [rbp+88h]
  wil::details::in1diag3 *retaddr; // [rsp+290h] [rbp+188h]

  if ( !*(_BYTE *)(*a1 + 144) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\walletimpl.cpp",
      (const char *)0x80070005LL,
      bIgnoreCase);
  v2 = (const WCHAR *)(*a1 + 80);
  if ( *(_QWORD *)(*a1 + 104) > 7u )
    v2 = *(const WCHAR **)v2;
  if ( CompareStringOrdinal(L"_desktop_", 9, v2, -1, 0) == 2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\walletimpl.cpp",
      (const char *)0x80070005LL,
      bIgnoreCasea);
  v40 = 0;
  v3 = Windows::Payment::Mediator::Service::PaymentTransactionRegistry::Instance();
  LODWORD(v37) = *(_DWORD *)a1[1];
  v4 = *a1;
  EnterCriticalSection((LPCRITICAL_SECTION)v3);
  *(_QWORD *)&v39 = v3;
  std::_Hash<std::_Umap_traits<unsigned int,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>,0>>::find(
    (char *)v3 + 40,
    &v41,
    &v37);
  v6 = v41;
  v7 = (_QWORD)v41 == *((_QWORD *)v3 + 6);
  if ( (_QWORD)v41 == *((_QWORD *)v3 + 6) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v5);
    v7 = v6 == *((_QWORD *)v3 + 6);
  }
  if ( v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\paymenttransactionregistry.cpp",
      (const char *)0x80070490LL,
      bIgnoreCasea);
  if ( !EqualSid(*(PSID *)(v6 + 24), **(PSID **)(v4 + 56)) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\paymenttransactionregistry.cpp",
      (const char *)0x80070005LL,
      bIgnoreCasea);
  v8 = Windows::Payment::Mediator::Service::RpcCallManager::PackageFamilyName((Windows::Payment::Mediator::Service::RpcCallManager *)(v4 + 24));
  v9 = (const wchar_t *)(*(_QWORD *)(v6 + 32) + 80LL);
  v10 = -1;
  do
    ++v10;
  while ( v8[v10] );
  v11 = *(_QWORD *)(*(_QWORD *)(v6 + 32) + 96LL);
  if ( *(_QWORD *)(*(_QWORD *)(v6 + 32) + 104LL) > 7u )
    v9 = *(const wchar_t **)v9;
  if ( v11 != v10 || v11 && wmemcmp(v9, v8, v11) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\paymenttransactionregistry.cpp",
      (const char *)0x80070005LL,
      bIgnoreCasea);
  v13 = *(_QWORD *)(v6 + 40);
  if ( v13 )
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 8));
  v14 = *(_QWORD *)(v6 + 32);
  v15 = *(_QWORD *)(v6 + 40);
  std::_Hash<std::_Umap_traits<unsigned int,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>>>,0>(
    (char *)v3 + 40,
    &v39,
    v6);
  Windows::Payment::Mediator::Service::PaymentLoggingProvider::PaymentRequestRetrieved<unsigned int &>(&v37);
  LeaveCriticalSection((LPCRITICAL_SECTION)v3);
  *(_QWORD *)&v40 = v14;
  v16 = (volatile signed __int32 *)*((_QWORD *)&v40 + 1);
  *((_QWORD *)&v40 + 1) = v15;
  if ( v16 )
  {
    if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  Windows::Payment::Mediator::Service::PaymentRequestTransaction::ConnectPaymentApp(v40, v43, *a1 + 24);
  v38 = 0;
  v17 = (Windows::Payment::Mediator::Service::PaymentServiceTransactionImpl *)operator new(
                                                                                0xA0u,
                                                                                (const struct std::nothrow_t *)std::nothrow);
  if ( v17 )
  {
    v19 = Windows::Payment::Mediator::Service::PaymentServiceTransactionImpl::PaymentServiceTransactionImpl(v17);
    *(_QWORD *)&v39 = v19;
    *(_QWORD *)&v41 = 0;
    v44[0] = off_1800A1420;
    v44[1] = v19;
    v44[2] = &v40;
    v45 = v44;
    v18 = Windows::Payment::Mediator::Service::RpcCallManager::EncapsulateCallWithLogging(
            "Windows::Payment::Mediator::Service::PaymentServiceTransactionImpl::RuntimeClassInitialize",
            v44);
    if ( v45 )
    {
      v20 = v44;
      LOBYTE(v20) = v45 != v44;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v45 + 32LL))(v45, v20);
    }
    if ( v18 >= 0 )
    {
      v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v19)(
              v19,
              &GUID_e1aeef9c_ea3a_46c6_aa0c_6cc89d7c7698,
              &v38);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    else if ( v19 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
  else
  {
    v18 = -2147024882;
  }
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\walletimpl.cpp",
      (const char *)(unsigned int)v18,
      bIgnoreCasea);
  v21 = v43[0];
  v22 = v43[1];
  v23 = v43[2];
  v24 = v43[3];
  v25 = v43[4];
  v26 = v43[5];
  v27 = v43[6];
  v28 = v43[7];
  v29 = v43[8];
  v30 = v43[9];
  v39 = v43[10];
  v41 = v43[11];
  v42 = v43[12];
  memset_0(v43, 0, sizeof(v43));
  v31 = *(_OWORD **)a1[2];
  *v31 = v21;
  v31[1] = v22;
  v31[2] = v23;
  v31[3] = v24;
  v31[4] = v25;
  v31[5] = v26;
  v31[6] = v27;
  v31[7] = v28;
  v31[8] = v29;
  v31[9] = v30;
  v31[10] = v39;
  v31[11] = v41;
  v31[12] = v42;
  v32 = v38;
  v38 = 0;
  **(_QWORD **)a1[3] = v32;
  v33 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  FreePaymentServiceTransaction((struct _PaymentServiceTransaction *)v43);
  v34 = (volatile signed __int32 *)*((_QWORD *)&v40 + 1);
  if ( *((_QWORD *)&v40 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v40 + 1) + 8LL), 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
    if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
  }
}

```

## disassembly

```asm
0x18007da08  mov     rax, rsp
0x18007da0b  push    rbp
0x18007da0c  push    rbx
0x18007da0d  push    rsi
0x18007da0e  push    rdi
0x18007da0f  push    r12
0x18007da11  push    r13
0x18007da13  push    r14
0x18007da15  push    r15
0x18007da17  lea     rbp, [rax-188h]
0x18007da1e  sub     rsp, 248h
0x18007da25  movaps  xmmword ptr [rax-58h], xmm6
0x18007da29  movaps  xmmword ptr [rax-68h], xmm7
0x18007da2d  movaps  xmmword ptr [rax-78h], xmm8
0x18007da32  movaps  xmmword ptr [rax-88h], xmm9
0x18007da3a  movaps  xmmword ptr [rax-98h], xmm10
0x18007da42  movaps  xmmword ptr [rax-0A8h], xmm11
0x18007da4a  movaps  xmmword ptr [rax-0B8h], xmm12
0x18007da52  movaps  xmmword ptr [rax-0C8h], xmm13
0x18007da5a  movaps  xmmword ptr [rax-0D8h], xmm14
0x18007da62  movaps  xmmword ptr [rax-0E8h], xmm15
0x18007da6a  mov     rax, cs:__security_cookie
0x18007da71  xor     rax, rsp
0x18007da74  mov     [rbp+180h+var_F0], rax
0x18007da7b  mov     r15, rcx
0x18007da7e  xor     r13d, r13d
0x18007da81  mov     r8, [rcx]
0x18007da84  mov     rcx, [rbp+188h]; this
0x18007da8b  cmp     [r8+90h], r13b
0x18007da92  jz      loc_18007DEDE
0x18007da98  add     r8, 50h ; 'P'
0x18007da9c  cmp     qword ptr [r8+18h], 7
0x18007daa1  jbe     short loc_18007DAA6
0x18007daa3  mov     r8, [r8]; lpString2
0x18007daa6  mov     rbx, [rbp+188h]
0x18007daad  mov     [rsp+280h+bIgnoreCase], r13d; int
0x18007dab2  or      r9d, 0FFFFFFFFh; cchCount2
0x18007dab6  lea     edx, [r9+0Ah]; cchCount1
0x18007daba  lea     rcx, String1; "_desktop_"
0x18007dac1  call    cs:__imp_CompareStringOrdinal
0x18007dac7  cmp     eax, 2
0x18007daca  jz      loc_18007DEF6
0x18007dad0  xorps   xmm0, xmm0
0x18007dad3  movdqu  [rsp+280h+var_238+8], xmm0
0x18007dad9  call    ?Instance@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@SAAEAV12345@XZ; Windows::Payment::Mediator::Service::PaymentTransactionRegistry::Instance(void)
0x18007dade  mov     r14, rax
0x18007dae1  mov     rcx, [r15+8]
0x18007dae5  mov     edx, [rcx]
0x18007dae7  mov     dword ptr [rsp+280h+var_250], edx
0x18007daeb  mov     rdi, [r15]
0x18007daee  mov     rcx, rax; lpCriticalSection
0x18007daf1  call    cs:__imp_EnterCriticalSection
0x18007daf7  mov     qword ptr [rsp+280h+var_248+8], r14
0x18007dafc  lea     r8, [rsp+280h+var_250]
0x18007db01  lea     rdx, [rsp+280h+var_228+8]
0x18007db06  lea     rcx, [r14+28h]
0x18007db0a  call    ?find@?$_Hash@V?$_Umap_traits@IURegistryEntry@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIURegistryEntry@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@@std@@@8@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIURegistryEntry@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@@std@@@std@@@std@@@2@AEBI@Z; std::_Hash<std::_Umap_traits<uint,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>,0>>::find(uint const &)
0x18007db0f  mov     rbx, qword ptr [rsp+280h+var_228+8]
0x18007db14  cmp     rbx, [r14+30h]
0x18007db18  jnz     short loc_18007DB23
0x18007db1a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007db1f  cmp     rbx, [r14+30h]
0x18007db23  setz    al
0x18007db26  mov     rcx, [rbp+188h]; this
0x18007db2d  test    al, al
0x18007db2f  jnz     loc_18007DF11
0x18007db35  mov     rsi, [rbp+188h]
0x18007db3c  mov     rdx, [rdi+38h]
0x18007db40  mov     rdx, [rdx]; pSid2
0x18007db43  mov     rcx, [rbx+18h]; pSid1
0x18007db47  call    cs:__imp_EqualSid
0x18007db4d  test    eax, eax
0x18007db4f  jz      loc_18007DF29
0x18007db55  lea     rcx, [rdi+18h]; this
0x18007db59  call    ?PackageFamilyName@RpcCallManager@Service@Mediator@Payment@Windows@@QEAAPEBGXZ; Windows::Payment::Mediator::Service::RpcCallManager::PackageFamilyName(void)
0x18007db5e  mov     rcx, [rbx+20h]
0x18007db62  add     rcx, 50h ; 'P'
0x18007db66  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18007db6a  inc     rdx
0x18007db6d  cmp     [rax+rdx*2], r13w
0x18007db72  jnz     short loc_18007DB6A
0x18007db74  mov     r8, [rcx+10h]; N
0x18007db78  cmp     qword ptr [rcx+18h], 7
0x18007db7d  jbe     short loc_18007DB82
0x18007db7f  mov     rcx, [rcx]; S1
0x18007db82  cmp     r8, rdx
0x18007db85  jnz     short loc_18007DB9D
0x18007db87  test    r8, r8
0x18007db8a  jz      short loc_18007DB98
0x18007db8c  mov     rdx, rax; S2
0x18007db8f  call    wmemcmp
0x18007db94  test    eax, eax
0x18007db96  jnz     short loc_18007DB9D
0x18007db98  mov     al, r13b
0x18007db9b  jmp     short loc_18007DB9F
0x18007db9d  mov     al, 1
0x18007db9f  mov     rcx, [rbp+188h]; this
0x18007dba6  test    al, al
0x18007dba8  jnz     loc_18007DF44
0x18007dbae  mov     rax, [rbx+28h]
0x18007dbb2  test    rax, rax
0x18007dbb5  jz      short loc_18007DBBB
0x18007dbb7  lock inc dword ptr [rax+8]
0x18007dbbb  mov     rdi, [rbx+20h]
0x18007dbbf  mov     rsi, [rbx+28h]
0x18007dbc3  mov     r8, rbx
0x18007dbc6  lea     rdx, [rsp+280h+var_248+8]
0x18007dbcb  lea     rcx, [r14+28h]
0x18007dbcf  call    ??$erase@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIURegistryEntry@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@@std@@@std@@@std@@@std@@$0A@@?$_Hash@V?$_Umap_traits@IURegistryEntry@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIURegistryEntry@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@@std@@@8@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIURegistryEntry@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@@std@@@std@@@std@@@1@V21@@Z; std::_Hash<std::_Umap_traits<uint,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>>>,0>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>>>)
0x18007dbd4  lea     rcx, [rsp+280h+var_250]
0x18007dbd9  call    ??$PaymentRequestRetrieved@AEAI@PaymentLoggingProvider@Service@Mediator@Payment@Windows@@SAXAEAI@Z; Windows::Payment::Mediator::Service::PaymentLoggingProvider::PaymentRequestRetrieved<uint &>(uint &)
0x18007dbde  nop
0x18007dbdf  mov     rcx, r14; lpCriticalSection
0x18007dbe2  call    cs:__imp_LeaveCriticalSection
0x18007dbe8  mov     qword ptr [rsp+280h+var_238+8], rdi
0x18007dbed  mov     rbx, qword ptr [rsp+280h+var_228]
0x18007dbf2  mov     qword ptr [rsp+280h+var_228], rsi
0x18007dbf7  test    rbx, rbx
0x18007dbfa  jz      short loc_18007DC33
0x18007dbfc  or      eax, 0FFFFFFFFh
0x18007dbff  lock xadd [rbx+8], eax
0x18007dc04  cmp     eax, 1
0x18007dc07  jnz     short loc_18007DC33
0x18007dc09  mov     rax, [rbx]
0x18007dc0c  mov     rcx, rbx
0x18007dc0f  mov     rax, [rax]
0x18007dc12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dc17  or      eax, 0FFFFFFFFh
0x18007dc1a  lock xadd [rbx+0Ch], eax
0x18007dc1f  cmp     eax, 1
0x18007dc22  jnz     short loc_18007DC33
0x18007dc24  mov     rax, [rbx]
0x18007dc27  mov     rcx, rbx
0x18007dc2a  mov     rax, [rax+8]
0x18007dc2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dc33  mov     r8, [r15]
0x18007dc36  add     r8, 18h
0x18007dc3a  lea     rdx, [rbp+180h+var_200]
0x18007dc3e  mov     rcx, qword ptr [rsp+280h+var_238+8]
0x18007dc43  call    ?ConnectPaymentApp@PaymentRequestTransaction@Service@Mediator@Payment@Windows@@QEAA?AV?$unique_struct@U_PaymentServiceTransaction@@$$A6AXPEAU1@@Z$1?FreePaymentServiceTransaction@@YAX0@Z$$T$0A@@wil@@AEAVRpcCallManager@2345@@Z; Windows::Payment::Mediator::Service::PaymentRequestTransaction::ConnectPaymentApp(Windows::Payment::Mediator::Service::RpcCallManager &)
0x18007dc48  nop
0x18007dc49  mov     qword ptr [rsp+280h+var_248], r13
0x18007dc4e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007dc55  mov     ecx, 0A0h; unsigned __int64
0x18007dc5a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18007dc5f  test    rax, rax
0x18007dc62  jnz     short loc_18007DC6E
0x18007dc64  mov     edi, 8007000Eh
0x18007dc69  jmp     loc_18007DD21
0x18007dc6e  mov     rcx, rax; this
0x18007dc71  call    ??0PaymentServiceTransactionImpl@Service@Mediator@Payment@Windows@@QEAA@XZ; Windows::Payment::Mediator::Service::PaymentServiceTransactionImpl::PaymentServiceTransactionImpl(void)
0x18007dc76  mov     rbx, rax
0x18007dc79  mov     qword ptr [rsp+280h+var_248+8], rax
0x18007dc7e  mov     qword ptr [rsp+280h+var_228+8], r13
0x18007dc83  lea     rax, off_1800A1420
0x18007dc8a  mov     [rbp+180h+var_130], rax
0x18007dc8e  mov     [rbp+180h+var_128], rbx
0x18007dc92  lea     rax, [rsp+280h+var_238+8]
0x18007dc97  mov     [rbp+180h+var_120], rax
0x18007dc9b  lea     rax, [rbp+180h+var_130]
0x18007dc9f  mov     [rbp+180h+var_F8], rax
0x18007dca6  lea     rdx, [rbp+180h+var_130]
0x18007dcaa  lea     rcx, aWindowsPayment_8; "Windows::Payment::Mediator::Service::Pa"...
0x18007dcb1  call    ?EncapsulateCallWithLogging@RpcCallManager@Service@Mediator@Payment@Windows@@SAJPEBDAEBV?$function@$$A6AXXZ@std@@@Z; Windows::Payment::Mediator::Service::RpcCallManager::EncapsulateCallWithLogging(char const *,std::function<void (void)> const &)
0x18007dcb6  mov     edi, eax
0x18007dcb8  mov     rcx, [rbp+180h+var_F8]
0x18007dcbf  test    rcx, rcx
0x18007dcc2  jz      short loc_18007DCDA
0x18007dcc4  mov     rax, [rcx]
0x18007dcc7  lea     rdx, [rbp+180h+var_130]
0x18007dccb  cmp     rcx, rdx
0x18007dcce  setnz   dl
0x18007dcd1  mov     rax, [rax+20h]
0x18007dcd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dcda  test    edi, edi
0x18007dcdc  jns     short loc_18007DCF5
0x18007dcde  test    rbx, rbx
0x18007dce1  jz      short loc_18007DCF3
0x18007dce3  mov     rax, [rbx]
0x18007dce6  mov     rcx, rbx
0x18007dce9  mov     rax, [rax+10h]
0x18007dced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dcf2  nop
0x18007dcf3  jmp     short loc_18007DD21
0x18007dcf5  mov     rax, [rbx]
0x18007dcf8  lea     r8, [rsp+280h+var_248]
0x18007dcfd  lea     rdx, _GUID_e1aeef9c_ea3a_46c6_aa0c_6cc89d7c7698
0x18007dd04  mov     rcx, rbx
0x18007dd07  mov     rax, [rax]
0x18007dd0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dd0f  mov     edi, eax
0x18007dd11  mov     rax, [rbx]
0x18007dd14  mov     rcx, rbx
0x18007dd17  mov     rax, [rax+10h]
0x18007dd1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dd20  nop
0x18007dd21  mov     rcx, [rbp+188h]; this
0x18007dd28  test    edi, edi
0x18007dd2a  js      loc_18007DEC9
0x18007dd30  movups  xmm6, [rbp+180h+var_200]
0x18007dd34  movups  xmm7, [rbp+180h+var_1F0]
0x18007dd38  movups  xmm8, [rbp+180h+var_1E0]
0x18007dd3d  movups  xmm9, [rbp+180h+var_1D0]
0x18007dd42  movups  xmm10, [rbp+180h+var_1C0]
0x18007dd47  movups  xmm11, [rbp+180h+var_1B0]
0x18007dd4c  movups  xmm12, [rbp+180h+var_1A0]
0x18007dd51  movups  xmm13, [rbp+180h+var_190]
0x18007dd56  movups  xmm14, [rbp+180h+var_180]
0x18007dd5b  movups  xmm15, [rbp+180h+var_170]
0x18007dd60  movups  xmm0, [rbp+180h+var_160]
0x18007dd64  movups  [rsp+280h+var_248+8], xmm0
0x18007dd69  movups  xmm0, [rbp+180h+var_150]
0x18007dd6d  movups  [rsp+280h+var_228+8], xmm0
0x18007dd72  movups  xmm0, [rbp+180h+var_140]
0x18007dd76  movups  xmmword ptr [rsp+280h+var_218+8], xmm0
0x18007dd7b  xor     edx, edx; Val
0x18007dd7d  mov     r8d, 0D0h; Size
0x18007dd83  lea     rcx, [rbp+180h+var_200]; void *
0x18007dd87  call    memset_0
0x18007dd8c  mov     rax, [r15+10h]
0x18007dd90  mov     rcx, [rax]
0x18007dd93  movups  xmmword ptr [rcx], xmm6
0x18007dd96  movups  xmmword ptr [rcx+10h], xmm7
0x18007dd9a  movups  xmmword ptr [rcx+20h], xmm8
0x18007dd9f  movups  xmmword ptr [rcx+30h], xmm9
0x18007dda4  movups  xmmword ptr [rcx+40h], xmm10
0x18007dda9  movups  xmmword ptr [rcx+50h], xmm11
0x18007ddae  movups  xmmword ptr [rcx+60h], xmm12
0x18007ddb3  movups  xmmword ptr [rcx+70h], xmm13
0x18007ddb8  movups  xmmword ptr [rcx+80h], xmm14
0x18007ddc0  movups  xmmword ptr [rcx+90h], xmm15
0x18007ddc8  movups  xmm0, [rsp+280h+var_248+8]
0x18007ddcd  movups  xmmword ptr [rcx+0A0h], xmm0
0x18007ddd4  movups  xmm1, [rsp+280h+var_228+8]
0x18007ddd9  movups  xmmword ptr [rcx+0B0h], xmm1
0x18007dde0  movups  xmm0, xmmword ptr [rsp+280h+var_218+8]
0x18007dde5  movups  xmmword ptr [rcx+0C0h], xmm0
0x18007ddec  mov     rdx, qword ptr [rsp+280h+var_248]
0x18007ddf1  mov     qword ptr [rsp+280h+var_248], r13
0x18007ddf6  mov     rax, [r15+18h]
0x18007ddfa  mov     rcx, [rax]
0x18007ddfd  mov     [rcx], rdx
0x18007de00  mov     rcx, qword ptr [rsp+280h+var_248]
0x18007de05  test    rcx, rcx
0x18007de08  jz      short loc_18007DE1C
0x18007de0a  mov     qword ptr [rsp+280h+var_248], r13
0x18007de0f  mov     rax, [rcx]
0x18007de12  mov     rax, [rax+10h]
0x18007de16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007de1b  nop
0x18007de1c  lea     rcx, [rbp+180h+var_200]; struct _PaymentServiceTransaction *
0x18007de20  call    ?FreePaymentServiceTransaction@@YAXPEAU_PaymentServiceTransaction@@@Z; FreePaymentServiceTransaction(_PaymentServiceTransaction *)
0x18007de25  nop
0x18007de26  mov     rbx, qword ptr [rsp+280h+var_228]
0x18007de2b  test    rbx, rbx
0x18007de2e  jz      short loc_18007DE67
0x18007de30  or      eax, 0FFFFFFFFh
0x18007de33  lock xadd [rbx+8], eax
0x18007de38  cmp     eax, 1
0x18007de3b  jnz     short loc_18007DE67
0x18007de3d  mov     rax, [rbx]
0x18007de40  mov     rcx, rbx
0x18007de43  mov     rax, [rax]
0x18007de46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007de4b  or      eax, 0FFFFFFFFh
0x18007de4e  lock xadd [rbx+0Ch], eax
0x18007de53  cmp     eax, 1
0x18007de56  jnz     short loc_18007DE67
0x18007de58  mov     rax, [rbx]
0x18007de5b  mov     rcx, rbx
0x18007de5e  mov     rax, [rax+8]
0x18007de62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007de67  mov     rcx, [rbp+180h+var_F0]
0x18007de6e  xor     rcx, rsp; StackCookie
0x18007de71  call    __security_check_cookie
0x18007de76  lea     r11, [rsp+280h+var_38]
0x18007de7e  movaps  xmm6, xmmword ptr [r11-18h]
0x18007de83  movaps  xmm7, xmmword ptr [r11-28h]
0x18007de88  movaps  xmm8, xmmword ptr [r11-38h]
0x18007de8d  movaps  xmm9, xmmword ptr [r11-48h]
0x18007de92  movaps  xmm10, xmmword ptr [r11-58h]
0x18007de97  movaps  xmm11, xmmword ptr [r11-68h]
0x18007de9c  movaps  xmm12, xmmword ptr [r11-78h]
0x18007dea1  movaps  xmm13, xmmword ptr [r11-88h]
0x18007dea9  movaps  xmm14, xmmword ptr [r11-98h]
0x18007deb1  movaps  xmm15, xmmword ptr [r11-0A8h]
0x18007deb9  mov     rsp, r11
0x18007debc  pop     r15
0x18007debe  pop     r14
0x18007dec0  pop     r13
0x18007dec2  pop     r12
0x18007dec4  pop     rdi
0x18007dec5  pop     rsi
0x18007dec6  pop     rbx
0x18007dec7  pop     rbp
0x18007dec8  retn
0x18007dec9  mov     r9d, edi; char *
0x18007decc  lea     r8, aOnecoreuapDsNf_21; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x18007ded3  mov     edx, 3Fh ; '?'; void *
0x18007ded8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
