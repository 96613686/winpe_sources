# ConnectedStorage::Context::DeleteContainerStart(std::shared_ptr<ConnectedStorage::ContextOperationToken>,ConnectedStorage::SimpleHStringWrapper,std::shared_ptr<ConnectedStorage::DeleteData>)

- ea: `0x18005c678`
- end: `0x18005c8d1`
- name: `?DeleteContainerStart@Context@ConnectedStorage@@AEAAXV?$shared_ptr@VContextOperationToken@ConnectedStorage@@@std@@VSimpleHStringWrapper@2@V?$shared_ptr@UDeleteData@ConnectedStorage@@@4@@Z`
- size: `601`
- prototype: `__int64 __fastcall(ConnectedStorage::Context *this)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting`

## callers

- `0x18005fc80`

## callees

- `0x18000c218`
- `0x18000cb9c`
- `0x18000d2b8`
- `0x180010f28`
- `0x180011b94`
- `0x1800190f0`
- `0x180019128`
- `0x18002a1dc`
- `0x1800596f4`
- `0x18005acac`
- `0x18005bdec`
- `0x18005c3dc`
- `0x18005c678`
- `0x1800609b0`
- `0x180064b44`
- `0x180074518`
- `0x1800748c4`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c83d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c83d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c89b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c89b`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall ConnectedStorage::Context::DeleteContainerStart(
        ConnectedStorage::Context *this,
        _QWORD *a2,
        HSTRING *a3,
        _QWORD *a4)
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

  if ( !*a4
    || !(unsigned __int8)ConnectedStorage::OperationData<IStorageReadHandler,AsyncIStorageReadHandler>::CheckCanceled(*a4) )
  {
    if ( *a4
      && *((_DWORD *)this + 21) == 1
      && *((_DWORD *)this + 20) == 1
      && ConnectedStorage::ContainerIndex::IsContainerSyncRequired(
           *((ConnectedStorage::ContainerIndex **)this + 38),
           (const struct ConnectedStorage::SimpleHStringWrapper *)a3) )
    {
      ConnectedStorage::Mutex::Lock::Lock(
        (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
        (struct _RTL_CRITICAL_SECTION *)((char *)this + 328),
        v8);
      ConnectedStorage::HasExecuteQueue<ConnectedStorage::DownloadContainer>::weak_from_this((char *)this + 8, &v23);
      std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(v27, &v23);
      std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(&v28, a2);
      ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&newString, a3);
      std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(v30, a4);
      v32 = 0;
      v32 = std::_Global_new_std::_Func_impl_no_alloc__lambda_637c939af204f079d472994f12457f3c__void_long___lambda_637c939af204f079d472994f12457f3c___(v27);
      v9 = *((_QWORD *)this + 38);
      v10 = *a4 + 32LL;
      (*(void (__fastcall **)(ConnectedStorage::Context *))(*(_QWORD *)this + 8LL))(this);
      std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(&v19, (_QWORD *)this + 3);
      v13 = ConnectedStorage::ActivatingContainer::Create(
              (unsigned int)&v21,
              (unsigned int)&v19,
              v11,
              v12,
              (__int64)this + 200,
              v10,
              v9,
              (__int64)a3,
              (__int64)v31);
      std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=((char *)this + 488, v13);
      if ( v22 )
        std::_Ref_count_base::_Decref(v22);
      if ( v20 )
        std::_Ref_count_base::_Decwref(v20);
      std::function<long (void)>::~function<long (void)>(v31);
      lambda_faef4cd59434e98fec4a82a064f14bae_::__lambda_faef4cd59434e98fec4a82a064f14bae_(v27);
      ConnectedStorage::ActivatingContainer::Start(*((ConnectedStorage::ActivatingContainer **)this + 61));
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
      ConnectedStorage::Context::DeleteContainerImpl(this, (__int64)v15, v16, Quota);
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
0x18005c678  mov     rax, rsp
0x18005c67b  mov     [rax+8], rbx
0x18005c67f  mov     [rax+20h], r9
0x18005c683  mov     [rax+18h], r8
0x18005c687  mov     [rax+10h], rdx
0x18005c68b  push    rbp
0x18005c68c  push    rsi
0x18005c68d  push    rdi
0x18005c68e  push    r12
0x18005c690  push    r13
0x18005c692  push    r14
0x18005c694  push    r15
0x18005c696  lea     rbp, [rax-58h]
0x18005c69a  sub     rsp, 120h
0x18005c6a1  mov     r15, r9
0x18005c6a4  mov     r14, r8
0x18005c6a7  mov     r13, rdx
0x18005c6aa  mov     r12, rcx
0x18005c6ad  mov     rcx, [r9]
0x18005c6b0  test    rcx, rcx
0x18005c6b3  jz      short loc_18005C6C2
0x18005c6b5  call    ?CheckCanceled@?$OperationData@UIStorageReadHandler@@UAsyncIStorageReadHandler@@@ConnectedStorage@@QEAA_NXZ; ConnectedStorage::OperationData<IStorageReadHandler,AsyncIStorageReadHandler>::CheckCanceled(void)
0x18005c6ba  test    al, al
0x18005c6bc  jnz     loc_18005C889
0x18005c6c2  cmp     qword ptr [r15], 0
0x18005c6c6  jz      loc_18005C845
0x18005c6cc  cmp     dword ptr [r12+54h], 1
0x18005c6d2  jnz     loc_18005C845
0x18005c6d8  cmp     dword ptr [r12+50h], 1
0x18005c6de  jnz     loc_18005C845
0x18005c6e4  mov     rdx, r14; struct ConnectedStorage::SimpleHStringWrapper *
0x18005c6e7  mov     rcx, [r12+130h]; this
0x18005c6ef  call    ?IsContainerSyncRequired@ContainerIndex@ConnectedStorage@@QEBA_NAEBVSimpleHStringWrapper@2@@Z; ConnectedStorage::ContainerIndex::IsContainerSyncRequired(ConnectedStorage::SimpleHStringWrapper const &)
0x18005c6f4  test    al, al
0x18005c6f6  jz      loc_18005C845
0x18005c6fc  lea     rdx, [r12+148h]; struct ConnectedStorage::Mutex *
0x18005c704  lea     rcx, [rbp+50h+lpCriticalSection]; this
0x18005c708  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18005c70d  nop
0x18005c70e  lea     rdx, [rsp+150h+var_E0]
0x18005c713  lea     rcx, [r12+8]
0x18005c718  call    ?weak_from_this@?$HasExecuteQueue@VDownloadContainer@ConnectedStorage@@@ConnectedStorage@@QEAA?AV?$weak_ptr@VDownloadContainer@ConnectedStorage@@@std@@XZ; ConnectedStorage::HasExecuteQueue<ConnectedStorage::DownloadContainer>::weak_from_this(void)
0x18005c71d  nop
0x18005c71e  lea     rdx, [rsp+150h+var_E0]
0x18005c723  lea     rcx, [rbp+50h+var_B0]
0x18005c727  call    ??$?0VContext@ConnectedStorage@@$0A@@?$weak_ptr@VContext@ConnectedStorage@@@std@@QEAA@AEBV?$shared_ptr@VContext@ConnectedStorage@@@1@@Z; std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(std::shared_ptr<ConnectedStorage::Context> const &)
0x18005c72c  nop
0x18005c72d  mov     rdx, r13
0x18005c730  lea     rcx, [rbp+50h+var_A0]
0x18005c734  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x18005c739  nop
0x18005c73a  mov     rdx, r14; struct ConnectedStorage::SimpleHStringWrapper *
0x18005c73d  lea     rcx, [rbp+50h+newString]; newString
0x18005c741  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x18005c746  mov     rdx, r15
0x18005c749  lea     rcx, [rbp+50h+var_88]
0x18005c74d  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x18005c752  nop
0x18005c753  mov     [rbp+50h+var_38], 0
0x18005c75b  lea     rcx, [rbp+50h+var_B0]
0x18005c75f  call    std___Global_new_std___Func_impl_no_alloc__lambda_637c939af204f079d472994f12457f3c__void_long___lambda_637c939af204f079d472994f12457f3c___
0x18005c764  mov     [rbp+50h+var_38], rax
0x18005c768  mov     rdi, [r12+130h]
0x18005c770  mov     rbx, [r15]
0x18005c773  add     rbx, 20h ; ' '
0x18005c777  mov     rax, [r12]
0x18005c77b  mov     rcx, r12
0x18005c77e  mov     rax, [rax+8]
0x18005c782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c787  mov     r9, rax
0x18005c78a  mov     rcx, [r15]
0x18005c78d  mov     r8, [rcx+98h]
0x18005c794  lea     rdx, [r12+18h]
0x18005c799  lea     rcx, [rsp+150h+var_100]
0x18005c79e  call    ??$?0VContext@ConnectedStorage@@$0A@@?$weak_ptr@VContext@ConnectedStorage@@@std@@QEAA@AEBV?$shared_ptr@VContext@ConnectedStorage@@@1@@Z; std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(std::shared_ptr<ConnectedStorage::Context> const &)
0x18005c7a3  nop
0x18005c7a4  lea     rcx, [r12+0C8h]
0x18005c7ac  lea     rax, [rbp+50h+var_70]
0x18005c7b0  mov     [rsp+40h], rax
0x18005c7b5  mov     [rsp+150h+var_118], r14
0x18005c7ba  mov     [rsp+150h+var_120], rdi
0x18005c7bf  mov     [rsp+150h+var_128], rbx
0x18005c7c4  mov     [rsp+150h+var_130], rcx
0x18005c7c9  lea     rdx, [rsp+150h+var_100]
0x18005c7ce  lea     rcx, [rsp+150h+var_F0]
0x18005c7d3  call    ?Create@ActivatingContainer@ConnectedStorage@@SA?AV?$shared_ptr@$$CBVActivatingContainer@ConnectedStorage@@@std@@AEBV?$weak_ptr@VExecuteQueue@ConnectedStorage@@@4@_KAEBVContextDesc@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@AEBVCallerInfo@2@PEBVContainerIndex@2@AEBVSimpleHStringWrapper@2@AEBV?$function@$$A6AXJ@Z@4@@Z; ConnectedStorage::ActivatingContainer::Create(std::weak_ptr<ConnectedStorage::ExecuteQueue> const &,unsigned __int64,ConnectedStorage::ContextDesc const &,std::wstring const &,ConnectedStorage::CallerInfo const &,ConnectedStorage::ContainerIndex const *,ConnectedStorage::SimpleHStringWrapper const &,std::function<void (long)> const &)
0x18005c7d8  mov     rdx, rax
0x18005c7db  lea     rcx, [r12+1E8h]
0x18005c7e3  call    ??4?$shared_ptr@$$CBVActivatingContainer@ConnectedStorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(std::shared_ptr<ConnectedStorage::ActivatingContainer const> &&)
0x18005c7e8  mov     rcx, [rsp+150h+var_E8]; this
0x18005c7ed  test    rcx, rcx
0x18005c7f0  jz      short loc_18005C7F8
0x18005c7f2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005c7f7  nop
0x18005c7f8  mov     rcx, [rsp+150h+var_F8]; this
0x18005c7fd  test    rcx, rcx
0x18005c800  jz      short loc_18005C808
0x18005c802  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18005c807  nop
0x18005c808  lea     rcx, [rbp+50h+var_70]
0x18005c80c  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18005c811  nop
0x18005c812  lea     rcx, [rbp+50h+var_B0]
0x18005c816  call    _lambda_faef4cd59434e98fec4a82a064f14bae_____lambda_faef4cd59434e98fec4a82a064f14bae_
0x18005c81b  mov     rcx, [r12+1E8h]; this
0x18005c823  call    ?Start@ActivatingContainer@ConnectedStorage@@QEBAXXZ; ConnectedStorage::ActivatingContainer::Start(void)
0x18005c828  nop
0x18005c829  mov     rcx, [rsp+150h+var_D8]; this
0x18005c82e  test    rcx, rcx
0x18005c831  jz      short loc_18005C839
0x18005c833  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18005c838  nop
0x18005c839  mov     rcx, [rbp+50h+lpCriticalSection]; lpCriticalSection
0x18005c83d  call    cs:__imp_LeaveCriticalSection
0x18005c843  jmp     short loc_18005C889
0x18005c845  lea     rax, [rbp+50h+lpCriticalSection]
0x18005c849  mov     [rsp+150h+var_E0], rax
0x18005c84e  mov     rdx, r15
0x18005c851  lea     rcx, [rbp+50h+lpCriticalSection]
0x18005c855  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x18005c85a  mov     rbx, rax
0x18005c85d  mov     rdx, r14; struct ConnectedStorage::SimpleHStringWrapper *
0x18005c860  lea     rcx, [rsp+150h+var_F0]; newString
0x18005c865  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x18005c86a  mov     r8, rax
0x18005c86d  mov     rdx, r13
0x18005c870  lea     rcx, [rbp+50h+var_C0]
0x18005c874  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x18005c879  nop
0x18005c87a  mov     r9, rbx
0x18005c87d  mov     rdx, rax
0x18005c880  mov     rcx, r12; this
0x18005c883  call    ?DeleteContainerImpl@Context@ConnectedStorage@@AEAAXV?$shared_ptr@VContextOperationToken@ConnectedStorage@@@std@@VSimpleHStringWrapper@2@V?$shared_ptr@UDeleteData@ConnectedStorage@@@4@@Z; ConnectedStorage::Context::DeleteContainerImpl(std::shared_ptr<ConnectedStorage::ContextOperationToken>,ConnectedStorage::SimpleHStringWrapper,std::shared_ptr<ConnectedStorage::DeleteData>)
0x18005c888  nop
0x18005c889  mov     rcx, [r13+8]; this
0x18005c88d  test    rcx, rcx
0x18005c890  jz      short loc_18005C898
0x18005c892  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005c897  nop
0x18005c898  mov     rcx, [r14]; string
0x18005c89b  call    cs:__imp_WindowsDeleteString
0x18005c8a1  mov     qword ptr [r14], 0
0x18005c8a8  mov     rcx, [r15+8]; this
0x18005c8ac  test    rcx, rcx
0x18005c8af  jz      short loc_18005C8B6
0x18005c8b1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005c8b6  mov     rbx, [rsp+150h+arg_0]
0x18005c8be  add     rsp, 120h
0x18005c8c5  pop     r15
0x18005c8c7  pop     r14
0x18005c8c9  pop     r13
0x18005c8cb  pop     r12
0x18005c8cd  pop     rdi
0x18005c8ce  pop     rsi
0x18005c8cf  pop     rbp
0x18005c8d0  retn
```
