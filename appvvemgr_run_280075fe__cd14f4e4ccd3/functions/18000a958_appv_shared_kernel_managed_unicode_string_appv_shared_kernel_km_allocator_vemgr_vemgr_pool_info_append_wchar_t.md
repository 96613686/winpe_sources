# appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(wchar_t const *)

- ea: `0x18000a958`
- end: `0x18000a9db`
- name: `?append@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJPEB_W@Z`
- size: `131`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b478`
- `0x18000e354`
- `0x180013f40`
- `0x180014470`
- `0x180017c7c`

## callees

- `0x18000a864`
- `0x18000a958`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(
        unsigned int *a1,
        __int64 a2)
{
  unsigned int v4; // ecx
  __int64 v5; // rax
  unsigned int v6; // ecx
  __int16 v7; // dx
  __int128 v9; // [rsp+20h] [rbp-18h] BYREF

  if ( a2 )
  {
    v5 = -1;
    v9 = 0;
    do
      ++v5;
    while ( *(_WORD *)(a2 + 2 * v5) );
    v6 = 2 * (unsigned __int16)v5;
    if ( v6 > 0xFFFF )
      v7 = -1;
    else
      v7 = 2 * v5;
    v4 = v6 > 0xFFFF ? 0xC0000095 : 0;
    if ( (v4 & 0xC0000000) != 0xC0000000 )
    {
      WORD1(v9) = v7;
      LOWORD(v9) = v7;
      *((_QWORD *)&v9 + 1) = a2;
      return (unsigned int)appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(
                             a1,
                             (const void **)&v9);
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v4;
}

```

## disassembly

```asm
0x18000a958  sub     rsp, 38h
0x18000a95c  mov     r9, rcx
0x18000a95f  mov     r8, rdx
0x18000a962  xor     ecx, ecx
0x18000a964  test    rdx, rdx
0x18000a967  jnz     short loc_18000A970
0x18000a969  mov     ecx, 0C000000Dh
0x18000a96e  jmp     short loc_18000A9D3
0x18000a970  xorps   xmm0, xmm0
0x18000a973  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a977  movups  [rsp+38h+var_18], xmm0
0x18000a97c  inc     rax
0x18000a97f  cmp     [rdx+rax*2], cx
0x18000a983  jnz     short loc_18000A97C
0x18000a985  movzx   ecx, ax
0x18000a988  mov     eax, 0FFFFh
0x18000a98d  add     rcx, rcx
0x18000a990  cmp     ecx, eax
0x18000a992  ja      short loc_18000A999
0x18000a994  movzx   edx, cx
0x18000a997  jmp     short loc_18000A99B
0x18000a999  mov     edx, eax
0x18000a99b  cmp     eax, ecx
0x18000a99d  mov     r10d, 0C0000000h
0x18000a9a3  sbb     ecx, ecx
0x18000a9a5  and     ecx, 0C0000095h
0x18000a9ab  mov     eax, ecx
0x18000a9ad  and     eax, r10d
0x18000a9b0  cmp     eax, r10d
0x18000a9b3  jz      short loc_18000A9D3
0x18000a9b5  mov     word ptr [rsp+38h+var_18+2], dx
0x18000a9ba  mov     rcx, r9
0x18000a9bd  mov     word ptr [rsp+38h+var_18], dx
0x18000a9c2  lea     rdx, [rsp+38h+var_18]
0x18000a9c7  mov     qword ptr [rsp+38h+var_18+8], r8
0x18000a9cc  call    ?append@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(_UNICODE_STRING const &)
0x18000a9d1  mov     ecx, eax
0x18000a9d3  mov     eax, ecx
0x18000a9d5  add     rsp, 38h
0x18000a9d9  retn
```
