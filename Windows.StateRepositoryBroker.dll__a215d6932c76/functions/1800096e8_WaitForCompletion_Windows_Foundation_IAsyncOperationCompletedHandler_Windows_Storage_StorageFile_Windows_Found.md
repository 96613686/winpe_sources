# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x1800096e8`
- end: `0x18000986d`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `389`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009af8`

## callees

- `0x1800071a4`
- `0x180009474`
- `0x1800096e8`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000978f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000978f`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        int a2,
        __int64 a3)
{
  unsigned int v4; // edi
  __int64 v5; // rbx
  int (__fastcall **v6)(_QWORD, GUID *, __int64 *); // rax
  int (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rdi
  int (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rbx
  int (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // [rsp+30h] [rbp-28h] BYREF
  HANDLE pHandles[4]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v12; // [rsp+80h] [rbp+28h] BYREF
  int v13; // [rsp+88h] [rbp+30h] BYREF
  __int64 dwindex; // [rsp+90h] [rbp+38h] BYREF
  __int64 v15; // [rsp+98h] [rbp+40h] BYREF

  dwindex = a3;
  v13 = a2;
  v10 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a1;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v15 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v15);
  v13 = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVStorageFile_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAVStorageFile_Storage_Windows___23___YAJPEAU__IAsyncOperation_PEAVStorageFile_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVStorageFile_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAVStorageFile_Storage_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVStorageFile_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAVStorageFile_Storage_Windows___23___YAJPEAU__IAsyncOperation_PEAVStorageFile_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&v15);
  v4 = v13;
  if ( v13 >= 0 )
  {
    v5 = v15;
    v13 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[6])(a1, v15);
    v4 = v13;
    if ( v13 >= 0 )
    {
      pHandles[0] = *(HANDLE *)(v5 + 56);
      pHandles[1] = 0;
      LODWORD(dwindex) = 0;
      v13 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex);
      if ( v13 >= 0 && (_DWORD)dwindex )
      {
        v6 = *a1;
        v13 = -2147023673;
        v12 = 0;
        v7 = *v6;
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v12);
        if ( v7(a1, &GUID_00000036_0000_0000_c000_000000000046, &v12) >= 0 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 72LL))(v12);
      }
      else
      {
        v12 = 0;
      }
      if ( v13 >= 0 && *(_DWORD *)(v5 + 48) != 1 )
      {
        if ( v12
          || (v8 = **a1,
              Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v12),
              v8(a1, &GUID_00000036_0000_0000_c000_000000000046, &v12) >= 0) )
        {
          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 64LL))(v12, &v13);
        }
      }
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v12);
      v4 = v13;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v10);
  return v4;
}

```

## disassembly

```asm
0x1800096e8  mov     [rsp-20h+dwindex], r8
0x1800096ed  mov     [rsp-20h+arg_8], edx
0x1800096f1  push    rbp
0x1800096f2  push    rbx
0x1800096f3  push    rsi
0x1800096f4  push    rdi
0x1800096f5  mov     rbp, rsp
0x1800096f8  sub     rsp, 58h
0x1800096fc  mov     [rbp+var_28], rcx
0x180009700  mov     rsi, rcx
0x180009703  test    rcx, rcx
0x180009706  jz      short loc_180009714
0x180009708  mov     rax, [rcx]
0x18000970b  mov     rax, [rax+8]
0x18000970f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009714  lea     rcx, [rbp+arg_18]
0x180009718  mov     [rbp+arg_18], 0
0x180009720  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180009725  lea     rcx, [rbp+arg_18]
0x180009729  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x18000972e  mov     [rbp+arg_8], eax
0x180009731  mov     edi, eax
0x180009733  test    eax, eax
0x180009735  js      loc_180009850
0x18000973b  mov     rax, [rsi]
0x18000973e  mov     rcx, rsi
0x180009741  mov     rbx, [rbp+arg_18]
0x180009745  mov     rdx, rbx
0x180009748  mov     rax, [rax+30h]
0x18000974c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009751  mov     [rbp+arg_8], eax
0x180009754  mov     edi, eax
0x180009756  test    eax, eax
0x180009758  js      loc_180009850
0x18000975e  mov     rax, [rbx+38h]
0x180009762  lea     r9, [rbp+pHandles]; pHandles
0x180009766  mov     r8d, 1; cHandles
0x18000976c  mov     [rbp+pHandles], rax
0x180009770  lea     rax, [rbp+dwindex]
0x180009774  mov     [rbp+var_18], 0
0x18000977c  or      edx, 0FFFFFFFFh; dwTimeout
0x18000977f  mov     dword ptr [rbp+dwindex], 0
0x180009786  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x18000978b  lea     ecx, [r8+7]; dwFlags
0x18000978f  call    cs:__imp_CoWaitForMultipleHandles
0x180009795  mov     [rbp+arg_8], eax
0x180009798  test    eax, eax
0x18000979a  js      short loc_1800097EC
0x18000979c  cmp     dword ptr [rbp+dwindex], 0
0x1800097a0  jz      short loc_1800097EC
0x1800097a2  mov     rax, [rsi]
0x1800097a5  lea     rcx, [rbp+arg_0]
0x1800097a9  mov     [rbp+arg_8], 800704C7h
0x1800097b0  mov     [rbp+arg_0], 0
0x1800097b8  mov     rdi, [rax]
0x1800097bb  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x1800097c0  lea     r8, [rbp+arg_0]
0x1800097c4  mov     rcx, rsi
0x1800097c7  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800097ce  mov     rax, rdi
0x1800097d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097d6  test    eax, eax
0x1800097d8  js      short loc_1800097F4
0x1800097da  mov     rcx, [rbp+arg_0]
0x1800097de  mov     rax, [rcx]
0x1800097e1  mov     rax, [rax+48h]
0x1800097e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097ea  jmp     short loc_1800097F4
0x1800097ec  mov     [rbp+arg_0], 0
0x1800097f4  cmp     [rbp+arg_8], 0
0x1800097f8  jl      short loc_180009844
0x1800097fa  cmp     dword ptr [rbx+30h], 1
0x1800097fe  jz      short loc_180009844
0x180009800  cmp     [rbp+arg_0], 0
0x180009805  jnz     short loc_180009830
0x180009807  mov     rax, [rsi]
0x18000980a  lea     rcx, [rbp+arg_0]
0x18000980e  mov     rbx, [rax]
0x180009811  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180009816  lea     r8, [rbp+arg_0]
0x18000981a  mov     rcx, rsi
0x18000981d  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180009824  mov     rax, rbx
0x180009827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000982c  test    eax, eax
0x18000982e  js      short loc_180009844
0x180009830  mov     rcx, [rbp+arg_0]
0x180009834  lea     rdx, [rbp+arg_8]
0x180009838  mov     rax, [rcx]
0x18000983b  mov     rax, [rax+40h]
0x18000983f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009844  lea     rcx, [rbp+arg_0]
0x180009848  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x18000984d  mov     edi, [rbp+arg_8]
0x180009850  lea     rcx, [rbp+arg_18]
0x180009854  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180009859  lea     rcx, [rbp+var_28]
0x18000985d  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180009862  mov     eax, edi
0x180009864  add     rsp, 58h
0x180009868  pop     rdi
0x180009869  pop     rsi
0x18000986a  pop     rbx
0x18000986b  pop     rbp
0x18000986c  retn
```
