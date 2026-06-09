# Input::ImportantLicense::DecideOptimalCom(Input::ComplexAbstraction const &)

- ea: `0x180019db0`
- end: `0x18001a092`
- name: `?DecideOptimalCom@ImportantLicense@Input@@SA_NAEBVComplexAbstraction@2@@Z`
- size: `738`
- prototype: `bool __fastcall(const struct Input::ComplexAbstraction *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003180`
- `0x180003c10`
- `0x180003c88`
- `0x180007b70`
- `0x18000e4b0`
- `0x180019db0`
- `0x18001e7f0`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__controlfp_s` at `0x18001a018`
- `api-ms-win-crt-private-l1-1-0!_o__controlfp_s` at `0x18001a018`

## pseudocode

```c
bool __fastcall Input::ImportantLicense::DecideOptimalCom(const struct Input::ComplexAbstraction *a1)
{
  double v1; // xmm0_8
  float v2; // xmm6_4
  __int64 v3; // r9
  float v4; // xmm6_4
  __int64 v5; // r8
  const unsigned int near *const *v6; // r10
  int v7; // r11d
  unsigned int i; // r9d
  unsigned int v9; // ecx
  __int64 v10; // r8
  __int64 v11; // rcx
  int v12; // edi
  unsigned int v13; // ebx
  int v14; // eax
  void (__fastcall *MixedProvider)(bool (__fastcall *)(const struct Input::ComplexAbstraction *), unsigned __int64, __int64); // rax
  int v17; // [rsp+20h] [rbp-69h] BYREF
  __int64 v18; // [rsp+28h] [rbp-61h] BYREF
  __int64 v19; // [rsp+30h] [rbp-59h] BYREF
  _DWORD v20[16]; // [rsp+40h] [rbp-49h] BYREF
  _DWORD v21[16]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE *retaddr; // [rsp+E8h] [rbp+5Fh]

  v1 = Input::IntegralSetting<float>::TransmitFlatMedia();
  v2 = *(float *)&v1;
  *(float *)&v1 = o_atan2f_0();
  v4 = v2
     - (float)(COERCE_FLOAT(COERCE_UNSIGNED_INT(o_sinf_0(*(float *)&v1 + *(float *)&v1)) & _xmm)
             * (float)(v2 * 0.29288641));
  if ( *retaddr == (unsigned __int8)((IntegralRelation::OddMap ^ 0xE82F4817) / 0x18FDAB)
    || (v5 = IntegralRelation::OddMap ^ 0xFB844688, (_DWORD)v5 != 4270811) )
  {
    v6 = &ScatteredInformation::PaintShortTermException;
    v7 = ScatteredInformation::StripedSeries ^ 0x157E9386;
    for ( i = 0; i < 0x1E; i += 2 )
    {
      v9 = *((_DWORD *)v6++ + 1);
      v10 = (unsigned __int8)((v7 ^ v9) / 0x9D28AF) - i - 1;
      v11 = (unsigned __int8)(((unsigned int)v7 ^ *((_DWORD *)v6 - 2)) / 0x9D28AF) - i;
      *((_QWORD *)&ScatteredInformation::StripedSeries + v11 + 1) = *((_QWORD *)&ScatteredInformation::StripedSeries
                                                                    + v10
                                                                    + 1);
    }
    v17 = 0;
    v18 = 0x2F5FFFFF008080D0LL;
    v20[0] = 923746055;
    v12 = ScatteredInformation::StripedSeries ^ 0x157E9386;
    v19 = 0xEF8F2FCFF09060B0uLL;
    IntegralRelation::OddMap = ScatteredInformation::StripedSeries ^ 0x157E9386;
    v20[1] = 656355095;
    v20[2] = 906903046;
    v20[3] = 639512086;
    v20[4] = 890060037;
    v20[5] = 622669077;
    v20[6] = 873217028;
    v20[7] = 605826068;
    v20[8] = 856374019;
    v20[9] = 588983059;
    v20[10] = 839531010;
    v20[11] = 572140050;
    v20[12] = 822688001;
    v20[13] = 555297041;
    v20[14] = 805844992;
    v20[15] = 538454032;
    v21[0] = 923746055;
    v21[1] = 656355095;
    v21[2] = 906903046;
    v21[3] = 639512086;
    v21[4] = 890060037;
    v21[5] = 622669077;
    v21[6] = 873217028;
    v21[7] = 605826068;
    v21[8] = 856374019;
    v21[9] = 588983059;
    v21[10] = 839531010;
    v21[11] = 572140050;
    v21[12] = 822688001;
    v21[13] = 555297041;
    v21[14] = 805844992;
    v21[15] = 538454032;
    v13 = ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
            (__int64)&ScatteredInformation::StripedSeries,
            &v18,
            (__int64)v20)
        ^ 0xAAAAAAAA;
    v14 = ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
            (__int64)&ScatteredInformation::StripedSeries,
            &v19,
            (__int64)v21);
    _o__controlfp_s(&v17, (v14 ^ 0xAAAAAAAA) - v12, v13);
  }
  MixedProvider = (void (__fastcall *)(bool (__fastcall *)(const struct Input::ComplexAbstraction *), unsigned __int64, __int64))GenerateMixedProvider(0x1F1F3F7FE0607050LL, 4054106282LL, v5, v3);
  MixedProvider(
    Input::ImportantLicense::DecideOptimalCom,
    (unsigned __int64)Input::ImportantLicense::DecideOptimalCom ^ 0x163F7A,
    409450);
  return v4 > 1.0;
}

```

## disassembly

```asm
0x180019db0  mov     [rsp-8+arg_10], rbx
0x180019db5  push    rbp
0x180019db6  lea     rbp, [rsp-57h]
0x180019dbb  sub     rsp, 0E0h
0x180019dc2  movaps  [rsp+0E0h+var_10], xmm6
0x180019dca  mov     rax, cs:__security_cookie
0x180019dd1  xor     rax, rsp
0x180019dd4  mov     [rbp+57h+var_20], rax
0x180019dd8  mov     rbx, rcx
0x180019ddb  call    ?TransmitFlatMedia@?$IntegralSetting@M@Input@@QEBAMXZ; Input::IntegralSetting<float>::TransmitFlatMedia(void)
0x180019de0  movss   xmm1, dword ptr [rbx+8]
0x180019de5  movaps  xmm6, xmm0
0x180019de8  movss   xmm0, dword ptr [rbx]
0x180019dec  call    _o_atan2f_0
0x180019df1  addss   xmm0, xmm0; X
0x180019df5  call    _o_sinf_0
0x180019dfa  mov     r8d, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x180019e01  mov     eax, 47CCA855h
0x180019e06  andps   xmm0, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x180019e0d  movaps  xmm1, xmm6
0x180019e10  mulss   xmm1, cs:__real@3e95f535
0x180019e18  mov     ecx, r8d
0x180019e1b  xor     ecx, 0E82F4817h
0x180019e21  mul     ecx
0x180019e23  mulss   xmm0, xmm1
0x180019e27  mov     rax, [rbp+5Fh]
0x180019e2b  sub     ecx, edx
0x180019e2d  subss   xmm6, xmm0
0x180019e31  shr     ecx, 1
0x180019e33  add     ecx, edx
0x180019e35  shr     ecx, 14h
0x180019e38  cmp     [rax], cl
0x180019e3a  jz      short loc_180019E50
0x180019e3c  xor     r8d, 0FB844688h
0x180019e43  cmp     r8d, 412ADBh
0x180019e4a  jz      loc_18001A02E
0x180019e50  mov     r11d, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180019e57  lea     r10, ?PaintShortTermException@ScatteredInformation@@2QBIB; uint const near * const ScatteredInformation::PaintShortTermException
0x180019e5e  mov     [rsp+0E0h+arg_0], rsi
0x180019e66  xor     r11d, 157E9386h
0x180019e6d  xor     r9d, r9d
0x180019e70  mov     [rsp+0E0h+arg_8], rdi
0x180019e78  lea     rsi, ?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180019e7f  nop
0x180019e80  mov     ecx, [r10+4]
0x180019e84  lea     r10, [r10+8]
0x180019e88  xor     ecx, r11d
0x180019e8b  mov     eax, 68404C21h
0x180019e90  mul     ecx
0x180019e92  mov     ecx, [r10-8]
0x180019e96  mov     eax, 68404C21h
0x180019e9b  xor     ecx, r11d
0x180019e9e  shr     edx, 16h
0x180019ea1  movzx   r8d, dl
0x180019ea5  mul     ecx
0x180019ea7  sub     r8d, r9d
0x180019eaa  shr     edx, 16h
0x180019ead  dec     r8d
0x180019eb0  movzx   ecx, dl
0x180019eb3  sub     ecx, r9d
0x180019eb6  add     r9d, 2
0x180019eba  mov     rax, [rsi+r8*8+8]
0x180019ebf  mov     [rsi+rcx*8+8], rax
0x180019ec4  cmp     r9d, 1Eh
0x180019ec8  jb      short loc_180019E80
0x180019eca  mov     edi, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180019ed0  lea     r8, [rbp+57h+var_A0]
0x180019ed4  mov     rax, 2F5FFFFF008080D0h
0x180019ede  mov     [rbp+57h+var_C0], 0
0x180019ee5  mov     [rbp+57h+var_B8], rax
0x180019ee9  lea     rdx, [rbp+57h+var_B8]
0x180019eed  mov     rax, 0EF8F2FCFF09060B0h
0x180019ef7  mov     [rbp+57h+var_A0], 370F3F07h
0x180019efe  xor     edi, 157E9386h
0x180019f04  mov     [rbp+57h+var_B0], rax
0x180019f08  mov     rcx, rsi
0x180019f0b  mov     cs:?OddMap@IntegralRelation@@2IA, edi; uint IntegralRelation::OddMap
0x180019f11  mov     [rbp+57h+var_9C], 271F2F17h
0x180019f18  mov     [rbp+57h+var_98], 360E3E06h
0x180019f1f  mov     [rbp+57h+var_94], 261E2E16h
0x180019f26  mov     [rbp+57h+var_90], 350D3D05h
0x180019f2d  mov     [rbp+57h+var_8C], 251D2D15h
0x180019f34  mov     [rbp+57h+var_88], 340C3C04h
0x180019f3b  mov     [rbp+57h+var_84], 241C2C14h
0x180019f42  mov     [rbp+57h+var_80], 330B3B03h
0x180019f49  mov     [rbp+57h+var_7C], 231B2B13h
0x180019f50  mov     [rbp+57h+var_78], 320A3A02h
0x180019f57  mov     [rbp+57h+var_74], 221A2A12h
0x180019f5e  mov     [rbp+57h+var_70], 31093901h
0x180019f65  mov     [rbp+57h+var_6C], 21192911h
0x180019f6c  mov     [rbp+57h+var_68], 30083800h
0x180019f73  mov     [rbp+57h+var_64], 20182810h
0x180019f7a  mov     [rbp+57h+var_60], 370F3F07h
0x180019f81  mov     [rbp+57h+var_5C], 271F2F17h
0x180019f88  mov     [rbp+57h+var_58], 360E3E06h
0x180019f8f  mov     [rbp+57h+var_54], 261E2E16h
0x180019f96  mov     [rbp+57h+var_50], 350D3D05h
0x180019f9d  mov     [rbp+57h+var_4C], 251D2D15h
0x180019fa4  mov     [rbp+57h+var_48], 340C3C04h
0x180019fab  mov     [rbp+57h+var_44], 241C2C14h
0x180019fb2  mov     [rbp+57h+var_40], 330B3B03h
0x180019fb9  mov     [rbp+57h+var_3C], 231B2B13h
0x180019fc0  mov     [rbp+57h+var_38], 320A3A02h
0x180019fc7  mov     [rbp+57h+var_34], 221A2A12h
0x180019fce  mov     [rbp+57h+var_30], 31093901h
0x180019fd5  mov     [rbp+57h+var_2C], 21192911h
0x180019fdc  mov     [rbp+57h+var_28], 30083800h
0x180019fe3  mov     [rbp+57h+var_24], 20182810h
0x180019fea  call    ??$WriteConstructStrategy@_K$0EA@@ScatteredInformation@@AEBA_KAEB_KAEAY0EA@$$CBE@Z; ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(unsigned __int64 const &,uchar const (&)[64])
0x180019fef  mov     rbx, rax
0x180019ff2  lea     r8, [rbp+57h+var_60]
0x180019ff6  lea     rdx, [rbp+57h+var_B0]
0x180019ffa  mov     rcx, rsi
0x180019ffd  xor     ebx, 0AAAAAAAAh
0x18001a003  call    ??$WriteConstructStrategy@_K$0EA@@ScatteredInformation@@AEBA_KAEB_KAEAY0EA@$$CBE@Z; ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(unsigned __int64 const &,uchar const (&)[64])
0x18001a008  xor     eax, 0AAAAAAAAh
0x18001a00d  lea     rcx, [rbp+57h+var_C0]
0x18001a011  sub     eax, edi
0x18001a013  mov     r8d, ebx
0x18001a016  mov     edx, eax
0x18001a018  call    cs:__imp__o__controlfp_s
0x18001a01e  mov     rdi, [rsp+0E0h+arg_8]
0x18001a026  mov     rsi, [rsp+0E0h+arg_0]
0x18001a02e  mov     edx, 0F1A4C0AAh
0x18001a033  mov     rcx, 1F1F3F7FE0607050h
0x18001a03d  call    GenerateMixedProvider
0x18001a042  lea     rdx, ?DecideOptimalCom@ImportantLicense@Input@@SA_NAEBVComplexAbstraction@2@@Z; Input::ImportantLicense::DecideOptimalCom(Input::ComplexAbstraction const &)
0x18001a049  mov     r8d, 63F6Ah
0x18001a04f  xor     rdx, 163F7Ah
0x18001a056  lea     rcx, ?DecideOptimalCom@ImportantLicense@Input@@SA_NAEBVComplexAbstraction@2@@Z; Input::ImportantLicense::DecideOptimalCom(Input::ComplexAbstraction const &)
0x18001a05d  call    cs:__guard_dispatch_icall_fptr
0x18001a063  comiss  xmm6, cs:__real@3f800000
0x18001a06a  setnbe  al
0x18001a06d  mov     rcx, [rbp+57h+var_20]
0x18001a071  xor     rcx, rsp; StackCookie
0x18001a074  call    __security_check_cookie
0x18001a079  mov     rbx, [rsp+0E0h+arg_10]
0x18001a081  movaps  xmm6, [rsp+0E0h+var_10]
0x18001a089  add     rsp, 0E0h
0x18001a090  pop     rbp
0x18001a091  retn
```
