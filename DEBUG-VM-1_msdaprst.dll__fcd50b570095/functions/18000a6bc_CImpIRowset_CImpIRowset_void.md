# CImpIRowset::~CImpIRowset(void)

- ea: `0x18000a6bc`
- end: `0x18000a724`
- name: `??1CImpIRowset@@QEAA@XZ`
- size: `104`
- prototype: `void __fastcall(CImpIRowset *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a3b0`

## callees

- `0x18000a6bc`
- `0x180030010`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18000a71d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CImpIRowset::~CImpIRowset(CImpIRowset *this)
{
  *((_QWORD *)this + 4) = &CImpIRowset::CNotUpdt_BidGeneric::`vftable';
  if ( *((_DWORD *)this + 10) && bidID != -1 )
    ((void (__fastcall *)(__int64, wchar_t *, __int64, _QWORD, _QWORD))off_180042128)(
      bidID,
      `CImpIRowset::CNotUpdt_BidGeneric::BidRecycleID'::`7'::_bidPtrSA_053_337[0],
      7,
      *((int *)this + 10),
      0);
  *((_DWORD *)this + 10) = 0;
  MPDeleteCriticalSection((char *)this + 16);
}

```

## disassembly

```asm
0x18000a6bc  push    rbx
0x18000a6be  sub     rsp, 30h
0x18000a6c2  mov     rbx, rcx
0x18000a6c5  lea     rax, ??_7CNotUpdt_BidGeneric@CImpIRowset@@6B@; const CImpIRowset::CNotUpdt_BidGeneric::`vftable'
0x18000a6cc  mov     [rcx+20h], rax
0x18000a6d0  cmp     dword ptr [rcx+28h], 0
0x18000a6d4  jz      short loc_18000A70D
0x18000a6d6  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18000a6de  jz      short loc_18000A70D
0x18000a6e0  mov     rax, cs:off_180042128
0x18000a6e7  movsxd  r9, dword ptr [rcx+28h]
0x18000a6eb  mov     [rsp+38h+var_18], 0
0x18000a6f4  mov     r8d, 7
0x18000a6fa  mov     rdx, cs:?_bidPtrSA_053_337@?6??BidRecycleID@CNotUpdt_BidGeneric@CImpIRowset@@AEAAHXZ@4REBGEB; ushort const * const `CImpIRowset::CNotUpdt_BidGeneric::BidRecycleID(void)'::`7'::_bidPtrSA_053_337
0x18000a701  mov     rcx, cs:_bidID
0x18000a708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a70d  mov     dword ptr [rbx+28h], 0
0x18000a714  lea     rcx, [rbx+10h]
0x18000a718  add     rsp, 30h
0x18000a71c  pop     rbx
0x18000a71d  jmp     cs:__imp_MPDeleteCriticalSection
```
