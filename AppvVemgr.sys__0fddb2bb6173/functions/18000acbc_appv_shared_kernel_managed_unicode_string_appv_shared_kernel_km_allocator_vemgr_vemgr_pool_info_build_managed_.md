# appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::build_managed_unicode_string(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)

- ea: `0x18000acbc`
- end: `0x18000ad47`
- name: `?build_managed_unicode_string@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBV1234@@Z`
- size: `139`
- prototype: `__int64 __fastcall(__int64, unsigned int *, __int64, __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1800038fc`
- `0x180004c6c`
- `0x180006880`
- `0x180008048`
- `0x18000c9a8`
- `0x18000fb58`
- `0x180017c7c`

## callees

- `0x18000acbc`
- `0x18000e8d4`
- `0x18001bc00`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18000ad2f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000ad2f`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::build_managed_unicode_string(
        __int64 a1,
        unsigned int *a2,
        __int64 a3,
        __int64 a4)
{
  size_t v4; // rdi
  const void *v6; // rsi
  unsigned int v7; // edi
  const WCHAR *v8; // rdx
  unsigned int v9; // ecx
  __int16 v10; // dx
  __int16 v11; // ax

  v4 = *a2;
  v6 = (const void *)*((_QWORD *)a2 + 1);
  if ( (appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(a1, v4, a3, a4)
      & 0xC0000000) == 0xC0000000 )
  {
    v7 = -1073741670;
  }
  else
  {
    memmove(*(void **)(a1 + 8), v6, v4);
    v7 = 0;
  }
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

```

## disassembly

```asm
0x18000acbc  push    rbx
0x18000acbe  push    rbp
0x18000acbf  push    rsi
0x18000acc0  push    rdi
0x18000acc1  sub     rsp, 28h
0x18000acc5  mov     edi, [rdx]
0x18000acc7  mov     rbx, rcx
0x18000acca  mov     rsi, [rdx+8]
0x18000acce  mov     edx, edi
0x18000acd0  call    ?resize@?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(ulong)
0x18000acd5  mov     ecx, 0C0000000h
0x18000acda  xor     ebp, ebp
0x18000acdc  and     eax, ecx
0x18000acde  cmp     eax, ecx
0x18000ace0  jnz     short loc_18000ACE9
0x18000ace2  mov     edi, 0C000009Ah
0x18000ace7  jmp     short loc_18000ACFA
0x18000ace9  mov     rcx, [rbx+8]; void *
0x18000aced  mov     r8, rdi; Size
0x18000acf0  mov     rdx, rsi; Src
0x18000acf3  call    memmove
0x18000acf8  mov     edi, ebp
0x18000acfa  mov     ecx, [rbx]
0x18000acfc  test    ecx, ecx
0x18000acfe  jnz     short loc_18000AD04
0x18000ad00  xor     edx, edx
0x18000ad02  jmp     short loc_18000AD2B
0x18000ad04  shr     ecx, 1
0x18000ad06  mov     r8d, 0FFFFh
0x18000ad0c  cmp     ecx, r8d
0x18000ad0f  ja      short loc_18000AD16
0x18000ad11  movzx   edx, cx
0x18000ad14  jmp     short loc_18000AD19
0x18000ad16  mov     edx, r8d
0x18000ad19  mov     eax, ebp
0x18000ad1b  cmovbe  ax, dx
0x18000ad1f  mov     rdx, rbp
0x18000ad22  test    ax, ax
0x18000ad25  jz      short loc_18000AD2B
0x18000ad27  mov     rdx, [rbx+8]; SourceString
0x18000ad2b  lea     rcx, [rbx+10h]; DestinationString
0x18000ad2f  call    cs:__imp_RtlInitUnicodeString
0x18000ad36  nop     dword ptr [rax+rax+00h]
0x18000ad3b  mov     eax, edi
0x18000ad3d  add     rsp, 28h
0x18000ad41  pop     rdi
0x18000ad42  pop     rsi
0x18000ad43  pop     rbp
0x18000ad44  pop     rbx
0x18000ad45  retn
```
