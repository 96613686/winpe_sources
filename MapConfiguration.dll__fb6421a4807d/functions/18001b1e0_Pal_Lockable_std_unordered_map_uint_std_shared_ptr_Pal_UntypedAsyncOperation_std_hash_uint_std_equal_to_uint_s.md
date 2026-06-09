# Pal::Lockable<std::unordered_map<uint,std::shared_ptr<Pal::UntypedAsyncOperation>,std::hash<uint>,std::equal_to<uint>,std::allocator<std::pair<uint const,std::shared_ptr<Pal::UntypedAsyncOperation>>>>>::~Lockable<std::unordered_map<uint,std::shared_ptr<Pal::UntypedAsyncOperation>,std::hash<uint>,std::equal_to<uint>,std::allocator<std::pair<uint const,std::shared_ptr<Pal::UntypedAsyncOperation>>>>>(void)

- ea: `0x18001b1e0`
- end: `0x18001b201`
- name: `??1?$Lockable@V?$unordered_map@IV?$shared_ptr@VUntypedAsyncOperation@Pal@@@std@@U?$hash@I@2@U?$equal_to@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VUntypedAsyncOperation@Pal@@@std@@@std@@@2@@std@@@Pal@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001b2f4`

## callees

- `0x18001b22c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b1fa`

## pseudocode

```c
void __fastcall Pal::Lockable<std::unordered_map<unsigned int,std::shared_ptr<Pal::UntypedAsyncOperation>>>::~Lockable<std::unordered_map<unsigned int,std::shared_ptr<Pal::UntypedAsyncOperation>>>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<Pal::UntypedAsyncOperation>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<Pal::UntypedAsyncOperation>>>,0>>::~_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<Pal::UntypedAsyncOperation>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<Pal::UntypedAsyncOperation>>>,0>>((__int64)&a1[1]);
  DeleteCriticalSection(a1);
}

```

## disassembly

```asm
0x18001b1e0  push    rbx
0x18001b1e2  sub     rsp, 20h
0x18001b1e6  mov     rbx, rcx
0x18001b1e9  add     rcx, 28h ; '('
0x18001b1ed  call    ??1?$_Hash@V?$_Umap_traits@IV?$shared_ptr@VUntypedAsyncOperation@Pal@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VUntypedAsyncOperation@Pal@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<uint,std::shared_ptr<Pal::UntypedAsyncOperation>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<Pal::UntypedAsyncOperation>>>,0>>::~_Hash<std::_Umap_traits<uint,std::shared_ptr<Pal::UntypedAsyncOperation>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<Pal::UntypedAsyncOperation>>>,0>>(void)
0x18001b1f2  mov     rcx, rbx
0x18001b1f5  add     rsp, 20h
0x18001b1f9  pop     rbx
0x18001b1fa  jmp     cs:__imp_DeleteCriticalSection
```
