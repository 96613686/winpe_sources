# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x18000e840`
- end: `0x18000e9c9`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `393`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800116b4`

## callees

- `0x18000dd98`
- `0x18000e840`
- `0x180013ae4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000e8ea`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000e8ea`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(
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
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v14);
  v4 = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&v14);
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
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v11);
        if ( v6(a1, &GUID_00000036_0000_0000_c000_000000000046, &v11) >= 0 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 72LL))(v11);
      }
      if ( v12 >= 0 && *(_DWORD *)(v14 + 48) != 1 )
      {
        if ( v11
          || (v7 = **a1,
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v11),
              v7(a1, &GUID_00000036_0000_0000_c000_000000000046, &v11) >= 0) )
        {
          (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v11 + 64LL))(v11, &v12);
        }
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v11);
      v4 = v12;
    }
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v14);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000e840  mov     [rsp-18h+dwindex], r8
0x18000e845  mov     [rsp-18h+arg_8], edx
0x18000e849  push    rbp
0x18000e84a  push    rbx
0x18000e84b  push    rdi
0x18000e84c  mov     rbp, rsp
0x18000e84f  sub     rsp, 50h
0x18000e853  mov     rdi, rcx
0x18000e856  mov     [rbp+var_20], rcx
0x18000e85a  test    rcx, rcx
0x18000e85d  jz      short loc_18000E86C
0x18000e85f  mov     rax, [rcx]
0x18000e862  mov     rax, [rax+8]
0x18000e866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e86b  nop
0x18000e86c  mov     [rbp+arg_18], 0
0x18000e874  lea     rcx, [rbp+arg_18]
0x18000e878  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000e87d  lea     rcx, [rbp+arg_18]
0x18000e881  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x18000e886  mov     ebx, eax
0x18000e888  mov     [rbp+arg_8], eax
0x18000e88b  test    eax, eax
0x18000e88d  js      loc_18000E9AC
0x18000e893  mov     rax, [rdi]
0x18000e896  mov     rdx, [rbp+arg_18]
0x18000e89a  mov     rcx, rdi
0x18000e89d  mov     rax, [rax+30h]
0x18000e8a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8a6  mov     ebx, eax
0x18000e8a8  mov     [rbp+arg_8], eax
0x18000e8ab  test    eax, eax
0x18000e8ad  js      loc_18000E9AC
0x18000e8b3  mov     rax, [rbp+arg_18]
0x18000e8b7  mov     rcx, [rax+38h]
0x18000e8bb  mov     [rbp+pHandles], rcx
0x18000e8bf  mov     [rbp+var_10], 0
0x18000e8c7  xor     bl, bl
0x18000e8c9  mov     dword ptr [rbp+dwindex], 0
0x18000e8d0  lea     rax, [rbp+dwindex]
0x18000e8d4  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x18000e8d9  lea     r9, [rbp+pHandles]; pHandles
0x18000e8dd  mov     r8d, 1; cHandles
0x18000e8e3  or      edx, 0FFFFFFFFh; dwTimeout
0x18000e8e6  lea     ecx, [r8+7]; dwFlags
0x18000e8ea  call    cs:__imp_CoWaitForMultipleHandles
0x18000e8f0  mov     [rbp+arg_8], eax
0x18000e8f3  test    eax, eax
0x18000e8f5  js      short loc_18000E906
0x18000e8f7  cmp     dword ptr [rbp+dwindex], 0
0x18000e8fb  jz      short loc_18000E906
0x18000e8fd  mov     [rbp+arg_8], 800704C7h
0x18000e904  mov     bl, 1
0x18000e906  mov     [rbp+arg_0], 0
0x18000e90e  test    bl, bl
0x18000e910  jz      short loc_18000E94B
0x18000e912  mov     rax, [rdi]
0x18000e915  mov     rbx, [rax]
0x18000e918  lea     rcx, [rbp+arg_0]
0x18000e91c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000e921  lea     r8, [rbp+arg_0]
0x18000e925  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000e92c  mov     rcx, rdi
0x18000e92f  mov     rax, rbx
0x18000e932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e937  test    eax, eax
0x18000e939  js      short loc_18000E94B
0x18000e93b  mov     rcx, [rbp+arg_0]
0x18000e93f  mov     rax, [rcx]
0x18000e942  mov     rax, [rax+48h]
0x18000e946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e94b  cmp     [rbp+arg_8], 0
0x18000e94f  jl      short loc_18000E9A0
0x18000e951  mov     rax, [rbp+arg_18]
0x18000e955  cmp     dword ptr [rax+30h], 1
0x18000e959  jz      short loc_18000E9A0
0x18000e95b  cmp     [rbp+arg_0], 0
0x18000e960  jnz     short loc_18000E98B
0x18000e962  mov     rax, [rdi]
0x18000e965  mov     rbx, [rax]
0x18000e968  lea     rcx, [rbp+arg_0]
0x18000e96c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000e971  lea     r8, [rbp+arg_0]
0x18000e975  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000e97c  mov     rcx, rdi
0x18000e97f  mov     rax, rbx
0x18000e982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e987  test    eax, eax
0x18000e989  js      short loc_18000E9A0
0x18000e98b  mov     rcx, [rbp+arg_0]
0x18000e98f  mov     rax, [rcx]
0x18000e992  lea     rdx, [rbp+arg_8]
0x18000e996  mov     rax, [rax+40h]
0x18000e99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e99f  nop
0x18000e9a0  lea     rcx, [rbp+arg_0]
0x18000e9a4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000e9a9  mov     ebx, [rbp+arg_8]
0x18000e9ac  lea     rcx, [rbp+arg_18]
0x18000e9b0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000e9b5  nop
0x18000e9b6  lea     rcx, [rbp+var_20]
0x18000e9ba  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000e9bf  mov     eax, ebx
0x18000e9c1  add     rsp, 50h
0x18000e9c5  pop     rdi
0x18000e9c6  pop     rbx
0x18000e9c7  pop     rbp
0x18000e9c8  retn
```
