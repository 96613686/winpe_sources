# CSmartRemuxEngine::~CSmartRemuxEngine(void)

- ea: `0x18001cd20`
- end: `0x18001cdd2`
- name: `??1CSmartRemuxEngine@@IEAA@XZ`
- size: `178`
- prototype: `void __fastcall(CSmartRemuxEngine *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180028834`

## callees

- `0x18000a3f4`
- `0x18001ccf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001cd6a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001cd6a`

## pseudocode

```c
void __fastcall CSmartRemuxEngine::~CSmartRemuxEngine(CSmartRemuxEngine *this)
{
  *(_QWORD *)this = &CSmartRemuxEngine::`vftable';
  CGITPtr::~CGITPtr((CSmartRemuxEngine *)((char *)this + 336));
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 328);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 320);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 312);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 152);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 120);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 72);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 64);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 48);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 40);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 32);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 24);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 16);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 8);
}

```

## disassembly

```asm
0x18001cd20  push    rbx
0x18001cd22  sub     rsp, 20h
0x18001cd26  lea     rax, ??_7CSmartRemuxEngine@@6B@; const CSmartRemuxEngine::`vftable'
0x18001cd2d  mov     rbx, rcx
0x18001cd30  mov     [rcx], rax
0x18001cd33  add     rcx, 150h; this
0x18001cd3a  call    ??1CGITPtr@@QEAA@XZ; CGITPtr::~CGITPtr(void)
0x18001cd3f  lea     rcx, [rbx+148h]
0x18001cd46  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001cd4b  lea     rcx, [rbx+140h]
0x18001cd52  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001cd57  lea     rcx, [rbx+138h]
0x18001cd5e  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001cd63  lea     rcx, [rbx+0D0h]; lpCriticalSection
0x18001cd6a  call    cs:__imp_DeleteCriticalSection
0x18001cd70  lea     rcx, [rbx+98h]
0x18001cd77  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001cd7c  lea     rcx, [rbx+78h]
0x18001cd80  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001cd85  lea     rcx, [rbx+48h]
0x18001cd89  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001cd8e  lea     rcx, [rbx+40h]
0x18001cd92  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001cd97  lea     rcx, [rbx+30h]
0x18001cd9b  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001cda0  lea     rcx, [rbx+28h]
0x18001cda4  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001cda9  lea     rcx, [rbx+20h]
0x18001cdad  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001cdb2  lea     rcx, [rbx+18h]
0x18001cdb6  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001cdbb  lea     rcx, [rbx+10h]
0x18001cdbf  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001cdc4  lea     rcx, [rbx+8]
0x18001cdc8  add     rsp, 20h
0x18001cdcc  pop     rbx
0x18001cdcd  jmp     ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
```
