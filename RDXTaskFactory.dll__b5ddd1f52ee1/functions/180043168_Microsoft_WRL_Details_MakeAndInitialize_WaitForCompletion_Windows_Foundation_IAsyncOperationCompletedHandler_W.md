# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180043168`
- end: `0x180043238`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `208`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800433f0`

## callees

- `0x18000534c`
- `0x180008bbc`
- `0x18000e264`
- `0x180043168`
- `0x180043d24`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800431c9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800431c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800431d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800431d8`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___Collections_Foundation_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  void *v2; // rax
  signed int v3; // ebx
  _QWORD *v4; // rdi
  HANDLE Event; // rax
  signed int LastError; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  _QWORD *v12; // [rsp+30h] [rbp+8h] BYREF
  void *v13; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v2;
  if ( v2 )
  {
    v4 = (_QWORD *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>>'::`2'::FTMEventDelegate::FTMEventDelegate(v2);
    v12 = v4;
    v13 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    v4[7] = Event;
    if ( Event )
      goto LABEL_8;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_8:
      (*(void (__fastcall **)(_QWORD *))(*v4 + 8LL))(v4);
      *a1 = v4;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12, v9, v10);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12, v7, v8);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<SetWallpaperTask>::~MakeAllocator<SetWallpaperTask>(&v13);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180043168  mov     [rsp+arg_10], rbx
0x18004316d  mov     [rsp+arg_18], rsi
0x180043172  push    rdi
0x180043173  sub     rsp, 20h
0x180043177  mov     rsi, rcx
0x18004317a  mov     qword ptr [rcx], 0
0x180043181  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180043188  mov     ecx, 40h ; '@'; unsigned __int64
0x18004318d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180043192  mov     [rsp+28h+arg_8], rax
0x180043197  test    rax, rax
0x18004319a  jnz     short loc_1800431A3
0x18004319c  mov     ebx, 8007000Eh
0x1800431a1  jmp     short loc_18004321C
0x1800431a3  mov     rcx, rax
0x1800431a6  call    ??0FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@QEAA@XZ; `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::FTMEventDelegate(void)
0x1800431ab  mov     rdi, rax
0x1800431ae  mov     [rsp+28h+arg_0], rax
0x1800431b3  mov     [rsp+28h+arg_8], 0
0x1800431bc  mov     r9d, 1F0003h; dwDesiredAccess
0x1800431c2  xor     r8d, r8d; dwFlags
0x1800431c5  xor     edx, edx; lpName
0x1800431c7  xor     ecx, ecx; lpEventAttributes
0x1800431c9  call    cs:__imp_CreateEventExW
0x1800431cf  mov     [rdi+38h], rax
0x1800431d3  test    rax, rax
0x1800431d6  jnz     short loc_1800431FD
0x1800431d8  call    cs:__imp_GetLastError
0x1800431de  mov     ebx, eax
0x1800431e0  test    eax, eax
0x1800431e2  jle     short loc_1800431ED
0x1800431e4  movzx   ebx, ax
0x1800431e7  or      ebx, 80070000h
0x1800431ed  test    ebx, ebx
0x1800431ef  jns     short loc_1800431FD
0x1800431f1  lea     rcx, [rsp+28h+arg_0]
0x1800431f6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800431fb  jmp     short loc_18004321C
0x1800431fd  mov     rax, [rdi]
0x180043200  mov     rcx, rdi
0x180043203  mov     rax, [rax+8]
0x180043207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004320c  nop
0x18004320d  mov     [rsi], rdi
0x180043210  lea     rcx, [rsp+28h+arg_0]
0x180043215  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004321a  xor     ebx, ebx
0x18004321c  lea     rcx, [rsp+28h+arg_8]
0x180043221  call    ??1?$MakeAllocator@VSetWallpaperTask@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SetWallpaperTask>::~MakeAllocator<SetWallpaperTask>(void)
0x180043226  mov     eax, ebx
0x180043228  mov     rbx, [rsp+28h+arg_10]
0x18004322d  mov     rsi, [rsp+28h+arg_18]
0x180043232  add     rsp, 20h
0x180043236  pop     rdi
0x180043237  retn
```
