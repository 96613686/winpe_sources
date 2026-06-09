# PixEventDecoder::ReadEventWithFormatParameters(unsigned __int64,unsigned __int64 const *,unsigned __int64 const *,ushort *,char *,uint,unsigned __int64 *,uint *)

- ea: `0x18017a18c`
- end: `0x18017a5c9`
- name: `?ReadEventWithFormatParameters@PixEventDecoder@@YA?AUEventData@1@_KPEB_K1PEAGPEADIPEA_KPEAI@Z`
- size: `1085`
- prototype: `struct PixEventDecoder::EventData __high(unsigned __int64, const unsigned __int64 *, const unsigned __int64 *, unsigned __int16 *, char *, unsigned int, unsigned __int64 *, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180023308`

## callees

- `0x180014368`
- `0x180064bac`
- `0x1800651a8`
- `0x180074a78`
- `0x1800bb480`
- `0x1800bb92c`
- `0x1800bc094`
- `0x1800bd8d0`
- `0x1800bd938`
- `0x180179f58`
- `0x18017a070`
- `0x18017a18c`
- `0x18017a5d0`
- `0x18017a5ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__mbstowcs_s_l` at `0x18017a37f`
- `api-ms-win-crt-private-l1-1-0!_o__mbstowcs_s_l` at `0x18017a4ba`
- `api-ms-win-crt-private-l1-1-0!_o__mbstowcs_s_l` at `0x18017a37f`
- `api-ms-win-crt-private-l1-1-0!_o__mbstowcs_s_l` at `0x18017a4ba`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18017a3b7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18017a3b7`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x18017a211`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x18017a211`

## pseudocode

```c
__int64 __fastcall PixEventDecoder::ReadEventWithFormatParameters(
        __int64 a1,
        unsigned __int64 a2,
        unsigned __int64 *a3,
        unsigned __int64 a4,
        unsigned __int16 *Source,
        char *String)
{
  unsigned __int8 *v10; // r15
  unsigned __int8 v11; // dl
  __int64 v12; // rsi
  unsigned __int64 v13; // rax
  int v14; // ecx
  __int64 v15; // rax
  unsigned int *v16; // rax
  unsigned int v17; // ecx
  __int64 v18; // r8
  int v19; // edx
  const char *v20; // r15
  unsigned __int64 *v21; // r9
  unsigned __int64 v22; // rcx
  size_t v23; // rdx
  _locale_t v24; // rbx
  size_t v25; // rax
  int v26; // eax
  size_t v27; // rdx
  const wchar_t *v28; // rcx
  int v29; // eax
  unsigned __int8 v31; // [rsp+A0h] [rbp-80h] BYREF
  unsigned __int8 v32[7]; // [rsp+A1h] [rbp-7Fh] BYREF
  __int64 v33; // [rsp+A8h] [rbp-78h] BYREF
  int v34; // [rsp+B0h] [rbp-70h] BYREF
  unsigned __int64 v35; // [rsp+B8h] [rbp-68h] BYREF
  char v36[32]; // [rsp+C0h] [rbp-60h] BYREF
  __int64 v37; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v38; // [rsp+E8h] [rbp-38h]
  __int64 v39; // [rsp+F0h] [rbp-30h]
  __int64 v40; // [rsp+F8h] [rbp-28h]
  __int64 v41; // [rsp+100h] [rbp-20h]
  __int64 v42; // [rsp+108h] [rbp-18h]
  __int64 v43; // [rsp+110h] [rbp-10h]
  __int64 v44; // [rsp+118h] [rbp-8h]
  __int64 v45; // [rsp+120h] [rbp+0h]
  __int64 v46; // [rsp+128h] [rbp+8h]
  __int64 v47; // [rsp+130h] [rbp+10h]
  __int64 v48; // [rsp+138h] [rbp+18h]
  __int64 v49; // [rsp+140h] [rbp+20h]
  __int64 v50; // [rsp+148h] [rbp+28h]
  __int64 v51; // [rsp+150h] [rbp+30h]
  __int64 v52; // [rsp+158h] [rbp+38h]

  if ( dword_18033B7B0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 8LL) )
  {
    Init_thread_header(&dword_18033B7B0);
    if ( dword_18033B7B0 == -1 )
    {
      qword_18033B7B8 = _create_locale(0, ".UTF8");
      atexit(PixEventDecoder::ReadEventWithFormatParameters_::_2_::_dynamic_atexit_destructor_for__utf8Locale__);
      Init_thread_footer(&dword_18033B7B0);
    }
  }
  v10 = 0;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1024;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 40) = 0;
  if ( (unsigned __int64)a3 < a4 )
  {
    LODWORD(v33) = 1024;
    v34 = 1024;
    v32[0] = 0;
    v31 = 0;
    PIXDecodeEventInfo(a2, &v35, (enum PixOp *)&v33, v32, &v31, (enum PixOp *)&v34);
    v11 = v31;
    v12 = v32[0];
    if ( (v31 & 0xF0) == 0xF0 )
    {
      v13 = *a3;
      v14 = 8;
      ++a3;
      *(_DWORD *)(a1 + 40) = 8;
    }
    else
    {
      v14 = 0;
      if ( !v32[0] )
        goto LABEL_11;
      v13 = (unsigned __int64)v31 >> 4;
    }
    *(_QWORD *)(a1 + 16) = v13;
    if ( (_BYTE)v12 )
      v10 = &v31;
LABEL_11:
    if ( (v11 & 1) != 0 )
    {
      v15 = *a3++;
      *(_QWORD *)(a1 + 24) = v15;
      *(_DWORD *)(a1 + 40) = v14 + 8;
    }
    memset_0(&v37, 0, 0x80u);
    v16 = (unsigned int *)PixEventDecoder::ReadString(v36, a3, a4, v10);
    v17 = v16[1];
    v18 = *v16;
    LOBYTE(v19) = *((_BYTE *)v16 + 8);
    v20 = (const char *)*((_QWORD *)v16 + 2);
    *(_DWORD *)(a1 + 40) += v17;
    *(_DWORD *)(a1 + 36) = v17;
    v21 = &a3[(unsigned __int64)v17 >> 3];
    v22 = ((unsigned __int64)*(unsigned int *)(a1 + 40) >> 3) + 1;
    if ( (unsigned __int8)(v12 - 1) <= 0x7Du )
      a4 = (unsigned __int64)&v21[v12 - v22];
    if ( v34 == 1024 && v22 == v12 )
    {
      if ( (_BYTE)v19 )
      {
        v33 = 0;
        if ( (unsigned int)_o__mbstowcs_s_l(&v33, Source, 0x4000, v20, v18, qword_18033B7B8) )
        {
          StringCchPrintfW(Source, 0x4000u, off_180324BA8);
          *(_DWORD *)(a1 + 32) = dword_180324BB0;
        }
      }
      else
      {
        _o_wcscpy_s(Source, 0x4000, v20);
      }
      return a1;
    }
    if ( (_BYTE)v19 )
    {
      *(_DWORD *)(a1 + 40) += PixEventDecoder::PopulateFormatArguments<char const>(
                                (unsigned int)&v37,
                                v19,
                                (_DWORD)v20,
                                (_DWORD)v21,
                                a4);
      if ( (int)StringCchPrintfA(
                  String,
                  0x4000u,
                  v20,
                  v37,
                  v38,
                  v39,
                  v40,
                  v41,
                  v42,
                  v43,
                  v44,
                  v45,
                  v46,
                  v47,
                  v48,
                  v49,
                  v50,
                  v51,
                  v52) < 0 )
        return a1;
      v24 = qword_18033B7B8;
      v33 = 0;
      v25 = strnlen_s(String, v23);
      v26 = _o__mbstowcs_s_l(&v33, Source, 0x4000, String, v25, v24);
      v28 = Source;
      if ( v26 )
      {
        StringCchPrintfW(Source, 0x4000u, off_180324BA8);
        v29 = dword_180324BB0;
LABEL_28:
        *(_DWORD *)(a1 + 32) = v29;
        return a1;
      }
    }
    else
    {
      *(_DWORD *)(a1 + 40) += PixEventDecoder::PopulateFormatArguments<unsigned short const>(
                                (unsigned int)&v37,
                                v19,
                                (_DWORD)v20,
                                (_DWORD)v21,
                                a4);
      if ( StringCchPrintfW(
             Source,
             0x4000u,
             (const unsigned __int16 *)v20,
             v37,
             v38,
             v39,
             v40,
             v41,
             v42,
             v43,
             v44,
             v45,
             v46,
             v47,
             v48,
             v49,
             v50,
             v51,
             v52) < 0 )
        return a1;
      v28 = Source;
    }
    v29 = wcsnlen_s(v28, v27);
    goto LABEL_28;
  }
  return a1;
}

```

## disassembly

```asm
0x18017a18c  mov     [rsp-8+arg_8], rbx
0x18017a191  push    rbp
0x18017a192  push    rsi
0x18017a193  push    rdi
0x18017a194  push    r12
0x18017a196  push    r13
0x18017a198  push    r14
0x18017a19a  push    r15
0x18017a19c  lea     rbp, [rsp-50h]
0x18017a1a1  sub     rsp, 170h
0x18017a1a8  mov     rax, cs:__security_cookie
0x18017a1af  xor     rax, rsp
0x18017a1b2  mov     [rbp+80h+var_40], rax
0x18017a1b6  mov     rax, gs:58h
0x18017a1bf  mov     rdi, rcx
0x18017a1c2  mov     ecx, cs:_tls_index
0x18017a1c8  mov     rsi, rdx
0x18017a1cb  mov     r14, [rbp+80h+Source]
0x18017a1d2  mov     r12, r9
0x18017a1d5  mov     r13, [rbp+80h+String]
0x18017a1dc  mov     rbx, r8
0x18017a1df  mov     edx, 8
0x18017a1e4  mov     rax, [rax+rcx*8]
0x18017a1e8  mov     ecx, [rdx+rax]
0x18017a1eb  cmp     cs:dword_18033B7B0, ecx
0x18017a1f1  jle     short loc_18017A236
0x18017a1f3  lea     rcx, dword_18033B7B0
0x18017a1fa  call    _Init_thread_header
0x18017a1ff  cmp     cs:dword_18033B7B0, 0FFFFFFFFh
0x18017a206  jnz     short loc_18017A236
0x18017a208  lea     rdx, Locale; ".UTF8"
0x18017a20f  xor     ecx, ecx; Category
0x18017a211  call    cs:__imp__create_locale
0x18017a217  lea     rcx, _PixEventDecoder__ReadEventWithFormatParameters____2____dynamic_atexit_destructor_for__utf8Locale__; void (__cdecl *)()
0x18017a21e  mov     cs:qword_18033B7B8, rax
0x18017a225  call    atexit
0x18017a22a  lea     rcx, dword_18033B7B0
0x18017a231  call    _Init_thread_footer
0x18017a236  xor     r15d, r15d
0x18017a239  mov     eax, 400h
0x18017a23e  mov     [rdi], r15
0x18017a241  mov     [rdi+8], eax
0x18017a244  mov     [rdi+10h], r15
0x18017a248  mov     [rdi+18h], r15
0x18017a24c  mov     [rdi+20h], r15
0x18017a250  mov     [rdi+28h], r15d
0x18017a254  cmp     rbx, r12
0x18017a257  jnb     loc_18017A59F
0x18017a25d  mov     dword ptr [rbp+80h+var_F8], eax
0x18017a260  lea     r9, [rbp+80h+var_FF]; unsigned __int8 *
0x18017a264  mov     [rbp+80h+var_F0], eax
0x18017a267  lea     r8, [rbp+80h+var_F8]; enum PixOp *
0x18017a26b  lea     rax, [rbp+80h+var_F0]
0x18017a26f  mov     [rbp+80h+var_FF], r15b
0x18017a273  mov     [rsp+1A0h+var_178], rax; enum PixOp *
0x18017a278  lea     rdx, [rbp+80h+var_E8]; unsigned __int64 *
0x18017a27c  lea     rax, [rbp+80h+var_100]
0x18017a280  mov     [rbp+80h+var_100], r15b
0x18017a284  mov     rcx, rsi; unsigned __int64
0x18017a287  mov     [rsp+1A0h+var_180], rax; unsigned __int8 *
0x18017a28c  call    ?PIXDecodeEventInfo@@YAX_KPEA_KPEAW4PixOp@@PEAE32@Z; PIXDecodeEventInfo(unsigned __int64,unsigned __int64 *,PixOp *,uchar *,uchar *,PixOp *)
0x18017a291  movzx   edx, [rbp+80h+var_100]
0x18017a295  movzx   esi, [rbp+80h+var_FF]
0x18017a299  mov     al, dl
0x18017a29b  and     al, 0F0h
0x18017a29d  cmp     al, 0F0h
0x18017a29f  jnz     short loc_18017A2B5
0x18017a2a1  mov     rax, [rbx]
0x18017a2a4  lea     ecx, [r15+8]
0x18017a2a8  add     rbx, 8
0x18017a2ac  mov     dword ptr [rdi+28h], 8
0x18017a2b3  jmp     short loc_18017A2C4
0x18017a2b5  mov     ecx, r15d
0x18017a2b8  test    sil, sil
0x18017a2bb  jz      short loc_18017A2D1
0x18017a2bd  mov     rax, rdx
0x18017a2c0  shr     rax, 4
0x18017a2c4  mov     [rdi+10h], rax
0x18017a2c8  test    sil, sil
0x18017a2cb  jz      short loc_18017A2D1
0x18017a2cd  lea     r15, [rbp+80h+var_100]
0x18017a2d1  test    dl, 1
0x18017a2d4  jz      short loc_18017A2E7
0x18017a2d6  mov     rax, [rbx]
0x18017a2d9  add     rbx, 8
0x18017a2dd  mov     [rdi+18h], rax
0x18017a2e1  lea     eax, [rcx+8]
0x18017a2e4  mov     [rdi+28h], eax
0x18017a2e7  xor     edx, edx; Val
0x18017a2e9  lea     rcx, [rbp+80h+var_C0]; void *
0x18017a2ed  mov     r8d, 80h; Size
0x18017a2f3  call    memset_0
0x18017a2f8  mov     r9, r15
0x18017a2fb  lea     rcx, [rbp+80h+var_E0]
0x18017a2ff  mov     r8, r12
0x18017a302  mov     rdx, rbx
0x18017a305  call    ?ReadString@PixEventDecoder@@YA?AUSavedStringInfo@1@PEB_K0PEBE@Z; PixEventDecoder::ReadString(unsigned __int64 const *,unsigned __int64 const *,uchar const *)
0x18017a30a  mov     ecx, [rax+4]
0x18017a30d  mov     r8d, [rax]
0x18017a310  mov     dl, [rax+8]
0x18017a313  mov     r15, [rax+10h]
0x18017a317  mov     eax, ecx
0x18017a319  add     [rdi+28h], ecx
0x18017a31c  shr     rax, 3
0x18017a320  mov     [rdi+24h], ecx
0x18017a323  mov     ecx, [rdi+28h]
0x18017a326  shr     rcx, 3
0x18017a32a  lea     r9, [rbx+rax*8]
0x18017a32e  inc     rcx
0x18017a331  lea     eax, [rsi-1]
0x18017a334  cmp     al, 7Dh ; '}'
0x18017a336  ja      short loc_18017A342
0x18017a338  mov     rax, rsi
0x18017a33b  sub     rax, rcx
0x18017a33e  lea     r12, [r9+rax*8]
0x18017a342  cmp     [rbp+80h+var_F0], 400h
0x18017a349  jnz     short loc_18017A3C2
0x18017a34b  cmp     rcx, rsi
0x18017a34e  jnz     short loc_18017A3C2
0x18017a350  test    dl, dl
0x18017a352  jz      short loc_18017A3AC
0x18017a354  mov     rax, cs:qword_18033B7B8
0x18017a35b  lea     rcx, [rbp+80h+var_F8]
0x18017a35f  mov     [rsp+1A0h+var_178], rax
0x18017a364  mov     esi, 4000h
0x18017a369  mov     [rsp+1A0h+var_180], r8
0x18017a36e  mov     r9, r15
0x18017a371  mov     r8d, esi
0x18017a374  mov     [rbp+80h+var_F8], 0
0x18017a37c  mov     rdx, r14
0x18017a37f  call    cs:__imp__o__mbstowcs_s_l
0x18017a385  test    eax, eax
0x18017a387  jz      loc_18017A59F
0x18017a38d  mov     r8, cs:off_180324BA8; unsigned __int16 *
0x18017a394  mov     edx, esi; unsigned __int64
0x18017a396  mov     rcx, r14; unsigned __int16 *
0x18017a399  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18017a39e  mov     ecx, cs:dword_180324BB0
0x18017a3a4  mov     [rdi+20h], ecx
0x18017a3a7  jmp     loc_18017A59F
0x18017a3ac  mov     r8, r15
0x18017a3af  mov     edx, 4000h
0x18017a3b4  mov     rcx, r14
0x18017a3b7  call    cs:__imp__o_wcscpy_s
0x18017a3bd  jmp     loc_18017A59F
0x18017a3c2  mov     [rsp+1A0h+var_180], r12
0x18017a3c7  mov     r8, r15
0x18017a3ca  lea     rcx, [rbp+80h+var_C0]
0x18017a3ce  test    dl, dl
0x18017a3d0  jz      loc_18017A4E4
0x18017a3d6  call    ??$PopulateFormatArguments@$$CBD@PixEventDecoder@@YAIPEA_KIPEBDPEB_K2@Z; PixEventDecoder::PopulateFormatArguments<char const>(unsigned __int64 *,uint,char const *,unsigned __int64 const *,unsigned __int64 const *)
0x18017a3db  add     [rdi+28h], eax
0x18017a3de  mov     esi, 4000h
0x18017a3e3  mov     rax, [rbp+80h+var_48]
0x18017a3e7  mov     r8, r15; char *
0x18017a3ea  mov     r9, [rbp+80h+var_C0]
0x18017a3ee  mov     edx, esi; unsigned __int64
0x18017a3f0  mov     [rsp+1A0h+var_110], rax
0x18017a3f8  mov     rcx, r13; char *
0x18017a3fb  mov     rax, [rbp+80h+var_50]
0x18017a3ff  mov     [rsp+1A0h+var_118], rax
0x18017a407  mov     rax, [rbp+80h+var_58]
0x18017a40b  mov     [rsp+1A0h+var_120], rax
0x18017a413  mov     rax, [rbp+80h+var_60]
0x18017a417  mov     [rsp+1A0h+var_128], rax
0x18017a41c  mov     rax, [rbp+80h+var_68]
0x18017a420  mov     [rsp+1A0h+var_130], rax
0x18017a425  mov     rax, [rbp+80h+var_70]
0x18017a429  mov     [rsp+1A0h+var_138], rax
0x18017a42e  mov     rax, [rbp+80h+var_78]
0x18017a432  mov     [rsp+1A0h+var_140], rax
0x18017a437  mov     rax, [rbp+80h+var_80]
0x18017a43b  mov     [rsp+1A0h+var_148], rax
0x18017a440  mov     rax, [rbp+80h+var_88]
0x18017a444  mov     [rsp+1A0h+var_150], rax
0x18017a449  mov     rax, [rbp+80h+var_90]
0x18017a44d  mov     [rsp+1A0h+var_158], rax
0x18017a452  mov     rax, [rbp+80h+var_98]
0x18017a456  mov     [rsp+1A0h+var_160], rax
0x18017a45b  mov     rax, [rbp+80h+var_A0]
0x18017a45f  mov     [rsp+1A0h+var_168], rax
0x18017a464  mov     rax, [rbp+80h+var_A8]
0x18017a468  mov     [rsp+1A0h+var_170], rax
0x18017a46d  mov     rax, [rbp+80h+var_B0]
0x18017a471  mov     [rsp+1A0h+var_178], rax
0x18017a476  mov     rax, [rbp+80h+var_B8]
0x18017a47a  mov     [rsp+1A0h+var_180], rax
0x18017a47f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18017a484  test    eax, eax
0x18017a486  js      loc_18017A59F
0x18017a48c  mov     rbx, cs:qword_18033B7B8
0x18017a493  mov     rcx, r13; String
0x18017a496  mov     [rbp+80h+var_F8], 0
0x18017a49e  call    strnlen_s
0x18017a4a3  mov     r9, r13
0x18017a4a6  mov     [rsp+1A0h+var_178], rbx
0x18017a4ab  mov     r8d, esi
0x18017a4ae  mov     [rsp+1A0h+var_180], rax
0x18017a4b3  mov     rdx, r14
0x18017a4b6  lea     rcx, [rbp+80h+var_F8]
0x18017a4ba  call    cs:__imp__o__mbstowcs_s_l
0x18017a4c0  mov     rcx, r14; unsigned __int16 *
0x18017a4c3  test    eax, eax
0x18017a4c5  jz      loc_18017A597
0x18017a4cb  mov     r8, cs:off_180324BA8; unsigned __int16 *
0x18017a4d2  mov     edx, esi; unsigned __int64
0x18017a4d4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18017a4d9  mov     eax, cs:dword_180324BB0
0x18017a4df  jmp     loc_18017A59C
0x18017a4e4  call    ??$PopulateFormatArguments@$$CBG@PixEventDecoder@@YAIPEA_KIPEBGPEB_K2@Z; PixEventDecoder::PopulateFormatArguments<ushort const>(unsigned __int64 *,uint,ushort const *,unsigned __int64 const *,unsigned __int64 const *)
0x18017a4e9  add     [rdi+28h], eax
0x18017a4ec  mov     r8, r15; unsigned __int16 *
0x18017a4ef  mov     rax, [rbp+80h+var_48]
0x18017a4f3  mov     edx, 4000h; unsigned __int64
0x18017a4f8  mov     r9, [rbp+80h+var_C0]
0x18017a4fc  mov     rcx, r14; unsigned __int16 *
0x18017a4ff  mov     [rsp+1A0h+var_110], rax
0x18017a507  mov     rax, [rbp+80h+var_50]
0x18017a50b  mov     [rsp+1A0h+var_118], rax
0x18017a513  mov     rax, [rbp+80h+var_58]
0x18017a517  mov     [rsp+1A0h+var_120], rax
0x18017a51f  mov     rax, [rbp+80h+var_60]
0x18017a523  mov     [rsp+1A0h+var_128], rax
0x18017a528  mov     rax, [rbp+80h+var_68]
0x18017a52c  mov     [rsp+1A0h+var_130], rax
0x18017a531  mov     rax, [rbp+80h+var_70]
0x18017a535  mov     [rsp+1A0h+var_138], rax
0x18017a53a  mov     rax, [rbp+80h+var_78]
0x18017a53e  mov     [rsp+1A0h+var_140], rax
0x18017a543  mov     rax, [rbp+80h+var_80]
0x18017a547  mov     [rsp+1A0h+var_148], rax
0x18017a54c  mov     rax, [rbp+80h+var_88]
0x18017a550  mov     [rsp+1A0h+var_150], rax
0x18017a555  mov     rax, [rbp+80h+var_90]
0x18017a559  mov     [rsp+1A0h+var_158], rax
0x18017a55e  mov     rax, [rbp+80h+var_98]
0x18017a562  mov     [rsp+1A0h+var_160], rax
0x18017a567  mov     rax, [rbp+80h+var_A0]
0x18017a56b  mov     [rsp+1A0h+var_168], rax
0x18017a570  mov     rax, [rbp+80h+var_A8]
0x18017a574  mov     [rsp+1A0h+var_170], rax
0x18017a579  mov     rax, [rbp+80h+var_B0]
0x18017a57d  mov     [rsp+1A0h+var_178], rax
0x18017a582  mov     rax, [rbp+80h+var_B8]
0x18017a586  mov     [rsp+1A0h+var_180], rax
0x18017a58b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18017a590  test    eax, eax
0x18017a592  js      short loc_18017A59F
0x18017a594  mov     rcx, r14; Source
0x18017a597  call    wcsnlen_s
0x18017a59c  mov     [rdi+20h], eax
0x18017a59f  mov     rax, rdi
0x18017a5a2  mov     rcx, [rbp+80h+var_40]
0x18017a5a6  xor     rcx, rsp; StackCookie
0x18017a5a9  call    __security_check_cookie
0x18017a5ae  mov     rbx, [rsp+1A0h+arg_8]
0x18017a5b6  add     rsp, 170h
0x18017a5bd  pop     r15
0x18017a5bf  pop     r14
0x18017a5c1  pop     r13
0x18017a5c3  pop     r12
0x18017a5c5  pop     rdi
0x18017a5c6  pop     rsi
0x18017a5c7  pop     rbp
0x18017a5c8  retn
```
