# StandardCollectorHost::`vector deleting destructor'(uint)

- ea: `0x140004958`
- end: `0x1400049c0`
- name: `??_EStandardCollectorHost@@UEAAPEAXI@Z`
- size: `104`
- prototype: `StandardCollectorHost *__fastcall(StandardCollectorHost *this, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140004c60`

## callees

- `0x140001fac`
- `0x140004958`
- `0x140004a8c`
- `0x14001382c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000497d`
- `KERNEL32!DeleteCriticalSection` at `0x14000497d`

## pseudocode

```c
StandardCollectorHost *__fastcall StandardCollectorHost::`vector deleting destructor'(
        StandardCollectorHost *this,
        char a2)
{
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>((__int64)this + 112);
  std::list<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>::~list<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>((void **)this + 12);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  *((_QWORD *)this + 4) = &CModuleRefCount::`vftable';
  _InterlockedDecrement((volatile signed __int32 *)&CModuleRefCount::s_ulcModuleRef);
  *((_QWORD *)this + 4) = &CRefCount::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140004958  mov     [rsp+arg_0], rbx
0x14000495d  push    rdi
0x14000495e  sub     rsp, 20h
0x140004962  mov     rdi, rcx
0x140004965  mov     ebx, edx
0x140004967  add     rcx, 70h ; 'p'
0x14000496b  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>(void)
0x140004970  lea     rcx, [rdi+60h]
0x140004974  call    ??1?$list@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>::~list<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>(void)
0x140004979  lea     rcx, [rdi+30h]; lpCriticalSection
0x14000497d  call    cs:__imp_DeleteCriticalSection
0x140004983  lea     rax, ??_7CModuleRefCount@@6B@; const CModuleRefCount::`vftable'
0x14000498a  mov     [rdi+20h], rax
0x14000498e  lea     rax, ??_7CRefCount@@6B@; const CRefCount::`vftable'
0x140004995  lock dec cs:?s_ulcModuleRef@CModuleRefCount@@0KA; ulong CModuleRefCount::s_ulcModuleRef
0x14000499c  mov     [rdi+20h], rax
0x1400049a0  test    bl, 1
0x1400049a3  jz      short loc_1400049B2
0x1400049a5  mov     edx, 98h
0x1400049aa  mov     rcx, rdi; Block
0x1400049ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400049b2  mov     rbx, [rsp+28h+arg_0]
0x1400049b7  mov     rax, rdi
0x1400049ba  add     rsp, 20h
0x1400049be  pop     rdi
0x1400049bf  retn
```
