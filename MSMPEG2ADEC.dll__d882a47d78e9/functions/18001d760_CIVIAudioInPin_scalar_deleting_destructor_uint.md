# CIVIAudioInPin::`scalar deleting destructor'(uint)

- ea: `0x18001d760`
- end: `0x18001d82d`
- name: `??_GCIVIAudioInPin@@UEAAPEAXI@Z`
- size: `205`
- prototype: `void *__fastcall(CIVIAudioInPin *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001b80`
- `0x18001d6e0`
- `0x18001d760`
- `0x180059170`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001d7d3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001d7e6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001d7d3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001d7e6`

## pseudocode

```c
CIVIAudioInPin *__fastcall CIVIAudioInPin::`scalar deleting destructor'(CIVIAudioInPin *this, char a2)
{
  *(_QWORD *)this = &CIVIAudioInPin::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CTransformInputPin::`vftable'{for `IPin'};
  *((_QWORD *)this + 4) = &CIVIAudioInPin::`vftable'{for `IQualityControl'};
  *((_QWORD *)this + 27) = &CIVIAudioInPin::`vftable'{for `CTransformInputPin'};
  *((_QWORD *)this + 39) = &CIVIAudioInPin::`vftable'{for `IKsPropertySet'};
  *((_QWORD *)this + 40) = &CIVIAudioInPin::`vftable'{for `CMPEG2MFSampleProtection'};
  *((_QWORD *)this + 133) = &CIVIAudioInPin::`vftable'{for `ICodecAPI'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1632));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1592));
  CMFSampleProtection::~CMFSampleProtection((CIVIAudioInPin *)((char *)this + 320));
  CTransformInputPin::~CTransformInputPin(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001d760  mov     [rsp+arg_0], rbx
0x18001d765  mov     [rsp+arg_8], rsi
0x18001d76a  push    rdi
0x18001d76b  sub     rsp, 20h
0x18001d76f  lea     rax, ??_7CIVIAudioInPin@@6BCUnknown@@@; const CIVIAudioInPin::`vftable'{for `CUnknown'}
0x18001d776  mov     rsi, rcx
0x18001d779  mov     [rcx], rax
0x18001d77c  mov     edi, edx
0x18001d77e  lea     rax, ??_7CTransformInputPin@@6BIPin@@@; const CTransformInputPin::`vftable'{for `IPin'}
0x18001d785  mov     [rcx+18h], rax
0x18001d789  lea     rax, ??_7CIVIAudioInPin@@6BIQualityControl@@@; const CIVIAudioInPin::`vftable'{for `IQualityControl'}
0x18001d790  mov     [rcx+20h], rax
0x18001d794  lea     rax, ??_7CIVIAudioInPin@@6BCTransformInputPin@@@; const CIVIAudioInPin::`vftable'{for `CTransformInputPin'}
0x18001d79b  mov     [rcx+0D8h], rax
0x18001d7a2  lea     rax, ??_7CIVIAudioInPin@@6BIKsPropertySet@@@; const CIVIAudioInPin::`vftable'{for `IKsPropertySet'}
0x18001d7a9  mov     [rcx+138h], rax
0x18001d7b0  lea     rax, ??_7CIVIAudioInPin@@6BCMPEG2MFSampleProtection@@@; const CIVIAudioInPin::`vftable'{for `CMPEG2MFSampleProtection'}
0x18001d7b7  mov     [rcx+140h], rax
0x18001d7be  lea     rax, ??_7CIVIAudioInPin@@6BICodecAPI@@@; const CIVIAudioInPin::`vftable'{for `ICodecAPI'}
0x18001d7c5  mov     [rcx+428h], rax
0x18001d7cc  add     rcx, 660h; lpCriticalSection
0x18001d7d3  call    cs:__imp_DeleteCriticalSection
0x18001d7da  nop     dword ptr [rax+rax+00h]
0x18001d7df  lea     rcx, [rsi+638h]; lpCriticalSection
0x18001d7e6  call    cs:__imp_DeleteCriticalSection
0x18001d7ed  nop     dword ptr [rax+rax+00h]
0x18001d7f2  lea     rcx, [rsi+140h]; this
0x18001d7f9  call    ??1CMFSampleProtection@@QEAA@XZ; CMFSampleProtection::~CMFSampleProtection(void)
0x18001d7fe  mov     rcx, rsi; this
0x18001d801  call    ??1CTransformInputPin@@UEAA@XZ; CTransformInputPin::~CTransformInputPin(void)
0x18001d806  test    dil, 1
0x18001d80a  jz      short loc_18001D819
0x18001d80c  mov     edx, 690h
0x18001d811  mov     rcx, rsi; Block
0x18001d814  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d819  mov     rbx, [rsp+28h+arg_0]
0x18001d81e  mov     rax, rsi
0x18001d821  mov     rsi, [rsp+28h+arg_8]
0x18001d826  add     rsp, 20h
0x18001d82a  pop     rdi
0x18001d82b  retn
```
