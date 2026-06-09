# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)

- ea: `0x140003750`
- end: `0x14000377c`
- name: `??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ`
- size: `44`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `25`
- callee_count: `2`
- tags: ``

## callers

- `0x140015cbe`
- `0x140015cd0`
- `0x140015d06`
- `0x140015d18`
- `0x140015d2a`
- `0x140015d3c`
- `0x140015d60`
- `0x140015df0`
- `0x140015e14`
- `0x140015e38`
- `0x140015e4a`
- `0x140015e6e`
- `0x140015eb6`
- `0x140015eec`
- `0x140015efe`
- `0x140015f22`
- `0x140015f38`
- `0x140015f4e`
- `0x140015f64`
- `0x140015f7a`
- `0x140015f90`
- `0x140015fa6`
- `0x140015fbc`
- `0x140015fd2`
- `0x1400160c3`

## callees

- `0x140003750`
- `0x140017010`

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
0x140003750  sub     rsp, 28h
0x140003754  mov     rdx, [rcx]
0x140003757  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000375b  or      eax, 0FFFFFFFFh
0x14000375e  lock xadd [rdx+10h], eax
0x140003763  sub     eax, 1
0x140003766  jg      short loc_140003777
0x140003768  mov     rcx, [rdx]
0x14000376b  mov     rax, [rcx]
0x14000376e  mov     rax, [rax+8]
0x140003772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003777  add     rsp, 28h
0x14000377b  retn
```
