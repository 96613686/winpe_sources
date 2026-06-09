# Input::VirtualFeature::LinkScatteredAbstraction(Input::GeneralEvent &,Input::PartialMessage &,Input::DerivativeFilter &)

- ea: `0x180036a30`
- end: `0x180036d41`
- name: `?LinkScatteredAbstraction@VirtualFeature@Input@@QEAAMAEAVGeneralEvent@2@AEAVPartialMessage@2@AEAVDerivativeFilter@2@@Z`
- size: `785`
- prototype: `float __fastcall(Input::VirtualFeature *__hidden this, struct Input::GeneralEvent *, struct Input::PartialMessage *, struct Input::DerivativeFilter *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18003b3e0`

## callees

- `0x180003180`
- `0x180007b70`
- `0x18000e4b0`
- `0x180036a30`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__controlfp_s` at `0x180036c98`
- `api-ms-win-crt-private-l1-1-0!_o__controlfp_s` at `0x180036c98`

## pseudocode

```c
void __fastcall Input::VirtualFeature::LinkScatteredAbstraction(
        Input::VirtualFeature *this,
        struct Input::GeneralEvent *a2,
        struct Input::PartialMessage *a3,
        struct Input::DerivativeFilter *a4)
{
  __int64 v7; // r8
  const unsigned int near *const *v8; // r11
  int v9; // r10d
  unsigned int i; // r9d
  unsigned int v11; // ecx
  __int64 v12; // r8
  __int64 v13; // rcx
  int v14; // edi
  unsigned int v15; // ebx
  int v16; // eax
  void (__fastcall *MixedProvider)(float (__fastcall *)(Input::VirtualFeature *__hidden, struct Input::GeneralEvent *, struct Input::PartialMessage *, struct Input::DerivativeFilter *), unsigned __int64, __int64); // rax
  __int64 v18; // r8
  __int64 v19; // r9
  void (__fastcall *v20)(char *, struct Input::GeneralEvent *, _WORD *, char *, char *); // rax
  _WORD v21[4]; // [rsp+30h] [rbp-69h] BYREF
  int v22; // [rsp+38h] [rbp-61h] BYREF
  __int64 v23; // [rsp+40h] [rbp-59h] BYREF
  __int64 v24; // [rsp+48h] [rbp-51h] BYREF
  _DWORD v25[16]; // [rsp+50h] [rbp-49h] BYREF
  _DWORD v26[16]; // [rsp+90h] [rbp-9h] BYREF
  _BYTE *retaddr; // [rsp+F8h] [rbp+5Fh]

  v21[0] = *((_WORD *)a3 + 4);
  v21[1] = *((_WORD *)a3 + 5);
  v21[2] = *((_WORD *)a3 + 6);
  v21[3] = *((_WORD *)a3 + 7);
  if ( (IntegralRelation::OddMap ^ 0xFBF7CDAC) != 0x32A1FF
    || (v7 = (IntegralRelation::OddMap ^ 0xFE0A64EF) / 0x74A15, *retaddr == (_BYTE)v7) )
  {
    v8 = &ScatteredInformation::PaintShortTermException;
    v9 = ScatteredInformation::StripedSeries ^ 0x157E9386;
    for ( i = 0; i < 0x1E; i += 2 )
    {
      v11 = *((_DWORD *)v8++ + 1);
      v12 = (unsigned __int8)((v9 ^ v11) / 0x9D28AF) - i - 1;
      v13 = (unsigned __int8)(((unsigned int)v9 ^ *((_DWORD *)v8 - 2)) / 0x9D28AF) - i;
      *((_QWORD *)&ScatteredInformation::StripedSeries + v13 + 1) = *((_QWORD *)&ScatteredInformation::StripedSeries
                                                                    + v12
                                                                    + 1);
    }
    v22 = 0;
    v23 = 0x2F5FFFFF008080D0LL;
    v25[0] = 923746055;
    v14 = ScatteredInformation::StripedSeries ^ 0x157E9386;
    v24 = 0xEF8F2FCFF09060B0uLL;
    IntegralRelation::OddMap = ScatteredInformation::StripedSeries ^ 0x157E9386;
    v25[1] = 656355095;
    v25[2] = 906903046;
    v25[3] = 639512086;
    v25[4] = 890060037;
    v25[5] = 622669077;
    v25[6] = 873217028;
    v25[7] = 605826068;
    v25[8] = 856374019;
    v25[9] = 588983059;
    v25[10] = 839531010;
    v25[11] = 572140050;
    v25[12] = 822688001;
    v25[13] = 555297041;
    v25[14] = 805844992;
    v25[15] = 538454032;
    v26[0] = 923746055;
    v26[1] = 656355095;
    v26[2] = 906903046;
    v26[3] = 639512086;
    v26[4] = 890060037;
    v26[5] = 622669077;
    v26[6] = 873217028;
    v26[7] = 605826068;
    v26[8] = 856374019;
    v26[9] = 588983059;
    v26[10] = 839531010;
    v26[11] = 572140050;
    v26[12] = 822688001;
    v26[13] = 555297041;
    v26[14] = 805844992;
    v26[15] = 538454032;
    v15 = ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
            (__int64)&ScatteredInformation::StripedSeries,
            &v23,
            (__int64)v25)
        ^ 0xAAAAAAAA;
    v16 = ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
            (__int64)&ScatteredInformation::StripedSeries,
            &v24,
            (__int64)v26);
    _o__controlfp_s(&v22, (v16 ^ 0xAAAAAAAA) - v14, v15);
  }
  MixedProvider = (void (__fastcall *)(float (__fastcall *)(Input::VirtualFeature *__hidden, struct Input::GeneralEvent *, struct Input::PartialMessage *, struct Input::DerivativeFilter *), unsigned __int64, __int64))GenerateMixedProvider(0xBFBF3F1F40A00010uLL, 1359265994, v7, a4);
  MixedProvider(
    Input::VirtualFeature::LinkScatteredAbstraction,
    (unsigned __int64)Input::VirtualFeature::LinkScatteredAbstraction ^ 0x11D295,
    119429);
  v20 = (void (__fastcall *)(char *, struct Input::GeneralEvent *, _WORD *, char *, char *))GenerateMixedProvider(
                                                                                              0x3F1F9FBF00A06040LL,
                                                                                              3517210730LL,
                                                                                              v18,
                                                                                              v19);
  v20((char *)this + 198336, a2, v21, (char *)a4 + 16, (char *)a4 + 24);
}

```

## disassembly

```asm
0x180036a30  mov     [rsp-8+arg_18], rsi
0x180036a35  push    rbp
0x180036a36  push    r14
0x180036a38  push    r15
0x180036a3a  lea     rbp, [rsp-47h]
0x180036a3f  sub     rsp, 0E0h
0x180036a46  mov     rax, cs:__security_cookie
0x180036a4d  xor     rax, rsp
0x180036a50  mov     [rbp+57h+var_20], rax
0x180036a54  movzx   eax, word ptr [r8+8]
0x180036a59  mov     rsi, r9
0x180036a5c  mov     [rbp+57h+var_C0], ax
0x180036a60  mov     r14, rdx
0x180036a63  movzx   eax, word ptr [r8+0Ah]
0x180036a68  mov     r15, rcx
0x180036a6b  mov     [rbp+57h+var_BE], ax
0x180036a6f  movzx   eax, word ptr [r8+0Ch]
0x180036a74  mov     [rbp+57h+var_BC], ax
0x180036a78  movzx   eax, word ptr [r8+0Eh]
0x180036a7d  mov     r8d, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x180036a84  mov     [rbp+57h+var_BA], ax
0x180036a88  mov     eax, r8d
0x180036a8b  xor     eax, 0FBF7CDACh
0x180036a90  cmp     eax, 32A1FFh
0x180036a95  jnz     short loc_180036AC0
0x180036a97  xor     r8d, 0FE0A64EFh
0x180036a9e  mov     eax, 18F4E189h
0x180036aa3  mul     r8d
0x180036aa6  mov     rax, [rbp+5Fh]
0x180036aaa  sub     r8d, edx
0x180036aad  shr     r8d, 1
0x180036ab0  add     r8d, edx
0x180036ab3  shr     r8d, 12h
0x180036ab7  cmp     [rax], r8b
0x180036aba  jnz     loc_180036CB6
0x180036ac0  mov     r10d, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180036ac7  lea     r11, ?PaintShortTermException@ScatteredInformation@@2QBIB; uint const near * const ScatteredInformation::PaintShortTermException
0x180036ace  mov     [rsp+0F0h+arg_0], rbx
0x180036ad6  xor     r10d, 157E9386h
0x180036add  mov     [rsp+0F0h+arg_8], rdi
0x180036ae5  xor     r9d, r9d
0x180036ae8  mov     [rsp+0F0h+arg_10], r12
0x180036af0  lea     r12, ?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180036af7  nop     word ptr [rax+rax+00000000h]
0x180036b00  mov     ecx, [r11+4]
0x180036b04  lea     r11, [r11+8]
0x180036b08  xor     ecx, r10d
0x180036b0b  mov     eax, 68404C21h
0x180036b10  mul     ecx
0x180036b12  mov     ecx, [r11-8]
0x180036b16  mov     eax, 68404C21h
0x180036b1b  xor     ecx, r10d
0x180036b1e  shr     edx, 16h
0x180036b21  movzx   r8d, dl
0x180036b25  mul     ecx
0x180036b27  sub     r8d, r9d
0x180036b2a  shr     edx, 16h
0x180036b2d  dec     r8d
0x180036b30  movzx   ecx, dl
0x180036b33  sub     ecx, r9d
0x180036b36  add     r9d, 2
0x180036b3a  mov     rax, [r12+r8*8+8]
0x180036b3f  mov     [r12+rcx*8+8], rax
0x180036b44  cmp     r9d, 1Eh
0x180036b48  jb      short loc_180036B00
0x180036b4a  mov     edi, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x180036b50  lea     r8, [rbp+57h+var_A0]
0x180036b54  mov     rax, 2F5FFFFF008080D0h
0x180036b5e  mov     [rbp+57h+var_B8], 0
0x180036b65  mov     [rbp+57h+var_B0], rax
0x180036b69  lea     rdx, [rbp+57h+var_B0]
0x180036b6d  mov     rax, 0EF8F2FCFF09060B0h
0x180036b77  mov     [rbp+57h+var_A0], 370F3F07h
0x180036b7e  xor     edi, 157E9386h
0x180036b84  mov     [rbp+57h+var_A8], rax
0x180036b88  mov     rcx, r12
0x180036b8b  mov     cs:?OddMap@IntegralRelation@@2IA, edi; uint IntegralRelation::OddMap
0x180036b91  mov     [rbp+57h+var_9C], 271F2F17h
0x180036b98  mov     [rbp+57h+var_98], 360E3E06h
0x180036b9f  mov     [rbp+57h+var_94], 261E2E16h
0x180036ba6  mov     [rbp+57h+var_90], 350D3D05h
0x180036bad  mov     [rbp+57h+var_8C], 251D2D15h
0x180036bb4  mov     [rbp+57h+var_88], 340C3C04h
0x180036bbb  mov     [rbp+57h+var_84], 241C2C14h
0x180036bc2  mov     [rbp+57h+var_80], 330B3B03h
0x180036bc9  mov     [rbp+57h+var_7C], 231B2B13h
0x180036bd0  mov     [rbp+57h+var_78], 320A3A02h
0x180036bd7  mov     [rbp+57h+var_74], 221A2A12h
0x180036bde  mov     [rbp+57h+var_70], 31093901h
0x180036be5  mov     [rbp+57h+var_6C], 21192911h
0x180036bec  mov     [rbp+57h+var_68], 30083800h
0x180036bf3  mov     [rbp+57h+var_64], 20182810h
0x180036bfa  mov     [rbp+57h+var_60], 370F3F07h
0x180036c01  mov     [rbp+57h+var_5C], 271F2F17h
0x180036c08  mov     [rbp+57h+var_58], 360E3E06h
0x180036c0f  mov     [rbp+57h+var_54], 261E2E16h
0x180036c16  mov     [rbp+57h+var_50], 350D3D05h
0x180036c1d  mov     [rbp+57h+var_4C], 251D2D15h
0x180036c24  mov     [rbp+57h+var_48], 340C3C04h
0x180036c2b  mov     [rbp+57h+var_44], 241C2C14h
0x180036c32  mov     [rbp+57h+var_40], 330B3B03h
0x180036c39  mov     [rbp+57h+var_3C], 231B2B13h
0x180036c40  mov     [rbp+57h+var_38], 320A3A02h
0x180036c47  mov     [rbp+57h+var_34], 221A2A12h
0x180036c4e  mov     [rbp+57h+var_30], 31093901h
0x180036c55  mov     [rbp+57h+var_2C], 21192911h
0x180036c5c  mov     [rbp+57h+var_28], 30083800h
0x180036c63  mov     [rbp+57h+var_24], 20182810h
0x180036c6a  call    ??$WriteConstructStrategy@_K$0EA@@ScatteredInformation@@AEBA_KAEB_KAEAY0EA@$$CBE@Z; ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(unsigned __int64 const &,uchar const (&)[64])
0x180036c6f  mov     rbx, rax
0x180036c72  lea     r8, [rbp+57h+var_60]
0x180036c76  lea     rdx, [rbp+57h+var_A8]
0x180036c7a  mov     rcx, r12
0x180036c7d  xor     ebx, 0AAAAAAAAh
0x180036c83  call    ??$WriteConstructStrategy@_K$0EA@@ScatteredInformation@@AEBA_KAEB_KAEAY0EA@$$CBE@Z; ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(unsigned __int64 const &,uchar const (&)[64])
0x180036c88  xor     eax, 0AAAAAAAAh
0x180036c8d  lea     rcx, [rbp+57h+var_B8]
0x180036c91  sub     eax, edi
0x180036c93  mov     r8d, ebx
0x180036c96  mov     edx, eax
0x180036c98  call    cs:__imp__o__controlfp_s
0x180036c9e  mov     r12, [rsp+0F0h+arg_10]
0x180036ca6  mov     rdi, [rsp+0F0h+arg_8]
0x180036cae  mov     rbx, [rsp+0F0h+arg_0]
0x180036cb6  mov     edx, 5104C0CAh
0x180036cbb  mov     rcx, 0BFBF3F1F40A00010h
0x180036cc5  call    GenerateMixedProvider
0x180036cca  lea     rdx, ?LinkScatteredAbstraction@VirtualFeature@Input@@QEAAMAEAVGeneralEvent@2@AEAVPartialMessage@2@AEAVDerivativeFilter@2@@Z; Input::VirtualFeature::LinkScatteredAbstraction(Input::GeneralEvent &,Input::PartialMessage &,Input::DerivativeFilter &)
0x180036cd1  mov     r8d, 1D285h
0x180036cd7  xor     rdx, 11D295h
0x180036cde  lea     rcx, ?LinkScatteredAbstraction@VirtualFeature@Input@@QEAAMAEAVGeneralEvent@2@AEAVPartialMessage@2@AEAVDerivativeFilter@2@@Z; Input::VirtualFeature::LinkScatteredAbstraction(Input::GeneralEvent &,Input::PartialMessage &,Input::DerivativeFilter &)
0x180036ce5  call    cs:__guard_dispatch_icall_fptr
0x180036ceb  mov     edx, 0D1A4606Ah
0x180036cf0  mov     rcx, 3F1F9FBF00A06040h
0x180036cfa  call    GenerateMixedProvider
0x180036cff  lea     rdx, [rsi+18h]
0x180036d03  mov     [rsp+0F0h+var_D0], rdx
0x180036d08  lea     r9, [rsi+10h]
0x180036d0c  mov     rdx, r14
0x180036d0f  lea     rcx, [r15+306C0h]
0x180036d16  lea     r8, [rbp+57h+var_C0]
0x180036d1a  call    cs:__guard_dispatch_icall_fptr
0x180036d20  mov     rcx, [rbp+57h+var_20]
0x180036d24  xor     rcx, rsp; StackCookie
0x180036d27  call    __security_check_cookie
0x180036d2c  mov     rsi, [rsp+0F0h+arg_18]
0x180036d34  add     rsp, 0E0h
0x180036d3b  pop     r15
0x180036d3d  pop     r14
0x180036d3f  pop     rbp
0x180036d40  retn
```
