# g_ConfigureDstBMPProperty(CDeColorConvParams *,tagBITMAPINFOHEADER *)

- ea: `0x18001e344`
- end: `0x18001e5fc`
- name: `?g_ConfigureDstBMPProperty@@YAJPEAVCDeColorConvParams@@PEAUtagBITMAPINFOHEADER@@@Z`
- size: `696`
- prototype: `__int64 __fastcall(struct CDeColorConvParams *, struct tagBITMAPINFOHEADER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001e208`

## callees

- `0x18001e344`

## pseudocode

```c
__int64 __fastcall g_ConfigureDstBMPProperty(struct CDeColorConvParams *a1, struct tagBITMAPINFOHEADER *a2)
{
  bool v2; // zf
  int v3; // eax
  __int16 v4; // dx
  void (*v5)(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int); // r8
  void (__fastcall *v6)(unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int); // rdx
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
      v6 = (void (__fastcall *)(unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int))UpdateDstMBRGB16;
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
      v6 = (void (__fastcall *)(unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int))UpdateDstMBRGB24;
      v7 = UpdateDstBlkRGB24;
      goto LABEL_13;
    case 32:
      v5 = UpdateDstPartialMBRGB32;
      v6 = (void (__fastcall *)(unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int))UpdateDstMBRGB32;
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
0x18001e344  movups  xmm0, xmmword ptr [rdx]
0x18001e347  cmp     dword ptr [rdx+10h], 3
0x18001e34b  movups  xmmword ptr [rcx], xmm0
0x18001e34e  movups  xmm1, xmmword ptr [rdx+10h]
0x18001e352  movups  xmmword ptr [rcx+10h], xmm1
0x18001e356  jnz     short loc_18001E368
0x18001e358  movups  xmm0, xmmword ptr [rdx+20h]
0x18001e35c  movups  xmmword ptr [rcx+20h], xmm0
0x18001e360  mov     eax, [rdx+30h]
0x18001e363  mov     [rcx+30h], eax
0x18001e366  jmp     short loc_18001E372
0x18001e368  movsd   xmm0, qword ptr [rdx+20h]
0x18001e36d  movsd   qword ptr [rcx+20h], xmm0
0x18001e372  mov     eax, [rcx+10h]
0x18001e375  xor     edx, edx
0x18001e377  mov     cs:?g_redscale@@3JA, edx; long g_redscale
0x18001e37d  test    eax, eax
0x18001e37f  jnz     loc_18001E42B
0x18001e385  mov     [rcx+38h], edx
0x18001e388  movzx   edx, word ptr [rcx+0Eh]
0x18001e38c  cmp     dx, 10h
0x18001e390  jnz     short loc_18001E3B4
0x18001e392  mov     eax, 7
0x18001e397  lea     r8, ?UpdateDstPartialMBRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e39e  mov     cs:?g_redscale@@3JA, eax; long g_redscale
0x18001e3a4  lea     rdx, ?UpdateDstMBRGB16@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB16(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e3ab  lea     rax, ?UpdateDstBlkRGB16@@YAXPEAEPEBE11JJJ@Z; UpdateDstBlkRGB16(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e3b2  jmp     short loc_18001E411
0x18001e3b4  cmp     dx, 18h
0x18001e3b8  jnz     short loc_18001E3D1
0x18001e3ba  lea     r8, ?UpdateDstPartialMBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e3c1  lea     rdx, ?UpdateDstMBRGB24@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB24(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e3c8  lea     rax, ?UpdateDstBlkRGB24@@YAXPEAEPEBE11JJJ@Z; UpdateDstBlkRGB24(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e3cf  jmp     short loc_18001E411
0x18001e3d1  cmp     dx, 20h ; ' '
0x18001e3d5  jnz     short loc_18001E3EE
0x18001e3d7  lea     r8, ?UpdateDstPartialMBRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e3de  lea     rdx, ?UpdateDstMBRGB32@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB32(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e3e5  lea     rax, ?UpdateDstBlkRGB32@@YAXPEAEPEBE11JJJ@Z; UpdateDstBlkRGB32(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e3ec  jmp     short loc_18001E411
0x18001e3ee  mov     eax, 8
0x18001e3f3  cmp     dx, ax
0x18001e3f6  jnz     loc_18001E5F6
0x18001e3fc  lea     r8, ?UpdateDstPartialMBRGB8@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBRGB8(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e403  lea     rdx, ?UpdateDstMBRGB8@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB8(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e40a  lea     rax, ?UpdateDstBlkRGB8@@YAXPEAEPEBE11JJJ@Z; UpdateDstBlkRGB8(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e411  mov     [rcx+0D8h], rax
0x18001e418  mov     [rcx+0C8h], rdx
0x18001e41f  mov     [rcx+0D0h], r8
0x18001e426  jmp     loc_18001E507
0x18001e42b  cmp     eax, 3
0x18001e42e  jnz     loc_18001E513
0x18001e434  cmp     word ptr [rcx+0Eh], 10h
0x18001e439  mov     [rcx+38h], edx
0x18001e43c  jnz     short loc_18001E4AB
0x18001e43e  cmp     dword ptr [rcx+28h], 7C00h
0x18001e445  jnz     short loc_18001E465
0x18001e447  cmp     dword ptr [rcx+2Ch], 3E0h
0x18001e44e  jnz     loc_18001E5F6
0x18001e454  cmp     dword ptr [rcx+30h], 1Fh
0x18001e458  jnz     loc_18001E5F6
0x18001e45e  mov     eax, 7
0x18001e463  jmp     short loc_18001E48E
0x18001e465  cmp     dword ptr [rcx+28h], 0F800h
0x18001e46c  jnz     loc_18001E5F6
0x18001e472  cmp     dword ptr [rcx+2Ch], 7E0h
0x18001e479  jnz     loc_18001E5F6
0x18001e47f  cmp     dword ptr [rcx+30h], 1Fh
0x18001e483  jnz     loc_18001E5F6
0x18001e489  mov     eax, 8
0x18001e48e  mov     cs:?g_redscale@@3JA, eax; long g_redscale
0x18001e494  lea     rdx, ?UpdateDstMBRGB16@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB16(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e49b  lea     rax, ?UpdateDstBlkRGB16@@YAXPEAEPEBE11JJJ@Z; UpdateDstBlkRGB16(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e4a2  lea     r8, ?UpdateDstPartialMBRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e4a9  jmp     short loc_18001E4F2
0x18001e4ab  cmp     word ptr [rcx+0Eh], 20h ; ' '
0x18001e4b0  jnz     loc_18001E5F6
0x18001e4b6  cmp     dword ptr [rcx+28h], 0FF0000h
0x18001e4bd  jnz     loc_18001E5F6
0x18001e4c3  cmp     dword ptr [rcx+2Ch], 0FF00h
0x18001e4ca  jnz     loc_18001E5F6
0x18001e4d0  cmp     dword ptr [rcx+30h], 0FFh
0x18001e4d7  jnz     loc_18001E5F6
0x18001e4dd  lea     rax, ?UpdateDstBlkRGB32@@YAXPEAEPEBE11JJJ@Z; UpdateDstBlkRGB32(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e4e4  lea     rdx, ?UpdateDstMBRGB32@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB32(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e4eb  lea     r8, ?UpdateDstPartialMBRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e4f2  mov     [rcx+0D0h], r8
0x18001e4f9  mov     [rcx+0C8h], rdx
0x18001e500  mov     [rcx+0D8h], rax
0x18001e507  mov     dword ptr [rcx+34h], 1
0x18001e50e  jmp     loc_18001E5F3
0x18001e513  cmp     eax, 59565955h
0x18001e518  jnz     short loc_18001E550
0x18001e51a  lea     rax, ?UpdateDstMBUYVY@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBUYVY(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e521  mov     [rcx+0C8h], rax
0x18001e528  lea     rax, ?UpdateDstPartialMBUYVY@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBUYVY(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e52f  mov     [rcx+0D0h], rax
0x18001e536  lea     rax, ?UpdateDstBlkUYVY@@YAXPEAEPEBE11JJJ@Z; UpdateDstBlkUYVY(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e53d  mov     [rcx+0D8h], rax
0x18001e544  mov     dword ptr [rcx+34h], 1
0x18001e54b  jmp     loc_18001E5EC
0x18001e550  cmp     eax, 55595659h
0x18001e555  jnz     short loc_18001E57C
0x18001e557  lea     rax, ?UpdateDstMBYVYU@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBYVYU(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e55e  mov     [rcx+0C8h], rax
0x18001e565  lea     rax, ?UpdateDstPartialMBYVYU@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBYVYU(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e56c  mov     [rcx+0D0h], rax
0x18001e573  lea     rax, ?UpdateDstBlkYVYU@@YAXPEAEPEBE11JJJ@Z; UpdateDstBlkYVYU(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e57a  jmp     short loc_18001E53D
0x18001e57c  cmp     eax, 32595559h
0x18001e581  jnz     short loc_18001E5A8
0x18001e583  lea     rax, ?UpdateDstMBYUY2@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBYUY2(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e58a  mov     [rcx+0C8h], rax
0x18001e591  lea     rax, ?UpdateDstPartialMBYUY2@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z; UpdateDstPartialMBYUY2(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e598  mov     [rcx+0D0h], rax
0x18001e59f  lea     rax, ?UpdateDstBlkYUY2@@YAXPEAEPEBE11JJJ@Z; UpdateDstBlkYUY2(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001e5a6  jmp     short loc_18001E53D
0x18001e5a8  cmp     eax, 39555659h
0x18001e5ad  jnz     short loc_18001E5C6
0x18001e5af  lea     rax, ?UpdateDstPartialMBYVU9@@YAXPEAE00PEBE11JJJJJJ@Z; UpdateDstPartialMBYVU9(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long,long,long)
0x18001e5b6  mov     [rcx+0E8h], rax
0x18001e5bd  lea     rax, ?UpdateDstMBYVU9@@YAXPEAE00PEBE11JJJJ@Z; UpdateDstMBYVU9(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e5c4  jmp     short loc_18001E5E2
0x18001e5c6  cmp     eax, 32315659h
0x18001e5cb  jnz     short loc_18001E5F6
0x18001e5cd  lea     rax, ?UpdateDstPartialMBYV12@@YAXPEAE00PEBE11JJJJJJ@Z; UpdateDstPartialMBYV12(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long,long,long)
0x18001e5d4  mov     [rcx+0E8h], rax
0x18001e5db  lea     rax, ?UpdateDstMBYV12@@YAXPEAE00PEBE11JJJJ@Z; UpdateDstMBYV12(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)
0x18001e5e2  mov     [rcx+34h], edx
0x18001e5e5  mov     [rcx+0E0h], rax
0x18001e5ec  mov     dword ptr [rcx+38h], 1
0x18001e5f3  xor     eax, eax
0x18001e5f5  retn
0x18001e5f6  mov     eax, 0FFFFFFFEh
0x18001e5fb  retn
```
