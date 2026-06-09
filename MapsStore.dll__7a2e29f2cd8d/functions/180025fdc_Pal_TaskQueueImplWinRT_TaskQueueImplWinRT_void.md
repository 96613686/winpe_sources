# Pal::TaskQueueImplWinRT::~TaskQueueImplWinRT(void)

- ea: `0x180025fdc`
- end: `0x180026059`
- name: `??1TaskQueueImplWinRT@Pal@@UEAA@XZ`
- size: `125`
- prototype: `void __fastcall(Pal::TaskQueueImplWinRT *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180026ee0`

## callees

- `0x180011d28`
- `0x1800150a8`
- `0x1800259c4`
- `0x180025fdc`
- `0x18002f774`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025ff7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025ff7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026052`

## pseudocode

```c
void __fastcall Pal::TaskQueueImplWinRT::~TaskQueueImplWinRT(Pal::TaskQueueImplWinRT *this)
{
  _QWORD **v2; // rdx
  _QWORD *v3; // rdx
  _QWORD *v4; // rbx

  *(_QWORD *)this = &Pal::TaskQueueImplWinRT::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  std::unique_ptr<Pal::ManualResetEventImplWindows>::~unique_ptr<Pal::ManualResetEventImplWindows>((char *)this + 88);
  v2 = (_QWORD **)*((_QWORD *)this + 8);
  *v2[1] = 0;
  v3 = *v2;
  if ( v3 )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      std::_List_node<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>,void *>::_Freenode<std::allocator<std::_List_node<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>,void *>>>();
      v3 = v4;
    }
    while ( v4 );
  }
  std::_Deallocate<16>(*((void **)this + 8), 0x20u);
  std::_Tree<std::_Tmap_traits<unsigned int,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>((char *)this + 48);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180025fdc  mov     [rsp+arg_0], rbx
0x180025fe1  push    rdi
0x180025fe2  sub     rsp, 20h
0x180025fe6  lea     rax, ??_7TaskQueueImplWinRT@Pal@@6B@; const Pal::TaskQueueImplWinRT::`vftable'
0x180025fed  mov     rdi, rcx
0x180025ff0  mov     [rcx], rax
0x180025ff3  add     rcx, 68h ; 'h'; lpCriticalSection
0x180025ff7  call    cs:__imp_DeleteCriticalSection
0x180025ffd  lea     rcx, [rdi+58h]
0x180026001  call    ??1?$unique_ptr@VManualResetEventImplWindows@Pal@@U?$default_delete@VManualResetEventImplWindows@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::ManualResetEventImplWindows>::~unique_ptr<Pal::ManualResetEventImplWindows>(void)
0x180026006  mov     rdx, [rdi+40h]
0x18002600a  mov     rax, [rdx+8]
0x18002600e  mov     qword ptr [rax], 0
0x180026015  mov     rdx, [rdx]
0x180026018  test    rdx, rdx
0x18002601b  jz      short loc_18002602D
0x18002601d  mov     rbx, [rdx]
0x180026020  call    ??$_Freenode@V?$allocator@U?$_List_node@V?$shared_ptr@VPersistedDataLoaderAsyncOperation@MapControl@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@VPersistedDataLoaderAsyncOperation@MapControl@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@VPersistedDataLoaderAsyncOperation@MapControl@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>,void *>::_Freenode<std::allocator<std::_List_node<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>,void *>> &,std::_List_node<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>,void *> *)
0x180026025  mov     rdx, rbx
0x180026028  test    rbx, rbx
0x18002602b  jnz     short loc_18002601D
0x18002602d  mov     rcx, [rdi+40h]
0x180026031  mov     edx, 20h ; ' '
0x180026036  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002603b  lea     rcx, [rdi+30h]
0x18002603f  call    ??1?$_Tree@V?$_Tmap_traits@IUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<uint>,std::allocator<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>::~_Tree<std::_Tmap_traits<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<uint>,std::allocator<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>(void)
0x180026044  lea     rcx, [rdi+8]
0x180026048  mov     rbx, [rsp+28h+arg_0]
0x18002604d  add     rsp, 20h
0x180026051  pop     rdi
0x180026052  jmp     cs:__imp_DeleteCriticalSection
```
