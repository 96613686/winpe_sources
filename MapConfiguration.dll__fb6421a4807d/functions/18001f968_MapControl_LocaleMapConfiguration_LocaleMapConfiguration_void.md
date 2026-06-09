# MapControl::LocaleMapConfiguration::~LocaleMapConfiguration(void)

- ea: `0x18001f968`
- end: `0x18001f9e6`
- name: `??1LocaleMapConfiguration@MapControl@@QEAA@XZ`
- size: `126`
- prototype: `void __fastcall(MapControl::LocaleMapConfiguration *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001ff20`

## callees

- `0x18000c354`
- `0x180010d7c`
- `0x18001dc60`
- `0x18001f568`
- `0x18001f968`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f9d3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f9d3`

## pseudocode

```c
void __fastcall MapControl::LocaleMapConfiguration::~LocaleMapConfiguration(MapControl::LocaleMapConfiguration *this)
{
  if ( *((_BYTE *)this + 505) )
    *((_BYTE *)this + 505) = 0;
  std::_Tree<std::_Tmap_traits<int,std::wstring,std::less<int>,std::allocator<std::pair<int const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<int,std::wstring,std::less<int>,std::allocator<std::pair<int const,std::wstring>>,0>>((char *)this + 480);
  std::wstring::_Tidy_deallocate((char *)this + 448);
  std::wstring::_Tidy_deallocate((char *)this + 416);
  std::wstring::_Tidy_deallocate((char *)this + 384);
  std::wstring::_Tidy_deallocate((char *)this + 352);
  std::_Tree_val<std::_Tree_simple_types<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>,void *>>>(
    (void **)this + 42,
    (__int64)this + 336);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
  Pal::CppEvent<>::~CppEvent<>((__int64)this);
}

```

## disassembly

```asm
0x18001f968  push    rbx
0x18001f96a  sub     rsp, 20h
0x18001f96e  cmp     byte ptr [rcx+1F9h], 0
0x18001f975  mov     rbx, rcx
0x18001f978  jz      short loc_18001F981
0x18001f97a  mov     byte ptr [rcx+1F9h], 0
0x18001f981  add     rcx, 1E0h
0x18001f988  call    ??1?$_Tree@V?$_Tmap_traits@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<int,std::wstring,std::less<int>,std::allocator<std::pair<int const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<int,std::wstring,std::less<int>,std::allocator<std::pair<int const,std::wstring>>,0>>(void)
0x18001f98d  lea     rcx, [rbx+1C0h]
0x18001f994  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f999  lea     rcx, [rbx+1A0h]
0x18001f9a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f9a5  lea     rcx, [rbx+180h]
0x18001f9ac  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f9b1  lea     rcx, [rbx+160h]
0x18001f9b8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f9bd  lea     rcx, [rbx+150h]
0x18001f9c4  mov     rdx, rcx
0x18001f9c7  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<MapControl::ConfigurationKeys const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<MapControl::ConfigurationKeys const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<MapControl::ConfigurationKeys const,std::wstring>,void *>> &)
0x18001f9cc  lea     rcx, [rbx+128h]; lpCriticalSection
0x18001f9d3  call    cs:__imp_DeleteCriticalSection
0x18001f9d9  mov     rcx, rbx
0x18001f9dc  add     rsp, 20h
0x18001f9e0  pop     rbx
0x18001f9e1  jmp     ??1?$CppEvent@$$V@Pal@@QEAA@XZ; Pal::CppEvent<>::~CppEvent<>(void)
```
