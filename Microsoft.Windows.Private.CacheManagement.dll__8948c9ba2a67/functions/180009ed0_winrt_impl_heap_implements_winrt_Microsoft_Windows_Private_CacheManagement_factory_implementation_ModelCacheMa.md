# winrt::impl::heap_implements<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager>::`vector deleting destructor'(uint)

- ea: `0x180009ed0`
- end: `0x180009f22`
- name: `??_E?$heap_implements@UModelCacheManager@factory_implementation@CacheManagement@Private@Windows@Microsoft@winrt@@@impl@winrt@@UEAAPEAXI@Z`
- size: `82`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180009b70`
- `0x180009ed0`
- `0x180018238`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180009f1b`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180009f1b`

## pseudocode

```c
void *__fastcall winrt::impl::heap_implements<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager>::`vector deleting destructor'(
        void *a1,
        char a2)
{
  winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(a1);
  if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
    abort();
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180009ed0  mov     [rsp+arg_8], rbx
0x180009ed5  push    rdi
0x180009ed6  sub     rsp, 20h
0x180009eda  mov     edi, edx
0x180009edc  mov     rbx, rcx
0x180009edf  call    ?subtract_final_reference@?$root_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U134567@UIModelCacheManager2@34567@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(void)
0x180009ee4  mov     eax, 0FFFFFFFFh
0x180009ee9  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180009ef1  sub     eax, 1
0x180009ef4  jnz     short loc_180009F17
0x180009ef6  test    dil, 1
0x180009efa  jz      short loc_180009F09
0x180009efc  mov     edx, 20h ; ' '; unsigned __int64
0x180009f01  mov     rcx, rbx; void *
0x180009f04  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009f09  mov     rax, rbx
0x180009f0c  mov     rbx, [rsp+28h+arg_8]
0x180009f11  add     rsp, 20h
0x180009f15  pop     rdi
0x180009f16  retn
0x180009f17  test    eax, eax
0x180009f19  jns     short loc_180009EF6
0x180009f1b  call    cs:__imp_abort
```
