# CAxisUrlCache::~CAxisUrlCache(void)

- ea: `0x180011c74`
- end: `0x180011caa`
- name: `??1CAxisUrlCache@@UEAA@XZ`
- size: `54`
- prototype: `void __fastcall(CAxisUrlCache *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011ce0`

## callees

- `0x180011c08`
- `0x180011c74`
- `0x180012034`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x180011c96`
- `ntdll!RtlDeleteResource` at `0x180011c96`

## pseudocode

```c
void __fastcall CAxisUrlCache::~CAxisUrlCache(CAxisUrlCache *this)
{
  *(_QWORD *)this = &CAxisUrlCache::`vftable';
  CAxisUrlCache::RemoveAll(this);
  if ( *((_DWORD *)this + 6) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 32));
  std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::~_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>((char *)this + 8);
}

```

## disassembly

```asm
0x180011c74  push    rbx
0x180011c76  sub     rsp, 20h
0x180011c7a  lea     rax, ??_7CAxisUrlCache@@6B@; const CAxisUrlCache::`vftable'
0x180011c81  mov     rbx, rcx
0x180011c84  mov     [rcx], rax
0x180011c87  call    ?RemoveAll@CAxisUrlCache@@QEAAJXZ; CAxisUrlCache::RemoveAll(void)
0x180011c8c  cmp     dword ptr [rbx+18h], 0
0x180011c90  jz      short loc_180011C9C
0x180011c92  lea     rcx, [rbx+20h]; Resource
0x180011c96  call    cs:__imp_RtlDeleteResource
0x180011c9c  lea     rcx, [rbx+8]
0x180011ca0  add     rsp, 20h
0x180011ca4  pop     rbx
0x180011ca5  jmp     ??1?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@PEAVCAxISUrlEntry@@UAxISCaseInsensitiveLessThan@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::~_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>(void)
```
