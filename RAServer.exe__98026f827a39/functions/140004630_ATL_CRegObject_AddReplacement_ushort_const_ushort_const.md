# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x140004630`
- end: `0x1400046a3`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `115`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b238`

## callees

- `0x140003340`
- `0x1400043a4`
- `0x140004630`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140004674`
- `KERNEL32!LeaveCriticalSection` at `0x140004674`
- `KERNEL32!EnterCriticalSection` at `0x140004650`
- `KERNEL32!EnterCriticalSection` at `0x140004650`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v6; // ebx
  _QWORD *v8; // [rsp+58h] [rbp+10h] BYREF

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
0x140004630  push    rbx
0x140004632  push    rbp
0x140004633  push    rsi
0x140004634  push    rdi
0x140004635  sub     rsp, 28h
0x140004639  mov     rbx, r8
0x14000463c  mov     rsi, rdx
0x14000463f  mov     rbp, rcx
0x140004642  test    rdx, rdx
0x140004645  jz      short loc_140004695
0x140004647  test    rbx, rbx
0x14000464a  jz      short loc_140004695
0x14000464c  add     rcx, 20h ; ' '; lpCriticalSection
0x140004650  call    cs:__imp_EnterCriticalSection
0x140004656  mov     [rsp+48h+arg_8], 0
0x14000465f  lea     rcx, [rbp+8]; this
0x140004663  mov     r8, rbx; unsigned __int16 *
0x140004666  mov     rdx, rsi; unsigned __int16 *
0x140004669  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x14000466e  mov     ebx, eax
0x140004670  lea     rcx, [rbp+20h]; lpCriticalSection
0x140004674  call    cs:__imp_LeaveCriticalSection
0x14000467a  nop
0x14000467b  neg     ebx
0x14000467d  sbb     ebx, ebx
0x14000467f  not     ebx
0x140004681  and     ebx, 8007000Eh
0x140004687  lea     rcx, [rsp+48h+arg_8]
0x14000468c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140004691  mov     eax, ebx
0x140004693  jmp     short loc_14000469A
0x140004695  mov     eax, 80070057h
0x14000469a  add     rsp, 28h
0x14000469e  pop     rdi
0x14000469f  pop     rsi
0x1400046a0  pop     rbp
0x1400046a1  pop     rbx
0x1400046a2  retn
```
