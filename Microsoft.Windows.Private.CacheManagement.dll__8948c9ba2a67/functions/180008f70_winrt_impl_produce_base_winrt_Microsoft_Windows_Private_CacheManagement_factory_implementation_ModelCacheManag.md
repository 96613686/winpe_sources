# winrt::impl::produce_base<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManagerStatics,void>::Release(void)

- ea: `0x180008f70`
- end: `0x180008fc4`
- name: `?Release@?$produce_base@UModelCacheManager@factory_implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIModelCacheManagerStatics@34567@X@impl@winrt@@UEAAIXZ`
- size: `84`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180008f70`
- `0x180009b70`
- `0x18001cdf0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManagerStatics,void>::Release(
        __int64 a1)
{
  _QWORD *v1; // rbx
  __int64 result; // rax
  unsigned int v3; // edi

  v1 = (_QWORD *)(a1 - 24);
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
0x180008f70  mov     [rsp+arg_8], rbx
0x180008f75  push    rdi
0x180008f76  sub     rsp, 20h
0x180008f7a  xor     eax, eax
0x180008f7c  lea     rbx, [rcx-18h]
0x180008f80  test    rcx, rcx
0x180008f83  cmovz   rbx, rax
0x180008f87  mov     rcx, rbx
0x180008f8a  call    ?subtract_final_reference@?$root_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U134567@UIModelCacheManager2@34567@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(void)
0x180008f8f  mov     edi, eax
0x180008f91  test    eax, eax
0x180008f93  jnz     short loc_180008FB9
0x180008f95  mov     qword ptr [rbx+8], 1
0x180008f9d  test    rbx, rbx
0x180008fa0  jz      short loc_180008FB9
0x180008fa2  mov     r8, [rbx]
0x180008fa5  mov     edx, 1
0x180008faa  mov     rcx, rbx
0x180008fad  mov     rax, [r8+8]
0x180008fb1  call    cs:__guard_dispatch_icall_fptr
0x180008fb7  mov     eax, edi
0x180008fb9  mov     rbx, [rsp+28h+arg_8]
0x180008fbe  add     rsp, 20h
0x180008fc2  pop     rdi
0x180008fc3  retn
```
