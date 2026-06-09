# Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Docking::VirtualInput::IVirtualInputManager,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Docking::VirtualInput::IVirtualInputManager,Microsoft::WRL::FtmBase> *,ulong *,_GUID * *)

- ea: `0x18000b8d0`
- end: `0x18000b973`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIVirtualInputManager@VirtualInput@Docking@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIVirtualInputManager@VirtualInput@Docking@@VFtmBase@23@@123@PEAKPEAPEAU_GUID@@@Z`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e1f0`

## callees

- `0x18000b8d0`
- `0x18000dfa0`
- `0x18000e144`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b91e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b91e`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Docking::VirtualInput::IVirtualInputManager,Microsoft::WRL::FtmBase>>(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3)
{
  unsigned int IidCount; // [rsp+20h] [rbp-18h]
  int v5; // [rsp+24h] [rbp-14h] BYREF
  LPVOID v6; // [rsp+28h] [rbp-10h]

  *a3 = 0;
  *a2 = 0;
  IidCount = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Docking::VirtualInput::IVirtualInputManager,IWeakReferenceSource,Microsoft::WRL::FtmBase>::GetIidCount(a1);
  if ( !IidCount )
    return 0;
  v6 = CoTaskMemAlloc(16LL * IidCount);
  if ( !v6 )
    return 2147942414LL;
  v5 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Docking::VirtualInput::IVirtualInputManager,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18000b8d0  mov     [rsp+arg_10], r8
0x18000b8d5  mov     [rsp+arg_8], rdx
0x18000b8da  mov     [rsp+arg_0], rcx
0x18000b8df  sub     rsp, 38h
0x18000b8e3  mov     rax, [rsp+38h+arg_10]
0x18000b8e8  mov     qword ptr [rax], 0
0x18000b8ef  mov     rax, [rsp+38h+arg_8]
0x18000b8f4  mov     dword ptr [rax], 0
0x18000b8fa  mov     rcx, [rsp+38h+arg_0]
0x18000b8ff  call    ?GetIidCount@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIVirtualInputManager@VirtualInput@Docking@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Docking::VirtualInput::IVirtualInputManager,IWeakReferenceSource,Microsoft::WRL::FtmBase>::GetIidCount(void)
0x18000b904  mov     [rsp+38h+var_18], eax
0x18000b908  cmp     [rsp+38h+var_18], 0
0x18000b90d  jnz     short loc_18000B913
0x18000b90f  xor     eax, eax
0x18000b911  jmp     short loc_18000B96E
0x18000b913  mov     eax, [rsp+38h+var_18]
0x18000b917  imul    rax, 10h
0x18000b91b  mov     rcx, rax; cb
0x18000b91e  call    cs:__imp_CoTaskMemAlloc
0x18000b924  mov     [rsp+38h+var_10], rax
0x18000b929  cmp     [rsp+38h+var_10], 0
0x18000b92f  jnz     short loc_18000B938
0x18000b931  mov     eax, 8007000Eh
0x18000b936  jmp     short loc_18000B96E
0x18000b938  mov     [rsp+38h+var_14], 0
0x18000b940  mov     r8, [rsp+38h+var_10]
0x18000b945  lea     rdx, [rsp+38h+var_14]
0x18000b94a  mov     rcx, [rsp+38h+arg_0]
0x18000b94f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIVirtualInputManager@VirtualInput@Docking@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Docking::VirtualInput::IVirtualInputManager,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18000b954  mov     rax, [rsp+38h+arg_8]
0x18000b959  mov     ecx, [rsp+38h+var_18]
0x18000b95d  mov     [rax], ecx
0x18000b95f  mov     rax, [rsp+38h+arg_10]
0x18000b964  mov     rcx, [rsp+38h+var_10]
0x18000b969  mov     [rax], rcx
0x18000b96c  xor     eax, eax
0x18000b96e  add     rsp, 38h
0x18000b972  retn
```
