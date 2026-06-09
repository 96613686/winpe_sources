# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x1800847e4`
- end: `0x1800848db`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180084a50`

## callees

- `0x18003c27c`
- `0x18007633c`
- `0x1800847e4`
- `0x180084ff0`
- `0x180087b94`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18008486c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18008486c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008487b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008487b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  v9 = v2;
  if ( v2 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>(v2);
    *v3 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>'::`2'::FTMEventDelegate::`vftable';
    v3[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
      Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::InternalRelease(&v8);
      v4 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::InternalRelease(&v8);
    }
  }
  else
  {
    v4 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<UserSigninChangeWatcher>::~MakeAllocator<UserSigninChangeWatcher>(&v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800847e4  mov     [rsp+arg_10], rbx
0x1800847e9  mov     [rsp+arg_18], rsi
0x1800847ee  push    rdi
0x1800847ef  sub     rsp, 20h
0x1800847f3  mov     rsi, rcx
0x1800847f6  mov     qword ptr [rcx], 0
0x1800847fd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180084804  mov     ecx, 40h ; '@'; unsigned __int64
0x180084809  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008480e  mov     rbx, rax
0x180084811  mov     [rsp+28h+arg_8], rax
0x180084816  test    rax, rax
0x180084819  jnz     short loc_180084825
0x18008481b  mov     edi, 8007000Eh
0x180084820  jmp     loc_1800848BF
0x180084825  mov     rcx, rbx
0x180084828  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>(void)
0x18008482d  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>'}
0x180084834  mov     [rbx], rax
0x180084837  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18008483e  mov     [rbx+8], rax
0x180084842  mov     dword ptr [rbx+30h], 0
0x180084849  mov     qword ptr [rbx+38h], 0
0x180084851  mov     [rsp+28h+arg_0], rbx
0x180084856  mov     [rsp+28h+arg_8], 0
0x18008485f  mov     r9d, 1F0003h; dwDesiredAccess
0x180084865  xor     r8d, r8d; dwFlags
0x180084868  xor     edx, edx; lpName
0x18008486a  xor     ecx, ecx; lpEventAttributes
0x18008486c  call    cs:__imp_CreateEventExW
0x180084872  mov     [rbx+38h], rax
0x180084876  test    rax, rax
0x180084879  jnz     short loc_1800848A0
0x18008487b  call    cs:__imp_GetLastError
0x180084881  mov     edi, eax
0x180084883  test    eax, eax
0x180084885  jle     short loc_180084890
0x180084887  movzx   edi, ax
0x18008488a  or      edi, 80070000h
0x180084890  test    edi, edi
0x180084892  jns     short loc_1800848A0
0x180084894  lea     rcx, [rsp+28h+arg_0]
0x180084899  call    ?InternalRelease@?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::InternalRelease(void)
0x18008489e  jmp     short loc_1800848BF
0x1800848a0  mov     rax, [rbx]
0x1800848a3  mov     rcx, rbx
0x1800848a6  mov     rax, [rax+8]
0x1800848aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800848af  nop
0x1800848b0  mov     [rsi], rbx
0x1800848b3  lea     rcx, [rsp+28h+arg_0]
0x1800848b8  call    ?InternalRelease@?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::InternalRelease(void)
0x1800848bd  xor     edi, edi
0x1800848bf  lea     rcx, [rsp+28h+arg_8]
0x1800848c4  call    ??1?$MakeAllocator@VUserSigninChangeWatcher@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<UserSigninChangeWatcher>::~MakeAllocator<UserSigninChangeWatcher>(void)
0x1800848c9  mov     eax, edi
0x1800848cb  mov     rbx, [rsp+28h+arg_10]
0x1800848d0  mov     rsi, [rsp+28h+arg_18]
0x1800848d5  add     rsp, 20h
0x1800848d9  pop     rdi
0x1800848da  retn
```
