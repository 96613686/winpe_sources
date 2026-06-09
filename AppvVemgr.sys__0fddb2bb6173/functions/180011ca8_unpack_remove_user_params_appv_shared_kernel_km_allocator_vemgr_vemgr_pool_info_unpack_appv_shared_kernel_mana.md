# unpack_remove_user_params<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::unpack<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(uchar const *,ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)

- ea: `0x180011ca8`
- end: `0x180011dc1`
- name: `??$unpack@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$unpack_remove_user_params@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@SAJPEBEKAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@11@Z`
- size: `281`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, _DWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800130ec`

## callees

- `0x180001504`
- `0x18000a9e4`
- `0x180011ca8`

## pseudocode

```c
__int64 __fastcall unpack_remove_user_params<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::unpack<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
        unsigned __int16 *a1,
        unsigned int a2,
        _DWORD *a3,
        __int64 a4,
        __int64 a5)
{
  unsigned __int64 v8; // r10
  unsigned __int16 *v9; // rsi
  __int64 v10; // rcx
  unsigned int v11; // edi
  char *v12; // rdx
  __int64 result; // rax
  unsigned __int64 v14; // r8
  __int64 v15; // rcx
  char *v16; // rdx
  int v17; // edx
  __int64 v18; // rcx
  char *v19; // rcx
  NTSTATUS v20; // eax
  unsigned int v21; // ecx

  if ( !a1 || a2 < 0x10 )
    return 3221225990LL;
  v8 = a1[3];
  v9 = a1 + 8;
  v10 = a1[2];
  v11 = a2 - 16;
  if ( __PAIR32__(v8, v10) )
  {
    if ( (unsigned int)v10 > v11 || (int)v10 + (int)v8 > v11 )
      return 3221225485LL;
    v12 = (char *)v9 + v10;
  }
  else
  {
    v12 = 0;
  }
  result = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
             a3,
             v12,
             v8 >> 1);
  if ( (int)result < 0 )
    return result;
  v14 = a1[5];
  v15 = a1[4];
  if ( __PAIR32__(v14, v15) )
  {
    if ( (unsigned int)v15 > v11 || (int)v15 + (int)v14 > v11 )
      return 3221225485LL;
    v16 = (char *)v9 + v15;
  }
  else
  {
    v16 = 0;
  }
  result = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
             a4,
             v16,
             v14 >> 1);
  if ( (int)result < 0 )
    return result;
  v17 = a1[7];
  v18 = a1[6];
  if ( __PAIR32__(v17, v18) )
  {
    if ( (unsigned int)v18 > v11 || (int)v18 + v17 > v11 )
      return 3221225485LL;
    v19 = (char *)v9 + v18;
  }
  else
  {
    v19 = 0;
  }
  if ( *a3 <= 2u || !v19 || !(_WORD)v17 )
    return 3221225485LL;
  v20 = appv::shared::kernel::ConvertSid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(v19, a5);
  v21 = 0;
  if ( v20 < 0 )
    return (unsigned int)v20;
  return v21;
}

```

## disassembly

```asm
0x180011ca8  push    rbx
0x180011caa  push    rbp
0x180011cab  push    rsi
0x180011cac  push    rdi
0x180011cad  push    r14
0x180011caf  push    r15
0x180011cb1  sub     rsp, 28h
0x180011cb5  xor     r15d, r15d
0x180011cb8  mov     r14, r9
0x180011cbb  mov     rbp, r8
0x180011cbe  mov     rbx, rcx
0x180011cc1  test    rcx, rcx
0x180011cc4  jz      loc_180011DAE
0x180011cca  cmp     edx, 10h
0x180011ccd  jb      loc_180011DAE
0x180011cd3  movzx   r10d, word ptr [rcx+6]
0x180011cd8  lea     rsi, [rcx+10h]
0x180011cdc  movzx   ecx, word ptr [rcx+4]
0x180011ce0  lea     edi, [rdx-10h]
0x180011ce3  test    r10w, r10w
0x180011ce7  jnz     short loc_180011CF3
0x180011ce9  test    cx, cx
0x180011cec  jnz     short loc_180011CF3
0x180011cee  mov     edx, r15d
0x180011cf1  jmp     short loc_180011D0B
0x180011cf3  cmp     ecx, edi
0x180011cf5  ja      loc_180011DA7
0x180011cfb  lea     eax, [rcx+r10]
0x180011cff  cmp     eax, edi
0x180011d01  ja      loc_180011DA7
0x180011d07  lea     rdx, [rsi+rcx]
0x180011d0b  mov     r8, r10
0x180011d0e  mov     rcx, rbp
0x180011d11  shr     r8, 1
0x180011d14  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x180011d19  test    eax, eax
0x180011d1b  js      loc_180011DB3
0x180011d21  movzx   r8d, word ptr [rbx+0Ah]
0x180011d26  movzx   ecx, word ptr [rbx+8]
0x180011d2a  test    r8w, r8w
0x180011d2e  jnz     short loc_180011D3A
0x180011d30  test    cx, cx
0x180011d33  jnz     short loc_180011D3A
0x180011d35  mov     rdx, r15
0x180011d38  jmp     short loc_180011D4A
0x180011d3a  cmp     ecx, edi
0x180011d3c  ja      short loc_180011DA7
0x180011d3e  lea     eax, [rcx+r8]
0x180011d42  cmp     eax, edi
0x180011d44  ja      short loc_180011DA7
0x180011d46  lea     rdx, [rsi+rcx]
0x180011d4a  shr     r8, 1
0x180011d4d  mov     rcx, r14
0x180011d50  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x180011d55  test    eax, eax
0x180011d57  js      short loc_180011DB3
0x180011d59  movzx   edx, word ptr [rbx+0Eh]
0x180011d5d  movzx   ecx, word ptr [rbx+0Ch]
0x180011d61  test    dx, dx
0x180011d64  jnz     short loc_180011D70
0x180011d66  test    cx, cx
0x180011d69  jnz     short loc_180011D70
0x180011d6b  mov     rcx, r15
0x180011d6e  jmp     short loc_180011D7E
0x180011d70  cmp     ecx, edi
0x180011d72  ja      short loc_180011DA7
0x180011d74  lea     eax, [rcx+rdx]
0x180011d77  cmp     eax, edi
0x180011d79  ja      short loc_180011DA7
0x180011d7b  add     rcx, rsi; Sid
0x180011d7e  cmp     dword ptr [rbp+0], 2
0x180011d82  jbe     short loc_180011DA7
0x180011d84  test    rcx, rcx
0x180011d87  jz      short loc_180011DA7
0x180011d89  test    dx, dx
0x180011d8c  jz      short loc_180011DA7
0x180011d8e  mov     rdx, [rsp+58h+arg_20]
0x180011d96  call    ??$ConvertSid@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@012@@Z; appv::shared::kernel::ConvertSid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x180011d9b  test    eax, eax
0x180011d9d  mov     ecx, r15d
0x180011da0  cmovs   ecx, eax
0x180011da3  mov     eax, ecx
0x180011da5  jmp     short loc_180011DB3
0x180011da7  mov     eax, 0C000000Dh
0x180011dac  jmp     short loc_180011DB3
0x180011dae  mov     eax, 0C0000206h
0x180011db3  add     rsp, 28h
0x180011db7  pop     r15
0x180011db9  pop     r14
0x180011dbb  pop     rdi
0x180011dbc  pop     rsi
0x180011dbd  pop     rbp
0x180011dbe  pop     rbx
0x180011dbf  retn
```
