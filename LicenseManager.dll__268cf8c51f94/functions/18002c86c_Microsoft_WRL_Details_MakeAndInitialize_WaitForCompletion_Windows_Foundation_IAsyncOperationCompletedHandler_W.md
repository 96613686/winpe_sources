# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate * *)

- ea: `0x18002c86c`
- end: `0x18002c940`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJ012K@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@@Z`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c694`

## callees

- `0x180004738`
- `0x18002c86c`
- `0x18002c948`
- `0x18003c27c`
- `0x18007633c`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002c8cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002c8cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8da`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAXK_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJ012K_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAXK_Z__Z(
        _QWORD *a1)
{
  void *v2; // rax
  _QWORD *v4; // rdi
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v7; // ebx
  _QWORD *v8; // [rsp+30h] [rbp+8h] BYREF
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v2 )
    return 2147942414LL;
  v4 = (_QWORD *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::FTMEventDelegate(v2);
  v8 = v4;
  v9 = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  v4[7] = Event;
  if ( Event )
    goto LABEL_8;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_8:
    (*(void (__fastcall **)(_QWORD *))(*v4 + 8LL))(v4);
    *a1 = v4;
    (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
    return 0;
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v8);
    Microsoft::WRL::Details::MakeAllocator<UserSigninChangeWatcher>::~MakeAllocator<UserSigninChangeWatcher>(&v9);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x18002c86c  mov     [rsp+arg_10], rbx
0x18002c871  mov     [rsp+arg_18], rsi
0x18002c876  push    rdi
0x18002c877  sub     rsp, 20h
0x18002c87b  mov     rsi, rcx
0x18002c87e  mov     qword ptr [rcx], 0
0x18002c885  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002c88c  mov     ecx, 40h ; '@'; unsigned __int64
0x18002c891  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002c896  test    rax, rax
0x18002c899  jnz     short loc_18002C8A5
0x18002c89b  mov     eax, 8007000Eh
0x18002c8a0  jmp     loc_18002C930
0x18002c8a5  mov     rcx, rax
0x18002c8a8  call    ??0FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@QEAA@XZ; `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate::FTMEventDelegate(void)
0x18002c8ad  mov     rdi, rax
0x18002c8b0  mov     [rsp+28h+arg_0], rax
0x18002c8b5  mov     [rsp+28h+arg_8], 0
0x18002c8be  mov     r9d, 1F0003h; dwDesiredAccess
0x18002c8c4  xor     r8d, r8d; dwFlags
0x18002c8c7  xor     edx, edx; lpName
0x18002c8c9  xor     ecx, ecx; lpEventAttributes
0x18002c8cb  call    cs:__imp_CreateEventExW
0x18002c8d1  mov     [rdi+38h], rax
0x18002c8d5  test    rax, rax
0x18002c8d8  jnz     short loc_18002C90B
0x18002c8da  call    cs:__imp_GetLastError
0x18002c8e0  mov     ebx, eax
0x18002c8e2  test    eax, eax
0x18002c8e4  jle     short loc_18002C8EF
0x18002c8e6  movzx   ebx, ax
0x18002c8e9  or      ebx, 80070000h
0x18002c8ef  test    ebx, ebx
0x18002c8f1  jns     short loc_18002C90B
0x18002c8f3  lea     rcx, [rsp+28h+arg_0]
0x18002c8f8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002c8fd  lea     rcx, [rsp+28h+arg_8]
0x18002c902  call    ??1?$MakeAllocator@VUserSigninChangeWatcher@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<UserSigninChangeWatcher>::~MakeAllocator<UserSigninChangeWatcher>(void)
0x18002c907  mov     eax, ebx
0x18002c909  jmp     short loc_18002C930
0x18002c90b  mov     rax, [rdi]
0x18002c90e  mov     rcx, rdi
0x18002c911  mov     rax, [rax+8]
0x18002c915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c91a  nop
0x18002c91b  mov     [rsi], rdi
0x18002c91e  mov     rax, [rdi]
0x18002c921  mov     rcx, rdi
0x18002c924  mov     rax, [rax+10h]
0x18002c928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c92d  nop
0x18002c92e  xor     eax, eax
0x18002c930  mov     rbx, [rsp+28h+arg_10]
0x18002c935  mov     rsi, [rsp+28h+arg_18]
0x18002c93a  add     rsp, 20h
0x18002c93e  pop     rdi
0x18002c93f  retn
```
