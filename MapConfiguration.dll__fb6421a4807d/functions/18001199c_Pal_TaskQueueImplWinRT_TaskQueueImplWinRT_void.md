# Pal::TaskQueueImplWinRT::~TaskQueueImplWinRT(void)

- ea: `0x18001199c`
- end: `0x180011a19`
- name: `??1TaskQueueImplWinRT@Pal@@UEAA@XZ`
- size: `125`
- prototype: `void __fastcall(Pal::TaskQueueImplWinRT *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180012b30`

## callees

- `0x18000b938`
- `0x18000e324`
- `0x180011224`
- `0x18001199c`
- `0x18001bb2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800119b7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800119b7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011a12`

## pseudocode

```c
void __fastcall Pal::TaskQueueImplWinRT::~TaskQueueImplWinRT(Pal::TaskQueueImplWinRT *this)
{
  __int64 v2; // rcx
  _QWORD **v3; // rdx
  _QWORD *v4; // rdx
  _QWORD *v5; // rbx

  *(_QWORD *)this = &Pal::TaskQueueImplWinRT::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  std::unique_ptr<Pal::ManualResetEventImplWindows>::~unique_ptr<Pal::ManualResetEventImplWindows>((char *)this + 88);
  v3 = (_QWORD **)*((_QWORD *)this + 8);
  *v3[1] = 0;
  v4 = *v3;
  if ( v4 )
  {
    do
    {
      v5 = (_QWORD *)*v4;
      std::_List_node<std::shared_ptr<Pal::Task>,void *>::_Freenode<std::allocator<std::_List_node<std::shared_ptr<Pal::Task>,void *>>>(
        v2,
        v4);
      v4 = v5;
    }
    while ( v5 );
  }
  std::_Deallocate<16>(*((void **)this + 8), 0x20u);
  std::_Tree<std::_Tmap_traits<unsigned int,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>((void **)this + 6);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18001199c  mov     [rsp+arg_0], rbx
0x1800119a1  push    rdi
0x1800119a2  sub     rsp, 20h
0x1800119a6  lea     rax, ??_7TaskQueueImplWinRT@Pal@@6B@; const Pal::TaskQueueImplWinRT::`vftable'
0x1800119ad  mov     rdi, rcx
0x1800119b0  mov     [rcx], rax
0x1800119b3  add     rcx, 68h ; 'h'; lpCriticalSection
0x1800119b7  call    cs:__imp_DeleteCriticalSection
0x1800119bd  lea     rcx, [rdi+58h]
0x1800119c1  call    ??1?$unique_ptr@VManualResetEventImplWindows@Pal@@U?$default_delete@VManualResetEventImplWindows@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::ManualResetEventImplWindows>::~unique_ptr<Pal::ManualResetEventImplWindows>(void)
0x1800119c6  mov     rdx, [rdi+40h]
0x1800119ca  mov     rax, [rdx+8]
0x1800119ce  mov     qword ptr [rax], 0
0x1800119d5  mov     rdx, [rdx]
0x1800119d8  test    rdx, rdx
0x1800119db  jz      short loc_1800119ED
0x1800119dd  mov     rbx, [rdx]
0x1800119e0  call    ??$_Freenode@V?$allocator@U?$_List_node@V?$shared_ptr@VTask@Pal@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@VTask@Pal@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@VTask@Pal@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<Pal::Task>,void *>::_Freenode<std::allocator<std::_List_node<std::shared_ptr<Pal::Task>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<Pal::Task>,void *>> &,std::_List_node<std::shared_ptr<Pal::Task>,void *> *)
0x1800119e5  mov     rdx, rbx
0x1800119e8  test    rbx, rbx
0x1800119eb  jnz     short loc_1800119DD
0x1800119ed  mov     rcx, [rdi+40h]
0x1800119f1  mov     edx, 20h ; ' '
0x1800119f6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800119fb  lea     rcx, [rdi+30h]
0x1800119ff  call    ??1?$_Tree@V?$_Tmap_traits@IUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<uint>,std::allocator<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>::~_Tree<std::_Tmap_traits<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<uint>,std::allocator<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>(void)
0x180011a04  lea     rcx, [rdi+8]
0x180011a08  mov     rbx, [rsp+28h+arg_0]
0x180011a0d  add     rsp, 20h
0x180011a11  pop     rdi
0x180011a12  jmp     cs:__imp_DeleteCriticalSection
```
