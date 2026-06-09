# BampEnumerateThrottledProcesses

- ea: `0x140013094`
- end: `0x14001321d`
- name: `BampEnumerateThrottledProcesses`
- size: `393`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c5b0`
- `0x14000f460`

## callees

- `0x140002710`
- `0x140013094`

## pseudocode

```c
PVOID __fastcall BampEnumerateThrottledProcesses(__int64 (__fastcall *a1)(_QWORD *, __int64), __int64 a2)
{
  PVOID result; // rax
  _QWORD *v5; // rbx
  _QWORD **v6; // rbx
  _QWORD **v7; // rdx
  __int64 v8; // [rsp+20h] [rbp-38h]

  if ( !P )
    goto LABEL_5;
  result = (PVOID)(*(_QWORD *)P & 0x8000000000000002uLL);
  if ( result == (PVOID)0x8000000000000002LL )
    result = 0;
  v5 = *(_QWORD **)P;
  if ( (*(_QWORD *)P & 1) == 0 )
  {
LABEL_10:
    while ( v5 )
    {
      result = (PVOID)a1(v5, a2);
      if ( !(_BYTE)result )
        break;
      v8 = v5[1] & (-1LL << (BYTE4(BampThrottledProcessTable) & 0x1F));
      result = (PVOID)(*v5 & 0x8000000000000002uLL);
      if ( result == (PVOID)0x8000000000000002LL )
        result = 0;
      v5 = (_QWORD *)*v5;
      if ( ((unsigned __int8)v5 & 1) != 0 )
      {
        v7 = (_QWORD **)((char *)P
                       + 8
                       * (((HIDWORD(BampThrottledProcessTable) >> 5) - 1)
                        & (HIBYTE(v8)
                         + 37
                         * (BYTE6(v8)
                          + 37
                          * (BYTE5(v8)
                           + 37
                           * (BYTE4(v8)
                            + 37
                            * (BYTE3(v8) + 37 * (BYTE2(v8) + 37 * (BYTE1(v8) + 37 * ((unsigned __int8)v8 + 11623883)))))))))
                       + 8);
        result = P;
        while ( v7 < (_QWORD **)((char *)P + 8 * ((unsigned __int64)HIDWORD(BampThrottledProcessTable) >> 5)) )
        {
          v5 = *v7;
          if ( ((unsigned __int8)*v7 & 1) == 0 )
            goto LABEL_10;
          ++v7;
        }
        return result;
      }
    }
  }
  else
  {
LABEL_5:
    v6 = (_QWORD **)((char *)P + 8);
    result = P;
    while ( v6 < (_QWORD **)((char *)P + 8 * ((unsigned __int64)HIDWORD(BampThrottledProcessTable) >> 5)) )
    {
      if ( (*(_BYTE *)v6 & 1) == 0 )
      {
        _mm_lfence();
        v5 = *v6;
        goto LABEL_10;
      }
      ++v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140013094  push    rbx
0x140013096  push    rbp
0x140013097  push    rsi
0x140013098  push    rdi
0x140013099  sub     rsp, 38h
0x14001309d  mov     r8, cs:P
0x1400130a4  mov     rdi, rdx
0x1400130a7  mov     rsi, rcx
0x1400130aa  mov     rbp, 8000000000000002h
0x1400130b4  test    r8, r8
0x1400130b7  jz      short loc_1400130D0
0x1400130b9  mov     rax, [r8]
0x1400130bc  and     rax, rbp
0x1400130bf  cmp     rax, rbp
0x1400130c2  jz      loc_14001320C
0x1400130c8  mov     rbx, [r8]
0x1400130cb  test    bl, 1
0x1400130ce  jz      short loc_1400130FF
0x1400130d0  mov     ecx, dword ptr cs:BampThrottledProcessTable+4
0x1400130d6  lea     rbx, [r8+8]
0x1400130da  mov     rax, cs:P
0x1400130e1  shr     rcx, 5
0x1400130e5  lea     rdx, [rax+rcx*8]
0x1400130e9  cmp     rbx, rdx
0x1400130ec  jnb     short loc_140013104
0x1400130ee  test    byte ptr [rbx], 1
0x1400130f1  jz      short loc_1400130F9
0x1400130f3  add     rbx, 8
0x1400130f7  jmp     short loc_1400130E9
0x1400130f9  lfence
0x1400130fc  mov     rbx, [rbx]
0x1400130ff  test    rbx, rbx
0x140013102  jnz     short loc_14001310E
0x140013104  add     rsp, 38h
0x140013108  pop     rdi
0x140013109  pop     rsi
0x14001310a  pop     rbp
0x14001310b  pop     rbx
0x14001310c  retn
0x14001310e  mov     rdx, rdi
0x140013111  mov     rcx, rbx
0x140013114  mov     rax, rsi
0x140013117  call    _guard_dispatch_icall
0x14001311c  test    al, al
0x14001311e  jz      short loc_140013104
0x140013120  test    rbx, rbx
0x140013123  jz      loc_1400131FB
0x140013129  mov     r8, cs:BampThrottledProcessTable+4
0x140013130  lea     r9, [rsp+58h+var_38]
0x140013135  or      rax, 0FFFFFFFFFFFFFFFFh
0x140013139  mov     ecx, r8d
0x14001313c  and     ecx, 1Fh
0x14001313f  shr     r8d, 5
0x140013143  shl     rax, cl
0x140013146  and     rax, [rbx+8]
0x14001314a  mov     [rsp+58h+var_38], rax
0x14001314f  movzx   eax, byte ptr [r9]
0x140013153  add     eax, 0B15DCBh
0x140013158  imul    ecx, eax, 25h ; '%'
0x14001315b  movzx   eax, byte ptr [r9+1]
0x140013160  add     ecx, eax
0x140013162  movzx   eax, byte ptr [r9+2]
0x140013167  imul    edx, ecx, 25h ; '%'
0x14001316a  add     edx, eax
0x14001316c  movzx   eax, byte ptr [r9+3]
0x140013171  imul    ecx, edx, 25h ; '%'
0x140013174  add     ecx, eax
0x140013176  movzx   eax, byte ptr [r9+4]
0x14001317b  imul    edx, ecx, 25h ; '%'
0x14001317e  add     edx, eax
0x140013180  movzx   eax, byte ptr [r9+5]
0x140013185  imul    ecx, edx, 25h ; '%'
0x140013188  add     ecx, eax
0x14001318a  movzx   eax, byte ptr [r9+6]
0x14001318f  imul    edx, ecx, 25h ; '%'
0x140013192  add     edx, eax
0x140013194  movzx   eax, byte ptr [r9+7]
0x140013199  imul    edx, 25h ; '%'
0x14001319c  add     edx, eax
0x14001319e  lea     eax, [r8-1]
0x1400131a2  mov     r8, cs:P
0x1400131a9  and     rdx, rax
0x1400131ac  lea     r8, [r8+rdx*8]
0x1400131b0  mov     rax, [rbx]
0x1400131b3  and     rax, rbp
0x1400131b6  cmp     rax, rbp
0x1400131b9  jz      short loc_140013216
0x1400131bb  mov     rbx, [rbx]
0x1400131be  test    bl, 1
0x1400131c1  jz      loc_1400130FF
0x1400131c7  mov     ecx, dword ptr cs:BampThrottledProcessTable+4
0x1400131cd  lea     rdx, [r8+8]
0x1400131d1  mov     rax, cs:P
0x1400131d8  shr     rcx, 5
0x1400131dc  lea     r8, [rax+rcx*8]
0x1400131e0  cmp     rdx, r8
0x1400131e3  jnb     loc_140013104
0x1400131e9  mov     rbx, [rdx]
0x1400131ec  test    bl, 1
0x1400131ef  jz      loc_1400130FF
0x1400131f5  add     rdx, 8
0x1400131f9  jmp     short loc_1400131E0
0x1400131fb  mov     r8, cs:P
0x140013202  mov     rbx, r8
0x140013205  test    r8, r8
0x140013208  jnz     short loc_1400131B0
0x14001320a  jmp     short loc_1400131C7
0x14001320c  xor     eax, eax
0x14001320e  mov     rcx, [rax]
0x140013211  jmp     loc_1400130C8
0x140013216  xor     eax, eax
0x140013218  mov     rcx, [rax]
0x14001321b  jmp     short loc_1400131BB
```
