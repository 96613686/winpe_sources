# RunToCompletionAsyncOperationImpl::ReadFromInputStreamAndWriteToPipe(void)

- ea: `0x18001b1d0`
- end: `0x18001b426`
- name: `?ReadFromInputStreamAndWriteToPipe@RunToCompletionAsyncOperationImpl@@AEAAJXZ`
- size: `598`
- prototype: `__int64 __fastcall(RunToCompletionAsyncOperationImpl *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bfa0`

## callees

- `0x180002dc0`
- `0x180003cc4`
- `0x180007248`
- `0x18000fd54`
- `0x180010c14`
- `0x180018a1c`
- `0x180019568`
- `0x180019ab0`
- `0x18001b1d0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001b258`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001b258`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001b38e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001b38e`

## string_xrefs

- `0x18001b239`: `Windows.Storage.Streams.DataReader`

## pseudocode

```c
__int64 __fastcall RunToCompletionAsyncOperationImpl::ReadFromInputStreamAndWriteToPipe(
        RunToCompletionAsyncOperationImpl *this)
{
  int ActivationFactory; // esi
  const void *v3; // rbx
  __int64 v4; // rsi
  __int64 (__fastcall *v5)(__int64, __int64, __int64 *); // rdi
  __int64 v6; // rdi
  DWORD v7; // edx
  __int64 v8; // rcx
  DWORD nNumberOfBytesToWrite; // [rsp+30h] [rbp-19h] BYREF
  __int64 v11; // [rsp+38h] [rbp-11h] BYREF
  __int64 v12; // [rsp+40h] [rbp-9h] BYREF
  __int64 v13; // [rsp+48h] [rbp-1h] BYREF
  __int64 v14; // [rsp+50h] [rbp+7h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp+Fh] BYREF
  const void *v16; // [rsp+60h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v18; // [rsp+80h] [rbp+37h]

  ActivationFactory = 0;
  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  v16 = 0;
  v14 = 0;
  v12 = 0;
  v11 = 0;
  v13 = 0;
  if ( *((_QWORD *)this + 25) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
    v18 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Storage.Streams.DataReader",
      0x23u,
      0x22u);
    ActivationFactory = RoGetActivationFactory(v18, &GUID_d7527847_57da_4e15_914c_06806699a098, &v14);
    if ( ActivationFactory >= 0 )
    {
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v14 + 48LL))(
                            v14,
                            *((_QWORD *)this + 25),
                            &v12);
      if ( ActivationFactory >= 0 )
      {
        v3 = operator new[](0x2000u, (const struct std::nothrow_t *)&std::nothrow);
        v16 = v3;
        if ( v3 )
        {
          do
          {
            v4 = v12;
            v5 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v12 + 232LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
            ActivationFactory = v5(v4, 0x2000, &v11);
            if ( ActivationFactory < 0 )
              break;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
            ActivationFactory = Microsoft::WRL::Details::MakeAndInitialize<AsyncInfoHelper<Windows::Foundation::IAsyncOperation<unsigned int>,Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>>,AsyncInfoHelper<Windows::Foundation::IAsyncOperation<unsigned int>,Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>>,>(&v13);
            if ( ActivationFactory < 0 )
              break;
            v6 = v13;
            ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 48LL))(v11, v13);
            if ( ActivationFactory < 0 )
              break;
            if ( !(unsigned __int8)_wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_NKH_Z(v6 + 56) )
            {
              ActivationFactory = -2147467260;
              break;
            }
            ActivationFactory = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v11 + 64LL))(
                                  v11,
                                  &nNumberOfBytesToWrite);
            if ( ActivationFactory < 0 )
              break;
            v7 = nNumberOfBytesToWrite;
            if ( nNumberOfBytesToWrite )
            {
              ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, const void *))(*(_QWORD *)v12 + 112LL))(
                                    v12,
                                    nNumberOfBytesToWrite,
                                    v3);
              if ( ActivationFactory < 0 )
                break;
              v7 = nNumberOfBytesToWrite;
              if ( nNumberOfBytesToWrite )
              {
                if ( !WriteFile(*((HANDLE *)this + 46), v3, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
                  break;
                v7 = nNumberOfBytesToWrite;
              }
            }
          }
          while ( v7 >= 0x2000 );
        }
        else
        {
          ActivationFactory = -2147024882;
        }
      }
    }
  }
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Close((char *)this + 360);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
  v8 = v12;
  if ( v12 )
  {
    v12 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v16);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18001b1d0  mov     [rsp-8+arg_8], rbx
0x18001b1d5  mov     [rsp-8+arg_10], rsi
0x18001b1da  push    rbp
0x18001b1db  push    rdi
0x18001b1dc  push    r14
0x18001b1de  lea     rbp, [rsp-47h]
0x18001b1e3  sub     rsp, 90h
0x18001b1ea  mov     rax, cs:__security_cookie
0x18001b1f1  xor     rax, rsp
0x18001b1f4  mov     [rbp+57h+var_18], rax
0x18001b1f8  mov     r14, rcx
0x18001b1fb  xor     esi, esi
0x18001b1fd  mov     [rbp+57h+nNumberOfBytesToWrite], esi
0x18001b200  mov     [rbp+57h+NumberOfBytesWritten], esi
0x18001b203  mov     [rbp+57h+var_40], rsi
0x18001b207  mov     [rbp+57h+var_50], rsi
0x18001b20b  mov     [rbp+57h+var_60], rsi
0x18001b20f  mov     [rbp+57h+var_68], rsi
0x18001b213  mov     [rbp+57h+var_58], rsi
0x18001b217  cmp     [rcx+0C8h], rsi
0x18001b21e  jz      loc_18001B3AE
0x18001b224  lea     rcx, [rbp+57h+var_50]
0x18001b228  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001b22d  mov     [rbp+57h+var_20], rsi
0x18001b231  lea     r9d, [rsi+22h]; unsigned int
0x18001b235  lea     r8d, [rsi+23h]; unsigned int
0x18001b239  lea     rdx, ?RuntimeClass_Windows_Storage_Streams_DataReader@@3QBGB; "Windows.Storage.Streams.DataReader"
0x18001b240  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001b244  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001b249  lea     r8, [rbp+57h+var_50]
0x18001b24d  lea     rdx, _GUID_d7527847_57da_4e15_914c_06806699a098
0x18001b254  mov     rcx, [rbp+57h+var_20]
0x18001b258  call    cs:__imp_RoGetActivationFactory
0x18001b25e  mov     esi, eax
0x18001b260  test    eax, eax
0x18001b262  js      loc_18001B3AE
0x18001b268  mov     rcx, [rbp+57h+var_50]
0x18001b26c  mov     rax, [rcx]
0x18001b26f  lea     r8, [rbp+57h+var_60]
0x18001b273  mov     rdx, [r14+0C8h]
0x18001b27a  mov     rax, [rax+30h]
0x18001b27e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b283  mov     esi, eax
0x18001b285  test    eax, eax
0x18001b287  js      loc_18001B3AE
0x18001b28d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b294  mov     ecx, 2000h; unsigned __int64
0x18001b299  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001b29e  mov     rbx, rax
0x18001b2a1  mov     [rbp+57h+var_40], rax
0x18001b2a5  test    rax, rax
0x18001b2a8  jnz     short loc_18001B2B4
0x18001b2aa  mov     esi, 8007000Eh
0x18001b2af  jmp     loc_18001B3AE
0x18001b2b4  mov     rsi, [rbp+57h+var_60]
0x18001b2b8  mov     rax, [rsi]
0x18001b2bb  mov     rdi, [rax+0E8h]
0x18001b2c2  lea     rcx, [rbp+57h+var_68]
0x18001b2c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001b2cb  lea     r8, [rbp+57h+var_68]
0x18001b2cf  mov     edx, 2000h
0x18001b2d4  mov     rcx, rsi
0x18001b2d7  mov     rax, rdi
0x18001b2da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2df  mov     esi, eax
0x18001b2e1  test    eax, eax
0x18001b2e3  js      loc_18001B3AE
0x18001b2e9  lea     rcx, [rbp+57h+var_58]
0x18001b2ed  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001b2f2  lea     rcx, [rbp+57h+var_58]
0x18001b2f6  call    ??$MakeAndInitialize@V?$AsyncInfoHelper@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$AsyncInfoHelper@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@@Z; Microsoft::WRL::Details::MakeAndInitialize<AsyncInfoHelper<Windows::Foundation::IAsyncOperation<uint>,Windows::Foundation::IAsyncOperationCompletedHandler<uint>>,AsyncInfoHelper<Windows::Foundation::IAsyncOperation<uint>,Windows::Foundation::IAsyncOperationCompletedHandler<uint>>,>(AsyncInfoHelper<Windows::Foundation::IAsyncOperation<uint>,Windows::Foundation::IAsyncOperationCompletedHandler<uint>> * *)
0x18001b2fb  mov     esi, eax
0x18001b2fd  test    eax, eax
0x18001b2ff  js      loc_18001B3AE
0x18001b305  mov     rcx, [rbp+57h+var_68]
0x18001b309  mov     rax, [rcx]
0x18001b30c  mov     rdi, [rbp+57h+var_58]
0x18001b310  mov     rdx, rdi
0x18001b313  mov     rax, [rax+30h]
0x18001b317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b31c  mov     esi, eax
0x18001b31e  test    eax, eax
0x18001b320  js      loc_18001B3AE
0x18001b326  lea     rcx, [rdi+38h]
0x18001b32a  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA_NKH@Z
0x18001b32f  test    al, al
0x18001b331  jz      short loc_18001B3A9
0x18001b333  mov     rcx, [rbp+57h+var_68]
0x18001b337  mov     rax, [rcx]
0x18001b33a  lea     rdx, [rbp+57h+nNumberOfBytesToWrite]
0x18001b33e  mov     rax, [rax+40h]
0x18001b342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b347  mov     esi, eax
0x18001b349  test    eax, eax
0x18001b34b  js      short loc_18001B3AE
0x18001b34d  mov     edx, [rbp+57h+nNumberOfBytesToWrite]
0x18001b350  test    edx, edx
0x18001b352  jz      short loc_18001B39B
0x18001b354  mov     rcx, [rbp+57h+var_60]
0x18001b358  mov     rax, [rcx]
0x18001b35b  mov     r8, rbx
0x18001b35e  mov     rax, [rax+70h]
0x18001b362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b367  mov     esi, eax
0x18001b369  test    eax, eax
0x18001b36b  js      short loc_18001B3AE
0x18001b36d  mov     edx, [rbp+57h+nNumberOfBytesToWrite]
0x18001b370  test    edx, edx
0x18001b372  jz      short loc_18001B39B
0x18001b374  mov     [rsp+0A0h+lpOverlapped], 0; lpOverlapped
0x18001b37d  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001b381  mov     r8d, edx; nNumberOfBytesToWrite
0x18001b384  mov     rdx, rbx; lpBuffer
0x18001b387  mov     rcx, [r14+170h]; hFile
0x18001b38e  call    cs:__imp_WriteFile
0x18001b394  test    eax, eax
0x18001b396  jz      short loc_18001B3AE
0x18001b398  mov     edx, [rbp+57h+nNumberOfBytesToWrite]
0x18001b39b  cmp     edx, 2000h
0x18001b3a1  jnb     loc_18001B2B4
0x18001b3a7  jmp     short loc_18001B3AE
0x18001b3a9  mov     esi, 80004004h
0x18001b3ae  lea     rcx, [r14+168h]
0x18001b3b5  call    ?Close@?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Close(void)
0x18001b3ba  nop
0x18001b3bb  lea     rcx, [rbp+57h+var_58]
0x18001b3bf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001b3c4  nop
0x18001b3c5  lea     rcx, [rbp+57h+var_68]
0x18001b3c9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001b3ce  nop
0x18001b3cf  mov     rcx, [rbp+57h+var_60]
0x18001b3d3  test    rcx, rcx
0x18001b3d6  jz      short loc_18001B3ED
0x18001b3d8  mov     [rbp+57h+var_60], 0
0x18001b3e0  mov     rax, [rcx]
0x18001b3e3  mov     rax, [rax+10h]
0x18001b3e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3ec  nop
0x18001b3ed  lea     rcx, [rbp+57h+var_50]
0x18001b3f1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001b3f6  nop
0x18001b3f7  lea     rcx, [rbp+57h+var_40]
0x18001b3fb  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x18001b400  mov     eax, esi
0x18001b402  mov     rcx, [rbp+57h+var_18]
0x18001b406  xor     rcx, rsp; StackCookie
0x18001b409  call    __security_check_cookie
0x18001b40e  lea     r11, [rsp+0A0h+var_10]
0x18001b416  mov     rbx, [r11+28h]
0x18001b41a  mov     rsi, [r11+30h]
0x18001b41e  mov     rsp, r11
0x18001b421  pop     r14
0x18001b423  pop     rdi
0x18001b424  pop     rbp
0x18001b425  retn
```
