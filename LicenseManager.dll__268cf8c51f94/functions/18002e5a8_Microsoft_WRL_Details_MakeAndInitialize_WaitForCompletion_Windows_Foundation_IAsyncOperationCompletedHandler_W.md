# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate * *)

- ea: `0x18002e5a8`
- end: `0x18002e67c`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJ012K@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@@Z`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002e3cc`

## callees

- `0x180004738`
- `0x18002e5a8`
- `0x18002e684`
- `0x18003c27c`
- `0x18007633c`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002e607`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002e607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e616`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAXK_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJ012K_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAXK_Z__Z(
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
  v4 = (_QWORD *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>'::`2'::FTMEventDelegate::FTMEventDelegate(v2);
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
0x18002e5a8  mov     [rsp+arg_10], rbx
0x18002e5ad  mov     [rsp+arg_18], rsi
0x18002e5b2  push    rdi
0x18002e5b3  sub     rsp, 20h
0x18002e5b7  mov     rsi, rcx
0x18002e5ba  mov     qword ptr [rcx], 0
0x18002e5c1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e5c8  mov     ecx, 40h ; '@'; unsigned __int64
0x18002e5cd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002e5d2  test    rax, rax
0x18002e5d5  jnz     short loc_18002E5E1
0x18002e5d7  mov     eax, 8007000Eh
0x18002e5dc  jmp     loc_18002E66C
0x18002e5e1  mov     rcx, rax
0x18002e5e4  call    ??0FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@QEAA@XZ; `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate::FTMEventDelegate(void)
0x18002e5e9  mov     rdi, rax
0x18002e5ec  mov     [rsp+28h+arg_0], rax
0x18002e5f1  mov     [rsp+28h+arg_8], 0
0x18002e5fa  mov     r9d, 1F0003h; dwDesiredAccess
0x18002e600  xor     r8d, r8d; dwFlags
0x18002e603  xor     edx, edx; lpName
0x18002e605  xor     ecx, ecx; lpEventAttributes
0x18002e607  call    cs:__imp_CreateEventExW
0x18002e60d  mov     [rdi+38h], rax
0x18002e611  test    rax, rax
0x18002e614  jnz     short loc_18002E647
0x18002e616  call    cs:__imp_GetLastError
0x18002e61c  mov     ebx, eax
0x18002e61e  test    eax, eax
0x18002e620  jle     short loc_18002E62B
0x18002e622  movzx   ebx, ax
0x18002e625  or      ebx, 80070000h
0x18002e62b  test    ebx, ebx
0x18002e62d  jns     short loc_18002E647
0x18002e62f  lea     rcx, [rsp+28h+arg_0]
0x18002e634  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002e639  lea     rcx, [rsp+28h+arg_8]
0x18002e63e  call    ??1?$MakeAllocator@VUserSigninChangeWatcher@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<UserSigninChangeWatcher>::~MakeAllocator<UserSigninChangeWatcher>(void)
0x18002e643  mov     eax, ebx
0x18002e645  jmp     short loc_18002E66C
0x18002e647  mov     rax, [rdi]
0x18002e64a  mov     rcx, rdi
0x18002e64d  mov     rax, [rax+8]
0x18002e651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e656  nop
0x18002e657  mov     [rsi], rdi
0x18002e65a  mov     rax, [rdi]
0x18002e65d  mov     rcx, rdi
0x18002e660  mov     rax, [rax+10h]
0x18002e664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e669  nop
0x18002e66a  xor     eax, eax
0x18002e66c  mov     rbx, [rsp+28h+arg_10]
0x18002e671  mov     rsi, [rsp+28h+arg_18]
0x18002e676  add     rsp, 20h
0x18002e67a  pop     rdi
0x18002e67b  retn
```
