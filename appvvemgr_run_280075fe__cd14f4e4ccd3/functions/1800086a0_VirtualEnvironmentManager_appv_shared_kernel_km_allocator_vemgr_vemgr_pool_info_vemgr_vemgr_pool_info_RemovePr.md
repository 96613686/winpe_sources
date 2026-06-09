# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVEInternal(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &,VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVEDisposition &)

- ea: `0x1800086a0`
- end: `0x180008770`
- name: `?RemoveProcessFromVEInternal@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@AEAW4RemoveVEDisposition@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z`
- size: `208`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005ec4`
- `0x18000855c`

## callees

- `0x180007b88`
- `0x1800086a0`
- `0x180008778`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180008747`
- `ntoskrnl!KeReleaseMutex` at `0x180008747`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800086fd`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800086fd`

## pseudocode

```c
__int64 __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVEInternal(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
        _DWORD *a4)
{
  __int64 v8; // rax
  void *v9; // rcx
  int ProcessInVE; // esi
  union _LARGE_INTEGER v12; // [rsp+60h] [rbp+18h] BYREF

  if ( !*a3 )
    return 3221225485LL;
  v8 = a3[1];
  if ( !v8 || !*(_DWORD *)(v8 + 8) )
    return 3221225485LL;
  v9 = *(void **)(a1 + 72);
  if ( v9 )
  {
    v12.QuadPart = -300000000;
    if ( KeWaitForSingleObject(v9, Executive, 0, 0, &v12) )
      return 3221225653LL;
  }
  ProcessInVE = ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindProcessInVE(
                  *(_QWORD *)(a1 + 16),
                  a2,
                  *(const UNICODE_STRING **)(*a3 + 120),
                  a3);
  if ( ProcessInVE >= 0 )
    ProcessInVE = VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVEInternal_Unlocked(
                    (_QWORD *)a1,
                    a2,
                    a3,
                    a4);
  KeReleaseMutex(*(PRKMUTEX *)(a1 + 72), 0);
  return (unsigned int)ProcessInVE;
}

```

## disassembly

```asm
0x1800086a0  mov     r11, rsp
0x1800086a3  mov     [r11+8], rbx
0x1800086a7  mov     [r11+10h], rbp
0x1800086ab  push    rsi
0x1800086ac  push    rdi
0x1800086ad  push    r14
0x1800086af  sub     rsp, 30h
0x1800086b3  cmp     qword ptr [r8], 0
0x1800086b7  mov     r14, r9
0x1800086ba  mov     rbx, r8
0x1800086bd  mov     ebp, edx
0x1800086bf  mov     rdi, rcx
0x1800086c2  jz      loc_180008757
0x1800086c8  mov     rax, [r8+8]
0x1800086cc  test    rax, rax
0x1800086cf  jz      loc_180008757
0x1800086d5  mov     eax, [rax+8]
0x1800086d8  test    eax, eax
0x1800086da  jz      short loc_180008757
0x1800086dc  mov     rcx, [rcx+48h]; Object
0x1800086e0  test    rcx, rcx
0x1800086e3  jz      short loc_180008714
0x1800086e5  lea     rax, [r11+18h]
0x1800086e9  mov     qword ptr [r11+18h], 0FFFFFFFFEE1E5D00h
0x1800086f1  xor     r9d, r9d; Alertable
0x1800086f4  mov     [r11-28h], rax
0x1800086f8  xor     r8d, r8d; WaitMode
0x1800086fb  xor     edx, edx; WaitReason
0x1800086fd  call    cs:__imp_KeWaitForSingleObject
0x180008704  nop     dword ptr [rax+rax+00h]
0x180008709  test    eax, eax
0x18000870b  jz      short loc_180008714
0x18000870d  mov     eax, 0C00000B5h
0x180008712  jmp     short loc_18000875C
0x180008714  mov     r8, [rbx]
0x180008717  mov     r9, rbx
0x18000871a  mov     rcx, [rdi+10h]
0x18000871e  mov     edx, ebp
0x180008720  mov     r8, [r8+78h]
0x180008724  call    ?FindProcessInVE@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindProcessInVE(ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x180008729  mov     esi, eax
0x18000872b  test    eax, eax
0x18000872d  js      short loc_180008741
0x18000872f  mov     r9, r14
0x180008732  mov     r8, rbx
0x180008735  mov     edx, ebp
0x180008737  mov     rcx, rdi
0x18000873a  call    ?RemoveProcessFromVEInternal_Unlocked@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@AEAW4RemoveVEDisposition@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVEInternal_Unlocked(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &,VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVEDisposition &)
0x18000873f  mov     esi, eax
0x180008741  mov     rcx, [rdi+48h]; Mutex
0x180008745  xor     edx, edx; Wait
0x180008747  call    cs:__imp_KeReleaseMutex
0x18000874e  nop     dword ptr [rax+rax+00h]
0x180008753  mov     eax, esi
0x180008755  jmp     short loc_18000875C
0x180008757  mov     eax, 0C000000Dh
0x18000875c  mov     rbx, [rsp+48h+arg_0]
0x180008761  mov     rbp, [rsp+48h+arg_8]
0x180008766  add     rsp, 30h
0x18000876a  pop     r14
0x18000876c  pop     rdi
0x18000876d  pop     rsi
0x18000876e  retn
```
