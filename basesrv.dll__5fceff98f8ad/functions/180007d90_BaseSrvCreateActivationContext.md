# BaseSrvCreateActivationContext

- ea: `0x180007d90`
- end: `0x180007ff2`
- name: `BaseSrvCreateActivationContext`
- size: `610`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002390`
- `0x180007d90`
- `0x18000db1d`

## pseudocode

```c
__int64 __fastcall BaseSrvCreateActivationContext(_OWORD *a1)
{
  __int64 v1; // rsi
  _OWORD *v2; // rbx
  _OWORD *v3; // rax
  _OWORD *v4; // rcx
  __int64 v5; // r8
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  _OWORD *v13; // rdi
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int64 v16; // rax
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int64 v19; // rax
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  int ActivationContext2; // ecx
  _OWORD *v33; // rax
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int64 v43; // rax
  __int128 v44; // xmm1
  __int64 v45; // rax
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  __int128 v52; // xmm0
  __int128 v53; // xmm1
  __int128 v54; // xmm0
  __int128 v55; // xmm1
  __int128 v56; // xmm0
  __int128 v57; // xmm1
  _BYTE v59[64]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v60; // [rsp+60h] [rbp-A0h]
  __int128 v61; // [rsp+70h] [rbp-90h]
  __int128 v62; // [rsp+80h] [rbp-80h]
  __int128 v63; // [rsp+90h] [rbp-70h]
  __int128 v64; // [rsp+A0h] [rbp-60h]
  __int128 v65; // [rsp+B0h] [rbp-50h]
  __int128 v66; // [rsp+C0h] [rbp-40h]
  __int128 v67; // [rsp+D0h] [rbp-30h]
  __int128 v68; // [rsp+E0h] [rbp-20h]
  __int128 v69; // [rsp+F0h] [rbp-10h]
  __int128 v70; // [rsp+100h] [rbp+0h]
  __int128 v71; // [rsp+110h] [rbp+10h]
  __int128 v72; // [rsp+120h] [rbp+20h]
  __int128 v73; // [rsp+130h] [rbp+30h]
  __int64 v74; // [rsp+140h] [rbp+40h]
  char v75[712]; // [rsp+148h] [rbp+48h] BYREF

  v1 = 7;
  v2 = a1;
  v3 = a1;
  v4 = v59;
  v5 = 7;
  do
  {
    v6 = v3[1];
    *v4 = *v3;
    v7 = v3[2];
    v4[1] = v6;
    v8 = v3[3];
    v4[2] = v7;
    v9 = v3[4];
    v4[3] = v8;
    v10 = v3[5];
    v4[4] = v9;
    v11 = v3[6];
    v4[5] = v10;
    v12 = v3[7];
    v3 += 8;
    v4[6] = v11;
    v4[7] = v12;
    v4 += 8;
    --v5;
  }
  while ( v5 );
  v13 = v2 + 4;
  v14 = v3[1];
  *v4 = *v3;
  v15 = v3[2];
  v16 = *((_QWORD *)v3 + 6);
  v4[1] = v14;
  v17 = v2[5];
  v4[2] = v15;
  *((_QWORD *)v4 + 6) = v16;
  v18 = v2[4];
  v19 = *((_QWORD *)v2 + 36);
  v61 = v17;
  v74 = v19;
  v20 = v2[7];
  v60 = v18;
  v21 = v2[6];
  v63 = v20;
  v22 = v2[9];
  v62 = v21;
  v23 = v2[8];
  v65 = v22;
  v24 = v2[11];
  v64 = v23;
  v25 = v2[10];
  v67 = v24;
  v26 = v2[13];
  v66 = v25;
  v27 = v2[12];
  v69 = v26;
  v28 = v2[15];
  v68 = v27;
  v29 = v2[14];
  v71 = v28;
  v30 = v2[17];
  v70 = v29;
  v31 = v2[16];
  v73 = v30;
  v72 = v31;
  memset_0(v75, 0, 0x110u);
  ActivationContext2 = BaseSrvCreateActivationContext2();
  if ( ActivationContext2 >= 0 )
  {
    v33 = v59;
    do
    {
      v34 = v33[1];
      *v2 = *v33;
      v35 = v33[2];
      v2[1] = v34;
      v36 = v33[3];
      v2[2] = v35;
      v37 = v33[4];
      v2[3] = v36;
      v38 = v33[5];
      v2[4] = v37;
      v39 = v33[6];
      v2[5] = v38;
      v40 = v33[7];
      v33 += 8;
      v2[6] = v39;
      v2[7] = v40;
      v2 += 8;
      --v1;
    }
    while ( v1 );
    v41 = v33[1];
    *v2 = *v33;
    v42 = v33[2];
    v43 = *((_QWORD *)v33 + 6);
    v2[1] = v41;
    v44 = v61;
    v2[2] = v42;
    *((_QWORD *)v2 + 6) = v43;
    v45 = v74;
    *v13 = v60;
    v46 = v62;
    v13[1] = v44;
    v47 = v63;
    v13[2] = v46;
    v48 = v64;
    v13[3] = v47;
    v49 = v65;
    v13[4] = v48;
    v50 = v66;
    v13[5] = v49;
    v51 = v67;
    v13[6] = v50;
    v52 = v68;
    v13[7] = v51;
    v53 = v69;
    v13[8] = v52;
    v54 = v70;
    v13[9] = v53;
    v55 = v71;
    v13[10] = v54;
    v56 = v72;
    v13[11] = v55;
    v57 = v73;
    v13[12] = v56;
    v13[13] = v57;
    *((_QWORD *)v13 + 28) = v45;
  }
  return (unsigned int)ActivationContext2;
}

```

## disassembly

```asm
0x180007d90  push    rbp
0x180007d92  push    rbx
0x180007d93  push    rsi
0x180007d94  push    rdi
0x180007d95  push    r14
0x180007d97  push    r15
0x180007d99  lea     rbp, [rsp-2E8h]
0x180007da1  sub     rsp, 3E8h
0x180007da8  mov     esi, 7
0x180007dad  mov     rbx, rcx
0x180007db0  mov     rax, rcx
0x180007db3  mov     r14, rdx
0x180007db6  lea     rcx, [rsp+410h+var_3F0]
0x180007dbb  mov     r8d, esi
0x180007dbe  lea     r15d, [rsi+79h]
0x180007dc2  movups  xmm0, xmmword ptr [rax]
0x180007dc5  movups  xmm1, xmmword ptr [rax+10h]
0x180007dc9  movups  xmmword ptr [rcx], xmm0
0x180007dcc  movups  xmm0, xmmword ptr [rax+20h]
0x180007dd0  movups  xmmword ptr [rcx+10h], xmm1
0x180007dd4  movups  xmm1, xmmword ptr [rax+30h]
0x180007dd8  movups  xmmword ptr [rcx+20h], xmm0
0x180007ddc  movups  xmm0, xmmword ptr [rax+40h]
0x180007de0  movups  xmmword ptr [rcx+30h], xmm1
0x180007de4  movups  xmm1, xmmword ptr [rax+50h]
0x180007de8  movups  xmmword ptr [rcx+40h], xmm0
0x180007dec  movups  xmm0, xmmword ptr [rax+60h]
0x180007df0  movups  xmmword ptr [rcx+50h], xmm1
0x180007df4  movups  xmm1, xmmword ptr [rax+70h]
0x180007df8  add     rax, r15
0x180007dfb  movups  xmmword ptr [rcx+60h], xmm0
0x180007dff  movups  xmmword ptr [rcx+70h], xmm1
0x180007e03  add     rcx, r15
0x180007e06  sub     r8, 1
0x180007e0a  jnz     short loc_180007DC2
0x180007e0c  movups  xmm0, xmmword ptr [rax]
0x180007e0f  lea     rdi, [rbx+40h]
0x180007e13  xor     edx, edx; Val
0x180007e15  movups  xmm1, xmmword ptr [rax+10h]
0x180007e19  mov     r8d, 110h; Size
0x180007e1f  movups  xmmword ptr [rcx], xmm0
0x180007e22  movups  xmm0, xmmword ptr [rax+20h]
0x180007e26  mov     rax, [rax+30h]
0x180007e2a  movups  xmmword ptr [rcx+10h], xmm1
0x180007e2e  movups  xmm1, xmmword ptr [rdi+10h]
0x180007e32  movups  xmmword ptr [rcx+20h], xmm0
0x180007e36  mov     [rcx+30h], rax
0x180007e3a  lea     rcx, [rbp+310h+var_2C8]; void *
0x180007e3e  movups  xmm0, xmmword ptr [rdi]
0x180007e41  mov     rax, [rdi+0E0h]
0x180007e48  movups  [rsp+410h+var_3A0], xmm1
0x180007e4d  mov     [rbp+310h+var_2D0], rax
0x180007e51  movups  xmm1, xmmword ptr [rdi+30h]
0x180007e55  movups  [rsp+410h+var_3B0], xmm0
0x180007e5a  movups  xmm0, xmmword ptr [rdi+20h]
0x180007e5e  movups  [rbp+310h+var_380], xmm1
0x180007e62  movups  xmm1, xmmword ptr [rdi+50h]
0x180007e66  movups  [rbp+310h+var_390], xmm0
0x180007e6a  movups  xmm0, xmmword ptr [rdi+40h]
0x180007e6e  movups  [rbp+310h+var_360], xmm1
0x180007e72  movups  xmm1, xmmword ptr [rdi+70h]
0x180007e76  movups  [rbp+310h+var_370], xmm0
0x180007e7a  movups  xmm0, xmmword ptr [rdi+60h]
0x180007e7e  movups  [rbp+310h+var_340], xmm1
0x180007e82  movups  xmm1, xmmword ptr [rdi+90h]
0x180007e89  movups  [rbp+310h+var_350], xmm0
0x180007e8d  movups  xmm0, xmmword ptr [rdi+80h]
0x180007e94  movups  [rbp+310h+var_320], xmm1
0x180007e98  movups  xmm1, xmmword ptr [rdi+0B0h]
0x180007e9f  movups  [rbp+310h+var_330], xmm0
0x180007ea3  movups  xmm0, xmmword ptr [rdi+0A0h]
0x180007eaa  movups  [rbp+310h+var_300], xmm1
0x180007eae  movups  xmm1, xmmword ptr [rdi+0D0h]
0x180007eb5  movups  [rbp+310h+var_310], xmm0
0x180007eb9  movups  xmm0, xmmword ptr [rdi+0C0h]
0x180007ec0  movups  [rbp+310h+var_2E0], xmm1
0x180007ec4  movups  [rbp+310h+var_2F0], xmm0
0x180007ec8  call    memset_0
0x180007ecd  mov     rdx, r14
0x180007ed0  lea     rcx, [rsp+410h+var_3F0]
0x180007ed5  call    BaseSrvCreateActivationContext2
0x180007eda  mov     ecx, eax
0x180007edc  test    eax, eax
0x180007ede  js      loc_180007FDF
0x180007ee4  lea     rax, [rsp+410h+var_3F0]
0x180007ee9  movups  xmm0, xmmword ptr [rax]
0x180007eec  movups  xmm1, xmmword ptr [rax+10h]
0x180007ef0  movups  xmmword ptr [rbx], xmm0
0x180007ef3  movups  xmm0, xmmword ptr [rax+20h]
0x180007ef7  movups  xmmword ptr [rbx+10h], xmm1
0x180007efb  movups  xmm1, xmmword ptr [rax+30h]
0x180007eff  movups  xmmword ptr [rbx+20h], xmm0
0x180007f03  movups  xmm0, xmmword ptr [rax+40h]
0x180007f07  movups  xmmword ptr [rbx+30h], xmm1
0x180007f0b  movups  xmm1, xmmword ptr [rax+50h]
0x180007f0f  movups  xmmword ptr [rbx+40h], xmm0
0x180007f13  movups  xmm0, xmmword ptr [rax+60h]
0x180007f17  movups  xmmword ptr [rbx+50h], xmm1
0x180007f1b  movups  xmm1, xmmword ptr [rax+70h]
0x180007f1f  add     rax, r15
0x180007f22  movups  xmmword ptr [rbx+60h], xmm0
0x180007f26  movups  xmmword ptr [rbx+70h], xmm1
0x180007f2a  add     rbx, r15
0x180007f2d  sub     rsi, 1
0x180007f31  jnz     short loc_180007EE9
0x180007f33  movups  xmm0, xmmword ptr [rax]
0x180007f36  movups  xmm1, xmmword ptr [rax+10h]
0x180007f3a  movups  xmmword ptr [rbx], xmm0
0x180007f3d  movups  xmm0, xmmword ptr [rax+20h]
0x180007f41  mov     rax, [rax+30h]
0x180007f45  movups  xmmword ptr [rbx+10h], xmm1
0x180007f49  movaps  xmm1, [rsp+410h+var_3A0]
0x180007f4e  movups  xmmword ptr [rbx+20h], xmm0
0x180007f52  mov     [rbx+30h], rax
0x180007f56  movaps  xmm0, [rsp+410h+var_3B0]
0x180007f5b  mov     rax, [rbp+310h+var_2D0]
0x180007f5f  movups  xmmword ptr [rdi], xmm0
0x180007f62  movaps  xmm0, [rbp+310h+var_390]
0x180007f66  movups  xmmword ptr [rdi+10h], xmm1
0x180007f6a  movaps  xmm1, [rbp+310h+var_380]
0x180007f6e  movups  xmmword ptr [rdi+20h], xmm0
0x180007f72  movaps  xmm0, [rbp+310h+var_370]
0x180007f76  movups  xmmword ptr [rdi+30h], xmm1
0x180007f7a  movaps  xmm1, [rbp+310h+var_360]
0x180007f7e  movups  xmmword ptr [rdi+40h], xmm0
0x180007f82  movaps  xmm0, [rbp+310h+var_350]
0x180007f86  movups  xmmword ptr [rdi+50h], xmm1
0x180007f8a  movaps  xmm1, [rbp+310h+var_340]
0x180007f8e  movups  xmmword ptr [rdi+60h], xmm0
0x180007f92  movaps  xmm0, [rbp+310h+var_330]
0x180007f96  movups  xmmword ptr [rdi+70h], xmm1
0x180007f9a  movaps  xmm1, [rbp+310h+var_320]
0x180007f9e  movups  xmmword ptr [rdi+80h], xmm0
0x180007fa5  movaps  xmm0, [rbp+310h+var_310]
0x180007fa9  movups  xmmword ptr [rdi+90h], xmm1
0x180007fb0  movaps  xmm1, [rbp+310h+var_300]
0x180007fb4  movups  xmmword ptr [rdi+0A0h], xmm0
0x180007fbb  movaps  xmm0, [rbp+310h+var_2F0]
0x180007fbf  movups  xmmword ptr [rdi+0B0h], xmm1
0x180007fc6  movaps  xmm1, [rbp+310h+var_2E0]
0x180007fca  movups  xmmword ptr [rdi+0C0h], xmm0
0x180007fd1  movups  xmmword ptr [rdi+0D0h], xmm1
0x180007fd8  mov     [rdi+0E0h], rax
0x180007fdf  mov     eax, ecx
0x180007fe1  add     rsp, 3E8h
0x180007fe8  pop     r15
0x180007fea  pop     r14
0x180007fec  pop     rdi
0x180007fed  pop     rsi
0x180007fee  pop     rbx
0x180007fef  pop     rbp
0x180007ff0  retn
```
