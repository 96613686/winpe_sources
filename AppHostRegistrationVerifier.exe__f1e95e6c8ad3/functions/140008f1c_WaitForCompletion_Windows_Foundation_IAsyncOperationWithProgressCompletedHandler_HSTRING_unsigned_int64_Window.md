# WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)

- ea: `0x140008f1c`
- end: `0x1400090a5`
- name: `??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `393`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000c848`

## callees

- `0x140008850`
- `0x140008f1c`
- `0x14000d49c`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140008fc6`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140008fc6`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(
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
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v14);
  v4 = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUHSTRING_____K_Foundation_Windows__U__IAsyncOperationWithProgress_PEAUHSTRING_____K_23___YAJPEAU__IAsyncOperationWithProgress_PEAUHSTRING_____K_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUHSTRING_____K_Foundation_Windows__U__IAsyncOperationWithProgress_PEAUHSTRING_____K_23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUHSTRING_____K_Foundation_Windows__U__IAsyncOperationWithProgress_PEAUHSTRING_____K_23___YAJPEAU__IAsyncOperationWithProgress_PEAUHSTRING_____K_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&v14);
  v12 = v4;
  if ( v4 >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[8])(a1, v14);
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
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v11);
        if ( v6(a1, &GUID_00000036_0000_0000_c000_000000000046, &v11) >= 0 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 72LL))(v11);
      }
      if ( v12 >= 0 && *(_DWORD *)(v14 + 48) != 1 )
      {
        if ( v11
          || (v7 = **a1,
              Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v11),
              v7(a1, &GUID_00000036_0000_0000_c000_000000000046, &v11) >= 0) )
        {
          (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v11 + 64LL))(v11, &v12);
        }
      }
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v11);
      v4 = v12;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v14);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140008f1c  mov     [rsp-18h+dwindex], r8
0x140008f21  mov     [rsp-18h+arg_8], edx
0x140008f25  push    rbp
0x140008f26  push    rbx
0x140008f27  push    rdi
0x140008f28  mov     rbp, rsp
0x140008f2b  sub     rsp, 50h
0x140008f2f  mov     rdi, rcx
0x140008f32  mov     [rbp+var_20], rcx
0x140008f36  test    rcx, rcx
0x140008f39  jz      short loc_140008F48
0x140008f3b  mov     rax, [rcx]
0x140008f3e  mov     rax, [rax+8]
0x140008f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f47  nop
0x140008f48  mov     [rbp+arg_18], 0
0x140008f50  lea     rcx, [rbp+arg_18]
0x140008f54  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x140008f59  lea     rcx, [rbp+arg_18]
0x140008f5d  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x140008f62  mov     ebx, eax
0x140008f64  mov     [rbp+arg_8], eax
0x140008f67  test    eax, eax
0x140008f69  js      loc_140009088
0x140008f6f  mov     rax, [rdi]
0x140008f72  mov     rdx, [rbp+arg_18]
0x140008f76  mov     rcx, rdi
0x140008f79  mov     rax, [rax+40h]
0x140008f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f82  mov     ebx, eax
0x140008f84  mov     [rbp+arg_8], eax
0x140008f87  test    eax, eax
0x140008f89  js      loc_140009088
0x140008f8f  mov     rax, [rbp+arg_18]
0x140008f93  mov     rcx, [rax+38h]
0x140008f97  mov     [rbp+pHandles], rcx
0x140008f9b  mov     [rbp+var_10], 0
0x140008fa3  xor     bl, bl
0x140008fa5  mov     dword ptr [rbp+dwindex], 0
0x140008fac  lea     rax, [rbp+dwindex]
0x140008fb0  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x140008fb5  lea     r9, [rbp+pHandles]; pHandles
0x140008fb9  mov     r8d, 1; cHandles
0x140008fbf  or      edx, 0FFFFFFFFh; dwTimeout
0x140008fc2  lea     ecx, [r8+7]; dwFlags
0x140008fc6  call    cs:__imp_CoWaitForMultipleHandles
0x140008fcc  mov     [rbp+arg_8], eax
0x140008fcf  test    eax, eax
0x140008fd1  js      short loc_140008FE2
0x140008fd3  cmp     dword ptr [rbp+dwindex], 0
0x140008fd7  jz      short loc_140008FE2
0x140008fd9  mov     [rbp+arg_8], 800704C7h
0x140008fe0  mov     bl, 1
0x140008fe2  mov     [rbp+arg_0], 0
0x140008fea  test    bl, bl
0x140008fec  jz      short loc_140009027
0x140008fee  mov     rax, [rdi]
0x140008ff1  mov     rbx, [rax]
0x140008ff4  lea     rcx, [rbp+arg_0]
0x140008ff8  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x140008ffd  lea     r8, [rbp+arg_0]
0x140009001  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x140009008  mov     rcx, rdi
0x14000900b  mov     rax, rbx
0x14000900e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009013  test    eax, eax
0x140009015  js      short loc_140009027
0x140009017  mov     rcx, [rbp+arg_0]
0x14000901b  mov     rax, [rcx]
0x14000901e  mov     rax, [rax+48h]
0x140009022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009027  cmp     [rbp+arg_8], 0
0x14000902b  jl      short loc_14000907C
0x14000902d  mov     rax, [rbp+arg_18]
0x140009031  cmp     dword ptr [rax+30h], 1
0x140009035  jz      short loc_14000907C
0x140009037  cmp     [rbp+arg_0], 0
0x14000903c  jnz     short loc_140009067
0x14000903e  mov     rax, [rdi]
0x140009041  mov     rbx, [rax]
0x140009044  lea     rcx, [rbp+arg_0]
0x140009048  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000904d  lea     r8, [rbp+arg_0]
0x140009051  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x140009058  mov     rcx, rdi
0x14000905b  mov     rax, rbx
0x14000905e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009063  test    eax, eax
0x140009065  js      short loc_14000907C
0x140009067  mov     rcx, [rbp+arg_0]
0x14000906b  mov     rax, [rcx]
0x14000906e  lea     rdx, [rbp+arg_8]
0x140009072  mov     rax, [rax+40h]
0x140009076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000907b  nop
0x14000907c  lea     rcx, [rbp+arg_0]
0x140009080  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x140009085  mov     ebx, [rbp+arg_8]
0x140009088  lea     rcx, [rbp+arg_18]
0x14000908c  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x140009091  nop
0x140009092  lea     rcx, [rbp+var_20]
0x140009096  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000909b  mov     eax, ebx
0x14000909d  add     rsp, 50h
0x1400090a1  pop     rdi
0x1400090a2  pop     rbx
0x1400090a3  pop     rbp
0x1400090a4  retn
```
