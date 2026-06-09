# Windows::Foundation::Collections::Internal::Vector<IUnknown *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IUnknown *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IUnknown *>,Windows::Foundation::Collections::Internal::VectorOptions<IUnknown *,0,1,0>>::GetIids(ulong *,_GUID * *)

- ea: `0x180039090`
- end: `0x1800390fa`
- name: `?GetIids@?$Vector@PEAUIUnknown@@U?$DefaultEqualityPredicate@PEAUIUnknown@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIUnknown@@@3456@U?$VectorOptions@PEAUIUnknown@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180039100`

## callees

- `0x180038b6c`
- `0x180039090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800390b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800390b2`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<IUnknown *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IUnknown *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IUnknown *>,Windows::Foundation::Collections::Internal::VectorOptions<IUnknown *,0,1,0>>::GetIids(
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
  *v5 = GUID_075f425f_afd9_5492_bafc_a7e3c98b08c3;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<IUnknown *>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x180039090  mov     [rsp+arg_0], rbx
0x180039095  push    rdi
0x180039096  sub     rsp, 20h
0x18003909a  mov     qword ptr [r8], 0
0x1800390a1  mov     ecx, 30h ; '0'; cb
0x1800390a6  mov     dword ptr [rdx], 0
0x1800390ac  mov     rbx, r8
0x1800390af  mov     rdi, rdx
0x1800390b2  call    cs:__imp_CoTaskMemAlloc
0x1800390b8  mov     r8, rax
0x1800390bb  test    rax, rax
0x1800390be  jnz     short loc_1800390C7
0x1800390c0  mov     eax, 8007000Eh
0x1800390c5  jmp     short loc_1800390EF
0x1800390c7  movups  xmm0, xmmword ptr cs:_GUID_075f425f_afd9_5492_bafc_a7e3c98b08c3.Data1
0x1800390ce  lea     rdx, [rsp+28h+arg_8]
0x1800390d3  mov     [rsp+28h+arg_8], 1
0x1800390db  movdqu  xmmword ptr [rax], xmm0
0x1800390df  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@PEAUIUnknown@@@Collections@Foundation@Windows@@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<IUnknown *>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800390e4  mov     dword ptr [rdi], 3
0x1800390ea  xor     eax, eax
0x1800390ec  mov     [rbx], r8
0x1800390ef  mov     rbx, [rsp+28h+arg_0]
0x1800390f4  add     rsp, 20h
0x1800390f8  pop     rdi
0x1800390f9  retn
```
