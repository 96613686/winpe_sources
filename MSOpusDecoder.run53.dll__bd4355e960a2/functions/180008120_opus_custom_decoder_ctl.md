# opus_custom_decoder_ctl

- ea: `0x180008120`
- end: `0x1800083f0`
- name: `opus_custom_decoder_ctl`
- size: `720`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800022f0`
- `0x180003620`
- `0x180003840`
- `0x180007330`

## callees

- `0x18000227c`
- `0x180008120`

## pseudocode

```c
__int64 __fastcall opus_custom_decoder_ctl(_DWORD *a1, int a2, _QWORD *a3)
{
  __int64 result; // rax
  int v5; // r11d
  int v6; // r9d
  __int64 v7; // rdx
  _DWORD *v8; // rdi
  _DWORD *v9; // rsi
  int i; // edx
  __int64 v11; // rax
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx

  if ( a2 > 4046 )
  {
    if ( a2 > 10007 )
    {
      v12 = a2 - 10008;
      if ( !v12 )
      {
        if ( (unsigned int)((_DWORD)a3 - 1) <= 1 )
        {
          a1[4] = (_DWORD)a3;
          return 0;
        }
        return 0xFFFFFFFFLL;
      }
      v13 = v12 - 2;
      if ( !v13 )
      {
        if ( (int)a3 >= 0 && (int)a3 < *(_DWORD *)(*(_QWORD *)a1 + 8LL) )
        {
          a1[6] = (_DWORD)a3;
          return 0;
        }
        return 0xFFFFFFFFLL;
      }
      v14 = v13 - 2;
      if ( !v14 )
      {
        if ( (int)a3 >= 1 && (int)a3 <= *(_DWORD *)(*(_QWORD *)a1 + 8LL) )
        {
          a1[7] = (_DWORD)a3;
          return 0;
        }
        return 0xFFFFFFFFLL;
      }
      v15 = v14 - 3;
      if ( !v15 )
      {
        if ( a3 )
        {
          *a3 = *(_QWORD *)a1;
          return 0;
        }
        return 0xFFFFFFFFLL;
      }
      if ( v15 == 1 )
      {
        a1[8] = (_DWORD)a3;
        return 0;
      }
    }
    else
    {
      if ( a2 == 10007 )
      {
        if ( a3 )
        {
          *(_DWORD *)a3 = a1[13];
          result = 0;
          a1[13] = 0;
          return result;
        }
        return 0xFFFFFFFFLL;
      }
      if ( a2 == 4047 )
      {
        if ( a3 )
        {
          *(_DWORD *)a3 = a1[9];
          return 0;
        }
        return 0xFFFFFFFFLL;
      }
    }
    return 4294967291LL;
  }
  if ( a2 == 4046 )
  {
    if ( (unsigned int)a3 <= 1 )
    {
      a1[9] = (_DWORD)a3;
      return 0;
    }
    return 0xFFFFFFFFLL;
  }
  switch ( a2 )
  {
    case 4010:
      if ( (unsigned int)a3 > 0xA )
        return 0xFFFFFFFFLL;
      a1[10] = (_DWORD)a3;
      result = 0;
      break;
    case 4011:
      if ( !a3 )
        return 0xFFFFFFFFLL;
      *(_DWORD *)a3 = a1[10];
      result = 0;
      break;
    case 4027:
      if ( !a3 )
        return 0xFFFFFFFFLL;
      *(_DWORD *)a3 = a1[2] / a1[5];
      result = 0;
      break;
    case 4028:
      v5 = a1[3];
      v6 = *(_DWORD *)(*(_QWORD *)a1 + 8LL);
      v7 = 2 * v6;
      v8 = &a1[24 * v5 + 26 + v7 + v5 * (a1[2] + 2048)];
      v9 = &v8[v7];
      memset_0(a1 + 12, 0, 4 * (24 * v5 + v5 * (*(_DWORD *)(*(_QWORD *)a1 + 4LL) + 2048) + 8 * v6) + 108 - 48LL);
      for ( i = 0; i < 2 * *(_DWORD *)(*(_QWORD *)a1 + 8LL); v8[v11] = -1042284544 )
      {
        v11 = i++;
        v9[v11] = -1042284544;
      }
      result = 0;
      a1[16] = 1;
      break;
    case 4031:
      if ( !a3 )
        return 0xFFFFFFFFLL;
      *(_DWORD *)a3 = a1[12];
      result = 0;
      break;
    case 4033:
      if ( !a3 )
        return 0xFFFFFFFFLL;
      *(_DWORD *)a3 = a1[17];
      result = 0;
      break;
    default:
      return 4294967291LL;
  }
  return result;
}

```

## disassembly

```asm
0x180008120  mov     [rsp+arg_8], edx
0x180008124  mov     [rsp+arg_10], r8
0x180008129  mov     [rsp+arg_18], r9
0x18000812e  push    rbx
0x18000812f  sub     rsp, 30h
0x180008133  lea     r8, [rsp+38h+arg_10]
0x180008138  mov     rbx, rcx
0x18000813b  cmp     edx, 0FCEh
0x180008141  jg      loc_1800082D1
0x180008147  jz      loc_1800082BA
0x18000814d  add     edx, 0FFFFF056h; switch 24 cases
0x180008153  cmp     edx, 17h
0x180008156  ja      def_180008178; jumptable 0000000180008178 default case, cases 4012-4026,4029,4030,4032
0x18000815c  movsxd  rax, edx
0x18000815f  lea     rdx, __ImageBase
0x180008166  movzx   eax, ds:(byte_1800083D8 - 180000000h)[rdx+rax]
0x18000816e  mov     ecx, ds:(jpt_180008178 - 180000000h)[rdx+rax*4]
0x180008175  add     rcx, rdx
0x180008178  jmp     rcx; switch jump
0x18000817a  mov     eax, [r8]; jumptable 0000000180008178 case 4010
0x18000817d  cmp     eax, 0Ah
0x180008180  ja      loc_1800083B0
0x180008186  mov     [rbx+28h], eax
0x180008189  xor     eax, eax
0x18000818b  add     rsp, 30h
0x18000818f  pop     rbx
0x180008190  retn
0x180008191  mov     rcx, [r8]; jumptable 0000000180008178 case 4011
0x180008194  test    rcx, rcx
0x180008197  jz      loc_1800083B0
0x18000819d  mov     eax, [rbx+28h]
0x1800081a0  mov     [rcx], eax
0x1800081a2  xor     eax, eax
0x1800081a4  add     rsp, 30h
0x1800081a8  pop     rbx
0x1800081a9  retn
0x1800081aa  mov     rcx, [r8]; jumptable 0000000180008178 case 4027
0x1800081ad  test    rcx, rcx
0x1800081b0  jz      loc_1800083B0
0x1800081b6  mov     eax, [rbx+8]
0x1800081b9  cdq
0x1800081ba  idiv    dword ptr [rbx+14h]
0x1800081bd  mov     [rcx], eax
0x1800081bf  xor     eax, eax
0x1800081c1  add     rsp, 30h
0x1800081c5  pop     rbx
0x1800081c6  retn
0x1800081c7  mov     r8, [rbx]; jumptable 0000000180008178 case 4028
0x1800081ca  mov     r11d, [rbx+0Ch]
0x1800081ce  mov     [rsp+38h+var_10], rsi
0x1800081d3  mov     [rsp+38h+var_18], rdi
0x1800081d8  mov     r9d, [r8+8]
0x1800081dc  lea     eax, [r11+r11*2]
0x1800081e0  lea     r10d, ds:0[rax*8]
0x1800081e8  movsxd  rdi, r10d
0x1800081eb  lea     eax, [r9+r9]
0x1800081ef  add     rdi, 1Ah
0x1800081f3  movsxd  rdx, eax
0x1800081f6  mov     eax, [rbx+8]
0x1800081f9  add     eax, 800h
0x1800081fe  imul    eax, r11d
0x180008202  cdqe
0x180008204  add     rax, rdx
0x180008207  add     rdi, rax
0x18000820a  mov     eax, [r8+4]
0x18000820e  add     eax, 800h
0x180008213  imul    eax, r11d
0x180008217  lea     rdi, [rbx+rdi*4]
0x18000821b  lea     rsi, [rdi+rdx*4]
0x18000821f  xor     edx, edx; Val
0x180008221  add     eax, r10d
0x180008224  lea     ecx, [rax+r9*8]
0x180008228  lea     ecx, ds:6Ch[rcx*4]
0x18000822f  movsxd  r8, ecx
0x180008232  lea     rcx, [rbx+30h]; void *
0x180008236  sub     r8, 30h ; '0'; Size
0x18000823a  call    memset_0
0x18000823f  mov     rax, [rbx]
0x180008242  xor     edx, edx
0x180008244  mov     ecx, [rax+8]
0x180008247  add     ecx, ecx
0x180008249  test    ecx, ecx
0x18000824b  jle     short loc_18000826F
0x18000824d  nop     dword ptr [rax]
0x180008250  movsxd  rax, edx
0x180008253  inc     edx
0x180008255  mov     dword ptr [rsi+rax*4], 0C1E00000h
0x18000825c  mov     dword ptr [rdi+rax*4], 0C1E00000h
0x180008263  mov     rax, [rbx]
0x180008266  mov     ecx, [rax+8]
0x180008269  add     ecx, ecx
0x18000826b  cmp     edx, ecx
0x18000826d  jl      short loc_180008250
0x18000826f  mov     rdi, [rsp+38h+var_18]
0x180008274  xor     eax, eax
0x180008276  mov     rsi, [rsp+38h+var_10]
0x18000827b  mov     dword ptr [rbx+40h], 1
0x180008282  add     rsp, 30h
0x180008286  pop     rbx
0x180008287  retn
0x180008288  mov     rcx, [r8]; jumptable 0000000180008178 case 4033
0x18000828b  test    rcx, rcx
0x18000828e  jz      loc_1800083B0
0x180008294  mov     eax, [rbx+44h]
0x180008297  mov     [rcx], eax
0x180008299  xor     eax, eax
0x18000829b  add     rsp, 30h
0x18000829f  pop     rbx
0x1800082a0  retn
0x1800082a1  mov     rcx, [r8]; jumptable 0000000180008178 case 4031
0x1800082a4  test    rcx, rcx
0x1800082a7  jz      loc_1800083B0
0x1800082ad  mov     eax, [rbx+30h]
0x1800082b0  mov     [rcx], eax
0x1800082b2  xor     eax, eax
0x1800082b4  add     rsp, 30h
0x1800082b8  pop     rbx
0x1800082b9  retn
0x1800082ba  mov     eax, [r8]
0x1800082bd  cmp     eax, 1
0x1800082c0  ja      loc_1800083B0
0x1800082c6  mov     [rcx+24h], eax
0x1800082c9  xor     eax, eax
0x1800082cb  add     rsp, 30h
0x1800082cf  pop     rbx
0x1800082d0  retn
0x1800082d1  cmp     edx, 2717h
0x1800082d7  jg      short loc_18000831A
0x1800082d9  jz      short loc_1800082FC
0x1800082db  cmp     edx, 0FCFh
0x1800082e1  jnz     short def_180008178; jumptable 0000000180008178 default case, cases 4012-4026,4029,4030,4032
0x1800082e3  mov     rcx, [r8]
0x1800082e6  test    rcx, rcx
0x1800082e9  jz      loc_1800083B0
0x1800082ef  mov     eax, [rbx+24h]
0x1800082f2  mov     [rcx], eax
0x1800082f4  xor     eax, eax
0x1800082f6  add     rsp, 30h
0x1800082fa  pop     rbx
0x1800082fb  retn
0x1800082fc  mov     rcx, [r8]
0x1800082ff  test    rcx, rcx
0x180008302  jz      loc_1800083B0
0x180008308  mov     eax, [rbx+34h]
0x18000830b  xor     edx, edx
0x18000830d  mov     [rcx], eax
0x18000830f  xor     eax, eax
0x180008311  mov     [rbx+34h], edx
0x180008314  add     rsp, 30h
0x180008318  pop     rbx
0x180008319  retn
0x18000831a  sub     edx, 2718h
0x180008320  jz      short loc_18000839A
0x180008322  sub     edx, 2
0x180008325  jz      short loc_180008380
0x180008327  sub     edx, 2
0x18000832a  jz      short loc_180008365
0x18000832c  sub     edx, 3
0x18000832f  jz      short loc_18000834F
0x180008331  cmp     edx, 1
0x180008334  jz      short loc_180008341
0x180008336  mov     eax, 0FFFFFFFBh; jumptable 0000000180008178 default case, cases 4012-4026,4029,4030,4032
0x18000833b  add     rsp, 30h
0x18000833f  pop     rbx
0x180008340  retn
0x180008341  mov     eax, [r8]
0x180008344  mov     [rcx+20h], eax
0x180008347  xor     eax, eax
0x180008349  add     rsp, 30h
0x18000834d  pop     rbx
0x18000834e  retn
0x18000834f  mov     rcx, [r8]
0x180008352  test    rcx, rcx
0x180008355  jz      short loc_1800083B0
0x180008357  mov     rax, [rbx]
0x18000835a  mov     [rcx], rax
0x18000835d  xor     eax, eax
0x18000835f  add     rsp, 30h
0x180008363  pop     rbx
0x180008364  retn
0x180008365  mov     ecx, [r8]
0x180008368  cmp     ecx, 1
0x18000836b  jl      short loc_1800083B0
0x18000836d  mov     rax, [rbx]
0x180008370  cmp     ecx, [rax+8]
0x180008373  jg      short loc_1800083B0
0x180008375  mov     [rbx+1Ch], ecx
0x180008378  xor     eax, eax
0x18000837a  add     rsp, 30h
0x18000837e  pop     rbx
0x18000837f  retn
0x180008380  mov     ecx, [r8]
0x180008383  test    ecx, ecx
0x180008385  js      short loc_1800083B0
0x180008387  mov     rax, [rbx]
0x18000838a  cmp     ecx, [rax+8]
0x18000838d  jge     short loc_1800083B0
0x18000838f  mov     [rbx+18h], ecx
0x180008392  xor     eax, eax
0x180008394  add     rsp, 30h
0x180008398  pop     rbx
0x180008399  retn
0x18000839a  mov     ecx, [r8]
0x18000839d  lea     eax, [rcx-1]
0x1800083a0  cmp     eax, 1
0x1800083a3  ja      short loc_1800083B0
0x1800083a5  mov     [rbx+10h], ecx
0x1800083a8  xor     eax, eax
0x1800083aa  add     rsp, 30h
0x1800083ae  pop     rbx
0x1800083af  retn
0x1800083b0  mov     eax, 0FFFFFFFFh
0x1800083b5  add     rsp, 30h
0x1800083b9  pop     rbx
0x1800083ba  retn
```
