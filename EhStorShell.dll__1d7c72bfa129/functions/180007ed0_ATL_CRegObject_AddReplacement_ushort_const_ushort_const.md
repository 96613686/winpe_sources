# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180007ed0`
- end: `0x180007f18`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `72`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800091d4`

## callees

- `0x1800065fc`
- `0x180007cdc`
- `0x180007ed0`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned int v3; // ebx
  _QWORD *v5; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  v5 = 0;
  v3 = ATL::CExpansionVector::Add((ATL::CRegObject *)((char *)this + 8), a2, a3) == 0 ? 0x8007000E : 0;
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v5);
  return v3;
}

```

## disassembly

```asm
0x180007ed0  push    rbx
0x180007ed2  sub     rsp, 20h
0x180007ed6  test    rdx, rdx
0x180007ed9  jz      short loc_180007F0D
0x180007edb  test    r8, r8
0x180007ede  jz      short loc_180007F0D
0x180007ee0  mov     [rsp+28h+arg_8], 0
0x180007ee9  add     rcx, 8; this
0x180007eed  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180007ef2  nop
0x180007ef3  neg     eax
0x180007ef5  sbb     ebx, ebx
0x180007ef7  not     ebx
0x180007ef9  and     ebx, 8007000Eh
0x180007eff  lea     rcx, [rsp+28h+arg_8]
0x180007f04  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180007f09  mov     eax, ebx
0x180007f0b  jmp     short loc_180007F12
0x180007f0d  mov     eax, 80070057h
0x180007f12  add     rsp, 20h
0x180007f16  pop     rbx
0x180007f17  retn
```
