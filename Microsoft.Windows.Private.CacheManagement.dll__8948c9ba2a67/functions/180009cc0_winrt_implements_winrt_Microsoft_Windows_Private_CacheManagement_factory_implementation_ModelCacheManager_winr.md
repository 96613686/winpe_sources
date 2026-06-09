# winrt::implements<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManagerStatics>::GetIids(ulong *,_GUID * *)

- ea: `0x180009cc0`
- end: `0x180009d5a`
- name: `?GetIids@?$implements@UModelCacheManager@factory_implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@57@UIModelCacheManagerStatics@34567@@winrt@@QEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `154`
- prototype: `__int64 __fastcall(__int64, unsigned int *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008f50`
- `0x180009050`

## callees

- `0x180009cc0`
- `0x1800162c8`
- `0x1800181b0`
- `0x18001cdf0`
- `0x18001cf40`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::implements<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManagerStatics>::GetIids(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  void *v6; // rax
  unsigned int v8; // [rsp+20h] [rbp-28h] BYREF
  void *Src; // [rsp+28h] [rbp-20h]

  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a1 + 32LL))(a1, &v8);
  if ( v8 )
  {
    _mm_lfence();
    v5 = v8;
    *a2 = v8;
    v6 = WINRT_IMPL_CoTaskMemAlloc(16 * v5);
    *a3 = v6;
    if ( !v6 )
      return 2147942414LL;
    memmove(v6, Src, 16LL * v8);
  }
  else
  {
    *a2 = 0;
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180009cc0  mov     [rsp+arg_18], rbx
0x180009cc5  push    rdi
0x180009cc6  sub     rsp, 40h
0x180009cca  mov     rax, cs:__security_cookie
0x180009cd1  xor     rax, rsp
0x180009cd4  mov     [rsp+48h+var_18], rax
0x180009cd9  mov     rax, [rcx]
0x180009cdc  mov     rbx, rdx
0x180009cdf  lea     rdx, [rsp+48h+var_28]
0x180009ce4  mov     rdi, r8
0x180009ce7  mov     rax, [rax+20h]
0x180009ceb  call    cs:__guard_dispatch_icall_fptr
0x180009cf1  cmp     [rsp+48h+var_28], 0
0x180009cf6  jbe     short loc_180009D33
0x180009cf8  lfence
0x180009cfb  mov     eax, [rsp+48h+var_28]
0x180009cff  mov     ecx, eax
0x180009d01  mov     [rbx], eax
0x180009d03  shl     rcx, 4; cb
0x180009d07  call    WINRT_IMPL_CoTaskMemAlloc
0x180009d0c  mov     [rdi], rax
0x180009d0f  test    rax, rax
0x180009d12  jnz     short loc_180009D1B
0x180009d14  mov     eax, 8007000Eh
0x180009d19  jmp     short loc_180009D42
0x180009d1b  mov     r8d, [rsp+48h+var_28]
0x180009d20  mov     rcx, rax; void *
0x180009d23  mov     rdx, [rsp+48h+Src]; Src
0x180009d28  shl     r8, 4; Size
0x180009d2c  call    memmove
0x180009d31  jmp     short loc_180009D40
0x180009d33  mov     dword ptr [rbx], 0
0x180009d39  mov     qword ptr [rdi], 0
0x180009d40  xor     eax, eax
0x180009d42  mov     rcx, [rsp+48h+var_18]
0x180009d47  xor     rcx, rsp; StackCookie
0x180009d4a  call    __security_check_cookie
0x180009d4f  mov     rbx, [rsp+48h+arg_18]
0x180009d54  add     rsp, 40h
0x180009d58  pop     rdi
0x180009d59  retn
```
