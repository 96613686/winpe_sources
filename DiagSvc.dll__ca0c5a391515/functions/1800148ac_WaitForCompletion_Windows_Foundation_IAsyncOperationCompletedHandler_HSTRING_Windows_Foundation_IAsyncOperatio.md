# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x1800148ac`
- end: `0x180014a35`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `393`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016d70`

## callees

- `0x18000517c`
- `0x180014268`
- `0x1800148ac`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180014956`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180014956`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(
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
  v4 = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUHSTRING_____Foundation_Windows__U__IAsyncOperation_PEAUHSTRING_____23___YAJPEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUHSTRING_____Foundation_Windows__U__IAsyncOperation_PEAUHSTRING_____23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUHSTRING_____Foundation_Windows__U__IAsyncOperation_PEAUHSTRING_____23___YAJPEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&v14);
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
0x1800148ac  mov     [rsp-18h+dwindex], r8
0x1800148b1  mov     [rsp-18h+arg_8], edx
0x1800148b5  push    rbp
0x1800148b6  push    rbx
0x1800148b7  push    rdi
0x1800148b8  mov     rbp, rsp
0x1800148bb  sub     rsp, 50h
0x1800148bf  mov     rdi, rcx
0x1800148c2  mov     [rbp+var_20], rcx
0x1800148c6  test    rcx, rcx
0x1800148c9  jz      short loc_1800148D8
0x1800148cb  mov     rax, [rcx]
0x1800148ce  mov     rax, [rax+8]
0x1800148d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148d7  nop
0x1800148d8  mov     [rbp+arg_18], 0
0x1800148e0  lea     rcx, [rbp+arg_18]
0x1800148e4  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x1800148e9  lea     rcx, [rbp+arg_18]
0x1800148ed  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x1800148f2  mov     ebx, eax
0x1800148f4  mov     [rbp+arg_8], eax
0x1800148f7  test    eax, eax
0x1800148f9  js      loc_180014A18
0x1800148ff  mov     rax, [rdi]
0x180014902  mov     rdx, [rbp+arg_18]
0x180014906  mov     rcx, rdi
0x180014909  mov     rax, [rax+30h]
0x18001490d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014912  mov     ebx, eax
0x180014914  mov     [rbp+arg_8], eax
0x180014917  test    eax, eax
0x180014919  js      loc_180014A18
0x18001491f  mov     rax, [rbp+arg_18]
0x180014923  mov     rcx, [rax+38h]
0x180014927  mov     [rbp+pHandles], rcx
0x18001492b  mov     [rbp+var_10], 0
0x180014933  xor     bl, bl
0x180014935  mov     dword ptr [rbp+dwindex], 0
0x18001493c  lea     rax, [rbp+dwindex]
0x180014940  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180014945  lea     r9, [rbp+pHandles]; pHandles
0x180014949  mov     r8d, 1; cHandles
0x18001494f  or      edx, 0FFFFFFFFh; dwTimeout
0x180014952  lea     ecx, [r8+7]; dwFlags
0x180014956  call    cs:__imp_CoWaitForMultipleHandles
0x18001495c  mov     [rbp+arg_8], eax
0x18001495f  test    eax, eax
0x180014961  js      short loc_180014972
0x180014963  cmp     dword ptr [rbp+dwindex], 0
0x180014967  jz      short loc_180014972
0x180014969  mov     [rbp+arg_8], 800704C7h
0x180014970  mov     bl, 1
0x180014972  mov     [rbp+arg_0], 0
0x18001497a  test    bl, bl
0x18001497c  jz      short loc_1800149B7
0x18001497e  mov     rax, [rdi]
0x180014981  mov     rbx, [rax]
0x180014984  lea     rcx, [rbp+arg_0]
0x180014988  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001498d  lea     r8, [rbp+arg_0]
0x180014991  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180014998  mov     rcx, rdi
0x18001499b  mov     rax, rbx
0x18001499e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149a3  test    eax, eax
0x1800149a5  js      short loc_1800149B7
0x1800149a7  mov     rcx, [rbp+arg_0]
0x1800149ab  mov     rax, [rcx]
0x1800149ae  mov     rax, [rax+48h]
0x1800149b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149b7  cmp     [rbp+arg_8], 0
0x1800149bb  jl      short loc_180014A0C
0x1800149bd  mov     rax, [rbp+arg_18]
0x1800149c1  cmp     dword ptr [rax+30h], 1
0x1800149c5  jz      short loc_180014A0C
0x1800149c7  cmp     [rbp+arg_0], 0
0x1800149cc  jnz     short loc_1800149F7
0x1800149ce  mov     rax, [rdi]
0x1800149d1  mov     rbx, [rax]
0x1800149d4  lea     rcx, [rbp+arg_0]
0x1800149d8  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x1800149dd  lea     r8, [rbp+arg_0]
0x1800149e1  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800149e8  mov     rcx, rdi
0x1800149eb  mov     rax, rbx
0x1800149ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149f3  test    eax, eax
0x1800149f5  js      short loc_180014A0C
0x1800149f7  mov     rcx, [rbp+arg_0]
0x1800149fb  mov     rax, [rcx]
0x1800149fe  lea     rdx, [rbp+arg_8]
0x180014a02  mov     rax, [rax+40h]
0x180014a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a0b  nop
0x180014a0c  lea     rcx, [rbp+arg_0]
0x180014a10  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014a15  mov     ebx, [rbp+arg_8]
0x180014a18  lea     rcx, [rbp+arg_18]
0x180014a1c  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014a21  nop
0x180014a22  lea     rcx, [rbp+var_20]
0x180014a26  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014a2b  mov     eax, ebx
0x180014a2d  add     rsp, 50h
0x180014a31  pop     rdi
0x180014a32  pop     rbx
0x180014a33  pop     rbp
0x180014a34  retn
```
