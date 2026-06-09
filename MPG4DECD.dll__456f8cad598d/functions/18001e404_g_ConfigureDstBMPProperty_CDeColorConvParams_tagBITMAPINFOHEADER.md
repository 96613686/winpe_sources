# g_ConfigureDstBMPProperty(CDeColorConvParams *,tagBITMAPINFOHEADER *)

- ea: `0x18001e404`
- end: `0x18001e6bc`
- name: `?g_ConfigureDstBMPProperty@@YAJPEAVCDeColorConvParams@@PEAUtagBITMAPINFOHEADER@@@Z`
- size: `696`
- prototype: `__int64 __fastcall(struct CDeColorConvParams *, struct tagBITMAPINFOHEADER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001e2c8`

## callees

- `0x18001e404`

## pseudocode

```c
__int64 __fastcall g_ConfigureDstBMPProperty(struct CDeColorConvParams *a1, struct tagBITMAPINFOHEADER *a2)
{
  bool v2; // zf
  int v3; // eax
  __int16 v4; // dx
  void (*v5)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int); // r8
  void (__fastcall *v6)(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int); // rdx
  void (__fastcall *v7)(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int); // rax
  int v8; // eax
  void (__fastcall *v9)(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int); // rdx
  void (__fastcall *v10)(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int); // rax
  void (*v11)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int); // r8
  void (__fastcall *v12)(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int); // rax
  void (__fastcall *v13)(unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int); // rax

  v2 = a2->biCompression == 3;
  *(_OWORD *)a1 = *(_OWORD *)&a2->biSize;
  *((_OWORD *)a1 + 1) = *(_OWORD *)&a2->biCompression;
  if ( v2 )
  {
    *((_OWORD *)a1 + 2) = *(_OWORD *)&a2->biClrUsed;
    *((_DWORD *)a1 + 12) = a2[1].biHeight;
  }
  else
  {
    *((_QWORD *)a1 + 4) = *(_QWORD *)&a2->biClrUsed;
  }
  v3 = *((_DWORD *)a1 + 4);
  g_redscale = 0;
  if ( v3 )
  {
    if ( v3 == 3 )
    {
      v2 = *((_WORD *)a1 + 7) == 16;
      *((_DWORD *)a1 + 14) = 0;
      if ( v2 )
      {
        if ( *((_DWORD *)a1 + 10) == 31744 )
        {
          if ( *((_DWORD *)a1 + 11) != 992 || *((_DWORD *)a1 + 12) != 31 )
            return 4294967294LL;
          v8 = 7;
        }
        else
        {
          if ( *((_DWORD *)a1 + 10) != 63488 || *((_DWORD *)a1 + 11) != 2016 || *((_DWORD *)a1 + 12) != 31 )
            return 4294967294LL;
          v8 = 8;
        }
        g_redscale = v8;
        v9 = UpdateDstMBRGB16;
        v10 = UpdateDstBlkRGB16;
        v11 = UpdateDstPartialMBRGB16;
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
        v10 = UpdateDstBlkRGB32;
        v9 = UpdateDstMBRGB32;
        v11 = UpdateDstPartialMBRGB32;
      }
      *((_QWORD *)a1 + 26) = v11;
      *((_QWORD *)a1 + 25) = v9;
      *((_QWORD *)a1 + 27) = v10;
      goto LABEL_31;
    }
    if ( v3 == 1498831189 )
    {
      *((_QWORD *)a1 + 25) = UpdateDstMBUYVY;
      *((_QWORD *)a1 + 26) = UpdateDstPartialMBUYVY;
      v12 = UpdateDstBlkUYVY;
    }
    else if ( v3 == 1431918169 )
    {
      *((_QWORD *)a1 + 25) = UpdateDstMBYVYU;
      *((_QWORD *)a1 + 26) = UpdateDstPartialMBYVYU;
      v12 = UpdateDstBlkYVYU;
    }
    else
    {
      if ( v3 != 844715353 )
      {
        if ( v3 == 961893977 )
        {
          *((_QWORD *)a1 + 29) = UpdateDstPartialMBYVU9;
          v13 = UpdateDstMBYVU9;
        }
        else
        {
          if ( v3 != 842094169 )
            return 4294967294LL;
          *((_QWORD *)a1 + 29) = UpdateDstPartialMBYV12;
          v13 = UpdateDstMBYV12;
        }
        *((_DWORD *)a1 + 13) = 0;
        *((_QWORD *)a1 + 28) = v13;
LABEL_44:
        *((_DWORD *)a1 + 14) = 1;
        return 0;
      }
      *((_QWORD *)a1 + 25) = UpdateDstMBYUY2;
      *((_QWORD *)a1 + 26) = UpdateDstPartialMBYUY2;
      v12 = UpdateDstBlkYUY2;
    }
    *((_QWORD *)a1 + 27) = v12;
    *((_DWORD *)a1 + 13) = 1;
    goto LABEL_44;
  }
  *((_DWORD *)a1 + 14) = 0;
  v4 = *((_WORD *)a1 + 7);
  switch ( v4 )
  {
    case 16:
      v5 = UpdateDstPartialMBRGB16;
      g_redscale = 7;
      v6 = UpdateDstMBRGB16;
      v7 = UpdateDstBlkRGB16;
LABEL_13:
      *((_QWORD *)a1 + 27) = v7;
      *((_QWORD *)a1 + 25) = v6;
      *((_QWORD *)a1 + 26) = v5;
LABEL_31:
      *((_DWORD *)a1 + 13) = 1;
      return 0;
    case 24:
      v5 = UpdateDstPartialMBRGB24;
      v6 = UpdateDstMBRGB24;
      v7 = UpdateDstBlkRGB24;
      goto LABEL_13;
    case 32:
      v5 = UpdateDstPartialMBRGB32;
      v6 = UpdateDstMBRGB32;
      v7 = UpdateDstBlkRGB32;
      goto LABEL_13;
    case 8:
      v5 = UpdateDstPartialMBRGB8;
      v6 = UpdateDstMBRGB8;
      v7 = UpdateDstBlkRGB8;
      goto LABEL_13;
  }
  return 4294967294LL;
}

```

## disassembly

```asm
0x18001e404  movups  xmm0, xmmword ptr [rdx]
0x18001e407  cmp     dword ptr [rdx+10h], 3
0x18001e40b  movups  xmmword ptr [rcx], xmm0
0x18001e40e  movups  xmm1, xmmword ptr [rdx+10h]
0x18001e412  movups  xmmword ptr [rcx+10h], xmm1
0x18001e416  jnz     short loc_18001E428
0x18001e418  movups  xmm0, xmmword ptr [rdx+20h]
0x18001e41c  movups  xmmword ptr [rcx+20h], xmm0
0x18001e420  mov     eax, [rdx+30h]
0x18001e423  mov     [rcx+30h], eax
0x18001e426  jmp     short loc_18001E432
0x18001e428  movsd   xmm0, qword ptr [rdx+20h]
0x18001e42d  movsd   qword ptr [rcx+20h], xmm0
0x18001e432  mov     eax, [rcx+10h]
0x18001e435  xor     edx, edx
0x18001e437  mov     cs:?g_redscale@@3JA, edx; long g_redscale
0x18001e43d  test    eax, eax
0x18001e43f  jnz     loc_18001E4EB
0x18001e445  mov     [rcx+38h], edx
0x18001e448  movzx   edx, word ptr [rcx+0Eh]
0x18001e44c  cmp     dx, 10h
0x18001e450  jnz     short loc_18001E474
0x18001e452  mov     eax, 7
0x18001e457  lea     r8, ?UpdateDstPartialMBRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e45e  mov     cs:?g_redscale@@3JA, eax; long g_redscale
0x18001e464  lea     rdx, ?UpdateDstMBRGB16@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB16(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e46b  lea     rax, ?UpdateDstBlkRGB16@@YAXPEAEPEBE11JJJ@Z; UpdateDstBlkRGB16(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e472  jmp     short loc_18001E4D1
0x18001e474  cmp     dx, 18h
0x18001e478  jnz     short loc_18001E491
0x18001e47a  lea     r8, ?UpdateDstPartialMBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e481  lea     rdx, ?UpdateDstMBRGB24@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB24(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e488  lea     rax, ?UpdateDstBlkRGB24@@YAXPEAEPEBE11JJJ@Z; UpdateDstBlkRGB24(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e48f  jmp     short loc_18001E4D1
0x18001e491  cmp     dx, 20h ; ' '
0x18001e495  jnz     short loc_18001E4AE
0x18001e497  lea     r8, ?UpdateDstPartialMBRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e49e  lea     rdx, ?UpdateDstMBRGB32@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB32(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e4a5  lea     rax, ?UpdateDstBlkRGB32@@YAXPEAEPEBE11JJJ@Z; UpdateDstBlkRGB32(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e4ac  jmp     short loc_18001E4D1
0x18001e4ae  mov     eax, 8
0x18001e4b3  cmp     dx, ax
0x18001e4b6  jnz     loc_18001E6B6
0x18001e4bc  lea     r8, ?UpdateDstPartialMBRGB8@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBRGB8(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e4c3  lea     rdx, ?UpdateDstMBRGB8@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB8(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e4ca  lea     rax, ?UpdateDstBlkRGB8@@YAXPEAEPEBE11JJJ@Z; UpdateDstBlkRGB8(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e4d1  mov     [rcx+0D8h], rax
0x18001e4d8  mov     [rcx+0C8h], rdx
0x18001e4df  mov     [rcx+0D0h], r8
0x18001e4e6  jmp     loc_18001E5C7
0x18001e4eb  cmp     eax, 3
0x18001e4ee  jnz     loc_18001E5D3
0x18001e4f4  cmp     word ptr [rcx+0Eh], 10h
0x18001e4f9  mov     [rcx+38h], edx
0x18001e4fc  jnz     short loc_18001E56B
0x18001e4fe  cmp     dword ptr [rcx+28h], 7C00h
0x18001e505  jnz     short loc_18001E525
0x18001e507  cmp     dword ptr [rcx+2Ch], 3E0h
0x18001e50e  jnz     loc_18001E6B6
0x18001e514  cmp     dword ptr [rcx+30h], 1Fh
0x18001e518  jnz     loc_18001E6B6
0x18001e51e  mov     eax, 7
0x18001e523  jmp     short loc_18001E54E
0x18001e525  cmp     dword ptr [rcx+28h], 0F800h
0x18001e52c  jnz     loc_18001E6B6
0x18001e532  cmp     dword ptr [rcx+2Ch], 7E0h
0x18001e539  jnz     loc_18001E6B6
0x18001e53f  cmp     dword ptr [rcx+30h], 1Fh
0x18001e543  jnz     loc_18001E6B6
0x18001e549  mov     eax, 8
0x18001e54e  mov     cs:?g_redscale@@3JA, eax; long g_redscale
0x18001e554  lea     rdx, ?UpdateDstMBRGB16@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB16(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e55b  lea     rax, ?UpdateDstBlkRGB16@@YAXPEAEPEBE11JJJ@Z; UpdateDstBlkRGB16(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e562  lea     r8, ?UpdateDstPartialMBRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e569  jmp     short loc_18001E5B2
0x18001e56b  cmp     word ptr [rcx+0Eh], 20h ; ' '
0x18001e570  jnz     loc_18001E6B6
0x18001e576  cmp     dword ptr [rcx+28h], 0FF0000h
0x18001e57d  jnz     loc_18001E6B6
0x18001e583  cmp     dword ptr [rcx+2Ch], 0FF00h
0x18001e58a  jnz     loc_18001E6B6
0x18001e590  cmp     dword ptr [rcx+30h], 0FFh
0x18001e597  jnz     loc_18001E6B6
0x18001e59d  lea     rax, ?UpdateDstBlkRGB32@@YAXPEAEPEBE11JJJ@Z; UpdateDstBlkRGB32(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e5a4  lea     rdx, ?UpdateDstMBRGB32@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB32(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e5ab  lea     r8, ?UpdateDstPartialMBRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e5b2  mov     [rcx+0D0h], r8
0x18001e5b9  mov     [rcx+0C8h], rdx
0x18001e5c0  mov     [rcx+0D8h], rax
0x18001e5c7  mov     dword ptr [rcx+34h], 1
0x18001e5ce  jmp     loc_18001E6B3
0x18001e5d3  cmp     eax, 59565955h
0x18001e5d8  jnz     short loc_18001E610
0x18001e5da  lea     rax, ?UpdateDstMBUYVY@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBUYVY(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e5e1  mov     [rcx+0C8h], rax
0x18001e5e8  lea     rax, ?UpdateDstPartialMBUYVY@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBUYVY(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e5ef  mov     [rcx+0D0h], rax
0x18001e5f6  lea     rax, ?UpdateDstBlkUYVY@@YAXPEAEPEBE11JJJ@Z; UpdateDstBlkUYVY(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e5fd  mov     [rcx+0D8h], rax
0x18001e604  mov     dword ptr [rcx+34h], 1
0x18001e60b  jmp     loc_18001E6AC
0x18001e610  cmp     eax, 55595659h
0x18001e615  jnz     short loc_18001E63C
0x18001e617  lea     rax, ?UpdateDstMBYVYU@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBYVYU(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e61e  mov     [rcx+0C8h], rax
0x18001e625  lea     rax, ?UpdateDstPartialMBYVYU@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBYVYU(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e62c  mov     [rcx+0D0h], rax
0x18001e633  lea     rax, ?UpdateDstBlkYVYU@@YAXPEAEPEBE11JJJ@Z; UpdateDstBlkYVYU(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e63a  jmp     short loc_18001E5FD
0x18001e63c  cmp     eax, 32595559h
0x18001e641  jnz     short loc_18001E668
0x18001e643  lea     rax, ?UpdateDstMBYUY2@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBYUY2(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e64a  mov     [rcx+0C8h], rax
0x18001e651  lea     rax, ?UpdateDstPartialMBYUY2@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBYUY2(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e658  mov     [rcx+0D0h], rax
0x18001e65f  lea     rax, ?UpdateDstBlkYUY2@@YAXPEAEPEBE11JJJ@Z; UpdateDstBlkYUY2(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e666  jmp     short loc_18001E5FD
0x18001e668  cmp     eax, 39555659h
0x18001e66d  jnz     short loc_18001E686
0x18001e66f  lea     rax, ?UpdateDstPartialMBYVU9@@YAXPEAE00PEBE11JJJJJJ@Z; UpdateDstPartialMBYVU9(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long,long,long)
0x18001e676  mov     [rcx+0E8h], rax
0x18001e67d  lea     rax, ?UpdateDstMBYVU9@@YAXPEAE00PEBE11JJJJ@Z; UpdateDstMBYVU9(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e684  jmp     short loc_18001E6A2
0x18001e686  cmp     eax, 32315659h
0x18001e68b  jnz     short loc_18001E6B6
0x18001e68d  lea     rax, ?UpdateDstPartialMBYV12@@YAXPEAE00PEBE11JJJJJJ@Z; UpdateDstPartialMBYV12(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long,long,long)
0x18001e694  mov     [rcx+0E8h], rax
0x18001e69b  lea     rax, ?UpdateDstMBYV12@@YAXPEAE00PEBE11JJJJ@Z; UpdateDstMBYV12(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e6a2  mov     [rcx+34h], edx
0x18001e6a5  mov     [rcx+0E0h], rax
0x18001e6ac  mov     dword ptr [rcx+38h], 1
0x18001e6b3  xor     eax, eax
0x18001e6b5  retn
0x18001e6b6  mov     eax, 0FFFFFFFEh
0x18001e6bb  retn
```
