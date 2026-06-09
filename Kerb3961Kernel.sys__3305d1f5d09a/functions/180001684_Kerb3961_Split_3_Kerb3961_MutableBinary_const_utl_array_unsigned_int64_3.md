# Kerb3961::Split<3>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,3>)

- ea: `0x180001684`
- end: `0x1800016f7`
- name: `??$Split@$02@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$02@utl@@AEBUMutableBinary@0@U?$array@_K$02@2@@Z`
- size: `115`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800028d4`
- `0x180003dc0`
- `0x180004700`
- `0x180007338`
- `0x180009da0`
- `0x18000a320`
- `0x18000e6b0`

## callees

- `0x180001684`
- `0x180003a38`

## pseudocode

```c
_OWORD *__fastcall Kerb3961::Split<3>(_OWORD *a1, unsigned __int64 *a2, __int64 a3)
{
  unsigned __int64 v3; // r10
  unsigned __int64 i; // r11
  unsigned __int64 v7; // rcx
  const unsigned __int16 *v8; // rdx
  _OWORD *result; // rax
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  _OWORD v12[3]; // [rsp+20h] [rbp-38h]

  v3 = 0;
  for ( i = 0; i < 3; ++i )
  {
    v7 = i;
    v8 = (const unsigned __int16 *)(v3 + a2[1]);
    *(_QWORD *)&v12[v7] = *(_QWORD *)(a3 + 8 * i);
    *((_QWORD *)&v12[v7] + 1) = v8;
    v3 += *(_QWORD *)(a3 + 8 * i);
  }
  if ( v3 > *a2 )
    Kerb3961::ConsistencyFail((Kerb3961 *)L"Splitting buffer into parts that exceed the whole", v8);
  result = a1;
  v10 = v12[1];
  *a1 = v12[0];
  v11 = v12[2];
  a1[1] = v10;
  a1[2] = v11;
  return result;
}

```

## disassembly

```asm
0x180001684  push    rbx
0x180001686  sub     rsp, 50h
0x18000168a  xor     r10d, r10d
0x18000168d  mov     rbx, rdx
0x180001690  xor     r11d, r11d
0x180001693  mov     r9, rcx
0x180001696  mov     rdx, [rbx+8]
0x18000169a  mov     rcx, r11
0x18000169d  mov     rax, [r8+r11*8]
0x1800016a1  add     rcx, rcx
0x1800016a4  add     rdx, r10; unsigned __int16 *
0x1800016a7  mov     qword ptr [rsp+rcx*8+58h+var_38], rax
0x1800016ac  mov     qword ptr [rsp+rcx*8+58h+var_38+8], rdx
0x1800016b1  add     r10, [r8+r11*8]
0x1800016b5  inc     r11
0x1800016b8  cmp     r11, 3
0x1800016bc  jb      short loc_180001696
0x1800016be  cmp     r10, [rbx]
0x1800016c1  ja      short loc_1800016EA
0x1800016c3  movups  xmm0, [rsp+58h+var_38]
0x1800016c8  mov     rax, r9
0x1800016cb  movups  xmm1, [rsp+58h+var_28]
0x1800016d0  movups  xmmword ptr [r9], xmm0
0x1800016d4  movups  xmm0, [rsp+58h+var_18]
0x1800016d9  movups  xmmword ptr [r9+10h], xmm1
0x1800016de  movups  xmmword ptr [r9+20h], xmm0
0x1800016e3  add     rsp, 50h
0x1800016e7  pop     rbx
0x1800016e8  retn
0x1800016ea  lea     rcx, aSplittingBuffe; "Splitting buffer into parts that exceed"...
0x1800016f1  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
