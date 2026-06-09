# CVaultMemoryStore::~CVaultMemoryStore(void)

- ea: `0x1800379f8`
- end: `0x180037a4f`
- name: `??1CVaultMemoryStore@@UEAA@XZ`
- size: `87`
- prototype: `void __fastcall(struct _RTL_RESOURCE *this, unsigned __int8)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callers

- `0x180033e9c`
- `0x18003537c`
- `0x18003db20`

## callees

- `0x180024334`
- `0x18002f4e0`
- `0x1800379f8`
- `0x180037a88`
- `0x180037b9c`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x180037a20`
- `ntdll!RtlDeleteResource` at `0x180037a20`

## pseudocode

```c
void __fastcall CVaultMemoryStore::~CVaultMemoryStore(struct _RTL_RESOURCE *this, unsigned __int8 a2)
{
  this->Lock.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CVaultMemoryStore::`vftable';
  CVaultMemoryStore::Delete((CVaultMemoryStore *)this, a2);
  if ( LOBYTE(this[1].DebugInfo) )
    RtlDeleteResource(this + 2);
  CVaultPolicy::~CVaultPolicy((CVaultPolicy *)&this->OwningThread);
  std::_Tree<std::_Tmap_traits<_tagSIDArray,unsigned long,SidCmp,std::allocator<std::pair<_tagSIDArray const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<_tagSIDArray,unsigned long,SidCmp,std::allocator<std::pair<_tagSIDArray const,unsigned long>>,0>>((_QWORD **)&this->SharedSemaphore);
  std::_Tree<std::_Tmap_traits<_VAULT_CAUB,IVaultCredential *,CaubCmp,std::allocator<std::pair<_VAULT_CAUB const,IVaultCredential *>>,1>>::~_Tree<std::_Tmap_traits<_VAULT_CAUB,IVaultCredential *,CaubCmp,std::allocator<std::pair<_VAULT_CAUB const,IVaultCredential *>>,1>>(&this->Lock.LockSemaphore);
  std::_Tree<std::_Tmap_traits<_VAULT_CAUB,IVaultCredential *,CaubCmp,std::allocator<std::pair<_VAULT_CAUB const,IVaultCredential *>>,1>>::~_Tree<std::_Tmap_traits<_VAULT_CAUB,IVaultCredential *,CaubCmp,std::allocator<std::pair<_VAULT_CAUB const,IVaultCredential *>>,1>>(&this->Lock.LockCount);
}

```

## disassembly

```asm
0x1800379f8  push    rbx
0x1800379fa  sub     rsp, 20h
0x1800379fe  mov     rbx, rcx
0x180037a01  lea     rax, ??_7CVaultMemoryStore@@6B@; const CVaultMemoryStore::`vftable'
0x180037a08  mov     [rcx], rax
0x180037a0b  call    ?Delete@CVaultMemoryStore@@IEAAXE@Z; CVaultMemoryStore::Delete(uchar)
0x180037a10  cmp     byte ptr [rbx+0B8h], 0
0x180037a17  jz      short loc_180037A26
0x180037a19  lea     rcx, [rbx+0C0h]; Resource
0x180037a20  call    cs:__imp_RtlDeleteResource
0x180037a26  lea     rcx, [rbx+48h]; this
0x180037a2a  call    ??1CVaultPolicy@@UEAA@XZ; CVaultPolicy::~CVaultPolicy(void)
0x180037a2f  lea     rcx, [rbx+28h]
0x180037a33  call    ??1?$_Tree@V?$_Tmap_traits@U_tagSIDArray@@KUSidCmp@@V?$allocator@U?$pair@$$CBU_tagSIDArray@@K@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_tagSIDArray,ulong,SidCmp,std::allocator<std::pair<_tagSIDArray const,ulong>>,0>>::~_Tree<std::_Tmap_traits<_tagSIDArray,ulong,SidCmp,std::allocator<std::pair<_tagSIDArray const,ulong>>,0>>(void)
0x180037a38  lea     rcx, [rbx+18h]
0x180037a3c  call    ??1?$_Tree@V?$_Tmap_traits@U_VAULT_CAUB@@PEAUIVaultCredential@@UCaubCmp@@V?$allocator@U?$pair@$$CBU_VAULT_CAUB@@PEAUIVaultCredential@@@std@@@std@@$00@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_VAULT_CAUB,IVaultCredential *,CaubCmp,std::allocator<std::pair<_VAULT_CAUB const,IVaultCredential *>>,1>>::~_Tree<std::_Tmap_traits<_VAULT_CAUB,IVaultCredential *,CaubCmp,std::allocator<std::pair<_VAULT_CAUB const,IVaultCredential *>>,1>>(void)
0x180037a41  lea     rcx, [rbx+8]
0x180037a45  add     rsp, 20h
0x180037a49  pop     rbx
0x180037a4a  jmp     ??1?$_Tree@V?$_Tmap_traits@U_VAULT_CAUB@@PEAUIVaultCredential@@UCaubCmp@@V?$allocator@U?$pair@$$CBU_VAULT_CAUB@@PEAUIVaultCredential@@@std@@@std@@$00@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_VAULT_CAUB,IVaultCredential *,CaubCmp,std::allocator<std::pair<_VAULT_CAUB const,IVaultCredential *>>,1>>::~_Tree<std::_Tmap_traits<_VAULT_CAUB,IVaultCredential *,CaubCmp,std::allocator<std::pair<_VAULT_CAUB const,IVaultCredential *>>,1>>(void)
```
