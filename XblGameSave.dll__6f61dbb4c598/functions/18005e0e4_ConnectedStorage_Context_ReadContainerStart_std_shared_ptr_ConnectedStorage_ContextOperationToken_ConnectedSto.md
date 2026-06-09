# ConnectedStorage::Context::ReadContainerStart(std::shared_ptr<ConnectedStorage::ContextOperationToken>,ConnectedStorage::SimpleHStringWrapper,std::shared_ptr<ConnectedStorage::ReadData>)

- ea: `0x18005e0e4`
- end: `0x18005e32e`
- name: `?ReadContainerStart@Context@ConnectedStorage@@AEAAXV?$shared_ptr@VContextOperationToken@ConnectedStorage@@@std@@VSimpleHStringWrapper@2@V?$shared_ptr@UReadData@ConnectedStorage@@@4@@Z`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting`

## callers

- `0x1800601a0`

## callees

- `0x18000c218`
- `0x18000cb9c`
- `0x18000d2b8`
- `0x180010f28`
- `0x180011b94`
- `0x1800190f0`
- `0x180019128`
- `0x18002a1dc`
- `0x180059bc8`
- `0x18005acac`
- `0x18005bdec`
- `0x18005df14`
- `0x18005e0e4`
- `0x1800609b0`
- `0x180064b44`
- `0x180074518`
- `0x1800748c4`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e29a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e29a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e2f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e2f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall ConnectedStorage::Context::ReadContainerStart(__int64 a1, _QWORD *a2, HSTRING *a3, _QWORD *a4)
{
  char *v8; // r8
  __int64 v9; // rdi
  __int64 v10; // rbx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rax
  _QWORD *Quota; // rbx
  _QWORD *v15; // rax
  const struct ConnectedStorage::SimpleHStringWrapper *v16; // r8
  std::_Ref_count_base *v17; // rcx
  std::_Ref_count_base *v18; // rcx
  __int64 v19; // [rsp+58h] [rbp-B0h] BYREF
  std::_Ref_count_base *v20; // [rsp+60h] [rbp-A8h]
  HSTRING v21; // [rsp+68h] [rbp-A0h] BYREF
  std::_Ref_count_base *v22; // [rsp+70h] [rbp-98h]
  LPCRITICAL_SECTION *v23; // [rsp+78h] [rbp-90h] BYREF
  std::_Ref_count_base *v24; // [rsp+80h] [rbp-88h]
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v26; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v27[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v28; // [rsp+B8h] [rbp-50h] BYREF
  HSTRING newString; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v30[3]; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v31[56]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v32; // [rsp+120h] [rbp+18h]

  if ( !(unsigned __int8)ConnectedStorage::OperationData<IStorageReadHandler,AsyncIStorageReadHandler>::CheckCanceled(*a4) )
  {
    if ( *(_DWORD *)(a1 + 84) == 1
      && *(_DWORD *)(a1 + 80) == 1
      && ConnectedStorage::ContainerIndex::IsContainerSyncRequired(
           *(ConnectedStorage::ContainerIndex **)(a1 + 304),
           (const struct ConnectedStorage::SimpleHStringWrapper *)a3) )
    {
      ConnectedStorage::Mutex::Lock::Lock(
        (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
        (struct _RTL_CRITICAL_SECTION *)(a1 + 328),
        v8);
      ConnectedStorage::HasExecuteQueue<ConnectedStorage::DownloadContainer>::weak_from_this(a1 + 8, &v23);
      std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(v27, &v23);
      std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(&v28, a2);
      ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&newString, a3);
      std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(v30, a4);
      v32 = 0;
      v32 = std::_Global_new_std::_Func_impl_no_alloc__lambda_faef4cd59434e98fec4a82a064f14bae__void_long___lambda_faef4cd59434e98fec4a82a064f14bae___(v27);
      v9 = *(_QWORD *)(a1 + 304);
      v10 = *a4 + 32LL;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(&v19, (_QWORD *)(a1 + 24));
      v13 = ConnectedStorage::ActivatingContainer::Create(
              (unsigned int)&v21,
              (unsigned int)&v19,
              v11,
              v12,
              a1 + 200,
              v10,
              v9,
              (__int64)a3,
              (__int64)v31);
      std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(a1 + 488, v13);
      if ( v22 )
        std::_Ref_count_base::_Decref(v22);
      if ( v20 )
        std::_Ref_count_base::_Decwref(v20);
      std::function<long (void)>::~function<long (void)>(v31);
      lambda_faef4cd59434e98fec4a82a064f14bae_::__lambda_faef4cd59434e98fec4a82a064f14bae_(v27);
      ConnectedStorage::ActivatingContainer::Start(*(ConnectedStorage::ActivatingContainer **)(a1 + 488));
      if ( v24 )
        std::_Ref_count_base::_Decwref(v24);
      LeaveCriticalSection(lpCriticalSection[0]);
    }
    else
    {
      v23 = lpCriticalSection;
      Quota = std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(
                lpCriticalSection,
                a4);
      ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v21, a3);
      v15 = std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(&v26, a2);
      ConnectedStorage::Context::ReadContainerImpl(a1, v15, v16, Quota);
    }
  }
  v17 = (std::_Ref_count_base *)a2[1];
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  WindowsDeleteString(*a3);
  *a3 = 0;
  v18 = (std::_Ref_count_base *)a4[1];
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
}

```

## disassembly

```asm
0x18005e0e4  mov     rax, rsp
0x18005e0e7  mov     [rax+8], rbx
0x18005e0eb  mov     [rax+20h], r9
0x18005e0ef  mov     [rax+18h], r8
0x18005e0f3  mov     [rax+10h], rdx
0x18005e0f7  push    rbp
0x18005e0f8  push    rsi
0x18005e0f9  push    rdi
0x18005e0fa  push    r12
0x18005e0fc  push    r13
0x18005e0fe  push    r14
0x18005e100  push    r15
0x18005e102  lea     rbp, [rax-58h]
0x18005e106  sub     rsp, 120h
0x18005e10d  mov     r15, r9
0x18005e110  mov     r14, r8
0x18005e113  mov     r13, rdx
0x18005e116  mov     r12, rcx
0x18005e119  mov     rcx, [r9]
0x18005e11c  call    ?CheckCanceled@?$OperationData@UIStorageReadHandler@@UAsyncIStorageReadHandler@@@ConnectedStorage@@QEAA_NXZ; ConnectedStorage::OperationData<IStorageReadHandler,AsyncIStorageReadHandler>::CheckCanceled(void)
0x18005e121  test    al, al
0x18005e123  jnz     loc_18005E2E6
0x18005e129  cmp     dword ptr [r12+54h], 1
0x18005e12f  jnz     loc_18005E2A2
0x18005e135  cmp     dword ptr [r12+50h], 1
0x18005e13b  jnz     loc_18005E2A2
0x18005e141  mov     rdx, r14; struct ConnectedStorage::SimpleHStringWrapper *
0x18005e144  mov     rcx, [r12+130h]; this
0x18005e14c  call    ?IsContainerSyncRequired@ContainerIndex@ConnectedStorage@@QEBA_NAEBVSimpleHStringWrapper@2@@Z; ConnectedStorage::ContainerIndex::IsContainerSyncRequired(ConnectedStorage::SimpleHStringWrapper const &)
0x18005e151  test    al, al
0x18005e153  jz      loc_18005E2A2
0x18005e159  lea     rdx, [r12+148h]; struct ConnectedStorage::Mutex *
0x18005e161  lea     rcx, [rbp+50h+lpCriticalSection]; this
0x18005e165  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18005e16a  nop
0x18005e16b  lea     rdx, [rsp+150h+var_E0]
0x18005e170  lea     rcx, [r12+8]
0x18005e175  call    ?weak_from_this@?$HasExecuteQueue@VDownloadContainer@ConnectedStorage@@@ConnectedStorage@@QEAA?AV?$weak_ptr@VDownloadContainer@ConnectedStorage@@@std@@XZ; ConnectedStorage::HasExecuteQueue<ConnectedStorage::DownloadContainer>::weak_from_this(void)
0x18005e17a  nop
0x18005e17b  lea     rdx, [rsp+150h+var_E0]
0x18005e180  lea     rcx, [rbp+50h+var_B0]
0x18005e184  call    ??$?0VContext@ConnectedStorage@@$0A@@?$weak_ptr@VContext@ConnectedStorage@@@std@@QEAA@AEBV?$shared_ptr@VContext@ConnectedStorage@@@1@@Z; std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(std::shared_ptr<ConnectedStorage::Context> const &)
0x18005e189  nop
0x18005e18a  mov     rdx, r13
0x18005e18d  lea     rcx, [rbp+50h+var_A0]
0x18005e191  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x18005e196  nop
0x18005e197  mov     rdx, r14; struct ConnectedStorage::SimpleHStringWrapper *
0x18005e19a  lea     rcx, [rbp+50h+newString]; newString
0x18005e19e  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x18005e1a3  mov     rdx, r15
0x18005e1a6  lea     rcx, [rbp+50h+var_88]
0x18005e1aa  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x18005e1af  nop
0x18005e1b0  mov     [rbp+50h+var_38], 0
0x18005e1b8  lea     rcx, [rbp+50h+var_B0]
0x18005e1bc  call    std___Global_new_std___Func_impl_no_alloc__lambda_faef4cd59434e98fec4a82a064f14bae__void_long___lambda_faef4cd59434e98fec4a82a064f14bae___
0x18005e1c1  mov     [rbp+50h+var_38], rax
0x18005e1c5  mov     rdi, [r12+130h]
0x18005e1cd  mov     rbx, [r15]
0x18005e1d0  add     rbx, 20h ; ' '
0x18005e1d4  mov     rax, [r12]
0x18005e1d8  mov     rcx, r12
0x18005e1db  mov     rax, [rax+8]
0x18005e1df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e1e4  mov     r9, rax
0x18005e1e7  mov     rcx, [r15]
0x18005e1ea  mov     r8, [rcx+98h]
0x18005e1f1  lea     rdx, [r12+18h]
0x18005e1f6  lea     rcx, [rsp+150h+var_100]
0x18005e1fb  call    ??$?0VContext@ConnectedStorage@@$0A@@?$weak_ptr@VContext@ConnectedStorage@@@std@@QEAA@AEBV?$shared_ptr@VContext@ConnectedStorage@@@1@@Z; std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(std::shared_ptr<ConnectedStorage::Context> const &)
0x18005e200  nop
0x18005e201  lea     rcx, [r12+0C8h]
0x18005e209  lea     rax, [rbp+50h+var_70]
0x18005e20d  mov     [rsp+40h], rax
0x18005e212  mov     [rsp+150h+var_118], r14
0x18005e217  mov     [rsp+150h+var_120], rdi
0x18005e21c  mov     [rsp+150h+var_128], rbx
0x18005e221  mov     [rsp+150h+var_130], rcx
0x18005e226  lea     rdx, [rsp+150h+var_100]
0x18005e22b  lea     rcx, [rsp+150h+var_F0]
0x18005e230  call    ?Create@ActivatingContainer@ConnectedStorage@@SA?AV?$shared_ptr@$$CBVActivatingContainer@ConnectedStorage@@@std@@AEBV?$weak_ptr@VExecuteQueue@ConnectedStorage@@@4@_KAEBVContextDesc@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@AEBVCallerInfo@2@PEBVContainerIndex@2@AEBVSimpleHStringWrapper@2@AEBV?$function@$$A6AXJ@Z@4@@Z; ConnectedStorage::ActivatingContainer::Create(std::weak_ptr<ConnectedStorage::ExecuteQueue> const &,unsigned __int64,ConnectedStorage::ContextDesc const &,std::wstring const &,ConnectedStorage::CallerInfo const &,ConnectedStorage::ContainerIndex const *,ConnectedStorage::SimpleHStringWrapper const &,std::function<void (long)> const &)
0x18005e235  mov     rdx, rax
0x18005e238  lea     rcx, [r12+1E8h]
0x18005e240  call    ??4?$shared_ptr@$$CBVActivatingContainer@ConnectedStorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(std::shared_ptr<ConnectedStorage::ActivatingContainer const> &&)
0x18005e245  mov     rcx, [rsp+150h+var_E8]; this
0x18005e24a  test    rcx, rcx
0x18005e24d  jz      short loc_18005E255
0x18005e24f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005e254  nop
0x18005e255  mov     rcx, [rsp+150h+var_F8]; this
0x18005e25a  test    rcx, rcx
0x18005e25d  jz      short loc_18005E265
0x18005e25f  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18005e264  nop
0x18005e265  lea     rcx, [rbp+50h+var_70]
0x18005e269  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18005e26e  nop
0x18005e26f  lea     rcx, [rbp+50h+var_B0]
0x18005e273  call    _lambda_faef4cd59434e98fec4a82a064f14bae_____lambda_faef4cd59434e98fec4a82a064f14bae_
0x18005e278  mov     rcx, [r12+1E8h]; this
0x18005e280  call    ?Start@ActivatingContainer@ConnectedStorage@@QEBAXXZ; ConnectedStorage::ActivatingContainer::Start(void)
0x18005e285  nop
0x18005e286  mov     rcx, [rsp+150h+var_D8]; this
0x18005e28b  test    rcx, rcx
0x18005e28e  jz      short loc_18005E296
0x18005e290  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18005e295  nop
0x18005e296  mov     rcx, [rbp+50h+lpCriticalSection]; lpCriticalSection
0x18005e29a  call    cs:__imp_LeaveCriticalSection
0x18005e2a0  jmp     short loc_18005E2E6
0x18005e2a2  lea     rax, [rbp+50h+lpCriticalSection]
0x18005e2a6  mov     [rsp+150h+var_E0], rax
0x18005e2ab  mov     rdx, r15
0x18005e2ae  lea     rcx, [rbp+50h+lpCriticalSection]
0x18005e2b2  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x18005e2b7  mov     rbx, rax
0x18005e2ba  mov     rdx, r14; struct ConnectedStorage::SimpleHStringWrapper *
0x18005e2bd  lea     rcx, [rsp+150h+var_F0]; newString
0x18005e2c2  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x18005e2c7  mov     r8, rax
0x18005e2ca  mov     rdx, r13
0x18005e2cd  lea     rcx, [rbp+50h+var_C0]
0x18005e2d1  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x18005e2d6  nop
0x18005e2d7  mov     r9, rbx
0x18005e2da  mov     rdx, rax
0x18005e2dd  mov     rcx, r12
0x18005e2e0  call    ?ReadContainerImpl@Context@ConnectedStorage@@AEAAXV?$shared_ptr@VContextOperationToken@ConnectedStorage@@@std@@VSimpleHStringWrapper@2@V?$shared_ptr@UReadData@ConnectedStorage@@@4@@Z; ConnectedStorage::Context::ReadContainerImpl(std::shared_ptr<ConnectedStorage::ContextOperationToken>,ConnectedStorage::SimpleHStringWrapper,std::shared_ptr<ConnectedStorage::ReadData>)
0x18005e2e5  nop
0x18005e2e6  mov     rcx, [r13+8]; this
0x18005e2ea  test    rcx, rcx
0x18005e2ed  jz      short loc_18005E2F5
0x18005e2ef  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005e2f4  nop
0x18005e2f5  mov     rcx, [r14]; string
0x18005e2f8  call    cs:__imp_WindowsDeleteString
0x18005e2fe  mov     qword ptr [r14], 0
0x18005e305  mov     rcx, [r15+8]; this
0x18005e309  test    rcx, rcx
0x18005e30c  jz      short loc_18005E313
0x18005e30e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005e313  mov     rbx, [rsp+150h+arg_0]
0x18005e31b  add     rsp, 120h
0x18005e322  pop     r15
0x18005e324  pop     r14
0x18005e326  pop     r13
0x18005e328  pop     r12
0x18005e32a  pop     rdi
0x18005e32b  pop     rsi
0x18005e32c  pop     rbp
0x18005e32d  retn
```
