# COutQueueIP::~COutQueueIP(void)

- ea: `0x18006a4a0`
- end: `0x18006a548`
- name: `??1COutQueueIP@@QEAA@XZ`
- size: `168`
- prototype: `void __fastcall(COutQueueIP *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006a71c`

## callees

- `0x180059d9c`
- `0x18006a9ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006a507`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006a51c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006a52b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006a507`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006a51c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006a52b`

## pseudocode

```c
void __fastcall COutQueueIP::~COutQueueIP(COutQueueIP *this)
{
  *(_QWORD *)this = &COutQueueIP::`vftable';
  COutQueueIP::EmptyQueueOfReqBuffers(this);
  CResourceManager::ReleasePage(*((CResourceManager **)this + 36), *((struct CPageInfo **)this + 5));
  *((_QWORD *)this + 5) = 0;
  CResourceManager::ReleasePage(*((CResourceManager **)this + 36), *((struct CPageInfo **)this + 35));
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 28) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  *((_QWORD *)this + 20) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  *((_QWORD *)this + 12) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  *((_QWORD *)this + 8) = &UTStaticList<CPartnerPair *>::`vftable';
}

```

## disassembly

```asm
0x18006a4a0  mov     [rsp+arg_0], rbx
0x18006a4a5  push    rdi
0x18006a4a6  sub     rsp, 20h
0x18006a4aa  mov     rbx, rcx
0x18006a4ad  lea     rax, ??_7COutQueueIP@@6B@; const COutQueueIP::`vftable'
0x18006a4b4  mov     [rcx], rax
0x18006a4b7  call    ?EmptyQueueOfReqBuffers@COutQueueIP@@AEAAXXZ; COutQueueIP::EmptyQueueOfReqBuffers(void)
0x18006a4bc  mov     rdx, [rbx+28h]; struct CPageInfo *
0x18006a4c0  mov     rcx, [rbx+120h]; this
0x18006a4c7  call    ?ReleasePage@CResourceManager@@QEAAJPEAVCPageInfo@@@Z; CResourceManager::ReleasePage(CPageInfo *)
0x18006a4cc  mov     qword ptr [rbx+28h], 0
0x18006a4d4  mov     rdx, [rbx+118h]; struct CPageInfo *
0x18006a4db  mov     rcx, [rbx+120h]; this
0x18006a4e2  call    ?ReleasePage@CResourceManager@@QEAAJPEAVCPageInfo@@@Z; CResourceManager::ReleasePage(CPageInfo *)
0x18006a4e7  mov     qword ptr [rbx+118h], 0
0x18006a4f2  lea     rdi, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x18006a4f9  mov     [rbx+0E0h], rdi
0x18006a500  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x18006a507  call    cs:__imp_DeleteCriticalSection
0x18006a50d  nop
0x18006a50e  mov     [rbx+0A0h], rdi
0x18006a515  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x18006a51c  call    cs:__imp_DeleteCriticalSection
0x18006a522  nop
0x18006a523  mov     [rbx+60h], rdi
0x18006a527  lea     rcx, [rbx+68h]; lpCriticalSection
0x18006a52b  call    cs:__imp_DeleteCriticalSection
0x18006a531  nop
0x18006a532  lea     rax, ??_7?$UTStaticList@PEAVCPartnerPair@@@@6B@; const UTStaticList<CPartnerPair *>::`vftable'
0x18006a539  mov     [rbx+40h], rax
0x18006a53d  mov     rbx, [rsp+28h+arg_0]
0x18006a542  add     rsp, 20h
0x18006a546  pop     rdi
0x18006a547  retn
```
