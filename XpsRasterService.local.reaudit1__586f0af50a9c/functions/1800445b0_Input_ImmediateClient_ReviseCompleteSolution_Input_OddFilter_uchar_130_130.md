# Input::ImmediateClient::ReviseCompleteSolution(Input::OddFilter<uchar,130,130> &)

- ea: `0x1800445b0`
- end: `0x180044844`
- name: `?ReviseCompleteSolution@ImmediateClient@Input@@QEAAAEAV?$OddFilter@C$0IA@$0IA@@2@AEAV?$OddFilter@E$0IC@$0IC@@2@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180041e90`

## callees

- `0x180003180`
- `0x180007b70`
- `0x18000e4b0`
- `0x1800445b0`
- `0x180085ff0`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__controlfp_s` at `0x1800447d8`
- `api-ms-win-crt-private-l1-1-0!_o__controlfp_s` at `0x1800447d8`

## pseudocode

```c
__int64 __fastcall Input::ImmediateClient::ReviseCompleteSolution(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 v3; // r8
  const unsigned int near *const *v4; // r11
  int v5; // r10d
  unsigned int i; // r9d
  unsigned int v7; // ecx
  __int64 v8; // r8
  __int64 v9; // rcx
  int v10; // edi
  unsigned int v11; // ebx
  int v12; // eax
  void (__fastcall *MixedProvider)(__int64 (__fastcall *)(), unsigned __int64, __int64); // rax
  int v15; // [rsp+20h] [rbp-69h] BYREF
  __int64 v16; // [rsp+28h] [rbp-61h] BYREF
  __int64 v17; // [rsp+30h] [rbp-59h] BYREF
  _DWORD v18[16]; // [rsp+40h] [rbp-49h] BYREF
  _DWORD v19[16]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE *retaddr; // [rsp+E8h] [rbp+5Fh]

  v2 = a1 + 8;
  Input::ImmediateClient::HandleGlobalCategory(a1, a2, a1 + 8);
  if ( (IntegralRelation::OddMap ^ 0xFB64C5DA) != 0xA1A989
    || *retaddr == (unsigned __int8)((IntegralRelation::OddMap ^ 0x9BD85343) / 0x789D2C) )
  {
    v4 = &ScatteredInformation::PaintShortTermException;
    v5 = ScatteredInformation::StripedSeries ^ 0x157E9386;
    for ( i = 0; i < 0x1E; i += 2 )
    {
      v7 = *((_DWORD *)v4++ + 1);
      v8 = (unsigned __int8)((v5 ^ v7) / 0x9D28AF) - i - 1;
      v9 = (unsigned __int8)(((unsigned int)v5 ^ *((_DWORD *)v4 - 2)) / 0x9D28AF) - i;
      *((_QWORD *)&ScatteredInformation::StripedSeries + v9 + 1) = *((_QWORD *)&ScatteredInformation::StripedSeries
                                                                   + v8
                                                                   + 1);
    }
    v15 = 0;
    v16 = 0x2F5FFFFF008080D0LL;
    v18[0] = 923746055;
    v10 = ScatteredInformation::StripedSeries ^ 0x157E9386;
    v17 = 0xEF8F2FCFF09060B0uLL;
    IntegralRelation::OddMap = ScatteredInformation::StripedSeries ^ 0x157E9386;
    v18[1] = 656355095;
    v18[2] = 906903046;
    v18[3] = 639512086;
    v18[4] = 890060037;
    v18[5] = 622669077;
    v18[6] = 873217028;
    v18[7] = 605826068;
    v18[8] = 856374019;
    v18[9] = 588983059;
    v18[10] = 839531010;
    v18[11] = 572140050;
    v18[12] = 822688001;
    v18[13] = 555297041;
    v18[14] = 805844992;
    v18[15] = 538454032;
    v19[0] = 923746055;
    v19[1] = 656355095;
    v19[2] = 906903046;
    v19[3] = 639512086;
    v19[4] = 890060037;
    v19[5] = 622669077;
    v19[6] = 873217028;
    v19[7] = 605826068;
    v19[8] = 856374019;
    v19[9] = 588983059;
    v19[10] = 839531010;
    v19[11] = 572140050;
    v19[12] = 822688001;
    v19[13] = 555297041;
    v19[14] = 805844992;
    v19[15] = 538454032;
    v11 = ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
            (__int64)&ScatteredInformation::StripedSeries,
            &v16,
            (__int64)v18)
        ^ 0xAAAAAAAA;
    v12 = ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
            (__int64)&ScatteredInformation::StripedSeries,
            &v17,
            (__int64)v19);
    _o__controlfp_s(&v15, (v12 ^ 0xAAAAAAAA) - v10, v11);
  }
  MixedProvider = (void (__fastcall *)(__int64 (__fastcall *)(), unsigned __int64, __int64))GenerateMixedProvider(
                                                                                              0xFF4FDF1FE0904030uLL,
                                                                                              301211850,
                                                                                              v3);
  MixedProvider(
    Input::ImmediateClient::ReviseCompleteSolution,
    (unsigned __int64)Input::ImmediateClient::ReviseCompleteSolution ^ 0x2E275B,
    1976139);
  return v2;
}

```

## disassembly

```asm
0x1800445b0  push    rbp
0x1800445b2  push    rsi
0x1800445b3  lea     rbp, [rsp-4Fh]
0x1800445b8  sub     rsp, 0D8h
0x1800445bf  mov     rax, cs:__security_cookie
0x1800445c6  xor     rax, rsp
0x1800445c9  mov     [rbp+57h+var_20], rax
0x1800445cd  lea     rsi, [rcx+8]
0x1800445d1  mov     r8, rsi
0x1800445d4  call    ?HandleGlobalCategory@ImmediateClient@Input@@AEAAXAEAV?$OddFilter@E$0IC@$0IC@@2@AEAV?$OddFilter@C$0IA@$0IA@@2@@Z; Input::ImmediateClient::HandleGlobalCategory(Input::OddFilter<uchar,130,130> &,Input::OddFilter<signed char,128,128> &)
0x1800445d9  mov     ecx, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x1800445df  mov     eax, ecx
0x1800445e1  xor     eax, 0FB64C5DAh
0x1800445e6  cmp     eax, 0A1A989h
0x1800445eb  jnz     short loc_180044609
0x1800445ed  xor     ecx, 9BD85343h
0x1800445f3  mov     eax, 87D69DFh
0x1800445f8  mul     ecx
0x1800445fa  mov     rax, [rbp+5Fh]
0x1800445fe  shr     edx, 12h
0x180044601  cmp     [rax], dl
0x180044603  jnz     loc_1800447F6
0x180044609  mov     r10d, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180044610  lea     r11, ?PaintShortTermException@ScatteredInformation@@2QBIB; uint const near * const ScatteredInformation::PaintShortTermException
0x180044617  mov     [rsp+0E0h+arg_10], rbx
0x18004461f  xor     r10d, 157E9386h
0x180044626  mov     [rsp+0E0h+arg_18], rdi
0x18004462e  xor     r9d, r9d
0x180044631  mov     [rsp+0E0h+var_10], r14
0x180044639  lea     r14, ?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180044640  mov     ecx, [r11+4]
0x180044644  lea     r11, [r11+8]
0x180044648  xor     ecx, r10d
0x18004464b  mov     eax, 68404C21h
0x180044650  mul     ecx
0x180044652  mov     ecx, [r11-8]
0x180044656  mov     eax, 68404C21h
0x18004465b  xor     ecx, r10d
0x18004465e  shr     edx, 16h
0x180044661  movzx   r8d, dl
0x180044665  mul     ecx
0x180044667  sub     r8d, r9d
0x18004466a  shr     edx, 16h
0x18004466d  dec     r8d
0x180044670  movzx   ecx, dl
0x180044673  sub     ecx, r9d
0x180044676  add     r9d, 2
0x18004467a  mov     rax, [r14+r8*8+8]
0x18004467f  mov     [r14+rcx*8+8], rax
0x180044684  cmp     r9d, 1Eh
0x180044688  jb      short loc_180044640
0x18004468a  mov     edi, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180044690  lea     r8, [rbp+57h+var_A0]
0x180044694  mov     rax, 2F5FFFFF008080D0h
0x18004469e  mov     [rbp+57h+var_C0], 0
0x1800446a5  mov     [rbp+57h+var_B8], rax
0x1800446a9  lea     rdx, [rbp+57h+var_B8]
0x1800446ad  mov     rax, 0EF8F2FCFF09060B0h
0x1800446b7  mov     [rbp+57h+var_A0], 370F3F07h
0x1800446be  xor     edi, 157E9386h
0x1800446c4  mov     [rbp+57h+var_B0], rax
0x1800446c8  mov     rcx, r14
0x1800446cb  mov     cs:?OddMap@IntegralRelation@@2IA, edi; uint IntegralRelation::OddMap
0x1800446d1  mov     [rbp+57h+var_9C], 271F2F17h
0x1800446d8  mov     [rbp+57h+var_98], 360E3E06h
0x1800446df  mov     [rbp+57h+var_94], 261E2E16h
0x1800446e6  mov     [rbp+57h+var_90], 350D3D05h
0x1800446ed  mov     [rbp+57h+var_8C], 251D2D15h
0x1800446f4  mov     [rbp+57h+var_88], 340C3C04h
0x1800446fb  mov     [rbp+57h+var_84], 241C2C14h
0x180044702  mov     [rbp+57h+var_80], 330B3B03h
0x180044709  mov     [rbp+57h+var_7C], 231B2B13h
0x180044710  mov     [rbp+57h+var_78], 320A3A02h
0x180044717  mov     [rbp+57h+var_74], 221A2A12h
0x18004471e  mov     [rbp+57h+var_70], 31093901h
0x180044725  mov     [rbp+57h+var_6C], 21192911h
0x18004472c  mov     [rbp+57h+var_68], 30083800h
0x180044733  mov     [rbp+57h+var_64], 20182810h
0x18004473a  mov     [rbp+57h+var_60], 370F3F07h
0x180044741  mov     [rbp+57h+var_5C], 271F2F17h
0x180044748  mov     [rbp+57h+var_58], 360E3E06h
0x18004474f  mov     [rbp+57h+var_54], 261E2E16h
0x180044756  mov     [rbp+57h+var_50], 350D3D05h
0x18004475d  mov     [rbp+57h+var_4C], 251D2D15h
0x180044764  mov     [rbp+57h+var_48], 340C3C04h
0x18004476b  mov     [rbp+57h+var_44], 241C2C14h
0x180044772  mov     [rbp+57h+var_40], 330B3B03h
0x180044779  mov     [rbp+57h+var_3C], 231B2B13h
0x180044780  mov     [rbp+57h+var_38], 320A3A02h
0x180044787  mov     [rbp+57h+var_34], 221A2A12h
0x18004478e  mov     [rbp+57h+var_30], 31093901h
0x180044795  mov     [rbp+57h+var_2C], 21192911h
0x18004479c  mov     [rbp+57h+var_28], 30083800h
0x1800447a3  mov     [rbp+57h+var_24], 20182810h
0x1800447aa  call    ??$WriteConstructStrategy@_K$0EA@@ScatteredInformation@@AEBA_KAEB_KAEAY0EA@$$CBE@Z; ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(unsigned __int64 const &,uchar const (&)[64])
0x1800447af  mov     rbx, rax
0x1800447b2  lea     r8, [rbp+57h+var_60]
0x1800447b6  lea     rdx, [rbp+57h+var_B0]
0x1800447ba  mov     rcx, r14
0x1800447bd  xor     ebx, 0AAAAAAAAh
0x1800447c3  call    ??$WriteConstructStrategy@_K$0EA@@ScatteredInformation@@AEBA_KAEB_KAEAY0EA@$$CBE@Z; ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(unsigned __int64 const &,uchar const (&)[64])
0x1800447c8  xor     eax, 0AAAAAAAAh
0x1800447cd  lea     rcx, [rbp+57h+var_C0]
0x1800447d1  sub     eax, edi
0x1800447d3  mov     r8d, ebx
0x1800447d6  mov     edx, eax
0x1800447d8  call    cs:__imp__o__controlfp_s
0x1800447de  mov     r14, [rsp+0E0h+var_10]
0x1800447e6  mov     rdi, [rsp+0E0h+arg_18]
0x1800447ee  mov     rbx, [rsp+0E0h+arg_10]
0x1800447f6  mov     edx, 11F420CAh
0x1800447fb  mov     rcx, 0FF4FDF1FE0904030h
0x180044805  call    GenerateMixedProvider
0x18004480a  lea     rdx, ?ReviseCompleteSolution@ImmediateClient@Input@@QEAAAEAV?$OddFilter@C$0IA@$0IA@@2@AEAV?$OddFilter@E$0IC@$0IC@@2@@Z; Input::ImmediateClient::ReviseCompleteSolution(Input::OddFilter<uchar,130,130> &)
0x180044811  mov     r8d, 1E274Bh
0x180044817  xor     rdx, 2E275Bh
0x18004481e  lea     rcx, ?ReviseCompleteSolution@ImmediateClient@Input@@QEAAAEAV?$OddFilter@C$0IA@$0IA@@2@AEAV?$OddFilter@E$0IC@$0IC@@2@@Z; Input::ImmediateClient::ReviseCompleteSolution(Input::OddFilter<uchar,130,130> &)
0x180044825  call    cs:__guard_dispatch_icall_fptr
0x18004482b  mov     rax, rsi
0x18004482e  mov     rcx, [rbp+57h+var_20]
0x180044832  xor     rcx, rsp; StackCookie
0x180044835  call    __security_check_cookie
0x18004483a  add     rsp, 0D8h
0x180044841  pop     rsi
0x180044842  pop     rbp
0x180044843  retn
```
