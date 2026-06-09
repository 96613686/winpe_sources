# CPhotoPropertyStore::~CPhotoPropertyStore(void)

- ea: `0x18000d370`
- end: `0x18000d3fc`
- name: `??1CPhotoPropertyStore@@QEAA@XZ`
- size: `140`
- prototype: `void __fastcall(CPhotoPropertyStore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000d30c`

## callees

- `0x18000d370`
- `0x18000d404`
- `0x18000d430`
- `0x18001186c`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d37d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d37d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CPhotoPropertyStore::~CPhotoPropertyStore(CPhotoPropertyStore *this)
{
  const struct _GUID *v2; // rcx
  unsigned __int64 v3; // r8
  __int64 v4; // rcx
  __int64 v5; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v3 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v3 )
    ShellPrivateTraceEvent(v2, 0x14u, v3, 2u);
  CMetadataContainer::~CMetadataContainer((CPhotoPropertyStore *)((char *)this + 200));
  v4 = *((_QWORD *)this + 18);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 17);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  _InterlockedDecrement((_DWORD *)&qword_18009A048 + 1);
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((__int64)this + 32);
}

```

## disassembly

```asm
0x18000d370  push    rbx
0x18000d372  sub     rsp, 20h
0x18000d376  mov     rbx, rcx
0x18000d379  add     rcx, 60h ; '`'; lpCriticalSection
0x18000d37d  call    cs:__imp_DeleteCriticalSection
0x18000d384  nop     dword ptr [rax+rax+00h]
0x18000d389  mov     rax, cs:WPP_GLOBAL_Control
0x18000d390  mov     r8, [rax+38h]; unsigned __int64
0x18000d394  test    r8, r8
0x18000d397  jnz     short loc_18000D3ED
0x18000d399  lea     rcx, [rbx+0C8h]; this
0x18000d3a0  call    ??1CMetadataContainer@@QEAA@XZ; CMetadataContainer::~CMetadataContainer(void)
0x18000d3a5  nop
0x18000d3a6  mov     rcx, [rbx+90h]
0x18000d3ad  test    rcx, rcx
0x18000d3b0  jz      short loc_18000D3BF
0x18000d3b2  mov     rax, [rcx]
0x18000d3b5  mov     rax, [rax+10h]
0x18000d3b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3be  nop
0x18000d3bf  mov     rcx, [rbx+88h]
0x18000d3c6  test    rcx, rcx
0x18000d3c9  jz      short loc_18000D3D8
0x18000d3cb  mov     rax, [rcx]
0x18000d3ce  mov     rax, [rax+10h]
0x18000d3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3d7  nop
0x18000d3d8  lock dec dword ptr cs:qword_18009A048+4
0x18000d3df  lea     rcx, [rbx+20h]
0x18000d3e3  add     rsp, 20h
0x18000d3e7  pop     rbx
0x18000d3e8  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x18000d3ed  mov     r9b, 2; unsigned __int8
0x18000d3f0  mov     edx, 14h; unsigned int
0x18000d3f5  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18000d3fa  jmp     short loc_18000D399
```
