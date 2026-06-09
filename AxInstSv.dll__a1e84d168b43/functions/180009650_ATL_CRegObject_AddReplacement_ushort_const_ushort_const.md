# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180009650`
- end: `0x1800096c3`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `115`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800105bc`
- `0x180010834`

## callees

- `0x1800082ec`
- `0x180009270`
- `0x180009650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009694`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009694`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009670`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009670`

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
0x180009650  push    rbx
0x180009652  push    rbp
0x180009653  push    rsi
0x180009654  push    rdi
0x180009655  sub     rsp, 28h
0x180009659  mov     rbx, r8
0x18000965c  mov     rsi, rdx
0x18000965f  mov     rbp, rcx
0x180009662  test    rdx, rdx
0x180009665  jz      short loc_1800096B5
0x180009667  test    rbx, rbx
0x18000966a  jz      short loc_1800096B5
0x18000966c  add     rcx, 20h ; ' '; lpCriticalSection
0x180009670  call    cs:__imp_EnterCriticalSection
0x180009676  mov     [rsp+48h+arg_8], 0
0x18000967f  lea     rcx, [rbp+8]; this
0x180009683  mov     r8, rbx; unsigned __int16 *
0x180009686  mov     rdx, rsi; unsigned __int16 *
0x180009689  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000968e  mov     ebx, eax
0x180009690  lea     rcx, [rbp+20h]; lpCriticalSection
0x180009694  call    cs:__imp_LeaveCriticalSection
0x18000969a  nop
0x18000969b  neg     ebx
0x18000969d  sbb     ebx, ebx
0x18000969f  not     ebx
0x1800096a1  and     ebx, 8007000Eh
0x1800096a7  lea     rcx, [rsp+48h+arg_8]
0x1800096ac  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800096b1  mov     eax, ebx
0x1800096b3  jmp     short loc_1800096BA
0x1800096b5  mov     eax, 80070057h
0x1800096ba  add     rsp, 28h
0x1800096be  pop     rdi
0x1800096bf  pop     rsi
0x1800096c0  pop     rbp
0x1800096c1  pop     rbx
0x1800096c2  retn
```
