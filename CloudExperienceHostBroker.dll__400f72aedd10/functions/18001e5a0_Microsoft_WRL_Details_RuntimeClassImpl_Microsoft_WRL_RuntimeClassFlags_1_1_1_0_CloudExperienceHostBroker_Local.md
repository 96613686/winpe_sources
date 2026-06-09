# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,CloudExperienceHostBroker::LocalNgc::ILocalNgcManager,IInspectable,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001e5a0`
- end: `0x18001e60a`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UILocalNgcManager@LocalNgc@CloudExperienceHostBroker@@UIInspectable@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e610`

## callees

- `0x18001e018`
- `0x18001e5a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e5c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e5c2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,CloudExperienceHostBroker::LocalNgc::ILocalNgcManager,IInspectable,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_aa8c2f88_3bdc_4b7b_97ae_8884d0203923;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,IInspectable,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x18001e5a0  mov     [rsp+arg_0], rbx
0x18001e5a5  push    rdi
0x18001e5a6  sub     rsp, 20h
0x18001e5aa  mov     qword ptr [r8], 0
0x18001e5b1  mov     ecx, 30h ; '0'; cb
0x18001e5b6  mov     dword ptr [rdx], 0
0x18001e5bc  mov     rbx, r8
0x18001e5bf  mov     rdi, rdx
0x18001e5c2  call    cs:__imp_CoTaskMemAlloc
0x18001e5c8  mov     r8, rax
0x18001e5cb  test    rax, rax
0x18001e5ce  jnz     short loc_18001E5D7
0x18001e5d0  mov     eax, 8007000Eh
0x18001e5d5  jmp     short loc_18001E5FF
0x18001e5d7  movups  xmm0, xmmword ptr cs:_GUID_aa8c2f88_3bdc_4b7b_97ae_8884d0203923.Data1
0x18001e5de  lea     rdx, [rsp+28h+arg_8]
0x18001e5e3  mov     [rsp+28h+arg_8], 1
0x18001e5eb  movdqu  xmmword ptr [rax], xmm0
0x18001e5ef  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIInspectable@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,IInspectable,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001e5f4  mov     dword ptr [rdi], 3
0x18001e5fa  xor     eax, eax
0x18001e5fc  mov     [rbx], r8
0x18001e5ff  mov     rbx, [rsp+28h+arg_0]
0x18001e604  add     rsp, 20h
0x18001e608  pop     rdi
0x18001e609  retn
```
