# Pal::TaskQueueImplWinRT::startAndAddWorkItem(ABI::Windows::System::Threading::IWorkItemHandler *,std::shared_ptr<Pal::Task> const &)

- ea: `0x18002d438`
- end: `0x18002d7b9`
- name: `?startAndAddWorkItem@TaskQueueImplWinRT@Pal@@AEAAXPEAUIWorkItemHandler@Threading@System@Windows@ABI@@AEBV?$shared_ptr@VTask@Pal@@@std@@@Z`
- size: `897`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002d878`
- `0x18002d92c`

## callees

- `0x18000d090`
- `0x18000dce0`
- `0x180016770`
- `0x180019f3c`
- `0x180021da8`
- `0x18002203c`
- `0x180022078`
- `0x180022988`
- `0x18002468c`
- `0x180024a34`
- `0x180024bc8`
- `0x180025360`
- `0x180025c3c`
- `0x180027054`
- `0x1800279d0`
- `0x18002ab6c`
- `0x18002d438`
- `0x18002d9d8`
- `0x180098010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002d500`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002d5b9`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002d730`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002d500`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002d5b9`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002d730`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002d50b`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002d5c4`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002d73b`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002d50b`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002d5c4`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002d73b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002d474`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002d474`

## string_xrefs

- `0x18002d4a1`: `Windows.System.Threading.ThreadPool`
- `0x18002d4d7`: `Failed to retrieve the activation factory for Windows.System.Threading.ThreadPool`
- `0x18002d590`: `TaskQueueImplWinRT::startAndAddWorkItem - RunWithPriorityAsync failed`
- `0x18002d707`: `TaskQueueImplWinRT::startAndAddWorkItem - put_Completed failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Pal::TaskQueueImplWinRT::startAndAddWorkItem(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64, __int64, __int64 *); // rbx
  int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  int AsyncActionId; // ebx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64); // rsi
  __int64 *v21; // rax
  __int64 v22; // rbx
  int v23; // edi
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v29; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  __int64 pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v33[16]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v34[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v35[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v36[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v37[232]; // [rsp+88h] [rbp-78h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+170h] [rbp+70h] BYREF
  __int64 v39; // [rsp+188h] [rbp+88h]

  ResetEvent(**(HANDLE **)(a1 + 88));
  v29 = 0;
  v31 = 0;
  v39 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Threading.ThreadPool",
    0x24u,
    0x23u);
  v6 = ABI::Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<ABI::Windows::System::Threading::IThreadPoolStatics>>(
         v39,
         &v31);
  if ( v6 < 0 )
  {
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v35);
    v7 = std::operator<<<std::char_traits<char>>(
           v36,
           "Failed to retrieve the activation factory for Windows.System.Threading.ThreadPool");
    v8 = std::operator<<<std::char_traits<char>>(v7, " (HRESULT: 0x");
    v9 = std::ostream::operator<<(v8, std::hex);
    v10 = std::ostream::operator<<(v9, (unsigned int)v6);
    std::operator<<<std::char_traits<char>>(v10, ")");
    std::stringbuf::str(v37, &hstringHeader);
    std::runtime_error::runtime_error((std::exception *)&pExceptionObject);
    throw (std::runtime_error *)&pExceptionObject;
  }
  v11 = v31;
  v12 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v31 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  v13 = v12(v11, a2, 0xFFFFFFFFLL, &v29);
  if ( v13 < 0 )
  {
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v35);
    v14 = std::operator<<<std::char_traits<char>>(
            v36,
            "TaskQueueImplWinRT::startAndAddWorkItem - RunWithPriorityAsync failed");
    v15 = std::operator<<<std::char_traits<char>>(v14, " (HRESULT: 0x");
    v16 = std::ostream::operator<<(v15, std::hex);
    v17 = std::ostream::operator<<(v16, (unsigned int)v13);
    std::operator<<<std::char_traits<char>>(v17, ")");
    std::stringbuf::str(v37, &hstringHeader);
    std::runtime_error::runtime_error((std::exception *)&pExceptionObject);
    throw (std::runtime_error *)&pExceptionObject;
  }
  AsyncActionId = anonymous_namespace_::getAsyncActionId(v29);
  LODWORD(v30) = AsyncActionId;
  pExceptionObject = v29;
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
  std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>(
    v33,
    a3);
  LODWORD(hstringHeader.Reserved.Reserved1) = AsyncActionId;
  Pal::TaskQueueImplWinRT::AsyncActionAndTask::AsyncActionAndTask(
    (Pal::TaskQueueImplWinRT::AsyncActionAndTask *)&hstringHeader.Reserved.Reserved2[8],
    (const struct Pal::TaskQueueImplWinRT::AsyncActionAndTask *)&pExceptionObject);
  std::_Tree<std::_Tmap_traits<unsigned int,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>::_Emplace<std::pair<unsigned int,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>(
    (__int64 *)(a1 + 48),
    (__int64)v34,
    (unsigned int *)&hstringHeader);
  Pal::TaskQueueImplWinRT::AsyncActionAndTask::~AsyncActionAndTask((Pal::TaskQueueImplWinRT::AsyncActionAndTask *)&hstringHeader.Reserved.Reserved2[8]);
  Pal::TaskQueueImplWinRT::AsyncActionAndTask::~AsyncActionAndTask((Pal::TaskQueueImplWinRT::AsyncActionAndTask *)&pExceptionObject);
  lambda_8875b34cb5594d1a0f31d9dd8ea00989_::_lambda_8875b34cb5594d1a0f31d9dd8ea00989_(v34, &v30, a1);
  v19 = v29;
  v20 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 48LL);
  v21 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_ABI::Windows::Foundation::IAsyncActionCompletedHandler::___ABI::Windows::Foundation::IAsyncAction___enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__ABI::Windows::Foundation::IAsyncActionCompletedHandler_Microsoft::WRL::FtmBase___lambda_8875b34cb5594d1a0f31d9dd8ea00989_____1_ABI::Windows::Foundation::IAsyncAction___enum_ABI::Windows::Foundation::AsyncStatus___lambda_8875b34cb5594d1a0f31d9dd8ea00989____(
                     &v30,
                     v34);
  v22 = *v21;
  v34[0] = *v21;
  *v21 = 0;
  if ( v30 )
  {
    v30 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::System::Threading::ITimerDestroyedHandler,Microsoft::WRL::FtmBase>>::Release();
  }
  v23 = v20(v19, v22);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v23 < 0 )
  {
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v35);
    v24 = std::operator<<<std::char_traits<char>>(v36, "TaskQueueImplWinRT::startAndAddWorkItem - put_Completed failed");
    v25 = std::operator<<<std::char_traits<char>>(v24, " (HRESULT: 0x");
    v26 = std::ostream::operator<<(v25, std::hex);
    v27 = std::ostream::operator<<(v26, (unsigned int)v23);
    std::operator<<<std::char_traits<char>>(v27, ")");
    std::stringbuf::str(v37, &hstringHeader);
    std::runtime_error::runtime_error((std::exception *)&pExceptionObject);
    throw (std::runtime_error *)&pExceptionObject;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
}

```

## disassembly

```asm
0x18002d438  mov     [rsp-8+arg_18], rbx
0x18002d43d  push    rbp
0x18002d43e  push    rsi
0x18002d43f  push    rdi
0x18002d440  push    r14
0x18002d442  push    r15
0x18002d444  lea     rbp, [rsp-0A0h]
0x18002d44c  sub     rsp, 1A0h
0x18002d453  mov     rax, cs:__security_cookie
0x18002d45a  xor     rax, rsp
0x18002d45d  mov     [rbp+0C0h+var_30], rax
0x18002d464  mov     r15, r8
0x18002d467  mov     r14, rdx
0x18002d46a  mov     rsi, rcx
0x18002d46d  mov     rcx, [rcx+58h]
0x18002d471  mov     rcx, [rcx]; hEvent
0x18002d474  call    cs:__imp_ResetEvent
0x18002d47a  mov     [rsp+1C0h+var_190], 0
0x18002d483  mov     [rsp+1C0h+var_180], 0
0x18002d48c  mov     [rbp+0C0h+var_38], 0
0x18002d497  mov     r9d, 23h ; '#'; unsigned int
0x18002d49d  lea     r8d, [r9+1]; unsigned int
0x18002d4a1  lea     rdx, ?RuntimeClass_Windows_System_Threading_ThreadPool@@3QBGB; "Windows.System.Threading.ThreadPool"
0x18002d4a8  lea     rcx, [rbp+0C0h+hstringHeader]; hstringHeader
0x18002d4ac  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002d4b1  lea     rdx, [rsp+1C0h+var_180]
0x18002d4b6  mov     rcx, [rbp+0C0h+var_38]
0x18002d4bd  call    ??$GetActivationFactory@V?$ComPtr@UIThreadPoolStatics@Threading@System@Windows@ABI@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIThreadPoolStatics@Threading@System@Windows@ABI@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<ABI::Windows::System::Threading::IThreadPoolStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ABI::Windows::System::Threading::IThreadPoolStatics>>)
0x18002d4c2  mov     ebx, eax
0x18002d4c4  test    eax, eax
0x18002d4c6  jns     loc_18002D54E
0x18002d4cc  lea     rcx, [rsp+1C0h+var_150]
0x18002d4d1  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18002d4d6  nop
0x18002d4d7  lea     rdx, aFailedToRetrie_2; "Failed to retrieve the activation facto"...
0x18002d4de  lea     rcx, [rbp+0C0h+var_140]
0x18002d4e2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002d4e7  mov     rcx, rax
0x18002d4ea  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18002d4f1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002d4f6  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18002d4fd  mov     rcx, rax
0x18002d500  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18002d506  mov     edx, ebx
0x18002d508  mov     rcx, rax
0x18002d50b  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18002d511  mov     rcx, rax
0x18002d514  lea     rdx, asc_1800A4BE0; ")"
0x18002d51b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002d520  lea     rdx, [rbp+0C0h+hstringHeader]
0x18002d524  lea     rcx, [rbp+0C0h+var_138]
0x18002d528  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18002d52d  nop
0x18002d52e  lea     rdx, [rbp+0C0h+hstringHeader]
0x18002d532  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x18002d537  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18002d53c  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18002d543  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x18002d548  call    _CxxThrowException_0
0x18002d54e  mov     rdi, [rsp+1C0h+var_180]
0x18002d553  mov     rax, [rdi]
0x18002d556  mov     rbx, [rax+38h]
0x18002d55a  lea     rcx, [rsp+1C0h+var_190]
0x18002d55f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d564  lea     r9, [rsp+1C0h+var_190]
0x18002d569  or      r8d, 0FFFFFFFFh
0x18002d56d  mov     rdx, r14
0x18002d570  mov     rcx, rdi
0x18002d573  mov     rax, rbx
0x18002d576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d57b  mov     ebx, eax
0x18002d57d  test    eax, eax
0x18002d57f  jns     loc_18002D607
0x18002d585  lea     rcx, [rsp+1C0h+var_150]
0x18002d58a  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18002d58f  nop
0x18002d590  lea     rdx, aTaskqueueimplw_0; "TaskQueueImplWinRT::startAndAddWorkItem"...
0x18002d597  lea     rcx, [rbp+0C0h+var_140]
0x18002d59b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002d5a0  mov     rcx, rax
0x18002d5a3  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18002d5aa  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002d5af  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18002d5b6  mov     rcx, rax
0x18002d5b9  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18002d5bf  mov     edx, ebx
0x18002d5c1  mov     rcx, rax
0x18002d5c4  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18002d5ca  mov     rcx, rax
0x18002d5cd  lea     rdx, asc_1800A4BE0; ")"
0x18002d5d4  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002d5d9  lea     rdx, [rbp+0C0h+hstringHeader]
0x18002d5dd  lea     rcx, [rbp+0C0h+var_138]
0x18002d5e1  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18002d5e6  nop
0x18002d5e7  lea     rdx, [rbp+0C0h+hstringHeader]
0x18002d5eb  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x18002d5f0  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18002d5f5  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18002d5fc  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x18002d601  call    _CxxThrowException_0
0x18002d607  mov     rcx, [rsp+1C0h+var_190]
0x18002d60c  call    _anonymous_namespace___getAsyncActionId
0x18002d611  mov     ebx, eax
0x18002d613  mov     dword ptr [rsp+1C0h+var_188], eax
0x18002d617  mov     rcx, [rsp+1C0h+var_190]
0x18002d61c  mov     [rsp+1C0h+pExceptionObject], rcx
0x18002d621  test    rcx, rcx
0x18002d624  jz      short loc_18002D633
0x18002d626  mov     r8, [rcx]
0x18002d629  mov     rax, [r8+8]
0x18002d62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d632  nop
0x18002d633  mov     rdx, r15
0x18002d636  lea     rcx, [rsp+1C0h+var_170]
0x18002d63b  call    ??0?$shared_ptr@VCacheEntry@?$MemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@@Utility@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>(std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry> const &)
0x18002d640  nop
0x18002d641  mov     dword ptr [rbp+0C0h+hstringHeader.Reserved], ebx
0x18002d644  lea     rdx, [rsp+1C0h+pExceptionObject]; struct Pal::TaskQueueImplWinRT::AsyncActionAndTask *
0x18002d649  lea     rcx, [rbp+0C0h+hstringHeader.Reserved+8]; this
0x18002d64d  call    ??0AsyncActionAndTask@TaskQueueImplWinRT@Pal@@QEAA@AEBU012@@Z; Pal::TaskQueueImplWinRT::AsyncActionAndTask::AsyncActionAndTask(Pal::TaskQueueImplWinRT::AsyncActionAndTask const &)
0x18002d652  nop
0x18002d653  lea     rcx, [rsi+30h]
0x18002d657  lea     r8, [rbp+0C0h+hstringHeader]
0x18002d65b  lea     rdx, [rsp+1C0h+var_160]
0x18002d660  call    ??$_Emplace@U?$pair@IUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@@?$_Tree@V?$_Tmap_traits@IUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@IUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@1@@Z; std::_Tree<std::_Tmap_traits<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<uint>,std::allocator<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>::_Emplace<std::pair<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>(std::pair<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask> &&)
0x18002d665  nop
0x18002d666  lea     rcx, [rbp+0C0h+hstringHeader.Reserved+8]; this
0x18002d66a  call    ??1AsyncActionAndTask@TaskQueueImplWinRT@Pal@@QEAA@XZ; Pal::TaskQueueImplWinRT::AsyncActionAndTask::~AsyncActionAndTask(void)
0x18002d66f  nop
0x18002d670  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x18002d675  call    ??1AsyncActionAndTask@TaskQueueImplWinRT@Pal@@QEAA@XZ; Pal::TaskQueueImplWinRT::AsyncActionAndTask::~AsyncActionAndTask(void)
0x18002d67a  mov     r8, rsi
0x18002d67d  lea     rdx, [rsp+1C0h+var_188]
0x18002d682  lea     rcx, [rsp+1C0h+var_160]
0x18002d687  call    _lambda_8875b34cb5594d1a0f31d9dd8ea00989____lambda_8875b34cb5594d1a0f31d9dd8ea00989_
0x18002d68c  mov     rdi, [rsp+1C0h+var_190]
0x18002d691  mov     rax, [rdi]
0x18002d694  mov     rsi, [rax+30h]
0x18002d698  lea     rdx, [rsp+1C0h+var_160]
0x18002d69d  lea     rcx, [rsp+1C0h+var_188]
0x18002d6a2  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_ABI__Windows__Foundation__IAsyncActionCompletedHandler_____ABI__Windows__Foundation__IAsyncAction___enum_ABI__Windows__Foundation__AsyncStatus____DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__ABI__Windows__Foundation__IAsyncActionCompletedHandler_Microsoft__WRL__FtmBase___lambda_8875b34cb5594d1a0f31d9dd8ea00989_____1_ABI__Windows__Foundation__IAsyncAction___enum_ABI__Windows__Foundation__AsyncStatus___lambda_8875b34cb5594d1a0f31d9dd8ea00989____
0x18002d6a7  mov     rbx, [rax]
0x18002d6aa  mov     [rsp+1C0h+var_160], rbx
0x18002d6af  mov     qword ptr [rax], 0
0x18002d6b6  mov     rcx, [rsp+1C0h+var_188]
0x18002d6bb  test    rcx, rcx
0x18002d6be  jz      short loc_18002D6CF
0x18002d6c0  mov     [rsp+1C0h+var_188], 0
0x18002d6c9  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UITimerDestroyedHandler@Threading@System@Windows@ABI@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::System::Threading::ITimerDestroyedHandler,Microsoft::WRL::FtmBase>>::Release(void)
0x18002d6ce  nop
0x18002d6cf  mov     rdx, rbx
0x18002d6d2  mov     rcx, rdi
0x18002d6d5  mov     rax, rsi
0x18002d6d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6dd  mov     edi, eax
0x18002d6df  test    rbx, rbx
0x18002d6e2  jz      short loc_18002D6F4
0x18002d6e4  mov     rdx, [rbx]
0x18002d6e7  mov     rcx, rbx
0x18002d6ea  mov     rax, [rdx+10h]
0x18002d6ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6f3  nop
0x18002d6f4  test    edi, edi
0x18002d6f6  jns     loc_18002D77E
0x18002d6fc  lea     rcx, [rsp+1C0h+var_150]
0x18002d701  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18002d706  nop
0x18002d707  lea     rdx, aTaskqueueimplw; "TaskQueueImplWinRT::startAndAddWorkItem"...
0x18002d70e  lea     rcx, [rbp+0C0h+var_140]
0x18002d712  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002d717  mov     rcx, rax
0x18002d71a  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18002d721  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002d726  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18002d72d  mov     rcx, rax
0x18002d730  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18002d736  mov     edx, edi
0x18002d738  mov     rcx, rax
0x18002d73b  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18002d741  mov     rcx, rax
0x18002d744  lea     rdx, asc_1800A4BE0; ")"
0x18002d74b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002d750  lea     rdx, [rbp+0C0h+hstringHeader]
0x18002d754  lea     rcx, [rbp+0C0h+var_138]
0x18002d758  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18002d75d  nop
0x18002d75e  lea     rdx, [rbp+0C0h+hstringHeader]
0x18002d762  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x18002d767  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18002d76c  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18002d773  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x18002d778  call    _CxxThrowException_0
0x18002d77e  lea     rcx, [rsp+1C0h+var_180]
0x18002d783  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d788  nop
0x18002d789  lea     rcx, [rsp+1C0h+var_190]
0x18002d78e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d793  mov     rcx, [rbp+0C0h+var_30]
0x18002d79a  xor     rcx, rsp; StackCookie
0x18002d79d  call    __security_check_cookie
0x18002d7a2  mov     rbx, [rsp+1C0h+arg_18]
0x18002d7aa  add     rsp, 1A0h
0x18002d7b1  pop     r15
0x18002d7b3  pop     r14
0x18002d7b5  pop     rdi
0x18002d7b6  pop     rsi
0x18002d7b7  pop     rbp
0x18002d7b8  retn
```
