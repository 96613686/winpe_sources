# Kerb3961::Split<4>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,4>)

- ea: `0x180001794`
- end: `0x180001811`
- name: `??$Split@$03@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$03@utl@@AEBUMutableBinary@0@U?$array@_K$03@2@@Z`
- size: `125`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003240`
- `0x180004a00`
- `0x180007710`

## callees

- `0x180001794`
- `0x180003a38`

## pseudocode

```c
_OWORD *__fastcall Kerb3961::Split<4>(_OWORD *a1, unsigned __int64 *a2, __int64 a3)
{
  unsigned __int64 v3; // r10
  unsigned __int64 i; // r11
  unsigned __int64 v7; // rcx
  const unsigned __int16 *v8; // rdx
  _OWORD *result; // rax
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  _OWORD v13[4]; // [rsp+20h] [rbp-48h]

  v3 = 0;
  for ( i = 0; i < 4; ++i )
  {
    v7 = i;
    v8 = (const unsigned __int16 *)(v3 + a2[1]);
    *(_QWORD *)&v13[v7] = *(_QWORD *)(a3 + 8 * i);
    *((_QWORD *)&v13[v7] + 1) = v8;
    v3 += *(_QWORD *)(a3 + 8 * i);
  }
  if ( v3 > *a2 )
    Kerb3961::ConsistencyFail((Kerb3961 *)L"Splitting buffer into parts that exceed the whole", v8);
  result = a1;
  v10 = v13[1];
  *a1 = v13[0];
  v11 = v13[2];
  a1[1] = v10;
  v12 = v13[3];
  a1[2] = v11;
  a1[3] = v12;
  return result;
}

```

## disassembly

```asm
0x180001794  push    rbx
0x180001796  sub     rsp, 60h
0x18000179a  xor     r10d, r10d
0x18000179d  mov     rbx, rdx
0x1800017a0  xor     r11d, r11d
0x1800017a3  mov     r9, rcx
0x1800017a6  mov     rdx, [rbx+8]
0x1800017aa  mov     rcx, r11
0x1800017ad  mov     rax, [r8+r11*8]
0x1800017b1  add     rcx, rcx
0x1800017b4  add     rdx, r10; unsigned __int16 *
0x1800017b7  mov     qword ptr [rsp+rcx*8+68h+var_48], rax
0x1800017bc  mov     qword ptr [rsp+rcx*8+68h+var_48+8], rdx
0x1800017c1  add     r10, [r8+r11*8]
0x1800017c5  inc     r11
0x1800017c8  cmp     r11, 4
0x1800017cc  jb      short loc_1800017A6
0x1800017ce  cmp     r10, [rbx]
0x1800017d1  ja      short loc_180001804
0x1800017d3  movaps  xmm0, [rsp+68h+var_48]
0x1800017d8  mov     rax, r9
0x1800017db  movaps  xmm1, [rsp+68h+var_38]
0x1800017e0  movaps  xmmword ptr [r9], xmm0
0x1800017e4  movaps  xmm0, [rsp+68h+var_28]
0x1800017e9  movaps  xmmword ptr [r9+10h], xmm1
0x1800017ee  movaps  xmm1, [rsp+68h+var_18]
0x1800017f3  movaps  xmmword ptr [r9+20h], xmm0
0x1800017f8  movaps  xmmword ptr [r9+30h], xmm1
0x1800017fd  add     rsp, 60h
0x180001801  pop     rbx
0x180001802  retn
0x180001804  lea     rcx, aSplittingBuffe; "Splitting buffer into parts that exceed"...
0x18000180b  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
