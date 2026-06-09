# appv::shared::vfs::prefix_tree<PrefixTreeContext,PrefixTreeAllocator>::insert_avl(appv::shared::vfs::prefix_tree_table &,_UNICODE_STRING const &,_UNICODE_STRING const &,appv::shared::vfs::prefix_tree_name_entry<PrefixTreeContext> * &)

- ea: `0x140011d50`
- end: `0x14001205f`
- name: `?insert_avl@?$prefix_tree@VPrefixTreeContext@@VPrefixTreeAllocator@@@vfs@shared@appv@@CAJAEAUprefix_tree_table@234@AEBU_UNICODE_STRING@@1AEAPEAU?$prefix_tree_name_entry@VPrefixTreeContext@@@234@@Z`
- size: `783`
- prototype: `__int64 __fastcall(struct _RTL_AVL_TABLE **, UNICODE_STRING *, UNICODE_STRING *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140012548`

## callees

- `0x140011d50`
- `0x140014000`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140011eda`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140011eda`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140011e20`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140011f82`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140011e20`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140011f82`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140011fed`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140011fed`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140011df5`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140011f5c`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140011df5`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140011f5c`
- `ntoskrnl!ExAllocatePool2` at `0x140011dbc`
- `ntoskrnl!ExAllocatePool2` at `0x140011e79`
- `ntoskrnl!ExAllocatePool2` at `0x140011f22`
- `ntoskrnl!ExAllocatePool2` at `0x140011fd2`
- `ntoskrnl!ExAllocatePool2` at `0x140011dbc`
- `ntoskrnl!ExAllocatePool2` at `0x140011e79`
- `ntoskrnl!ExAllocatePool2` at `0x140011f22`
- `ntoskrnl!ExAllocatePool2` at `0x140011fd2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140011ea9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140012028`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001204c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140011ea9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140012028`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001204c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140011d9e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140011f04`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140011d9e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140011f04`

## pseudocode

```c
__int64 __fastcall appv::shared::vfs::prefix_tree<PrefixTreeContext,PrefixTreeAllocator>::insert_avl(
        struct _RTL_AVL_TABLE **a1,
        UNICODE_STRING *a2,
        UNICODE_STRING *a3,
        _QWORD *a4)
{
  struct _RTL_AVL_TABLE *Pool2; // rax
  struct _RTL_AVL_TABLE *v10; // rbp
  struct _RTL_AVL_TABLE *v11; // rcx
  _WORD *inserted; // rax
  _WORD *v13; // rbx
  __int64 v14; // rax
  struct _UNICODE_STRING *v15; // rdx
  struct _RTL_AVL_TABLE *v16; // rax
  struct _UNICODE_STRING *v17; // rax
  struct _UNICODE_STRING *v18; // rdi
  __int64 v19; // rax
  unsigned __int8 v20[56]; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int8 NewElement; // [rsp+80h] [rbp+18h] BYREF

  if ( a3->Length > 0x18u )
    return 3221225485LL;
  if ( !*a1 )
  {
    if ( PrefixTreeAllocator::LookasideInited )
      Pool2 = (struct _RTL_AVL_TABLE *)ExAllocateFromPagedLookasideList(&PrefixTreeAllocator::PrefixTableLookasideList);
    else
      Pool2 = (struct _RTL_AVL_TABLE *)ExAllocatePool2(256, 104, 812664406);
    *a1 = Pool2;
    if ( !Pool2 )
      return 3221225626LL;
    RtlInitializeGenericTableAvl(
      Pool2,
      appv::shared::vfs::named_avl_table<appv::shared::vfs::prefix_tree_name_entry<PrefixTreeContext>,PrefixTreeAllocator>::named_avl_compare,
      appv::shared::vfs::named_avl_table<appv::shared::vfs::prefix_tree_name_entry<PrefixTreeContext>,PrefixTreeAllocator>::named_avl_allocate,
      appv::shared::vfs::named_avl_table<appv::shared::vfs::prefix_tree_name_entry<PrefixTreeContext>,PrefixTreeAllocator>::named_avl_free,
      0);
  }
  v10 = *a1;
  v11 = *a1;
  NewElement = 0;
  inserted = RtlInsertElementGenericTableAvl(v11, a2, 0x10u, &NewElement);
  v13 = inserted;
  if ( !inserted )
    return 3221225626LL;
  if ( NewElement )
  {
    memset(inserted, 0, 0xB0u);
    *((_QWORD *)v13 + 1) = v13 + 8;
    v13[1] = 72;
    if ( a2->Length > 0x48u )
    {
      v14 = ExAllocatePool2(256, a2->Length, 812664406);
      *((_QWORD *)v13 + 1) = v14;
      if ( !v14 )
      {
        v15 = (struct _UNICODE_STRING *)v13;
LABEL_30:
        RtlDeleteElementGenericTableAvl(v10, v15);
        return 3221225626LL;
      }
      *v13 = 0;
      v13[1] = a2->Length;
    }
    RtlCopyUnicodeString((PUNICODE_STRING)v13, a2);
  }
  *((_QWORD *)v13 + 18) = a1;
  if ( !v13[44] && a3->Length && !RtlEqualUnicodeString((PCUNICODE_STRING)v13, a3, 1u) )
  {
    if ( !a1[1] )
    {
      if ( PrefixTreeAllocator::LookasideInited )
        v16 = (struct _RTL_AVL_TABLE *)ExAllocateFromPagedLookasideList(&PrefixTreeAllocator::PrefixTableLookasideList);
      else
        v16 = (struct _RTL_AVL_TABLE *)ExAllocatePool2(256, 104, 812664406);
      a1[1] = v16;
      if ( !v16 )
        return 3221225626LL;
      RtlInitializeGenericTableAvl(
        v16,
        appv::shared::vfs::named_avl_table<appv::shared::vfs::prefix_tree_name_entry<PrefixTreeContext>,PrefixTreeAllocator>::named_avl_compare,
        appv::shared::vfs::named_avl_table<appv::shared::vfs::prefix_tree_shortname_entry,PrefixTreeAllocator>::named_avl_allocate,
        appv::shared::vfs::named_avl_table<appv::shared::vfs::prefix_tree_shortname_entry,PrefixTreeAllocator>::named_avl_free,
        0);
    }
    v10 = a1[1];
    v20[0] = 0;
    v17 = (struct _UNICODE_STRING *)RtlInsertElementGenericTableAvl(v10, a3, 0x10u, v20);
    v18 = v17;
    if ( v17 )
    {
      if ( v20[0] )
      {
        *v17 = 0;
        v17[1] = 0;
        v17[2] = 0;
        v17->Buffer = &v17[1].Length;
        v17->MaximumLength = 24;
        if ( a3->Length > 0x18u )
        {
          v19 = ExAllocatePool2(256, a3->Length, 812664406);
          v18->Buffer = (wchar_t *)v19;
          if ( !v19 )
          {
            v15 = v18;
            goto LABEL_30;
          }
          v18->Length = 0;
          v18->MaximumLength = a3->Length;
        }
        RtlCopyUnicodeString(v18, a3);
      }
      v18[2].Buffer = v13;
      *((_QWORD *)v13 + 12) = v13 + 52;
      v13[45] = 24;
      RtlCopyUnicodeString((PUNICODE_STRING)(v13 + 44), a3);
      goto LABEL_35;
    }
    return 3221225626LL;
  }
LABEL_35:
  *a4 = v13;
  return 0;
}

```

## disassembly

```asm
0x140011d50  mov     [rsp+arg_0], rbx
0x140011d55  mov     [rsp+arg_8], rbp
0x140011d5a  push    rsi
0x140011d5b  push    rdi
0x140011d5c  push    r13
0x140011d5e  push    r14
0x140011d60  push    r15
0x140011d62  sub     rsp, 40h
0x140011d66  mov     r13d, 18h
0x140011d6c  mov     r15, r9
0x140011d6f  mov     rsi, r8
0x140011d72  mov     r14, rdx
0x140011d75  mov     rdi, rcx
0x140011d78  cmp     [r8], r13w
0x140011d7c  jbe     short loc_140011D88
0x140011d7e  mov     eax, 0C000000Dh
0x140011d83  jmp     loc_140011FFE
0x140011d88  cmp     qword ptr [rcx], 0
0x140011d8c  jnz     short loc_140011E01
0x140011d8e  cmp     cs:?LookasideInited@PrefixTreeAllocator@@0_NA, 0; bool PrefixTreeAllocator::LookasideInited
0x140011d95  jz      short loc_140011DAC
0x140011d97  lea     rcx, ?PrefixTableLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140011d9e  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140011da5  nop     dword ptr [rax+rax+00h]
0x140011daa  jmp     short loc_140011DC8
0x140011dac  mov     edx, 68h ; 'h'
0x140011db1  mov     ecx, 100h
0x140011db6  mov     r8d, 30704656h
0x140011dbc  call    cs:__imp_ExAllocatePool2
0x140011dc3  nop     dword ptr [rax+rax+00h]
0x140011dc8  mov     [rdi], rax
0x140011dcb  test    rax, rax
0x140011dce  jz      loc_140011FF9
0x140011dd4  lea     r9, ?named_avl_free@?$named_avl_table@U?$prefix_tree_name_entry@VPrefixTreeContext@@@vfs@shared@appv@@VPrefixTreeAllocator@@@vfs@shared@appv@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x140011ddb  mov     [rsp+68h+TableContext], 0; TableContext
0x140011de4  lea     r8, ?named_avl_allocate@?$named_avl_table@U?$prefix_tree_name_entry@VPrefixTreeContext@@@vfs@shared@appv@@VPrefixTreeAllocator@@@vfs@shared@appv@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x140011deb  mov     rcx, rax; Table
0x140011dee  lea     rdx, ?named_avl_compare@?$named_avl_table@U?$prefix_tree_name_entry@VPrefixTreeContext@@@vfs@shared@appv@@VPrefixTreeAllocator@@@vfs@shared@appv@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x140011df5  call    cs:__imp_RtlInitializeGenericTableAvl
0x140011dfc  nop     dword ptr [rax+rax+00h]
0x140011e01  mov     rbp, [rdi]
0x140011e04  lea     r9, [rsp+68h+NewElement]; NewElement
0x140011e0c  mov     rcx, rbp; Table
0x140011e0f  mov     [rsp+68h+NewElement], 0
0x140011e17  mov     r8d, 10h; BufferSize
0x140011e1d  mov     rdx, r14; Buffer
0x140011e20  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140011e27  nop     dword ptr [rax+rax+00h]
0x140011e2c  mov     rbx, rax
0x140011e2f  test    rax, rax
0x140011e32  jz      loc_140011FF9
0x140011e38  cmp     [rsp+68h+NewElement], 0
0x140011e40  jz      short loc_140011EB5
0x140011e42  xor     edx, edx; Val
0x140011e44  mov     r8d, 0B0h; Size
0x140011e4a  mov     rcx, rax; void *
0x140011e4d  call    memset
0x140011e52  lea     rcx, [rbx+10h]
0x140011e56  mov     [rbx+8], rcx
0x140011e5a  mov     ecx, 48h ; 'H'
0x140011e5f  mov     [rbx+2], cx
0x140011e63  movzx   eax, word ptr [r14]
0x140011e67  cmp     ax, cx
0x140011e6a  jbe     short loc_140011EA3
0x140011e6c  mov     edx, eax
0x140011e6e  mov     ecx, 100h
0x140011e73  mov     r8d, 30704656h
0x140011e79  call    cs:__imp_ExAllocatePool2
0x140011e80  nop     dword ptr [rax+rax+00h]
0x140011e85  mov     [rbx+8], rax
0x140011e89  test    rax, rax
0x140011e8c  jnz     short loc_140011E96
0x140011e8e  mov     rdx, rbx
0x140011e91  jmp     loc_140011FEA
0x140011e96  xor     eax, eax
0x140011e98  mov     [rbx], ax
0x140011e9b  movzx   eax, word ptr [r14]
0x140011e9f  mov     [rbx+2], ax
0x140011ea3  mov     rdx, r14; SourceString
0x140011ea6  mov     rcx, rbx; DestinationString
0x140011ea9  call    cs:__imp_RtlCopyUnicodeString
0x140011eb0  nop     dword ptr [rax+rax+00h]
0x140011eb5  xor     eax, eax
0x140011eb7  mov     [rbx+90h], rdi
0x140011ebe  cmp     ax, [rbx+58h]
0x140011ec2  jnz     loc_140012058
0x140011ec8  cmp     ax, [rsi]
0x140011ecb  jz      loc_140012058
0x140011ed1  mov     r8b, 1; CaseInSensitive
0x140011ed4  mov     rdx, rsi; String2
0x140011ed7  mov     rcx, rbx; String1
0x140011eda  call    cs:__imp_RtlEqualUnicodeString
0x140011ee1  nop     dword ptr [rax+rax+00h]
0x140011ee6  test    al, al
0x140011ee8  jnz     loc_140012058
0x140011eee  cmp     qword ptr [rdi+8], 0
0x140011ef3  jnz     short loc_140011F68
0x140011ef5  cmp     cs:?LookasideInited@PrefixTreeAllocator@@0_NA, al; bool PrefixTreeAllocator::LookasideInited
0x140011efb  jz      short loc_140011F12
0x140011efd  lea     rcx, ?PrefixTableLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140011f04  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140011f0b  nop     dword ptr [rax+rax+00h]
0x140011f10  jmp     short loc_140011F2E
0x140011f12  mov     edx, 68h ; 'h'
0x140011f17  mov     ecx, 100h
0x140011f1c  mov     r8d, 30704656h
0x140011f22  call    cs:__imp_ExAllocatePool2
0x140011f29  nop     dword ptr [rax+rax+00h]
0x140011f2e  mov     [rdi+8], rax
0x140011f32  test    rax, rax
0x140011f35  jz      loc_140011FF9
0x140011f3b  lea     r9, ?named_avl_free@?$named_avl_table@Uprefix_tree_shortname_entry@vfs@shared@appv@@VPrefixTreeAllocator@@@vfs@shared@appv@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x140011f42  mov     [rsp+68h+TableContext], 0; TableContext
0x140011f4b  lea     r8, ?named_avl_allocate@?$named_avl_table@Uprefix_tree_shortname_entry@vfs@shared@appv@@VPrefixTreeAllocator@@@vfs@shared@appv@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x140011f52  mov     rcx, rax; Table
0x140011f55  lea     rdx, ?named_avl_compare@?$named_avl_table@U?$prefix_tree_name_entry@VPrefixTreeContext@@@vfs@shared@appv@@VPrefixTreeAllocator@@@vfs@shared@appv@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x140011f5c  call    cs:__imp_RtlInitializeGenericTableAvl
0x140011f63  nop     dword ptr [rax+rax+00h]
0x140011f68  mov     rbp, [rdi+8]
0x140011f6c  lea     r9, [rsp+68h+var_38]; NewElement
0x140011f71  mov     rcx, rbp; Table
0x140011f74  mov     [rsp+68h+var_38], 0
0x140011f79  mov     r8d, 10h; BufferSize
0x140011f7f  mov     rdx, rsi; Buffer
0x140011f82  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140011f89  nop     dword ptr [rax+rax+00h]
0x140011f8e  mov     rdi, rax
0x140011f91  test    rax, rax
0x140011f94  jz      short loc_140011FF9
0x140011f96  cmp     [rsp+68h+var_38], 0
0x140011f9b  jz      loc_140012034
0x140011fa1  xorps   xmm0, xmm0
0x140011fa4  lea     rdx, [rax+10h]
0x140011fa8  movups  xmmword ptr [rax], xmm0
0x140011fab  movups  xmmword ptr [rax+10h], xmm0
0x140011faf  movups  xmmword ptr [rax+20h], xmm0
0x140011fb3  mov     [rax+8], rdx
0x140011fb7  mov     [rax+2], r13w
0x140011fbc  movzx   eax, word ptr [rsi]
0x140011fbf  cmp     ax, r13w
0x140011fc3  jbe     short loc_140012022
0x140011fc5  mov     edx, eax
0x140011fc7  mov     ecx, 100h
0x140011fcc  mov     r8d, 30704656h
0x140011fd2  call    cs:__imp_ExAllocatePool2
0x140011fd9  nop     dword ptr [rax+rax+00h]
0x140011fde  mov     [rdi+8], rax
0x140011fe2  test    rax, rax
0x140011fe5  jnz     short loc_140012016
0x140011fe7  mov     rdx, rdi; Buffer
0x140011fea  mov     rcx, rbp; Table
0x140011fed  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140011ff4  nop     dword ptr [rax+rax+00h]
0x140011ff9  mov     eax, 0C000009Ah
0x140011ffe  mov     rbx, [rsp+68h+arg_0]
0x140012003  mov     rbp, [rsp+68h+arg_8]
0x140012008  add     rsp, 40h
0x14001200c  pop     r15
0x14001200e  pop     r14
0x140012010  pop     r13
0x140012012  pop     rdi
0x140012013  pop     rsi
0x140012014  retn
0x140012016  xor     eax, eax
0x140012018  mov     [rdi], ax
0x14001201b  movzx   eax, word ptr [rsi]
0x14001201e  mov     [rdi+2], ax
0x140012022  mov     rdx, rsi; SourceString
0x140012025  mov     rcx, rdi; DestinationString
0x140012028  call    cs:__imp_RtlCopyUnicodeString
0x14001202f  nop     dword ptr [rax+rax+00h]
0x140012034  mov     [rdi+28h], rbx
0x140012038  lea     rax, [rbx+68h]
0x14001203c  mov     rdx, rsi; SourceString
0x14001203f  mov     [rbx+60h], rax
0x140012043  lea     rcx, [rbx+58h]; DestinationString
0x140012047  mov     [rbx+5Ah], r13w
0x14001204c  call    cs:__imp_RtlCopyUnicodeString
0x140012053  nop     dword ptr [rax+rax+00h]
0x140012058  mov     [r15], rbx
0x14001205b  xor     eax, eax
0x14001205d  jmp     short loc_140011FFE
```
