# UnionFs::UnionFsFilter::ContextCleanup(void *,ushort)

- ea: `0x140008a70`
- end: `0x140008b36`
- name: `?ContextCleanup@UnionFsFilter@UnionFs@@SAXPEAXG@Z`
- size: `198`
- prototype: `void __fastcall(void *, unsigned __int16)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14000511c`
- `0x140005a8c`
- `0x140005b20`
- `0x140006240`
- `0x140008a70`
- `0x140057a3c`
- `0x140079c48`

## import_xrefs

- `ntoskrnl!FsRtlTeardownPerFileContexts` at `0x140008ada`
- `ntoskrnl!FsRtlTeardownPerFileContexts` at `0x140008ada`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008b23`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008b23`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140008aab`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140008aab`

## pseudocode

```c
void __fastcall UnionFs::UnionFsFilter::ContextCleanup(char *a1, struct _UNICODE_STRING *a2)
{
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v3; // rcx
  FSRTL_ADVANCED_FCB_HEADER *v4; // rbx
  FSRTL_ADVANCED_FCB_HEADER *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8

  if ( (_WORD)a2 == 2 )
  {
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)(a1 + 120), a2);
    utl::_Tree<_GUID,utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>,UnionFs::Utils::GuidComparator,utl::allocator<utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>>,0>::~_Tree<_GUID,utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>,UnionFs::Utils::GuidComparator,utl::allocator<utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>>,0>(a1 + 72);
    v7 = *((_QWORD *)a1 + 6);
    if ( v7 != -1 )
    {
      v8 = *((_QWORD *)a1 + 7) - v7;
      *((_QWORD *)a1 + 7) = v7;
      utl::_RangeDestroyApc<utl::allocator<utl::weak_ptr<UnionFs::UfsUnionCtx>>>(v6, v7, v8 >> 4);
      v5 = (FSRTL_ADVANCED_FCB_HEADER *)*((_QWORD *)a1 + 6);
      if ( v5 )
        goto LABEL_13;
    }
  }
  else
  {
    if ( (_WORD)a2 == 4 )
    {
      FsRtlTeardownPerFileContexts((PVOID *)a1 + 13);
      return;
    }
    if ( (_WORD)a2 != 8 )
    {
      if ( (_WORD)a2 == 16 )
        UnionFs::UfsStreamHandleCtx::~UfsStreamHandleCtx((UnionFs::UfsStreamHandleCtx *)a1);
      return;
    }
    v3 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)a1 + 16);
    if ( v3 )
      ExFreeCacheAwareRundownProtection(v3);
    utl::_Tree<_FILE_OBJECT *,_FILE_OBJECT *,UnionFs::UfsStreamCtx::SFOCompare,utl::allocator<_FILE_OBJECT *>,0>::~_Tree<_FILE_OBJECT *,_FILE_OBJECT *,UnionFs::UfsStreamCtx::SFOCompare,utl::allocator<_FILE_OBJECT *>,0>(a1 + 40);
    v4 = (FSRTL_ADVANCED_FCB_HEADER *)*((_QWORD *)a1 + 4);
    if ( v4 )
    {
      UnionFs::UfsFsContext::~UfsFsContext(v4);
      v5 = v4;
LABEL_13:
      ExFreePoolWithTag(v5, 0);
    }
  }
}

```

## disassembly

```asm
0x140008a70  push    rbx
0x140008a72  sub     rsp, 20h
0x140008a76  mov     rbx, rcx
0x140008a79  cmp     dx, 2
0x140008a7d  jz      short loc_140008AE8
0x140008a7f  cmp     dx, 4
0x140008a83  jz      short loc_140008AD6
0x140008a85  cmp     dx, 8
0x140008a89  jz      short loc_140008A9F
0x140008a8b  cmp     dx, 10h
0x140008a8f  jnz     loc_140008B2F
0x140008a95  call    ??1UfsStreamHandleCtx@UnionFs@@QEAA@XZ; UnionFs::UfsStreamHandleCtx::~UfsStreamHandleCtx(void)
0x140008a9a  jmp     loc_140008B2F
0x140008a9f  mov     rcx, [rcx+80h]; RunRefCacheAware
0x140008aa6  test    rcx, rcx
0x140008aa9  jz      short loc_140008AB7
0x140008aab  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140008ab2  nop     dword ptr [rax+rax+00h]
0x140008ab7  lea     rcx, [rbx+28h]
0x140008abb  call    ??1?$_Tree@PEAU_FILE_OBJECT@@PEAU1@USFOCompare@UfsStreamCtx@UnionFs@@V?$allocator@PEAU_FILE_OBJECT@@@utl@@$0A@@utl@@IEAA@XZ; utl::_Tree<_FILE_OBJECT *,_FILE_OBJECT *,UnionFs::UfsStreamCtx::SFOCompare,utl::allocator<_FILE_OBJECT *>,0>::~_Tree<_FILE_OBJECT *,_FILE_OBJECT *,UnionFs::UfsStreamCtx::SFOCompare,utl::allocator<_FILE_OBJECT *>,0>(void)
0x140008ac0  mov     rbx, [rbx+20h]
0x140008ac4  test    rbx, rbx
0x140008ac7  jz      short loc_140008B2F
0x140008ac9  mov     rcx, rbx; AdvancedHeader
0x140008acc  call    ??1UfsFsContext@UnionFs@@QEAA@XZ; UnionFs::UfsFsContext::~UfsFsContext(void)
0x140008ad1  mov     rcx, rbx
0x140008ad4  jmp     short loc_140008B21
0x140008ad6  add     rcx, 68h ; 'h'; PerFileContextPointer
0x140008ada  call    cs:__imp_FsRtlTeardownPerFileContexts
0x140008ae1  nop     dword ptr [rax+rax+00h]
0x140008ae6  jmp     short loc_140008B2F
0x140008ae8  add     rcx, 78h ; 'x'; UnicodeString
0x140008aec  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140008af1  lea     rcx, [rbx+48h]
0x140008af5  call    ??1?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$weak_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@UGuidComparator@Utils@UnionFs@@V?$allocator@U?$pair@$$CBU_GUID@@V?$weak_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@3@$0A@@utl@@IEAA@XZ; utl::_Tree<_GUID,utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>,UnionFs::Utils::GuidComparator,utl::allocator<utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>>,0>::~_Tree<_GUID,utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>,UnionFs::Utils::GuidComparator,utl::allocator<utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>>,0>(void)
0x140008afa  mov     rdx, [rbx+30h]
0x140008afe  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x140008b02  jz      short loc_140008B2F
0x140008b04  mov     r8, [rbx+38h]
0x140008b08  sub     r8, rdx
0x140008b0b  mov     [rbx+38h], rdx
0x140008b0f  sar     r8, 4
0x140008b13  call    ??$_RangeDestroyApc@V?$allocator@V?$weak_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$weak_ptr@VUfsUnionCtx@UnionFs@@@utl@@@0@PEAV?$weak_ptr@VUfsUnionCtx@UnionFs@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::weak_ptr<UnionFs::UfsUnionCtx>>>(utl::allocator<utl::weak_ptr<UnionFs::UfsUnionCtx>> &,utl::weak_ptr<UnionFs::UfsUnionCtx> *,unsigned __int64)
0x140008b18  mov     rcx, [rbx+30h]; P
0x140008b1c  test    rcx, rcx
0x140008b1f  jz      short loc_140008B2F
0x140008b21  xor     edx, edx; Tag
0x140008b23  call    cs:__imp_ExFreePoolWithTag
0x140008b2a  nop     dword ptr [rax+rax+00h]
0x140008b2f  add     rsp, 20h
0x140008b33  pop     rbx
0x140008b34  retn
```
