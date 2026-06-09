# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180025c58`
- end: `0x180025de1`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `393`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026a08`

## callees

- `0x180004060`
- `0x1800257ec`
- `0x180025c58`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180025d02`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180025d02`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        HRESULT a2,
        __int64 a3)
{
  int v4; // ebx
  char v5; // bl
  int (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rbx
  int (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rbx
  int (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // [rsp+30h] [rbp-20h] BYREF
  HANDLE pHandles[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v11; // [rsp+70h] [rbp+20h] BYREF
  HRESULT v12; // [rsp+78h] [rbp+28h] BYREF
  __int64 dwindex; // [rsp+80h] [rbp+30h] BYREF
  __int64 v14; // [rsp+88h] [rbp+38h] BYREF

  dwindex = a3;
  v12 = a2;
  v9 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a1;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v14 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  v4 = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&v14);
  v12 = v4;
  if ( v4 >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[6])(a1, v14);
    v12 = v4;
    if ( v4 >= 0 )
    {
      pHandles[0] = *(HANDLE *)(v14 + 56);
      pHandles[1] = 0;
      v5 = 0;
      LODWORD(dwindex) = 0;
      v12 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex);
      if ( v12 >= 0 && (_DWORD)dwindex )
      {
        v12 = -2147023673;
        v5 = 1;
      }
      v11 = 0;
      if ( v5 )
      {
        v6 = **a1;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
        if ( v6(a1, &GUID_00000036_0000_0000_c000_000000000046, &v11) >= 0 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 72LL))(v11);
      }
      if ( v12 >= 0 && *(_DWORD *)(v14 + 48) != 1 )
      {
        if ( v11
          || (v7 = **a1,
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11),
              v7(a1, &GUID_00000036_0000_0000_c000_000000000046, &v11) >= 0) )
        {
          (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v11 + 64LL))(v11, &v12);
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
      v4 = v12;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180025c58  mov     [rsp-18h+dwindex], r8
0x180025c5d  mov     [rsp-18h+arg_8], edx
0x180025c61  push    rbp
0x180025c62  push    rbx
0x180025c63  push    rdi
0x180025c64  mov     rbp, rsp
0x180025c67  sub     rsp, 50h
0x180025c6b  mov     rdi, rcx
0x180025c6e  mov     [rbp+var_20], rcx
0x180025c72  test    rcx, rcx
0x180025c75  jz      short loc_180025C84
0x180025c77  mov     rax, [rcx]
0x180025c7a  mov     rax, [rax+8]
0x180025c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c83  nop
0x180025c84  mov     [rbp+arg_18], 0
0x180025c8c  lea     rcx, [rbp+arg_18]
0x180025c90  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025c95  lea     rcx, [rbp+arg_18]
0x180025c99  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x180025c9e  mov     ebx, eax
0x180025ca0  mov     [rbp+arg_8], eax
0x180025ca3  test    eax, eax
0x180025ca5  js      loc_180025DC4
0x180025cab  mov     rax, [rdi]
0x180025cae  mov     rdx, [rbp+arg_18]
0x180025cb2  mov     rcx, rdi
0x180025cb5  mov     rax, [rax+30h]
0x180025cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cbe  mov     ebx, eax
0x180025cc0  mov     [rbp+arg_8], eax
0x180025cc3  test    eax, eax
0x180025cc5  js      loc_180025DC4
0x180025ccb  mov     rax, [rbp+arg_18]
0x180025ccf  mov     rcx, [rax+38h]
0x180025cd3  mov     [rbp+pHandles], rcx
0x180025cd7  mov     [rbp+var_10], 0
0x180025cdf  xor     bl, bl
0x180025ce1  mov     dword ptr [rbp+dwindex], 0
0x180025ce8  lea     rax, [rbp+dwindex]
0x180025cec  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180025cf1  lea     r9, [rbp+pHandles]; pHandles
0x180025cf5  mov     r8d, 1; cHandles
0x180025cfb  or      edx, 0FFFFFFFFh; dwTimeout
0x180025cfe  lea     ecx, [r8+7]; dwFlags
0x180025d02  call    cs:__imp_CoWaitForMultipleHandles
0x180025d08  mov     [rbp+arg_8], eax
0x180025d0b  test    eax, eax
0x180025d0d  js      short loc_180025D1E
0x180025d0f  cmp     dword ptr [rbp+dwindex], 0
0x180025d13  jz      short loc_180025D1E
0x180025d15  mov     [rbp+arg_8], 800704C7h
0x180025d1c  mov     bl, 1
0x180025d1e  mov     [rbp+arg_0], 0
0x180025d26  test    bl, bl
0x180025d28  jz      short loc_180025D63
0x180025d2a  mov     rax, [rdi]
0x180025d2d  mov     rbx, [rax]
0x180025d30  lea     rcx, [rbp+arg_0]
0x180025d34  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025d39  lea     r8, [rbp+arg_0]
0x180025d3d  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180025d44  mov     rcx, rdi
0x180025d47  mov     rax, rbx
0x180025d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d4f  test    eax, eax
0x180025d51  js      short loc_180025D63
0x180025d53  mov     rcx, [rbp+arg_0]
0x180025d57  mov     rax, [rcx]
0x180025d5a  mov     rax, [rax+48h]
0x180025d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d63  cmp     [rbp+arg_8], 0
0x180025d67  jl      short loc_180025DB8
0x180025d69  mov     rax, [rbp+arg_18]
0x180025d6d  cmp     dword ptr [rax+30h], 1
0x180025d71  jz      short loc_180025DB8
0x180025d73  cmp     [rbp+arg_0], 0
0x180025d78  jnz     short loc_180025DA3
0x180025d7a  mov     rax, [rdi]
0x180025d7d  mov     rbx, [rax]
0x180025d80  lea     rcx, [rbp+arg_0]
0x180025d84  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025d89  lea     r8, [rbp+arg_0]
0x180025d8d  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180025d94  mov     rcx, rdi
0x180025d97  mov     rax, rbx
0x180025d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d9f  test    eax, eax
0x180025da1  js      short loc_180025DB8
0x180025da3  mov     rcx, [rbp+arg_0]
0x180025da7  mov     rax, [rcx]
0x180025daa  lea     rdx, [rbp+arg_8]
0x180025dae  mov     rax, [rax+40h]
0x180025db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025db7  nop
0x180025db8  lea     rcx, [rbp+arg_0]
0x180025dbc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025dc1  mov     ebx, [rbp+arg_8]
0x180025dc4  lea     rcx, [rbp+arg_18]
0x180025dc8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025dcd  nop
0x180025dce  lea     rcx, [rbp+var_20]
0x180025dd2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025dd7  mov     eax, ebx
0x180025dd9  add     rsp, 50h
0x180025ddd  pop     rdi
0x180025dde  pop     rbx
0x180025ddf  pop     rbp
0x180025de0  retn
```
