# CDuckingManager::~CDuckingManager(void)

- ea: `0x18002f33c`
- end: `0x18002f3db`
- name: `??1CDuckingManager@@UEAA@XZ`
- size: `159`
- prototype: `void __fastcall(CDuckingManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180043a20`

## callees

- `0x180008d20`
- `0x18000ac00`
- `0x18002f33c`
- `0x18002f3e4`
- `0x18002f440`
- `0x18002f49c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f38a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f3c3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f38a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f3c3`

## pseudocode

```c
void __fastcall CDuckingManager::~CDuckingManager(CDuckingManager *this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx
  _QWORD *v4; // rcx
  _QWORD *v5; // rbx

  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 56);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 54);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  CSerialWorkQueue::~CSerialWorkQueue((CDuckingManager *)((char *)this + 240));
  std::_Hash<std::_Umap_traits<std::wstring,CRenderEndpointDuckingManagerContext,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,CRenderEndpointDuckingManagerContext>>,0>>::~_Hash<std::_Umap_traits<std::wstring,CRenderEndpointDuckingManagerContext,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,CRenderEndpointDuckingManagerContext>>,0>>((char *)this + 176);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  CLockedList_UniqueValuesOnly<CDuckingNotification,0>::~CLockedList_UniqueValuesOnly<CDuckingNotification,0>((char *)this + 72);
  v4 = (_QWORD *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v4 )
  {
    do
    {
      v5 = (_QWORD *)*v4;
      std::_Deallocate<16>(v4, 16);
      v4 = v5;
    }
    while ( v5 );
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *((_DWORD *)this + 5) = -1073741823;
}

```

## disassembly

```asm
0x18002f33c  mov     [rsp+arg_0], rbx
0x18002f341  push    rdi
0x18002f342  sub     rsp, 20h
0x18002f346  mov     rdi, rcx
0x18002f349  mov     rcx, [rcx+1C0h]; this
0x18002f350  test    rcx, rcx
0x18002f353  jz      short loc_18002F35A
0x18002f355  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002f35a  mov     rcx, [rdi+1B0h]; this
0x18002f361  test    rcx, rcx
0x18002f364  jz      short loc_18002F36B
0x18002f366  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002f36b  lea     rcx, [rdi+0F0h]; this
0x18002f372  call    ??1CSerialWorkQueue@@QEAA@XZ; CSerialWorkQueue::~CSerialWorkQueue(void)
0x18002f377  lea     rcx, [rdi+0B0h]
0x18002f37e  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCRenderEndpointDuckingManagerContext@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCRenderEndpointDuckingManagerContext@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,CRenderEndpointDuckingManagerContext,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,CRenderEndpointDuckingManagerContext>>,0>>::~_Hash<std::_Umap_traits<std::wstring,CRenderEndpointDuckingManagerContext,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,CRenderEndpointDuckingManagerContext>>,0>>(void)
0x18002f383  lea     rcx, [rdi+88h]; lpCriticalSection
0x18002f38a  call    cs:__imp_DeleteCriticalSection
0x18002f390  lea     rcx, [rdi+48h]
0x18002f394  call    ??1?$CLockedList_UniqueValuesOnly@VCDuckingNotification@@$0A@@@QEAA@XZ; CLockedList_UniqueValuesOnly<CDuckingNotification,0>::~CLockedList_UniqueValuesOnly<CDuckingNotification,0>(void)
0x18002f399  mov     rcx, [rdi+40h]
0x18002f39d  mov     qword ptr [rdi+40h], 0
0x18002f3a5  test    rcx, rcx
0x18002f3a8  jz      short loc_18002F3BF
0x18002f3aa  mov     rbx, [rcx]
0x18002f3ad  mov     edx, 10h
0x18002f3b2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002f3b7  mov     rcx, rbx
0x18002f3ba  test    rbx, rbx
0x18002f3bd  jnz     short loc_18002F3AA
0x18002f3bf  lea     rcx, [rdi+18h]; lpCriticalSection
0x18002f3c3  call    cs:__imp_DeleteCriticalSection
0x18002f3c9  mov     rbx, [rsp+28h+arg_0]
0x18002f3ce  mov     dword ptr [rdi+14h], 0C0000001h
0x18002f3d5  add     rsp, 20h
0x18002f3d9  pop     rdi
0x18002f3da  retn
```
