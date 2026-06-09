# WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)

- ea: `0x1400090ac`
- end: `0x140009235`
- name: `??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `393`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000c848`

## callees

- `0x140008984`
- `0x1400090ac`
- `0x14000d49c`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140009156`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140009156`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(
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
  v4 = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__Foundation_Windows__U__IAsyncOperationWithProgress_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__23___YAJPEAU__IAsyncOperationWithProgress_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__Foundation_Windows__U__IAsyncOperationWithProgress_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__Foundation_Windows__U__IAsyncOperationWithProgress_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__23___YAJPEAU__IAsyncOperationWithProgress_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&v14);
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
0x1400090ac  mov     [rsp-18h+dwindex], r8
0x1400090b1  mov     [rsp-18h+arg_8], edx
0x1400090b5  push    rbp
0x1400090b6  push    rbx
0x1400090b7  push    rdi
0x1400090b8  mov     rbp, rsp
0x1400090bb  sub     rsp, 50h
0x1400090bf  mov     rdi, rcx
0x1400090c2  mov     [rbp+var_20], rcx
0x1400090c6  test    rcx, rcx
0x1400090c9  jz      short loc_1400090D8
0x1400090cb  mov     rax, [rcx]
0x1400090ce  mov     rax, [rax+8]
0x1400090d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400090d7  nop
0x1400090d8  mov     [rbp+arg_18], 0
0x1400090e0  lea     rcx, [rbp+arg_18]
0x1400090e4  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x1400090e9  lea     rcx, [rbp+arg_18]
0x1400090ed  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x1400090f2  mov     ebx, eax
0x1400090f4  mov     [rbp+arg_8], eax
0x1400090f7  test    eax, eax
0x1400090f9  js      loc_140009218
0x1400090ff  mov     rax, [rdi]
0x140009102  mov     rdx, [rbp+arg_18]
0x140009106  mov     rcx, rdi
0x140009109  mov     rax, [rax+40h]
0x14000910d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009112  mov     ebx, eax
0x140009114  mov     [rbp+arg_8], eax
0x140009117  test    eax, eax
0x140009119  js      loc_140009218
0x14000911f  mov     rax, [rbp+arg_18]
0x140009123  mov     rcx, [rax+38h]
0x140009127  mov     [rbp+pHandles], rcx
0x14000912b  mov     [rbp+var_10], 0
0x140009133  xor     bl, bl
0x140009135  mov     dword ptr [rbp+dwindex], 0
0x14000913c  lea     rax, [rbp+dwindex]
0x140009140  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x140009145  lea     r9, [rbp+pHandles]; pHandles
0x140009149  mov     r8d, 1; cHandles
0x14000914f  or      edx, 0FFFFFFFFh; dwTimeout
0x140009152  lea     ecx, [r8+7]; dwFlags
0x140009156  call    cs:__imp_CoWaitForMultipleHandles
0x14000915c  mov     [rbp+arg_8], eax
0x14000915f  test    eax, eax
0x140009161  js      short loc_140009172
0x140009163  cmp     dword ptr [rbp+dwindex], 0
0x140009167  jz      short loc_140009172
0x140009169  mov     [rbp+arg_8], 800704C7h
0x140009170  mov     bl, 1
0x140009172  mov     [rbp+arg_0], 0
0x14000917a  test    bl, bl
0x14000917c  jz      short loc_1400091B7
0x14000917e  mov     rax, [rdi]
0x140009181  mov     rbx, [rax]
0x140009184  lea     rcx, [rbp+arg_0]
0x140009188  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000918d  lea     r8, [rbp+arg_0]
0x140009191  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x140009198  mov     rcx, rdi
0x14000919b  mov     rax, rbx
0x14000919e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400091a3  test    eax, eax
0x1400091a5  js      short loc_1400091B7
0x1400091a7  mov     rcx, [rbp+arg_0]
0x1400091ab  mov     rax, [rcx]
0x1400091ae  mov     rax, [rax+48h]
0x1400091b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400091b7  cmp     [rbp+arg_8], 0
0x1400091bb  jl      short loc_14000920C
0x1400091bd  mov     rax, [rbp+arg_18]
0x1400091c1  cmp     dword ptr [rax+30h], 1
0x1400091c5  jz      short loc_14000920C
0x1400091c7  cmp     [rbp+arg_0], 0
0x1400091cc  jnz     short loc_1400091F7
0x1400091ce  mov     rax, [rdi]
0x1400091d1  mov     rbx, [rax]
0x1400091d4  lea     rcx, [rbp+arg_0]
0x1400091d8  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x1400091dd  lea     r8, [rbp+arg_0]
0x1400091e1  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1400091e8  mov     rcx, rdi
0x1400091eb  mov     rax, rbx
0x1400091ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400091f3  test    eax, eax
0x1400091f5  js      short loc_14000920C
0x1400091f7  mov     rcx, [rbp+arg_0]
0x1400091fb  mov     rax, [rcx]
0x1400091fe  lea     rdx, [rbp+arg_8]
0x140009202  mov     rax, [rax+40h]
0x140009206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000920b  nop
0x14000920c  lea     rcx, [rbp+arg_0]
0x140009210  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x140009215  mov     ebx, [rbp+arg_8]
0x140009218  lea     rcx, [rbp+arg_18]
0x14000921c  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x140009221  nop
0x140009222  lea     rcx, [rbp+var_20]
0x140009226  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000922b  mov     eax, ebx
0x14000922d  add     rsp, 50h
0x140009231  pop     rdi
0x140009232  pop     rbx
0x140009233  pop     rbp
0x140009234  retn
```
