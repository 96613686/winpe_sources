# winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::CreateInstance2(uint,uint,int,uint,unsigned __int64,unsigned __int64,void * *)

- ea: `0x1800060b0`
- end: `0x18000618f`
- name: `?CreateInstance2@?$produce@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResourceFactory@3456@@impl@winrt@@UEAAHIIHI_K0PEAPEAX@Z`
- size: `223`
- prototype: `__int64 __fastcall(__int64, int, int, int, int, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005e50`
- `0x1800060b0`
- `0x1800072a0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::CreateInstance2(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8)
{
  _QWORD *v11; // rbx
  char *v12; // rdi
  __int64 result; // rax
  _QWORD *v14; // [rsp+20h] [rbp-28h] BYREF

  *a8 = 0;
  try
  {
    v11 = operator new(0x40u);
    v14 = v11;
    v12 = (char *)(v11 + 2);
    v11[2] = &winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v11[1] = 1;
    *v11 = &winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource::`vftable';
    *((_DWORD *)v11 + 6) = a2;
    *((_DWORD *)v11 + 7) = a3;
    *((_DWORD *)v11 + 8) = a4;
    *((_DWORD *)v11 + 9) = a5;
    v11[5] = a6;
    v11[6] = a7;
    v11[7] = 0;
    winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource::ValidateSharedMemorySection((winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource *)v11);
    *v11 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource>::`vftable';
    if ( !v11 )
      v12 = 0;
    *a8 = v12;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v14);
  }
  return result;
}

```

## disassembly

```asm
0x1800060b0  mov     [rsp+arg_0], rbx
0x1800060b5  mov     [rsp+arg_8], rsi
0x1800060ba  mov     [rsp+arg_10], rdi
0x1800060bf  mov     [rsp+arg_18], r12
0x1800060c4  push    r13
0x1800060c6  push    r14
0x1800060c8  push    r15
0x1800060ca  sub     rsp, 30h
0x1800060ce  mov     r14d, r9d
0x1800060d1  mov     r15d, r8d
0x1800060d4  mov     r12d, edx
0x1800060d7  mov     rsi, [rsp+48h+arg_38]
0x1800060df  xor     r13d, r13d
0x1800060e2  mov     [rsi], r13
0x1800060e5  mov     ecx, 40h ; '@'; Size
0x1800060ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800060ef  mov     rbx, rax
0x1800060f2  mov     [rsp+48h+var_28], rax
0x1800060f7  lea     rdi, [rax+10h]
0x1800060fb  lea     rax, ??_7?$produce@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResource@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::`vftable'
0x180006102  mov     [rdi], rax
0x180006105  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000610c  mov     qword ptr [rbx+8], 1
0x180006114  lea     rax, ??_7ImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@6B@; const winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource::`vftable'
0x18000611b  mov     [rbx], rax
0x18000611e  mov     [rbx+18h], r12d
0x180006122  mov     [rbx+1Ch], r15d
0x180006126  mov     [rbx+20h], r14d
0x18000612a  mov     eax, [rsp+48h+arg_20]
0x18000612e  mov     [rbx+24h], eax
0x180006131  mov     rax, [rsp+48h+arg_28]
0x180006136  mov     [rbx+28h], rax
0x18000613a  mov     rax, [rsp+48h+arg_30]
0x180006142  mov     [rbx+30h], rax
0x180006146  mov     [rbx+38h], r13
0x18000614a  mov     rcx, rbx; this
0x18000614d  call    ?ValidateSharedMemorySection@ImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@AEAAXXZ; winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource::ValidateSharedMemorySection(void)
0x180006152  nop
0x180006153  lea     rax, ??_7?$heap_implements@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource>::`vftable'
0x18000615a  mov     [rbx], rax
0x18000615d  test    rbx, rbx
0x180006160  cmovz   rdi, r13
0x180006164  mov     [rsi], rdi
0x180006167  xor     eax, eax
0x180006169  jmp     short loc_18000616F
0x18000616b  mov     eax, dword ptr [rsp+48h+var_28]
0x18000616f  mov     rbx, [rsp+48h+arg_0]
0x180006174  mov     rsi, [rsp+48h+arg_8]
0x180006179  mov     rdi, [rsp+48h+arg_10]
0x18000617e  mov     r12, [rsp+48h+arg_18]
0x180006183  add     rsp, 30h
0x180006187  pop     r15
0x180006189  pop     r14
0x18000618b  pop     r13
0x18000618d  retn
```
