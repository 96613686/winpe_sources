# winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory>::ActivateInstance(void * *)

- ea: `0x180006370`
- end: `0x1800063fb`
- name: `?ActivateInstance@?$produce@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `139`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006370`
- `0x1800072a0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory>::ActivateInstance(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rcx
  __int64 result; // rax
  _DWORD v6[6]; // [rsp+20h] [rbp-18h] BYREF

  *a2 = 0;
  try
  {
    v3 = operator new(0x40u);
    *v3 = 0;
    v3[1] = 0;
    v3[3] = 0;
    v3[4] = 0;
    v3[5] = 0;
    v3[6] = 0;
    v3[7] = 0;
    v4 = v3 + 2;
    v3[2] = &winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v3[1] = 1;
    *(_OWORD *)(v3 + 3) = 0;
    *(_OWORD *)(v3 + 5) = 0;
    v3[7] = 0;
    *v3 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource>::`vftable';
    if ( !v3 )
      v4 = 0;
    *a2 = v4;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(v6);
  }
  return result;
}

```

## disassembly

```asm
0x180006370  mov     [rsp+arg_0], rbx
0x180006375  push    rdi
0x180006376  sub     rsp, 30h
0x18000637a  mov     rbx, rdx
0x18000637d  xor     edi, edi
0x18000637f  mov     [rdx], rdi
0x180006382  mov     ecx, 40h ; '@'; Size
0x180006387  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000638c  mov     [rax], rdi
0x18000638f  mov     [rax+8], rdi
0x180006393  mov     [rax+18h], rdi
0x180006397  mov     [rax+20h], rdi
0x18000639b  mov     [rax+28h], rdi
0x18000639f  mov     [rax+30h], rdi
0x1800063a3  mov     [rax+38h], rdi
0x1800063a7  lea     rcx, [rax+10h]
0x1800063ab  lea     rdx, ??_7?$produce@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResource@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::`vftable'
0x1800063b2  mov     [rcx], rdx
0x1800063b5  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800063bc  mov     qword ptr [rax+8], 1
0x1800063c4  xorps   xmm0, xmm0
0x1800063c7  movups  xmmword ptr [rax+18h], xmm0
0x1800063cb  movups  xmmword ptr [rax+28h], xmm0
0x1800063cf  mov     [rax+38h], rdi
0x1800063d3  lea     rdx, ??_7?$heap_implements@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource>::`vftable'
0x1800063da  mov     [rax], rdx
0x1800063dd  test    rax, rax
0x1800063e0  cmovz   rcx, rdi
0x1800063e4  mov     [rbx], rcx
0x1800063e7  xor     eax, eax
0x1800063e9  jmp     short loc_1800063EF
0x1800063eb  mov     eax, [rsp+38h+var_18]
0x1800063ef  mov     rbx, [rsp+38h+arg_0]
0x1800063f4  add     rsp, 30h
0x1800063f8  pop     rdi
0x1800063f9  retn
```
