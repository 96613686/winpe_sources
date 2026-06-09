# std::thread::_Invoke<std::tuple<void (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::*)(void),winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *>,0,1>(void *)

- ea: `0x180009f30`
- end: `0x180009f64`
- name: `??$_Invoke@V?$tuple@P8ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@EAAXXZPEAU1234567@@std@@$0A@$00@thread@std@@CAIPEAX@Z`
- size: `52`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180017ff8`
- `0x180018238`
- `0x18001cdf0`

## pseudocode

```c
__int64 __fastcall std::thread::_Invoke<std::tuple<void (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::*)(void),winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *>,0,1>(
        int *a1)
{
  (*((void (__fastcall **)(_QWORD))a1 + 1))(*(_QWORD *)a1 + a1[4]);
  Cnd_do_broadcast_at_thread_exit();
  operator delete(a1, 0x18u);
  return 0;
}

```

## disassembly

```asm
0x180009f30  push    rbx
0x180009f32  sub     rsp, 20h
0x180009f36  mov     rbx, rcx
0x180009f39  movsxd  rcx, dword ptr [rcx+10h]
0x180009f3d  add     rcx, [rbx]
0x180009f40  mov     rax, [rbx+8]
0x180009f44  call    cs:__guard_dispatch_icall_fptr
0x180009f4a  call    _Cnd_do_broadcast_at_thread_exit
0x180009f4f  mov     edx, 18h; unsigned __int64
0x180009f54  mov     rcx, rbx; void *
0x180009f57  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009f5c  xor     eax, eax
0x180009f5e  add     rsp, 20h
0x180009f62  pop     rbx
0x180009f63  retn
```
