# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)

- ea: `0x18000a850`
- end: `0x18000a87c`
- name: `??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ`
- size: `44`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cb72`
- `0x18000cbe4`
- `0x18000cbfa`
- `0x18000cc26`
- `0x18000cc38`
- `0x18000cc5c`
- `0x18000ccc6`
- `0x18000ccd8`
- `0x18000ccea`
- `0x18000cd59`
- `0x18000cd6b`
- `0x18000cdaa`

## callees

- `0x18000a850`
- `0x18000e010`

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
0x18000a850  sub     rsp, 28h
0x18000a854  mov     rdx, [rcx]
0x18000a857  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000a85b  or      eax, 0FFFFFFFFh
0x18000a85e  lock xadd [rdx+10h], eax
0x18000a863  sub     eax, 1
0x18000a866  jg      short loc_18000A877
0x18000a868  mov     rcx, [rdx]
0x18000a86b  mov     rax, [rcx]
0x18000a86e  mov     rax, [rax+8]
0x18000a872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a877  add     rsp, 28h
0x18000a87b  retn
```
