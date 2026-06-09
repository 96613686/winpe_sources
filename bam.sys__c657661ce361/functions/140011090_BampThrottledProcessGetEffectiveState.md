# BampThrottledProcessGetEffectiveState

- ea: `0x140011090`
- end: `0x1400110ce`
- name: `BampThrottledProcessGetEffectiveState`
- size: `62`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c990`
- `0x140010a30`
- `0x140011010`
- `0x1400110d8`

## callees

- `0x140011090`

## pseudocode

```c
__int64 __fastcall BampThrottledProcessGetEffectiveState(__int64 a1, unsigned int *a2)
{
  __int64 result; // rax
  bool v3; // zf

  *(_OWORD *)a2 = *(_OWORD *)(a1 + 304);
  *((_QWORD *)a2 + 2) = *(_QWORD *)(a1 + 320);
  result = *a2;
  if ( (result & 0x10) != 0 )
  {
    result = (unsigned int)result | 1;
    *a2 = result;
  }
  if ( (result & 1) == 0 )
  {
    v3 = a2[5] == 0;
    result = *(unsigned int *)(a1 + 328);
    *a2 = result;
    if ( v3 )
    {
      result = *(unsigned int *)(a1 + 348);
      a2[5] = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140011090  movups  xmm0, xmmword ptr [rcx+130h]
0x140011097  movups  xmmword ptr [rdx], xmm0
0x14001109a  movsd   xmm1, qword ptr [rcx+140h]
0x1400110a2  movsd   qword ptr [rdx+10h], xmm1
0x1400110a7  mov     eax, [rdx]
0x1400110a9  test    al, 10h
0x1400110ab  jz      short loc_1400110B2
0x1400110ad  or      eax, 1
0x1400110b0  mov     [rdx], eax
0x1400110b2  test    al, 1
0x1400110b4  jnz     short locret_1400110CD
0x1400110b6  cmp     dword ptr [rdx+14h], 0
0x1400110ba  mov     eax, [rcx+148h]
0x1400110c0  mov     [rdx], eax
0x1400110c2  jnz     short locret_1400110CD
0x1400110c4  mov     eax, [rcx+15Ch]
0x1400110ca  mov     [rdx+14h], eax
0x1400110cd  retn
```
