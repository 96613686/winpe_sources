# Windows::Foundation::Collections::Internal::SimpleVectorView<Windows::Graphics::Imaging::BitmapPixelFormat,Windows::Foundation::Collections::Internal::Vector<Windows::Graphics::Imaging::BitmapPixelFormat,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Graphics::Imaging::BitmapPixelFormat>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Graphics::Imaging::BitmapPixelFormat>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Graphics::Imaging::BitmapPixelFormat,0,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Graphics::Imaging::BitmapPixelFormat>,XWinRT::IntVersionTag,1>::GetIids(ulong *,_GUID * *)

- ea: `0x1800a6490`
- end: `0x1800a64fa`
- name: `?GetIids@?$SimpleVectorView@W4BitmapPixelFormat@Imaging@Graphics@Windows@@V?$Vector@W4BitmapPixelFormat@Imaging@Graphics@Windows@@U?$DefaultEqualityPredicate@W4BitmapPixelFormat@Imaging@Graphics@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@W4BitmapPixelFormat@Imaging@Graphics@Windows@@@6784@U?$VectorOptions@W4BitmapPixelFormat@Imaging@Graphics@Windows@@$0A@$00$0A@@6784@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@W4BitmapPixelFormat@Imaging@Graphics@Windows@@@6784@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a6500`

## callees

- `0x1800a563c`
- `0x1800a6490`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a64b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a64b2`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleVectorView<enum Windows::Graphics::Imaging::BitmapPixelFormat,Windows::Foundation::Collections::Internal::Vector<enum Windows::Graphics::Imaging::BitmapPixelFormat,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<enum Windows::Graphics::Imaging::BitmapPixelFormat>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Graphics::Imaging::BitmapPixelFormat>,Windows::Foundation::Collections::Internal::VectorOptions<enum Windows::Graphics::Imaging::BitmapPixelFormat,0,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Graphics::Imaging::BitmapPixelFormat>,XWinRT::IntVersionTag,1>::GetIids(
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
  *v5 = GUID_76ac4bc2_c19c_559c_b287_1694c0dc3a0d;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<enum Windows::Graphics::Imaging::BitmapPixelFormat>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x1800a6490  mov     [rsp+arg_0], rbx
0x1800a6495  push    rdi
0x1800a6496  sub     rsp, 20h
0x1800a649a  mov     qword ptr [r8], 0
0x1800a64a1  mov     ecx, 30h ; '0'; cb
0x1800a64a6  mov     dword ptr [rdx], 0
0x1800a64ac  mov     rbx, r8
0x1800a64af  mov     rdi, rdx
0x1800a64b2  call    cs:__imp_CoTaskMemAlloc
0x1800a64b8  mov     r8, rax
0x1800a64bb  test    rax, rax
0x1800a64be  jnz     short loc_1800A64C7
0x1800a64c0  mov     eax, 8007000Eh
0x1800a64c5  jmp     short loc_1800A64EF
0x1800a64c7  movups  xmm0, xmmword ptr cs:_GUID_76ac4bc2_c19c_559c_b287_1694c0dc3a0d.Data1
0x1800a64ce  lea     rdx, [rsp+28h+arg_8]
0x1800a64d3  mov     [rsp+28h+arg_8], 1
0x1800a64db  movdqu  xmmword ptr [rax], xmm0
0x1800a64df  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@W4BitmapPixelFormat@Imaging@Graphics@Windows@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Graphics::Imaging::BitmapPixelFormat>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800a64e4  mov     dword ptr [rdi], 3
0x1800a64ea  xor     eax, eax
0x1800a64ec  mov     [rbx], r8
0x1800a64ef  mov     rbx, [rsp+28h+arg_0]
0x1800a64f4  add     rsp, 20h
0x1800a64f8  pop     rdi
0x1800a64f9  retn
```
