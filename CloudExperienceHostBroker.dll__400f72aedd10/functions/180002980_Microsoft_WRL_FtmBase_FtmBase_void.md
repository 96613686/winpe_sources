# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180002980`
- end: `0x180002a34`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `180`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `24`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010608`
- `0x18001cde8`
- `0x18001cfec`
- `0x18002030c`
- `0x1800211b8`
- `0x18002127c`
- `0x180021340`
- `0x180021404`
- `0x180028c70`
- `0x180028d0c`
- `0x180028dd0`
- `0x180028e94`
- `0x180028f58`
- `0x18002901c`
- `0x1800290e0`
- `0x180029944`
- `0x1800309f8`
- `0x180030abc`
- `0x180032918`
- `0x1800329dc`
- `0x180032aa0`
- `0x180032b64`
- `0x180032c28`
- `0x1800336ec`

## callees

- `0x180002980`
- `0x180002a3c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800029bc`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800029bc`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  LPUNKNOWN v2; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v4; // rcx
  LPUNKNOWN v5; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::Cortana::SetCortanaOptinAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::Cortana::SetCortanaOptinAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v2 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v4 = *((_QWORD *)this + 3);
    if ( v4 )
    {
      *((_QWORD *)this + 3) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(
      v2,
      &GUID_00000003_0000_0000_c000_000000000046,
      (char *)this + 24);
  }
  v5 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v5->lpVtbl->Release)(v5);
  }
  return this;
}

```

## disassembly

```asm
0x180002980  mov     [rsp+arg_8], rbx
0x180002985  mov     [rsp+arg_10], rbp
0x18000298a  push    rsi
0x18000298b  push    rdi
0x18000298c  push    r14
0x18000298e  sub     rsp, 20h
0x180002992  mov     rsi, rcx
0x180002995  lea     rax, ??_7?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?SetCortanaOptinAsyncActionName@Cortana@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SetCortanaOptinAsyncActionName@Cortana@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::Cortana::SetCortanaOptinAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::Cortana::SetCortanaOptinAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x18000299c  mov     [rcx], rax
0x18000299f  xor     r14d, r14d
0x1800029a2  mov     [rcx+18h], r14
0x1800029a6  mov     [rsp+38h+ppunkMarshal], r14
0x1800029ab  lea     rcx, [rsp+38h+ppunkMarshal]
0x1800029b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800029b5  lea     rdx, [rsp+38h+ppunkMarshal]; ppunkMarshal
0x1800029ba  xor     ecx, ecx; punkOuter
0x1800029bc  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800029c2  test    eax, eax
0x1800029c4  js      short loc_180002A02
0x1800029c6  mov     rbx, [rsp+38h+ppunkMarshal]
0x1800029cb  mov     rax, [rbx]
0x1800029ce  mov     rbp, [rax]
0x1800029d1  mov     rcx, [rsi+18h]
0x1800029d5  test    rcx, rcx
0x1800029d8  jz      short loc_1800029EB
0x1800029da  mov     [rsi+18h], r14
0x1800029de  mov     rdx, [rcx]
0x1800029e1  mov     rax, [rdx+10h]
0x1800029e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ea  nop
0x1800029eb  lea     r8, [rsi+18h]
0x1800029ef  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800029f6  mov     rcx, rbx
0x1800029f9  mov     rax, rbp
0x1800029fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a01  nop
0x180002a02  mov     rcx, [rsp+38h+ppunkMarshal]
0x180002a07  test    rcx, rcx
0x180002a0a  jz      short loc_180002A1E
0x180002a0c  mov     [rsp+38h+ppunkMarshal], r14
0x180002a11  mov     rax, [rcx]
0x180002a14  mov     rax, [rax+10h]
0x180002a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a1d  nop
0x180002a1e  mov     rax, rsi
0x180002a21  mov     rbx, [rsp+38h+arg_8]
0x180002a26  mov     rbp, [rsp+38h+arg_10]
0x180002a2b  add     rsp, 20h
0x180002a2f  pop     r14
0x180002a31  pop     rdi
0x180002a32  pop     rsi
0x180002a33  retn
```
