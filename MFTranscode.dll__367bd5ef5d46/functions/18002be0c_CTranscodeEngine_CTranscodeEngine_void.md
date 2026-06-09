# CTranscodeEngine::~CTranscodeEngine(void)

- ea: `0x18002be0c`
- end: `0x18002bea7`
- name: `??1CTranscodeEngine@@IEAA@XZ`
- size: `155`
- prototype: `void __fastcall(CTranscodeEngine *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002fed4`

## callees

- `0x18000a3f4`
- `0x18001ccf8`
- `0x18002beb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002bea0`

## pseudocode

```c
void __fastcall CTranscodeEngine::~CTranscodeEngine(CTranscodeEngine *this)
{
  *(_QWORD *)this = &CTranscodeEngine::`vftable';
  CVPtrList::~CVPtrList((CTranscodeEngine *)((char *)this + 224));
  CGITPtr::~CGITPtr((CTranscodeEngine *)((char *)this + 192));
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 184);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 176);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 168);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 160);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 152);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 144);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 136);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 128);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18002be0c  push    rbx
0x18002be0e  sub     rsp, 20h
0x18002be12  lea     rax, ??_7CTranscodeEngine@@6B@; const CTranscodeEngine::`vftable'
0x18002be19  mov     rbx, rcx
0x18002be1c  mov     [rcx], rax
0x18002be1f  add     rcx, 0E0h; this
0x18002be26  call    ??1CVPtrList@@QEAA@XZ; CVPtrList::~CVPtrList(void)
0x18002be2b  lea     rcx, [rbx+0C0h]; this
0x18002be32  call    ??1CGITPtr@@QEAA@XZ; CGITPtr::~CGITPtr(void)
0x18002be37  lea     rcx, [rbx+0B8h]
0x18002be3e  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002be43  lea     rcx, [rbx+0B0h]
0x18002be4a  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002be4f  lea     rcx, [rbx+0A8h]
0x18002be56  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002be5b  lea     rcx, [rbx+0A0h]
0x18002be62  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002be67  lea     rcx, [rbx+98h]
0x18002be6e  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002be73  lea     rcx, [rbx+90h]
0x18002be7a  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002be7f  lea     rcx, [rbx+88h]
0x18002be86  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002be8b  lea     rcx, [rbx+80h]
0x18002be92  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002be97  lea     rcx, [rbx+8]
0x18002be9b  add     rsp, 20h
0x18002be9f  pop     rbx
0x18002bea0  jmp     cs:__imp_DeleteCriticalSection
```
