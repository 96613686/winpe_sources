# Windows::Foundation::Collections::Internal::SimpleVectorIterator<Windows::Graphics::Imaging::BitmapPixelFormat,Windows::Foundation::Collections::Internal::Vector<Windows::Graphics::Imaging::BitmapPixelFormat,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Graphics::Imaging::BitmapPixelFormat>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Graphics::Imaging::BitmapPixelFormat>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Graphics::Imaging::BitmapPixelFormat,0,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Graphics::Imaging::BitmapPixelFormat>,XWinRT::IntVersionTag,1>::GetIids(ulong *,_GUID * *)

- ea: `0x1800a6420`
- end: `0x1800a647f`
- name: `?GetIids@?$SimpleVectorIterator@W4BitmapPixelFormat@Imaging@Graphics@Windows@@V?$Vector@W4BitmapPixelFormat@Imaging@Graphics@Windows@@U?$DefaultEqualityPredicate@W4BitmapPixelFormat@Imaging@Graphics@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@W4BitmapPixelFormat@Imaging@Graphics@Windows@@@6784@U?$VectorOptions@W4BitmapPixelFormat@Imaging@Graphics@Windows@@$0A@$00$0A@@6784@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@W4BitmapPixelFormat@Imaging@Graphics@Windows@@@6784@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800a566c`
- `0x1800a6420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a6442`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a6442`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleVectorIterator<enum Windows::Graphics::Imaging::BitmapPixelFormat,Windows::Foundation::Collections::Internal::Vector<enum Windows::Graphics::Imaging::BitmapPixelFormat,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<enum Windows::Graphics::Imaging::BitmapPixelFormat>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Graphics::Imaging::BitmapPixelFormat>,Windows::Foundation::Collections::Internal::VectorOptions<enum Windows::Graphics::Imaging::BitmapPixelFormat,0,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Graphics::Imaging::BitmapPixelFormat>,XWinRT::IntVersionTag,1>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<enum Windows::Graphics::Imaging::BitmapPixelFormat>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x1800a6420  mov     [rsp+arg_0], rbx
0x1800a6425  push    rdi
0x1800a6426  sub     rsp, 20h
0x1800a642a  mov     qword ptr [r8], 0
0x1800a6431  mov     ecx, 20h ; ' '; cb
0x1800a6436  mov     dword ptr [rdx], 0
0x1800a643c  mov     rbx, r8
0x1800a643f  mov     rdi, rdx
0x1800a6442  call    cs:__imp_CoTaskMemAlloc
0x1800a6448  mov     r8, rax
0x1800a644b  test    rax, rax
0x1800a644e  jnz     short loc_1800A6457
0x1800a6450  mov     eax, 8007000Eh
0x1800a6455  jmp     short loc_1800A6474
0x1800a6457  lea     rdx, [rsp+28h+arg_8]
0x1800a645c  mov     [rsp+28h+arg_8], 0
0x1800a6464  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$IIterator@W4BitmapPixelFormat@Imaging@Graphics@Windows@@@Collections@Foundation@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<Windows::Graphics::Imaging::BitmapPixelFormat>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800a6469  mov     dword ptr [rdi], 2
0x1800a646f  xor     eax, eax
0x1800a6471  mov     [rbx], r8
0x1800a6474  mov     rbx, [rsp+28h+arg_0]
0x1800a6479  add     rsp, 20h
0x1800a647d  pop     rdi
0x1800a647e  retn
```
