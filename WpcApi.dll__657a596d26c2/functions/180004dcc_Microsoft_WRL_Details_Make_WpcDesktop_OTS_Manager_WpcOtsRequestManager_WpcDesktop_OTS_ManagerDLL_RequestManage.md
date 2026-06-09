# Microsoft::WRL::Details::Make<WpcDesktop::OTS::Manager::WpcOtsRequestManager,WpcDesktop::OTS::ManagerDLL::RequestManagerDesktopDependencies &>(WpcDesktop::OTS::ManagerDLL::RequestManagerDesktopDependencies &)

- ea: `0x180004dcc`
- end: `0x180004eae`
- name: `??$Make@VWpcOtsRequestManager@Manager@OTS@WpcDesktop@@AEAVRequestManagerDesktopDependencies@ManagerDLL@34@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWpcOtsRequestManager@Manager@OTS@WpcDesktop@@@12@AEAVRequestManagerDesktopDependencies@ManagerDLL@OTS@WpcDesktop@@@Z`
- size: `226`
- prototype: `Microsoft::WRL::FtmBase **__fastcall(Microsoft::WRL::FtmBase **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a790`

## callees

- `0x180003308`
- `0x180004dcc`
- `0x180005b38`
- `0x18000b274`
- `0x18002c010`

## pseudocode

```c
Microsoft::WRL::FtmBase **__fastcall Microsoft::WRL::Details::Make<WpcDesktop::OTS::Manager::WpcOtsRequestManager,WpcDesktop::OTS::ManagerDLL::RequestManagerDesktopDependencies &>(
        Microsoft::WRL::FtmBase **a1)
{
  Microsoft::WRL::FtmBase *v2; // rax
  Microsoft::WRL::FtmBase *v3; // rbx

  *a1 = 0;
  v2 = (Microsoft::WRL::FtmBase *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( v2 )
  {
    Microsoft::WRL::FtmBase::FtmBase(v2);
    *((_DWORD *)v3 + 11) = 1;
    *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IWpcOtsRequestManager>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWpcOtsRequestManager>>'};
    *((_QWORD *)v3 + 4) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IWpcOtsRequestManager>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWpcOtsRequestManager>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWpcOtsRequestManager>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v3 = &WpcDesktop::OTS::Manager::WpcOtsRequestManager::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWpcOtsRequestManager>>'};
    *((_QWORD *)v3 + 4) = &WpcDesktop::OTS::Manager::WpcOtsRequestManager::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWpcOtsRequestManager>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWpcOtsRequestManager>>'};
    *((_QWORD *)v3 + 6) = WpcDesktop::OTS::ManagerDLL::s_dependencies;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, &WPP_dc195e4bdbd63c33a4e68728034627b2_Traceguids);
    if ( *a1 )
      (*(void (__fastcall **)(Microsoft::WRL::FtmBase *))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v3;
  }
  return a1;
}

```

## disassembly

```asm
0x180004dcc  mov     [rsp+arg_0], rbx
0x180004dd1  push    rdi
0x180004dd2  sub     rsp, 20h
0x180004dd6  mov     rdi, rcx
0x180004dd9  mov     qword ptr [rcx], 0
0x180004de0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004de7  mov     ecx, 38h ; '8'; unsigned __int64
0x180004dec  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004df1  mov     rbx, rax
0x180004df4  test    rax, rax
0x180004df7  jz      loc_180004EA0
0x180004dfd  mov     rcx, rax; this
0x180004e00  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180004e05  mov     dword ptr [rbx+2Ch], 1
0x180004e0c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VFtmBase@23@UIWpcOtsRequestManager@@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWpcOtsRequestManager@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IWpcOtsRequestManager>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWpcOtsRequestManager>>'}
0x180004e13  mov     [rbx], rax
0x180004e16  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VFtmBase@23@UIWpcOtsRequestManager@@@WRL@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIWpcOtsRequestManager@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWpcOtsRequestManager@@@234@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IWpcOtsRequestManager>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWpcOtsRequestManager>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWpcOtsRequestManager>>'}
0x180004e1d  mov     [rbx+20h], rax
0x180004e21  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180004e28  test    rcx, rcx
0x180004e2b  jz      short loc_180004E3A
0x180004e2d  mov     rax, [rcx]
0x180004e30  mov     rax, [rax+8]
0x180004e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e39  nop
0x180004e3a  lea     rax, ??_7WpcOtsRequestManager@Manager@OTS@WpcDesktop@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWpcOtsRequestManager@@@Details@23@@Details@WRL@Microsoft@@@; const WpcDesktop::OTS::Manager::WpcOtsRequestManager::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWpcOtsRequestManager>>'}
0x180004e41  mov     [rbx], rax
0x180004e44  lea     rax, ??_7WpcOtsRequestManager@Manager@OTS@WpcDesktop@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIWpcOtsRequestManager@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWpcOtsRequestManager@@@234@@Details@WRL@Microsoft@@@; const WpcDesktop::OTS::Manager::WpcOtsRequestManager::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWpcOtsRequestManager>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWpcOtsRequestManager>>'}
0x180004e4b  mov     [rbx+20h], rax
0x180004e4f  lea     rax, ?s_dependencies@ManagerDLL@OTS@WpcDesktop@@3VRequestManagerDesktopDependencies@123@A; WpcDesktop::OTS::ManagerDLL::RequestManagerDesktopDependencies WpcDesktop::OTS::ManagerDLL::s_dependencies
0x180004e56  mov     [rbx+30h], rax
0x180004e5a  lea     rax, WPP_GLOBAL_Control
0x180004e61  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e68  cmp     rcx, rax
0x180004e6b  jz      short loc_180004E89
0x180004e6d  test    byte ptr [rcx+1Ch], 8
0x180004e71  jz      short loc_180004E89
0x180004e73  mov     edx, 10h
0x180004e78  lea     r8, WPP_dc195e4bdbd63c33a4e68728034627b2_Traceguids
0x180004e7f  mov     rcx, [rcx+10h]
0x180004e83  call    WPP_SF_
0x180004e88  nop
0x180004e89  mov     rcx, [rdi]
0x180004e8c  test    rcx, rcx
0x180004e8f  jz      short loc_180004E9D
0x180004e91  mov     rax, [rcx]
0x180004e94  mov     rax, [rax+10h]
0x180004e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e9d  mov     [rdi], rbx
0x180004ea0  mov     rax, rdi
0x180004ea3  mov     rbx, [rsp+28h+arg_0]
0x180004ea8  add     rsp, 20h
0x180004eac  pop     rdi
0x180004ead  retn
```
