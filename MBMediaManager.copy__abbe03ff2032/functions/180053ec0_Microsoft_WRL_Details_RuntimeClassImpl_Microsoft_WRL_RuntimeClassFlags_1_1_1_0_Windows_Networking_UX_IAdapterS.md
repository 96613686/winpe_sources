# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IAdapterStatistics,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180053ec0`
- end: `0x180053f1f`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIAdapterStatistics@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180053a5c`
- `0x180053ec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053ee2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053ee2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IAdapterStatistics,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Networking::UX::IAdapterStatistics,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180053ec0  mov     [rsp+arg_0], rbx
0x180053ec5  push    rdi
0x180053ec6  sub     rsp, 20h
0x180053eca  mov     qword ptr [r8], 0
0x180053ed1  mov     ecx, 20h ; ' '; cb
0x180053ed6  mov     dword ptr [rdx], 0
0x180053edc  mov     rbx, r8
0x180053edf  mov     rdi, rdx
0x180053ee2  call    cs:__imp_CoTaskMemAlloc
0x180053ee8  mov     r8, rax
0x180053eeb  test    rax, rax
0x180053eee  jnz     short loc_180053EF7
0x180053ef0  mov     eax, 8007000Eh
0x180053ef5  jmp     short loc_180053F14
0x180053ef7  lea     rdx, [rsp+28h+arg_8]
0x180053efc  mov     [rsp+28h+arg_8], 0
0x180053f04  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIAdapterStatistics@UX@Networking@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Networking::UX::IAdapterStatistics,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180053f09  mov     dword ptr [rdi], 2
0x180053f0f  xor     eax, eax
0x180053f11  mov     [rbx], r8
0x180053f14  mov     rbx, [rsp+28h+arg_0]
0x180053f19  add     rsp, 20h
0x180053f1d  pop     rdi
0x180053f1e  retn
```
