# MSCryptDuplicateHash

- ea: `0x18004c440`
- end: `0x18004d418`
- name: `MSCryptDuplicateHash`
- size: `4056`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001650`
- `0x180001850`
- `0x180001a50`
- `0x180001c40`
- `0x180001f40`
- `0x18000ecb0`
- `0x18000ee60`
- `0x18000ef28`
- `0x1800185c0`
- `0x18002e570`
- `0x18004c440`
- `0x18004d420`
- `0x180052878`
- `0x180063170`
- `0x180065680`
- `0x18006e88c`
- `0x1800709ac`
- `0x180078040`
- `0x180078160`

## string_xrefs

- `0x18004c4a4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18004d38b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptDuplicateHash(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v7; // r9
  unsigned int *v8; // rax
  int v9; // edx
  unsigned int v10; // r9d
  unsigned int *v11; // rdi
  int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx

  if ( a5 )
  {
    v7 = 3090;
    goto LABEL_68;
  }
  v8 = (unsigned int *)validateMSCryptHash(a1, a2);
  v11 = v8;
  if ( !v8 )
  {
    v12 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        27);
    return (unsigned int)v12;
  }
  if ( !a2 || !a3 || v8[9] )
  {
    v7 = 3108;
LABEL_68:
    v12 = -1073741811;
    v16 = 3221225485LL;
LABEL_69:
    DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v7);
    return (unsigned int)v12;
  }
  if ( v10 >= *v8 )
  {
    memcpy_0((void *)a3, v8, *v8);
    switch ( v11[2] )
    {
      case 0x20001u:
      case 0x20003u:
      case 0x20004u:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v11 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v11 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v11 + 10);
        *(_OWORD *)(a3 + 176) = *((_OWORD *)v11 + 11);
        *(_OWORD *)(a3 + 192) = *((_OWORD *)v11 + 12);
        *(_OWORD *)(a3 + 208) = *((_OWORD *)v11 + 13);
        *(_OWORD *)(a3 + 224) = *((_OWORD *)v11 + 14);
        goto LABEL_65;
      case 0x20002u:
      case 0x20005u:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v11 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v11 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v11 + 10);
        *(_OWORD *)(a3 + 176) = *((_OWORD *)v11 + 11);
        *(_OWORD *)(a3 + 192) = *((_OWORD *)v11 + 12);
        *(_OWORD *)(a3 + 208) = *((_OWORD *)v11 + 13);
        *(_OWORD *)(a3 + 224) = *((_OWORD *)v11 + 14);
        *(_OWORD *)(a3 + 240) = *((_OWORD *)v11 + 15);
        goto LABEL_65;
      case 0x20006u:
      case 0x20007u:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v11 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v11 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v11 + 10);
        *(_OWORD *)(a3 + 176) = *((_OWORD *)v11 + 11);
        *(_OWORD *)(a3 + 192) = *((_OWORD *)v11 + 12);
        *(_OWORD *)(a3 + 208) = *((_OWORD *)v11 + 13);
        *(_OWORD *)(a3 + 224) = *((_OWORD *)v11 + 14);
        *(_OWORD *)(a3 + 240) = *((_OWORD *)v11 + 15);
        *(_OWORD *)(a3 + 256) = *((_OWORD *)v11 + 16);
        *(_OWORD *)(a3 + 272) = *((_OWORD *)v11 + 17);
        *(_OWORD *)(a3 + 288) = *((_OWORD *)v11 + 18);
        *(_OWORD *)(a3 + 304) = *((_OWORD *)v11 + 19);
        *(_OWORD *)(a3 + 320) = *((_OWORD *)v11 + 20);
        *(_OWORD *)(a3 + 336) = *((_OWORD *)v11 + 21);
        goto LABEL_65;
      case 0x20008u:
        SymCryptGcmExpandKey(a3 + 128, *((_QWORD *)v11 + 272), v11 + 674, *((_QWORD *)v11 + 336));
        if ( v11[29] )
        {
          *(_OWORD *)(a3 + 2736) = *((_OWORD *)v11 + 171);
          *(_OWORD *)(a3 + 2752) = *((_OWORD *)v11 + 172);
          *(_OWORD *)(a3 + 2768) = *((_OWORD *)v11 + 173);
          *(_OWORD *)(a3 + 2784) = *((_OWORD *)v11 + 174);
          *(_OWORD *)(a3 + 2800) = *((_OWORD *)v11 + 175);
          *(_OWORD *)(a3 + 2816) = *((_OWORD *)v11 + 176);
          *(_OWORD *)(a3 + 2832) = *((_OWORD *)v11 + 177);
          if ( a3 != -128 )
            *(_QWORD *)(a3 + 2736) = a3 + 128;
        }
        goto LABEL_65;
      case 0x20009u:
      case 0x2000Bu:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v11 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v11 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v11 + 10);
        *(_OWORD *)(a3 + 176) = *((_OWORD *)v11 + 11);
        *(_OWORD *)(a3 + 192) = *((_OWORD *)v11 + 12);
        SymCryptHmacSha1StateCopy(v11 + 52, a3 + 128, a3 + 208);
        goto LABEL_65;
      case 0x2000Au:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v11 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v11 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v11 + 10);
        SymCryptHmacMd5StateCopy(v11 + 44, a3 + 128, a3 + 176);
        goto LABEL_65;
      case 0x2000Cu:
      case 0x2000Du:
        *(_OWORD *)(a3 + 128) = *((_OWORD *)v11 + 8);
        *(_OWORD *)(a3 + 144) = *((_OWORD *)v11 + 9);
        *(_OWORD *)(a3 + 160) = *((_OWORD *)v11 + 10);
        *(_OWORD *)(a3 + 176) = *((_OWORD *)v11 + 11);
        *(_OWORD *)(a3 + 192) = *((_OWORD *)v11 + 12);
        *(_OWORD *)(a3 + 208) = *((_OWORD *)v11 + 13);
        *(_OWORD *)(a3 + 224) = *((_OWORD *)v11 + 14);
        *(_OWORD *)(a3 + 240) = *((_OWORD *)v11 + 15);
        *(_OWORD *)(a3 + 256) = *((_OWORD *)v11 + 16);
        SymCryptHmacSha512StateCopy(v11 + 68, a3 + 128, a3 + 272);
        goto LABEL_65;
      case 0x2000Eu:
        SymCryptAesKeyCopy(v11 + 32, a3 + 128);
        *(_OWORD *)(v13 + 496) = *(_OWORD *)(v14 + 496);
        *(_OWORD *)(v13 + 512) = *(_OWORD *)(v14 + 512);
        *(_OWORD *)(a3 + 672) = *((_OWORD *)v11 + 42);
        *(_OWORD *)(a3 + 688) = *((_OWORD *)v11 + 43);
        *(_OWORD *)(a3 + 704) = *((_OWORD *)v11 + 44);
        *(_OWORD *)(a3 + 720) = *((_OWORD *)v11 + 45);
        if ( !v13 )
          v13 = *((_QWORD *)v11 + 89);
        *(_QWORD *)(a3 + 712) = v13;
        goto LABEL_65;
      case 0x2000Fu:
        SymCryptSha3_256StateCopy(v11 + 32, (void *)(a3 + 128));
        goto LABEL_65;
      case 0x20010u:
        SymCryptSha3_384StateCopy(v11 + 32, (void *)(a3 + 128));
        goto LABEL_65;
      case 0x20011u:
        SymCryptSha3_512StateCopy(v11 + 32, (void *)(a3 + 128));
        goto LABEL_65;
      case 0x20012u:
      case 0x20013u:
      case 0x20014u:
        SymCryptHmacKeyCopy(v11 + 32, a3 + 128);
        SymCryptHmacStateCopy(v11 + 160, a3 + 128, a3 + 640);
        goto LABEL_65;
      case 0x20015u:
        if ( v11[70] - 2 <= 1 )
        {
          *(_OWORD *)(a3 + 528) = *((_OWORD *)v11 + 33);
          *(_OWORD *)(a3 + 544) = *((_OWORD *)v11 + 34);
          *(_OWORD *)(a3 + 560) = *((_OWORD *)v11 + 35);
          *(_OWORD *)(a3 + 576) = *((_OWORD *)v11 + 36);
          *(_OWORD *)(a3 + 592) = *((_OWORD *)v11 + 37);
          *(_OWORD *)(a3 + 608) = *((_OWORD *)v11 + 38);
          *(_OWORD *)(a3 + 624) = *((_OWORD *)v11 + 39);
          *(_OWORD *)(a3 + 640) = *((_OWORD *)v11 + 40);
          *(_OWORD *)(a3 + 656) = *((_OWORD *)v11 + 41);
          *(_OWORD *)(a3 + 672) = *((_OWORD *)v11 + 42);
          *(_OWORD *)(a3 + 688) = *((_OWORD *)v11 + 43);
          *(_OWORD *)(a3 + 704) = *((_OWORD *)v11 + 44);
          *(_OWORD *)(a3 + 720) = *((_OWORD *)v11 + 45);
          *(_OWORD *)(a3 + 736) = *((_OWORD *)v11 + 46);
          *(_OWORD *)(a3 + 752) = *((_OWORD *)v11 + 47);
        }
        if ( v11[70] )
        {
          *(_OWORD *)(a3 + 288) = *((_OWORD *)v11 + 18);
          *(_OWORD *)(a3 + 304) = *((_OWORD *)v11 + 19);
          *(_OWORD *)(a3 + 320) = *((_OWORD *)v11 + 20);
          *(_OWORD *)(a3 + 336) = *((_OWORD *)v11 + 21);
          *(_OWORD *)(a3 + 352) = *((_OWORD *)v11 + 22);
          *(_OWORD *)(a3 + 368) = *((_OWORD *)v11 + 23);
          *(_OWORD *)(a3 + 384) = *((_OWORD *)v11 + 24);
          *(_OWORD *)(a3 + 400) = *((_OWORD *)v11 + 25);
          *(_OWORD *)(a3 + 416) = *((_OWORD *)v11 + 26);
          *(_OWORD *)(a3 + 432) = *((_OWORD *)v11 + 27);
          *(_OWORD *)(a3 + 448) = *((_OWORD *)v11 + 28);
          *(_OWORD *)(a3 + 464) = *((_OWORD *)v11 + 29);
          *(_OWORD *)(a3 + 480) = *((_OWORD *)v11 + 30);
          *(_OWORD *)(a3 + 496) = *((_OWORD *)v11 + 31);
          *(_OWORD *)(a3 + 512) = *((_OWORD *)v11 + 32);
        }
        *(_QWORD *)(a3 + 184) = 0;
        *(_DWORD *)(a3 + 192) = 0;
        *(_QWORD *)(a3 + 264) = 0;
        *(_DWORD *)(a3 + 272) = 0;
        v15 = MSCryptCustomBufferUpdate(a3 + 120, *((_QWORD *)v11 + 23), v11[48]);
        v12 = v15;
        if ( v15 < 0 )
        {
          v7 = 3335;
          goto LABEL_35;
        }
        v12 = MSCryptCustomBufferUpdate(a3 + 200, *((_QWORD *)v11 + 33), v11[68]);
        if ( v12 >= 0 )
          goto LABEL_65;
        MSCryptCustomBufferReset(a3 + 120);
        v7 = 3343;
        goto LABEL_38;
      case 0x20016u:
        if ( v11[70] - 2 <= 1 )
        {
          *(_OWORD *)(a3 + 528) = *((_OWORD *)v11 + 33);
          *(_OWORD *)(a3 + 544) = *((_OWORD *)v11 + 34);
          *(_OWORD *)(a3 + 560) = *((_OWORD *)v11 + 35);
          *(_OWORD *)(a3 + 576) = *((_OWORD *)v11 + 36);
          *(_OWORD *)(a3 + 592) = *((_OWORD *)v11 + 37);
          *(_OWORD *)(a3 + 608) = *((_OWORD *)v11 + 38);
          *(_OWORD *)(a3 + 624) = *((_OWORD *)v11 + 39);
          *(_OWORD *)(a3 + 640) = *((_OWORD *)v11 + 40);
          *(_OWORD *)(a3 + 656) = *((_OWORD *)v11 + 41);
          *(_OWORD *)(a3 + 672) = *((_OWORD *)v11 + 42);
          *(_OWORD *)(a3 + 688) = *((_OWORD *)v11 + 43);
          *(_OWORD *)(a3 + 704) = *((_OWORD *)v11 + 44);
          *(_OWORD *)(a3 + 720) = *((_OWORD *)v11 + 45);
          *(_OWORD *)(a3 + 736) = *((_OWORD *)v11 + 46);
          *(_OWORD *)(a3 + 752) = *((_OWORD *)v11 + 47);
        }
        if ( v11[70] )
        {
          *(_OWORD *)(a3 + 288) = *((_OWORD *)v11 + 18);
          *(_OWORD *)(a3 + 304) = *((_OWORD *)v11 + 19);
          *(_OWORD *)(a3 + 320) = *((_OWORD *)v11 + 20);
          *(_OWORD *)(a3 + 336) = *((_OWORD *)v11 + 21);
          *(_OWORD *)(a3 + 352) = *((_OWORD *)v11 + 22);
          *(_OWORD *)(a3 + 368) = *((_OWORD *)v11 + 23);
          *(_OWORD *)(a3 + 384) = *((_OWORD *)v11 + 24);
          *(_OWORD *)(a3 + 400) = *((_OWORD *)v11 + 25);
          *(_OWORD *)(a3 + 416) = *((_OWORD *)v11 + 26);
          *(_OWORD *)(a3 + 432) = *((_OWORD *)v11 + 27);
          *(_OWORD *)(a3 + 448) = *((_OWORD *)v11 + 28);
          *(_OWORD *)(a3 + 464) = *((_OWORD *)v11 + 29);
          *(_OWORD *)(a3 + 480) = *((_OWORD *)v11 + 30);
          *(_OWORD *)(a3 + 496) = *((_OWORD *)v11 + 31);
          *(_OWORD *)(a3 + 512) = *((_OWORD *)v11 + 32);
        }
        *(_QWORD *)(a3 + 184) = 0;
        *(_DWORD *)(a3 + 192) = 0;
        *(_QWORD *)(a3 + 264) = 0;
        *(_DWORD *)(a3 + 272) = 0;
        v15 = MSCryptCustomBufferUpdate(a3 + 120, *((_QWORD *)v11 + 23), v11[48]);
        v12 = v15;
        if ( v15 < 0 )
        {
          v7 = 3374;
          goto LABEL_35;
        }
        v12 = MSCryptCustomBufferUpdate(a3 + 200, *((_QWORD *)v11 + 33), v11[68]);
        if ( v12 >= 0 )
          goto LABEL_65;
        MSCryptCustomBufferReset(a3 + 120);
        v7 = 3382;
LABEL_38:
        v16 = (unsigned int)v12;
        goto LABEL_69;
      case 0x20017u:
        if ( v11[132] )
        {
          *(_OWORD *)(a3 + 128) = *((_OWORD *)v11 + 8);
          *(_OWORD *)(a3 + 144) = *((_OWORD *)v11 + 9);
          *(_OWORD *)(a3 + 160) = *((_OWORD *)v11 + 10);
          *(_OWORD *)(a3 + 176) = *((_OWORD *)v11 + 11);
          *(_OWORD *)(a3 + 192) = *((_OWORD *)v11 + 12);
          *(_OWORD *)(a3 + 208) = *((_OWORD *)v11 + 13);
          *(_OWORD *)(a3 + 224) = *((_OWORD *)v11 + 14);
          *(_OWORD *)(a3 + 240) = *((_OWORD *)v11 + 15);
          *(_OWORD *)(a3 + 256) = *((_OWORD *)v11 + 16);
          *(_OWORD *)(a3 + 272) = *((_OWORD *)v11 + 17);
          *(_OWORD *)(a3 + 288) = *((_OWORD *)v11 + 18);
          *(_OWORD *)(a3 + 304) = *((_OWORD *)v11 + 19);
          *(_OWORD *)(a3 + 320) = *((_OWORD *)v11 + 20);
          *(_OWORD *)(a3 + 336) = *((_OWORD *)v11 + 21);
          *(_OWORD *)(a3 + 352) = *((_OWORD *)v11 + 22);
        }
        if ( v11[132] - 2 <= 1 )
        {
          *(_OWORD *)(a3 + 544) = *((_OWORD *)v11 + 34);
          *(_OWORD *)(a3 + 560) = *((_OWORD *)v11 + 35);
          *(_OWORD *)(a3 + 576) = *((_OWORD *)v11 + 36);
          *(_OWORD *)(a3 + 592) = *((_OWORD *)v11 + 37);
          *(_OWORD *)(a3 + 608) = *((_OWORD *)v11 + 38);
          *(_OWORD *)(a3 + 624) = *((_OWORD *)v11 + 39);
          *(_OWORD *)(a3 + 640) = *((_OWORD *)v11 + 40);
          *(_OWORD *)(a3 + 656) = *((_OWORD *)v11 + 41);
          *(_OWORD *)(a3 + 672) = *((_OWORD *)v11 + 42);
          *(_OWORD *)(a3 + 688) = *((_OWORD *)v11 + 43);
          *(_OWORD *)(a3 + 704) = *((_OWORD *)v11 + 44);
          *(_OWORD *)(a3 + 720) = *((_OWORD *)v11 + 45);
          *(_OWORD *)(a3 + 736) = *((_OWORD *)v11 + 46);
          *(_OWORD *)(a3 + 752) = *((_OWORD *)v11 + 47);
          *(_OWORD *)(a3 + 768) = *((_OWORD *)v11 + 48);
        }
        *(_QWORD *)(a3 + 432) = 0;
        *(_DWORD *)(a3 + 440) = 0;
        v15 = MSCryptCustomBufferUpdate(a3 + 368, *((_QWORD *)v11 + 54), v11[110]);
        v12 = v15;
        if ( v15 < 0 )
        {
          v7 = 3409;
          goto LABEL_35;
        }
        *(_QWORD *)(a3 + 512) = 0;
        *(_DWORD *)(a3 + 520) = 0;
        v15 = MSCryptCustomBufferUpdate(a3 + 448, *((_QWORD *)v11 + 64), v11[130]);
        v12 = v15;
        if ( v15 >= 0 )
          goto LABEL_65;
        v7 = 3417;
        goto LABEL_35;
      case 0x20018u:
        if ( v11[132] )
        {
          *(_OWORD *)(a3 + 128) = *((_OWORD *)v11 + 8);
          *(_OWORD *)(a3 + 144) = *((_OWORD *)v11 + 9);
          *(_OWORD *)(a3 + 160) = *((_OWORD *)v11 + 10);
          *(_OWORD *)(a3 + 176) = *((_OWORD *)v11 + 11);
          *(_OWORD *)(a3 + 192) = *((_OWORD *)v11 + 12);
          *(_OWORD *)(a3 + 208) = *((_OWORD *)v11 + 13);
          *(_OWORD *)(a3 + 224) = *((_OWORD *)v11 + 14);
          *(_OWORD *)(a3 + 240) = *((_OWORD *)v11 + 15);
          *(_OWORD *)(a3 + 256) = *((_OWORD *)v11 + 16);
          *(_OWORD *)(a3 + 272) = *((_OWORD *)v11 + 17);
          *(_OWORD *)(a3 + 288) = *((_OWORD *)v11 + 18);
          *(_OWORD *)(a3 + 304) = *((_OWORD *)v11 + 19);
          *(_OWORD *)(a3 + 320) = *((_OWORD *)v11 + 20);
          *(_OWORD *)(a3 + 336) = *((_OWORD *)v11 + 21);
          *(_OWORD *)(a3 + 352) = *((_OWORD *)v11 + 22);
        }
        if ( v11[132] - 2 <= 1 )
        {
          *(_OWORD *)(a3 + 544) = *((_OWORD *)v11 + 34);
          *(_OWORD *)(a3 + 560) = *((_OWORD *)v11 + 35);
          *(_OWORD *)(a3 + 576) = *((_OWORD *)v11 + 36);
          *(_OWORD *)(a3 + 592) = *((_OWORD *)v11 + 37);
          *(_OWORD *)(a3 + 608) = *((_OWORD *)v11 + 38);
          *(_OWORD *)(a3 + 624) = *((_OWORD *)v11 + 39);
          *(_OWORD *)(a3 + 640) = *((_OWORD *)v11 + 40);
          *(_OWORD *)(a3 + 656) = *((_OWORD *)v11 + 41);
          *(_OWORD *)(a3 + 672) = *((_OWORD *)v11 + 42);
          *(_OWORD *)(a3 + 688) = *((_OWORD *)v11 + 43);
          *(_OWORD *)(a3 + 704) = *((_OWORD *)v11 + 44);
          *(_OWORD *)(a3 + 720) = *((_OWORD *)v11 + 45);
          *(_OWORD *)(a3 + 736) = *((_OWORD *)v11 + 46);
          *(_OWORD *)(a3 + 752) = *((_OWORD *)v11 + 47);
          *(_OWORD *)(a3 + 768) = *((_OWORD *)v11 + 48);
        }
        *(_QWORD *)(a3 + 432) = 0;
        *(_DWORD *)(a3 + 440) = 0;
        v15 = MSCryptCustomBufferUpdate(a3 + 368, *((_QWORD *)v11 + 54), v11[110]);
        v12 = v15;
        if ( v15 >= 0 )
        {
          *(_QWORD *)(a3 + 512) = 0;
          *(_DWORD *)(a3 + 520) = 0;
          v15 = MSCryptCustomBufferUpdate(a3 + 448, *((_QWORD *)v11 + 64), v11[130]);
          v12 = v15;
          if ( v15 >= 0 )
          {
LABEL_65:
            *a2 = a3;
            return 0;
          }
          v7 = 3452;
        }
        else
        {
          v7 = 3444;
        }
LABEL_35:
        v16 = (unsigned int)v15;
        goto LABEL_69;
      case 0x20019u:
        SymCryptShake128StateCopy(v11 + 32, (void *)(a3 + 128));
        goto LABEL_65;
      case 0x2001Au:
        SymCryptShake256StateCopy(v11 + 32, (void *)(a3 + 128));
        goto LABEL_65;
      default:
        v12 = -1073741637;
        v7 = 3483;
        v16 = 3221225659LL;
        goto LABEL_69;
    }
  }
  return (unsigned int)-1073741789;
}

```

## disassembly

```asm
0x18004c440  push    rbx
0x18004c442  push    rbp
0x18004c443  push    rsi
0x18004c444  push    rdi
0x18004c445  push    r12
0x18004c447  push    r14
0x18004c449  push    r15
0x18004c44b  sub     rsp, 40h
0x18004c44f  xor     r12d, r12d
0x18004c452  mov     rsi, r8
0x18004c455  mov     r15, rdx
0x18004c458  cmp     [rsp+78h+arg_20], r12d
0x18004c460  jz      short loc_18004C46D
0x18004c462  mov     r9d, 0C12h
0x18004c468  jmp     loc_18004D381
0x18004c46d  call    validateMSCryptHash
0x18004c472  mov     rdi, rax
0x18004c475  test    rax, rax
0x18004c478  jnz     short loc_18004C4D1
0x18004c47a  mov     ebx, 0C000000Dh
0x18004c47f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c486  lea     rax, WPP_GLOBAL_Control
0x18004c48d  cmp     rcx, rax
0x18004c490  jz      loc_18004D39E
0x18004c496  test    byte ptr [rcx+1Ch], 1
0x18004c49a  jz      loc_18004D39E
0x18004c4a0  mov     rcx, [rcx+10h]
0x18004c4a4  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004c4ab  mov     [rsp+78h+var_48], 0C1Bh
0x18004c4b3  lea     r9, aStatus; "Status"
0x18004c4ba  mov     [rsp+78h+var_50], r8
0x18004c4bf  mov     [rsp+78h+var_58], 0C000000Dh
0x18004c4c7  call    WPP_SF_sDsd
0x18004c4cc  jmp     loc_18004D39E
0x18004c4d1  test    r15, r15
0x18004c4d4  jz      loc_18004D37B
0x18004c4da  test    rsi, rsi
0x18004c4dd  jz      loc_18004D37B
0x18004c4e3  cmp     [rax+24h], r12d
0x18004c4e7  jnz     loc_18004D37B
0x18004c4ed  cmp     r9d, [rax]
0x18004c4f0  jnb     short loc_18004C4FC
0x18004c4f2  mov     ebx, 0C0000023h
0x18004c4f7  jmp     loc_18004D39E
0x18004c4fc  mov     r8d, [rax]; Size
0x18004c4ff  mov     rdx, rdi; Src
0x18004c502  mov     rcx, rsi; void *
0x18004c505  call    memcpy_0
0x18004c50a  mov     eax, [rdi+8]
0x18004c50d  add     eax, 0FFFDFFFFh; switch 26 cases
0x18004c512  cmp     eax, 19h
0x18004c515  ja      def_18004C52C; jumptable 000000018004C52C default case
0x18004c51b  lea     rcx, cs:180000000h
0x18004c522  mov     eax, ds:(jpt_18004C52C - 180000000h)[rcx+rax*4]
0x18004c529  add     rax, rcx
0x18004c52c  jmp     rax; switch jump
0x18004c532  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018004C52C cases 131073,131075,131076
0x18004c539  movaps  xmmword ptr [rsi+80h], xmm0
0x18004c540  movaps  xmm1, xmmword ptr [rdi+90h]
0x18004c547  movaps  xmmword ptr [rsi+90h], xmm1
0x18004c54e  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x18004c555  movaps  xmmword ptr [rsi+0A0h], xmm0
0x18004c55c  movaps  xmm1, xmmword ptr [rdi+0B0h]
0x18004c563  movaps  xmmword ptr [rsi+0B0h], xmm1
0x18004c56a  movaps  xmm0, xmmword ptr [rdi+0C0h]
0x18004c571  movaps  xmmword ptr [rsi+0C0h], xmm0
0x18004c578  movaps  xmm1, xmmword ptr [rdi+0D0h]
0x18004c57f  movaps  xmmword ptr [rsi+0D0h], xmm1
0x18004c586  movaps  xmm0, xmmword ptr [rdi+0E0h]
0x18004c58d  movaps  xmmword ptr [rsi+0E0h], xmm0
0x18004c594  jmp     loc_18004D361
0x18004c599  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018004C52C cases 131074,131077
0x18004c5a0  movaps  xmmword ptr [rsi+80h], xmm0
0x18004c5a7  movaps  xmm1, xmmword ptr [rdi+90h]
0x18004c5ae  movaps  xmmword ptr [rsi+90h], xmm1
0x18004c5b5  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x18004c5bc  movaps  xmmword ptr [rsi+0A0h], xmm0
0x18004c5c3  movaps  xmm1, xmmword ptr [rdi+0B0h]
0x18004c5ca  movaps  xmmword ptr [rsi+0B0h], xmm1
0x18004c5d1  movaps  xmm0, xmmword ptr [rdi+0C0h]
0x18004c5d8  movaps  xmmword ptr [rsi+0C0h], xmm0
0x18004c5df  movaps  xmm1, xmmword ptr [rdi+0D0h]
0x18004c5e6  movaps  xmmword ptr [rsi+0D0h], xmm1
0x18004c5ed  movaps  xmm0, xmmword ptr [rdi+0E0h]
0x18004c5f4  movaps  xmmword ptr [rsi+0E0h], xmm0
0x18004c5fb  movaps  xmm1, xmmword ptr [rdi+0F0h]
0x18004c602  movaps  xmmword ptr [rsi+0F0h], xmm1
0x18004c609  jmp     loc_18004D361
0x18004c60e  movups  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018004C52C cases 131078,131079
0x18004c615  movups  xmmword ptr [rsi+80h], xmm0
0x18004c61c  movups  xmm1, xmmword ptr [rdi+90h]
0x18004c623  movups  xmmword ptr [rsi+90h], xmm1
0x18004c62a  movups  xmm0, xmmword ptr [rdi+0A0h]
0x18004c631  movups  xmmword ptr [rsi+0A0h], xmm0
0x18004c638  movups  xmm1, xmmword ptr [rdi+0B0h]
0x18004c63f  movups  xmmword ptr [rsi+0B0h], xmm1
0x18004c646  movups  xmm0, xmmword ptr [rdi+0C0h]
0x18004c64d  movups  xmmword ptr [rsi+0C0h], xmm0
0x18004c654  movups  xmm1, xmmword ptr [rdi+0D0h]
0x18004c65b  movups  xmmword ptr [rsi+0D0h], xmm1
0x18004c662  movups  xmm0, xmmword ptr [rdi+0E0h]
0x18004c669  movups  xmmword ptr [rsi+0E0h], xmm0
0x18004c670  movups  xmm1, xmmword ptr [rdi+0F0h]
0x18004c677  movups  xmmword ptr [rsi+0F0h], xmm1
0x18004c67e  movups  xmm0, xmmword ptr [rdi+100h]
0x18004c685  movups  xmmword ptr [rsi+100h], xmm0
0x18004c68c  movups  xmm1, xmmword ptr [rdi+110h]
0x18004c693  movups  xmmword ptr [rsi+110h], xmm1
0x18004c69a  movups  xmm0, xmmword ptr [rdi+120h]
0x18004c6a1  movups  xmmword ptr [rsi+120h], xmm0
0x18004c6a8  movups  xmm1, xmmword ptr [rdi+130h]
0x18004c6af  movups  xmmword ptr [rsi+130h], xmm1
0x18004c6b6  movups  xmm0, xmmword ptr [rdi+140h]
0x18004c6bd  movups  xmmword ptr [rsi+140h], xmm0
0x18004c6c4  movups  xmm1, xmmword ptr [rdi+150h]
0x18004c6cb  movups  xmmword ptr [rsi+150h], xmm1
0x18004c6d2  jmp     loc_18004D361
0x18004c6d7  mov     r9, [rdi+0A80h]; jumptable 000000018004C52C case 131080
0x18004c6de  lea     rbx, [rsi+80h]
0x18004c6e5  mov     rdx, [rdi+880h]
0x18004c6ec  lea     r8, [rdi+0A88h]
0x18004c6f3  mov     rcx, rbx
0x18004c6f6  call    SymCryptGcmExpandKey
0x18004c6fb  cmp     [rdi+74h], r12d
0x18004c6ff  jz      loc_18004D361
0x18004c705  movaps  xmm0, xmmword ptr [rdi+0AB0h]
0x18004c70c  movaps  xmmword ptr [rsi+0AB0h], xmm0
0x18004c713  movaps  xmm1, xmmword ptr [rdi+0AC0h]
0x18004c71a  movaps  xmmword ptr [rsi+0AC0h], xmm1
0x18004c721  movaps  xmm0, xmmword ptr [rdi+0AD0h]
0x18004c728  movaps  xmmword ptr [rsi+0AD0h], xmm0
0x18004c72f  movaps  xmm1, xmmword ptr [rdi+0AE0h]
0x18004c736  movaps  xmmword ptr [rsi+0AE0h], xmm1
0x18004c73d  movaps  xmm0, xmmword ptr [rdi+0AF0h]
0x18004c744  movaps  xmmword ptr [rsi+0AF0h], xmm0
0x18004c74b  movaps  xmm1, xmmword ptr [rdi+0B00h]
0x18004c752  movaps  xmmword ptr [rsi+0B00h], xmm1
0x18004c759  movaps  xmm0, xmmword ptr [rdi+0B10h]
0x18004c760  movaps  xmmword ptr [rsi+0B10h], xmm0
0x18004c767  test    rbx, rbx
0x18004c76a  jz      loc_18004D361
0x18004c770  mov     [rsi+0AB0h], rbx
0x18004c777  jmp     loc_18004D361
0x18004c77c  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018004C52C case 131081
0x18004c783  lea     rdx, [rsi+80h]
0x18004c78a  movaps  xmmword ptr [rdx], xmm0
0x18004c78d  lea     r8, [rsi+0D0h]
0x18004c794  movaps  xmm1, xmmword ptr [rdi+90h]
0x18004c79b  lea     rcx, [rdi+0D0h]
0x18004c7a2  movaps  xmmword ptr [rdx+10h], xmm1
0x18004c7a6  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x18004c7ad  movaps  xmmword ptr [rdx+20h], xmm0
0x18004c7b1  movaps  xmm1, xmmword ptr [rdi+0B0h]
0x18004c7b8  movaps  xmmword ptr [rdx+30h], xmm1
0x18004c7bc  movaps  xmm0, xmmword ptr [rdi+0C0h]
0x18004c7c3  movaps  xmmword ptr [rdx+40h], xmm0
0x18004c7c7  call    SymCryptHmacSha1StateCopy
0x18004c7cc  jmp     loc_18004D361
0x18004c7d1  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018004C52C case 131082
0x18004c7d8  lea     rdx, [rsi+80h]
0x18004c7df  movaps  xmmword ptr [rdx], xmm0
0x18004c7e2  lea     r8, [rsi+0B0h]
0x18004c7e9  movaps  xmm1, xmmword ptr [rdi+90h]
0x18004c7f0  lea     rcx, [rdi+0B0h]
0x18004c7f7  movaps  xmmword ptr [rdx+10h], xmm1
0x18004c7fb  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x18004c802  movaps  xmmword ptr [rdx+20h], xmm0
0x18004c806  call    SymCryptHmacMd5StateCopy
0x18004c80b  jmp     loc_18004D361
0x18004c810  movaps  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018004C52C case 131083
0x18004c817  lea     rdx, [rsi+80h]
0x18004c81e  movaps  xmmword ptr [rdx], xmm0
0x18004c821  lea     r8, [rsi+0D0h]
0x18004c828  movaps  xmm1, xmmword ptr [rdi+90h]
0x18004c82f  lea     rcx, [rdi+0D0h]
0x18004c836  movaps  xmmword ptr [rdx+10h], xmm1
0x18004c83a  movaps  xmm0, xmmword ptr [rdi+0A0h]
0x18004c841  movaps  xmmword ptr [rdx+20h], xmm0
0x18004c845  movaps  xmm1, xmmword ptr [rdi+0B0h]
0x18004c84c  movaps  xmmword ptr [rdx+30h], xmm1
0x18004c850  movaps  xmm0, xmmword ptr [rdi+0C0h]
0x18004c857  movaps  xmmword ptr [rdx+40h], xmm0
0x18004c85b  call    SymCryptHmacSha1StateCopy
0x18004c860  jmp     loc_18004D361
0x18004c865  movups  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018004C52C case 131084
0x18004c86c  lea     rdx, [rsi+80h]
0x18004c873  lea     r8, [rsi+110h]
0x18004c87a  movups  xmmword ptr [rdx], xmm0
0x18004c87d  lea     rcx, [rdi+110h]
0x18004c884  movups  xmm1, xmmword ptr [rdi+90h]
0x18004c88b  movups  xmmword ptr [rdx+10h], xmm1
0x18004c88f  movups  xmm0, xmmword ptr [rdi+0A0h]
0x18004c896  movups  xmmword ptr [rdx+20h], xmm0
0x18004c89a  movups  xmm1, xmmword ptr [rdi+0B0h]
0x18004c8a1  movups  xmmword ptr [rdx+30h], xmm1
0x18004c8a5  movups  xmm0, xmmword ptr [rdi+0C0h]
0x18004c8ac  movups  xmmword ptr [rdx+40h], xmm0
0x18004c8b0  movups  xmm1, xmmword ptr [rdi+0D0h]
0x18004c8b7  movups  xmmword ptr [rdx+50h], xmm1
0x18004c8bb  movups  xmm0, xmmword ptr [rdi+0E0h]
0x18004c8c2  movups  xmmword ptr [rdx+60h], xmm0
0x18004c8c6  movups  xmm1, xmmword ptr [rdi+0F0h]
0x18004c8cd  movups  xmmword ptr [rdx+70h], xmm1
0x18004c8d1  movups  xmm0, xmmword ptr [rdi+100h]
0x18004c8d8  movups  xmmword ptr [rdx+80h], xmm0
0x18004c8df  call    SymCryptHmacSha512StateCopy
0x18004c8e4  jmp     loc_18004D361
0x18004c8e9  movups  xmm0, xmmword ptr [rdi+80h]; jumptable 000000018004C52C case 131085
0x18004c8f0  lea     rdx, [rsi+80h]
0x18004c8f7  lea     r8, [rsi+110h]
0x18004c8fe  movups  xmmword ptr [rdx], xmm0
0x18004c901  lea     rcx, [rdi+110h]
0x18004c908  movups  xmm1, xmmword ptr [rdi+90h]
0x18004c90f  movups  xmmword ptr [rdx+10h], xmm1
0x18004c913  movups  xmm0, xmmword ptr [rdi+0A0h]
0x18004c91a  movups  xmmword ptr [rdx+20h], xmm0
0x18004c91e  movups  xmm1, xmmword ptr [rdi+0B0h]
0x18004c925  movups  xmmword ptr [rdx+30h], xmm1
0x18004c929  movups  xmm0, xmmword ptr [rdi+0C0h]
0x18004c930  movups  xmmword ptr [rdx+40h], xmm0
0x18004c934  movups  xmm1, xmmword ptr [rdi+0D0h]
0x18004c93b  movups  xmmword ptr [rdx+50h], xmm1
0x18004c93f  movups  xmm0, xmmword ptr [rdi+0E0h]
0x18004c946  movups  xmmword ptr [rdx+60h], xmm0
0x18004c94a  movups  xmm1, xmmword ptr [rdi+0F0h]
0x18004c951  movups  xmmword ptr [rdx+70h], xmm1
0x18004c955  movups  xmm0, xmmword ptr [rdi+100h]
0x18004c95c  movups  xmmword ptr [rdx+80h], xmm0
0x18004c963  call    SymCryptHmacSha512StateCopy
0x18004c968  jmp     loc_18004D361
0x18004c96d  lea     rdx, [rsi+80h]; jumptable 000000018004C52C case 131086
0x18004c974  lea     rcx, [rdi+80h]
0x18004c97b  call    SymCryptAesKeyCopy
0x18004c980  movups  xmm2, xmmword ptr [rcx+1F0h]
0x18004c987  movdqu  xmmword ptr [rdx+1F0h], xmm2
0x18004c98f  movups  xmm3, xmmword ptr [rcx+200h]
0x18004c996  movdqu  xmmword ptr [rdx+200h], xmm3
0x18004c99e  movaps  xmm0, xmmword ptr [rdi+2A0h]
0x18004c9a5  movaps  xmmword ptr [rsi+2A0h], xmm0
0x18004c9ac  movaps  xmm1, xmmword ptr [rdi+2B0h]
0x18004c9b3  movaps  xmmword ptr [rsi+2B0h], xmm1
0x18004c9ba  movaps  xmm0, xmmword ptr [rdi+2C0h]
0x18004c9c1  movaps  xmmword ptr [rsi+2C0h], xmm0
0x18004c9c8  movaps  xmm1, xmmword ptr [rdi+2D0h]
0x18004c9cf  movaps  xmmword ptr [rsi+2D0h], xmm1
0x18004c9d6  test    rdx, rdx
0x18004c9d9  jnz     short loc_18004C9E2
0x18004c9db  mov     rdx, [rdi+2C8h]
0x18004c9e2  mov     [rsi+2C8h], rdx
0x18004c9e9  jmp     loc_18004D361
0x18004c9ee  lea     rdx, [rsi+80h]; jumptable 000000018004C52C case 131087
0x18004c9f5  lea     rcx, [rdi+80h]; Src
0x18004c9fc  call    SymCryptSha3_256StateCopy
0x18004ca01  jmp     loc_18004D361
0x18004ca06  lea     rdx, [rsi+80h]; jumptable 000000018004C52C case 131088
0x18004ca0d  lea     rcx, [rdi+80h]; Src
0x18004ca14  call    SymCryptSha3_384StateCopy
0x18004ca19  jmp     loc_18004D361
0x18004ca1e  lea     rdx, [rsi+80h]; jumptable 000000018004C52C case 131089
0x18004ca25  lea     rcx, [rdi+80h]; Src
0x18004ca2c  call    SymCryptSha3_512StateCopy
0x18004ca31  jmp     loc_18004D361
0x18004ca36  lea     rbx, [rsi+80h]; jumptable 000000018004C52C cases 131090-131092
0x18004ca3d  mov     rdx, rbx
0x18004ca40  lea     rcx, [rdi+80h]
0x18004ca47  call    SymCryptHmacKeyCopy
0x18004ca4c  lea     r8, [rsi+280h]
0x18004ca53  mov     rdx, rbx
0x18004ca56  lea     rcx, [rdi+280h]
0x18004ca5d  call    SymCryptHmacStateCopy
0x18004ca62  jmp     loc_18004D361
0x18004ca67  mov     eax, [rdi+118h]; jumptable 000000018004C52C case 131093
0x18004ca6d  sub     eax, 2
0x18004ca70  cmp     eax, 1
0x18004ca73  ja      loc_18004CB4B
0x18004ca79  movups  xmm0, xmmword ptr [rdi+210h]
0x18004ca80  movups  xmmword ptr [rsi+210h], xmm0
0x18004ca87  movups  xmm1, xmmword ptr [rdi+220h]
0x18004ca8e  movups  xmmword ptr [rsi+220h], xmm1
0x18004ca95  movups  xmm0, xmmword ptr [rdi+230h]
0x18004ca9c  movups  xmmword ptr [rsi+230h], xmm0
0x18004caa3  movups  xmm1, xmmword ptr [rdi+240h]
0x18004caaa  movups  xmmword ptr [rsi+240h], xmm1
0x18004cab1  movups  xmm0, xmmword ptr [rdi+250h]
0x18004cab8  movups  xmmword ptr [rsi+250h], xmm0
0x18004cabf  movups  xmm1, xmmword ptr [rdi+260h]
0x18004cac6  movups  xmmword ptr [rsi+260h], xmm1
0x18004cacd  movups  xmm0, xmmword ptr [rdi+270h]
0x18004cad4  movups  xmmword ptr [rsi+270h], xmm0
0x18004cadb  movups  xmm1, xmmword ptr [rdi+280h]
0x18004cae2  movups  xmmword ptr [rsi+280h], xmm1
0x18004cae9  movups  xmm0, xmmword ptr [rdi+290h]
0x18004caf0  movups  xmmword ptr [rsi+290h], xmm0
0x18004caf7  movups  xmm1, xmmword ptr [rdi+2A0h]
0x18004cafe  movups  xmmword ptr [rsi+2A0h], xmm1
0x18004cb05  movups  xmm0, xmmword ptr [rdi+2B0h]
0x18004cb0c  movups  xmmword ptr [rsi+2B0h], xmm0
0x18004cb13  movups  xmm1, xmmword ptr [rdi+2C0h]
0x18004cb1a  movups  xmmword ptr [rsi+2C0h], xmm1
0x18004cb21  movups  xmm0, xmmword ptr [rdi+2D0h]
  ... truncated ...
```
