# BaseSrvCreateProcess

- ea: `0x180007cf0`
- end: `0x180007f07`
- name: `BaseSrvCreateProcess`
- size: `535`
- prototype: `__int64 __fastcall(_OWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180006ee0`
- `0x18000798c`
- `0x180007cf0`

## pseudocode

```c
__int64 __fastcall BaseSrvCreateProcess(_OWORD *a1)
{
  __int64 v1; // rdi
  __int64 *v2; // r8
  _OWORD *v3; // rbx
  _OWORD *v4; // rax
  __int64 v5; // rcx
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  _OWORD *v13; // rsi
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int64 v16; // rax
  int Process2; // edx
  __int64 *v18; // rax
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int64 v28; // rax
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int64 v41; // rax
  __int64 v43[8]; // [rsp+20h] [rbp-3C8h] BYREF
  _OWORD v44[3]; // [rsp+60h] [rbp-388h] BYREF
  __int64 v45; // [rsp+90h] [rbp-358h]
  __int128 v46; // [rsp+98h] [rbp-350h]
  __int128 v47; // [rsp+A8h] [rbp-340h]
  __int128 v48; // [rsp+B8h] [rbp-330h]
  __int128 v49; // [rsp+C8h] [rbp-320h]
  __int128 v50; // [rsp+D8h] [rbp-310h]
  __int128 v51; // [rsp+E8h] [rbp-300h]
  __int128 v52; // [rsp+F8h] [rbp-2F0h]
  __int128 v53; // [rsp+108h] [rbp-2E0h]
  __int128 v54; // [rsp+118h] [rbp-2D0h]
  __int128 v55; // [rsp+128h] [rbp-2C0h]
  __int128 v56; // [rsp+138h] [rbp-2B0h]
  __int64 v57; // [rsp+148h] [rbp-2A0h]
  __int128 v58; // [rsp+260h] [rbp-188h]
  __int64 v59; // [rsp+270h] [rbp-178h]

  v1 = 7;
  v2 = v43;
  v3 = a1;
  v4 = a1;
  v5 = 7;
  do
  {
    v6 = v4[1];
    *(_OWORD *)v2 = *v4;
    v7 = v4[2];
    *((_OWORD *)v2 + 1) = v6;
    v8 = v4[3];
    *((_OWORD *)v2 + 2) = v7;
    v9 = v4[4];
    *((_OWORD *)v2 + 3) = v8;
    v10 = v4[5];
    *((_OWORD *)v2 + 4) = v9;
    v11 = v4[6];
    *((_OWORD *)v2 + 5) = v10;
    v12 = v4[7];
    v4 += 8;
    *((_OWORD *)v2 + 6) = v11;
    v2 += 16;
    *((_OWORD *)v2 - 1) = v12;
    --v5;
  }
  while ( v5 );
  v13 = v3 + 4;
  v14 = v4[1];
  *(_OWORD *)v2 = *v4;
  v15 = v4[2];
  v16 = *((_QWORD *)v4 + 6);
  *((_OWORD *)v2 + 1) = v14;
  *((_OWORD *)v2 + 2) = v15;
  v2[6] = v16;
  BaseSrvConvertV1CreateProcessToV2(v3 + 4, v44);
  Process2 = BaseSrvCreateProcess2((__int64)v43);
  if ( Process2 >= 0 )
  {
    v18 = v43;
    do
    {
      v19 = *((_OWORD *)v18 + 1);
      *v3 = *(_OWORD *)v18;
      v20 = *((_OWORD *)v18 + 2);
      v3[1] = v19;
      v21 = *((_OWORD *)v18 + 3);
      v3[2] = v20;
      v22 = *((_OWORD *)v18 + 4);
      v3[3] = v21;
      v23 = *((_OWORD *)v18 + 5);
      v3[4] = v22;
      v24 = *((_OWORD *)v18 + 6);
      v3[5] = v23;
      v25 = *((_OWORD *)v18 + 7);
      v18 += 16;
      v3[6] = v24;
      v3 += 8;
      *(v3 - 1) = v25;
      --v1;
    }
    while ( v1 );
    v26 = *((_OWORD *)v18 + 1);
    *v3 = *(_OWORD *)v18;
    v27 = *((_OWORD *)v18 + 2);
    v28 = v18[6];
    v3[1] = v26;
    v29 = v44[1];
    v3[2] = v27;
    *((_QWORD *)v3 + 6) = v28;
    *v13 = v44[0];
    v30 = v44[2];
    v13[1] = v29;
    *(_QWORD *)&v29 = v45;
    v13[2] = v30;
    v31 = v46;
    *((_QWORD *)v13 + 6) = v29;
    v32 = v47;
    *(_OWORD *)((char *)v13 + 56) = v31;
    v33 = v48;
    *(_OWORD *)((char *)v13 + 72) = v32;
    v34 = v49;
    *(_OWORD *)((char *)v13 + 88) = v33;
    v35 = v50;
    *(_OWORD *)((char *)v13 + 104) = v34;
    v36 = v51;
    *(_OWORD *)((char *)v13 + 120) = v35;
    v37 = v52;
    *(_OWORD *)((char *)v13 + 136) = v36;
    v38 = v53;
    *(_OWORD *)((char *)v13 + 152) = v37;
    *(_OWORD *)((char *)v13 + 168) = v38;
    v39 = v55;
    *(_OWORD *)((char *)v13 + 184) = v54;
    v40 = v56;
    v41 = v57;
    *(_OWORD *)((char *)v13 + 200) = v39;
    *(_QWORD *)&v39 = v59;
    *(_OWORD *)((char *)v13 + 216) = v40;
    *((_QWORD *)v13 + 29) = v41;
    v13[15] = v58;
    *((_QWORD *)v13 + 32) = v39;
  }
  return (unsigned int)Process2;
}

```

## disassembly

```asm
0x180007cf0  mov     rax, rsp
0x180007cf3  mov     [rax+8], rbx
0x180007cf7  mov     [rax+10h], rbp
0x180007cfb  mov     [rax+18h], rsi
0x180007cff  mov     [rax+20h], rdi
0x180007d03  push    r14
0x180007d05  sub     rsp, 3E0h
0x180007d0c  mov     edi, 7
0x180007d11  lea     r8, [rsp+3E8h+var_3C8]
0x180007d16  mov     rbx, rcx
0x180007d19  mov     rax, rcx
0x180007d1c  mov     rbp, rdx
0x180007d1f  mov     ecx, edi
0x180007d21  lea     r14d, [rdi+79h]
0x180007d25  movups  xmm0, xmmword ptr [rax]
0x180007d28  movups  xmm1, xmmword ptr [rax+10h]
0x180007d2c  movups  xmmword ptr [r8], xmm0
0x180007d30  movups  xmm0, xmmword ptr [rax+20h]
0x180007d34  movups  xmmword ptr [r8+10h], xmm1
0x180007d39  movups  xmm1, xmmword ptr [rax+30h]
0x180007d3d  movups  xmmword ptr [r8+20h], xmm0
0x180007d42  movups  xmm0, xmmword ptr [rax+40h]
0x180007d46  movups  xmmword ptr [r8+30h], xmm1
0x180007d4b  movups  xmm1, xmmword ptr [rax+50h]
0x180007d4f  movups  xmmword ptr [r8+40h], xmm0
0x180007d54  movups  xmm0, xmmword ptr [rax+60h]
0x180007d58  movups  xmmword ptr [r8+50h], xmm1
0x180007d5d  movups  xmm1, xmmword ptr [rax+70h]
0x180007d61  add     rax, r14
0x180007d64  movups  xmmword ptr [r8+60h], xmm0
0x180007d69  add     r8, r14
0x180007d6c  movups  xmmword ptr [r8-10h], xmm1
0x180007d71  sub     rcx, 1
0x180007d75  jnz     short loc_180007D25
0x180007d77  movups  xmm0, xmmword ptr [rax]
0x180007d7a  lea     rsi, [rbx+40h]
0x180007d7e  movups  xmm1, xmmword ptr [rax+10h]
0x180007d82  lea     rdx, [rsp+3E8h+var_388]
0x180007d87  mov     rcx, rsi
0x180007d8a  movups  xmmword ptr [r8], xmm0
0x180007d8e  movups  xmm0, xmmword ptr [rax+20h]
0x180007d92  mov     rax, [rax+30h]
0x180007d96  movups  xmmword ptr [r8+10h], xmm1
0x180007d9b  movups  xmmword ptr [r8+20h], xmm0
0x180007da0  mov     [r8+30h], rax
0x180007da4  call    BaseSrvConvertV1CreateProcessToV2
0x180007da9  mov     rdx, rbp
0x180007dac  lea     rcx, [rsp+3E8h+var_3C8]; __int64
0x180007db1  call    BaseSrvCreateProcess2
0x180007db6  mov     edx, eax
0x180007db8  test    eax, eax
0x180007dba  js      loc_180007EE6
0x180007dc0  lea     rax, [rsp+3E8h+var_3C8]
0x180007dc5  movups  xmm0, xmmword ptr [rax]
0x180007dc8  movups  xmm1, xmmword ptr [rax+10h]
0x180007dcc  movups  xmmword ptr [rbx], xmm0
0x180007dcf  movups  xmm0, xmmword ptr [rax+20h]
0x180007dd3  movups  xmmword ptr [rbx+10h], xmm1
0x180007dd7  movups  xmm1, xmmword ptr [rax+30h]
0x180007ddb  movups  xmmword ptr [rbx+20h], xmm0
0x180007ddf  movups  xmm0, xmmword ptr [rax+40h]
0x180007de3  movups  xmmword ptr [rbx+30h], xmm1
0x180007de7  movups  xmm1, xmmword ptr [rax+50h]
0x180007deb  movups  xmmword ptr [rbx+40h], xmm0
0x180007def  movups  xmm0, xmmword ptr [rax+60h]
0x180007df3  movups  xmmword ptr [rbx+50h], xmm1
0x180007df7  movups  xmm1, xmmword ptr [rax+70h]
0x180007dfb  add     rax, r14
0x180007dfe  movups  xmmword ptr [rbx+60h], xmm0
0x180007e02  add     rbx, r14
0x180007e05  movups  xmmword ptr [rbx-10h], xmm1
0x180007e09  sub     rdi, 1
0x180007e0d  jnz     short loc_180007DC5
0x180007e0f  movups  xmm0, xmmword ptr [rax]
0x180007e12  lea     rcx, [rsi+38h]
0x180007e16  movups  xmm1, xmmword ptr [rax+10h]
0x180007e1a  movups  xmmword ptr [rbx], xmm0
0x180007e1d  movups  xmm0, xmmword ptr [rax+20h]
0x180007e21  mov     rax, [rax+30h]
0x180007e25  movups  xmmword ptr [rbx+10h], xmm1
0x180007e29  movaps  xmm1, [rsp+3E8h+var_378]
0x180007e2e  movups  xmmword ptr [rbx+20h], xmm0
0x180007e32  mov     [rbx+30h], rax
0x180007e36  lea     rax, [rsp+3E8h+var_350]
0x180007e3e  movaps  xmm0, [rsp+3E8h+var_388]
0x180007e43  movups  xmmword ptr [rsi], xmm0
0x180007e46  movaps  xmm0, [rsp+3E8h+var_368]
0x180007e4e  movups  xmmword ptr [rsi+10h], xmm1
0x180007e52  movsd   xmm1, [rsp+3E8h+var_358]
0x180007e5b  movups  xmmword ptr [rsi+20h], xmm0
0x180007e5f  movups  xmm0, xmmword ptr [rax]
0x180007e62  movsd   qword ptr [rsi+30h], xmm1
0x180007e67  movups  xmm1, xmmword ptr [rax+10h]
0x180007e6b  movups  xmmword ptr [rcx], xmm0
0x180007e6e  movups  xmm0, xmmword ptr [rax+20h]
0x180007e72  movups  xmmword ptr [rcx+10h], xmm1
0x180007e76  movups  xmm1, xmmword ptr [rax+30h]
0x180007e7a  movups  xmmword ptr [rcx+20h], xmm0
0x180007e7e  movups  xmm0, xmmword ptr [rax+40h]
0x180007e82  movups  xmmword ptr [rcx+30h], xmm1
0x180007e86  movups  xmm1, xmmword ptr [rax+50h]
0x180007e8a  movups  xmmword ptr [rcx+40h], xmm0
0x180007e8e  movups  xmm0, xmmword ptr [rax+60h]
0x180007e92  movups  xmmword ptr [rcx+50h], xmm1
0x180007e96  movups  xmm1, xmmword ptr [rax+70h]
0x180007e9a  movups  xmmword ptr [rcx+60h], xmm0
0x180007e9e  add     rcx, r14
0x180007ea1  add     rax, r14
0x180007ea4  movups  xmmword ptr [rcx-10h], xmm1
0x180007ea8  movups  xmm0, xmmword ptr [rax]
0x180007eab  movups  xmm1, xmmword ptr [rax+10h]
0x180007eaf  movups  xmmword ptr [rcx], xmm0
0x180007eb2  movups  xmm0, xmmword ptr [rax+20h]
0x180007eb6  mov     rax, [rax+30h]
0x180007eba  movups  xmmword ptr [rcx+10h], xmm1
0x180007ebe  movsd   xmm1, [rsp+3E8h+var_178]
0x180007ec7  movups  xmmword ptr [rcx+20h], xmm0
0x180007ecb  mov     [rcx+30h], rax
0x180007ecf  movaps  xmm0, [rsp+3E8h+var_188]
0x180007ed7  movups  xmmword ptr [rsi+0F0h], xmm0
0x180007ede  movsd   qword ptr [rsi+100h], xmm1
0x180007ee6  lea     r11, [rsp+3E8h+var_8]
0x180007eee  mov     eax, edx
0x180007ef0  mov     rbx, [r11+10h]
0x180007ef4  mov     rbp, [r11+18h]
0x180007ef8  mov     rsi, [r11+20h]
0x180007efc  mov     rdi, [r11+28h]
0x180007f00  mov     rsp, r11
0x180007f03  pop     r14
0x180007f05  retn
```
