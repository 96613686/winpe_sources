# g_ConfigureDstBMPProperty(CDeColorConvParams *,tagBITMAPINFOHEADER *)

- ea: `0x180043f84`
- end: `0x1800443b4`
- name: `?g_ConfigureDstBMPProperty@@YAJPEAVCDeColorConvParams@@PEAUtagBITMAPINFOHEADER@@@Z`
- size: `1072`
- prototype: `__int64 __fastcall(struct CDeColorConvParams *, struct tagBITMAPINFOHEADER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180043db8`

## callees

- `0x180043f84`

## pseudocode

```c
__int64 __fastcall g_ConfigureDstBMPProperty(struct CDeColorConvParams *a1, struct tagBITMAPINFOHEADER *a2)
{
  int v2; // r8d
  bool v3; // zf
  int v4; // eax
  __int16 v5; // ax
  void (*v6)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int); // rax
  void (__fastcall *v7)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int); // r8
  void (__fastcall *v8)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int); // rdx
  int v9; // r9d
  int v10; // eax
  int v11; // edx
  void (__fastcall *v12)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int); // rdx
  void (__fastcall *v13)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int); // r8
  void (*v14)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int); // rax
  void (__fastcall *v15)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int); // rax
  void (__fastcall *v16)(unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int); // rax

  v2 = 3;
  v3 = a2->biCompression == 3;
  *(_OWORD *)a1 = *(_OWORD *)&a2->biSize;
  *((_OWORD *)a1 + 1) = *(_OWORD *)&a2->biCompression;
  if ( v3 )
  {
    *((_OWORD *)a1 + 2) = *(_OWORD *)&a2->biClrUsed;
    *((_DWORD *)a1 + 12) = a2[1].biHeight;
  }
  else
  {
    *((_QWORD *)a1 + 4) = *(_QWORD *)&a2->biClrUsed;
  }
  v4 = *((_DWORD *)a1 + 4);
  *((_QWORD *)a1 + 13) = 0;
  *((_QWORD *)a1 + 14) = 0;
  if ( v4 )
  {
    switch ( v4 )
    {
      case 3:
        v3 = *((_WORD *)a1 + 7) == 16;
        *((_DWORD *)a1 + 14) = 0;
        if ( v3 )
        {
          v9 = 31744;
          if ( *((_DWORD *)a1 + 10) == 31744 )
          {
            v10 = 992;
            if ( *((_DWORD *)a1 + 11) != 992 || *((_DWORD *)a1 + 12) != 31 )
              return 4294967294LL;
            v11 = 7;
            v2 = 2;
          }
          else
          {
            v9 = 63488;
            if ( *((_DWORD *)a1 + 10) != 63488 )
              return 4294967294LL;
            v10 = 2016;
            if ( *((_DWORD *)a1 + 11) != 2016 || *((_DWORD *)a1 + 12) != 31 )
              return 4294967294LL;
            v11 = 8;
          }
          *((_DWORD *)a1 + 26) = v11;
          *((_DWORD *)a1 + 27) = v2;
          *((_DWORD *)a1 + 28) = v9;
          *((_DWORD *)a1 + 29) = v10;
          if ( *((_DWORD *)a1 + 17) )
            goto LABEL_7;
          v6 = (void (*)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int))UpdateDstPartialMBRGB16;
          v12 = UpdateDstBlkRGB16;
          v13 = UpdateDstMBRGB16;
        }
        else
        {
          if ( *((_WORD *)a1 + 7) != 32
            || *((_DWORD *)a1 + 10) != 16711680
            || *((_DWORD *)a1 + 11) != 65280
            || *((_DWORD *)a1 + 12) != 255 )
          {
            return 4294967294LL;
          }
          v6 = (void (*)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int))UpdateDstPartialMBRGB32;
          v12 = UpdateDstBlkRGB32;
          v13 = UpdateDstMBRGB32;
        }
        *((_QWORD *)a1 + 28) = v13;
        *((_QWORD *)a1 + 30) = v12;
        goto LABEL_40;
      case 1498831189:
        *((_DWORD *)a1 + 14) = 1;
        *((_DWORD *)a1 + 13) = 1;
        if ( *((_DWORD *)a1 + 17) )
        {
          *((_QWORD *)a1 + 28) = UpdateDst411MBUYVY;
          v14 = UpdateDst411PartialMBUYVY;
LABEL_44:
          *((_QWORD *)a1 + 29) = v14;
          return 0;
        }
        *((_QWORD *)a1 + 28) = UpdateDstMBUYVY;
        *((_QWORD *)a1 + 29) = UpdateDstPartialMBUYVY;
        v15 = UpdateDstBlkUYVY;
        goto LABEL_54;
      case 1431918169:
        *((_DWORD *)a1 + 14) = 1;
        *((_DWORD *)a1 + 13) = 1;
        if ( *((_DWORD *)a1 + 17) )
        {
          *((_QWORD *)a1 + 28) = UpdateDst411MBYVYU;
          v14 = UpdateDst411PartialMBYVYU;
          goto LABEL_44;
        }
        *((_QWORD *)a1 + 28) = UpdateDstMBYVYU;
        *((_QWORD *)a1 + 29) = UpdateDstPartialMBYVYU;
        v15 = UpdateDstBlkYVYU;
LABEL_54:
        *((_QWORD *)a1 + 30) = v15;
        return 0;
      case 844715353:
        *((_DWORD *)a1 + 14) = 1;
        *((_DWORD *)a1 + 13) = 1;
        if ( *((_DWORD *)a1 + 17) )
        {
          *((_QWORD *)a1 + 28) = UpdateDst411MBYUY2;
          v14 = UpdateDst411PartialMBYUY2;
          goto LABEL_44;
        }
        *((_QWORD *)a1 + 28) = UpdateDstMBYUY2;
        *((_QWORD *)a1 + 29) = UpdateDstPartialMBYUY2;
        v15 = UpdateDstBlkYUY2;
        goto LABEL_54;
      case 961893977:
        *((_QWORD *)a1 + 32) = UpdateDstPartialMBYVU9;
        v16 = UpdateDstMBYVU9;
        break;
      default:
        if ( v4 != 842094169 )
        {
          if ( v4 == 842094158 )
          {
            *((_QWORD *)a1 + 31) = UpdateDstMBNV12;
            *((_QWORD *)a1 + 32) = UpdateDstPartialMBNV12;
LABEL_65:
            *((_DWORD *)a1 + 14) = 1;
            *((_DWORD *)a1 + 13) = 0;
            return 0;
          }
          if ( v4 != 1448433993 && v4 != 808596553 )
            return 4294967294LL;
        }
        *((_QWORD *)a1 + 32) = UpdateDstPartialMBYV12;
        v16 = UpdateDstMBYV12;
        break;
    }
    *((_QWORD *)a1 + 31) = v16;
    goto LABEL_65;
  }
  v5 = *((_WORD *)a1 + 7);
  *((_DWORD *)a1 + 14) = 0;
  if ( v5 != 16 )
  {
    switch ( v5 )
    {
      case 24:
        if ( *((_DWORD *)a1 + 17) )
        {
          *((_QWORD *)a1 + 28) = UpdateDst411MBRGB24;
          v6 = UpdateDst411PartialMBRGB24;
          goto LABEL_40;
        }
        if ( *((_DWORD *)a1 + 18) )
        {
          *((_QWORD *)a1 + 28) = UpdateDst422MBRGB24;
          v6 = (void (*)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int))UpdateDst422PartialMBRGB24;
          goto LABEL_40;
        }
        v6 = (void (*)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int))UpdateDstPartialMBRGB24;
        v7 = UpdateDstMBRGB24;
        v8 = UpdateDstBlkRGB24;
LABEL_21:
        *((_QWORD *)a1 + 30) = v8;
        *((_QWORD *)a1 + 28) = v7;
        goto LABEL_40;
      case 32:
        if ( *((_DWORD *)a1 + 17) )
        {
          *((_QWORD *)a1 + 28) = UpdateDst411MBRGB32;
          v6 = (void (*)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int))UpdateDst411PartialMBRGB32;
          goto LABEL_40;
        }
        v6 = (void (*)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int))UpdateDstPartialMBRGB32;
        v7 = UpdateDstMBRGB32;
        v8 = UpdateDstBlkRGB32;
        goto LABEL_21;
      case 8:
        v6 = (void (*)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int))UpdateDstPartialMBRGB8;
        v7 = UpdateDstMBRGB8;
        v8 = UpdateDstBlkRGB8;
        goto LABEL_21;
    }
    return 4294967294LL;
  }
  *((_DWORD *)a1 + 26) = 7;
  *((_DWORD *)a1 + 27) = 2;
  *((_DWORD *)a1 + 28) = 31744;
  *((_DWORD *)a1 + 29) = 992;
  if ( !*((_DWORD *)a1 + 17) )
  {
    v6 = (void (*)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int))UpdateDstPartialMBRGB16;
    v7 = UpdateDstMBRGB16;
    v8 = UpdateDstBlkRGB16;
    goto LABEL_21;
  }
LABEL_7:
  *((_QWORD *)a1 + 28) = UpdateDst411MBRGB16;
  v6 = (void (*)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int))UpdateDst411PartialMBRGB16;
LABEL_40:
  *((_QWORD *)a1 + 29) = v6;
  *((_DWORD *)a1 + 13) = 1;
  return 0;
}

```

## disassembly

```asm
0x180043f84  movups  xmm0, xmmword ptr [rdx]
0x180043f87  mov     r8d, 3
0x180043f8d  cmp     [rdx+10h], r8d
0x180043f91  movups  xmmword ptr [rcx], xmm0
0x180043f94  movups  xmm1, xmmword ptr [rdx+10h]
0x180043f98  movups  xmmword ptr [rcx+10h], xmm1
0x180043f9c  jnz     short loc_180043FAE
0x180043f9e  movups  xmm0, xmmword ptr [rdx+20h]
0x180043fa2  movups  xmmword ptr [rcx+20h], xmm0
0x180043fa6  mov     eax, [rdx+30h]
0x180043fa9  mov     [rcx+30h], eax
0x180043fac  jmp     short loc_180043FB8
0x180043fae  movsd   xmm0, qword ptr [rdx+20h]
0x180043fb3  movsd   qword ptr [rcx+20h], xmm0
0x180043fb8  mov     eax, [rcx+10h]
0x180043fbb  xor     r10d, r10d
0x180043fbe  mov     [rcx+68h], r10
0x180043fc2  mov     [rcx+70h], r10
0x180043fc6  test    eax, eax
0x180043fc8  jnz     loc_180044102
0x180043fce  movzx   eax, word ptr [rcx+0Eh]
0x180043fd2  mov     [rcx+38h], r10d
0x180043fd6  cmp     ax, 10h
0x180043fda  jnz     short loc_180044032
0x180043fdc  mov     dword ptr [rcx+68h], 7
0x180043fe3  mov     dword ptr [rcx+6Ch], 2
0x180043fea  mov     dword ptr [rcx+70h], 7C00h
0x180043ff1  mov     dword ptr [rcx+74h], 3E0h
0x180043ff8  cmp     [rcx+44h], r10d
0x180043ffc  jz      short loc_180044018
0x180043ffe  lea     rax, ?UpdateDst411MBRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDst411MBRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x180044005  mov     [rcx+0E0h], rax
0x18004400c  lea     rax, ?UpdateDst411PartialMBRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDst411PartialMBRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x180044013  jmp     loc_1800441FA
0x180044018  lea     rax, ?UpdateDstPartialMBRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18004401f  lea     r8, ?UpdateDstMBRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstMBRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x180044026  lea     rdx, ?UpdateDstBlkRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstBlkRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18004402d  jmp     loc_1800440EF
0x180044032  cmp     ax, 18h
0x180044036  jnz     short loc_18004408F
0x180044038  cmp     [rcx+44h], r10d
0x18004403c  jz      short loc_180044058
0x18004403e  lea     rax, ?UpdateDst411MBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDst411MBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x180044045  mov     [rcx+0E0h], rax
0x18004404c  lea     rax, ?UpdateDst411PartialMBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDst411PartialMBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x180044053  jmp     loc_1800441FA
0x180044058  cmp     [rcx+48h], r10d
0x18004405c  jz      short loc_180044078
0x18004405e  lea     rax, ?UpdateDst422MBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDst422MBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x180044065  mov     [rcx+0E0h], rax
0x18004406c  lea     rax, ?UpdateDst422PartialMBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDst422PartialMBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x180044073  jmp     loc_1800441FA
0x180044078  lea     rax, ?UpdateDstPartialMBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18004407f  lea     r8, ?UpdateDstMBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstMBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x180044086  lea     rdx, ?UpdateDstBlkRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstBlkRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18004408d  jmp     short loc_1800440EF
0x18004408f  cmp     ax, 20h ; ' '
0x180044093  jnz     short loc_1800440CC
0x180044095  cmp     [rcx+44h], r10d
0x180044099  jz      short loc_1800440B5
0x18004409b  lea     rax, ?UpdateDst411MBRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDst411MBRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x1800440a2  mov     [rcx+0E0h], rax
0x1800440a9  lea     rax, ?UpdateDst411PartialMBRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDst411PartialMBRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x1800440b0  jmp     loc_1800441FA
0x1800440b5  lea     rax, ?UpdateDstPartialMBRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x1800440bc  lea     r8, ?UpdateDstMBRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstMBRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x1800440c3  lea     rdx, ?UpdateDstBlkRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstBlkRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x1800440ca  jmp     short loc_1800440EF
0x1800440cc  mov     edx, 8
0x1800440d1  cmp     ax, dx
0x1800440d4  jnz     loc_180044384
0x1800440da  lea     rax, ?UpdateDstPartialMBRGB8@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBRGB8(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x1800440e1  lea     r8, ?UpdateDstMBRGB8@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstMBRGB8(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x1800440e8  lea     rdx, ?UpdateDstBlkRGB8@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstBlkRGB8(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x1800440ef  mov     [rcx+0F0h], rdx
0x1800440f6  mov     [rcx+0E0h], r8
0x1800440fd  jmp     loc_1800441FA
0x180044102  cmp     eax, r8d
0x180044105  jnz     loc_18004420D
0x18004410b  cmp     word ptr [rcx+0Eh], 10h
0x180044110  mov     [rcx+38h], r10d
0x180044114  jnz     loc_1800441A5
0x18004411a  mov     r9d, 7C00h
0x180044120  cmp     [rcx+28h], r9d
0x180044124  jnz     short loc_180044149
0x180044126  mov     eax, 3E0h
0x18004412b  cmp     [rcx+2Ch], eax
0x18004412e  jnz     loc_180044384
0x180044134  cmp     dword ptr [rcx+30h], 1Fh
0x180044138  jnz     loc_180044384
0x18004413e  mov     edx, 7
0x180044143  lea     r8d, [rdx-5]
0x180044147  jmp     short loc_180044176
0x180044149  mov     r9d, 0F800h
0x18004414f  cmp     [rcx+28h], r9d
0x180044153  jnz     loc_180044384
0x180044159  mov     eax, 7E0h
0x18004415e  cmp     [rcx+2Ch], eax
0x180044161  jnz     loc_180044384
0x180044167  cmp     dword ptr [rcx+30h], 1Fh
0x18004416b  jnz     loc_180044384
0x180044171  mov     edx, 8
0x180044176  mov     [rcx+68h], edx
0x180044179  mov     [rcx+6Ch], r8d
0x18004417d  mov     [rcx+70h], r9d
0x180044181  mov     [rcx+74h], eax
0x180044184  cmp     [rcx+44h], r10d
0x180044188  jnz     loc_180043FFE
0x18004418e  lea     rax, ?UpdateDstPartialMBRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x180044195  lea     rdx, ?UpdateDstBlkRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstBlkRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18004419c  lea     r8, ?UpdateDstMBRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstMBRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x1800441a3  jmp     short loc_1800441EC
0x1800441a5  cmp     word ptr [rcx+0Eh], 20h ; ' '
0x1800441aa  jnz     loc_180044384
0x1800441b0  cmp     dword ptr [rcx+28h], 0FF0000h
0x1800441b7  jnz     loc_180044384
0x1800441bd  cmp     dword ptr [rcx+2Ch], 0FF00h
0x1800441c4  jnz     loc_180044384
0x1800441ca  cmp     dword ptr [rcx+30h], 0FFh
0x1800441d1  jnz     loc_180044384
0x1800441d7  lea     rax, ?UpdateDstPartialMBRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x1800441de  lea     rdx, ?UpdateDstBlkRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstBlkRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x1800441e5  lea     r8, ?UpdateDstMBRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstMBRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x1800441ec  mov     [rcx+0E0h], r8
0x1800441f3  mov     [rcx+0F0h], rdx
0x1800441fa  mov     [rcx+0E8h], rax
0x180044201  mov     dword ptr [rcx+34h], 1
0x180044208  jmp     loc_1800443B1
0x18004420d  cmp     eax, 59565955h
0x180044212  jnz     short loc_180044271
0x180044214  mov     dword ptr [rcx+38h], 1
0x18004421b  mov     dword ptr [rcx+34h], 1
0x180044222  cmp     [rcx+44h], r10d
0x180044226  jz      short loc_180044249
0x180044228  lea     rax, ?UpdateDst411MBUYVY@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDst411MBUYVY(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18004422f  mov     [rcx+0E0h], rax
0x180044236  lea     rax, ?UpdateDst411PartialMBUYVY@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDst411PartialMBUYVY(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18004423d  mov     [rcx+0E8h], rax
0x180044244  jmp     loc_1800443B1
0x180044249  lea     rax, ?UpdateDstMBUYVY@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstMBUYVY(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x180044250  mov     [rcx+0E0h], rax
0x180044257  lea     rax, ?UpdateDstPartialMBUYVY@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBUYVY(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18004425e  mov     [rcx+0E8h], rax
0x180044265  lea     rax, ?UpdateDstBlkUYVY@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstBlkUYVY(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18004426c  jmp     loc_180044320
0x180044271  cmp     eax, 55595659h
0x180044276  jnz     short loc_1800442C8
0x180044278  mov     dword ptr [rcx+38h], 1
0x18004427f  mov     dword ptr [rcx+34h], 1
0x180044286  cmp     [rcx+44h], r10d
0x18004428a  jz      short loc_1800442A3
0x18004428c  lea     rax, ?UpdateDst411MBYVYU@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDst411MBYVYU(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x180044293  mov     [rcx+0E0h], rax
0x18004429a  lea     rax, ?UpdateDst411PartialMBYVYU@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDst411PartialMBYVYU(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x1800442a1  jmp     short loc_18004423D
0x1800442a3  lea     rax, ?UpdateDstMBYVYU@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstMBYVYU(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x1800442aa  mov     [rcx+0E0h], rax
0x1800442b1  lea     rax, ?UpdateDstPartialMBYVYU@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBYVYU(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x1800442b8  mov     [rcx+0E8h], rax
0x1800442bf  lea     rax, ?UpdateDstBlkYVYU@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstBlkYVYU(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x1800442c6  jmp     short loc_180044320
0x1800442c8  cmp     eax, 32595559h
0x1800442cd  jnz     short loc_18004432C
0x1800442cf  mov     dword ptr [rcx+38h], 1
0x1800442d6  mov     dword ptr [rcx+34h], 1
0x1800442dd  cmp     [rcx+44h], r10d
0x1800442e1  jz      short loc_1800442FD
0x1800442e3  lea     rax, ?UpdateDst411MBYUY2@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDst411MBYUY2(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x1800442ea  mov     [rcx+0E0h], rax
0x1800442f1  lea     rax, ?UpdateDst411PartialMBYUY2@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDst411PartialMBYUY2(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x1800442f8  jmp     loc_18004423D
0x1800442fd  lea     rax, ?UpdateDstMBYUY2@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstMBYUY2(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x180044304  mov     [rcx+0E0h], rax
0x18004430b  lea     rax, ?UpdateDstPartialMBYUY2@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBYUY2(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x180044312  mov     [rcx+0E8h], rax
0x180044319  lea     rax, ?UpdateDstBlkYUY2@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstBlkYUY2(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x180044320  mov     [rcx+0F0h], rax
0x180044327  jmp     loc_1800443B1
0x18004432c  cmp     eax, 39555659h
0x180044331  jnz     short loc_18004434A
0x180044333  lea     rax, ?UpdateDstPartialMBYVU9@@YAXPEAE00PEBE11JJJJJJ@Z; UpdateDstPartialMBYVU9(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long,long,long)
0x18004433a  mov     [rcx+100h], rax
0x180044341  lea     rax, ?UpdateDstMBYVU9@@YAXPEAE00PEBE11JJJJ@Z; UpdateDstMBYVU9(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x180044348  jmp     short loc_18004439F
0x18004434a  cmp     eax, 32315659h
0x18004434f  jz      short loc_18004438A
0x180044351  cmp     eax, 3231564Eh
0x180044356  jnz     short loc_180044376
0x180044358  lea     rax, ?UpdateDstMBNV12@@YAXPEAE00PEBE11JJJJ@Z; UpdateDstMBNV12(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18004435f  mov     [rcx+0F8h], rax
0x180044366  lea     rax, ?UpdateDstPartialMBNV12@@YAXPEAE00PEBE11JJJJJJ@Z; UpdateDstPartialMBNV12(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long,long,long)
0x18004436d  mov     [rcx+100h], rax
0x180044374  jmp     short loc_1800443A6
0x180044376  cmp     eax, 56555949h
0x18004437b  jz      short loc_18004438A
0x18004437d  cmp     eax, 30323449h
0x180044382  jz      short loc_18004438A
0x180044384  mov     eax, 0FFFFFFFEh
0x180044389  retn
0x18004438a  lea     rax, ?UpdateDstPartialMBYV12@@YAXPEAE00PEBE11JJJJJJ@Z; UpdateDstPartialMBYV12(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long,long,long)
0x180044391  mov     [rcx+100h], rax
0x180044398  lea     rax, ?UpdateDstMBYV12@@YAXPEAE00PEBE11JJJJ@Z; UpdateDstMBYV12(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18004439f  mov     [rcx+0F8h], rax
0x1800443a6  mov     dword ptr [rcx+38h], 1
0x1800443ad  mov     [rcx+34h], r10d
0x1800443b1  xor     eax, eax
0x1800443b3  retn
```
