# appv::shared::vfs::named_avl_table<appv::shared::vfs::prefix_tree_name_entry<PrefixTreeContext>,PrefixTreeAllocator>::named_avl_compare(_RTL_AVL_TABLE *,void *,void *)

- ea: `0x1400120b0`
- end: `0x1400120e5`
- name: `?named_avl_compare@?$named_avl_table@U?$prefix_tree_name_entry@VPrefixTreeContext@@@vfs@shared@appv@@VPrefixTreeAllocator@@@vfs@shared@appv@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z`
- size: `53`
- prototype: `__int64 __fastcall(struct _RTL_AVL_TABLE *Table, const UNICODE_STRING *FirstStruct, const UNICODE_STRING *SecondStruct)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400120b0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1400120c0`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400120c0`

## pseudocode

```c
__int64 __fastcall appv::shared::vfs::named_avl_table<appv::shared::vfs::prefix_tree_name_entry<PrefixTreeContext>,PrefixTreeAllocator>::named_avl_compare(
        struct _RTL_AVL_TABLE *Table,
        const UNICODE_STRING *FirstStruct,
        const UNICODE_STRING *SecondStruct)
{
  LONG v3; // ecx

  v3 = RtlCompareUnicodeString(FirstStruct, SecondStruct, 1u);
  if ( v3 >= 0 )
    return (unsigned int)(v3 <= 0) + 1;
  else
    return 0;
}

```

## disassembly

```asm
0x1400120b0  sub     rsp, 28h
0x1400120b4  mov     rax, r8
0x1400120b7  mov     rcx, rdx; String1
0x1400120ba  mov     rdx, rax; String2
0x1400120bd  mov     r8b, 1; CaseInSensitive
0x1400120c0  call    cs:__imp_RtlCompareUnicodeString
0x1400120c7  nop     dword ptr [rax+rax+00h]
0x1400120cc  mov     ecx, eax
0x1400120ce  test    eax, eax
0x1400120d0  jns     short loc_1400120D6
0x1400120d2  xor     eax, eax
0x1400120d4  jmp     short loc_1400120DF
0x1400120d6  xor     eax, eax
0x1400120d8  test    ecx, ecx
0x1400120da  setle   al
0x1400120dd  inc     eax
0x1400120df  add     rsp, 28h
0x1400120e3  retn
```
