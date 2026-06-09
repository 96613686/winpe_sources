# Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)

- ea: `0x180001580`
- end: `0x1800015e9`
- name: `??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180002cc4`
- `0x180003b10`
- `0x180004700`
- `0x180004a00`
- `0x180007ad0`
- `0x1800083f0`
- `0x18000a320`
- `0x18000d900`
- `0x18000f730`

## callees

- `0x180001580`
- `0x180003a38`

## pseudocode

```c
_OWORD *__fastcall Kerb3961::Split<2>(_OWORD *a1, unsigned __int64 *a2, __int64 a3)
{
  unsigned __int64 v3; // r10
  unsigned __int64 i; // r11
  unsigned __int64 v7; // rcx
  const unsigned __int16 *v8; // rdx
  _OWORD *result; // rax
  __int128 v10; // xmm1
  _OWORD v11[2]; // [rsp+20h] [rbp-28h]

  v3 = 0;
  for ( i = 0; i < 2; ++i )
  {
    v7 = i;
    v8 = (const unsigned __int16 *)(v3 + a2[1]);
    *(_QWORD *)&v11[v7] = *(_QWORD *)(a3 + 8 * i);
    *((_QWORD *)&v11[v7] + 1) = v8;
    v3 += *(_QWORD *)(a3 + 8 * i);
  }
  if ( v3 > *a2 )
    Kerb3961::ConsistencyFail((Kerb3961 *)L"Splitting buffer into parts that exceed the whole", v8);
  result = a1;
  v10 = v11[1];
  *a1 = v11[0];
  a1[1] = v10;
  return result;
}

```

## disassembly

```asm
0x180001580  push    rbx
0x180001582  sub     rsp, 40h
0x180001586  xor     r10d, r10d
0x180001589  mov     rbx, rdx
0x18000158c  xor     r11d, r11d
0x18000158f  mov     r9, rcx
0x180001592  mov     rdx, [rbx+8]
0x180001596  mov     rcx, r11
0x180001599  mov     rax, [r8+r11*8]
0x18000159d  add     rcx, rcx
0x1800015a0  add     rdx, r10; unsigned __int16 *
0x1800015a3  mov     qword ptr [rsp+rcx*8+48h+var_28], rax
0x1800015a8  mov     qword ptr [rsp+rcx*8+48h+var_28+8], rdx
0x1800015ad  add     r10, [r8+r11*8]
0x1800015b1  inc     r11
0x1800015b4  cmp     r11, 2
0x1800015b8  jb      short loc_180001592
0x1800015ba  cmp     r10, [rbx]
0x1800015bd  ja      short loc_1800015DC
0x1800015bf  movups  xmm0, [rsp+48h+var_28]
0x1800015c4  mov     rax, r9
0x1800015c7  movups  xmm1, [rsp+48h+var_18]
0x1800015cc  movups  xmmword ptr [r9], xmm0
0x1800015d0  movups  xmmword ptr [r9+10h], xmm1
0x1800015d5  add     rsp, 40h
0x1800015d9  pop     rbx
0x1800015da  retn
0x1800015dc  lea     rcx, aSplittingBuffe; "Splitting buffer into parts that exceed"...
0x1800015e3  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
