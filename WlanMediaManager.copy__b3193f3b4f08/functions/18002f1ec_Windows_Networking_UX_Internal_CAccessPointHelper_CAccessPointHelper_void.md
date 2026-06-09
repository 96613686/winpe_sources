# Windows::Networking::UX::Internal::CAccessPointHelper::~CAccessPointHelper(void)

- ea: `0x18002f1ec`
- end: `0x18002f288`
- name: `??1CAccessPointHelper@Internal@UX@Networking@Windows@@EEAA@XZ`
- size: `156`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CAccessPointHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18002f340`

## callees

- `0x18000de4c`
- `0x18002f148`
- `0x18002f1ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f26f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f26f`
- `TetheringStation!TetheringStationDeinitialize` at `0x18002f23e`
- `TetheringStation!TetheringStationDeinitialize` at `0x18002f23e`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::CAccessPointHelper::~CAccessPointHelper(
        Windows::Networking::UX::Internal::CAccessPointHelper *this)
{
  PVOID *v2; // rcx

  *(_QWORD *)this = &Windows::Networking::UX::Internal::CAccessPointHelper::`vftable';
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_BYTE *)this + 12) )
  {
    TetheringStationDeinitialize();
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 )
    WPP_SF_(v2[2], 26, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  std::_Tree<std::_Tmap_traits<_GUID,Windows::Networking::UX::Internal::CAccessPointHelper::CachedPrivilegedAccessPointList,std::less<_GUID>,std::allocator<std::pair<_GUID const,Windows::Networking::UX::Internal::CAccessPointHelper::CachedPrivilegedAccessPointList>>,0>>::~_Tree<std::_Tmap_traits<_GUID,Windows::Networking::UX::Internal::CAccessPointHelper::CachedPrivilegedAccessPointList,std::less<_GUID>,std::allocator<std::pair<_GUID const,Windows::Networking::UX::Internal::CAccessPointHelper::CachedPrivilegedAccessPointList>>,0>>((char *)this + 16);
}

```

## disassembly

```asm
0x18002f1ec  mov     [rsp+arg_0], rbx
0x18002f1f1  push    rdi
0x18002f1f2  sub     rsp, 20h
0x18002f1f6  mov     rbx, rcx
0x18002f1f9  lea     rax, ??_7CAccessPointHelper@Internal@UX@Networking@Windows@@6B@; const Windows::Networking::UX::Internal::CAccessPointHelper::`vftable'
0x18002f200  mov     [rcx], rax
0x18002f203  lea     rdi, WPP_GLOBAL_Control
0x18002f20a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f211  cmp     rcx, rdi
0x18002f214  jz      short loc_18002F238
0x18002f216  test    byte ptr [rcx+1Ch], 40h
0x18002f21a  jz      short loc_18002F238
0x18002f21c  mov     edx, 19h
0x18002f221  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x18002f228  mov     rcx, [rcx+10h]
0x18002f22c  call    WPP_SF_
0x18002f231  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f238  cmp     byte ptr [rbx+0Ch], 0
0x18002f23c  jz      short loc_18002F24B
0x18002f23e  call    cs:__imp_?TetheringStationDeinitialize@@YAXXZ; TetheringStationDeinitialize(void)
0x18002f244  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f24b  cmp     rcx, rdi
0x18002f24e  jz      short loc_18002F26B
0x18002f250  test    byte ptr [rcx+1Ch], 40h
0x18002f254  jz      short loc_18002F26B
0x18002f256  mov     edx, 1Ah
0x18002f25b  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x18002f262  mov     rcx, [rcx+10h]
0x18002f266  call    WPP_SF_
0x18002f26b  lea     rcx, [rbx+20h]; lpCriticalSection
0x18002f26f  call    cs:__imp_DeleteCriticalSection
0x18002f275  lea     rcx, [rbx+10h]
0x18002f279  mov     rbx, [rsp+28h+arg_0]
0x18002f27e  add     rsp, 20h
0x18002f282  pop     rdi
0x18002f283  jmp     ??1?$_Tree@V?$_Tmap_traits@U_GUID@@VCachedPrivilegedAccessPointList@CAccessPointHelper@Internal@UX@Networking@Windows@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@VCachedPrivilegedAccessPointList@CAccessPointHelper@Internal@UX@Networking@Windows@@@std@@@9@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,Windows::Networking::UX::Internal::CAccessPointHelper::CachedPrivilegedAccessPointList,std::less<_GUID>,std::allocator<std::pair<_GUID const,Windows::Networking::UX::Internal::CAccessPointHelper::CachedPrivilegedAccessPointList>>,0>>::~_Tree<std::_Tmap_traits<_GUID,Windows::Networking::UX::Internal::CAccessPointHelper::CachedPrivilegedAccessPointList,std::less<_GUID>,std::allocator<std::pair<_GUID const,Windows::Networking::UX::Internal::CAccessPointHelper::CachedPrivilegedAccessPointList>>,0>>(void)
```
