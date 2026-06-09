# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::GetPublishedPackageGroups<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info> &,ulong)

- ea: `0x180001d4c`
- end: `0x180001f71`
- name: `??$GetPublishedPackageGroups@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@456@K@Z`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180001f78`

## callees

- `0x18000199c`
- `0x180001d4c`
- `0x1800021d0`
- `0x180002b48`
- `0x18000e588`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180001dea`
- `ntoskrnl!ExFreePoolWithTag` at `0x180001e42`
- `ntoskrnl!ExFreePoolWithTag` at `0x180001dea`
- `ntoskrnl!ExFreePoolWithTag` at `0x180001e42`
- `ntoskrnl!RtlInitUnicodeString` at `0x180001dbe`
- `ntoskrnl!RtlInitUnicodeString` at `0x180001e13`
- `ntoskrnl!RtlInitUnicodeString` at `0x180001dbe`
- `ntoskrnl!RtlInitUnicodeString` at `0x180001e13`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::GetPublishedPackageGroups<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        const UNICODE_STRING ***a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  int v9; // esi
  const UNICODE_STRING *i; // rbx
  const UNICODE_STRING *v11; // rax
  __int64 v12; // rdi
  const UNICODE_STRING **v13; // rdx
  int v14; // edi
  volatile signed __int32 *v15; // rdi
  volatile signed __int32 *v16; // rbx
  volatile signed __int32 *v18; // rbx
  PVOID P[2]; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF
  char v21; // [rsp+A8h] [rbp+50h] BYREF

  v9 = 0;
  for ( i = (*a2)[16]; ; i = (const UNICODE_STRING *)i[1].Buffer )
  {
    if ( i == (const UNICODE_STRING *)(*a2 + 13) )
      return (unsigned int)v9;
    if ( !ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedForUser_Internal<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
            a1,
            *a2,
            *(_QWORD **)&i->Length,
            a3,
            a5) )
      continue;
    v11 = *(const UNICODE_STRING **)&i->Length;
    v21 = 0;
    v12 = *(_QWORD *)&v11->Length;
    P[0] = 0;
    P[1] = 0;
    RtlInitUnicodeString(&DestinationString, 0);
    v9 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedGlobally<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
           a1,
           P,
           v12,
           &v21);
    if ( P[1] )
      ExFreePoolWithTag(P[1], 0);
    if ( v9 < 0 )
      continue;
    if ( v21 )
    {
      P[0] = 0;
      P[1] = 0;
      RtlInitUnicodeString(&DestinationString, 0);
      v9 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedGlobally<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
             a1,
             **a2,
             P,
             &v21);
      if ( P[1] )
        ExFreePoolWithTag(P[1], 0);
      if ( v9 < 0 || !v21 )
        continue;
    }
    v13 = *(const UNICODE_STRING ***)&i->Length;
    *(_OWORD *)P = 0;
    v14 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackageGroup<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
            a1,
            *v13,
            (__int64 *)P);
    if ( v14 < 0 )
      break;
    v9 = appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
           a4,
           P);
    if ( v9 < 0 )
    {
      v16 = (volatile signed __int32 *)P[1];
      if ( P[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)P[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
          if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 16LL))(v16);
        }
      }
      return (unsigned int)v9;
    }
    v15 = (volatile signed __int32 *)P[1];
    if ( P[1] && _InterlockedExchangeAdd((volatile signed __int32 *)P[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  v18 = (volatile signed __int32 *)P[1];
  if ( P[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)P[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 16LL))(v18);
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180001d4c  push    rbp
0x180001d4e  push    rbx
0x180001d4f  push    rsi
0x180001d50  push    rdi
0x180001d51  push    r12
0x180001d53  push    r13
0x180001d55  push    r14
0x180001d57  push    r15
0x180001d59  mov     rbp, rsp
0x180001d5c  sub     rsp, 58h
0x180001d60  mov     rbx, [rdx]
0x180001d63  mov     r12, r9
0x180001d66  mov     r13, r8
0x180001d69  mov     r15, rdx
0x180001d6c  mov     r14, rcx
0x180001d6f  xor     esi, esi
0x180001d71  mov     rbx, [rbx+80h]
0x180001d78  mov     rdx, [r15]
0x180001d7b  lea     rax, [rdx+68h]
0x180001d7f  cmp     rbx, rax
0x180001d82  jz      loc_180001F19
0x180001d88  mov     eax, [rbp+arg_20]
0x180001d8b  mov     r9, r13
0x180001d8e  mov     r8, [rbx]
0x180001d91  mov     rcx, r14
0x180001d94  mov     [rsp+58h+var_38], eax
0x180001d98  call    ??$IsPublishedForUser_Internal@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAA_NAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@0AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@K@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedForUser_Internal<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong)
0x180001d9d  xor     ecx, ecx
0x180001d9f  test    al, al
0x180001da1  jz      loc_180001ED0
0x180001da7  mov     rax, [rbx]
0x180001daa  xor     edx, edx; SourceString
0x180001dac  mov     [rbp+arg_8], cl
0x180001daf  mov     rdi, [rax]
0x180001db2  mov     [rbp+P], rcx
0x180001db6  mov     [rbp+P+8], rcx
0x180001dba  lea     rcx, [rbp+DestinationString]; DestinationString
0x180001dbe  call    cs:__imp_RtlInitUnicodeString
0x180001dc5  nop     dword ptr [rax+rax+00h]
0x180001dca  lea     r9, [rbp+arg_8]
0x180001dce  mov     r8, rdi
0x180001dd1  lea     rdx, [rbp+P]
0x180001dd5  mov     rcx, r14
0x180001dd8  call    ??$IsPublishedGlobally@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0AEA_N@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedGlobally<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,bool &)
0x180001ddd  mov     rcx, [rbp+P+8]; P
0x180001de1  mov     esi, eax
0x180001de3  test    rcx, rcx
0x180001de6  jz      short loc_180001DF6
0x180001de8  xor     edx, edx; Tag
0x180001dea  call    cs:__imp_ExFreePoolWithTag
0x180001df1  nop     dword ptr [rax+rax+00h]
0x180001df6  xor     ecx, ecx
0x180001df8  test    esi, esi
0x180001dfa  js      loc_180001ED0
0x180001e00  cmp     [rbp+arg_8], cl
0x180001e03  jz      short loc_180001E59
0x180001e05  mov     [rbp+P], rcx
0x180001e09  xor     edx, edx; SourceString
0x180001e0b  mov     [rbp+P+8], rcx
0x180001e0f  lea     rcx, [rbp+DestinationString]; DestinationString
0x180001e13  call    cs:__imp_RtlInitUnicodeString
0x180001e1a  nop     dword ptr [rax+rax+00h]
0x180001e1f  mov     rdx, [r15]
0x180001e22  lea     r9, [rbp+arg_8]
0x180001e26  lea     r8, [rbp+P]
0x180001e2a  mov     rcx, r14
0x180001e2d  mov     rdx, [rdx]
0x180001e30  call    ??$IsPublishedGlobally@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0AEA_N@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedGlobally<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,bool &)
0x180001e35  mov     rcx, [rbp+P+8]; P
0x180001e39  mov     esi, eax
0x180001e3b  test    rcx, rcx
0x180001e3e  jz      short loc_180001E4E
0x180001e40  xor     edx, edx; Tag
0x180001e42  call    cs:__imp_ExFreePoolWithTag
0x180001e49  nop     dword ptr [rax+rax+00h]
0x180001e4e  xor     ecx, ecx
0x180001e50  test    esi, esi
0x180001e52  js      short loc_180001ED0
0x180001e54  cmp     [rbp+arg_8], cl
0x180001e57  jz      short loc_180001ED0
0x180001e59  mov     rdx, [rbx]
0x180001e5c  lea     r8, [rbp+P]
0x180001e60  xorps   xmm0, xmm0
0x180001e63  mov     rcx, r14
0x180001e66  movdqu  xmmword ptr [rbp+P], xmm0
0x180001e6b  mov     rdx, [rdx]
0x180001e6e  call    ??$FindPackageGroup@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackageGroup<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x180001e73  mov     edi, eax
0x180001e75  test    eax, eax
0x180001e77  js      loc_180001F2D
0x180001e7d  lea     rdx, [rbp+P]
0x180001e81  mov     rcx, r12
0x180001e84  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x180001e89  mov     esi, eax
0x180001e8b  test    eax, eax
0x180001e8d  js      short loc_180001ED9
0x180001e8f  mov     rdi, [rbp+P+8]
0x180001e93  test    rdi, rdi
0x180001e96  jz      short loc_180001ED0
0x180001e98  or      eax, 0FFFFFFFFh
0x180001e9b  lock xadd [rdi+8], eax
0x180001ea0  cmp     eax, 1
0x180001ea3  jnz     short loc_180001ED0
0x180001ea5  mov     rax, [rdi]
0x180001ea8  mov     rcx, rdi
0x180001eab  mov     rax, [rax+8]
0x180001eaf  call    _guard_dispatch_icall
0x180001eb4  or      eax, 0FFFFFFFFh
0x180001eb7  lock xadd [rdi+0Ch], eax
0x180001ebc  cmp     eax, 1
0x180001ebf  jnz     short loc_180001ED0
0x180001ec1  mov     rax, [rdi]
0x180001ec4  mov     rcx, rdi
0x180001ec7  mov     rax, [rax+10h]
0x180001ecb  call    _guard_dispatch_icall
0x180001ed0  mov     rbx, [rbx+18h]
0x180001ed4  jmp     loc_180001D78
0x180001ed9  mov     rbx, [rbp+P+8]
0x180001edd  test    rbx, rbx
0x180001ee0  jz      short loc_180001F19
0x180001ee2  or      edi, 0FFFFFFFFh
0x180001ee5  mov     eax, edi
0x180001ee7  lock xadd [rbx+8], eax
0x180001eec  add     eax, edi
0x180001eee  jnz     short loc_180001F19
0x180001ef0  mov     rax, [rbx]
0x180001ef3  mov     rcx, rbx
0x180001ef6  mov     rax, [rax+8]
0x180001efa  call    _guard_dispatch_icall
0x180001eff  mov     eax, edi
0x180001f01  lock xadd [rbx+0Ch], eax
0x180001f06  add     eax, edi
0x180001f08  jnz     short loc_180001F19
0x180001f0a  mov     rax, [rbx]
0x180001f0d  mov     rcx, rbx
0x180001f10  mov     rax, [rax+10h]
0x180001f14  call    _guard_dispatch_icall
0x180001f19  mov     eax, esi
0x180001f1b  add     rsp, 58h
0x180001f1f  pop     r15
0x180001f21  pop     r14
0x180001f23  pop     r13
0x180001f25  pop     r12
0x180001f27  pop     rdi
0x180001f28  pop     rsi
0x180001f29  pop     rbx
0x180001f2a  pop     rbp
0x180001f2b  retn
0x180001f2d  mov     rbx, [rbp+P+8]
0x180001f31  test    rbx, rbx
0x180001f34  jz      short loc_180001F6D
0x180001f36  or      esi, 0FFFFFFFFh
0x180001f39  mov     eax, esi
0x180001f3b  lock xadd [rbx+8], eax
0x180001f40  add     eax, esi
0x180001f42  jnz     short loc_180001F6D
0x180001f44  mov     rax, [rbx]
0x180001f47  mov     rcx, rbx
0x180001f4a  mov     rax, [rax+8]
0x180001f4e  call    _guard_dispatch_icall
0x180001f53  mov     eax, esi
0x180001f55  lock xadd [rbx+0Ch], eax
0x180001f5a  add     eax, esi
0x180001f5c  jnz     short loc_180001F6D
0x180001f5e  mov     rax, [rbx]
0x180001f61  mov     rcx, rbx
0x180001f64  mov     rax, [rax+10h]
0x180001f68  call    _guard_dispatch_icall
0x180001f6d  mov     eax, edi
0x180001f6f  jmp     short loc_180001F1B
```
