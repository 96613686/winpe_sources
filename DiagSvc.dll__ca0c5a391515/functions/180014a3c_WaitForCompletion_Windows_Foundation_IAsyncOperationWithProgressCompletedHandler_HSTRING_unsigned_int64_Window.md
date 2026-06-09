# WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180014a3c`
- end: `0x180014bc5`
- name: `??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `393`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001890c`

## callees

- `0x18000517c`
- `0x1800143a8`
- `0x180014a3c`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180014ae6`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180014ae6`

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
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v14);
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
0x180014a3c  mov     [rsp-18h+dwindex], r8
0x180014a41  mov     [rsp-18h+arg_8], edx
0x180014a45  push    rbp
0x180014a46  push    rbx
0x180014a47  push    rdi
0x180014a48  mov     rbp, rsp
0x180014a4b  sub     rsp, 50h
0x180014a4f  mov     rdi, rcx
0x180014a52  mov     [rbp+var_20], rcx
0x180014a56  test    rcx, rcx
0x180014a59  jz      short loc_180014A68
0x180014a5b  mov     rax, [rcx]
0x180014a5e  mov     rax, [rax+8]
0x180014a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a67  nop
0x180014a68  mov     [rbp+arg_18], 0
0x180014a70  lea     rcx, [rbp+arg_18]
0x180014a74  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014a79  lea     rcx, [rbp+arg_18]
0x180014a7d  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x180014a82  mov     ebx, eax
0x180014a84  mov     [rbp+arg_8], eax
0x180014a87  test    eax, eax
0x180014a89  js      loc_180014BA8
0x180014a8f  mov     rax, [rdi]
0x180014a92  mov     rdx, [rbp+arg_18]
0x180014a96  mov     rcx, rdi
0x180014a99  mov     rax, [rax+40h]
0x180014a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014aa2  mov     ebx, eax
0x180014aa4  mov     [rbp+arg_8], eax
0x180014aa7  test    eax, eax
0x180014aa9  js      loc_180014BA8
0x180014aaf  mov     rax, [rbp+arg_18]
0x180014ab3  mov     rcx, [rax+38h]
0x180014ab7  mov     [rbp+pHandles], rcx
0x180014abb  mov     [rbp+var_10], 0
0x180014ac3  xor     bl, bl
0x180014ac5  mov     dword ptr [rbp+dwindex], 0
0x180014acc  lea     rax, [rbp+dwindex]
0x180014ad0  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180014ad5  lea     r9, [rbp+pHandles]; pHandles
0x180014ad9  mov     r8d, 1; cHandles
0x180014adf  or      edx, 0FFFFFFFFh; dwTimeout
0x180014ae2  lea     ecx, [r8+7]; dwFlags
0x180014ae6  call    cs:__imp_CoWaitForMultipleHandles
0x180014aec  mov     [rbp+arg_8], eax
0x180014aef  test    eax, eax
0x180014af1  js      short loc_180014B02
0x180014af3  cmp     dword ptr [rbp+dwindex], 0
0x180014af7  jz      short loc_180014B02
0x180014af9  mov     [rbp+arg_8], 800704C7h
0x180014b00  mov     bl, 1
0x180014b02  mov     [rbp+arg_0], 0
0x180014b0a  test    bl, bl
0x180014b0c  jz      short loc_180014B47
0x180014b0e  mov     rax, [rdi]
0x180014b11  mov     rbx, [rax]
0x180014b14  lea     rcx, [rbp+arg_0]
0x180014b18  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014b1d  lea     r8, [rbp+arg_0]
0x180014b21  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180014b28  mov     rcx, rdi
0x180014b2b  mov     rax, rbx
0x180014b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b33  test    eax, eax
0x180014b35  js      short loc_180014B47
0x180014b37  mov     rcx, [rbp+arg_0]
0x180014b3b  mov     rax, [rcx]
0x180014b3e  mov     rax, [rax+48h]
0x180014b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b47  cmp     [rbp+arg_8], 0
0x180014b4b  jl      short loc_180014B9C
0x180014b4d  mov     rax, [rbp+arg_18]
0x180014b51  cmp     dword ptr [rax+30h], 1
0x180014b55  jz      short loc_180014B9C
0x180014b57  cmp     [rbp+arg_0], 0
0x180014b5c  jnz     short loc_180014B87
0x180014b5e  mov     rax, [rdi]
0x180014b61  mov     rbx, [rax]
0x180014b64  lea     rcx, [rbp+arg_0]
0x180014b68  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014b6d  lea     r8, [rbp+arg_0]
0x180014b71  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180014b78  mov     rcx, rdi
0x180014b7b  mov     rax, rbx
0x180014b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b83  test    eax, eax
0x180014b85  js      short loc_180014B9C
0x180014b87  mov     rcx, [rbp+arg_0]
0x180014b8b  mov     rax, [rcx]
0x180014b8e  lea     rdx, [rbp+arg_8]
0x180014b92  mov     rax, [rax+40h]
0x180014b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b9b  nop
0x180014b9c  lea     rcx, [rbp+arg_0]
0x180014ba0  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014ba5  mov     ebx, [rbp+arg_8]
0x180014ba8  lea     rcx, [rbp+arg_18]
0x180014bac  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014bb1  nop
0x180014bb2  lea     rcx, [rbp+var_20]
0x180014bb6  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014bbb  mov     eax, ebx
0x180014bbd  add     rsp, 50h
0x180014bc1  pop     rdi
0x180014bc2  pop     rbx
0x180014bc3  pop     rbp
0x180014bc4  retn
```
