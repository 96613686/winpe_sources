# CMpeg2StatsCOM::~CMpeg2StatsCOM(void)

- ea: `0x180010f0c`
- end: `0x180010f79`
- name: `??1CMpeg2StatsCOM@@UEAA@XZ`
- size: `109`
- prototype: `void __fastcall(CMpeg2StatsCOM *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011640`

## callees

- `0x180010f0c`
- `0x180017f44`
- `0x180034010`

## pseudocode

```c
void __fastcall CMpeg2StatsCOM::~CMpeg2StatsCOM(CMpeg2StatsCOM *this, unsigned __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &CMpeg2StatsCOM::`vftable';
  v3 = *((_QWORD *)this + 3);
  if ( v3 )
    (**(void (__fastcall ***)(__int64, __int64))(v3 + 8))(v3 + 8, 1);
  v4 = *((_QWORD *)this + 4);
  if ( v4 )
    (**(void (__fastcall ***)(__int64, __int64))(v4 + 8))(v4 + 8, 1);
  *((_QWORD *)this + 5) = &Mp2DemuxSec::CDemuxDiagnosticsSec::`vftable';
  Mp2DemuxSec::CDemuxSec::~CDemuxSec((CMpeg2StatsCOM *)((char *)this + 40), a2);
  _InterlockedDecrement(&CBaseObject::m_cObjects);
}

```

## disassembly

```asm
0x180010f0c  push    rbx
0x180010f0e  sub     rsp, 20h
0x180010f12  lea     rax, ??_7CMpeg2StatsCOM@@6B@; const CMpeg2StatsCOM::`vftable'
0x180010f19  mov     rbx, rcx
0x180010f1c  mov     [rcx], rax
0x180010f1f  mov     rcx, [rcx+18h]
0x180010f23  test    rcx, rcx
0x180010f26  jz      short loc_180010F3C
0x180010f28  add     rcx, 8
0x180010f2c  mov     edx, 1
0x180010f31  mov     rax, [rcx]
0x180010f34  mov     rax, [rax]
0x180010f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f3c  mov     rcx, [rbx+20h]
0x180010f40  test    rcx, rcx
0x180010f43  jz      short loc_180010F59
0x180010f45  add     rcx, 8
0x180010f49  mov     edx, 1
0x180010f4e  mov     rax, [rcx]
0x180010f51  mov     rax, [rax]
0x180010f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f59  lea     rcx, [rbx+28h]; this
0x180010f5d  lea     rax, ??_7CDemuxDiagnosticsSec@Mp2DemuxSec@@6B@; const Mp2DemuxSec::CDemuxDiagnosticsSec::`vftable'
0x180010f64  mov     [rcx], rax
0x180010f67  call    ??1CDemuxSec@Mp2DemuxSec@@UEAA@XZ; Mp2DemuxSec::CDemuxSec::~CDemuxSec(void)
0x180010f6c  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180010f73  add     rsp, 20h
0x180010f77  pop     rbx
0x180010f78  retn
```
