# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)

- ea: `0x18000361c`
- end: `0x180003648`
- name: `??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ`
- size: `44`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180010139`
- `0x1800102d4`
- `0x1800104a4`
- `0x180010596`
- `0x180010668`
- `0x180010757`
- `0x180010876`
- `0x180010888`
- `0x1800108ac`
- `0x18001093c`
- `0x180010a2c`
- `0x180010a3e`
- `0x180010bbe`

## callees

- `0x18000361c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        _QWORD *a1)
{
  volatile signed __int32 *v1; // rdx
  signed __int32 v2; // eax
  bool v3; // cc
  __int64 result; // rax

  v1 = (volatile signed __int32 *)(*a1 - 24LL);
  v2 = _InterlockedExchangeAdd(v1 + 4, 0xFFFFFFFF);
  v3 = v2 <= 1;
  result = (unsigned int)(v2 - 1);
  if ( v3 )
    return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v1 + 8LL))(*(_QWORD *)v1);
  return result;
}

```

## disassembly

```asm
0x18000361c  sub     rsp, 28h
0x180003620  mov     rdx, [rcx]
0x180003623  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180003627  or      eax, 0FFFFFFFFh
0x18000362a  lock xadd [rdx+10h], eax
0x18000362f  sub     eax, 1
0x180003632  jg      short loc_180003643
0x180003634  mov     rcx, [rdx]
0x180003637  mov     rax, [rcx]
0x18000363a  mov     rax, [rax+8]
0x18000363e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003643  add     rsp, 28h
0x180003647  retn
```
