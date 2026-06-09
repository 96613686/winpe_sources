# Pal::TaskQueueImplWinRT::startAndAddWorkItem(ABI::Windows::System::Threading::IWorkItemHandler *,std::shared_ptr<Pal::Task> const &)

- ea: `0x18001a208`
- end: `0x18001a589`
- name: `?startAndAddWorkItem@TaskQueueImplWinRT@Pal@@AEAAXPEAUIWorkItemHandler@Threading@System@Windows@ABI@@AEBV?$shared_ptr@VTask@Pal@@@std@@@Z`
- size: `897`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001a648`
- `0x18001a6fc`

## callees

- `0x1800094a0`
- `0x18000a080`
- `0x18000b4b8`
- `0x18000cb24`
- `0x18000cd80`
- `0x18000d088`
- `0x18000d0c4`
- `0x18000db3c`
- `0x18000faf8`
- `0x18001006c`
- `0x180010308`
- `0x180010b18`
- `0x1800115fc`
- `0x180012ca4`
- `0x180013620`
- `0x18001722c`
- `0x18001a208`
- `0x18001a7a8`
- `0x180043010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001a2d0`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001a389`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001a500`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001a2d0`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001a389`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001a500`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18001a2db`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18001a394`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18001a50b`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18001a2db`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18001a394`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18001a50b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001a244`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001a244`

## string_xrefs

- `0x18001a2a7`: `Failed to retrieve the activation factory for Windows.System.Threading.ThreadPool`
- `0x18001a360`: `TaskQueueImplWinRT::startAndAddWorkItem - RunWithPriorityAsync failed`
- `0x18001a4d7`: `TaskQueueImplWinRT::startAndAddWorkItem - put_Completed failed`
- `0x18001a271`: `Windows.System.Threading.ThreadPool`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Pal::TaskQueueImplWinRT::startAndAddWorkItem(__int64 a1, __int64 a2, _QWORD *a3)
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
  __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
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
         (__int64)&v31);
  if ( v6 < 0 )
  {
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v35);
    v7 = std::operator<<<std::char_traits<char>>(
           (__int64)v36,
           (__int64)"Failed to retrieve the activation factory for Windows.System.Threading.ThreadPool");
    v8 = std::operator<<<std::char_traits<char>>(v7, (__int64)" (HRESULT: 0x");
    v9 = std::ostream::operator<<(v8, std::hex);
    v10 = std::ostream::operator<<(v9, (unsigned int)v6);
    std::operator<<<std::char_traits<char>>(v10, (__int64)")");
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
            (__int64)v36,
            (__int64)"TaskQueueImplWinRT::startAndAddWorkItem - RunWithPriorityAsync failed");
    v15 = std::operator<<<std::char_traits<char>>(v14, (__int64)" (HRESULT: 0x");
    v16 = std::ostream::operator<<(v15, std::hex);
    v17 = std::ostream::operator<<(v16, (unsigned int)v13);
    std::operator<<<std::char_traits<char>>(v17, (__int64)")");
    std::stringbuf::str(v37, &hstringHeader);
    std::runtime_error::runtime_error((std::exception *)&pExceptionObject);
    throw (std::runtime_error *)&pExceptionObject;
  }
  AsyncActionId = anonymous_namespace_::getAsyncActionId(v29);
  LODWORD(v30) = AsyncActionId;
  pExceptionObject = v29;
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
  std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(&v33, a3);
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
    v24 = std::operator<<<std::char_traits<char>>(
            (__int64)v36,
            (__int64)"TaskQueueImplWinRT::startAndAddWorkItem - put_Completed failed");
    v25 = std::operator<<<std::char_traits<char>>(v24, (__int64)" (HRESULT: 0x");
    v26 = std::ostream::operator<<(v25, std::hex);
    v27 = std::ostream::operator<<(v26, (unsigned int)v23);
    std::operator<<<std::char_traits<char>>(v27, (__int64)")");
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
0x18001a208  mov     [rsp-8+arg_18], rbx
0x18001a20d  push    rbp
0x18001a20e  push    rsi
0x18001a20f  push    rdi
0x18001a210  push    r14
0x18001a212  push    r15
0x18001a214  lea     rbp, [rsp-0A0h]
0x18001a21c  sub     rsp, 1A0h
0x18001a223  mov     rax, cs:__security_cookie
0x18001a22a  xor     rax, rsp
0x18001a22d  mov     [rbp+0C0h+var_30], rax
0x18001a234  mov     r15, r8
0x18001a237  mov     r14, rdx
0x18001a23a  mov     rsi, rcx
0x18001a23d  mov     rcx, [rcx+58h]
0x18001a241  mov     rcx, [rcx]; hEvent
0x18001a244  call    cs:__imp_ResetEvent
0x18001a24a  mov     [rsp+1C0h+var_190], 0
0x18001a253  mov     [rsp+1C0h+var_180], 0
0x18001a25c  mov     [rbp+0C0h+var_38], 0
0x18001a267  mov     r9d, 23h ; '#'; unsigned int
0x18001a26d  lea     r8d, [r9+1]; unsigned int
0x18001a271  lea     rdx, ?RuntimeClass_Windows_System_Threading_ThreadPool@@3QBGB; "Windows.System.Threading.ThreadPool"
0x18001a278  lea     rcx, [rbp+0C0h+hstringHeader]; hstringHeader
0x18001a27c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001a281  lea     rdx, [rsp+1C0h+var_180]
0x18001a286  mov     rcx, [rbp+0C0h+var_38]
0x18001a28d  call    ??$GetActivationFactory@V?$ComPtr@UIThreadPoolStatics@Threading@System@Windows@ABI@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIThreadPoolStatics@Threading@System@Windows@ABI@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<ABI::Windows::System::Threading::IThreadPoolStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ABI::Windows::System::Threading::IThreadPoolStatics>>)
0x18001a292  mov     ebx, eax
0x18001a294  test    eax, eax
0x18001a296  jns     loc_18001A31E
0x18001a29c  lea     rcx, [rsp+1C0h+var_150]
0x18001a2a1  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18001a2a6  nop
0x18001a2a7  lea     rdx, aFailedToRetrie_2; "Failed to retrieve the activation facto"...
0x18001a2ae  lea     rcx, [rbp+0C0h+var_140]
0x18001a2b2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001a2b7  mov     rcx, rax
0x18001a2ba  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18001a2c1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001a2c6  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18001a2cd  mov     rcx, rax
0x18001a2d0  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18001a2d6  mov     edx, ebx
0x18001a2d8  mov     rcx, rax
0x18001a2db  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18001a2e1  mov     rcx, rax
0x18001a2e4  lea     rdx, asc_180048470; ")"
0x18001a2eb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001a2f0  lea     rdx, [rbp+0C0h+hstringHeader]
0x18001a2f4  lea     rcx, [rbp+0C0h+var_138]
0x18001a2f8  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18001a2fd  nop
0x18001a2fe  lea     rdx, [rbp+0C0h+hstringHeader]
0x18001a302  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x18001a307  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18001a30c  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001a313  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x18001a318  call    _CxxThrowException_0
0x18001a31e  mov     rdi, [rsp+1C0h+var_180]
0x18001a323  mov     rax, [rdi]
0x18001a326  mov     rbx, [rax+38h]
0x18001a32a  lea     rcx, [rsp+1C0h+var_190]
0x18001a32f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a334  lea     r9, [rsp+1C0h+var_190]
0x18001a339  or      r8d, 0FFFFFFFFh
0x18001a33d  mov     rdx, r14
0x18001a340  mov     rcx, rdi
0x18001a343  mov     rax, rbx
0x18001a346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a34b  mov     ebx, eax
0x18001a34d  test    eax, eax
0x18001a34f  jns     loc_18001A3D7
0x18001a355  lea     rcx, [rsp+1C0h+var_150]
0x18001a35a  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18001a35f  nop
0x18001a360  lea     rdx, aTaskqueueimplw_0; "TaskQueueImplWinRT::startAndAddWorkItem"...
0x18001a367  lea     rcx, [rbp+0C0h+var_140]
0x18001a36b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001a370  mov     rcx, rax
0x18001a373  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18001a37a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001a37f  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18001a386  mov     rcx, rax
0x18001a389  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18001a38f  mov     edx, ebx
0x18001a391  mov     rcx, rax
0x18001a394  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18001a39a  mov     rcx, rax
0x18001a39d  lea     rdx, asc_180048470; ")"
0x18001a3a4  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001a3a9  lea     rdx, [rbp+0C0h+hstringHeader]
0x18001a3ad  lea     rcx, [rbp+0C0h+var_138]
0x18001a3b1  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18001a3b6  nop
0x18001a3b7  lea     rdx, [rbp+0C0h+hstringHeader]
0x18001a3bb  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x18001a3c0  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18001a3c5  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001a3cc  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x18001a3d1  call    _CxxThrowException_0
0x18001a3d7  mov     rcx, [rsp+1C0h+var_190]
0x18001a3dc  call    _anonymous_namespace___getAsyncActionId
0x18001a3e1  mov     ebx, eax
0x18001a3e3  mov     dword ptr [rsp+1C0h+var_188], eax
0x18001a3e7  mov     rcx, [rsp+1C0h+var_190]
0x18001a3ec  mov     [rsp+1C0h+pExceptionObject], rcx
0x18001a3f1  test    rcx, rcx
0x18001a3f4  jz      short loc_18001A403
0x18001a3f6  mov     r8, [rcx]
0x18001a3f9  mov     rax, [r8+8]
0x18001a3fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a402  nop
0x18001a403  mov     rdx, r15
0x18001a406  lea     rcx, [rsp+1C0h+var_170]
0x18001a40b  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x18001a410  nop
0x18001a411  mov     dword ptr [rbp+0C0h+hstringHeader.Reserved], ebx
0x18001a414  lea     rdx, [rsp+1C0h+pExceptionObject]; struct Pal::TaskQueueImplWinRT::AsyncActionAndTask *
0x18001a419  lea     rcx, [rbp+0C0h+hstringHeader.Reserved+8]; this
0x18001a41d  call    ??0AsyncActionAndTask@TaskQueueImplWinRT@Pal@@QEAA@AEBU012@@Z; Pal::TaskQueueImplWinRT::AsyncActionAndTask::AsyncActionAndTask(Pal::TaskQueueImplWinRT::AsyncActionAndTask const &)
0x18001a422  nop
0x18001a423  lea     rcx, [rsi+30h]
0x18001a427  lea     r8, [rbp+0C0h+hstringHeader]
0x18001a42b  lea     rdx, [rsp+1C0h+var_160]
0x18001a430  call    ??$_Emplace@U?$pair@IUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@@?$_Tree@V?$_Tmap_traits@IUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@IUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@1@@Z; std::_Tree<std::_Tmap_traits<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<uint>,std::allocator<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>::_Emplace<std::pair<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>(std::pair<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask> &&)
0x18001a435  nop
0x18001a436  lea     rcx, [rbp+0C0h+hstringHeader.Reserved+8]; this
0x18001a43a  call    ??1AsyncActionAndTask@TaskQueueImplWinRT@Pal@@QEAA@XZ; Pal::TaskQueueImplWinRT::AsyncActionAndTask::~AsyncActionAndTask(void)
0x18001a43f  nop
0x18001a440  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x18001a445  call    ??1AsyncActionAndTask@TaskQueueImplWinRT@Pal@@QEAA@XZ; Pal::TaskQueueImplWinRT::AsyncActionAndTask::~AsyncActionAndTask(void)
0x18001a44a  mov     r8, rsi
0x18001a44d  lea     rdx, [rsp+1C0h+var_188]
0x18001a452  lea     rcx, [rsp+1C0h+var_160]
0x18001a457  call    _lambda_8875b34cb5594d1a0f31d9dd8ea00989____lambda_8875b34cb5594d1a0f31d9dd8ea00989_
0x18001a45c  mov     rdi, [rsp+1C0h+var_190]
0x18001a461  mov     rax, [rdi]
0x18001a464  mov     rsi, [rax+30h]
0x18001a468  lea     rdx, [rsp+1C0h+var_160]
0x18001a46d  lea     rcx, [rsp+1C0h+var_188]
0x18001a472  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_ABI__Windows__Foundation__IAsyncActionCompletedHandler_____ABI__Windows__Foundation__IAsyncAction___enum_ABI__Windows__Foundation__AsyncStatus____DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__ABI__Windows__Foundation__IAsyncActionCompletedHandler_Microsoft__WRL__FtmBase___lambda_8875b34cb5594d1a0f31d9dd8ea00989_____1_ABI__Windows__Foundation__IAsyncAction___enum_ABI__Windows__Foundation__AsyncStatus___lambda_8875b34cb5594d1a0f31d9dd8ea00989____
0x18001a477  mov     rbx, [rax]
0x18001a47a  mov     [rsp+1C0h+var_160], rbx
0x18001a47f  mov     qword ptr [rax], 0
0x18001a486  mov     rcx, [rsp+1C0h+var_188]
0x18001a48b  test    rcx, rcx
0x18001a48e  jz      short loc_18001A49F
0x18001a490  mov     [rsp+1C0h+var_188], 0
0x18001a499  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UITimerDestroyedHandler@Threading@System@Windows@ABI@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::System::Threading::ITimerDestroyedHandler,Microsoft::WRL::FtmBase>>::Release(void)
0x18001a49e  nop
0x18001a49f  mov     rdx, rbx
0x18001a4a2  mov     rcx, rdi
0x18001a4a5  mov     rax, rsi
0x18001a4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4ad  mov     edi, eax
0x18001a4af  test    rbx, rbx
0x18001a4b2  jz      short loc_18001A4C4
0x18001a4b4  mov     rdx, [rbx]
0x18001a4b7  mov     rcx, rbx
0x18001a4ba  mov     rax, [rdx+10h]
0x18001a4be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4c3  nop
0x18001a4c4  test    edi, edi
0x18001a4c6  jns     loc_18001A54E
0x18001a4cc  lea     rcx, [rsp+1C0h+var_150]
0x18001a4d1  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18001a4d6  nop
0x18001a4d7  lea     rdx, aTaskqueueimplw; "TaskQueueImplWinRT::startAndAddWorkItem"...
0x18001a4de  lea     rcx, [rbp+0C0h+var_140]
0x18001a4e2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001a4e7  mov     rcx, rax
0x18001a4ea  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18001a4f1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001a4f6  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18001a4fd  mov     rcx, rax
0x18001a500  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18001a506  mov     edx, edi
0x18001a508  mov     rcx, rax
0x18001a50b  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18001a511  mov     rcx, rax
0x18001a514  lea     rdx, asc_180048470; ")"
0x18001a51b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001a520  lea     rdx, [rbp+0C0h+hstringHeader]
0x18001a524  lea     rcx, [rbp+0C0h+var_138]
0x18001a528  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18001a52d  nop
0x18001a52e  lea     rdx, [rbp+0C0h+hstringHeader]
0x18001a532  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x18001a537  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18001a53c  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001a543  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x18001a548  call    _CxxThrowException_0
0x18001a54e  lea     rcx, [rsp+1C0h+var_180]
0x18001a553  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a558  nop
0x18001a559  lea     rcx, [rsp+1C0h+var_190]
0x18001a55e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a563  mov     rcx, [rbp+0C0h+var_30]
0x18001a56a  xor     rcx, rsp; StackCookie
0x18001a56d  call    __security_check_cookie
0x18001a572  mov     rbx, [rsp+1C0h+arg_18]
0x18001a57a  add     rsp, 1A0h
0x18001a581  pop     r15
0x18001a583  pop     r14
0x18001a585  pop     rdi
0x18001a586  pop     rsi
0x18001a587  pop     rbp
0x18001a588  retn
```
