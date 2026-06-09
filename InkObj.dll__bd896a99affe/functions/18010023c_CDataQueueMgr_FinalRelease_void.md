# CDataQueueMgr::FinalRelease(void)

- ea: `0x18010023c`
- end: `0x1801002f9`
- name: `?FinalRelease@CDataQueueMgr@@QEAAXXZ`
- size: `189`
- prototype: `void __fastcall(CDataQueueMgr *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800f7678`

## callees

- `0x1800fee34`
- `0x1800ff974`
- `0x18010023c`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801002aa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801002b7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801002c4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801002ce`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801002db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801002aa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801002b7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801002c4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801002ce`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801002db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801002f2`

## pseudocode

```c
void __fastcall CDataQueueMgr::FinalRelease(CDataQueueMgr *this)
{
  _QWORD *v1; // rdi
  __int64 v3; // rcx

  v1 = (_QWORD *)((char *)this + 147832);
  if ( *((_QWORD *)this + 18480) )
  {
    Allocator<CStylusSinkList::StylusSinkPtr>::Destruct(this, *v1);
    v1[1] = 0;
  }
  Vector<CStylusSinkList::StylusSinkPtr,Allocator<CStylusSinkList::StylusSinkPtr>>::reserve(v1, 0);
  v3 = *((_QWORD *)this + 7);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 272LL))(v3);
    *((_QWORD *)this + 7) = 0;
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 2) + 40LL))((char *)this + 16);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 49272));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2463);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 147768));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2464);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 49312));
}

```

## disassembly

```asm
0x18010023c  mov     [rsp+arg_0], rbx
0x180100241  push    rdi
0x180100242  sub     rsp, 20h
0x180100246  lea     rdi, [rcx+24178h]
0x18010024d  mov     rbx, rcx
0x180100250  mov     r8, [rdi+8]
0x180100254  test    r8, r8
0x180100257  jz      short loc_180100269
0x180100259  mov     rdx, [rdi]
0x18010025c  call    ?Destruct@?$Allocator@VStylusSinkPtr@CStylusSinkList@@@@QEAAXPEAVStylusSinkPtr@CStylusSinkList@@_K@Z; Allocator<CStylusSinkList::StylusSinkPtr>::Destruct(CStylusSinkList::StylusSinkPtr *,unsigned __int64)
0x180100261  mov     qword ptr [rdi+8], 0
0x180100269  xor     edx, edx
0x18010026b  mov     rcx, rdi
0x18010026e  call    ?reserve@?$Vector@VStylusSinkPtr@CStylusSinkList@@V?$Allocator@VStylusSinkPtr@CStylusSinkList@@@@@@QEAA_N_K@Z; Vector<CStylusSinkList::StylusSinkPtr,Allocator<CStylusSinkList::StylusSinkPtr>>::reserve(unsigned __int64)
0x180100273  mov     rcx, [rbx+38h]
0x180100277  test    rcx, rcx
0x18010027a  jz      short loc_180100293
0x18010027c  mov     rax, [rcx]
0x18010027f  mov     rax, [rax+110h]
0x180100286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010028b  mov     qword ptr [rbx+38h], 0
0x180100293  lea     rcx, [rbx+10h]
0x180100297  mov     rax, [rcx]
0x18010029a  mov     rax, [rax+28h]
0x18010029e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801002a3  lea     rcx, [rbx+0C078h]; lpCriticalSection
0x1801002aa  call    cs:__imp_DeleteCriticalSection
0x1801002b0  lea     rcx, [rbx+180D8h]; lpCriticalSection
0x1801002b7  call    cs:__imp_DeleteCriticalSection
0x1801002bd  lea     rcx, [rbx+24138h]; lpCriticalSection
0x1801002c4  call    cs:__imp_DeleteCriticalSection
0x1801002ca  lea     rcx, [rbx+40h]; lpCriticalSection
0x1801002ce  call    cs:__imp_DeleteCriticalSection
0x1801002d4  lea     rcx, [rbx+18100h]; lpCriticalSection
0x1801002db  call    cs:__imp_DeleteCriticalSection
0x1801002e1  lea     rcx, [rbx+0C0A0h]
0x1801002e8  mov     rbx, [rsp+28h+arg_0]
0x1801002ed  add     rsp, 20h
0x1801002f1  pop     rdi
0x1801002f2  jmp     cs:__imp_DeleteCriticalSection
```
