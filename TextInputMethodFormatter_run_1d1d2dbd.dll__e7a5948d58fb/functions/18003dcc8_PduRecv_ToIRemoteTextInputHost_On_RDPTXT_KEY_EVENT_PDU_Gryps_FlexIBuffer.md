# PduRecv_ToIRemoteTextInputHost::On_RDPTXT_KEY_EVENT_PDU(Gryps::FlexIBuffer *)

- ea: `0x18003dcc8`
- end: `0x18003e22d`
- name: `?On_RDPTXT_KEY_EVENT_PDU@PduRecv_ToIRemoteTextInputHost@@QEAAJPEAVFlexIBuffer@Gryps@@@Z`
- size: `1381`
- prototype: `__int64 __fastcall(PduRecv_ToIRemoteTextInputHost *__hidden this, struct Gryps::FlexIBuffer *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18003cf80`

## callees

- `0x1800019cc`
- `0x180002240`
- `0x180002db8`
- `0x180038c0c`
- `0x180038cc4`
- `0x180038d7c`
- `0x180038e34`
- `0x180039678`
- `0x1800396e0`
- `0x18003b8a4`
- `0x18003b984`
- `0x18003dcc8`
- `0x180058010`

## import_xrefs

- `CoreMessaging!MsgBlobCreateShared` at `0x18003e00c`
- `CoreMessaging!MsgBlobCreateShared` at `0x18003e00c`
- `CoreMessaging!MsgStringCreateShared` at `0x18003e064`
- `CoreMessaging!MsgStringCreateShared` at `0x18003e0c9`
- `CoreMessaging!MsgStringCreateShared` at `0x18003e064`
- `CoreMessaging!MsgStringCreateShared` at `0x18003e0c9`
- `CoreMessaging!MsgRelease` at `0x18003e1d0`
- `CoreMessaging!MsgRelease` at `0x18003e1da`
- `CoreMessaging!MsgRelease` at `0x18003e1e4`
- `CoreMessaging!MsgRelease` at `0x18003e1d0`
- `CoreMessaging!MsgRelease` at `0x18003e1da`
- `CoreMessaging!MsgRelease` at `0x18003e1e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PduRecv_ToIRemoteTextInputHost::On_RDPTXT_KEY_EVENT_PDU(
        PduRecv_ToIRemoteTextInputHost *this,
        struct Gryps::FlexIBuffer *a2)
{
  unsigned int v4; // esi
  bool v5; // r14
  __int128 *v6; // rcx
  __int128 *v7; // rcx
  __int128 *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  int v21; // [rsp+20h] [rbp-E0h]
  unsigned int v22; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v23; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v24; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v25; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v26; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v27; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h] BYREF
  __int64 v29; // [rsp+80h] [rbp-80h] BYREF
  __int64 v30; // [rsp+88h] [rbp-78h] BYREF
  __int128 v31; // [rsp+90h] [rbp-70h] BYREF
  __int128 v32; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v33; // [rsp+B0h] [rbp-50h] BYREF
  int v34; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+C4h] [rbp-3Ch] BYREF
  int v36; // [rsp+CCh] [rbp-34h] BYREF
  _WORD v37[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v38; // [rsp+E0h] [rbp-20h] BYREF
  __m128i v39; // [rsp+F0h] [rbp-10h]
  __int128 v40; // [rsp+100h] [rbp+0h] BYREF
  __m128i v41; // [rsp+110h] [rbp+10h]
  __int128 v42; // [rsp+120h] [rbp+20h] BYREF
  __m128i si128; // [rsp+130h] [rbp+30h]
  __int128 v44; // [rsp+140h] [rbp+40h] BYREF
  __int128 v45; // [rsp+150h] [rbp+50h]
  __int128 v46; // [rsp+160h] [rbp+60h]

  v26 = 0;
  v25 = 0;
  v27 = 0;
  v24 = 0;
  memset_0(&v31, 0, 0x48u);
  v28 = 0;
  v29 = 0;
  v23 = 0;
  v30 = 0;
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000) != 0
    && (qword_180082098 & 0x400000) == qword_180082098 )
  {
    tlgWriteTransfer_EventWriteTransfer(&dword_180082080, &unk_180076294, 0, 0, 2, &v44);
  }
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v26);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v25);
  LOBYTE(v22) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned char>(a2, &v22);
  v4 = (unsigned __int8)v22;
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v27);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v24);
  LOBYTE(v22) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned char>(a2, &v22);
  v5 = (_BYTE)v22 != 0;
  LOWORD(v22) = 0;
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, &v22);
  LODWORD(v31) = (unsigned __int16)v22;
  LOWORD(v22) = 0;
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, &v22);
  DWORD1(v31) = (unsigned __int16)v22;
  v22 = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v22);
  DWORD2(v31) = v22;
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, (_WORD *)&v31 + 6);
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, (_WORD *)&v31 + 7);
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, &v32);
  Gryps::FlexIBuffer::extractLE<unsigned __int64>((__int64)a2, (_QWORD *)&v32 + 1);
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, &v33);
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, (_WORD *)&v33 + 1);
  LOBYTE(v22) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned char>(a2, &v22);
  DWORD1(v33) = (unsigned __int8)v22;
  LOBYTE(v22) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned char>(a2, &v22);
  DWORD2(v33) = (unsigned __int8)v22;
  LOBYTE(v22) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned char>(a2, &v22);
  HIDWORD(v33) = (unsigned __int8)v22;
  LOBYTE(v22) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned char>(a2, &v22);
  v34 = (unsigned __int8)v22;
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v35);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, (_DWORD *)&v35 + 1);
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, &v36);
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, (_WORD *)&v36 + 1);
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, v37);
  LOWORD(v44) = v31;
  WORD1(v44) = WORD2(v31);
  *(_QWORD *)((char *)&v44 + 4) = *((_QWORD *)&v31 + 1);
  HIDWORD(v44) = (unsigned __int16)v32;
  *(_QWORD *)&v45 = *((_QWORD *)&v32 + 1);
  DWORD2(v45) = v33;
  BYTE12(v45) = DWORD1(v33) != 0;
  BYTE13(v45) = DWORD2(v33) != 0;
  BYTE14(v45) = HIDWORD(v33) != 0;
  HIBYTE(v45) = v34 != 0;
  *(_QWORD *)&v46 = v35;
  DWORD2(v46) = v36;
  HIDWORD(v46) = v37[0];
  v22 = 0;
  v42 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v42) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v22);
  Gryps::FlexIBuffer::extractString((__int64)a2, &v42, v22);
  v6 = &v42;
  if ( si128.m128i_i64[1] > 0xFuLL )
    v6 = (__int128 *)v42;
  MsgBlobCreateShared(v6, v22, &v28);
  v22 = 0;
  v40 = 0;
  v41 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v40) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v22);
  Gryps::FlexIBuffer::extractUTF16String((__int64)a2, (char ***)&v40, v22);
  v7 = &v40;
  if ( v41.m128i_i64[1] > 7uLL )
    v7 = (__int128 *)v40;
  MsgStringCreateShared(v7, v22, &v29);
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, &v23);
  v22 = 0;
  v38 = 0;
  v39 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v38) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v22);
  Gryps::FlexIBuffer::extractUTF16String((__int64)a2, (char ***)&v38, v22);
  v8 = &v38;
  if ( v39.m128i_i64[1] > 7uLL )
    v8 = (__int128 *)v38;
  MsgStringCreateShared(v8, v22, &v30);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1), v26);
  if ( v4 == 2 )
  {
    v13 = *((_QWORD *)this + 3);
    v31 = v44;
    v32 = v45;
    v33 = v46;
    LOBYTE(v21) = v5;
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int, __int128 *, __int64, __int64, __int16, __int64))(*(_QWORD *)v13 + 24LL))(
      v13,
      v25,
      v27,
      v24,
      v21,
      &v31,
      v28,
      v29,
      v23,
      v30);
  }
  else if ( v4 != 2 )
  {
    v12 = *((_QWORD *)this + 3);
    v31 = v44;
    v32 = v45;
    v33 = v46;
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int128 *, __int64, __int64, __int16, __int64))(*(_QWORD *)v12 + 48LL))(
      v12,
      v25,
      v24,
      v4,
      &v31,
      v28,
      v29,
      v23,
      v30);
  }
  MsgRelease(v28, v9, v10, v11);
  MsgRelease(v29, v14, v15, v16);
  MsgRelease(v30, v17, v18, v19);
  std::wstring::~wstring(&v38);
  std::wstring::~wstring(&v40);
  std::string::~string(&v42);
  return 0;
}

```

## disassembly

```asm
0x18003dcc8  mov     [rsp-8+arg_10], rbx
0x18003dccd  push    rbp
0x18003dcce  push    rsi
0x18003dccf  push    rdi
0x18003dcd0  push    r14
0x18003dcd2  push    r15
0x18003dcd4  lea     rbp, [rsp-80h]
0x18003dcd9  sub     rsp, 180h
0x18003dce0  mov     rax, cs:__security_cookie
0x18003dce7  xor     rax, rsp
0x18003dcea  mov     [rbp+0A0h+var_30], rax
0x18003dcee  mov     rdi, rdx
0x18003dcf1  mov     rbx, rcx
0x18003dcf4  xor     r15d, r15d
0x18003dcf7  mov     [rsp+1A0h+var_130], r15d
0x18003dcfc  mov     [rsp+1A0h+var_134], r15d
0x18003dd01  mov     [rsp+1A0h+var_12C], r15d
0x18003dd06  mov     [rsp+1A0h+var_138], r15d
0x18003dd0b  xor     edx, edx; Val
0x18003dd0d  lea     r8d, [r15+48h]; Size
0x18003dd11  lea     rcx, [rbp+0A0h+var_110]; void *
0x18003dd15  call    memset_0
0x18003dd1a  mov     [rsp+1A0h+var_128], r15
0x18003dd1f  mov     [rbp+0A0h+var_120], r15
0x18003dd23  mov     [rsp+1A0h+var_13C], r15w
0x18003dd29  mov     [rbp+0A0h+var_118], r15
0x18003dd2d  mov     eax, cs:dword_180082080
0x18003dd33  cmp     eax, 5
0x18003dd36  jbe     short loc_18003DD85
0x18003dd38  mov     rcx, cs:qword_180082098
0x18003dd3f  mov     rax, cs:qword_180082090
0x18003dd46  mov     edx, 400000h
0x18003dd4b  test    rdx, rax
0x18003dd4e  jz      short loc_18003DD85
0x18003dd50  mov     rax, rcx
0x18003dd53  and     rax, rdx
0x18003dd56  cmp     rax, rcx
0x18003dd59  jnz     short loc_18003DD85
0x18003dd5b  lea     rax, [rbp+0A0h+var_60]
0x18003dd5f  mov     [rsp+1A0h+var_178], rax
0x18003dd64  mov     dword ptr [rsp+1A0h+var_180], 2
0x18003dd6c  xor     r9d, r9d
0x18003dd6f  xor     r8d, r8d
0x18003dd72  lea     rdx, unk_180076294
0x18003dd79  lea     rcx, dword_180082080
0x18003dd80  call    _tlgWriteTransfer_EventWriteTransfer
0x18003dd85  lea     rdx, [rsp+1A0h+var_130]
0x18003dd8a  mov     rcx, rdi
0x18003dd8d  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003dd92  lea     rdx, [rsp+1A0h+var_134]
0x18003dd97  mov     rcx, rdi
0x18003dd9a  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003dd9f  mov     byte ptr [rsp+1A0h+var_140], r15b
0x18003dda4  lea     rdx, [rsp+1A0h+var_140]
0x18003dda9  mov     rcx, rdi
0x18003ddac  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x18003ddb1  movzx   esi, byte ptr [rsp+1A0h+var_140]
0x18003ddb6  lea     rdx, [rsp+1A0h+var_12C]
0x18003ddbb  mov     rcx, rdi
0x18003ddbe  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003ddc3  lea     rdx, [rsp+1A0h+var_138]
0x18003ddc8  mov     rcx, rdi
0x18003ddcb  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003ddd0  mov     byte ptr [rsp+1A0h+var_140], r15b
0x18003ddd5  lea     rdx, [rsp+1A0h+var_140]
0x18003ddda  mov     rcx, rdi
0x18003dddd  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x18003dde2  cmp     byte ptr [rsp+1A0h+var_140], r15b
0x18003dde7  setnz   r14b
0x18003ddeb  mov     word ptr [rsp+1A0h+var_140], r15w
0x18003ddf1  lea     rdx, [rsp+1A0h+var_140]
0x18003ddf6  mov     rcx, rdi
0x18003ddf9  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x18003ddfe  movzx   eax, word ptr [rsp+1A0h+var_140]
0x18003de03  mov     dword ptr [rbp+0A0h+var_110], eax
0x18003de06  mov     word ptr [rsp+1A0h+var_140], r15w
0x18003de0c  lea     rdx, [rsp+1A0h+var_140]
0x18003de11  mov     rcx, rdi
0x18003de14  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x18003de19  movzx   eax, word ptr [rsp+1A0h+var_140]
0x18003de1e  mov     dword ptr [rbp+0A0h+var_110+4], eax
0x18003de21  mov     [rsp+1A0h+var_140], r15d
0x18003de26  lea     rdx, [rsp+1A0h+var_140]
0x18003de2b  mov     rcx, rdi
0x18003de2e  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003de33  mov     eax, [rsp+1A0h+var_140]
0x18003de37  mov     dword ptr [rbp+0A0h+var_110+8], eax
0x18003de3a  lea     rdx, [rbp+0A0h+var_110+0Ch]
0x18003de3e  mov     rcx, rdi
0x18003de41  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x18003de46  lea     rdx, [rbp+0A0h+var_110+0Eh]
0x18003de4a  mov     rcx, rdi
0x18003de4d  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x18003de52  lea     rdx, [rbp+0A0h+var_100]
0x18003de56  mov     rcx, rdi
0x18003de59  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x18003de5e  lea     rdx, [rbp+0A0h+var_100+8]
0x18003de62  mov     rcx, rdi
0x18003de65  call    ??$extractLE@_K@FlexIBuffer@Gryps@@QEAAXAEA_K@Z; Gryps::FlexIBuffer::extractLE<unsigned __int64>(unsigned __int64 &)
0x18003de6a  lea     rdx, [rbp+0A0h+var_F0]
0x18003de6e  mov     rcx, rdi
0x18003de71  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x18003de76  lea     rdx, [rbp+0A0h+var_F0+2]
0x18003de7a  mov     rcx, rdi
0x18003de7d  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x18003de82  mov     byte ptr [rsp+1A0h+var_140], r15b
0x18003de87  lea     rdx, [rsp+1A0h+var_140]
0x18003de8c  mov     rcx, rdi
0x18003de8f  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x18003de94  movzx   eax, byte ptr [rsp+1A0h+var_140]
0x18003de99  mov     dword ptr [rbp+0A0h+var_F0+4], eax
0x18003de9c  mov     byte ptr [rsp+1A0h+var_140], r15b
0x18003dea1  lea     rdx, [rsp+1A0h+var_140]
0x18003dea6  mov     rcx, rdi
0x18003dea9  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x18003deae  movzx   eax, byte ptr [rsp+1A0h+var_140]
0x18003deb3  mov     dword ptr [rbp+0A0h+var_F0+8], eax
0x18003deb6  mov     byte ptr [rsp+1A0h+var_140], r15b
0x18003debb  lea     rdx, [rsp+1A0h+var_140]
0x18003dec0  mov     rcx, rdi
0x18003dec3  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x18003dec8  movzx   eax, byte ptr [rsp+1A0h+var_140]
0x18003decd  mov     dword ptr [rbp+0A0h+var_F0+0Ch], eax
0x18003ded0  mov     byte ptr [rsp+1A0h+var_140], r15b
0x18003ded5  lea     rdx, [rsp+1A0h+var_140]
0x18003deda  mov     rcx, rdi
0x18003dedd  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x18003dee2  movzx   eax, byte ptr [rsp+1A0h+var_140]
0x18003dee7  mov     [rbp+0A0h+var_E0], eax
0x18003deea  lea     rdx, [rbp+0A0h+var_DC]
0x18003deee  mov     rcx, rdi
0x18003def1  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003def6  lea     rdx, [rbp+0A0h+var_DC+4]
0x18003defa  mov     rcx, rdi
0x18003defd  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003df02  lea     rdx, [rbp+0A0h+var_D4]
0x18003df06  mov     rcx, rdi
0x18003df09  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x18003df0e  lea     rdx, [rbp+0A0h+var_D4+2]
0x18003df12  mov     rcx, rdi
0x18003df15  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x18003df1a  lea     rdx, [rbp+0A0h+var_D0]
0x18003df1e  mov     rcx, rdi
0x18003df21  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x18003df26  mov     word ptr [rbp+0A0h+var_60+0Eh], r15w
0x18003df2b  mov     word ptr [rbp+0A0h+var_40+0Eh], r15w
0x18003df30  movzx   eax, word ptr [rbp+0A0h+var_110]
0x18003df34  mov     word ptr [rbp+0A0h+var_60], ax
0x18003df38  movzx   eax, word ptr [rbp+0A0h+var_110+4]
0x18003df3c  mov     word ptr [rbp+0A0h+var_60+2], ax
0x18003df40  mov     eax, dword ptr [rbp+0A0h+var_110+8]
0x18003df43  mov     dword ptr [rbp+0A0h+var_60+4], eax
0x18003df46  movzx   eax, word ptr [rbp+0A0h+var_110+0Ch]
0x18003df4a  mov     word ptr [rbp+0A0h+var_60+8], ax
0x18003df4e  movzx   eax, word ptr [rbp+0A0h+var_110+0Eh]
0x18003df52  mov     word ptr [rbp+0A0h+var_60+0Ah], ax
0x18003df56  movzx   eax, word ptr [rbp+0A0h+var_100]
0x18003df5a  mov     word ptr [rbp+0A0h+var_60+0Ch], ax
0x18003df5e  mov     rax, qword ptr [rbp+0A0h+var_100+8]
0x18003df62  mov     qword ptr [rbp+0A0h+var_50], rax
0x18003df66  movzx   eax, word ptr [rbp+0A0h+var_F0]
0x18003df6a  mov     word ptr [rbp+0A0h+var_50+8], ax
0x18003df6e  movzx   eax, word ptr [rbp+0A0h+var_F0+2]
0x18003df72  mov     word ptr [rbp+0A0h+var_50+0Ah], ax
0x18003df76  cmp     dword ptr [rbp+0A0h+var_F0+4], r15d
0x18003df7a  setnz   byte ptr [rbp+0A0h+var_50+0Ch]
0x18003df7e  cmp     dword ptr [rbp+0A0h+var_F0+8], r15d
0x18003df82  setnz   byte ptr [rbp+0A0h+var_50+0Dh]
0x18003df86  cmp     dword ptr [rbp+0A0h+var_F0+0Ch], r15d
0x18003df8a  setnz   byte ptr [rbp+0A0h+var_50+0Eh]
0x18003df8e  cmp     [rbp+0A0h+var_E0], r15d
0x18003df92  setnz   byte ptr [rbp+0A0h+var_50+0Fh]
0x18003df96  mov     eax, dword ptr [rbp+0A0h+var_DC]
0x18003df99  mov     dword ptr [rbp+0A0h+var_40], eax
0x18003df9c  mov     eax, dword ptr [rbp+0A0h+var_DC+4]
0x18003df9f  mov     dword ptr [rbp+0A0h+var_40+4], eax
0x18003dfa2  movzx   eax, word ptr [rbp+0A0h+var_D4]
0x18003dfa6  mov     word ptr [rbp+0A0h+var_40+8], ax
0x18003dfaa  movzx   eax, word ptr [rbp+0A0h+var_D4+2]
0x18003dfae  mov     word ptr [rbp+0A0h+var_40+0Ah], ax
0x18003dfb2  movzx   eax, [rbp+0A0h+var_D0]
0x18003dfb6  mov     word ptr [rbp+0A0h+var_40+0Ch], ax
0x18003dfba  mov     [rsp+1A0h+var_140], r15d
0x18003dfbf  xorps   xmm0, xmm0
0x18003dfc2  movups  [rbp+0A0h+var_80], xmm0
0x18003dfc6  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18003dfce  movdqu  [rbp+0A0h+var_70], xmm1
0x18003dfd3  mov     byte ptr [rbp+0A0h+var_80], r15b
0x18003dfd7  lea     rdx, [rsp+1A0h+var_140]
0x18003dfdc  mov     rcx, rdi
0x18003dfdf  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003dfe4  mov     r8d, [rsp+1A0h+var_140]
0x18003dfe9  lea     rdx, [rbp+0A0h+var_80]
0x18003dfed  mov     rcx, rdi
0x18003dff0  call    ?extractString@FlexIBuffer@Gryps@@QEAAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K_N@Z; Gryps::FlexIBuffer::extractString(std::string &,unsigned __int64,bool)
0x18003dff5  lea     rcx, [rbp+0A0h+var_80]
0x18003dff9  cmp     qword ptr [rbp+0A0h+var_70+8], 0Fh
0x18003dffe  cmova   rcx, qword ptr [rbp+0A0h+var_80]
0x18003e003  lea     r8, [rsp+1A0h+var_128]
0x18003e008  mov     edx, [rsp+1A0h+var_140]
0x18003e00c  call    cs:__imp_MsgBlobCreateShared
0x18003e012  mov     [rsp+1A0h+var_140], r15d
0x18003e017  xorps   xmm0, xmm0
0x18003e01a  movups  [rbp+0A0h+var_A0], xmm0
0x18003e01e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003e026  movdqu  [rbp+0A0h+var_90], xmm1
0x18003e02b  mov     word ptr [rbp+0A0h+var_A0], r15w
0x18003e030  lea     rdx, [rsp+1A0h+var_140]
0x18003e035  mov     rcx, rdi
0x18003e038  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003e03d  mov     r8d, [rsp+1A0h+var_140]
0x18003e042  lea     rdx, [rbp+0A0h+var_A0]
0x18003e046  mov     rcx, rdi
0x18003e049  call    ?extractUTF16String@FlexIBuffer@Gryps@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K_N@Z; Gryps::FlexIBuffer::extractUTF16String(std::wstring &,unsigned __int64,bool)
0x18003e04e  lea     rcx, [rbp+0A0h+var_A0]
0x18003e052  cmp     qword ptr [rbp+0A0h+var_90+8], 7
0x18003e057  cmova   rcx, qword ptr [rbp+0A0h+var_A0]
0x18003e05c  lea     r8, [rbp+0A0h+var_120]
0x18003e060  mov     edx, [rsp+1A0h+var_140]
0x18003e064  call    cs:__imp_MsgStringCreateShared
0x18003e06a  lea     rdx, [rsp+1A0h+var_13C]
0x18003e06f  mov     rcx, rdi
0x18003e072  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x18003e077  mov     [rsp+1A0h+var_140], r15d
0x18003e07c  xorps   xmm0, xmm0
0x18003e07f  movups  [rbp+0A0h+var_C0], xmm0
0x18003e083  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003e08b  movdqu  [rbp+0A0h+var_B0], xmm1
0x18003e090  mov     word ptr [rbp+0A0h+var_C0], r15w
0x18003e095  lea     rdx, [rsp+1A0h+var_140]
0x18003e09a  mov     rcx, rdi
0x18003e09d  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003e0a2  mov     r8d, [rsp+1A0h+var_140]
0x18003e0a7  lea     rdx, [rbp+0A0h+var_C0]
0x18003e0ab  mov     rcx, rdi
0x18003e0ae  call    ?extractUTF16String@FlexIBuffer@Gryps@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K_N@Z; Gryps::FlexIBuffer::extractUTF16String(std::wstring &,unsigned __int64,bool)
0x18003e0b3  lea     rcx, [rbp+0A0h+var_C0]
0x18003e0b7  cmp     qword ptr [rbp+0A0h+var_B0+8], 7
0x18003e0bc  cmova   rcx, qword ptr [rbp+0A0h+var_C0]
0x18003e0c1  lea     r8, [rbp+0A0h+var_118]
0x18003e0c5  mov     edx, [rsp+1A0h+var_140]
0x18003e0c9  call    cs:__imp_MsgStringCreateShared
0x18003e0cf  mov     rcx, [rbx+8]
0x18003e0d3  mov     rax, [rcx]
0x18003e0d6  mov     edx, [rsp+1A0h+var_130]
0x18003e0da  mov     rax, [rax+10h]
0x18003e0de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e0e3  mov     eax, r15d
0x18003e0e6  cmp     esi, 2
0x18003e0e9  setnz   al
0x18003e0ec  inc     eax
0x18003e0ee  sub     eax, 1
0x18003e0f1  jz      short loc_18003E161
0x18003e0f3  cmp     eax, 1
0x18003e0f6  jnz     loc_18003E1CB
0x18003e0fc  mov     rcx, [rbx+18h]
0x18003e100  movups  xmm0, [rbp+0A0h+var_60]
0x18003e104  movaps  [rbp+0A0h+var_110], xmm0
0x18003e108  movups  xmm1, [rbp+0A0h+var_50]
0x18003e10c  movaps  [rbp+0A0h+var_100], xmm1
0x18003e110  movups  xmm0, [rbp+0A0h+var_40]
0x18003e114  movaps  [rbp+0A0h+var_F0], xmm0
0x18003e118  mov     rax, [rcx]
0x18003e11b  mov     rdx, [rbp+0A0h+var_118]
0x18003e11f  mov     [rsp+1A0h+var_160], rdx
0x18003e124  movzx   edx, [rsp+1A0h+var_13C]
0x18003e129  mov     word ptr [rsp+1A0h+var_168], dx
0x18003e12e  mov     rdx, [rbp+0A0h+var_120]
0x18003e132  mov     [rsp+1A0h+var_170], rdx
0x18003e137  mov     rdx, [rsp+1A0h+var_128]
0x18003e13c  mov     [rsp+1A0h+var_178], rdx
0x18003e141  lea     rdx, [rbp+0A0h+var_110]
0x18003e145  mov     [rsp+1A0h+var_180], rdx
0x18003e14a  mov     r9d, esi
0x18003e14d  mov     r8d, [rsp+1A0h+var_138]
0x18003e152  mov     edx, [rsp+1A0h+var_134]
0x18003e156  mov     rax, [rax+30h]
0x18003e15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e15f  jmp     short loc_18003E1CB
0x18003e161  mov     rcx, [rbx+18h]
0x18003e165  movups  xmm0, [rbp+0A0h+var_60]
0x18003e169  movaps  [rbp+0A0h+var_110], xmm0
0x18003e16d  movups  xmm1, [rbp+0A0h+var_50]
0x18003e171  movaps  [rbp+0A0h+var_100], xmm1
0x18003e175  movups  xmm0, [rbp+0A0h+var_40]
0x18003e179  movaps  [rbp+0A0h+var_F0], xmm0
0x18003e17d  mov     rax, [rcx]
0x18003e180  mov     rdx, [rbp+0A0h+var_118]
0x18003e184  mov     [rsp+1A0h+var_158], rdx
0x18003e189  movzx   edx, [rsp+1A0h+var_13C]
0x18003e18e  mov     word ptr [rsp+1A0h+var_160], dx
0x18003e193  mov     rdx, [rbp+0A0h+var_120]
0x18003e197  mov     [rsp+1A0h+var_168], rdx
0x18003e19c  mov     rdx, [rsp+1A0h+var_128]
0x18003e1a1  mov     [rsp+1A0h+var_170], rdx
0x18003e1a6  lea     rdx, [rbp+0A0h+var_110]
0x18003e1aa  mov     [rsp+1A0h+var_178], rdx
0x18003e1af  mov     byte ptr [rsp+1A0h+var_180], r14b
0x18003e1b4  mov     r9d, [rsp+1A0h+var_138]
0x18003e1b9  mov     r8d, [rsp+1A0h+var_12C]
  ... truncated ...
```
