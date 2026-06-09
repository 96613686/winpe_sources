# CWICRawMetadataBlockReaderBase::~CWICRawMetadataBlockReaderBase(void)

- ea: `0x1800986cc`
- end: `0x180098735`
- name: `??1CWICRawMetadataBlockReaderBase@@QEAA@XZ`
- size: `105`
- prototype: `void __fastcall(CWICRawMetadataBlockReaderBase *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800985cc`

## callees

- `0x180005ed0`
- `0x1800967ac`
- `0x1800986cc`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180098721`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180098721`

## pseudocode

```c
void __fastcall CWICRawMetadataBlockReaderBase::~CWICRawMetadataBlockReaderBase(CWICRawMetadataBlockReaderBase *this)
{
  __int64 v2; // rcx

  `eh vector destructor iterator'(
    (char *)this + 80,
    8u,
    2u,
    Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::~ComPtr<IWICMetadataBlockReader>);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 64);
  v2 = *((_QWORD *)this + 7);
  if ( v2 )
  {
    *((_QWORD *)this + 7) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x1800986cc  push    rbx
0x1800986ce  sub     rsp, 30h
0x1800986d2  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800986db  mov     rbx, rcx
0x1800986de  add     rcx, 50h ; 'P'; void *
0x1800986e2  lea     r9, ??1?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@QEAA@XZ; void (*)(void *)
0x1800986e9  mov     edx, 8; unsigned __int64
0x1800986ee  lea     r8d, [rdx-6]; unsigned __int64
0x1800986f2  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800986f7  lea     rcx, [rbx+40h]
0x1800986fb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180098700  mov     rcx, [rbx+38h]
0x180098704  test    rcx, rcx
0x180098707  jz      short loc_18009871D
0x180098709  mov     qword ptr [rbx+38h], 0
0x180098711  mov     rax, [rcx]
0x180098714  mov     rax, [rax+10h]
0x180098718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009871d  lea     rcx, [rbx+10h]; lpCriticalSection
0x180098721  call    cs:__imp_DeleteCriticalSection
0x180098728  nop     dword ptr [rax+rax+00h]
0x18009872d  nop
0x18009872e  add     rsp, 30h
0x180098732  pop     rbx
0x180098733  retn
```
