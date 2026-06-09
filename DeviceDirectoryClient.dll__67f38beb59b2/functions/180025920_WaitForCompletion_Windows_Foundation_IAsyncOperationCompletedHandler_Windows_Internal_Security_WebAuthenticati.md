# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180025920`
- end: `0x180025ab5`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `405`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026474`

## callees

- `0x180004060`
- `0x180025584`
- `0x180025920`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800259ca`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800259ca`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(
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
  v4 = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVUserHostIdentity_WebAuthentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVUserHostIdentity_WebAuthentication_Security_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVUserHostIdentity_WebAuthentication_Security_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVUserHostIdentity_WebAuthentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVUserHostIdentity_WebAuthentication_Security_Internal_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVUserHostIdentity_WebAuthentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVUserHostIdentity_WebAuthentication_Security_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVUserHostIdentity_WebAuthentication_Security_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&v13);
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
0x180025920  mov     [rsp-18h+dwindex], r8
0x180025925  mov     [rsp-18h+arg_8], edx
0x180025929  push    rbp
0x18002592a  push    rbx
0x18002592b  push    rdi
0x18002592c  mov     rbp, rsp
0x18002592f  sub     rsp, 50h
0x180025933  mov     rdi, rcx
0x180025936  mov     [rbp+var_20], rcx
0x18002593a  test    rcx, rcx
0x18002593d  jz      short loc_18002594C
0x18002593f  mov     rax, [rcx]
0x180025942  mov     rax, [rax+8]
0x180025946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002594b  nop
0x18002594c  mov     [rbp+arg_18], 0
0x180025954  lea     rcx, [rbp+arg_18]
0x180025958  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002595d  lea     rcx, [rbp+arg_18]
0x180025961  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x180025966  mov     ebx, eax
0x180025968  mov     [rbp+arg_8], eax
0x18002596b  test    eax, eax
0x18002596d  js      loc_180025A8C
0x180025973  mov     rax, [rdi]
0x180025976  mov     rdx, [rbp+arg_18]
0x18002597a  mov     rcx, rdi
0x18002597d  mov     rax, [rax+30h]
0x180025981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025986  mov     ebx, eax
0x180025988  mov     [rbp+arg_8], eax
0x18002598b  test    eax, eax
0x18002598d  js      loc_180025A8C
0x180025993  mov     rax, [rbp+arg_18]
0x180025997  mov     rcx, [rax+38h]
0x18002599b  mov     [rbp+pHandles], rcx
0x18002599f  mov     [rbp+var_10], 0
0x1800259a7  xor     bl, bl
0x1800259a9  mov     dword ptr [rbp+dwindex], 0
0x1800259b0  lea     rax, [rbp+dwindex]
0x1800259b4  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x1800259b9  lea     r9, [rbp+pHandles]; pHandles
0x1800259bd  mov     r8d, 1; cHandles
0x1800259c3  or      edx, 0FFFFFFFFh; dwTimeout
0x1800259c6  lea     ecx, [r8+7]; dwFlags
0x1800259ca  call    cs:__imp_CoWaitForMultipleHandles
0x1800259d0  mov     [rbp+arg_8], eax
0x1800259d3  test    eax, eax
0x1800259d5  js      short loc_1800259E6
0x1800259d7  cmp     dword ptr [rbp+dwindex], 0
0x1800259db  jz      short loc_1800259E6
0x1800259dd  mov     [rbp+arg_8], 800704C7h
0x1800259e4  mov     bl, 1
0x1800259e6  mov     [rbp+arg_0], 0
0x1800259ee  test    bl, bl
0x1800259f0  jz      short loc_180025A2B
0x1800259f2  mov     rax, [rdi]
0x1800259f5  mov     rbx, [rax]
0x1800259f8  lea     rcx, [rbp+arg_0]
0x1800259fc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025a01  lea     r8, [rbp+arg_0]
0x180025a05  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180025a0c  mov     rcx, rdi
0x180025a0f  mov     rax, rbx
0x180025a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a17  test    eax, eax
0x180025a19  js      short loc_180025A2B
0x180025a1b  mov     rcx, [rbp+arg_0]
0x180025a1f  mov     rax, [rcx]
0x180025a22  mov     rax, [rax+48h]
0x180025a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a2b  cmp     [rbp+arg_8], 0
0x180025a2f  jl      short loc_180025A80
0x180025a31  mov     rax, [rbp+arg_18]
0x180025a35  cmp     dword ptr [rax+30h], 1
0x180025a39  jz      short loc_180025A80
0x180025a3b  cmp     [rbp+arg_0], 0
0x180025a40  jnz     short loc_180025A6B
0x180025a42  mov     rax, [rdi]
0x180025a45  mov     rbx, [rax]
0x180025a48  lea     rcx, [rbp+arg_0]
0x180025a4c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025a51  lea     r8, [rbp+arg_0]
0x180025a55  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180025a5c  mov     rcx, rdi
0x180025a5f  mov     rax, rbx
0x180025a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a67  test    eax, eax
0x180025a69  js      short loc_180025A80
0x180025a6b  mov     rcx, [rbp+arg_0]
0x180025a6f  mov     rax, [rcx]
0x180025a72  lea     rdx, [rbp+arg_8]
0x180025a76  mov     rax, [rax+40h]
0x180025a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a7f  nop
0x180025a80  lea     rcx, [rbp+arg_0]
0x180025a84  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025a89  mov     ebx, [rbp+arg_8]
0x180025a8c  lea     rcx, [rbp+arg_18]
0x180025a90  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025a95  nop
0x180025a96  test    rdi, rdi
0x180025a99  jz      short loc_180025AAB
0x180025a9b  mov     rcx, [rdi]
0x180025a9e  mov     rax, [rcx+10h]
0x180025aa2  mov     rcx, rdi
0x180025aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025aaa  nop
0x180025aab  mov     eax, ebx
0x180025aad  add     rsp, 50h
0x180025ab1  pop     rdi
0x180025ab2  pop     rbx
0x180025ab3  pop     rbp
0x180025ab4  retn
```
