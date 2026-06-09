# DShow::COutputQueue::~COutputQueue(void)

- ea: `0x1800bce00`
- end: `0x1800bcecf`
- name: `??1COutputQueue@DShow@@QEAA@XZ`
- size: `207`
- prototype: `void __fastcall(DShow::COutputQueue *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800bc088`

## callees

- `0x18002314c`
- `0x18006e524`
- `0x180073d4c`
- `0x1800ba2c4`
- `0x1800ba67c`
- `0x1800bce00`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800bce60`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800bce60`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800bcebb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800bcebb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bce4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bce4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bce28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bce28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bce70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bce9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bce70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bce9a`

## pseudocode

```c
void __fastcall DShow::COutputQueue::~COutputQueue(DShow::COutputQueue *this)
{
  __int64 v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  v2 = *((_QWORD *)this + 6);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *((_QWORD *)this + 11) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)this);
    *((_DWORD *)this + 31) = 1;
    *((_DWORD *)this + 33) = 1;
    CMMCSSOutputQueue::NotifyThread(this);
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
    WaitForSingleObject(*((HANDLE *)this + 11), 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 11));
    v3 = (void *)*((_QWORD *)this + 8);
    if ( v3 )
      CGenericList<IMediaSample>::`scalar deleting destructor'(v3);
  }
  else
  {
    DShow::COutputQueue::FreeSamples(this);
  }
  v4 = (void *)*((_QWORD *)this + 9);
  if ( v4 )
    CloseHandle(v4);
  operator delete(*((void **)this + 12));
  CAMEvent::~CAMEvent((DShow::COutputQueue *)((char *)this + 80));
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x1800bce00  push    rbx
0x1800bce02  sub     rsp, 20h
0x1800bce06  mov     rbx, rcx
0x1800bce09  mov     rcx, [rcx+30h]
0x1800bce0d  test    rcx, rcx
0x1800bce10  jz      short loc_1800BCE1E
0x1800bce12  mov     rax, [rcx]
0x1800bce15  mov     rax, [rax+10h]
0x1800bce19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bce1e  mov     rcx, rbx; this
0x1800bce21  cmp     qword ptr [rbx+58h], 0
0x1800bce26  jz      short loc_1800BCE8C
0x1800bce28  call    cs:__imp_EnterCriticalSection
0x1800bce2f  nop     dword ptr [rax+rax+00h]
0x1800bce34  mov     eax, 1
0x1800bce39  mov     [rbx+7Ch], eax
0x1800bce3c  mov     [rbx+84h], eax
0x1800bce42  mov     rcx, rbx; this
0x1800bce45  call    ?NotifyThread@CMMCSSOutputQueue@@IEAAXXZ; CMMCSSOutputQueue::NotifyThread(void)
0x1800bce4a  mov     rcx, rbx; lpCriticalSection
0x1800bce4d  call    cs:__imp_LeaveCriticalSection
0x1800bce54  nop     dword ptr [rax+rax+00h]
0x1800bce59  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800bce5c  mov     rcx, [rbx+58h]; hHandle
0x1800bce60  call    cs:__imp_WaitForSingleObject
0x1800bce67  nop     dword ptr [rax+rax+00h]
0x1800bce6c  mov     rcx, [rbx+58h]; hObject
0x1800bce70  call    cs:__imp_CloseHandle
0x1800bce77  nop     dword ptr [rax+rax+00h]
0x1800bce7c  mov     rcx, [rbx+40h]; Block
0x1800bce80  test    rcx, rcx
0x1800bce83  jz      short loc_1800BCE91
0x1800bce85  call    ??_G?$CGenericList@UIMediaSample@@@@QEAAPEAXI@Z; CGenericList<IMediaSample>::`scalar deleting destructor'(uint)
0x1800bce8a  jmp     short loc_1800BCE91
0x1800bce8c  call    ?FreeSamples@COutputQueue@DShow@@IEAAXXZ; DShow::COutputQueue::FreeSamples(void)
0x1800bce91  mov     rcx, [rbx+48h]; hObject
0x1800bce95  test    rcx, rcx
0x1800bce98  jz      short loc_1800BCEA6
0x1800bce9a  call    cs:__imp_CloseHandle
0x1800bcea1  nop     dword ptr [rax+rax+00h]
0x1800bcea6  mov     rcx, [rbx+60h]; Block
0x1800bceaa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bceaf  lea     rcx, [rbx+50h]; this
0x1800bceb3  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x1800bceb8  mov     rcx, rbx; lpCriticalSection
0x1800bcebb  call    cs:__imp_DeleteCriticalSection
0x1800bcec2  nop     dword ptr [rax+rax+00h]
0x1800bcec7  nop
0x1800bcec8  add     rsp, 20h
0x1800bcecc  pop     rbx
0x1800bcecd  retn
```
