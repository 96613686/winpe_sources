# Microsoft::WRL::Details::MakeAndInitialize<ProgressHandler,ProgressHandler,ulong>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ProgressHandler>>,ulong &&)

- ea: `0x18000dd2c`
- end: `0x18000de65`
- name: `??$MakeAndInitialize@VProgressHandler@@V1@K@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VProgressHandler@@@WRL@Microsoft@@@012@$$QEAK@Z`
- size: `313`
- prototype: `__int64 __fastcall(__int64 *, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800170b0`

## callees

- `0x180001ea8`
- `0x18000dd2c`
- `0x18000ed8c`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<ProgressHandler,ProgressHandler,unsigned long>(
        __int64 *a1,
        _DWORD *a2)
{
  __int64 v4; // rcx
  _QWORD *v5; // rdi
  struct Microsoft::WRL::Details::ModuleBase *v7; // rcx

  v4 = *a1;
  if ( v4 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  *a1 = 0;
  v5 = operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v5 )
    return 2147942414LL;
  v5[1] = &Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v5 + 4));
  v7 = Microsoft::WRL::Details::ModuleBase::module_;
  *v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::`vftable';
  v5[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionProgressHandler<double>'};
  v5[2] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IInspectable,Microsoft::WRL::FtmBase>'};
  v5[3] = &ProgressHandler::`vftable'{for `IInspectable'};
  v5[4] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v5[9] = 1;
  if ( v7 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v7 + 8LL))(v7);
  *((_DWORD *)v5 + 20) = 0;
  *v5 = &ProgressHandler::`vftable';
  v5[1] = &ProgressHandler::`vftable'{for `Windows::Foundation::IAsyncActionProgressHandler<double>'};
  v5[2] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IInspectable,Microsoft::WRL::FtmBase>'};
  v5[3] = &ProgressHandler::`vftable'{for `IInspectable'};
  v5[4] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_DWORD *)v5 + 20) = *a2;
  ((void (__fastcall *)(_QWORD *))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::AddRef)(v5);
  *a1 = (__int64)v5;
  (*(void (__fastcall **)(_QWORD *))(*v5 + 16LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x18000dd2c  mov     [rsp+arg_0], rbx
0x18000dd31  mov     [rsp+arg_8], rsi
0x18000dd36  push    rdi
0x18000dd37  sub     rsp, 20h
0x18000dd3b  mov     rbx, rcx
0x18000dd3e  mov     rsi, rdx
0x18000dd41  mov     rcx, [rcx]
0x18000dd44  test    rcx, rcx
0x18000dd47  jz      short loc_18000DD5C
0x18000dd49  mov     qword ptr [rbx], 0
0x18000dd50  mov     rax, [rcx]
0x18000dd53  mov     rax, [rax+10h]
0x18000dd57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd5c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000dd63  mov     qword ptr [rbx], 0
0x18000dd6a  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000dd6f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000dd74  mov     rdi, rax
0x18000dd77  test    rax, rax
0x18000dd7a  jnz     short loc_18000DD86
0x18000dd7c  mov     eax, 8007000Eh
0x18000dd81  jmp     loc_18000DE55
0x18000dd86  lea     rax, ??_7?$IAsyncActionWithProgressCompletedHandler@N@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>::`vftable'
0x18000dd8d  lea     rcx, [rdi+20h]; this
0x18000dd91  mov     [rdi+8], rax
0x18000dd95  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000dd9a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000dda1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$IAsyncActionProgressHandler@N@Foundation@Windows@@UIInspectable@@VFtmBase@23@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::`vftable'
0x18000dda8  mov     [rdi], rax
0x18000ddab  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$IAsyncActionProgressHandler@N@Foundation@Windows@@UIInspectable@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncActionProgressHandler@N@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionProgressHandler<double>'}
0x18000ddb2  mov     [rdi+8], rax
0x18000ddb6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$IAsyncActionProgressHandler@N@Foundation@Windows@@UIInspectable@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIInspectable@@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IInspectable,Microsoft::WRL::FtmBase>'}
0x18000ddbd  mov     [rdi+10h], rax
0x18000ddc1  lea     rax, ??_7ProgressHandler@@6BIInspectable@@@; const ProgressHandler::`vftable'{for `IInspectable'}
0x18000ddc8  mov     [rdi+18h], rax
0x18000ddcc  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$IAsyncActionProgressHandler@N@Foundation@Windows@@UIInspectable@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000ddd3  mov     [rdi+20h], rax
0x18000ddd7  mov     qword ptr [rdi+48h], 1
0x18000dddf  test    rcx, rcx
0x18000dde2  jz      short loc_18000DDF0
0x18000dde4  mov     rax, [rcx]
0x18000dde7  mov     rax, [rax+8]
0x18000ddeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddf0  mov     dword ptr [rdi+50h], 0
0x18000ddf7  lea     rax, ??_7ProgressHandler@@6B@; const ProgressHandler::`vftable'
0x18000ddfe  mov     [rdi], rax
0x18000de01  mov     rcx, rdi
0x18000de04  lea     rax, ??_7ProgressHandler@@6B?$IAsyncActionProgressHandler@N@Foundation@Windows@@@; const ProgressHandler::`vftable'{for `Windows::Foundation::IAsyncActionProgressHandler<double>'}
0x18000de0b  mov     [rdi+8], rax
0x18000de0f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$IAsyncActionProgressHandler@N@Foundation@Windows@@UIInspectable@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIInspectable@@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IInspectable,Microsoft::WRL::FtmBase>'}
0x18000de16  mov     [rdi+10h], rax
0x18000de1a  lea     rax, ??_7ProgressHandler@@6BIInspectable@@@; const ProgressHandler::`vftable'{for `IInspectable'}
0x18000de21  mov     [rdi+18h], rax
0x18000de25  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$IAsyncActionProgressHandler@N@Foundation@Windows@@UIInspectable@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000de2c  mov     [rdi+20h], rax
0x18000de30  mov     eax, [rsi]
0x18000de32  mov     [rdi+50h], eax
0x18000de35  mov     rax, cs:off_1800258A8
0x18000de3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de41  mov     [rbx], rdi
0x18000de44  mov     rcx, rdi
0x18000de47  mov     rax, [rdi]
0x18000de4a  mov     rax, [rax+10h]
0x18000de4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de53  xor     eax, eax
0x18000de55  mov     rbx, [rsp+28h+arg_0]
0x18000de5a  mov     rsi, [rsp+28h+arg_8]
0x18000de5f  add     rsp, 20h
0x18000de63  pop     rdi
0x18000de64  retn
```
