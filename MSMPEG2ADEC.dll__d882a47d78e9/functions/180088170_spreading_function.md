# spreading_function

- ea: `0x180088170`
- end: `0x18008853d`
- name: `spreading_function`
- size: `973`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18004cb00`

## pseudocode

```c
void __fastcall spreading_function(float *a1)
{
  double v1; // xmm4_8
  float v2; // xmm0_4
  float v3; // xmm2_4
  double v4; // xmm1_8
  float v5; // xmm3_4
  double v6; // xmm2_8
  double v7; // xmm3_8
  float v8; // xmm0_4
  double v9; // xmm1_8
  double v10; // xmm4_8
  float v11; // xmm0_4
  double v12; // xmm1_8
  double v13; // xmm2_8
  float v14; // xmm0_4
  double v15; // xmm1_8
  double v16; // xmm3_8
  float v17; // xmm0_4
  double v18; // xmm1_8
  double v19; // xmm4_8
  float v20; // xmm0_4
  double v21; // xmm1_8
  double v22; // xmm2_8
  float v23; // xmm0_4
  double v24; // xmm1_8
  double v25; // xmm3_8
  float v26; // xmm0_4
  double v27; // xmm1_8
  double v28; // xmm4_8
  float v29; // xmm0_4
  double v30; // xmm1_8
  double v31; // xmm2_8
  float v32; // xmm0_4
  double v33; // xmm1_8
  double v34; // xmm3_8
  float v35; // xmm0_4
  double v36; // xmm1_8
  double v37; // xmm4_8
  float v38; // xmm0_4
  double v39; // xmm1_8
  double v40; // xmm2_8
  float v41; // xmm0_4
  double v42; // xmm1_8
  double v43; // xmm3_8
  float v44; // xmm0_4
  double v45; // xmm1_8
  double v46; // xmm4_8
  float v47; // xmm0_4
  double v48; // xmm1_8
  double v49; // xmm2_8
  double v50; // xmm5_8
  float v51; // xmm0_4
  double v52; // xmm1_8
  double v53; // xmm3_8
  float v54; // xmm0_4
  double v55; // xmm1_8
  double v56; // xmm4_8
  float v57; // xmm0_4
  double v58; // xmm1_8
  double v59; // xmm2_8
  float v60; // xmm0_4
  double v61; // xmm1_8
  double v62; // xmm3_8
  float v63; // xmm0_4
  float v64; // xmm0_4
  double v65; // xmm1_8
  double v66; // xmm2_8
  float v67; // xmm0_4
  float v68; // xmm0_4

  v1 = a1[22];
  v2 = a1[23] * 0.0316 + a1[24] + v1 * 0.000316;
  v3 = a1[21];
  v4 = v1 * 0.0316 + a1[23];
  v5 = a1[20];
  a1[24] = v2;
  v6 = v3;
  v7 = v5;
  v8 = v4 + v6 * 0.000316;
  a1[23] = v8;
  v9 = v6 * 0.0316 + v1;
  v10 = a1[19];
  v11 = v9 + v7 * 0.000316;
  a1[22] = v11;
  v12 = v7 * 0.0316 + v6;
  v13 = a1[18];
  v14 = v12 + v10 * 0.000316;
  a1[21] = v14;
  v15 = v10 * 0.0316 + v7;
  v16 = a1[17];
  v17 = v15 + v13 * 0.000316;
  a1[20] = v17;
  v18 = v13 * 0.0316 + v10;
  v19 = a1[16];
  v20 = v18 + v16 * 0.000316;
  a1[19] = v20;
  v21 = v16 * 0.0316 + v13;
  v22 = a1[15];
  v23 = v21 + v19 * 0.000316;
  a1[18] = v23;
  v24 = v19 * 0.0316 + v16;
  v25 = a1[14];
  v26 = v24 + v22 * 0.000316;
  a1[17] = v26;
  v27 = v22 * 0.0316 + v19;
  v28 = a1[13];
  v29 = v27 + v25 * 0.000316;
  a1[16] = v29;
  v30 = v25 * 0.0316 + v22;
  v31 = a1[12];
  v32 = v30 + v28 * 0.000316;
  a1[15] = v32;
  v33 = v28 * 0.0316 + v25;
  v34 = a1[11];
  v35 = v33 + v31 * 0.000316;
  a1[14] = v35;
  v36 = v31 * 0.0316 + v28;
  v37 = a1[10];
  v38 = v36 + v34 * 0.000316;
  a1[13] = v38;
  v39 = v34 * 0.0316 + v31;
  v40 = a1[9];
  v41 = v39 + v37 * 0.000316;
  a1[12] = v41;
  v42 = v37 * 0.0316 + v34;
  v43 = a1[8];
  v44 = v42 + v40 * 0.000316;
  a1[11] = v44;
  v45 = v40 * 0.0316 + v37;
  v46 = a1[7];
  v47 = v45 + v43 * 0.000316;
  a1[10] = v47;
  v48 = v43 * 0.0316 + v40;
  v49 = a1[6];
  v50 = a1[4];
  v51 = v48 + v46 * 0.000316;
  a1[9] = v51;
  v52 = v46 * 0.0316 + v43;
  v53 = a1[5];
  v54 = v52 + v49 * 0.000316;
  a1[8] = v54;
  v55 = v49 * 0.0316 + v46;
  v56 = a1[2];
  v57 = v55 + v53 * 0.000316;
  a1[7] = v57;
  v58 = v53 * 0.0316 + v49;
  v59 = a1[3];
  v60 = v58 + v50 * 0.000316;
  a1[6] = v60;
  v61 = v50 * 0.0316 + v53;
  v62 = a1[1];
  v63 = v61 + v59 * 0.000316;
  a1[5] = v63;
  v64 = v59 * 0.0316 + v50 + v56 * 0.000316;
  a1[4] = v64;
  v65 = v56 * 0.0316 + v59;
  v66 = *a1;
  v67 = v65 + v62 * 0.000316;
  a1[3] = v67;
  v68 = v62 * 0.0316 + v56 + v66 * 0.000316;
  a1[2] = v68;
  a1[1] = v66 * 0.0316 + v62;
}

```

## disassembly

```asm
0x180088170  sub     rsp, 28h
0x180088174  movss   xmm3, dword ptr [rcx+5Ch]
0x180088179  movss   xmm4, dword ptr [rcx+58h]
0x18008817e  movss   xmm0, dword ptr [rcx+60h]
0x180088183  cvtps2pd xmm0, xmm0
0x180088186  cvtps2pd xmm4, xmm4
0x180088189  cvtps2pd xmm3, xmm3
0x18008818c  movaps  xmm1, xmm4
0x18008818f  movaps  [rsp+28h+var_18], xmm6
0x180088194  movsd   xmm6, cs:__real@3f34b599aa60913a
0x18008819c  movaps  xmm2, xmm3
0x18008819f  mulsd   xmm1, xmm6
0x1800881a3  movaps  [rsp+28h+var_28], xmm7
0x1800881a7  movsd   xmm7, cs:__real@3fa02de00d1b7176
0x1800881af  mulsd   xmm2, xmm7
0x1800881b3  addsd   xmm2, xmm0
0x1800881b7  addsd   xmm2, xmm1
0x1800881bb  movaps  xmm1, xmm4
0x1800881be  mulsd   xmm1, xmm7
0x1800881c2  cvtpd2ps xmm0, xmm2
0x1800881c6  movss   xmm2, dword ptr [rcx+54h]
0x1800881cb  addsd   xmm1, xmm3
0x1800881cf  movss   xmm3, dword ptr [rcx+50h]
0x1800881d4  movss   dword ptr [rcx+60h], xmm0
0x1800881d9  cvtps2pd xmm2, xmm2
0x1800881dc  cvtps2pd xmm3, xmm3
0x1800881df  movaps  xmm0, xmm2
0x1800881e2  mulsd   xmm0, xmm6
0x1800881e6  addsd   xmm1, xmm0
0x1800881ea  cvtpd2ps xmm0, xmm1
0x1800881ee  movaps  xmm1, xmm2
0x1800881f1  mulsd   xmm1, xmm7
0x1800881f5  movss   dword ptr [rcx+5Ch], xmm0
0x1800881fa  movaps  xmm0, xmm3
0x1800881fd  mulsd   xmm0, xmm6
0x180088201  addsd   xmm1, xmm4
0x180088205  movss   xmm4, dword ptr [rcx+4Ch]
0x18008820a  cvtps2pd xmm4, xmm4
0x18008820d  addsd   xmm1, xmm0
0x180088211  cvtpd2ps xmm0, xmm1
0x180088215  movaps  xmm1, xmm3
0x180088218  mulsd   xmm1, xmm7
0x18008821c  movss   dword ptr [rcx+58h], xmm0
0x180088221  movaps  xmm0, xmm4
0x180088224  mulsd   xmm0, xmm6
0x180088228  addsd   xmm1, xmm2
0x18008822c  movss   xmm2, dword ptr [rcx+48h]
0x180088231  cvtps2pd xmm2, xmm2
0x180088234  addsd   xmm1, xmm0
0x180088238  cvtpd2ps xmm0, xmm1
0x18008823c  movaps  xmm1, xmm4
0x18008823f  mulsd   xmm1, xmm7
0x180088243  movss   dword ptr [rcx+54h], xmm0
0x180088248  movaps  xmm0, xmm2
0x18008824b  mulsd   xmm0, xmm6
0x18008824f  addsd   xmm1, xmm3
0x180088253  movss   xmm3, dword ptr [rcx+44h]
0x180088258  cvtps2pd xmm3, xmm3
0x18008825b  addsd   xmm1, xmm0
0x18008825f  cvtpd2ps xmm0, xmm1
0x180088263  movaps  xmm1, xmm2
0x180088266  mulsd   xmm1, xmm7
0x18008826a  movss   dword ptr [rcx+50h], xmm0
0x18008826f  movaps  xmm0, xmm3
0x180088272  mulsd   xmm0, xmm6
0x180088276  addsd   xmm1, xmm4
0x18008827a  movss   xmm4, dword ptr [rcx+40h]
0x18008827f  cvtps2pd xmm4, xmm4
0x180088282  addsd   xmm1, xmm0
0x180088286  cvtpd2ps xmm0, xmm1
0x18008828a  movaps  xmm1, xmm3
0x18008828d  mulsd   xmm1, xmm7
0x180088291  movss   dword ptr [rcx+4Ch], xmm0
0x180088296  movaps  xmm0, xmm4
0x180088299  mulsd   xmm0, xmm6
0x18008829d  addsd   xmm1, xmm2
0x1800882a1  movss   xmm2, dword ptr [rcx+3Ch]
0x1800882a6  cvtps2pd xmm2, xmm2
0x1800882a9  addsd   xmm1, xmm0
0x1800882ad  cvtpd2ps xmm0, xmm1
0x1800882b1  movaps  xmm1, xmm4
0x1800882b4  movss   dword ptr [rcx+48h], xmm0
0x1800882b9  mulsd   xmm1, xmm7
0x1800882bd  movaps  xmm0, xmm2
0x1800882c0  mulsd   xmm0, xmm6
0x1800882c4  addsd   xmm1, xmm3
0x1800882c8  movss   xmm3, dword ptr [rcx+38h]
0x1800882cd  cvtps2pd xmm3, xmm3
0x1800882d0  addsd   xmm1, xmm0
0x1800882d4  cvtpd2ps xmm0, xmm1
0x1800882d8  movaps  xmm1, xmm2
0x1800882db  mulsd   xmm1, xmm7
0x1800882df  movss   dword ptr [rcx+44h], xmm0
0x1800882e4  movaps  xmm0, xmm3
0x1800882e7  mulsd   xmm0, xmm6
0x1800882eb  addsd   xmm1, xmm4
0x1800882ef  movss   xmm4, dword ptr [rcx+34h]
0x1800882f4  cvtps2pd xmm4, xmm4
0x1800882f7  addsd   xmm1, xmm0
0x1800882fb  cvtpd2ps xmm0, xmm1
0x1800882ff  movaps  xmm1, xmm3
0x180088302  mulsd   xmm1, xmm7
0x180088306  movss   dword ptr [rcx+40h], xmm0
0x18008830b  movaps  xmm0, xmm4
0x18008830e  mulsd   xmm0, xmm6
0x180088312  addsd   xmm1, xmm2
0x180088316  movss   xmm2, dword ptr [rcx+30h]
0x18008831b  cvtps2pd xmm2, xmm2
0x18008831e  addsd   xmm1, xmm0
0x180088322  cvtpd2ps xmm0, xmm1
0x180088326  movaps  xmm1, xmm4
0x180088329  mulsd   xmm1, xmm7
0x18008832d  movss   dword ptr [rcx+3Ch], xmm0
0x180088332  movaps  xmm0, xmm2
0x180088335  mulsd   xmm0, xmm6
0x180088339  addsd   xmm1, xmm3
0x18008833d  movss   xmm3, dword ptr [rcx+2Ch]
0x180088342  cvtps2pd xmm3, xmm3
0x180088345  addsd   xmm1, xmm0
0x180088349  cvtpd2ps xmm0, xmm1
0x18008834d  movaps  xmm1, xmm2
0x180088350  mulsd   xmm1, xmm7
0x180088354  movss   dword ptr [rcx+38h], xmm0
0x180088359  movaps  xmm0, xmm3
0x18008835c  mulsd   xmm0, xmm6
0x180088360  addsd   xmm1, xmm4
0x180088364  movss   xmm4, dword ptr [rcx+28h]
0x180088369  cvtps2pd xmm4, xmm4
0x18008836c  addsd   xmm1, xmm0
0x180088370  cvtpd2ps xmm0, xmm1
0x180088374  movaps  xmm1, xmm3
0x180088377  mulsd   xmm1, xmm7
0x18008837b  movss   dword ptr [rcx+34h], xmm0
0x180088380  movaps  xmm0, xmm4
0x180088383  mulsd   xmm0, xmm6
0x180088387  addsd   xmm1, xmm2
0x18008838b  movss   xmm2, dword ptr [rcx+24h]
0x180088390  cvtps2pd xmm2, xmm2
0x180088393  addsd   xmm1, xmm0
0x180088397  cvtpd2ps xmm0, xmm1
0x18008839b  movaps  xmm1, xmm4
0x18008839e  mulsd   xmm1, xmm7
0x1800883a2  movss   dword ptr [rcx+30h], xmm0
0x1800883a7  movaps  xmm0, xmm2
0x1800883aa  mulsd   xmm0, xmm6
0x1800883ae  addsd   xmm1, xmm3
0x1800883b2  movss   xmm3, dword ptr [rcx+20h]
0x1800883b7  cvtps2pd xmm3, xmm3
0x1800883ba  addsd   xmm1, xmm0
0x1800883be  cvtpd2ps xmm0, xmm1
0x1800883c2  movaps  xmm1, xmm2
0x1800883c5  mulsd   xmm1, xmm7
0x1800883c9  movss   dword ptr [rcx+2Ch], xmm0
0x1800883ce  movaps  xmm0, xmm3
0x1800883d1  mulsd   xmm0, xmm6
0x1800883d5  addsd   xmm1, xmm4
0x1800883d9  movss   xmm4, dword ptr [rcx+1Ch]
0x1800883de  cvtps2pd xmm4, xmm4
0x1800883e1  addsd   xmm1, xmm0
0x1800883e5  cvtpd2ps xmm0, xmm1
0x1800883e9  movaps  xmm1, xmm3
0x1800883ec  movss   dword ptr [rcx+28h], xmm0
0x1800883f1  mulsd   xmm1, xmm7
0x1800883f5  addsd   xmm1, xmm2
0x1800883f9  movss   xmm5, dword ptr [rcx+10h]
0x1800883fe  movss   xmm2, dword ptr [rcx+18h]
0x180088403  movaps  xmm0, xmm4
0x180088406  mulsd   xmm0, xmm6
0x18008840a  cvtps2pd xmm2, xmm2
0x18008840d  addsd   xmm1, xmm0
0x180088411  cvtps2pd xmm5, xmm5
0x180088414  cvtpd2ps xmm0, xmm1
0x180088418  movaps  xmm1, xmm4
0x18008841b  mulsd   xmm1, xmm7
0x18008841f  movss   dword ptr [rcx+24h], xmm0
0x180088424  movaps  xmm0, xmm2
0x180088427  mulsd   xmm0, xmm6
0x18008842b  addsd   xmm1, xmm3
0x18008842f  movss   xmm3, dword ptr [rcx+14h]
0x180088434  cvtps2pd xmm3, xmm3
0x180088437  addsd   xmm1, xmm0
0x18008843b  cvtpd2ps xmm0, xmm1
0x18008843f  movaps  xmm1, xmm2
0x180088442  mulsd   xmm1, xmm7
0x180088446  movss   dword ptr [rcx+20h], xmm0
0x18008844b  movaps  xmm0, xmm3
0x18008844e  mulsd   xmm0, xmm6
0x180088452  addsd   xmm1, xmm4
0x180088456  movss   xmm4, dword ptr [rcx+8]
0x18008845b  cvtps2pd xmm4, xmm4
0x18008845e  addsd   xmm1, xmm0
0x180088462  cvtpd2ps xmm0, xmm1
0x180088466  movaps  xmm1, xmm3
0x180088469  mulsd   xmm1, xmm7
0x18008846d  movss   dword ptr [rcx+1Ch], xmm0
0x180088472  movaps  xmm0, xmm5
0x180088475  mulsd   xmm0, xmm6
0x180088479  addsd   xmm1, xmm2
0x18008847d  movss   xmm2, dword ptr [rcx+0Ch]
0x180088482  cvtps2pd xmm2, xmm2
0x180088485  addsd   xmm1, xmm0
0x180088489  cvtpd2ps xmm0, xmm1
0x18008848d  movaps  xmm1, xmm5
0x180088490  mulsd   xmm1, xmm7
0x180088494  movss   dword ptr [rcx+18h], xmm0
0x180088499  movaps  xmm0, xmm2
0x18008849c  mulsd   xmm0, xmm6
0x1800884a0  addsd   xmm1, xmm3
0x1800884a4  movss   xmm3, dword ptr [rcx+4]
0x1800884a9  cvtps2pd xmm3, xmm3
0x1800884ac  addsd   xmm1, xmm0
0x1800884b0  cvtpd2ps xmm0, xmm1
0x1800884b4  movaps  xmm1, xmm2
0x1800884b7  mulsd   xmm1, xmm7
0x1800884bb  movss   dword ptr [rcx+14h], xmm0
0x1800884c0  movaps  xmm0, xmm4
0x1800884c3  mulsd   xmm0, xmm6
0x1800884c7  addsd   xmm1, xmm5
0x1800884cb  addsd   xmm1, xmm0
0x1800884cf  cvtpd2ps xmm0, xmm1
0x1800884d3  movaps  xmm1, xmm4
0x1800884d6  mulsd   xmm1, xmm7
0x1800884da  movss   dword ptr [rcx+10h], xmm0
0x1800884df  movaps  xmm0, xmm3
0x1800884e2  mulsd   xmm0, xmm6
0x1800884e6  addsd   xmm1, xmm2
0x1800884ea  movss   xmm2, dword ptr [rcx]
0x1800884ee  cvtps2pd xmm2, xmm2
0x1800884f1  addsd   xmm1, xmm0
0x1800884f5  cvtpd2ps xmm0, xmm1
0x1800884f9  movaps  xmm1, xmm3
0x1800884fc  movss   dword ptr [rcx+0Ch], xmm0
0x180088501  movaps  xmm0, xmm2
0x180088504  mulsd   xmm0, xmm6
0x180088508  movaps  xmm6, [rsp+28h+var_18]
0x18008850d  mulsd   xmm1, xmm7
0x180088511  mulsd   xmm2, xmm7
0x180088515  addsd   xmm1, xmm4
0x180088519  addsd   xmm2, xmm3
0x18008851d  addsd   xmm1, xmm0
0x180088521  cvtpd2ps xmm0, xmm1
0x180088525  movss   dword ptr [rcx+8], xmm0
0x18008852a  cvtpd2ps xmm0, xmm2
0x18008852e  movss   dword ptr [rcx+4], xmm0
0x180088533  movaps  xmm7, [rsp+28h+var_28]
0x180088537  add     rsp, 28h
0x18008853b  retn
```
