# appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_package_root<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_package_root<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)

- ea: `0x180002f20`
- end: `0x18000302d`
- name: `??$find_first_element@U?$find_by_package_root@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEBA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@123@AEAU?$find_by_package_root@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001788`

## callees

- `0x180002f20`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x180003000`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180003000`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_package_root<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  const UNICODE_STRING **v3; // rsi
  const UNICODE_STRING **v4; // r9
  const UNICODE_STRING *v7; // rax
  const UNICODE_STRING *v8; // r11
  unsigned int v9; // eax
  unsigned int v10; // ecx
  unsigned __int16 v11; // r10
  unsigned int v12; // edx
  __int16 v13; // r8
  unsigned __int16 v14; // ax
  unsigned __int16 v15; // dx
  unsigned __int16 v16; // ax

  *(_QWORD *)a2 = 0;
  v3 = (const UNICODE_STRING **)(a1 + 8);
  v4 = *(const UNICODE_STRING ***)(a1 + 32);
  for ( *(_QWORD *)a2 = v4; v4 != v3; *(_QWORD *)a2 = v4 )
  {
    if ( *v4 )
    {
      v7 = v4[1];
      if ( v7 )
      {
        if ( LODWORD(v7->Buffer) )
        {
          v8 = *v4;
          v9 = *(_DWORD *)&(*v4)[1].Length >> 1;
          v10 = v9;
          if ( v9 > 0xFFFF )
            LOWORD(v9) = -1;
          v11 = 0;
          if ( v10 <= 0xFFFF )
            v11 = v9;
          v12 = **(_DWORD **)a3 >> 1;
          if ( v12 > 0xFFFF )
            v13 = -1;
          else
            v13 = **(_DWORD **)a3 >> 1;
          v14 = 0;
          if ( v12 <= 0xFFFF )
            v14 = v13;
          if ( v11 < v14 && (!*(_BYTE *)(a3 + 24) || HIBYTE(v8[3].Length)) )
          {
            v15 = v10 > 0xFFFF ? -1 : v10;
            v16 = 0;
            if ( v10 <= 0xFFFF )
              v16 = v15;
            if ( *(_WORD *)(*(_QWORD *)(a3 + 16) + 2LL * v16 - 2) == 92 )
            {
              *(_WORD *)(a3 + 8) = v8[2].Length;
              if ( !RtlCompareUnicodeString(*v4 + 2, (PCUNICODE_STRING)(a3 + 8), 1u) )
                break;
            }
          }
        }
      }
    }
    v4 = *(const UNICODE_STRING ***)(*(_QWORD *)a2 + 24LL);
  }
  return a2;
}

```

## disassembly

```asm
0x180002f20  push    rbx
0x180002f22  push    rsi
0x180002f23  push    rdi
0x180002f24  push    r14
0x180002f26  sub     rsp, 28h
0x180002f2a  mov     qword ptr [rdx], 0
0x180002f31  lea     rsi, [rcx+8]
0x180002f35  mov     r9, [rcx+20h]
0x180002f39  mov     rdi, r8
0x180002f3c  mov     [rdx], r9
0x180002f3f  mov     rbx, rdx
0x180002f42  mov     r14d, 0FFFFh
0x180002f48  cmp     r9, rsi
0x180002f4b  jz      loc_18000301F
0x180002f51  cmp     qword ptr [r9], 0
0x180002f55  jz      loc_180003010
0x180002f5b  mov     rax, [r9+8]
0x180002f5f  test    rax, rax
0x180002f62  jz      loc_180003010
0x180002f68  mov     eax, [rax+8]
0x180002f6b  test    eax, eax
0x180002f6d  jz      loc_180003010
0x180002f73  mov     r11, [r9]
0x180002f76  mov     eax, [r11+10h]
0x180002f7a  shr     eax, 1
0x180002f7c  mov     ecx, eax
0x180002f7e  cmp     eax, r14d
0x180002f81  jbe     short loc_180002F86
0x180002f83  mov     eax, r14d
0x180002f86  xor     r10d, r10d
0x180002f89  cmp     ecx, r14d
0x180002f8c  cmovbe  r10w, ax
0x180002f91  mov     rax, [rdi]
0x180002f94  mov     edx, [rax]
0x180002f96  shr     edx, 1
0x180002f98  cmp     edx, r14d
0x180002f9b  ja      short loc_180002FA3
0x180002f9d  movzx   r8d, dx
0x180002fa1  jmp     short loc_180002FA6
0x180002fa3  mov     r8d, r14d
0x180002fa6  xor     eax, eax
0x180002fa8  cmp     edx, r14d
0x180002fab  cmovbe  ax, r8w
0x180002fb0  cmp     r10w, ax
0x180002fb4  jnb     short loc_180003010
0x180002fb6  cmp     byte ptr [rdi+18h], 0
0x180002fba  jz      short loc_180002FC3
0x180002fbc  cmp     byte ptr [r11+31h], 0
0x180002fc1  jz      short loc_180003010
0x180002fc3  mov     r8, [rdi+10h]
0x180002fc7  cmp     ecx, r14d
0x180002fca  ja      short loc_180002FD1
0x180002fcc  movzx   edx, cx
0x180002fcf  jmp     short loc_180002FD4
0x180002fd1  mov     edx, r14d
0x180002fd4  xor     eax, eax
0x180002fd6  cmp     ecx, r14d
0x180002fd9  cmovbe  ax, dx
0x180002fdd  movzx   eax, ax
0x180002fe0  cmp     word ptr [r8+rax*2-2], 5Ch ; '\'
0x180002fe7  jnz     short loc_180003010
0x180002fe9  movzx   eax, word ptr [r11+20h]
0x180002fee  lea     rdx, [rdi+8]; String2
0x180002ff2  mov     [rdi+8], ax
0x180002ff6  mov     r8b, 1; CaseInSensitive
0x180002ff9  mov     rcx, [r9]
0x180002ffc  add     rcx, 20h ; ' '; String1
0x180003000  call    cs:__imp_RtlCompareUnicodeString
0x180003007  nop     dword ptr [rax+rax+00h]
0x18000300c  test    eax, eax
0x18000300e  jz      short loc_18000301F
0x180003010  mov     rax, [rbx]
0x180003013  mov     r9, [rax+18h]
0x180003017  mov     [rbx], r9
0x18000301a  jmp     loc_180002F48
0x18000301f  mov     rax, rbx
0x180003022  add     rsp, 28h
0x180003026  pop     r14
0x180003028  pop     rdi
0x180003029  pop     rsi
0x18000302a  pop     rbx
0x18000302b  retn
```
