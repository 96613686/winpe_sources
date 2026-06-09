# `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::FTMEventDelegate(void)

- ea: `0x140010430`
- end: `0x140010538`
- name: `??0FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@QEAA@XZ`
- size: `264`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400101f8`

## callees

- `0x140010430`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x14001046c`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x14001046c`

## pseudocode

```c
__int64 __fastcall `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>'::`2'::FTMEventDelegate::FTMEventDelegate(
        __int64 a1)
{
  __int64 *v2; // rsi
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v5; // rcx
  LPUNKNOWN v6; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)a1 = &Windows::Foundation::IAsyncOperationCompletedHandler<bool>::`vftable';
  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::FtmBase::`vftable';
  v2 = (__int64 *)(a1 + 32);
  *(_QWORD *)(a1 + 32) = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v5 = *v2;
    if ( *v2 )
    {
      *v2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, __int64 *))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v2);
  }
  v6 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v6->lpVtbl->Release)(v6);
  }
  *(_DWORD *)(a1 + 44) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'};
  *(_QWORD *)(a1 + 8) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>'::`2'::FTMEventDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)a1 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>'::`2'::FTMEventDelegate::`vftable';
  *(_QWORD *)(a1 + 8) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>'::`2'::FTMEventDelegate::`vftable';
  *(_DWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  return a1;
}

```

## disassembly

```asm
0x140010430  push    rbx
0x140010432  push    rbp
0x140010433  push    rsi
0x140010434  push    rdi
0x140010435  sub     rsp, 28h
0x140010439  mov     rdi, rcx
0x14001043c  lea     rax, ??_7?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<bool>::`vftable'
0x140010443  mov     [rcx], rax
0x140010446  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x14001044d  mov     [rcx+8], rax
0x140010451  lea     rsi, [rcx+20h]
0x140010455  mov     qword ptr [rsi], 0
0x14001045c  mov     [rsp+48h+ppunkMarshal], 0
0x140010465  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x14001046a  xor     ecx, ecx; punkOuter
0x14001046c  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x140010472  test    eax, eax
0x140010474  js      short loc_1400104B3
0x140010476  mov     rbx, [rsp+48h+ppunkMarshal]
0x14001047b  mov     rax, [rbx]
0x14001047e  mov     rbp, [rax]
0x140010481  mov     rcx, [rsi]
0x140010484  test    rcx, rcx
0x140010487  jz      short loc_14001049D
0x140010489  mov     qword ptr [rsi], 0
0x140010490  mov     rdx, [rcx]
0x140010493  mov     rax, [rdx+10h]
0x140010497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001049c  nop
0x14001049d  mov     r8, rsi
0x1400104a0  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1400104a7  mov     rcx, rbx
0x1400104aa  mov     rax, rbp
0x1400104ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400104b2  nop
0x1400104b3  mov     rcx, [rsp+48h+ppunkMarshal]
0x1400104b8  test    rcx, rcx
0x1400104bb  jz      short loc_1400104D3
0x1400104bd  mov     [rsp+48h+ppunkMarshal], 0
0x1400104c6  mov     rax, [rcx]
0x1400104c9  mov     rax, [rax+10h]
0x1400104cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400104d2  nop
0x1400104d3  mov     dword ptr [rdi+2Ch], 1
0x1400104da  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'}
0x1400104e1  mov     [rdi], rax
0x1400104e4  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1400104eb  mov     [rdi+8], rax
0x1400104ef  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1400104f6  test    rcx, rcx
0x1400104f9  jz      short loc_140010508
0x1400104fb  mov     rax, [rcx]
0x1400104fe  mov     rax, [rax+8]
0x140010502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010507  nop
0x140010508  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@_N@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'}
0x14001050f  mov     [rdi], rax
0x140010512  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140010519  mov     [rdi+8], rax
0x14001051d  mov     dword ptr [rdi+30h], 0
0x140010524  mov     qword ptr [rdi+38h], 0
0x14001052c  mov     rax, rdi
0x14001052f  add     rsp, 28h
0x140010533  pop     rdi
0x140010534  pop     rsi
0x140010535  pop     rbp
0x140010536  pop     rbx
0x140010537  retn
```
