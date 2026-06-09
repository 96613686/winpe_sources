# CADTGPersistStreamInit::~CADTGPersistStreamInit(void)

- ea: `0x180013990`
- end: `0x180013a18`
- name: `??1CADTGPersistStreamInit@@QEAA@XZ`
- size: `136`
- prototype: `void __fastcall(CADTGPersistStreamInit *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800138e0`

## callees

- `0x180013990`
- `0x180030010`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x180013a11`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CADTGPersistStreamInit::~CADTGPersistStreamInit(CADTGPersistStreamInit *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CADTGPersistStreamInit::`vftable';
  v2 = *((_QWORD *)this + 7);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  *((_QWORD *)this + 3) = &CADTGPersistStreamInit::CNotUpdt_BidGeneric::`vftable';
  if ( *((_DWORD *)this + 8) && bidID != -1 )
    ((void (__fastcall *)(__int64, wchar_t *, __int64, _QWORD, _QWORD))off_180042128)(
      bidID,
      `CADTGPersistStreamInit::CNotUpdt_BidGeneric::BidRecycleID'::`7'::_bidPtrSA_053_525[0],
      7,
      *((int *)this + 8),
      0);
  *((_DWORD *)this + 8) = 0;
  MPDeleteCriticalSection((char *)this + 16);
}

```

## disassembly

```asm
0x180013990  push    rbx
0x180013992  sub     rsp, 30h
0x180013996  mov     rbx, rcx
0x180013999  lea     rax, ??_7CADTGPersistStreamInit@@6B@; const CADTGPersistStreamInit::`vftable'
0x1800139a0  mov     [rcx], rax
0x1800139a3  mov     rcx, [rcx+38h]
0x1800139a7  test    rcx, rcx
0x1800139aa  jz      short loc_1800139B9
0x1800139ac  mov     rax, [rcx]
0x1800139af  mov     rax, [rax+10h]
0x1800139b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139b8  nop
0x1800139b9  lea     rax, ??_7CNotUpdt_BidGeneric@CADTGPersistStreamInit@@6B@; const CADTGPersistStreamInit::CNotUpdt_BidGeneric::`vftable'
0x1800139c0  mov     [rbx+18h], rax
0x1800139c4  cmp     dword ptr [rbx+20h], 0
0x1800139c8  jz      short loc_180013A01
0x1800139ca  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1800139d2  jz      short loc_180013A01
0x1800139d4  mov     rax, cs:off_180042128
0x1800139db  movsxd  r9, dword ptr [rbx+20h]
0x1800139df  mov     [rsp+38h+var_18], 0
0x1800139e8  mov     r8d, 7
0x1800139ee  mov     rdx, cs:?_bidPtrSA_053_525@?6??BidRecycleID@CNotUpdt_BidGeneric@CADTGPersistStreamInit@@AEAAHXZ@4REBGEB; ushort const * const `CADTGPersistStreamInit::CNotUpdt_BidGeneric::BidRecycleID(void)'::`7'::_bidPtrSA_053_525
0x1800139f5  mov     rcx, cs:_bidID
0x1800139fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a01  mov     dword ptr [rbx+20h], 0
0x180013a08  lea     rcx, [rbx+10h]
0x180013a0c  add     rsp, 30h
0x180013a10  pop     rbx
0x180013a11  jmp     cs:__imp_MPDeleteCriticalSection
```
