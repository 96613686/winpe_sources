# spreading_function

- ea: `0x180002820`
- end: `0x180002bec`
- name: `spreading_function`
- size: `972`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002110`

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
0x180002820  sub     rsp, 28h
0x180002824  movss   xmm3, dword ptr [rcx+5Ch]
0x180002829  movss   xmm4, dword ptr [rcx+58h]
0x18000282e  movss   xmm0, dword ptr [rcx+60h]
0x180002833  cvtps2pd xmm0, xmm0
0x180002836  cvtps2pd xmm4, xmm4
0x180002839  cvtps2pd xmm3, xmm3
0x18000283c  movaps  xmm1, xmm4
0x18000283f  movaps  [rsp+28h+var_18], xmm6
0x180002844  movsd   xmm6, cs:__real@3f34b599aa60913a
0x18000284c  movaps  xmm2, xmm3
0x18000284f  mulsd   xmm1, xmm6
0x180002853  movaps  [rsp+28h+var_28], xmm7
0x180002857  movsd   xmm7, cs:__real@3fa02de00d1b7176
0x18000285f  mulsd   xmm2, xmm7
0x180002863  addsd   xmm2, xmm0
0x180002867  addsd   xmm2, xmm1
0x18000286b  movaps  xmm1, xmm4
0x18000286e  mulsd   xmm1, xmm7
0x180002872  cvtpd2ps xmm0, xmm2
0x180002876  movss   xmm2, dword ptr [rcx+54h]
0x18000287b  addsd   xmm1, xmm3
0x18000287f  movss   xmm3, dword ptr [rcx+50h]
0x180002884  movss   dword ptr [rcx+60h], xmm0
0x180002889  cvtps2pd xmm2, xmm2
0x18000288c  cvtps2pd xmm3, xmm3
0x18000288f  movaps  xmm0, xmm2
0x180002892  mulsd   xmm0, xmm6
0x180002896  addsd   xmm1, xmm0
0x18000289a  cvtpd2ps xmm0, xmm1
0x18000289e  movaps  xmm1, xmm2
0x1800028a1  mulsd   xmm1, xmm7
0x1800028a5  movss   dword ptr [rcx+5Ch], xmm0
0x1800028aa  movaps  xmm0, xmm3
0x1800028ad  mulsd   xmm0, xmm6
0x1800028b1  addsd   xmm1, xmm4
0x1800028b5  movss   xmm4, dword ptr [rcx+4Ch]
0x1800028ba  cvtps2pd xmm4, xmm4
0x1800028bd  addsd   xmm1, xmm0
0x1800028c1  cvtpd2ps xmm0, xmm1
0x1800028c5  movaps  xmm1, xmm3
0x1800028c8  mulsd   xmm1, xmm7
0x1800028cc  movss   dword ptr [rcx+58h], xmm0
0x1800028d1  movaps  xmm0, xmm4
0x1800028d4  mulsd   xmm0, xmm6
0x1800028d8  addsd   xmm1, xmm2
0x1800028dc  movss   xmm2, dword ptr [rcx+48h]
0x1800028e1  cvtps2pd xmm2, xmm2
0x1800028e4  addsd   xmm1, xmm0
0x1800028e8  cvtpd2ps xmm0, xmm1
0x1800028ec  movaps  xmm1, xmm4
0x1800028ef  mulsd   xmm1, xmm7
0x1800028f3  movss   dword ptr [rcx+54h], xmm0
0x1800028f8  movaps  xmm0, xmm2
0x1800028fb  mulsd   xmm0, xmm6
0x1800028ff  addsd   xmm1, xmm3
0x180002903  movss   xmm3, dword ptr [rcx+44h]
0x180002908  cvtps2pd xmm3, xmm3
0x18000290b  addsd   xmm1, xmm0
0x18000290f  cvtpd2ps xmm0, xmm1
0x180002913  movaps  xmm1, xmm2
0x180002916  mulsd   xmm1, xmm7
0x18000291a  movss   dword ptr [rcx+50h], xmm0
0x18000291f  movaps  xmm0, xmm3
0x180002922  mulsd   xmm0, xmm6
0x180002926  addsd   xmm1, xmm4
0x18000292a  movss   xmm4, dword ptr [rcx+40h]
0x18000292f  cvtps2pd xmm4, xmm4
0x180002932  addsd   xmm1, xmm0
0x180002936  cvtpd2ps xmm0, xmm1
0x18000293a  movaps  xmm1, xmm3
0x18000293d  mulsd   xmm1, xmm7
0x180002941  movss   dword ptr [rcx+4Ch], xmm0
0x180002946  movaps  xmm0, xmm4
0x180002949  mulsd   xmm0, xmm6
0x18000294d  addsd   xmm1, xmm2
0x180002951  movss   xmm2, dword ptr [rcx+3Ch]
0x180002956  cvtps2pd xmm2, xmm2
0x180002959  addsd   xmm1, xmm0
0x18000295d  cvtpd2ps xmm0, xmm1
0x180002961  movaps  xmm1, xmm4
0x180002964  movss   dword ptr [rcx+48h], xmm0
0x180002969  mulsd   xmm1, xmm7
0x18000296d  movaps  xmm0, xmm2
0x180002970  mulsd   xmm0, xmm6
0x180002974  addsd   xmm1, xmm3
0x180002978  movss   xmm3, dword ptr [rcx+38h]
0x18000297d  cvtps2pd xmm3, xmm3
0x180002980  addsd   xmm1, xmm0
0x180002984  cvtpd2ps xmm0, xmm1
0x180002988  movaps  xmm1, xmm2
0x18000298b  mulsd   xmm1, xmm7
0x18000298f  movss   dword ptr [rcx+44h], xmm0
0x180002994  movaps  xmm0, xmm3
0x180002997  mulsd   xmm0, xmm6
0x18000299b  addsd   xmm1, xmm4
0x18000299f  movss   xmm4, dword ptr [rcx+34h]
0x1800029a4  cvtps2pd xmm4, xmm4
0x1800029a7  addsd   xmm1, xmm0
0x1800029ab  cvtpd2ps xmm0, xmm1
0x1800029af  movaps  xmm1, xmm3
0x1800029b2  mulsd   xmm1, xmm7
0x1800029b6  movss   dword ptr [rcx+40h], xmm0
0x1800029bb  movaps  xmm0, xmm4
0x1800029be  mulsd   xmm0, xmm6
0x1800029c2  addsd   xmm1, xmm2
0x1800029c6  movss   xmm2, dword ptr [rcx+30h]
0x1800029cb  cvtps2pd xmm2, xmm2
0x1800029ce  addsd   xmm1, xmm0
0x1800029d2  cvtpd2ps xmm0, xmm1
0x1800029d6  movaps  xmm1, xmm4
0x1800029d9  mulsd   xmm1, xmm7
0x1800029dd  movss   dword ptr [rcx+3Ch], xmm0
0x1800029e2  movaps  xmm0, xmm2
0x1800029e5  mulsd   xmm0, xmm6
0x1800029e9  addsd   xmm1, xmm3
0x1800029ed  movss   xmm3, dword ptr [rcx+2Ch]
0x1800029f2  cvtps2pd xmm3, xmm3
0x1800029f5  addsd   xmm1, xmm0
0x1800029f9  cvtpd2ps xmm0, xmm1
0x1800029fd  movaps  xmm1, xmm2
0x180002a00  mulsd   xmm1, xmm7
0x180002a04  movss   dword ptr [rcx+38h], xmm0
0x180002a09  movaps  xmm0, xmm3
0x180002a0c  mulsd   xmm0, xmm6
0x180002a10  addsd   xmm1, xmm4
0x180002a14  movss   xmm4, dword ptr [rcx+28h]
0x180002a19  cvtps2pd xmm4, xmm4
0x180002a1c  addsd   xmm1, xmm0
0x180002a20  cvtpd2ps xmm0, xmm1
0x180002a24  movaps  xmm1, xmm3
0x180002a27  mulsd   xmm1, xmm7
0x180002a2b  movss   dword ptr [rcx+34h], xmm0
0x180002a30  movaps  xmm0, xmm4
0x180002a33  mulsd   xmm0, xmm6
0x180002a37  addsd   xmm1, xmm2
0x180002a3b  movss   xmm2, dword ptr [rcx+24h]
0x180002a40  cvtps2pd xmm2, xmm2
0x180002a43  addsd   xmm1, xmm0
0x180002a47  cvtpd2ps xmm0, xmm1
0x180002a4b  movaps  xmm1, xmm4
0x180002a4e  mulsd   xmm1, xmm7
0x180002a52  movss   dword ptr [rcx+30h], xmm0
0x180002a57  movaps  xmm0, xmm2
0x180002a5a  mulsd   xmm0, xmm6
0x180002a5e  addsd   xmm1, xmm3
0x180002a62  movss   xmm3, dword ptr [rcx+20h]
0x180002a67  cvtps2pd xmm3, xmm3
0x180002a6a  addsd   xmm1, xmm0
0x180002a6e  cvtpd2ps xmm0, xmm1
0x180002a72  movaps  xmm1, xmm2
0x180002a75  mulsd   xmm1, xmm7
0x180002a79  movss   dword ptr [rcx+2Ch], xmm0
0x180002a7e  movaps  xmm0, xmm3
0x180002a81  mulsd   xmm0, xmm6
0x180002a85  addsd   xmm1, xmm4
0x180002a89  movss   xmm4, dword ptr [rcx+1Ch]
0x180002a8e  cvtps2pd xmm4, xmm4
0x180002a91  addsd   xmm1, xmm0
0x180002a95  cvtpd2ps xmm0, xmm1
0x180002a99  movaps  xmm1, xmm3
0x180002a9c  movss   dword ptr [rcx+28h], xmm0
0x180002aa1  mulsd   xmm1, xmm7
0x180002aa5  addsd   xmm1, xmm2
0x180002aa9  movss   xmm5, dword ptr [rcx+10h]
0x180002aae  movss   xmm2, dword ptr [rcx+18h]
0x180002ab3  movaps  xmm0, xmm4
0x180002ab6  mulsd   xmm0, xmm6
0x180002aba  cvtps2pd xmm2, xmm2
0x180002abd  addsd   xmm1, xmm0
0x180002ac1  cvtps2pd xmm5, xmm5
0x180002ac4  cvtpd2ps xmm0, xmm1
0x180002ac8  movaps  xmm1, xmm4
0x180002acb  mulsd   xmm1, xmm7
0x180002acf  movss   dword ptr [rcx+24h], xmm0
0x180002ad4  movaps  xmm0, xmm2
0x180002ad7  mulsd   xmm0, xmm6
0x180002adb  addsd   xmm1, xmm3
0x180002adf  movss   xmm3, dword ptr [rcx+14h]
0x180002ae4  cvtps2pd xmm3, xmm3
0x180002ae7  addsd   xmm1, xmm0
0x180002aeb  cvtpd2ps xmm0, xmm1
0x180002aef  movaps  xmm1, xmm2
0x180002af2  mulsd   xmm1, xmm7
0x180002af6  movss   dword ptr [rcx+20h], xmm0
0x180002afb  movaps  xmm0, xmm3
0x180002afe  mulsd   xmm0, xmm6
0x180002b02  addsd   xmm1, xmm4
0x180002b06  movss   xmm4, dword ptr [rcx+8]
0x180002b0b  cvtps2pd xmm4, xmm4
0x180002b0e  addsd   xmm1, xmm0
0x180002b12  cvtpd2ps xmm0, xmm1
0x180002b16  movaps  xmm1, xmm3
0x180002b19  mulsd   xmm1, xmm7
0x180002b1d  movss   dword ptr [rcx+1Ch], xmm0
0x180002b22  movaps  xmm0, xmm5
0x180002b25  mulsd   xmm0, xmm6
0x180002b29  addsd   xmm1, xmm2
0x180002b2d  movss   xmm2, dword ptr [rcx+0Ch]
0x180002b32  cvtps2pd xmm2, xmm2
0x180002b35  addsd   xmm1, xmm0
0x180002b39  cvtpd2ps xmm0, xmm1
0x180002b3d  movaps  xmm1, xmm5
0x180002b40  mulsd   xmm1, xmm7
0x180002b44  movss   dword ptr [rcx+18h], xmm0
0x180002b49  movaps  xmm0, xmm2
0x180002b4c  mulsd   xmm0, xmm6
0x180002b50  addsd   xmm1, xmm3
0x180002b54  movss   xmm3, dword ptr [rcx+4]
0x180002b59  cvtps2pd xmm3, xmm3
0x180002b5c  addsd   xmm1, xmm0
0x180002b60  cvtpd2ps xmm0, xmm1
0x180002b64  movaps  xmm1, xmm2
0x180002b67  mulsd   xmm1, xmm7
0x180002b6b  movss   dword ptr [rcx+14h], xmm0
0x180002b70  movaps  xmm0, xmm4
0x180002b73  mulsd   xmm0, xmm6
0x180002b77  addsd   xmm1, xmm5
0x180002b7b  addsd   xmm1, xmm0
0x180002b7f  cvtpd2ps xmm0, xmm1
0x180002b83  movaps  xmm1, xmm4
0x180002b86  mulsd   xmm1, xmm7
0x180002b8a  movss   dword ptr [rcx+10h], xmm0
0x180002b8f  movaps  xmm0, xmm3
0x180002b92  mulsd   xmm0, xmm6
0x180002b96  addsd   xmm1, xmm2
0x180002b9a  movss   xmm2, dword ptr [rcx]
0x180002b9e  cvtps2pd xmm2, xmm2
0x180002ba1  addsd   xmm1, xmm0
0x180002ba5  cvtpd2ps xmm0, xmm1
0x180002ba9  movaps  xmm1, xmm3
0x180002bac  movss   dword ptr [rcx+0Ch], xmm0
0x180002bb1  movaps  xmm0, xmm2
0x180002bb4  mulsd   xmm0, xmm6
0x180002bb8  movaps  xmm6, [rsp+28h+var_18]
0x180002bbd  mulsd   xmm1, xmm7
0x180002bc1  mulsd   xmm2, xmm7
0x180002bc5  addsd   xmm1, xmm4
0x180002bc9  addsd   xmm2, xmm3
0x180002bcd  addsd   xmm1, xmm0
0x180002bd1  cvtpd2ps xmm0, xmm1
0x180002bd5  movss   dword ptr [rcx+8], xmm0
0x180002bda  cvtpd2ps xmm0, xmm2
0x180002bde  movss   dword ptr [rcx+4], xmm0
0x180002be3  movaps  xmm7, [rsp+28h+var_28]
0x180002be7  add     rsp, 28h
0x180002beb  retn
```
