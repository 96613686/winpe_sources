# VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,long &)

- ea: `0x180004a90`
- end: `0x180004c66`
- name: `??0?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@V?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@2@AEAJ@Z`
- size: `470`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800071a0`

## callees

- `0x180004a90`
- `0x180005430`
- `0x18000e588`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180004b0e`
- `ntoskrnl!RtlInitUnicodeString` at `0x180004b0e`

## pseudocode

```c
__int64 __fastcall VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int *a4)
{
  __int64 v4; // rdi
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  _QWORD *v12; // rdi
  __int64 v13; // rbp
  __int64 i; // rbx
  int v15; // eax
  volatile signed __int32 *v16; // rbx
  volatile signed __int32 *v17; // rbx

  *(_QWORD *)(a1 + 8) = 0;
  v4 = a1 + 128;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 32) = a1 + 8;
  *(_QWORD *)(a1 + 24) = a1 + 8;
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 72) = a1 + 48;
  *(_QWORD *)(a1 + 64) = a1 + 48;
  *(_DWORD *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 104) = a1 + 88;
  *(_QWORD *)(a1 + 96) = a1 + 88;
  *(_QWORD *)(a1 + 128) = 0;
  RtlInitUnicodeString((PUNICODE_STRING)(a1 + 152), 0);
  *(_DWORD *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 200) = a1 + 176;
  *(_QWORD *)(a1 + 192) = a1 + 176;
  v9 = appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
         a1,
         a2);
  *a4 = v9;
  if ( v9 >= 0 )
  {
    v10 = appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
            a1 + 40,
            a3);
    *a4 = v10;
    if ( v10 >= 0 )
    {
      v11 = *(_QWORD *)a2 + 8LL;
      *(_QWORD *)(a1 + 120) = **(_QWORD **)a2;
      kernel_std::detail::shared_count::operator=(v4, v11);
      *(_BYTE *)(a1 + 116) = 1;
      v12 = *(_QWORD **)(a1 + 72);
LABEL_4:
      if ( v12 == (_QWORD *)(a1 + 48) )
      {
        *a4 = 0;
        *(_DWORD *)(a1 + 112) = _InterlockedIncrement(&VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::next_id_);
      }
      else
      {
        v13 = *v12 + 152LL;
        for ( i = *(_QWORD *)(*v12 + 176LL); ; i = *(_QWORD *)(i + 24) )
        {
          if ( i == v13 )
          {
            v12 = (_QWORD *)v12[3];
            goto LABEL_4;
          }
          v15 = appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
                  a1 + 168,
                  i);
          if ( v15 < 0 )
            break;
        }
        *a4 = v15;
      }
    }
  }
  v16 = *(volatile signed __int32 **)(a2 + 8);
  if ( v16 )
  {
    if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 16LL))(v16);
    }
  }
  v17 = *(volatile signed __int32 **)(a3 + 8);
  if ( v17 )
  {
    if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180004a90  push    rbx
0x180004a92  push    rbp
0x180004a93  push    rsi
0x180004a94  push    rdi
0x180004a95  push    r12
0x180004a97  push    r13
0x180004a99  push    r14
0x180004a9b  push    r15
0x180004a9d  sub     rsp, 28h
0x180004aa1  xor     ebp, ebp
0x180004aa3  lea     rax, [rcx+8]
0x180004aa7  mov     [rax], rbp
0x180004aaa  lea     rdi, [rcx+80h]
0x180004ab1  mov     [rax+8], rbp
0x180004ab5  mov     r15, rdx
0x180004ab8  mov     [rax+18h], rax
0x180004abc  mov     rsi, rcx
0x180004abf  mov     [rax+10h], rax
0x180004ac3  xor     edx, edx; SourceString
0x180004ac5  lea     rax, [rcx+30h]
0x180004ac9  mov     [rcx], ebp
0x180004acb  mov     [rax], rbp
0x180004ace  mov     r14, r9
0x180004ad1  mov     [rax+8], rbp
0x180004ad5  mov     r13, r8
0x180004ad8  mov     [rax+18h], rax
0x180004adc  mov     [rax+10h], rax
0x180004ae0  lea     rax, [rcx+58h]
0x180004ae4  mov     [rcx+28h], ebp
0x180004ae7  mov     [rcx+50h], ebp
0x180004aea  mov     [rcx+78h], rbp
0x180004aee  mov     [rcx+88h], rbp
0x180004af5  mov     [rcx+90h], rbp
0x180004afc  add     rcx, 98h; DestinationString
0x180004b03  mov     [rax+10h], rax
0x180004b07  mov     [rax+8], rax
0x180004b0b  mov     [rdi], rbp
0x180004b0e  call    cs:__imp_RtlInitUnicodeString
0x180004b15  nop     dword ptr [rax+rax+00h]
0x180004b1a  lea     rax, [rsi+0A8h]
0x180004b21  mov     rdx, r15
0x180004b24  mov     [rax], ebp
0x180004b26  mov     rcx, rsi
0x180004b29  add     rax, 8
0x180004b2d  mov     [rax], rbp
0x180004b30  mov     [rax+8], rbp
0x180004b34  mov     [rax+18h], rax
0x180004b38  mov     [rax+10h], rax
0x180004b3c  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x180004b41  mov     [r14], eax
0x180004b44  test    eax, eax
0x180004b46  js      loc_180004BD4
0x180004b4c  mov     rdx, r13
0x180004b4f  lea     rcx, [rsi+28h]
0x180004b53  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x180004b58  mov     [r14], eax
0x180004b5b  test    eax, eax
0x180004b5d  js      short loc_180004BD4
0x180004b5f  mov     rdx, [r15]
0x180004b62  mov     rcx, rdi
0x180004b65  mov     rax, [rdx]
0x180004b68  add     rdx, 8
0x180004b6c  mov     [rsi+78h], rax
0x180004b70  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x180004b75  mov     byte ptr [rsi+74h], 1
0x180004b79  lea     r12, [rsi+30h]
0x180004b7d  mov     rdi, [rsi+48h]
0x180004b81  cmp     rdi, r12
0x180004b84  jz      short loc_180004BBF
0x180004b86  mov     rbp, [rdi]
0x180004b89  add     rbp, 98h
0x180004b90  mov     rbx, [rbp+18h]
0x180004b94  cmp     rbx, rbp
0x180004b97  jz      short loc_180004BB2
0x180004b99  mov     rdx, rbx
0x180004b9c  lea     rcx, [rsi+0A8h]
0x180004ba3  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x180004ba8  test    eax, eax
0x180004baa  js      short loc_180004BB8
0x180004bac  mov     rbx, [rbx+18h]
0x180004bb0  jmp     short loc_180004B94
0x180004bb2  mov     rdi, [rdi+18h]
0x180004bb6  jmp     short loc_180004B81
0x180004bb8  mov     [r14], eax
0x180004bbb  xor     ebp, ebp
0x180004bbd  jmp     short loc_180004BD4
0x180004bbf  xor     ebp, ebp
0x180004bc1  mov     [r14], ebp
0x180004bc4  lea     eax, [rbp+1]
0x180004bc7  lock xadd cs:?next_id_@?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@0JA, eax; long VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::next_id_
0x180004bcf  inc     eax
0x180004bd1  mov     [rsi+70h], eax
0x180004bd4  mov     rbx, [r15+8]
0x180004bd8  or      edi, 0FFFFFFFFh
0x180004bdb  test    rbx, rbx
0x180004bde  jz      short loc_180004C14
0x180004be0  mov     eax, edi
0x180004be2  lock xadd [rbx+8], eax
0x180004be7  add     eax, edi
0x180004be9  jnz     short loc_180004C14
0x180004beb  mov     rax, [rbx]
0x180004bee  mov     rcx, rbx
0x180004bf1  mov     rax, [rax+8]
0x180004bf5  call    _guard_dispatch_icall
0x180004bfa  mov     eax, edi
0x180004bfc  lock xadd [rbx+0Ch], eax
0x180004c01  add     eax, edi
0x180004c03  jnz     short loc_180004C14
0x180004c05  mov     rax, [rbx]
0x180004c08  mov     rcx, rbx
0x180004c0b  mov     rax, [rax+10h]
0x180004c0f  call    _guard_dispatch_icall
0x180004c14  mov     rbx, [r13+8]
0x180004c18  test    rbx, rbx
0x180004c1b  jz      short loc_180004C51
0x180004c1d  mov     eax, edi
0x180004c1f  lock xadd [rbx+8], eax
0x180004c24  add     eax, edi
0x180004c26  jnz     short loc_180004C51
0x180004c28  mov     rax, [rbx]
0x180004c2b  mov     rcx, rbx
0x180004c2e  mov     rax, [rax+8]
0x180004c32  call    _guard_dispatch_icall
0x180004c37  mov     eax, edi
0x180004c39  lock xadd [rbx+0Ch], eax
0x180004c3e  add     eax, edi
0x180004c40  jnz     short loc_180004C51
0x180004c42  mov     rax, [rbx]
0x180004c45  mov     rcx, rbx
0x180004c48  mov     rax, [rax+10h]
0x180004c4c  call    _guard_dispatch_icall
0x180004c51  mov     rax, rsi
0x180004c54  add     rsp, 28h
0x180004c58  pop     r15
0x180004c5a  pop     r14
0x180004c5c  pop     r13
0x180004c5e  pop     r12
0x180004c60  pop     rdi
0x180004c61  pop     rsi
0x180004c62  pop     rbp
0x180004c63  pop     rbx
0x180004c64  retn
```
