# winrt::impl::produce<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManagerStatics>::GetCurrent(void * *)

- ea: `0x180008ff0`
- end: `0x180009023`
- name: `?GetCurrent@?$produce@UModelCacheManager@factory_implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIModelCacheManagerStatics@34567@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `51`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005200`
- `0x180008ff0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManagerStatics>::GetCurrent(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = a1;
  *a2 = 0;
  try
  {
    winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::GetCurrent();
    *a2 = v4;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v4);
  }
  return result;
}

```

## disassembly

```asm
0x180008ff0  mov     [rsp+arg_0], rcx
0x180008ff5  push    rbx
0x180008ff6  sub     rsp, 20h
0x180008ffa  mov     rbx, rdx
0x180008ffd  xor     eax, eax
0x180008fff  mov     [rdx], rax
0x180009002  lea     rcx, [rsp+28h+arg_0]
0x180009007  call    ?GetCurrent@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@SA?AU134567@XZ; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::GetCurrent(void)
0x18000900c  mov     rax, [rsp+28h+arg_0]
0x180009011  mov     [rbx], rax
0x180009014  xor     eax, eax
0x180009016  jmp     short loc_18000901C
0x180009018  mov     eax, dword ptr [rsp+28h+arg_0]
0x18000901c  add     rsp, 20h
0x180009020  pop     rbx
0x180009021  retn
```
