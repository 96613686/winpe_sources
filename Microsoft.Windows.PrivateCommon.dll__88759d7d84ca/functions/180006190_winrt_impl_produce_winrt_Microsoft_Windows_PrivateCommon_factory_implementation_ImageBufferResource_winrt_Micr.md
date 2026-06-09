# winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::CreateInstance(winrt::impl::struct_Microsoft_Windows_PrivateCommon_ImageBufferData,void * *)

- ea: `0x180006190`
- end: `0x180006237`
- name: `?CreateInstance@?$produce@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResourceFactory@3456@@impl@winrt@@UEAAHUstruct_Microsoft_Windows_PrivateCommon_ImageBufferData@23@PEAPEAX@Z`
- size: `167`
- prototype: `__int64 __fastcall(__int64, _OWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005e50`
- `0x180006190`
- `0x1800072a0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::CreateInstance(
        __int64 a1,
        _OWORD *a2,
        _QWORD *a3)
{
  char *v5; // rbx
  char *v6; // rdi
  __int64 result; // rax
  char *v8; // [rsp+20h] [rbp-28h] BYREF

  *a3 = 0;
  try
  {
    v5 = (char *)operator new(0x40u);
    v8 = v5;
    v6 = v5 + 16;
    *((_QWORD *)v5 + 2) = &winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    *((_QWORD *)v5 + 1) = 1;
    *(_QWORD *)v5 = &winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource::`vftable';
    *(_OWORD *)(v5 + 24) = *a2;
    *(_OWORD *)(v5 + 40) = a2[1];
    *((_QWORD *)v5 + 7) = 0;
    winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource::ValidateSharedMemorySection((winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource *)v5);
    *(_QWORD *)v5 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource>::`vftable';
    if ( !v5 )
      v6 = 0;
    *a3 = v6;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v8);
  }
  return result;
}

```

## disassembly

```asm
0x180006190  mov     [rsp+arg_0], rbx
0x180006195  mov     [rsp+arg_8], rsi
0x18000619a  push    rdi
0x18000619b  push    r14
0x18000619d  push    r15
0x18000619f  sub     rsp, 30h
0x1800061a3  mov     rsi, r8
0x1800061a6  mov     r14, rdx
0x1800061a9  xor     r15d, r15d
0x1800061ac  mov     [r8], r15
0x1800061af  mov     ecx, 40h ; '@'; Size
0x1800061b4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800061b9  mov     rbx, rax
0x1800061bc  mov     [rsp+48h+var_28], rax
0x1800061c1  lea     rdi, [rax+10h]
0x1800061c5  lea     rax, ??_7?$produce@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResource@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::`vftable'
0x1800061cc  mov     [rdi], rax
0x1800061cf  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800061d6  mov     qword ptr [rbx+8], 1
0x1800061de  lea     rax, ??_7ImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@6B@; const winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource::`vftable'
0x1800061e5  mov     [rbx], rax
0x1800061e8  movups  xmm0, xmmword ptr [r14]
0x1800061ec  movups  xmmword ptr [rbx+18h], xmm0
0x1800061f0  movups  xmm1, xmmword ptr [r14+10h]
0x1800061f5  movups  xmmword ptr [rbx+28h], xmm1
0x1800061f9  mov     [rbx+38h], r15
0x1800061fd  mov     rcx, rbx; this
0x180006200  call    ?ValidateSharedMemorySection@ImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@AEAAXXZ; winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource::ValidateSharedMemorySection(void)
0x180006205  nop
0x180006206  lea     rax, ??_7?$heap_implements@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource>::`vftable'
0x18000620d  mov     [rbx], rax
0x180006210  test    rbx, rbx
0x180006213  cmovz   rdi, r15
0x180006217  mov     [rsi], rdi
0x18000621a  xor     eax, eax
0x18000621c  jmp     short loc_180006222
0x18000621e  mov     eax, dword ptr [rsp+48h+var_28]
0x180006222  mov     rbx, [rsp+48h+arg_0]
0x180006227  mov     rsi, [rsp+48h+arg_8]
0x18000622c  add     rsp, 30h
0x180006230  pop     r15
0x180006232  pop     r14
0x180006234  pop     rdi
0x180006235  retn
```
