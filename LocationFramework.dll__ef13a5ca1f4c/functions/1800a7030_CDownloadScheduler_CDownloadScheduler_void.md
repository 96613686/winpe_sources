# CDownloadScheduler::~CDownloadScheduler(void)

- ea: `0x1800a7030`
- end: `0x1800a711b`
- name: `??1CDownloadScheduler@@QEAA@XZ`
- size: `235`
- prototype: `void __fastcall(CDownloadScheduler *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18014496c`

## callees

- `0x180012194`
- `0x180012398`
- `0x1800123c0`
- `0x180028434`
- `0x18003d8a0`
- `0x1800a7030`
- `0x1800a7124`
- `0x1801460a0`
- `0x1801460b0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800a70cd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800a70cd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800a70d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800a70d6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a70f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a7103`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a70f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a7103`

## pseudocode

```c
void __fastcall CDownloadScheduler::~CDownloadScheduler(CDownloadScheduler *this)
{
  struct _TP_WORK *v2; // rdi
  char *v3; // rcx
  std::_Ref_count_base *v4; // rcx
  _BYTE v5[56]; // [rsp+20h] [rbp-38h] BYREF

  v2 = 0;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v5,
    (char *)this + 88);
  v3 = (char *)this + 48;
  while ( !(unsigned __int8)std::queue<__MIDL___MIDL_itf_locationcommondata_0000_0000_0010>::empty(v3) )
    std::queue<__MIDL___MIDL_itf_locationcommondata_0000_0000_0010>::pop((char *)this + 48);
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v5);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v5,
    (char *)this + 8);
  if ( *(_QWORD *)this )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 104LL))(*(_QWORD *)this);
    ATL::CComPtr<ILocationWebServiceProxy>::operator=(this);
  }
  if ( *((_QWORD *)this + 16) )
  {
    v2 = (struct _TP_WORK *)*((_QWORD *)this + 16);
    *((_QWORD *)this + 16) = 0;
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v5);
  if ( v2 )
  {
    WaitForThreadpoolWorkCallbacks(v2, 1);
    CloseThreadpoolWork(v2);
  }
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 18);
  if ( v4 )
    std::_Ref_count_base::_Decwref(v4);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  std::queue<__MIDL___MIDL_itf_locationcommondata_0000_0000_0010>::~queue<__MIDL___MIDL_itf_locationcommondata_0000_0000_0010,std::deque<__MIDL___MIDL_itf_locationcommondata_0000_0000_0010>>((char *)this + 48);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(this);
}

```

## disassembly

```asm
0x1800a7030  push    rbx
0x1800a7032  push    rbp
0x1800a7033  push    rsi
0x1800a7034  push    rdi
0x1800a7035  push    r14
0x1800a7037  sub     rsp, 30h
0x1800a703b  mov     rbx, rcx
0x1800a703e  xor     edi, edi
0x1800a7040  lea     rdx, [rcx+58h]
0x1800a7044  lea     rcx, [rsp+58h+var_38]
0x1800a7049  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x1800a704e  lea     rsi, [rbx+30h]
0x1800a7052  mov     rcx, rsi
0x1800a7055  jmp     short loc_1800A705F
0x1800a7057  mov     rcx, rsi
0x1800a705a  call    ?pop@?$queue@U__MIDL___MIDL_itf_locationcommondata_0000_0000_0010@@V?$deque@U__MIDL___MIDL_itf_locationcommondata_0000_0000_0010@@V?$allocator@U__MIDL___MIDL_itf_locationcommondata_0000_0000_0010@@@std@@@std@@@std@@QEAAXXZ; std::queue<__MIDL___MIDL_itf_locationcommondata_0000_0000_0010>::pop(void)
0x1800a705f  call    ?empty@?$queue@U__MIDL___MIDL_itf_locationcommondata_0000_0000_0010@@V?$deque@U__MIDL___MIDL_itf_locationcommondata_0000_0000_0010@@V?$allocator@U__MIDL___MIDL_itf_locationcommondata_0000_0000_0010@@@std@@@std@@@std@@QEBA_NXZ; std::queue<__MIDL___MIDL_itf_locationcommondata_0000_0000_0010>::empty(void)
0x1800a7064  test    al, al
0x1800a7066  jz      short loc_1800A7057
0x1800a7068  lea     rcx, [rsp+58h+var_38]
0x1800a706d  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800a7072  lea     rdx, [rbx+8]
0x1800a7076  lea     rcx, [rsp+58h+var_38]
0x1800a707b  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x1800a7080  mov     rcx, [rbx]
0x1800a7083  test    rcx, rcx
0x1800a7086  jz      short loc_1800A709C
0x1800a7088  mov     rax, [rcx]
0x1800a708b  mov     rax, [rax+68h]
0x1800a708f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7094  mov     rcx, rbx
0x1800a7097  call    ??4?$CComPtr@UILocationWebServiceProxy@@@ATL@@QEAAPEAUILocationWebServiceProxy@@PEAU2@@Z; ATL::CComPtr<ILocationWebServiceProxy>::operator=(ILocationWebServiceProxy *)
0x1800a709c  mov     rax, [rbx+80h]
0x1800a70a3  test    rax, rax
0x1800a70a6  jz      short loc_1800A70B6
0x1800a70a8  mov     rdi, rax
0x1800a70ab  mov     qword ptr [rbx+80h], 0
0x1800a70b6  lea     rcx, [rsp+58h+var_38]
0x1800a70bb  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800a70c0  test    rdi, rdi
0x1800a70c3  jz      short loc_1800A70DC
0x1800a70c5  mov     edx, 1; fCancelPendingCallbacks
0x1800a70ca  mov     rcx, rdi; pwk
0x1800a70cd  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800a70d3  mov     rcx, rdi; pwk
0x1800a70d6  call    cs:__imp_CloseThreadpoolWork
0x1800a70dc  mov     rcx, [rbx+90h]; this
0x1800a70e3  test    rcx, rcx
0x1800a70e6  jz      short loc_1800A70ED
0x1800a70e8  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800a70ed  lea     rcx, [rbx+58h]; lpCriticalSection
0x1800a70f1  call    cs:__imp_DeleteCriticalSection
0x1800a70f7  mov     rcx, rsi
0x1800a70fa  call    ??1?$queue@U__MIDL___MIDL_itf_locationcommondata_0000_0000_0010@@V?$deque@U__MIDL___MIDL_itf_locationcommondata_0000_0000_0010@@V?$allocator@U__MIDL___MIDL_itf_locationcommondata_0000_0000_0010@@@std@@@std@@@std@@QEAA@XZ; std::queue<__MIDL___MIDL_itf_locationcommondata_0000_0000_0010>::~queue<__MIDL___MIDL_itf_locationcommondata_0000_0000_0010,std::deque<__MIDL___MIDL_itf_locationcommondata_0000_0000_0010>>(void)
0x1800a70ff  lea     rcx, [rbx+8]; lpCriticalSection
0x1800a7103  call    cs:__imp_DeleteCriticalSection
0x1800a7109  mov     rcx, rbx
0x1800a710c  add     rsp, 30h
0x1800a7110  pop     r14
0x1800a7112  pop     rdi
0x1800a7113  pop     rsi
0x1800a7114  pop     rbp
0x1800a7115  pop     rbx
0x1800a7116  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
