# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18001c86c`
- end: `0x18001c94b`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `223`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001cbc0`

## callees

- `0x18000d530`
- `0x180014a00`
- `0x180017db0`
- `0x18001c86c`
- `0x18001cd98`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001c8e5`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001c8e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c8f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c8f4`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  void *v2; // rax
  signed int v3; // ebx
  _QWORD *v4; // rdi
  HANDLE Event; // rax
  signed int LastError; // eax
  _QWORD *v8; // [rsp+40h] [rbp+8h] BYREF
  void *v9; // [rsp+48h] [rbp+10h] BYREF
  void *v10; // [rsp+50h] [rbp+18h]

  *a1 = 0;
  v9 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v9 = v2;
  v8 = v2;
  if ( v2 )
  {
    v10 = v2;
    v4 = (_QWORD *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>'::`2'::FTMEventDelegate::FTMEventDelegate(v2);
    v8 = v4;
    v9 = 0;
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
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v8);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v8);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<StorSvcNVMeHealthNotificationActivationCallback>::~MakeAllocator<StorSvcNVMeHealthNotificationActivationCallback>(&v9);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001c86c  push    rbx
0x18001c86e  push    rsi
0x18001c86f  push    rdi
0x18001c870  sub     rsp, 20h
0x18001c874  mov     rsi, rcx
0x18001c877  mov     qword ptr [rcx], 0
0x18001c87e  mov     [rsp+38h+arg_8], 0
0x18001c887  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c88e  mov     ecx, 40h ; '@'; unsigned __int64
0x18001c893  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001c898  mov     [rsp+38h+arg_8], rax
0x18001c89d  mov     [rsp+38h+arg_0], rax
0x18001c8a2  test    rax, rax
0x18001c8a5  jnz     short loc_18001C8B1
0x18001c8a7  mov     ebx, 8007000Eh
0x18001c8ac  jmp     loc_18001C937
0x18001c8b1  mov     [rsp+38h+arg_10], rax
0x18001c8b6  mov     rcx, rax
0x18001c8b9  call    ??0FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@QEAA@XZ; `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::FTMEventDelegate(void)
0x18001c8be  mov     rdi, rax
0x18001c8c1  mov     [rsp+38h+arg_0], 0
0x18001c8ca  mov     [rsp+38h+arg_0], rax
0x18001c8cf  mov     [rsp+38h+arg_8], 0
0x18001c8d8  mov     r9d, 1F0003h; dwDesiredAccess
0x18001c8de  xor     r8d, r8d; dwFlags
0x18001c8e1  xor     edx, edx; lpName
0x18001c8e3  xor     ecx, ecx; lpEventAttributes
0x18001c8e5  call    cs:__imp_CreateEventExW
0x18001c8eb  mov     [rdi+38h], rax
0x18001c8ef  test    rax, rax
0x18001c8f2  jnz     short loc_18001C919
0x18001c8f4  call    cs:__imp_GetLastError
0x18001c8fa  mov     ebx, eax
0x18001c8fc  test    eax, eax
0x18001c8fe  jle     short loc_18001C909
0x18001c900  movzx   ebx, ax
0x18001c903  or      ebx, 80070000h
0x18001c909  test    ebx, ebx
0x18001c90b  jns     short loc_18001C919
0x18001c90d  lea     rcx, [rsp+38h+arg_0]
0x18001c912  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001c917  jmp     short loc_18001C937
0x18001c919  mov     rax, [rdi]
0x18001c91c  mov     rcx, rdi
0x18001c91f  mov     rax, [rax+8]
0x18001c923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c928  mov     [rsi], rdi
0x18001c92b  lea     rcx, [rsp+38h+arg_0]
0x18001c930  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001c935  xor     ebx, ebx
0x18001c937  lea     rcx, [rsp+38h+arg_8]
0x18001c93c  call    ??1?$MakeAllocator@VStorSvcNVMeHealthNotificationActivationCallback@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<StorSvcNVMeHealthNotificationActivationCallback>::~MakeAllocator<StorSvcNVMeHealthNotificationActivationCallback>(void)
0x18001c941  mov     eax, ebx
0x18001c943  add     rsp, 20h
0x18001c947  pop     rdi
0x18001c948  pop     rsi
0x18001c949  pop     rbx
0x18001c94a  retn
```
