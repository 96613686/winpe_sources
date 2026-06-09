# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x18001f818`
- end: `0x18001f9f9`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `481`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), int, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e4f0`
- `0x18001f668`

## callees

- `0x18001f818`
- `0x18001fa00`
- `0x18001fa2c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001f8be`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001f8be`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        int a2,
        __int64 a3)
{
  char v4; // bl
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rcx
  int (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rbx
  int (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rbx
  HANDLE pHandles[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v12; // [rsp+70h] [rbp+20h] BYREF
  int v13; // [rsp+78h] [rbp+28h] BYREF
  __int64 dwindex; // [rsp+80h] [rbp+30h] BYREF
  __int64 v15; // [rsp+88h] [rbp+38h] BYREF

  dwindex = a3;
  v13 = a2;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v15 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  v13 = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&v15);
  if ( v13 >= 0 )
  {
    v13 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[6])(a1, v15);
    if ( v13 >= 0 )
    {
      pHandles[0] = *(HANDLE *)(v15 + 56);
      pHandles[1] = 0;
      v4 = 0;
      LODWORD(dwindex) = 0;
      v13 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex);
      if ( v13 >= 0 && (_DWORD)dwindex )
      {
        v13 = -2147023673;
        v4 = 1;
      }
      v12 = 0;
      if ( v4 )
      {
        v9 = **a1;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
        if ( v9(a1, &GUID_00000036_0000_0000_c000_000000000046, &v12) >= 0 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 72LL))(v12);
      }
      if ( v13 >= 0 && *(_DWORD *)(v15 + 48) != 1 )
      {
        if ( v12
          || (v10 = **a1,
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12),
              v10(a1, &GUID_00000036_0000_0000_c000_000000000046, &v12) >= 0) )
        {
          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 64LL))(v12, &v13);
        }
      }
      v5 = v12;
      if ( v12 )
      {
        v12 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      }
    }
  }
  v6 = v13;
  v7 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return v6;
}

```

## disassembly

```asm
0x18001f818  mov     [rsp-18h+dwindex], r8
0x18001f81d  mov     [rsp-18h+arg_8], edx
0x18001f821  push    rbp
0x18001f822  push    rbx
0x18001f823  push    rdi
0x18001f824  mov     rbp, rsp
0x18001f827  sub     rsp, 50h
0x18001f82b  mov     rdi, rcx
0x18001f82e  mov     [rbp+var_20], rcx
0x18001f832  test    rcx, rcx
0x18001f835  jz      short loc_18001F844
0x18001f837  mov     rax, [rcx]
0x18001f83a  mov     rax, [rax+8]
0x18001f83e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f843  nop
0x18001f844  mov     [rbp+arg_18], 0
0x18001f84c  lea     rcx, [rbp+arg_18]
0x18001f850  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f855  lea     rcx, [rbp+arg_18]
0x18001f859  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x18001f85e  mov     [rbp+arg_8], eax
0x18001f861  test    eax, eax
0x18001f863  js      loc_18001F911
0x18001f869  mov     rax, [rdi]
0x18001f86c  mov     rdx, [rbp+arg_18]
0x18001f870  mov     rcx, rdi
0x18001f873  mov     rax, [rax+30h]
0x18001f877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f87c  mov     [rbp+arg_8], eax
0x18001f87f  test    eax, eax
0x18001f881  js      loc_18001F911
0x18001f887  mov     rax, [rbp+arg_18]
0x18001f88b  mov     rcx, [rax+38h]
0x18001f88f  mov     [rbp+pHandles], rcx
0x18001f893  mov     [rbp+var_10], 0
0x18001f89b  xor     bl, bl
0x18001f89d  mov     dword ptr [rbp+dwindex], 0
0x18001f8a4  lea     rax, [rbp+dwindex]
0x18001f8a8  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x18001f8ad  lea     r9, [rbp+pHandles]; pHandles
0x18001f8b1  mov     r8d, 1; cHandles
0x18001f8b7  or      edx, 0FFFFFFFFh; dwTimeout
0x18001f8ba  lea     ecx, [r8+7]; dwFlags
0x18001f8be  call    cs:__imp_CoWaitForMultipleHandles
0x18001f8c4  mov     [rbp+arg_8], eax
0x18001f8c7  test    eax, eax
0x18001f8c9  jns     loc_18001F951
0x18001f8cf  mov     [rbp+arg_0], 0
0x18001f8d7  test    bl, bl
0x18001f8d9  jnz     loc_18001F969
0x18001f8df  cmp     [rbp+arg_8], 0
0x18001f8e3  jl      short loc_18001F8F3
0x18001f8e5  mov     rax, [rbp+arg_18]
0x18001f8e9  cmp     dword ptr [rax+30h], 1
0x18001f8ed  jnz     loc_18001F9AB
0x18001f8f3  mov     rcx, [rbp+arg_0]
0x18001f8f7  test    rcx, rcx
0x18001f8fa  jz      short loc_18001F911
0x18001f8fc  mov     [rbp+arg_0], 0
0x18001f904  mov     rax, [rcx]
0x18001f907  mov     rax, [rax+10h]
0x18001f90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f910  nop
0x18001f911  mov     ebx, [rbp+arg_8]
0x18001f914  mov     rcx, [rbp+arg_18]
0x18001f918  test    rcx, rcx
0x18001f91b  jz      short loc_18001F932
0x18001f91d  mov     [rbp+arg_18], 0
0x18001f925  mov     rax, [rcx]
0x18001f928  mov     rax, [rax+10h]
0x18001f92c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f931  nop
0x18001f932  test    rdi, rdi
0x18001f935  jz      short loc_18001F947
0x18001f937  mov     rcx, [rdi]
0x18001f93a  mov     rax, [rcx+10h]
0x18001f93e  mov     rcx, rdi
0x18001f941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f946  nop
0x18001f947  mov     eax, ebx
0x18001f949  add     rsp, 50h
0x18001f94d  pop     rdi
0x18001f94e  pop     rbx
0x18001f94f  pop     rbp
0x18001f950  retn
0x18001f951  cmp     dword ptr [rbp+dwindex], 0
0x18001f955  jz      loc_18001F8CF
0x18001f95b  mov     [rbp+arg_8], 800704C7h
0x18001f962  mov     bl, 1
0x18001f964  jmp     loc_18001F8CF
0x18001f969  mov     rax, [rdi]
0x18001f96c  mov     rbx, [rax]
0x18001f96f  lea     rcx, [rbp+arg_0]
0x18001f973  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f978  lea     r8, [rbp+arg_0]
0x18001f97c  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18001f983  mov     rcx, rdi
0x18001f986  mov     rax, rbx
0x18001f989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f98e  test    eax, eax
0x18001f990  js      loc_18001F8DF
0x18001f996  mov     rcx, [rbp+arg_0]
0x18001f99a  mov     rax, [rcx]
0x18001f99d  mov     rax, [rax+48h]
0x18001f9a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9a6  jmp     loc_18001F8DF
0x18001f9ab  cmp     [rbp+arg_0], 0
0x18001f9b0  jnz     short loc_18001F9DF
0x18001f9b2  mov     rax, [rdi]
0x18001f9b5  mov     rbx, [rax]
0x18001f9b8  lea     rcx, [rbp+arg_0]
0x18001f9bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f9c1  lea     r8, [rbp+arg_0]
0x18001f9c5  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18001f9cc  mov     rcx, rdi
0x18001f9cf  mov     rax, rbx
0x18001f9d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9d7  test    eax, eax
0x18001f9d9  js      loc_18001F8F3
0x18001f9df  mov     rcx, [rbp+arg_0]
0x18001f9e3  mov     rax, [rcx]
0x18001f9e6  lea     rdx, [rbp+arg_8]
0x18001f9ea  mov     rax, [rax+40h]
0x18001f9ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9f3  jmp     loc_18001F8F3
```
