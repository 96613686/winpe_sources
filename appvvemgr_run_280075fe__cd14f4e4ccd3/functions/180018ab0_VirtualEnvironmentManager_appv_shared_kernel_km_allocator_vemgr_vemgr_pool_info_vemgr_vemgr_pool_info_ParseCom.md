# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ParseCommonAppvVESwitch(ulong,_UNICODE_STRING const *,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,_UNICODE_STRING const *)

- ea: `0x180018ab0`
- end: `0x180018b94`
- name: `?ParseCommonAppvVESwitch@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAA_NKPEBU_UNICODE_STRING@@AEAV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0@Z`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018848`
- `0x180018964`

## callees

- `0x180002cb4`
- `0x180003f50`
- `0x18000a9e4`
- `0x180018ab0`
- `0x18001a380`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180018b00`
- `ntoskrnl!ExAllocatePool2` at `0x180018b00`
- `ntoskrnl!RtlInitUnicodeString` at `0x180018b21`
- `ntoskrnl!RtlInitUnicodeString` at `0x180018b21`

## pseudocode

```c
bool __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ParseCommonAppvVESwitch(
        __int64 a1,
        unsigned int a2,
        const struct _UNICODE_STRING *a3,
        _QWORD *a4,
        __int64 a5,
        struct _UNICODE_STRING *a6)
{
  __int64 v6; // rbp
  __int64 Pool2; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  struct _UNICODE_STRING v12; // [rsp+20h] [rbp-38h] BYREF

  v6 = a2;
  v12 = 0;
  if ( !appv::shared::kernel::command_line_processor::get_argument_value_from_command_line(a3, a6, &v12) || !v12.Length )
    return 0;
  Pool2 = ExAllocatePool2(64, 32, 1715758931);
  v9 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = 0;
    *(_QWORD *)(Pool2 + 8) = 0;
    RtlInitUnicodeString((PUNICODE_STRING)(Pool2 + 16), 0);
  }
  else
  {
    v9 = 0;
  }
  kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
    a4,
    v9);
  return *a4
      && (v10 = a4[1]) != 0
      && *(_DWORD *)(v10 + 8)
      && (int)appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
                *a4,
                v12.Buffer,
                (unsigned __int64)v12.Length >> 1) >= 0
      && (int)appv::shared::kernel::SidFromPid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(v6, a5, 0) >= 0;
}

```

## disassembly

```asm
0x180018ab0  push    rbx
0x180018ab2  push    rbp
0x180018ab3  push    rdi
0x180018ab4  push    r14
0x180018ab6  sub     rsp, 38h
0x180018aba  mov     rcx, r8; struct _UNICODE_STRING *
0x180018abd  mov     ebp, edx
0x180018abf  mov     rdx, [rsp+58h+arg_28]; struct _UNICODE_STRING *
0x180018ac7  lea     r8, [rsp+58h+var_38]; struct _UNICODE_STRING *
0x180018acc  xorps   xmm0, xmm0
0x180018acf  mov     rdi, r9
0x180018ad2  movups  xmmword ptr [rsp+58h+var_38.Length], xmm0
0x180018ad7  call    ?get_argument_value_from_command_line@command_line_processor@kernel@shared@appv@@SA_NPEBU_UNICODE_STRING@@0AEAU5@@Z; appv::shared::kernel::command_line_processor::get_argument_value_from_command_line(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING &)
0x180018adc  xor     r14d, r14d
0x180018adf  test    al, al
0x180018ae1  jz      loc_180018B87
0x180018ae7  cmp     [rsp+58h+var_38.Length], r14w
0x180018aed  jz      loc_180018B87
0x180018af3  lea     edx, [r14+20h]
0x180018af7  mov     r8d, 66446753h
0x180018afd  lea     ecx, [rdx+20h]
0x180018b00  call    cs:__imp_ExAllocatePool2
0x180018b07  nop     dword ptr [rax+rax+00h]
0x180018b0c  mov     rbx, rax
0x180018b0f  test    rax, rax
0x180018b12  jz      short loc_180018B2F
0x180018b14  lea     rcx, [rax+10h]; DestinationString
0x180018b18  mov     [rax], r14
0x180018b1b  xor     edx, edx; SourceString
0x180018b1d  mov     [rax+8], r14
0x180018b21  call    cs:__imp_RtlInitUnicodeString
0x180018b28  nop     dword ptr [rax+rax+00h]
0x180018b2d  jmp     short loc_180018B32
0x180018b2f  mov     rbx, r14
0x180018b32  mov     rdx, rbx
0x180018b35  mov     rcx, rdi
0x180018b38  call    ??$reset@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAAXPEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)
0x180018b3d  cmp     [rdi], r14
0x180018b40  jz      short loc_180018B87
0x180018b42  mov     rax, [rdi+8]
0x180018b46  test    rax, rax
0x180018b49  jz      short loc_180018B87
0x180018b4b  mov     eax, [rax+8]
0x180018b4e  test    eax, eax
0x180018b50  jz      short loc_180018B87
0x180018b52  movzx   r8d, [rsp+58h+var_38.Length]
0x180018b58  mov     rdx, [rsp+58h+var_38.Buffer]
0x180018b5d  mov     rcx, [rdi]
0x180018b60  shr     r8, 1
0x180018b63  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x180018b68  test    eax, eax
0x180018b6a  js      short loc_180018B87
0x180018b6c  mov     rdx, [rsp+58h+arg_20]
0x180018b74  mov     rcx, rbp
0x180018b77  xor     r8d, r8d
0x180018b7a  call    ??$SidFromPid@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@012@PEAE@Z; appv::shared::kernel::SidFromPid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,uchar *)
0x180018b7f  test    eax, eax
0x180018b81  js      short loc_180018B87
0x180018b83  mov     al, 1
0x180018b85  jmp     short loc_180018B89
0x180018b87  xor     al, al
0x180018b89  add     rsp, 38h
0x180018b8d  pop     r14
0x180018b8f  pop     rdi
0x180018b90  pop     rbp
0x180018b91  pop     rbx
0x180018b92  retn
```
