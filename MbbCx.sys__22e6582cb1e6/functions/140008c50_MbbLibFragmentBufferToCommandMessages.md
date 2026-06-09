# MbbLibFragmentBufferToCommandMessages

- ea: `0x140008c50`
- end: `0x140008e94`
- name: `MbbLibFragmentBufferToCommandMessages`
- size: `580`
- prototype: `__int64 __fastcall(__int64, int, __int64, unsigned int, _DWORD *, unsigned int, _DWORD *, unsigned int *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140020330`
- `0x140020988`

## callees

- `0x140008c50`
- `0x140048040`

## pseudocode

```c
__int64 __fastcall MbbLibFragmentBufferToCommandMessages(
        __int64 a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        _DWORD *a5,
        unsigned int a6,
        _DWORD *a7,
        unsigned int *a8,
        __int64 a9)
{
  int v10; // r15d
  __int64 v11; // r11
  unsigned int *v12; // r9
  __int64 v13; // r10
  __int64 v14; // r8
  unsigned int v15; // edi
  unsigned __int64 v16; // rbp
  unsigned int v18; // eax
  _DWORD *v19; // r14
  unsigned int v20; // r8d
  unsigned int v21; // ebx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // eax
  unsigned int v26; // r15d
  void *v27; // rcx
  unsigned int v28; // eax
  int v29; // [rsp+20h] [rbp-48h]
  unsigned int Size; // [rsp+24h] [rbp-44h]
  unsigned int Size_4; // [rsp+28h] [rbp-40h]

  v10 = a2;
  v11 = a1;
  if ( !a1 )
    return 3221225485LL;
  if ( !a7 )
    return 3221225485LL;
  v12 = a8;
  if ( !a8 || a4 && !a3 )
    return 3221225485LL;
  v13 = a9;
  if ( *a7 )
  {
    if ( !a9 )
      return 3221225485LL;
  }
  v14 = *a8;
  if ( (unsigned int)v14 < 0x30 )
    return 3221225485LL;
  v15 = a6;
  v16 = ((unsigned int)v14 + a4 + 7) / (unsigned __int64)(v14 - 20);
  if ( a6 >= (unsigned int)v16 || !a5 )
    return 3221225485LL;
  if ( !*a5 )
    *a5 = _InterlockedIncrement((volatile signed __int32 *)&WPP_MAIN_CB.Queue);
  if ( *a7 )
  {
    v18 = v14 - 48;
    v19 = 0;
    v20 = v14 - 20;
    Size = v18;
    Size_4 = v20;
    if ( a6 )
      v21 = v18 + v20 * (a6 - 1);
    else
      v21 = 0;
    v22 = 0;
    v29 = 0;
    if ( *a7 )
    {
      do
      {
        if ( a4 && v21 >= a4 )
          break;
        v19 = *(_DWORD **)(v13 + 8 * v22);
        v23 = (unsigned int)v22;
        *v19 = 3;
        v19[2] = *a5;
        v19[4] = (unsigned __int16)v15;
        v19[3] = (unsigned __int16)v16;
        v24 = *(_QWORD *)(v13 + 8LL * (unsigned int)v22);
        if ( v15 )
        {
          v27 = (void *)(v24 + 20);
          v26 = a4 - v21;
          if ( a4 - v21 >= v20 )
            v26 = v20;
          v28 = v26 + 20;
        }
        else
        {
          *(_DWORD *)(v24 + 20) = _byteswap_ulong(*(_DWORD *)v11);
          *(_WORD *)(v24 + 24) = __ROR2__(*(_WORD *)(v11 + 4), 8);
          *(_WORD *)(v24 + 26) = __ROR2__(*(_WORD *)(v11 + 6), 8);
          *(_QWORD *)(v24 + 28) = *(_QWORD *)(v11 + 8);
          v25 = *(_DWORD *)(v11 + 16);
          *(_DWORD *)(v24 + 40) = v10;
          *(_DWORD *)(v24 + 36) = v25;
          v26 = a4 - v21;
          *(_DWORD *)(v24 + 44) = a4;
          v27 = (void *)(*(_QWORD *)(v13 + 8 * v23) + 48LL);
          if ( a4 - v21 >= Size )
            v26 = Size;
          v28 = v26 + 48;
        }
        v19[1] = v28;
        memmove(v27, (const void *)(a3 + v21), v26);
        v21 += v26;
        v13 = a9;
        v22 = (unsigned int)(v29 + 1);
        v11 = a1;
        ++v15;
        v20 = Size_4;
        v10 = a2;
        v29 = v22;
      }
      while ( (unsigned int)v22 < *a7 );
      v12 = a8;
    }
    *a7 = v22;
    if ( v19 )
      *v12 = v19[1];
    return v15 < (unsigned int)v16 ? 0xC0000016 : 0;
  }
  else
  {
    *a7 = v16 - a6;
    return 0;
  }
}

```

## disassembly

```asm
0x140008c50  mov     rax, rsp
0x140008c53  mov     [rax+20h], rbx
0x140008c57  mov     [rax+18h], r8
0x140008c5b  mov     [rax+10h], edx
0x140008c5e  mov     [rax+8], rcx
0x140008c62  push    rbp
0x140008c63  push    rsi
0x140008c64  push    rdi
0x140008c65  push    r12
0x140008c67  push    r13
0x140008c69  push    r14
0x140008c6b  push    r15
0x140008c6d  sub     rsp, 30h
0x140008c71  mov     r12d, r9d
0x140008c74  mov     rax, r8
0x140008c77  mov     r15d, edx
0x140008c7a  mov     r11, rcx
0x140008c7d  test    rcx, rcx
0x140008c80  jz      loc_140008E76
0x140008c86  mov     rsi, [rsp+68h+arg_30]
0x140008c8e  test    rsi, rsi
0x140008c91  jz      loc_140008E76
0x140008c97  mov     r9, [rsp+68h+arg_38]
0x140008c9f  test    r9, r9
0x140008ca2  jz      loc_140008E76
0x140008ca8  test    r12d, r12d
0x140008cab  jz      short loc_140008CB6
0x140008cad  test    rax, rax
0x140008cb0  jz      loc_140008E76
0x140008cb6  cmp     dword ptr [rsi], 0
0x140008cb9  mov     r10, [rsp+68h+arg_40]
0x140008cc1  jz      short loc_140008CCC
0x140008cc3  test    r10, r10
0x140008cc6  jz      loc_140008E76
0x140008ccc  mov     r8d, [r9]
0x140008ccf  cmp     r8d, 30h ; '0'
0x140008cd3  jb      loc_140008E76
0x140008cd9  mov     edi, [rsp+68h+arg_28]
0x140008ce0  lea     eax, [r12+7]
0x140008ce5  add     eax, r8d
0x140008ce8  lea     rcx, [r8-14h]
0x140008cec  xor     edx, edx
0x140008cee  div     rcx
0x140008cf1  mov     rbp, rax
0x140008cf4  cmp     edi, eax
0x140008cf6  jnb     loc_140008E76
0x140008cfc  mov     r13, [rsp+68h+arg_20]
0x140008d04  test    r13, r13
0x140008d07  jz      loc_140008E76
0x140008d0d  cmp     dword ptr [r13+0], 0
0x140008d12  jnz     short loc_140008D27
0x140008d14  mov     eax, 1
0x140008d19  lock xadd dword ptr cs:WPP_MAIN_CB.Queue, eax
0x140008d21  inc     eax
0x140008d23  mov     [r13+0], eax
0x140008d27  mov     ecx, [rsi]
0x140008d29  test    ecx, ecx
0x140008d2b  jnz     short loc_140008D38
0x140008d2d  sub     ebp, edi
0x140008d2f  mov     [rsi], ebp
0x140008d31  xor     eax, eax
0x140008d33  jmp     loc_140008E7B
0x140008d38  lea     eax, [r8-30h]
0x140008d3c  xor     r14d, r14d
0x140008d3f  add     r8d, 0FFFFFFECh
0x140008d43  mov     dword ptr [rsp+68h+Size], eax
0x140008d47  mov     dword ptr [rsp+68h+Size+4], r8d
0x140008d4c  test    edi, edi
0x140008d4e  jz      short loc_140008D5B
0x140008d50  lea     ebx, [rdi-1]
0x140008d53  imul    ebx, r8d
0x140008d57  add     ebx, eax
0x140008d59  jmp     short loc_140008D5D
0x140008d5b  xor     ebx, ebx
0x140008d5d  xor     eax, eax
0x140008d5f  mov     [rsp+68h+var_48], eax
0x140008d63  test    ecx, ecx
0x140008d65  jz      loc_140008E5D
0x140008d6b  test    r12d, r12d
0x140008d6e  jz      short loc_140008D79
0x140008d70  cmp     ebx, r12d
0x140008d73  jnb     loc_140008E55
0x140008d79  mov     r14, [r10+rax*8]
0x140008d7d  mov     edx, eax
0x140008d7f  mov     dword ptr [r14], 3
0x140008d86  mov     eax, [r13+0]
0x140008d8a  mov     [r14+8], eax
0x140008d8e  movzx   eax, di
0x140008d91  mov     [r14+10h], eax
0x140008d95  movzx   eax, bp
0x140008d98  mov     [r14+0Ch], eax
0x140008d9c  mov     rcx, [r10+rdx*8]
0x140008da0  test    edi, edi
0x140008da2  jnz     short loc_140008DFC
0x140008da4  mov     eax, [r11]
0x140008da7  bswap   eax
0x140008da9  mov     [rcx+14h], eax
0x140008dac  movzx   eax, word ptr [r11+4]
0x140008db1  ror     ax, 8
0x140008db5  mov     [rcx+18h], ax
0x140008db9  movzx   eax, word ptr [r11+6]
0x140008dbe  ror     ax, 8
0x140008dc2  mov     [rcx+1Ah], ax
0x140008dc6  mov     rax, [r11+8]
0x140008dca  mov     [rcx+1Ch], rax
0x140008dce  mov     eax, [r11+10h]
0x140008dd2  mov     [rcx+28h], r15d
0x140008dd6  mov     r15d, r12d
0x140008dd9  mov     [rcx+24h], eax
0x140008ddc  sub     r15d, ebx
0x140008ddf  mov     [rcx+2Ch], r12d
0x140008de3  mov     rcx, [r10+rdx*8]
0x140008de7  add     rcx, 30h ; '0'
0x140008deb  cmp     r15d, dword ptr [rsp+68h+Size]
0x140008df0  cmovnb  r15d, dword ptr [rsp+68h+Size]
0x140008df6  lea     eax, [r15+30h]
0x140008dfa  jmp     short loc_140008E11
0x140008dfc  mov     r15d, r12d
0x140008dff  add     rcx, 14h; void *
0x140008e03  sub     r15d, ebx
0x140008e06  cmp     r15d, r8d
0x140008e09  cmovnb  r15d, r8d
0x140008e0d  lea     eax, [r15+14h]
0x140008e11  mov     [r14+4], eax
0x140008e15  mov     edx, ebx
0x140008e17  add     rdx, [rsp+68h+arg_10]; Src
0x140008e1f  mov     r8d, r15d; Size
0x140008e22  call    memmove
0x140008e27  mov     eax, [rsp+68h+var_48]
0x140008e2b  add     ebx, r15d
0x140008e2e  mov     r10, [rsp+68h+arg_40]
0x140008e36  inc     eax
0x140008e38  mov     r11, [rsp+68h+arg_0]
0x140008e3d  inc     edi
0x140008e3f  mov     r8d, dword ptr [rsp+68h+Size+4]
0x140008e44  mov     r15d, [rsp+68h+arg_8]
0x140008e49  mov     [rsp+68h+var_48], eax
0x140008e4d  cmp     eax, [rsi]
0x140008e4f  jb      loc_140008D6B
0x140008e55  mov     r9, [rsp+68h+arg_38]
0x140008e5d  mov     [rsi], eax
0x140008e5f  test    r14, r14
0x140008e62  jz      short loc_140008E6B
0x140008e64  mov     eax, [r14+4]
0x140008e68  mov     [r9], eax
0x140008e6b  cmp     edi, ebp
0x140008e6d  sbb     eax, eax
0x140008e6f  and     eax, 0C0000016h
0x140008e74  jmp     short loc_140008E7B
0x140008e76  mov     eax, 0C000000Dh
0x140008e7b  mov     rbx, [rsp+68h+arg_18]
0x140008e83  add     rsp, 30h
0x140008e87  pop     r15
0x140008e89  pop     r14
0x140008e8b  pop     r13
0x140008e8d  pop     r12
0x140008e8f  pop     rdi
0x140008e90  pop     rsi
0x140008e91  pop     rbp
0x140008e92  retn
```
