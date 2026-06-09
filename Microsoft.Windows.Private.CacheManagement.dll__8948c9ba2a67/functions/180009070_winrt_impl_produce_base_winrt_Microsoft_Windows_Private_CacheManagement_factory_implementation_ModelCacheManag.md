# winrt::impl::produce_base<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Windows::Foundation::IActivationFactory,void>::Release(void)

- ea: `0x180009070`
- end: `0x1800090c4`
- name: `?Release@?$produce_base@UModelCacheManager@factory_implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@57@X@impl@winrt@@UEAAIXZ`
- size: `84`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009070`
- `0x180009b70`
- `0x18001cdf0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Windows::Foundation::IActivationFactory,void>::Release(
        __int64 a1)
{
  _QWORD *v1; // rbx
  __int64 result; // rax
  unsigned int v3; // edi

  v1 = (_QWORD *)(a1 - 16);
  if ( !a1 )
    v1 = 0;
  result = winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(v1);
  v3 = result;
  if ( !(_DWORD)result )
  {
    v1[1] = 1;
    if ( v1 )
    {
      (*(void (__fastcall **)(_QWORD *, __int64))(*v1 + 8LL))(v1, 1);
      return v3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009070  mov     [rsp+arg_8], rbx
0x180009075  push    rdi
0x180009076  sub     rsp, 20h
0x18000907a  xor     eax, eax
0x18000907c  lea     rbx, [rcx-10h]
0x180009080  test    rcx, rcx
0x180009083  cmovz   rbx, rax
0x180009087  mov     rcx, rbx
0x18000908a  call    ?subtract_final_reference@?$root_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U134567@UIModelCacheManager2@34567@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(void)
0x18000908f  mov     edi, eax
0x180009091  test    eax, eax
0x180009093  jnz     short loc_1800090B9
0x180009095  mov     qword ptr [rbx+8], 1
0x18000909d  test    rbx, rbx
0x1800090a0  jz      short loc_1800090B9
0x1800090a2  mov     r8, [rbx]
0x1800090a5  mov     edx, 1
0x1800090aa  mov     rcx, rbx
0x1800090ad  mov     rax, [r8+8]
0x1800090b1  call    cs:__guard_dispatch_icall_fptr
0x1800090b7  mov     eax, edi
0x1800090b9  mov     rbx, [rsp+28h+arg_8]
0x1800090be  add     rsp, 20h
0x1800090c2  pop     rdi
0x1800090c3  retn
```
