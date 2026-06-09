# Planar::BD_DecompressBitmap(uchar *,uchar *,uint,uint,uint,uchar,int,ushort,ushort,uchar *,uint,int,uint,uint,uint,uint,ITSGraphicsSurface *,int *)

- ea: `0x1800b48b0`
- end: `0x1800b50e9`
- name: `?BD_DecompressBitmap@Planar@@YAJPEAE0IIIEHGG0IHIIIIPEAVITSGraphicsSurface@@PEAH@Z`
- size: `2105`
- prototype: `__int64 __usercall@<rax>(Planar *__hidden this@<rcx>, unsigned __int8 *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned int, char, unsigned __int8, __int16, unsigned __int16, void *Block, unsigned __int8 *, unsigned int, int, unsigned int, unsigned int, unsigned int, unsigned int, struct ITSGraphicsSurface *, int *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800a6c40`
- `0x1800cfe20`

## callees

- `0x1800018a4`
- `0x1800711c8`
- `0x180071a60`
- `0x1800721d4`
- `0x1800787d4`
- `0x180078820`
- `0x1800a7d10`
- `0x1800adaf4`
- `0x1800aef40`
- `0x1800b038c`
- `0x1800b1c0c`
- `0x1800b39e0`
- `0x1800b48b0`
- `0x1800b5184`
- `0x1800b543c`
- `0x1800c67f8`
- `0x1800c68c8`

## string_xrefs

- `0x1800b4a75`: `onecore\termsrv\rdpplatform\codecs\planar\planardecompression.cpp`
- `0x1800b4bcf`: `onecore\termsrv\rdpplatform\codecs\planar\planardecompression.cpp`
- `0x1800b4cd6`: `onecore\termsrv\rdpplatform\codecs\planar\planardecompression.cpp`
- `0x1800b4d6e`: `onecore\termsrv\rdpplatform\codecs\planar\planardecompression.cpp`
- `0x1800b4e85`: `onecore\termsrv\rdpplatform\codecs\planar\planardecompression.cpp`
- `0x1800b4f20`: `onecore\termsrv\rdpplatform\codecs\planar\planardecompression.cpp`
- `0x1800b4a59`: `BD_DecompressBitmap`
- `0x1800b4bb3`: `BD_DecompressBitmap`
- `0x1800b4cba`: `BD_DecompressBitmap`
- `0x1800b4d52`: `BD_DecompressBitmap`
- `0x1800b4e69`: `BD_DecompressBitmap`
- `0x1800b4f04`: `BD_DecompressBitmap`
- `0x1800b4ceb`: `Bitmap Decompression Failed`
- `0x1800b4d7c`: `Bitmap Decompression Failed`
- `0x1800b4ff3`: `Failed to combine color planes`

## pseudocode

```c
__int64 __fastcall Planar::BD_DecompressBitmap(
        Planar *this,
        unsigned __int8 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int8 a6,
        int a7,
        unsigned __int16 a8,
        unsigned __int16 a9,
        char *Block,
        unsigned __int8 *a11,
        unsigned int a12,
        int a13,
        unsigned int a14,
        unsigned int a15,
        unsigned int a16,
        const char *a17,
        struct ITSGraphicsSurface *a18)
{
  unsigned int v18; // r12d
  Planar *v19; // rbx
  unsigned __int8 *v20; // r14
  unsigned __int8 v21; // r15
  __int64 v22; // rsi
  unsigned int v23; // r13d
  unsigned int v24; // edi
  __int16 v25; // cx
  const unsigned __int16 *v26; // r9
  unsigned int v27; // ebx
  unsigned __int8 v28; // r14
  Planar *v29; // rcx
  unsigned __int8 v30; // dl
  unsigned int v31; // eax
  unsigned int v32; // r8d
  unsigned int v33; // r9d
  unsigned int v34; // ecx
  __int16 *v35; // rdx
  const char *v36; // rax
  unsigned int v37; // r11d
  unsigned __int8 *v38; // rbx
  int v39; // r14d
  int v40; // r10d
  unsigned int v41; // edx
  char *v42; // r14
  char *v43; // rcx
  unsigned int v44; // esi
  int v45; // eax
  int v46; // eax
  unsigned __int8 *v47; // rbx
  unsigned int v48; // esi
  int v49; // eax
  unsigned __int64 v50; // rcx
  int v51; // r8d
  char v52; // r10
  unsigned __int8 *v53; // rcx
  unsigned int v54; // eax
  unsigned int v55; // edi
  unsigned int v56; // edx
  __int128 *v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // r8
  int ActivityIdPrefix; // eax
  unsigned int v61; // edi
  unsigned int v62; // edi
  unsigned int v63; // edi
  unsigned int v64; // edi
  unsigned int v67; // [rsp+28h] [rbp-D9h]
  int v68; // [rsp+30h] [rbp-D1h]
  unsigned __int16 v69; // [rsp+38h] [rbp-C9h]
  const char *v70; // [rsp+58h] [rbp-A9h] BYREF
  int v71[4]; // [rsp+60h] [rbp-A1h] BYREF
  __int128 v72; // [rsp+70h] [rbp-91h]
  int v73[4]; // [rsp+80h] [rbp-81h] BYREF
  __int128 v74; // [rsp+90h] [rbp-71h]
  unsigned __int8 *v75; // [rsp+A0h] [rbp-61h] BYREF
  unsigned int v76; // [rsp+A8h] [rbp-59h]
  unsigned int v77; // [rsp+ACh] [rbp-55h]
  int v78; // [rsp+B0h] [rbp-51h]
  unsigned int v79; // [rsp+B4h] [rbp-4Dh]
  unsigned __int8 v80; // [rsp+B8h] [rbp-49h]
  int v81; // [rsp+B9h] [rbp-48h]
  __int16 v82; // [rsp+BDh] [rbp-44h]
  char v83; // [rsp+BFh] [rbp-42h]
  int v84[4]; // [rsp+C0h] [rbp-41h] BYREF
  __int128 v85; // [rsp+D0h] [rbp-31h]
  __int128 v86; // [rsp+E0h] [rbp-21h] BYREF
  __int128 v87; // [rsp+F0h] [rbp-11h]
  unsigned __int8 *v88; // [rsp+150h] [rbp+4Fh]
  int v89; // [rsp+158h] [rbp+57h]

  v89 = (int)a3;
  v88 = a2;
  v18 = (unsigned int)a4;
  v19 = this;
  v20 = (unsigned __int8 *)this + (unsigned int)a3;
  if ( a5 )
  {
    v21 = a6;
    LODWORD(v22) = (_DWORD)a3;
    v23 = a8;
    v24 = a6;
    v25 = 4 * ((a8 * ((a6 + 3) & 0xFFFFFFFC) + 31) >> 5);
LABEL_14:
    if ( ((v21 - 24) & 0xF7) == 0 && a12 )
    {
      if ( !(unsigned int)CheckReadOneByte((unsigned __int8 *)v19, v20, a3) )
        return (unsigned int)-1626585967;
      v28 = *(_BYTE *)v19;
      v29 = (Planar *)(*(_BYTE *)v19 & 8);
      a15 = *(unsigned __int8 *)v19;
      a7 = (int)v29;
      LOBYTE(a5) = v28 & 0x20;
      v30 = (unsigned __int8)v29;
      LOBYTE(v29) = v21;
      v31 = Planar::BD_PlanarBitmapSize(v29, v30, a8, a9, (v28 & 0x20) == 0, v68);
      v34 = v31;
      if ( !v31 )
      {
        v27 = -1626389339;
        if ( (unsigned int)CallbackContext <= 2 )
          return v27;
        a5 = 1190;
        a17 = "BD_DecompressBitmap";
        v35 = (__int16 *)&byte_1801B601F;
        a18 = (struct ITSGraphicsSurface *)"onecore\\termsrv\\rdpplatform\\codecs\\planar\\planardecompression.cpp";
        v36 = "Overflow in memory allocation calculation";
LABEL_21:
        v70 = v36;
        a7 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v34,
          (_DWORD)v35,
          v32,
          v33,
          (__int64)&v70,
          (__int64)&a7,
          (__int64)&a18,
          (__int64)&a5,
          (__int64)&a17);
        return v27;
      }
      v37 = (unsigned __int16)v33;
      *(_QWORD *)v71 = 0;
      v38 = (unsigned __int8 *)v19 + 1;
      v71[3] = (unsigned __int16)v33;
      *((_QWORD *)&v72 + 1) = 8;
      v71[2] = v23;
      v39 = v28 & 0x10;
      v40 = (unsigned __int16)v33;
      v32 = v23;
      *(_QWORD *)&v72 = v23 | 0x100000000LL;
      a13 = 0;
      *(_OWORD *)v73 = *(_OWORD *)v71;
      a17 = (const char *)v38;
      v74 = v72;
      a14 = (unsigned __int16)v33;
      *(_OWORD *)v84 = *(_OWORD *)v71;
      v85 = v72;
      v86 = *(_OWORD *)v71;
      v87 = v72;
      if ( a7 )
      {
        v33 = ((unsigned int)(unsigned __int16)v33 + 1) >> 1;
        v41 = (v23 + 1) >> 1;
        v73[2] = v41;
        v84[2] = v41;
        LODWORD(v74) = v41;
        LODWORD(v85) = v41;
        v73[3] = (v37 + 1) >> 1;
        v84[3] = v73[3];
      }
      else
      {
        v41 = v23;
        v33 = (unsigned __int16)v33;
      }
      if ( v39 )
      {
        if ( v31 > (unsigned int)a11 )
        {
          v42 = (char *)operator new(v31);
          if ( !v42 )
          {
            v27 = -1626389305;
            if ( (unsigned int)CallbackContext <= 2 )
              return v27;
            a5 = 1224;
            a17 = "BD_DecompressBitmap";
            v35 = word_1801B5FDA;
            a18 = (struct ITSGraphicsSurface *)"onecore\\termsrv\\rdpplatform\\codecs\\planar\\planardecompression.cpp";
            v36 = "Memory Allocation Failed";
            goto LABEL_21;
          }
          v32 = v72;
          v40 = v71[3];
          a13 = 1;
        }
        else
        {
          v42 = Block;
        }
        *(_QWORD *)&v86 = v42;
        if ( (_BYTE)a5 || v21 != 32 )
          v43 = v42;
        else
          v43 = &v42[(unsigned int)(v87 * HIDWORD(v86))];
        *(_QWORD *)v71 = v43;
        *(_QWORD *)v73 = &v43[v40 * v32];
        v44 = v22 - 1;
        *(_QWORD *)v84 = *(_QWORD *)v73 + (unsigned int)(v73[3] * v74);
        if ( !(_BYTE)a5 && v21 == 32 )
        {
          v45 = DecodeBitmapFromRLE(v38, v44);
          v38 = (unsigned __int8 *)&a17[v45];
          v44 -= v45;
        }
        v46 = DecodeBitmapFromRLE(v38, v44);
        v47 = &v38[v46];
        v48 = v44 - v46;
        v49 = DecodeBitmapFromRLE(v47, v48);
        if ( v48 - v49 != (unsigned int)DecodeBitmapFromRLE(&v47[v49], v48 - v49) )
        {
          v27 = -1626471163;
          if ( (unsigned int)CallbackContext > 2 )
          {
            a5 = 1286;
            a17 = "BD_DecompressBitmap";
            a7 = -2147467259;
            a18 = (struct ITSGraphicsSurface *)"onecore\\termsrv\\rdpplatform\\codecs\\planar\\planardecompression.cpp";
            v70 = "Bitmap Decompression Failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v50,
              (unsigned int)byte_1801B5F95,
              v51,
              v33,
              (__int64)&v70,
              (__int64)&a7,
              (__int64)&a18,
              (__int64)&a5,
              (__int64)&a17);
          }
LABEL_68:
          if ( a13 && v42 )
            operator delete(v42);
          return v27;
        }
        v52 = a5;
        v37 = a14;
      }
      else
      {
        if ( v31 > v89 - 1 )
        {
          v27 = -1626471151;
          if ( (unsigned int)CallbackContext <= 2 )
            return v27;
          a5 = 1298;
          a17 = "BD_DecompressBitmap";
          v35 = (__int16 *)qword_1801B5F50;
          a18 = (struct ITSGraphicsSurface *)"onecore\\termsrv\\rdpplatform\\codecs\\planar\\planardecompression.cpp";
          v36 = "Bitmap Decompression Failed";
          goto LABEL_21;
        }
        v52 = a5;
        v42 = 0;
        *(_QWORD *)&v86 = v38;
        if ( (_BYTE)a5 || v21 != 32 )
        {
          v53 = v38;
          *(_QWORD *)v71 = v38;
        }
        else
        {
          v53 = &v38[v37 * v23];
          *(_QWORD *)v71 = v53;
        }
        v51 = v71[3] * v23;
        v50 = (unsigned __int64)&v53[v71[3] * v23];
        *(_QWORD *)v73 = v50;
        *(_QWORD *)v84 = v50 + v33 * v41;
      }
      v81 = 0;
      v82 = 0;
      v83 = 0;
      v54 = v24 >> 3;
      v55 = v24 + 3;
      v79 = v54;
      v75 = v88;
      v80 = v21;
      v77 = v37;
      v76 = v23;
      v56 = (v23 * (v55 & 0xFFFFFFFC) + 31) >> 5;
      v78 = 4 * v56;
      if ( v55 >= 3 || v23 * v55 + 31 < 0x1F || (v50 = a9 * (unsigned __int64)(4 * v56), v50 > 0xFFFFFFFF) )
      {
        if ( 4 * v37 * v56 <= v18 )
        {
          v57 = &v86;
          if ( v52 )
            LODWORD(v57) = 0;
          v27 = BitmapCombinePlanes((int)v57, (int)v71, (int)v73, (int)v84, (struct _RDP_BITMAP *)&v75, 0, a15 & 7, a7);
          if ( (v27 & 0x80000000) != 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            ActivityIdPrefix = RdpX_GetActivityIdPrefix(v58, &WPP_GLOBAL_Control, v59);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19,
              (unsigned int)WPP_4941ae0f7e3f3e14ba8ac0b41363f8b1_Traceguids,
              ActivityIdPrefix,
              (__int64)"Failed to combine color planes",
              v27);
          }
        }
        else
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            a5 = 1378;
            a17 = "BD_DecompressBitmap";
            a7 = -2147467259;
            a18 = (struct ITSGraphicsSurface *)"onecore\\termsrv\\rdpplatform\\codecs\\planar\\planardecompression.cpp";
            v70 = "Not enough destination buffer";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v50,
              (unsigned int)&word_1801B5EC6,
              v51,
              v33,
              (__int64)&v70,
              (__int64)&a7,
              (__int64)&a18,
              (__int64)&a5,
              (__int64)&a17);
          }
          v27 = -2147467259;
        }
      }
      else
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          a5 = 1370;
          a17 = "BD_DecompressBitmap";
          a7 = -2147467259;
          a18 = (struct ITSGraphicsSurface *)"onecore\\termsrv\\rdpplatform\\codecs\\planar\\planardecompression.cpp";
          v70 = "Integer overflow calculating bitmap size";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v50,
            (unsigned int)byte_1801B5F0B,
            v51,
            v33,
            (__int64)&v70,
            (__int64)&a7,
            (__int64)&a18,
            (__int64)&a5,
            (__int64)&a17);
        }
        v27 = -1626389157;
      }
      goto LABEL_68;
    }
    v61 = v24 - 8;
    if ( v61 )
    {
      v62 = v61 - 7;
      if ( !v62 )
      {
        LOWORD(v67) = v25;
        return (unsigned int)Planar::BDDecompressBitmap15(v19, a2, (unsigned __int8 *)(unsigned int)v22, v18, v67, v68);
      }
      v63 = v62 - 1;
      if ( !v63 )
      {
        LOWORD(v67) = v25;
        return (unsigned int)Planar::BDDecompressBitmap16(v19, a2, (unsigned __int8 *)(unsigned int)v22, v18, v67, v68);
      }
      v64 = v63 - 8;
      if ( !v64 )
      {
        LOWORD(v67) = v25;
        return (unsigned int)Planar::BDDecompressBitmap24(v19, a2, (unsigned __int8 *)(unsigned int)v22, v18, v67, v68);
      }
      if ( v64 == 8 )
        return (unsigned int)Planar::BDDecompressBitmap32(v19, a2, (unsigned __int8 *)(unsigned int)v22, v18, v25);
    }
    LOBYTE(v67) = v21;
    return (unsigned int)Planar::BDDecompressBitmap8(v19, a2, (unsigned __int8 *)(unsigned int)v22, v18, v67, v25, v69);
  }
  if ( !(unsigned int)CheckReadNBytes((unsigned __int8 *)this, v20, 8u, a4) )
    return (unsigned int)-1626586002;
  v22 = *((unsigned __int16 *)v19 + 1);
  if ( !(unsigned int)CheckReadNBytes((unsigned __int8 *)v19, v20, v22 + 8, v26) )
    return (unsigned int)-1626585988;
  v21 = a6;
  v23 = a8;
  v24 = a6;
  a3 = (const unsigned __int16 *)*((unsigned __int16 *)v19 + 2);
  if ( (_DWORD)a3 == 4 * ((a8 * ((a6 + 3) & 0xFFFFFFFC) + 31) >> 5) )
  {
    a2 = v88;
    v25 = *((_WORD *)v19 + 2);
    v19 = (Planar *)((char *)v19 + 8);
    goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_4941ae0f7e3f3e14ba8ac0b41363f8b1_Traceguids,
      *((unsigned __int16 *)v19 + 2),
      4 * ((a8 * ((a6 + 3) & 0xFFFFFFFC) + 31) >> 5));
  }
  return (unsigned int)-1626585980;
}

```

## disassembly

```asm
0x1800b48b0  mov     rax, rsp
0x1800b48b3  mov     [rax+8], rbx
0x1800b48b7  mov     [rax+18h], r8d
0x1800b48bb  mov     [rax+10h], rdx
0x1800b48bf  push    rbp
0x1800b48c0  push    rsi
0x1800b48c1  push    rdi
0x1800b48c2  push    r12
0x1800b48c4  push    r13
0x1800b48c6  push    r14
0x1800b48c8  push    r15
0x1800b48ca  lea     rbp, [rax-3Fh]
0x1800b48ce  sub     rsp, 100h
0x1800b48d5  mov     r12d, r9d
0x1800b48d8  mov     rbx, rcx
0x1800b48db  mov     r14d, r8d
0x1800b48de  add     r14, rcx
0x1800b48e1  cmp     [rbp+37h+arg_20], 0
0x1800b48e5  jz      short loc_1800B4911
0x1800b48e7  movzx   r15d, [rbp+37h+arg_28]
0x1800b48ec  mov     esi, r8d
0x1800b48ef  movzx   r13d, [rbp+37h+arg_38]
0x1800b48f4  mov     edi, r15d
0x1800b48f7  lea     ecx, [r15+3]
0x1800b48fb  and     ecx, 0FFFFFFFCh
0x1800b48fe  imul    ecx, r13d
0x1800b4902  add     ecx, 1Fh
0x1800b4905  shr     ecx, 5
0x1800b4908  shl     cx, 2; unsigned __int8 *
0x1800b490c  jmp     loc_1800B49CA
0x1800b4911  mov     r8d, 8; unsigned __int64
0x1800b4917  mov     rdx, r14; unsigned __int8 *
0x1800b491a  call    ?CheckReadNBytes@@YAHPEAE0_KPEBG@Z; CheckReadNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x1800b491f  test    eax, eax
0x1800b4921  jnz     short loc_1800B492D
0x1800b4923  mov     ebx, 9F0C446Eh
0x1800b4928  jmp     loc_1800B50CC
0x1800b492d  movzx   esi, word ptr [rbx+2]
0x1800b4931  mov     rdx, r14; unsigned __int8 *
0x1800b4934  mov     rcx, rbx; unsigned __int8 *
0x1800b4937  lea     r8, [rsi+8]; unsigned __int64
0x1800b493b  call    ?CheckReadNBytes@@YAHPEAE0_KPEBG@Z; CheckReadNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x1800b4940  test    eax, eax
0x1800b4942  jnz     short loc_1800B494E
0x1800b4944  mov     ebx, 9F0C447Ch
0x1800b4949  jmp     loc_1800B50CC
0x1800b494e  movzx   r15d, [rbp+37h+arg_28]
0x1800b4953  movzx   r13d, [rbp+37h+arg_38]
0x1800b4958  mov     edi, r15d
0x1800b495b  movzx   r8d, word ptr [rbx+4]; unsigned __int16 *
0x1800b4960  lea     eax, [r15+3]
0x1800b4964  and     eax, 0FFFFFFFCh
0x1800b4967  imul    eax, r13d
0x1800b496b  add     eax, 1Fh
0x1800b496e  shr     eax, 5
0x1800b4971  shl     eax, 2
0x1800b4974  cmp     r8d, eax
0x1800b4977  jz      short loc_1800B49BE
0x1800b4979  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4980  lea     rdx, WPP_GLOBAL_Control
0x1800b4987  cmp     rcx, rdx
0x1800b498a  jz      short loc_1800B49B4
0x1800b498c  test    byte ptr [rcx+1Ch], 1
0x1800b4990  jz      short loc_1800B49B4
0x1800b4992  cmp     byte ptr [rcx+19h], 1
0x1800b4996  jb      short loc_1800B49B4
0x1800b4998  mov     rcx, [rcx+10h]
0x1800b499c  mov     r9d, r8d
0x1800b499f  lea     r8, WPP_4941ae0f7e3f3e14ba8ac0b41363f8b1_Traceguids
0x1800b49a6  mov     dword ptr [rsp+130h+var_110], eax
0x1800b49aa  mov     edx, 11h
0x1800b49af  call    WPP_SF_Dd
0x1800b49b4  mov     ebx, 9F0C4484h
0x1800b49b9  jmp     loc_1800B50CC
0x1800b49be  mov     rdx, [rbp+37h+arg_8]; unsigned __int8 *
0x1800b49c2  movzx   ecx, r8w
0x1800b49c6  add     rbx, 8
0x1800b49ca  lea     eax, [r15-18h]
0x1800b49ce  test    al, 0F7h
0x1800b49d0  jnz     loc_1800B5045
0x1800b49d6  cmp     [rbp+37h+arg_58], 0
0x1800b49dd  jz      loc_1800B5045
0x1800b49e3  mov     rdx, r14; unsigned __int8 *
0x1800b49e6  mov     rcx, rbx; unsigned __int8 *
0x1800b49e9  call    ?CheckReadOneByte@@YAHPEAE0PEBG@Z; CheckReadOneByte(uchar *,uchar *,ushort const *)
0x1800b49ee  test    eax, eax
0x1800b49f0  jnz     short loc_1800B49FC
0x1800b49f2  mov     ebx, 9F0C4491h
0x1800b49f7  jmp     loc_1800B50CC
0x1800b49fc  movzx   r14d, byte ptr [rbx]
0x1800b4a00  movzx   r9d, [rbp+37h+arg_40]; unsigned __int16
0x1800b4a08  mov     al, r14b
0x1800b4a0b  movzx   r8d, [rbp+37h+arg_38]; int
0x1800b4a10  mov     ecx, r14d
0x1800b4a13  and     ecx, 8
0x1800b4a16  mov     [rbp+37h+arg_70], r14d
0x1800b4a1d  and     al, 20h
0x1800b4a1f  mov     [rbp+37h+arg_30], ecx
0x1800b4a22  mov     byte ptr [rbp+37h+arg_20], al
0x1800b4a25  mov     edx, ecx; unsigned __int8
0x1800b4a27  mov     eax, 0
0x1800b4a2c  mov     cl, r15b; this
0x1800b4a2f  setz    al
0x1800b4a32  mov     dword ptr [rsp+130h+var_110], eax; unsigned __int16
0x1800b4a36  call    ?BD_PlanarBitmapSize@Planar@@YAIEHGGH@Z; Planar::BD_PlanarBitmapSize(uchar,int,ushort,ushort,int)
0x1800b4a3b  mov     ecx, eax; Size
0x1800b4a3d  test    eax, eax
0x1800b4a3f  jnz     loc_1800B4AD4
0x1800b4a45  mov     eax, cs:CallbackContext
0x1800b4a4b  mov     ebx, 9F0F44A5h
0x1800b4a50  cmp     eax, 2
0x1800b4a53  jbe     loc_1800B50CC
0x1800b4a59  lea     rax, aBdDecompressbi; "BD_DecompressBitmap"
0x1800b4a60  mov     [rbp+37h+arg_20], 4A6h
0x1800b4a67  mov     [rbp+37h+arg_80], rax
0x1800b4a6e  lea     rdx, byte_1801B601F
0x1800b4a75  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\codecs\\"...
0x1800b4a7c  mov     [rbp+37h+arg_88], rax
0x1800b4a83  lea     rax, aOverflowInMemo; "Overflow in memory allocation calculati"...
0x1800b4a8a  mov     qword ptr [rsp+130h+var_E0], rax
0x1800b4a8f  lea     rax, [rbp+37h+arg_80]
0x1800b4a96  mov     [rsp+40h], rax
0x1800b4a9b  lea     rax, [rbp+37h+arg_20]
0x1800b4a9f  mov     qword ptr [rsp+130h+var_F8], rax
0x1800b4aa4  lea     rax, [rbp+37h+arg_88]
0x1800b4aab  mov     qword ptr [rsp+130h+var_100], rax
0x1800b4ab0  lea     rax, [rbp+37h+arg_30]
0x1800b4ab4  mov     qword ptr [rsp+130h+var_108], rax
0x1800b4ab9  lea     rax, [rsp+130h+var_E0]
0x1800b4abe  mov     [rsp+130h+var_110], rax
0x1800b4ac3  mov     [rbp+37h+arg_30], 80004005h
0x1800b4aca  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800b4acf  jmp     loc_1800B50CC
0x1800b4ad4  xorps   xmm0, xmm0
0x1800b4ad7  movzx   r11d, r9w
0x1800b4adb  movups  xmmword ptr [rsp+130h+var_E0+8], xmm0
0x1800b4ae0  inc     rbx
0x1800b4ae3  mov     dword ptr [rsp+130h+var_D0+4], r11d
0x1800b4ae8  movups  [rsp+130h+var_D0+8], xmm0
0x1800b4aed  mov     dword ptr [rsp+130h+var_D0], r13d
0x1800b4af2  and     r14d, 10h
0x1800b4af6  cmp     [rbp+37h+arg_30], 0
0x1800b4afa  mov     r10d, r11d
0x1800b4afd  movups  xmm1, xmmword ptr [rsp+130h+var_E0+8]
0x1800b4b02  mov     dword ptr [rsp+130h+var_D0+0Ch], 1
0x1800b4b0a  mov     r8d, r13d
0x1800b4b0d  mov     dword ptr [rsp+130h+var_D0+8], r13d
0x1800b4b12  mov     byte ptr [rsp+130h+var_C0], 8
0x1800b4b17  movups  xmm0, [rsp+130h+var_D0+8]
0x1800b4b1c  mov     [rbp+37h+arg_60], 0
0x1800b4b26  movups  xmmword ptr [rsp+130h+var_C0+8], xmm1
0x1800b4b2b  mov     [rbp+37h+arg_80], rbx
0x1800b4b32  movups  [rbp+37h+var_A8], xmm0
0x1800b4b36  mov     [rbp+37h+arg_68], r11d
0x1800b4b3d  movups  xmmword ptr [rbp+37h+var_78], xmm1
0x1800b4b41  movups  [rbp+37h+var_68], xmm0
0x1800b4b45  movups  [rbp+37h+var_58], xmm1
0x1800b4b49  movups  [rbp+37h+var_48], xmm0
0x1800b4b4d  jz      short loc_1800B4B72
0x1800b4b4f  lea     r9d, [r11+1]
0x1800b4b53  shr     r9d, 1
0x1800b4b56  lea     edx, [r13+1]
0x1800b4b5a  shr     edx, 1
0x1800b4b5c  mov     [rbp+37h+var_B0], edx
0x1800b4b5f  mov     [rbp+37h+var_78+8], edx
0x1800b4b62  mov     dword ptr [rbp+37h+var_A8], edx
0x1800b4b65  mov     dword ptr [rbp+37h+var_68], edx
0x1800b4b68  mov     [rbp+37h+var_AC], r9d
0x1800b4b6c  mov     [rbp+37h+var_78+0Ch], r9d
0x1800b4b70  jmp     short loc_1800B4B78
0x1800b4b72  mov     edx, r13d
0x1800b4b75  mov     r9d, r11d
0x1800b4b78  test    r14d, r14d
0x1800b4b7b  jz      loc_1800B4D35
0x1800b4b81  cmp     ecx, dword ptr [rbp+37h+arg_50]
0x1800b4b87  ja      short loc_1800B4B92
0x1800b4b89  mov     r14, [rbp+37h+Block]
0x1800b4b90  jmp     short loc_1800B4BFD
0x1800b4b92  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b4b97  mov     r14, rax
0x1800b4b9a  test    rax, rax
0x1800b4b9d  jnz     short loc_1800B4BE9
0x1800b4b9f  mov     eax, cs:CallbackContext
0x1800b4ba5  mov     ebx, 9F0F44C7h
0x1800b4baa  cmp     eax, 2
0x1800b4bad  jbe     loc_1800B50CC
0x1800b4bb3  lea     rax, aBdDecompressbi; "BD_DecompressBitmap"
0x1800b4bba  mov     [rbp+37h+arg_20], 4C8h
0x1800b4bc1  mov     [rbp+37h+arg_80], rax
0x1800b4bc8  lea     rdx, word_1801B5FDA
0x1800b4bcf  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\codecs\\"...
0x1800b4bd6  mov     [rbp+37h+arg_88], rax
0x1800b4bdd  lea     rax, aMemoryAllocati; "Memory Allocation Failed"
0x1800b4be4  jmp     loc_1800B4A8A
0x1800b4be9  mov     r8d, dword ptr [rsp+130h+var_D0+8]
0x1800b4bee  mov     r10d, dword ptr [rsp+130h+var_D0+4]
0x1800b4bf3  mov     [rbp+37h+arg_60], 1
0x1800b4bfd  mov     r9b, byte ptr [rbp+37h+arg_20]
0x1800b4c01  mov     qword ptr [rbp+37h+var_58], r14
0x1800b4c05  test    r9b, r9b
0x1800b4c08  jnz     short loc_1800B4C1C
0x1800b4c0a  cmp     r15b, 20h ; ' '
0x1800b4c0e  jnz     short loc_1800B4C1C
0x1800b4c10  mov     ecx, dword ptr [rbp+37h+var_58+0Ch]
0x1800b4c13  imul    ecx, dword ptr [rbp+37h+var_48]
0x1800b4c17  add     rcx, r14
0x1800b4c1a  jmp     short loc_1800B4C1F
0x1800b4c1c  mov     rcx, r14
0x1800b4c1f  imul    r8d, r10d
0x1800b4c23  mov     qword ptr [rsp+130h+var_E0+8], rcx
0x1800b4c28  mov     edx, r8d
0x1800b4c2b  add     rdx, rcx
0x1800b4c2e  mov     ecx, dword ptr [rbp+37h+var_A8]
0x1800b4c31  imul    ecx, [rbp+37h+var_AC]
0x1800b4c35  mov     qword ptr [rsp+130h+var_C0+8], rdx
0x1800b4c3a  add     rcx, rdx
0x1800b4c3d  dec     esi
0x1800b4c3f  mov     qword ptr [rbp+37h+var_78], rcx
0x1800b4c43  test    r9b, r9b
0x1800b4c46  jnz     short loc_1800B4C67
0x1800b4c48  cmp     r15b, 20h ; ' '
0x1800b4c4c  jnz     short loc_1800B4C67
0x1800b4c4e  lea     r8, [rbp+37h+var_58]
0x1800b4c52  mov     edx, esi; unsigned int
0x1800b4c54  mov     rcx, rbx; unsigned __int8 *
0x1800b4c57  call    DecodeBitmapFromRLE
0x1800b4c5c  mov     ebx, eax
0x1800b4c5e  add     rbx, [rbp+37h+arg_80]
0x1800b4c65  sub     esi, eax
0x1800b4c67  lea     r8, [rsp+130h+var_E0+8]
0x1800b4c6c  mov     edx, esi; unsigned int
0x1800b4c6e  mov     rcx, rbx; unsigned __int8 *
0x1800b4c71  call    DecodeBitmapFromRLE
0x1800b4c76  mov     ecx, eax
0x1800b4c78  lea     r8, [rsp+130h+var_C0+8]
0x1800b4c7d  add     rbx, rcx
0x1800b4c80  sub     esi, eax
0x1800b4c82  mov     rcx, rbx; unsigned __int8 *
0x1800b4c85  mov     edx, esi; unsigned int
0x1800b4c87  call    DecodeBitmapFromRLE
0x1800b4c8c  sub     esi, eax
0x1800b4c8e  mov     ecx, eax
0x1800b4c90  add     rcx, rbx; unsigned __int8 *
0x1800b4c93  lea     r8, [rbp+37h+var_78]
0x1800b4c97  mov     edx, esi; unsigned int
0x1800b4c99  call    DecodeBitmapFromRLE
0x1800b4c9e  cmp     esi, eax
0x1800b4ca0  jz      loc_1800B4DD7
0x1800b4ca6  mov     eax, cs:CallbackContext
0x1800b4cac  mov     ebx, 9F0E0505h
0x1800b4cb1  cmp     eax, 2
0x1800b4cb4  jbe     loc_1800B5022
0x1800b4cba  lea     rax, aBdDecompressbi; "BD_DecompressBitmap"
0x1800b4cc1  mov     [rbp+37h+arg_20], 506h
0x1800b4cc8  mov     [rbp+37h+arg_80], rax
0x1800b4ccf  lea     rdx, byte_1801B5F95
0x1800b4cd6  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\codecs\\"...
0x1800b4cdd  mov     [rbp+37h+arg_30], 80004005h
0x1800b4ce4  mov     [rbp+37h+arg_88], rax
0x1800b4ceb  lea     rax, aBitmapDecompre; "Bitmap Decompression Failed"
0x1800b4cf2  mov     qword ptr [rsp+130h+var_E0], rax
0x1800b4cf7  lea     rax, [rbp+37h+arg_80]
0x1800b4cfe  mov     [rsp+40h], rax
0x1800b4d03  lea     rax, [rbp+37h+arg_20]
0x1800b4d07  mov     qword ptr [rsp+130h+var_F8], rax
0x1800b4d0c  lea     rax, [rbp+37h+arg_88]
0x1800b4d13  mov     qword ptr [rsp+130h+var_100], rax
0x1800b4d18  lea     rax, [rbp+37h+arg_30]
0x1800b4d1c  mov     qword ptr [rsp+130h+var_108], rax
0x1800b4d21  lea     rax, [rsp+130h+var_E0]
0x1800b4d26  mov     [rsp+130h+var_110], rax
0x1800b4d2b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800b4d30  jmp     loc_1800B5022
0x1800b4d35  mov     eax, [rbp+37h+arg_10]
0x1800b4d38  dec     eax
0x1800b4d3a  cmp     ecx, eax
0x1800b4d3c  jbe     short loc_1800B4D88
0x1800b4d3e  mov     eax, cs:CallbackContext
0x1800b4d44  mov     ebx, 9F0E0511h
0x1800b4d49  cmp     eax, 2
0x1800b4d4c  jbe     loc_1800B50CC
0x1800b4d52  lea     rax, aBdDecompressbi; "BD_DecompressBitmap"
0x1800b4d59  mov     [rbp+37h+arg_20], 512h
0x1800b4d60  mov     [rbp+37h+arg_80], rax
0x1800b4d67  lea     rdx, qword_1801B5F50
0x1800b4d6e  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\codecs\\"...
0x1800b4d75  mov     [rbp+37h+arg_88], rax
0x1800b4d7c  lea     rax, aBitmapDecompre; "Bitmap Decompression Failed"
0x1800b4d83  jmp     loc_1800B4A8A
0x1800b4d88  mov     r10b, byte ptr [rbp+37h+arg_20]
0x1800b4d8c  xor     r14d, r14d
0x1800b4d8f  mov     qword ptr [rbp+37h+var_58], rbx
0x1800b4d93  test    r10b, r10b
0x1800b4d96  jnz     short loc_1800B4DAF
0x1800b4d98  cmp     r15b, 20h ; ' '
0x1800b4d9c  jnz     short loc_1800B4DAF
0x1800b4d9e  mov     ecx, r13d
0x1800b4da1  imul    ecx, r11d
0x1800b4da5  add     rcx, rbx
0x1800b4da8  mov     qword ptr [rsp+130h+var_E0+8], rcx
  ... truncated ...
```
