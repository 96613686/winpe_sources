# XC_DecompressInternal(uchar *,ulong,ulong,uchar * *,ulong *,void *,ulong)

- ea: `0x1800a331c`
- end: `0x1800a3973`
- name: `?XC_DecompressInternal@@YAKPEAEKKPEAPEAEPEAKPEAXK@Z`
- size: `1623`
- prototype: `unsigned int __fastcall(unsigned __int8 *, unsigned int, unsigned int, unsigned __int8 **, unsigned int *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800a31e0`

## callees

- `0x180004970`
- `0x180005970`
- `0x180005b20`
- `0x180005cd0`
- `0x180005e90`
- `0x1800a331c`

## string_xrefs

- `0x1800a3554`: `XC_DecompressInternal`
- `0x1800a35f7`: `XC_DecompressInternal`
- `0x1800a3643`: `XC_DecompressInternal`
- `0x1800a3686`: `XC_DecompressInternal`
- `0x1800a371b`: `XC_DecompressInternal`
- `0x1800a37aa`: `XC_DecompressInternal`
- `0x1800a386c`: `XC_DecompressInternal`
- `0x1800a38e9`: `XC_DecompressInternal`
- `0x1800a356a`: `onecore\termsrv\rdpplatform\common\compress\codecs\xcdecompress.cpp`
- `0x1800a360d`: `onecore\termsrv\rdpplatform\common\compress\codecs\xcdecompress.cpp`
- `0x1800a3659`: `onecore\termsrv\rdpplatform\common\compress\codecs\xcdecompress.cpp`
- `0x1800a369b`: `onecore\termsrv\rdpplatform\common\compress\codecs\xcdecompress.cpp`
- `0x1800a3731`: `onecore\termsrv\rdpplatform\common\compress\codecs\xcdecompress.cpp`
- `0x1800a37c0`: `onecore\termsrv\rdpplatform\common\compress\codecs\xcdecompress.cpp`
- `0x1800a3877`: `onecore\termsrv\rdpplatform\common\compress\codecs\xcdecompress.cpp`
- `0x1800a38fe`: `onecore\termsrv\rdpplatform\common\compress\codecs\xcdecompress.cpp`
- `0x1800a3882`: `TS: Invalid decompress stream - USHORT: pInBuf (%p), pEnd(%p)`
- `0x1800a3743`: `TS: Invalid decompress stream - ULONG: pInBuf (%p), pEnd(%p)`
- `0x1800a36aa`: `TS: Invalid decompress stream: (matchOffsetInCurrent (0x%x) < offsetInCurrentDecompressedPacket (0x%x))`
- `0x1800a366b`: `TS: Invalid decompress stream: (matchBackPtr (0x%x) > XC_HISTORY_BUF_SIZE)`
- `0x1800a3579`: `TS: Invalid decompress stream: (pWritePointer(%p) + literalCopyLen(%d)) < pWritePointerMax(%p)`
- `0x1800a361c`: `TS: copy match fail: pWritePointer (%p), matchLen (%d), matchstart(%p) < pWritePointerMax (%p)`
- `0x1800a3910`: `TS: Invalid decompress flags (0x%x)`
- `0x1800a37cf`: `TS: Invalid decompress stream: pWritePointer(%p), literalCopyLen(%d), pLiteralCopyStart(%p) < pWritePointerMax(%p)`

## pseudocode

```c
__int64 __fastcall XC_DecompressInternal(
        unsigned __int8 *a1,
        int a2,
        unsigned __int16 *a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        const char *a6,
        unsigned int a7)
{
  const char *v7; // r15
  unsigned __int8 **v8; // r14
  unsigned __int8 *v9; // r11
  unsigned __int8 *v10; // r10
  _DWORD *v11; // rdi
  unsigned __int16 *v12; // rcx
  const char *v13; // rdx
  __int64 v14; // rsi
  const char *v15; // rsi
  unsigned __int8 *v16; // rbx
  unsigned int v17; // ebx
  unsigned __int16 v18; // r12
  __int64 v19; // r14
  __int64 v20; // r12
  _BYTE *v21; // r10
  const char *v22; // r14
  unsigned __int64 v23; // rcx
  int v24; // r13d
  __int64 v25; // r12
  const char *v26; // r15
  __int64 v27; // r9
  const char *v28; // r10
  int i; // r8d
  __int64 result; // rax
  __int16 *v31; // rdx
  const char *v32; // rax
  __int16 *v33; // rdx
  const char *v34; // rax
  char *v35; // rdx
  const char *v36; // rax
  const char *v37; // [rsp+70h] [rbp-31h]
  _BYTE *v38; // [rsp+78h] [rbp-29h] BYREF
  const char *v39; // [rsp+80h] [rbp-21h] BYREF
  const char *v40; // [rsp+88h] [rbp-19h] BYREF
  int v41[20]; // [rsp+90h] [rbp-11h] BYREF
  const char *v42; // [rsp+F0h] [rbp+4Fh] BYREF
  int v43; // [rsp+F8h] [rbp+57h] BYREF
  int v44; // [rsp+100h] [rbp+5Fh] BYREF
  unsigned __int8 **v45; // [rsp+108h] [rbp+67h]

  v45 = a4;
  v7 = a6;
  v8 = a4;
  v9 = a1;
  v10 = &a1[a2];
  v39 = (const char *)v10;
  v11 = a6 + 4;
  if ( (_DWORD)a3 )
    *v11 = 0;
  LODWORD(v12) = a7;
  v13 = &v7[*v11 + 16];
  v14 = *((unsigned int *)v7 + 2) + 16LL;
  v42 = v13;
  v15 = &v7[v14];
  v16 = (unsigned __int8 *)v13;
  if ( (a7 & 2) == 0 )
  {
    if ( (a7 & 1) == 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        a6 = "XC_DecompressInternal";
        v33 = &word_1801B3A76;
        v43 = 439;
        v42 = "onecore\\termsrv\\rdpplatform\\common\\compress\\codecs\\xcdecompress.cpp";
        v34 = "TS: Invalid decompress flags (0x%x)";
LABEL_59:
        *(_QWORD *)v41 = v34;
        v44 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)v12,
          (_DWORD)v33,
          (_DWORD)a3,
          (_DWORD)a4,
          (__int64)v41,
          (__int64)&v44,
          (__int64)&v42,
          (__int64)&v43,
          (__int64)&a6,
          (__int64)&a7);
      }
      return 0;
    }
    a3 = (unsigned __int16 *)(v9 + 2);
    if ( v9 + 2 > v10 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v42 = (const char *)v9;
        v35 = (char *)word_1801B3D92;
        a7 = 320;
LABEL_55:
        *(_QWORD *)v41 = "XC_DecompressInternal";
        v40 = "onecore\\termsrv\\rdpplatform\\common\\compress\\codecs\\xcdecompress.cpp";
        v36 = "TS: Invalid decompress stream - USHORT: pInBuf (%p), pEnd(%p)";
LABEL_56:
        v39 = v36;
        v43 = -2147467259;
        a6 = (const char *)v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (_DWORD)v12,
          (_DWORD)v35,
          (_DWORD)a3,
          (_DWORD)a4,
          (__int64)&v39,
          (__int64)&v43,
          (__int64)&v40,
          (__int64)&a7,
          (__int64)v41,
          (__int64)&v42,
          (__int64)&a6);
        return 0;
      }
      return 0;
    }
    v17 = 0;
    *(_QWORD *)v41 = *(unsigned __int16 *)v9;
    a7 = 0;
    v9 = (unsigned __int8 *)&a3[4 * *(_QWORD *)v41];
    if ( v41[0] )
    {
      while ( 1 )
      {
        v12 = a3 + 1;
        if ( a3 + 1 > (unsigned __int16 *)v10 )
          break;
        v18 = *a3;
        a4 = (unsigned __int8 **)(a3 + 2);
        v40 = (const char *)*a3;
        if ( a3 + 2 > (unsigned __int16 *)v10 )
        {
          if ( (unsigned int)CallbackContext <= 2 )
            return 0;
          v42 = (const char *)(a3 + 1);
          v35 = (char *)qword_1801B3CE8;
          a7 = 351;
          goto LABEL_55;
        }
        LODWORD(v12) = *v12;
        a3 += 4;
        if ( (char *)a4 + 4 > (char *)v10 )
        {
          if ( (unsigned int)CallbackContext <= 2 )
            return 0;
          v42 = (const char *)a4;
          *(_QWORD *)v41 = "XC_DecompressInternal";
          v35 = byte_1801B3C93;
          a7 = 362;
          v40 = "onecore\\termsrv\\rdpplatform\\common\\compress\\codecs\\xcdecompress.cpp";
          v36 = "TS: Invalid decompress stream - ULONG: pInBuf (%p), pEnd(%p)";
          goto LABEL_56;
        }
        if ( (unsigned int)v12 < v17 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            v43 = v17;
            v42 = "XC_DecompressInternal";
            LOWORD(a7) = (_WORD)v12;
            *(_QWORD *)v41 = "onecore\\termsrv\\rdpplatform\\common\\compress\\codecs\\xcdecompress.cpp";
            v40 = "TS: Invalid decompress stream: (matchOffsetInCurrent (0x%x) < offsetInCurrentDecompressedPacket (0x%x))";
            v44 = 375;
            LODWORD(a6) = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
              (_DWORD)v12,
              (unsigned int)byte_1801B3C15,
              (_DWORD)a3,
              (_DWORD)a4,
              (__int64)&v40,
              (__int64)&a6,
              (__int64)v41,
              (__int64)&v44,
              (__int64)&v42,
              (__int64)&a7,
              (__int64)&v43);
          }
          return 0;
        }
        v19 = *(unsigned int *)a4;
        if ( (unsigned int)v19 > 0x1E8480 )
        {
          if ( (unsigned int)CallbackContext <= 2 )
            return 0;
          a7 = *(_DWORD *)a4;
          a6 = "XC_DecompressInternal";
          v33 = word_1801B3BC2;
          v43 = 383;
          v42 = "onecore\\termsrv\\rdpplatform\\common\\compress\\codecs\\xcdecompress.cpp";
          v34 = "TS: Invalid decompress stream: (matchBackPtr (0x%x) > XC_HISTORY_BUF_SIZE)";
          goto LABEL_59;
        }
        LOWORD(v12) = (_WORD)v12 - v17;
        if ( (_WORD)v12 )
        {
          if ( &v13[(unsigned __int16)v12] >= v15
            || v9 >= v10
            || (LODWORD(a4) = (unsigned __int16)v12 + (_DWORD)v9, &v9[(unsigned __int16)v12] > v10) )
          {
            if ( (unsigned int)CallbackContext > 2 )
            {
              v42 = v13;
              *(_QWORD *)v41 = "XC_DecompressInternal";
              a6 = v15;
              v40 = "onecore\\termsrv\\rdpplatform\\common\\compress\\codecs\\xcdecompress.cpp";
              v39 = "TS: Invalid decompress stream: (pWritePointer(%p) + literalCopyLen(%d)) < pWritePointerMax(%p)";
              LOWORD(a7) = (_WORD)v12;
              v43 = 409;
              v44 = -2147467259;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>>(
                (_DWORD)v12,
                (unsigned int)byte_1801B3B49,
                (_DWORD)a3,
                (_DWORD)a4,
                (__int64)&v39,
                (__int64)&v44,
                (__int64)&v40,
                (__int64)&v43,
                (__int64)v41,
                (__int64)&v42,
                (__int64)&a7,
                (__int64)&a6);
            }
            return 0;
          }
          v37 = v13;
          v13 += (unsigned __int16)v12;
          v20 = 0;
          v38 = v9;
          v9 += (unsigned __int16)v12;
          LODWORD(a4) = (unsigned __int16)v12;
          v21 = v38;
          do
          {
            v37[v20] = v21[v20];
            v20 = (unsigned int)(v20 + 1);
            LODWORD(a4) = (_DWORD)a4 - 1;
          }
          while ( (_DWORD)a4 );
          v10 = (unsigned __int8 *)v39;
          v7 = a6;
          v18 = (unsigned __int16)v40;
          v17 += (unsigned __int16)v12;
        }
        v22 = &v7[v19 + 16];
        v23 = (unsigned __int64)&v13[v18];
        if ( v23 >= (unsigned __int64)v15 || &v22[v18] >= v15 )
        {
          if ( (unsigned int)CallbackContext <= 2 )
            return 0;
          *(_QWORD *)v41 = v13;
          v40 = "XC_DecompressInternal";
          v31 = (__int16 *)&dword_1801B3ACC;
          v42 = v22;
          v39 = "onecore\\termsrv\\rdpplatform\\common\\compress\\codecs\\xcdecompress.cpp";
          v32 = "TS: copy match fail: pWritePointer (%p), matchLen (%d), matchstart(%p) < pWritePointerMax (%p)";
          LOWORD(a7) = v18;
          v43 = 430;
          goto LABEL_52;
        }
        v24 = v18;
        v25 = 0;
        v40 = v13;
        v13 = (const char *)v23;
        LODWORD(a4) = v24;
        if ( v24 )
        {
          v26 = v40;
          do
          {
            v26[v25] = v22[v25];
            v25 = (unsigned int)(v25 + 1);
            LODWORD(a4) = (_DWORD)a4 - 1;
          }
          while ( (_DWORD)a4 );
          v7 = a6;
        }
        v17 += v24;
        if ( (int)++a7 >= v41[0] )
        {
          v8 = v45;
          goto LABEL_29;
        }
      }
      if ( (unsigned int)CallbackContext <= 2 )
        return 0;
      v42 = (const char *)a3;
      v35 = byte_1801B3D3D;
      a7 = 340;
      goto LABEL_55;
    }
LABEL_29:
    v16 = (unsigned __int8 *)v42;
  }
  if ( v9 >= v10 )
  {
LABEL_35:
    result = 1;
    *v11 = (_DWORD)v13 - (_DWORD)v7 - 16;
    *a5 = (_DWORD)v13 - (_DWORD)v16;
    *v8 = v16;
    return result;
  }
  v23 = (unsigned __int16)((_WORD)v10 - (_WORD)v9);
  LODWORD(a3) = v23 + (_DWORD)v13;
  if ( &v13[v23] < v15 && &v9[v23] <= v10 )
  {
    v27 = 0;
    v28 = v13;
    LODWORD(v13) = v23 + (_DWORD)v13;
    for ( i = v23; i; --i )
    {
      v28[v27] = v9[v27];
      v27 = (unsigned int)(v27 + 1);
    }
    goto LABEL_35;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    *(_QWORD *)v41 = v13;
    v40 = "XC_DecompressInternal";
    v31 = word_1801B39EA;
    v42 = (const char *)v9;
    v39 = "onecore\\termsrv\\rdpplatform\\common\\compress\\codecs\\xcdecompress.cpp";
    v32 = "TS: Invalid decompress stream: pWritePointer(%p), literalCopyLen(%d), pLiteralCopyStart(%p) < pWritePointerMax(%p)";
    LOWORD(a7) = (_WORD)v10 - (_WORD)v9;
    v43 = 457;
LABEL_52:
    v38 = v32;
    a6 = v15;
    v44 = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v23,
      (_DWORD)v31,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)&v38,
      (__int64)&v44,
      (__int64)&v39,
      (__int64)&v43,
      (__int64)&v40,
      (__int64)v41,
      (__int64)&a7,
      (__int64)&v42,
      (__int64)&a6);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a331c  mov     [rsp-8+arg_18], r9
0x1800a3321  push    rbp
0x1800a3322  push    rbx
0x1800a3323  push    rsi
0x1800a3324  push    rdi
0x1800a3325  push    r12
0x1800a3327  push    r13
0x1800a3329  push    r14
0x1800a332b  push    r15
0x1800a332d  lea     rbp, [rsp-7]
0x1800a3332  sub     rsp, 0A8h
0x1800a3339  mov     r15, [rbp+3Fh+arg_28]
0x1800a333d  mov     r14, r9
0x1800a3340  mov     r10d, edx
0x1800a3343  mov     r11, rcx
0x1800a3346  add     r10, rcx
0x1800a3349  mov     [rbp+3Fh+var_60], r10
0x1800a334d  lea     rdi, [r15+4]
0x1800a3351  test    r8d, r8d
0x1800a3354  jz      short loc_1800A335C
0x1800a3356  mov     dword ptr [rdi], 0
0x1800a335c  mov     edx, [rdi]
0x1800a335e  mov     esi, [r15+8]
0x1800a3362  add     rdx, 10h
0x1800a3366  mov     ecx, [rbp+3Fh+arg_30]
0x1800a3369  add     rdx, r15
0x1800a336c  add     rsi, 10h
0x1800a3370  mov     [rbp+3Fh+arg_0], rdx
0x1800a3374  add     rsi, r15
0x1800a3377  mov     rbx, rdx
0x1800a337a  test    cl, 2
0x1800a337d  jnz     loc_1800A34DB
0x1800a3383  test    cl, 1
0x1800a3386  jz      loc_1800A38DE
0x1800a338c  lea     r8, [r11+2]
0x1800a3390  cmp     r8, r10
0x1800a3393  ja      loc_1800A384B
0x1800a3399  movzx   eax, word ptr [r11]
0x1800a339d  xor     ebx, ebx
0x1800a339f  mov     qword ptr [rbp+3Fh+var_50], rax
0x1800a33a3  mov     [rbp+3Fh+arg_30], ebx
0x1800a33a6  lea     r11, [r8+rax*8]
0x1800a33aa  test    eax, eax
0x1800a33ac  jz      loc_1800A34D7
0x1800a33b2  lea     rcx, [r8+2]
0x1800a33b6  cmp     rcx, r10
0x1800a33b9  ja      loc_1800A3775
0x1800a33bf  movzx   r12d, word ptr [r8]
0x1800a33c3  lea     r9, [rcx+2]
0x1800a33c7  mov     [rbp+3Fh+var_58], r12
0x1800a33cb  cmp     r9, r10
0x1800a33ce  ja      loc_1800A374F
0x1800a33d4  movzx   ecx, word ptr [rcx]
0x1800a33d7  lea     r8, [r9+4]
0x1800a33db  cmp     r8, r10
0x1800a33de  ja      loc_1800A370C
0x1800a33e4  cmp     ecx, ebx
0x1800a33e6  jb      loc_1800A3677
0x1800a33ec  mov     r14d, [r9]
0x1800a33ef  cmp     r14d, 1E8480h
0x1800a33f6  ja      loc_1800A3634
0x1800a33fc  sub     cx, bx
0x1800a33ff  jz      short loc_1800A346C
0x1800a3401  movzx   eax, cx
0x1800a3404  lea     r12, [rax+rdx]
0x1800a3408  cmp     r12, rsi
0x1800a340b  jnb     loc_1800A3545
0x1800a3411  cmp     r11, r10
0x1800a3414  jnb     loc_1800A3545
0x1800a341a  lea     r9, [rax+r11]
0x1800a341e  cmp     r9, r10
0x1800a3421  ja      loc_1800A3545
0x1800a3427  movzx   r13d, cx
0x1800a342b  mov     [rbp+3Fh+var_70], rdx
0x1800a342f  mov     rdx, r12
0x1800a3432  xor     r12d, r12d
0x1800a3435  mov     [rbp+3Fh+var_68], r11
0x1800a3439  mov     r11, r9
0x1800a343c  mov     r9d, r13d
0x1800a343f  test    r13d, r13d
0x1800a3442  jz      short loc_1800A3465
0x1800a3444  mov     r15, [rbp+3Fh+var_70]
0x1800a3448  mov     r10, [rbp+3Fh+var_68]
0x1800a344c  mov     al, [r10+r12]
0x1800a3450  mov     [r15+r12], al
0x1800a3454  inc     r12d
0x1800a3457  add     r9d, 0FFFFFFFFh
0x1800a345b  jnz     short loc_1800A344C
0x1800a345d  mov     r10, [rbp+3Fh+var_60]
0x1800a3461  mov     r15, [rbp+3Fh+arg_28]
0x1800a3465  mov     r12, [rbp+3Fh+var_58]
0x1800a3469  add     ebx, r13d
0x1800a346c  add     r14, 10h
0x1800a3470  movzx   eax, r12w
0x1800a3474  add     r14, r15
0x1800a3477  lea     rcx, [rax+rdx]
0x1800a347b  cmp     rcx, rsi
0x1800a347e  jnb     loc_1800A35E8
0x1800a3484  add     rax, r14
0x1800a3487  cmp     rax, rsi
0x1800a348a  jnb     loc_1800A35E8
0x1800a3490  movzx   r13d, r12w
0x1800a3494  xor     r12d, r12d
0x1800a3497  mov     [rbp+3Fh+var_58], rdx
0x1800a349b  mov     rdx, rcx
0x1800a349e  mov     r9d, r13d
0x1800a34a1  test    r13d, r13d
0x1800a34a4  jz      short loc_1800A34BF
0x1800a34a6  mov     r15, [rbp+3Fh+var_58]
0x1800a34aa  mov     al, [r12+r14]
0x1800a34ae  mov     [r15+r12], al
0x1800a34b2  inc     r12d
0x1800a34b5  add     r9d, 0FFFFFFFFh
0x1800a34b9  jnz     short loc_1800A34AA
0x1800a34bb  mov     r15, [rbp+3Fh+arg_28]
0x1800a34bf  mov     eax, [rbp+3Fh+arg_30]
0x1800a34c2  add     ebx, r13d
0x1800a34c5  inc     eax
0x1800a34c7  mov     [rbp+3Fh+arg_30], eax
0x1800a34ca  cmp     eax, [rbp+3Fh+var_50]
0x1800a34cd  jl      loc_1800A33B2
0x1800a34d3  mov     r14, [rbp+3Fh+arg_18]
0x1800a34d7  mov     rbx, [rbp+3Fh+arg_0]
0x1800a34db  cmp     r11, r10
0x1800a34de  jnb     short loc_1800A3526
0x1800a34e0  movzx   eax, r10w
0x1800a34e4  sub     ax, r11w
0x1800a34e8  movzx   ecx, ax
0x1800a34eb  lea     r8, [rcx+rdx]
0x1800a34ef  cmp     r8, rsi
0x1800a34f2  jnb     loc_1800A379B
0x1800a34f8  lea     rax, [rcx+r11]
0x1800a34fc  cmp     rax, r10
0x1800a34ff  ja      loc_1800A379B
0x1800a3505  xor     r9d, r9d
0x1800a3508  mov     r10, rdx
0x1800a350b  mov     rdx, r8
0x1800a350e  mov     r8d, ecx
0x1800a3511  test    ecx, ecx
0x1800a3513  jz      short loc_1800A3526
0x1800a3515  mov     al, [r9+r11]
0x1800a3519  mov     [r9+r10], al
0x1800a351d  inc     r9d
0x1800a3520  add     r8d, 0FFFFFFFFh
0x1800a3524  jnz     short loc_1800A3515
0x1800a3526  mov     ecx, edx
0x1800a3528  mov     eax, 1
0x1800a352d  sub     ecx, r15d
0x1800a3530  sub     ecx, 10h
0x1800a3533  mov     [rdi], ecx
0x1800a3535  sub     edx, ebx
0x1800a3537  mov     rcx, [rbp+3Fh+arg_20]
0x1800a353b  mov     [rcx], edx
0x1800a353d  mov     [r14], rbx
0x1800a3540  jmp     loc_1800A395F
0x1800a3545  mov     eax, cs:CallbackContext
0x1800a354b  cmp     eax, 2
0x1800a354e  jbe     loc_1800A395D
0x1800a3554  lea     rax, aXcDecompressin; "XC_DecompressInternal"
0x1800a355b  mov     [rbp+3Fh+arg_0], rdx
0x1800a355f  mov     qword ptr [rbp+3Fh+var_50], rax
0x1800a3563  lea     rdx, byte_1801B3B49
0x1800a356a  lea     rax, aOnecoreTermsrv_21; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800a3571  mov     [rbp+3Fh+arg_28], rsi
0x1800a3575  mov     [rbp+3Fh+var_58], rax
0x1800a3579  lea     rax, aTsInvalidDecom_5; "TS: Invalid decompress stream: (pWriteP"...
0x1800a3580  mov     [rbp+3Fh+var_60], rax
0x1800a3584  lea     rax, [rbp+3Fh+arg_28]
0x1800a3588  mov     [rsp+0E0h+var_88], rax
0x1800a358d  lea     rax, [rbp+3Fh+arg_30]
0x1800a3591  mov     [rsp+0E0h+var_90], rax
0x1800a3596  lea     rax, [rbp+3Fh+arg_0]
0x1800a359a  mov     [rsp+0E0h+var_98], rax
0x1800a359f  lea     rax, [rbp+3Fh+var_50]
0x1800a35a3  mov     [rsp+0E0h+var_A0], rax
0x1800a35a8  lea     rax, [rbp+3Fh+arg_8]
0x1800a35ac  mov     [rsp+0E0h+var_A8], rax
0x1800a35b1  lea     rax, [rbp+3Fh+var_58]
0x1800a35b5  mov     [rsp+0E0h+var_B0], rax
0x1800a35ba  lea     rax, [rbp+3Fh+arg_10]
0x1800a35be  mov     [rsp+0E0h+var_B8], rax
0x1800a35c3  lea     rax, [rbp+3Fh+var_60]
0x1800a35c7  mov     [rsp+0E0h+var_C0], rax
0x1800a35cc  mov     word ptr [rbp+3Fh+arg_30], cx
0x1800a35d0  mov     [rbp+3Fh+arg_8], 199h
0x1800a35d7  mov     [rbp+3Fh+arg_10], 80004005h
0x1800a35de  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$01@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$01@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &)
0x1800a35e3  jmp     loc_1800A395D
0x1800a35e8  mov     eax, cs:CallbackContext
0x1800a35ee  cmp     eax, 2
0x1800a35f1  jbe     loc_1800A395D
0x1800a35f7  lea     rax, aXcDecompressin; "XC_DecompressInternal"
0x1800a35fe  mov     qword ptr [rbp+3Fh+var_50], rdx
0x1800a3602  mov     [rbp+3Fh+var_58], rax
0x1800a3606  lea     rdx, dword_1801B3ACC
0x1800a360d  lea     rax, aOnecoreTermsrv_21; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800a3614  mov     [rbp+3Fh+arg_0], r14
0x1800a3618  mov     [rbp+3Fh+var_60], rax
0x1800a361c  lea     rax, aTsCopyMatchFai; "TS: copy match fail: pWritePointer (%p)"...
0x1800a3623  mov     word ptr [rbp+3Fh+arg_30], r12w
0x1800a3628  mov     [rbp+3Fh+arg_8], 1AEh
0x1800a362f  jmp     loc_1800A37E1
0x1800a3634  mov     eax, cs:CallbackContext
0x1800a363a  cmp     eax, 2
0x1800a363d  jbe     loc_1800A395D
0x1800a3643  lea     rax, aXcDecompressin; "XC_DecompressInternal"
0x1800a364a  mov     [rbp+3Fh+arg_30], r14d
0x1800a364e  mov     [rbp+3Fh+arg_28], rax
0x1800a3652  lea     rdx, word_1801B3BC2
0x1800a3659  lea     rax, aOnecoreTermsrv_21; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800a3660  mov     [rbp+3Fh+arg_8], 17Fh
0x1800a3667  mov     [rbp+3Fh+arg_0], rax
0x1800a366b  lea     rax, aTsInvalidDecom_2; "TS: Invalid decompress stream: (matchBa"...
0x1800a3672  jmp     loc_1800A3917
0x1800a3677  mov     eax, cs:CallbackContext
0x1800a367d  cmp     eax, 2
0x1800a3680  jbe     loc_1800A395D
0x1800a3686  lea     rax, aXcDecompressin; "XC_DecompressInternal"
0x1800a368d  mov     [rbp+3Fh+arg_8], ebx
0x1800a3690  mov     [rbp+3Fh+arg_0], rax
0x1800a3694  lea     rdx, byte_1801B3C15
0x1800a369b  lea     rax, aOnecoreTermsrv_21; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800a36a2  mov     word ptr [rbp+3Fh+arg_30], cx
0x1800a36a6  mov     qword ptr [rbp+3Fh+var_50], rax
0x1800a36aa  lea     rax, aTsInvalidDecom_3; "TS: Invalid decompress stream: (matchOf"...
0x1800a36b1  mov     [rbp+3Fh+var_58], rax
0x1800a36b5  lea     rax, [rbp+3Fh+arg_8]
0x1800a36b9  mov     [rsp+0E0h+var_90], rax
0x1800a36be  lea     rax, [rbp+3Fh+arg_30]
0x1800a36c2  mov     [rsp+0E0h+var_98], rax
0x1800a36c7  lea     rax, [rbp+3Fh+arg_0]
0x1800a36cb  mov     [rsp+0E0h+var_A0], rax
0x1800a36d0  lea     rax, [rbp+3Fh+arg_10]
0x1800a36d4  mov     [rsp+0E0h+var_A8], rax
0x1800a36d9  lea     rax, [rbp+3Fh+var_50]
0x1800a36dd  mov     [rsp+0E0h+var_B0], rax
0x1800a36e2  lea     rax, [rbp+3Fh+arg_28]
0x1800a36e6  mov     [rsp+0E0h+var_B8], rax
0x1800a36eb  lea     rax, [rbp+3Fh+var_58]
0x1800a36ef  mov     [rsp+0E0h+var_C0], rax
0x1800a36f4  mov     [rbp+3Fh+arg_10], 177h
0x1800a36fb  mov     dword ptr [rbp+3Fh+arg_28], 80004005h
0x1800a3702  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800a3707  jmp     loc_1800A395D
0x1800a370c  mov     eax, cs:CallbackContext
0x1800a3712  cmp     eax, 2
0x1800a3715  jbe     loc_1800A395D
0x1800a371b  lea     rax, aXcDecompressin; "XC_DecompressInternal"
0x1800a3722  mov     [rbp+3Fh+arg_0], r9
0x1800a3726  mov     qword ptr [rbp+3Fh+var_50], rax
0x1800a372a  lea     rdx, byte_1801B3C93
0x1800a3731  lea     rax, aOnecoreTermsrv_21; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800a3738  mov     [rbp+3Fh+arg_30], 16Ah
0x1800a373f  mov     [rbp+3Fh+var_58], rax
0x1800a3743  lea     rax, aTsInvalidDecom_4; "TS: Invalid decompress stream - ULONG: "...
0x1800a374a  jmp     loc_1800A3889
0x1800a374f  mov     eax, cs:CallbackContext
0x1800a3755  cmp     eax, 2
0x1800a3758  jbe     loc_1800A395D
0x1800a375e  mov     [rbp+3Fh+arg_0], rcx
0x1800a3762  lea     rdx, qword_1801B3CE8
0x1800a3769  mov     [rbp+3Fh+arg_30], 15Fh
0x1800a3770  jmp     loc_1800A386C
0x1800a3775  mov     eax, cs:CallbackContext
0x1800a377b  cmp     eax, 2
0x1800a377e  jbe     loc_1800A395D
0x1800a3784  mov     [rbp+3Fh+arg_0], r8
0x1800a3788  lea     rdx, byte_1801B3D3D
0x1800a378f  mov     [rbp+3Fh+arg_30], 154h
0x1800a3796  jmp     loc_1800A386C
0x1800a379b  mov     eax, cs:CallbackContext
0x1800a37a1  cmp     eax, 2
0x1800a37a4  jbe     loc_1800A395D
0x1800a37aa  lea     rax, aXcDecompressin; "XC_DecompressInternal"
0x1800a37b1  mov     qword ptr [rbp+3Fh+var_50], rdx
0x1800a37b5  mov     [rbp+3Fh+var_58], rax
0x1800a37b9  lea     rdx, word_1801B39EA
0x1800a37c0  lea     rax, aOnecoreTermsrv_21; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800a37c7  mov     [rbp+3Fh+arg_0], r11
0x1800a37cb  mov     [rbp+3Fh+var_60], rax
0x1800a37cf  lea     rax, aTsInvalidDecom_0; "TS: Invalid decompress stream: pWritePo"...
0x1800a37d6  mov     word ptr [rbp+3Fh+arg_30], cx
0x1800a37da  mov     [rbp+3Fh+arg_8], 1C9h
0x1800a37e1  mov     [rbp+3Fh+var_68], rax
0x1800a37e5  lea     rax, [rbp+3Fh+arg_28]
0x1800a37e9  mov     [rsp+0E0h+var_80], rax
0x1800a37ee  lea     rax, [rbp+3Fh+arg_0]
0x1800a37f2  mov     [rsp+0E0h+var_88], rax
0x1800a37f7  lea     rax, [rbp+3Fh+arg_30]
0x1800a37fb  mov     [rsp+0E0h+var_90], rax
0x1800a3800  lea     rax, [rbp+3Fh+var_50]
0x1800a3804  mov     [rsp+0E0h+var_98], rax
0x1800a3809  lea     rax, [rbp+3Fh+var_58]
0x1800a380d  mov     [rsp+0E0h+var_A0], rax
0x1800a3812  lea     rax, [rbp+3Fh+arg_8]
0x1800a3816  mov     [rsp+0E0h+var_A8], rax
0x1800a381b  lea     rax, [rbp+3Fh+var_60]
0x1800a381f  mov     [rsp+0E0h+var_B0], rax
0x1800a3824  lea     rax, [rbp+3Fh+arg_10]
0x1800a3828  mov     [rsp+0E0h+var_B8], rax
  ... truncated ...
```
