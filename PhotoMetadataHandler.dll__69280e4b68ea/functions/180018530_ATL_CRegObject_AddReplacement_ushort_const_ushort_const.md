# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180018530`
- end: `0x1800185b0`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `128`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001aa20`
- `0x18001aca4`

## callees

- `0x180018078`
- `0x18001832c`
- `0x180018530`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001857a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001857a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018550`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018550`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v6; // ebx
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v8 = 0;
  v6 = ATL::CExpansionVector::Add((ATL::CRegObject *)((char *)this + 8), a2, a3);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v8);
  return v6 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x180018530  push    rbx
0x180018532  push    rbp
0x180018533  push    rsi
0x180018534  push    rdi
0x180018535  sub     rsp, 28h
0x180018539  mov     rbx, r8
0x18001853c  mov     rsi, rdx
0x18001853f  mov     rbp, rcx
0x180018542  test    rdx, rdx
0x180018545  jz      short loc_1800185A1
0x180018547  test    rbx, rbx
0x18001854a  jz      short loc_1800185A1
0x18001854c  add     rcx, 20h ; ' '; lpCriticalSection
0x180018550  call    cs:__imp_EnterCriticalSection
0x180018557  nop     dword ptr [rax+rax+00h]
0x18001855c  mov     [rsp+48h+arg_8], 0
0x180018565  lea     rcx, [rbp+8]; this
0x180018569  mov     r8, rbx; unsigned __int16 *
0x18001856c  mov     rdx, rsi; unsigned __int16 *
0x18001856f  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180018574  mov     ebx, eax
0x180018576  lea     rcx, [rbp+20h]; lpCriticalSection
0x18001857a  call    cs:__imp_LeaveCriticalSection
0x180018581  nop     dword ptr [rax+rax+00h]
0x180018586  nop
0x180018587  neg     ebx
0x180018589  sbb     ebx, ebx
0x18001858b  not     ebx
0x18001858d  and     ebx, 8007000Eh
0x180018593  lea     rcx, [rsp+48h+arg_8]
0x180018598  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001859d  mov     eax, ebx
0x18001859f  jmp     short loc_1800185A6
0x1800185a1  mov     eax, 80070057h
0x1800185a6  add     rsp, 28h
0x1800185aa  pop     rdi
0x1800185ab  pop     rsi
0x1800185ac  pop     rbp
0x1800185ad  pop     rbx
0x1800185ae  retn
```
