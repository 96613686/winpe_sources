# Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Docking::VirtualInput::ITouch,Docking::VirtualInput::IVirtualTouchpadDriver,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Docking::VirtualInput::ITouch,Docking::VirtualInput::IVirtualTouchpadDriver,Microsoft::WRL::FtmBase> *,ulong *,_GUID * *)

- ea: `0x18000b824`
- end: `0x18000b8c7`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UITouch@VirtualInput@Docking@@UIVirtualTouchpadDriver@56@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UITouch@VirtualInput@Docking@@UIVirtualTouchpadDriver@56@VFtmBase@23@@123@PEAKPEAPEAU_GUID@@@Z`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e1a0`

## callees

- `0x18000b824`
- `0x18000df30`
- `0x18000e16c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b872`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b872`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Docking::VirtualInput::ITouch,Docking::VirtualInput::IVirtualTouchpadDriver,Microsoft::WRL::FtmBase>>(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3)
{
  unsigned int IidCount; // [rsp+20h] [rbp-18h]
  int v5; // [rsp+24h] [rbp-14h] BYREF
  LPVOID v6; // [rsp+28h] [rbp-10h]

  *a3 = 0;
  *a2 = 0;
  IidCount = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Docking::VirtualInput::ITouch,IWeakReferenceSource,Docking::VirtualInput::IVirtualTouchpadDriver,Microsoft::WRL::FtmBase>::GetIidCount(a1);
  if ( !IidCount )
    return 0;
  v6 = CoTaskMemAlloc(16LL * IidCount);
  if ( !v6 )
    return 2147942414LL;
  v5 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Docking::VirtualInput::ITouch,IWeakReferenceSource,Docking::VirtualInput::IVirtualTouchpadDriver,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    a1,
    &v5,
    v6);
  *a2 = IidCount;
  *a3 = v6;
  return 0;
}

```

## disassembly

```asm
0x18000b824  mov     [rsp+arg_10], r8
0x18000b829  mov     [rsp+arg_8], rdx
0x18000b82e  mov     [rsp+arg_0], rcx
0x18000b833  sub     rsp, 38h
0x18000b837  mov     rax, [rsp+38h+arg_10]
0x18000b83c  mov     qword ptr [rax], 0
0x18000b843  mov     rax, [rsp+38h+arg_8]
0x18000b848  mov     dword ptr [rax], 0
0x18000b84e  mov     rcx, [rsp+38h+arg_0]
0x18000b853  call    ?GetIidCount@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UITouch@VirtualInput@Docking@@UIWeakReferenceSource@@UIVirtualTouchpadDriver@56@VFtmBase@23@@Details@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Docking::VirtualInput::ITouch,IWeakReferenceSource,Docking::VirtualInput::IVirtualTouchpadDriver,Microsoft::WRL::FtmBase>::GetIidCount(void)
0x18000b858  mov     [rsp+38h+var_18], eax
0x18000b85c  cmp     [rsp+38h+var_18], 0
0x18000b861  jnz     short loc_18000B867
0x18000b863  xor     eax, eax
0x18000b865  jmp     short loc_18000B8C2
0x18000b867  mov     eax, [rsp+38h+var_18]
0x18000b86b  imul    rax, 10h
0x18000b86f  mov     rcx, rax; cb
0x18000b872  call    cs:__imp_CoTaskMemAlloc
0x18000b878  mov     [rsp+38h+var_10], rax
0x18000b87d  cmp     [rsp+38h+var_10], 0
0x18000b883  jnz     short loc_18000B88C
0x18000b885  mov     eax, 8007000Eh
0x18000b88a  jmp     short loc_18000B8C2
0x18000b88c  mov     [rsp+38h+var_14], 0
0x18000b894  mov     r8, [rsp+38h+var_10]
0x18000b899  lea     rdx, [rsp+38h+var_14]
0x18000b89e  mov     rcx, [rsp+38h+arg_0]
0x18000b8a3  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UITouch@VirtualInput@Docking@@UIWeakReferenceSource@@UIVirtualTouchpadDriver@56@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Docking::VirtualInput::ITouch,IWeakReferenceSource,Docking::VirtualInput::IVirtualTouchpadDriver,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18000b8a8  mov     rax, [rsp+38h+arg_8]
0x18000b8ad  mov     ecx, [rsp+38h+var_18]
0x18000b8b1  mov     [rax], ecx
0x18000b8b3  mov     rax, [rsp+38h+arg_10]
0x18000b8b8  mov     rcx, [rsp+38h+var_10]
0x18000b8bd  mov     [rax], rcx
0x18000b8c0  xor     eax, eax
0x18000b8c2  add     rsp, 38h
0x18000b8c6  retn
```
