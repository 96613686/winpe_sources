# Windows::Compat::Inventory::Service::PnpListener::~PnpListener(void)

- ea: `0x1800c1260`
- end: `0x1800c1366`
- name: `??1PnpListener@Service@Inventory@Compat@Windows@@UEAA@XZ`
- size: `262`
- prototype: `void __fastcall(Windows::Compat::Inventory::Service::PnpListener *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c1480`

## callees

- `0x180003100`
- `0x1800108d4`
- `0x1800152d0`
- `0x180020650`
- `0x1800c109c`
- `0x1800c11bc`
- `0x1800c1260`
- `0x1800c2d48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800c1301`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800c1301`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c1326`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c1326`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c12de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c12f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c12de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c12f1`

## string_xrefs

- `0x1800c133d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800c1354`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800c1294`: `Windows::Compat::Inventory::Service::PnpListener::~PnpListener`

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::Service::PnpListener::~PnpListener(
        Windows::Compat::Inventory::Service::PnpListener *this)
{
  void *v2; // rdi
  __int64 v3; // rdx
  void *v4; // rcx
  const char *v5; // r9
  void *v6; // rcx
  const char *v7; // r9
  HKEY v8; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &Windows::Compat::Inventory::Service::PnpListener::`vftable'{for `Windows::Compat::Inventory::Service::Tracer'};
  *((_QWORD *)this + 3) = &Windows::Compat::Inventory::Service::PnpListener::`vftable'{for `Windows::Compat::Inventory::Service::InvSvcTenant'};
  Windows::Compat::Inventory::Service::PnpListener::Uninitialize(this);
  AslLogCallPrintf(3, "Windows::Compat::Inventory::Service::PnpListener::~PnpListener", 347, "Shut down PnpListener");
  v2 = (void *)*((_QWORD *)this + 14);
  if ( v2 )
  {
    Windows::Compat::Inventory::Service::LRUCache::~LRUCache(*((Windows::Compat::Inventory::Service::LRUCache **)this
                                                             + 14));
    operator delete(v2, (const struct std::nothrow_t *)0x60);
  }
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>((char *)this + 96);
  std::list<std::wstring>::~list<std::wstring>((char *)this + 80);
  v4 = (void *)*((_QWORD *)this + 8);
  if ( v4 && !CloseHandle(v4) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v5);
  v6 = (void *)*((_QWORD *)this + 6);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v7);
  if ( *((_DWORD *)this + 10) )
  {
    _o_terminate(v6, v3);
    __debugbreak();
  }
  *((_QWORD *)this + 3) = &Windows::Compat::Inventory::Service::InvSvcTenant::`vftable';
  *(_QWORD *)this = &Windows::Compat::Inventory::Service::Tracer::`vftable';
  v8 = (HKEY)*((_QWORD *)this + 2);
  if ( v8 )
    RegCloseKey(v8);
}

```

## disassembly

```asm
0x1800c1260  mov     [rsp+arg_0], rbx
0x1800c1265  push    rdi
0x1800c1266  sub     rsp, 20h
0x1800c126a  mov     rbx, rcx
0x1800c126d  lea     rax, ??_7PnpListener@Service@Inventory@Compat@Windows@@6BTracer@1234@@; const Windows::Compat::Inventory::Service::PnpListener::`vftable'{for `Windows::Compat::Inventory::Service::Tracer'}
0x1800c1274  mov     [rcx], rax
0x1800c1277  lea     rax, ??_7PnpListener@Service@Inventory@Compat@Windows@@6BInvSvcTenant@1234@@; const Windows::Compat::Inventory::Service::PnpListener::`vftable'{for `Windows::Compat::Inventory::Service::InvSvcTenant'}
0x1800c127e  mov     [rcx+18h], rax
0x1800c1282  call    ?Uninitialize@PnpListener@Service@Inventory@Compat@Windows@@AEAAXXZ; Windows::Compat::Inventory::Service::PnpListener::Uninitialize(void)
0x1800c1287  lea     r9, aShutDownPnplis; "Shut down PnpListener"
0x1800c128e  mov     r8d, 15Bh
0x1800c1294  lea     rdx, aWindowsCompatI_19; "Windows::Compat::Inventory::Service::Pn"...
0x1800c129b  mov     ecx, 3
0x1800c12a0  call    AslLogCallPrintf
0x1800c12a5  mov     rdi, [rbx+70h]
0x1800c12a9  test    rdi, rdi
0x1800c12ac  jz      short loc_1800C12C3
0x1800c12ae  mov     rcx, rdi; this
0x1800c12b1  call    ??1LRUCache@Service@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::Service::LRUCache::~LRUCache(void)
0x1800c12b6  mov     edx, 60h ; '`'; struct std::nothrow_t *
0x1800c12bb  mov     rcx, rdi; void *
0x1800c12be  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c12c3  lea     rcx, [rbx+60h]
0x1800c12c7  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x1800c12cc  lea     rcx, [rbx+50h]
0x1800c12d0  call    ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x1800c12d5  mov     rcx, [rbx+40h]; hObject
0x1800c12d9  test    rcx, rcx
0x1800c12dc  jz      short loc_1800C12E8
0x1800c12de  call    cs:__imp_CloseHandle
0x1800c12e4  test    eax, eax
0x1800c12e6  jz      short loc_1800C134F
0x1800c12e8  mov     rcx, [rbx+30h]; hObject
0x1800c12ec  test    rcx, rcx
0x1800c12ef  jz      short loc_1800C12FB
0x1800c12f1  call    cs:__imp_CloseHandle
0x1800c12f7  test    eax, eax
0x1800c12f9  jz      short loc_1800C1338
0x1800c12fb  cmp     dword ptr [rbx+28h], 0
0x1800c12ff  jz      short loc_1800C1308
0x1800c1301  call    cs:__imp__o_terminate
0x1800c1307  int     3; Trap to Debugger
0x1800c1308  lea     rax, ??_7InvSvcTenant@Service@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::Service::InvSvcTenant::`vftable'
0x1800c130f  mov     [rbx+18h], rax
0x1800c1313  lea     rax, ??_7Tracer@Service@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::Service::Tracer::`vftable'
0x1800c131a  mov     [rbx], rax
0x1800c131d  mov     rcx, [rbx+10h]; hKey
0x1800c1321  test    rcx, rcx
0x1800c1324  jz      short loc_1800C132D
0x1800c1326  call    cs:__imp_RegCloseKey
0x1800c132c  nop
0x1800c132d  mov     rbx, [rsp+28h+arg_0]
0x1800c1332  add     rsp, 20h
0x1800c1336  pop     rdi
0x1800c1337  retn
0x1800c1338  mov     rcx, [rsp+28h]; this
0x1800c133d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c1344  mov     edx, 0A0Bh; void *
0x1800c1349  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800c134f  mov     rcx, [rsp+28h]; this
0x1800c1354  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c135b  mov     edx, 0A0Bh; void *
0x1800c1360  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
