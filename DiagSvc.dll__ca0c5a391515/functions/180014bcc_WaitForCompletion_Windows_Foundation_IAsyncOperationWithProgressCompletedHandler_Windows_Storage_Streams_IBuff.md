# WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180014bcc`
- end: `0x180014d55`
- name: `??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `393`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a01c`

## callees

- `0x18000517c`
- `0x1800144e8`
- `0x180014bcc`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180014c76`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180014c76`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,unsigned int>>(
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
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v14);
  v4 = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUIBuffer_Streams_Storage_Windows__I_Foundation_Windows__U__IAsyncOperationWithProgress_PEAUIBuffer_Streams_Storage_Windows__I_23___YAJPEAU__IAsyncOperationWithProgress_PEAUIBuffer_Streams_Storage_Windows__I_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUIBuffer_Streams_Storage_Windows__I_Foundation_Windows__U__IAsyncOperationWithProgress_PEAUIBuffer_Streams_Storage_Windows__I_23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUIBuffer_Streams_Storage_Windows__I_Foundation_Windows__U__IAsyncOperationWithProgress_PEAUIBuffer_Streams_Storage_Windows__I_23___YAJPEAU__IAsyncOperationWithProgress_PEAUIBuffer_Streams_Storage_Windows__I_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&v14);
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
        Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v11);
        if ( v6(a1, &GUID_00000036_0000_0000_c000_000000000046, &v11) >= 0 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 72LL))(v11);
      }
      if ( v12 >= 0 && *(_DWORD *)(v14 + 48) != 1 )
      {
        if ( v11
          || (v7 = **a1,
              Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v11),
              v7(a1, &GUID_00000036_0000_0000_c000_000000000046, &v11) >= 0) )
        {
          (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v11 + 64LL))(v11, &v12);
        }
      }
      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v11);
      v4 = v12;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v14);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180014bcc  mov     [rsp-18h+dwindex], r8
0x180014bd1  mov     [rsp-18h+arg_8], edx
0x180014bd5  push    rbp
0x180014bd6  push    rbx
0x180014bd7  push    rdi
0x180014bd8  mov     rbp, rsp
0x180014bdb  sub     rsp, 50h
0x180014bdf  mov     rdi, rcx
0x180014be2  mov     [rbp+var_20], rcx
0x180014be6  test    rcx, rcx
0x180014be9  jz      short loc_180014BF8
0x180014beb  mov     rax, [rcx]
0x180014bee  mov     rax, [rax+8]
0x180014bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bf7  nop
0x180014bf8  mov     [rbp+arg_18], 0
0x180014c00  lea     rcx, [rbp+arg_18]
0x180014c04  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014c09  lea     rcx, [rbp+arg_18]
0x180014c0d  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x180014c12  mov     ebx, eax
0x180014c14  mov     [rbp+arg_8], eax
0x180014c17  test    eax, eax
0x180014c19  js      loc_180014D38
0x180014c1f  mov     rax, [rdi]
0x180014c22  mov     rdx, [rbp+arg_18]
0x180014c26  mov     rcx, rdi
0x180014c29  mov     rax, [rax+40h]
0x180014c2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c32  mov     ebx, eax
0x180014c34  mov     [rbp+arg_8], eax
0x180014c37  test    eax, eax
0x180014c39  js      loc_180014D38
0x180014c3f  mov     rax, [rbp+arg_18]
0x180014c43  mov     rcx, [rax+38h]
0x180014c47  mov     [rbp+pHandles], rcx
0x180014c4b  mov     [rbp+var_10], 0
0x180014c53  xor     bl, bl
0x180014c55  mov     dword ptr [rbp+dwindex], 0
0x180014c5c  lea     rax, [rbp+dwindex]
0x180014c60  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180014c65  lea     r9, [rbp+pHandles]; pHandles
0x180014c69  mov     r8d, 1; cHandles
0x180014c6f  or      edx, 0FFFFFFFFh; dwTimeout
0x180014c72  lea     ecx, [r8+7]; dwFlags
0x180014c76  call    cs:__imp_CoWaitForMultipleHandles
0x180014c7c  mov     [rbp+arg_8], eax
0x180014c7f  test    eax, eax
0x180014c81  js      short loc_180014C92
0x180014c83  cmp     dword ptr [rbp+dwindex], 0
0x180014c87  jz      short loc_180014C92
0x180014c89  mov     [rbp+arg_8], 800704C7h
0x180014c90  mov     bl, 1
0x180014c92  mov     [rbp+arg_0], 0
0x180014c9a  test    bl, bl
0x180014c9c  jz      short loc_180014CD7
0x180014c9e  mov     rax, [rdi]
0x180014ca1  mov     rbx, [rax]
0x180014ca4  lea     rcx, [rbp+arg_0]
0x180014ca8  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014cad  lea     r8, [rbp+arg_0]
0x180014cb1  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180014cb8  mov     rcx, rdi
0x180014cbb  mov     rax, rbx
0x180014cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cc3  test    eax, eax
0x180014cc5  js      short loc_180014CD7
0x180014cc7  mov     rcx, [rbp+arg_0]
0x180014ccb  mov     rax, [rcx]
0x180014cce  mov     rax, [rax+48h]
0x180014cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cd7  cmp     [rbp+arg_8], 0
0x180014cdb  jl      short loc_180014D2C
0x180014cdd  mov     rax, [rbp+arg_18]
0x180014ce1  cmp     dword ptr [rax+30h], 1
0x180014ce5  jz      short loc_180014D2C
0x180014ce7  cmp     [rbp+arg_0], 0
0x180014cec  jnz     short loc_180014D17
0x180014cee  mov     rax, [rdi]
0x180014cf1  mov     rbx, [rax]
0x180014cf4  lea     rcx, [rbp+arg_0]
0x180014cf8  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014cfd  lea     r8, [rbp+arg_0]
0x180014d01  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180014d08  mov     rcx, rdi
0x180014d0b  mov     rax, rbx
0x180014d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d13  test    eax, eax
0x180014d15  js      short loc_180014D2C
0x180014d17  mov     rcx, [rbp+arg_0]
0x180014d1b  mov     rax, [rcx]
0x180014d1e  lea     rdx, [rbp+arg_8]
0x180014d22  mov     rax, [rax+40h]
0x180014d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d2b  nop
0x180014d2c  lea     rcx, [rbp+arg_0]
0x180014d30  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014d35  mov     ebx, [rbp+arg_8]
0x180014d38  lea     rcx, [rbp+arg_18]
0x180014d3c  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014d41  nop
0x180014d42  lea     rcx, [rbp+var_20]
0x180014d46  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014d4b  mov     eax, ebx
0x180014d4d  add     rsp, 50h
0x180014d51  pop     rdi
0x180014d52  pop     rbx
0x180014d53  pop     rbp
0x180014d54  retn
```
