# RunToCompletionAsyncOperationImpl::ReadFromPipeAndWriteToStream(void *,Windows::Storage::Streams::IOutputStream *)

- ea: `0x18001b42c`
- end: `0x18001b5cb`
- name: `?ReadFromPipeAndWriteToStream@RunToCompletionAsyncOperationImpl@@AEAAJPEAXPEAUIOutputStream@Streams@Storage@Windows@@@Z`
- size: `415`
- prototype: `__int64 __fastcall(RunToCompletionAsyncOperationImpl *this, void *, struct Windows::Storage::Streams::IOutputStream *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c0a0`
- `0x18001c110`

## callees

- `0x180003de8`
- `0x180007248`
- `0x18000fd54`
- `0x180010198`
- `0x180019568`
- `0x18001ac74`
- `0x18001b42c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4d5`
- `api-ms-win-core-namedpipe-l1-1-0!PeekNamedPipe` at `0x18001b487`
- `api-ms-win-core-namedpipe-l1-1-0!PeekNamedPipe` at `0x18001b487`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001b4c2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001b4c2`

## pseudocode

```c
__int64 __fastcall RunToCompletionAsyncOperationImpl::ReadFromPipeAndWriteToStream(
        RunToCompletionAsyncOperationImpl *this,
        void *a2,
        struct Windows::Storage::Streams::IOutputStream *a3)
{
  int v6; // ebx
  void *v7; // rdi
  RunToCompletionAsyncOperationImpl *v8; // rcx
  DWORD v9; // r9d
  __int64 (__fastcall *v10)(struct Windows::Storage::Streams::IOutputStream *, __int64 *); // rbx
  DWORD TotalBytesAvail; // [rsp+30h] [rbp-28h] BYREF
  __int64 v13; // [rsp+38h] [rbp-20h] BYREF
  __int64 v14; // [rsp+40h] [rbp-18h] BYREF
  void *v15; // [rsp+48h] [rbp-10h] BYREF
  DWORD NumberOfBytesRead; // [rsp+A8h] [rbp+50h] BYREF

  v6 = 0;
  v7 = operator new[](0x2000u);
  v15 = v7;
  while ( 1 )
  {
    TotalBytesAvail = 0;
    NumberOfBytesRead = 0;
    if ( !PeekNamedPipe(a2, 0, 0, 0, &TotalBytesAvail, 0) || !TotalBytesAvail && *((_DWORD *)this + 68) )
      break;
    if ( !ReadFile(a2, v7, 0x2000u, &NumberOfBytesRead, 0) || (v9 = NumberOfBytesRead) == 0 )
    {
      if ( GetLastError() != 995 )
        break;
      v9 = NumberOfBytesRead;
    }
    v6 = RunToCompletionAsyncOperationImpl::OutputStreamSyncWrite(v8, a3, (const unsigned __int8 *)v7, v9);
    if ( v6 < 0 )
      break;
    v13 = 0;
    v10 = *(__int64 (__fastcall **)(struct Windows::Storage::Streams::IOutputStream *, __int64 *))(*(_QWORD *)a3 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
    v6 = v10(a3, &v13);
    if ( v6 < 0 )
      goto LABEL_17;
    v14 = 0;
    v6 = Microsoft::WRL::Details::MakeAndInitialize<AsyncInfoHelper<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>,AsyncInfoHelper<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>,>(&v14);
    if ( v6 < 0 || (v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 48LL))(v13, v14), v6 < 0) )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
LABEL_17:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      break;
    }
    if ( !(unsigned __int8)_wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_NKH_Z(v14 + 56) )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      v6 = -2147467260;
      break;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
    v6 = 0;
  }
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001b42c  push    rbp
0x18001b42e  push    rbx
0x18001b42f  push    rsi
0x18001b430  push    rdi
0x18001b431  push    r14
0x18001b433  push    r15
0x18001b435  mov     rbp, rsp
0x18001b438  sub     rsp, 58h
0x18001b43c  mov     rsi, r8
0x18001b43f  mov     r14, rdx
0x18001b442  mov     r15, rcx
0x18001b445  xor     ebx, ebx
0x18001b447  mov     [rbp+var_10], rbx
0x18001b44b  mov     ecx, 2000h; unsigned __int64
0x18001b450  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001b455  mov     rdi, rax
0x18001b458  mov     [rbp+var_10], rax
0x18001b45c  mov     [rbp+TotalBytesAvail], 0
0x18001b463  mov     [rbp+NumberOfBytesRead], 0
0x18001b46a  mov     [rsp+58h+lpBytesLeftThisMessage], 0; lpBytesLeftThisMessage
0x18001b473  lea     rax, [rbp+TotalBytesAvail]
0x18001b477  mov     [rsp+58h+lpTotalBytesAvail], rax; lpTotalBytesAvail
0x18001b47c  xor     r9d, r9d; lpBytesRead
0x18001b47f  xor     r8d, r8d; nBufferSize
0x18001b482  xor     edx, edx; lpBuffer
0x18001b484  mov     rcx, r14; hNamedPipe
0x18001b487  call    cs:__imp_PeekNamedPipe
0x18001b48d  test    eax, eax
0x18001b48f  jz      loc_18001B5B3
0x18001b495  cmp     [rbp+TotalBytesAvail], 0
0x18001b499  jnz     short loc_18001B4A9
0x18001b49b  cmp     dword ptr [r15+110h], 0
0x18001b4a3  jnz     loc_18001B5B3
0x18001b4a9  mov     [rsp+58h+lpTotalBytesAvail], 0; lpOverlapped
0x18001b4b2  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001b4b6  mov     r8d, 2000h; nNumberOfBytesToRead
0x18001b4bc  mov     rdx, rdi; lpBuffer
0x18001b4bf  mov     rcx, r14; hFile
0x18001b4c2  call    cs:__imp_ReadFile
0x18001b4c8  test    eax, eax
0x18001b4ca  jz      short loc_18001B4D5
0x18001b4cc  mov     r9d, [rbp+NumberOfBytesRead]
0x18001b4d0  test    r9d, r9d
0x18001b4d3  jnz     short loc_18001B4EA
0x18001b4d5  call    cs:__imp_GetLastError
0x18001b4db  cmp     eax, 3E3h
0x18001b4e0  jnz     loc_18001B5B3
0x18001b4e6  mov     r9d, [rbp+NumberOfBytesRead]; unsigned int
0x18001b4ea  mov     r8, rdi; unsigned __int8 *
0x18001b4ed  mov     rdx, rsi; struct Windows::Storage::Streams::IOutputStream *
0x18001b4f0  call    ?OutputStreamSyncWrite@RunToCompletionAsyncOperationImpl@@AEAAJPEAUIOutputStream@Streams@Storage@Windows@@PEBEI@Z; RunToCompletionAsyncOperationImpl::OutputStreamSyncWrite(Windows::Storage::Streams::IOutputStream *,uchar const *,uint)
0x18001b4f5  mov     ebx, eax
0x18001b4f7  test    eax, eax
0x18001b4f9  js      loc_18001B5B3
0x18001b4ff  mov     [rbp+var_20], 0
0x18001b507  mov     rax, [rsi]
0x18001b50a  mov     rbx, [rax+38h]
0x18001b50e  lea     rcx, [rbp+var_20]
0x18001b512  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001b517  lea     rdx, [rbp+var_20]
0x18001b51b  mov     rcx, rsi
0x18001b51e  mov     rax, rbx
0x18001b521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b526  mov     ebx, eax
0x18001b528  test    eax, eax
0x18001b52a  js      short loc_18001B5A9
0x18001b52c  mov     [rbp+var_18], 0
0x18001b534  lea     rcx, [rbp+var_18]
0x18001b538  call    ??$MakeAndInitialize@V?$AsyncInfoHelper@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@V?$AsyncInfoHelper@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<AsyncInfoHelper<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>,AsyncInfoHelper<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<AsyncInfoHelper<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>>>)
0x18001b53d  mov     ebx, eax
0x18001b53f  test    eax, eax
0x18001b541  js      short loc_18001B59F
0x18001b543  mov     rcx, [rbp+var_20]
0x18001b547  mov     rax, [rcx]
0x18001b54a  mov     rdx, [rbp+var_18]
0x18001b54e  mov     rax, [rax+30h]
0x18001b552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b557  mov     ebx, eax
0x18001b559  test    eax, eax
0x18001b55b  js      short loc_18001B59F
0x18001b55d  mov     rcx, [rbp+var_18]
0x18001b561  add     rcx, 38h ; '8'
0x18001b565  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA_NKH@Z
0x18001b56a  nop
0x18001b56b  lea     rcx, [rbp+var_18]
0x18001b56f  test    al, al
0x18001b571  jz      short loc_18001B589
0x18001b573  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001b578  nop
0x18001b579  lea     rcx, [rbp+var_20]
0x18001b57d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001b582  xor     ebx, ebx
0x18001b584  jmp     loc_18001B45C
0x18001b589  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001b58e  nop
0x18001b58f  lea     rcx, [rbp+var_20]
0x18001b593  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001b598  mov     ebx, 80004004h
0x18001b59d  jmp     short loc_18001B5B3
0x18001b59f  lea     rcx, [rbp+var_18]
0x18001b5a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001b5a8  nop
0x18001b5a9  lea     rcx, [rbp+var_20]
0x18001b5ad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001b5b2  nop
0x18001b5b3  lea     rcx, [rbp+var_10]
0x18001b5b7  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x18001b5bc  mov     eax, ebx
0x18001b5be  add     rsp, 58h
0x18001b5c2  pop     r15
0x18001b5c4  pop     r14
0x18001b5c6  pop     rdi
0x18001b5c7  pop     rsi
0x18001b5c8  pop     rbx
0x18001b5c9  pop     rbp
0x18001b5ca  retn
```
