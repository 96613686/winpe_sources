# WpcDesktop::OTS::Manager::WpcOtsTimeRequest::WpcOtsTimeRequest(WpcDesktop::OTS::Manager::RequestManagerDependencies const &,std::shared_ptr<Com::InterfaceMarshaler<IWpcOtsRequestManager>>,Sid const &)

- ea: `0x18000b808`
- end: `0x18000b9c2`
- name: `??0WpcOtsTimeRequest@Manager@OTS@WpcDesktop@@QEAA@AEBURequestManagerDependencies@123@V?$shared_ptr@V?$InterfaceMarshaler@UIWpcOtsRequestManager@@@Com@@@std@@AEBVSid@@@Z`
- size: `442`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b6e0`

## callees

- `0x1800032a0`
- `0x180005a04`
- `0x180005b38`
- `0x180005f9c`
- `0x18000b808`
- `0x18000dc7c`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WpcDesktop::OTS::Manager::WpcOtsTimeRequest::WpcOtsTimeRequest(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4)
{
  char v8; // si
  __int64 v9; // rax
  _QWORD *v10; // r9
  volatile signed __int32 *v11; // rbx
  _QWORD v13[4]; // [rsp+38h] [rbp-50h] BYREF

  v8 = 0;
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)a1);
  *(_DWORD *)(a1 + 44) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IWpcOtsTimeRequest>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWpcOtsTimeRequest>>'};
  *(_QWORD *)(a1 + 32) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IWpcOtsTimeRequest>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWpcOtsTimeRequest>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWpcOtsTimeRequest>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)a1 = &WpcDesktop::OTS::Manager::WpcOtsTimeRequest::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWpcOtsTimeRequest>>'};
  *(_QWORD *)(a1 + 32) = &WpcDesktop::OTS::Manager::WpcOtsTimeRequest::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWpcOtsTimeRequest>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWpcOtsTimeRequest>>'};
  *(_OWORD *)(a1 + 48) = *(_OWORD *)a4;
  *(_OWORD *)(a1 + 64) = *(_OWORD *)(a4 + 16);
  *(_OWORD *)(a1 + 80) = *(_OWORD *)(a4 + 32);
  *(_OWORD *)(a1 + 96) = *(_OWORD *)(a4 + 48);
  *(_DWORD *)(a1 + 112) = *(_DWORD *)(a4 + 64);
  std::wstring::wstring(a1 + 120, a4 + 72);
  *(_QWORD *)(a1 + 152) = a2;
  *(_QWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 168) = 0;
  v9 = a3[1];
  if ( v9 )
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
  *(_QWORD *)(a1 + 160) = *a3;
  *(_QWORD *)(a1 + 168) = a3[1];
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
  {
    std::wstring::wstring((__int64)v13, a4 + 72);
    v8 = 3;
    v10 = v13;
    if ( v13[3] > 7u )
      v10 = (_QWORD *)v13[0];
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, &WPP_dc195e4bdbd63c33a4e68728034627b2_Traceguids, v10);
  }
  if ( (v8 & 1) != 0 )
    std::wstring::~wstring(v13);
  v11 = (volatile signed __int32 *)a3[1];
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18000b808  push    rbx
0x18000b80a  push    rbp
0x18000b80b  push    rsi
0x18000b80c  push    rdi
0x18000b80d  push    r14
0x18000b80f  sub     rsp, 60h
0x18000b813  mov     rax, cs:__security_cookie
0x18000b81a  xor     rax, rsp
0x18000b81d  mov     [rsp+88h+var_30], rax
0x18000b822  mov     rbp, r9
0x18000b825  mov     rbx, r8
0x18000b828  mov     r14, rdx
0x18000b82b  mov     rdi, rcx
0x18000b82e  mov     [rsp+88h+var_60], rcx
0x18000b833  mov     [rsp+88h+var_58], rbx
0x18000b838  xor     esi, esi
0x18000b83a  mov     [rsp+88h+var_68], esi
0x18000b83e  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000b843  mov     dword ptr [rdi+2Ch], 1
0x18000b84a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VFtmBase@23@UIWpcOtsTimeRequest@@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWpcOtsTimeRequest@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IWpcOtsTimeRequest>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWpcOtsTimeRequest>>'}
0x18000b851  mov     [rdi], rax
0x18000b854  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VFtmBase@23@UIWpcOtsTimeRequest@@@WRL@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIWpcOtsTimeRequest@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWpcOtsTimeRequest@@@234@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IWpcOtsTimeRequest>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWpcOtsTimeRequest>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWpcOtsTimeRequest>>'}
0x18000b85b  mov     [rdi+20h], rax
0x18000b85f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000b866  test    rcx, rcx
0x18000b869  jz      short loc_18000B878
0x18000b86b  mov     rax, [rcx]
0x18000b86e  mov     rax, [rax+8]
0x18000b872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b877  nop
0x18000b878  lea     rax, ??_7WpcOtsTimeRequest@Manager@OTS@WpcDesktop@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWpcOtsTimeRequest@@@Details@23@@Details@WRL@Microsoft@@@; const WpcDesktop::OTS::Manager::WpcOtsTimeRequest::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWpcOtsTimeRequest>>'}
0x18000b87f  mov     [rdi], rax
0x18000b882  lea     rax, ??_7WpcOtsTimeRequest@Manager@OTS@WpcDesktop@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIWpcOtsTimeRequest@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWpcOtsTimeRequest@@@234@@Details@WRL@Microsoft@@@; const WpcDesktop::OTS::Manager::WpcOtsTimeRequest::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWpcOtsTimeRequest>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWpcOtsTimeRequest>>'}
0x18000b889  mov     [rdi+20h], rax
0x18000b88d  movups  xmm0, xmmword ptr [rbp+0]
0x18000b891  movups  xmmword ptr [rdi+30h], xmm0
0x18000b895  movups  xmm1, xmmword ptr [rbp+10h]
0x18000b899  movups  xmmword ptr [rdi+40h], xmm1
0x18000b89d  movups  xmm0, xmmword ptr [rbp+20h]
0x18000b8a1  movups  xmmword ptr [rdi+50h], xmm0
0x18000b8a5  movups  xmm1, xmmword ptr [rbp+30h]
0x18000b8a9  movups  xmmword ptr [rdi+60h], xmm1
0x18000b8ad  mov     eax, [rbp+40h]
0x18000b8b0  mov     [rdi+70h], eax
0x18000b8b3  lea     rcx, [rdi+78h]
0x18000b8b7  lea     rdx, [rbp+48h]
0x18000b8bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000b8c0  nop
0x18000b8c1  mov     [rdi+98h], r14
0x18000b8c8  mov     qword ptr [rdi+0A0h], 0
0x18000b8d3  mov     qword ptr [rdi+0A8h], 0
0x18000b8de  mov     rax, [rbx+8]
0x18000b8e2  test    rax, rax
0x18000b8e5  jz      short loc_18000B8EB
0x18000b8e7  lock inc dword ptr [rax+8]
0x18000b8eb  mov     rax, [rbx]
0x18000b8ee  mov     [rdi+0A0h], rax
0x18000b8f5  mov     rax, [rbx+8]
0x18000b8f9  mov     [rdi+0A8h], rax
0x18000b900  lea     rcx, WPP_GLOBAL_Control
0x18000b907  mov     rax, cs:WPP_GLOBAL_Control
0x18000b90e  cmp     rax, rcx
0x18000b911  jz      short loc_18000B957
0x18000b913  test    byte ptr [rax+1Ch], 8
0x18000b917  jz      short loc_18000B957
0x18000b919  lea     rdx, [rbp+48h]
0x18000b91d  lea     rcx, [rsp+88h+var_50]
0x18000b922  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000b927  mov     esi, 3
0x18000b92c  lea     r9, [rsp+88h+var_50]
0x18000b931  cmp     [rsp+88h+var_38], 7
0x18000b937  cmova   r9, [rsp+88h+var_50]
0x18000b93d  lea     edx, [rsi+7]
0x18000b940  lea     r8, WPP_dc195e4bdbd63c33a4e68728034627b2_Traceguids
0x18000b947  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b94e  mov     rcx, [rcx+10h]
0x18000b952  call    WPP_SF_S
0x18000b957  test    sil, 1
0x18000b95b  jz      short loc_18000B968
0x18000b95d  lea     rcx, [rsp+88h+var_50]
0x18000b962  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b967  nop
0x18000b968  mov     rbx, [rbx+8]
0x18000b96c  test    rbx, rbx
0x18000b96f  jz      short loc_18000B9A7
0x18000b971  or      esi, 0FFFFFFFFh
0x18000b974  mov     eax, esi
0x18000b976  lock xadd [rbx+8], eax
0x18000b97b  add     eax, esi
0x18000b97d  jnz     short loc_18000B9A7
0x18000b97f  mov     rax, [rbx]
0x18000b982  mov     rcx, rbx
0x18000b985  mov     rax, [rax]
0x18000b988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b98d  mov     edx, esi
0x18000b98f  lock xadd [rbx+0Ch], edx
0x18000b994  add     edx, esi
0x18000b996  jnz     short loc_18000B9A7
0x18000b998  mov     rdx, [rbx]
0x18000b99b  mov     rcx, rbx
0x18000b99e  mov     rax, [rdx+8]
0x18000b9a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9a7  mov     rax, rdi
0x18000b9aa  mov     rcx, [rsp+88h+var_30]
0x18000b9af  xor     rcx, rsp; StackCookie
0x18000b9b2  call    __security_check_cookie
0x18000b9b7  add     rsp, 60h
0x18000b9bb  pop     r14
0x18000b9bd  pop     rdi
0x18000b9be  pop     rsi
0x18000b9bf  pop     rbp
0x18000b9c0  pop     rbx
0x18000b9c1  retn
```
