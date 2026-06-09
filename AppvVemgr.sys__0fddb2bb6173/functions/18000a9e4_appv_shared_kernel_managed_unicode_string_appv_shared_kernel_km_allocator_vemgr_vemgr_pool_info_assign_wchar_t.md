# appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)

- ea: `0x18000a9e4`
- end: `0x18000ab26`
- name: `?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z`
- size: `322`
- prototype: `__int64 __fastcall(__int64, const void *, __int64, __int64)`
- caller_count: `33`
- callee_count: `3`
- tags: ``

## callers

- `0x180001504`
- `0x180003750`
- `0x1800038fc`
- `0x180009710`
- `0x18000b478`
- `0x18000bfb8`
- `0x18000c31c`
- `0x18000cf74`
- `0x18000d250`
- `0x18000d37c`
- `0x18000da60`
- `0x18000e960`
- `0x18000ef74`
- `0x180010b50`
- `0x1800110e8`
- `0x180011538`
- `0x180011bd0`
- `0x180011ca8`
- `0x180011dc8`
- `0x180012ebc`
- `0x180012fd4`
- `0x1800134a8`
- `0x180013b78`
- `0x180015524`
- `0x180016798`
- `0x1800168b0`
- `0x180016f64`
- `0x180017c7c`
- `0x18001872c`
- `0x180018ab0`
- `0x180018ea0`
- `0x180019014`
- `0x18001a79c`

## callees

- `0x18000a9e4`
- `0x18000e8d4`
- `0x18001bc00`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18000aa3a`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000ab0c`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000aa3a`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000ab0c`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
        __int64 a1,
        const void *a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v7; // esi
  const WCHAR *v8; // rdx
  unsigned int v9; // ecx
  __int16 v10; // dx
  __int16 v11; // ax
  __int64 result; // rax
  unsigned int v13; // eax
  unsigned __int16 v14; // dx
  unsigned int v15; // ecx
  __int16 v16; // dx
  __int16 v17; // ax
  __int64 v18; // r8
  __int16 v19; // dx
  unsigned __int16 v20; // ax
  const WCHAR *v21; // rdx
  unsigned int v22; // ecx
  __int16 v23; // dx
  __int16 v24; // ax

  if ( a2 )
  {
    v13 = 2 * a3 + 2;
    if ( v13 > 0xFFFF )
      v14 = -1;
    else
      v14 = 2 * a3 + 2;
    if ( v13 <= 0xFFFF )
    {
      result = appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(
                 a1,
                 v14,
                 a3,
                 a4);
      if ( (int)result >= 0 )
      {
        memmove(*(void **)(a1 + 8), a2, 2 * a3);
        if ( *(_DWORD *)a1 )
        {
          v15 = *(_DWORD *)a1 >> 1;
          if ( v15 > 0xFFFF )
            v16 = -1;
          else
            v16 = *(_DWORD *)a1 >> 1;
          v17 = 0;
          v18 = 0;
          if ( v15 <= 0xFFFF )
            v17 = v16;
          if ( v17 )
            v18 = *(_QWORD *)(a1 + 8);
          if ( v15 > 0xFFFF )
            v19 = -1;
          else
            v19 = *(_DWORD *)a1 >> 1;
          v20 = 0;
          if ( v15 <= 0xFFFF )
            v20 = v19;
          *(_WORD *)(v18 + 2LL * v20 - 2) = 0;
        }
        if ( *(_DWORD *)a1 )
        {
          v22 = *(_DWORD *)a1 >> 1;
          if ( v22 > 0xFFFF )
            v23 = -1;
          else
            v23 = *(_DWORD *)a1 >> 1;
          v24 = 0;
          if ( v22 <= 0xFFFF )
            v24 = v23;
          v21 = 0;
          if ( v24 )
            v21 = *(const WCHAR **)(a1 + 8);
        }
        else
        {
          v21 = 0;
        }
        RtlInitUnicodeString((PUNICODE_STRING)(a1 + 16), v21);
        return 0;
      }
    }
    else
    {
      return v13 > 0xFFFF ? 0xC0000095 : 0;
    }
  }
  else
  {
    v7 = appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(a1, 0, a3, a4);
    if ( *(_DWORD *)a1 )
    {
      v9 = *(_DWORD *)a1 >> 1;
      if ( v9 > 0xFFFF )
        v10 = -1;
      else
        v10 = *(_DWORD *)a1 >> 1;
      v11 = 0;
      if ( v9 <= 0xFFFF )
        v11 = v10;
      v8 = 0;
      if ( v11 )
        v8 = *(const WCHAR **)(a1 + 8);
    }
    else
    {
      v8 = 0;
    }
    RtlInitUnicodeString((PUNICODE_STRING)(a1 + 16), v8);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x18000a9e4  push    rbx
0x18000a9e6  push    rbp
0x18000a9e7  push    rsi
0x18000a9e8  push    rdi
0x18000a9e9  push    r14
0x18000a9eb  sub     rsp, 20h
0x18000a9ef  xor     r14d, r14d
0x18000a9f2  mov     rsi, r8
0x18000a9f5  mov     rbp, rdx
0x18000a9f8  mov     rdi, rcx
0x18000a9fb  test    rdx, rdx
0x18000a9fe  jnz     short loc_18000AA4D
0x18000aa00  call    ?resize@?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(ulong)
0x18000aa05  mov     ecx, [rdi]
0x18000aa07  mov     esi, eax
0x18000aa09  test    ecx, ecx
0x18000aa0b  jnz     short loc_18000AA11
0x18000aa0d  xor     edx, edx
0x18000aa0f  jmp     short loc_18000AA36
0x18000aa11  shr     ecx, 1
0x18000aa13  mov     ebx, 0FFFFh
0x18000aa18  cmp     ecx, ebx
0x18000aa1a  ja      short loc_18000AA21
0x18000aa1c  movzx   edx, cx
0x18000aa1f  jmp     short loc_18000AA23
0x18000aa21  mov     edx, ebx
0x18000aa23  mov     eax, r14d
0x18000aa26  cmovbe  ax, dx
0x18000aa2a  mov     rdx, r14
0x18000aa2d  test    ax, ax
0x18000aa30  jz      short loc_18000AA36
0x18000aa32  mov     rdx, [rdi+8]; SourceString
0x18000aa36  lea     rcx, [rdi+10h]; DestinationString
0x18000aa3a  call    cs:__imp_RtlInitUnicodeString
0x18000aa41  nop     dword ptr [rax+rax+00h]
0x18000aa46  mov     eax, esi
0x18000aa48  jmp     loc_18000AB1A
0x18000aa4d  lea     eax, ds:2[r8*2]
0x18000aa55  mov     ebx, 0FFFFh
0x18000aa5a  cmp     eax, ebx
0x18000aa5c  ja      short loc_18000AA63
0x18000aa5e  movzx   edx, ax
0x18000aa61  jmp     short loc_18000AA65
0x18000aa63  mov     edx, ebx
0x18000aa65  cmp     ebx, eax
0x18000aa67  sbb     ecx, ecx
0x18000aa69  and     ecx, 0C0000095h
0x18000aa6f  cmp     eax, ebx
0x18000aa71  jbe     short loc_18000AA7A
0x18000aa73  mov     eax, ecx
0x18000aa75  jmp     loc_18000AB1A
0x18000aa7a  movzx   edx, dx
0x18000aa7d  mov     rcx, rdi
0x18000aa80  call    ?resize@?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(ulong)
0x18000aa85  test    eax, eax
0x18000aa87  js      loc_18000AB1A
0x18000aa8d  mov     rcx, [rdi+8]; void *
0x18000aa91  lea     r8, [rsi+rsi]; Size
0x18000aa95  mov     rdx, rbp; Src
0x18000aa98  call    memmove
0x18000aa9d  mov     ecx, [rdi]
0x18000aa9f  test    ecx, ecx
0x18000aaa1  jz      short loc_18000AADE
0x18000aaa3  shr     ecx, 1
0x18000aaa5  cmp     ecx, ebx
0x18000aaa7  ja      short loc_18000AAAE
0x18000aaa9  movzx   edx, cx
0x18000aaac  jmp     short loc_18000AAB0
0x18000aaae  mov     edx, ebx
0x18000aab0  mov     eax, r14d
0x18000aab3  mov     r8, r14
0x18000aab6  cmovbe  ax, dx
0x18000aaba  test    ax, ax
0x18000aabd  jz      short loc_18000AAC3
0x18000aabf  mov     r8, [rdi+8]
0x18000aac3  cmp     ecx, ebx
0x18000aac5  ja      short loc_18000AACC
0x18000aac7  movzx   edx, cx
0x18000aaca  jmp     short loc_18000AACE
0x18000aacc  mov     edx, ebx
0x18000aace  mov     eax, r14d
0x18000aad1  cmovbe  ax, dx
0x18000aad5  movzx   ecx, ax
0x18000aad8  mov     [r8+rcx*2-2], r14w
0x18000aade  mov     ecx, [rdi]
0x18000aae0  test    ecx, ecx
0x18000aae2  jnz     short loc_18000AAE8
0x18000aae4  xor     edx, edx
0x18000aae6  jmp     short loc_18000AB08
0x18000aae8  shr     ecx, 1
0x18000aaea  cmp     ecx, ebx
0x18000aaec  ja      short loc_18000AAF3
0x18000aaee  movzx   edx, cx
0x18000aaf1  jmp     short loc_18000AAF5
0x18000aaf3  mov     edx, ebx
0x18000aaf5  mov     eax, r14d
0x18000aaf8  cmovbe  ax, dx
0x18000aafc  mov     rdx, r14
0x18000aaff  test    ax, ax
0x18000ab02  jz      short loc_18000AB08
0x18000ab04  mov     rdx, [rdi+8]; SourceString
0x18000ab08  lea     rcx, [rdi+10h]; DestinationString
0x18000ab0c  call    cs:__imp_RtlInitUnicodeString
0x18000ab13  nop     dword ptr [rax+rax+00h]
0x18000ab18  xor     eax, eax
0x18000ab1a  add     rsp, 20h
0x18000ab1e  pop     r14
0x18000ab20  pop     rdi
0x18000ab21  pop     rsi
0x18000ab22  pop     rbp
0x18000ab23  pop     rbx
0x18000ab24  retn
```
