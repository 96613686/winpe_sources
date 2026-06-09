# UnionFs::UnionFsFilter::ContextCleanup(void *,ushort)

- ea: `0x140008a40`
- end: `0x140008b06`
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
- `0x140008a40`
- `0x140057bbc`
- `0x140079f68`

## import_xrefs

- `ntoskrnl!FsRtlTeardownPerFileContexts` at `0x140008aaa`
- `ntoskrnl!FsRtlTeardownPerFileContexts` at `0x140008aaa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008af3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008af3`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140008a7b`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140008a7b`

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
0x140008a40  push    rbx
0x140008a42  sub     rsp, 20h
0x140008a46  mov     rbx, rcx
0x140008a49  cmp     dx, 2
0x140008a4d  jz      short loc_140008AB8
0x140008a4f  cmp     dx, 4
0x140008a53  jz      short loc_140008AA6
0x140008a55  cmp     dx, 8
0x140008a59  jz      short loc_140008A6F
0x140008a5b  cmp     dx, 10h
0x140008a5f  jnz     loc_140008AFF
0x140008a65  call    ??1UfsStreamHandleCtx@UnionFs@@QEAA@XZ; UnionFs::UfsStreamHandleCtx::~UfsStreamHandleCtx(void)
0x140008a6a  jmp     loc_140008AFF
0x140008a6f  mov     rcx, [rcx+80h]; RunRefCacheAware
0x140008a76  test    rcx, rcx
0x140008a79  jz      short loc_140008A87
0x140008a7b  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140008a82  nop     dword ptr [rax+rax+00h]
0x140008a87  lea     rcx, [rbx+28h]
0x140008a8b  call    ??1?$_Tree@PEAU_FILE_OBJECT@@PEAU1@USFOCompare@UfsStreamCtx@UnionFs@@V?$allocator@PEAU_FILE_OBJECT@@@utl@@$0A@@utl@@IEAA@XZ; utl::_Tree<_FILE_OBJECT *,_FILE_OBJECT *,UnionFs::UfsStreamCtx::SFOCompare,utl::allocator<_FILE_OBJECT *>,0>::~_Tree<_FILE_OBJECT *,_FILE_OBJECT *,UnionFs::UfsStreamCtx::SFOCompare,utl::allocator<_FILE_OBJECT *>,0>(void)
0x140008a90  mov     rbx, [rbx+20h]
0x140008a94  test    rbx, rbx
0x140008a97  jz      short loc_140008AFF
0x140008a99  mov     rcx, rbx; AdvancedHeader
0x140008a9c  call    ??1UfsFsContext@UnionFs@@QEAA@XZ; UnionFs::UfsFsContext::~UfsFsContext(void)
0x140008aa1  mov     rcx, rbx
0x140008aa4  jmp     short loc_140008AF1
0x140008aa6  add     rcx, 68h ; 'h'; PerFileContextPointer
0x140008aaa  call    cs:__imp_FsRtlTeardownPerFileContexts
0x140008ab1  nop     dword ptr [rax+rax+00h]
0x140008ab6  jmp     short loc_140008AFF
0x140008ab8  add     rcx, 78h ; 'x'; UnicodeString
0x140008abc  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140008ac1  lea     rcx, [rbx+48h]
0x140008ac5  call    ??1?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$weak_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@UGuidComparator@Utils@UnionFs@@V?$allocator@U?$pair@$$CBU_GUID@@V?$weak_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@3@$0A@@utl@@IEAA@XZ; utl::_Tree<_GUID,utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>,UnionFs::Utils::GuidComparator,utl::allocator<utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>>,0>::~_Tree<_GUID,utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>,UnionFs::Utils::GuidComparator,utl::allocator<utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>>,0>(void)
0x140008aca  mov     rdx, [rbx+30h]
0x140008ace  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x140008ad2  jz      short loc_140008AFF
0x140008ad4  mov     r8, [rbx+38h]
0x140008ad8  sub     r8, rdx
0x140008adb  mov     [rbx+38h], rdx
0x140008adf  sar     r8, 4
0x140008ae3  call    ??$_RangeDestroyApc@V?$allocator@V?$weak_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$weak_ptr@VUfsUnionCtx@UnionFs@@@utl@@@0@PEAV?$weak_ptr@VUfsUnionCtx@UnionFs@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::weak_ptr<UnionFs::UfsUnionCtx>>>(utl::allocator<utl::weak_ptr<UnionFs::UfsUnionCtx>> &,utl::weak_ptr<UnionFs::UfsUnionCtx> *,unsigned __int64)
0x140008ae8  mov     rcx, [rbx+30h]; P
0x140008aec  test    rcx, rcx
0x140008aef  jz      short loc_140008AFF
0x140008af1  xor     edx, edx; Tag
0x140008af3  call    cs:__imp_ExFreePoolWithTag
0x140008afa  nop     dword ptr [rax+rax+00h]
0x140008aff  add     rsp, 20h
0x140008b03  pop     rbx
0x140008b04  retn
```
