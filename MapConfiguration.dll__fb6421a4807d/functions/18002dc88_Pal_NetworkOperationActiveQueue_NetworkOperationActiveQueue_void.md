# Pal::NetworkOperationActiveQueue::~NetworkOperationActiveQueue(void)

- ea: `0x18002dc88`
- end: `0x18002dcaa`
- name: `??1NetworkOperationActiveQueue@Pal@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(Pal::NetworkOperationActiveQueue *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18002cd90`
- `0x1800413e4`
- `0x1800413fa`

## callees

- `0x18002d894`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002dca3`

## pseudocode

```c
void __fastcall Pal::NetworkOperationActiveQueue::~NetworkOperationActiveQueue(Pal::NetworkOperationActiveQueue *this)
{
  std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>>>,0>>((char *)this + 48);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18002dc88  push    rbx
0x18002dc8a  sub     rsp, 20h
0x18002dc8e  mov     rbx, rcx
0x18002dc91  add     rcx, 30h ; '0'
0x18002dc95  call    ??1?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@VNetworkAsyncOperationImplementation@Pal@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VNetworkAsyncOperationImplementation@Pal@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>>>,0>>::~_Tree<std::_Tmap_traits<uint,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>>>,0>>(void)
0x18002dc9a  lea     rcx, [rbx+8]
0x18002dc9e  add     rsp, 20h
0x18002dca2  pop     rbx
0x18002dca3  jmp     cs:__imp_DeleteCriticalSection
```
