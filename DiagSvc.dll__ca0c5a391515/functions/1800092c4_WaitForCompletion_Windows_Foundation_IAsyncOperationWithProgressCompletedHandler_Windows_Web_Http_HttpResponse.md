# WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)

- ea: `0x1800092c4`
- end: `0x18000944d`
- name: `??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `393`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000851c`

## callees

- `0x18000517c`
- `0x180008950`
- `0x1800092c4`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000936e`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000936e`

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
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v14);
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
0x1800092c4  mov     [rsp-18h+dwindex], r8
0x1800092c9  mov     [rsp-18h+arg_8], edx
0x1800092cd  push    rbp
0x1800092ce  push    rbx
0x1800092cf  push    rdi
0x1800092d0  mov     rbp, rsp
0x1800092d3  sub     rsp, 50h
0x1800092d7  mov     rdi, rcx
0x1800092da  mov     [rbp+var_20], rcx
0x1800092de  test    rcx, rcx
0x1800092e1  jz      short loc_1800092F0
0x1800092e3  mov     rax, [rcx]
0x1800092e6  mov     rax, [rax+8]
0x1800092ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092ef  nop
0x1800092f0  mov     [rbp+arg_18], 0
0x1800092f8  lea     rcx, [rbp+arg_18]
0x1800092fc  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180009301  lea     rcx, [rbp+arg_18]
0x180009305  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x18000930a  mov     ebx, eax
0x18000930c  mov     [rbp+arg_8], eax
0x18000930f  test    eax, eax
0x180009311  js      loc_180009430
0x180009317  mov     rax, [rdi]
0x18000931a  mov     rdx, [rbp+arg_18]
0x18000931e  mov     rcx, rdi
0x180009321  mov     rax, [rax+40h]
0x180009325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000932a  mov     ebx, eax
0x18000932c  mov     [rbp+arg_8], eax
0x18000932f  test    eax, eax
0x180009331  js      loc_180009430
0x180009337  mov     rax, [rbp+arg_18]
0x18000933b  mov     rcx, [rax+38h]
0x18000933f  mov     [rbp+pHandles], rcx
0x180009343  mov     [rbp+var_10], 0
0x18000934b  xor     bl, bl
0x18000934d  mov     dword ptr [rbp+dwindex], 0
0x180009354  lea     rax, [rbp+dwindex]
0x180009358  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x18000935d  lea     r9, [rbp+pHandles]; pHandles
0x180009361  mov     r8d, 1; cHandles
0x180009367  or      edx, 0FFFFFFFFh; dwTimeout
0x18000936a  lea     ecx, [r8+7]; dwFlags
0x18000936e  call    cs:__imp_CoWaitForMultipleHandles
0x180009374  mov     [rbp+arg_8], eax
0x180009377  test    eax, eax
0x180009379  js      short loc_18000938A
0x18000937b  cmp     dword ptr [rbp+dwindex], 0
0x18000937f  jz      short loc_18000938A
0x180009381  mov     [rbp+arg_8], 800704C7h
0x180009388  mov     bl, 1
0x18000938a  mov     [rbp+arg_0], 0
0x180009392  test    bl, bl
0x180009394  jz      short loc_1800093CF
0x180009396  mov     rax, [rdi]
0x180009399  mov     rbx, [rax]
0x18000939c  lea     rcx, [rbp+arg_0]
0x1800093a0  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x1800093a5  lea     r8, [rbp+arg_0]
0x1800093a9  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800093b0  mov     rcx, rdi
0x1800093b3  mov     rax, rbx
0x1800093b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093bb  test    eax, eax
0x1800093bd  js      short loc_1800093CF
0x1800093bf  mov     rcx, [rbp+arg_0]
0x1800093c3  mov     rax, [rcx]
0x1800093c6  mov     rax, [rax+48h]
0x1800093ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093cf  cmp     [rbp+arg_8], 0
0x1800093d3  jl      short loc_180009424
0x1800093d5  mov     rax, [rbp+arg_18]
0x1800093d9  cmp     dword ptr [rax+30h], 1
0x1800093dd  jz      short loc_180009424
0x1800093df  cmp     [rbp+arg_0], 0
0x1800093e4  jnz     short loc_18000940F
0x1800093e6  mov     rax, [rdi]
0x1800093e9  mov     rbx, [rax]
0x1800093ec  lea     rcx, [rbp+arg_0]
0x1800093f0  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x1800093f5  lea     r8, [rbp+arg_0]
0x1800093f9  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180009400  mov     rcx, rdi
0x180009403  mov     rax, rbx
0x180009406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000940b  test    eax, eax
0x18000940d  js      short loc_180009424
0x18000940f  mov     rcx, [rbp+arg_0]
0x180009413  mov     rax, [rcx]
0x180009416  lea     rdx, [rbp+arg_8]
0x18000941a  mov     rax, [rax+40h]
0x18000941e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009423  nop
0x180009424  lea     rcx, [rbp+arg_0]
0x180009428  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18000942d  mov     ebx, [rbp+arg_8]
0x180009430  lea     rcx, [rbp+arg_18]
0x180009434  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180009439  nop
0x18000943a  lea     rcx, [rbp+var_20]
0x18000943e  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180009443  mov     eax, ebx
0x180009445  add     rsp, 50h
0x180009449  pop     rdi
0x18000944a  pop     rbx
0x18000944b  pop     rbp
0x18000944c  retn
```
