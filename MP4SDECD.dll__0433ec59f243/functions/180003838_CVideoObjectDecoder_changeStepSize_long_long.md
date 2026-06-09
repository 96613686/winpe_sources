# CVideoObjectDecoder::changeStepSize(long,long)

- ea: `0x180003838`
- end: `0x1800038d5`
- name: `?changeStepSize@CVideoObjectDecoder@@AEAAXJJ@Z`
- size: `157`
- prototype: `void __fastcall(CVideoObjectDecoder *__hidden this, int, int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002e90`
- `0x18000b1e0`
- `0x180035770`
- `0x180035e90`

## callees

- `0x180003838`
- `0x180024e8c`

## pseudocode

```c
void __fastcall CVideoObjectDecoder::changeStepSize(CVideoObjectDecoder *this, int a2, int a3)
{
  _DWORD *v3; // r10
  int v4; // r8d
  BOOL v5; // eax
  int v6; // ecx
  int v7; // edx
  int v8; // eax
  int v9; // r8d

  CVideoObjectDecoder::changeStepSizeQuick(this, a2, a3);
  v4 = v3[349];
  v5 = (v4 & 1) == 0;
  v6 = v4 - v5;
  v3[354] = v5;
  v3[356] = v4 - v5;
  v7 = 2 * v4;
  v3[355] = 2 * v4;
  v8 = 8;
  if ( v4 > 4 )
  {
    if ( v4 <= 8 )
    {
      v8 = (v4 + 13) >> 1;
      v9 = 2 * v4;
    }
    else if ( v4 > 24 )
    {
      v8 = v4 - 6;
      v9 = 2 * v4 - 16;
    }
    else
    {
      v8 = (v4 + 13) >> 1;
      v9 = v4 + 8;
    }
  }
  else
  {
    v9 = 8;
  }
  v3[350] = v9;
  v3[351] = v8;
  v3[352] = v6 + v7;
  v3[353] = -(v6 + v7);
}

```

## disassembly

```asm
0x180003838  sub     rsp, 28h
0x18000383c  mov     r10, rcx
0x18000383f  call    ?changeStepSizeQuick@CVideoObjectDecoder@@AEAAXJJ@Z; CVideoObjectDecoder::changeStepSizeQuick(long,long)
0x180003844  mov     r8d, [r10+574h]
0x18000384b  mov     eax, r8d
0x18000384e  not     eax
0x180003850  mov     ecx, r8d
0x180003853  and     eax, 1
0x180003856  sub     ecx, eax
0x180003858  mov     [r10+588h], eax
0x18000385f  mov     [r10+590h], ecx
0x180003866  lea     edx, [r8+r8]
0x18000386a  mov     [r10+58Ch], edx
0x180003871  mov     eax, 8
0x180003876  cmp     r8d, 4
0x18000387a  jg      short loc_1800038A5
0x18000387c  mov     r8d, eax
0x18000387f  mov     [r10+578h], r8d
0x180003886  mov     [r10+57Ch], eax
0x18000388d  lea     eax, [rcx+rdx]
0x180003890  mov     [r10+580h], eax
0x180003897  neg     eax
0x180003899  mov     [r10+584h], eax
0x1800038a0  add     rsp, 28h
0x1800038a4  retn
0x1800038a5  cmp     r8d, eax
0x1800038a8  jle     short loc_1800038BC
0x1800038aa  cmp     r8d, 18h
0x1800038ae  jg      short loc_1800038C7
0x1800038b0  lea     eax, [r8+0Dh]
0x1800038b4  sar     eax, 1
0x1800038b6  add     r8d, 8
0x1800038ba  jmp     short loc_18000387F
0x1800038bc  lea     eax, [r8+0Dh]
0x1800038c0  sar     eax, 1
0x1800038c2  add     r8d, r8d
0x1800038c5  jmp     short loc_18000387F
0x1800038c7  lea     eax, [r8-6]
0x1800038cb  lea     r8d, ds:0FFFFFFFFFFFFFFF0h[r8*2]
0x1800038d3  jmp     short loc_18000387F
```
