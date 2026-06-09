# CBaseSplitterFilter::CreateStream(ushort const *,CStreamNotify * *)

- ea: `0x18000c488`
- end: `0x18000c66e`
- name: `?CreateStream@CBaseSplitterFilter@@QEAAJPEBGPEAPEAVCStreamNotify@@@Z`
- size: `486`
- prototype: `__int64 __fastcall(CBaseSplitterFilter *__hidden this, const unsigned __int16 *, struct CStreamNotify **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c680`

## callees

- `0x180001008`
- `0x180002cf8`
- `0x1800067a4`
- `0x18000c488`
- `0x180034010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000c52a`
- `KERNEL32!InitializeCriticalSection` at `0x18000c52a`
- `KERNEL32!LeaveCriticalSection` at `0x18000c61d`
- `KERNEL32!LeaveCriticalSection` at `0x18000c626`
- `KERNEL32!LeaveCriticalSection` at `0x18000c651`
- `KERNEL32!LeaveCriticalSection` at `0x18000c65a`
- `KERNEL32!LeaveCriticalSection` at `0x18000c61d`
- `KERNEL32!LeaveCriticalSection` at `0x18000c626`
- `KERNEL32!LeaveCriticalSection` at `0x18000c651`
- `KERNEL32!LeaveCriticalSection` at `0x18000c65a`
- `KERNEL32!EnterCriticalSection` at `0x18000c5dc`
- `KERNEL32!EnterCriticalSection` at `0x18000c5ec`
- `KERNEL32!EnterCriticalSection` at `0x18000c5dc`
- `KERNEL32!EnterCriticalSection` at `0x18000c5ec`

## pseudocode

```c
__int64 __fastcall CBaseSplitterFilter::CreateStream(
        CBaseSplitterFilter *this,
        const unsigned __int16 *a2,
        struct CStreamNotify **a3)
{
  CBasePin *v6; // rax
  const unsigned __int16 *v7; // rdx
  CBasePin *v8; // rbx
  char *v9; // rdx
  struct __POSITION *v10; // rax
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  int *v13; // [rsp+20h] [rbp-58h]

  v6 = (CBasePin *)operator new(0x1B0u);
  v8 = v6;
  if ( !v6 )
    return 2147942414LL;
  CBasePin::CBasePin(v6, v7, this, (CBaseSplitterFilter *)((char *)this + 176), v13, a2, PINDIR_OUTPUT);
  *((_QWORD *)v8 + 27) = 0;
  *(_QWORD *)v8 = &CSplitterOutputPin::`vftable'{for `CUnknown'};
  *((_QWORD *)v8 + 28) = 0;
  *((_QWORD *)v8 + 3) = &CSplitterOutputPin::`vftable'{for `IPin'};
  *((_QWORD *)v8 + 4) = &CSplitterOutputPin::`vftable'{for `IQualityControl'};
  *((_QWORD *)v8 + 29) = &CSplitterOutputPin::CImplStreamNotify::`vftable';
  *((_QWORD *)v8 + 30) = v8;
  *((_DWORD *)v8 + 62) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 256));
  v9 = (char *)*((_QWORD *)v8 + 1);
  *((_QWORD *)v8 + 37) = 0;
  *((_QWORD *)v8 + 38) = 0;
  *((_QWORD *)v8 + 39) = 0;
  *((_DWORD *)v8 + 80) = 0;
  *((_QWORD *)v8 + 41) = 10;
  *((_QWORD *)v8 + 42) = 0;
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  *((_QWORD *)v8 + 49) = 0;
  *((_QWORD *)v8 + 43) = &CBaseSeeking::`vftable'{for `CUnknown'};
  *((_QWORD *)v8 + 50) = ((unsigned __int64)this + 120) & -(__int64)(this != 0);
  *((_QWORD *)v8 + 46) = &CBaseSeeking::`vftable'{for `IMediaSeeking'};
  if ( !v9 )
    v9 = (char *)v8 + 344;
  *((_QWORD *)v8 + 44) = v9;
  *((_QWORD *)v8 + 47) = 0x3FF0000000000000LL;
  *((_DWORD *)v8 + 90) = 0;
  *((_QWORD *)v8 + 48) = 0x7FFFFFFFFFFFFFFFLL;
  *((_DWORD *)v8 + 102) = 0;
  *(GUID *)((char *)v8 + 412) = TIME_FORMAT_MEDIA_TIME;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 256));
  _InterlockedIncrement((volatile signed __int32 *)this + 28);
  (*(void (__fastcall **)(__int64))(*((_QWORD *)v8 + 3) + 8LL))((__int64)v8 + 24);
  v10 = CBaseList::AddTailI((CBaseSplitterFilter *)((char *)this + 136), v8);
  v11 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 256);
  if ( !v10 )
  {
    LeaveCriticalSection(v11);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
    (*(void (__fastcall **)(CBasePin *, __int64))(*(_QWORD *)v8 + 24LL))(v8, 1);
    return 2147942414LL;
  }
  LeaveCriticalSection(v11);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  *a3 = (CBasePin *)((char *)v8 + 232);
  return 0;
}

```

## disassembly

```asm
0x18000c488  push    rbx
0x18000c48a  push    rbp
0x18000c48b  push    rsi
0x18000c48c  push    rdi
0x18000c48d  push    r14
0x18000c48f  push    r15
0x18000c491  sub     rsp, 48h
0x18000c495  mov     rbp, rcx
0x18000c498  mov     r14, r8
0x18000c49b  mov     ecx, 1B0h; Size
0x18000c4a0  mov     rsi, rdx
0x18000c4a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c4a8  xor     r15d, r15d
0x18000c4ab  mov     rbx, rax
0x18000c4ae  test    rax, rax
0x18000c4b1  jz      loc_18000C63F
0x18000c4b7  lea     rdi, [rbp+0B0h]
0x18000c4be  mov     [rsp+78h+var_48], 1; enum _PinDirection
0x18000c4c6  mov     r9, rdi; struct CCritSec *
0x18000c4c9  mov     [rsp+78h+var_50], rsi; unsigned __int16 *
0x18000c4ce  mov     r8, rbp; struct CBaseFilter *
0x18000c4d1  mov     rcx, rax; this
0x18000c4d4  call    ??0CBasePin@@QEAA@PEBGPEAVCBaseFilter@@PEAVCCritSec@@PEAJ0W4_PinDirection@@@Z; CBasePin::CBasePin(ushort const *,CBaseFilter *,CCritSec *,long *,ushort const *,_PinDirection)
0x18000c4d9  lea     rax, ??_7CSplitterOutputPin@@6BCUnknown@@@; const CSplitterOutputPin::`vftable'{for `CUnknown'}
0x18000c4e0  mov     [rbx+0D8h], r15
0x18000c4e7  mov     [rbx], rax
0x18000c4ea  lea     rcx, [rbx+100h]; lpCriticalSection
0x18000c4f1  lea     rax, ??_7CSplitterOutputPin@@6BIPin@@@; const CSplitterOutputPin::`vftable'{for `IPin'}
0x18000c4f8  mov     [rbx+0E0h], r15
0x18000c4ff  mov     [rbx+18h], rax
0x18000c503  lea     rax, ??_7CSplitterOutputPin@@6BIQualityControl@@@; const CSplitterOutputPin::`vftable'{for `IQualityControl'}
0x18000c50a  mov     [rbx+20h], rax
0x18000c50e  lea     rax, ??_7CImplStreamNotify@CSplitterOutputPin@@6B@; const CSplitterOutputPin::CImplStreamNotify::`vftable'
0x18000c515  mov     [rbx+0E8h], rax
0x18000c51c  mov     [rbx+0F0h], rbx
0x18000c523  mov     [rbx+0F8h], r15d
0x18000c52a  call    cs:__imp_InitializeCriticalSection
0x18000c530  mov     rdx, [rbx+8]
0x18000c534  lea     rcx, [rbp+78h]
0x18000c538  mov     rax, rbp
0x18000c53b  mov     [rbx+128h], r15
0x18000c542  neg     rax
0x18000c545  mov     [rbx+130h], r15
0x18000c54c  mov     [rbx+138h], r15
0x18000c553  lea     r9, [rbx+158h]
0x18000c55a  sbb     r8, r8
0x18000c55d  mov     [rbx+140h], r15d
0x18000c564  and     r8, rcx
0x18000c567  mov     qword ptr [rbx+148h], 0Ah
0x18000c572  mov     [rbx+150h], r15
0x18000c579  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x18000c580  lea     rax, ??_7CBaseSeeking@@6BCUnknown@@@; const CBaseSeeking::`vftable'{for `CUnknown'}
0x18000c587  mov     [r9+30h], r15
0x18000c58b  mov     [r9], rax
0x18000c58e  test    rdx, rdx
0x18000c591  lea     rax, ??_7CBaseSeeking@@6BIMediaSeeking@@@; const CBaseSeeking::`vftable'{for `IMediaSeeking'}
0x18000c598  mov     [r9+38h], r8
0x18000c59c  mov     [r9+18h], rax
0x18000c5a0  cmovz   rdx, r9
0x18000c5a4  mov     [r9+8], rdx
0x18000c5a8  mov     rax, 3FF0000000000000h
0x18000c5b2  mov     [r9+20h], rax
0x18000c5b6  mov     rcx, rdi; lpCriticalSection
0x18000c5b9  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000c5c3  mov     [r9+10h], r15d
0x18000c5c7  mov     [r9+28h], rax
0x18000c5cb  mov     [r9+40h], r15d
0x18000c5cf  movups  xmm0, xmmword ptr cs:TIME_FORMAT_MEDIA_TIME.Data1
0x18000c5d6  movdqu  xmmword ptr [r9+44h], xmm0
0x18000c5dc  call    cs:__imp_EnterCriticalSection
0x18000c5e2  lea     rsi, [rbp+100h]
0x18000c5e9  mov     rcx, rsi; lpCriticalSection
0x18000c5ec  call    cs:__imp_EnterCriticalSection
0x18000c5f2  lock inc dword ptr [rbp+70h]
0x18000c5f6  lea     rcx, [rbx+18h]
0x18000c5fa  mov     rax, [rcx]
0x18000c5fd  mov     rax, [rax+8]
0x18000c601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c606  lea     rcx, [rbp+88h]; this
0x18000c60d  mov     rdx, rbx; void *
0x18000c610  call    ?AddTailI@CBaseList@@IEAAPEAU__POSITION@@PEAX@Z; CBaseList::AddTailI(void *)
0x18000c615  mov     rcx, rsi; lpCriticalSection
0x18000c618  test    rax, rax
0x18000c61b  jnz     short loc_18000C651
0x18000c61d  call    cs:__imp_LeaveCriticalSection
0x18000c623  mov     rcx, rdi; lpCriticalSection
0x18000c626  call    cs:__imp_LeaveCriticalSection
0x18000c62c  mov     rax, [rbx]
0x18000c62f  lea     edx, [r15+1]
0x18000c633  mov     rcx, rbx
0x18000c636  mov     rax, [rax+18h]
0x18000c63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c63f  mov     eax, 8007000Eh
0x18000c644  add     rsp, 48h
0x18000c648  pop     r15
0x18000c64a  pop     r14
0x18000c64c  pop     rdi
0x18000c64d  pop     rsi
0x18000c64e  pop     rbp
0x18000c64f  pop     rbx
0x18000c650  retn
0x18000c651  call    cs:__imp_LeaveCriticalSection
0x18000c657  mov     rcx, rdi; lpCriticalSection
0x18000c65a  call    cs:__imp_LeaveCriticalSection
0x18000c660  lea     rax, [rbx+0E8h]
0x18000c667  mov     [r14], rax
0x18000c66a  xor     eax, eax
0x18000c66c  jmp     short loc_18000C644
```
