# Mpeg2DemuxAttributes::CMediaSampleWrapper::~CMediaSampleWrapper(void)

- ea: `0x18002192c`
- end: `0x1800219b6`
- name: `??1CMediaSampleWrapper@Mpeg2DemuxAttributes@@MEAA@XZ`
- size: `138`
- prototype: `void __fastcall(Mpeg2DemuxAttributes::CMediaSampleWrapper *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800218f0`
- `0x18009a020`

## callees

- `0x18002192c`
- `0x180021f04`
- `0x18002329c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021997`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021997`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021988`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021988`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021963`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021963`

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
0x18002192c  mov     [rsp+arg_0], rbx
0x180021931  push    rdi
0x180021932  sub     rsp, 20h
0x180021936  lea     rax, ??_7CMediaSampleWrapper@Mpeg2DemuxAttributes@@6BIMediaSample2@@@; const Mpeg2DemuxAttributes::CMediaSampleWrapper::`vftable'{for `IMediaSample2'}
0x18002193d  mov     rbx, rcx
0x180021940  mov     [rcx], rax
0x180021943  lea     rdi, [rcx+138h]
0x18002194a  lea     rax, ??_7CDemuxIMediaSample@Mpeg2DemuxAttributes@@6BIAttributeSet@@@; const Mpeg2DemuxAttributes::CDemuxIMediaSample::`vftable'{for `IAttributeSet'}
0x180021951  mov     [rcx+8], rax
0x180021955  lea     rax, ??_7CMediaSampleWrapper@Mpeg2DemuxAttributes@@6BIAttributeGet@@@; const Mpeg2DemuxAttributes::CMediaSampleWrapper::`vftable'{for `IAttributeGet'}
0x18002195c  mov     [rcx+10h], rax
0x180021960  mov     rcx, rdi; lpCriticalSection
0x180021963  call    cs:__imp_EnterCriticalSection
0x18002196a  nop     dword ptr [rax+rax+00h]
0x18002196f  mov     rcx, [rbx+50h]; pv
0x180021973  test    rcx, rcx
0x180021976  jz      short loc_180021985
0x180021978  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x18002197d  mov     qword ptr [rbx+50h], 0
0x180021985  mov     rcx, rdi; lpCriticalSection
0x180021988  call    cs:__imp_LeaveCriticalSection
0x18002198f  nop     dword ptr [rax+rax+00h]
0x180021994  mov     rcx, rdi; lpCriticalSection
0x180021997  call    cs:__imp_DeleteCriticalSection
0x18002199e  nop     dword ptr [rax+rax+00h]
0x1800219a3  lea     rcx, [rbx+60h]; this
0x1800219a7  mov     rbx, [rsp+28h+arg_0]
0x1800219ac  add     rsp, 20h
0x1800219b0  pop     rdi
0x1800219b1  jmp     ??1CAttributeList@Mpeg2DemuxAttributes@@UEAA@XZ; Mpeg2DemuxAttributes::CAttributeList::~CAttributeList(void)
```
