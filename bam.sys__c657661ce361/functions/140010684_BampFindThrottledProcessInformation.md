# BampFindThrottledProcessInformation

- ea: `0x140010684`
- end: `0x14001074c`
- name: `BampFindThrottledProcessInformation`
- size: `200`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400105b0`
- `0x14001202c`
- `0x140012450`
- `0x140012eec`
- `0x140014648`
- `0x14001474c`
- `0x140014f90`

## callees

- `0x140010684`
- `0x140010880`

## pseudocode

```c
__int64 __fastcall BampFindThrottledProcessInformation(__int64 a1)
{
  _QWORD *v1; // r8
  __int64 v2; // r8
  __int64 v4; // [rsp+30h] [rbp+8h]

  if ( HIDWORD(BampThrottledProcessTable) >> 5 )
  {
    v4 = a1 & (-1LL << (BYTE4(BampThrottledProcessTable) & 0x1F));
    v1 = (char *)P
       + 8
       * (((HIDWORD(BampThrottledProcessTable) >> 5) - 1)
        & (HIBYTE(v4)
         + 37
         * (BYTE6(v4)
          + 37
          * (BYTE5(v4)
           + 37
           * (BYTE4(v4) + 37 * (BYTE3(v4) + 37 * (BYTE2(v4) + 37 * (BYTE1(v4) + 37 * ((unsigned __int8)v4 + 11623883)))))))));
    while ( 1 )
    {
      v1 = (_QWORD *)*v1;
      if ( ((unsigned __int8)v1 & 1) != 0 )
        break;
      if ( (a1 & (-1LL << (BYTE4(BampThrottledProcessTable) & 0x1F))) == ((-1LL << (BYTE4(BampThrottledProcessTable)
                                                                                  & 0x1F))
                                                                        & v1[1]) )
      {
        if ( !v1 )
          return 0;
        BampReferenceThrottledProcessInformation(v1);
        return v2;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140010684  sub     rsp, 28h
0x140010688  mov     rax, rcx
0x14001068b  mov     ecx, dword ptr cs:BampThrottledProcessTable+4
0x140010691  mov     r8d, ecx
0x140010694  shr     r8d, 5
0x140010698  test    r8d, r8d
0x14001069b  jz      loc_140010740
0x1400106a1  and     ecx, 1Fh
0x1400106a4  lea     r11, [rsp+28h+arg_0]
0x1400106a9  or      r9, 0FFFFFFFFFFFFFFFFh
0x1400106ad  shl     r9, cl
0x1400106b0  mov     r10, r9
0x1400106b3  and     r10, rax
0x1400106b6  mov     [rsp+28h+arg_0], r10
0x1400106bb  movzx   eax, byte ptr [r11]
0x1400106bf  add     eax, 0B15DCBh
0x1400106c4  imul    ecx, eax, 25h ; '%'
0x1400106c7  movzx   eax, byte ptr [r11+1]
0x1400106cc  add     ecx, eax
0x1400106ce  movzx   eax, byte ptr [r11+2]
0x1400106d3  imul    edx, ecx, 25h ; '%'
0x1400106d6  add     edx, eax
0x1400106d8  movzx   eax, byte ptr [r11+3]
0x1400106dd  imul    ecx, edx, 25h ; '%'
0x1400106e0  add     ecx, eax
0x1400106e2  movzx   eax, byte ptr [r11+4]
0x1400106e7  imul    edx, ecx, 25h ; '%'
0x1400106ea  add     edx, eax
0x1400106ec  movzx   eax, byte ptr [r11+5]
0x1400106f1  imul    ecx, edx, 25h ; '%'
0x1400106f4  add     ecx, eax
0x1400106f6  movzx   eax, byte ptr [r11+6]
0x1400106fb  imul    edx, ecx, 25h ; '%'
0x1400106fe  lea     ecx, [r8-1]
0x140010702  add     edx, eax
0x140010704  movzx   eax, byte ptr [r11+7]
0x140010709  imul    edx, 25h ; '%'
0x14001070c  add     edx, eax
0x14001070e  mov     rax, cs:P
0x140010715  and     rdx, rcx
0x140010718  lea     r8, [rax+rdx*8]
0x14001071c  mov     r8, [r8]
0x14001071f  test    r8b, 1
0x140010723  jnz     short loc_140010740
0x140010725  mov     rax, [r8+8]
0x140010729  and     rax, r9
0x14001072c  cmp     r10, rax
0x14001072f  jnz     short loc_14001071C
0x140010731  test    r8, r8
0x140010734  jz      short loc_140010740
0x140010736  mov     rcx, r8
0x140010739  call    BampReferenceThrottledProcessInformation
0x14001073e  jmp     short loc_140010743
0x140010740  xor     r8d, r8d
0x140010743  mov     rax, r8
0x140010746  add     rsp, 28h
0x14001074a  retn
```
