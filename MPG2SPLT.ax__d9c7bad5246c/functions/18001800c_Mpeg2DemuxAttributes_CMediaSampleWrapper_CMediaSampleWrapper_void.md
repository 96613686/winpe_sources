# Mpeg2DemuxAttributes::CMediaSampleWrapper::~CMediaSampleWrapper(void)

- ea: `0x18001800c`
- end: `0x180018084`
- name: `??1CMediaSampleWrapper@Mpeg2DemuxAttributes@@MEAA@XZ`
- size: `120`
- prototype: `void __fastcall(Mpeg2DemuxAttributes::CMediaSampleWrapper *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180018150`
- `0x180022400`

## callees

- `0x180006af0`
- `0x180017f0c`
- `0x18001800c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001806b`
- `KERNEL32!DeleteCriticalSection` at `0x18001806b`
- `KERNEL32!LeaveCriticalSection` at `0x180018062`
- `KERNEL32!LeaveCriticalSection` at `0x180018062`
- `KERNEL32!EnterCriticalSection` at `0x180018043`
- `KERNEL32!EnterCriticalSection` at `0x180018043`

## pseudocode

```c
void __fastcall Mpeg2DemuxAttributes::CMediaSampleWrapper::~CMediaSampleWrapper(
        Mpeg2DemuxAttributes::CMediaSampleWrapper *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  struct _AMMediaType *v3; // rcx

  *(_QWORD *)this = &Mpeg2DemuxAttributes::CMediaSampleWrapper::`vftable'{for `IMediaSample2'};
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 312);
  *((_QWORD *)this + 1) = &Mpeg2DemuxAttributes::CDemuxIMediaSample::`vftable'{for `IAttributeSet'};
  *((_QWORD *)this + 2) = &Mpeg2DemuxAttributes::CMediaSampleWrapper::`vftable'{for `IAttributeGet'};
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
  v3 = (struct _AMMediaType *)*((_QWORD *)this + 10);
  if ( v3 )
  {
    DeleteMediaType(v3);
    *((_QWORD *)this + 10) = 0;
  }
  LeaveCriticalSection(v2);
  DeleteCriticalSection(v2);
  Mpeg2DemuxAttributes::CAttributeList::~CAttributeList((Mpeg2DemuxAttributes::CMediaSampleWrapper *)((char *)this + 96));
}

```

## disassembly

```asm
0x18001800c  mov     [rsp+arg_0], rbx
0x180018011  push    rdi
0x180018012  sub     rsp, 20h
0x180018016  lea     rax, ??_7CMediaSampleWrapper@Mpeg2DemuxAttributes@@6BIMediaSample2@@@; const Mpeg2DemuxAttributes::CMediaSampleWrapper::`vftable'{for `IMediaSample2'}
0x18001801d  mov     rbx, rcx
0x180018020  mov     [rcx], rax
0x180018023  lea     rdi, [rcx+138h]
0x18001802a  lea     rax, ??_7CDemuxIMediaSample@Mpeg2DemuxAttributes@@6BIAttributeSet@@@; const Mpeg2DemuxAttributes::CDemuxIMediaSample::`vftable'{for `IAttributeSet'}
0x180018031  mov     [rcx+8], rax
0x180018035  lea     rax, ??_7CMediaSampleWrapper@Mpeg2DemuxAttributes@@6BIAttributeGet@@@; const Mpeg2DemuxAttributes::CMediaSampleWrapper::`vftable'{for `IAttributeGet'}
0x18001803c  mov     [rcx+10h], rax
0x180018040  mov     rcx, rdi; lpCriticalSection
0x180018043  call    cs:__imp_EnterCriticalSection
0x180018049  mov     rcx, [rbx+50h]; pv
0x18001804d  test    rcx, rcx
0x180018050  jz      short loc_18001805F
0x180018052  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x180018057  mov     qword ptr [rbx+50h], 0
0x18001805f  mov     rcx, rdi; lpCriticalSection
0x180018062  call    cs:__imp_LeaveCriticalSection
0x180018068  mov     rcx, rdi; lpCriticalSection
0x18001806b  call    cs:__imp_DeleteCriticalSection
0x180018071  lea     rcx, [rbx+60h]; this
0x180018075  mov     rbx, [rsp+28h+arg_0]
0x18001807a  add     rsp, 20h
0x18001807e  pop     rdi
0x18001807f  jmp     ??1CAttributeList@Mpeg2DemuxAttributes@@UEAA@XZ; Mpeg2DemuxAttributes::CAttributeList::~CAttributeList(void)
```
