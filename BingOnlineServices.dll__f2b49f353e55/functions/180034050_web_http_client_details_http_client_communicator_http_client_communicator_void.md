# web::http::client::details::_http_client_communicator::~_http_client_communicator(void)

- ea: `0x180034050`
- end: `0x180034096`
- name: `??1_http_client_communicator@details@client@http@web@@UEAA@XZ`
- size: `70`
- prototype: `void __fastcall(web::http::client::details::_http_client_communicator *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034208`
- `0x180034e60`

## callees

- `0x18001ad68`
- `0x18001adbc`
- `0x18002541c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034076`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034076`

## pseudocode

```c
void __fastcall web::http::client::details::_http_client_communicator::~_http_client_communicator(
        web::http::client::details::_http_client_communicator *this)
{
  *(_QWORD *)this = &web::http::client::details::_http_client_communicator::`vftable';
  std::deque<std::shared_ptr<Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::_block>>::~deque<std::shared_ptr<Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::_block>>((char *)this + 816);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 752));
  web::http::client::http_client_config::~http_client_config((web::http::client::details::_http_client_communicator *)((char *)this + 240));
  web::uri::~uri((web::http::client::details::_http_client_communicator *)((char *)this + 8));
}

```

## disassembly

```asm
0x180034050  push    rbx
0x180034052  sub     rsp, 20h
0x180034056  lea     rax, ??_7_http_client_communicator@details@client@http@web@@6B@; const web::http::client::details::_http_client_communicator::`vftable'
0x18003405d  mov     rbx, rcx
0x180034060  mov     [rcx], rax
0x180034063  add     rcx, 330h
0x18003406a  call    ??1?$deque@V?$shared_ptr@V_block@?$basic_producer_consumer_buffer@E@details@streams@Concurrency@@@std@@V?$allocator@V?$shared_ptr@V_block@?$basic_producer_consumer_buffer@E@details@streams@Concurrency@@@std@@@2@@std@@QEAA@XZ; std::deque<std::shared_ptr<Concurrency::streams::details::basic_producer_consumer_buffer<uchar>::_block>>::~deque<std::shared_ptr<Concurrency::streams::details::basic_producer_consumer_buffer<uchar>::_block>>(void)
0x18003406f  lea     rcx, [rbx+2F0h]; lpCriticalSection
0x180034076  call    cs:__imp_DeleteCriticalSection
0x18003407c  lea     rcx, [rbx+0F0h]; this
0x180034083  call    ??1http_client_config@client@http@web@@QEAA@XZ; web::http::client::http_client_config::~http_client_config(void)
0x180034088  lea     rcx, [rbx+8]; this
0x18003408c  add     rsp, 20h
0x180034090  pop     rbx
0x180034091  jmp     ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
```
