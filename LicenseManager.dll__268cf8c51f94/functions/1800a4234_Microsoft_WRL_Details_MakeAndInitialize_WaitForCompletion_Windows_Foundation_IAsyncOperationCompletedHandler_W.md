# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate * *)

- ea: `0x1800a4234`
- end: `0x1800a432b`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJ012K@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@@Z`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a4334`

## callees

- `0x180004738`
- `0x18003c27c`
- `0x18007633c`
- `0x180084ff0`
- `0x1800a4234`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800a42bc`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800a42bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a42cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a42cb`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAXK_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___23___YAJ012K_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAXK_Z__Z(
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
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v8);
      v4 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v8);
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
0x1800a4234  mov     [rsp+arg_10], rbx
0x1800a4239  mov     [rsp+arg_18], rsi
0x1800a423e  push    rdi
0x1800a423f  sub     rsp, 20h
0x1800a4243  mov     rsi, rcx
0x1800a4246  mov     qword ptr [rcx], 0
0x1800a424d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a4254  mov     ecx, 40h ; '@'; unsigned __int64
0x1800a4259  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a425e  mov     rbx, rax
0x1800a4261  mov     [rsp+28h+arg_8], rax
0x1800a4266  test    rax, rax
0x1800a4269  jnz     short loc_1800A4275
0x1800a426b  mov     edi, 8007000Eh
0x1800a4270  jmp     loc_1800A430F
0x1800a4275  mov     rcx, rbx
0x1800a4278  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>(void)
0x1800a427d  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>'}
0x1800a4284  mov     [rbx], rax
0x1800a4287  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800a428e  mov     [rbx+8], rax
0x1800a4292  mov     dword ptr [rbx+30h], 0
0x1800a4299  mov     qword ptr [rbx+38h], 0
0x1800a42a1  mov     [rsp+28h+arg_0], rbx
0x1800a42a6  mov     [rsp+28h+arg_8], 0
0x1800a42af  mov     r9d, 1F0003h; dwDesiredAccess
0x1800a42b5  xor     r8d, r8d; dwFlags
0x1800a42b8  xor     edx, edx; lpName
0x1800a42ba  xor     ecx, ecx; lpEventAttributes
0x1800a42bc  call    cs:__imp_CreateEventExW
0x1800a42c2  mov     [rbx+38h], rax
0x1800a42c6  test    rax, rax
0x1800a42c9  jnz     short loc_1800A42F0
0x1800a42cb  call    cs:__imp_GetLastError
0x1800a42d1  mov     edi, eax
0x1800a42d3  test    eax, eax
0x1800a42d5  jle     short loc_1800A42E0
0x1800a42d7  movzx   edi, ax
0x1800a42da  or      edi, 80070000h
0x1800a42e0  test    edi, edi
0x1800a42e2  jns     short loc_1800A42F0
0x1800a42e4  lea     rcx, [rsp+28h+arg_0]
0x1800a42e9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a42ee  jmp     short loc_1800A430F
0x1800a42f0  mov     rax, [rbx]
0x1800a42f3  mov     rcx, rbx
0x1800a42f6  mov     rax, [rax+8]
0x1800a42fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a42ff  nop
0x1800a4300  mov     [rsi], rbx
0x1800a4303  lea     rcx, [rsp+28h+arg_0]
0x1800a4308  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a430d  xor     edi, edi
0x1800a430f  lea     rcx, [rsp+28h+arg_8]
0x1800a4314  call    ??1?$MakeAllocator@VUserSigninChangeWatcher@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<UserSigninChangeWatcher>::~MakeAllocator<UserSigninChangeWatcher>(void)
0x1800a4319  mov     eax, edi
0x1800a431b  mov     rbx, [rsp+28h+arg_10]
0x1800a4320  mov     rsi, [rsp+28h+arg_18]
0x1800a4325  add     rsp, 20h
0x1800a4329  pop     rdi
0x1800a432a  retn
```
