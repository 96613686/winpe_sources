# appv::shared::kernel::SidFromPid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,uchar *)

- ea: `0x180002cb4`
- end: `0x180002d75`
- name: `??$SidFromPid@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@012@PEAE@Z`
- size: `193`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180007840`
- `0x180018ab0`
- `0x180018b9c`

## callees

- `0x180002cb4`
- `0x180002d7c`
- `0x18000e534`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180002d1c`
- `ntoskrnl!ZwClose` at `0x180002d49`
- `ntoskrnl!ZwClose` at `0x180002d5d`
- `ntoskrnl!ZwClose` at `0x180002d1c`
- `ntoskrnl!ZwClose` at `0x180002d49`
- `ntoskrnl!ZwClose` at `0x180002d5d`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x180002d02`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x180002d02`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::SidFromPid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 result; // rax
  HANDLE v6; // rbx
  NTSTATUS v7; // edi
  void *v8; // rdi
  unsigned int v9; // esi
  void *TokenHandle; // [rsp+20h] [rbp-38h] BYREF
  HANDLE ProcessHandle; // [rsp+78h] [rbp+20h] BYREF

  ProcessHandle = 0;
  result = appv::shared::kernel::open_process_handle(&ProcessHandle, a1);
  if ( (int)result >= 0 )
  {
    v6 = ProcessHandle;
    TokenHandle = 0;
    v7 = ZwOpenProcessTokenEx(ProcessHandle, 0x20008u, 0x200u, &TokenHandle);
    if ( v7 >= 0 )
    {
      v8 = TokenHandle;
      v9 = appv::shared::kernel::SidFromToken<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
             TokenHandle,
             a2,
             a3);
      if ( v8 )
        ZwClose(v8);
      if ( v6 )
        ZwClose(v6);
      return v9;
    }
    else
    {
      if ( v6 )
        ZwClose(v6);
      return (unsigned int)v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002cb4  push    rbx
0x180002cb6  push    rbp
0x180002cb7  push    rsi
0x180002cb8  push    rdi
0x180002cb9  sub     rsp, 38h
0x180002cbd  mov     rbp, rdx
0x180002cc0  mov     [rsp+58h+ProcessHandle], 0
0x180002cc9  mov     rdx, rcx
0x180002ccc  mov     rsi, r8
0x180002ccf  lea     rcx, [rsp+58h+ProcessHandle]
0x180002cd4  call    appv__shared__kernel__open_process_handle
0x180002cd9  test    eax, eax
0x180002cdb  js      loc_180002D6B
0x180002ce1  mov     rbx, [rsp+58h+ProcessHandle]
0x180002ce6  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180002ceb  mov     rcx, rbx; ProcessHandle
0x180002cee  mov     [rsp+58h+TokenHandle], 0
0x180002cf7  mov     edx, 20008h; DesiredAccess
0x180002cfc  mov     r8d, 200h; HandleAttributes
0x180002d02  call    cs:__imp_ZwOpenProcessTokenEx
0x180002d09  nop     dword ptr [rax+rax+00h]
0x180002d0e  mov     edi, eax
0x180002d10  test    eax, eax
0x180002d12  jns     short loc_180002D2C
0x180002d14  test    rbx, rbx
0x180002d17  jz      short loc_180002D28
0x180002d19  mov     rcx, rbx; Handle
0x180002d1c  call    cs:__imp_ZwClose
0x180002d23  nop     dword ptr [rax+rax+00h]
0x180002d28  mov     eax, edi
0x180002d2a  jmp     short loc_180002D6B
0x180002d2c  mov     rdi, [rsp+58h+TokenHandle]
0x180002d31  mov     r8, rsi
0x180002d34  mov     rcx, rdi
0x180002d37  mov     rdx, rbp
0x180002d3a  call    ??$SidFromToken@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@012@PEAE@Z; appv::shared::kernel::SidFromToken<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,uchar *)
0x180002d3f  mov     esi, eax
0x180002d41  test    rdi, rdi
0x180002d44  jz      short loc_180002D55
0x180002d46  mov     rcx, rdi; Handle
0x180002d49  call    cs:__imp_ZwClose
0x180002d50  nop     dword ptr [rax+rax+00h]
0x180002d55  test    rbx, rbx
0x180002d58  jz      short loc_180002D69
0x180002d5a  mov     rcx, rbx; Handle
0x180002d5d  call    cs:__imp_ZwClose
0x180002d64  nop     dword ptr [rax+rax+00h]
0x180002d69  mov     eax, esi
0x180002d6b  add     rsp, 38h
0x180002d6f  pop     rdi
0x180002d70  pop     rsi
0x180002d71  pop     rbp
0x180002d72  pop     rbx
0x180002d73  retn
```
