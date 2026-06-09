# SDK::LogicalFunction::LinkSlowAPI(int,int,IWICBitmap *)

- ea: `0x180011b20`
- end: `0x180011efa`
- name: `?LinkSlowAPI@LogicalFunction@SDK@@UEAAJHHPEAUIWICBitmap@@@Z`
- size: `986`
- prototype: `int(SDK::LogicalFunction *__hidden this, int, int, struct IWICBitmap *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003180`
- `0x180007b70`
- `0x18000e4b0`
- `0x180011b20`
- `0x18003fc70`
- `0x180050270`
- `0x1800502e0`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__controlfp_s` at `0x180011d69`
- `api-ms-win-crt-private-l1-1-0!_o__controlfp_s` at `0x180011d69`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SDK::LogicalFunction::LinkSlowAPI(
        SDK::LogicalFunction *this,
        unsigned int a2,
        __int64 a3,
        struct IWICBitmap *a4)
{
  unsigned int v5; // r15d
  int v8; // edx
  int v9; // r11d
  unsigned int v10; // r10d
  const unsigned int near *const *v11; // r9
  int v12; // edi
  unsigned int v13; // ebx
  int v14; // eax
  __int64 (__fastcall *MixedProvider)(char *, _QWORD, _QWORD, struct IWICBitmap *); // rax
  int v17; // eax
  unsigned int v18; // edi
  unsigned int v19; // ebx
  __int64 v20; // r8
  __int64 (__fastcall *v21)(SDK::LogicalFunction *, _QWORD, _QWORD, struct IWICBitmap *); // rax
  int v22; // r10d
  const unsigned int near *const *v23; // r9
  __int64 v24; // r8
  void (__fastcall *v25)(_QWORD, __int64); // rax
  int v26; // [rsp+30h] [rbp-99h] BYREF
  __int64 v27; // [rsp+38h] [rbp-91h] BYREF
  __int64 v28; // [rsp+40h] [rbp-89h] BYREF
  _DWORD v29[16]; // [rsp+50h] [rbp-79h] BYREF
  _DWORD v30[16]; // [rsp+90h] [rbp-39h] BYREF
  _BYTE *retaddr; // [rsp+128h] [rbp+5Fh]

  v5 = a3;
  if ( a4 )
  {
    MixedProvider = (__int64 (__fastcall *)(char *, _QWORD, _QWORD, struct IWICBitmap *))GenerateMixedProvider(
                                                                                           0xFF9F1F7F6000A0E0uLL,
                                                                                           287629482,
                                                                                           a3);
    v17 = MixedProvider((char *)this + 28, a2, v5, a4);
    v18 = v17;
    v19 = 0;
    if ( v17 >= 0 )
    {
      if ( v17 == 1 || SDK::LowAPI::DeriveAsyncRecommendation((SDK::LogicalFunction *)((char *)this + 28), a2, v5, a4) )
      {
        v18 = 0;
      }
      else
      {
        PureSelection::PureSelection((PureSelection *)&v26);
        v21 = (__int64 (__fastcall *)(SDK::LogicalFunction *, _QWORD, _QWORD, struct IWICBitmap *))GenerateMixedProvider(
                                                                                                     0x9F9F5FFFA020E090uLL,
                                                                                                     1898225706,
                                                                                                     v20);
        v18 = v21(this, a2, v5, a4);
        PureSelection::~PureSelection((PureSelection *)&v26);
      }
    }
    if ( (IntegralRelation::OddMap ^ 0xFBF847F1) != 0x3D2BA2
      || *retaddr == (unsigned __int8)((IntegralRelation::OddMap ^ 0xDB183443) / 0x293DEC) )
    {
      v22 = ScatteredInformation::StripedSeries ^ 0x157E9386;
      v23 = &ScatteredInformation::PaintShortTermException;
      do
      {
        v24 = (unsigned __int8)(((unsigned int)v22 ^ *((_DWORD *)v23 + 1)) / 0x9D28AF) - v19 - 1;
        *((_QWORD *)&ScatteredInformation::StripedSeries
        + (unsigned __int8)((*(_DWORD *)v23 ^ (unsigned int)v22) / 0x9D28AF)
        - v19
        + 1) = *((_QWORD *)&ScatteredInformation::StripedSeries + v24 + 1);
        v19 += 2;
        ++v23;
      }
      while ( v19 < 0x1E );
      IntegralRelation::OddMap = ScatteredInformation::StripedSeries ^ 0x157E9386;
      v25 = (void (__fastcall *)(_QWORD, __int64))GenerateMixedProvider(0xDFFF9F3F2040C010uLL, 826564842, v24);
      v25(0, 104);
    }
    return v18;
  }
  else
  {
    v8 = (unsigned __int8)*retaddr;
    if ( (float)(4145176 * v8) > 842945860.0 && (float)(2309164 * v8) < 473026460.0
      || (IntegralRelation::OddMap ^ 0xFB8E9588) != 0x4BF9DB )
    {
      v9 = ScatteredInformation::StripedSeries ^ 0x157E9386;
      v10 = 0;
      v11 = &ScatteredInformation::PaintShortTermException;
      do
      {
        *((_QWORD *)&ScatteredInformation::StripedSeries
        + (unsigned __int8)((*(_DWORD *)v11 ^ (unsigned int)v9) / 0x9D28AF)
        - v10
        + 1) = *((_QWORD *)&ScatteredInformation::StripedSeries
               + (unsigned __int8)(((unsigned int)v9 ^ *((_DWORD *)v11 + 1)) / 0x9D28AF)
               - v10);
        v10 += 2;
        ++v11;
      }
      while ( v10 < 0x1E );
      v12 = ScatteredInformation::StripedSeries ^ 0x157E9386;
      IntegralRelation::OddMap = ScatteredInformation::StripedSeries ^ 0x157E9386;
      v26 = 0;
      v27 = 0x2F5FFFFF008080D0LL;
      v29[0] = 923746055;
      v29[1] = 656355095;
      v29[2] = 906903046;
      v29[3] = 639512086;
      v29[4] = 890060037;
      v29[5] = 622669077;
      v29[6] = 873217028;
      v29[7] = 605826068;
      v29[8] = 856374019;
      v29[9] = 588983059;
      v29[10] = 839531010;
      v29[11] = 572140050;
      v29[12] = 822688001;
      v29[13] = 555297041;
      v29[14] = 805844992;
      v29[15] = 538454032;
      v28 = 0xEF8F2FCFF09060B0uLL;
      v30[0] = 923746055;
      v30[1] = 656355095;
      v30[2] = 906903046;
      v30[3] = 639512086;
      v30[4] = 890060037;
      v30[5] = 622669077;
      v30[6] = 873217028;
      v30[7] = 605826068;
      v30[8] = 856374019;
      v30[9] = 588983059;
      v30[10] = 839531010;
      v30[11] = 572140050;
      v30[12] = 822688001;
      v30[13] = 555297041;
      v30[14] = 805844992;
      v30[15] = 538454032;
      v13 = ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
              (__int64)&ScatteredInformation::StripedSeries,
              &v27,
              (__int64)v29)
          ^ 0xAAAAAAAA;
      v14 = ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
              (__int64)&ScatteredInformation::StripedSeries,
              &v28,
              (__int64)v30);
      _o__controlfp_s(&v26, (v14 ^ 0xAAAAAAAA) - v12, v13);
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180011b20  push    rbp
0x180011b22  push    rbx
0x180011b23  push    rsi
0x180011b24  push    rdi
0x180011b25  push    r12
0x180011b27  push    r13
0x180011b29  push    r14
0x180011b2b  push    r15
0x180011b2d  lea     rbp, [rsp-1Fh]
0x180011b32  sub     rsp, 0E8h
0x180011b39  mov     rax, cs:__security_cookie
0x180011b40  xor     rax, rsp
0x180011b43  mov     [rbp+57h+var_50], rax
0x180011b47  mov     rsi, r9
0x180011b4a  mov     r15d, r8d
0x180011b4d  mov     r14d, edx
0x180011b50  mov     r13, rcx
0x180011b53  test    r9, r9
0x180011b56  jnz     loc_180011D79
0x180011b5c  mov     rax, [rbp+5Fh]
0x180011b60  movzx   edx, byte ptr [rax]
0x180011b63  imul    ecx, edx, 3F4018h
0x180011b69  xorps   xmm0, xmm0
0x180011b6c  cvtsi2ss xmm0, rcx
0x180011b71  comiss  xmm0, cs:__real@4e48f955
0x180011b78  jbe     short loc_180011B95
0x180011b7a  imul    ecx, edx, 233C2Ch
0x180011b80  xorps   xmm1, xmm1
0x180011b83  cvtsi2ss xmm1, rcx
0x180011b88  movss   xmm0, cs:__real@4de18e7d
0x180011b90  comiss  xmm0, xmm1
0x180011b93  ja      short loc_180011BAB
0x180011b95  mov     eax, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x180011b9b  xor     eax, 0FB8E9588h
0x180011ba0  cmp     eax, 4BF9DBh
0x180011ba5  jz      loc_180011D6F
0x180011bab  mov     r11d, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180011bb2  xor     r11d, 157E9386h
0x180011bb9  xor     ebx, ebx
0x180011bbb  mov     r10d, ebx
0x180011bbe  lea     r9, ?PaintShortTermException@ScatteredInformation@@2QBIB; uint const near * const ScatteredInformation::PaintShortTermException
0x180011bc5  lea     rsi, ?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180011bcc  nop     dword ptr [rax+00h]
0x180011bd0  mov     ecx, [r9+4]
0x180011bd4  xor     ecx, r11d
0x180011bd7  mov     eax, 68404C21h
0x180011bdc  mul     ecx
0x180011bde  shr     edx, 16h
0x180011be1  movzx   r8d, dl
0x180011be5  sub     r8d, r10d
0x180011be8  dec     r8d
0x180011beb  mov     ecx, r11d
0x180011bee  xor     ecx, [r9]
0x180011bf1  mov     eax, 68404C21h
0x180011bf6  mul     ecx
0x180011bf8  shr     edx, 16h
0x180011bfb  movzx   ecx, dl
0x180011bfe  sub     ecx, r10d
0x180011c01  mov     rax, [rsi+r8*8+8]
0x180011c06  mov     [rsi+rcx*8+8], rax
0x180011c0b  add     r10d, 2
0x180011c0f  lea     r9, [r9+8]
0x180011c13  cmp     r10d, 1Eh
0x180011c17  jb      short loc_180011BD0
0x180011c19  mov     edi, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180011c1f  xor     edi, 157E9386h
0x180011c25  mov     cs:?OddMap@IntegralRelation@@2IA, edi; uint IntegralRelation::OddMap
0x180011c2b  mov     [rsp+120h+var_F0], ebx
0x180011c2f  mov     rax, 2F5FFFFF008080D0h
0x180011c39  mov     [rsp+120h+var_E8], rax
0x180011c3e  mov     [rbp+57h+var_D0], 370F3F07h
0x180011c45  mov     [rbp+57h+var_CC], 271F2F17h
0x180011c4c  mov     [rbp+57h+var_C8], 360E3E06h
0x180011c53  mov     [rbp+57h+var_C4], 261E2E16h
0x180011c5a  mov     [rbp+57h+var_C0], 350D3D05h
0x180011c61  mov     [rbp+57h+var_BC], 251D2D15h
0x180011c68  mov     [rbp+57h+var_B8], 340C3C04h
0x180011c6f  mov     [rbp+57h+var_B4], 241C2C14h
0x180011c76  mov     [rbp+57h+var_B0], 330B3B03h
0x180011c7d  mov     [rbp+57h+var_AC], 231B2B13h
0x180011c84  mov     [rbp+57h+var_A8], 320A3A02h
0x180011c8b  mov     [rbp+57h+var_A4], 221A2A12h
0x180011c92  mov     [rbp+57h+var_A0], 31093901h
0x180011c99  mov     [rbp+57h+var_9C], 21192911h
0x180011ca0  mov     [rbp+57h+var_98], 30083800h
0x180011ca7  mov     [rbp+57h+var_94], 20182810h
0x180011cae  mov     rax, 0EF8F2FCFF09060B0h
0x180011cb8  mov     [rsp+120h+var_E0], rax
0x180011cbd  mov     [rbp+57h+var_90], 370F3F07h
0x180011cc4  mov     [rbp+57h+var_8C], 271F2F17h
0x180011ccb  mov     [rbp+57h+var_88], 360E3E06h
0x180011cd2  mov     [rbp+57h+var_84], 261E2E16h
0x180011cd9  mov     [rbp+57h+var_80], 350D3D05h
0x180011ce0  mov     [rbp+57h+var_7C], 251D2D15h
0x180011ce7  mov     [rbp+57h+var_78], 340C3C04h
0x180011cee  mov     [rbp+57h+var_74], 241C2C14h
0x180011cf5  mov     [rbp+57h+var_70], 330B3B03h
0x180011cfc  mov     [rbp+57h+var_6C], 231B2B13h
0x180011d03  mov     [rbp+57h+var_68], 320A3A02h
0x180011d0a  mov     [rbp+57h+var_64], 221A2A12h
0x180011d11  mov     [rbp+57h+var_60], 31093901h
0x180011d18  mov     [rbp+57h+var_5C], 21192911h
0x180011d1f  mov     [rbp+57h+var_58], 30083800h
0x180011d26  mov     [rbp+57h+var_54], 20182810h
0x180011d2d  lea     r8, [rbp+57h+var_D0]
0x180011d31  lea     rdx, [rsp+120h+var_E8]
0x180011d36  mov     rcx, rsi
0x180011d39  call    ??$WriteConstructStrategy@_K$0EA@@ScatteredInformation@@AEBA_KAEB_KAEAY0EA@$$CBE@Z; ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(unsigned __int64 const &,uchar const (&)[64])
0x180011d3e  mov     rbx, rax
0x180011d41  xor     ebx, 0AAAAAAAAh
0x180011d47  lea     r8, [rbp+57h+var_90]
0x180011d4b  lea     rdx, [rsp+120h+var_E0]
0x180011d50  mov     rcx, rsi
0x180011d53  call    ??$WriteConstructStrategy@_K$0EA@@ScatteredInformation@@AEBA_KAEB_KAEAY0EA@$$CBE@Z; ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(unsigned __int64 const &,uchar const (&)[64])
0x180011d58  xor     eax, 0AAAAAAAAh
0x180011d5d  sub     eax, edi
0x180011d5f  mov     r8d, ebx
0x180011d62  mov     edx, eax
0x180011d64  lea     rcx, [rsp+120h+var_F0]
0x180011d69  call    cs:__imp__o__controlfp_s
0x180011d6f  mov     eax, 80004005h
0x180011d74  jmp     loc_180011EDA
0x180011d79  mov     edx, 1124E0AAh
0x180011d7e  mov     rcx, 0FF9F1F7F6000A0E0h
0x180011d88  call    GenerateMixedProvider
0x180011d8d  mov     r9, rsi
0x180011d90  mov     r8d, r15d
0x180011d93  mov     edx, r14d
0x180011d96  lea     rcx, [r13+1Ch]
0x180011d9a  call    cs:__guard_dispatch_icall_fptr
0x180011da0  mov     edi, eax
0x180011da2  xor     ebx, ebx
0x180011da4  test    eax, eax
0x180011da6  js      short loc_180011E04
0x180011da8  cmp     eax, 1
0x180011dab  jz      short loc_180011E02
0x180011dad  mov     r9, rsi; struct IWICBitmap *
0x180011db0  mov     r8d, r15d; int
0x180011db3  mov     edx, r14d; int
0x180011db6  lea     rcx, [r13+1Ch]; this
0x180011dba  call    ?DeriveAsyncRecommendation@LowAPI@SDK@@QEAA_NHHPEAUIWICBitmap@@@Z; SDK::LowAPI::DeriveAsyncRecommendation(int,int,IWICBitmap *)
0x180011dbf  test    al, al
0x180011dc1  jnz     short loc_180011E02
0x180011dc3  lea     rcx, [rsp+120h+var_F0]; this
0x180011dc8  call    ??0PureSelection@@QEAA@XZ; PureSelection::PureSelection(void)
0x180011dcd  nop
0x180011dce  mov     edx, 7124A02Ah
0x180011dd3  mov     rcx, 9F9F5FFFA020E090h
0x180011ddd  call    GenerateMixedProvider
0x180011de2  mov     r9, rsi
0x180011de5  mov     r8d, r15d
0x180011de8  mov     edx, r14d
0x180011deb  mov     rcx, r13
0x180011dee  call    cs:__guard_dispatch_icall_fptr
0x180011df4  mov     edi, eax
0x180011df6  lea     rcx, [rsp+120h+var_F0]; this
0x180011dfb  call    ??1PureSelection@@QEAA@XZ; PureSelection::~PureSelection(void)
0x180011e00  jmp     short loc_180011E04
0x180011e02  mov     edi, ebx
0x180011e04  mov     ecx, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x180011e0a  mov     eax, ecx
0x180011e0c  xor     eax, 0FBF847F1h
0x180011e11  cmp     eax, 3D2BA2h
0x180011e16  jnz     short loc_180011E3A
0x180011e18  xor     ecx, 0DB183443h
0x180011e1e  mov     eax, 8D441C5Bh
0x180011e23  mul     ecx
0x180011e25  sub     ecx, edx
0x180011e27  shr     ecx, 1
0x180011e29  add     ecx, edx
0x180011e2b  shr     ecx, 15h
0x180011e2e  mov     rax, [rbp+5Fh]
0x180011e32  cmp     [rax], cl
0x180011e34  jnz     loc_180011ED8
0x180011e3a  mov     r10d, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180011e41  xor     r10d, 157E9386h
0x180011e48  lea     r9, ?PaintShortTermException@ScatteredInformation@@2QBIB; uint const near * const ScatteredInformation::PaintShortTermException
0x180011e4f  lea     rsi, ?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180011e56  nop     word ptr [rax+rax+00000000h]
0x180011e60  mov     ecx, [r9+4]
0x180011e64  xor     ecx, r10d
0x180011e67  mov     eax, 68404C21h
0x180011e6c  mul     ecx
0x180011e6e  shr     edx, 16h
0x180011e71  movzx   r8d, dl
0x180011e75  sub     r8d, ebx
0x180011e78  dec     r8d
0x180011e7b  mov     ecx, r10d
0x180011e7e  xor     ecx, [r9]
0x180011e81  mov     eax, 68404C21h
0x180011e86  mul     ecx
0x180011e88  shr     edx, 16h
0x180011e8b  movzx   ecx, dl
0x180011e8e  sub     ecx, ebx
0x180011e90  mov     rax, [rsi+r8*8+8]
0x180011e95  mov     [rsi+rcx*8+8], rax
0x180011e9a  add     ebx, 2
0x180011e9d  lea     r9, [r9+8]
0x180011ea1  cmp     ebx, 1Eh
0x180011ea4  jb      short loc_180011E60
0x180011ea6  mov     eax, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180011eac  xor     eax, 157E9386h
0x180011eb1  mov     cs:?OddMap@IntegralRelation@@2IA, eax; uint IntegralRelation::OddMap
0x180011eb7  mov     edx, 314460EAh
0x180011ebc  mov     rcx, 0DFFF9F3F2040C010h
0x180011ec6  call    GenerateMixedProvider
0x180011ecb  mov     edx, 68h ; 'h'
0x180011ed0  xor     ecx, ecx
0x180011ed2  call    cs:__guard_dispatch_icall_fptr
0x180011ed8  mov     eax, edi
0x180011eda  mov     rcx, [rbp+57h+var_50]
0x180011ede  xor     rcx, rsp; StackCookie
0x180011ee1  call    __security_check_cookie
0x180011ee6  add     rsp, 0E8h
0x180011eed  pop     r15
0x180011eef  pop     r14
0x180011ef1  pop     r13
0x180011ef3  pop     r12
0x180011ef5  pop     rdi
0x180011ef6  pop     rsi
0x180011ef7  pop     rbx
0x180011ef8  pop     rbp
0x180011ef9  retn
```
