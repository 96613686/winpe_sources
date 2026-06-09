# av_read_frame

- ea: `0x180006060`
- end: `0x1800062d7`
- name: `av_read_frame`
- size: `631`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001ae48`

## callees

- `0x180006060`
- `0x18000a920`
- `0x180019b90`
- `0x18001aa74`
- `0x18001b9f6`
- `0x18001bae0`
- `0x18001bae6`
- `0x18001bc78`

## pseudocode

```c
__int64 __fastcall av_read_frame(__int64 a1, __int64 a2)
{
  int v2; // r12d
  __int64 **v3; // r15
  __int64 v4; // rbx
  int v6; // eax
  int v7; // edi
  __int64 *v8; // rdi
  __int64 *v9; // rbp
  __int64 v10; // r14
  _QWORD *v11; // r15
  int v12; // ebx
  __int64 result; // rax
  __int64 v14; // rbp
  __int64 v15; // rax
  __int64 v16; // rax

  v2 = 0;
  v3 = (__int64 **)(a1 + 480);
  v4 = a2;
  if ( (*(_BYTE *)(a1 + 128) & 1) != 0 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v8 = *v3;
        v9 = *v3;
        if ( *v3 )
        {
          v10 = v8[3];
          if ( v10 != 0x8000000000000000uLL )
          {
            v11 = v8 + 2;
            v12 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL * *((int *)v8 + 11)) + 212LL);
            do
            {
              if ( *v11 != 0x8000000000000000uLL )
                break;
              if ( *((_DWORD *)v8 + 11) == *((_DWORD *)v9 + 11)
                && av_compare_mod(v9[3], v8[3], 2LL << ((unsigned __int8)v12 - 1)) < 0 )
              {
                _mm_lfence();
                if ( av_compare_mod(v8[2], v8[3], 2LL << ((unsigned __int8)v12 - 1)) )
                  *v11 = v8[3];
                if ( v10 != 0x8000000000000000uLL )
                  v10 = v8[3];
              }
              v8 = (__int64 *)*v8;
            }
            while ( v8 );
            v4 = a2;
            v3 = (__int64 **)(a1 + 480);
            if ( v2 && v9[2] == 0x8000000000000000uLL && v10 != 0x8000000000000000uLL )
              v9[2] = v10 + v9[9];
            v8 = *v3;
          }
          if ( v9[2] != 0x8000000000000000uLL
            || *(int *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL * *((int *)v9 + 11)) + 68LL) >= 48
            || v9[3] == 0x8000000000000000uLL
            || v2 )
          {
            v7 = avpriv_packet_list_get(a1 + 480, v4);
            goto LABEL_35;
          }
        }
        result = sub_18000A920(a1, v4);
        if ( (int)result < 0 )
          break;
        _mm_lfence();
        v7 = avpriv_packet_list_put(v3, v4, 0, 0);
        if ( v7 < 0 )
        {
          _mm_lfence();
          av_packet_unref(v4);
          return (unsigned int)v7;
        }
      }
      if ( !v8 || (_DWORD)result == -11 )
        break;
      v2 = 1;
    }
    _mm_lfence();
  }
  else
  {
    if ( *v3 )
      v6 = avpriv_packet_list_get(a1 + 480, a2);
    else
      v6 = sub_18000A920(a1, a2);
    v7 = v6;
    if ( v6 >= 0 )
    {
LABEL_35:
      v14 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL * *(int *)(v4 + 36));
      if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 16LL) & 0x100) != 0 && (*(_BYTE *)(v4 + 40) & 1) != 0 )
      {
        sub_18001AA74(a1, *(unsigned int *)(v14 + 8));
        av_add_index_entry(v14, *(_QWORD *)(v4 + 72), *(_QWORD *)(v4 + 16), 0, 0, 1);
      }
      v15 = *(_QWORD *)(v4 + 16);
      if ( v15 > 0x7FFDFFFFFFFFFFFFLL )
        *(_QWORD *)(v4 + 16) = v15 - 0x7FFEFFFFFFFFFFFFLL;
      v16 = *(_QWORD *)(v4 + 8);
      if ( v16 > 0x7FFDFFFFFFFFFFFFLL )
        *(_QWORD *)(v4 + 8) = v16 - 0x7FFEFFFFFFFFFFFFLL;
    }
    else
    {
      _mm_lfence();
    }
    return (unsigned int)v7;
  }
  return result;
}

```

## disassembly

```asm
0x180006060  mov     rax, rsp
0x180006063  mov     [rax+8], rbx
0x180006067  mov     [rax+18h], rbp
0x18000606b  mov     [rax+20h], rsi
0x18000606f  mov     [rax+10h], rdx
0x180006073  push    rdi
0x180006074  push    r12
0x180006076  push    r13
0x180006078  push    r14
0x18000607a  push    r15
0x18000607c  sub     rsp, 30h
0x180006080  xor     r12d, r12d
0x180006083  lea     r15, [rcx+1E0h]
0x18000608a  test    byte ptr [rcx+80h], 1
0x180006091  mov     rbx, rdx
0x180006094  mov     rsi, rcx
0x180006097  jnz     short loc_1800060BF
0x180006099  cmp     [r15], r12
0x18000609c  jz      short loc_1800060A8
0x18000609e  mov     rcx, r15
0x1800060a1  call    avpriv_packet_list_get
0x1800060a6  jmp     short loc_1800060AD
0x1800060a8  call    sub_18000A920
0x1800060ad  mov     edi, eax
0x1800060af  test    eax, eax
0x1800060b1  jns     loc_180006245
0x1800060b7  lfence
0x1800060ba  jmp     loc_180006215
0x1800060bf  mov     rdi, [r15]
0x1800060c2  mov     rdx, 8000000000000000h
0x1800060cc  mov     rbp, rdi
0x1800060cf  test    rdi, rdi
0x1800060d2  jz      loc_1800061C0
0x1800060d8  mov     r14, [rdi+18h]
0x1800060dc  cmp     r14, rdx
0x1800060df  jz      loc_180006199
0x1800060e5  movsxd  rcx, dword ptr [rdi+2Ch]
0x1800060e9  lea     r15, [rdi+10h]
0x1800060ed  mov     rax, [rsi+30h]
0x1800060f1  mov     rcx, [rax+rcx*8]
0x1800060f5  mov     ebx, [rcx+0D4h]
0x1800060fb  cmp     [r15], rdx
0x1800060fe  jnz     short loc_18000616F
0x180006100  mov     eax, [rbp+2Ch]
0x180006103  cmp     [rdi+2Ch], eax
0x180006106  jnz     short loc_180006167
0x180006108  mov     rdx, [rdi+18h]
0x18000610c  lea     ecx, [rbx-1]
0x18000610f  mov     r13d, 2
0x180006115  shl     r13, cl
0x180006118  mov     rcx, [rbp+18h]
0x18000611c  mov     r8, r13
0x18000611f  call    av_compare_mod
0x180006124  test    rax, rax
0x180006127  jns     short loc_18000615D
0x180006129  lfence
0x18000612c  mov     rdx, [rdi+18h]
0x180006130  mov     r8, r13
0x180006133  mov     rcx, [rdi+10h]
0x180006137  call    av_compare_mod
0x18000613c  test    rax, rax
0x18000613f  jz      short loc_180006148
0x180006141  mov     rax, [rdi+18h]
0x180006145  mov     [r15], rax
0x180006148  mov     rdx, 8000000000000000h
0x180006152  cmp     r14, rdx
0x180006155  jz      short loc_180006167
0x180006157  mov     r14, [rdi+18h]
0x18000615b  jmp     short loc_180006167
0x18000615d  mov     rdx, 8000000000000000h
0x180006167  mov     rdi, [rdi]
0x18000616a  test    rdi, rdi
0x18000616d  jnz     short loc_1800060FB
0x18000616f  mov     rbx, [rsp+58h+arg_8]
0x180006174  lea     r15, [rsi+1E0h]
0x18000617b  test    r12d, r12d
0x18000617e  jz      short loc_180006196
0x180006180  cmp     [rbp+10h], rdx
0x180006184  jnz     short loc_180006196
0x180006186  cmp     r14, rdx
0x180006189  jz      short loc_180006196
0x18000618b  mov     rcx, [rbp+48h]
0x18000618f  add     rcx, r14
0x180006192  mov     [rbp+10h], rcx
0x180006196  mov     rdi, [r15]
0x180006199  cmp     [rbp+10h], rdx
0x18000619d  jnz     loc_180006234
0x1800061a3  movsxd  rcx, dword ptr [rbp+2Ch]
0x1800061a7  mov     rax, [rsi+30h]
0x1800061ab  mov     rcx, [rax+rcx*8]
0x1800061af  cmp     dword ptr [rcx+44h], 30h ; '0'
0x1800061b3  jge     short loc_180006234
0x1800061b5  cmp     [rbp+18h], rdx
0x1800061b9  jz      short loc_180006234
0x1800061bb  test    r12d, r12d
0x1800061be  jnz     short loc_180006234
0x1800061c0  mov     rdx, rbx
0x1800061c3  mov     rcx, rsi
0x1800061c6  call    sub_18000A920
0x1800061cb  test    eax, eax
0x1800061cd  jns     short loc_1800061EC
0x1800061cf  test    rdi, rdi
0x1800061d2  jz      loc_1800062CF
0x1800061d8  cmp     eax, 0FFFFFFF5h
0x1800061db  jz      loc_1800062CF
0x1800061e1  mov     r12d, 1
0x1800061e7  jmp     loc_1800060BF
0x1800061ec  lfence
0x1800061ef  xor     r9d, r9d
0x1800061f2  xor     r8d, r8d
0x1800061f5  mov     rdx, rbx
0x1800061f8  mov     rcx, r15
0x1800061fb  call    avpriv_packet_list_put
0x180006200  mov     edi, eax
0x180006202  test    eax, eax
0x180006204  jns     loc_1800060BF
0x18000620a  lfence
0x18000620d  mov     rcx, rbx
0x180006210  call    av_packet_unref
0x180006215  mov     eax, edi
0x180006217  mov     rbx, [rsp+58h+arg_0]
0x18000621c  mov     rbp, [rsp+58h+arg_10]
0x180006221  mov     rsi, [rsp+58h+arg_18]
0x180006226  add     rsp, 30h
0x18000622a  pop     r15
0x18000622c  pop     r14
0x18000622e  pop     r13
0x180006230  pop     r12
0x180006232  pop     rdi
0x180006233  retn
0x180006234  lea     rcx, [rsi+1E0h]
0x18000623b  mov     rdx, rbx
0x18000623e  call    avpriv_packet_list_get
0x180006243  mov     edi, eax
0x180006245  mov     rax, [rsi+30h]
0x180006249  movsxd  rcx, dword ptr [rbx+24h]
0x18000624d  mov     rbp, [rax+rcx*8]
0x180006251  mov     rax, [rsi+8]
0x180006255  test    dword ptr [rax+10h], 100h
0x18000625c  jz      short loc_180006292
0x18000625e  test    byte ptr [rbx+28h], 1
0x180006262  jz      short loc_180006292
0x180006264  mov     edx, [rbp+8]
0x180006267  mov     rcx, rsi
0x18000626a  call    sub_18001AA74
0x18000626f  mov     r8, [rbx+10h]
0x180006273  xor     r9d, r9d
0x180006276  mov     rdx, [rbx+48h]
0x18000627a  mov     rcx, rbp
0x18000627d  mov     [rsp+58h+var_30], 1
0x180006285  mov     [rsp+58h+var_38], 0
0x18000628d  call    av_add_index_entry
0x180006292  mov     rax, [rbx+10h]
0x180006296  mov     rdx, 7FFDFFFFFFFFFFFFh
0x1800062a0  mov     rcx, 8001000000000001h
0x1800062aa  cmp     rax, rdx
0x1800062ad  jle     short loc_1800062B6
0x1800062af  add     rax, rcx
0x1800062b2  mov     [rbx+10h], rax
0x1800062b6  mov     rax, [rbx+8]
0x1800062ba  cmp     rax, rdx
0x1800062bd  jle     loc_180006215
0x1800062c3  add     rax, rcx
0x1800062c6  mov     [rbx+8], rax
0x1800062ca  jmp     loc_180006215
0x1800062cf  lfence
0x1800062d2  jmp     loc_180006217
```
