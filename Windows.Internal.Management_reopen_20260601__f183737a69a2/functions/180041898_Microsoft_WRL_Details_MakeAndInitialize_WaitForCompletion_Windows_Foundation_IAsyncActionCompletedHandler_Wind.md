# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180041898`
- end: `0x18004199c`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800427a0`

## callees

- `0x1800053e0`
- `0x180009be4`
- `0x18000da60`
- `0x18001fbb0`
- `0x180041898`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180041920`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180041920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041935`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  signed int v4; // edi
  HANDLE Event; // rax
  signed int LastError; // eax
  _QWORD *v8; // [rsp+30h] [rbp+8h] BYREF
  void *v9; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  v9 = v2;
  if ( v2 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>(v2);
    *v3 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
    v3[1] = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate::`vftable';
    *((_DWORD *)v3 + 12) = 0;
    v3[7] = 0;
    v8 = v3;
    v9 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    v3[7] = Event;
    if ( Event )
      goto LABEL_8;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_8:
      (*(void (__fastcall **)(_QWORD *))(*v3 + 8LL))(v3);
      *a1 = v3;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
      v4 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
    }
  }
  else
  {
    v4 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<EnterpriseDeviceManagement::Enrollment::GetManagementUrlsResults *>,Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::GetManagementUrlsResults *>,Windows::Internal::CMarshaledInterfaceResult<EnterpriseDeviceManagement::Enrollment::IGetManagementUrlsResults>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::~MakeAllocator<Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<EnterpriseDeviceManagement::Enrollment::GetManagementUrlsResults *>,Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::GetManagementUrlsResults *>,Windows::Internal::CMarshaledInterfaceResult<EnterpriseDeviceManagement::Enrollment::IGetManagementUrlsResults>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>(&v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180041898  mov     [rsp+arg_10], rbx
0x18004189d  mov     [rsp+arg_18], rsi
0x1800418a2  push    rdi
0x1800418a3  sub     rsp, 20h
0x1800418a7  mov     rsi, rcx
0x1800418aa  mov     qword ptr [rcx], 0
0x1800418b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800418b8  mov     ecx, 40h ; '@'; unsigned __int64
0x1800418bd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800418c2  mov     rbx, rax
0x1800418c5  mov     [rsp+28h+arg_8], rax
0x1800418ca  test    rax, rax
0x1800418cd  jnz     short loc_1800418D9
0x1800418cf  mov     edi, 8007000Eh
0x1800418d4  jmp     loc_18004197F
0x1800418d9  mov     rcx, rbx
0x1800418dc  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>(void)
0x1800418e1  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6BIAsyncActionCompletedHandler@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x1800418e8  mov     [rbx], rax
0x1800418eb  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800418f2  mov     [rbx+8], rax
0x1800418f6  mov     dword ptr [rbx+30h], 0
0x1800418fd  mov     qword ptr [rbx+38h], 0
0x180041905  mov     [rsp+28h+arg_0], rbx
0x18004190a  mov     [rsp+28h+arg_8], 0
0x180041913  mov     r9d, 1F0003h; dwDesiredAccess
0x180041919  xor     r8d, r8d; dwFlags
0x18004191c  xor     edx, edx; lpName
0x18004191e  xor     ecx, ecx; lpEventAttributes
0x180041920  call    cs:__imp_CreateEventExW
0x180041927  nop     dword ptr [rax+rax+00h]
0x18004192c  mov     [rbx+38h], rax
0x180041930  test    rax, rax
0x180041933  jnz     short loc_180041960
0x180041935  call    cs:__imp_GetLastError
0x18004193c  nop     dword ptr [rax+rax+00h]
0x180041941  mov     edi, eax
0x180041943  test    eax, eax
0x180041945  jle     short loc_180041950
0x180041947  movzx   edi, ax
0x18004194a  or      edi, 80070000h
0x180041950  test    edi, edi
0x180041952  jns     short loc_180041960
0x180041954  lea     rcx, [rsp+28h+arg_0]
0x180041959  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004195e  jmp     short loc_18004197F
0x180041960  mov     rax, [rbx]
0x180041963  mov     rcx, rbx
0x180041966  mov     rax, [rax+8]
0x18004196a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004196f  nop
0x180041970  mov     [rsi], rbx
0x180041973  lea     rcx, [rsp+28h+arg_0]
0x180041978  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004197d  xor     edi, edi
0x18004197f  lea     rcx, [rsp+28h+arg_8]
0x180041984  call    ??1?$MakeAllocator@V?$AsyncOperation@U?$IAsyncOperation@PEAVGetManagementUrlsResults@Enrollment@EnterpriseDeviceManagement@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVGetManagementUrlsResults@Enrollment@EnterpriseDeviceManagement@@@23@V?$CMarshaledInterfaceResult@UIGetManagementUrlsResults@Enrollment@EnterpriseDeviceManagement@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<EnterpriseDeviceManagement::Enrollment::GetManagementUrlsResults *>,Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::GetManagementUrlsResults *>,Windows::Internal::CMarshaledInterfaceResult<EnterpriseDeviceManagement::Enrollment::IGetManagementUrlsResults>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::~MakeAllocator<Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<EnterpriseDeviceManagement::Enrollment::GetManagementUrlsResults *>,Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::GetManagementUrlsResults *>,Windows::Internal::CMarshaledInterfaceResult<EnterpriseDeviceManagement::Enrollment::IGetManagementUrlsResults>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>(void)
0x180041989  mov     eax, edi
0x18004198b  mov     rbx, [rsp+28h+arg_10]
0x180041990  mov     rsi, [rsp+28h+arg_18]
0x180041995  add     rsp, 20h
0x180041999  pop     rdi
0x18004199a  retn
```
