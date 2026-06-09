# ConnectedStorage::Contexts::~Contexts(void)

- ea: `0x1800314d0`
- end: `0x1800315f2`
- name: `??1Contexts@ConnectedStorage@@QEAA@XZ`
- size: `290`
- prototype: `void __fastcall(ConnectedStorage::Contexts *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task`

## callers

- `0x180019340`

## callees

- `0x18000cb9c`
- `0x180010f88`
- `0x180012278`
- `0x1800124b0`
- `0x180012fd0`
- `0x180012ff8`
- `0x180013018`
- `0x180013088`
- `0x18001c2a8`
- `0x18002a1dc`
- `0x180031244`
- `0x1800312ac`
- `0x1800314d0`
- `0x180031604`
- `0x18005320c`
- `0x18005e460`
- `0x180061670`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800315bd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800315bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800315a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800315a0`

## pseudocode

```c
void __fastcall ConnectedStorage::Contexts::~Contexts(ConnectedStorage::Contexts *this, __int64 a2, char *a3)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  __int64 v5; // rax
  ConnectedStorage::UploadingContext **v6; // rbx
  ConnectedStorage::ActivatingContext **v7; // rcx
  _BYTE v8[16]; // [rsp+20h] [rbp-38h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[5]; // [rsp+30h] [rbp-28h] BYREF
  char v10; // [rsp+60h] [rbp+8h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 176);
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 176),
    a3);
  std::list<ConnectedStorage::NtmTransferWrapper>::begin((char *)this + 224, &v10);
  while ( (unsigned __int8)std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ConnectedStorage::BlobRecord>>,std::_Iterator_base0>::operator!=(&v10) )
  {
    v5 = std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ConnectedStorage::ContextDesc const,ConnectedStorage::Contexts::ContextEntry>>>>::operator->(&v10);
    v6 = (ConnectedStorage::UploadingContext **)(v5 + 48);
    if ( (unsigned __int8)std::shared_ptr<ConnectedStorage::WebService>::operator bool(v5 + 64) )
      ConnectedStorage::ActivatingContext::Abort(*v7);
    if ( (unsigned __int8)std::shared_ptr<ConnectedStorage::WebService>::operator bool(v6 + 4) )
    {
      ConnectedStorage::Context::RunDownSynchronous(v6[4]);
      std::weak_ptr<ConnectedStorage::AtomManager>::weak_ptr<ConnectedStorage::AtomManager>(v8);
      std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(v6 + 4, v8);
      std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(v8);
    }
    if ( (unsigned __int8)std::shared_ptr<ConnectedStorage::WebService>::operator bool(v6) )
      ConnectedStorage::UploadingContext::Abort(*v6);
    std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::weak_ptr<ConnectedStorage::ISnapshotableContainer const> const,ConnectedStorage::Uploader::Entry>>>>::operator++(&v10);
  }
  LeaveCriticalSection(lpCriticalSection[0]);
  std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>((char *)this + 256);
  std::_Tree<std::_Tmap_traits<ConnectedStorage::ContextDesc,ConnectedStorage::Contexts::ContextEntry,std::less<ConnectedStorage::ContextDesc>,std::allocator<std::pair<ConnectedStorage::ContextDesc const,ConnectedStorage::Contexts::ContextEntry>>,0>>::~_Tree<std::_Tmap_traits<ConnectedStorage::ContextDesc,ConnectedStorage::Contexts::ContextEntry,std::less<ConnectedStorage::ContextDesc>,std::allocator<std::pair<ConnectedStorage::ContextDesc const,ConnectedStorage::Contexts::ContextEntry>>,0>>((char *)this + 224);
  DeleteCriticalSection(v4);
  std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>((char *)this + 152);
  ConnectedStorage::ResumeUploadPolicy::~ResumeUploadPolicy((ConnectedStorage::Contexts *)((char *)this + 32));
  ConnectedStorage::HasExecuteQueue<ConnectedStorage::ActivatingContext>::~HasExecuteQueue<ConnectedStorage::ActivatingContext>(this);
}

```

## disassembly

```asm
0x1800314d0  mov     [rsp+arg_8], rbx
0x1800314d5  mov     [rsp+arg_10], rbp
0x1800314da  push    rsi
0x1800314db  push    rdi
0x1800314dc  push    r14
0x1800314de  sub     rsp, 40h
0x1800314e2  mov     rdi, rcx
0x1800314e5  lea     rbp, [rcx+0B0h]
0x1800314ec  mov     rdx, rbp; struct ConnectedStorage::Mutex *
0x1800314ef  lea     rcx, [rsp+58h+lpCriticalSection]; this
0x1800314f4  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x1800314f9  lea     r14, [rdi+0E0h]
0x180031500  lea     rdx, [rsp+58h+arg_0]
0x180031505  mov     rcx, r14
0x180031508  call    ?begin@?$list@VNtmTransferWrapper@ConnectedStorage@@V?$allocator@VNtmTransferWrapper@ConnectedStorage@@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@VNtmTransferWrapper@ConnectedStorage@@@std@@@std@@@2@XZ; std::list<ConnectedStorage::NtmTransferWrapper>::begin(void)
0x18003150d  jmp     short loc_180031589
0x18003150f  lea     rcx, [rsp+58h+arg_0]
0x180031514  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVContextDesc@ConnectedStorage@@UContextEntry@Contexts@2@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBVContextDesc@ConnectedStorage@@UContextEntry@Contexts@2@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ConnectedStorage::ContextDesc const,ConnectedStorage::Contexts::ContextEntry>>>>::operator->(void)
0x180031519  lea     rbx, [rax+30h]
0x18003151d  lea     rcx, [rbx+10h]
0x180031521  call    ??B?$shared_ptr@VWebService@ConnectedStorage@@@std@@QEBA_NXZ; std::shared_ptr<ConnectedStorage::WebService>::operator bool(void)
0x180031526  test    al, al
0x180031528  jz      short loc_180031532
0x18003152a  mov     rcx, [rcx]; this
0x18003152d  call    ?Abort@ActivatingContext@ConnectedStorage@@QEBAXXZ; ConnectedStorage::ActivatingContext::Abort(void)
0x180031532  lea     rsi, [rbx+20h]
0x180031536  mov     rcx, rsi
0x180031539  call    ??B?$shared_ptr@VWebService@ConnectedStorage@@@std@@QEBA_NXZ; std::shared_ptr<ConnectedStorage::WebService>::operator bool(void)
0x18003153e  test    al, al
0x180031540  jz      short loc_18003156B
0x180031542  mov     rcx, [rsi]; this
0x180031545  call    ?RunDownSynchronous@Context@ConnectedStorage@@QEBAXXZ; ConnectedStorage::Context::RunDownSynchronous(void)
0x18003154a  lea     rcx, [rsp+58h+var_38]
0x18003154f  call    ??0?$weak_ptr@VAtomManager@ConnectedStorage@@@std@@QEAA@XZ; std::weak_ptr<ConnectedStorage::AtomManager>::weak_ptr<ConnectedStorage::AtomManager>(void)
0x180031554  lea     rdx, [rsp+58h+var_38]
0x180031559  mov     rcx, rsi
0x18003155c  call    ??4?$shared_ptr@$$CBVActivatingContainer@ConnectedStorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(std::shared_ptr<ConnectedStorage::ActivatingContainer const> &&)
0x180031561  lea     rcx, [rsp+58h+var_38]
0x180031566  call    ??1?$shared_ptr@V?$vector@VContainerQueryInfoWrapper@ConnectedStorage@@V?$allocator@VContainerQueryInfoWrapper@ConnectedStorage@@@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(void)
0x18003156b  mov     rcx, rbx
0x18003156e  call    ??B?$shared_ptr@VWebService@ConnectedStorage@@@std@@QEBA_NXZ; std::shared_ptr<ConnectedStorage::WebService>::operator bool(void)
0x180031573  test    al, al
0x180031575  jz      short loc_18003157F
0x180031577  mov     rcx, [rbx]; this
0x18003157a  call    ?Abort@UploadingContext@ConnectedStorage@@QEBAXXZ; ConnectedStorage::UploadingContext::Abort(void)
0x18003157f  lea     rcx, [rsp+58h+arg_0]
0x180031584  call    ??E?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$weak_ptr@$$CBVISnapshotableContainer@ConnectedStorage@@@std@@UEntry@Uploader@ConnectedStorage@@@std@@@std@@@std@@@std@@QEAAAEAV01@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::weak_ptr<ConnectedStorage::ISnapshotableContainer const> const,ConnectedStorage::Uploader::Entry>>>>::operator++(void)
0x180031589  lea     rcx, [rsp+58h+arg_0]
0x18003158e  call    ??9?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@U_Iterator_base0@2@@std@@QEBA_NU_Default_sentinel@1@@Z; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ConnectedStorage::BlobRecord>>,std::_Iterator_base0>::operator!=(std::_Default_sentinel)
0x180031593  test    al, al
0x180031595  jnz     loc_18003150F
0x18003159b  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800315a0  call    cs:__imp_LeaveCriticalSection
0x1800315a6  lea     rcx, [rdi+100h]
0x1800315ad  call    ??1?$shared_ptr@V?$vector@VContainerQueryInfoWrapper@ConnectedStorage@@V?$allocator@VContainerQueryInfoWrapper@ConnectedStorage@@@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(void)
0x1800315b2  mov     rcx, r14
0x1800315b5  call    ??1?$_Tree@V?$_Tmap_traits@VContextDesc@ConnectedStorage@@UContextEntry@Contexts@2@U?$less@VContextDesc@ConnectedStorage@@@std@@V?$allocator@U?$pair@$$CBVContextDesc@ConnectedStorage@@UContextEntry@Contexts@2@@std@@@6@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ConnectedStorage::ContextDesc,ConnectedStorage::Contexts::ContextEntry,std::less<ConnectedStorage::ContextDesc>,std::allocator<std::pair<ConnectedStorage::ContextDesc const,ConnectedStorage::Contexts::ContextEntry>>,0>>::~_Tree<std::_Tmap_traits<ConnectedStorage::ContextDesc,ConnectedStorage::Contexts::ContextEntry,std::less<ConnectedStorage::ContextDesc>,std::allocator<std::pair<ConnectedStorage::ContextDesc const,ConnectedStorage::Contexts::ContextEntry>>,0>>(void)
0x1800315ba  mov     rcx, rbp; lpCriticalSection
0x1800315bd  call    cs:__imp_DeleteCriticalSection
0x1800315c3  lea     rcx, [rdi+98h]
0x1800315ca  call    ??1?$weak_ptr@VActivatingContainer@ConnectedStorage@@@std@@QEAA@XZ; std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>(void)
0x1800315cf  lea     rcx, [rdi+20h]; this
0x1800315d3  call    ??1ResumeUploadPolicy@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ResumeUploadPolicy::~ResumeUploadPolicy(void)
0x1800315d8  mov     rcx, rdi
0x1800315db  mov     rbx, [rsp+58h+arg_8]
0x1800315e0  mov     rbp, [rsp+58h+arg_10]
0x1800315e5  add     rsp, 40h
0x1800315e9  pop     r14
0x1800315eb  pop     rdi
0x1800315ec  pop     rsi
0x1800315ed  jmp     ??1?$HasExecuteQueue@VActivatingContext@ConnectedStorage@@@ConnectedStorage@@QEAA@XZ; ConnectedStorage::HasExecuteQueue<ConnectedStorage::ActivatingContext>::~HasExecuteQueue<ConnectedStorage::ActivatingContext>(void)
```
