# Pal::NetworkOperationQueueManager::tryRemoveRequest(uint,bool,Pal::NetworkOperationActiveQueue *)

- ea: `0x18002d034`
- end: `0x18002d11e`
- name: `?tryRemoveRequest@NetworkOperationQueueManager@Pal@@AEAA_NI_NPEAVNetworkOperationActiveQueue@2@@Z`
- size: `234`
- prototype: `bool __fastcall(Pal::NetworkOperationQueueManager *__hidden this, unsigned int, bool, struct Pal::NetworkOperationActiveQueue *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18002cfc4`

## callees

- `0x180011f48`
- `0x180013da8`
- `0x18002ce54`
- `0x18002d034`
- `0x18002d5a0`
- `0x18002d994`
- `0x18002da70`
- `0x18002dacc`
- `0x18002dbd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d05b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d05b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Pal::NetworkOperationQueueManager::tryRemoveRequest(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned int a2,
        char a3,
        struct Pal::NetworkOperationActiveQueue *a4)
{
  _QWORD *v8; // rbp
  __int64 v9; // rbx
  char v10; // bl
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  struct Pal::NetworkOperationActiveQueue *v13; // [rsp+20h] [rbp-38h] BYREF
  std::_Ref_count_base *v14[2]; // [rsp+28h] [rbp-30h] BYREF
  unsigned int v15; // [rsp+68h] [rbp+10h] BYREF
  __int64 v16; // [rsp+78h] [rbp+20h] BYREF

  v13 = a4;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a4 + 8));
  *(_OWORD *)v14 = 0;
  v15 = a2;
  v8 = (_QWORD *)((char *)a4 + 48);
  std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>>>,0>>::find(
    (char *)a4 + 48,
    &v16,
    &v15);
  v9 = v16;
  if ( v16 == *v8 )
  {
    v10 = 0;
  }
  else
  {
    std::shared_ptr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::operator=(v14, v16 + 40);
    std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>>>,0>>::_Erase_unchecked(
      v8,
      v9);
    v10 = 1;
    if ( a3 )
      v11 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 184);
    else
      v11 = this + 6;
    Pal::NetworkOperationWaitingQueue::add(v11, v14);
  }
  if ( v14[1] )
    std::_Ref_count_base::_Decref(v14[1]);
  Pal::NetworkOperationActiveQueueLock::~NetworkOperationActiveQueueLock((Pal::NetworkOperationActiveQueueLock *)&v13);
  if ( v10 )
  {
    Pal::NetworkOperationQueueManager::processQueuedRequests((Pal::NetworkOperationQueueManager *)this);
    if ( !a3 )
      Pal::NetworkOperationWaitingQueue::remove(this + 6, a2);
  }
  return v10;
}

```

## disassembly

```asm
0x18002d034  mov     [rsp+arg_0], rbx
0x18002d039  mov     [rsp+arg_10], rbp
0x18002d03e  push    rsi
0x18002d03f  push    rdi
0x18002d040  push    r14
0x18002d042  sub     rsp, 40h
0x18002d046  mov     rbx, r9
0x18002d049  mov     sil, r8b
0x18002d04c  mov     r14d, edx
0x18002d04f  mov     rdi, rcx
0x18002d052  mov     [rsp+58h+var_38], rbx
0x18002d057  lea     rcx, [r9+8]; lpCriticalSection
0x18002d05b  call    cs:__imp_EnterCriticalSection
0x18002d061  nop
0x18002d062  xorps   xmm0, xmm0
0x18002d065  movdqu  xmmword ptr [rsp+58h+var_30], xmm0
0x18002d06b  mov     [rsp+58h+arg_8], r14d
0x18002d070  lea     rbp, [rbx+30h]
0x18002d074  lea     r8, [rsp+58h+arg_8]
0x18002d079  lea     rdx, [rsp+58h+arg_18]
0x18002d07e  mov     rcx, rbp
0x18002d081  call    ?find@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@VNetworkAsyncOperationImplementation@Pal@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VNetworkAsyncOperationImplementation@Pal@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@VNetworkAsyncOperationImplementation@Pal@@@std@@@std@@@std@@@std@@@2@AEBI@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>>>,0>>::find(uint const &)
0x18002d086  mov     rbx, [rsp+58h+arg_18]
0x18002d08b  cmp     rbx, [rbp+0]
0x18002d08f  jz      short loc_18002D0CD
0x18002d091  lea     rdx, [rbx+28h]
0x18002d095  lea     rcx, [rsp+58h+var_30]
0x18002d09a  call    ??4?$shared_ptr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::operator=(std::shared_ptr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>> const &)
0x18002d09f  mov     rdx, rbx
0x18002d0a2  mov     rcx, rbp
0x18002d0a5  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@VNetworkAsyncOperationImplementation@Pal@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VNetworkAsyncOperationImplementation@Pal@@@std@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VNetworkAsyncOperationImplementation@Pal@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@VNetworkAsyncOperationImplementation@Pal@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<Pal::NetworkAsyncOperationImplementation>>>>,std::_Iterator_base0>)
0x18002d0aa  mov     bl, 1
0x18002d0ac  lea     rdx, [rsp+58h+var_30]
0x18002d0b1  test    sil, sil
0x18002d0b4  jz      short loc_18002D0C4
0x18002d0b6  lea     rcx, [rdi+0B8h]
0x18002d0bd  call    ?add@NetworkOperationWaitingQueue@Pal@@QEAAXAEBV?$shared_ptr@VNetworkAsyncOperationImplementation@Pal@@@std@@@Z; Pal::NetworkOperationWaitingQueue::add(std::shared_ptr<Pal::NetworkAsyncOperationImplementation> const &)
0x18002d0c2  jmp     short loc_18002D0CF
0x18002d0c4  lea     rcx, [rdi+0F0h]
0x18002d0cb  jmp     short loc_18002D0BD
0x18002d0cd  xor     bl, bl
0x18002d0cf  mov     rcx, [rsp+58h+var_30+8]; this
0x18002d0d4  test    rcx, rcx
0x18002d0d7  jz      short loc_18002D0DF
0x18002d0d9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002d0de  nop
0x18002d0df  lea     rcx, [rsp+58h+var_38]; this
0x18002d0e4  call    ??1NetworkOperationActiveQueueLock@Pal@@QEAA@XZ; Pal::NetworkOperationActiveQueueLock::~NetworkOperationActiveQueueLock(void)
0x18002d0e9  test    bl, bl
0x18002d0eb  jz      short loc_18002D109
0x18002d0ed  mov     rcx, rdi; this
0x18002d0f0  call    ?processQueuedRequests@NetworkOperationQueueManager@Pal@@AEAAXXZ; Pal::NetworkOperationQueueManager::processQueuedRequests(void)
0x18002d0f5  test    sil, sil
0x18002d0f8  jnz     short loc_18002D109
0x18002d0fa  lea     rcx, [rdi+0F0h]; lpCriticalSection
0x18002d101  mov     edx, r14d; unsigned int
0x18002d104  call    ?remove@NetworkOperationWaitingQueue@Pal@@QEAA_NI@Z; Pal::NetworkOperationWaitingQueue::remove(uint)
0x18002d109  mov     al, bl
0x18002d10b  mov     rbx, [rsp+58h+arg_0]
0x18002d110  mov     rbp, [rsp+58h+arg_10]
0x18002d115  add     rsp, 40h
0x18002d119  pop     r14
0x18002d11b  pop     rdi
0x18002d11c  pop     rsi
0x18002d11d  retn
```
