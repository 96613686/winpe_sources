# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>(void)

- ea: `0x1800072e8`
- end: `0x180007366`
- name: `??1?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000748c`
- `0x180007960`

## callees

- `0x1800072e8`
- `0x18000f610`
- `0x180019010`

## pseudocode

```c
void **__fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>(
        __int64 a1)
{
  __int64 v2; // rcx
  bool v3; // zf
  void **result; // rax
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = *(_QWORD *)(a1 + 104);
  if ( v2 )
  {
    *(_QWORD *)(a1 + 104) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  v3 = *(_DWORD *)(a1 + 16) == 0;
  result = &Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable';
  *(_QWORD *)a1 = &Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable';
  if ( v3 )
    result = (void **)Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
  v5 = *(_QWORD *)(a1 + 48);
  if ( v5 )
  {
    *(_QWORD *)(a1 + 48) = 0;
    result = (void **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = *(_QWORD *)(a1 + 24);
  if ( v6 )
  {
    *(_QWORD *)(a1 + 24) = 0;
    return (void **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return result;
}

```

## disassembly

```asm
0x1800072e8  push    rbx
0x1800072ea  sub     rsp, 20h
0x1800072ee  mov     rbx, rcx
0x1800072f1  mov     rcx, [rcx+68h]
0x1800072f5  test    rcx, rcx
0x1800072f8  jz      short loc_18000730E
0x1800072fa  mov     qword ptr [rbx+68h], 0
0x180007302  mov     rax, [rcx]
0x180007305  mov     rax, [rax+10h]
0x180007309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000730e  cmp     dword ptr [rbx+10h], 0
0x180007312  lea     rax, ??_7?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@6B@; const Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'
0x180007319  mov     [rbx], rax
0x18000731c  jnz     short loc_180007326
0x18000731e  mov     rcx, rbx
0x180007321  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x180007326  mov     rcx, [rbx+30h]
0x18000732a  test    rcx, rcx
0x18000732d  jz      short loc_180007343
0x18000732f  mov     qword ptr [rbx+30h], 0
0x180007337  mov     rax, [rcx]
0x18000733a  mov     rax, [rax+10h]
0x18000733e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007343  mov     rcx, [rbx+18h]
0x180007347  test    rcx, rcx
0x18000734a  jz      short loc_180007360
0x18000734c  mov     qword ptr [rbx+18h], 0
0x180007354  mov     rax, [rcx]
0x180007357  mov     rax, [rax+10h]
0x18000735b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007360  add     rsp, 20h
0x180007364  pop     rbx
0x180007365  retn
```
