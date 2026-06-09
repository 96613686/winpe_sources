# Binary::Policy::CompleteOperation::TargetDigitalRegion(Data::ShortTermResolution<int> const &)

- ea: `0x180087ce0`
- end: `0x180087d5e`
- name: `?TargetDigitalRegion@CompleteOperation@Policy@Binary@@QEAA?AV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `126`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `25`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180087d70`
- `0x180089230`
- `0x1800896c0`
- `0x180089c70`
- `0x18008a170`
- `0x18008a670`
- `0x18008aae0`
- `0x18008b130`
- `0x18008bc80`
- `0x18008ca80`
- `0x18008d660`
- `0x18008e070`
- `0x18008e6d0`
- `0x18008fe70`
- `0x180090300`
- `0x1800908b0`
- `0x180090e30`
- `0x1800913b0`
- `0x180091820`
- `0x1800920e0`
- `0x180092da0`
- `0x180093ab0`
- `0x180094590`
- `0x180094b90`
- `0x180095970`

## pseudocode

```c
_QWORD *__fastcall Binary::Policy::CompleteOperation::TargetDigitalRegion(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  __int128 v5; // xmm0
  int v6; // ecx
  int v7; // edx
  int v8; // edx
  _QWORD *result; // rax

  v5 = *(_OWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 16900LL);
  *a2 = 0;
  a2[1] = 0;
  v6 = *(_DWORD *)a1 + *a3 - v5;
  if ( v6 > 129 )
    v6 = 129;
  if ( v6 < 0 )
    v6 = 0;
  v7 = a3[1];
  if ( v7 < SDWORD1(v5) )
    v7 = DWORD1(v5);
  v8 = v7 - DWORD1(v5);
  if ( v8 > 129 )
    v8 = 129;
  *(_DWORD *)a2 = 130 - v8;
  result = a2;
  a2[1] = v8 + *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 130LL * v6;
  return result;
}

```

## disassembly

```asm
0x180087ce0  mov     rax, [rcx+8]
0x180087ce4  mov     r11, rdx
0x180087ce7  xor     edx, edx
0x180087ce9  mov     r10, rcx
0x180087cec  mov     r9, [rax+8]
0x180087cf0  movups  xmm0, xmmword ptr [r9+4204h]
0x180087cf8  mov     [r11], rdx
0x180087cfb  mov     r9d, 81h
0x180087d01  mov     [r11+8], rdx
0x180087d05  mov     ecx, [r8]
0x180087d08  movq    rax, xmm0
0x180087d0d  sub     ecx, eax
0x180087d0f  add     ecx, [r10]
0x180087d12  cmp     ecx, r9d
0x180087d15  cmovg   ecx, r9d
0x180087d19  test    ecx, ecx
0x180087d1b  cmovs   ecx, edx
0x180087d1e  mov     edx, [r8+4]
0x180087d22  shr     rax, 20h
0x180087d26  cmp     edx, eax
0x180087d28  cmovl   edx, eax
0x180087d2b  sub     edx, eax
0x180087d2d  mov     eax, 82h
0x180087d32  cmp     edx, r9d
0x180087d35  cmovg   edx, r9d
0x180087d39  sub     eax, edx
0x180087d3b  mov     [r11], eax
0x180087d3e  movsxd  rax, ecx
0x180087d41  imul    rcx, rax, 82h
0x180087d48  mov     rax, [r10+8]
0x180087d4c  add     rcx, [rax+8]
0x180087d50  movsxd  rax, edx
0x180087d53  add     rcx, rax
0x180087d56  mov     rax, r11
0x180087d59  mov     [r11+8], rcx
0x180087d5d  retn
```
