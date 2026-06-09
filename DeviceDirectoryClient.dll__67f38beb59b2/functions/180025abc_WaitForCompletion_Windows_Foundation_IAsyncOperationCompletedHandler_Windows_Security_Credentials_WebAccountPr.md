# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180025abc`
- end: `0x180025c51`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `405`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026a08`

## callees

- `0x180004060`
- `0x1800256b8`
- `0x180025abc`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180025b66`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180025b66`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        HRESULT a2,
        __int64 a3)
{
  int v4; // ebx
  char v5; // bl
  int (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rbx
  int (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rbx
  HANDLE pHandles[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v10; // [rsp+70h] [rbp+20h] BYREF
  HRESULT v11; // [rsp+78h] [rbp+28h] BYREF
  __int64 dwindex; // [rsp+80h] [rbp+30h] BYREF
  __int64 v13; // [rsp+88h] [rbp+38h] BYREF

  dwindex = a3;
  v11 = a2;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v13 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  v4 = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&v13);
  v11 = v4;
  if ( v4 >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[6])(a1, v13);
    v11 = v4;
    if ( v4 >= 0 )
    {
      pHandles[0] = *(HANDLE *)(v13 + 56);
      pHandles[1] = 0;
      v5 = 0;
      LODWORD(dwindex) = 0;
      v11 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex);
      if ( v11 >= 0 && (_DWORD)dwindex )
      {
        v11 = -2147023673;
        v5 = 1;
      }
      v10 = 0;
      if ( v5 )
      {
        v6 = **a1;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
        if ( v6(a1, &GUID_00000036_0000_0000_c000_000000000046, &v10) >= 0 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 72LL))(v10);
      }
      if ( v11 >= 0 && *(_DWORD *)(v13 + 48) != 1 )
      {
        if ( v10
          || (v7 = **a1,
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10),
              v7(a1, &GUID_00000036_0000_0000_c000_000000000046, &v10) >= 0) )
        {
          (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v10 + 64LL))(v10, &v11);
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
      v4 = v11;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180025abc  mov     [rsp-18h+dwindex], r8
0x180025ac1  mov     [rsp-18h+arg_8], edx
0x180025ac5  push    rbp
0x180025ac6  push    rbx
0x180025ac7  push    rdi
0x180025ac8  mov     rbp, rsp
0x180025acb  sub     rsp, 50h
0x180025acf  mov     rdi, rcx
0x180025ad2  mov     [rbp+var_20], rcx
0x180025ad6  test    rcx, rcx
0x180025ad9  jz      short loc_180025AE8
0x180025adb  mov     rax, [rcx]
0x180025ade  mov     rax, [rax+8]
0x180025ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ae7  nop
0x180025ae8  mov     [rbp+arg_18], 0
0x180025af0  lea     rcx, [rbp+arg_18]
0x180025af4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025af9  lea     rcx, [rbp+arg_18]
0x180025afd  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x180025b02  mov     ebx, eax
0x180025b04  mov     [rbp+arg_8], eax
0x180025b07  test    eax, eax
0x180025b09  js      loc_180025C28
0x180025b0f  mov     rax, [rdi]
0x180025b12  mov     rdx, [rbp+arg_18]
0x180025b16  mov     rcx, rdi
0x180025b19  mov     rax, [rax+30h]
0x180025b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b22  mov     ebx, eax
0x180025b24  mov     [rbp+arg_8], eax
0x180025b27  test    eax, eax
0x180025b29  js      loc_180025C28
0x180025b2f  mov     rax, [rbp+arg_18]
0x180025b33  mov     rcx, [rax+38h]
0x180025b37  mov     [rbp+pHandles], rcx
0x180025b3b  mov     [rbp+var_10], 0
0x180025b43  xor     bl, bl
0x180025b45  mov     dword ptr [rbp+dwindex], 0
0x180025b4c  lea     rax, [rbp+dwindex]
0x180025b50  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180025b55  lea     r9, [rbp+pHandles]; pHandles
0x180025b59  mov     r8d, 1; cHandles
0x180025b5f  or      edx, 0FFFFFFFFh; dwTimeout
0x180025b62  lea     ecx, [r8+7]; dwFlags
0x180025b66  call    cs:__imp_CoWaitForMultipleHandles
0x180025b6c  mov     [rbp+arg_8], eax
0x180025b6f  test    eax, eax
0x180025b71  js      short loc_180025B82
0x180025b73  cmp     dword ptr [rbp+dwindex], 0
0x180025b77  jz      short loc_180025B82
0x180025b79  mov     [rbp+arg_8], 800704C7h
0x180025b80  mov     bl, 1
0x180025b82  mov     [rbp+arg_0], 0
0x180025b8a  test    bl, bl
0x180025b8c  jz      short loc_180025BC7
0x180025b8e  mov     rax, [rdi]
0x180025b91  mov     rbx, [rax]
0x180025b94  lea     rcx, [rbp+arg_0]
0x180025b98  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025b9d  lea     r8, [rbp+arg_0]
0x180025ba1  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180025ba8  mov     rcx, rdi
0x180025bab  mov     rax, rbx
0x180025bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bb3  test    eax, eax
0x180025bb5  js      short loc_180025BC7
0x180025bb7  mov     rcx, [rbp+arg_0]
0x180025bbb  mov     rax, [rcx]
0x180025bbe  mov     rax, [rax+48h]
0x180025bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bc7  cmp     [rbp+arg_8], 0
0x180025bcb  jl      short loc_180025C1C
0x180025bcd  mov     rax, [rbp+arg_18]
0x180025bd1  cmp     dword ptr [rax+30h], 1
0x180025bd5  jz      short loc_180025C1C
0x180025bd7  cmp     [rbp+arg_0], 0
0x180025bdc  jnz     short loc_180025C07
0x180025bde  mov     rax, [rdi]
0x180025be1  mov     rbx, [rax]
0x180025be4  lea     rcx, [rbp+arg_0]
0x180025be8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025bed  lea     r8, [rbp+arg_0]
0x180025bf1  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180025bf8  mov     rcx, rdi
0x180025bfb  mov     rax, rbx
0x180025bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c03  test    eax, eax
0x180025c05  js      short loc_180025C1C
0x180025c07  mov     rcx, [rbp+arg_0]
0x180025c0b  mov     rax, [rcx]
0x180025c0e  lea     rdx, [rbp+arg_8]
0x180025c12  mov     rax, [rax+40h]
0x180025c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c1b  nop
0x180025c1c  lea     rcx, [rbp+arg_0]
0x180025c20  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025c25  mov     ebx, [rbp+arg_8]
0x180025c28  lea     rcx, [rbp+arg_18]
0x180025c2c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025c31  nop
0x180025c32  test    rdi, rdi
0x180025c35  jz      short loc_180025C47
0x180025c37  mov     rcx, [rdi]
0x180025c3a  mov     rax, [rcx+10h]
0x180025c3e  mov     rcx, rdi
0x180025c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c46  nop
0x180025c47  mov     eax, ebx
0x180025c49  add     rsp, 50h
0x180025c4d  pop     rdi
0x180025c4e  pop     rbx
0x180025c4f  pop     rbp
0x180025c50  retn
```
