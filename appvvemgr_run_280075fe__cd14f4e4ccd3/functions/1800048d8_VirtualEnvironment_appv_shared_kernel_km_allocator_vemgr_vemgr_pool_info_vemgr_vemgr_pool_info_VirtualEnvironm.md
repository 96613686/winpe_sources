# VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info> const &,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info> const &,long &)

- ea: `0x1800048d8`
- end: `0x180004a8a`
- name: `??0?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@AEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEBV?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@AEBV?$doubly_linked_list@V?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@456@AEAJ@Z`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800071a0`

## callees

- `0x1800048d8`
- `0x180005430`
- `0x18000e588`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18000495a`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000495a`

## pseudocode

```c
__int64 __fastcall VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        int *a5)
{
  __int64 v5; // r14
  int v10; // eax
  _QWORD *v11; // rbx
  _QWORD *v12; // rbp
  _QWORD *v13; // rbx
  int v14; // eax
  _QWORD *v15; // rdi
  _QWORD *v16; // rbx
  __int64 v17; // rbp
  _QWORD *i; // rdi
  int v19; // eax

  *(_QWORD *)(a1 + 8) = 0;
  v5 = a1 + 128;
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
  if ( *(_DWORD *)a3 && *(_DWORD *)a4 )
  {
    *(_QWORD *)(a1 + 120) = *a2;
    kernel_std::detail::shared_count::operator=(v5, a2 + 1);
    *(_BYTE *)(a1 + 116) = 0;
    v10 = 0;
    v11 = *(_QWORD **)(a3 + 32);
    v12 = (_QWORD *)(a3 + 8);
    while ( v11 != v12 )
    {
      v10 = appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
              a1,
              v11);
      if ( v10 < 0 )
        break;
      v11 = (_QWORD *)v11[3];
    }
    *a5 = v10;
    if ( v10 >= 0 )
    {
      v13 = *(_QWORD **)(a4 + 32);
      v14 = 0;
      v15 = (_QWORD *)(a4 + 8);
      while ( v13 != v15 )
      {
        v14 = appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
                a1 + 40,
                v13);
        if ( v14 < 0 )
          break;
        v13 = (_QWORD *)v13[3];
      }
      v16 = *(_QWORD **)(a1 + 72);
      *a5 = v14;
LABEL_13:
      if ( v16 == (_QWORD *)(a1 + 48) )
      {
        *a5 = 0;
        *(_DWORD *)(a1 + 112) = _InterlockedIncrement(&VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::next_id_);
      }
      else
      {
        v17 = *v16 + 152LL;
        for ( i = *(_QWORD **)(*v16 + 176LL); ; i = (_QWORD *)i[3] )
        {
          if ( i == (_QWORD *)v17 )
          {
            v16 = (_QWORD *)v16[3];
            goto LABEL_13;
          }
          v19 = appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
                  a1 + 168,
                  i);
          if ( v19 < 0 )
            break;
        }
        *a5 = v19;
      }
    }
  }
  else
  {
    *a5 = -1073741811;
  }
  return a1;
}

```

## disassembly

```asm
0x1800048d8  push    rbx
0x1800048da  push    rbp
0x1800048db  push    rsi
0x1800048dc  push    rdi
0x1800048dd  push    r12
0x1800048df  push    r13
0x1800048e1  push    r14
0x1800048e3  push    r15
0x1800048e5  sub     rsp, 28h
0x1800048e9  xor     r13d, r13d
0x1800048ec  lea     rax, [rcx+8]
0x1800048f0  mov     [rax], r13
0x1800048f3  lea     r14, [rcx+80h]
0x1800048fa  mov     [rax+8], r13
0x1800048fe  mov     rbx, rdx
0x180004901  mov     [rax+18h], rax
0x180004905  mov     rsi, rcx
0x180004908  mov     [rax+10h], rax
0x18000490c  xor     edx, edx; SourceString
0x18000490e  lea     rax, [rcx+30h]
0x180004912  mov     [rcx], r13d
0x180004915  mov     [rax], r13
0x180004918  mov     rdi, r9
0x18000491b  mov     [rax+8], r13
0x18000491f  mov     rbp, r8
0x180004922  mov     [rax+18h], rax
0x180004926  mov     [rax+10h], rax
0x18000492a  lea     rax, [rcx+58h]
0x18000492e  mov     [rcx+28h], r13d
0x180004932  mov     [rcx+50h], r13d
0x180004936  mov     [rcx+78h], r13
0x18000493a  mov     [rcx+88h], r13
0x180004941  mov     [rcx+90h], r13
0x180004948  add     rcx, 98h; DestinationString
0x18000494f  mov     [rax+10h], rax
0x180004953  mov     [rax+8], rax
0x180004957  mov     [r14], r13
0x18000495a  call    cs:__imp_RtlInitUnicodeString
0x180004961  nop     dword ptr [rax+rax+00h]
0x180004966  lea     r12, [rsi+0A8h]
0x18000496d  lea     rax, [r12+8]
0x180004972  mov     [r12], r13d
0x180004976  mov     [rax], r13
0x180004979  mov     [rax+8], r13
0x18000497d  mov     [rax+18h], rax
0x180004981  mov     [rax+10h], rax
0x180004985  cmp     [rbp+0], r13d
0x180004989  jz      loc_180004A67
0x18000498f  cmp     [rdi], r13d
0x180004992  jz      loc_180004A67
0x180004998  mov     rax, [rbx]
0x18000499b  lea     rdx, [rbx+8]
0x18000499f  mov     rcx, r14
0x1800049a2  mov     [rsi+78h], rax
0x1800049a6  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x1800049ab  mov     [rsi+74h], r13b
0x1800049af  mov     eax, r13d
0x1800049b2  mov     rbx, [rbp+20h]
0x1800049b6  add     rbp, 8
0x1800049ba  cmp     rbx, rbp
0x1800049bd  jz      short loc_1800049D4
0x1800049bf  mov     rdx, rbx
0x1800049c2  mov     rcx, rsi
0x1800049c5  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x1800049ca  test    eax, eax
0x1800049cc  js      short loc_1800049D4
0x1800049ce  mov     rbx, [rbx+18h]
0x1800049d2  jmp     short loc_1800049BA
0x1800049d4  mov     r14, [rsp+68h+arg_20]
0x1800049dc  mov     [r14], eax
0x1800049df  test    eax, eax
0x1800049e1  js      loc_180004A75
0x1800049e7  mov     rbx, [rdi+20h]
0x1800049eb  mov     eax, r13d
0x1800049ee  add     rdi, 8
0x1800049f2  cmp     rbx, rdi
0x1800049f5  jz      short loc_180004A0D
0x1800049f7  mov     rdx, rbx
0x1800049fa  lea     rcx, [rsi+28h]
0x1800049fe  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x180004a03  test    eax, eax
0x180004a05  js      short loc_180004A0D
0x180004a07  mov     rbx, [rbx+18h]
0x180004a0b  jmp     short loc_1800049F2
0x180004a0d  mov     rbx, [rsi+48h]
0x180004a11  lea     r15, [rsi+30h]
0x180004a15  mov     [r14], eax
0x180004a18  cmp     rbx, r15
0x180004a1b  jz      short loc_180004A50
0x180004a1d  mov     rbp, [rbx]
0x180004a20  add     rbp, 98h
0x180004a27  mov     rdi, [rbp+18h]
0x180004a2b  cmp     rdi, rbp
0x180004a2e  jz      short loc_180004A45
0x180004a30  mov     rdx, rdi
0x180004a33  mov     rcx, r12
0x180004a36  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x180004a3b  test    eax, eax
0x180004a3d  js      short loc_180004A4B
0x180004a3f  mov     rdi, [rdi+18h]
0x180004a43  jmp     short loc_180004A2B
0x180004a45  mov     rbx, [rbx+18h]
0x180004a49  jmp     short loc_180004A18
0x180004a4b  mov     [r14], eax
0x180004a4e  jmp     short loc_180004A75
0x180004a50  mov     [r14], r13d
0x180004a53  mov     eax, 1
0x180004a58  lock xadd cs:?next_id_@?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@0JA, eax; long VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::next_id_
0x180004a60  inc     eax
0x180004a62  mov     [rsi+70h], eax
0x180004a65  jmp     short loc_180004A75
0x180004a67  mov     rax, [rsp+68h+arg_20]
0x180004a6f  mov     dword ptr [rax], 0C000000Dh
0x180004a75  mov     rax, rsi
0x180004a78  add     rsp, 28h
0x180004a7c  pop     r15
0x180004a7e  pop     r14
0x180004a80  pop     r13
0x180004a82  pop     r12
0x180004a84  pop     rdi
0x180004a85  pop     rsi
0x180004a86  pop     rbp
0x180004a87  pop     rbx
0x180004a88  retn
```
