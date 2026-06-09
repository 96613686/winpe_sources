# WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180014d5c`
- end: `0x180014ee5`
- name: `??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `393`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016d70`

## callees

- `0x18000517c`
- `0x180014628`
- `0x180014d5c`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180014e06`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180014e06`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>>(
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
  v4 = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUIInputStream_Streams_Storage_Windows__UHttpProgress_Http_Web_4__Foundation_Windows__U__IAsyncOperationWithProgress_PEAUIInputStream_Streams_Storage_Windows__UHttpProgress_Http_Web_4__23___YAJPEAU__IAsyncOperationWithProgress_PEAUIInputStream_Streams_Storage_Windows__UHttpProgress_Http_Web_4__Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUIInputStream_Streams_Storage_Windows__UHttpProgress_Http_Web_4__Foundation_Windows__U__IAsyncOperationWithProgress_PEAUIInputStream_Streams_Storage_Windows__UHttpProgress_Http_Web_4__23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUIInputStream_Streams_Storage_Windows__UHttpProgress_Http_Web_4__Foundation_Windows__U__IAsyncOperationWithProgress_PEAUIInputStream_Streams_Storage_Windows__UHttpProgress_Http_Web_4__23___YAJPEAU__IAsyncOperationWithProgress_PEAUIInputStream_Streams_Storage_Windows__UHttpProgress_Http_Web_4__Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&v14);
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
0x180014d5c  mov     [rsp-18h+dwindex], r8
0x180014d61  mov     [rsp-18h+arg_8], edx
0x180014d65  push    rbp
0x180014d66  push    rbx
0x180014d67  push    rdi
0x180014d68  mov     rbp, rsp
0x180014d6b  sub     rsp, 50h
0x180014d6f  mov     rdi, rcx
0x180014d72  mov     [rbp+var_20], rcx
0x180014d76  test    rcx, rcx
0x180014d79  jz      short loc_180014D88
0x180014d7b  mov     rax, [rcx]
0x180014d7e  mov     rax, [rax+8]
0x180014d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d87  nop
0x180014d88  mov     [rbp+arg_18], 0
0x180014d90  lea     rcx, [rbp+arg_18]
0x180014d94  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014d99  lea     rcx, [rbp+arg_18]
0x180014d9d  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x180014da2  mov     ebx, eax
0x180014da4  mov     [rbp+arg_8], eax
0x180014da7  test    eax, eax
0x180014da9  js      loc_180014EC8
0x180014daf  mov     rax, [rdi]
0x180014db2  mov     rdx, [rbp+arg_18]
0x180014db6  mov     rcx, rdi
0x180014db9  mov     rax, [rax+40h]
0x180014dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dc2  mov     ebx, eax
0x180014dc4  mov     [rbp+arg_8], eax
0x180014dc7  test    eax, eax
0x180014dc9  js      loc_180014EC8
0x180014dcf  mov     rax, [rbp+arg_18]
0x180014dd3  mov     rcx, [rax+38h]
0x180014dd7  mov     [rbp+pHandles], rcx
0x180014ddb  mov     [rbp+var_10], 0
0x180014de3  xor     bl, bl
0x180014de5  mov     dword ptr [rbp+dwindex], 0
0x180014dec  lea     rax, [rbp+dwindex]
0x180014df0  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180014df5  lea     r9, [rbp+pHandles]; pHandles
0x180014df9  mov     r8d, 1; cHandles
0x180014dff  or      edx, 0FFFFFFFFh; dwTimeout
0x180014e02  lea     ecx, [r8+7]; dwFlags
0x180014e06  call    cs:__imp_CoWaitForMultipleHandles
0x180014e0c  mov     [rbp+arg_8], eax
0x180014e0f  test    eax, eax
0x180014e11  js      short loc_180014E22
0x180014e13  cmp     dword ptr [rbp+dwindex], 0
0x180014e17  jz      short loc_180014E22
0x180014e19  mov     [rbp+arg_8], 800704C7h
0x180014e20  mov     bl, 1
0x180014e22  mov     [rbp+arg_0], 0
0x180014e2a  test    bl, bl
0x180014e2c  jz      short loc_180014E67
0x180014e2e  mov     rax, [rdi]
0x180014e31  mov     rbx, [rax]
0x180014e34  lea     rcx, [rbp+arg_0]
0x180014e38  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014e3d  lea     r8, [rbp+arg_0]
0x180014e41  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180014e48  mov     rcx, rdi
0x180014e4b  mov     rax, rbx
0x180014e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e53  test    eax, eax
0x180014e55  js      short loc_180014E67
0x180014e57  mov     rcx, [rbp+arg_0]
0x180014e5b  mov     rax, [rcx]
0x180014e5e  mov     rax, [rax+48h]
0x180014e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e67  cmp     [rbp+arg_8], 0
0x180014e6b  jl      short loc_180014EBC
0x180014e6d  mov     rax, [rbp+arg_18]
0x180014e71  cmp     dword ptr [rax+30h], 1
0x180014e75  jz      short loc_180014EBC
0x180014e77  cmp     [rbp+arg_0], 0
0x180014e7c  jnz     short loc_180014EA7
0x180014e7e  mov     rax, [rdi]
0x180014e81  mov     rbx, [rax]
0x180014e84  lea     rcx, [rbp+arg_0]
0x180014e88  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014e8d  lea     r8, [rbp+arg_0]
0x180014e91  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180014e98  mov     rcx, rdi
0x180014e9b  mov     rax, rbx
0x180014e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ea3  test    eax, eax
0x180014ea5  js      short loc_180014EBC
0x180014ea7  mov     rcx, [rbp+arg_0]
0x180014eab  mov     rax, [rcx]
0x180014eae  lea     rdx, [rbp+arg_8]
0x180014eb2  mov     rax, [rax+40h]
0x180014eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ebb  nop
0x180014ebc  lea     rcx, [rbp+arg_0]
0x180014ec0  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014ec5  mov     ebx, [rbp+arg_8]
0x180014ec8  lea     rcx, [rbp+arg_18]
0x180014ecc  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014ed1  nop
0x180014ed2  lea     rcx, [rbp+var_20]
0x180014ed6  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014edb  mov     eax, ebx
0x180014edd  add     rsp, 50h
0x180014ee1  pop     rdi
0x180014ee2  pop     rbx
0x180014ee3  pop     rbp
0x180014ee4  retn
```
