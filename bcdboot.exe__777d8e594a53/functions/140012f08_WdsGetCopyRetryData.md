# WdsGetCopyRetryData

- ea: `0x140012f08`
- end: `0x140013270`
- name: `WdsGetCopyRetryData`
- size: `872`
- prototype: `__int64 __fastcall(int, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140012cec`

## callees

- `0x140012f08`

## pseudocode

```c
__int64 __fastcall WdsGetCopyRetryData(int a1, _DWORD *a2, _DWORD *a3)
{
  __int64 result; // rax
  unsigned int v5; // edx
  int v6; // [rsp+0h] [rbp-100h]
  int v7; // [rsp+4h] [rbp-FCh]
  _DWORD v8[126]; // [rsp+8h] [rbp-F8h]

  result = 0;
  v8[1] = 1743;
  v8[2] = 6;
  v8[5] = 1744;
  v8[6] = 53;
  v8[0] = 5000;
  v6 = 5;
  v7 = 5;
  v8[3] = 5;
  v8[7] = 5;
  v8[11] = 5;
  v8[15] = 5;
  v8[19] = 5;
  v8[23] = 5;
  v8[27] = 5;
  v8[31] = 5;
  v8[35] = 5;
  v8[39] = 5;
  v8[43] = 5;
  v8[47] = 5;
  v8[51] = 5;
  v8[55] = 5;
  v8[59] = 5;
  v8[63] = 5;
  v8[67] = 5;
  v8[71] = 5;
  v8[4] = 5000;
  v8[8] = 5000;
  v8[9] = 1745;
  v8[10] = 67;
  v8[12] = 5000;
  v8[13] = 1746;
  v8[14] = 58;
  v8[16] = 5000;
  v8[17] = 1747;
  v8[18] = 1204;
  v8[20] = 5000;
  v8[21] = 1748;
  v8[22] = 1351;
  v8[24] = 5000;
  v8[25] = 1749;
  v8[26] = 1236;
  v8[28] = 5000;
  v8[29] = 1750;
  v8[30] = 1229;
  v8[32] = 5000;
  v8[33] = 1751;
  v8[34] = 1225;
  v8[36] = 5000;
  v8[37] = 1752;
  v8[38] = 1226;
  v8[40] = 5000;
  v8[41] = 1753;
  v8[42] = 1256;
  v8[44] = 5000;
  v8[45] = 1754;
  v8[46] = 1232;
  v8[48] = 5000;
  v8[49] = 1755;
  v8[50] = 1326;
  v8[52] = 5000;
  v8[53] = 1756;
  v8[54] = 64;
  v8[56] = 5000;
  v8[57] = 1757;
  v8[58] = 65;
  v8[60] = 5000;
  v8[61] = 1758;
  v8[62] = 1231;
  v8[64] = 5000;
  v8[65] = 1759;
  v8[66] = 1203;
  v8[68] = 5000;
  v8[69] = 1760;
  v8[70] = 1222;
  v8[72] = 5000;
  v8[73] = 1761;
  v8[76] = 5000;
  v8[80] = 5000;
  v8[84] = 5000;
  v8[88] = 5000;
  v8[92] = 5000;
  v8[96] = 20000;
  v8[100] = 20000;
  v8[104] = 20000;
  v8[108] = 20000;
  v8[75] = 5;
  v8[79] = 5;
  v8[83] = 5;
  v8[87] = 5;
  v8[91] = 5;
  v8[95] = 5;
  v8[99] = 5;
  v8[103] = 5;
  v8[107] = 5;
  v8[111] = 5;
  v8[115] = 5;
  v8[119] = 5;
  v8[123] = 5;
  v5 = 0;
  v8[112] = 500;
  v8[116] = 500;
  v8[120] = 500;
  v8[124] = 500;
  v8[74] = 1234;
  v8[77] = 1762;
  v8[78] = 71;
  v8[81] = 1763;
  v8[82] = 121;
  v8[85] = 1764;
  v8[86] = 32;
  v8[89] = 1765;
  v8[90] = 59;
  v8[93] = 1766;
  v8[94] = 1238;
  v8[97] = 1767;
  v8[98] = 54;
  v8[101] = 1768;
  v8[102] = 1130;
  v8[105] = 1769;
  v8[106] = 1220;
  v8[109] = 1770;
  v8[110] = 23;
  v8[113] = 1771;
  v8[114] = 1392;
  v8[117] = 1772;
  v8[118] = 577;
  v8[121] = 1773;
  v8[122] = 1117;
  v8[125] = 1806;
  do
  {
    if ( (_DWORD)result )
      break;
    if ( *(&v6 + 4 * v5) == a1 )
    {
      if ( a2 )
        *a2 = v8[4 * v5 - 1];
      if ( a3 )
        *a3 = v8[4 * v5];
      result = 1;
    }
    ++v5;
  }
  while ( v5 < 0x20 );
  return result;
}

```

## disassembly

```asm
0x140012f08  push    rbp
0x140012f0a  lea     rbp, [rsp-100h]
0x140012f12  sub     rsp, 200h
0x140012f19  xor     eax, eax
0x140012f1b  mov     [rsp+200h+var_1F4], 6CFh
0x140012f23  mov     r9, rdx
0x140012f26  mov     [rsp+200h+var_1F0], 6
0x140012f2e  mov     r10d, ecx
0x140012f31  mov     [rsp+200h+var_1E4], 6D0h
0x140012f39  mov     ecx, 1388h
0x140012f3e  mov     [rsp+200h+var_1E0], 35h ; '5'
0x140012f46  lea     edx, [rax+5]
0x140012f49  mov     [rsp+200h+var_1F8], ecx
0x140012f4d  mov     [rsp+200h+var_200], edx
0x140012f50  mov     [rsp+200h+var_1FC], edx
0x140012f54  mov     [rsp+200h+var_1EC], edx
0x140012f58  mov     [rsp+200h+var_1DC], edx
0x140012f5c  mov     [rsp+200h+var_1CC], edx
0x140012f60  mov     [rsp+200h+var_1BC], edx
0x140012f64  mov     [rsp+200h+var_1AC], edx
0x140012f68  mov     [rsp+200h+var_19C], edx
0x140012f6c  mov     [rsp+200h+var_18C], edx
0x140012f70  mov     [rbp+100h+var_17C], edx
0x140012f73  mov     [rbp+100h+var_16C], edx
0x140012f76  mov     [rbp+100h+var_15C], edx
0x140012f79  mov     [rbp+100h+var_14C], edx
0x140012f7c  mov     [rbp+100h+var_13C], edx
0x140012f7f  mov     [rbp+100h+var_12C], edx
0x140012f82  mov     [rbp+100h+var_11C], edx
0x140012f85  mov     [rbp+100h+var_10C], edx
0x140012f88  mov     [rbp+100h+var_FC], edx
0x140012f8b  mov     [rbp+100h+var_EC], edx
0x140012f8e  mov     [rbp+100h+var_DC], edx
0x140012f91  mov     [rsp+200h+var_1E8], ecx
0x140012f95  mov     [rsp+200h+var_1D8], ecx
0x140012f99  mov     [rsp+200h+var_1D4], 6D1h
0x140012fa1  mov     [rsp+200h+var_1D0], 43h ; 'C'
0x140012fa9  mov     [rsp+200h+var_1C8], ecx
0x140012fad  mov     [rsp+200h+var_1C4], 6D2h
0x140012fb5  mov     [rsp+200h+var_1C0], 3Ah ; ':'
0x140012fbd  mov     [rsp+200h+var_1B8], ecx
0x140012fc1  mov     [rsp+200h+var_1B4], 6D3h
0x140012fc9  mov     [rsp+200h+var_1B0], 4B4h
0x140012fd1  mov     [rsp+200h+var_1A8], ecx
0x140012fd5  mov     [rsp+200h+var_1A4], 6D4h
0x140012fdd  mov     [rsp+200h+var_1A0], 547h
0x140012fe5  mov     [rsp+200h+var_198], ecx
0x140012fe9  mov     [rsp+200h+var_194], 6D5h
0x140012ff1  mov     [rsp+200h+var_190], 4D4h
0x140012ff9  mov     [rsp+200h+var_188], ecx
0x140012ffd  mov     [rsp+200h+var_184], 6D6h
0x140013005  mov     [rbp+100h+var_180], 4CDh
0x14001300c  mov     [rbp+100h+var_178], ecx
0x14001300f  mov     [rbp+100h+var_174], 6D7h
0x140013016  mov     [rbp+100h+var_170], 4C9h
0x14001301d  mov     [rbp+100h+var_168], ecx
0x140013020  mov     [rbp+100h+var_164], 6D8h
0x140013027  mov     [rbp+100h+var_160], 4CAh
0x14001302e  mov     [rbp+100h+var_158], ecx
0x140013031  mov     [rbp+100h+var_154], 6D9h
0x140013038  mov     [rbp+100h+var_150], 4E8h
0x14001303f  mov     [rbp+100h+var_148], ecx
0x140013042  mov     [rbp+100h+var_144], 6DAh
0x140013049  mov     [rbp+100h+var_140], 4D0h
0x140013050  mov     [rbp+100h+var_138], ecx
0x140013053  mov     [rbp+100h+var_134], 6DBh
0x14001305a  mov     [rbp+100h+var_130], 52Eh
0x140013061  mov     [rbp+100h+var_128], ecx
0x140013064  mov     [rbp+100h+var_124], 6DCh
0x14001306b  mov     [rbp+100h+var_120], 40h ; '@'
0x140013072  mov     [rbp+100h+var_118], ecx
0x140013075  mov     [rbp+100h+var_114], 6DDh
0x14001307c  mov     [rbp+100h+var_110], 41h ; 'A'
0x140013083  mov     [rbp+100h+var_108], ecx
0x140013086  mov     [rbp+100h+var_104], 6DEh
0x14001308d  mov     [rbp+100h+var_100], 4CFh
0x140013094  mov     [rbp+100h+var_F8], ecx
0x140013097  mov     [rbp+100h+var_F4], 6DFh
0x14001309e  mov     [rbp+100h+var_F0], 4B3h
0x1400130a5  mov     [rbp+100h+var_E8], ecx
0x1400130a8  mov     [rbp+100h+var_E4], 6E0h
0x1400130af  mov     [rbp+100h+var_E0], 4C6h
0x1400130b6  mov     [rbp+100h+var_D8], ecx
0x1400130b9  mov     [rbp+100h+var_D4], 6E1h
0x1400130c0  mov     [rbp+100h+var_C8], ecx
0x1400130c3  mov     [rbp+100h+var_B8], ecx
0x1400130c6  mov     [rbp+100h+var_A8], ecx
0x1400130c9  mov     [rbp+100h+var_98], ecx
0x1400130cc  mov     [rbp+100h+var_88], ecx
0x1400130cf  mov     ecx, 4E20h
0x1400130d4  mov     [rbp+100h+var_78], ecx
0x1400130da  mov     [rbp+100h+var_68], ecx
0x1400130e0  mov     [rbp+100h+var_58], ecx
0x1400130e6  mov     [rbp+100h+var_48], ecx
0x1400130ec  mov     ecx, 1F4h
0x1400130f1  mov     [rbp+100h+var_CC], edx
0x1400130f4  mov     [rbp+100h+var_BC], edx
0x1400130f7  mov     [rbp+100h+var_AC], edx
0x1400130fa  mov     [rbp+100h+var_9C], edx
0x1400130fd  mov     [rbp+100h+var_8C], edx
0x140013100  mov     [rbp+100h+var_7C], edx
0x140013106  mov     [rbp+100h+var_6C], edx
0x14001310c  mov     [rbp+100h+var_5C], edx
0x140013112  mov     [rbp+100h+var_4C], edx
0x140013118  mov     [rbp+100h+var_3C], edx
0x14001311e  mov     [rbp+100h+var_2C], edx
0x140013124  mov     [rbp+100h+var_1C], edx
0x14001312a  mov     [rbp+100h+var_C], edx
0x140013130  xor     edx, edx
0x140013132  mov     [rbp+100h+var_38], ecx
0x140013138  mov     [rbp+100h+var_28], ecx
0x14001313e  mov     [rbp+100h+var_18], ecx
0x140013144  mov     [rbp+100h+var_8], ecx
0x14001314a  mov     [rbp+100h+var_D0], 4D2h
0x140013151  mov     [rbp+100h+var_C4], 6E2h
0x140013158  mov     [rbp+100h+var_C0], 47h ; 'G'
0x14001315f  mov     [rbp+100h+var_B4], 6E3h
0x140013166  mov     [rbp+100h+var_B0], 79h ; 'y'
0x14001316d  mov     [rbp+100h+var_A4], 6E4h
0x140013174  mov     [rbp+100h+var_A0], 20h ; ' '
0x14001317b  mov     [rbp+100h+var_94], 6E5h
0x140013182  mov     [rbp+100h+var_90], 3Bh ; ';'
0x140013189  mov     [rbp+100h+var_84], 6E6h
0x140013190  mov     [rbp+100h+var_80], 4D6h
0x14001319a  mov     [rbp+100h+var_74], 6E7h
0x1400131a4  mov     [rbp+100h+var_70], 36h ; '6'
0x1400131ae  mov     [rbp+100h+var_64], 6E8h
0x1400131b8  mov     [rbp+100h+var_60], 46Ah
0x1400131c2  mov     [rbp+100h+var_54], 6E9h
0x1400131cc  mov     [rbp+100h+var_50], 4C4h
0x1400131d6  mov     [rbp+100h+var_44], 6EAh
0x1400131e0  mov     [rbp+100h+var_40], 17h
0x1400131ea  mov     [rbp+100h+var_34], 6EBh
0x1400131f4  mov     [rbp+100h+var_30], 570h
0x1400131fe  mov     [rbp+100h+var_24], 6ECh
0x140013208  mov     [rbp+100h+var_20], 241h
0x140013212  mov     [rbp+100h+var_14], 6EDh
0x14001321c  mov     [rbp+100h+var_10], 45Dh
0x140013226  mov     [rbp+100h+var_4], 70Eh
0x140013230  test    eax, eax
0x140013232  jnz     short loc_140013267
0x140013234  mov     ecx, edx
0x140013236  add     rcx, rcx
0x140013239  cmp     [rsp+rcx*8+200h+var_200], r10d
0x14001323d  jnz     short loc_140013260
0x14001323f  test    r9, r9
0x140013242  jz      short loc_14001324B
0x140013244  mov     eax, [rsp+rcx*8+200h+var_1FC]
0x140013248  mov     [r9], eax
0x14001324b  lea     rax, [rsp+200h+var_1F8]
0x140013250  test    r8, r8
0x140013253  jz      short loc_14001325B
0x140013255  mov     eax, [rax+rcx*8]
0x140013258  mov     [r8], eax
0x14001325b  mov     eax, 1
0x140013260  inc     edx
0x140013262  cmp     edx, 20h ; ' '
0x140013265  jb      short loc_140013230
0x140013267  add     rsp, 200h
0x14001326e  pop     rbp
0x14001326f  retn
```
