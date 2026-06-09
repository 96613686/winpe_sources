# PduRecv_ToRemoteTextAppIntegration::On_RDPTXT_TEXT_CHANGED_PDU(Gryps::FlexIBuffer *)

- ea: `0x1800519e8`
- end: `0x180051e74`
- name: `?On_RDPTXT_TEXT_CHANGED_PDU@PduRecv_ToRemoteTextAppIntegration@@QEAAJPEAVFlexIBuffer@Gryps@@@Z`
- size: `1164`
- prototype: `__int64 __fastcall(PduRecv_ToRemoteTextAppIntegration *__hidden this, struct Gryps::FlexIBuffer *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18004f430`

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
- `0x1800519e8`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180051cc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180051d3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180051cc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180051d3a`

## pseudocode

```c
__int64 __fastcall PduRecv_ToRemoteTextAppIntegration::On_RDPTXT_TEXT_CHANGED_PDU(
        PduRecv_ToRemoteTextAppIntegration *this,
        struct Gryps::FlexIBuffer *a2)
{
  BOOL v4; // esi
  BOOL v5; // edi
  const WCHAR *v6; // rcx
  const WCHAR *v7; // rcx
  unsigned int v8; // ebx
  __int128 *v9; // rcx
  __int64 v10; // r11
  UINT32 length; // [rsp+90h] [rbp-80h] BYREF
  unsigned int v13; // [rsp+94h] [rbp-7Ch] BYREF
  int v14; // [rsp+98h] [rbp-78h] BYREF
  int v15; // [rsp+9Ch] [rbp-74h] BYREF
  int v16; // [rsp+A0h] [rbp-70h] BYREF
  int v17; // [rsp+A4h] [rbp-6Ch] BYREF
  unsigned int v18; // [rsp+A8h] [rbp-68h] BYREF
  unsigned int v19; // [rsp+ACh] [rbp-64h] BYREF
  __int64 v20; // [rsp+B0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+B8h] [rbp-58h] BYREF
  HSTRING v22; // [rsp+C0h] [rbp-50h] BYREF
  HSTRING string; // [rsp+C8h] [rbp-48h] BYREF
  __int128 v24; // [rsp+D0h] [rbp-40h] BYREF
  __int128 v25; // [rsp+E0h] [rbp-30h] BYREF
  __int128 v26; // [rsp+F0h] [rbp-20h] BYREF
  __int128 v27; // [rsp+100h] [rbp-10h] BYREF
  __int64 v28; // [rsp+110h] [rbp+0h] BYREF
  _OWORD v29[4]; // [rsp+120h] [rbp+10h] BYREF
  __int64 v30; // [rsp+160h] [rbp+50h]
  __int128 v31; // [rsp+170h] [rbp+60h] BYREF
  __m128i v32; // [rsp+180h] [rbp+70h]
  PCNZWCH v33[2]; // [rsp+190h] [rbp+80h] BYREF
  __m128i v34; // [rsp+1A0h] [rbp+90h]
  PCNZWCH sourceString[2]; // [rsp+1B0h] [rbp+A0h] BYREF
  __m128i si128; // [rsp+1C0h] [rbp+B0h]
  _BYTE v37[32]; // [rsp+1D0h] [rbp+C0h] BYREF

  v19 = 0;
  v18 = 0;
  v21 = 0;
  v20 = 0;
  v17 = 0;
  v16 = 0;
  memset_0(&v24, 0, 0x48u);
  v15 = 0;
  string = 0;
  v14 = 0;
  v22 = 0;
  v13 = 0;
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000) != 0
    && (qword_180082098 & 0x400000) == qword_180082098 )
  {
    tlgWriteTransfer_EventWriteTransfer(&dword_180082080, &unk_180078754, 0, 0, 2, v37);
  }
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v19);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v18);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v21);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, (_DWORD *)&v21 + 1);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v20);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, (_DWORD *)&v20 + 1);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v17);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v16);
  LOWORD(length) = 0;
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, &length);
  LODWORD(v24) = (unsigned __int16)length;
  LOWORD(length) = 0;
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, &length);
  DWORD1(v24) = (unsigned __int16)length;
  length = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &length);
  DWORD2(v24) = length;
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, (_WORD *)&v24 + 6);
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, (_WORD *)&v24 + 7);
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, &v25);
  Gryps::FlexIBuffer::extractLE<unsigned __int64>((__int64)a2, (_QWORD *)&v25 + 1);
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, &v26);
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, (_WORD *)&v26 + 1);
  LOBYTE(length) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned char>(a2, &length);
  DWORD1(v26) = (unsigned __int8)length;
  LOBYTE(length) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned char>(a2, &length);
  DWORD2(v26) = (unsigned __int8)length;
  LOBYTE(length) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned char>(a2, &length);
  HIDWORD(v26) = (unsigned __int8)length;
  LOBYTE(length) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned char>(a2, &length);
  LODWORD(v27) = (unsigned __int8)length;
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, (_DWORD *)&v27 + 1);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, (_DWORD *)&v27 + 2);
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, (_WORD *)&v27 + 6);
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, (_WORD *)&v27 + 7);
  Gryps::FlexIBuffer::extractLE<short>((__int64)a2, &v28);
  LOBYTE(length) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned char>(a2, &length);
  v4 = (_BYTE)length != 0;
  LOBYTE(length) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned char>(a2, &length);
  v5 = (_BYTE)length != 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v15);
  length = 0;
  *(_OWORD *)sourceString = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(sourceString[0]) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &length);
  Gryps::FlexIBuffer::extractUTF16String((__int64)a2, (char ***)sourceString, length);
  v6 = (const WCHAR *)sourceString;
  if ( si128.m128i_i64[1] > 7uLL )
    v6 = sourceString[0];
  WindowsCreateString(v6, length, &string);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v14);
  length = 0;
  *(_OWORD *)v33 = 0;
  v34 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v33[0]) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &length);
  Gryps::FlexIBuffer::extractUTF16String((__int64)a2, (char ***)v33, length);
  v7 = (const WCHAR *)v33;
  if ( v34.m128i_i64[1] > 7uLL )
    v7 = v33[0];
  WindowsCreateString(v7, length, &v22);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v13);
  v31 = 0;
  v32 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v31) = 0;
  v8 = v13;
  Gryps::FlexIBuffer::extractString((__int64)a2, &v31, v13);
  v9 = &v31;
  if ( v32.m128i_i64[1] > 0xFuLL )
    v9 = (__int128 *)v31;
  v10 = *((_QWORD *)this + 1);
  v29[0] = v24;
  v29[1] = v25;
  v29[2] = v26;
  v29[3] = v27;
  v30 = v28;
  (*(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64, __int64, int, int, _OWORD *, BOOL, BOOL, int, HSTRING, int, HSTRING, unsigned int, __int128 *))(*(_QWORD *)v10 + 688LL))(
    v10,
    v19,
    v18,
    v21,
    v20,
    v17,
    v16,
    v29,
    v4,
    v5,
    v15,
    string,
    v14,
    v22,
    v8,
    v9);
  std::string::~string(&v31);
  std::wstring::~wstring(v33);
  std::wstring::~wstring(sourceString);
  return 0;
}

```

## disassembly

```asm
0x1800519e8  mov     [rsp-8+arg_10], rbx
0x1800519ed  push    rbp
0x1800519ee  push    rsi
0x1800519ef  push    rdi
0x1800519f0  push    r14
0x1800519f2  push    r15
0x1800519f4  lea     rbp, [rsp-0F0h]
0x1800519fc  sub     rsp, 200h
0x180051a03  mov     rax, cs:__security_cookie
0x180051a0a  xor     rax, rsp
0x180051a0d  mov     [rbp+110h+var_30], rax
0x180051a14  mov     r14, rdx
0x180051a17  mov     r15, rcx
0x180051a1a  xor     ebx, ebx
0x180051a1c  mov     [rbp+110h+var_174], ebx
0x180051a1f  mov     [rbp+110h+var_178], ebx
0x180051a22  mov     [rbp+110h+var_168], rbx
0x180051a26  mov     [rbp+110h+var_170], rbx
0x180051a2a  mov     [rbp+110h+var_17C], ebx
0x180051a2d  mov     [rbp+110h+var_180], ebx
0x180051a30  xor     edx, edx; Val
0x180051a32  lea     r8d, [rbx+48h]; Size
0x180051a36  lea     rcx, [rbp+110h+var_150]; void *
0x180051a3a  call    memset_0
0x180051a3f  mov     [rbp+110h+var_184], ebx
0x180051a42  mov     [rbp+110h+string], rbx
0x180051a46  mov     [rbp+110h+var_188], ebx
0x180051a49  mov     [rbp+110h+var_160], rbx
0x180051a4d  mov     [rbp+110h+var_18C], ebx
0x180051a50  mov     eax, cs:dword_180082080
0x180051a56  cmp     eax, 5
0x180051a59  jbe     short loc_180051AAB
0x180051a5b  mov     rcx, cs:qword_180082098
0x180051a62  mov     rax, cs:qword_180082090
0x180051a69  mov     edx, 400000h
0x180051a6e  test    rdx, rax
0x180051a71  jz      short loc_180051AAB
0x180051a73  mov     rax, rcx
0x180051a76  and     rax, rdx
0x180051a79  cmp     rax, rcx
0x180051a7c  jnz     short loc_180051AAB
0x180051a7e  lea     rax, [rbp+110h+var_50]
0x180051a85  mov     [rsp+220h+var_1F8], rax
0x180051a8a  mov     dword ptr [rsp+220h+var_200], 2
0x180051a92  xor     r9d, r9d
0x180051a95  xor     r8d, r8d
0x180051a98  lea     rdx, unk_180078754
0x180051a9f  lea     rcx, dword_180082080
0x180051aa6  call    _tlgWriteTransfer_EventWriteTransfer
0x180051aab  lea     rdx, [rbp+110h+var_174]
0x180051aaf  mov     rcx, r14
0x180051ab2  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180051ab7  lea     rdx, [rbp+110h+var_178]
0x180051abb  mov     rcx, r14
0x180051abe  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180051ac3  lea     rdx, [rbp+110h+var_168]
0x180051ac7  mov     rcx, r14
0x180051aca  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180051acf  lea     rdx, [rbp+110h+var_168+4]
0x180051ad3  mov     rcx, r14
0x180051ad6  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180051adb  lea     rdx, [rbp+110h+var_170]
0x180051adf  mov     rcx, r14
0x180051ae2  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180051ae7  lea     rdx, [rbp+110h+var_170+4]
0x180051aeb  mov     rcx, r14
0x180051aee  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180051af3  lea     rdx, [rbp+110h+var_17C]
0x180051af7  mov     rcx, r14
0x180051afa  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180051aff  lea     rdx, [rbp+110h+var_180]
0x180051b03  mov     rcx, r14
0x180051b06  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180051b0b  mov     word ptr [rbp+110h+length], bx
0x180051b0f  lea     rdx, [rbp+110h+length]
0x180051b13  mov     rcx, r14
0x180051b16  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x180051b1b  movzx   eax, word ptr [rbp+110h+length]
0x180051b1f  mov     dword ptr [rbp+110h+var_150], eax
0x180051b22  mov     word ptr [rbp+110h+length], bx
0x180051b26  lea     rdx, [rbp+110h+length]
0x180051b2a  mov     rcx, r14
0x180051b2d  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x180051b32  movzx   eax, word ptr [rbp+110h+length]
0x180051b36  mov     dword ptr [rbp+110h+var_150+4], eax
0x180051b39  mov     [rbp+110h+length], ebx
0x180051b3c  lea     rdx, [rbp+110h+length]
0x180051b40  mov     rcx, r14
0x180051b43  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180051b48  mov     eax, [rbp+110h+length]
0x180051b4b  mov     dword ptr [rbp+110h+var_150+8], eax
0x180051b4e  lea     rdx, [rbp+110h+var_150+0Ch]
0x180051b52  mov     rcx, r14
0x180051b55  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x180051b5a  lea     rdx, [rbp+110h+var_150+0Eh]
0x180051b5e  mov     rcx, r14
0x180051b61  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x180051b66  lea     rdx, [rbp+110h+var_140]
0x180051b6a  mov     rcx, r14
0x180051b6d  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x180051b72  lea     rdx, [rbp+110h+var_140+8]
0x180051b76  mov     rcx, r14
0x180051b79  call    ??$extractLE@_K@FlexIBuffer@Gryps@@QEAAXAEA_K@Z; Gryps::FlexIBuffer::extractLE<unsigned __int64>(unsigned __int64 &)
0x180051b7e  lea     rdx, [rbp+110h+var_130]
0x180051b82  mov     rcx, r14
0x180051b85  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x180051b8a  lea     rdx, [rbp+110h+var_130+2]
0x180051b8e  mov     rcx, r14
0x180051b91  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x180051b96  mov     byte ptr [rbp+110h+length], bl
0x180051b99  lea     rdx, [rbp+110h+length]
0x180051b9d  mov     rcx, r14
0x180051ba0  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x180051ba5  movzx   eax, byte ptr [rbp+110h+length]
0x180051ba9  mov     dword ptr [rbp+110h+var_130+4], eax
0x180051bac  mov     byte ptr [rbp+110h+length], bl
0x180051baf  lea     rdx, [rbp+110h+length]
0x180051bb3  mov     rcx, r14
0x180051bb6  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x180051bbb  movzx   eax, byte ptr [rbp+110h+length]
0x180051bbf  mov     dword ptr [rbp+110h+var_130+8], eax
0x180051bc2  mov     byte ptr [rbp+110h+length], bl
0x180051bc5  lea     rdx, [rbp+110h+length]
0x180051bc9  mov     rcx, r14
0x180051bcc  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x180051bd1  movzx   eax, byte ptr [rbp+110h+length]
0x180051bd5  mov     dword ptr [rbp+110h+var_130+0Ch], eax
0x180051bd8  mov     byte ptr [rbp+110h+length], bl
0x180051bdb  lea     rdx, [rbp+110h+length]
0x180051bdf  mov     rcx, r14
0x180051be2  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x180051be7  movzx   eax, byte ptr [rbp+110h+length]
0x180051beb  mov     dword ptr [rbp+110h+var_120], eax
0x180051bee  lea     rdx, [rbp+110h+var_120+4]
0x180051bf2  mov     rcx, r14
0x180051bf5  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180051bfa  lea     rdx, [rbp+110h+var_120+8]
0x180051bfe  mov     rcx, r14
0x180051c01  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180051c06  lea     rdx, [rbp+110h+var_120+0Ch]
0x180051c0a  mov     rcx, r14
0x180051c0d  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x180051c12  lea     rdx, [rbp+110h+var_120+0Eh]
0x180051c16  mov     rcx, r14
0x180051c19  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x180051c1e  lea     rdx, [rbp+110h+var_110]
0x180051c22  mov     rcx, r14
0x180051c25  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x180051c2a  mov     byte ptr [rbp+110h+length], bl
0x180051c2d  lea     rdx, [rbp+110h+length]
0x180051c31  mov     rcx, r14
0x180051c34  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x180051c39  mov     esi, ebx
0x180051c3b  cmp     byte ptr [rbp+110h+length], bl
0x180051c3e  setnz   sil
0x180051c42  mov     byte ptr [rbp+110h+length], bl
0x180051c45  lea     rdx, [rbp+110h+length]
0x180051c49  mov     rcx, r14
0x180051c4c  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x180051c51  mov     edi, ebx
0x180051c53  cmp     byte ptr [rbp+110h+length], bl
0x180051c56  setnz   dil
0x180051c5a  lea     rdx, [rbp+110h+var_184]
0x180051c5e  mov     rcx, r14
0x180051c61  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180051c66  mov     [rbp+110h+length], ebx
0x180051c69  xorps   xmm0, xmm0
0x180051c6c  movups  xmmword ptr [rbp+110h+sourceString], xmm0
0x180051c73  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180051c7b  movdqu  [rbp+110h+var_60], xmm1
0x180051c83  mov     word ptr [rbp+110h+sourceString], bx
0x180051c8a  lea     rdx, [rbp+110h+length]
0x180051c8e  mov     rcx, r14
0x180051c91  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180051c96  mov     r8d, [rbp+110h+length]
0x180051c9a  lea     rdx, [rbp+110h+sourceString]
0x180051ca1  mov     rcx, r14
0x180051ca4  call    ?extractUTF16String@FlexIBuffer@Gryps@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K_N@Z; Gryps::FlexIBuffer::extractUTF16String(std::wstring &,unsigned __int64,bool)
0x180051ca9  lea     rcx, [rbp+110h+sourceString]
0x180051cb0  cmp     qword ptr [rbp+110h+var_60+8], 7
0x180051cb8  cmova   rcx, [rbp+110h+sourceString]; sourceString
0x180051cc0  lea     r8, [rbp+110h+string]; string
0x180051cc4  mov     edx, [rbp+110h+length]; length
0x180051cc7  call    cs:__imp_WindowsCreateString
0x180051ccd  lea     rdx, [rbp+110h+var_188]
0x180051cd1  mov     rcx, r14
0x180051cd4  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180051cd9  mov     [rbp+110h+length], ebx
0x180051cdc  xorps   xmm0, xmm0
0x180051cdf  movups  xmmword ptr [rbp+110h+var_90], xmm0
0x180051ce6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180051cee  movdqu  [rbp+110h+var_80], xmm1
0x180051cf6  mov     word ptr [rbp+110h+var_90], bx
0x180051cfd  lea     rdx, [rbp+110h+length]
0x180051d01  mov     rcx, r14
0x180051d04  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180051d09  mov     r8d, [rbp+110h+length]
0x180051d0d  lea     rdx, [rbp+110h+var_90]
0x180051d14  mov     rcx, r14
0x180051d17  call    ?extractUTF16String@FlexIBuffer@Gryps@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K_N@Z; Gryps::FlexIBuffer::extractUTF16String(std::wstring &,unsigned __int64,bool)
0x180051d1c  lea     rcx, [rbp+110h+var_90]
0x180051d23  cmp     qword ptr [rbp+110h+var_80+8], 7
0x180051d2b  cmova   rcx, [rbp+110h+var_90]; sourceString
0x180051d33  lea     r8, [rbp+110h+var_160]; string
0x180051d37  mov     edx, [rbp+110h+length]; length
0x180051d3a  call    cs:__imp_WindowsCreateString
0x180051d40  lea     rdx, [rbp+110h+var_18C]
0x180051d44  mov     rcx, r14
0x180051d47  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180051d4c  xorps   xmm0, xmm0
0x180051d4f  movups  [rbp+110h+var_B0], xmm0
0x180051d53  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180051d5b  movdqu  [rbp+110h+var_A0], xmm1
0x180051d60  mov     byte ptr [rbp+110h+var_B0], bl
0x180051d63  mov     ebx, [rbp+110h+var_18C]
0x180051d66  mov     r8d, ebx
0x180051d69  lea     rdx, [rbp+110h+var_B0]
0x180051d6d  mov     rcx, r14
0x180051d70  call    ?extractString@FlexIBuffer@Gryps@@QEAAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K_N@Z; Gryps::FlexIBuffer::extractString(std::string &,unsigned __int64,bool)
0x180051d75  lea     rcx, [rbp+110h+var_B0]
0x180051d79  cmp     qword ptr [rbp+110h+var_A0+8], 0Fh
0x180051d7e  cmova   rcx, qword ptr [rbp+110h+var_B0]
0x180051d83  mov     r11, [r15+8]
0x180051d87  mov     rdx, [rbp+110h+var_170]
0x180051d8b  movaps  xmm0, [rbp+110h+var_150]
0x180051d8f  movaps  [rbp+110h+var_100], xmm0
0x180051d93  movaps  xmm1, [rbp+110h+var_140]
0x180051d97  movaps  [rbp+110h+var_F0], xmm1
0x180051d9b  movaps  xmm0, [rbp+110h+var_130]
0x180051d9f  movaps  [rbp+110h+var_E0], xmm0
0x180051da3  movaps  xmm1, [rbp+110h+var_120]
0x180051da7  movaps  [rbp+110h+var_D0], xmm1
0x180051dab  movsd   xmm0, [rbp+110h+var_110]
0x180051db0  movsd   [rbp+110h+var_C0], xmm0
0x180051db5  mov     rax, [r11]
0x180051db8  mov     r10, [rax+2B0h]
0x180051dbf  mov     [rsp+220h+var_1A8], rcx
0x180051dc4  mov     [rsp+220h+var_1B0], ebx
0x180051dc8  mov     rax, [rbp+110h+var_160]
0x180051dcc  mov     [rsp+220h+var_1B8], rax
0x180051dd1  mov     eax, [rbp+110h+var_188]
0x180051dd4  mov     [rsp+220h+var_1C0], eax
0x180051dd8  mov     rax, [rbp+110h+string]
0x180051ddc  mov     [rsp+220h+var_1C8], rax
0x180051de1  mov     r8d, [rbp+110h+var_184]
0x180051de5  mov     [rsp+220h+var_1D0], r8d
0x180051dea  mov     [rsp+220h+var_1D8], edi
0x180051dee  mov     [rsp+220h+var_1E0], esi
0x180051df2  lea     rax, [rbp+110h+var_100]
0x180051df6  mov     [rsp+220h+var_1E8], rax
0x180051dfb  mov     r8d, [rbp+110h+var_180]
0x180051dff  mov     [rsp+220h+var_1F0], r8d
0x180051e04  mov     r8d, [rbp+110h+var_17C]
0x180051e08  mov     dword ptr [rsp+220h+var_1F8], r8d
0x180051e0d  mov     [rsp+220h+var_200], rdx
0x180051e12  mov     r9, [rbp+110h+var_168]
0x180051e16  mov     r8d, [rbp+110h+var_178]
0x180051e1a  mov     edx, [rbp+110h+var_174]
0x180051e1d  mov     rcx, r11
0x180051e20  mov     rax, r10
0x180051e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e28  nop
0x180051e29  lea     rcx, [rbp+110h+var_B0]
0x180051e2d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180051e32  nop
0x180051e33  lea     rcx, [rbp+110h+var_90]
0x180051e3a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180051e3f  nop
0x180051e40  lea     rcx, [rbp+110h+sourceString]
0x180051e47  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180051e4c  xor     eax, eax
0x180051e4e  mov     rcx, [rbp+110h+var_30]
0x180051e55  xor     rcx, rsp; StackCookie
0x180051e58  call    __security_check_cookie
0x180051e5d  mov     rbx, [rsp+220h+arg_10]
0x180051e65  add     rsp, 200h
0x180051e6c  pop     r15
0x180051e6e  pop     r14
0x180051e70  pop     rdi
0x180051e71  pop     rsi
0x180051e72  pop     rbp
0x180051e73  retn
```
