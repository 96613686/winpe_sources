# Microsoft::WRL::Details::CreateAgileHelper<Windows::Foundation::IEventHandler<IInspectable *>>(Windows::Foundation::IEventHandler<IInspectable *> *,Windows::Foundation::IEventHandler<IInspectable *> * *)

- ea: `0x18000166c`
- end: `0x180001778`
- name: `??$CreateAgileHelper@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@@Details@WRL@Microsoft@@YAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@PEAPEAU345@@Z`
- size: `268`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000145c`

## callees

- `0x18000166c`
- `0x1800018c4`
- `0x18001376c`
- `0x180013ce8`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800016af`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800016af`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateAgileHelper<Windows::Foundation::IEventHandler<IInspectable *>>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v2; // rax
  int AgileReference; // ebx
  __int64 v6; // rcx
  void *v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // [rsp+30h] [rbp+10h] BYREF
  __int64 v12; // [rsp+38h] [rbp+18h] BYREF

  v2 = 0;
  *a2 = 0;
  v11 = 0;
  if ( a1 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
    AgileReference = RoGetAgileReference(0, &GUID_c50898f6_c536_5f47_8583_8b2c2438a13b, a1, &v11);
    if ( AgileReference < 0 )
    {
      v6 = v11;
      if ( v11 )
      {
        v11 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      }
      return (unsigned int)AgileReference;
    }
    v2 = v11;
  }
  v12 = v2;
  v11 = 0;
  v8 = operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
  if ( v8 )
    v9 = Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IEventHandler_impl<IInspectable *>::*)(IInspectable *,IInspectable *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::FtmBase>,_lambda_ab78ac3a848141b5f56954aedecd34c8_,-1,IInspectable *,IInspectable *>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::FtmBase>,_lambda_ab78ac3a848141b5f56954aedecd34c8_,-1,IInspectable *,IInspectable *>(
           v8,
           &v12);
  else
    v9 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  v10 = v11;
  if ( v9 )
  {
    *a2 = v9;
    if ( v10 )
    {
      v11 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return 0;
  }
  else
  {
    if ( v11 )
    {
      v11 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000166c  mov     [rsp-8+arg_10], rbx
0x180001671  mov     [rsp-8+arg_18], rdi
0x180001676  push    rbp
0x180001677  mov     rbp, rsp
0x18000167a  sub     rsp, 20h
0x18000167e  xor     eax, eax
0x180001680  mov     qword ptr [rdx], 0
0x180001687  mov     [rbp+arg_0], rax
0x18000168b  mov     rdi, rdx
0x18000168e  mov     rbx, rcx
0x180001691  test    rcx, rcx
0x180001694  jz      short loc_1800016EE
0x180001696  lea     rcx, [rbp+arg_0]
0x18000169a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000169f  lea     r9, [rbp+arg_0]
0x1800016a3  mov     r8, rbx
0x1800016a6  lea     rdx, _GUID_c50898f6_c536_5f47_8583_8b2c2438a13b
0x1800016ad  xor     ecx, ecx
0x1800016af  call    cs:__imp_RoGetAgileReference
0x1800016b5  mov     ebx, eax
0x1800016b7  test    eax, eax
0x1800016b9  jns     short loc_1800016EA
0x1800016bb  mov     rcx, [rbp+arg_0]
0x1800016bf  test    rcx, rcx
0x1800016c2  jz      short loc_1800016D8
0x1800016c4  mov     [rbp+arg_0], 0
0x1800016cc  mov     rdx, [rcx]
0x1800016cf  mov     rax, [rdx+10h]
0x1800016d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016d8  mov     eax, ebx
0x1800016da  mov     rbx, [rsp+20h+arg_10]
0x1800016df  mov     rdi, [rsp+20h+arg_18]
0x1800016e4  add     rsp, 20h
0x1800016e8  pop     rbp
0x1800016e9  retn
0x1800016ea  mov     rax, [rbp+arg_0]
0x1800016ee  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800016f5  mov     [rbp+arg_8], rax
0x1800016f9  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800016fe  mov     [rbp+arg_0], 0
0x180001706  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000170b  test    rax, rax
0x18000170e  jnz     short loc_180001767
0x180001710  xor     ebx, ebx
0x180001712  lea     rcx, [rbp+arg_8]
0x180001716  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000171b  mov     rcx, [rbp+arg_0]
0x18000171f  test    rbx, rbx
0x180001722  jz      short loc_180001744
0x180001724  mov     [rdi], rbx
0x180001727  test    rcx, rcx
0x18000172a  jz      short loc_180001740
0x18000172c  mov     [rbp+arg_0], 0
0x180001734  mov     rax, [rcx]
0x180001737  mov     rax, [rax+10h]
0x18000173b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001740  xor     eax, eax
0x180001742  jmp     short loc_1800016DA
0x180001744  test    rcx, rcx
0x180001747  jz      short loc_18000175D
0x180001749  mov     [rbp+arg_0], 0
0x180001751  mov     rax, [rcx]
0x180001754  mov     rax, [rax+10h]
0x180001758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000175d  mov     eax, 8007000Eh
0x180001762  jmp     loc_1800016DA
0x180001767  lea     rdx, [rbp+arg_8]
0x18000176b  mov     rcx, rax
0x18000176e  call    ??0?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_ab78ac3a848141b5f56954aedecd34c8_@@$0?0PEAUIInspectable@@PEAU5@@?$DelegateArgTraits@P8?$IEventHandler_impl@PEAUIInspectable@@@Foundation@Windows@@EAAJPEAUIInspectable@@0@Z@Details@WRL@Microsoft@@QEAA@$$QEAV_lambda_ab78ac3a848141b5f56954aedecd34c8_@@@Z; Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IEventHandler_impl<IInspectable *>::*)(IInspectable *,IInspectable *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::FtmBase>,_lambda_ab78ac3a848141b5f56954aedecd34c8_,-1,IInspectable *,IInspectable *>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::FtmBase>,_lambda_ab78ac3a848141b5f56954aedecd34c8_,-1,IInspectable *,IInspectable *>(_lambda_ab78ac3a848141b5f56954aedecd34c8_ &&)
0x180001773  mov     rbx, rax
0x180001776  jmp     short loc_180001712
```
