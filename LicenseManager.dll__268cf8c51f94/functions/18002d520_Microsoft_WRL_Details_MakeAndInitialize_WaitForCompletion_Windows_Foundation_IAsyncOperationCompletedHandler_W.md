# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate * *)

- ea: `0x18002d520`
- end: `0x18002d61a`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJ012K@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@@Z`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002d344`

## callees

- `0x180004738`
- `0x18002d520`
- `0x18002d620`
- `0x18003c27c`
- `0x18007633c`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002d5a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002d5a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d5b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d5b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAXK_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___23___YAJ012K_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAXK_Z__Z(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  signed int v4; // edi
  HANDLE Event; // rax
  signed int LastError; // eax
  void *v8; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v9; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  v8 = v2;
  if ( !v2 )
  {
    v4 = -2147024882;
LABEL_8:
    Microsoft::WRL::Details::MakeAllocator<UserSigninChangeWatcher>::~MakeAllocator<UserSigninChangeWatcher>(&v8);
    return (unsigned int)v4;
  }
  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>(v2);
  *v3 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>'::`2'::FTMEventDelegate::`vftable';
  v3[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_DWORD *)v3 + 12) = 0;
  v3[7] = 0;
  v9 = v3;
  v8 = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  v3[7] = Event;
  if ( !Event )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v9);
      goto LABEL_8;
    }
  }
  (*(void (__fastcall **)(_QWORD *))(*v3 + 8LL))(v3);
  *a1 = v3;
  (*(void (__fastcall **)(_QWORD *))(*v3 + 16LL))(v3);
  return 0;
}

```

## disassembly

```asm
0x18002d520  mov     [rsp+arg_10], rbx
0x18002d525  mov     [rsp+arg_18], rsi
0x18002d52a  push    rdi
0x18002d52b  sub     rsp, 20h
0x18002d52f  mov     rsi, rcx
0x18002d532  mov     qword ptr [rcx], 0
0x18002d539  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002d540  mov     ecx, 40h ; '@'; unsigned __int64
0x18002d545  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002d54a  mov     rbx, rax
0x18002d54d  mov     [rsp+28h+arg_0], rax
0x18002d552  test    rax, rax
0x18002d555  jnz     short loc_18002D55E
0x18002d557  mov     edi, 8007000Eh
0x18002d55c  jmp     short loc_18002D5D7
0x18002d55e  mov     rcx, rbx
0x18002d561  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>(void)
0x18002d566  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'}
0x18002d56d  mov     [rbx], rax
0x18002d570  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002d577  mov     [rbx+8], rax
0x18002d57b  mov     dword ptr [rbx+30h], 0
0x18002d582  mov     qword ptr [rbx+38h], 0
0x18002d58a  mov     [rsp+28h+arg_8], rbx
0x18002d58f  mov     [rsp+28h+arg_0], 0
0x18002d598  mov     r9d, 1F0003h; dwDesiredAccess
0x18002d59e  xor     r8d, r8d; dwFlags
0x18002d5a1  xor     edx, edx; lpName
0x18002d5a3  xor     ecx, ecx; lpEventAttributes
0x18002d5a5  call    cs:__imp_CreateEventExW
0x18002d5ab  mov     [rbx+38h], rax
0x18002d5af  test    rax, rax
0x18002d5b2  jnz     short loc_18002D5E5
0x18002d5b4  call    cs:__imp_GetLastError
0x18002d5ba  mov     edi, eax
0x18002d5bc  test    eax, eax
0x18002d5be  jle     short loc_18002D5C9
0x18002d5c0  movzx   edi, ax
0x18002d5c3  or      edi, 80070000h
0x18002d5c9  test    edi, edi
0x18002d5cb  jns     short loc_18002D5E5
0x18002d5cd  lea     rcx, [rsp+28h+arg_8]
0x18002d5d2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002d5d7  lea     rcx, [rsp+28h+arg_0]
0x18002d5dc  call    ??1?$MakeAllocator@VUserSigninChangeWatcher@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<UserSigninChangeWatcher>::~MakeAllocator<UserSigninChangeWatcher>(void)
0x18002d5e1  mov     eax, edi
0x18002d5e3  jmp     short loc_18002D60A
0x18002d5e5  mov     rax, [rbx]
0x18002d5e8  mov     rcx, rbx
0x18002d5eb  mov     rax, [rax+8]
0x18002d5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5f4  nop
0x18002d5f5  mov     [rsi], rbx
0x18002d5f8  mov     rax, [rbx]
0x18002d5fb  mov     rcx, rbx
0x18002d5fe  mov     rax, [rax+10h]
0x18002d602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d607  nop
0x18002d608  xor     eax, eax
0x18002d60a  mov     rbx, [rsp+28h+arg_10]
0x18002d60f  mov     rsi, [rsp+28h+arg_18]
0x18002d614  add     rsp, 20h
0x18002d618  pop     rdi
0x18002d619  retn
```
