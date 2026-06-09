# winrt::impl::heap_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>::`vector deleting destructor'(uint)

- ea: `0x1800050b0`
- end: `0x1800050e4`
- name: `??_E?$heap_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@@impl@winrt@@UEAAPEAXI@Z`
- size: `52`
- prototype: `winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *__fastcall(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800050b0`
- `0x1800050f0`
- `0x180018238`

## pseudocode

```c
winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *__fastcall winrt::impl::heap_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>::`vector deleting destructor'(
        winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *a1,
        char a2)
{
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::~ModelCacheManager(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800050b0  mov     [rsp+arg_0], rbx
0x1800050b5  push    rdi
0x1800050b6  sub     rsp, 20h
0x1800050ba  mov     ebx, edx
0x1800050bc  mov     rdi, rcx
0x1800050bf  call    ??1ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UEAA@XZ; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::~ModelCacheManager(void)
0x1800050c4  test    bl, 1
0x1800050c7  jz      short loc_1800050D6
0x1800050c9  mov     edx, 120h; unsigned __int64
0x1800050ce  mov     rcx, rdi; void *
0x1800050d1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800050d6  mov     rbx, [rsp+28h+arg_0]
0x1800050db  mov     rax, rdi
0x1800050de  add     rsp, 20h
0x1800050e2  pop     rdi
0x1800050e3  retn
```
