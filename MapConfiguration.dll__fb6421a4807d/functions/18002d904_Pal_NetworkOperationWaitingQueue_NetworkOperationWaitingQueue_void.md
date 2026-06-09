# Pal::NetworkOperationWaitingQueue::~NetworkOperationWaitingQueue(void)

- ea: `0x18002d904`
- end: `0x18002d92a`
- name: `??1NetworkOperationWaitingQueue@Pal@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(Pal::NetworkOperationWaitingQueue *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18002cd90`
- `0x1800413d2`
- `0x180041410`

## callees

- `0x18002d894`
- `0x18002d9d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d923`

## pseudocode

```c
void __fastcall Pal::NetworkOperationWaitingQueue::~NetworkOperationWaitingQueue(struct _RTL_CRITICAL_SECTION *this)
{
  Pal::NetworkOperationWaitingQueue::abortAll(this);
  std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>>>,0>>(&this[1]);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18002d904  push    rbx
0x18002d906  sub     rsp, 20h
0x18002d90a  mov     rbx, rcx
0x18002d90d  call    ?abortAll@NetworkOperationWaitingQueue@Pal@@QEAAXXZ; Pal::NetworkOperationWaitingQueue::abortAll(void)
0x18002d912  lea     rcx, [rbx+28h]
0x18002d916  call    ??1?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@VNetworkAsyncOperationImplementation@Pal@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VNetworkAsyncOperationImplementation@Pal@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>>>,0>>::~_Tree<std::_Tmap_traits<uint,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>>>,0>>(void)
0x18002d91b  mov     rcx, rbx
0x18002d91e  add     rsp, 20h
0x18002d922  pop     rbx
0x18002d923  jmp     cs:__imp_DeleteCriticalSection
```
