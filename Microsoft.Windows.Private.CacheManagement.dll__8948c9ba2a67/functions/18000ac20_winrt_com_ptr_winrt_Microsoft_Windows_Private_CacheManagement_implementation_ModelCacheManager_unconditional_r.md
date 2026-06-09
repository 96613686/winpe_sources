# winrt::com_ptr<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>::unconditional_release_ref(void)

- ea: `0x18000ac20`
- end: `0x18000ac65`
- name: `?unconditional_release_ref@?$com_ptr@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ`
- size: `69`
- prototype: `__int64 __fastcall(_QWORD **)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005200`
- `0x180009300`
- `0x18001cca0`

## callees

- `0x180009b70`
- `0x18000ac20`
- `0x18001cdf0`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>::unconditional_release_ref(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  __int64 result; // rax

  v1 = *a1;
  *a1 = 0;
  result = winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference((__int64)v1);
  if ( !(_DWORD)result )
  {
    v1[1] = 1;
    return (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v1 + 8LL))(v1, 1);
  }
  return result;
}

```

## disassembly

```asm
0x18000ac20  push    rbx
0x18000ac22  sub     rsp, 20h
0x18000ac26  mov     rbx, [rcx]
0x18000ac29  mov     qword ptr [rcx], 0
0x18000ac30  mov     rcx, rbx
0x18000ac33  call    ?subtract_final_reference@?$root_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U134567@UIModelCacheManager2@34567@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(void)
0x18000ac38  test    eax, eax
0x18000ac3a  jnz     short loc_18000AC5F
0x18000ac3c  mov     qword ptr [rbx+8], 1
0x18000ac44  mov     edx, 1
0x18000ac49  mov     rax, [rbx]
0x18000ac4c  mov     rcx, rbx
0x18000ac4f  mov     rax, [rax+8]
0x18000ac53  add     rsp, 20h
0x18000ac57  pop     rbx
0x18000ac58  jmp     cs:__guard_dispatch_icall_fptr
0x18000ac5f  add     rsp, 20h
0x18000ac63  pop     rbx
0x18000ac64  retn
```
