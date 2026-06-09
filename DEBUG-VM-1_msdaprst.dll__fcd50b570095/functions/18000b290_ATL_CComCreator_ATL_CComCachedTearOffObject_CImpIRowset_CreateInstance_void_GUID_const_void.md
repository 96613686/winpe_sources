# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIRowset>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000b290`
- end: `0x18000b390`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIRowset@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001d94`
- `0x18000a1e8`
- `0x18000a834`
- `0x18000b290`
- `0x18001a54c`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIRowset>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // ebp
  unsigned __int8 *v8; // rax
  unsigned __int8 *v9; // r14
  __int64 v10; // rsi

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = MMMAlloc(0x48u, a2);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIRowset>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &CImpIRowset::`vftable';
    *((_DWORD *)v9 + 16) = 0;
    *((_QWORD *)v9 + 7) = &CImpIRowset::CNotUpdt_BidGeneric::`vftable';
    *((_DWORD *)v9 + 16) = bidObtainItemIDW(
                             `CImpIRowset::CNotUpdt_BidGeneric::BidObtainID'::`7'::_bidPtrSA_051_337[0],
                             v9 + 56);
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIRowset>::`vftable';
    *((_QWORD *)v9 + 4) = v10;
    *((_QWORD *)v9 + 6) = a1;
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    v7 = (**(__int64 (__fastcall ***)(unsigned __int8 *, __int64, _QWORD *))v9)(v9, a2, a3);
    if ( v7 )
      ATL::CComCachedTearOffObject<CImpIRowset>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b290  push    rbx
0x18000b292  push    rbp
0x18000b293  push    rsi
0x18000b294  push    rdi
0x18000b295  push    r12
0x18000b297  push    r13
0x18000b299  push    r14
0x18000b29b  push    r15
0x18000b29d  sub     rsp, 28h
0x18000b2a1  mov     r15, r8
0x18000b2a4  mov     r12, rdx
0x18000b2a7  mov     r13, rcx
0x18000b2aa  test    r8, r8
0x18000b2ad  jnz     short loc_18000B2B9
0x18000b2af  mov     eax, 80004003h
0x18000b2b4  jmp     loc_18000B37F
0x18000b2b9  mov     qword ptr [r8], 0
0x18000b2c0  mov     ebp, 8007000Eh
0x18000b2c5  mov     ecx, 48h ; 'H'; unsigned int
0x18000b2ca  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b2cf  mov     r14, rax
0x18000b2d2  mov     [rsp+68h+arg_10], rax
0x18000b2da  test    rax, rax
0x18000b2dd  jz      short loc_18000B353
0x18000b2df  mov     dword ptr [rax+8], 0
0x18000b2e6  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIRowset@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIRowset>::`vftable'
0x18000b2ed  mov     [r14], rax
0x18000b2f0  mov     rax, [r13+0]
0x18000b2f4  mov     rcx, r13
0x18000b2f7  mov     rax, [rax+20h]
0x18000b2fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b300  mov     rsi, rax
0x18000b303  lea     rcx, [r14+20h]
0x18000b307  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000b30c  lea     rax, ??_7CImpIRowset@@6B@; const CImpIRowset::`vftable'
0x18000b313  mov     [r14+18h], rax
0x18000b317  mov     dword ptr [r14+40h], 0
0x18000b31f  lea     rax, ??_7CNotUpdt_BidGeneric@CImpIRowset@@6B@; const CImpIRowset::CNotUpdt_BidGeneric::`vftable'
0x18000b326  mov     [r14+38h], rax
0x18000b32a  lea     rdx, [r14+38h]
0x18000b32e  mov     rcx, cs:?_bidPtrSA_051_337@?6??BidObtainID@CNotUpdt_BidGeneric@CImpIRowset@@AEAAHPEBX@Z@4REBGEB; ushort const * const `CImpIRowset::CNotUpdt_BidGeneric::BidObtainID(void const *)'::`7'::_bidPtrSA_051_337
0x18000b335  call    _bidObtainItemIDW
0x18000b33a  mov     [r14+40h], eax
0x18000b33e  lea     rax, ??_7?$CComContainedObject@VCImpIRowset@@@ATL@@6B@; const ATL::CComContainedObject<CImpIRowset>::`vftable'
0x18000b345  mov     [r14+18h], rax
0x18000b349  mov     [r14+20h], rsi
0x18000b34d  mov     [r14+30h], r13
0x18000b351  jmp     short loc_18000B356
0x18000b353  xor     r14d, r14d
0x18000b356  test    r14, r14
0x18000b359  jz      short loc_18000B37D
0x18000b35b  mov     rax, [r14]
0x18000b35e  mov     r8, r15
0x18000b361  mov     rdx, r12
0x18000b364  mov     rcx, r14
0x18000b367  mov     rax, [rax]
0x18000b36a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b36f  mov     ebp, eax
0x18000b371  test    eax, eax
0x18000b373  jz      short loc_18000B37D
0x18000b375  mov     rcx, r14; unsigned __int8 *
0x18000b378  call    ??_G?$CComCachedTearOffObject@VCImpIRowset@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIRowset>::`scalar deleting destructor'(uint)
0x18000b37d  mov     eax, ebp
0x18000b37f  add     rsp, 28h
0x18000b383  pop     r15
0x18000b385  pop     r14
0x18000b387  pop     r13
0x18000b389  pop     r12
0x18000b38b  pop     rdi
0x18000b38c  pop     rsi
0x18000b38d  pop     rbp
0x18000b38e  pop     rbx
0x18000b38f  retn
```
