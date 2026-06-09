# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)

- ea: `0x18000d98c`
- end: `0x18000d9b9`
- name: `??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ`
- size: `45`
- prototype: ``
- caller_count: `36`
- callee_count: `2`
- tags: ``

## callers

- `0x180027ef8`
- `0x180027f7e`
- `0x180027fb7`
- `0x180027fca`
- `0x180028016`
- `0x18002806a`
- `0x180028076`
- `0x1800281a8`
- `0x1800281b4`
- `0x180028383`
- `0x1800283a9`
- `0x1800283e2`
- `0x1800283f5`
- `0x180028929`
- `0x180028939`
- `0x180028949`
- `0x180028959`
- `0x1800289c2`
- `0x180028a16`
- `0x180028a6a`
- `0x180028a76`
- `0x180028adc`
- `0x180028ae8`
- `0x180028af4`
- `0x180028b00`
- `0x180028b0c`
- `0x180028b18`
- `0x180028b6f`
- `0x180028b7f`
- `0x180028b8f`
- `0x180028b9f`
- `0x180028cd7`
- `0x18002954e`
- `0x180029653`
- `0x18002966b`
- `0x1800297e4`

## callees

- `0x18000d98c`
- `0x180027910`

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
0x18000d98c  sub     rsp, 28h
0x18000d990  mov     rdx, [rcx]
0x18000d993  sub     rdx, 18h
0x18000d997  or      eax, 0FFFFFFFFh
0x18000d99a  lock xadd [rdx+10h], eax
0x18000d99f  sub     eax, 1
0x18000d9a2  jg      short loc_18000D9B4
0x18000d9a4  mov     rcx, [rdx]
0x18000d9a7  mov     rax, [rcx]
0x18000d9aa  mov     rax, [rax+8]
0x18000d9ae  call    cs:__guard_dispatch_icall_fptr
0x18000d9b4  add     rsp, 28h
0x18000d9b8  retn
```
