# BaseSrvCreateActivationContext

- ea: `0x180007a80`
- end: `0x180007cdb`
- name: `BaseSrvCreateActivationContext`
- size: `603`
- prototype: `__int64 __fastcall(_OWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002390`
- `0x180007a80`
- `0x18000d713`

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
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int64 v30; // rax
  int ActivationContext2; // ecx
  _OWORD *v32; // rax
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int64 v42; // rax
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  _OWORD *v50; // rdi
  __int128 v51; // xmm1
  __int128 v52; // xmm0
  __int128 v53; // xmm1
  __int128 v54; // xmm0
  __int128 v55; // xmm1
  __int64 v56; // rax
  _BYTE v58[64]; // [rsp+20h] [rbp-3C8h] BYREF
  __int128 v59; // [rsp+60h] [rbp-388h]
  __int128 v60; // [rsp+70h] [rbp-378h]
  __int128 v61; // [rsp+80h] [rbp-368h]
  __int128 v62; // [rsp+90h] [rbp-358h]
  __int128 v63; // [rsp+A0h] [rbp-348h]
  __int128 v64; // [rsp+B0h] [rbp-338h]
  __int128 v65; // [rsp+C0h] [rbp-328h]
  __int128 v66; // [rsp+D0h] [rbp-318h]
  __int128 v67; // [rsp+E0h] [rbp-308h]
  __int128 v68; // [rsp+F0h] [rbp-2F8h]
  __int128 v69; // [rsp+100h] [rbp-2E8h]
  __int128 v70; // [rsp+110h] [rbp-2D8h]
  __int128 v71; // [rsp+120h] [rbp-2C8h]
  __int128 v72; // [rsp+130h] [rbp-2B8h]
  __int64 v73; // [rsp+140h] [rbp-2A8h]
  char v74[664]; // [rsp+148h] [rbp-2A0h] BYREF

  v1 = 7;
  v2 = a1;
  v3 = a1;
  v4 = v58;
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
    v4 += 8;
    *(v4 - 1) = v12;
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
  v59 = v2[4];
  v18 = v2[6];
  v60 = v17;
  v19 = v2[7];
  v61 = v18;
  v20 = v2[8];
  v62 = v19;
  v21 = v2[9];
  v63 = v20;
  v22 = v2[10];
  v64 = v21;
  v23 = v2[11];
  v65 = v22;
  v24 = v2[12];
  v66 = v23;
  v25 = v2[13];
  v67 = v24;
  v26 = v2[14];
  v68 = v25;
  v27 = v2[15];
  v69 = v26;
  v28 = v2[16];
  v70 = v27;
  v29 = v2[17];
  v30 = *((_QWORD *)v2 + 36);
  v71 = v28;
  v72 = v29;
  v73 = v30;
  memset_0(v74, 0, 0x110u);
  ActivationContext2 = BaseSrvCreateActivationContext2();
  if ( ActivationContext2 >= 0 )
  {
    v32 = v58;
    do
    {
      v33 = v32[1];
      *v2 = *v32;
      v34 = v32[2];
      v2[1] = v33;
      v35 = v32[3];
      v2[2] = v34;
      v36 = v32[4];
      v2[3] = v35;
      v37 = v32[5];
      v2[4] = v36;
      v38 = v32[6];
      v2[5] = v37;
      v39 = v32[7];
      v32 += 8;
      v2[6] = v38;
      v2 += 8;
      *(v2 - 1) = v39;
      --v1;
    }
    while ( v1 );
    v40 = v32[1];
    *v2 = *v32;
    v41 = v32[2];
    v42 = *((_QWORD *)v32 + 6);
    v2[1] = v40;
    v2[2] = v41;
    *((_QWORD *)v2 + 6) = v42;
    v43 = v60;
    *v13 = v59;
    v44 = v61;
    v13[1] = v43;
    v45 = v62;
    v13[2] = v44;
    v46 = v63;
    v13[3] = v45;
    v47 = v64;
    v13[4] = v46;
    v48 = v65;
    v13[5] = v47;
    v49 = v66;
    v13[6] = v48;
    v50 = v13 + 8;
    *(v50 - 1) = v49;
    v51 = v68;
    *v50 = v67;
    v52 = v69;
    v50[1] = v51;
    v53 = v70;
    v50[2] = v52;
    v54 = v71;
    v50[3] = v53;
    v55 = v72;
    v56 = v73;
    v50[4] = v54;
    v50[5] = v55;
    *((_QWORD *)v50 + 12) = v56;
  }
  return (unsigned int)ActivationContext2;
}

```

## disassembly

```asm
0x180007a80  mov     rax, rsp
0x180007a83  mov     [rax+8], rbx
0x180007a87  mov     [rax+10h], rbp
0x180007a8b  mov     [rax+18h], rsi
0x180007a8f  mov     [rax+20h], rdi
0x180007a93  push    r14
0x180007a95  sub     rsp, 3E0h
0x180007a9c  mov     esi, 7
0x180007aa1  mov     rbx, rcx
0x180007aa4  mov     rax, rcx
0x180007aa7  mov     rbp, rdx
0x180007aaa  lea     rcx, [rsp+3E8h+var_3C8]
0x180007aaf  mov     r8d, esi
0x180007ab2  lea     r14d, [rsi+79h]
0x180007ab6  movups  xmm0, xmmword ptr [rax]
0x180007ab9  movups  xmm1, xmmword ptr [rax+10h]
0x180007abd  movups  xmmword ptr [rcx], xmm0
0x180007ac0  movups  xmm0, xmmword ptr [rax+20h]
0x180007ac4  movups  xmmword ptr [rcx+10h], xmm1
0x180007ac8  movups  xmm1, xmmword ptr [rax+30h]
0x180007acc  movups  xmmword ptr [rcx+20h], xmm0
0x180007ad0  movups  xmm0, xmmword ptr [rax+40h]
0x180007ad4  movups  xmmword ptr [rcx+30h], xmm1
0x180007ad8  movups  xmm1, xmmword ptr [rax+50h]
0x180007adc  movups  xmmword ptr [rcx+40h], xmm0
0x180007ae0  movups  xmm0, xmmword ptr [rax+60h]
0x180007ae4  movups  xmmword ptr [rcx+50h], xmm1
0x180007ae8  movups  xmm1, xmmword ptr [rax+70h]
0x180007aec  add     rax, r14
0x180007aef  movups  xmmword ptr [rcx+60h], xmm0
0x180007af3  add     rcx, r14
0x180007af6  movups  xmmword ptr [rcx-10h], xmm1
0x180007afa  sub     r8, 1
0x180007afe  jnz     short loc_180007AB6
0x180007b00  movups  xmm0, xmmword ptr [rax]
0x180007b03  lea     rdi, [rbx+40h]
0x180007b07  xor     edx, edx; Val
0x180007b09  movups  xmm1, xmmword ptr [rax+10h]
0x180007b0d  mov     r8d, 110h; Size
0x180007b13  movups  xmmword ptr [rcx], xmm0
0x180007b16  movups  xmm0, xmmword ptr [rax+20h]
0x180007b1a  mov     rax, [rax+30h]
0x180007b1e  movups  xmmword ptr [rcx+10h], xmm1
0x180007b22  movups  xmm1, xmmword ptr [rdi+10h]
0x180007b26  movups  xmmword ptr [rcx+20h], xmm0
0x180007b2a  mov     [rcx+30h], rax
0x180007b2e  lea     rcx, [rsp+3E8h+var_388]
0x180007b33  movups  xmm0, xmmword ptr [rdi]
0x180007b36  lea     rax, [r14+rdi]
0x180007b3a  movups  xmmword ptr [rcx], xmm0
0x180007b3d  movups  xmm0, xmmword ptr [rdi+20h]
0x180007b41  movups  xmmword ptr [rcx+10h], xmm1
0x180007b45  movups  xmm1, xmmword ptr [rdi+30h]
0x180007b49  movups  xmmword ptr [rcx+20h], xmm0
0x180007b4d  movups  xmm0, xmmword ptr [rdi+40h]
0x180007b51  movups  xmmword ptr [rcx+30h], xmm1
0x180007b55  movups  xmm1, xmmword ptr [rdi+50h]
0x180007b59  movups  xmmword ptr [rcx+40h], xmm0
0x180007b5d  movups  xmm0, xmmword ptr [rdi+60h]
0x180007b61  movups  xmmword ptr [rcx+50h], xmm1
0x180007b65  movups  xmm1, xmmword ptr [rdi+70h]
0x180007b69  movups  xmmword ptr [rcx+60h], xmm0
0x180007b6d  add     rcx, r14
0x180007b70  movups  xmm0, xmmword ptr [rax]
0x180007b73  movups  xmmword ptr [rcx-10h], xmm1
0x180007b77  movups  xmm1, xmmword ptr [rax+10h]
0x180007b7b  movups  xmmword ptr [rcx], xmm0
0x180007b7e  movups  xmm0, xmmword ptr [rax+20h]
0x180007b82  movups  xmmword ptr [rcx+10h], xmm1
0x180007b86  movups  xmm1, xmmword ptr [rax+30h]
0x180007b8a  movups  xmmword ptr [rcx+20h], xmm0
0x180007b8e  movups  xmm0, xmmword ptr [rax+40h]
0x180007b92  movups  xmmword ptr [rcx+30h], xmm1
0x180007b96  movups  xmm1, xmmword ptr [rax+50h]
0x180007b9a  mov     rax, [rax+60h]
0x180007b9e  movups  xmmword ptr [rcx+40h], xmm0
0x180007ba2  movups  xmmword ptr [rcx+50h], xmm1
0x180007ba6  mov     [rcx+60h], rax
0x180007baa  lea     rcx, [rsp+3E8h+var_2A0]; void *
0x180007bb2  call    memset_0
0x180007bb7  mov     rdx, rbp
0x180007bba  lea     rcx, [rsp+3E8h+var_3C8]
0x180007bbf  call    BaseSrvCreateActivationContext2
0x180007bc4  mov     ecx, eax
0x180007bc6  test    eax, eax
0x180007bc8  js      loc_180007CBA
0x180007bce  lea     rax, [rsp+3E8h+var_3C8]
0x180007bd3  movups  xmm0, xmmword ptr [rax]
0x180007bd6  movups  xmm1, xmmword ptr [rax+10h]
0x180007bda  movups  xmmword ptr [rbx], xmm0
0x180007bdd  movups  xmm0, xmmword ptr [rax+20h]
0x180007be1  movups  xmmword ptr [rbx+10h], xmm1
0x180007be5  movups  xmm1, xmmword ptr [rax+30h]
0x180007be9  movups  xmmword ptr [rbx+20h], xmm0
0x180007bed  movups  xmm0, xmmword ptr [rax+40h]
0x180007bf1  movups  xmmword ptr [rbx+30h], xmm1
0x180007bf5  movups  xmm1, xmmword ptr [rax+50h]
0x180007bf9  movups  xmmword ptr [rbx+40h], xmm0
0x180007bfd  movups  xmm0, xmmword ptr [rax+60h]
0x180007c01  movups  xmmword ptr [rbx+50h], xmm1
0x180007c05  movups  xmm1, xmmword ptr [rax+70h]
0x180007c09  add     rax, r14
0x180007c0c  movups  xmmword ptr [rbx+60h], xmm0
0x180007c10  add     rbx, r14
0x180007c13  movups  xmmword ptr [rbx-10h], xmm1
0x180007c17  sub     rsi, 1
0x180007c1b  jnz     short loc_180007BD3
0x180007c1d  movups  xmm0, xmmword ptr [rax]
0x180007c20  movups  xmm1, xmmword ptr [rax+10h]
0x180007c24  movups  xmmword ptr [rbx], xmm0
0x180007c27  movups  xmm0, xmmword ptr [rax+20h]
0x180007c2b  mov     rax, [rax+30h]
0x180007c2f  movups  xmmword ptr [rbx+10h], xmm1
0x180007c33  movups  xmmword ptr [rbx+20h], xmm0
0x180007c37  mov     [rbx+30h], rax
0x180007c3b  lea     rax, [rsp+3E8h+var_388]
0x180007c40  movups  xmm0, xmmword ptr [rax]
0x180007c43  movups  xmm1, xmmword ptr [rax+10h]
0x180007c47  movups  xmmword ptr [rdi], xmm0
0x180007c4a  movups  xmm0, xmmword ptr [rax+20h]
0x180007c4e  movups  xmmword ptr [rdi+10h], xmm1
0x180007c52  movups  xmm1, xmmword ptr [rax+30h]
0x180007c56  movups  xmmword ptr [rdi+20h], xmm0
0x180007c5a  movups  xmm0, xmmword ptr [rax+40h]
0x180007c5e  movups  xmmword ptr [rdi+30h], xmm1
0x180007c62  movups  xmm1, xmmword ptr [rax+50h]
0x180007c66  movups  xmmword ptr [rdi+40h], xmm0
0x180007c6a  movups  xmm0, xmmword ptr [rax+60h]
0x180007c6e  movups  xmmword ptr [rdi+50h], xmm1
0x180007c72  movups  xmm1, xmmword ptr [rax+70h]
0x180007c76  movups  xmmword ptr [rdi+60h], xmm0
0x180007c7a  add     rdi, r14
0x180007c7d  add     rax, r14
0x180007c80  movups  xmmword ptr [rdi-10h], xmm1
0x180007c84  movups  xmm0, xmmword ptr [rax]
0x180007c87  movups  xmm1, xmmword ptr [rax+10h]
0x180007c8b  movups  xmmword ptr [rdi], xmm0
0x180007c8e  movups  xmm0, xmmword ptr [rax+20h]
0x180007c92  movups  xmmword ptr [rdi+10h], xmm1
0x180007c96  movups  xmm1, xmmword ptr [rax+30h]
0x180007c9a  movups  xmmword ptr [rdi+20h], xmm0
0x180007c9e  movups  xmm0, xmmword ptr [rax+40h]
0x180007ca2  movups  xmmword ptr [rdi+30h], xmm1
0x180007ca6  movups  xmm1, xmmword ptr [rax+50h]
0x180007caa  mov     rax, [rax+60h]
0x180007cae  movups  xmmword ptr [rdi+40h], xmm0
0x180007cb2  movups  xmmword ptr [rdi+50h], xmm1
0x180007cb6  mov     [rdi+60h], rax
0x180007cba  lea     r11, [rsp+3E8h+var_8]
0x180007cc2  mov     eax, ecx
0x180007cc4  mov     rbx, [r11+10h]
0x180007cc8  mov     rbp, [r11+18h]
0x180007ccc  mov     rsi, [r11+20h]
0x180007cd0  mov     rdi, [r11+28h]
0x180007cd4  mov     rsp, r11
0x180007cd7  pop     r14
0x180007cd9  retn
```
