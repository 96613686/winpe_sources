# Pal::TaskQueueImplWinRT::cancelWorkItems(void)

- ea: `0x180015d54`
- end: `0x180015e8d`
- name: `?cancelWorkItems@TaskQueueImplWinRT@Pal@@AEAAXXZ`
- size: `313`
- prototype: `void __fastcall(Pal::TaskQueueImplWinRT *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015d10`

## callees

- `0x18000b4b8`
- `0x18000d9b8`
- `0x180010220`
- `0x180011224`
- `0x180012158`
- `0x180014b48`
- `0x180015d54`
- `0x180015ef0`
- `0x180017350`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015d7e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015d7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015e01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015e01`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Pal::TaskQueueImplWinRT::cancelWorkItems(Pal::TaskQueueImplWinRT *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  void **v3; // rdi
  _QWORD *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 *v8; // r8
  __int64 i; // rcx
  __int64 v10; // rbx
  __int64 v11; // rcx
  void *v12[2]; // [rsp+20h] [rbp-10h] BYREF
  __int64 v13; // [rsp+40h] [rbp+10h] BYREF
  __int64 v14; // [rsp+48h] [rbp+18h] BYREF

  std::map<unsigned int,Pal::TaskQueueImplWinRT::AsyncActionAndTask>::map<unsigned int,Pal::TaskQueueImplWinRT::AsyncActionAndTask>(v12);
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v13 = (__int64)this + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v3 = (void **)((char *)this + 48);
  if ( v12 != v3 )
  {
    std::_Tree<std::_Tmap_traits<unsigned int,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>::clear(v12);
    v4 = std::_Tree<std::_Tmap_traits<unsigned int,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>::_Copy_nodes<0>(
           (__int64 *)v12,
           *((_QWORD *)*v3 + 1),
           (__int64)v12[0]);
    *((_QWORD *)v12[0] + 1) = v4;
    v12[1] = v3[1];
    v6 = *((_QWORD *)v12[0] + 1);
    if ( *(_BYTE *)(v6 + 25) )
    {
      *(_QWORD *)v12[0] = v12[0];
      *((void **)v12[0] + 2) = v12[0];
    }
    else
    {
      v7 = std::_Tree_val<std::_Tree_simple_types<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>>::_Min(
             v6,
             v5,
             v12[0]);
      *v8 = v7;
      for ( i = *((_QWORD *)v12[0] + 1); !*(_BYTE *)(*(_QWORD *)(i + 16) + 25LL); i = *(_QWORD *)(i + 16) )
        ;
      *((_QWORD *)v12[0] + 2) = i;
    }
  }
  LeaveCriticalSection(v2);
  v10 = *(_QWORD *)v12[0];
  v14 = *(_QWORD *)v12[0];
  while ( !*(_BYTE *)(v10 + 25) )
  {
    v13 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    anonymous_namespace_::getAsyncActionInfo(
      *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(v10 + 40),
      (__int64)&v13);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 72LL))(v13);
    v11 = *(_QWORD *)(v10 + 48);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>>,std::_Iterator_base0>::operator++(&v14);
    v10 = v14;
  }
  std::_Tree<std::_Tmap_traits<unsigned int,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>(v12);
}

```

## disassembly

```asm
0x180015d54  mov     [rsp-8+arg_10], rbx
0x180015d59  mov     [rsp-8+arg_18], rdi
0x180015d5e  push    rbp
0x180015d5f  mov     rbp, rsp
0x180015d62  sub     rsp, 30h
0x180015d66  mov     rdi, rcx
0x180015d69  lea     rcx, [rbp+var_10]
0x180015d6d  call    ??0?$map@IUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@@5@@std@@QEAA@XZ; std::map<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask>::map<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask>(void)
0x180015d72  nop
0x180015d73  lea     rbx, [rdi+8]
0x180015d77  mov     [rbp+arg_0], rbx
0x180015d7b  mov     rcx, rbx; lpCriticalSection
0x180015d7e  call    cs:__imp_EnterCriticalSection
0x180015d84  nop
0x180015d85  add     rdi, 30h ; '0'
0x180015d89  lea     rax, [rbp+var_10]
0x180015d8d  cmp     rax, rdi
0x180015d90  jz      short loc_180015DFE
0x180015d92  lea     rcx, [rbp+var_10]
0x180015d96  call    ?clear@?$_Tree@V?$_Tmap_traits@IUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@@5@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<uint>,std::allocator<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>::clear(void)
0x180015d9b  mov     rdx, [rdi]
0x180015d9e  mov     r8, [rbp+var_10]
0x180015da2  mov     rdx, [rdx+8]
0x180015da6  lea     rcx, [rbp+var_10]
0x180015daa  call    ??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@IUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@@5@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@PEAX@1@PEAU21@0@Z; std::_Tree<std::_Tmap_traits<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<uint>,std::allocator<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> *,std::_Tree_node<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> *)
0x180015daf  mov     rcx, [rbp+var_10]
0x180015db3  mov     [rcx+8], rax
0x180015db7  mov     rax, [rdi+8]
0x180015dbb  mov     [rbp+var_8], rax
0x180015dbf  mov     r8, [rbp+var_10]
0x180015dc3  mov     rcx, [r8+8]
0x180015dc7  cmp     byte ptr [rcx+19h], 0
0x180015dcb  jnz     short loc_180015DF3
0x180015dcd  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<MapControl::ConfigurationKeys const,std::wstring>>>::_Min(std::_Tree_node<std::pair<MapControl::ConfigurationKeys const,std::wstring>,void *> *)
0x180015dd2  mov     [r8], rax
0x180015dd5  mov     rdx, [rbp+var_10]
0x180015dd9  mov     rcx, [rdx+8]
0x180015ddd  jmp     short loc_180015DE3
0x180015ddf  mov     rcx, [rcx+10h]
0x180015de3  mov     rax, [rcx+10h]
0x180015de7  cmp     byte ptr [rax+19h], 0
0x180015deb  jz      short loc_180015DDF
0x180015ded  mov     [rdx+10h], rcx
0x180015df1  jmp     short loc_180015DFE
0x180015df3  mov     [r8], r8
0x180015df6  mov     rax, [rbp+var_10]
0x180015dfa  mov     [rax+10h], rax
0x180015dfe  mov     rcx, rbx; lpCriticalSection
0x180015e01  call    cs:__imp_LeaveCriticalSection
0x180015e07  mov     rbx, [rbp+var_10]
0x180015e0b  mov     rbx, [rbx]
0x180015e0e  mov     [rbp+arg_8], rbx
0x180015e12  cmp     byte ptr [rbx+19h], 0
0x180015e16  jnz     short loc_180015E74
0x180015e18  mov     [rbp+arg_0], 0
0x180015e20  lea     rcx, [rbp+arg_0]
0x180015e24  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015e29  lea     rdx, [rbp+arg_0]
0x180015e2d  mov     rcx, [rbx+28h]
0x180015e31  call    _anonymous_namespace___getAsyncActionInfo
0x180015e36  mov     rcx, [rbp+arg_0]
0x180015e3a  mov     rax, [rcx]
0x180015e3d  mov     rax, [rax+48h]
0x180015e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e46  mov     rcx, [rbx+30h]
0x180015e4a  test    rcx, rcx
0x180015e4d  jz      short loc_180015E5C
0x180015e4f  mov     rax, [rcx]
0x180015e52  mov     rax, [rax+8]
0x180015e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e5b  nop
0x180015e5c  lea     rcx, [rbp+arg_0]
0x180015e60  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015e65  lea     rcx, [rbp+arg_8]
0x180015e69  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<MapControl::ConfigurationKeys const,std::wstring>>>,std::_Iterator_base0>::operator++(void)
0x180015e6e  mov     rbx, [rbp+arg_8]
0x180015e72  jmp     short loc_180015E12
0x180015e74  lea     rcx, [rbp+var_10]
0x180015e78  call    ??1?$_Tree@V?$_Tmap_traits@IUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<uint>,std::allocator<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>::~_Tree<std::_Tmap_traits<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<uint>,std::allocator<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>(void)
0x180015e7d  mov     rbx, [rsp+30h+arg_10]
0x180015e82  mov     rdi, [rsp+30h+arg_18]
0x180015e87  add     rsp, 30h
0x180015e8b  pop     rbp
0x180015e8c  retn
```
