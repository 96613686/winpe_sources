# kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)

- ea: `0x180003f50`
- end: `0x180003fc8`
- name: `??$reset@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAAXPEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `120`
- prototype: ``
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x180009710`
- `0x18000bfb8`
- `0x18000c31c`
- `0x18000c9a8`
- `0x18000d250`
- `0x18000d37c`
- `0x18000da60`
- `0x18000e960`
- `0x18000ef74`
- `0x180013b78`
- `0x180017c7c`
- `0x180018ab0`
- `0x180019014`
- `0x18001a79c`

## callees

- `0x180001448`
- `0x180003f50`
- `0x18001bb30`

## pseudocode

```c
__int64 __fastcall kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
        _QWORD *a1,
        __int64 a2)
{
  __int64 result; // rax
  __int64 v4; // r8
  __int64 v5; // r8
  volatile signed __int32 *v6; // rbx
  _BYTE v7[8]; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v8; // [rsp+28h] [rbp-10h]

  result = kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
             v7,
             a2);
  v4 = *(_QWORD *)result;
  *(_QWORD *)result = *a1;
  *a1 = v4;
  v5 = a1[1];
  a1[1] = *(_QWORD *)(result + 8);
  *(_QWORD *)(result + 8) = v5;
  v6 = v8;
  if ( v8 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      result = (unsigned int)_InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003f50  push    rbx
0x180003f52  sub     rsp, 30h
0x180003f56  mov     rbx, rcx
0x180003f59  lea     rcx, [rsp+38h+var_18]
0x180003f5e  call    ??$?0V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAA@PEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)
0x180003f63  mov     rdx, [rbx]
0x180003f66  mov     r8, [rax]
0x180003f69  mov     [rax], rdx
0x180003f6c  mov     [rbx], r8
0x180003f6f  mov     r8, [rbx+8]
0x180003f73  mov     rdx, [rax+8]
0x180003f77  mov     [rbx+8], rdx
0x180003f7b  mov     [rax+8], r8
0x180003f7f  mov     rbx, [rsp+38h+var_10]
0x180003f84  test    rbx, rbx
0x180003f87  jz      short loc_180003FC1
0x180003f89  or      eax, 0FFFFFFFFh
0x180003f8c  lock xadd [rbx+8], eax
0x180003f91  cmp     eax, 1
0x180003f94  jnz     short loc_180003FC1
0x180003f96  mov     rax, [rbx]
0x180003f99  mov     rcx, rbx
0x180003f9c  mov     rax, [rax+8]
0x180003fa0  call    _guard_dispatch_icall
0x180003fa5  or      eax, 0FFFFFFFFh
0x180003fa8  lock xadd [rbx+0Ch], eax
0x180003fad  cmp     eax, 1
0x180003fb0  jnz     short loc_180003FC1
0x180003fb2  mov     rax, [rbx]
0x180003fb5  mov     rcx, rbx
0x180003fb8  mov     rax, [rax+10h]
0x180003fbc  call    _guard_dispatch_icall
0x180003fc1  add     rsp, 30h
0x180003fc5  pop     rbx
0x180003fc6  retn
```
