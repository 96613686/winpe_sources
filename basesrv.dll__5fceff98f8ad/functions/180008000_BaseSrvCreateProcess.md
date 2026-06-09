# BaseSrvCreateProcess

- ea: `0x180008000`
- end: `0x180008202`
- name: `BaseSrvCreateProcess`
- size: `514`
- prototype: `__int64 __fastcall(_OWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180007170`
- `0x180007c84`
- `0x180008000`

## pseudocode

```c
__int64 __fastcall BaseSrvCreateProcess(_OWORD *a1, _DWORD *a2)
{
  __int64 v2; // rsi
  __int64 *v3; // r8
  _OWORD *v4; // rbx
  _OWORD *v5; // rax
  __int64 v7; // rcx
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  _OWORD *v15; // rdi
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int64 v18; // rax
  int Process2; // ecx
  __int64 *v20; // rax
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int64 v30; // rax
  __int128 v31; // xmm1
  __int64 v32; // rax
  __int128 v33; // xmm0
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int64 v46[8]; // [rsp+20h] [rbp-E0h] BYREF
  _OWORD v47[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+90h] [rbp-70h]
  __int128 v49; // [rsp+98h] [rbp-68h]
  __int128 v50; // [rsp+A8h] [rbp-58h]
  __int128 v51; // [rsp+B8h] [rbp-48h]
  __int128 v52; // [rsp+C8h] [rbp-38h]
  __int128 v53; // [rsp+D8h] [rbp-28h]
  __int128 v54; // [rsp+E8h] [rbp-18h]
  __int128 v55; // [rsp+F8h] [rbp-8h]
  __int128 v56; // [rsp+108h] [rbp+8h]
  __int128 v57; // [rsp+118h] [rbp+18h]
  __int128 v58; // [rsp+128h] [rbp+28h]
  __int128 v59; // [rsp+138h] [rbp+38h]
  __int64 v60; // [rsp+148h] [rbp+48h]
  __int128 v61; // [rsp+260h] [rbp+160h]
  __int64 v62; // [rsp+270h] [rbp+170h]

  v2 = 7;
  v3 = v46;
  v4 = a1;
  v5 = a1;
  v7 = 7;
  do
  {
    v8 = v5[1];
    *(_OWORD *)v3 = *v5;
    v9 = v5[2];
    *((_OWORD *)v3 + 1) = v8;
    v10 = v5[3];
    *((_OWORD *)v3 + 2) = v9;
    v11 = v5[4];
    *((_OWORD *)v3 + 3) = v10;
    v12 = v5[5];
    *((_OWORD *)v3 + 4) = v11;
    v13 = v5[6];
    *((_OWORD *)v3 + 5) = v12;
    v14 = v5[7];
    v5 += 8;
    *((_OWORD *)v3 + 6) = v13;
    *((_OWORD *)v3 + 7) = v14;
    v3 += 16;
    --v7;
  }
  while ( v7 );
  v15 = v4 + 4;
  v16 = v5[1];
  *(_OWORD *)v3 = *v5;
  v17 = v5[2];
  v18 = *((_QWORD *)v5 + 6);
  *((_OWORD *)v3 + 1) = v16;
  *((_OWORD *)v3 + 2) = v17;
  v3[6] = v18;
  BaseSrvConvertV1CreateProcessToV2(v4 + 4, v47);
  Process2 = BaseSrvCreateProcess2((__int64)v46, a2);
  if ( Process2 >= 0 )
  {
    v20 = v46;
    do
    {
      v21 = *((_OWORD *)v20 + 1);
      *v4 = *(_OWORD *)v20;
      v22 = *((_OWORD *)v20 + 2);
      v4[1] = v21;
      v23 = *((_OWORD *)v20 + 3);
      v4[2] = v22;
      v24 = *((_OWORD *)v20 + 4);
      v4[3] = v23;
      v25 = *((_OWORD *)v20 + 5);
      v4[4] = v24;
      v26 = *((_OWORD *)v20 + 6);
      v4[5] = v25;
      v27 = *((_OWORD *)v20 + 7);
      v20 += 16;
      v4[6] = v26;
      v4[7] = v27;
      v4 += 8;
      --v2;
    }
    while ( v2 );
    v28 = *((_OWORD *)v20 + 1);
    *v4 = *(_OWORD *)v20;
    v29 = *((_OWORD *)v20 + 2);
    v30 = v20[6];
    v4[1] = v28;
    v31 = v47[1];
    v4[2] = v29;
    *((_QWORD *)v4 + 6) = v30;
    v32 = v60;
    *v15 = v47[0];
    v33 = v47[2];
    v15[1] = v31;
    *(_QWORD *)&v31 = v48;
    v15[2] = v33;
    v34 = v49;
    *((_QWORD *)v15 + 6) = v31;
    v35 = v50;
    *(_OWORD *)((char *)v15 + 56) = v34;
    v36 = v51;
    *(_OWORD *)((char *)v15 + 72) = v35;
    v37 = v52;
    *(_OWORD *)((char *)v15 + 88) = v36;
    v38 = v53;
    *(_OWORD *)((char *)v15 + 104) = v37;
    v39 = v54;
    *(_OWORD *)((char *)v15 + 120) = v38;
    v40 = v55;
    *(_OWORD *)((char *)v15 + 136) = v39;
    v41 = v56;
    *(_OWORD *)((char *)v15 + 152) = v40;
    v42 = v57;
    *(_OWORD *)((char *)v15 + 168) = v41;
    v43 = v58;
    *(_OWORD *)((char *)v15 + 184) = v42;
    v44 = v59;
    *(_OWORD *)((char *)v15 + 200) = v43;
    *(_QWORD *)&v43 = v62;
    *(_OWORD *)((char *)v15 + 216) = v44;
    *((_QWORD *)v15 + 29) = v32;
    v15[15] = v61;
    *((_QWORD *)v15 + 32) = v43;
  }
  return (unsigned int)Process2;
}

```

## disassembly

```asm
0x180008000  push    rbp
0x180008002  push    rbx
0x180008003  push    rsi
0x180008004  push    rdi
0x180008005  push    r14
0x180008007  push    r15
0x180008009  lea     rbp, [rsp-2E8h]
0x180008011  sub     rsp, 3E8h
0x180008018  mov     esi, 7
0x18000801d  lea     r8, [rsp+410h+var_3F0]
0x180008022  mov     rbx, rcx
0x180008025  mov     rax, rcx
0x180008028  mov     r14, rdx
0x18000802b  mov     ecx, esi
0x18000802d  lea     r15d, [rsi+79h]
0x180008031  movups  xmm0, xmmword ptr [rax]
0x180008034  movups  xmm1, xmmword ptr [rax+10h]
0x180008038  movups  xmmword ptr [r8], xmm0
0x18000803c  movups  xmm0, xmmword ptr [rax+20h]
0x180008040  movups  xmmword ptr [r8+10h], xmm1
0x180008045  movups  xmm1, xmmword ptr [rax+30h]
0x180008049  movups  xmmword ptr [r8+20h], xmm0
0x18000804e  movups  xmm0, xmmword ptr [rax+40h]
0x180008052  movups  xmmword ptr [r8+30h], xmm1
0x180008057  movups  xmm1, xmmword ptr [rax+50h]
0x18000805b  movups  xmmword ptr [r8+40h], xmm0
0x180008060  movups  xmm0, xmmword ptr [rax+60h]
0x180008064  movups  xmmword ptr [r8+50h], xmm1
0x180008069  movups  xmm1, xmmword ptr [rax+70h]
0x18000806d  add     rax, r15
0x180008070  movups  xmmword ptr [r8+60h], xmm0
0x180008075  movups  xmmword ptr [r8+70h], xmm1
0x18000807a  add     r8, r15
0x18000807d  sub     rcx, 1
0x180008081  jnz     short loc_180008031
0x180008083  movups  xmm0, xmmword ptr [rax]
0x180008086  lea     rdi, [rbx+40h]
0x18000808a  movups  xmm1, xmmword ptr [rax+10h]
0x18000808e  lea     rdx, [rsp+410h+var_3B0]
0x180008093  mov     rcx, rdi
0x180008096  movups  xmmword ptr [r8], xmm0
0x18000809a  movups  xmm0, xmmword ptr [rax+20h]
0x18000809e  mov     rax, [rax+30h]
0x1800080a2  movups  xmmword ptr [r8+10h], xmm1
0x1800080a7  movups  xmmword ptr [r8+20h], xmm0
0x1800080ac  mov     [r8+30h], rax
0x1800080b0  call    BaseSrvConvertV1CreateProcessToV2
0x1800080b5  mov     rdx, r14
0x1800080b8  lea     rcx, [rsp+410h+var_3F0]; __int64
0x1800080bd  call    BaseSrvCreateProcess2
0x1800080c2  mov     ecx, eax
0x1800080c4  test    eax, eax
0x1800080c6  js      loc_1800081EF
0x1800080cc  lea     rax, [rsp+410h+var_3F0]
0x1800080d1  movups  xmm0, xmmword ptr [rax]
0x1800080d4  movups  xmm1, xmmword ptr [rax+10h]
0x1800080d8  movups  xmmword ptr [rbx], xmm0
0x1800080db  movups  xmm0, xmmword ptr [rax+20h]
0x1800080df  movups  xmmword ptr [rbx+10h], xmm1
0x1800080e3  movups  xmm1, xmmword ptr [rax+30h]
0x1800080e7  movups  xmmword ptr [rbx+20h], xmm0
0x1800080eb  movups  xmm0, xmmword ptr [rax+40h]
0x1800080ef  movups  xmmword ptr [rbx+30h], xmm1
0x1800080f3  movups  xmm1, xmmword ptr [rax+50h]
0x1800080f7  movups  xmmword ptr [rbx+40h], xmm0
0x1800080fb  movups  xmm0, xmmword ptr [rax+60h]
0x1800080ff  movups  xmmword ptr [rbx+50h], xmm1
0x180008103  movups  xmm1, xmmword ptr [rax+70h]
0x180008107  add     rax, r15
0x18000810a  movups  xmmword ptr [rbx+60h], xmm0
0x18000810e  movups  xmmword ptr [rbx+70h], xmm1
0x180008112  add     rbx, r15
0x180008115  sub     rsi, 1
0x180008119  jnz     short loc_1800080D1
0x18000811b  movups  xmm0, xmmword ptr [rax]
0x18000811e  movups  xmm1, xmmword ptr [rax+10h]
0x180008122  movups  xmmword ptr [rbx], xmm0
0x180008125  movups  xmm0, xmmword ptr [rax+20h]
0x180008129  mov     rax, [rax+30h]
0x18000812d  movups  xmmword ptr [rbx+10h], xmm1
0x180008131  movaps  xmm1, [rsp+410h+var_3A0]
0x180008136  movups  xmmword ptr [rbx+20h], xmm0
0x18000813a  mov     [rbx+30h], rax
0x18000813e  movaps  xmm0, [rsp+410h+var_3B0]
0x180008143  mov     rax, [rbp+310h+var_2C8]
0x180008147  movups  xmmword ptr [rdi], xmm0
0x18000814a  movaps  xmm0, [rbp+310h+var_390]
0x18000814e  movups  xmmword ptr [rdi+10h], xmm1
0x180008152  movsd   xmm1, [rbp+310h+var_380]
0x180008157  movups  xmmword ptr [rdi+20h], xmm0
0x18000815b  movups  xmm0, [rbp+310h+var_378]
0x18000815f  movsd   qword ptr [rdi+30h], xmm1
0x180008164  movups  xmm1, [rbp+310h+var_368]
0x180008168  movups  xmmword ptr [rdi+38h], xmm0
0x18000816c  movups  xmm0, [rbp+310h+var_358]
0x180008170  movups  xmmword ptr [rdi+48h], xmm1
0x180008174  movups  xmm1, [rbp+310h+var_348]
0x180008178  movups  xmmword ptr [rdi+58h], xmm0
0x18000817c  movups  xmm0, [rbp+310h+var_338]
0x180008180  movups  xmmword ptr [rdi+68h], xmm1
0x180008184  movups  xmm1, [rbp+310h+var_328]
0x180008188  movups  xmmword ptr [rdi+78h], xmm0
0x18000818c  movups  xmm0, [rbp+310h+var_318]
0x180008190  movups  xmmword ptr [rdi+88h], xmm1
0x180008197  movups  xmm1, [rbp+310h+var_308]
0x18000819b  movups  xmmword ptr [rdi+98h], xmm0
0x1800081a2  movups  xmm0, [rbp+310h+var_2F8]
0x1800081a6  movups  xmmword ptr [rdi+0A8h], xmm1
0x1800081ad  movups  xmm1, [rbp+310h+var_2E8]
0x1800081b1  movups  xmmword ptr [rdi+0B8h], xmm0
0x1800081b8  movups  xmm0, [rbp+310h+var_2D8]
0x1800081bc  movups  xmmword ptr [rdi+0C8h], xmm1
0x1800081c3  movsd   xmm1, [rbp+310h+var_1A0]
0x1800081cb  movups  xmmword ptr [rdi+0D8h], xmm0
0x1800081d2  mov     [rdi+0E8h], rax
0x1800081d9  movaps  xmm0, [rbp+310h+var_1B0]
0x1800081e0  movups  xmmword ptr [rdi+0F0h], xmm0
0x1800081e7  movsd   qword ptr [rdi+100h], xmm1
0x1800081ef  mov     eax, ecx
0x1800081f1  add     rsp, 3E8h
0x1800081f8  pop     r15
0x1800081fa  pop     r14
0x1800081fc  pop     rdi
0x1800081fd  pop     rsi
0x1800081fe  pop     rbx
0x1800081ff  pop     rbp
0x180008200  retn
```
