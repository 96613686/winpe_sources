# ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)

- ea: `0x1400053cc`
- end: `0x140005401`
- name: `?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z`
- size: `53`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b250`
- `0x14000cfd0`
- `0x14000f810`
- `0x140010244`
- `0x140010960`

## callees

- `0x1400053cc`

## pseudocode

```c
_QWORD *__fastcall ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
        _QWORD *a1,
        __int64 a2)
{
  _QWORD *result; // rax
  unsigned __int16 *v4; // rcx
  __int64 v5; // r8
  int v6; // r9d
  int v7; // edx

  for ( result = (_QWORD *)*a1; result; result = (_QWORD *)*result )
  {
    v4 = (unsigned __int16 *)result[2];
    v5 = a2 - (_QWORD)v4;
    do
    {
      v6 = *(unsigned __int16 *)((char *)v4 + v5);
      v7 = *v4 - v6;
      if ( v7 )
        break;
      ++v4;
    }
    while ( v6 );
    if ( !v7 )
      break;
  }
  return result;
}

```

## disassembly

```asm
0x1400053cc  mov     rax, [rcx]
0x1400053cf  mov     r10, rdx
0x1400053d2  jmp     short loc_1400053FB
0x1400053d4  mov     rcx, [rax+10h]
0x1400053d8  mov     r8, r10
0x1400053db  sub     r8, rcx
0x1400053de  movzx   edx, word ptr [rcx]
0x1400053e1  movzx   r9d, word ptr [rcx+r8]
0x1400053e6  sub     edx, r9d
0x1400053e9  jnz     short loc_1400053F4
0x1400053eb  add     rcx, 2
0x1400053ef  test    r9d, r9d
0x1400053f2  jnz     short loc_1400053DE
0x1400053f4  test    edx, edx
0x1400053f6  jz      short locret_140005400
0x1400053f8  mov     rax, [rax]
0x1400053fb  test    rax, rax
0x1400053fe  jnz     short loc_1400053D4
0x140005400  retn
```
