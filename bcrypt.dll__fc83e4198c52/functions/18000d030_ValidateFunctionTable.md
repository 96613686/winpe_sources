# ValidateFunctionTable

- ea: `0x18000d030`
- end: `0x18000d540`
- name: `ValidateFunctionTable`
- size: `1296`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800070d0`
- `0x180014f98`

## callees

- `0x180005060`
- `0x180007a7c`
- `0x18000d030`

## string_xrefs

- `0x18000d15a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000d4a2`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall ValidateFunctionTable(int a1, _QWORD *a2, _QWORD *a3, _QWORD *a4, _QWORD *a5, _QWORD *a6)
{
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // r10
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v12; // rcx
  __int64 v13; // r10
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // r10
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // r10
  __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // r10
  __int64 v23; // r9
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // r10
  __int64 v27; // r8
  __int64 v28; // rcx
  __int64 v29; // r10
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rcx
  __int64 v33; // r10
  __int64 v34; // r8

  v6 = 0;
  if ( a1 == 2 )
  {
    v7 = a2[1];
    v8 = a2[4];
    *a4 = v8;
    v9 = a2[3];
    *a5 = v9;
    *a3 = v7;
    v10 = a2[2];
    *a6 = v10;
    if ( !v7 || !v8 || !v9 || !v10 || !a2[5] || !a2[6] || !a2[7] || !a2[8] || !a2[9] )
    {
      v6 = -1073741816;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          v10,
          (unsigned int)"Status",
          8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          243);
    }
  }
  else if ( a1 == 1 )
  {
    v12 = a2[1];
    v13 = a2[4];
    *a3 = v12;
    v14 = a2[3];
    *a5 = v14;
    *a4 = v13;
    if ( !v12 || !v13 || !v14 || !a2[2] || !a2[5] || !a2[6] || !a2[7] || !a2[8] || !a2[9] || !a2[10] || !a2[11] )
    {
      v6 = -1073741816;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          v14,
          (unsigned int)"Status",
          8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          224);
    }
  }
  else
  {
    switch ( a1 )
    {
      case 3:
        v21 = a2[1];
        v22 = a2[4];
        *a4 = v22;
        v23 = a2[3];
        *a5 = v23;
        *a3 = v21;
        v24 = a2[2];
        *a6 = v24;
        if ( !v21
          || !v22
          || !v23
          || !v24
          || !a2[5]
          || !a2[6]
          || !a2[7]
          || !a2[8]
          || !a2[11]
          || !a2[9]
          || !a2[10]
          || !a2[12]
          || !a2[13] )
        {
          v6 = -1073741816;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)a2,
              v24,
              (unsigned int)"Status",
              8,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
              10);
        }
        break;
      case 4:
        v18 = a2[1];
        v19 = a2[4];
        *a3 = v18;
        v20 = a2[3];
        *a5 = v20;
        *a4 = v19;
        if ( !v18
          || !v19
          || !v20
          || !a2[2]
          || !a2[5]
          || !a2[6]
          || !a2[7]
          || !a2[8]
          || !a2[9]
          || !a2[10]
          || !a2[11]
          || !a2[12] )
        {
          v6 = -1073741816;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)a2,
              v20,
              (unsigned int)"Status",
              8,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
              31);
        }
        break;
      case 5:
        v25 = a2[1];
        v26 = a2[4];
        *a3 = v25;
        v27 = a2[3];
        *a5 = v27;
        *a4 = v26;
        if ( !v25 || !v26 || !v27 || !a2[2] || !a2[5] || !a2[6] || !a2[7] || !a2[8] || !a2[9] || !a2[10] || !a2[11] )
        {
          v6 = -1073741816;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)a2,
              v27,
              (unsigned int)"Status",
              8,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
              51);
        }
        break;
      case 6:
        v15 = a2[1];
        v16 = a2[4];
        *a3 = v15;
        v17 = a2[3];
        *a5 = v17;
        *a4 = v16;
        if ( !v15 || !v16 || !v17 || !a2[2] || !a2[5] )
        {
          v6 = -1073741816;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)a2,
              v17,
              (unsigned int)"Status",
              8,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
              65);
        }
        break;
      case 7:
        v28 = a2[1];
        v29 = a2[4];
        *a3 = v28;
        v30 = a2[3];
        *a5 = v30;
        *a4 = v29;
        if ( !v28 || !v29 || !v30 || !a2[2] || !a2[5] || !a2[7] || !a2[9] || !a2[8] || !a2[10] || !a2[6] )
        {
          v31 = 1364;
          goto LABEL_101;
        }
        break;
      case 8:
        v32 = a2[1];
        v33 = a2[4];
        *a3 = v32;
        v34 = a2[3];
        *a5 = v34;
        *a4 = v33;
        if ( !v32 || !v33 || !v34 || !a2[2] || !a2[5] || !a2[6] || !a2[7] || !a2[8] || !a2[9] || !a2[10] || !a2[11] )
        {
          v31 = 1384;
LABEL_101:
          v6 = -1073741816;
          DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v31);
        }
        break;
      default:
        v6 = -1073741816;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)a2,
            (_DWORD)a3,
            (unsigned int)"Status",
            8,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
            111);
        break;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000d030  push    rbx
0x18000d032  sub     rsp, 40h
0x18000d036  xor     ebx, ebx
0x18000d038  cmp     ecx, 2
0x18000d03b  jnz     loc_18000D0C6
0x18000d041  mov     rax, [rsp+48h+arg_20]
0x18000d046  mov     rcx, [rdx+8]
0x18000d04a  mov     r10, [rdx+20h]
0x18000d04e  mov     [r9], r10
0x18000d051  mov     r9, [rdx+18h]
0x18000d055  mov     [rax], r9
0x18000d058  mov     rax, [rsp+48h+arg_28]
0x18000d05d  mov     [r8], rcx
0x18000d060  mov     r8, [rdx+10h]
0x18000d064  mov     [rax], r8
0x18000d067  test    rcx, rcx
0x18000d06a  jz      loc_18000D3FE
0x18000d070  test    r10, r10
0x18000d073  jz      loc_18000D3FE
0x18000d079  test    r9, r9
0x18000d07c  jz      loc_18000D3FE
0x18000d082  test    r8, r8
0x18000d085  jz      loc_18000D3FE
0x18000d08b  cmp     [rdx+28h], rbx
0x18000d08f  jz      loc_18000D3FE
0x18000d095  cmp     [rdx+30h], rbx
0x18000d099  jz      loc_18000D3FE
0x18000d09f  cmp     [rdx+38h], rbx
0x18000d0a3  jz      loc_18000D3FE
0x18000d0a9  cmp     [rdx+40h], rbx
0x18000d0ad  jz      loc_18000D3FE
0x18000d0b3  cmp     [rdx+48h], rbx
0x18000d0b7  jz      loc_18000D3FE
0x18000d0bd  mov     eax, ebx
0x18000d0bf  add     rsp, 40h
0x18000d0c3  pop     rbx
0x18000d0c4  retn
0x18000d0c6  cmp     ecx, 1
0x18000d0c9  jnz     loc_18000D17F
0x18000d0cf  mov     rcx, [rdx+8]
0x18000d0d3  mov     rax, [rsp+48h+arg_20]
0x18000d0d8  mov     r10, [rdx+20h]
0x18000d0dc  mov     [r8], rcx
0x18000d0df  mov     r8, [rdx+18h]
0x18000d0e3  mov     [rax], r8
0x18000d0e6  mov     [r9], r10
0x18000d0e9  test    rcx, rcx
0x18000d0ec  jz      short loc_18000D128
0x18000d0ee  test    r10, r10
0x18000d0f1  jz      short loc_18000D128
0x18000d0f3  test    r8, r8
0x18000d0f6  jz      short loc_18000D128
0x18000d0f8  cmp     [rdx+10h], rbx
0x18000d0fc  jz      short loc_18000D128
0x18000d0fe  cmp     [rdx+28h], rbx
0x18000d102  jz      short loc_18000D128
0x18000d104  cmp     [rdx+30h], rbx
0x18000d108  jz      short loc_18000D128
0x18000d10a  cmp     [rdx+38h], rbx
0x18000d10e  jz      short loc_18000D128
0x18000d110  cmp     [rdx+40h], rbx
0x18000d114  jz      short loc_18000D128
0x18000d116  cmp     [rdx+48h], rbx
0x18000d11a  jz      short loc_18000D128
0x18000d11c  cmp     [rdx+50h], rbx
0x18000d120  jz      short loc_18000D128
0x18000d122  cmp     [rdx+58h], rbx
0x18000d126  jnz     short loc_18000D0BD
0x18000d128  mov     ebx, 0C0000008h
0x18000d12d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d134  lea     rax, WPP_GLOBAL_Control
0x18000d13b  cmp     rcx, rax
0x18000d13e  jz      loc_18000D0BD
0x18000d144  test    byte ptr [rcx+1Ch], 1
0x18000d148  jz      loc_18000D0BD
0x18000d14e  mov     [rsp+48h+var_18], 4E0h
0x18000d156  mov     rcx, [rcx+10h]
0x18000d15a  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d161  mov     [rsp+48h+var_20], rax
0x18000d166  lea     r9, aStatus; "Status"
0x18000d16d  mov     [rsp+48h+var_28], 0C0000008h
0x18000d175  call    WPP_SF_sDsd
0x18000d17a  jmp     loc_18000D0BD
0x18000d17f  add     ecx, 0FFFFFFFDh; switch 6 cases
0x18000d182  cmp     ecx, 5
0x18000d185  jbe     short loc_18000D1B7
0x18000d187  mov     ebx, 0C0000008h; jumptable 000000018000D1C9 default case
0x18000d18c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d193  lea     rax, WPP_GLOBAL_Control
0x18000d19a  cmp     rcx, rax
0x18000d19d  jz      loc_18000D0BD
0x18000d1a3  test    byte ptr [rcx+1Ch], 1
0x18000d1a7  jz      loc_18000D0BD
0x18000d1ad  mov     [rsp+48h+var_18], 56Fh
0x18000d1b5  jmp     short loc_18000D156
0x18000d1b7  lea     r10, __ImageBase
0x18000d1be  mov     eax, ds:(jpt_18000D1C9 - 180000000h)[r10+rcx*4]
0x18000d1c6  add     rax, r10
0x18000d1c9  jmp     rax; switch jump
0x18000d1cf  mov     rcx, [rdx+8]; jumptable 000000018000D1C9 case 6
0x18000d1d3  mov     rax, [rsp+48h+arg_20]
0x18000d1d8  mov     r10, [rdx+20h]
0x18000d1dc  mov     [r8], rcx
0x18000d1df  mov     r8, [rdx+18h]
0x18000d1e3  mov     [rax], r8
0x18000d1e6  mov     [r9], r10
0x18000d1e9  test    rcx, rcx
0x18000d1ec  jz      short loc_18000D208
0x18000d1ee  test    r10, r10
0x18000d1f1  jz      short loc_18000D208
0x18000d1f3  test    r8, r8
0x18000d1f6  jz      short loc_18000D208
0x18000d1f8  cmp     [rdx+10h], rbx
0x18000d1fc  jz      short loc_18000D208
0x18000d1fe  cmp     [rdx+28h], rbx
0x18000d202  jnz     loc_18000D0BD
0x18000d208  mov     ebx, 0C0000008h
0x18000d20d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d214  lea     rax, WPP_GLOBAL_Control
0x18000d21b  cmp     rcx, rax
0x18000d21e  jz      loc_18000D0BD
0x18000d224  test    byte ptr [rcx+1Ch], 1
0x18000d228  jz      loc_18000D0BD
0x18000d22e  mov     [rsp+48h+var_18], 541h
0x18000d236  jmp     loc_18000D156
0x18000d23b  mov     rcx, [rdx+8]; jumptable 000000018000D1C9 case 4
0x18000d23f  mov     rax, [rsp+48h+arg_20]
0x18000d244  mov     r10, [rdx+20h]
0x18000d248  mov     [r8], rcx
0x18000d24b  mov     r8, [rdx+18h]
0x18000d24f  mov     [rax], r8
0x18000d252  mov     [r9], r10
0x18000d255  test    rcx, rcx
0x18000d258  jz      short loc_18000D29E
0x18000d25a  test    r10, r10
0x18000d25d  jz      short loc_18000D29E
0x18000d25f  test    r8, r8
0x18000d262  jz      short loc_18000D29E
0x18000d264  cmp     [rdx+10h], rbx
0x18000d268  jz      short loc_18000D29E
0x18000d26a  cmp     [rdx+28h], rbx
0x18000d26e  jz      short loc_18000D29E
0x18000d270  cmp     [rdx+30h], rbx
0x18000d274  jz      short loc_18000D29E
0x18000d276  cmp     [rdx+38h], rbx
0x18000d27a  jz      short loc_18000D29E
0x18000d27c  cmp     [rdx+40h], rbx
0x18000d280  jz      short loc_18000D29E
0x18000d282  cmp     [rdx+48h], rbx
0x18000d286  jz      short loc_18000D29E
0x18000d288  cmp     [rdx+50h], rbx
0x18000d28c  jz      short loc_18000D29E
0x18000d28e  cmp     [rdx+58h], rbx
0x18000d292  jz      short loc_18000D29E
0x18000d294  cmp     [rdx+60h], rbx
0x18000d298  jnz     loc_18000D0BD
0x18000d29e  mov     ebx, 0C0000008h
0x18000d2a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2aa  lea     rax, WPP_GLOBAL_Control
0x18000d2b1  cmp     rcx, rax
0x18000d2b4  jz      loc_18000D0BD
0x18000d2ba  test    byte ptr [rcx+1Ch], 1
0x18000d2be  jz      loc_18000D0BD
0x18000d2c4  mov     [rsp+48h+var_18], 51Fh
0x18000d2cc  jmp     loc_18000D156
0x18000d2d1  mov     rax, [rsp+48h+arg_20]; jumptable 000000018000D1C9 case 3
0x18000d2d6  mov     rcx, [rdx+8]
0x18000d2da  mov     r10, [rdx+20h]
0x18000d2de  mov     [r9], r10
0x18000d2e1  mov     r9, [rdx+18h]
0x18000d2e5  mov     [rax], r9
0x18000d2e8  mov     rax, [rsp+48h+arg_28]
0x18000d2ed  mov     [r8], rcx
0x18000d2f0  mov     r8, [rdx+10h]
0x18000d2f4  mov     [rax], r8
0x18000d2f7  test    rcx, rcx
0x18000d2fa  jz      short loc_18000D345
0x18000d2fc  test    r10, r10
0x18000d2ff  jz      short loc_18000D345
0x18000d301  test    r9, r9
0x18000d304  jz      short loc_18000D345
0x18000d306  test    r8, r8
0x18000d309  jz      short loc_18000D345
0x18000d30b  cmp     [rdx+28h], rbx
0x18000d30f  jz      short loc_18000D345
0x18000d311  cmp     [rdx+30h], rbx
0x18000d315  jz      short loc_18000D345
0x18000d317  cmp     [rdx+38h], rbx
0x18000d31b  jz      short loc_18000D345
0x18000d31d  cmp     [rdx+40h], rbx
0x18000d321  jz      short loc_18000D345
0x18000d323  cmp     [rdx+58h], rbx
0x18000d327  jz      short loc_18000D345
0x18000d329  cmp     [rdx+48h], rbx
0x18000d32d  jz      short loc_18000D345
0x18000d32f  cmp     [rdx+50h], rbx
0x18000d333  jz      short loc_18000D345
0x18000d335  cmp     [rdx+60h], rbx
0x18000d339  jz      short loc_18000D345
0x18000d33b  cmp     [rdx+68h], rbx
0x18000d33f  jnz     loc_18000D0BD
0x18000d345  mov     ebx, 0C0000008h
0x18000d34a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d351  lea     rax, WPP_GLOBAL_Control
0x18000d358  cmp     rcx, rax
0x18000d35b  jz      loc_18000D0BD
0x18000d361  test    byte ptr [rcx+1Ch], 1
0x18000d365  jz      loc_18000D0BD
0x18000d36b  mov     [rsp+48h+var_18], 50Ah
0x18000d373  jmp     loc_18000D156
0x18000d378  mov     rcx, [rdx+8]; jumptable 000000018000D1C9 case 5
0x18000d37c  mov     rax, [rsp+48h+arg_20]
0x18000d381  mov     r10, [rdx+20h]
0x18000d385  mov     [r8], rcx
0x18000d388  mov     r8, [rdx+18h]
0x18000d38c  mov     [rax], r8
0x18000d38f  mov     [r9], r10
0x18000d392  test    rcx, rcx
0x18000d395  jz      short loc_18000D3CB
0x18000d397  test    r10, r10
0x18000d39a  jz      short loc_18000D3CB
0x18000d39c  test    r8, r8
0x18000d39f  jz      short loc_18000D3CB
0x18000d3a1  cmp     [rdx+10h], rbx
0x18000d3a5  jz      short loc_18000D3CB
0x18000d3a7  cmp     [rdx+28h], rbx
0x18000d3ab  jz      short loc_18000D3CB
0x18000d3ad  cmp     [rdx+30h], rbx
0x18000d3b1  jz      short loc_18000D3CB
0x18000d3b3  cmp     [rdx+38h], rbx
0x18000d3b7  jz      short loc_18000D3CB
0x18000d3b9  cmp     [rdx+40h], rbx
0x18000d3bd  jz      short loc_18000D3CB
0x18000d3bf  cmp     [rdx+48h], rbx
0x18000d3c3  jz      short loc_18000D3CB
0x18000d3c5  cmp     [rdx+50h], rbx
0x18000d3c9  jnz     short loc_18000D431
0x18000d3cb  mov     ebx, 0C0000008h
0x18000d3d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3d7  lea     rax, WPP_GLOBAL_Control
0x18000d3de  cmp     rcx, rax
0x18000d3e1  jz      loc_18000D0BD
0x18000d3e7  test    byte ptr [rcx+1Ch], 1
0x18000d3eb  jz      loc_18000D0BD
0x18000d3f1  mov     [rsp+48h+var_18], 533h
0x18000d3f9  jmp     loc_18000D156
0x18000d3fe  mov     ebx, 0C0000008h
0x18000d403  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d40a  lea     rax, WPP_GLOBAL_Control
0x18000d411  cmp     rcx, rax
0x18000d414  jz      loc_18000D0BD
0x18000d41a  test    byte ptr [rcx+1Ch], 1
0x18000d41e  jz      loc_18000D0BD
0x18000d424  mov     [rsp+48h+var_18], 4F3h
0x18000d42c  jmp     loc_18000D156
0x18000d431  cmp     [rdx+58h], rbx
0x18000d435  jnz     loc_18000D0BD
0x18000d43b  jmp     short loc_18000D3CB
0x18000d43d  mov     rcx, [rdx+8]; jumptable 000000018000D1C9 case 7
0x18000d441  mov     rax, [rsp+48h+arg_20]
0x18000d446  mov     r10, [rdx+20h]
0x18000d44a  mov     [r8], rcx
0x18000d44d  mov     r8, [rdx+18h]
0x18000d451  mov     [rax], r8
0x18000d454  mov     [r9], r10
0x18000d457  test    rcx, rcx
0x18000d45a  jz      short loc_18000D494
0x18000d45c  test    r10, r10
0x18000d45f  jz      short loc_18000D494
0x18000d461  test    r8, r8
0x18000d464  jz      short loc_18000D494
0x18000d466  cmp     [rdx+10h], rbx
0x18000d46a  jz      short loc_18000D494
0x18000d46c  cmp     [rdx+28h], rbx
0x18000d470  jz      short loc_18000D494
0x18000d472  cmp     [rdx+38h], rbx
0x18000d476  jz      short loc_18000D494
0x18000d478  cmp     [rdx+48h], rbx
0x18000d47c  jz      short loc_18000D494
0x18000d47e  cmp     [rdx+40h], rbx
0x18000d482  jz      short loc_18000D494
0x18000d484  cmp     [rdx+50h], rbx
0x18000d488  jz      short loc_18000D494
0x18000d48a  cmp     [rdx+30h], rbx
0x18000d48e  jnz     loc_18000D0BD
0x18000d494  mov     r9d, 554h
0x18000d49a  jmp     short loc_18000D4A2
0x18000d49c  mov     r9d, 568h
0x18000d4a2  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d4a9  mov     ecx, 0C0000008h
0x18000d4ae  lea     rdx, aStatus; "Status"
0x18000d4b5  mov     ebx, 0C0000008h
0x18000d4ba  call    DebugTraceError
0x18000d4bf  jmp     loc_18000D0BD
0x18000d4c4  mov     rcx, [rdx+8]; jumptable 000000018000D1C9 case 8
0x18000d4c8  mov     rax, [rsp+48h+arg_20]
0x18000d4cd  mov     r10, [rdx+20h]
0x18000d4d1  mov     [r8], rcx
0x18000d4d4  mov     r8, [rdx+18h]
0x18000d4d8  mov     [rax], r8
  ... truncated ...
```
