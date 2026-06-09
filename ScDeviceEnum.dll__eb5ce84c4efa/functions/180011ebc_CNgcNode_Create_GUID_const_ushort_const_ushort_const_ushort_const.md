# CNgcNode::Create(_GUID const &,ushort const *,ushort const *,ushort const *)

- ea: `0x180011ebc`
- end: `0x18001203d`
- name: `?Create@CNgcNode@@SAJAEBU_GUID@@PEBG11@Z`
- size: `385`
- prototype: `__int64 __fastcall(GUID *rguid, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000fae0`

## callees

- `0x180008bbc`
- `0x180009840`
- `0x1800119c4`
- `0x180011abc`
- `0x180011e44`
- `0x180011e74`
- `0x180011ebc`
- `0x180012304`
- `0x180012a68`
- `0x180012b70`
- `0x18001e020`

## string_xrefs

- `0x180011ef9`: `CNgcNode::Create`

## pseudocode

```c
__int64 __fastcall CNgcNode::Create(
        GUID *rguid,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v5; // rdx
  int Node; // ebx
  int v8; // [rsp+30h] [rbp-79h] BYREF
  int v9; // [rsp+34h] [rbp-75h] BYREF
  __int64 v10; // [rsp+38h] [rbp-71h] BYREF
  struct HSWDEVICE__ *v11; // [rsp+40h] [rbp-69h]
  _QWORD v12[2]; // [rsp+48h] [rbp-61h] BYREF
  __int16 v13; // [rsp+58h] [rbp-51h]
  _QWORD *v14; // [rsp+60h] [rbp-49h] BYREF
  __int64 *v15; // [rsp+68h] [rbp-41h] BYREF
  __int16 v16; // [rsp+70h] [rbp-39h]
  _QWORD v17[3]; // [rsp+78h] [rbp-31h] BYREF
  __int64 v18[4]; // [rsp+90h] [rbp-19h] BYREF
  char v19[24]; // [rsp+B0h] [rbp+7h] BYREF

  v8 = 0;
  v9 = 0;
  strcpy(v19, "CNgcNode::Create");
  v17[0] = v19;
  v17[1] = &v9;
  v17[2] = &v8;
  lambda_49814db34b3fe9e8c4081c346b960d47_::operator()(v17);
  v9 = 1;
  v14 = v17;
  v10 = (__int64)&Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::`vftable';
  v11 = 0;
  v18[3] = 7;
  v18[2] = 0;
  LOWORD(v18[0]) = 0;
  Node = CNgcNode::_CreateNode(rguid, (__int64)&v10, (__int64)v18);
  v8 = Node;
  if ( Node >= 0 )
  {
    v12[0] = &v10;
    v12[1] = v18;
    v13 = 258;
    Node = CNgcNode::_SetupInterface(v11, rguid);
    v8 = Node;
    if ( Node >= 0 )
    {
      Node = CNgcNode::_SetLifetime(v11, 1);
      v8 = Node;
      if ( Node >= 0 )
      {
        v15 = &v10;
        v16 = 2;
        HIBYTE(v13) = 0;
        wil::details::ScopeExitFnGuard__lambda_4d0273268d281c1b94f3252edd42a67f___::operator()(&v15);
      }
    }
    wil::details::ScopeExitFnGuard__lambda_6736b1de380d277c5af6e1a19711af71___::operator()(v12);
  }
  LOBYTE(v5) = 1;
  std::wstring::_Tidy(v18, v5, 0);
  v10 = (__int64)&Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(&v10);
  WppTraceUnwinder__lambda_49814db34b3fe9e8c4081c346b960d47____::_WppTraceUnwinder__lambda_49814db34b3fe9e8c4081c346b960d47____(&v14);
  return (unsigned int)Node;
}

```

## disassembly

```asm
0x180011ebc  push    rbp
0x180011ebe  push    rbx
0x180011ebf  push    rsi
0x180011ec0  push    rdi
0x180011ec1  push    r13
0x180011ec3  push    r14
0x180011ec5  lea     rbp, [rsp-2Fh]
0x180011eca  sub     rsp, 0D8h
0x180011ed1  mov     rax, cs:__security_cookie
0x180011ed8  xor     rax, rsp
0x180011edb  mov     [rbp+57h+var_38], rax
0x180011edf  mov     rsi, r9
0x180011ee2  mov     rdi, r8
0x180011ee5  mov     rbx, rdx
0x180011ee8  mov     r14, rcx
0x180011eeb  mov     [rbp+57h+var_D0], 0
0x180011ef2  mov     [rbp+57h+var_CC], 0
0x180011ef9  movups  xmm0, xmmword ptr cs:aCngcnodeCreate; "CNgcNode::Create"
0x180011f00  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x180011f04  mov     al, byte ptr cs:aCngcnodeCreate+10h; ""
0x180011f0a  mov     [rbp+57h+var_50+10h], al
0x180011f0d  lea     rax, [rbp+57h+var_50]
0x180011f11  mov     [rbp+57h+var_88], rax
0x180011f15  lea     rax, [rbp+57h+var_CC]
0x180011f19  mov     [rbp+57h+var_80], rax
0x180011f1d  lea     rax, [rbp+57h+var_D0]
0x180011f21  mov     [rbp+57h+var_78], rax
0x180011f25  lea     rcx, [rbp+57h+var_88]
0x180011f29  call    _lambda_49814db34b3fe9e8c4081c346b960d47___operator__
0x180011f2e  mov     [rbp+57h+var_CC], 1
0x180011f35  lea     rax, [rbp+57h+var_88]
0x180011f39  mov     [rbp+57h+var_A0], rax
0x180011f3d  lea     r13, ??_7?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::`vftable'
0x180011f44  mov     [rbp+57h+var_C8], r13
0x180011f48  mov     [rbp+57h+var_C0], 0
0x180011f50  mov     [rbp+57h+var_58], 7
0x180011f58  mov     [rbp+57h+var_60], 0
0x180011f60  xor     eax, eax
0x180011f62  mov     word ptr [rbp+57h+var_70], ax
0x180011f66  lea     rax, [rbp+57h+var_70]
0x180011f6a  mov     [rsp+100h+var_D8], rax; __int64
0x180011f6f  lea     rax, [rbp+57h+var_C8]
0x180011f73  mov     [rsp+100h+var_E0], rax; __int64
0x180011f78  mov     r9, rsi
0x180011f7b  mov     r8, rdi
0x180011f7e  mov     rdx, rbx
0x180011f81  mov     rcx, r14; rguid
0x180011f84  call    ?_CreateNode@CNgcNode@@CAJAEBU_GUID@@PEBG11PEAV?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CNgcNode::_CreateNode(_GUID const &,ushort const *,ushort const *,ushort const *,Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits> *,std::wstring *)
0x180011f89  mov     ebx, eax
0x180011f8b  mov     [rbp+57h+var_D0], eax
0x180011f8e  test    eax, eax
0x180011f90  js      short loc_180011FF9
0x180011f92  lea     rax, [rbp+57h+var_C8]
0x180011f96  mov     [rbp+57h+var_B8], rax
0x180011f9a  lea     rax, [rbp+57h+var_70]
0x180011f9e  mov     [rbp+57h+var_B0], rax
0x180011fa2  mov     [rbp+57h+var_A8], 102h
0x180011fa8  mov     rdx, r14; struct _GUID *
0x180011fab  mov     rcx, [rbp+57h+var_C0]; struct HSWDEVICE__ *
0x180011faf  call    ?_SetupInterface@CNgcNode@@CAJPEAUHSWDEVICE__@@AEBU_GUID@@@Z; CNgcNode::_SetupInterface(HSWDEVICE__ *,_GUID const &)
0x180011fb4  mov     ebx, eax
0x180011fb6  mov     [rbp+57h+var_D0], eax
0x180011fb9  test    eax, eax
0x180011fbb  js      short loc_180011FEF
0x180011fbd  mov     edx, 1
0x180011fc2  mov     rcx, [rbp+57h+var_C0]
0x180011fc6  call    ?_SetLifetime@CNgcNode@@CAJPEAUHSWDEVICE__@@W4_SW_DEVICE_LIFETIME@@@Z; CNgcNode::_SetLifetime(HSWDEVICE__ *,_SW_DEVICE_LIFETIME)
0x180011fcb  mov     ebx, eax
0x180011fcd  mov     [rbp+57h+var_D0], eax
0x180011fd0  test    eax, eax
0x180011fd2  js      short loc_180011FEF
0x180011fd4  lea     rax, [rbp+57h+var_C8]
0x180011fd8  mov     [rbp+57h+var_98], rax
0x180011fdc  mov     [rbp+57h+var_90], 2
0x180011fe2  mov     byte ptr [rbp+57h+var_A8+1], 0
0x180011fe6  lea     rcx, [rbp+57h+var_98]
0x180011fea  call    wil__details__ScopeExitFnGuard__lambda_4d0273268d281c1b94f3252edd42a67f_____operator__
0x180011fef  lea     rcx, [rbp+57h+var_B8]
0x180011ff3  call    wil__details__ScopeExitFnGuard__lambda_6736b1de380d277c5af6e1a19711af71_____operator__
0x180011ff8  nop
0x180011ff9  xor     r8d, r8d
0x180011ffc  mov     dl, 1
0x180011ffe  lea     rcx, [rbp+57h+var_70]
0x180012002  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180012007  nop
0x180012008  mov     [rbp+57h+var_C8], r13
0x18001200c  lea     rcx, [rbp+57h+var_C8]
0x180012010  call    ?Close@?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(void)
0x180012015  nop
0x180012016  lea     rcx, [rbp+57h+var_A0]
0x18001201a  call    WppTraceUnwinder__lambda_49814db34b3fe9e8c4081c346b960d47_______WppTraceUnwinder__lambda_49814db34b3fe9e8c4081c346b960d47____
0x18001201f  mov     eax, ebx
0x180012021  mov     rcx, [rbp+57h+var_38]
0x180012025  xor     rcx, rsp; StackCookie
0x180012028  call    __security_check_cookie
0x18001202d  add     rsp, 0D8h
0x180012034  pop     r14
0x180012036  pop     r13
0x180012038  pop     rdi
0x180012039  pop     rsi
0x18001203a  pop     rbx
0x18001203b  pop     rbp
0x18001203c  retn
```
