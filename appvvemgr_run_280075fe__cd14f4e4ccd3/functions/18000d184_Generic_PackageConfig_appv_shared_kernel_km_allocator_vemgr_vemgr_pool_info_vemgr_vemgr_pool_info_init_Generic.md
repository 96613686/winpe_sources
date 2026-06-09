# Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> const &)

- ea: `0x18000d184`
- end: `0x18000d248`
- name: `?init@?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA_NAEBV1@@Z`
- size: `196`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180001598`
- `0x180001788`

## callees

- `0x18000d184`
- `0x18000d250`
- `0x18000e588`

## pseudocode

```c
char __fastcall Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(
        __int64 a1,
        __int64 a2)
{
  char v2; // r9
  char v4; // r11
  unsigned int v6; // edx
  __int16 v7; // r8
  __int16 v8; // ax
  __int64 v9; // r10
  unsigned int v10; // ecx
  __int16 v11; // r8
  __int16 v12; // ax
  __int64 v13; // rdx
  _QWORD *v14; // rbx
  _QWORD *v15; // rdi

  v2 = *(_BYTE *)(a2 + 49);
  v4 = *(_BYTE *)(a2 + 48);
  v6 = *(_DWORD *)(a2 + 16) >> 1;
  if ( v6 > 0xFFFF )
    v7 = -1;
  else
    v7 = v6;
  v8 = 0;
  v9 = 0;
  if ( v6 <= 0xFFFF )
    v8 = v7;
  if ( v8 )
    v9 = *(_QWORD *)(a2 + 24);
  v10 = **(_DWORD **)a2 >> 1;
  if ( v10 > 0xFFFF )
    v11 = -1;
  else
    v11 = **(_DWORD **)a2 >> 1;
  v12 = 0;
  if ( v10 <= 0xFFFF )
    v12 = v11;
  if ( v12 )
    v13 = *(_QWORD *)(*(_QWORD *)a2 + 8LL);
  else
    v13 = 0;
  if ( !Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(
          a1,
          v13,
          v9,
          v4,
          v2,
          a2 + 56) )
    return 0;
  v14 = *(_QWORD **)(a2 + 128);
  v15 = (_QWORD *)(a2 + 104);
  while ( v14 != v15 )
  {
    if ( (int)appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
                a1 + 96,
                v14) < 0 )
      return 0;
    v14 = (_QWORD *)v14[3];
  }
  return 1;
}

```

## disassembly

```asm
0x18000d184  push    rbx
0x18000d186  push    rbp
0x18000d187  push    rsi
0x18000d188  push    rdi
0x18000d189  sub     rsp, 38h
0x18000d18d  mov     r9b, [rdx+31h]
0x18000d191  mov     rdi, rdx
0x18000d194  mov     r11b, [rdx+30h]
0x18000d198  mov     ebx, 0FFFFh
0x18000d19d  mov     edx, [rdx+10h]
0x18000d1a0  mov     rsi, rcx
0x18000d1a3  shr     edx, 1
0x18000d1a5  cmp     edx, ebx
0x18000d1a7  ja      short loc_18000D1AF
0x18000d1a9  movzx   r8d, dx
0x18000d1ad  jmp     short loc_18000D1B2
0x18000d1af  mov     r8d, ebx
0x18000d1b2  xor     ebp, ebp
0x18000d1b4  cmp     edx, ebx
0x18000d1b6  mov     eax, ebp
0x18000d1b8  mov     r10d, ebp
0x18000d1bb  cmovbe  ax, r8w
0x18000d1c0  test    ax, ax
0x18000d1c3  jz      short loc_18000D1C9
0x18000d1c5  mov     r10, [rdi+18h]
0x18000d1c9  mov     rdx, [rdi]
0x18000d1cc  mov     ecx, [rdx]
0x18000d1ce  shr     ecx, 1
0x18000d1d0  cmp     ecx, ebx
0x18000d1d2  ja      short loc_18000D1DA
0x18000d1d4  movzx   r8d, cx
0x18000d1d8  jmp     short loc_18000D1DD
0x18000d1da  mov     r8d, ebx
0x18000d1dd  mov     eax, ebp
0x18000d1df  cmovbe  ax, r8w
0x18000d1e4  test    ax, ax
0x18000d1e7  jnz     short loc_18000D1EE
0x18000d1e9  mov     rdx, rbp
0x18000d1ec  jmp     short loc_18000D1F2
0x18000d1ee  mov     rdx, [rdx+8]
0x18000d1f2  lea     rax, [rdi+38h]
0x18000d1f6  mov     r8, r10
0x18000d1f9  mov     [rsp+58h+var_30], rax
0x18000d1fe  mov     rcx, rsi
0x18000d201  mov     [rsp+58h+var_38], r9b
0x18000d206  mov     r9b, r11b
0x18000d209  call    ?init@?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA_NPEB_W0_N1AEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(wchar_t const *,wchar_t const *,bool,bool,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &)
0x18000d20e  test    al, al
0x18000d210  jz      short loc_18000D23C
0x18000d212  mov     rbx, [rdi+80h]
0x18000d219  add     rdi, 68h ; 'h'
0x18000d21d  cmp     rbx, rdi
0x18000d220  jz      short loc_18000D238
0x18000d222  mov     rdx, rbx
0x18000d225  lea     rcx, [rsi+60h]
0x18000d229  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x18000d22e  test    eax, eax
0x18000d230  js      short loc_18000D23C
0x18000d232  mov     rbx, [rbx+18h]
0x18000d236  jmp     short loc_18000D21D
0x18000d238  mov     al, 1
0x18000d23a  jmp     short loc_18000D23E
0x18000d23c  xor     al, al
0x18000d23e  add     rsp, 38h
0x18000d242  pop     rdi
0x18000d243  pop     rsi
0x18000d244  pop     rbp
0x18000d245  pop     rbx
0x18000d246  retn
```
